# CFsrmClusterUtil::IsClusterKeyPresent(HKEY__ *,ushort const *)

- ea: `0x18001f83c`
- end: `0x18001facf`
- name: `?IsClusterKeyPresent@CFsrmClusterUtil@@SA_NPEAUHKEY__@@PEBG@Z`
- size: `659`
- prototype: `bool __fastcall(HKEY hKey, LPCWSTR lpszSubKey)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task`

## callers

- `0x180020f84`

## callees

- `0x180006a1c`
- `0x1800095f4`
- `0x18001f83c`
- `0x18006fe68`
- `0x18006febc`
- `0x1800700b8`
- `0x180074048`
- `0x18007424c`
- `0x180074a04`
- `0x1800b078a`
- `0x1800b07d0`

## import_xrefs

- `CLUSAPI!ClusterRegCloseKey` at `0x18001f990`
- `CLUSAPI!ClusterRegCloseKey` at `0x18001fa0d`
- `CLUSAPI!ClusterRegCloseKey` at `0x18001f990`
- `CLUSAPI!ClusterRegCloseKey` at `0x18001fa0d`
- `CLUSAPI!ClusterRegOpenKey` at `0x18001f949`
- `CLUSAPI!ClusterRegOpenKey` at `0x18001f949`

## string_xrefs

- `0x18001f86e`: `base\fs\fsrm\service\globalstore\clusterutil.cpp`
- `0x18001fabb`: `ClusterRegCreateKey()`
- `0x18001f90b`: `- Trying to open subkey for path '%s'`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall CFsrmClusterUtil::IsClusterKeyPresent(HKEY hKey, LPCWSTR lpszSubKey)
{
  int v4; // eax
  unsigned int Hr; // eax
  __int64 v7; // rdx
  HKEY phkResult; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v9[4]; // [rsp+58h] [rbp-A8h] BYREF
  int v10; // [rsp+78h] [rbp-88h]
  _BYTE v11[96]; // [rsp+80h] [rbp-80h] BYREF
  int v12; // [rsp+E0h] [rbp-20h]
  _QWORD v13[4]; // [rsp+E8h] [rbp-18h] BYREF
  int v14; // [rsp+108h] [rbp+8h]
  _BYTE v15[96]; // [rsp+110h] [rbp+10h] BYREF
  int v16; // [rsp+170h] [rbp+70h]
  _QWORD v17[22]; // [rsp+180h] [rbp+80h] BYREF

  v13[0] = L"base\\fs\\fsrm\\service\\globalstore\\clusterutil.cpp";
  v13[1] = L"CFsrmClusterUtil::IsClusterKeyPresent";
  v13[2] = L"CLUSUTLC";
  v13[3] = 324;
  v14 = 255;
  v16 = 0x1000000;
  memset_0(v15, 0, sizeof(v15));
  CSrmFunctionTracer::CSrmFunctionTracer(
    (__int64)v17,
    (const struct CSrmDebugInfo *)v13,
    (__int64)L"CFsrmClusterUtil::IsClusterKeyPresent");
  v9[0] = L"base\\fs\\fsrm\\service\\globalstore\\clusterutil.cpp";
  v9[1] = L"CFsrmClusterUtil::IsClusterKeyPresent";
  v9[2] = L"CLUSUTLC";
  v9[3] = 326;
  v10 = 255;
  v12 = 0x1000000;
  memset_0(v11, 0, sizeof(v11));
  CSrmFunctionTracer::Trace(v17, v9, L"- Trying to open subkey for path '%s'", lpszSubKey);
  phkResult = 0;
  v4 = ClusterRegOpenKey(hKey, lpszSubKey, 0xF003Fu, &phkResult);
  if ( v4 == 2 )
  {
    CSrmFunctionTracerBase::TraceInternalWithFormat(
      (CSrmFunctionTracerBase *)v17,
      L"RETURN",
      0xAAu,
      L"Returning BOOL: %s",
      L"FALSE");
    if ( phkResult )
      ClusterRegCloseKey(phkResult);
    phkResult = 0;
    v17[0] = &CSrmFunctionTracer::`vftable';
    CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)v17);
    return 0;
  }
  else
  {
    if ( v4 )
    {
      if ( v4 > 0 )
        v4 = (unsigned __int16)v4 | 0x80070000;
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)v17, v4);
      CSrmDebugInfo::CSrmDebugInfo(
        (__int64)v9,
        (__int64)L"base\\fs\\fsrm\\service\\globalstore\\clusterutil.cpp",
        (__int64)L"CLUSUTLC",
        (__int64)L"CFsrmClusterUtil::IsClusterKeyPresent",
        342,
        0);
      Hr = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)v17);
      CSrmFunctionTracer::TranslateGenericError(v17, v7, Hr, L"ClusterRegCreateKey()");
    }
    CSrmFunctionTracerBase::TraceInternalWithFormat(
      (CSrmFunctionTracerBase *)v17,
      L"RETURN",
      0xAAu,
      L"Returning BOOL: %s",
      L"TRUE");
    if ( phkResult )
      ClusterRegCloseKey(phkResult);
    phkResult = 0;
    v17[0] = &CSrmFunctionTracer::`vftable';
    CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)v17);
    return 1;
  }
}

```

## disassembly

```asm
0x18001f83c  mov     [rsp-8+arg_10], rbx
0x18001f841  push    rbp
0x18001f842  push    rsi
0x18001f843  push    rdi
0x18001f844  push    r12
0x18001f846  push    r13
0x18001f848  lea     rbp, [rsp-140h]
0x18001f850  sub     rsp, 240h
0x18001f857  mov     rax, cs:__security_cookie
0x18001f85e  xor     rax, rsp
0x18001f861  mov     [rbp+160h+var_30], rax
0x18001f868  mov     rdi, rdx
0x18001f86b  mov     rbx, rcx
0x18001f86e  lea     r13, aBaseFsFsrmServ_40; "base\\fs\\fsrm\\service\\globalstore\\c"...
0x18001f875  mov     [rbp+160h+var_178], r13
0x18001f879  lea     r12, aCfsrmclusterut_12; "CFsrmClusterUtil::IsClusterKeyPresent"
0x18001f880  mov     [rbp+160h+var_170], r12
0x18001f884  lea     rax, aClusutlc; "CLUSUTLC"
0x18001f88b  mov     [rbp+160h+var_168], rax
0x18001f88f  mov     [rbp+160h+var_160], 144h
0x18001f897  mov     [rbp+160h+var_158], 0FFh
0x18001f89e  mov     [rbp+160h+var_F0], 1000000h
0x18001f8a5  mov     esi, 60h ; '`'
0x18001f8aa  mov     r8d, esi; Size
0x18001f8ad  xor     edx, edx; Val
0x18001f8af  lea     rcx, [rbp+160h+var_150]; void *
0x18001f8b3  call    memset_0
0x18001f8b8  mov     r8, r12
0x18001f8bb  lea     rdx, [rbp+160h+var_178]
0x18001f8bf  lea     rcx, [rbp+160h+var_E0]
0x18001f8c6  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x18001f8cb  nop
0x18001f8cc  mov     [rsp+260h+var_208], r13
0x18001f8d1  mov     [rsp+260h+var_200], r12
0x18001f8d6  lea     rax, aClusutlc; "CLUSUTLC"
0x18001f8dd  mov     [rsp+260h+var_1F8], rax
0x18001f8e2  mov     [rsp+260h+var_1F0], 146h
0x18001f8eb  mov     [rsp+260h+var_1E8], 0FFh
0x18001f8f3  mov     [rbp+160h+var_180], 1000000h
0x18001f8fa  mov     r8d, esi; Size
0x18001f8fd  xor     edx, edx; Val
0x18001f8ff  lea     rcx, [rbp+160h+var_1E0]; void *
0x18001f903  call    memset_0
0x18001f908  mov     r9, rdi
0x18001f90b  lea     r8, aTryingToOpenSu; "- Trying to open subkey for path '%s'"
0x18001f912  lea     rdx, [rsp+260h+var_208]
0x18001f917  lea     rcx, [rbp+160h+var_E0]
0x18001f91e  call    ?Trace@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@PEBGZZ; CSrmFunctionTracer::Trace(CSrmDebugInfo,ushort const *,...)
0x18001f923  lea     rsi, ??_7?$CSrmAuto@PEAUHKEY__@@V?$CSrmAutoGenericValue_Storage@PEAUHKEY__@@$0A@P6AJPEAU1@@Z$1?ClusterRegCloseKey@@YAJ0@ZP6AAEAPEAU1@AEAPEAU1@@Z$1?Identity@?$DTyper@PEAUHKEY__@@@@SAAEAPEAU1@1@Z@@@@6B@; const CSrmAuto<HKEY__ *,CSrmAutoGenericValue_Storage<HKEY__ *,0,long (*)(HKEY__ *),&ClusterRegCloseKey(HKEY__ *),HKEY__ * & (*)(HKEY__ * &),&DTyper<HKEY__ *>::Identity(HKEY__ * &)>>::`vftable'
0x18001f92a  mov     [rsp+260h+var_220], rsi
0x18001f92f  mov     [rsp+260h+phkResult], 0
0x18001f938  lea     r9, [rsp+260h+phkResult]; phkResult
0x18001f93d  mov     r8d, 0F003Fh; samDesired
0x18001f943  mov     rdx, rdi; lpszSubKey
0x18001f946  mov     rcx, rbx; hKey
0x18001f949  call    cs:__imp_ClusterRegOpenKey
0x18001f94f  cmp     eax, 2
0x18001f952  jnz     short loc_18001F9C9
0x18001f954  lea     rax, aFalse; "FALSE"
0x18001f95b  mov     [rsp+260h+var_240], rax
0x18001f960  lea     r9, aReturningBoolS; "Returning BOOL: %s"
0x18001f967  mov     r8d, 0AAh; unsigned int
0x18001f96d  lea     rdx, aReturn; "RETURN"
0x18001f974  lea     rcx, [rbp+160h+var_E0]; this
0x18001f97b  call    ?TraceInternalWithFormat@CSrmFunctionTracerBase@@QEAAXPEBGK0ZZ; CSrmFunctionTracerBase::TraceInternalWithFormat(ushort const *,ulong,ushort const *,...)
0x18001f980  nop
0x18001f981  mov     [rsp+260h+var_220], rsi
0x18001f986  mov     rcx, [rsp+260h+phkResult]; hKey
0x18001f98b  test    rcx, rcx
0x18001f98e  jz      short loc_18001F996
0x18001f990  call    cs:__imp_ClusterRegCloseKey
0x18001f996  lea     rax, ??_7?$CSrmAutoGenericValue_Storage@PEAUHKEY__@@$0A@P6AJPEAU1@@Z$1?ClusterRegCloseKey@@YAJ0@ZP6AAEAPEAU1@AEAPEAU1@@Z$1?Identity@?$DTyper@PEAUHKEY__@@@@SAAEAPEAU1@1@Z@@6B@; const CSrmAutoGenericValue_Storage<HKEY__ *,0,long (*)(HKEY__ *),&ClusterRegCloseKey(HKEY__ *),HKEY__ * & (*)(HKEY__ * &),&DTyper<HKEY__ *>::Identity(HKEY__ * &)>::`vftable'
0x18001f99d  mov     [rsp+260h+var_220], rax
0x18001f9a2  mov     [rsp+260h+phkResult], 0
0x18001f9ab  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x18001f9b2  mov     [rbp+160h+var_E0], rax
0x18001f9b9  lea     rcx, [rbp+160h+var_E0]; this
0x18001f9c0  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x18001f9c5  xor     al, al
0x18001f9c7  jmp     short loc_18001FA44
0x18001f9c9  test    eax, eax
0x18001f9cb  jnz     loc_18001FA6A
0x18001f9d1  lea     rax, aTrue_0; "TRUE"
0x18001f9d8  mov     [rsp+260h+var_240], rax
0x18001f9dd  lea     r9, aReturningBoolS; "Returning BOOL: %s"
0x18001f9e4  mov     r8d, 0AAh; unsigned int
0x18001f9ea  lea     rdx, aReturn; "RETURN"
0x18001f9f1  lea     rcx, [rbp+160h+var_E0]; this
0x18001f9f8  call    ?TraceInternalWithFormat@CSrmFunctionTracerBase@@QEAAXPEBGK0ZZ; CSrmFunctionTracerBase::TraceInternalWithFormat(ushort const *,ulong,ushort const *,...)
0x18001f9fd  nop
0x18001f9fe  mov     [rsp+260h+var_220], rsi
0x18001fa03  mov     rcx, [rsp+260h+phkResult]; hKey
0x18001fa08  test    rcx, rcx
0x18001fa0b  jz      short loc_18001FA13
0x18001fa0d  call    cs:__imp_ClusterRegCloseKey
0x18001fa13  lea     rax, ??_7?$CSrmAutoGenericValue_Storage@PEAUHKEY__@@$0A@P6AJPEAU1@@Z$1?ClusterRegCloseKey@@YAJ0@ZP6AAEAPEAU1@AEAPEAU1@@Z$1?Identity@?$DTyper@PEAUHKEY__@@@@SAAEAPEAU1@1@Z@@6B@; const CSrmAutoGenericValue_Storage<HKEY__ *,0,long (*)(HKEY__ *),&ClusterRegCloseKey(HKEY__ *),HKEY__ * & (*)(HKEY__ * &),&DTyper<HKEY__ *>::Identity(HKEY__ * &)>::`vftable'
0x18001fa1a  mov     [rsp+260h+var_220], rax
0x18001fa1f  mov     [rsp+260h+phkResult], 0
0x18001fa28  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x18001fa2f  mov     [rbp+160h+var_E0], rax
0x18001fa36  lea     rcx, [rbp+160h+var_E0]; this
0x18001fa3d  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x18001fa42  mov     al, 1
0x18001fa44  mov     rcx, [rbp+160h+var_30]
0x18001fa4b  xor     rcx, rsp; StackCookie
0x18001fa4e  call    __security_check_cookie
0x18001fa53  mov     rbx, [rsp+260h+arg_10]
0x18001fa5b  add     rsp, 240h
0x18001fa62  pop     r13
0x18001fa64  pop     r12
0x18001fa66  pop     rdi
0x18001fa67  pop     rsi
0x18001fa68  pop     rbp
0x18001fa69  retn
0x18001fa6a  jle     short loc_18001FA74
0x18001fa6c  movzx   eax, ax
0x18001fa6f  or      eax, 80070000h
0x18001fa74  mov     edx, eax; int
0x18001fa76  lea     rcx, [rbp+160h+var_E0]; this
0x18001fa7d  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x18001fa82  mov     [rsp+260h+var_238], 0
0x18001fa8a  mov     dword ptr [rsp+260h+var_240], 156h
0x18001fa92  mov     r9, r12
0x18001fa95  lea     r8, aClusutlc; "CLUSUTLC"
0x18001fa9c  mov     rdx, r13
0x18001fa9f  lea     rcx, [rsp+260h+var_208]
0x18001faa4  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x18001faa9  mov     rdx, rax
0x18001faac  lea     rcx, [rbp+160h+var_E0]; this
0x18001fab3  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18001fab8  mov     r8d, eax
0x18001fabb  lea     r9, aClusterregcrea; "ClusterRegCreateKey()"
0x18001fac2  lea     rcx, [rbp+160h+var_E0]
0x18001fac9  call    ?TranslateGenericError@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::TranslateGenericError(CSrmDebugInfo,long,ushort const *,...)
```
