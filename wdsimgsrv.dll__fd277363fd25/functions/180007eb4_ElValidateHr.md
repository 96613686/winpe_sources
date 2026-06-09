# ElValidateHr

- ea: `0x180007eb4`
- end: `0x180007f01`
- name: `ElValidateHr`
- size: `77`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `10`
- callee_count: `3`
- tags: ``

## callers

- `0x180002a0c`
- `0x180002e64`
- `0x1800036b0`
- `0x180003af4`
- `0x180003dc4`
- `0x180006020`
- `0x180006548`
- `0x180007120`
- `0x180007700`
- `0x180007880`

## callees

- `0x180007ddc`
- `0x180007eb4`
- `0x180007f08`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180007ee7`
- `KERNEL32!SetLastError` at `0x180007ee7`
- `KERNEL32!GetLastError` at `0x180007ec9`
- `KERNEL32!GetLastError` at `0x180007ec9`

## pseudocode

```c
__int64 __fastcall ElValidateHr(int a1)
{
  DWORD LastError; // edi

  ElValidateHrLite();
  if ( a1 < 0 )
  {
    LastError = GetLastError();
    if ( (g_uErrLibFlags & 1) != 0 )
      ElTraceErrorInfo();
    SetLastError(LastError);
  }
  return (unsigned int)a1;
}

```

## disassembly

```asm
0x180007eb4  mov     [rsp+arg_0], rbx
0x180007eb9  push    rdi
0x180007eba  sub     rsp, 20h
0x180007ebe  mov     ebx, ecx
0x180007ec0  call    ElValidateHrLite
0x180007ec5  test    ebx, ebx
0x180007ec7  jns     short loc_180007EF3
0x180007ec9  call    cs:__imp_GetLastError
0x180007ed0  nop     dword ptr [rax+rax+00h]
0x180007ed5  test    cs:?g_uErrLibFlags@@3KA, 1; ulong g_uErrLibFlags
0x180007edc  mov     edi, eax
0x180007ede  jz      short loc_180007EE5
0x180007ee0  call    ElTraceErrorInfo
0x180007ee5  mov     ecx, edi; dwErrCode
0x180007ee7  call    cs:__imp_SetLastError
0x180007eee  nop     dword ptr [rax+rax+00h]
0x180007ef3  mov     eax, ebx
0x180007ef5  mov     rbx, [rsp+28h+arg_0]
0x180007efa  add     rsp, 20h
0x180007efe  pop     rdi
0x180007eff  retn
```
