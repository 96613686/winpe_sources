# HrBool(int)

- ea: `0x180002fe8`
- end: `0x180003014`
- name: `?HrBool@@YAJH@Z`
- size: `44`
- prototype: `signed int __fastcall(int)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180003080`
- `0x1800035b0`
- `0x1800040c0`
- `0x180006b48`
- `0x180007c44`

## callees

- `0x180002fe8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002ff4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002ff4`

## pseudocode

```c
signed int __fastcall HrBool(int a1)
{
  signed int result; // eax

  if ( a1 )
    return 0;
  result = GetLastError();
  if ( !result )
    return -2147467259;
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180002fe8  sub     rsp, 28h
0x180002fec  test    ecx, ecx
0x180002fee  jz      short loc_180002FF4
0x180002ff0  xor     eax, eax
0x180002ff2  jmp     short loc_18000300F
0x180002ff4  call    cs:__imp_GetLastError
0x180002ffa  test    eax, eax
0x180002ffc  jnz     short loc_180003005
0x180002ffe  mov     eax, 80004005h
0x180003003  jmp     short loc_18000300F
0x180003005  jle     short loc_18000300F
0x180003007  movzx   eax, ax
0x18000300a  or      eax, 80070000h
0x18000300f  add     rsp, 28h
0x180003013  retn
```
