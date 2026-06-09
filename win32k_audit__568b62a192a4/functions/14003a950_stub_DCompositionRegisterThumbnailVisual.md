# _stub_DCompositionRegisterThumbnailVisual

- ea: `0x14003a950`
- end: `0x14003a9f7`
- name: `_stub_DCompositionRegisterThumbnailVisual`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x14003a950`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003a999`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003a999`

## string_xrefs

- `0x14003a97f`: `NtDCompositionRegisterThumbnailVisual`

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
0x14003a950  sub     rsp, 48h
0x14003a954  mov     [rsp+48h+var_28], rcx
0x14003a959  mov     [rsp+48h+var_20], rdx
0x14003a95e  mov     [rsp+48h+var_18], r8
0x14003a963  mov     [rsp+48h+var_10], r9
0x14003a968  mov     rcx, 134h
0x14003a96f  call    cs:__imp_IsWin32KSyscallFiltered
0x14003a976  nop     dword ptr [rax+rax+00h]
0x14003a97b  test    al, al
0x14003a97d  jz      short loc_14003A9D3
0x14003a97f  lea     rcx, aNtdcomposition_32; "NtDCompositionRegisterThumbnailVisual"
0x14003a986  mov     rdx, 134h
0x14003a98d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x14003a994  nop     dword ptr [rax+rax+00h]
0x14003a999  call    cs:__imp_PsIsWin32KFilterEnabled
0x14003a9a0  nop     dword ptr [rax+rax+00h]
0x14003a9a5  test    al, al
0x14003a9a7  jz      short loc_14003A9D3
0x14003a9a9  lea     rcx, W32pServiceTableFilter
0x14003a9b0  mov     edx, cs:W32pServiceLimitFilter
0x14003a9b6  mov     rax, 134h
0x14003a9bd  lea     rcx, [rcx+rdx*4]
0x14003a9c1  movsx   eax, byte ptr [rcx+rax]
0x14003a9c5  or      eax, eax
0x14003a9c7  jle     short loc_14003A9CE
0x14003a9c9  mov     eax, 0C000001Ch
0x14003a9ce  add     rsp, 48h
0x14003a9d2  retn
0x14003a9d3  mov     rax, cs:__imp_NtDCompositionRegisterThumbnailVisual
0x14003a9da  mov     rcx, [rsp+48h+var_28]
0x14003a9df  mov     rdx, [rsp+48h+var_20]
0x14003a9e4  mov     r8, [rsp+48h+var_18]
0x14003a9e9  mov     r9, [rsp+48h+var_10]
0x14003a9ee  add     rsp, 48h
0x14003a9f2  jmp     rax
```
