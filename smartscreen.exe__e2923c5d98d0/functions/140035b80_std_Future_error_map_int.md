# std::_Future_error_map(int)

- ea: `0x140035b80`
- end: `0x140035bb7`
- name: `?_Future_error_map@std@@YAPEBDH@Z`
- size: `55`
- prototype: `const char *__fastcall(int)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140036450`
- `0x1400365a0`

## callees

- `0x140035b80`

## string_xrefs

- `0x140035ba7`: `future already retrieved`
- `0x140035b9f`: `promise already satisfied`

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
0x140035b80  sub     ecx, 1
0x140035b83  jz      short loc_140035BAF
0x140035b85  sub     ecx, 1
0x140035b88  jz      short loc_140035BA7
0x140035b8a  sub     ecx, 1
0x140035b8d  jz      short loc_140035B9F
0x140035b8f  cmp     ecx, 1
0x140035b92  jz      short loc_140035B97
0x140035b94  xor     eax, eax
0x140035b96  retn
0x140035b97  lea     rax, aNoState; "no state"
0x140035b9e  retn
0x140035b9f  lea     rax, aPromiseAlready; "promise already satisfied"
0x140035ba6  retn
0x140035ba7  lea     rax, aFutureAlreadyR; "future already retrieved"
0x140035bae  retn
0x140035baf  lea     rax, aBrokenPromise; "broken promise"
0x140035bb6  retn
```
