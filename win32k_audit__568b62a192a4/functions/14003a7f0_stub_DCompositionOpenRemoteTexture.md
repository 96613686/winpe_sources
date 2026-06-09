# _stub_DCompositionOpenRemoteTexture

- ea: `0x14003a7f0`
- end: `0x14003a897`
- name: `_stub_DCompositionOpenRemoteTexture`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x14003a7f0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003a839`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003a839`

## string_xrefs

- `0x14003a81f`: `NtDCompositionOpenRemoteTexture`

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
0x14003a7f0  sub     rsp, 48h
0x14003a7f4  mov     [rsp+48h+var_28], rcx
0x14003a7f9  mov     [rsp+48h+var_20], rdx
0x14003a7fe  mov     [rsp+48h+var_18], r8
0x14003a803  mov     [rsp+48h+var_10], r9
0x14003a808  mov     rcx, 132h
0x14003a80f  call    cs:__imp_IsWin32KSyscallFiltered
0x14003a816  nop     dword ptr [rax+rax+00h]
0x14003a81b  test    al, al
0x14003a81d  jz      short loc_14003A873
0x14003a81f  lea     rcx, aNtdcomposition_30; "NtDCompositionOpenRemoteTexture"
0x14003a826  mov     rdx, 132h
0x14003a82d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x14003a834  nop     dword ptr [rax+rax+00h]
0x14003a839  call    cs:__imp_PsIsWin32KFilterEnabled
0x14003a840  nop     dword ptr [rax+rax+00h]
0x14003a845  test    al, al
0x14003a847  jz      short loc_14003A873
0x14003a849  lea     rcx, W32pServiceTableFilter
0x14003a850  mov     edx, cs:W32pServiceLimitFilter
0x14003a856  mov     rax, 132h
0x14003a85d  lea     rcx, [rcx+rdx*4]
0x14003a861  movsx   eax, byte ptr [rcx+rax]
0x14003a865  or      eax, eax
0x14003a867  jle     short loc_14003A86E
0x14003a869  mov     eax, 0C000001Ch
0x14003a86e  add     rsp, 48h
0x14003a872  retn
0x14003a873  mov     rax, cs:__imp_NtDCompositionOpenRemoteTexture
0x14003a87a  mov     rcx, [rsp+48h+var_28]
0x14003a87f  mov     rdx, [rsp+48h+var_20]
0x14003a884  mov     r8, [rsp+48h+var_18]
0x14003a889  mov     r9, [rsp+48h+var_10]
0x14003a88e  add     rsp, 48h
0x14003a892  jmp     rax
```
