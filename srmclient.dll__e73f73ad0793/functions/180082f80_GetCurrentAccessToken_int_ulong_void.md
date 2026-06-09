# GetCurrentAccessToken(int,ulong,void * *)

- ea: `0x180082f80`
- end: `0x1800832f2`
- name: `?GetCurrentAccessToken@@YA_NHKPEAPEAX@Z`
- size: `882`
- prototype: `bool(int, unsigned int, void **)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180081e14`
- `0x1800832f8`

## callees

- `0x180006a1c`
- `0x18006fe68`
- `0x18006febc`
- `0x1800700b8`
- `0x180074a04`
- `0x180075034`
- `0x180082f80`
- `0x1800b078a`
- `0x1800b07d0`

## import_xrefs

- `ole32!CoImpersonateClient` at `0x180083031`
- `ole32!CoImpersonateClient` at `0x180083031`
- `ole32!CoRevertToSelf` at `0x1800830b1`
- `ole32!CoRevertToSelf` at `0x1800830b1`
- `KERNEL32!GetCurrentProcess` at `0x180083049`
- `KERNEL32!GetCurrentProcess` at `0x18008311f`
- `KERNEL32!GetCurrentProcess` at `0x180083049`
- `KERNEL32!GetCurrentProcess` at `0x18008311f`
- `KERNEL32!GetLastError` at `0x18008309c`
- `KERNEL32!GetLastError` at `0x18008310e`
- `KERNEL32!GetLastError` at `0x18008309c`
- `KERNEL32!GetLastError` at `0x18008310e`
- `KERNEL32!GetCurrentThread` at `0x180083080`
- `KERNEL32!GetCurrentThread` at `0x1800830d7`
- `KERNEL32!GetCurrentThread` at `0x180083080`
- `KERNEL32!GetCurrentThread` at `0x1800830d7`
- `ADVAPI32!OpenProcessToken` at `0x180083058`
- `ADVAPI32!OpenProcessToken` at `0x180083130`
- `ADVAPI32!OpenProcessToken` at `0x180083058`
- `ADVAPI32!OpenProcessToken` at `0x180083130`
- `ADVAPI32!OpenThreadToken` at `0x180083094`
- `ADVAPI32!OpenThreadToken` at `0x1800830eb`
- `ADVAPI32!OpenThreadToken` at `0x180083094`
- `ADVAPI32!OpenThreadToken` at `0x1800830eb`

## string_xrefs

- `0x180082fbc`: `base\fs\fsrm\utilities\security\srmsec.cpp`
- `0x180082fc8`: `GetCurrentAccessToken`
- `0x180083261`: `OpenThreadToken`
- `0x1800832de`: `OpenThreadToken`
- `0x1800831e4`: `CoImpersonateClient`
- `0x18008319c`: `OpenProcessToken`
- `0x180083224`: `OpenProcessToken`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
char __fastcall GetCurrentAccessToken(int a1, __int64 a2, void **a3)
{
  char v5; // di
  HRESULT v6; // eax
  HANDLE CurrentProcess; // rax
  HANDLE CurrentThread; // rax
  BOOL v9; // esi
  signed int LastError; // eax
  unsigned int v11; // ebx
  HANDLE v12; // rax
  HANDLE v14; // rax
  __int64 v15; // rax
  unsigned int Hr; // ebx
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rax
  _QWORD v22[3]; // [rsp+48h] [rbp-B8h] BYREF
  int v23; // [rsp+60h] [rbp-A0h]
  int v24; // [rsp+64h] [rbp-9Ch]
  int v25; // [rsp+68h] [rbp-98h]
  _BYTE v26[96]; // [rsp+70h] [rbp-90h] BYREF
  int v27; // [rsp+D0h] [rbp-30h]
  _BYTE v28[152]; // [rsp+D8h] [rbp-28h] BYREF
  void **v29; // [rsp+170h] [rbp+70h] BYREF
  HRESULT v30; // [rsp+178h] [rbp+78h]

  v22[0] = L"base\\fs\\fsrm\\utilities\\security\\srmsec.cpp";
  v22[1] = L"GetCurrentAccessToken";
  v22[2] = L"SECSECRC";
  v23 = 83;
  v24 = 17;
  v25 = 255;
  v27 = 0x1000000;
  v5 = 1;
  memset_0(v26, 0, sizeof(v26));
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)&v29, (const struct CSrmDebugInfo *)v22, 0);
  if ( a1 )
  {
    v6 = CoImpersonateClient();
    v30 = v6;
    if ( v6 >= 0 )
    {
      CurrentThread = GetCurrentThread();
      v9 = OpenThreadToken(CurrentThread, 8u, 1, a3);
      LastError = GetLastError();
      v11 = LastError;
      if ( LastError > 0 )
        v11 = (unsigned __int16)LastError | 0x80070000;
      v30 = CoRevertToSelf();
      if ( v30 < 0 )
      {
        v20 = CSrmDebugInfo::CSrmDebugInfo(
                (__int64)v28,
                (__int64)L"base\\fs\\fsrm\\utilities\\security\\srmsec.cpp",
                (__int64)L"SECSECRC",
                (__int64)L"GetCurrentAccessToken",
                122,
                17);
        CSrmFunctionTracer::TranslateWin32Error(&v29, v20, L"CoRevertToSelf");
      }
      if ( !v9 )
      {
        v19 = CSrmDebugInfo::CSrmDebugInfo(
                (__int64)v28,
                (__int64)L"base\\fs\\fsrm\\utilities\\security\\srmsec.cpp",
                (__int64)L"SECSECRC",
                (__int64)L"GetCurrentAccessToken",
                127,
                17);
        CSrmFunctionTracer::TranslateGenericError(&v29, v19, v11, L"OpenThreadToken");
      }
      v29 = &CSrmFunctionTracer::`vftable';
    }
    else
    {
      if ( v6 != -2147417833 )
      {
        Hr = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v29);
        v17 = CSrmDebugInfo::CSrmDebugInfo(
                (__int64)v28,
                (__int64)L"base\\fs\\fsrm\\utilities\\security\\srmsec.cpp",
                (__int64)L"SECSECRC",
                (__int64)L"GetCurrentAccessToken",
                96,
                17);
        CSrmFunctionTracer::TranslateGenericError(&v29, v17, Hr, L"CoImpersonateClient");
      }
      CurrentProcess = GetCurrentProcess();
      if ( !OpenProcessToken(CurrentProcess, 8u, a3) )
      {
        v18 = CSrmDebugInfo::CSrmDebugInfo(
                (__int64)v28,
                (__int64)L"base\\fs\\fsrm\\utilities\\security\\srmsec.cpp",
                (__int64)L"SECSECRC",
                (__int64)L"GetCurrentAccessToken",
                104,
                17);
        CSrmFunctionTracer::TranslateWin32Error(&v29, v18, L"OpenProcessToken");
      }
      v30 = 0;
      v29 = &CSrmFunctionTracer::`vftable';
      v5 = 0;
    }
    goto LABEL_13;
  }
  v12 = GetCurrentThread();
  if ( OpenThreadToken(v12, 8u, 1, a3) )
  {
    v29 = &CSrmFunctionTracer::`vftable';
LABEL_13:
    CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v29);
    return v5;
  }
  if ( GetLastError() != 1008 )
  {
    v21 = CSrmDebugInfo::CSrmDebugInfo(
            (__int64)v28,
            (__int64)L"base\\fs\\fsrm\\utilities\\security\\srmsec.cpp",
            (__int64)L"SECSECRC",
            (__int64)L"GetCurrentAccessToken",
            156,
            17);
    CSrmFunctionTracer::TranslateWin32Error(&v29, v21, L"OpenThreadToken");
  }
  v14 = GetCurrentProcess();
  if ( !OpenProcessToken(v14, 8u, a3) )
  {
    v15 = CSrmDebugInfo::CSrmDebugInfo(
            (__int64)v28,
            (__int64)L"base\\fs\\fsrm\\utilities\\security\\srmsec.cpp",
            (__int64)L"SECSECRC",
            (__int64)L"GetCurrentAccessToken",
            163,
            17);
    CSrmFunctionTracer::TranslateWin32Error(&v29, v15, L"OpenProcessToken");
  }
  v29 = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v29);
  return 0;
}

```

## disassembly

```asm
0x180082f80  push    rbp
0x180082f82  push    rbx
0x180082f83  push    rsi
0x180082f84  push    rdi
0x180082f85  push    r12
0x180082f87  push    r13
0x180082f89  push    r14
0x180082f8b  push    r15
0x180082f8d  lea     rbp, [rsp-138h]
0x180082f95  sub     rsp, 238h
0x180082f9c  mov     rax, cs:__security_cookie
0x180082fa3  xor     rax, rsp
0x180082fa6  mov     [rbp+170h+var_50], rax
0x180082fad  mov     rsi, r8
0x180082fb0  mov     ebx, ecx
0x180082fb2  lea     rax, [rsp+270h+var_228]
0x180082fb7  mov     [rsp+270h+var_230], rax
0x180082fbc  lea     r14, aBaseFsFsrmUtil_11; "base\\fs\\fsrm\\utilities\\security\\sr"...
0x180082fc3  mov     [rsp+270h+var_228], r14
0x180082fc8  lea     r15, aGetcurrentacce; "GetCurrentAccessToken"
0x180082fcf  mov     [rsp+270h+var_220], r15
0x180082fd4  lea     r12, aSecsecrc; "SECSECRC"
0x180082fdb  mov     [rsp+270h+var_218], r12
0x180082fe0  mov     [rsp+270h+var_210], 53h ; 'S'
0x180082fe8  mov     r13d, 11h
0x180082fee  mov     [rsp+270h+var_20C], r13d
0x180082ff3  mov     [rsp+270h+var_208], 0FFh
0x180082ffb  mov     [rbp+170h+var_1A0], 1000000h
0x180083002  lea     edi, [r13-10h]
0x180083006  xor     edx, edx; Val
0x180083008  lea     r8d, [r13+4Fh]; Size
0x18008300c  lea     rcx, [rsp+270h+var_200]; void *
0x180083011  call    memset_0
0x180083016  nop
0x180083017  xor     r8d, r8d
0x18008301a  lea     rdx, [rsp+270h+var_228]
0x18008301f  lea     rcx, [rbp+170h+var_100]
0x180083023  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x180083028  nop
0x180083029  test    ebx, ebx
0x18008302b  jz      loc_1800830D7
0x180083031  call    cs:__imp_CoImpersonateClient
0x180083037  mov     [rbp+170h+var_F8], eax
0x18008303a  test    eax, eax
0x18008303c  jns     short loc_180083080
0x18008303e  cmp     eax, 80010117h
0x180083043  jnz     loc_1800831B0
0x180083049  call    cs:__imp_GetCurrentProcess
0x18008304f  mov     rcx, rax; ProcessHandle
0x180083052  mov     r8, rsi; TokenHandle
0x180083055  lea     edx, [rdi+7]; DesiredAccess
0x180083058  call    cs:__imp_OpenProcessToken
0x18008305e  test    eax, eax
0x180083060  jz      loc_1800831FB
0x180083066  mov     [rbp+170h+var_F8], 0
0x18008306d  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x180083074  mov     [rbp+170h+var_100], rax
0x180083078  xor     dil, dil
0x18008307b  jmp     loc_180083100
0x180083080  call    cs:__imp_GetCurrentThread
0x180083086  mov     rcx, rax; ThreadHandle
0x180083089  mov     r9, rsi; TokenHandle
0x18008308c  mov     r8d, edi; OpenAsSelf
0x18008308f  mov     edx, 8; DesiredAccess
0x180083094  call    cs:__imp_OpenThreadToken
0x18008309a  mov     esi, eax
0x18008309c  call    cs:__imp_GetLastError
0x1800830a2  mov     ebx, eax
0x1800830a4  test    eax, eax
0x1800830a6  jle     short loc_1800830B1
0x1800830a8  movzx   ebx, ax
0x1800830ab  or      ebx, 80070000h
0x1800830b1  call    cs:__imp_CoRevertToSelf
0x1800830b7  mov     [rbp+170h+var_F8], eax
0x1800830ba  test    eax, eax
0x1800830bc  js      loc_180083278
0x1800830c2  test    esi, esi
0x1800830c4  jz      loc_180083238
0x1800830ca  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x1800830d1  mov     [rbp+170h+var_100], rax
0x1800830d5  jmp     short loc_180083100
0x1800830d7  call    cs:__imp_GetCurrentThread
0x1800830dd  mov     rcx, rax; ThreadHandle
0x1800830e0  mov     r9, rsi; TokenHandle
0x1800830e3  mov     r8d, edi; OpenAsSelf
0x1800830e6  mov     edx, 8; DesiredAccess
0x1800830eb  call    cs:__imp_OpenThreadToken
0x1800830f1  test    eax, eax
0x1800830f3  jz      short loc_18008310E
0x1800830f5  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x1800830fc  mov     [rbp+170h+var_100], rax
0x180083100  lea     rcx, [rbp+170h+var_100]; this
0x180083104  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x180083109  mov     al, dil
0x18008310c  jmp     short loc_180083150
0x18008310e  call    cs:__imp_GetLastError
0x180083114  cmp     eax, 3F0h
0x180083119  jnz     loc_1800832B5
0x18008311f  call    cs:__imp_GetCurrentProcess
0x180083125  mov     rcx, rax; ProcessHandle
0x180083128  mov     r8, rsi; TokenHandle
0x18008312b  mov     edx, 8; DesiredAccess
0x180083130  call    cs:__imp_OpenProcessToken
0x180083136  test    eax, eax
0x180083138  jz      short loc_180083173
0x18008313a  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x180083141  mov     [rbp+170h+var_100], rax
0x180083145  lea     rcx, [rbp+170h+var_100]; this
0x180083149  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x18008314e  xor     al, al
0x180083150  mov     rcx, [rbp+170h+var_50]
0x180083157  xor     rcx, rsp; StackCookie
0x18008315a  call    __security_check_cookie
0x18008315f  add     rsp, 238h
0x180083166  pop     r15
0x180083168  pop     r14
0x18008316a  pop     r13
0x18008316c  pop     r12
0x18008316e  pop     rdi
0x18008316f  pop     rsi
0x180083170  pop     rbx
0x180083171  pop     rbp
0x180083172  retn
0x180083173  lea     rax, [rbp+170h+var_198]
0x180083177  mov     [rsp+270h+var_230], rax
0x18008317c  mov     [rsp+270h+var_248], r13d
0x180083181  mov     [rsp+270h+var_250], 0A3h
0x180083189  mov     r9, r15
0x18008318c  mov     r8, r12
0x18008318f  mov     rdx, r14
0x180083192  lea     rcx, [rbp+170h+var_198]
0x180083196  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x18008319b  nop
0x18008319c  lea     r8, aOpenprocesstok; "OpenProcessToken"
0x1800831a3  mov     rdx, rax
0x1800831a6  lea     rcx, [rbp+170h+var_100]
0x1800831aa  call    ?TranslateWin32Error@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@PEBGZZ; CSrmFunctionTracer::TranslateWin32Error(CSrmDebugInfo,ushort const *,...)
0x1800831b0  lea     rcx, [rbp+170h+var_100]; this
0x1800831b4  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x1800831b9  mov     ebx, eax
0x1800831bb  lea     rax, [rbp+170h+var_198]
0x1800831bf  mov     [rsp+270h+var_230], rax
0x1800831c4  mov     [rsp+270h+var_248], r13d
0x1800831c9  mov     [rsp+270h+var_250], 60h ; '`'
0x1800831d1  mov     r9, r15
0x1800831d4  mov     r8, r12
0x1800831d7  mov     rdx, r14
0x1800831da  lea     rcx, [rbp+170h+var_198]
0x1800831de  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x1800831e3  nop
0x1800831e4  lea     r9, aCoimpersonatec; "CoImpersonateClient"
0x1800831eb  mov     r8d, ebx
0x1800831ee  mov     rdx, rax
0x1800831f1  lea     rcx, [rbp+170h+var_100]
0x1800831f5  call    ?TranslateGenericError@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::TranslateGenericError(CSrmDebugInfo,long,ushort const *,...)
0x1800831fb  lea     rax, [rbp+170h+var_198]
0x1800831ff  mov     [rsp+270h+var_230], rax
0x180083204  mov     [rsp+270h+var_248], r13d
0x180083209  mov     [rsp+270h+var_250], 68h ; 'h'
0x180083211  mov     r9, r15
0x180083214  mov     r8, r12
0x180083217  mov     rdx, r14
0x18008321a  lea     rcx, [rbp+170h+var_198]
0x18008321e  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x180083223  nop
0x180083224  lea     r8, aOpenprocesstok; "OpenProcessToken"
0x18008322b  mov     rdx, rax
0x18008322e  lea     rcx, [rbp+170h+var_100]
0x180083232  call    ?TranslateWin32Error@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@PEBGZZ; CSrmFunctionTracer::TranslateWin32Error(CSrmDebugInfo,ushort const *,...)
0x180083238  lea     rax, [rbp+170h+var_198]
0x18008323c  mov     [rsp+270h+var_230], rax
0x180083241  mov     [rsp+270h+var_248], r13d
0x180083246  mov     [rsp+270h+var_250], 7Fh
0x18008324e  mov     r9, r15
0x180083251  mov     r8, r12
0x180083254  mov     rdx, r14
0x180083257  lea     rcx, [rbp+170h+var_198]
0x18008325b  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x180083260  nop
0x180083261  lea     r9, aOpenthreadtoke; "OpenThreadToken"
0x180083268  mov     r8d, ebx
0x18008326b  mov     rdx, rax
0x18008326e  lea     rcx, [rbp+170h+var_100]
0x180083272  call    ?TranslateGenericError@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::TranslateGenericError(CSrmDebugInfo,long,ushort const *,...)
0x180083278  lea     rax, [rbp+170h+var_198]
0x18008327c  mov     [rsp+270h+var_230], rax
0x180083281  mov     [rsp+270h+var_248], r13d
0x180083286  mov     [rsp+270h+var_250], 7Ah ; 'z'
0x18008328e  mov     r9, r15
0x180083291  mov     r8, r12
0x180083294  mov     rdx, r14
0x180083297  lea     rcx, [rbp+170h+var_198]
0x18008329b  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x1800832a0  nop
0x1800832a1  lea     r8, aCoreverttoself; "CoRevertToSelf"
0x1800832a8  mov     rdx, rax
0x1800832ab  lea     rcx, [rbp+170h+var_100]
0x1800832af  call    ?TranslateWin32Error@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@PEBGZZ; CSrmFunctionTracer::TranslateWin32Error(CSrmDebugInfo,ushort const *,...)
0x1800832b5  lea     rax, [rbp+170h+var_198]
0x1800832b9  mov     [rsp+270h+var_230], rax
0x1800832be  mov     [rsp+270h+var_248], r13d
0x1800832c3  mov     [rsp+270h+var_250], 9Ch
0x1800832cb  mov     r9, r15
0x1800832ce  mov     r8, r12
0x1800832d1  mov     rdx, r14
0x1800832d4  lea     rcx, [rbp+170h+var_198]
0x1800832d8  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x1800832dd  nop
0x1800832de  lea     r8, aOpenthreadtoke; "OpenThreadToken"
0x1800832e5  mov     rdx, rax
0x1800832e8  lea     rcx, [rbp+170h+var_100]
0x1800832ec  call    ?TranslateWin32Error@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@PEBGZZ; CSrmFunctionTracer::TranslateWin32Error(CSrmDebugInfo,ushort const *,...)
```
