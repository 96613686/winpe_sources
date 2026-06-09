# UpdateDosDriveMap

- ea: `0x14001f410`
- end: `0x14001f4ce`
- name: `UpdateDosDriveMap`
- size: `190`
- prototype: `void __stdcall(PFLT_GENERIC_WORKITEM FltWorkItem, PVOID FltObject, PVOID Context)`
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update`

## callees

- `0x1400041ac`
- `0x140004260`
- `0x14000df1c`
- `0x14001f130`
- `0x14001f410`

## import_xrefs

- `ntoskrnl!ExReleaseRundownProtection` at `0x14001f4a2`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14001f4a2`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14001f433`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14001f433`
- `FLTMGR!FltFreeGenericWorkItem` at `0x14001f4b1`
- `FLTMGR!FltFreeGenericWorkItem` at `0x14001f4b1`

## string_xrefs

- `0x14001f463`: `WinSetupMon::UpdateDosDriveMap: Failed FltGetDiskDeviceObject`
- `0x14001f48d`: `WinSetupMon::UpdateDosDriveMap: MapDosDrive failed`

## pseudocode

```c
void __fastcall UpdateDosDriveMap(PFLT_GENERIC_WORKITEM FltWorkItem, PVOID FltObject, PFLT_VOLUME *Context)
{
  int DriveLetter; // eax
  const char *v6; // rcx
  const UNICODE_STRING *v7; // rcx
  unsigned __int16 v8; // [rsp+40h] [rbp+18h] BYREF

  v8 = 0;
  if ( ExAcquireRundownProtection(&FilterRundownRef) )
  {
    DriveLetter = GetDriveLetter(*Context, &v8);
    if ( (int)(DriveLetter + 0x80000000) < 0 || DriveLetter == -1073741275 )
    {
      v7 = (const UNICODE_STRING *)(Context + 17);
      if ( !v8 )
      {
        UnmapDosDrive(v7);
        goto LABEL_10;
      }
      DriveLetter = MapDosDrive(v7, v8);
      if ( DriveLetter >= 0 )
      {
LABEL_10:
        ExReleaseRundownProtection(&FilterRundownRef);
        goto LABEL_11;
      }
      v6 = "WinSetupMon::UpdateDosDriveMap: MapDosDrive failed";
    }
    else
    {
      v6 = "WinSetupMon::UpdateDosDriveMap: Failed FltGetDiskDeviceObject";
    }
    TraceError(v6, (unsigned int)DriveLetter);
    goto LABEL_10;
  }
LABEL_11:
  FltFreeGenericWorkItem(FltWorkItem);
}

```

## disassembly

```asm
0x14001f410  mov     [rsp+arg_0], rbx
0x14001f415  mov     [rsp+arg_8], rsi
0x14001f41a  push    rdi
0x14001f41b  sub     rsp, 20h
0x14001f41f  mov     rdi, rcx
0x14001f422  xor     esi, esi
0x14001f424  lea     rcx, ?FilterRundownRef@@3U_EX_RUNDOWN_REF@@A; RunRef
0x14001f42b  mov     [rsp+28h+arg_10], si
0x14001f430  mov     rbx, r8
0x14001f433  call    cs:__imp_ExAcquireRundownProtection
0x14001f43a  nop     dword ptr [rax+rax+00h]
0x14001f43f  test    al, al
0x14001f441  jz      short loc_14001F4AE
0x14001f443  mov     rcx, [rbx]; Volume
0x14001f446  lea     rdx, [rsp+28h+arg_10]; unsigned __int16 *
0x14001f44b  call    ?GetDriveLetter@@YAJPEAU_FLT_VOLUME@@PEAG@Z; GetDriveLetter(_FLT_VOLUME *,ushort *)
0x14001f450  mov     edx, 80000000h
0x14001f455  lea     ecx, [rax+rdx]
0x14001f458  test    edx, ecx
0x14001f45a  jnz     short loc_14001F473
0x14001f45c  cmp     eax, 0C0000225h
0x14001f461  jz      short loc_14001F473
0x14001f463  lea     rcx, aWinsetupmonUpd_1; "WinSetupMon::UpdateDosDriveMap: Failed "...
0x14001f46a  mov     edx, eax
0x14001f46c  call    TraceError
0x14001f471  jmp     short loc_14001F49B
0x14001f473  movzx   edx, [rsp+28h+arg_10]; unsigned __int16
0x14001f478  lea     rcx, [rbx+88h]; String1
0x14001f47f  test    dx, dx
0x14001f482  jz      short loc_14001F496
0x14001f484  call    ?MapDosDrive@@YAJPEBU_UNICODE_STRING@@G@Z; MapDosDrive(_UNICODE_STRING const *,ushort)
0x14001f489  test    eax, eax
0x14001f48b  jns     short loc_14001F49B
0x14001f48d  lea     rcx, aWinsetupmonUpd_0; "WinSetupMon::UpdateDosDriveMap: MapDosD"...
0x14001f494  jmp     short loc_14001F46A
0x14001f496  call    ?UnmapDosDrive@@YAXPEBU_UNICODE_STRING@@@Z; UnmapDosDrive(_UNICODE_STRING const *)
0x14001f49b  lea     rcx, ?FilterRundownRef@@3U_EX_RUNDOWN_REF@@A; RunRef
0x14001f4a2  call    cs:__imp_ExReleaseRundownProtection
0x14001f4a9  nop     dword ptr [rax+rax+00h]
0x14001f4ae  mov     rcx, rdi; FltWorkItem
0x14001f4b1  call    cs:__imp_FltFreeGenericWorkItem
0x14001f4b8  nop     dword ptr [rax+rax+00h]
0x14001f4bd  mov     rbx, [rsp+28h+arg_0]
0x14001f4c2  mov     rsi, [rsp+28h+arg_8]
0x14001f4c7  add     rsp, 20h
0x14001f4cb  pop     rdi
0x14001f4cc  retn
```
