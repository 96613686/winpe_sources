# RunRemoteUHProcess

- ea: `0x140005f84`
- end: `0x1400062ef`
- name: `RunRemoteUHProcess`
- size: `875`
- prototype: `__int64 __fastcall(int, const struct _GUID *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14000631c`

## callees

- `0x140002ac0`
- `0x140002aec`
- `0x140003e74`
- `0x140005e60`
- `0x140005f84`
- `0x14000bda4`
- `0x14000fd28`
- `0x14001052c`
- `0x14001aa60`
- `0x14001ad2c`
- `0x1400206e0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1400062b0`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1400062b0`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140005ff6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140005ff6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000628d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400062c4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000628d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400062c4`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x14000620a`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x14000620a`

## string_xrefs

- `0x140005fc1`: `Starting remote process for UpdateHandler %d, classId %ws`
- `0x14000600c`: `C:\__w\1\s\src\Client\lib\util\commonutil.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall RunRemoteUHProcess(int a1, const struct _GUID *a2)
{
  char *EventW; // rax
  unsigned int v5; // edx
  bool v6; // r8
  const char *v7; // r9
  char *v8; // rbx
  int LastError; // eax
  int v10; // esi
  char *v11; // r14
  int v12; // eax
  __int64 v13; // rdx
  _QWORD *v14; // rax
  _QWORD *v15; // rdi
  char *v16; // rdi
  __int64 v17; // rdx
  const char *v18; // r9
  int v20; // [rsp+20h] [rbp-69h]
  int v21; // [rsp+40h] [rbp-49h] BYREF
  char *v22; // [rsp+48h] [rbp-41h]
  char v23[80]; // [rsp+50h] [rbp-39h] BYREF
  __int64 v24; // [rsp+A0h] [rbp+17h] BYREF
  HANDLE Handles[2]; // [rsp+A8h] [rbp+1Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  Trace::GuidToString::GuidToString((Trace::GuidToString *)v23, a2);
  v20 = 0;
  WUTrace(0, 0, 4096, 4);
  EventW = (char *)CreateEventW(0, 1, 0, 0);
  v8 = EventW;
  v22 = EventW;
  if ( EventW )
  {
    v11 = EventW;
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x1B9,
                  (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\commonutil.cpp",
                  v7);
    v10 = LastError;
    v11 = 0;
    if ( LastError < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3B,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UserProcess\\core\\RemoteUHProcessHost.cpp",
        (const char *)(unsigned int)LastError,
        0);
      goto LABEL_32;
    }
  }
  v21 = 0;
  v12 = CCoInit::Initialize((CCoInit *)&v21, v5, v6);
  v10 = v12;
  if ( v12 >= 0 )
  {
    RegisterProxyStubCLSIDs(1u);
    v24 = 0;
    if ( a1 != 12 )
    {
      v10 = -2145116155;
      v13 = 77;
LABEL_17:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v13,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UserProcess\\core\\RemoteUHProcessHost.cpp",
        (const char *)(unsigned int)v10,
        v20);
LABEL_28:
      if ( v24 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
      goto LABEL_30;
    }
    v24 = 0;
    v14 = operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
    v15 = v14;
    if ( !v14 )
    {
      v10 = -2147024882;
LABEL_16:
      v13 = 74;
      goto LABEL_17;
    }
    *((_DWORD *)v14 + 5) = 1;
    *v14 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IRemoteUHOSProcessHost,IRemoteUHProcessHost>::`vftable'{for `IRemoteUHOSProcessHost'};
    v14[1] = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IRemoteUHOSProcessHost,IRemoteUHProcessHost>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IRemoteUHProcessHost>'};
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *v15 = &OSDeploymentRemote::RemoteUHOSDeploymentProcessHost::`vftable'{for `IRemoteUHOSProcessHost'};
    v15[1] = &OSDeploymentRemote::RemoteUHOSDeploymentProcessHost::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IRemoteUHProcessHost>'};
    v15[3] = 0;
    if ( v11 == (char *)-1LL )
    {
      v10 = -2147024809;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Remote\\RemoteUHOSDeploymentProcessHost.cpp",
        (const char *)0x80070057LL,
        0);
      (*(void (__fastcall **)(_QWORD *))(*v15 + 16LL))(v15);
      goto LABEL_16;
    }
    v15[3] = v11;
    v10 = ((__int64 (__fastcall *)(_QWORD *, GUID *, __int64 *))OSDeploymentRemote::RemoteUHOSDeploymentProcessHost::`vftable'{for `IRemoteUHOSProcessHost'})(
            v15,
            &GUID_32bfe70b_f940_46a0_a1aa_9f7e62960294,
            &v24);
    (*(void (__fastcall **)(_QWORD *))(*v15 + 16LL))(v15);
    if ( v10 < 0 )
      goto LABEL_16;
    Handles[0] = 0;
    v10 = RegisterRemoteUHProcessHost(a2, v24, Handles);
    v16 = (char *)Handles[0];
    if ( v10 < 0 )
    {
      v17 = 81;
LABEL_23:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v17,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UserProcess\\core\\RemoteUHProcessHost.cpp",
        (const char *)(unsigned int)v10,
        0);
      goto LABEL_26;
    }
    WUTrace(0, 0, 4096, 4);
    Handles[0] = v16;
    Handles[1] = v8;
    if ( WaitForMultipleObjects(2u, Handles, 0, 0xFFFFFFFF) < 2 )
    {
      WUTrace(0, 0, 4096, 4);
    }
    else
    {
      v10 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0x2E,
              (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UserProcess\\core\\RemoteUHProcessHost.cpp",
              v18);
      if ( v10 < 0 )
      {
        v17 = 84;
        goto LABEL_23;
      }
    }
    v10 = 0;
LABEL_26:
    if ( (unsigned __int64)(v16 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v16);
    goto LABEL_28;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x3E,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UserProcess\\core\\RemoteUHProcessHost.cpp",
    (const char *)(unsigned int)v12,
    0);
LABEL_30:
  if ( v21 )
    CoUninitialize();
LABEL_32:
  if ( (unsigned __int64)(v8 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v8);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140005f84  mov     [rsp-8+arg_10], rbx
0x140005f89  push    rbp
0x140005f8a  push    rsi
0x140005f8b  push    rdi
0x140005f8c  push    r14
0x140005f8e  push    r15
0x140005f90  lea     rbp, [rsp-37h]
0x140005f95  sub     rsp, 0C0h
0x140005f9c  mov     rax, cs:__security_cookie
0x140005fa3  xor     rax, rsp
0x140005fa6  mov     [rbp+57h+var_28], rax
0x140005faa  mov     r15, rdx
0x140005fad  mov     edi, ecx
0x140005faf  lea     rcx, [rbp+57h+var_90]; this
0x140005fb3  call    ??0GuidToString@Trace@@QEAA@AEBU_GUID@@@Z; Trace::GuidToString::GuidToString(_GUID const &)
0x140005fb8  mov     [rsp+0E0h+var_A8], rax
0x140005fbd  mov     [rsp+0E0h+var_B0], edi
0x140005fc1  lea     rax, aStartingRemote; "Starting remote process for UpdateHandl"...
0x140005fc8  mov     [rsp+0E0h+var_B8], rax
0x140005fcd  mov     qword ptr [rsp+0E0h+var_C0], 0; int
0x140005fd6  xor     edx, edx
0x140005fd8  xor     ecx, ecx
0x140005fda  lea     r9d, [rdx+4]
0x140005fde  mov     r8d, 1000h
0x140005fe4  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x140005fe9  nop
0x140005fea  xor     r9d, r9d; lpName
0x140005fed  xor     r8d, r8d; bInitialState
0x140005ff0  lea     edx, [r9+1]; bManualReset
0x140005ff4  xor     ecx, ecx; lpEventAttributes
0x140005ff6  call    cs:__imp_CreateEventW
0x140005ffc  mov     rbx, rax
0x140005fff  mov     [rbp+57h+var_98], rax
0x140006003  test    rax, rax
0x140006006  jnz     short loc_140006041
0x140006008  mov     rcx, [rbp+5Fh]; this
0x14000600c  lea     r8, aCW1SSrcClientL_1; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x140006013  mov     edx, 1B9h; void *
0x140006018  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000601d  mov     esi, eax
0x14000601f  mov     r14, rbx
0x140006022  test    eax, eax
0x140006024  jns     short loc_140006044
0x140006026  mov     rcx, [rbp+5Fh]; this
0x14000602a  mov     r9d, eax; char *
0x14000602d  lea     r8, aCW1SSrcClientU_3; "C:\\__w\\1\\s\\src\\Client\\UserProcess"...
0x140006034  lea     edx, [rbx+3Bh]; void *
0x140006037  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000603c  jmp     loc_1400062B7
0x140006041  mov     r14, rbx
0x140006044  mov     [rbp+57h+var_A0], 0
0x14000604b  lea     rcx, [rbp+57h+var_A0]; this
0x14000604f  call    ?Initialize@CCoInit@@QEAAJK_N@Z; CCoInit::Initialize(ulong,bool)
0x140006054  mov     esi, eax
0x140006056  test    eax, eax
0x140006058  jns     short loc_140006077
0x14000605a  mov     rcx, [rbp+5Fh]; this
0x14000605e  mov     r9d, eax; char *
0x140006061  lea     r8, aCW1SSrcClientU_3; "C:\\__w\\1\\s\\src\\Client\\UserProcess"...
0x140006068  mov     edx, 3Eh ; '>'; void *
0x14000606d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140006072  jmp     loc_1400062AA
0x140006077  mov     esi, 1
0x14000607c  mov     ecx, esi; unsigned int
0x14000607e  call    ?RegisterProxyStubCLSIDs@@YAXK@Z; RegisterProxyStubCLSIDs(ulong)
0x140006083  mov     [rbp+57h+var_40], 0
0x14000608b  cmp     edi, 0Ch
0x14000608e  jz      short loc_14000609F
0x140006090  mov     esi, 80242005h
0x140006095  mov     edx, 4Dh ; 'M'
0x14000609a  jmp     loc_140006186
0x14000609f  mov     [rbp+57h+var_40], 0
0x1400060a7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400060ae  mov     ecx, 20h ; ' '; unsigned __int64
0x1400060b3  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1400060b8  mov     rdi, rax
0x1400060bb  test    rax, rax
0x1400060be  jnz     short loc_1400060CA
0x1400060c0  mov     esi, 8007000Eh
0x1400060c5  jmp     loc_140006181
0x1400060ca  mov     [rax+14h], esi
0x1400060cd  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIRemoteUHOSProcessHost@@UIRemoteUHProcessHost@@@WRL@Microsoft@@6BIRemoteUHOSProcessHost@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IRemoteUHOSProcessHost,IRemoteUHProcessHost>::`vftable'{for `IRemoteUHOSProcessHost'}
0x1400060d4  mov     [rdi], rax
0x1400060d7  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIRemoteUHOSProcessHost@@UIRemoteUHProcessHost@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIRemoteUHProcessHost@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IRemoteUHOSProcessHost,IRemoteUHProcessHost>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IRemoteUHProcessHost>'}
0x1400060de  mov     [rdi+8], rax
0x1400060e2  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1400060e9  test    rcx, rcx
0x1400060ec  jz      short loc_1400060FB
0x1400060ee  mov     rax, [rcx]
0x1400060f1  mov     rax, [rax+8]
0x1400060f5  call    _guard_dispatch_icall
0x1400060fa  nop
0x1400060fb  lea     rax, ??_7RemoteUHOSDeploymentProcessHost@OSDeploymentRemote@@6BIRemoteUHOSProcessHost@@@; const OSDeploymentRemote::RemoteUHOSDeploymentProcessHost::`vftable'{for `IRemoteUHOSProcessHost'}
0x140006102  mov     [rdi], rax
0x140006105  lea     rax, ??_7RemoteUHOSDeploymentProcessHost@OSDeploymentRemote@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIRemoteUHProcessHost@@@Details@WRL@Microsoft@@@; const OSDeploymentRemote::RemoteUHOSDeploymentProcessHost::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IRemoteUHProcessHost>'}
0x14000610c  mov     [rdi+8], rax
0x140006110  mov     qword ptr [rdi+18h], 0
0x140006118  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x14000611c  jnz     short loc_14000614D
0x14000611e  mov     rcx, [rbp+5Fh]; this
0x140006122  mov     esi, 80070057h
0x140006127  mov     r9d, esi; char *
0x14000612a  lea     r8, aCW1SSrcClientE; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x140006131  lea     edx, [r14+0Dh]; void *
0x140006135  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000613a  nop
0x14000613b  mov     rax, [rdi]
0x14000613e  mov     rcx, rdi
0x140006141  mov     rax, [rax+10h]
0x140006145  call    _guard_dispatch_icall
0x14000614a  nop
0x14000614b  jmp     short loc_140006181
0x14000614d  mov     [rdi+18h], r14
0x140006151  lea     r8, [rbp+57h+var_40]
0x140006155  lea     rdx, _GUID_32bfe70b_f940_46a0_a1aa_9f7e62960294
0x14000615c  mov     rcx, rdi
0x14000615f  mov     rax, cs:??_7RemoteUHOSDeploymentProcessHost@OSDeploymentRemote@@6BIRemoteUHOSProcessHost@@@; const OSDeploymentRemote::RemoteUHOSDeploymentProcessHost::`vftable'{for `IRemoteUHOSProcessHost'}
0x140006166  call    _guard_dispatch_icall
0x14000616b  mov     esi, eax
0x14000616d  mov     rax, [rdi]
0x140006170  mov     rcx, rdi
0x140006173  mov     rax, [rax+10h]
0x140006177  call    _guard_dispatch_icall
0x14000617c  nop
0x14000617d  test    esi, esi
0x14000617f  jns     short loc_14000619E
0x140006181  mov     edx, 4Ah ; 'J'; void *
0x140006186  mov     rcx, [rbp+5Fh]; this
0x14000618a  mov     r9d, esi; char *
0x14000618d  lea     r8, aCW1SSrcClientU_3; "C:\\__w\\1\\s\\src\\Client\\UserProcess"...
0x140006194  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140006199  jmp     loc_140006294
0x14000619e  mov     [rbp+57h+Handles], 0
0x1400061a6  lea     r8, [rbp+57h+Handles]
0x1400061aa  mov     rdx, [rbp+57h+var_40]
0x1400061ae  mov     rcx, r15
0x1400061b1  call    RegisterRemoteUHProcessHost
0x1400061b6  mov     esi, eax
0x1400061b8  mov     rdi, [rbp+57h+Handles]
0x1400061bc  test    eax, eax
0x1400061be  jns     short loc_1400061C7
0x1400061c0  mov     edx, 51h ; 'Q'
0x1400061c5  jmp     short loc_140006239
0x1400061c7  lea     rax, aRemoteProcessI; "Remote process is executing and will wa"...
0x1400061ce  mov     [rsp+0E0h+var_B8], rax
0x1400061d3  mov     qword ptr [rsp+0E0h+var_C0], 0; int
0x1400061dc  mov     esi, 1000h
0x1400061e1  mov     r9d, 4
0x1400061e7  mov     r8d, esi
0x1400061ea  xor     edx, edx
0x1400061ec  xor     ecx, ecx
0x1400061ee  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1400061f3  mov     [rbp+57h+Handles], rdi
0x1400061f7  mov     [rbp+57h+var_30], rbx
0x1400061fb  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x1400061ff  xor     r8d, r8d; bWaitAll
0x140006202  lea     rdx, [rbp+57h+Handles]; lpHandles
0x140006206  lea     ecx, [r8+2]; nCount
0x14000620a  call    cs:__imp_WaitForMultipleObjects
0x140006210  test    eax, eax
0x140006212  jz      short loc_140006257
0x140006214  cmp     eax, 1
0x140006217  jz      short loc_14000624E
0x140006219  mov     rcx, [rbp+5Fh]; this
0x14000621d  lea     r8, aCW1SSrcClientU_3; "C:\\__w\\1\\s\\src\\Client\\UserProcess"...
0x140006224  mov     edx, 2Eh ; '.'; void *
0x140006229  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000622e  mov     esi, eax
0x140006230  test    eax, eax
0x140006232  jns     short loc_14000627E
0x140006234  mov     edx, 54h ; 'T'; void *
0x140006239  mov     rcx, [rbp+5Fh]; this
0x14000623d  mov     r9d, esi; char *
0x140006240  lea     r8, aCW1SSrcClientU_3; "C:\\__w\\1\\s\\src\\Client\\UserProcess"...
0x140006247  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000624c  jmp     short loc_140006280
0x14000624e  lea     rax, aShutdownHasBee; "Shutdown has been requested for the rem"...
0x140006255  jmp     short loc_14000625E
0x140006257  lea     rax, aParentProcessH; "Parent process has been terminated, shu"...
0x14000625e  mov     [rsp+0E0h+var_B8], rax
0x140006263  mov     qword ptr [rsp+0E0h+var_C0], 0
0x14000626c  mov     r9d, 4
0x140006272  mov     r8d, esi
0x140006275  xor     edx, edx
0x140006277  xor     ecx, ecx
0x140006279  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x14000627e  xor     esi, esi
0x140006280  lea     rax, [rdi-1]
0x140006284  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140006288  ja      short loc_140006294
0x14000628a  mov     rcx, rdi; hObject
0x14000628d  call    cs:__imp_CloseHandle
0x140006293  nop
0x140006294  mov     rcx, [rbp+57h+var_40]
0x140006298  test    rcx, rcx
0x14000629b  jz      short loc_1400062AA
0x14000629d  mov     rax, [rcx]
0x1400062a0  mov     rax, [rax+10h]
0x1400062a4  call    _guard_dispatch_icall
0x1400062a9  nop
0x1400062aa  cmp     [rbp+57h+var_A0], 0
0x1400062ae  jz      short loc_1400062B7
0x1400062b0  call    cs:__imp_CoUninitialize
0x1400062b6  nop
0x1400062b7  lea     rcx, [rbx-1]
0x1400062bb  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x1400062bf  ja      short loc_1400062CA
0x1400062c1  mov     rcx, rbx; hObject
0x1400062c4  call    cs:__imp_CloseHandle
0x1400062ca  mov     eax, esi
0x1400062cc  mov     rcx, [rbp+57h+var_28]
0x1400062d0  xor     rcx, rsp; StackCookie
0x1400062d3  call    __security_check_cookie
0x1400062d8  mov     rbx, [rsp+0E0h+arg_10]
0x1400062e0  add     rsp, 0C0h
0x1400062e7  pop     r15
0x1400062e9  pop     r14
0x1400062eb  pop     rdi
0x1400062ec  pop     rsi
0x1400062ed  pop     rbp
0x1400062ee  retn
```
