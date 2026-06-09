# CFsrmClusterUtil::GetClusterKeyForPath(HKEY__ *,ushort const *)

- ea: `0x18001e69c`
- end: `0x18001e99a`
- name: `?GetClusterKeyForPath@CFsrmClusterUtil@@SAPEAUHKEY__@@PEAU2@PEBG@Z`
- size: `766`
- prototype: `HKEY __fastcall(HKEY hKey, LPCWSTR lpszSubKey)`
- caller_count: `6`
- callee_count: `12`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x18001eb94`
- `0x1800209ac`
- `0x180020b08`
- `0x180020d48`
- `0x180020f84`
- `0x180021148`

## callees

- `0x180006a1c`
- `0x1800095f4`
- `0x180010bc4`
- `0x18001e69c`
- `0x1800202b8`
- `0x18006fe68`
- `0x18006febc`
- `0x1800700b8`
- `0x180074048`
- `0x180074a04`
- `0x1800b078a`
- `0x1800b07d0`

## import_xrefs

- `CLUSAPI!ClusterRegCreateKey` at `0x18001e7be`
- `CLUSAPI!ClusterRegCreateKey` at `0x18001e7be`

## string_xrefs

- `0x18001e6d2`: `base\fs\fsrm\service\globalstore\clusterutil.cpp`
- `0x18001e6dd`: `CFsrmClusterUtil::GetClusterKeyForPath`
- `0x18001e769`: `- Creating/Opening subkey for path '%s'`
- `0x18001e986`: `ClusterRegCreateKey()`
- `0x18001e869`: `- The key is now created.`
- `0x18001e896`: `CreateSubkey`
- `0x18001e8c2`: `Create`
- `0x18001e83c`: `- The existing SRM key is was opened.`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
HKEY __fastcall CFsrmClusterUtil::GetClusterKeyForPath(HKEY hKey, LPCWSTR lpszSubKey)
{
  int v4; // eax
  HKEY v5; // rbx
  unsigned int Hr; // eax
  __int64 v8; // rdx
  DWORD dwDisposition; // [rsp+48h] [rbp-B8h] BYREF
  void **v10; // [rsp+50h] [rbp-B0h]
  HKEY hKeya; // [rsp+58h] [rbp-A8h] BYREF
  const wchar_t *v12; // [rsp+60h] [rbp-A0h] BYREF
  const wchar_t *v13; // [rsp+68h] [rbp-98h]
  const wchar_t *v14; // [rsp+70h] [rbp-90h]
  __int64 v15; // [rsp+78h] [rbp-88h]
  int v16; // [rsp+80h] [rbp-80h]
  _BYTE v17[96]; // [rsp+88h] [rbp-78h] BYREF
  int v18; // [rsp+E8h] [rbp-18h]
  BYTE Data[16]; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v20; // [rsp+100h] [rbp+0h]
  __int64 v21; // [rsp+108h] [rbp+8h]
  _QWORD v22[4]; // [rsp+118h] [rbp+18h] BYREF
  int v23; // [rsp+138h] [rbp+38h]
  _BYTE v24[96]; // [rsp+140h] [rbp+40h] BYREF
  int v25; // [rsp+1A0h] [rbp+A0h]
  _QWORD v26[22]; // [rsp+1B0h] [rbp+B0h] BYREF

  v22[0] = L"base\\fs\\fsrm\\service\\globalstore\\clusterutil.cpp";
  v22[1] = L"CFsrmClusterUtil::GetClusterKeyForPath";
  v22[2] = L"CLUSUTLC";
  v22[3] = 276;
  v23 = 255;
  v25 = 0x1000000;
  memset_0(v24, 0, sizeof(v24));
  CSrmFunctionTracer::CSrmFunctionTracer(
    (__int64)v26,
    (const struct CSrmDebugInfo *)v22,
    (__int64)L"CFsrmClusterUtil::GetClusterKeyForPath");
  v12 = L"base\\fs\\fsrm\\service\\globalstore\\clusterutil.cpp";
  v13 = L"CFsrmClusterUtil::GetClusterKeyForPath";
  v14 = L"CLUSUTLC";
  v15 = 278;
  v16 = 255;
  v18 = 0x1000000;
  memset_0(v17, 0, sizeof(v17));
  CSrmFunctionTracer::Trace(v26, &v12, L"- Creating/Opening subkey for path '%s'", lpszSubKey);
  v10 = &CSrmAuto<HKEY__ *,CSrmAutoGenericValue_Storage<HKEY__ *,0,long (*)(HKEY__ *),&long ClusterRegCloseKey(HKEY__ *),HKEY__ * & (*)(HKEY__ * &),&public: static HKEY__ * & DTyper<HKEY__ *>::Identity(HKEY__ * &)>>::`vftable';
  dwDisposition = 0;
  hKeya = 0;
  v4 = ClusterRegCreateKey(hKey, lpszSubKey, 0, 0xF003Fu, 0, &hKeya, &dwDisposition);
  if ( v4 )
  {
    if ( v4 > 0 )
      v4 = (unsigned __int16)v4 | 0x80070000;
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)v26, v4);
    CSrmDebugInfo::CSrmDebugInfo(
      (__int64)&v12,
      (__int64)L"base\\fs\\fsrm\\service\\globalstore\\clusterutil.cpp",
      (__int64)L"CLUSUTLC",
      (__int64)L"CFsrmClusterUtil::GetClusterKeyForPath",
      295,
      0);
    Hr = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)v26);
    CSrmFunctionTracer::TranslateGenericError(v26, v8, Hr, L"ClusterRegCreateKey()");
  }
  v12 = L"base\\fs\\fsrm\\service\\globalstore\\clusterutil.cpp";
  v13 = L"CFsrmClusterUtil::GetClusterKeyForPath";
  v14 = L"CLUSUTLC";
  v16 = 255;
  v18 = 0x1000000;
  if ( dwDisposition == 1 )
  {
    v15 = 302;
    memset_0(v17, 0, sizeof(v17));
    CSrmFunctionTracer::Trace(v26, &v12, L"- The key is now created.");
    v21 = 7;
    v20 = 0;
    *(_WORD *)Data = 0;
    std::wstring::assign(Data, L"CreateSubkey");
    CFsrmClusterUtil::UpdateKeyDiagnoseInfo(hKey, Data);
    v21 = 7;
    v20 = 0;
    *(_WORD *)Data = 0;
    std::wstring::assign(Data, L"Create");
    CFsrmClusterUtil::UpdateKeyDiagnoseInfo(hKeya, Data);
  }
  else if ( dwDisposition == 2 )
  {
    v15 = 309;
    memset_0(v17, 0, sizeof(v17));
    CSrmFunctionTracer::Trace(v26, &v12, L"- The existing SRM key is was opened.");
  }
  else
  {
    v15 = 312;
    memset_0(v17, 0, sizeof(v17));
    CSrmFunctionTracer::Trace(v26, &v12, L"- Unknown disposition. [%d]", dwDisposition);
  }
  v5 = hKeya;
  v10 = &CSrmAutoGenericValue_Storage<HKEY__ *,0,long (*)(HKEY__ *),&long ClusterRegCloseKey(HKEY__ *),HKEY__ * & (*)(HKEY__ * &),&public: static HKEY__ * & DTyper<HKEY__ *>::Identity(HKEY__ * &)>::`vftable';
  hKeya = 0;
  v26[0] = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)v26);
  return v5;
}

```

## disassembly

```asm
0x18001e69c  mov     [rsp-8+arg_10], rbx
0x18001e6a1  push    rbp
0x18001e6a2  push    rsi
0x18001e6a3  push    rdi
0x18001e6a4  push    r12
0x18001e6a6  push    r13
0x18001e6a8  push    r14
0x18001e6aa  push    r15
0x18001e6ac  lea     rbp, [rsp-170h]
0x18001e6b4  sub     rsp, 270h
0x18001e6bb  mov     rax, cs:__security_cookie
0x18001e6c2  xor     rax, rsp
0x18001e6c5  mov     [rbp+1A0h+var_40], rax
0x18001e6cc  mov     rbx, rdx
0x18001e6cf  mov     rdi, rcx
0x18001e6d2  lea     r15, aBaseFsFsrmServ_40; "base\\fs\\fsrm\\service\\globalstore\\c"...
0x18001e6d9  mov     [rbp+1A0h+var_188], r15
0x18001e6dd  lea     r14, aCfsrmclusterut_9; "CFsrmClusterUtil::GetClusterKeyForPath"
0x18001e6e4  mov     [rbp+1A0h+var_180], r14
0x18001e6e8  lea     r12, aClusutlc; "CLUSUTLC"
0x18001e6ef  mov     [rbp+1A0h+var_178], r12
0x18001e6f3  mov     [rbp+1A0h+var_170], 114h
0x18001e6fb  xor     esi, esi
0x18001e6fd  mov     r13d, 0FFh
0x18001e703  mov     [rbp+1A0h+var_168], r13d
0x18001e707  mov     [rbp+1A0h+var_100], 1000000h
0x18001e711  xor     edx, edx; Val
0x18001e713  lea     r8d, [rsi+60h]; Size
0x18001e717  lea     rcx, [rbp+1A0h+var_160]; void *
0x18001e71b  call    memset_0
0x18001e720  mov     r8, r14
0x18001e723  lea     rdx, [rbp+1A0h+var_188]
0x18001e727  lea     rcx, [rbp+1A0h+var_F0]
0x18001e72e  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x18001e733  nop
0x18001e734  mov     [rsp+2A0h+var_240], r15
0x18001e739  mov     [rsp+2A0h+var_238], r14
0x18001e73e  mov     [rsp+2A0h+var_230], r12
0x18001e743  mov     [rsp+2A0h+var_228], 116h
0x18001e74c  mov     [rbp+1A0h+var_220], r13d
0x18001e750  mov     [rbp+1A0h+var_1B8], 1000000h
0x18001e757  xor     edx, edx; Val
0x18001e759  lea     r8d, [rsi+60h]; Size
0x18001e75d  lea     rcx, [rbp+1A0h+var_218]; void *
0x18001e761  call    memset_0
0x18001e766  mov     r9, rbx
0x18001e769  lea     r8, aCreatingOpenin; "- Creating/Opening subkey for path '%s'"
0x18001e770  lea     rdx, [rsp+2A0h+var_240]
0x18001e775  lea     rcx, [rbp+1A0h+var_F0]
0x18001e77c  call    ?Trace@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@PEBGZZ; CSrmFunctionTracer::Trace(CSrmDebugInfo,ushort const *,...)
0x18001e781  lea     rax, ??_7?$CSrmAuto@PEAUHKEY__@@V?$CSrmAutoGenericValue_Storage@PEAUHKEY__@@$0A@P6AJPEAU1@@Z$1?ClusterRegCloseKey@@YAJ0@ZP6AAEAPEAU1@AEAPEAU1@@Z$1?Identity@?$DTyper@PEAUHKEY__@@@@SAAEAPEAU1@1@Z@@@@6B@; const CSrmAuto<HKEY__ *,CSrmAutoGenericValue_Storage<HKEY__ *,0,long (*)(HKEY__ *),&ClusterRegCloseKey(HKEY__ *),HKEY__ * & (*)(HKEY__ * &),&DTyper<HKEY__ *>::Identity(HKEY__ * &)>>::`vftable'
0x18001e788  mov     [rsp+2A0h+var_250], rax
0x18001e78d  mov     [rsp+2A0h+dwDisposition], esi
0x18001e791  mov     [rsp+2A0h+hKey], rsi
0x18001e796  lea     rax, [rsp+2A0h+dwDisposition]
0x18001e79b  mov     [rsp+2A0h+lpdwDisposition], rax; lpdwDisposition
0x18001e7a0  lea     rax, [rsp+2A0h+hKey]
0x18001e7a5  mov     [rsp+2A0h+phkResult], rax; phkResult
0x18001e7aa  mov     [rsp+2A0h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x18001e7af  mov     r9d, 0F003Fh; samDesired
0x18001e7b5  xor     r8d, r8d; dwOptions
0x18001e7b8  mov     rdx, rbx; lpszSubKey
0x18001e7bb  mov     rcx, rdi; hKey
0x18001e7be  call    cs:__imp_ClusterRegCreateKey
0x18001e7c4  test    eax, eax
0x18001e7c6  jnz     loc_18001E93D
0x18001e7cc  mov     eax, [rsp+2A0h+dwDisposition]
0x18001e7d0  sub     eax, 1
0x18001e7d3  mov     [rsp+2A0h+var_240], r15
0x18001e7d8  mov     [rsp+2A0h+var_238], r14
0x18001e7dd  mov     [rsp+2A0h+var_230], r12
0x18001e7e2  mov     [rbp+1A0h+var_220], r13d
0x18001e7e6  mov     [rbp+1A0h+var_1B8], 1000000h
0x18001e7ed  lea     r8d, [rsi+60h]; Size
0x18001e7f1  lea     rcx, [rbp+1A0h+var_218]; void *
0x18001e7f5  jz      short loc_18001E859
0x18001e7f7  xor     edx, edx; Val
0x18001e7f9  cmp     eax, 1
0x18001e7fc  jz      short loc_18001E82E
0x18001e7fe  mov     [rsp+2A0h+var_228], 138h
0x18001e807  call    memset_0
0x18001e80c  mov     r9d, [rsp+2A0h+dwDisposition]
0x18001e811  lea     r8, aUnknownDisposi; "- Unknown disposition. [%d]"
0x18001e818  lea     rdx, [rsp+2A0h+var_240]
0x18001e81d  lea     rcx, [rbp+1A0h+var_F0]
0x18001e824  call    ?Trace@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@PEBGZZ; CSrmFunctionTracer::Trace(CSrmDebugInfo,ushort const *,...)
0x18001e829  jmp     loc_18001E8E0
0x18001e82e  mov     [rsp+2A0h+var_228], 135h
0x18001e837  call    memset_0
0x18001e83c  lea     r8, aTheExistingSrm; "- The existing SRM key is was opened."
0x18001e843  lea     rdx, [rsp+2A0h+var_240]
0x18001e848  lea     rcx, [rbp+1A0h+var_F0]
0x18001e84f  call    ?Trace@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@PEBGZZ; CSrmFunctionTracer::Trace(CSrmDebugInfo,ushort const *,...)
0x18001e854  jmp     loc_18001E8E0
0x18001e859  mov     [rsp+2A0h+var_228], 12Eh
0x18001e862  xor     edx, edx; Val
0x18001e864  call    memset_0
0x18001e869  lea     r8, aTheKeyIsNowCre; "- The key is now created."
0x18001e870  lea     rdx, [rsp+2A0h+var_240]
0x18001e875  lea     rcx, [rbp+1A0h+var_F0]
0x18001e87c  call    ?Trace@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@PEBGZZ; CSrmFunctionTracer::Trace(CSrmDebugInfo,ushort const *,...)
0x18001e881  mov     ebx, 7
0x18001e886  mov     [rbp+1A0h+var_198], rbx
0x18001e88a  mov     [rbp+1A0h+var_1A0], rsi
0x18001e88e  mov     word ptr [rbp+1A0h+Data], si
0x18001e892  lea     r8d, [rbx+5]
0x18001e896  lea     rdx, aCreatesubkey; "CreateSubkey"
0x18001e89d  lea     rcx, [rbp+1A0h+Data]; void *
0x18001e8a1  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18001e8a6  lea     rdx, [rbp+1A0h+Data]; lpData
0x18001e8aa  mov     rcx, rdi; hKey
0x18001e8ad  call    ?UpdateKeyDiagnoseInfo@CFsrmClusterUtil@@SAXPEAUHKEY__@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CFsrmClusterUtil::UpdateKeyDiagnoseInfo(HKEY__ *,std::wstring)
0x18001e8b2  mov     [rbp+1A0h+var_198], rbx
0x18001e8b6  mov     [rbp+1A0h+var_1A0], rsi
0x18001e8ba  mov     word ptr [rbp+1A0h+Data], si
0x18001e8be  lea     r8d, [rbx-1]
0x18001e8c2  lea     rdx, aCreate; "Create"
0x18001e8c9  lea     rcx, [rbp+1A0h+Data]; void *
0x18001e8cd  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18001e8d2  lea     rdx, [rbp+1A0h+Data]; lpData
0x18001e8d6  mov     rcx, [rsp+2A0h+hKey]; hKey
0x18001e8db  call    ?UpdateKeyDiagnoseInfo@CFsrmClusterUtil@@SAXPEAUHKEY__@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CFsrmClusterUtil::UpdateKeyDiagnoseInfo(HKEY__ *,std::wstring)
0x18001e8e0  mov     rbx, [rsp+2A0h+hKey]
0x18001e8e5  lea     rax, ??_7?$CSrmAutoGenericValue_Storage@PEAUHKEY__@@$0A@P6AJPEAU1@@Z$1?ClusterRegCloseKey@@YAJ0@ZP6AAEAPEAU1@AEAPEAU1@@Z$1?Identity@?$DTyper@PEAUHKEY__@@@@SAAEAPEAU1@1@Z@@6B@; const CSrmAutoGenericValue_Storage<HKEY__ *,0,long (*)(HKEY__ *),&ClusterRegCloseKey(HKEY__ *),HKEY__ * & (*)(HKEY__ * &),&DTyper<HKEY__ *>::Identity(HKEY__ * &)>::`vftable'
0x18001e8ec  mov     [rsp+2A0h+var_250], rax
0x18001e8f1  mov     [rsp+2A0h+hKey], rsi
0x18001e8f6  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x18001e8fd  mov     [rbp+1A0h+var_F0], rax
0x18001e904  lea     rcx, [rbp+1A0h+var_F0]; this
0x18001e90b  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x18001e910  mov     rax, rbx
0x18001e913  mov     rcx, [rbp+1A0h+var_40]
0x18001e91a  xor     rcx, rsp; StackCookie
0x18001e91d  call    __security_check_cookie
0x18001e922  mov     rbx, [rsp+2A0h+arg_10]
0x18001e92a  add     rsp, 270h
0x18001e931  pop     r15
0x18001e933  pop     r14
0x18001e935  pop     r13
0x18001e937  pop     r12
0x18001e939  pop     rdi
0x18001e93a  pop     rsi
0x18001e93b  pop     rbp
0x18001e93c  retn
0x18001e93d  jle     short loc_18001E947
0x18001e93f  movzx   eax, ax
0x18001e942  or      eax, 80070000h
0x18001e947  mov     edx, eax; int
0x18001e949  lea     rcx, [rbp+1A0h+var_F0]; this
0x18001e950  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x18001e955  mov     dword ptr [rsp+2A0h+phkResult], esi
0x18001e959  mov     dword ptr [rsp+2A0h+lpSecurityAttributes], 127h
0x18001e961  mov     r9, r14
0x18001e964  mov     r8, r12
0x18001e967  mov     rdx, r15
0x18001e96a  lea     rcx, [rsp+2A0h+var_240]
0x18001e96f  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x18001e974  mov     rdx, rax
0x18001e977  lea     rcx, [rbp+1A0h+var_F0]; this
0x18001e97e  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18001e983  mov     r8d, eax
0x18001e986  lea     r9, aClusterregcrea; "ClusterRegCreateKey()"
0x18001e98d  lea     rcx, [rbp+1A0h+var_F0]
0x18001e994  call    ?TranslateGenericError@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::TranslateGenericError(CSrmDebugInfo,long,ushort const *,...)
```
