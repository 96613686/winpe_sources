# _stub_DCompositionRegisterThumbnailVisual

- ea: `0x14003ab20`
- end: `0x14003abc7`
- name: `_stub_DCompositionRegisterThumbnailVisual`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x14003ab20`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003ab69`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003ab69`

## string_xrefs

- `0x14003ab4f`: `NtDCompositionRegisterThumbnailVisual`

## pseudocode

```c
__int64 __fastcall stub_DCompositionRegisterThumbnailVisual(
        int a1,
        int a2,
        int a3,
        int a4,
        __int64 a5,
        __int64 a6,
        char a7,
        __int64 a8,
        __int64 a9)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtDCompositionRegisterThumbnailVisual(a1, a2, a3, a4, a5, a6, a7, a8, a9);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtDCompositionRegisterThumbnailVisual(a1, a2, a3, a4, a5, a6, a7, a8, a9);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[38] + 4 * (unsigned int)W32pServiceLimitFilter + 4);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x14003ab20  sub     rsp, 48h
0x14003ab24  mov     [rsp+48h+var_28], rcx
0x14003ab29  mov     [rsp+48h+var_20], rdx
0x14003ab2e  mov     [rsp+48h+var_18], r8
0x14003ab33  mov     [rsp+48h+var_10], r9
0x14003ab38  mov     rcx, 134h
0x14003ab3f  call    cs:__imp_IsWin32KSyscallFiltered
0x14003ab46  nop     dword ptr [rax+rax+00h]
0x14003ab4b  test    al, al
0x14003ab4d  jz      short loc_14003ABA3
0x14003ab4f  lea     rcx, aNtdcomposition_32; "NtDCompositionRegisterThumbnailVisual"
0x14003ab56  mov     rdx, 134h
0x14003ab5d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x14003ab64  nop     dword ptr [rax+rax+00h]
0x14003ab69  call    cs:__imp_PsIsWin32KFilterEnabled
0x14003ab70  nop     dword ptr [rax+rax+00h]
0x14003ab75  test    al, al
0x14003ab77  jz      short loc_14003ABA3
0x14003ab79  lea     rcx, W32pServiceTableFilter
0x14003ab80  mov     edx, cs:W32pServiceLimitFilter
0x14003ab86  mov     rax, 134h
0x14003ab8d  lea     rcx, [rcx+rdx*4]
0x14003ab91  movsx   eax, byte ptr [rcx+rax]
0x14003ab95  or      eax, eax
0x14003ab97  jle     short loc_14003AB9E
0x14003ab99  mov     eax, 0C000001Ch
0x14003ab9e  add     rsp, 48h
0x14003aba2  retn
0x14003aba3  mov     rax, cs:__imp_NtDCompositionRegisterThumbnailVisual
0x14003abaa  mov     rcx, [rsp+48h+var_28]
0x14003abaf  mov     rdx, [rsp+48h+var_20]
0x14003abb4  mov     r8, [rsp+48h+var_18]
0x14003abb9  mov     r9, [rsp+48h+var_10]
0x14003abbe  add     rsp, 48h
0x14003abc2  jmp     rax
```
