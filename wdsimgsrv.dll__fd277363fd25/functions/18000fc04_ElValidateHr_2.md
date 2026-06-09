# ElValidateHr_2

- ea: `0x18000fc04`
- end: `0x18000fc51`
- name: `ElValidateHr_2`
- size: `77`
- prototype: ``
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x18000d39c`
- `0x18000d638`
- `0x18000d754`
- `0x18000d8c4`
- `0x18000d980`
- `0x18000db14`
- `0x18000f9f8`

## callees

- `0x180007ddc`
- `0x18000fc04`
- `0x18000fc58`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18000fc37`
- `KERNEL32!SetLastError` at `0x18000fc37`
- `KERNEL32!GetLastError` at `0x18000fc19`
- `KERNEL32!GetLastError` at `0x18000fc19`

## pseudocode

```c
__int64 __fastcall ElValidateHr_2(int a1)
{
  DWORD LastError; // edi

  ElValidateHrLite_2();
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
0x18000fc04  mov     [rsp+arg_0], rbx
0x18000fc09  push    rdi
0x18000fc0a  sub     rsp, 20h
0x18000fc0e  mov     ebx, ecx
0x18000fc10  call    ElValidateHrLite_2
0x18000fc15  test    ebx, ebx
0x18000fc17  jns     short loc_18000FC43
0x18000fc19  call    cs:__imp_GetLastError
0x18000fc20  nop     dword ptr [rax+rax+00h]
0x18000fc25  test    cs:?g_uErrLibFlags@@3KA, 1; ulong g_uErrLibFlags
0x18000fc2c  mov     edi, eax
0x18000fc2e  jz      short loc_18000FC35
0x18000fc30  call    ElTraceErrorInfo
0x18000fc35  mov     ecx, edi; dwErrCode
0x18000fc37  call    cs:__imp_SetLastError
0x18000fc3e  nop     dword ptr [rax+rax+00h]
0x18000fc43  mov     eax, ebx
0x18000fc45  mov     rbx, [rsp+28h+arg_0]
0x18000fc4a  add     rsp, 20h
0x18000fc4e  pop     rdi
0x18000fc4f  retn
```
