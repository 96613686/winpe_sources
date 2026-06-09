# CEventNotifier::FindEventByGUID(ushort *,_GUID const *,HKEY__ * *)

- ea: `0x180024cb0`
- end: `0x1800250b4`
- name: `?FindEventByGUID@CEventNotifier@@AEAAJPEAGPEBU_GUID@@PEAPEAUHKEY__@@@Z`
- size: `1028`
- prototype: `__int64 __fastcall(CEventNotifier *__hidden this, unsigned __int16 *, const struct _GUID *, HKEY *)`
- caller_count: `2`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800245f0`
- `0x180030294`

## callees

- `0x180004380`
- `0x18000b6a0`
- `0x18000c7c0`
- `0x18000cba0`
- `0x18000d770`
- `0x18000d7b0`
- `0x18000dd00`
- `0x18000f4fc`
- `0x180011a94`
- `0x180024cb0`
- `0x180027590`
- `0x18002c868`
- `0x18002c8b0`
- `0x18002e5d4`
- `0x18002e9d8`
- `0x18002eab4`
- `0x180033cc0`
- `0x180034658`
- `0x180078010`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180024f61`
- `ADVAPI32!RegCloseKey` at `0x180024fef`
- `ADVAPI32!RegCloseKey` at `0x180025059`
- `ADVAPI32!RegCloseKey` at `0x180024f61`
- `ADVAPI32!RegCloseKey` at `0x180024fef`
- `ADVAPI32!RegCloseKey` at `0x180025059`
- `ADVAPI32!RegEnumKeyExW` at `0x180024e96`
- `ADVAPI32!RegEnumKeyExW` at `0x180024e96`
- `ADVAPI32!RegOpenKeyExW` at `0x180024ecb`
- `ADVAPI32!RegOpenKeyExW` at `0x180024ecb`
- `ADVAPI32!RegQueryValueExW` at `0x180024f0b`
- `ADVAPI32!RegQueryValueExW` at `0x180024f0b`
- `ole32!CLSIDFromString` at `0x180024f2f`
- `ole32!CLSIDFromString` at `0x180024f2f`

## string_xrefs

- `0x180024f71`: `Couldn't open Events subkey, on device %ws`
- `0x180024f96`: `Couldn't open Events subkey, on device %ws`

## pseudocode

```c
__int64 __fastcall CEventNotifier::FindEventByGUID(
        CEventNotifier *this,
        unsigned __int16 *a2,
        const struct _GUID *a3,
        HKEY *a4)
{
  struct tagWiaTraceData_Type *v7; // rax
  char *v8; // rdx
  unsigned int v9; // r8d
  char *v10; // rbx
  void *v11; // rdx
  void *v12; // rax
  int v13; // edx
  int v14; // ecx
  int GlobalEventsKey; // ebx
  __int64 v16; // rcx
  __int64 USDWrapperFromDeviceList; // rbx
  char *v18; // rbx
  void *v19; // rdx
  void *v20; // rax
  int v21; // edx
  int v22; // ecx
  DWORD i; // edi
  __int64 v24; // rax
  char *v25; // rbx
  void *v26; // rdx
  void *v27; // rax
  int v28; // edx
  int v29; // ecx
  char *v31; // rbx
  void *v32; // rdx
  void *v33; // rax
  int v34; // edx
  int v35; // ecx
  unsigned int lpReserved; // [rsp+20h] [rbp-E0h]
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  HKEY phkResult; // [rsp+50h] [rbp-B0h] BYREF
  DWORD cbData; // [rsp+58h] [rbp-A8h] BYREF
  DWORD Type; // [rsp+5Ch] [rbp-A4h] BYREF
  _BYTE v42[80]; // [rsp+60h] [rbp-A0h] BYREF
  GUID pclsid; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD v44[38]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR Name[96]; // [rsp+1F0h] [rbp+F0h] BYREF

  v7 = WiaTrace_Trace(&Class);
  CWiaTraceFn::CWiaTraceFn((CWiaTraceFn *)v42, v8, v9, "CEventNotifier::FindEventByGUID", lpReserved, v7);
  memset_0(Name, 0, sizeof(Name));
  hKey = 0;
  phkResult = 0;
  cchName = 0;
  cbData = 0;
  Type = 0;
  pclsid = 0;
  if ( !a3 )
  {
    v10 = (char *)WiaTrace_TraceLogWithSubComp(0, "Event pointer is NULL");
    WriteDbgTraceWarningWI("CEventNotifier::FindEventByGUID", v10);
    WiaTrcLib::Free((WiaTrcLib *)v10, v11);
    v12 = (void *)WiaTrace_TraceWithSubComp(0, "Event pointer is NULL");
    WiaTrace_ProcessTrace_Ex(v14, v13, (int)"CEventNotifier::FindEventByGUID", 2, v12);
    GlobalEventsKey = -2147024809;
LABEL_21:
    CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v42);
    return (unsigned int)GlobalEventsKey;
  }
  *a4 = 0;
  if ( a2 )
  {
    CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>(v44, a2);
    USDWrapperFromDeviceList = GetUSDWrapperFromDeviceList(v16, v44);
    v44[0] = &CSimpleStringBase<unsigned short>::`vftable';
    CSimpleStringBase<unsigned short>::DeleteStorage(v44);
    v44[34] = 0;
    if ( USDWrapperFromDeviceList )
    {
      hKey = (HKEY)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)USDWrapperFromDeviceList + 504LL))(USDWrapperFromDeviceList);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)USDWrapperFromDeviceList + 16LL))(USDWrapperFromDeviceList);
    }
    if ( (unsigned __int64)hKey - 1 > 0xFFFFFFFFFFFFFFFDuLL )
    {
      v25 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(0, 0, "Couldn't open Events subkey, on device %ws", a2);
      WriteDbgTraceInfoWI("CEventNotifier::FindEventByGUID", v25);
      WiaTrcLib::Free((WiaTrcLib *)v25, v26);
      v27 = (void *)WiaTrace_TraceWithSubCompTraceLevel(0, 0, "Couldn't open Events subkey, on device %ws", a2);
      WiaTrace_ProcessTrace_Ex(v29, v28, (int)"CEventNotifier::FindEventByGUID", 4, v27);
      GlobalEventsKey = -2147467259;
      goto LABEL_21;
    }
    v18 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(0, 0, "Found Events key on device %ws", a2);
    WriteDbgTraceInfoWI("CEventNotifier::FindEventByGUID", v18);
    WiaTrcLib::Free((WiaTrcLib *)v18, v19);
    v20 = (void *)WiaTrace_TraceWithSubCompTraceLevel(0, 0, "Found Events key on device %ws", a2);
    WiaTrace_ProcessTrace_Ex(v22, v21, (int)"CEventNotifier::FindEventByGUID", 4, v20);
  }
  else
  {
    GlobalEventsKey = CEventNotifier::GetGlobalEventsKey(&hKey);
    if ( GlobalEventsKey < 0 )
      goto LABEL_21;
  }
  for ( i = 0; ; ++i )
  {
    cchName = 95;
    if ( RegEnumKeyExW(hKey, i, Name, &cchName, 0, 0, 0, 0) )
      break;
    cchName = 192;
    if ( !RegOpenKeyExW(hKey, Name, 0, 0x2001Fu, &phkResult) )
    {
      cbData = 192;
      if ( RegQueryValueExW(phkResult, L"GUID", 0, &Type, (LPBYTE)Name, &cbData) || Type != 1 )
      {
        if ( phkResult )
        {
          RegCloseKey(phkResult);
          phkResult = 0;
        }
        v31 = (char *)WiaTrace_TraceLogWithSubComp(0, "Junk event %S found", Name);
        WriteDbgTraceWarningWI("CEventNotifier::FindEventByGUID", v31);
        WiaTrcLib::Free((WiaTrcLib *)v31, v32);
        v33 = (void *)WiaTrace_TraceWithSubComp(0, "Junk event %S found", Name);
        WiaTrace_ProcessTrace_Ex(v35, v34, (int)"CEventNotifier::FindEventByGUID", 2, v33);
      }
      else
      {
        if ( CLSIDFromString(Name, &pclsid) >= 0 )
        {
          v24 = *(_QWORD *)&pclsid.Data1 - *(_QWORD *)&a3->Data1;
          if ( *(_QWORD *)&pclsid.Data1 == *(_QWORD *)&a3->Data1 )
            v24 = *(_QWORD *)pclsid.Data4 - *(_QWORD *)a3->Data4;
          if ( !v24 )
          {
            RegCloseKey(hKey);
            *a4 = phkResult;
            hKey = 0;
            CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v42);
            return 0;
          }
        }
        if ( phkResult )
        {
          RegCloseKey(phkResult);
          phkResult = 0;
        }
      }
    }
  }
  CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v42);
  return 2147500037LL;
}

```

## disassembly

```asm
0x180024cb0  mov     [rsp-8+arg_0], rbx
0x180024cb5  mov     [rsp-8+arg_10], rsi
0x180024cba  push    rbp
0x180024cbb  push    rdi
0x180024cbc  push    r12
0x180024cbe  push    r14
0x180024cc0  push    r15
0x180024cc2  lea     rbp, [rsp-1C0h]
0x180024cca  sub     rsp, 2C0h
0x180024cd1  mov     rax, cs:__security_cookie
0x180024cd8  xor     rax, rsp
0x180024cdb  mov     [rbp+1E0h+var_30], rax
0x180024ce2  lea     rcx, Class; unsigned __int16 *
0x180024ce9  mov     rsi, r9
0x180024cec  mov     r14, r8
0x180024cef  mov     rdi, rdx
0x180024cf2  call    ?WiaTrace_Trace@@YAPEAUtagWiaTraceData_Type@@PEBGZZ; WiaTrace_Trace(ushort const *,...)
0x180024cf7  lea     r12, aCeventnotifier_18; "CEventNotifier::FindEventByGUID"
0x180024cfe  mov     [rsp+2E0h+lpClass], rax; struct tagWiaTraceData_Type *
0x180024d03  mov     r9, r12; char *
0x180024d06  lea     rcx, [rsp+2E0h+var_280]; this
0x180024d0b  call    ??0CWiaTraceFn@@QEAA@PEADK0KPEAUtagWiaTraceData_Type@@@Z; CWiaTraceFn::CWiaTraceFn(char *,ulong,char *,ulong,tagWiaTraceData_Type *)
0x180024d10  xor     edx, edx; Val
0x180024d12  lea     rcx, [rbp+1E0h+Name]; void *
0x180024d19  mov     r8d, 0C0h; Size
0x180024d1f  call    memset_0
0x180024d24  xor     r15d, r15d
0x180024d27  xorps   xmm0, xmm0
0x180024d2a  mov     [rsp+2E0h+hKey], r15
0x180024d2f  mov     [rsp+2E0h+phkResult], r15
0x180024d34  mov     [rsp+2E0h+cchName], r15d
0x180024d39  mov     [rsp+2E0h+cbData], r15d
0x180024d3e  mov     [rsp+2E0h+Type], r15d
0x180024d43  movups  xmmword ptr [rbp+1E0h+pclsid.Data1], xmm0
0x180024d47  test    r14, r14
0x180024d4a  jnz     short loc_180024D99
0x180024d4c  lea     rdx, aEventPointerIs; "Event pointer is NULL"
0x180024d53  xor     ecx, ecx
0x180024d55  call    WiaTrace_TraceLogWithSubComp
0x180024d5a  mov     rdx, rax; char *
0x180024d5d  mov     rcx, r12; char *
0x180024d60  mov     rbx, rax
0x180024d63  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x180024d68  mov     rcx, rbx; this
0x180024d6b  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180024d70  lea     rdx, aEventPointerIs; "Event pointer is NULL"
0x180024d77  xor     ecx, ecx
0x180024d79  call    WiaTrace_TraceWithSubComp
0x180024d7e  lea     r9d, [r15+2]; int
0x180024d82  mov     [rsp+2E0h+lpReserved], rax; lpMem
0x180024d87  mov     r8, r12; int
0x180024d8a  call    WiaTrace_ProcessTrace_Ex
0x180024d8f  mov     ebx, 80070057h
0x180024d94  jmp     loc_180024FD4
0x180024d99  mov     [rsi], r15
0x180024d9c  test    rdi, rdi
0x180024d9f  jz      loc_180024FC0
0x180024da5  mov     rdx, rdi
0x180024da8  lea     rcx, [rbp+1E0h+var_220]
0x180024dac  call    ??0?$CSimpleStringBase@G@@QEAA@PEBG@Z; CSimpleStringBase<ushort>::CSimpleStringBase<ushort>(ushort const *)
0x180024db1  lea     rdx, [rbp+1E0h+var_220]
0x180024db5  call    ?GetUSDWrapperFromDeviceList@@YAPEAVUSDWrapper@@JAEBV?$CSimpleStringBase@G@@@Z; GetUSDWrapperFromDeviceList(long,CSimpleStringBase<ushort> const &)
0x180024dba  mov     rbx, rax
0x180024dbd  lea     rcx, [rbp+1E0h+var_220]
0x180024dc1  lea     rax, ??_7?$CSimpleStringBase@G@@6B@; const CSimpleStringBase<ushort>::`vftable'
0x180024dc8  mov     [rbp+1E0h+var_220], rax
0x180024dcc  call    ?DeleteStorage@?$CSimpleStringBase@G@@AEAAXXZ; CSimpleStringBase<ushort>::DeleteStorage(void)
0x180024dd1  mov     [rbp+1E0h+var_110], r15
0x180024dd8  test    rbx, rbx
0x180024ddb  jz      short loc_180024E03
0x180024ddd  mov     rcx, [rbx]
0x180024de0  mov     rax, [rcx+1F8h]
0x180024de7  mov     rcx, rbx
0x180024dea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024def  mov     [rsp+2E0h+hKey], rax
0x180024df4  mov     rcx, rbx
0x180024df7  mov     rax, [rbx]
0x180024dfa  mov     rax, [rax+10h]
0x180024dfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024e03  mov     rax, [rsp+2E0h+hKey]
0x180024e08  xor     edx, edx
0x180024e0a  dec     rax
0x180024e0d  xor     ecx, ecx
0x180024e0f  mov     r9, rdi
0x180024e12  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180024e16  ja      loc_180024F71
0x180024e1c  lea     r8, aFoundEventsKey; "Found Events key on device %ws"
0x180024e23  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x180024e28  mov     rdx, rax; char *
0x180024e2b  mov     rcx, r12; char *
0x180024e2e  mov     rbx, rax
0x180024e31  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x180024e36  mov     rcx, rbx; this
0x180024e39  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180024e3e  mov     r9, rdi
0x180024e41  lea     r8, aFoundEventsKey; "Found Events key on device %ws"
0x180024e48  xor     edx, edx
0x180024e4a  xor     ecx, ecx
0x180024e4c  call    WiaTrace_TraceWithSubCompTraceLevel
0x180024e51  mov     r9d, 4; int
0x180024e57  mov     [rsp+2E0h+lpReserved], rax; lpMem
0x180024e5c  mov     r8, r12; int
0x180024e5f  call    WiaTrace_ProcessTrace_Ex
0x180024e64  mov     edi, r15d
0x180024e67  mov     rcx, [rsp+2E0h+hKey]; hKey
0x180024e6c  lea     r9, [rsp+2E0h+cchName]; lpcchName
0x180024e71  mov     [rsp+2E0h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180024e76  lea     r8, [rbp+1E0h+Name]; lpName
0x180024e7d  mov     [rsp+2E0h+lpcchClass], r15; lpcchClass
0x180024e82  mov     edx, edi; dwIndex
0x180024e84  mov     [rsp+2E0h+lpClass], r15; lpClass
0x180024e89  mov     [rsp+2E0h+lpReserved], r15; lpReserved
0x180024e8e  mov     [rsp+2E0h+cchName], 5Fh ; '_'
0x180024e96  call    cs:__imp_RegEnumKeyExW
0x180024e9c  test    eax, eax
0x180024e9e  jnz     loc_18002507A
0x180024ea4  mov     rcx, [rsp+2E0h+hKey]; hKey
0x180024ea9  lea     rax, [rsp+2E0h+phkResult]
0x180024eae  mov     r9d, 2001Fh; samDesired
0x180024eb4  mov     [rsp+2E0h+lpReserved], rax; phkResult
0x180024eb9  xor     r8d, r8d; ulOptions
0x180024ebc  mov     [rsp+2E0h+cchName], 0C0h
0x180024ec4  lea     rdx, [rbp+1E0h+Name]; lpSubKey
0x180024ecb  call    cs:__imp_RegOpenKeyExW
0x180024ed1  test    eax, eax
0x180024ed3  jnz     loc_18002504D
0x180024ed9  mov     rcx, [rsp+2E0h+phkResult]; hKey
0x180024ede  lea     rax, [rsp+2E0h+cbData]
0x180024ee3  mov     [rsp+2E0h+lpClass], rax; lpcbData
0x180024ee8  lea     r9, [rsp+2E0h+Type]; lpType
0x180024eed  lea     rax, [rbp+1E0h+Name]
0x180024ef4  mov     [rsp+2E0h+cbData], 0C0h
0x180024efc  xor     r8d, r8d; lpReserved
0x180024eff  mov     [rsp+2E0h+lpReserved], rax; lpData
0x180024f04  lea     rdx, aGuid; "GUID"
0x180024f0b  call    cs:__imp_RegQueryValueExW
0x180024f11  test    eax, eax
0x180024f13  jnz     loc_180024FE5
0x180024f19  cmp     [rsp+2E0h+Type], 1
0x180024f1e  jnz     loc_180024FE5
0x180024f24  lea     rdx, [rbp+1E0h+pclsid]; pclsid
0x180024f28  lea     rcx, [rbp+1E0h+Name]; lpsz
0x180024f2f  call    cs:__imp_CLSIDFromString
0x180024f35  test    eax, eax
0x180024f37  js      short loc_180024F53
0x180024f39  mov     rax, qword ptr [rbp+1E0h+pclsid.Data1]
0x180024f3d  sub     rax, [r14]
0x180024f40  jnz     short loc_180024F4A
0x180024f42  mov     rax, qword ptr [rbp+1E0h+pclsid.Data4]
0x180024f46  sub     rax, [r14+8]
0x180024f4a  test    rax, rax
0x180024f4d  jz      loc_180025054
0x180024f53  mov     rcx, [rsp+2E0h+phkResult]; hKey
0x180024f58  test    rcx, rcx
0x180024f5b  jz      loc_18002504D
0x180024f61  call    cs:__imp_RegCloseKey
0x180024f67  mov     [rsp+2E0h+phkResult], r15
0x180024f6c  jmp     loc_18002504D
0x180024f71  lea     r8, aCouldnTOpenEve; "Couldn't open Events subkey, on device "...
0x180024f78  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x180024f7d  mov     rdx, rax; char *
0x180024f80  mov     rcx, r12; char *
0x180024f83  mov     rbx, rax
0x180024f86  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x180024f8b  mov     rcx, rbx; this
0x180024f8e  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180024f93  mov     r9, rdi
0x180024f96  lea     r8, aCouldnTOpenEve; "Couldn't open Events subkey, on device "...
0x180024f9d  xor     edx, edx
0x180024f9f  xor     ecx, ecx
0x180024fa1  call    WiaTrace_TraceWithSubCompTraceLevel
0x180024fa6  mov     r9d, 4; int
0x180024fac  mov     [rsp+2E0h+lpReserved], rax; lpMem
0x180024fb1  mov     r8, r12; int
0x180024fb4  call    WiaTrace_ProcessTrace_Ex
0x180024fb9  mov     ebx, 80004005h
0x180024fbe  jmp     short loc_180024FD4
0x180024fc0  lea     rcx, [rsp+2E0h+hKey]; phkResult
0x180024fc5  call    ?GetGlobalEventsKey@CEventNotifier@@SAJPEAPEAUHKEY__@@@Z; CEventNotifier::GetGlobalEventsKey(HKEY__ * *)
0x180024fca  mov     ebx, eax
0x180024fcc  test    eax, eax
0x180024fce  jns     loc_180024E64
0x180024fd4  lea     rcx, [rsp+2E0h+var_280]; this
0x180024fd9  call    ??1CWiaTraceFn@@QEAA@XZ; CWiaTraceFn::~CWiaTraceFn(void)
0x180024fde  mov     eax, ebx
0x180024fe0  jmp     loc_180025089
0x180024fe5  mov     rcx, [rsp+2E0h+phkResult]; hKey
0x180024fea  test    rcx, rcx
0x180024fed  jz      short loc_180024FFA
0x180024fef  call    cs:__imp_RegCloseKey
0x180024ff5  mov     [rsp+2E0h+phkResult], r15
0x180024ffa  lea     r8, [rbp+1E0h+Name]
0x180025001  xor     ecx, ecx
0x180025003  lea     rdx, aJunkEventSFoun; "Junk event %S found"
0x18002500a  call    WiaTrace_TraceLogWithSubComp
0x18002500f  mov     rdx, rax; char *
0x180025012  mov     rcx, r12; char *
0x180025015  mov     rbx, rax
0x180025018  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x18002501d  mov     rcx, rbx; this
0x180025020  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180025025  lea     r8, [rbp+1E0h+Name]
0x18002502c  xor     ecx, ecx
0x18002502e  lea     rdx, aJunkEventSFoun; "Junk event %S found"
0x180025035  call    WiaTrace_TraceWithSubComp
0x18002503a  mov     r9d, 2; int
0x180025040  mov     [rsp+2E0h+lpReserved], rax; lpMem
0x180025045  mov     r8, r12; int
0x180025048  call    WiaTrace_ProcessTrace_Ex
0x18002504d  inc     edi
0x18002504f  jmp     loc_180024E67
0x180025054  mov     rcx, [rsp+2E0h+hKey]; hKey
0x180025059  call    cs:__imp_RegCloseKey
0x18002505f  mov     rax, [rsp+2E0h+phkResult]
0x180025064  lea     rcx, [rsp+2E0h+var_280]; this
0x180025069  mov     [rsi], rax
0x18002506c  mov     [rsp+2E0h+hKey], r15
0x180025071  call    ??1CWiaTraceFn@@QEAA@XZ; CWiaTraceFn::~CWiaTraceFn(void)
0x180025076  xor     eax, eax
0x180025078  jmp     short loc_180025089
0x18002507a  lea     rcx, [rsp+2E0h+var_280]; this
0x18002507f  call    ??1CWiaTraceFn@@QEAA@XZ; CWiaTraceFn::~CWiaTraceFn(void)
0x180025084  mov     eax, 80004005h
0x180025089  mov     rcx, [rbp+1E0h+var_30]
0x180025090  xor     rcx, rsp; StackCookie
0x180025093  call    __security_check_cookie
0x180025098  lea     r11, [rsp+2E0h+var_20]
0x1800250a0  mov     rbx, [r11+30h]
0x1800250a4  mov     rsi, [r11+40h]
0x1800250a8  mov     rsp, r11
0x1800250ab  pop     r15
0x1800250ad  pop     r14
0x1800250af  pop     r12
0x1800250b1  pop     rdi
0x1800250b2  pop     rbp
0x1800250b3  retn
```
