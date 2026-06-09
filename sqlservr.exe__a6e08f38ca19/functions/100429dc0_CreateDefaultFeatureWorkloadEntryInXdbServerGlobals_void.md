# CreateDefaultFeatureWorkloadEntryInXdbServerGlobals(void)

- ea: `0x100429dc0`
- end: `0x10042a375`
- name: `?CreateDefaultFeatureWorkloadEntryInXdbServerGlobals@@YAXXZ`
- size: `1461`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x10042a380`

## callees

- `0x100401010`
- `0x1004010b0`
- `0x100401580`
- `0x100404900`
- `0x100423b10`
- `0x100429dc0`
- `0x100440860`
- `0x10044dbf0`

## import_xrefs

- `sqlmin!GetXdbServerGlobals` at `0x10042a281`
- `sqlmin!GetXdbServerGlobals` at `0x10042a281`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x100429df9`
- `sqldk!??_V@YAXPEAX@Z` at `0x10042a341`
- `sqldk!??_V@YAXPEAX@Z` at `0x10042a341`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100429e42`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100429f11`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10042a305`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100429e42`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100429f11`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10042a305`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100429fb7`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10042a2bb`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100429fb7`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10042a2bb`
- `sqldk!SystemThread_TlsOffset` at `0x100429e27`
- `sqldk!SystemThread_TlsOffset` at `0x100429ef6`
- `sqldk!SystemThread_TlsOffset` at `0x10042a2ec`
- `sqldk!SystemThread_TlsIndex` at `0x100429e1e`
- `sqldk!SystemThread_TlsIndex` at `0x100429eed`
- `sqldk!SystemThread_TlsIndex` at `0x10042a2e3`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x10042a31b`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x10042a31b`
- `sqldk!?hdl_backout@@YAHHHHHPEAD@Z` at `0x100429eb7`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100429f4b`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100429f4b`
- `api-ms-win-crt-string-l1-1-0!wcstok_s` at `0x100429e99`
- `api-ms-win-crt-string-l1-1-0!wcstok_s` at `0x100429e99`

## string_xrefs

- `0x10042a043`: `specified default value %d for %sMaxCpuPercent is outside allowable limits. It should be between 1-100`
- `0x10042a0ad`: `specified default value %d for %sMaxCpu is outside allowable limits. Please set to either -1 or %d-MaxInt`
- `0x10042a11d`: `specified default value %d for %sLogRatePercent is outside allowable limits. It should be between 1-100`
- `0x10042a189`: `specified default value %d for %sLogRate is outside allowable limits. Please set to either -1 or %d-MaxInt`
- `0x10042a1fa`: `specified default value %d for %sMaxIOPSPercent is outside allowable limits. It should be between 1-100`
- `0x10042a264`: `specified default value %d for %sMaxIOPS is outside allowable limits. Please set to either -1 or %d-MaxInt`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void CreateDefaultFeatureWorkloadEntryInXdbServerGlobals(void)
{
  IServerConfiguration *v0; // r15
  __int64 v1; // rbx
  __int64 v2; // r9
  wchar_t *v3; // rcx
  wchar_t *v4; // rsi
  __int64 v5; // rbx
  __int64 v6; // rax
  wchar_t *v7; // rax
  wchar_t *v8; // rdi
  wchar_t *v9; // rbx
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // rax
  __int64 v13; // rbx
  __int64 v14; // rcx
  __int64 v15; // r8
  int v16; // [rsp+20h] [rbp-2E8h]
  int v17; // [rsp+20h] [rbp-2E8h]
  int v18; // [rsp+20h] [rbp-2E8h]
  int v19; // [rsp+20h] [rbp-2E8h]
  unsigned int v20; // [rsp+30h] [rbp-2D8h] BYREF
  __int64 v21; // [rsp+38h] [rbp-2D0h] BYREF
  wchar_t *String; // [rsp+40h] [rbp-2C8h] BYREF
  wchar_t *v23; // [rsp+48h] [rbp-2C0h]
  wchar_t *Context; // [rsp+50h] [rbp-2B8h] BYREF
  wchar_t *v25; // [rsp+58h] [rbp-2B0h]
  int v26; // [rsp+60h] [rbp-2A8h]
  struct IServerConfiguration *v27; // [rsp+68h] [rbp-2A0h]
  _DWORD v28[6]; // [rsp+70h] [rbp-298h] BYREF
  __int64 v29; // [rsp+88h] [rbp-280h]
  struct IMemObj *v30; // [rsp+90h] [rbp-278h]
  wchar_t *v31; // [rsp+98h] [rbp-270h]
  _BYTE v32[16]; // [rsp+A0h] [rbp-268h] BYREF
  _BYTE v33[48]; // [rsp+B0h] [rbp-258h] BYREF
  wchar_t v34[264]; // [rsp+E0h] [rbp-228h] BYREF

  v29 = -2;
  v0 = s_pServerConf;
  v27 = s_pServerConf;
  Context = 0;
  String = 0;
  v1 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v2 = *(_QWORD *)(v1 + 256);
  if ( !v2 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v2 = *(_QWORD *)(v1 + 256);
  }
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, _QWORD, wchar_t **, _QWORD))(*(_QWORD *)s_pServerConf + 528LL))(
    s_pServerConf,
    L"FeatureWorkloadGroupsInUserPool",
    L"GroupNameArray",
    *(_QWORD *)(v2 + 1000),
    &String,
    0);
  v3 = String;
  if ( String )
  {
    while ( 1 )
    {
      v4 = wcstok_s(v3, L";", &Context);
      v25 = v4;
      if ( !v4 )
        break;
      try
      {
        ExcHandler::ExcHandler((ExcHandler *)v33, 0, 0, 0, hdl_backout, 0);
        v23 = 0;
        v26 = 3939;
        v5 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
        v6 = *(_QWORD *)(v5 + 256);
        if ( !v6 )
        {
          SystemThread::MakeMiniSOSThread(0);
          v6 = *(_QWORD *)(v5 + 256);
        }
        v30 = *(struct IMemObj **)(*(_QWORD *)(v6 + 992) + 320LL);
        v7 = (wchar_t *)operator new(0x240u, v30, "sql\\ntdbms\\ksource\\dbfabric.cpp", 3939, 6u);
        v8 = v7;
        v31 = v7;
        if ( v7 )
        {
          *(_QWORD *)v7 = 0;
          *((_QWORD *)v7 + 1) = 0;
          *((_DWORD *)v7 + 135) = 30;
          *((_DWORD *)v7 + 136) = 2;
          *((_DWORD *)v7 + 137) = 30;
          *((_QWORD *)v7 + 69) = 1024;
          *((_DWORD *)v7 + 140) = 30;
          *((_QWORD *)v7 + 71) = 8;
        }
        else
        {
          v8 = 0;
        }
        if ( v8 )
          operator delete(0, 0x240u);
        v9 = v8;
        v23 = v8;
        if ( v8 )
        {
          if ( (int)StringCchCopyW(v8 + 8, 0x105u, v4) < 0 )
          {
            LogSystemMetadataNotSentToClient(L"Default resource group %s name could not be copied", v4);
          }
          else
          {
            ConcatenateWCHARArray(v4, L"MaxCpuPercent", v34);
            LOBYTE(v16) = 0;
            if ( (*(unsigned __int8 (__fastcall **)(IServerConfiguration *, const wchar_t *, wchar_t *, unsigned int *, int, _QWORD))(*(_QWORD *)v0 + 520LL))(
                   v0,
                   L"FeatureWorkloadGroupsInUserPool",
                   v34,
                   &v20,
                   v16,
                   0) )
            {
              if ( v20 - 1 > 0x63 )
                LogSystemMetadataNotSentToClient(
                  L"specified default value %d for %sMaxCpuPercent is outside allowable limits. It should be between 1-100",
                  v20,
                  v4);
              else
                *((_DWORD *)v8 + 135) = v20;
            }
            ConcatenateWCHARArray(v4, L"MaxCpu", v34);
            LOBYTE(v17) = 0;
            if ( (*(unsigned __int8 (__fastcall **)(IServerConfiguration *, const wchar_t *, wchar_t *, unsigned int *, int, _QWORD))(*(_QWORD *)v0 + 520LL))(
                   v0,
                   L"FeatureWorkloadGroupsInUserPool",
                   v34,
                   &v20,
                   v17,
                   0) )
            {
              if ( v20 == -1 || (int)v20 >= 2 )
                *((_DWORD *)v8 + 136) = v20;
              else
                LogSystemMetadataNotSentToClient(
                  L"specified default value %d for %sMaxCpu is outside allowable limits. Please set to either -1 or %d-MaxInt",
                  v20,
                  v4,
                  2);
            }
            ConcatenateWCHARArray(v4, L"LogRatePercent", v34);
            LOBYTE(v18) = 0;
            if ( (*(unsigned __int8 (__fastcall **)(IServerConfiguration *, const wchar_t *, wchar_t *, unsigned int *, int, _QWORD))(*(_QWORD *)v0 + 520LL))(
                   v0,
                   L"FeatureWorkloadGroupsInUserPool",
                   v34,
                   &v20,
                   v18,
                   0) )
            {
              if ( v20 - 1 > 0x63 )
                LogSystemMetadataNotSentToClient(
                  L"specified default value %d for %sLogRatePercent is outside allowable limits. It should be between 1-100",
                  v20,
                  v4);
              else
                *((_DWORD *)v8 + 137) = v20;
            }
            ConcatenateWCHARArray(v4, L"LogRate", v34);
            if ( IServerConfiguration::GetDynamicInt64Setting(v0, L"FeatureWorkloadGroupsInUserPool", v34, &v21, 0, 0) )
            {
              if ( v21 == -1 || v21 >= 1024 )
                *((_QWORD *)v8 + 69) = v21;
              else
                LogSystemMetadataNotSentToClient(
                  L"specified default value %d for %sLogRate is outside allowable limits. Please set to either -1 or %d-MaxInt",
                  v21,
                  v4,
                  1024);
            }
            ConcatenateWCHARArray(v4, L"MaxIOPSPercent", v34);
            LOBYTE(v19) = 0;
            if ( (*(unsigned __int8 (__fastcall **)(IServerConfiguration *, const wchar_t *, wchar_t *, unsigned int *, int, _QWORD))(*(_QWORD *)v0 + 520LL))(
                   v0,
                   L"FeatureWorkloadGroupsInUserPool",
                   v34,
                   &v20,
                   v19,
                   0) )
            {
              if ( v20 - 1 > 0x63 )
                LogSystemMetadataNotSentToClient(
                  L"specified default value %d for %sMaxIOPSPercent is outside allowable limits. It should be between 1-100",
                  v20,
                  v4);
              else
                *((_DWORD *)v8 + 140) = v20;
            }
            ConcatenateWCHARArray(v4, L"MaxIOPS", v34);
            if ( IServerConfiguration::GetDynamicInt64Setting(v0, L"FeatureWorkloadGroupsInUserPool", v34, &v21, 0, 0) )
            {
              if ( v21 == -1 || v21 >= 8 )
                *((_QWORD *)v8 + 71) = v21;
              else
                LogSystemMetadataNotSentToClient(
                  L"specified default value %d for %sMaxIOPS is outside allowable limits. Please set to either -1 or %d-MaxInt",
                  v21,
                  v4,
                  8);
            }
            v9 = 0;
            v23 = 0;
            v12 = GetXdbServerGlobals(v11, v10) + 28296;
            *(_QWORD *)v8 = *(_QWORD *)v12;
            *(_QWORD *)(*(_QWORD *)v12 + 8LL) = v8;
            *(_QWORD *)v12 = v8;
            *((_QWORD *)v8 + 1) = v12;
          }
        }
        operator delete(v9, 0x240u);
        ExcHandler::~ExcHandler((ExcHandler *)v33);
      }
      catch ( SQLError v28 )
      {
        try
        {
          ExceptionBackout::ExceptionBackout((ExceptionBackout *)v32, (const struct SQLError *)v28);
          if ( v28[4] == 1 )
            v15 = v28[0];
          else
            v15 = LOWORD(v28[0]);
          LogSystemMetadataNotSentToClient(
            L"Default resource group %s could not be read or created. Error : %d, State : %d",
            v25,
            v15,
            v28[3]);
          ExceptionBackout::~ExceptionBackout((ExceptionBackout *)v32);
        }
        catch ( ShortStackException )
        {
        }
        v0 = v27;
      }
      v13 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v14 = *(_QWORD *)(v13 + 256);
      if ( !v14 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v14 = *(_QWORD *)(v13 + 256);
      }
      if ( *(_DWORD *)(v14 + 556) )
        ExceptionPostCatchActions((struct Worker *)v14);
      v3 = 0;
    }
  }
  else
  {
    LogSystemMetadataNotSentToClient(
      L"Section :: %s setting :: GroupNameArray not available",
      L"FeatureWorkloadGroupsInUserPool");
  }
  operator delete[](String);
}

```

## disassembly

```asm
0x100429dc0  mov     rax, rsp
0x100429dc3  push    r15
0x100429dc5  sub     rsp, 300h
0x100429dcc  mov     qword ptr [rax-280h], 0FFFFFFFFFFFFFFFEh
0x100429dd7  mov     [rax+8], rbx
0x100429ddb  mov     [rax+10h], rsi
0x100429ddf  mov     [rax+18h], rdi
0x100429de3  mov     [rax+20h], r14
0x100429de7  mov     rax, cs:__security_cookie
0x100429dee  xor     rax, rsp
0x100429df1  mov     [rsp+308h+var_18], rax
0x100429df9  mov     rax, cs:__imp_?s_pServerConf@@3PEAVIServerConfiguration@@EA; IServerConfiguration * s_pServerConf
0x100429e00  mov     r15, [rax]
0x100429e03  mov     [rsp+308h+var_2A0], r15
0x100429e08  xor     r14d, r14d
0x100429e0b  mov     [rsp+308h+Context], r14
0x100429e10  mov     [rsp+308h+String], r14
0x100429e15  mov     rdx, gs:58h
0x100429e1e  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100429e25  mov     ecx, [rax]
0x100429e27  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100429e2e  mov     ebx, [rax]
0x100429e30  add     rbx, [rdx+rcx*8]
0x100429e34  mov     r9, [rbx+100h]
0x100429e3b  test    r9, r9
0x100429e3e  jnz     short loc_100429E4F
0x100429e40  xor     ecx, ecx
0x100429e42  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100429e48  mov     r9, [rbx+100h]
0x100429e4f  mov     rax, [r15]
0x100429e52  mov     [rsp+308h+var_2E0], r14
0x100429e57  lea     rcx, [rsp+308h+String]
0x100429e5c  mov     [rsp+308h+var_2E8], rcx
0x100429e61  mov     r9, [r9+3E8h]
0x100429e68  lea     r8, aGroupnamearray; "GroupNameArray"
0x100429e6f  lea     rdx, aFeatureworkloa; "FeatureWorkloadGroupsInUserPool"
0x100429e76  mov     rcx, r15
0x100429e79  call    qword ptr [rax+210h]
0x100429e7f  mov     rcx, [rsp+308h+String]; String
0x100429e84  test    rcx, rcx
0x100429e87  jz      loc_10042A328
0x100429e8d  lea     r8, [rsp+308h+Context]; Context
0x100429e92  lea     rdx, pszSrc; ";"
0x100429e99  call    cs:__imp_wcstok_s
0x100429e9f  mov     rsi, rax
0x100429ea2  mov     [rsp+308h+var_2B0], rax
0x100429ea7  test    rax, rax
0x100429eaa  jz      loc_10042A33C
0x100429eb0  xor     edx, edx; unsigned __int16
0x100429eb2  mov     [rsp+308h+var_2E0], r14; struct Worker *
0x100429eb7  mov     rax, cs:__imp_?hdl_backout@@YAHHHHHPEAD@Z; hdl_backout(int,int,int,int,char *)
0x100429ebe  mov     [rsp+308h+var_2E8], rax; int (*)(int, int, int, int, char *)
0x100429ec3  xor     r9d, r9d; unsigned __int8
0x100429ec6  xor     r8d, r8d; unsigned __int8
0x100429ec9  lea     rcx, [rsp+308h+var_258]; this
0x100429ed1  call    ??0ExcHandler@@QEAA@GEEP6AHHHHHPEAD@ZPEAVWorker@@@Z; ExcHandler::ExcHandler(ushort,uchar,uchar,int (*)(int,int,int,int,char *),Worker *)
0x100429ed6  nop
0x100429ed7  mov     [rsp+308h+var_2C0], r14
0x100429edc  mov     [rsp+308h+var_2A8], 0F63h
0x100429ee4  mov     rdx, gs:58h
0x100429eed  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100429ef4  mov     ecx, [rax]
0x100429ef6  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100429efd  mov     ebx, [rax]
0x100429eff  add     rbx, [rdx+rcx*8]
0x100429f03  mov     rax, [rbx+100h]
0x100429f0a  test    rax, rax
0x100429f0d  jnz     short loc_100429F1E
0x100429f0f  xor     ecx, ecx
0x100429f11  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100429f17  mov     rax, [rbx+100h]
0x100429f1e  mov     rax, [rax+3E0h]
0x100429f25  mov     rdx, [rax+140h]
0x100429f2c  mov     [rsp+308h+var_278], rdx
0x100429f34  mov     byte ptr [rsp+308h+var_2E8], 6
0x100429f39  mov     r9d, 0F63h
0x100429f3f  lea     r8, aSqlNtdbmsKsour; "sql\\ntdbms\\ksource\\dbfabric.cpp"
0x100429f46  mov     ecx, 240h
0x100429f4b  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new(unsigned __int64,IMemObj *,char const *,int,uchar)
0x100429f51  mov     rdi, rax
0x100429f54  mov     [rsp+308h+var_270], rax
0x100429f5c  test    rax, rax
0x100429f5f  jz      short loc_100429FA8
0x100429f61  mov     [rax], r14
0x100429f64  mov     [rax+8], r14
0x100429f68  mov     dword ptr [rax+21Ch], 1Eh
0x100429f72  mov     dword ptr [rax+220h], 2
0x100429f7c  mov     dword ptr [rax+224h], 1Eh
0x100429f86  mov     qword ptr [rax+228h], 400h
0x100429f91  mov     dword ptr [rax+230h], 1Eh
0x100429f9b  mov     qword ptr [rax+238h], 8
0x100429fa6  jmp     short loc_100429FAB
0x100429fa8  mov     rdi, r14
0x100429fab  test    rdi, rdi
0x100429fae  jz      short loc_100429FBD
0x100429fb0  mov     edx, 240h
0x100429fb5  xor     ecx, ecx
0x100429fb7  call    cs:__imp_??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x100429fbd  mov     rbx, rdi
0x100429fc0  mov     [rsp+308h+var_2C0], rbx
0x100429fc5  test    rdi, rdi
0x100429fc8  jz      loc_10042A2B3
0x100429fce  lea     rcx, [rdi+10h]; wchar_t *
0x100429fd2  mov     r8, rsi; wchar_t *
0x100429fd5  mov     edx, 105h; unsigned __int64
0x100429fda  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x100429fdf  test    eax, eax
0x100429fe1  js      loc_10042A2A3
0x100429fe7  lea     r8, [rsp+308h+var_228]; wchar_t *
0x100429fef  lea     rdx, aMaxcpupercent; "MaxCpuPercent"
0x100429ff6  mov     rcx, rsi; wchar_t *
0x100429ff9  call    ?ConcatenateWCHARArray@@YAXPEB_W0PEA_W@Z; ConcatenateWCHARArray(wchar_t const *,wchar_t const *,wchar_t *)
0x100429ffe  mov     rax, [r15]
0x10042a001  mov     [rsp+308h+var_2E0], r14
0x10042a006  mov     byte ptr [rsp+308h+var_2E8], 0
0x10042a00b  lea     r9, [rsp+308h+var_2D8]
0x10042a010  lea     r8, [rsp+308h+var_228]
0x10042a018  lea     rdx, aFeatureworkloa; "FeatureWorkloadGroupsInUserPool"
0x10042a01f  mov     rcx, r15
0x10042a022  call    qword ptr [rax+208h]
0x10042a028  test    al, al
0x10042a02a  jz      short loc_10042A04F
0x10042a02c  mov     edx, [rsp+308h+var_2D8]
0x10042a030  lea     eax, [rdx-1]
0x10042a033  cmp     eax, 63h ; 'c'
0x10042a036  ja      short loc_10042A040
0x10042a038  mov     [rdi+21Ch], edx
0x10042a03e  jmp     short loc_10042A04F
0x10042a040  mov     r8, rsi
0x10042a043  lea     rcx, aSpecifiedDefau_0; "specified default value %d for %sMaxCpu"...
0x10042a04a  call    ?LogSystemMetadataNotSentToClient@@YAXPEB_WZZ; LogSystemMetadataNotSentToClient(wchar_t const *,...)
0x10042a04f  lea     r8, [rsp+308h+var_228]; wchar_t *
0x10042a057  lea     rdx, aMaxcpu; "MaxCpu"
0x10042a05e  mov     rcx, rsi; wchar_t *
0x10042a061  call    ?ConcatenateWCHARArray@@YAXPEB_W0PEA_W@Z; ConcatenateWCHARArray(wchar_t const *,wchar_t const *,wchar_t *)
0x10042a066  mov     rax, [r15]
0x10042a069  mov     [rsp+308h+var_2E0], r14
0x10042a06e  mov     byte ptr [rsp+308h+var_2E8], 0
0x10042a073  lea     r9, [rsp+308h+var_2D8]
0x10042a078  lea     r8, [rsp+308h+var_228]
0x10042a080  lea     rdx, aFeatureworkloa; "FeatureWorkloadGroupsInUserPool"
0x10042a087  mov     rcx, r15
0x10042a08a  call    qword ptr [rax+208h]
0x10042a090  test    al, al
0x10042a092  jz      short loc_10042A0C1
0x10042a094  mov     eax, [rsp+308h+var_2D8]
0x10042a098  cmp     eax, 0FFFFFFFFh
0x10042a09b  jz      short loc_10042A0BB
0x10042a09d  cmp     eax, 2
0x10042a0a0  jge     short loc_10042A0BB
0x10042a0a2  mov     r9d, 2
0x10042a0a8  mov     r8, rsi
0x10042a0ab  mov     edx, eax
0x10042a0ad  lea     rcx, aSpecifiedDefau_4; "specified default value %d for %sMaxCpu"...
0x10042a0b4  call    ?LogSystemMetadataNotSentToClient@@YAXPEB_WZZ; LogSystemMetadataNotSentToClient(wchar_t const *,...)
0x10042a0b9  jmp     short loc_10042A0C1
0x10042a0bb  mov     [rdi+220h], eax
0x10042a0c1  lea     r8, [rsp+308h+var_228]; wchar_t *
0x10042a0c9  lea     rdx, aLogratepercent; "LogRatePercent"
0x10042a0d0  mov     rcx, rsi; wchar_t *
0x10042a0d3  call    ?ConcatenateWCHARArray@@YAXPEB_W0PEA_W@Z; ConcatenateWCHARArray(wchar_t const *,wchar_t const *,wchar_t *)
0x10042a0d8  mov     rax, [r15]
0x10042a0db  mov     [rsp+308h+var_2E0], r14
0x10042a0e0  mov     byte ptr [rsp+308h+var_2E8], 0
0x10042a0e5  lea     r9, [rsp+308h+var_2D8]
0x10042a0ea  lea     r8, [rsp+308h+var_228]
0x10042a0f2  lea     rdx, aFeatureworkloa; "FeatureWorkloadGroupsInUserPool"
0x10042a0f9  mov     rcx, r15
0x10042a0fc  call    qword ptr [rax+208h]
0x10042a102  test    al, al
0x10042a104  jz      short loc_10042A129
0x10042a106  mov     edx, [rsp+308h+var_2D8]
0x10042a10a  lea     eax, [rdx-1]
0x10042a10d  cmp     eax, 63h ; 'c'
0x10042a110  ja      short loc_10042A11A
0x10042a112  mov     [rdi+224h], edx
0x10042a118  jmp     short loc_10042A129
0x10042a11a  mov     r8, rsi
0x10042a11d  lea     rcx, aSpecifiedDefau_2; "specified default value %d for %sLogRat"...
0x10042a124  call    ?LogSystemMetadataNotSentToClient@@YAXPEB_WZZ; LogSystemMetadataNotSentToClient(wchar_t const *,...)
0x10042a129  lea     r8, [rsp+308h+var_228]; wchar_t *
0x10042a131  lea     rdx, aLograte; "LogRate"
0x10042a138  mov     rcx, rsi; wchar_t *
0x10042a13b  call    ?ConcatenateWCHARArray@@YAXPEB_W0PEA_W@Z; ConcatenateWCHARArray(wchar_t const *,wchar_t const *,wchar_t *)
0x10042a140  mov     [rsp+308h+var_2E0], r14; wchar_t *
0x10042a145  mov     byte ptr [rsp+308h+var_2E8], 0; bool
0x10042a14a  lea     r9, [rsp+308h+var_2D0]; __int64 *
0x10042a14f  lea     r8, [rsp+308h+var_228]; wchar_t *
0x10042a157  lea     rdx, aFeatureworkloa; "FeatureWorkloadGroupsInUserPool"
0x10042a15e  mov     rcx, r15; this
0x10042a161  call    ?GetDynamicInt64Setting@IServerConfiguration@@QEAA_NPEB_W0PEA_J_N0@Z; IServerConfiguration::GetDynamicInt64Setting(wchar_t const *,wchar_t const *,__int64 *,bool,wchar_t const *)
0x10042a166  test    al, al
0x10042a168  jz      short loc_10042A19E
0x10042a16a  mov     rax, [rsp+308h+var_2D0]
0x10042a16f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x10042a173  jz      short loc_10042A197
0x10042a175  cmp     rax, 400h
0x10042a17b  jge     short loc_10042A197
0x10042a17d  mov     r9d, 400h
0x10042a183  mov     r8, rsi
0x10042a186  mov     rdx, rax
0x10042a189  lea     rcx, aSpecifiedDefau_3; "specified default value %d for %sLogRat"...
0x10042a190  call    ?LogSystemMetadataNotSentToClient@@YAXPEB_WZZ; LogSystemMetadataNotSentToClient(wchar_t const *,...)
0x10042a195  jmp     short loc_10042A19E
0x10042a197  mov     [rdi+228h], rax
0x10042a19e  lea     r8, [rsp+308h+var_228]; wchar_t *
0x10042a1a6  lea     rdx, aMaxiopspercent; "MaxIOPSPercent"
0x10042a1ad  mov     rcx, rsi; wchar_t *
0x10042a1b0  call    ?ConcatenateWCHARArray@@YAXPEB_W0PEA_W@Z; ConcatenateWCHARArray(wchar_t const *,wchar_t const *,wchar_t *)
0x10042a1b5  mov     rax, [r15]
0x10042a1b8  mov     [rsp+308h+var_2E0], r14
0x10042a1bd  mov     byte ptr [rsp+308h+var_2E8], 0
0x10042a1c2  lea     r9, [rsp+308h+var_2D8]
0x10042a1c7  lea     r8, [rsp+308h+var_228]
0x10042a1cf  lea     rdx, aFeatureworkloa; "FeatureWorkloadGroupsInUserPool"
0x10042a1d6  mov     rcx, r15
0x10042a1d9  call    qword ptr [rax+208h]
0x10042a1df  test    al, al
0x10042a1e1  jz      short loc_10042A206
0x10042a1e3  mov     edx, [rsp+308h+var_2D8]
0x10042a1e7  lea     eax, [rdx-1]
0x10042a1ea  cmp     eax, 63h ; 'c'
0x10042a1ed  ja      short loc_10042A1F7
0x10042a1ef  mov     [rdi+230h], edx
0x10042a1f5  jmp     short loc_10042A206
0x10042a1f7  mov     r8, rsi
0x10042a1fa  lea     rcx, aSpecifiedDefau; "specified default value %d for %sMaxIOP"...
0x10042a201  call    ?LogSystemMetadataNotSentToClient@@YAXPEB_WZZ; LogSystemMetadataNotSentToClient(wchar_t const *,...)
0x10042a206  lea     r8, [rsp+308h+var_228]; wchar_t *
0x10042a20e  lea     rdx, aMaxiops; "MaxIOPS"
0x10042a215  mov     rcx, rsi; wchar_t *
0x10042a218  call    ?ConcatenateWCHARArray@@YAXPEB_W0PEA_W@Z; ConcatenateWCHARArray(wchar_t const *,wchar_t const *,wchar_t *)
0x10042a21d  mov     [rsp+308h+var_2E0], r14; wchar_t *
0x10042a222  mov     byte ptr [rsp+308h+var_2E8], 0; bool
0x10042a227  lea     r9, [rsp+308h+var_2D0]; __int64 *
0x10042a22c  lea     r8, [rsp+308h+var_228]; wchar_t *
0x10042a234  lea     rdx, aFeatureworkloa; "FeatureWorkloadGroupsInUserPool"
0x10042a23b  mov     rcx, r15; this
0x10042a23e  call    ?GetDynamicInt64Setting@IServerConfiguration@@QEAA_NPEB_W0PEA_J_N0@Z; IServerConfiguration::GetDynamicInt64Setting(wchar_t const *,wchar_t const *,__int64 *,bool,wchar_t const *)
0x10042a243  test    al, al
0x10042a245  jz      short loc_10042A279
0x10042a247  mov     rax, [rsp+308h+var_2D0]
0x10042a24c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x10042a250  jz      short loc_10042A272
0x10042a252  cmp     rax, 8
0x10042a256  jge     short loc_10042A272
0x10042a258  mov     r9d, 8
0x10042a25e  mov     r8, rsi
0x10042a261  mov     rdx, rax
0x10042a264  lea     rcx, aSpecifiedDefau_1; "specified default value %d for %sMaxIOP"...
0x10042a26b  call    ?LogSystemMetadataNotSentToClient@@YAXPEB_WZZ; LogSystemMetadataNotSentToClient(wchar_t const *,...)
0x10042a270  jmp     short loc_10042A279
0x10042a272  mov     [rdi+238h], rax
0x10042a279  mov     rbx, r14
0x10042a27c  mov     [rsp+308h+var_2C0], rbx
0x10042a281  call    cs:__imp_GetXdbServerGlobals
0x10042a287  add     rax, 6E88h
0x10042a28d  mov     rcx, [rax]
0x10042a290  mov     [rdi], rcx
0x10042a293  mov     rcx, [rax]
0x10042a296  mov     [rcx+8], rdi
0x10042a29a  mov     [rax], rdi
0x10042a29d  mov     [rdi+8], rax
0x10042a2a1  jmp     short loc_10042A2B3
0x10042a2a3  mov     rdx, rsi
0x10042a2a6  lea     rcx, aDefaultResourc_0; "Default resource group %s name could no"...
0x10042a2ad  call    ?LogSystemMetadataNotSentToClient@@YAXPEB_WZZ; LogSystemMetadataNotSentToClient(wchar_t const *,...)
0x10042a2b2  nop
0x10042a2b3  mov     edx, 240h
0x10042a2b8  mov     rcx, rbx
0x10042a2bb  call    cs:__imp_??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x10042a2c1  nop
0x10042a2c2  lea     rcx, [rsp+308h+var_258]; this
0x10042a2ca  call    ??1ExcHandler@@QEAA@XZ; ExcHandler::~ExcHandler(void)
0x10042a2cf  nop
0x10042a2d0  jmp     short loc_10042A2DA
0x10042a2d2  xor     r14d, r14d
0x10042a2d5  mov     r15, [rsp+308h+var_2A0]
0x10042a2da  mov     rdx, gs:58h
0x10042a2e3  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10042a2ea  mov     ecx, [rax]
0x10042a2ec  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10042a2f3  mov     ebx, [rax]
0x10042a2f5  add     rbx, [rdx+rcx*8]
0x10042a2f9  mov     rcx, [rbx+100h]
0x10042a300  test    rcx, rcx
0x10042a303  jnz     short loc_10042A312
0x10042a305  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10042a30b  mov     rcx, [rbx+100h]
0x10042a312  cmp     dword ptr [rcx+22Ch], 0
0x10042a319  jz      short loc_10042A321
0x10042a31b  call    cs:__imp_?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z; ExceptionPostCatchActions(Worker *)
0x10042a321  xor     ecx, ecx
0x10042a323  jmp     loc_100429E8D
0x10042a328  lea     rdx, aFeatureworkloa; "FeatureWorkloadGroupsInUserPool"
0x10042a32f  lea     rcx, aSectionSSettin; "Section :: %s setting :: GroupNameArray"...
0x10042a336  call    ?LogSystemMetadataNotSentToClient@@YAXPEB_WZZ; LogSystemMetadataNotSentToClient(wchar_t const *,...)
0x10042a33b  nop
0x10042a33c  mov     rcx, [rsp+308h+String]
0x10042a341  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
  ... truncated ...
```
