# _stub_DCompositionGetChannels

- ea: `0x14003a230`
- end: `0x14003a2d7`
- name: `_stub_DCompositionGetChannels`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x14003a230`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003a279`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003a279`

## string_xrefs

- `0x14003a25f`: `NtDCompositionGetChannels`

## pseudocode

```c
__int64 stub_DCompositionGetChannels()
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtDCompositionGetChannels();
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtDCompositionGetChannels();
  result = (unsigned int)*((char *)&W32pServiceTableFilter[36] + 4 * (unsigned int)W32pServiceLimitFilter + 7);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x14003a230  sub     rsp, 48h
0x14003a234  mov     [rsp+48h+var_28], rcx
0x14003a239  mov     [rsp+48h+var_20], rdx
0x14003a23e  mov     [rsp+48h+var_18], r8
0x14003a243  mov     [rsp+48h+var_10], r9
0x14003a248  mov     rcx, 127h
0x14003a24f  call    cs:__imp_IsWin32KSyscallFiltered
0x14003a256  nop     dword ptr [rax+rax+00h]
0x14003a25b  test    al, al
0x14003a25d  jz      short loc_14003A2B3
0x14003a25f  lea     rcx, aNtdcomposition_19; "NtDCompositionGetChannels"
0x14003a266  mov     rdx, 127h
0x14003a26d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x14003a274  nop     dword ptr [rax+rax+00h]
0x14003a279  call    cs:__imp_PsIsWin32KFilterEnabled
0x14003a280  nop     dword ptr [rax+rax+00h]
0x14003a285  test    al, al
0x14003a287  jz      short loc_14003A2B3
0x14003a289  lea     rcx, W32pServiceTableFilter
0x14003a290  mov     edx, cs:W32pServiceLimitFilter
0x14003a296  mov     rax, 127h
0x14003a29d  lea     rcx, [rcx+rdx*4]
0x14003a2a1  movsx   eax, byte ptr [rcx+rax]
0x14003a2a5  or      eax, eax
0x14003a2a7  jle     short loc_14003A2AE
0x14003a2a9  mov     eax, 0C000001Ch
0x14003a2ae  add     rsp, 48h
0x14003a2b2  retn
0x14003a2b3  mov     rax, cs:__imp_NtDCompositionGetChannels
0x14003a2ba  mov     rcx, [rsp+48h+var_28]
0x14003a2bf  mov     rdx, [rsp+48h+var_20]
0x14003a2c4  mov     r8, [rsp+48h+var_18]
0x14003a2c9  mov     r9, [rsp+48h+var_10]
0x14003a2ce  add     rsp, 48h
0x14003a2d2  jmp     rax
```
