# std::_Future_error_map(int)

- ea: `0x14003707c`
- end: `0x1400370b7`
- name: `?_Future_error_map@std@@YAPEBDH@Z`
- size: `59`
- prototype: `const char *__fastcall(int)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140037970`
- `0x140037ad0`

## callees

- `0x14003707c`

## string_xrefs

- `0x1400370a6`: `future already retrieved`
- `0x14003709d`: `promise already satisfied`

## pseudocode

```c
const char *__fastcall std::_Future_error_map(int a1)
{
  int v1; // ecx
  int v2; // ecx
  int v3; // ecx

  v1 = a1 - 1;
  if ( !v1 )
    return "broken promise";
  v2 = v1 - 1;
  if ( !v2 )
    return "future already retrieved";
  v3 = v2 - 1;
  if ( !v3 )
    return "promise already satisfied";
  if ( v3 == 1 )
    return "no state";
  return 0;
}

```

## disassembly

```asm
0x14003707c  sub     ecx, 1
0x14003707f  jz      short loc_1400370AF
0x140037081  sub     ecx, 1
0x140037084  jz      short loc_1400370A6
0x140037086  sub     ecx, 1
0x140037089  jz      short loc_14003709D
0x14003708b  cmp     ecx, 1
0x14003708e  jz      short loc_140037094
0x140037090  xor     eax, eax
0x140037092  retn
0x140037094  lea     rax, aNoState; "no state"
0x14003709b  retn
0x14003709d  lea     rax, aPromiseAlready; "promise already satisfied"
0x1400370a4  retn
0x1400370a6  lea     rax, aFutureAlreadyR; "future already retrieved"
0x1400370ad  retn
0x1400370af  lea     rax, aBrokenPromise; "broken promise"
0x1400370b6  retn
```
