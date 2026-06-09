# _stub_DCompositionSynchronize

- ea: `0x14003b240`
- end: `0x14003b2e7`
- name: `_stub_DCompositionSynchronize`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x14003b240`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003b289`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003b289`

## string_xrefs

- `0x14003b26f`: `NtDCompositionSynchronize`

## pseudocode

```c
__int64 stub_DCompositionSynchronize()
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtDCompositionSynchronize();
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtDCompositionSynchronize();
  result = (unsigned int)*((char *)&W32pServiceTableFilter[40] + 4 * (unsigned int)W32pServiceLimitFilter + 1);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x14003b240  sub     rsp, 48h
0x14003b244  mov     [rsp+48h+var_28], rcx
0x14003b249  mov     [rsp+48h+var_20], rdx
0x14003b24e  mov     [rsp+48h+var_18], r8
0x14003b253  mov     [rsp+48h+var_10], r9
0x14003b258  mov     rcx, 141h
0x14003b25f  call    cs:__imp_IsWin32KSyscallFiltered
0x14003b266  nop     dword ptr [rax+rax+00h]
0x14003b26b  test    al, al
0x14003b26d  jz      short loc_14003B2C3
0x14003b26f  lea     rcx, aNtdcomposition_45; "NtDCompositionSynchronize"
0x14003b276  mov     rdx, 141h
0x14003b27d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x14003b284  nop     dword ptr [rax+rax+00h]
0x14003b289  call    cs:__imp_PsIsWin32KFilterEnabled
0x14003b290  nop     dword ptr [rax+rax+00h]
0x14003b295  test    al, al
0x14003b297  jz      short loc_14003B2C3
0x14003b299  lea     rcx, W32pServiceTableFilter
0x14003b2a0  mov     edx, cs:W32pServiceLimitFilter
0x14003b2a6  mov     rax, 141h
0x14003b2ad  lea     rcx, [rcx+rdx*4]
0x14003b2b1  movsx   eax, byte ptr [rcx+rax]
0x14003b2b5  or      eax, eax
0x14003b2b7  jle     short loc_14003B2BE
0x14003b2b9  mov     eax, 0C000001Ch
0x14003b2be  add     rsp, 48h
0x14003b2c2  retn
0x14003b2c3  mov     rax, cs:__imp_NtDCompositionSynchronize
0x14003b2ca  mov     rcx, [rsp+48h+var_28]
0x14003b2cf  mov     rdx, [rsp+48h+var_20]
0x14003b2d4  mov     r8, [rsp+48h+var_18]
0x14003b2d9  mov     r9, [rsp+48h+var_10]
0x14003b2de  add     rsp, 48h
0x14003b2e2  jmp     rax
```
