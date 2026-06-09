# std::regex_error::_Stringify(std::regex_constants::error_type)

- ea: `0x14002f448`
- end: `0x14002f514`
- name: `?_Stringify@regex_error@std@@CAPEBDW4error_type@regex_constants@2@@Z`
- size: `204`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14002f594`

## callees

- `0x14002f448`

## string_xrefs

- `0x14002f4f4`: `regex_error(error_complexity): The complexity of an attempted match against a regular expression exceeded a pre-set level.`

## pseudocode

```c
const char *__fastcall std::regex_error::_Stringify(int a1)
{
  int v1; // ecx
  int v2; // ecx
  int v3; // ecx
  int v4; // ecx
  int v5; // ecx
  int v7; // ecx
  int v8; // ecx
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx

  if ( a1 <= 7 )
  {
    if ( a1 == 7 )
      return "regex_error(error_badbrace): The expression contained an invalid range in a {} expression.";
    if ( !a1 )
      return "regex_error(error_collate): The expression contained an invalid collating element name.";
    v1 = a1 - 1;
    if ( !v1 )
      return "regex_error(error_ctype): The expression contained an invalid character class name.";
    v2 = v1 - 1;
    if ( !v2 )
      return "regex_error(error_escape): The expression contained an invalid escaped character, or a trailing escape.";
    v3 = v2 - 1;
    if ( !v3 )
      return "regex_error(error_backref): The expression contained an invalid back reference.";
    v4 = v3 - 1;
    if ( !v4 )
      return "regex_error(error_brack): The expression contained mismatched [ and ].";
    v5 = v4 - 1;
    if ( !v5 )
      return "regex_error(error_paren): The expression contained mismatched ( and ).";
    if ( v5 == 1 )
      return "regex_error(error_brace): The expression contained mismatched { and }.";
    return "regex_error";
  }
  v7 = a1 - 8;
  if ( !v7 )
    return "regex_error(error_range): The expression contained an invalid character range, such as [b-a] in most encodings.";
  v8 = v7 - 1;
  if ( !v8 )
    return "regex_error(error_space): There was insufficient memory to convert the expression into a finite state machine.";
  v9 = v8 - 1;
  if ( !v9 )
    return "regex_error(error_badrepeat): One of *?+{ was not preceded by a valid regular expression.";
  v10 = v9 - 1;
  if ( !v10 )
    return "regex_error(error_complexity): The complexity of an attempted match against a regular expression exceeded a pre-set level.";
  v11 = v10 - 1;
  if ( !v11 )
    return "regex_error(error_stack): There was insufficient memory to determine whether the regular expression could mat"
           "ch the specified character sequence.";
  v12 = v11 - 1;
  if ( !v12 )
    return "regex_error(error_parse)";
  if ( v12 != 1 )
    return "regex_error";
  return "regex_error(error_syntax)";
}

```

## disassembly

```asm
0x14002f448  cmp     ecx, 7
0x14002f44b  jg      short loc_14002F4B1
0x14002f44d  jz      short loc_14002F4A9
0x14002f44f  test    ecx, ecx
0x14002f451  jz      short loc_14002F4A1
0x14002f453  sub     ecx, 1
0x14002f456  jz      short loc_14002F499
0x14002f458  sub     ecx, 1
0x14002f45b  jz      short loc_14002F491
0x14002f45d  sub     ecx, 1
0x14002f460  jz      short loc_14002F489
0x14002f462  sub     ecx, 1
0x14002f465  jz      short loc_14002F481
0x14002f467  sub     ecx, 1
0x14002f46a  jz      short loc_14002F479
0x14002f46c  cmp     ecx, 1
0x14002f46f  jnz     short loc_14002F4D4
0x14002f471  lea     rax, aRegexErrorErro_2; "regex_error(error_brace): The expressio"...
0x14002f478  retn
0x14002f479  lea     rax, aRegexErrorErro_13; "regex_error(error_paren): The expressio"...
0x14002f480  retn
0x14002f481  lea     rax, aRegexErrorErro_0; "regex_error(error_brack): The expressio"...
0x14002f488  retn
0x14002f489  lea     rax, aRegexErrorErro_10; "regex_error(error_backref): The express"...
0x14002f490  retn
0x14002f491  lea     rax, aRegexErrorErro_12; "regex_error(error_escape): The expressi"...
0x14002f498  retn
0x14002f499  lea     rax, aRegexErrorErro_7; "regex_error(error_ctype): The expressio"...
0x14002f4a0  retn
0x14002f4a1  lea     rax, aRegexErrorErro; "regex_error(error_collate): The express"...
0x14002f4a8  retn
0x14002f4a9  lea     rax, aRegexErrorErro_3; "regex_error(error_badbrace): The expres"...
0x14002f4b0  retn
0x14002f4b1  sub     ecx, 8
0x14002f4b4  jz      short loc_14002F50C
0x14002f4b6  sub     ecx, 1
0x14002f4b9  jz      short loc_14002F504
0x14002f4bb  sub     ecx, 1
0x14002f4be  jz      short loc_14002F4FC
0x14002f4c0  sub     ecx, 1
0x14002f4c3  jz      short loc_14002F4F4
0x14002f4c5  sub     ecx, 1
0x14002f4c8  jz      short loc_14002F4EC
0x14002f4ca  sub     ecx, 1
0x14002f4cd  jz      short loc_14002F4E4
0x14002f4cf  cmp     ecx, 1
0x14002f4d2  jz      short loc_14002F4DC
0x14002f4d4  lea     rax, aRegexError; "regex_error"
0x14002f4db  retn
0x14002f4dc  lea     rax, aRegexErrorErro_11; "regex_error(error_syntax)"
0x14002f4e3  retn
0x14002f4e4  lea     rax, aRegexErrorErro_9; "regex_error(error_parse)"
0x14002f4eb  retn
0x14002f4ec  lea     rax, aRegexErrorErro_6; "regex_error(error_stack): There was ins"...
0x14002f4f3  retn
0x14002f4f4  lea     rax, aRegexErrorErro_1; "regex_error(error_complexity): The comp"...
0x14002f4fb  retn
0x14002f4fc  lea     rax, aRegexErrorErro_5; "regex_error(error_badrepeat): One of *?"...
0x14002f503  retn
0x14002f504  lea     rax, aRegexErrorErro_8; "regex_error(error_space): There was ins"...
0x14002f50b  retn
0x14002f50c  lea     rax, aRegexErrorErro_4; "regex_error(error_range): The expressio"...
0x14002f513  retn
```
