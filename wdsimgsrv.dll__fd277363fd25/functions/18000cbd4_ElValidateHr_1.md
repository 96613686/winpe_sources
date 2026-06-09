# ElValidateHr_1

- ea: `0x18000cbd4`
- end: `0x18000cc21`
- name: `ElValidateHr_1`
- size: `77`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x18000b5b0`
- `0x18000b668`
- `0x18000b858`
- `0x18000baf8`
- `0x18000c0ec`
- `0x18000c69c`

## callees

- `0x180007ddc`
- `0x18000cbd4`
- `0x18000cc28`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18000cc07`
- `KERNEL32!SetLastError` at `0x18000cc07`
- `KERNEL32!GetLastError` at `0x18000cbe9`
- `KERNEL32!GetLastError` at `0x18000cbe9`

## pseudocode

```c
__int64 __fastcall ElValidateHr_1(int a1)
{
  DWORD LastError; // edi

  ElValidateHrLite_1();
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
0x18000cbd4  mov     [rsp+arg_0], rbx
0x18000cbd9  push    rdi
0x18000cbda  sub     rsp, 20h
0x18000cbde  mov     ebx, ecx
0x18000cbe0  call    ElValidateHrLite_1
0x18000cbe5  test    ebx, ebx
0x18000cbe7  jns     short loc_18000CC13
0x18000cbe9  call    cs:__imp_GetLastError
0x18000cbf0  nop     dword ptr [rax+rax+00h]
0x18000cbf5  test    cs:?g_uErrLibFlags@@3KA, 1; ulong g_uErrLibFlags
0x18000cbfc  mov     edi, eax
0x18000cbfe  jz      short loc_18000CC05
0x18000cc00  call    ElTraceErrorInfo
0x18000cc05  mov     ecx, edi; dwErrCode
0x18000cc07  call    cs:__imp_SetLastError
0x18000cc0e  nop     dword ptr [rax+rax+00h]
0x18000cc13  mov     eax, ebx
0x18000cc15  mov     rbx, [rsp+28h+arg_0]
0x18000cc1a  add     rsp, 20h
0x18000cc1e  pop     rdi
0x18000cc1f  retn
```
