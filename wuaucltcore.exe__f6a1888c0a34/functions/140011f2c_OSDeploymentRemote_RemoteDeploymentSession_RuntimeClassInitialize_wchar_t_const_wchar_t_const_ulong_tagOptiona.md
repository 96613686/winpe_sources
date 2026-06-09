# OSDeploymentRemote::RemoteDeploymentSession::RuntimeClassInitialize(wchar_t const *,wchar_t const *,ulong,tagOptionalSessionInfo6 *)

- ea: `0x140011f2c`
- end: `0x14001211f`
- name: `?RuntimeClassInitialize@RemoteDeploymentSession@OSDeploymentRemote@@QEAAJPEB_W0KPEAUtagOptionalSessionInfo6@@@Z`
- size: `499`
- prototype: `__int64 __fastcall(OSDeploymentRemote::RemoteDeploymentSession *this, const wchar_t *, const wchar_t *, unsigned int, struct tagOptionalSessionInfo6 *ProcAddress)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x140011530`

## callees

- `0x140002ac0`
- `0x14000fd28`
- `0x140011f2c`
- `0x140012128`
- `0x1400126b8`
- `0x1400197cc`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140011ff1`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140011ff1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14001207e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14001207e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140011fd4`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140011fd4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011fe6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140012008`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011fe6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140012008`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140011ff9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140011ff9`

## string_xrefs

- `0x140011f89`: `Remote: Creating remote deployment session. DLL %ws, Sandbox %ws`
- `0x140012077`: `CreateDeploymentSessionEx`
- `0x140012035`: `Remote: Failed to load the service stack dll file '%ws'`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall OSDeploymentRemote::RemoteDeploymentSession::RuntimeClassInitialize(
        OSDeploymentRemote::RemoteDeploymentSession *this,
        const wchar_t *a2,
        const wchar_t *a3,
        unsigned int a4,
        struct tagOptionalSessionInfo6 *ProcAddress)
{
  struct tagOptionalSessionInfo6 *v5; // rsi
  signed int started; // ebx
  __int64 v11; // rdx
  HMODULE Library; // rax
  HMODULE v14; // r12
  HMODULE v15; // r15
  DWORD LastError; // ebx
  signed int v17; // eax
  int v18; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v5 = ProcAddress;
  if ( !ProcAddress )
  {
    started = -2147024809;
    v11 = 68;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Remote\\RemoteDeploymentSession.cpp",
      (const char *)(unsigned int)started,
      v18);
    return (unsigned int)started;
  }
  v18 = 0;
  WUTrace(0, 0, 4096, 4);
  started = OSDeploymentInformationFactory::StartJITCOMServer((OSDeploymentRemote::RemoteDeploymentSession *)((char *)this + 40));
  if ( started < 0 )
  {
    v11 = 76;
    goto LABEL_3;
  }
  Library = LoadLibraryExW(a2, 0, 0);
  v14 = (HMODULE)*((_QWORD *)this + 3);
  v15 = Library;
  if ( v14 )
  {
    LastError = GetLastError();
    FreeLibrary(v14);
    SetLastError(LastError);
  }
  *((_QWORD *)this + 3) = v15;
  if ( !v15 )
  {
    v17 = GetLastError();
    started = (unsigned __int16)v17 | 0x80070000;
    if ( v17 <= 0 )
      started = v17;
    if ( started >= 0 )
      started = -2147418113;
    WUTrace(0, 0, 4096, 1);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6F,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Remote\\RemoteDeploymentSession.cpp",
      (const char *)(unsigned int)started,
      started);
    v11 = 78;
    goto LABEL_3;
  }
  ProcAddress = (struct tagOptionalSessionInfo6 *)GetProcAddress(*((HMODULE *)this + 3), "CreateDeploymentSessionEx");
  if ( ProcAddress )
  {
    started = OSDeploymentRemote::RemoteDeploymentSession::InvokeCreateDeploymentSessionEx(
                this,
                (int (*const *)(unsigned int, const wchar_t *, struct _GUID *__struct_ptr, unsigned int, void *, struct IDeploymentSession **))&ProcAddress,
                a3,
                a4,
                v5);
    if ( started < 0 )
    {
      v11 = 88;
      goto LABEL_3;
    }
  }
  else
  {
    started = OSDeploymentRemote::RemoteDeploymentSession::InvokeCreateDeploymentSession(this, a3, v5);
    if ( started < 0 )
    {
      v11 = 92;
      goto LABEL_3;
    }
  }
  WUTrace(0, 0, 4096, 4);
  return 0;
}

```

## disassembly

```asm
0x140011f2c  mov     [rsp+arg_0], rbx
0x140011f31  mov     [rsp+arg_8], rbp
0x140011f36  mov     [rsp+arg_10], rsi
0x140011f3b  push    rdi
0x140011f3c  push    r12
0x140011f3e  push    r13
0x140011f40  push    r14
0x140011f42  push    r15
0x140011f44  sub     rsp, 40h
0x140011f48  mov     rsi, [rsp+68h+arg_20]
0x140011f50  mov     r13d, r9d
0x140011f53  mov     rbp, r8
0x140011f56  mov     r14, rdx
0x140011f59  mov     rdi, rcx
0x140011f5c  test    rsi, rsi
0x140011f5f  jnz     short loc_140011F84
0x140011f61  mov     ebx, 80070057h
0x140011f66  lea     edx, [rsi+44h]; void *
0x140011f69  mov     rcx, [rsp+68h]; this
0x140011f6e  lea     r8, aCW1SSrcClientE_1; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x140011f75  mov     r9d, ebx; char *
0x140011f78  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140011f7d  mov     eax, ebx
0x140011f7f  jmp     loc_140012101
0x140011f84  mov     [rsp+68h+var_30], rbp
0x140011f89  lea     rax, aRemoteCreating_0; "Remote: Creating remote deployment sess"...
0x140011f90  xor     edx, edx
0x140011f92  mov     [rsp+68h+var_38], r14
0x140011f97  mov     [rsp+68h+var_40], rax
0x140011f9c  xor     ecx, ecx
0x140011f9e  mov     r8d, 1000h
0x140011fa4  mov     [rsp+68h+var_48], 0
0x140011fad  lea     r9d, [rdx+4]
0x140011fb1  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x140011fb6  lea     rcx, [rdi+28h]; this
0x140011fba  call    ?StartJITCOMServer@OSDeploymentInformationFactory@@QEAAJXZ; OSDeploymentInformationFactory::StartJITCOMServer(void)
0x140011fbf  mov     ebx, eax
0x140011fc1  test    eax, eax
0x140011fc3  jns     short loc_140011FCC
0x140011fc5  mov     edx, 4Ch ; 'L'
0x140011fca  jmp     short loc_140011F69
0x140011fcc  xor     r8d, r8d; dwFlags
0x140011fcf  xor     edx, edx; hFile
0x140011fd1  mov     rcx, r14; lpLibFileName
0x140011fd4  call    cs:__imp_LoadLibraryExW
0x140011fda  mov     r12, [rdi+18h]
0x140011fde  mov     r15, rax
0x140011fe1  test    r12, r12
0x140011fe4  jz      short loc_140011FFF
0x140011fe6  call    cs:__imp_GetLastError
0x140011fec  mov     rcx, r12; hLibModule
0x140011fef  mov     ebx, eax
0x140011ff1  call    cs:__imp_FreeLibrary
0x140011ff7  mov     ecx, ebx; dwErrCode
0x140011ff9  call    cs:__imp_SetLastError
0x140011fff  mov     [rdi+18h], r15
0x140012003  test    r15, r15
0x140012006  jnz     short loc_140012073
0x140012008  call    cs:__imp_GetLastError
0x14001200e  mov     [rsp+68h+var_38], r14
0x140012013  lea     r9d, [r15+1]
0x140012017  movzx   ebx, ax
0x14001201a  mov     r8d, 1000h
0x140012020  or      ebx, 80070000h
0x140012026  test    eax, eax
0x140012028  cmovle  ebx, eax
0x14001202b  mov     eax, 8000FFFFh
0x140012030  test    ebx, ebx
0x140012032  cmovns  ebx, eax
0x140012035  lea     rax, aRemoteFailedTo; "Remote: Failed to load the service stac"...
0x14001203c  mov     [rsp+68h+var_40], rax
0x140012041  xor     edx, edx
0x140012043  xor     ecx, ecx
0x140012045  mov     dword ptr [rsp+68h+var_48], ebx; int
0x140012049  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x14001204e  mov     rcx, [rsp+68h]; this
0x140012053  lea     r8, aCW1SSrcClientE_1; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x14001205a  mov     r9d, ebx; char *
0x14001205d  lea     edx, [r15+6Fh]; void *
0x140012061  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140012066  test    ebx, ebx
0x140012068  jns     short loc_140012073
0x14001206a  lea     edx, [r15+4Eh]
0x14001206e  jmp     loc_140011F69
0x140012073  mov     rcx, [rdi+18h]; hModule
0x140012077  lea     rdx, aCreatedeployme; "CreateDeploymentSessionEx"
0x14001207e  call    cs:__imp_GetProcAddress
0x140012084  mov     [rsp+68h+arg_20], rax
0x14001208c  mov     rcx, rdi; this
0x14001208f  test    rax, rax
0x140012092  jz      short loc_1400120BC
0x140012094  mov     r9d, r13d; unsigned int
0x140012097  mov     [rsp+68h+var_48], rsi; struct tagOptionalSessionInfo6 *
0x14001209c  mov     r8, rbp; wchar_t *
0x14001209f  lea     rdx, [rsp+68h+arg_20]; int (**)(unsigned int, const wchar_t *, struct _GUID *__struct_ptr, unsigned int, void *, struct IDeploymentSession **)
0x1400120a7  call    ?InvokeCreateDeploymentSessionEx@RemoteDeploymentSession@OSDeploymentRemote@@AEAAJAEBQ6AJKPEB_WU_GUID@@KPEAXPEAPEAUIDeploymentSession@@@Z0KPEAUtagOptionalSessionInfo6@@@Z; OSDeploymentRemote::RemoteDeploymentSession::InvokeCreateDeploymentSessionEx(long (*const &)(ulong,wchar_t const *,_GUID,ulong,void *,IDeploymentSession * *),wchar_t const *,ulong,tagOptionalSessionInfo6 *)
0x1400120ac  mov     ebx, eax
0x1400120ae  test    eax, eax
0x1400120b0  jns     short loc_1400120D7
0x1400120b2  mov     edx, 58h ; 'X'
0x1400120b7  jmp     loc_140011F69
0x1400120bc  mov     r8, rsi; struct tagOptionalSessionInfo6 *
0x1400120bf  mov     rdx, rbp; wchar_t *
0x1400120c2  call    ?InvokeCreateDeploymentSession@RemoteDeploymentSession@OSDeploymentRemote@@AEAAJPEB_WPEAUtagOptionalSessionInfo6@@@Z; OSDeploymentRemote::RemoteDeploymentSession::InvokeCreateDeploymentSession(wchar_t const *,tagOptionalSessionInfo6 *)
0x1400120c7  mov     ebx, eax
0x1400120c9  test    eax, eax
0x1400120cb  jns     short loc_1400120D7
0x1400120cd  mov     edx, 5Ch ; '\'
0x1400120d2  jmp     loc_140011F69
0x1400120d7  xor     edx, edx
0x1400120d9  lea     rax, aRemoteCreating; "Remote: creating deployment session has"...
0x1400120e0  mov     [rsp+68h+var_40], rax
0x1400120e5  xor     ecx, ecx
0x1400120e7  mov     r8d, 1000h
0x1400120ed  mov     [rsp+68h+var_48], 0
0x1400120f6  lea     r9d, [rdx+4]
0x1400120fa  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1400120ff  xor     eax, eax
0x140012101  lea     r11, [rsp+68h+var_28]
0x140012106  mov     rbx, [r11+30h]
0x14001210a  mov     rbp, [r11+38h]
0x14001210e  mov     rsi, [r11+40h]
0x140012112  mov     rsp, r11
0x140012115  pop     r15
0x140012117  pop     r14
0x140012119  pop     r13
0x14001211b  pop     r12
0x14001211d  pop     rdi
0x14001211e  retn
```
