# CEventNotifier::DelPersistentEventCB(ushort *,_GUID const *,_GUID const *,int)

- ea: `0x180030294`
- end: `0x180030719`
- name: `?DelPersistentEventCB@CEventNotifier@@AEAAJPEAGPEBU_GUID@@1H@Z`
- size: `1157`
- prototype: `__int64 __fastcall(CEventNotifier *this, unsigned __int16 *, const struct _GUID *, const struct _GUID *, int)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800315a0`

## callees

- `0x18000c7c0`
- `0x18000cba0`
- `0x18000d770`
- `0x18000da10`
- `0x18000dd00`
- `0x18000f4fc`
- `0x180011a94`
- `0x18001247c`
- `0x180024cb0`
- `0x18002de18`
- `0x18002def8`
- `0x180030294`
- `0x180030720`
- `0x180033cc0`
- `0x180034658`
- `0x18003b75c`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180030400`
- `ADVAPI32!RegCloseKey` at `0x1800305ee`
- `ADVAPI32!RegCloseKey` at `0x18003064f`
- `ADVAPI32!RegCloseKey` at `0x18003069f`
- `ADVAPI32!RegCloseKey` at `0x180030400`
- `ADVAPI32!RegCloseKey` at `0x1800305ee`
- `ADVAPI32!RegCloseKey` at `0x18003064f`
- `ADVAPI32!RegCloseKey` at `0x18003069f`
- `ADVAPI32!RegDeleteKeyW` at `0x1800303a5`
- `ADVAPI32!RegDeleteKeyW` at `0x18003058b`
- `ADVAPI32!RegDeleteKeyW` at `0x180030694`
- `ADVAPI32!RegDeleteKeyW` at `0x1800303a5`
- `ADVAPI32!RegDeleteKeyW` at `0x18003058b`
- `ADVAPI32!RegDeleteKeyW` at `0x180030694`
- `ADVAPI32!RegEnumKeyExW` at `0x1800304bd`
- `ADVAPI32!RegEnumKeyExW` at `0x180030639`
- `ADVAPI32!RegEnumKeyExW` at `0x1800304bd`
- `ADVAPI32!RegEnumKeyExW` at `0x180030639`
- `ADVAPI32!RegOpenKeyExW` at `0x18003067e`
- `ADVAPI32!RegOpenKeyExW` at `0x18003067e`
- `KERNEL32!GetLastError` at `0x18003047b`
- `KERNEL32!GetLastError` at `0x18003047b`
- `OLEAUT32!__imp_SysAllocString` at `0x18003054e`
- `OLEAUT32!__imp_SysAllocString` at `0x18003054e`
- `OLEAUT32!__imp_SysFreeString` at `0x180030575`
- `OLEAUT32!__imp_SysFreeString` at `0x180030575`
- `ole32!StringFromGUID2` at `0x180030393`
- `ole32!StringFromGUID2` at `0x180030393`
- `SETUPAPI!SetupDiOpenClassRegKey` at `0x18003042d`
- `SETUPAPI!SetupDiOpenClassRegKey` at `0x18003042d`

## string_xrefs

- `0x180030670`: `CLSID`
- `0x1800303b6`: `RegDeleteValue() failed, lRet = 0x%08X`
- `0x1800303da`: `RegDeleteValue() failed, lRet = 0x%08X`
- `0x18003059d`: `RegDeleteValue() failed, lRet = 0x%08X`
- `0x1800305c6`: `RegDeleteValue() failed, lRet = 0x%08X`
- `0x18003043c`: `Can not open Image device class key.`
- `0x18003045e`: `Can not open Image device class key.`

## pseudocode

```c
__int64 __fastcall CEventNotifier::DelPersistentEventCB(
        CEventNotifier *this,
        unsigned __int16 *a2,
        const struct _GUID *a3,
        const struct _GUID *a4,
        int a5)
{
  const struct _GUID *v5; // r13
  struct tagWiaTraceData_Type *v8; // rax
  char *v9; // rdx
  unsigned int v10; // r8d
  CEventNotifier *v11; // rcx
  int EventByGUID; // edi
  char *v13; // rbx
  void *v14; // rdx
  void *v15; // rax
  int v16; // edx
  int v17; // ecx
  char *v18; // rbx
  void *v19; // rdx
  void *v20; // rax
  int v21; // edx
  int v22; // ecx
  HKEY v23; // rdi
  char *v24; // rbx
  void *v25; // rdx
  void *v26; // rax
  int v27; // edx
  int v28; // ecx
  DWORD v29; // r12d
  unsigned __int16 *v30; // rax
  CEventNotifier *v31; // rcx
  OLECHAR *v32; // r15
  int v33; // ebx
  LSTATUS v34; // r15d
  char *v35; // rbx
  void *v36; // rdx
  void *v37; // rax
  int v38; // edx
  int v39; // ecx
  __int64 v40; // rax
  __int64 v41; // rax
  unsigned int lpReserved; // [rsp+20h] [rbp-E0h]
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  HKEY phkResult; // [rsp+50h] [rbp-B0h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+58h] [rbp-A8h] BYREF
  const struct _GUID *v48; // [rsp+60h] [rbp-A0h]
  _BYTE v49[80]; // [rsp+70h] [rbp-90h] BYREF
  const unsigned __int64 *v50; // [rsp+C0h] [rbp-40h] BYREF
  __int16 v51; // [rsp+C8h] [rbp-38h] BYREF
  OLECHAR *psz; // [rsp+1C8h] [rbp+C8h]
  __int64 v53; // [rsp+1D0h] [rbp+D0h]
  __int64 v54; // [rsp+1D8h] [rbp+D8h]
  char v55; // [rsp+1E0h] [rbp+E0h]
  _QWORD v56[38]; // [rsp+1F0h] [rbp+F0h] BYREF
  WCHAR Name[8]; // [rsp+320h] [rbp+220h] BYREF
  OLECHAR sz[40]; // [rsp+330h] [rbp+230h] BYREF

  v48 = a4;
  v5 = a4;
  v8 = (struct tagWiaTraceData_Type *)WiaTrace_Trace((const char *)&word_18007CF56);
  CWiaTraceFn::CWiaTraceFn((CWiaTraceFn *)v49, v9, v10, "CEventNotifier::DelPersistentEventCB", lpReserved, v8);
  hKey = 0;
  cchName = 0;
  *(_OWORD *)Name = 0;
  memset_0(sz, 0, sizeof(sz));
  ftLastWriteTime = 0;
  phkResult = 0;
  EventByGUID = CEventNotifier::FindEventByGUID(v11, a2, a3, &hKey);
  if ( EventByGUID )
  {
    v13 = (char *)WiaTrace_TraceLog("FindEventByGUID() failed, hr=0x%08X");
    WriteDbgTraceErrorWI("CEventNotifier::DelPersistentEventCB", v13);
    WiaTrcLib::Free((WiaTrcLib *)v13, v14);
    v15 = (void *)WiaTrace_Trace("FindEventByGUID() failed, hr=0x%08X", EventByGUID);
    WiaTrace_ProcessTrace_Ex(v17, v16, (int)"CEventNotifier::DelPersistentEventCB", 1, v15);
    goto LABEL_30;
  }
  StringFromGUID2(v5, sz, 40);
  EventByGUID = RegDeleteKeyW(hKey, sz);
  if ( (EventByGUID & 0xFFFFFFFD) != 0 )
  {
    v18 = (char *)WiaTrace_TraceLog("RegDeleteValue() failed, lRet = 0x%08X");
    WriteDbgTraceErrorWI("CEventNotifier::DelPersistentEventCB", v18);
    WiaTrcLib::Free((WiaTrcLib *)v18, v19);
    v20 = (void *)WiaTrace_Trace("RegDeleteValue() failed, lRet = 0x%08X", EventByGUID);
    WiaTrace_ProcessTrace_Ex(v22, v21, (int)"CEventNotifier::DelPersistentEventCB", 1, v20);
  }
  RegCloseKey(hKey);
  if ( !a2 )
  {
    v23 = SetupDiOpenClassRegKey(&GUID_DEVCLASS_IMAGE, 0x2001Fu);
    if ( v23 == HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
    {
      v24 = (char *)WiaTrace_TraceLog("Can not open Image device class key.");
      WriteDbgTraceErrorWI("CEventNotifier::DelPersistentEventCB", v24);
      WiaTrcLib::Free((WiaTrcLib *)v24, v25);
      v26 = (void *)WiaTrace_Trace("Can not open Image device class key.");
      WiaTrace_ProcessTrace_Ex(v28, v27, (int)"CEventNotifier::DelPersistentEventCB", 1, v26);
      GetLastError();
    }
    else
    {
      cchName = 8;
      v29 = 0;
      if ( !RegEnumKeyExW(v23, 0, Name, &cchName, 0, 0, 0, &ftLastWriteTime) )
      {
        do
        {
          v50 = &CSimpleStringBase<unsigned short>::`vftable';
          psz = (OLECHAR *)&v51;
          v53 = 128;
          v54 = 16;
          v55 = 0;
          v51 = 0;
          CSimpleStringBase<unsigned short>::operator=(&v50, L"{6BDD1FC6-810F-11D0-BEC7-08002BE2092F}\\");
          CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>(v56, Name);
          CSimpleStringBase<unsigned short>::operator+=(&v50, v56);
          v56[0] = &CSimpleStringBase<unsigned short>::`vftable';
          CSimpleStringBase<unsigned short>::DeleteStorage(v56);
          v30 = SysAllocString(psz);
          v32 = v30;
          if ( v30 )
          {
            v33 = CEventNotifier::FindEventByGUID(v31, v30, a3, &hKey);
            SysFreeString(v32);
            if ( !v33 )
            {
              v34 = RegDeleteKeyW(hKey, sz);
              if ( (v34 & 0xFFFFFFFD) != 0 )
              {
                v35 = (char *)WiaTrace_TraceLog("RegDeleteValue() failed, lRet = 0x%08X");
                WriteDbgTraceErrorWI("CEventNotifier::DelPersistentEventCB", v35);
                WiaTrcLib::Free((WiaTrcLib *)v35, v36);
                v37 = (void *)WiaTrace_Trace("RegDeleteValue() failed, lRet = 0x%08X", v34);
                WiaTrace_ProcessTrace_Ex(v39, v38, (int)"CEventNotifier::DelPersistentEventCB", 1, v37);
              }
              RegCloseKey(hKey);
            }
          }
          v50 = &CSimpleStringBase<unsigned short>::`vftable';
          CSimpleStringBase<unsigned short>::DeleteStorage(&v50);
          cchName = 8;
          ++v29;
        }
        while ( !RegEnumKeyExW(v23, v29, Name, &cchName, 0, 0, 0, &ftLastWriteTime) );
        v5 = v48;
      }
    }
    RegCloseKey(v23);
    if ( a5 )
    {
      if ( RegOpenKeyExW(HKEY_CLASSES_ROOT, L"CLSID", 0, 0x20006u, &phkResult) )
      {
LABEL_29:
        EventByGUID = 0;
        goto LABEL_30;
      }
      RegDeleteKeyW(phkResult, sz);
      RegCloseKey(phkResult);
    }
    if ( a3 )
    {
      v40 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&WIA_EVENT_STI_PROXY.Data1;
      if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&WIA_EVENT_STI_PROXY.Data1 )
        v40 = *(_QWORD *)a3->Data4 - *(_QWORD *)WIA_EVENT_STI_PROXY.Data4;
      if ( !v40 )
        goto LABEL_28;
      v41 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&WIA_EVENT_DEVICE_CONNECTED.Data1;
      if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&WIA_EVENT_DEVICE_CONNECTED.Data1 )
        v41 = *(_QWORD *)a3->Data4 - *(_QWORD *)WIA_EVENT_DEVICE_CONNECTED.Data4;
      if ( !v41 )
LABEL_28:
        RemoveWiaHandlerFromWindowsAutoPlay(v5);
    }
    goto LABEL_29;
  }
  if ( EventByGUID > 0 )
    EventByGUID = (unsigned __int16)EventByGUID | 0x80070000;
LABEL_30:
  CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v49);
  return (unsigned int)EventByGUID;
}

```

## disassembly

```asm
0x180030294  push    rbp
0x180030296  push    rbx
0x180030297  push    rsi
0x180030298  push    rdi
0x180030299  push    r12
0x18003029b  push    r13
0x18003029d  push    r15
0x18003029f  lea     rbp, [rsp-290h]
0x1800302a7  sub     rsp, 390h
0x1800302ae  mov     rax, cs:__security_cookie
0x1800302b5  xor     rax, rsp
0x1800302b8  mov     [rbp+2C0h+var_40], rax
0x1800302bf  lea     rcx, word_18007CF56
0x1800302c6  mov     [rsp+3C0h+var_360], r9
0x1800302cb  mov     r13, r9
0x1800302ce  mov     rsi, r8
0x1800302d1  mov     r15, rdx
0x1800302d4  call    WiaTrace_Trace
0x1800302d9  lea     r12, aCeventnotifier_20; "CEventNotifier::DelPersistentEventCB"
0x1800302e0  mov     [rsp+3C0h+lpClass], rax; struct tagWiaTraceData_Type *
0x1800302e5  mov     r9, r12; char *
0x1800302e8  lea     rcx, [rsp+3C0h+var_350]; this
0x1800302ed  call    ??0CWiaTraceFn@@QEAA@PEADK0KPEAUtagWiaTraceData_Type@@@Z; CWiaTraceFn::CWiaTraceFn(char *,ulong,char *,ulong,tagWiaTraceData_Type *)
0x1800302f2  xor     ebx, ebx
0x1800302f4  lea     rcx, [rbp+2C0h+sz]; void *
0x1800302fb  xorps   xmm0, xmm0
0x1800302fe  mov     [rsp+3C0h+hKey], rbx
0x180030303  xor     edx, edx; Val
0x180030305  mov     [rsp+3C0h+cchName], ebx
0x180030309  movups  xmmword ptr [rbp+2C0h+Name], xmm0
0x180030310  lea     r8d, [rbx+50h]; Size
0x180030314  call    memset_0
0x180030319  lea     r9, [rsp+3C0h+hKey]; HKEY *
0x18003031e  mov     qword ptr [rsp+3C0h+ftLastWriteTime.dwLowDateTime], rbx
0x180030323  mov     r8, rsi; struct _GUID *
0x180030326  mov     [rsp+3C0h+phkResult], rbx
0x18003032b  mov     rdx, r15; unsigned __int16 *
0x18003032e  call    ?FindEventByGUID@CEventNotifier@@AEAAJPEAGPEBU_GUID@@PEAPEAUHKEY__@@@Z; CEventNotifier::FindEventByGUID(ushort *,_GUID const *,HKEY__ * *)
0x180030333  mov     edi, eax
0x180030335  test    eax, eax
0x180030337  jz      short loc_180030383
0x180030339  mov     edx, eax
0x18003033b  lea     rcx, aFindeventbygui; "FindEventByGUID() failed, hr=0x%08X"
0x180030342  call    WiaTrace_TraceLog
0x180030347  mov     rdx, rax; char *
0x18003034a  mov     rcx, r12; char *
0x18003034d  mov     rbx, rax
0x180030350  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180030355  mov     rcx, rbx; this
0x180030358  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18003035d  mov     edx, edi
0x18003035f  lea     rcx, aFindeventbygui; "FindEventByGUID() failed, hr=0x%08X"
0x180030366  call    WiaTrace_Trace
0x18003036b  mov     r9d, 1; int
0x180030371  mov     [rsp+3C0h+lpReserved], rax; lpMem
0x180030376  mov     r8, r12; int
0x180030379  call    WiaTrace_ProcessTrace_Ex
0x18003037e  jmp     loc_1800306EC
0x180030383  mov     r8d, 28h ; '('; cchMax
0x180030389  lea     rdx, [rbp+2C0h+sz]; lpsz
0x180030390  mov     rcx, r13; rguid
0x180030393  call    cs:__imp_StringFromGUID2
0x180030399  mov     rcx, [rsp+3C0h+hKey]; hKey
0x18003039e  lea     rdx, [rbp+2C0h+sz]; lpSubKey
0x1800303a5  call    cs:__imp_RegDeleteKeyW
0x1800303ab  mov     edi, eax
0x1800303ad  test    eax, 0FFFFFFFDh
0x1800303b2  jz      short loc_1800303FB
0x1800303b4  mov     edx, eax
0x1800303b6  lea     rcx, aRegdeletevalue; "RegDeleteValue() failed, lRet = 0x%08X"
0x1800303bd  call    WiaTrace_TraceLog
0x1800303c2  mov     rdx, rax; char *
0x1800303c5  mov     rcx, r12; char *
0x1800303c8  mov     rbx, rax
0x1800303cb  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x1800303d0  mov     rcx, rbx; this
0x1800303d3  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x1800303d8  mov     edx, edi
0x1800303da  lea     rcx, aRegdeletevalue; "RegDeleteValue() failed, lRet = 0x%08X"
0x1800303e1  call    WiaTrace_Trace
0x1800303e6  mov     r9d, 1; int
0x1800303ec  mov     [rsp+3C0h+lpReserved], rax; lpMem
0x1800303f1  mov     r8, r12; int
0x1800303f4  call    WiaTrace_ProcessTrace_Ex
0x1800303f9  xor     ebx, ebx
0x1800303fb  mov     rcx, [rsp+3C0h+hKey]; hKey
0x180030400  call    cs:__imp_RegCloseKey
0x180030406  test    r15, r15
0x180030409  jz      short loc_180030421
0x18003040b  test    edi, edi
0x18003040d  jle     loc_1800306EC
0x180030413  movzx   edi, di
0x180030416  or      edi, 80070000h
0x18003041c  jmp     loc_1800306EC
0x180030421  mov     edx, 2001Fh; samDesired
0x180030426  lea     rcx, GUID_DEVCLASS_IMAGE; ClassGuid
0x18003042d  call    cs:__imp_SetupDiOpenClassRegKey
0x180030433  mov     rdi, rax
0x180030436  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003043a  jnz     short loc_180030488
0x18003043c  lea     rcx, aCanNotOpenImag; "Can not open Image device class key."
0x180030443  call    WiaTrace_TraceLog
0x180030448  mov     rdx, rax; char *
0x18003044b  mov     rcx, r12; char *
0x18003044e  mov     rbx, rax
0x180030451  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180030456  mov     rcx, rbx; this
0x180030459  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18003045e  lea     rcx, aCanNotOpenImag; "Can not open Image device class key."
0x180030465  call    WiaTrace_Trace
0x18003046a  lea     r9d, [rdi+2]; int
0x18003046e  mov     [rsp+3C0h+lpReserved], rax; lpMem
0x180030473  mov     r8, r12; int
0x180030476  call    WiaTrace_ProcessTrace_Ex
0x18003047b  call    cs:__imp_GetLastError
0x180030481  xor     ebx, ebx
0x180030483  jmp     loc_18003064C
0x180030488  lea     rax, [rsp+3C0h+ftLastWriteTime]
0x18003048d  mov     [rsp+3C0h+cchName], 8
0x180030495  mov     [rsp+3C0h+lpftLastWriteTime], rax; lpftLastWriteTime
0x18003049a  lea     r9, [rsp+3C0h+cchName]; lpcchName
0x18003049f  mov     [rsp+3C0h+lpcchClass], rbx; lpcchClass
0x1800304a4  lea     r8, [rbp+2C0h+Name]; lpName
0x1800304ab  mov     [rsp+3C0h+lpClass], rbx; lpClass
0x1800304b0  xor     edx, edx; dwIndex
0x1800304b2  mov     rcx, rdi; hKey
0x1800304b5  mov     [rsp+3C0h+lpReserved], rbx; lpReserved
0x1800304ba  mov     r12d, ebx
0x1800304bd  call    cs:__imp_RegEnumKeyExW
0x1800304c3  test    eax, eax
0x1800304c5  jnz     loc_18003064C
0x1800304cb  lea     r13, ??_7?$CSimpleStringBase@G@@6B@; const CSimpleStringBase<ushort>::`vftable'
0x1800304d2  lea     rax, [rbp+2C0h+var_2F8]
0x1800304d6  mov     [rbp+2C0h+var_300], r13
0x1800304da  lea     rdx, a6bdd1fc6810f11_0; "{6BDD1FC6-810F-11D0-BEC7-08002BE2092F}"...
0x1800304e1  mov     [rbp+2C0h+psz], rax
0x1800304e8  lea     rcx, [rbp+2C0h+var_300]
0x1800304ec  mov     [rbp+2C0h+var_1F0], 80h
0x1800304f7  mov     [rbp+2C0h+var_1E8], 10h
0x180030502  mov     [rbp+2C0h+var_1E0], bl
0x180030508  mov     [rbp+2C0h+var_2F8], bx
0x18003050c  call    ??4?$CSimpleStringBase@G@@QEAAAEAV0@PEBG@Z; CSimpleStringBase<ushort>::operator=(ushort const *)
0x180030511  lea     rdx, [rbp+2C0h+Name]
0x180030518  lea     rcx, [rbp+2C0h+var_1D0]
0x18003051f  call    ??0?$CSimpleStringBase@G@@QEAA@PEBG@Z; CSimpleStringBase<ushort>::CSimpleStringBase<ushort>(ushort const *)
0x180030524  lea     rdx, [rbp+2C0h+var_1D0]
0x18003052b  lea     rcx, [rbp+2C0h+var_300]
0x18003052f  call    ??Y?$CSimpleStringBase@G@@QEAAAEAV0@AEBV0@@Z; CSimpleStringBase<ushort>::operator+=(CSimpleStringBase<ushort> const &)
0x180030534  lea     rcx, [rbp+2C0h+var_1D0]
0x18003053b  mov     [rbp+2C0h+var_1D0], r13
0x180030542  call    ?DeleteStorage@?$CSimpleStringBase@G@@AEAAXXZ; CSimpleStringBase<ushort>::DeleteStorage(void)
0x180030547  mov     rcx, [rbp+2C0h+psz]; psz
0x18003054e  call    cs:__imp_SysAllocString
0x180030554  mov     r15, rax
0x180030557  test    rax, rax
0x18003055a  jz      loc_1800305F6
0x180030560  lea     r9, [rsp+3C0h+hKey]; HKEY *
0x180030565  mov     r8, rsi; struct _GUID *
0x180030568  mov     rdx, rax; unsigned __int16 *
0x18003056b  call    ?FindEventByGUID@CEventNotifier@@AEAAJPEAGPEBU_GUID@@PEAPEAUHKEY__@@@Z; CEventNotifier::FindEventByGUID(ushort *,_GUID const *,HKEY__ * *)
0x180030570  mov     rcx, r15; bstrString
0x180030573  mov     ebx, eax
0x180030575  call    cs:__imp_SysFreeString
0x18003057b  test    ebx, ebx
0x18003057d  jnz     short loc_1800305F4
0x18003057f  mov     rcx, [rsp+3C0h+hKey]; hKey
0x180030584  lea     rdx, [rbp+2C0h+sz]; lpSubKey
0x18003058b  call    cs:__imp_RegDeleteKeyW
0x180030591  mov     r15d, eax
0x180030594  test    eax, 0FFFFFFFDh
0x180030599  jz      short loc_1800305E9
0x18003059b  mov     edx, eax
0x18003059d  lea     rcx, aRegdeletevalue; "RegDeleteValue() failed, lRet = 0x%08X"
0x1800305a4  call    WiaTrace_TraceLog
0x1800305a9  mov     rdx, rax; char *
0x1800305ac  lea     rcx, aCeventnotifier_20; "CEventNotifier::DelPersistentEventCB"
0x1800305b3  mov     rbx, rax
0x1800305b6  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x1800305bb  mov     rcx, rbx; this
0x1800305be  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x1800305c3  mov     edx, r15d
0x1800305c6  lea     rcx, aRegdeletevalue; "RegDeleteValue() failed, lRet = 0x%08X"
0x1800305cd  call    WiaTrace_Trace
0x1800305d2  mov     r9d, 1; int
0x1800305d8  mov     [rsp+3C0h+lpReserved], rax; lpMem
0x1800305dd  lea     r8, aCeventnotifier_20; "CEventNotifier::DelPersistentEventCB"
0x1800305e4  call    WiaTrace_ProcessTrace_Ex
0x1800305e9  mov     rcx, [rsp+3C0h+hKey]; hKey
0x1800305ee  call    cs:__imp_RegCloseKey
0x1800305f4  xor     ebx, ebx
0x1800305f6  lea     rcx, [rbp+2C0h+var_300]
0x1800305fa  mov     [rbp+2C0h+var_300], r13
0x1800305fe  call    ?DeleteStorage@?$CSimpleStringBase@G@@AEAAXXZ; CSimpleStringBase<ushort>::DeleteStorage(void)
0x180030603  lea     rax, [rsp+3C0h+ftLastWriteTime]
0x180030608  mov     [rsp+3C0h+cchName], 8
0x180030610  mov     [rsp+3C0h+lpftLastWriteTime], rax; lpftLastWriteTime
0x180030615  lea     r9, [rsp+3C0h+cchName]; lpcchName
0x18003061a  mov     [rsp+3C0h+lpcchClass], rbx; lpcchClass
0x18003061f  lea     r8, [rbp+2C0h+Name]; lpName
0x180030626  inc     r12d
0x180030629  mov     [rsp+3C0h+lpClass], rbx; lpClass
0x18003062e  mov     edx, r12d; dwIndex
0x180030631  mov     [rsp+3C0h+lpReserved], rbx; lpReserved
0x180030636  mov     rcx, rdi; hKey
0x180030639  call    cs:__imp_RegEnumKeyExW
0x18003063f  test    eax, eax
0x180030641  jz      loc_1800304D2
0x180030647  mov     r13, [rsp+3C0h+var_360]
0x18003064c  mov     rcx, rdi; hKey
0x18003064f  call    cs:__imp_RegCloseKey
0x180030655  cmp     [rbp+2C0h+arg_20], ebx
0x18003065b  jz      short loc_1800306A5
0x18003065d  lea     rax, [rsp+3C0h+phkResult]
0x180030662  mov     r9d, 20006h; samDesired
0x180030668  xor     r8d, r8d; ulOptions
0x18003066b  mov     [rsp+3C0h+lpReserved], rax; phkResult
0x180030670  lea     rdx, aClsid; "CLSID"
0x180030677  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18003067e  call    cs:__imp_RegOpenKeyExW
0x180030684  test    eax, eax
0x180030686  jnz     short loc_1800306EA
0x180030688  mov     rcx, [rsp+3C0h+phkResult]; hKey
0x18003068d  lea     rdx, [rbp+2C0h+sz]; lpSubKey
0x180030694  call    cs:__imp_RegDeleteKeyW
0x18003069a  mov     rcx, [rsp+3C0h+phkResult]; hKey
0x18003069f  call    cs:__imp_RegCloseKey
0x1800306a5  test    rsi, rsi
0x1800306a8  jz      short loc_1800306EA
0x1800306aa  mov     rax, [rsi]
0x1800306ad  sub     rax, qword ptr cs:WIA_EVENT_STI_PROXY.Data1
0x1800306b4  jnz     short loc_1800306C1
0x1800306b6  mov     rax, [rsi+8]
0x1800306ba  sub     rax, qword ptr cs:WIA_EVENT_STI_PROXY.Data4
0x1800306c1  test    rax, rax
0x1800306c4  jz      short loc_1800306E2
0x1800306c6  mov     rax, [rsi]
0x1800306c9  sub     rax, qword ptr cs:WIA_EVENT_DEVICE_CONNECTED.Data1
0x1800306d0  jnz     short loc_1800306DD
0x1800306d2  mov     rax, [rsi+8]
0x1800306d6  sub     rax, qword ptr cs:WIA_EVENT_DEVICE_CONNECTED.Data4
0x1800306dd  test    rax, rax
0x1800306e0  jnz     short loc_1800306EA
0x1800306e2  mov     rcx, r13; struct _GUID *
0x1800306e5  call    ?RemoveWiaHandlerFromWindowsAutoPlay@@YAXPEBU_GUID@@@Z; RemoveWiaHandlerFromWindowsAutoPlay(_GUID const *)
0x1800306ea  mov     edi, ebx
0x1800306ec  lea     rcx, [rsp+3C0h+var_350]; this
0x1800306f1  call    ??1CWiaTraceFn@@QEAA@XZ; CWiaTraceFn::~CWiaTraceFn(void)
0x1800306f6  mov     eax, edi
0x1800306f8  mov     rcx, [rbp+2C0h+var_40]
0x1800306ff  xor     rcx, rsp; StackCookie
0x180030702  call    __security_check_cookie
0x180030707  add     rsp, 390h
0x18003070e  pop     r15
0x180030710  pop     r13
0x180030712  pop     r12
0x180030714  pop     rdi
0x180030715  pop     rsi
0x180030716  pop     rbx
0x180030717  pop     rbp
0x180030718  retn
```
