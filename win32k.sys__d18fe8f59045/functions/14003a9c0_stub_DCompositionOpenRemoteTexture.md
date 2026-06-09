# _stub_DCompositionOpenRemoteTexture

- ea: `0x14003a9c0`
- end: `0x14003aa67`
- name: `_stub_DCompositionOpenRemoteTexture`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x14003a9c0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003aa09`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003aa09`

## string_xrefs

- `0x14003a9ef`: `NtDCompositionOpenRemoteTexture`

## pseudocode

```c
__int64 stub_DCompositionOpenRemoteTexture()
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtDCompositionOpenRemoteTexture();
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtDCompositionOpenRemoteTexture();
  result = (unsigned int)*((char *)&W32pServiceTableFilter[38] + 4 * (unsigned int)W32pServiceLimitFilter + 2);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x14003a9c0  sub     rsp, 48h
0x14003a9c4  mov     [rsp+48h+var_28], rcx
0x14003a9c9  mov     [rsp+48h+var_20], rdx
0x14003a9ce  mov     [rsp+48h+var_18], r8
0x14003a9d3  mov     [rsp+48h+var_10], r9
0x14003a9d8  mov     rcx, 132h
0x14003a9df  call    cs:__imp_IsWin32KSyscallFiltered
0x14003a9e6  nop     dword ptr [rax+rax+00h]
0x14003a9eb  test    al, al
0x14003a9ed  jz      short loc_14003AA43
0x14003a9ef  lea     rcx, aNtdcomposition_30; "NtDCompositionOpenRemoteTexture"
0x14003a9f6  mov     rdx, 132h
0x14003a9fd  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x14003aa04  nop     dword ptr [rax+rax+00h]
0x14003aa09  call    cs:__imp_PsIsWin32KFilterEnabled
0x14003aa10  nop     dword ptr [rax+rax+00h]
0x14003aa15  test    al, al
0x14003aa17  jz      short loc_14003AA43
0x14003aa19  lea     rcx, W32pServiceTableFilter
0x14003aa20  mov     edx, cs:W32pServiceLimitFilter
0x14003aa26  mov     rax, 132h
0x14003aa2d  lea     rcx, [rcx+rdx*4]
0x14003aa31  movsx   eax, byte ptr [rcx+rax]
0x14003aa35  or      eax, eax
0x14003aa37  jle     short loc_14003AA3E
0x14003aa39  mov     eax, 0C000001Ch
0x14003aa3e  add     rsp, 48h
0x14003aa42  retn
0x14003aa43  mov     rax, cs:__imp_NtDCompositionOpenRemoteTexture
0x14003aa4a  mov     rcx, [rsp+48h+var_28]
0x14003aa4f  mov     rdx, [rsp+48h+var_20]
0x14003aa54  mov     r8, [rsp+48h+var_18]
0x14003aa59  mov     r9, [rsp+48h+var_10]
0x14003aa5e  add     rsp, 48h
0x14003aa62  jmp     rax
```
