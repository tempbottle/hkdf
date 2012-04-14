# HKDF [![Build Status](https://secure.travis-ci.org/jtdowney/hkdf.png?branch=master)](http://travis-ci.org/jtdowney/hkdf)

This is a ruby implementation of [RFC 5869](http://tools.ietf.org/html/rfc5869): HMAC-based Extract-and-Expand Key Derivation Function. The goal of HKDF is to take some source key material and generate suitable cryptographic keys from it.

## Usage

```ruby
hkdf = HKDF.new('source key material')
hkdf.next_bytes(32)
 => "\f#\xF4b\x98\x9B\x7Fw>|/|k\xF4k\xB7\xB9\x11e\xC5\x92\xD1\fH\xFDG\x94vt\xB4\x14\xCE"
```

The default algorithm is HMAC-SHA256, you can override this and other defaults by providing an options hash during construction.

```ruby
hkdf = HKDF.new('source key material', :salt => 'NaCl', :algorithm => 'SHA1', :info => 'the 411')
hkdf.next_bytes(16)
 => "\xC0<\x13\x85\x8C\x84z\xCE\xC7\xCE+\xFF\x1C\xEB\xE6\xBC"
```

## License

The HKDF gem is released under the [MIT license](http://www.opensource.org/licenses/MIT).
