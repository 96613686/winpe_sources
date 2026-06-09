# _stub_DCompositionCreateBufferCollection

- ea: `0x140039820`
- end: `0x1400398c7`
- name: `_stub_DCompositionCreateBufferCollection`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140039820`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140039869`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140039869`

## string_xrefs

- `0x14003984f`: `NtDCompositionCreateBufferCollection`

## pseudocode

```c
__int64 stub_DCompositionCreateBufferCollection()
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtDCompositionCreateBufferCollection();
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtDCompositionCreateBufferCollection();
  result = (unsigned int)*((char *)&W32pServiceTableFilter[35] + 4 * (unsigned int)W32pServiceLimitFilter + 3);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140039820  sub     rsp, 48h
0x140039824  mov     [rsp+48h+var_28], rcx
0x140039829  mov     [rsp+48h+var_20], rdx
0x14003982e  mov     [rsp+48h+var_18], r8
0x140039833  mov     [rsp+48h+var_10], r9
0x140039838  mov     rcx, 11Bh
0x14003983f  call    cs:__imp_IsWin32KSyscallFiltered
0x140039846  nop     dword ptr [rax+rax+00h]
0x14003984b  test    al, al
0x14003984d  jz      short loc_1400398A3
0x14003984f  lea     rcx, aNtdcomposition_7; "NtDCompositionCreateBufferCollection"
0x140039856  mov     rdx, 11Bh
0x14003985d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140039864  nop     dword ptr [rax+rax+00h]
0x140039869  call    cs:__imp_PsIsWin32KFilterEnabled
0x140039870  nop     dword ptr [rax+rax+00h]
0x140039875  test    al, al
0x140039877  jz      short loc_1400398A3
0x140039879  lea     rcx, W32pServiceTableFilter
0x140039880  mov     edx, cs:W32pServiceLimitFilter
0x140039886  mov     rax, 11Bh
0x14003988d  lea     rcx, [rcx+rdx*4]
0x140039891  movsx   eax, byte ptr [rcx+rax]
0x140039895  or      eax, eax
0x140039897  jle     short loc_14003989E
0x140039899  mov     eax, 0C000001Ch
0x14003989e  add     rsp, 48h
0x1400398a2  retn
0x1400398a3  mov     rax, cs:__imp_NtDCompositionCreateBufferCollection
0x1400398aa  mov     rcx, [rsp+48h+var_28]
0x1400398af  mov     rdx, [rsp+48h+var_20]
0x1400398b4  mov     r8, [rsp+48h+var_18]
0x1400398b9  mov     r9, [rsp+48h+var_10]
0x1400398be  add     rsp, 48h
0x1400398c2  jmp     rax
```
