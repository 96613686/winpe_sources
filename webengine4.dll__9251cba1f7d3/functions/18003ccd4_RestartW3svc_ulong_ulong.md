# RestartW3svc(ulong,ulong)

- ea: `0x18003ccd4`
- end: `0x18003cf57`
- name: `?RestartW3svc@@YAJKK@Z`
- size: `643`
- prototype: `__int64 __fastcall(unsigned int, unsigned int)`
- caller_count: `3`
- callee_count: `8`
- tags: `service_task, installer_update`

## callers

- `0x1800293d0`
- `0x18003c1e8`
- `0x18003ef38`

## callees

- `0x180012b30`
- `0x18003abe4`
- `0x18003ccd4`
- `0x18003dd70`
- `0x18003dfc0`
- `0x18004a2dc`
- `0x18004d350`
- `0x18004e638`

## import_xrefs

- `ADVAPI32!CloseServiceHandle` at `0x18003cef7`
- `ADVAPI32!CloseServiceHandle` at `0x18003cf05`
- `ADVAPI32!CloseServiceHandle` at `0x18003cef7`
- `ADVAPI32!CloseServiceHandle` at `0x18003cf05`
- `ADVAPI32!OpenSCManagerW` at `0x18003cd8f`
- `ADVAPI32!OpenSCManagerW` at `0x18003cd8f`
- `ADVAPI32!OpenServiceW` at `0x18003cded`
- `ADVAPI32!OpenServiceW` at `0x18003cded`

## string_xrefs

- `0x18003cd6d`: `Connecting to Service Manager`
- `0x18003cda9`: `Connecting to Service Manager`
- `0x18003cd79`: `OpenSCManager`
- `0x18003cdb3`: `OpenSCManager`
- `0x18003cdce`: `OpenService`
- `0x18003ce08`: `OpenService`
- `0x18003cd5b`: `Opening handle to IISAdmin`
- `0x18003cd62`: `Opening handle to W3SVC`
- `0x18003ce2a`: `StopService`
- `0x18003ce5a`: `StopService`

## pseudocode

```c
__int64 __fastcall RestartW3svc(int a1, int a2)
{
  SC_HANDLE v4; // rsi
  unsigned int LastWin32Error; // ebx
  const WCHAR *v6; // r13
  const char *v7; // r15
  const char *v8; // r14
  SC_HANDLE v9; // rbp
  unsigned __int64 i; // rdi
  __int128 v12; // [rsp+30h] [rbp-48h] BYREF
  __int128 v13; // [rsp+40h] [rbp-38h] BYREF

  v4 = 0;
  LastWin32Error = 0;
  v12 = 0;
  v13 = 0;
  CSetupLogging::Log(1, "RestartW3svc", 0, "Restarting W3SVC", 0);
  XspLogEvent(0x400003FFu);
  v6 = L"iisadmin";
  if ( a2 != 1 )
    v6 = L"w3svc";
  v7 = "Stopping IISAdmin";
  if ( a2 != 1 )
    v7 = "Stopping W3SVC";
  v8 = "Opening handle to IISAdmin";
  if ( a2 != 1 )
    v8 = "Opening handle to W3SVC";
  CSetupLogging::Log(1, "OpenSCManager", 0, "Connecting to Service Manager", 0);
  v9 = OpenSCManagerW(0, 0, 1u);
  if ( !v9 )
    LastWin32Error = GetLastWin32Error();
  CSetupLogging::Log(LastWin32Error, "OpenSCManager", 0, "Connecting to Service Manager", 0);
  if ( !LastWin32Error )
  {
    CSetupLogging::Log(1, "OpenService", 0, v8, 0);
    v4 = OpenServiceW(v9, v6, 0x2Cu);
    if ( !v4 )
      LastWin32Error = GetLastWin32Error();
    CSetupLogging::Log(LastWin32Error, "OpenService", 0, v8, 0);
    if ( !LastWin32Error )
    {
      CSetupLogging::Log(1, "StopService", 0, v7, 0);
      LastWin32Error = StopService(v9, v4, (CImplPtrAry *)&v12, (CImplAry *)&v13);
      CSetupLogging::Log(LastWin32Error, "StopService", 0, v7, 0);
      if ( !LastWin32Error && a2 != 1 && a1 != 1 )
      {
        LastWin32Error = StartServiceByName(L"w3svc", a1);
        if ( !LastWin32Error )
        {
          for ( i = (unsigned __int64)(unsigned int)v12 >> 2;
                (--i & 0x8000000000000000uLL) == 0LL;
                LastWin32Error = StartServiceByName(
                                   *(const unsigned __int16 **)(*((_QWORD *)&v12 + 1) + 8 * i),
                                   *(_DWORD *)(*((_QWORD *)&v13 + 1) + 4 * i)) )
          {
            ;
          }
        }
      }
    }
  }
  CSetupLogging::Log(LastWin32Error, "RestartW3svc", 0, "Restarting W3SVC", 0);
  XspLogEvent(0x40000401u);
  CleanupCStrAry((CImplAry *)&v12);
  if ( v4 )
    CloseServiceHandle(v4);
  if ( v9 )
    CloseServiceHandle(v9);
  if ( LastWin32Error )
    XspLogEvent(0xC0000400);
  CImplAry::~CImplAry((CImplAry *)&v13);
  CImplAry::~CImplAry((CImplAry *)&v12);
  return LastWin32Error;
}

```

## disassembly

```asm
0x18003ccd4  mov     rax, rsp
0x18003ccd7  mov     [rax+8], rbx
0x18003ccdb  mov     [rax+10h], rbp
0x18003ccdf  mov     [rax+18h], rsi
0x18003cce3  push    rdi
0x18003cce4  push    r12
0x18003cce6  push    r13
0x18003cce8  push    r14
0x18003ccea  push    r15
0x18003ccec  sub     rsp, 50h
0x18003ccf0  mov     r12d, edx
0x18003ccf3  lea     r9, aRestartingW3sv; "Restarting W3SVC"
0x18003ccfa  mov     edi, ecx
0x18003ccfc  lea     rdx, aRestartw3svc; "RestartW3svc"
0x18003cd03  xorps   xmm0, xmm0
0x18003cd06  xorps   xmm1, xmm1
0x18003cd09  xor     esi, esi
0x18003cd0b  xor     ebx, ebx
0x18003cd0d  and     [rax-58h], rbx
0x18003cd11  xor     r8d, r8d; unsigned int
0x18003cd14  movups  xmmword ptr [rax-48h], xmm0
0x18003cd18  lea     ebp, [rsi+1]
0x18003cd1b  mov     ecx, ebp; int
0x18003cd1d  movups  xmmword ptr [rax-38h], xmm1
0x18003cd21  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x18003cd26  xor     edx, edx
0x18003cd28  mov     ecx, 400003FFh; dwEventID
0x18003cd2d  call    XspLogEvent
0x18003cd32  cmp     r12d, ebp
0x18003cd35  lea     rax, ServiceName; "w3svc"
0x18003cd3c  lea     r13, aIisadmin; "iisadmin"
0x18003cd43  mov     ecx, ebp; int
0x18003cd45  cmovnz  r13, rax
0x18003cd49  lea     r15, aStoppingIisadm; "Stopping IISAdmin"
0x18003cd50  lea     rax, aStoppingW3svc; "Stopping W3SVC"
0x18003cd57  cmovnz  r15, rax
0x18003cd5b  lea     r14, aOpeningHandleT; "Opening handle to IISAdmin"
0x18003cd62  lea     rax, aOpeningHandleT_0; "Opening handle to W3SVC"
0x18003cd69  cmovnz  r14, rax
0x18003cd6d  lea     r9, aConnectingToSe; "Connecting to Service Manager"
0x18003cd74  and     [rsp+78h+var_58], rbx
0x18003cd79  lea     rdx, aOpenscmanager; "OpenSCManager"
0x18003cd80  xor     r8d, r8d; unsigned int
0x18003cd83  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x18003cd88  mov     r8d, ebp; dwDesiredAccess
0x18003cd8b  xor     edx, edx; lpDatabaseName
0x18003cd8d  xor     ecx, ecx; lpMachineName
0x18003cd8f  call    cs:__imp_OpenSCManagerW
0x18003cd95  mov     rbp, rax
0x18003cd98  test    rax, rax
0x18003cd9b  jnz     short loc_18003CDA4
0x18003cd9d  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x18003cda2  mov     ebx, eax
0x18003cda4  and     [rsp+78h+var_58], rsi
0x18003cda9  lea     r9, aConnectingToSe; "Connecting to Service Manager"
0x18003cdb0  xor     r8d, r8d; unsigned int
0x18003cdb3  lea     rdx, aOpenscmanager; "OpenSCManager"
0x18003cdba  mov     ecx, ebx; int
0x18003cdbc  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x18003cdc1  test    ebx, ebx
0x18003cdc3  jnz     loc_18003CEBB
0x18003cdc9  and     [rsp+78h+var_58], rsi
0x18003cdce  lea     rdx, aOpenservice; "OpenService"
0x18003cdd5  mov     r9, r14; char *
0x18003cdd8  lea     ecx, [rbx+1]; int
0x18003cddb  xor     r8d, r8d; unsigned int
0x18003cdde  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x18003cde3  lea     r8d, [rbx+2Ch]; dwDesiredAccess
0x18003cde7  mov     rdx, r13; lpServiceName
0x18003cdea  mov     rcx, rbp; hSCManager
0x18003cded  call    cs:__imp_OpenServiceW
0x18003cdf3  mov     rsi, rax
0x18003cdf6  test    rax, rax
0x18003cdf9  jnz     short loc_18003CE02
0x18003cdfb  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x18003ce00  mov     ebx, eax
0x18003ce02  and     [rsp+78h+var_58], 0
0x18003ce08  lea     rdx, aOpenservice; "OpenService"
0x18003ce0f  mov     r9, r14; char *
0x18003ce12  xor     r8d, r8d; unsigned int
0x18003ce15  mov     ecx, ebx; int
0x18003ce17  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x18003ce1c  test    ebx, ebx
0x18003ce1e  jnz     loc_18003CEBB
0x18003ce24  and     [rsp+78h+var_58], 0
0x18003ce2a  lea     rdx, aStopservice; "StopService"
0x18003ce31  mov     r9, r15; char *
0x18003ce34  lea     ecx, [rbx+1]; int
0x18003ce37  xor     r8d, r8d; unsigned int
0x18003ce3a  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x18003ce3f  lea     r9, [rsp+78h+var_38]
0x18003ce44  mov     rdx, rsi; struct SC_HANDLE__ *
0x18003ce47  lea     r8, [rsp+78h+var_48]; this
0x18003ce4c  mov     rcx, rbp; struct SC_HANDLE__ *
0x18003ce4f  call    ?StopService@@YAJPEAUSC_HANDLE__@@0PEAV?$CPtrAry@PEAG@@PEAV?$CDataAry@K@@@Z; StopService(SC_HANDLE__ *,SC_HANDLE__ *,CPtrAry<ushort *> *,CDataAry<ulong> *)
0x18003ce54  and     [rsp+78h+var_58], 0
0x18003ce5a  lea     rdx, aStopservice; "StopService"
0x18003ce61  mov     r9, r15; char *
0x18003ce64  xor     r8d, r8d; unsigned int
0x18003ce67  mov     ecx, eax; int
0x18003ce69  mov     ebx, eax
0x18003ce6b  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x18003ce70  test    ebx, ebx
0x18003ce72  jnz     short loc_18003CEBB
0x18003ce74  cmp     r12d, 1
0x18003ce78  jz      short loc_18003CEBB
0x18003ce7a  cmp     edi, 1
0x18003ce7d  jz      short loc_18003CEBB
0x18003ce7f  mov     edx, edi; unsigned int
0x18003ce81  lea     rcx, ServiceName; "w3svc"
0x18003ce88  call    ?StartServiceByName@@YAJPEBGK@Z; StartServiceByName(ushort const *,ulong)
0x18003ce8d  mov     ebx, eax
0x18003ce8f  test    eax, eax
0x18003ce91  jnz     short loc_18003CEBB
0x18003ce93  mov     edi, [rsp+78h+var_48]
0x18003ce97  shr     rdi, 2
0x18003ce9b  jmp     short loc_18003CEB5
0x18003ce9d  mov     rax, [rsp+78h+var_30]
0x18003cea2  mov     rcx, [rsp+78h+var_40]
0x18003cea7  mov     edx, [rax+rdi*4]; unsigned int
0x18003ceaa  mov     rcx, [rcx+rdi*8]; unsigned __int16 *
0x18003ceae  call    ?StartServiceByName@@YAJPEBGK@Z; StartServiceByName(ushort const *,ulong)
0x18003ceb3  mov     ebx, eax
0x18003ceb5  sub     rdi, 1
0x18003ceb9  jns     short loc_18003CE9D
0x18003cebb  and     [rsp+78h+var_58], 0
0x18003cec1  lea     r9, aRestartingW3sv; "Restarting W3SVC"
0x18003cec8  xor     r8d, r8d; unsigned int
0x18003cecb  lea     rdx, aRestartw3svc; "RestartW3svc"
0x18003ced2  mov     ecx, ebx; int
0x18003ced4  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x18003ced9  xor     edx, edx
0x18003cedb  mov     ecx, 40000401h; dwEventID
0x18003cee0  call    XspLogEvent
0x18003cee5  lea     rcx, [rsp+78h+var_48]; this
0x18003ceea  call    ?CleanupCStrAry@@YAXPEAV?$CPtrAry@PEAG@@@Z; CleanupCStrAry(CPtrAry<ushort *> *)
0x18003ceef  test    rsi, rsi
0x18003cef2  jz      short loc_18003CEFD
0x18003cef4  mov     rcx, rsi; hSCObject
0x18003cef7  call    cs:__imp_CloseServiceHandle
0x18003cefd  test    rbp, rbp
0x18003cf00  jz      short loc_18003CF0B
0x18003cf02  mov     rcx, rbp; hSCObject
0x18003cf05  call    cs:__imp_CloseServiceHandle
0x18003cf0b  test    ebx, ebx
0x18003cf0d  jz      short loc_18003CF23
0x18003cf0f  mov     r8d, ebx
0x18003cf12  lea     rdx, a0x08x_0; "0x%08x"
0x18003cf19  mov     ecx, 0C0000400h; dwEventID
0x18003cf1e  call    XspLogEvent
0x18003cf23  lea     rcx, [rsp+78h+var_38]; this
0x18003cf28  call    ??1CImplAry@@QEAA@XZ; CImplAry::~CImplAry(void)
0x18003cf2d  lea     rcx, [rsp+78h+var_48]; this
0x18003cf32  call    ??1CImplAry@@QEAA@XZ; CImplAry::~CImplAry(void)
0x18003cf37  lea     r11, [rsp+78h+var_28]
0x18003cf3c  mov     eax, ebx
0x18003cf3e  mov     rbx, [r11+30h]
0x18003cf42  mov     rbp, [r11+38h]
0x18003cf46  mov     rsi, [r11+40h]
0x18003cf4a  mov     rsp, r11
0x18003cf4d  pop     r15
0x18003cf4f  pop     r14
0x18003cf51  pop     r13
0x18003cf53  pop     r12
0x18003cf55  pop     rdi
0x18003cf56  retn
```
