# std::regex_error::_Stringify(std::regex_constants::error_type)

- ea: `0x14003070c`
- end: `0x1400307e7`
- name: `?_Stringify@regex_error@std@@CAPEBDW4error_type@regex_constants@2@@Z`
- size: `219`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140030868`

## callees

- `0x14003070c`

## string_xrefs

- `0x1400307c4`: `regex_error(error_complexity): The complexity of an attempted match against a regular expression exceeded a pre-set level.`

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
0x14003070c  cmp     ecx, 7
0x14003070f  jg      short loc_14003077D
0x140030711  jz      short loc_140030774
0x140030713  test    ecx, ecx
0x140030715  jz      short loc_14003076B
0x140030717  sub     ecx, 1
0x14003071a  jz      short loc_140030762
0x14003071c  sub     ecx, 1
0x14003071f  jz      short loc_140030759
0x140030721  sub     ecx, 1
0x140030724  jz      short loc_140030750
0x140030726  sub     ecx, 1
0x140030729  jz      short loc_140030747
0x14003072b  sub     ecx, 1
0x14003072e  jz      short loc_14003073E
0x140030730  cmp     ecx, 1
0x140030733  jnz     short loc_1400307A0
0x140030735  lea     rax, aRegexErrorErro_2; "regex_error(error_brace): The expressio"...
0x14003073c  retn
0x14003073e  lea     rax, aRegexErrorErro_13; "regex_error(error_paren): The expressio"...
0x140030745  retn
0x140030747  lea     rax, aRegexErrorErro_0; "regex_error(error_brack): The expressio"...
0x14003074e  retn
0x140030750  lea     rax, aRegexErrorErro_10; "regex_error(error_backref): The express"...
0x140030757  retn
0x140030759  lea     rax, aRegexErrorErro_12; "regex_error(error_escape): The expressi"...
0x140030760  retn
0x140030762  lea     rax, aRegexErrorErro_7; "regex_error(error_ctype): The expressio"...
0x140030769  retn
0x14003076b  lea     rax, aRegexErrorErro; "regex_error(error_collate): The express"...
0x140030772  retn
0x140030774  lea     rax, aRegexErrorErro_3; "regex_error(error_badbrace): The expres"...
0x14003077b  retn
0x14003077d  sub     ecx, 8
0x140030780  jz      short loc_1400307DF
0x140030782  sub     ecx, 1
0x140030785  jz      short loc_1400307D6
0x140030787  sub     ecx, 1
0x14003078a  jz      short loc_1400307CD
0x14003078c  sub     ecx, 1
0x14003078f  jz      short loc_1400307C4
0x140030791  sub     ecx, 1
0x140030794  jz      short loc_1400307BB
0x140030796  sub     ecx, 1
0x140030799  jz      short loc_1400307B2
0x14003079b  cmp     ecx, 1
0x14003079e  jz      short loc_1400307A9
0x1400307a0  lea     rax, aRegexError; "regex_error"
0x1400307a7  retn
0x1400307a9  lea     rax, aRegexErrorErro_11; "regex_error(error_syntax)"
0x1400307b0  retn
0x1400307b2  lea     rax, aRegexErrorErro_9; "regex_error(error_parse)"
0x1400307b9  retn
0x1400307bb  lea     rax, aRegexErrorErro_6; "regex_error(error_stack): There was ins"...
0x1400307c2  retn
0x1400307c4  lea     rax, aRegexErrorErro_1; "regex_error(error_complexity): The comp"...
0x1400307cb  retn
0x1400307cd  lea     rax, aRegexErrorErro_5; "regex_error(error_badrepeat): One of *?"...
0x1400307d4  retn
0x1400307d6  lea     rax, aRegexErrorErro_8; "regex_error(error_space): There was ins"...
0x1400307dd  retn
0x1400307df  lea     rax, aRegexErrorErro_4; "regex_error(error_range): The expressio"...
0x1400307e6  retn
```
