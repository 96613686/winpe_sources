# _stub_DCompositionReleaseRemoteTexture

- ea: `0x14003ab60`
- end: `0x14003ac07`
- name: `_stub_DCompositionReleaseRemoteTexture`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x14003ab60`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003aba9`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003aba9`

## string_xrefs

- `0x14003ab8f`: `NtDCompositionReleaseRemoteTexture`

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
0x14003ab60  sub     rsp, 48h
0x14003ab64  mov     [rsp+48h+var_28], rcx
0x14003ab69  mov     [rsp+48h+var_20], rdx
0x14003ab6e  mov     [rsp+48h+var_18], r8
0x14003ab73  mov     [rsp+48h+var_10], r9
0x14003ab78  mov     rcx, 137h
0x14003ab7f  call    cs:__imp_IsWin32KSyscallFiltered
0x14003ab86  nop     dword ptr [rax+rax+00h]
0x14003ab8b  test    al, al
0x14003ab8d  jz      short loc_14003ABE3
0x14003ab8f  lea     rcx, aNtdcomposition_35; "NtDCompositionReleaseRemoteTexture"
0x14003ab96  mov     rdx, 137h
0x14003ab9d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x14003aba4  nop     dword ptr [rax+rax+00h]
0x14003aba9  call    cs:__imp_PsIsWin32KFilterEnabled
0x14003abb0  nop     dword ptr [rax+rax+00h]
0x14003abb5  test    al, al
0x14003abb7  jz      short loc_14003ABE3
0x14003abb9  lea     rcx, W32pServiceTableFilter
0x14003abc0  mov     edx, cs:W32pServiceLimitFilter
0x14003abc6  mov     rax, 137h
0x14003abcd  lea     rcx, [rcx+rdx*4]
0x14003abd1  movsx   eax, byte ptr [rcx+rax]
0x14003abd5  or      eax, eax
0x14003abd7  jle     short loc_14003ABDE
0x14003abd9  mov     eax, 0C000001Ch
0x14003abde  add     rsp, 48h
0x14003abe2  retn
0x14003abe3  mov     rax, cs:__imp_NtDCompositionReleaseRemoteTexture
0x14003abea  mov     rcx, [rsp+48h+var_28]
0x14003abef  mov     rdx, [rsp+48h+var_20]
0x14003abf4  mov     r8, [rsp+48h+var_18]
0x14003abf9  mov     r9, [rsp+48h+var_10]
0x14003abfe  add     rsp, 48h
0x14003ac02  jmp     rax
```
