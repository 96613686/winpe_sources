# _stub_DCompositionReleaseRemoteTexture

- ea: `0x14003ad30`
- end: `0x14003add7`
- name: `_stub_DCompositionReleaseRemoteTexture`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x14003ad30`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003ad79`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003ad79`

## string_xrefs

- `0x14003ad5f`: `NtDCompositionReleaseRemoteTexture`

## pseudocode

```c
__int64 stub_DCompositionReleaseRemoteTexture()
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtDCompositionReleaseRemoteTexture();
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtDCompositionReleaseRemoteTexture();
  result = (unsigned int)*((char *)&W32pServiceTableFilter[38] + 4 * (unsigned int)W32pServiceLimitFilter + 7);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x14003ad30  sub     rsp, 48h
0x14003ad34  mov     [rsp+48h+var_28], rcx
0x14003ad39  mov     [rsp+48h+var_20], rdx
0x14003ad3e  mov     [rsp+48h+var_18], r8
0x14003ad43  mov     [rsp+48h+var_10], r9
0x14003ad48  mov     rcx, 137h
0x14003ad4f  call    cs:__imp_IsWin32KSyscallFiltered
0x14003ad56  nop     dword ptr [rax+rax+00h]
0x14003ad5b  test    al, al
0x14003ad5d  jz      short loc_14003ADB3
0x14003ad5f  lea     rcx, aNtdcomposition_35; "NtDCompositionReleaseRemoteTexture"
0x14003ad66  mov     rdx, 137h
0x14003ad6d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x14003ad74  nop     dword ptr [rax+rax+00h]
0x14003ad79  call    cs:__imp_PsIsWin32KFilterEnabled
0x14003ad80  nop     dword ptr [rax+rax+00h]
0x14003ad85  test    al, al
0x14003ad87  jz      short loc_14003ADB3
0x14003ad89  lea     rcx, W32pServiceTableFilter
0x14003ad90  mov     edx, cs:W32pServiceLimitFilter
0x14003ad96  mov     rax, 137h
0x14003ad9d  lea     rcx, [rcx+rdx*4]
0x14003ada1  movsx   eax, byte ptr [rcx+rax]
0x14003ada5  or      eax, eax
0x14003ada7  jle     short loc_14003ADAE
0x14003ada9  mov     eax, 0C000001Ch
0x14003adae  add     rsp, 48h
0x14003adb2  retn
0x14003adb3  mov     rax, cs:__imp_NtDCompositionReleaseRemoteTexture
0x14003adba  mov     rcx, [rsp+48h+var_28]
0x14003adbf  mov     rdx, [rsp+48h+var_20]
0x14003adc4  mov     r8, [rsp+48h+var_18]
0x14003adc9  mov     r9, [rsp+48h+var_10]
0x14003adce  add     rsp, 48h
0x14003add2  jmp     rax
```
