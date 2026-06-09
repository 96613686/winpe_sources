# _stub_DCompositionGetConnectionBatch

- ea: `0x14003a110`
- end: `0x14003a1b7`
- name: `_stub_DCompositionGetConnectionBatch`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x14003a110`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003a159`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003a159`

## string_xrefs

- `0x14003a13f`: `NtDCompositionGetConnectionBatch`

## pseudocode

```c
__int64 stub_DCompositionGetConnectionBatch()
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtDCompositionGetConnectionBatch();
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtDCompositionGetConnectionBatch();
  result = (unsigned int)*((char *)&W32pServiceTableFilter[37] + 4 * (unsigned int)W32pServiceLimitFilter);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x14003a110  sub     rsp, 48h
0x14003a114  mov     [rsp+48h+var_28], rcx
0x14003a119  mov     [rsp+48h+var_20], rdx
0x14003a11e  mov     [rsp+48h+var_18], r8
0x14003a123  mov     [rsp+48h+var_10], r9
0x14003a128  mov     rcx, 128h
0x14003a12f  call    cs:__imp_IsWin32KSyscallFiltered
0x14003a136  nop     dword ptr [rax+rax+00h]
0x14003a13b  test    al, al
0x14003a13d  jz      short loc_14003A193
0x14003a13f  lea     rcx, aNtdcomposition_20; "NtDCompositionGetConnectionBatch"
0x14003a146  mov     rdx, 128h
0x14003a14d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x14003a154  nop     dword ptr [rax+rax+00h]
0x14003a159  call    cs:__imp_PsIsWin32KFilterEnabled
0x14003a160  nop     dword ptr [rax+rax+00h]
0x14003a165  test    al, al
0x14003a167  jz      short loc_14003A193
0x14003a169  lea     rcx, W32pServiceTableFilter
0x14003a170  mov     edx, cs:W32pServiceLimitFilter
0x14003a176  mov     rax, 128h
0x14003a17d  lea     rcx, [rcx+rdx*4]
0x14003a181  movsx   eax, byte ptr [rcx+rax]
0x14003a185  or      eax, eax
0x14003a187  jle     short loc_14003A18E
0x14003a189  mov     eax, 0C000001Ch
0x14003a18e  add     rsp, 48h
0x14003a192  retn
0x14003a193  mov     rax, cs:__imp_NtDCompositionGetConnectionBatch
0x14003a19a  mov     rcx, [rsp+48h+var_28]
0x14003a19f  mov     rdx, [rsp+48h+var_20]
0x14003a1a4  mov     r8, [rsp+48h+var_18]
0x14003a1a9  mov     r9, [rsp+48h+var_10]
0x14003a1ae  add     rsp, 48h
0x14003a1b2  jmp     rax
```
