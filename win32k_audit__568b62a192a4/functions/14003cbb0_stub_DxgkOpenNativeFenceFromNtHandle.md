# _stub_DxgkOpenNativeFenceFromNtHandle

- ea: `0x14003cbb0`
- end: `0x14003cc57`
- name: `_stub_DxgkOpenNativeFenceFromNtHandle`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x14003cbb0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003cbf9`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003cbf9`
- `ext-ms-win-core-win32k-dxgk-l1-1-0!NtDxgkOpenNativeFenceFromNtHandle` at `0x14003cc33`

## string_xrefs

- `0x14003cbdf`: `NtDxgkOpenNativeFenceFromNtHandle`

## pseudocode

```c
__int64 __fastcall stub_DxgkOpenNativeFenceFromNtHandle(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtDxgkOpenNativeFenceFromNtHandle(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtDxgkOpenNativeFenceFromNtHandle(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[44] + 4 * (unsigned int)W32pServiceLimitFilter + 6);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x14003cbb0  sub     rsp, 48h
0x14003cbb4  mov     [rsp+48h+var_28], rcx
0x14003cbb9  mov     [rsp+48h+var_20], rdx
0x14003cbbe  mov     [rsp+48h+var_18], r8
0x14003cbc3  mov     [rsp+48h+var_10], r9
0x14003cbc8  mov     rcx, 166h
0x14003cbcf  call    cs:__imp_IsWin32KSyscallFiltered
0x14003cbd6  nop     dword ptr [rax+rax+00h]
0x14003cbdb  test    al, al
0x14003cbdd  jz      short loc_14003CC33
0x14003cbdf  lea     rcx, aNtdxgkopennati; "NtDxgkOpenNativeFenceFromNtHandle"
0x14003cbe6  mov     rdx, 166h
0x14003cbed  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x14003cbf4  nop     dword ptr [rax+rax+00h]
0x14003cbf9  call    cs:__imp_PsIsWin32KFilterEnabled
0x14003cc00  nop     dword ptr [rax+rax+00h]
0x14003cc05  test    al, al
0x14003cc07  jz      short loc_14003CC33
0x14003cc09  lea     rcx, W32pServiceTableFilter
0x14003cc10  mov     edx, cs:W32pServiceLimitFilter
0x14003cc16  mov     rax, 166h
0x14003cc1d  lea     rcx, [rcx+rdx*4]
0x14003cc21  movsx   eax, byte ptr [rcx+rax]
0x14003cc25  or      eax, eax
0x14003cc27  jle     short loc_14003CC2E
0x14003cc29  mov     eax, 0C000001Ch
0x14003cc2e  add     rsp, 48h
0x14003cc32  retn
0x14003cc33  mov     rax, cs:__imp_NtDxgkOpenNativeFenceFromNtHandle
0x14003cc3a  mov     rcx, [rsp+48h+var_28]
0x14003cc3f  mov     rdx, [rsp+48h+var_20]
0x14003cc44  mov     r8, [rsp+48h+var_18]
0x14003cc49  mov     r9, [rsp+48h+var_10]
0x14003cc4e  add     rsp, 48h
0x14003cc52  jmp     rax
```
