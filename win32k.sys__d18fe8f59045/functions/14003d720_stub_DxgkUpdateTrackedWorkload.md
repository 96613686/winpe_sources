# _stub_DxgkUpdateTrackedWorkload

- ea: `0x14003d720`
- end: `0x14003d7c7`
- name: `_stub_DxgkUpdateTrackedWorkload`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, installer_update`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x14003d720`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003d769`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003d769`
- `ext-ms-win-core-win32k-dxgk-l1-1-0!NtDxgkUpdateTrackedWorkload` at `0x14003d7a3`

## string_xrefs

- `0x14003d74f`: `NtDxgkUpdateTrackedWorkload`

## pseudocode

```c
__int64 __fastcall stub_DxgkUpdateTrackedWorkload(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtDxgkUpdateTrackedWorkload(a1, a2, a3, a4);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtDxgkUpdateTrackedWorkload(a1, a2, a3, a4);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[46] + 4 * (unsigned int)W32pServiceLimitFilter + 4);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x14003d720  sub     rsp, 48h
0x14003d724  mov     [rsp+48h+var_28], rcx
0x14003d729  mov     [rsp+48h+var_20], rdx
0x14003d72e  mov     [rsp+48h+var_18], r8
0x14003d733  mov     [rsp+48h+var_10], r9
0x14003d738  mov     rcx, 174h
0x14003d73f  call    cs:__imp_IsWin32KSyscallFiltered
0x14003d746  nop     dword ptr [rax+rax+00h]
0x14003d74b  test    al, al
0x14003d74d  jz      short loc_14003D7A3
0x14003d74f  lea     rcx, aNtdxgkupdatetr; "NtDxgkUpdateTrackedWorkload"
0x14003d756  mov     rdx, 174h
0x14003d75d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x14003d764  nop     dword ptr [rax+rax+00h]
0x14003d769  call    cs:__imp_PsIsWin32KFilterEnabled
0x14003d770  nop     dword ptr [rax+rax+00h]
0x14003d775  test    al, al
0x14003d777  jz      short loc_14003D7A3
0x14003d779  lea     rcx, W32pServiceTableFilter
0x14003d780  mov     edx, cs:W32pServiceLimitFilter
0x14003d786  mov     rax, 174h
0x14003d78d  lea     rcx, [rcx+rdx*4]
0x14003d791  movsx   eax, byte ptr [rcx+rax]
0x14003d795  or      eax, eax
0x14003d797  jle     short loc_14003D79E
0x14003d799  mov     eax, 0C000001Ch
0x14003d79e  add     rsp, 48h
0x14003d7a2  retn
0x14003d7a3  mov     rax, cs:__imp_NtDxgkUpdateTrackedWorkload
0x14003d7aa  mov     rcx, [rsp+48h+var_28]
0x14003d7af  mov     rdx, [rsp+48h+var_20]
0x14003d7b4  mov     r8, [rsp+48h+var_18]
0x14003d7b9  mov     r9, [rsp+48h+var_10]
0x14003d7be  add     rsp, 48h
0x14003d7c2  jmp     rax
```
