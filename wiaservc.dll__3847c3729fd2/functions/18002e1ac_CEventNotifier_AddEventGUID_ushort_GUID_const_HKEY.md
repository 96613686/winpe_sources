# CEventNotifier::AddEventGUID(ushort *,_GUID const *,HKEY__ * *)

- ea: `0x18002e1ac`
- end: `0x18002e5cc`
- name: `?AddEventGUID@CEventNotifier@@AEAAJPEAGPEBU_GUID@@PEAPEAUHKEY__@@@Z`
- size: `1056`
- prototype: `__int64 __fastcall(CEventNotifier *this, unsigned __int16 *, const struct _GUID *, HKEY *)`
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800245f0`

## callees

- `0x18000b6a0`
- `0x18000cba0`
- `0x18000d770`
- `0x18000da10`
- `0x18000f4fc`
- `0x180011a94`
- `0x180016e88`
- `0x180027590`
- `0x18002de18`
- `0x18002def8`
- `0x18002e1ac`
- `0x18002e5d4`
- `0x18002e9d8`
- `0x18002eab4`
- `0x180033cc0`
- `0x180034658`
- `0x18003b854`
- `0x180078010`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18002e534`
- `ADVAPI32!RegCloseKey` at `0x18002e59a`
- `ADVAPI32!RegCloseKey` at `0x18002e534`
- `ADVAPI32!RegCloseKey` at `0x18002e59a`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18002e3cf`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18002e3cf`
- `ADVAPI32!RegCreateKeyExW` at `0x18002e43d`
- `ADVAPI32!RegCreateKeyExW` at `0x18002e43d`
- `ADVAPI32!RegSetValueExW` at `0x18002e49d`
- `ADVAPI32!RegSetValueExW` at `0x18002e49d`
- `KERNEL32!lstrlenW` at `0x18002e46f`
- `KERNEL32!lstrlenW` at `0x18002e46f`
- `ole32!CoTaskMemFree` at `0x18002e4c7`
- `ole32!CoTaskMemFree` at `0x18002e4c7`
- `ole32!StringFromCLSID` at `0x18002e45a`
- `ole32!StringFromCLSID` at `0x18002e45a`

## pseudocode

```c
__int64 __fastcall CEventNotifier::AddEventGUID(
        CEventNotifier *this,
        unsigned __int16 *a2,
        const struct _GUID *a3,
        HKEY *a4)
{
  unsigned int i; // ebx
  _QWORD *v8; // rcx
  __int64 v9; // rax
  int v10; // r15d
  int GlobalEventsKey; // edi
  char *v12; // rbx
  void *v13; // rdx
  void *v14; // rax
  int v15; // edx
  int v16; // ecx
  __int64 v17; // rcx
  __int64 USDWrapperFromDeviceList; // rdi
  int v19; // eax
  char *v20; // rbx
  void *v21; // rdx
  void *v22; // rax
  int v23; // edx
  int v24; // ecx
  LSTATUS v25; // eax
  int v26; // eax
  LSTATUS v27; // eax
  char *v28; // rbx
  void *v29; // rdx
  char *v30; // rbx
  void *v31; // rdx
  void *v32; // rax
  int v33; // edx
  int v34; // ecx
  LPDWORD lpcSubKeys; // [rsp+20h] [rbp-E0h]
  DWORD cSubKeys; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  LPOLESTR lpsz; // [rsp+70h] [rbp-90h] BYREF
  HKEY phkResult; // [rsp+78h] [rbp-88h] BYREF
  WCHAR SubKey[136]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v42; // [rsp+190h] [rbp+90h]

  hKey = 0;
  phkResult = 0;
  if ( !a2 )
  {
    for ( i = 0; i < 0x19; ++i )
    {
      v8 = (_QWORD *)*((_QWORD *)&off_1800797C0 + 2 * (int)i);
      v9 = *v8 - *(_QWORD *)&a3->Data1;
      if ( *v8 == *(_QWORD *)&a3->Data1 )
        v9 = v8[1] - *(_QWORD *)a3->Data4;
      if ( !v9 )
      {
        v10 = 1;
        GlobalEventsKey = CEventNotifier::GetGlobalEventsKey(&hKey);
        goto LABEL_14;
      }
    }
    v12 = (char *)WiaTrace_TraceLog("Trying to register application for a unknown global event");
    WriteDbgTraceErrorWI("CEventNotifier::AddEventGUID", v12);
    WiaTrcLib::Free((WiaTrcLib *)v12, v13);
    v14 = (void *)WiaTrace_Trace("Trying to register application for a unknown global event");
    goto LABEL_30;
  }
  v10 = 0;
  i = -1;
  CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>(SubKey, a2);
  USDWrapperFromDeviceList = GetUSDWrapperFromDeviceList(v17, SubKey);
  *(_QWORD *)SubKey = &CSimpleStringBase<unsigned short>::`vftable';
  CSimpleStringBase<unsigned short>::DeleteStorage(SubKey);
  v42 = 0;
  if ( USDWrapperFromDeviceList )
  {
    hKey = (HKEY)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)USDWrapperFromDeviceList + 504LL))(USDWrapperFromDeviceList);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)USDWrapperFromDeviceList + 16LL))(USDWrapperFromDeviceList);
  }
  if ( hKey )
    goto LABEL_15;
  GlobalEventsKey = -2147418113;
LABEL_14:
  if ( GlobalEventsKey >= 0 )
  {
LABEL_15:
    memset_0(SubKey, 0, 0x208u);
    if ( v10 )
    {
      v19 = StringCchPrintfW(SubKey, 0x104u, L"%s", *((_QWORD *)&off_1800797C0 + 2 * (int)i + 1));
    }
    else
    {
      if ( !(unsigned int)ActionGuidExists(a2, a3) )
      {
        v28 = (char *)WiaTrace_TraceLog("Trying to register an application for a event not supported by the device");
        WriteDbgTraceErrorWI("CEventNotifier::AddEventGUID", v28);
        WiaTrcLib::Free((WiaTrcLib *)v28, v29);
        v14 = (void *)WiaTrace_Trace("Trying to register an application for a event not supported by the device");
LABEL_30:
        WiaTrace_ProcessTrace_Ex(v16, v15, (int)"CEventNotifier::AddEventGUID", 1, v14);
        GlobalEventsKey = -2147024809;
        goto LABEL_31;
      }
      cSubKeys = 0;
      v20 = (char *)WiaTrace_TraceLogWithSubComp(0, "Event GUID was not found in key enumeration, creating one ...");
      WriteDbgTraceWarningWI("CEventNotifier::AddEventGUID", v20);
      WiaTrcLib::Free((WiaTrcLib *)v20, v21);
      v22 = (void *)WiaTrace_TraceWithSubComp(0, "Event GUID was not found in key enumeration, creating one ...");
      WiaTrace_ProcessTrace_Ex(v24, v23, (int)"CEventNotifier::AddEventGUID", 2, v22);
      RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
      LODWORD(lpcSubKeys) = cSubKeys;
      v19 = StringCchPrintfW(SubKey, 0x104u, L"%ws_%d", L"Event", lpcSubKeys);
    }
    GlobalEventsKey = v19;
    if ( v19 >= 0 )
    {
      cSubKeys = 0;
      v25 = RegCreateKeyExW(hKey, SubKey, 0, 0, 0, 0x2001Fu, 0, &phkResult, &cSubKeys);
      GlobalEventsKey = v25;
      if ( v25 )
      {
        if ( v25 > 0 )
          GlobalEventsKey = (unsigned __int16)v25 | 0x80070000;
      }
      else
      {
        lpsz = 0;
        GlobalEventsKey = StringFromCLSID(a3, &lpsz);
        if ( !GlobalEventsKey )
        {
          v26 = lstrlenW(lpsz);
          v27 = RegSetValueExW(phkResult, L"GUID", 0, 1u, (const BYTE *)lpsz, 2 * v26 + 2);
          GlobalEventsKey = v27;
          if ( v27 )
          {
            if ( v27 > 0 )
              GlobalEventsKey = (unsigned __int16)v27 | 0x80070000;
          }
          else
          {
            GlobalEventsKey = 0;
            *a4 = phkResult;
          }
          CoTaskMemFree(lpsz);
        }
      }
    }
  }
LABEL_31:
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( GlobalEventsKey < 0 )
  {
    v30 = (char *)WiaTrace_TraceLog("Returning failure hr = %#x");
    WriteDbgTraceErrorWI("CEventNotifier::AddEventGUID", v30);
    WiaTrcLib::Free((WiaTrcLib *)v30, v31);
    v32 = (void *)WiaTrace_Trace("Returning failure hr = %#x", GlobalEventsKey);
    WiaTrace_ProcessTrace_Ex(v34, v33, (int)"CEventNotifier::AddEventGUID", 1, v32);
    if ( phkResult )
      RegCloseKey(phkResult);
  }
  return (unsigned int)GlobalEventsKey;
}

```

## disassembly

```asm
0x18002e1ac  mov     [rsp-8+arg_0], rbx
0x18002e1b1  push    rbp
0x18002e1b2  push    rsi
0x18002e1b3  push    rdi
0x18002e1b4  push    r12
0x18002e1b6  push    r13
0x18002e1b8  push    r14
0x18002e1ba  push    r15
0x18002e1bc  lea     rbp, [rsp-1A0h]
0x18002e1c4  sub     rsp, 2A0h
0x18002e1cb  mov     rax, cs:__security_cookie
0x18002e1d2  xor     rax, rsp
0x18002e1d5  mov     [rbp+1D0h+var_40], rax
0x18002e1dc  xor     r13d, r13d
0x18002e1df  lea     rcx, off_1800797C0
0x18002e1e6  mov     [rsp+2D0h+hKey], r13
0x18002e1eb  mov     r12, r9
0x18002e1ee  mov     [rsp+2D0h+phkResult], r13
0x18002e1f3  mov     rsi, r8
0x18002e1f6  mov     r14, rdx
0x18002e1f9  test    rdx, rdx
0x18002e1fc  jnz     short loc_18002E279
0x18002e1fe  mov     ebx, r13d
0x18002e201  cmp     ebx, 19h
0x18002e204  jnb     short loc_18002E247
0x18002e206  movsxd  rax, ebx
0x18002e209  add     rax, rax
0x18002e20c  mov     rcx, [rcx+rax*8]
0x18002e210  mov     rax, [rcx]
0x18002e213  sub     rax, [r8]
0x18002e216  jnz     short loc_18002E220
0x18002e218  mov     rax, [rcx+8]
0x18002e21c  sub     rax, [r8+8]
0x18002e220  test    rax, rax
0x18002e223  jz      short loc_18002E230
0x18002e225  inc     ebx
0x18002e227  lea     rcx, off_1800797C0
0x18002e22e  jmp     short loc_18002E201
0x18002e230  lea     rcx, [rsp+2D0h+hKey]; phkResult
0x18002e235  mov     r15d, 1
0x18002e23b  call    ?GetGlobalEventsKey@CEventNotifier@@SAJPEAPEAUHKEY__@@@Z; CEventNotifier::GetGlobalEventsKey(HKEY__ * *)
0x18002e240  mov     edi, eax
0x18002e242  jmp     loc_18002E2E6
0x18002e247  lea     rcx, aTryingToRegist_0; "Trying to register application for a un"...
0x18002e24e  call    WiaTrace_TraceLog
0x18002e253  mov     rdx, rax; char *
0x18002e256  lea     rcx, aCeventnotifier_2; "CEventNotifier::AddEventGUID"
0x18002e25d  mov     rbx, rax
0x18002e260  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18002e265  mov     rcx, rbx; this
0x18002e268  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18002e26d  lea     rcx, aTryingToRegist_0; "Trying to register application for a un"...
0x18002e274  jmp     loc_18002E509
0x18002e279  lea     rcx, [rbp+1D0h+SubKey]
0x18002e27d  mov     r15d, r13d
0x18002e280  or      ebx, 0FFFFFFFFh
0x18002e283  call    ??0?$CSimpleStringBase@G@@QEAA@PEBG@Z; CSimpleStringBase<ushort>::CSimpleStringBase<ushort>(ushort const *)
0x18002e288  lea     rdx, [rbp+1D0h+SubKey]
0x18002e28c  call    ?GetUSDWrapperFromDeviceList@@YAPEAVUSDWrapper@@JAEBV?$CSimpleStringBase@G@@@Z; GetUSDWrapperFromDeviceList(long,CSimpleStringBase<ushort> const &)
0x18002e291  mov     rdi, rax
0x18002e294  lea     rcx, [rbp+1D0h+SubKey]
0x18002e298  lea     rax, ??_7?$CSimpleStringBase@G@@6B@; const CSimpleStringBase<ushort>::`vftable'
0x18002e29f  mov     qword ptr [rbp+1D0h+SubKey], rax
0x18002e2a3  call    ?DeleteStorage@?$CSimpleStringBase@G@@AEAAXXZ; CSimpleStringBase<ushort>::DeleteStorage(void)
0x18002e2a8  mov     [rbp+1D0h+var_140], r13
0x18002e2af  test    rdi, rdi
0x18002e2b2  jz      short loc_18002E2DA
0x18002e2b4  mov     rcx, [rdi]
0x18002e2b7  mov     rax, [rcx+1F8h]
0x18002e2be  mov     rcx, rdi
0x18002e2c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e2c6  mov     [rsp+2D0h+hKey], rax
0x18002e2cb  mov     rcx, rdi
0x18002e2ce  mov     rax, [rdi]
0x18002e2d1  mov     rax, [rax+10h]
0x18002e2d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e2da  cmp     [rsp+2D0h+hKey], r13
0x18002e2df  jnz     short loc_18002E2EE
0x18002e2e1  mov     edi, 8000FFFFh
0x18002e2e6  test    edi, edi
0x18002e2e8  js      loc_18002E52A
0x18002e2ee  xor     edx, edx; Val
0x18002e2f0  lea     rcx, [rbp+1D0h+SubKey]; void *
0x18002e2f4  mov     r8d, 208h; Size
0x18002e2fa  call    memset_0
0x18002e2ff  test    r15d, r15d
0x18002e302  jz      short loc_18002E330
0x18002e304  lea     rax, off_1800797C0
0x18002e30b  movsxd  r9, ebx
0x18002e30e  add     r9, r9
0x18002e311  lea     r8, aS_2; "%s"
0x18002e318  mov     edx, 104h; unsigned __int64
0x18002e31d  lea     rcx, [rbp+1D0h+SubKey]; unsigned __int16 *
0x18002e321  mov     r9, [rax+r9*8+8]
0x18002e326  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002e32b  jmp     loc_18002E3F9
0x18002e330  mov     rdx, rsi; struct _GUID *
0x18002e333  mov     rcx, r14; unsigned __int16 *
0x18002e336  call    ?ActionGuidExists@@YAHPEAGPEBU_GUID@@@Z; ActionGuidExists(ushort *,_GUID const *)
0x18002e33b  test    eax, eax
0x18002e33d  jz      loc_18002E4DC
0x18002e343  lea     rdx, aEventGuidWasNo; "Event GUID was not found in key enumera"...
0x18002e34a  mov     [rsp+2D0h+cSubKeys], r13d
0x18002e34f  xor     ecx, ecx
0x18002e351  call    WiaTrace_TraceLogWithSubComp
0x18002e356  mov     rdx, rax; char *
0x18002e359  lea     rcx, aCeventnotifier_2; "CEventNotifier::AddEventGUID"
0x18002e360  mov     rbx, rax
0x18002e363  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x18002e368  mov     rcx, rbx; this
0x18002e36b  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18002e370  lea     rdx, aEventGuidWasNo; "Event GUID was not found in key enumera"...
0x18002e377  xor     ecx, ecx
0x18002e379  call    WiaTrace_TraceWithSubComp
0x18002e37e  mov     r9d, 2; int
0x18002e384  mov     [rsp+2D0h+lpcSubKeys], rax; lpMem
0x18002e389  lea     r8, aCeventnotifier_2; "CEventNotifier::AddEventGUID"
0x18002e390  call    WiaTrace_ProcessTrace_Ex
0x18002e395  mov     rcx, [rsp+2D0h+hKey]; hKey
0x18002e39a  lea     rax, [rsp+2D0h+cSubKeys]
0x18002e39f  mov     [rsp+2D0h+lpftLastWriteTime], r13; lpftLastWriteTime
0x18002e3a4  xor     r9d, r9d; lpReserved
0x18002e3a7  mov     [rsp+2D0h+lpcbSecurityDescriptor], r13; lpcbSecurityDescriptor
0x18002e3ac  xor     r8d, r8d; lpcchClass
0x18002e3af  mov     [rsp+2D0h+lpcbMaxValueLen], r13; lpcbMaxValueLen
0x18002e3b4  xor     edx, edx; lpClass
0x18002e3b6  mov     [rsp+2D0h+lpcbMaxValueNameLen], r13; lpcbMaxValueNameLen
0x18002e3bb  mov     [rsp+2D0h+lpcValues], r13; lpcValues
0x18002e3c0  mov     [rsp+2D0h+lpcbMaxClassLen], r13; lpcbMaxClassLen
0x18002e3c5  mov     [rsp+2D0h+lpcbMaxSubKeyLen], r13; lpcbMaxSubKeyLen
0x18002e3ca  mov     [rsp+2D0h+lpcSubKeys], rax; lpcSubKeys
0x18002e3cf  call    cs:__imp_RegQueryInfoKeyW
0x18002e3d5  mov     eax, [rsp+2D0h+cSubKeys]
0x18002e3d9  lea     r9, aEvent; "Event"
0x18002e3e0  lea     r8, aWsD; "%ws_%d"
0x18002e3e7  mov     dword ptr [rsp+2D0h+lpcSubKeys], eax
0x18002e3eb  mov     edx, 104h; unsigned __int64
0x18002e3f0  lea     rcx, [rbp+1D0h+SubKey]; unsigned __int16 *
0x18002e3f4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002e3f9  mov     edi, eax
0x18002e3fb  test    eax, eax
0x18002e3fd  js      loc_18002E52A
0x18002e403  mov     rcx, [rsp+2D0h+hKey]; hKey
0x18002e408  lea     rax, [rsp+2D0h+cSubKeys]
0x18002e40d  mov     [rsp+2D0h+lpcbMaxValueNameLen], rax; lpdwDisposition
0x18002e412  lea     rdx, [rbp+1D0h+SubKey]; lpSubKey
0x18002e416  lea     rax, [rsp+2D0h+phkResult]
0x18002e41b  mov     [rsp+2D0h+cSubKeys], r13d
0x18002e420  mov     [rsp+2D0h+lpcValues], rax; phkResult
0x18002e425  xor     r9d, r9d; lpClass
0x18002e428  mov     [rsp+2D0h+lpcbMaxClassLen], r13; lpSecurityAttributes
0x18002e42d  xor     r8d, r8d; Reserved
0x18002e430  mov     dword ptr [rsp+2D0h+lpcbMaxSubKeyLen], 2001Fh; samDesired
0x18002e438  mov     dword ptr [rsp+2D0h+lpcSubKeys], r13d; dwOptions
0x18002e43d  call    cs:__imp_RegCreateKeyExW
0x18002e443  mov     edi, eax
0x18002e445  test    eax, eax
0x18002e447  jnz     loc_18002E4CF
0x18002e44d  lea     rdx, [rsp+2D0h+lpsz]; lplpsz
0x18002e452  mov     [rsp+2D0h+lpsz], r13
0x18002e457  mov     rcx, rsi; rclsid
0x18002e45a  call    cs:__imp_StringFromCLSID
0x18002e460  mov     edi, eax
0x18002e462  test    eax, eax
0x18002e464  jnz     loc_18002E52A
0x18002e46a  mov     rcx, [rsp+2D0h+lpsz]; lpString
0x18002e46f  call    cs:__imp_lstrlenW
0x18002e475  mov     rdx, [rsp+2D0h+lpsz]
0x18002e47a  lea     r9d, [rdi+1]; dwType
0x18002e47e  mov     rcx, [rsp+2D0h+phkResult]; hKey
0x18002e483  xor     r8d, r8d; Reserved
0x18002e486  lea     eax, ds:2[rax*2]
0x18002e48d  mov     dword ptr [rsp+2D0h+lpcbMaxSubKeyLen], eax; cbData
0x18002e491  mov     [rsp+2D0h+lpcSubKeys], rdx; lpData
0x18002e496  lea     rdx, aGuid_0; "GUID"
0x18002e49d  call    cs:__imp_RegSetValueExW
0x18002e4a3  mov     edi, eax
0x18002e4a5  test    eax, eax
0x18002e4a7  jnz     short loc_18002E4B7
0x18002e4a9  mov     rax, [rsp+2D0h+phkResult]
0x18002e4ae  mov     edi, r13d
0x18002e4b1  mov     [r12], rax
0x18002e4b5  jmp     short loc_18002E4C2
0x18002e4b7  jle     short loc_18002E4C2
0x18002e4b9  movzx   edi, ax
0x18002e4bc  or      edi, 80070000h
0x18002e4c2  mov     rcx, [rsp+2D0h+lpsz]; pv
0x18002e4c7  call    cs:__imp_CoTaskMemFree
0x18002e4cd  jmp     short loc_18002E52A
0x18002e4cf  jle     short loc_18002E52A
0x18002e4d1  movzx   edi, ax
0x18002e4d4  or      edi, 80070000h
0x18002e4da  jmp     short loc_18002E52A
0x18002e4dc  lea     rcx, aTryingToRegist; "Trying to register an application for a"...
0x18002e4e3  call    WiaTrace_TraceLog
0x18002e4e8  mov     rdx, rax; char *
0x18002e4eb  lea     rcx, aCeventnotifier_2; "CEventNotifier::AddEventGUID"
0x18002e4f2  mov     rbx, rax
0x18002e4f5  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18002e4fa  mov     rcx, rbx; this
0x18002e4fd  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18002e502  lea     rcx, aTryingToRegist; "Trying to register an application for a"...
0x18002e509  call    WiaTrace_Trace
0x18002e50e  mov     r9d, 1; int
0x18002e514  mov     [rsp+2D0h+lpcSubKeys], rax; lpMem
0x18002e519  lea     r8, aCeventnotifier_2; "CEventNotifier::AddEventGUID"
0x18002e520  call    WiaTrace_ProcessTrace_Ex
0x18002e525  mov     edi, 80070057h
0x18002e52a  mov     rcx, [rsp+2D0h+hKey]; hKey
0x18002e52f  test    rcx, rcx
0x18002e532  jz      short loc_18002E53F
0x18002e534  call    cs:__imp_RegCloseKey
0x18002e53a  mov     [rsp+2D0h+hKey], r13
0x18002e53f  test    edi, edi
0x18002e541  jns     short loc_18002E5A0
0x18002e543  mov     edx, edi
0x18002e545  lea     rcx, aReturningFailu; "Returning failure hr = %#x"
0x18002e54c  call    WiaTrace_TraceLog
0x18002e551  mov     rdx, rax; char *
0x18002e554  lea     rcx, aCeventnotifier_2; "CEventNotifier::AddEventGUID"
0x18002e55b  mov     rbx, rax
0x18002e55e  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18002e563  mov     rcx, rbx; this
0x18002e566  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18002e56b  mov     edx, edi
0x18002e56d  lea     rcx, aReturningFailu; "Returning failure hr = %#x"
0x18002e574  call    WiaTrace_Trace
0x18002e579  mov     r9d, 1; int
0x18002e57f  mov     [rsp+2D0h+lpcSubKeys], rax; lpMem
0x18002e584  lea     r8, aCeventnotifier_2; "CEventNotifier::AddEventGUID"
0x18002e58b  call    WiaTrace_ProcessTrace_Ex
0x18002e590  mov     rcx, [rsp+2D0h+phkResult]; hKey
0x18002e595  test    rcx, rcx
0x18002e598  jz      short loc_18002E5A0
0x18002e59a  call    cs:__imp_RegCloseKey
0x18002e5a0  mov     eax, edi
0x18002e5a2  mov     rcx, [rbp+1D0h+var_40]
0x18002e5a9  xor     rcx, rsp; StackCookie
0x18002e5ac  call    __security_check_cookie
0x18002e5b1  mov     rbx, [rsp+2D0h+arg_0]
0x18002e5b9  add     rsp, 2A0h
0x18002e5c0  pop     r15
0x18002e5c2  pop     r14
0x18002e5c4  pop     r13
0x18002e5c6  pop     r12
0x18002e5c8  pop     rdi
0x18002e5c9  pop     rsi
0x18002e5ca  pop     rbp
0x18002e5cb  retn
```
