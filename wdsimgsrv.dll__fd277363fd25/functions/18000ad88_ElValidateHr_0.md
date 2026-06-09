# ElValidateHr_0

- ea: `0x18000ad88`
- end: `0x18000add5`
- name: `ElValidateHr_0`
- size: `77`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x1800081d0`
- `0x180008364`
- `0x180008494`
- `0x180009490`
- `0x1800096e8`

## callees

- `0x180007ddc`
- `0x18000ad88`
- `0x18000addc`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18000adbb`
- `KERNEL32!SetLastError` at `0x18000adbb`
- `KERNEL32!GetLastError` at `0x18000ad9d`
- `KERNEL32!GetLastError` at `0x18000ad9d`

## pseudocode

```c
__int64 __fastcall ElValidateHr_0(int a1, __int64 a2, __int64 a3, unsigned int a4)
{
  DWORD LastError; // edi

  ElValidateHrLite_0(a1, a2, a3, a4);
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
0x18000ad88  mov     [rsp+arg_0], rbx
0x18000ad8d  push    rdi
0x18000ad8e  sub     rsp, 20h
0x18000ad92  mov     ebx, ecx
0x18000ad94  call    ElValidateHrLite_0
0x18000ad99  test    ebx, ebx
0x18000ad9b  jns     short loc_18000ADC7
0x18000ad9d  call    cs:__imp_GetLastError
0x18000ada4  nop     dword ptr [rax+rax+00h]
0x18000ada9  test    cs:?g_uErrLibFlags@@3KA, 1; ulong g_uErrLibFlags
0x18000adb0  mov     edi, eax
0x18000adb2  jz      short loc_18000ADB9
0x18000adb4  call    ElTraceErrorInfo
0x18000adb9  mov     ecx, edi; dwErrCode
0x18000adbb  call    cs:__imp_SetLastError
0x18000adc2  nop     dword ptr [rax+rax+00h]
0x18000adc7  mov     eax, ebx
0x18000adc9  mov     rbx, [rsp+28h+arg_0]
0x18000adce  add     rsp, 20h
0x18000add2  pop     rdi
0x18000add3  retn
```
