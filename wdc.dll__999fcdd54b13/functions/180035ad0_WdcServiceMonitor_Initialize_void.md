# WdcServiceMonitor::Initialize(void)

- ea: `0x180035ad0`
- end: `0x180035c48`
- name: `?Initialize@WdcServiceMonitor@@UEAAJXZ`
- size: `376`
- prototype: `__int64 __fastcall(WdcServiceMonitor *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, service_task`

## callees

- `0x18000b854`
- `0x18001c718`
- `0x180035ad0`
- `0x180036e80`
- `0x18003a3c0`
- `0x18003b0ac`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180035b1f`
- `ntdll!RtlNtStatusToDosError` at `0x180035b1f`
- `ntdll!NtQuerySystemInformation` at `0x180035b13`
- `ntdll!NtQuerySystemInformation` at `0x180035b13`
- `KERNEL32!GetLastError` at `0x180035bbb`
- `KERNEL32!GetLastError` at `0x180035be0`
- `KERNEL32!GetLastError` at `0x180035bbb`
- `KERNEL32!GetLastError` at `0x180035be0`
- `wevtapi!EvtSubscribe` at `0x180035ba9`
- `wevtapi!EvtSubscribe` at `0x180035ba9`

## string_xrefs

- `0x180035c19`: `base\diagnosis\pdui\perfmon\mon\service.cpp`
- `0x180035c12`: `WdcServiceMonitor::Initialize`
- `0x180035b89`: `*[System[Provider[@Name='Service Control Manager']]]`

## pseudocode

```c
__int64 __fastcall WdcServiceMonitor::Initialize(WdcServiceMonitor *this)
{
  NTSTATUS v2; // eax
  signed int v3; // eax
  signed int v4; // ebx
  int v5; // eax
  EVT_HANDLE v6; // rax
  signed int LastError; // eax
  signed int v8; // eax
  EVT_HANDLE Bookmark; // [rsp+20h] [rbp-78h]
  _BYTE SystemInformation[4]; // [rsp+40h] [rbp-58h] BYREF
  int v12; // [rsp+44h] [rbp-54h]

  memset_0(SystemInformation, 0, 0x40u);
  v2 = NtQuerySystemInformation(SystemBasicInformation, SystemInformation, 0x40u, 0);
  if ( v2 )
  {
    v3 = RtlNtStatusToDosError(v2);
    v4 = 0;
    if ( v3 )
    {
      if ( v3 > 0 )
        v4 = (unsigned __int16)v3 | 0x80070000;
      else
        v4 = v3;
    }
    if ( v4 < 0 )
    {
      LODWORD(Bookmark) = v4;
LABEL_24:
      WdcDebugMessage(
        "base\\diagnosis\\pdui\\perfmon\\mon\\service.cpp",
        "WdcServiceMonitor::Initialize",
        0,
        L"FAILURE: 0x%08x",
        Bookmark);
      return (unsigned int)v4;
    }
  }
  *((_DWORD *)this + 2355) = v12;
  v5 = WdcServiceMonitor::EnumServices(this);
  v4 = v5;
  if ( v5 < 0 || (v5 = WdcServiceMonitor::CheckInExistingThreads((WdcThreadStat **)this), v4 = v5, v5 < 0) )
  {
LABEL_23:
    LODWORD(Bookmark) = v5;
    goto LABEL_24;
  }
  v6 = EvtSubscribe(0, 0, L"System", L"*[System[Provider[@Name='Service Control Manager']]]", 0, this, ScmCallback, 1u);
  *((_QWORD *)this + 1169) = v6;
  if ( !v6 )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( !LastError )
      goto LABEL_21;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    if ( v4 < 0 )
      goto LABEL_22;
  }
  if ( *((_QWORD *)this + 1169) != -1 )
    return (unsigned int)v4;
  v8 = GetLastError();
  v4 = v8;
  if ( !v8 )
  {
LABEL_21:
    v4 = -2147467259;
LABEL_22:
    v5 = v4;
    goto LABEL_23;
  }
  if ( v8 > 0 )
    v4 = (unsigned __int16)v8 | 0x80070000;
  if ( v4 < 0 )
    goto LABEL_22;
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180035ad0  mov     [rsp+arg_8], rbx
0x180035ad5  push    rdi
0x180035ad6  sub     rsp, 90h
0x180035add  mov     rax, cs:__security_cookie
0x180035ae4  xor     rax, rsp
0x180035ae7  mov     [rsp+98h+var_18], rax
0x180035aef  mov     rdi, rcx
0x180035af2  mov     ebx, 40h ; '@'
0x180035af7  mov     r8d, ebx; Size
0x180035afa  lea     rcx, [rsp+98h+SystemInformation]; void *
0x180035aff  xor     edx, edx; Val
0x180035b01  call    memset_0
0x180035b06  xor     r9d, r9d; ReturnLength
0x180035b09  lea     rdx, [rsp+98h+SystemInformation]; SystemInformation
0x180035b0e  mov     r8d, ebx; SystemInformationLength
0x180035b11  xor     ecx, ecx; SystemInformationClass
0x180035b13  call    cs:__imp_NtQuerySystemInformation
0x180035b19  test    eax, eax
0x180035b1b  jz      short loc_180035B47
0x180035b1d  mov     ecx, eax; Status
0x180035b1f  call    cs:__imp_RtlNtStatusToDosError
0x180035b25  xor     ebx, ebx
0x180035b27  test    eax, eax
0x180035b29  jz      short loc_180035B3A
0x180035b2b  jg      short loc_180035B31
0x180035b2d  mov     ebx, eax
0x180035b2f  jmp     short loc_180035B3A
0x180035b31  movzx   ebx, ax
0x180035b34  or      ebx, 80070000h
0x180035b3a  test    ebx, ebx
0x180035b3c  jns     short loc_180035B47
0x180035b3e  mov     dword ptr [rsp+98h+Bookmark], ebx
0x180035b42  jmp     loc_180035C08
0x180035b47  mov     eax, [rsp+98h+var_54]
0x180035b4b  mov     rcx, rdi; this
0x180035b4e  mov     [rdi+24CCh], eax
0x180035b54  call    ?EnumServices@WdcServiceMonitor@@QEAAJXZ; WdcServiceMonitor::EnumServices(void)
0x180035b59  mov     ebx, eax
0x180035b5b  test    eax, eax
0x180035b5d  js      loc_180035C04
0x180035b63  mov     rcx, rdi; this
0x180035b66  call    ?CheckInExistingThreads@WdcServiceMonitor@@QEAAJXZ; WdcServiceMonitor::CheckInExistingThreads(void)
0x180035b6b  mov     ebx, eax
0x180035b6d  test    eax, eax
0x180035b6f  js      loc_180035C04
0x180035b75  mov     [rsp+98h+Flags], 1; Flags
0x180035b7d  lea     rax, ?ScmCallback@@YAKW4_EVT_SUBSCRIBE_NOTIFY_ACTION@@PEAX1@Z; ScmCallback(_EVT_SUBSCRIBE_NOTIFY_ACTION,void *,void *)
0x180035b84  mov     [rsp+98h+Callback], rax; Callback
0x180035b89  lea     r9, Query; "*[System[Provider[@Name='Service Contro"...
0x180035b90  mov     [rsp+98h+Context], rdi; Context
0x180035b95  lea     r8, ChannelPath; "System"
0x180035b9c  xor     edx, edx; SignalEvent
0x180035b9e  mov     [rsp+98h+Bookmark], 0; Bookmark
0x180035ba7  xor     ecx, ecx; Session
0x180035ba9  call    cs:__imp_EvtSubscribe
0x180035baf  mov     [rdi+2488h], rax
0x180035bb6  test    rax, rax
0x180035bb9  jnz     short loc_180035BD6
0x180035bbb  call    cs:__imp_GetLastError
0x180035bc1  mov     ebx, eax
0x180035bc3  test    eax, eax
0x180035bc5  jz      short loc_180035BFD
0x180035bc7  jle     short loc_180035BD2
0x180035bc9  movzx   ebx, ax
0x180035bcc  or      ebx, 80070000h
0x180035bd2  test    ebx, ebx
0x180035bd4  js      short loc_180035C02
0x180035bd6  cmp     qword ptr [rdi+2488h], 0FFFFFFFFFFFFFFFFh
0x180035bde  jnz     short loc_180035C25
0x180035be0  call    cs:__imp_GetLastError
0x180035be6  mov     ebx, eax
0x180035be8  test    eax, eax
0x180035bea  jz      short loc_180035BFD
0x180035bec  jle     short loc_180035BF7
0x180035bee  movzx   ebx, ax
0x180035bf1  or      ebx, 80070000h
0x180035bf7  test    ebx, ebx
0x180035bf9  jns     short loc_180035C25
0x180035bfb  jmp     short loc_180035C02
0x180035bfd  mov     ebx, 80004005h
0x180035c02  mov     eax, ebx
0x180035c04  mov     dword ptr [rsp+98h+Bookmark], eax
0x180035c08  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180035c0f  xor     r8d, r8d; int
0x180035c12  lea     rdx, aWdcservicemoni_2; "WdcServiceMonitor::Initialize"
0x180035c19  lea     rcx, aBaseDiagnosisP_45; "base\\diagnosis\\pdui\\perfmon\\mon\\se"...
0x180035c20  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x180035c25  mov     eax, ebx
0x180035c27  mov     rcx, [rsp+98h+var_18]
0x180035c2f  xor     rcx, rsp; StackCookie
0x180035c32  call    __security_check_cookie
0x180035c37  mov     rbx, [rsp+98h+arg_8]
0x180035c3f  add     rsp, 90h
0x180035c46  pop     rdi
0x180035c47  retn
```
