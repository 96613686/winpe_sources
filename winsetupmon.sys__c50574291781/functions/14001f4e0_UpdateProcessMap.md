# UpdateProcessMap

- ea: `0x14001f4e0`
- end: `0x14001f570`
- name: `UpdateProcessMap`
- size: `144`
- prototype: `void __stdcall(PFLT_GENERIC_WORKITEM FltWorkItem, PVOID FltObject, PVOID Context)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, installer_update`

## callees

- `0x14000439c`
- `0x140004564`
- `0x14000d880`
- `0x14001f130`
- `0x14001f4e0`

## import_xrefs

- `ntoskrnl!ExReleaseRundownProtection` at `0x14001f541`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14001f541`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14001f4f7`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14001f4f7`
- `FLTMGR!FltFreeGenericWorkItem` at `0x14001f558`
- `FLTMGR!FltFreeGenericWorkItem` at `0x14001f558`

## string_xrefs

- `0x14001f51a`: `WinSetupMon::UpdateProcessMap: MapProcess failed`
- `0x14001f52c`: `WinSetupMon::UpdateProcessMap: UnmapProcess failed`

## pseudocode

```c
void __fastcall UpdateProcessMap(PFLT_GENERIC_WORKITEM FltWorkItem, PVOID FltObject, _QWORD *Context)
{
  void *v5; // rcx
  int v6; // eax
  const char *v7; // rcx

  if ( ExAcquireRundownProtection(&FilterRundownRef) )
  {
    v5 = (void *)Context[1];
    if ( *((_BYTE *)Context + 16) )
    {
      v6 = MapProcess(v5);
      if ( v6 < 0 )
      {
        v7 = "WinSetupMon::UpdateProcessMap: MapProcess failed";
LABEL_7:
        TraceError(v7, (unsigned int)v6);
      }
    }
    else
    {
      v6 = UnmapProcess((ULONG_PTR)v5);
      if ( v6 < 0 )
      {
        v7 = "WinSetupMon::UpdateProcessMap: UnmapProcess failed";
        goto LABEL_7;
      }
    }
    ExReleaseRundownProtection(&FilterRundownRef);
  }
  operator delete(Context);
  FltFreeGenericWorkItem(FltWorkItem);
}

```

## disassembly

```asm
0x14001f4e0  mov     [rsp+arg_0], rbx
0x14001f4e5  push    rdi
0x14001f4e6  sub     rsp, 20h
0x14001f4ea  mov     rdi, rcx
0x14001f4ed  mov     rbx, r8
0x14001f4f0  lea     rcx, ?FilterRundownRef@@3U_EX_RUNDOWN_REF@@A; RunRef
0x14001f4f7  call    cs:__imp_ExAcquireRundownProtection
0x14001f4fe  nop     dword ptr [rax+rax+00h]
0x14001f503  test    al, al
0x14001f505  jz      short loc_14001F54D
0x14001f507  cmp     byte ptr [rbx+10h], 0
0x14001f50b  mov     rcx, [rbx+8]; Signature
0x14001f50f  jz      short loc_14001F523
0x14001f511  call    ?MapProcess@@YAJPEAX@Z; MapProcess(void *)
0x14001f516  test    eax, eax
0x14001f518  jns     short loc_14001F53A
0x14001f51a  lea     rcx, aWinsetupmonUpd_2; "WinSetupMon::UpdateProcessMap: MapProce"...
0x14001f521  jmp     short loc_14001F533
0x14001f523  call    ?UnmapProcess@@YAJPEAX@Z; UnmapProcess(void *)
0x14001f528  test    eax, eax
0x14001f52a  jns     short loc_14001F53A
0x14001f52c  lea     rcx, aWinsetupmonUpd; "WinSetupMon::UpdateProcessMap: UnmapPro"...
0x14001f533  mov     edx, eax
0x14001f535  call    TraceError
0x14001f53a  lea     rcx, ?FilterRundownRef@@3U_EX_RUNDOWN_REF@@A; RunRef
0x14001f541  call    cs:__imp_ExReleaseRundownProtection
0x14001f548  nop     dword ptr [rax+rax+00h]
0x14001f54d  mov     rcx, rbx; void *
0x14001f550  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14001f555  mov     rcx, rdi; FltWorkItem
0x14001f558  call    cs:__imp_FltFreeGenericWorkItem
0x14001f55f  nop     dword ptr [rax+rax+00h]
0x14001f564  mov     rbx, [rsp+28h+arg_0]
0x14001f569  add     rsp, 20h
0x14001f56d  pop     rdi
0x14001f56e  retn
```
