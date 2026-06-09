# _stub_ConfirmCompositionSurfaceIndependentFlipEntry

- ea: `0x140038fe0`
- end: `0x140039087`
- name: `_stub_ConfirmCompositionSurfaceIndependentFlipEntry`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140038fe0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140039029`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140039029`
- `ext-ms-win-core-win32k-surfmgr-l1-1-1!NtConfirmCompositionSurfaceIndependentFlipEntry` at `0x140039063`

## string_xrefs

- `0x14003900f`: `NtConfirmCompositionSurfaceIndependentFlipEntry`

## pseudocode

```c
__int64 __fastcall stub_ConfirmCompositionSurfaceIndependentFlipEntry(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtConfirmCompositionSurfaceIndependentFlipEntry(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtConfirmCompositionSurfaceIndependentFlipEntry(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[33] + 4 * (unsigned int)W32pServiceLimitFilter + 7);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140038fe0  sub     rsp, 48h
0x140038fe4  mov     [rsp+48h+var_28], rcx
0x140038fe9  mov     [rsp+48h+var_20], rdx
0x140038fee  mov     [rsp+48h+var_18], r8
0x140038ff3  mov     [rsp+48h+var_10], r9
0x140038ff8  mov     rcx, 10Fh
0x140038fff  call    cs:__imp_IsWin32KSyscallFiltered
0x140039006  nop     dword ptr [rax+rax+00h]
0x14003900b  test    al, al
0x14003900d  jz      short loc_140039063
0x14003900f  lea     rcx, aNtconfirmcompo; "NtConfirmCompositionSurfaceIndependentF"...
0x140039016  mov     rdx, 10Fh
0x14003901d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140039024  nop     dword ptr [rax+rax+00h]
0x140039029  call    cs:__imp_PsIsWin32KFilterEnabled
0x140039030  nop     dword ptr [rax+rax+00h]
0x140039035  test    al, al
0x140039037  jz      short loc_140039063
0x140039039  lea     rcx, W32pServiceTableFilter
0x140039040  mov     edx, cs:W32pServiceLimitFilter
0x140039046  mov     rax, 10Fh
0x14003904d  lea     rcx, [rcx+rdx*4]
0x140039051  movsx   eax, byte ptr [rcx+rax]
0x140039055  or      eax, eax
0x140039057  jle     short loc_14003905E
0x140039059  mov     eax, 0C000001Ch
0x14003905e  add     rsp, 48h
0x140039062  retn
0x140039063  mov     rax, cs:__imp_NtConfirmCompositionSurfaceIndependentFlipEntry
0x14003906a  mov     rcx, [rsp+48h+var_28]
0x14003906f  mov     rdx, [rsp+48h+var_20]
0x140039074  mov     r8, [rsp+48h+var_18]
0x140039079  mov     r9, [rsp+48h+var_10]
0x14003907e  add     rsp, 48h
0x140039082  jmp     rax
```
