# WinSetupMonInstanceTeardownStart

- ea: `0x14001fab0`
- end: `0x14001fc09`
- name: `WinSetupMonInstanceTeardownStart`
- size: `345`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x140002628`
- `0x140003554`
- `0x14000f900`
- `0x14000fd40`
- `0x14001f130`
- `0x14001fab0`

## import_xrefs

- `ntoskrnl!IoUnregisterPlugPlayNotificationEx` at `0x14001fb6e`
- `ntoskrnl!IoUnregisterPlugPlayNotificationEx` at `0x14001fb6e`
- `ntoskrnl!ObfDereferenceObject` at `0x14001fb9c`
- `ntoskrnl!ObfDereferenceObject` at `0x14001fb9c`
- `FLTMGR!FltDeleteContext` at `0x14001fbbb`
- `FLTMGR!FltDeleteContext` at `0x14001fbbb`
- `FLTMGR!FltGetVolumeContext` at `0x14001fb4b`
- `FLTMGR!FltGetVolumeContext` at `0x14001fb4b`
- `FLTMGR!FltReleaseContext` at `0x14001fbcb`
- `FLTMGR!FltReleaseContext` at `0x14001fbcb`
- `FLTMGR!FltGetVolumeName` at `0x14001fb0c`
- `FLTMGR!FltGetVolumeName` at `0x14001fb0c`

## pseudocode

```c
void __fastcall WinSetupMonInstanceTeardownStart(__int64 a1)
{
  struct _FLT_VOLUME *v2; // rcx
  NTSTATUS v3; // eax
  struct _FLT_INSTANCE *v4; // rcx
  NTSTATUS VolumeContext; // eax
  PVOID *v6; // rcx
  PFLT_CONTEXT Context; // [rsp+20h] [rbp-59h] BYREF
  struct _UNICODE_STRING VolumeName; // [rsp+28h] [rbp-51h] BYREF
  _BYTE v9[128]; // [rsp+40h] [rbp-39h] BYREF

  memset(v9, 0, sizeof(v9));
  v2 = *(struct _FLT_VOLUME **)(a1 + 16);
  VolumeName.Buffer = (wchar_t *)v9;
  *(_QWORD *)&VolumeName.Length = 0x800000;
  Context = 0;
  v3 = FltGetVolumeName(v2, &VolumeName, 0);
  if ( v3 < 0 )
    TraceError("WinSetupMonInstanceTeardownStart: Failed FltGetVolumeName", (unsigned int)v3);
  if ( IsLogPathOnInstance(*(struct _FLT_INSTANCE *const *)(a1 + 24)) )
    StopLoggingToFile(v4);
  VolumeContext = FltGetVolumeContext((PFLT_FILTER)FilterHandle, *(PFLT_VOLUME *)(a1 + 16), &Context);
  if ( VolumeContext < 0 )
  {
    TraceError("WinSetupMonInstanceTeardownStart: Failed FltGetVolumeContext", (unsigned int)VolumeContext);
  }
  else
  {
    v6 = (PVOID *)Context;
    if ( *((_QWORD *)Context + 20) )
    {
      IoUnregisterPlugPlayNotificationEx(*((PVOID *)Context + 20));
      *((_QWORD *)Context + 20) = 0;
      v6 = (PVOID *)Context;
    }
    if ( v6[19] )
    {
      ObfDereferenceObject(v6[19]);
      *((_QWORD *)Context + 19) = 0;
      v6 = (PVOID *)Context;
    }
    FltDeleteContext(v6);
    FltReleaseContext(Context);
  }
}

```

## disassembly

```asm
0x14001fab0  mov     [rsp-8+arg_8], rbx
0x14001fab5  mov     [rsp-8+arg_10], rdi
0x14001faba  push    rbp
0x14001fabb  lea     rbp, [rsp-57h]
0x14001fac0  sub     rsp, 0D0h
0x14001fac7  mov     rax, cs:__security_cookie
0x14001face  xor     rax, rsp
0x14001fad1  mov     [rbp+57h+var_10], rax
0x14001fad5  mov     rbx, rcx
0x14001fad8  xor     edx, edx; Val
0x14001fada  lea     rcx, [rbp+57h+var_90]; void *
0x14001fade  mov     r8d, 80h; Size
0x14001fae4  call    memset
0x14001fae9  mov     rcx, [rbx+10h]; Volume
0x14001faed  lea     rax, [rbp+57h+var_90]
0x14001faf1  xor     r8d, r8d; BufferSizeNeeded
0x14001faf4  mov     [rbp+57h+VolumeName.Buffer], rax
0x14001faf8  lea     rdx, [rbp+57h+VolumeName]; VolumeName
0x14001fafc  mov     qword ptr [rbp+57h+VolumeName.Length], 800000h
0x14001fb04  mov     [rbp+57h+Context], 0
0x14001fb0c  call    cs:__imp_FltGetVolumeName
0x14001fb13  nop     dword ptr [rax+rax+00h]
0x14001fb18  test    eax, eax
0x14001fb1a  jns     short loc_14001FB2A
0x14001fb1c  mov     edx, eax
0x14001fb1e  lea     rcx, aWinsetupmonins_1; "WinSetupMonInstanceTeardownStart: Faile"...
0x14001fb25  call    TraceError
0x14001fb2a  mov     rcx, [rbx+18h]; struct _FLT_INSTANCE *
0x14001fb2e  call    ?IsLogPathOnInstance@@YAEQEAU_FLT_INSTANCE@@@Z; IsLogPathOnInstance(_FLT_INSTANCE * const)
0x14001fb33  test    al, al
0x14001fb35  jz      short loc_14001FB3C
0x14001fb37  call    ?StopLoggingToFile@@YAXPEAU_FLT_INSTANCE@@@Z; StopLoggingToFile(_FLT_INSTANCE *)
0x14001fb3c  mov     rdx, [rbx+10h]; Volume
0x14001fb40  lea     r8, [rbp+57h+Context]; Context
0x14001fb44  mov     rcx, cs:?FilterHandle@@3PEAU_FLT_FILTER@@EA; Filter
0x14001fb4b  call    cs:__imp_FltGetVolumeContext
0x14001fb52  nop     dword ptr [rax+rax+00h]
0x14001fb57  test    eax, eax
0x14001fb59  js      short loc_14001FBD9
0x14001fb5b  mov     rcx, [rbp+57h+Context]
0x14001fb5f  mov     rax, [rcx+0A0h]
0x14001fb66  test    rax, rax
0x14001fb69  jz      short loc_14001FB8D
0x14001fb6b  mov     rcx, rax; NotificationEntry
0x14001fb6e  call    cs:__imp_IoUnregisterPlugPlayNotificationEx
0x14001fb75  nop     dword ptr [rax+rax+00h]
0x14001fb7a  mov     rax, [rbp+57h+Context]
0x14001fb7e  mov     qword ptr [rax+0A0h], 0
0x14001fb89  mov     rcx, [rbp+57h+Context]
0x14001fb8d  mov     rax, [rcx+98h]
0x14001fb94  test    rax, rax
0x14001fb97  jz      short loc_14001FBBB
0x14001fb99  mov     rcx, rax; Object
0x14001fb9c  call    cs:__imp_ObfDereferenceObject
0x14001fba3  nop     dword ptr [rax+rax+00h]
0x14001fba8  mov     rax, [rbp+57h+Context]
0x14001fbac  mov     qword ptr [rax+98h], 0
0x14001fbb7  mov     rcx, [rbp+57h+Context]; Context
0x14001fbbb  call    cs:__imp_FltDeleteContext
0x14001fbc2  nop     dword ptr [rax+rax+00h]
0x14001fbc7  mov     rcx, [rbp+57h+Context]; Context
0x14001fbcb  call    cs:__imp_FltReleaseContext
0x14001fbd2  nop     dword ptr [rax+rax+00h]
0x14001fbd7  jmp     short loc_14001FBE7
0x14001fbd9  mov     edx, eax
0x14001fbdb  lea     rcx, aWinsetupmonins_4; "WinSetupMonInstanceTeardownStart: Faile"...
0x14001fbe2  call    TraceError
0x14001fbe7  mov     rcx, [rbp+57h+var_10]
0x14001fbeb  xor     rcx, rsp; StackCookie
0x14001fbee  call    __security_check_cookie
0x14001fbf3  lea     r11, [rsp+0D0h+var_s0]
0x14001fbfb  mov     rbx, [r11+18h]
0x14001fbff  mov     rdi, [r11+20h]
0x14001fc03  mov     rsp, r11
0x14001fc06  pop     rbp
0x14001fc07  retn
```
