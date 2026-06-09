# wWinMain

- ea: `0x14000ccb8`
- end: `0x14000d24d`
- name: `wWinMain`
- size: `1429`
- prototype: `int __stdcall(HINSTANCE hInstance, HINSTANCE hPrevInstance, LPWSTR lpCmdLine, int nShowCmd)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x1400011e0`

## callees

- `0x140001008`
- `0x140001390`
- `0x1400099e0`
- `0x14000a4e4`
- `0x14000a828`
- `0x14000a9ec`
- `0x14000aae0`
- `0x14000b004`
- `0x14000c860`
- `0x14000c9bc`
- `0x14000ccb8`
- `0x14000e3d4`
- `0x14000f010`

## import_xrefs

- `ADVAPI32!UnregisterTraceGuids` at `0x14000d07b`
- `ADVAPI32!UnregisterTraceGuids` at `0x14000d07b`
- `KERNEL32!GetCommandLineW` at `0x14000ccde`
- `KERNEL32!GetCommandLineW` at `0x14000ccde`
- `KERNEL32!CreateEventW` at `0x14000cdb9`
- `KERNEL32!CreateEventW` at `0x14000cdb9`
- `KERNEL32!Sleep` at `0x14000d0d2`
- `KERNEL32!Sleep` at `0x14000d0d2`
- `KERNEL32!CreateThread` at `0x14000cdeb`
- `KERNEL32!CreateThread` at `0x14000cdeb`
- `KERNEL32!HeapDestroy` at `0x14000d205`
- `KERNEL32!HeapDestroy` at `0x14000d223`
- `KERNEL32!HeapDestroy` at `0x14000d205`
- `KERNEL32!HeapDestroy` at `0x14000d223`
- `KERNEL32!DeleteCriticalSection` at `0x14000d157`
- `KERNEL32!DeleteCriticalSection` at `0x14000d17b`
- `KERNEL32!DeleteCriticalSection` at `0x14000d19f`
- `KERNEL32!DeleteCriticalSection` at `0x14000d157`
- `KERNEL32!DeleteCriticalSection` at `0x14000d17b`
- `KERNEL32!DeleteCriticalSection` at `0x14000d19f`
- `KERNEL32!lstrcmpiW` at `0x14000cd76`
- `KERNEL32!lstrcmpiW` at `0x14000cd8e`
- `KERNEL32!lstrcmpiW` at `0x14000cd76`
- `KERNEL32!lstrcmpiW` at `0x14000cd8e`
- `KERNEL32!GetCurrentThreadId` at `0x14000cd3c`
- `KERNEL32!GetCurrentThreadId` at `0x14000cd3c`
- `USER32!DispatchMessageW` at `0x14000d01d`
- `USER32!DispatchMessageW` at `0x14000d01d`
- `USER32!GetMessageW` at `0x14000d02f`
- `USER32!GetMessageW` at `0x14000d02f`
- `ole32!CoInitialize` at `0x14000cce9`
- `ole32!CoInitialize` at `0x14000cce9`
- `ole32!CoUninitialize` at `0x14000d229`
- `ole32!CoUninitialize` at `0x14000d229`
- `ole32!CoRegisterClassObject` at `0x14000cf93`
- `ole32!CoRegisterClassObject` at `0x14000cf93`
- `ole32!CoRevokeClassObject` at `0x14000d0ac`
- `ole32!CoRevokeClassObject` at `0x14000d0ac`

## pseudocode

```c
int __stdcall wWinMain(HINSTANCE hInstance, HINSTANCE hPrevInstance, LPWSTR lpCmdLine, int nShowCmd)
{
  LPWSTR CommandLineW; // rdi
  struct ATL::_ATL_OBJMAP_ENTRY *v6; // rdx
  const WCHAR *v7; // rcx
  unsigned int v8; // edx
  ATL::CComModule *v9; // rcx
  struct ATL::_ATL_REGMAP_ENTRY *v10; // r9
  unsigned int v11; // edx
  ATL::CComModule *v12; // rcx
  struct ATL::_ATL_REGMAP_ENTRY *v13; // r9
  const WCHAR *OneOf; // rax
  const WCHAR *v15; // rbx
  int v16; // esi
  __int64 v17; // rbx
  HRESULT v18; // edi
  const unsigned __int16 *v19; // rdx
  __int64 v20; // rbx
  __int64 (*v21)(void); // rax
  int v22; // eax
  const struct ATL::_ATL_CATMAP_ENTRY *v23; // rax
  const unsigned __int16 *v24; // rdx
  __int64 v25; // rbx
  __int64 (*v26)(void); // rax
  __int64 (*v27)(void); // rax
  const struct ATL::_ATL_CATMAP_ENTRY *v28; // rax
  __int64 (__fastcall *v29)(_QWORD, GUID *, DWORD *); // rax
  _UNKNOWN **v30; // rbx
  TRACEHANDLE v31; // rcx
  __int64 v32; // rbx
  HRESULT v33; // eax
  _QWORD *v34; // rbx
  __int64 v35; // rcx
  void (__fastcall *v36)(_QWORD); // rax
  _QWORD *v37; // rdi
  _QWORD *v38; // rbx
  HANDLE v39; // rcx
  __int64 v40; // rdx
  unsigned int v41; // ebx
  void *v42; // rcx
  DWORD ThreadId[2]; // [rsp+30h] [rbp-29h] BYREF
  MSG Msg; // [rsp+38h] [rbp-21h] BYREF
  wchar_t v46[4]; // [rsp+68h] [rbp+Fh] BYREF

  CommandLineW = GetCommandLineW();
  CoInitialize(0);
  _Module = 248;
  ATL::_pModule = (struct ATL::CComModule *)&_Module;
  qword_140015478 = (__int64)&ATL::GUID_ATLVer30;
  dword_140015460 = 769;
  if ( (int)ATL::AtlModuleInit((struct ATL::_ATL_MODULE *)&_Module, v6, hInstance) >= 0 )
    dword_1400154A0 = 1;
  dword_1400154A8 = GetCurrentThreadId();
  v7 = CommandLineW;
  wcscpy(v46, L"-/");
  *(_OWORD *)&hEvent = 0;
  while ( 1 )
  {
    OneOf = FindOneOf(v7, v46);
    v15 = OneOf;
    if ( !OneOf )
    {
      v16 = 0;
      hEvent = CreateEventW(0, 0, 0, 0);
      if ( hEvent )
      {
        ThreadId[0] = 0;
        *(&hEvent + 1) = CreateThread(0, 0, MonitorProc, &_Module, 0, ThreadId);
      }
      v17 = qword_1400153D0;
      if ( qword_1400153D0 )
      {
        v18 = 0;
        while ( *(_QWORD *)v17 && !v18 )
        {
          v29 = *(__int64 (__fastcall **)(_QWORD, GUID *, DWORD *))(v17 + 16);
          *(_QWORD *)ThreadId = 0;
          if ( v29 )
          {
            v18 = v29(*(_QWORD *)(v17 + 24), &IID_IUnknown, ThreadId);
            if ( v18 >= 0 )
              v18 = CoRegisterClassObject(*(const IID *const *)v17, *(LPUNKNOWN *)ThreadId, 4u, 2u, (LPDWORD)(v17 + 40));
            if ( *(_QWORD *)ThreadId )
              (*(void (__fastcall **)(_QWORD))(**(_QWORD **)ThreadId + 16LL))(*(_QWORD *)ThreadId);
          }
          else
          {
            v18 = 0;
          }
          if ( _Module == 176 )
            v17 += 56;
          else
            v17 += 72;
        }
      }
      WMP_SetupTracing();
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 7u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_9d7a0a9d9880359b431ba27d6bc46ee1_Traceguids);
      }
      memset(&Msg, 0, sizeof(Msg));
      while ( GetMessageW(&Msg, 0, 0, 0) )
        DispatchMessageW(&Msg);
      v30 = (_UNKNOWN **)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 7u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_9d7a0a9d9880359b431ba27d6bc46ee1_Traceguids);
          v30 = (_UNKNOWN **)WPP_GLOBAL_Control;
        }
        if ( v30 != &WPP_GLOBAL_Control )
        {
          while ( v30 )
          {
            v31 = (TRACEHANDLE)v30[1];
            if ( v31 )
            {
              UnregisterTraceGuids(v31);
              v30[1] = 0;
            }
            v30 = (_UNKNOWN **)*v30;
          }
          WPP_GLOBAL_Control = &WPP_GLOBAL_Control;
        }
      }
      v32 = qword_1400153D0;
      if ( qword_1400153D0 )
      {
        v33 = 0;
        while ( *(_QWORD *)v32 && !v33 )
        {
          v33 = CoRevokeClassObject(*(_DWORD *)(v32 + 40));
          if ( _Module == 176 )
            v32 += 56;
          else
            v32 += 72;
        }
      }
      Sleep(0x3E8u);
      goto LABEL_75;
    }
    if ( !lstrcmpiW(OneOf, L"UnregServer") )
      break;
    if ( !lstrcmpiW(v15, L"RegServer") )
    {
      ATL::CComModule::UpdateRegistryFromResourceS(v12, v11, 1, v13);
      v20 = qword_1400153D0;
      v16 = 0;
      if ( !qword_1400153D0 )
        goto LABEL_75;
      if ( !*(_QWORD *)qword_1400153D0 )
      {
LABEL_24:
        v16 = ATL::AtlModuleRegisterTypeLib((struct ATL::_ATL_MODULE *)&_Module, v19);
        goto LABEL_75;
      }
      while ( 2 )
      {
        v21 = *(__int64 (**)(void))(v20 + 48);
        if ( v21 && v21() )
        {
LABEL_19:
          v22 = _Module;
        }
        else
        {
          v16 = (*(__int64 (__fastcall **)(__int64))(v20 + 8))(1);
          if ( v16 < 0 )
            goto LABEL_75;
          v22 = _Module;
          if ( _Module == 248 )
          {
            v23 = (const struct ATL::_ATL_CATMAP_ENTRY *)(*(__int64 (**)(void))(v20 + 56))();
            v16 = ATL::AtlRegisterClassCategoriesHelper(*(const struct _GUID **)v20, v23, 1);
            if ( v16 < 0 )
              goto LABEL_75;
            goto LABEL_19;
          }
        }
        if ( v22 == 176 )
          v20 += 56;
        else
          v20 += 72;
        if ( !*(_QWORD *)v20 )
          goto LABEL_24;
        continue;
      }
    }
    v7 = v15;
  }
  ATL::CComModule::UpdateRegistryFromResourceS(v9, v8, 0, v10);
  v25 = qword_1400153D0;
  if ( !qword_1400153D0 )
    goto LABEL_37;
  while ( *(_QWORD *)v25 )
  {
    v26 = *(__int64 (**)(void))(v25 + 48);
    if ( !v26 || !v26() )
    {
      (*(void (__fastcall **)(_QWORD))(v25 + 8))(0);
      if ( _Module == 248 )
      {
        v27 = *(__int64 (**)(void))(v25 + 56);
        if ( !v27 )
          goto LABEL_34;
        v28 = (const struct ATL::_ATL_CATMAP_ENTRY *)v27();
        ATL::AtlRegisterClassCategoriesHelper(*(const struct _GUID **)v25, v28, 0);
      }
    }
    if ( _Module == 176 )
      v25 += 56;
    else
LABEL_34:
      v25 += 72;
  }
  ATL::AtlModuleUnRegisterTypeLib((struct ATL::_ATL_MODULE *)&_Module, v24);
LABEL_37:
  v16 = 0;
LABEL_75:
  v34 = (_QWORD *)qword_1400153D0;
  if ( qword_1400153D0 )
  {
    while ( *v34 )
    {
      v35 = v34[4];
      if ( v35 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
      v36 = (void (__fastcall *)(_QWORD))v34[8];
      v34[4] = 0;
      v36(0);
      if ( _Module == 176 )
        v34 += 7;
      else
        v34 += 9;
    }
  }
  memset(&Msg, 0, 40);
  if ( memcmp_0(&Buf1, &Msg, 0x28u) )
    DeleteCriticalSection(&Buf1);
  if ( memcmp_0(&CriticalSection, &Msg, 0x28u) )
    DeleteCriticalSection(&CriticalSection);
  if ( memcmp_0(&stru_140015438, &Msg, 0x28u) )
    DeleteCriticalSection(&stru_140015438);
  v37 = qword_140015498;
  if ( qword_140015498 )
  {
    do
    {
      ((void (__fastcall *)(_QWORD))*v37)(v37[1]);
      v38 = (_QWORD *)v37[2];
      operator delete(v37, 0x18u);
      v37 = v38;
    }
    while ( v38 );
  }
  v39 = hHeap;
  if ( hHeap && byte_140015470 )
  {
    v40 = qword_140015488;
    if ( qword_140015488 )
    {
      v41 = 0;
      do
      {
        v42 = *(void **)(v40 + 8LL * v41);
        if ( v42 )
        {
          HeapDestroy(v42);
          v40 = qword_140015488;
        }
        ++v41;
      }
      while ( v41 <= dword_140015480 );
      v39 = hHeap;
    }
    HeapDestroy(v39);
  }
  CoUninitialize();
  return v16;
}

```

## disassembly

```asm
0x14000ccb8  push    rbp
0x14000ccba  push    rbx
0x14000ccbb  push    rsi
0x14000ccbc  push    rdi
0x14000ccbd  push    r12
0x14000ccbf  push    r15
0x14000ccc1  lea     rbp, [rsp-2Fh]
0x14000ccc6  sub     rsp, 88h
0x14000cccd  mov     rax, cs:__security_cookie
0x14000ccd4  xor     rax, rsp
0x14000ccd7  mov     [rbp+57h+var_40], rax
0x14000ccdb  mov     rbx, rcx
0x14000ccde  call    cs:__imp_GetCommandLineW
0x14000cce4  xor     ecx, ecx; pvReserved
0x14000cce6  mov     rdi, rax
0x14000cce9  call    cs:__imp_CoInitialize
0x14000ccef  lea     r12, ?_Module@@3VCExeModule@@A; CExeModule _Module
0x14000ccf6  mov     cs:?_Module@@3VCExeModule@@A, 0F8h; CExeModule _Module
0x14000cd00  lea     rax, ?GUID_ATLVer30@ATL@@3U_GUID@@A; _GUID ATL::GUID_ATLVer30
0x14000cd07  mov     cs:?_pModule@ATL@@3PEAVCComModule@1@EA, r12; ATL::CComModule * ATL::_pModule
0x14000cd0e  mov     rcx, r12; struct ATL::_ATL_MODULE *
0x14000cd11  mov     cs:qword_140015478, rax
0x14000cd18  mov     r8, rbx; HINSTANCE
0x14000cd1b  mov     cs:dword_140015460, 301h
0x14000cd25  call    ?AtlModuleInit@ATL@@YAJPEAU_ATL_MODULE@1@PEAU_ATL_OBJMAP_ENTRY@1@PEAUHINSTANCE__@@@Z; ATL::AtlModuleInit(ATL::_ATL_MODULE *,ATL::_ATL_OBJMAP_ENTRY *,HINSTANCE__ *)
0x14000cd2a  xor     r15d, r15d
0x14000cd2d  mov     esi, 1
0x14000cd32  test    eax, eax
0x14000cd34  js      short loc_14000CD3C
0x14000cd36  mov     cs:dword_1400154A0, esi
0x14000cd3c  call    cs:__imp_GetCurrentThreadId
0x14000cd42  mov     cs:dword_1400154A8, eax
0x14000cd48  xorps   xmm0, xmm0
0x14000cd4b  mov     eax, dword ptr cs:asc_140012214; "-/"
0x14000cd51  mov     rcx, rdi
0x14000cd54  mov     dword ptr [rbp+57h+var_48], eax
0x14000cd57  movzx   eax, word ptr cs:asc_140012214+4; ""
0x14000cd5e  mov     word ptr [rbp+57h+var_48+4], ax
0x14000cd62  movdqa  cs:hEvent, xmm0
0x14000cd6a  jmp     short loc_14000CD9B
0x14000cd6c  lea     rdx, aUnregserver; "UnregServer"
0x14000cd73  mov     rcx, rbx; lpString1
0x14000cd76  call    cs:__imp_lstrcmpiW
0x14000cd7c  test    eax, eax
0x14000cd7e  jz      loc_14000CEBE
0x14000cd84  lea     rdx, aRegserver; "RegServer"
0x14000cd8b  mov     rcx, rbx; lpString1
0x14000cd8e  call    cs:__imp_lstrcmpiW
0x14000cd94  test    eax, eax
0x14000cd96  jz      short loc_14000CE10
0x14000cd98  mov     rcx, rbx; lpsz
0x14000cd9b  lea     rdx, [rbp+57h+var_48]; LPCWSTR
0x14000cd9f  call    ?FindOneOf@@YAPEBGPEBG0@Z; FindOneOf(ushort const *,ushort const *)
0x14000cda4  mov     rbx, rax
0x14000cda7  test    rax, rax
0x14000cdaa  jnz     short loc_14000CD6C
0x14000cdac  xor     r9d, r9d; lpName
0x14000cdaf  xor     r8d, r8d; bInitialState
0x14000cdb2  xor     edx, edx; bManualReset
0x14000cdb4  xor     ecx, ecx; lpEventAttributes
0x14000cdb6  mov     esi, r15d
0x14000cdb9  call    cs:__imp_CreateEventW
0x14000cdbf  mov     qword ptr cs:hEvent, rax
0x14000cdc6  test    rax, rax
0x14000cdc9  jz      short loc_14000CDF8
0x14000cdcb  lea     rax, [rbp+57h+ThreadId]
0x14000cdcf  mov     [rbp+57h+ThreadId], r15d
0x14000cdd3  mov     [rsp+0B0h+lpThreadId], rax; lpThreadId
0x14000cdd8  lea     r8, MonitorProc; lpStartAddress
0x14000cddf  mov     r9, r12; lpParameter
0x14000cde2  mov     [rsp+0B0h+dwCreationFlags], r15d; dwCreationFlags
0x14000cde7  xor     edx, edx; dwStackSize
0x14000cde9  xor     ecx, ecx; lpThreadAttributes
0x14000cdeb  call    cs:__imp_CreateThread
0x14000cdf1  mov     qword ptr cs:hEvent+8, rax
0x14000cdf8  mov     rbx, cs:qword_1400153D0
0x14000cdff  test    rbx, rbx
0x14000ce02  jz      loc_14000CFCF
0x14000ce08  mov     edi, r15d
0x14000ce0b  jmp     loc_14000CFC6
0x14000ce10  mov     r8d, esi; int
0x14000ce13  call    ?UpdateRegistryFromResourceS@CComModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z; ATL::CComModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)
0x14000ce18  mov     rbx, cs:qword_1400153D0
0x14000ce1f  mov     esi, r15d
0x14000ce22  test    rbx, rbx
0x14000ce25  jz      loc_14000D0D8
0x14000ce2b  cmp     [rbx], r15
0x14000ce2e  jz      short loc_14000CEAF
0x14000ce30  mov     rax, [rbx+30h]
0x14000ce34  test    rax, rax
0x14000ce37  jz      short loc_14000CE43
0x14000ce39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ce3e  test    rax, rax
0x14000ce41  jnz     short loc_14000CE8B
0x14000ce43  mov     rax, [rbx+8]
0x14000ce47  mov     edi, 1
0x14000ce4c  mov     ecx, edi
0x14000ce4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ce53  mov     esi, eax
0x14000ce55  test    eax, eax
0x14000ce57  js      loc_14000D0D8
0x14000ce5d  mov     eax, cs:?_Module@@3VCExeModule@@A; CExeModule _Module
0x14000ce63  cmp     eax, 0F8h
0x14000ce68  jnz     short loc_14000CE91
0x14000ce6a  mov     rax, [rbx+38h]
0x14000ce6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ce73  mov     rcx, [rbx]; struct _GUID *
0x14000ce76  mov     r8d, edi; int
0x14000ce79  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x14000ce7c  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x14000ce81  mov     esi, eax
0x14000ce83  test    eax, eax
0x14000ce85  js      loc_14000D0D8
0x14000ce8b  mov     eax, cs:?_Module@@3VCExeModule@@A; CExeModule _Module
0x14000ce91  cmp     eax, 0B0h
0x14000ce96  jnz     short loc_14000CE9E
0x14000ce98  add     rbx, 38h ; '8'
0x14000ce9c  jmp     short loc_14000CEA2
0x14000ce9e  add     rbx, 48h ; 'H'
0x14000cea2  cmp     [rbx], r15
0x14000cea5  jnz     short loc_14000CE30
0x14000cea7  test    esi, esi
0x14000cea9  js      loc_14000D0D8
0x14000ceaf  mov     rcx, r12; struct ATL::_ATL_MODULE *
0x14000ceb2  call    ?AtlModuleRegisterTypeLib@ATL@@YAJPEAU_ATL_MODULE@1@PEBG@Z; ATL::AtlModuleRegisterTypeLib(ATL::_ATL_MODULE *,ushort const *)
0x14000ceb7  mov     esi, eax
0x14000ceb9  jmp     loc_14000D0D8
0x14000cebe  xor     r8d, r8d; int
0x14000cec1  call    ?UpdateRegistryFromResourceS@CComModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z; ATL::CComModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)
0x14000cec6  mov     rbx, cs:qword_1400153D0
0x14000cecd  test    rbx, rbx
0x14000ced0  jz      short loc_14000CF3D
0x14000ced2  jmp     short loc_14000CF30
0x14000ced4  mov     rax, [rbx+30h]
0x14000ced8  test    rax, rax
0x14000cedb  jz      short loc_14000CEE7
0x14000cedd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cee2  test    rax, rax
0x14000cee5  jnz     short loc_14000CF1A
0x14000cee7  mov     rax, [rbx+8]
0x14000ceeb  xor     ecx, ecx
0x14000ceed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cef2  cmp     cs:?_Module@@3VCExeModule@@A, 0F8h; CExeModule _Module
0x14000cefc  jnz     short loc_14000CF1A
0x14000cefe  mov     rax, [rbx+38h]
0x14000cf02  test    rax, rax
0x14000cf05  jz      short loc_14000CF2C
0x14000cf07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cf0c  mov     rcx, [rbx]; struct _GUID *
0x14000cf0f  xor     r8d, r8d; int
0x14000cf12  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x14000cf15  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x14000cf1a  cmp     cs:?_Module@@3VCExeModule@@A, 0B0h; CExeModule _Module
0x14000cf24  jnz     short loc_14000CF2C
0x14000cf26  add     rbx, 38h ; '8'
0x14000cf2a  jmp     short loc_14000CF30
0x14000cf2c  add     rbx, 48h ; 'H'
0x14000cf30  cmp     [rbx], r15
0x14000cf33  jnz     short loc_14000CED4
0x14000cf35  mov     rcx, r12; struct ATL::_ATL_MODULE *
0x14000cf38  call    ?AtlModuleUnRegisterTypeLib@ATL@@YAJPEAU_ATL_MODULE@1@PEBG@Z; ATL::AtlModuleUnRegisterTypeLib(ATL::_ATL_MODULE *,ushort const *)
0x14000cf3d  mov     esi, r15d
0x14000cf40  jmp     loc_14000D0D8
0x14000cf45  test    edi, edi
0x14000cf47  jnz     loc_14000CFCF
0x14000cf4d  mov     rax, [rbx+10h]
0x14000cf51  mov     qword ptr [rbp+57h+ThreadId], r15
0x14000cf55  test    rax, rax
0x14000cf58  jnz     short loc_14000CF5F
0x14000cf5a  mov     edi, r15d
0x14000cf5d  jmp     short loc_14000CFB0
0x14000cf5f  mov     rcx, [rbx+18h]
0x14000cf63  lea     r8, [rbp+57h+ThreadId]
0x14000cf67  lea     rdx, IID_IUnknown
0x14000cf6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cf73  mov     edi, eax
0x14000cf75  test    eax, eax
0x14000cf77  js      short loc_14000CF9B
0x14000cf79  mov     rdx, qword ptr [rbp+57h+ThreadId]; pUnk
0x14000cf7d  lea     rax, [rbx+28h]
0x14000cf81  mov     rcx, [rbx]; rclsid
0x14000cf84  mov     r9d, 2; flags
0x14000cf8a  mov     qword ptr [rsp+0B0h+dwCreationFlags], rax; lpdwRegister
0x14000cf8f  lea     r8d, [r9+2]; dwClsContext
0x14000cf93  call    cs:__imp_CoRegisterClassObject
0x14000cf99  mov     edi, eax
0x14000cf9b  mov     rcx, qword ptr [rbp+57h+ThreadId]
0x14000cf9f  test    rcx, rcx
0x14000cfa2  jz      short loc_14000CFB0
0x14000cfa4  mov     rax, [rcx]
0x14000cfa7  mov     rax, [rax+10h]
0x14000cfab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cfb0  cmp     cs:?_Module@@3VCExeModule@@A, 0B0h; CExeModule _Module
0x14000cfba  jnz     short loc_14000CFC2
0x14000cfbc  add     rbx, 38h ; '8'
0x14000cfc0  jmp     short loc_14000CFC6
0x14000cfc2  add     rbx, 48h ; 'H'
0x14000cfc6  cmp     [rbx], r15
0x14000cfc9  jnz     loc_14000CF45
0x14000cfcf  call    ?WMP_SetupTracing@@YAXXZ; WMP_SetupTracing(void)
0x14000cfd4  mov     rcx, cs:WPP_GLOBAL_Control
0x14000cfdb  lea     rdi, WPP_GLOBAL_Control
0x14000cfe2  cmp     rcx, rdi
0x14000cfe5  jz      short loc_14000D008
0x14000cfe7  test    byte ptr [rcx+1Ch], 1
0x14000cfeb  jz      short loc_14000D008
0x14000cfed  cmp     byte ptr [rcx+19h], 7
0x14000cff1  jb      short loc_14000D008
0x14000cff3  mov     rcx, [rcx+10h]
0x14000cff7  lea     r8, WPP_9d7a0a9d9880359b431ba27d6bc46ee1_Traceguids
0x14000cffe  mov     edx, 0Ah
0x14000d003  call    WPP_SF_
0x14000d008  xorps   xmm0, xmm0
0x14000d00b  movups  xmmword ptr [rbp+57h+Msg.hwnd], xmm0
0x14000d00f  movups  xmmword ptr [rbp+57h+Msg.wParam], xmm0
0x14000d013  movups  xmmword ptr [rbp+57h+Msg.time], xmm0
0x14000d017  jmp     short loc_14000D023
0x14000d019  lea     rcx, [rbp+57h+Msg]; lpMsg
0x14000d01d  call    cs:__imp_DispatchMessageW
0x14000d023  xor     r9d, r9d; wMsgFilterMax
0x14000d026  lea     rcx, [rbp+57h+Msg]; lpMsg
0x14000d02a  xor     r8d, r8d; wMsgFilterMin
0x14000d02d  xor     edx, edx; hWnd
0x14000d02f  call    cs:__imp_GetMessageW
0x14000d035  test    eax, eax
0x14000d037  jnz     short loc_14000D019
0x14000d039  mov     rbx, cs:WPP_GLOBAL_Control
0x14000d040  cmp     rbx, rdi
0x14000d043  jz      short loc_14000D094
0x14000d045  test    byte ptr [rbx+1Ch], 1
0x14000d049  jz      short loc_14000D06B
0x14000d04b  cmp     byte ptr [rbx+19h], 7
0x14000d04f  jb      short loc_14000D06B
0x14000d051  mov     rcx, [rbx+10h]
0x14000d055  lea     edx, [rax+0Bh]
0x14000d058  lea     r8, WPP_9d7a0a9d9880359b431ba27d6bc46ee1_Traceguids
0x14000d05f  call    WPP_SF_
0x14000d064  mov     rbx, cs:WPP_GLOBAL_Control
0x14000d06b  cmp     rbx, rdi
0x14000d06e  jz      short loc_14000D094
0x14000d070  jmp     short loc_14000D088
0x14000d072  mov     rcx, [rbx+8]; RegistrationHandle
0x14000d076  test    rcx, rcx
0x14000d079  jz      short loc_14000D085
0x14000d07b  call    cs:__imp_UnregisterTraceGuids
0x14000d081  mov     [rbx+8], r15
0x14000d085  mov     rbx, [rbx]
0x14000d088  test    rbx, rbx
0x14000d08b  jnz     short loc_14000D072
0x14000d08d  mov     cs:WPP_GLOBAL_Control, rdi
0x14000d094  mov     rbx, cs:qword_1400153D0
0x14000d09b  test    rbx, rbx
0x14000d09e  jz      short loc_14000D0CD
0x14000d0a0  mov     eax, r15d
0x14000d0a3  jmp     short loc_14000D0C8
0x14000d0a5  test    eax, eax
0x14000d0a7  jnz     short loc_14000D0CD
0x14000d0a9  mov     ecx, [rbx+28h]; dwRegister
0x14000d0ac  call    cs:__imp_CoRevokeClassObject
0x14000d0b2  cmp     cs:?_Module@@3VCExeModule@@A, 0B0h; CExeModule _Module
0x14000d0bc  jnz     short loc_14000D0C4
0x14000d0be  add     rbx, 38h ; '8'
0x14000d0c2  jmp     short loc_14000D0C8
0x14000d0c4  add     rbx, 48h ; 'H'
0x14000d0c8  cmp     [rbx], r15
0x14000d0cb  jnz     short loc_14000D0A5
0x14000d0cd  mov     ecx, 3E8h; dwMilliseconds
0x14000d0d2  call    cs:__imp_Sleep
0x14000d0d8  mov     rbx, cs:qword_1400153D0
0x14000d0df  test    rbx, rbx
0x14000d0e2  jz      short loc_14000D125
0x14000d0e4  jmp     short loc_14000D120
0x14000d0e6  mov     rcx, [rbx+20h]
0x14000d0ea  test    rcx, rcx
0x14000d0ed  jz      short loc_14000D0FB
0x14000d0ef  mov     rax, [rcx]
0x14000d0f2  mov     rax, [rax+10h]
0x14000d0f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d0fb  mov     rax, [rbx+40h]
0x14000d0ff  xor     ecx, ecx
0x14000d101  mov     [rbx+20h], r15
0x14000d105  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d10a  cmp     cs:?_Module@@3VCExeModule@@A, 0B0h; CExeModule _Module
0x14000d114  jnz     short loc_14000D11C
0x14000d116  add     rbx, 38h ; '8'
0x14000d11a  jmp     short loc_14000D120
0x14000d11c  add     rbx, 48h ; 'H'
0x14000d120  cmp     [rbx], r15
0x14000d123  jnz     short loc_14000D0E6
0x14000d125  xor     eax, eax
0x14000d127  lea     rdx, [rbp+57h+Msg]; Buf2
0x14000d12b  xorps   xmm0, xmm0
0x14000d12e  mov     qword ptr [rbp+57h+Msg.time], rax
0x14000d132  lea     rcx, Buf1; Buf1
0x14000d139  movups  xmmword ptr [rbp+57h+Msg.hwnd], xmm0
0x14000d13d  lea     ebx, [rax+28h]
0x14000d140  mov     r8d, ebx; Size
0x14000d143  movups  xmmword ptr [rbp+57h+Msg.wParam], xmm0
0x14000d147  call    memcmp_0
0x14000d14c  test    eax, eax
  ... truncated ...
```
