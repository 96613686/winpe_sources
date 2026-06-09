# CExtensionList::_Initialize(ushort const *,ushort const *)

- ea: `0x18007e23c`
- end: `0x18007e5f0`
- name: `?_Initialize@CExtensionList@@AEAAJPEBG0@Z`
- size: `948`
- prototype: `__int64 __fastcall(CExtensionList *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180078a24`

## callees

- `0x180003d24`
- `0x180016c98`
- `0x180022fb4`
- `0x180025bb4`
- `0x180026498`
- `0x18002b1b0`
- `0x1800568d4`
- `0x18005add0`
- `0x180075240`
- `0x180076fec`
- `0x180077ea0`
- `0x180078b08`
- `0x180078b94`
- `0x18007c870`
- `0x18007dcd0`
- `0x18007df6c`
- `0x18007e23c`
- `0x18007f500`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18007e4f5`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18007e4f5`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007e311`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007e36e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007e4b5`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007e311`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007e36e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007e4b5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007e2f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007e386`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007e4cd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007e2f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007e386`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007e4cd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007e5ba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007e5ba`

## string_xrefs

- `0x18007e4ea`: `__EXTENSION_POINTS_STATE_MUTEX__`
- `0x18007e2ef`: `Windows.Foundation.ExtensionCatalog`

## pseudocode

```c
__int64 __fastcall CExtensionList::_Initialize(
        struct _FILETIME *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  struct _FILETIME *v3; // r15
  int Instance; // ebx
  __int64 v6; // rbx
  __int64 (__fastcall *v7)(__int64, HSTRING, __int64 **); // rdi
  int v8; // ecx
  char *Reserved1; // rsi
  HSTRING v10; // r14
  __int64 v11; // rax
  __int64 *v12; // rdi
  int (__fastcall *v13)(__int64 *, UINT32 *); // rbx
  int v14; // eax
  _QWORD *v15; // rcx
  int v16; // ebx
  int v17; // ecx
  const unsigned __int16 *v18; // rcx
  const struct _GUID *v19; // r8
  unsigned __int64 v20; // rdi
  const struct _GUID *v21; // r8
  struct _FILETIME v22; // rdx
  _QWORD *v23; // rcx
  unsigned __int64 v24; // rdi
  char v26[8]; // [rsp+30h] [rbp-59h] BYREF
  UINT32 length[2]; // [rsp+38h] [rbp-51h] BYREF
  __int64 *v28; // [rsp+40h] [rbp-49h] BYREF
  struct IExtensionStateManager *v29; // [rsp+48h] [rbp-41h] BYREF
  __int64 v30; // [rsp+50h] [rbp-39h] BYREF
  HANDLE MutexW; // [rsp+58h] [rbp-31h] BYREF
  HSTRING v32; // [rsp+60h] [rbp-29h] BYREF
  HSTRING_HEADER v33; // [rsp+68h] [rbp-21h] BYREF
  HSTRING string; // [rsp+80h] [rbp-9h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+88h] [rbp-1h] BYREF

  v3 = this + 4;
  CTSimpleArray<Microsoft::WRL::ComPtr<IExtensionListItem>,4294967294,CTPolicyCoTaskMem<Microsoft::WRL::ComPtr<IExtensionListItem>>,CSimpleArrayStandardCompareHelper<Microsoft::WRL::ComPtr<IExtensionListItem>>,CSimpleArrayStandardMergeHelper<Microsoft::WRL::ComPtr<IExtensionListItem>>>::RemoveAll(
    &this[4],
    a2,
    a3);
  Instance = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
               &this[9],
               L"Windows.ShareTarget",
               -1);
  if ( Instance >= 0 )
  {
    Instance = CExtensionList::_GetLastExtensionCatalogWriteTime((CExtensionList *)this, this + 12);
    if ( Instance >= 0 )
    {
      Instance = _GetRegKeyLastWriteTime(
                   -2147483647,
                   L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\AppContract",
                   *(_QWORD *)&this[9],
                   1,
                   &this[13]);
      if ( Instance >= 0 )
      {
        CExtensionList::_RecordUsageDataLastWriteTime((CExtensionList *)this);
        v30 = 0;
        if ( WindowsCreateStringReference(L"Windows.Foundation.ExtensionCatalog", 0x23u, &hstringHeader, &string) < 0 )
          RaiseException(0xC000000D, 1u, 0, 0);
        Instance = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Foundation::IExtensionCatalog>>(
                     string,
                     &v30);
        if ( Instance >= 0 )
        {
          v6 = v30;
          v28 = 0;
          v7 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 **))(*(_QWORD *)v30 + 48LL);
          Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(&v28);
          length[0] = 0;
          if ( (int)ULongLongToUInt(0x13u, length) < 0 )
            RaiseException(0xC000000D, v8 - 18, 0, 0);
          WindowsCreateStringReference(L"Windows.ShareTarget", length[0], &v33, &v32);
          Instance = v7(v6, v32, &v28);
          if ( Instance >= 0 )
          {
            Reserved1 = 0;
            v10 = 0;
            v26[0] = 0;
            v32 = 0;
            v11 = *v28;
            memset(&v33, 0, sizeof(v33));
            if ( (*(int (__fastcall **)(__int64 *, char *))(v11 + 56))(v28, v26) >= 0 )
            {
              do
              {
                if ( !v26[0] )
                  break;
                v12 = v28;
                *(_QWORD *)length = 0;
                v13 = *(int (__fastcall **)(__int64 *, UINT32 *))(*v28 + 48);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(length);
                if ( v13(v12, length) >= 0 )
                {
                  if ( Reserved1 != *(char **)&v33.Reserved.Reserved2[16]
                    || (v14 = CTSimpleArray<IRunningShareEntry *,4294967294,CTPolicyCoTaskMem<IRunningShareEntry *>,CSimpleArrayStandardCompareHelper<IRunningShareEntry *>,CSimpleArrayStandardMergeHelper<IRunningShareEntry *>>::_EnsureCapacity(
                                &v32,
                                Reserved1 + 1),
                        Reserved1 = (char *)v33.Reserved.Reserved1,
                        v10 = v32,
                        v14 >= 0) )
                  {
                    v33.Reserved.Reserved1 = ++Reserved1;
                    v15 = v10 + 2 * (_QWORD)(Reserved1 - 1);
                    if ( v15 )
                    {
                      *v15 = *(_QWORD *)length;
                      Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(v15);
                    }
                  }
                }
                v16 = (*(__int64 (__fastcall **)(__int64 *, char *))(*v28 + 64))(v28, v26);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(length);
              }
              while ( v16 >= 0 );
            }
            v29 = 0;
            Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(&v29);
            length[0] = 0;
            if ( (int)ULongLongToUInt(0x13u, length) < 0 )
              RaiseException(0xC000000D, v17 - 18, 0, 0);
            WindowsCreateStringReference(L"Windows.ShareTarget", length[0], &v33, &v32);
            Instance = CExtensionStateManager::CreateInstance(v18, v32, v19, (void **)&v29);
            if ( Instance >= 0 )
            {
              MutexW = CreateMutexW(0, 0, L"__EXTENSION_POINTS_STATE_MUTEX__");
              Instance = CExtensionStateLock::TryLock((CExtensionStateLock *)&MutexW);
              if ( Instance >= 0 )
              {
                v20 = 0;
                if ( Reserved1 )
                {
                  do
                  {
                    *(_QWORD *)length = 0;
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(length);
                    if ( (int)CExtensionListItem::CreateInstance(
                                *((struct Windows::Foundation::IExtensionRegistration **)v10 + v20),
                                v29,
                                v21,
                                (void **)length) >= 0 )
                    {
                      v22 = v3[1];
                      if ( v22 != *(_QWORD *)&v3[3]
                        || (int)CTSimpleArray<IRunningShareEntry *,4294967294,CTPolicyCoTaskMem<IRunningShareEntry *>,CSimpleArrayStandardCompareHelper<IRunningShareEntry *>,CSimpleArrayStandardMergeHelper<IRunningShareEntry *>>::_EnsureCapacity(
                                  v3,
                                  *(_QWORD *)&v22 + 1LL) >= 0 )
                      {
                        v23 = (_QWORD *)(*(_QWORD *)v3 + 8 * (*(_QWORD *)&v3[1])++);
                        if ( v23 )
                        {
                          *v23 = *(_QWORD *)length;
                          Microsoft::WRL::ComPtr<IExtensionListItem>::InternalAddRef();
                        }
                      }
                    }
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(length);
                    ++v20;
                  }
                  while ( v20 < (unsigned __int64)Reserved1 );
                }
              }
              CExtensionStateLock::~CExtensionStateLock((CExtensionStateLock *)&MutexW);
            }
            Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(&v29);
            if ( v10 )
            {
              v24 = 0;
              if ( Reserved1 )
              {
                do
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v10 + 2 * v24++);
                while ( v24 < (unsigned __int64)Reserved1 );
              }
              CoTaskMemFree(v10);
            }
          }
          Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(&v28);
        }
        Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(&v30);
      }
    }
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18007e23c  push    rbp
0x18007e23e  push    rbx
0x18007e23f  push    rsi
0x18007e240  push    rdi
0x18007e241  push    r14
0x18007e243  push    r15
0x18007e245  lea     rbp, [rsp-2Fh]
0x18007e24a  sub     rsp, 0B8h
0x18007e251  mov     rax, cs:__security_cookie
0x18007e258  xor     rax, rsp
0x18007e25b  mov     [rbp+57h+var_40], rax
0x18007e25f  lea     r15, [rcx+20h]
0x18007e263  mov     rdi, rcx
0x18007e266  mov     rcx, r15
0x18007e269  call    ?RemoveAll@?$CTSimpleArray@V?$ComPtr@UIExtensionListItem@@@WRL@Microsoft@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@V?$ComPtr@UIExtensionListItem@@@WRL@Microsoft@@@@V?$CSimpleArrayStandardCompareHelper@V?$ComPtr@UIExtensionListItem@@@WRL@Microsoft@@@@V?$CSimpleArrayStandardMergeHelper@V?$ComPtr@UIExtensionListItem@@@WRL@Microsoft@@@@@@QEAAXXZ; CTSimpleArray<Microsoft::WRL::ComPtr<IExtensionListItem>,4294967294,CTPolicyCoTaskMem<Microsoft::WRL::ComPtr<IExtensionListItem>>,CSimpleArrayStandardCompareHelper<Microsoft::WRL::ComPtr<IExtensionListItem>>,CSimpleArrayStandardMergeHelper<Microsoft::WRL::ComPtr<IExtensionListItem>>>::RemoveAll(void)
0x18007e26e  or      r8, 0FFFFFFFFFFFFFFFFh
0x18007e272  lea     rdx, aWindowsShareta; "Windows.ShareTarget"
0x18007e279  lea     rcx, [rdi+48h]
0x18007e27d  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x18007e282  mov     ebx, eax
0x18007e284  test    eax, eax
0x18007e286  js      loc_18007E5D2
0x18007e28c  lea     rdx, [rdi+60h]; struct _FILETIME *
0x18007e290  mov     rcx, rdi; this
0x18007e293  call    ?_GetLastExtensionCatalogWriteTime@CExtensionList@@AEAAJPEAU_FILETIME@@@Z; CExtensionList::_GetLastExtensionCatalogWriteTime(_FILETIME *)
0x18007e298  mov     ebx, eax
0x18007e29a  test    eax, eax
0x18007e29c  js      loc_18007E5D2
0x18007e2a2  mov     r8, [rdi+48h]
0x18007e2a6  lea     rax, [rdi+68h]
0x18007e2aa  mov     r9d, 1
0x18007e2b0  mov     [rsp+0E0h+var_C0], rax
0x18007e2b5  lea     rdx, aSoftwareMicros_4; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18007e2bc  mov     rcx, 0FFFFFFFF80000001h
0x18007e2c3  call    ?_GetRegKeyLastWriteTime@@YAJPEAUHKEY__@@PEBG1W4REG_LAST_WRITE_OPTION@@PEAU_FILETIME@@@Z; _GetRegKeyLastWriteTime(HKEY__ *,ushort const *,ushort const *,REG_LAST_WRITE_OPTION,_FILETIME *)
0x18007e2c8  mov     ebx, eax
0x18007e2ca  test    eax, eax
0x18007e2cc  js      loc_18007E5D2
0x18007e2d2  mov     rcx, rdi; this
0x18007e2d5  call    ?_RecordUsageDataLastWriteTime@CExtensionList@@AEAAJXZ; CExtensionList::_RecordUsageDataLastWriteTime(void)
0x18007e2da  lea     r9, [rbp+57h+string]; string
0x18007e2de  mov     [rbp+57h+var_90], 0
0x18007e2e6  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18007e2ea  mov     edx, 23h ; '#'; length
0x18007e2ef  lea     rcx, sourceString; "Windows.Foundation.ExtensionCatalog"
0x18007e2f6  call    cs:__imp_WindowsCreateStringReference
0x18007e2fc  mov     esi, 0C000000Dh
0x18007e301  test    eax, eax
0x18007e303  jns     short loc_18007E317
0x18007e305  xor     r9d, r9d; lpArguments
0x18007e308  xor     r8d, r8d; nNumberOfArguments
0x18007e30b  mov     ecx, esi; dwExceptionCode
0x18007e30d  lea     edx, [r9+1]; dwExceptionFlags
0x18007e311  call    cs:__imp_RaiseException
0x18007e317  mov     rcx, [rbp+57h+string]
0x18007e31b  lea     rdx, [rbp+57h+var_90]
0x18007e31f  call    ??$ActivateInstance@V?$ComPtr@UIExtensionCatalog@Foundation@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIExtensionCatalog@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Foundation::IExtensionCatalog>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IExtensionCatalog>>)
0x18007e324  mov     ebx, eax
0x18007e326  test    eax, eax
0x18007e328  js      loc_18007E5C9
0x18007e32e  mov     rbx, [rbp+57h+var_90]
0x18007e332  lea     rcx, [rbp+57h+var_A0]
0x18007e336  mov     [rbp+57h+var_A0], 0
0x18007e33e  mov     rax, [rbx]
0x18007e341  mov     rdi, [rax+30h]
0x18007e345  call    ?InternalRelease@?$ComPtr@UICoreWindowInterop@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(void)
0x18007e34a  lea     rdx, [rbp+57h+length]; unsigned int *
0x18007e34e  mov     [rbp+57h+length], 0
0x18007e355  mov     ecx, 13h; unsigned __int64
0x18007e35a  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x18007e35f  test    eax, eax
0x18007e361  jns     short loc_18007E374
0x18007e363  lea     edx, [rcx-12h]; dwExceptionFlags
0x18007e366  xor     r9d, r9d; lpArguments
0x18007e369  mov     ecx, esi; dwExceptionCode
0x18007e36b  xor     r8d, r8d; nNumberOfArguments
0x18007e36e  call    cs:__imp_RaiseException
0x18007e374  mov     edx, [rbp+57h+length]; length
0x18007e377  lea     r9, [rbp+57h+var_80]; string
0x18007e37b  lea     r8, [rbp+57h+var_78]; hstringHeader
0x18007e37f  lea     rcx, aWindowsShareta; "Windows.ShareTarget"
0x18007e386  call    cs:__imp_WindowsCreateStringReference
0x18007e38c  mov     rdx, [rbp+57h+var_80]
0x18007e390  lea     r8, [rbp+57h+var_A0]
0x18007e394  mov     rcx, rbx
0x18007e397  mov     rax, rdi
0x18007e39a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e39f  mov     ebx, eax
0x18007e3a1  test    eax, eax
0x18007e3a3  js      loc_18007E5C0
0x18007e3a9  mov     rcx, [rbp+57h+var_A0]
0x18007e3ad  lea     rdx, [rbp+57h+var_B0]
0x18007e3b1  xor     esi, esi
0x18007e3b3  xor     r14d, r14d
0x18007e3b6  mov     [rbp+57h+var_B0], sil
0x18007e3ba  mov     [rbp+57h+var_80], r14
0x18007e3be  mov     rax, [rcx]
0x18007e3c1  mov     qword ptr [rbp+57h+var_78.Reserved], rsi
0x18007e3c5  mov     qword ptr [rbp+57h+var_78.Reserved+8], rsi
0x18007e3c9  mov     qword ptr [rbp+57h+var_78.Reserved+10h], rsi
0x18007e3cd  mov     rax, [rax+38h]
0x18007e3d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e3d6  test    eax, eax
0x18007e3d8  js      loc_18007E47D
0x18007e3de  cmp     [rbp+57h+var_B0], 0
0x18007e3e2  jz      loc_18007E47D
0x18007e3e8  mov     rdi, [rbp+57h+var_A0]
0x18007e3ec  lea     rcx, [rbp+57h+length]
0x18007e3f0  mov     qword ptr [rbp+57h+length], 0
0x18007e3f8  mov     rax, [rdi]
0x18007e3fb  mov     rbx, [rax+30h]
0x18007e3ff  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007e404  lea     rdx, [rbp+57h+length]
0x18007e408  mov     rcx, rdi
0x18007e40b  mov     rax, rbx
0x18007e40e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e413  test    eax, eax
0x18007e415  js      short loc_18007E456
0x18007e417  cmp     rsi, qword ptr [rbp+57h+var_78.Reserved+10h]
0x18007e41b  jnz     short loc_18007E436
0x18007e41d  lea     rdx, [rsi+1]
0x18007e421  lea     rcx, [rbp+57h+var_80]
0x18007e425  call    ?_EnsureCapacity@?$CTSimpleArray@PEAUIRunningShareEntry@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@PEAUIRunningShareEntry@@@@V?$CSimpleArrayStandardCompareHelper@PEAUIRunningShareEntry@@@@V?$CSimpleArrayStandardMergeHelper@PEAUIRunningShareEntry@@@@@@QEAAJ_K0@Z; CTSimpleArray<IRunningShareEntry *,4294967294,CTPolicyCoTaskMem<IRunningShareEntry *>,CSimpleArrayStandardCompareHelper<IRunningShareEntry *>,CSimpleArrayStandardMergeHelper<IRunningShareEntry *>>::_EnsureCapacity(unsigned __int64,unsigned __int64)
0x18007e42a  mov     rsi, qword ptr [rbp+57h+var_78.Reserved]
0x18007e42e  mov     r14, [rbp+57h+var_80]
0x18007e432  test    eax, eax
0x18007e434  js      short loc_18007E456
0x18007e436  inc     rsi
0x18007e439  mov     qword ptr [rbp+57h+var_78.Reserved], rsi
0x18007e43d  lea     rcx, [rsi-1]
0x18007e441  lea     rcx, [r14+rcx*8]
0x18007e445  test    rcx, rcx
0x18007e448  jz      short loc_18007E456
0x18007e44a  mov     rax, qword ptr [rbp+57h+length]
0x18007e44e  mov     [rcx], rax
0x18007e451  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x18007e456  mov     rcx, [rbp+57h+var_A0]
0x18007e45a  lea     rdx, [rbp+57h+var_B0]
0x18007e45e  mov     rax, [rcx]
0x18007e461  mov     rax, [rax+40h]
0x18007e465  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e46a  lea     rcx, [rbp+57h+length]
0x18007e46e  mov     ebx, eax
0x18007e470  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007e475  test    ebx, ebx
0x18007e477  jns     loc_18007E3DE
0x18007e47d  lea     rcx, [rbp+57h+var_98]
0x18007e481  mov     [rbp+57h+var_98], 0
0x18007e489  call    ?InternalRelease@?$ComPtr@UICoreWindowInterop@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(void)
0x18007e48e  lea     rdx, [rbp+57h+length]; unsigned int *
0x18007e492  mov     [rbp+57h+length], 0
0x18007e499  mov     ecx, 13h; unsigned __int64
0x18007e49e  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x18007e4a3  test    eax, eax
0x18007e4a5  jns     short loc_18007E4BB
0x18007e4a7  lea     edx, [rcx-12h]; dwExceptionFlags
0x18007e4aa  xor     r9d, r9d; lpArguments
0x18007e4ad  mov     ecx, 0C000000Dh; dwExceptionCode
0x18007e4b2  xor     r8d, r8d; nNumberOfArguments
0x18007e4b5  call    cs:__imp_RaiseException
0x18007e4bb  mov     edx, [rbp+57h+length]; length
0x18007e4be  lea     r9, [rbp+57h+var_80]; string
0x18007e4c2  lea     r8, [rbp+57h+var_78]; hstringHeader
0x18007e4c6  lea     rcx, aWindowsShareta; "Windows.ShareTarget"
0x18007e4cd  call    cs:__imp_WindowsCreateStringReference
0x18007e4d3  mov     rdx, [rbp+57h+var_80]; HSTRING
0x18007e4d7  lea     r9, [rbp+57h+var_98]; void **
0x18007e4db  call    ?CreateInstance@CExtensionStateManager@@SAJPEBGPEAUHSTRING__@@AEBU_GUID@@PEAPEAX@Z; CExtensionStateManager::CreateInstance(ushort const *,HSTRING__ *,_GUID const &,void * *)
0x18007e4e0  mov     ebx, eax
0x18007e4e2  test    eax, eax
0x18007e4e4  js      loc_18007E591
0x18007e4ea  lea     r8, Name; "__EXTENSION_POINTS_STATE_MUTEX__"
0x18007e4f1  xor     edx, edx; bInitialOwner
0x18007e4f3  xor     ecx, ecx; lpMutexAttributes
0x18007e4f5  call    cs:__imp_CreateMutexW
0x18007e4fb  lea     rcx, [rbp+57h+var_88]; this
0x18007e4ff  mov     [rbp+57h+var_88], rax
0x18007e503  call    ?TryLock@CExtensionStateLock@@QEAAJXZ; CExtensionStateLock::TryLock(void)
0x18007e508  mov     ebx, eax
0x18007e50a  test    eax, eax
0x18007e50c  js      short loc_18007E588
0x18007e50e  xor     edi, edi
0x18007e510  test    rsi, rsi
0x18007e513  jz      short loc_18007E588
0x18007e515  lea     rcx, [rbp+57h+length]
0x18007e519  mov     qword ptr [rbp+57h+length], 0
0x18007e521  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007e526  mov     rdx, [rbp+57h+var_98]; struct IExtensionStateManager *
0x18007e52a  lea     r9, [rbp+57h+length]; void **
0x18007e52e  mov     rcx, [r14+rdi*8]; struct Windows::Foundation::IExtensionRegistration *
0x18007e532  call    ?CreateInstance@CExtensionListItem@@SAJPEAUIExtensionRegistration@Foundation@Windows@@PEAUIExtensionStateManager@@AEBU_GUID@@PEAPEAX@Z; CExtensionListItem::CreateInstance(Windows::Foundation::IExtensionRegistration *,IExtensionStateManager *,_GUID const &,void * *)
0x18007e537  test    eax, eax
0x18007e539  js      short loc_18007E577
0x18007e53b  mov     rdx, [r15+8]
0x18007e53f  cmp     rdx, [r15+18h]
0x18007e543  jnz     short loc_18007E554
0x18007e545  inc     rdx
0x18007e548  mov     rcx, r15
0x18007e54b  call    ?_EnsureCapacity@?$CTSimpleArray@PEAUIRunningShareEntry@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@PEAUIRunningShareEntry@@@@V?$CSimpleArrayStandardCompareHelper@PEAUIRunningShareEntry@@@@V?$CSimpleArrayStandardMergeHelper@PEAUIRunningShareEntry@@@@@@QEAAJ_K0@Z; CTSimpleArray<IRunningShareEntry *,4294967294,CTPolicyCoTaskMem<IRunningShareEntry *>,CSimpleArrayStandardCompareHelper<IRunningShareEntry *>,CSimpleArrayStandardMergeHelper<IRunningShareEntry *>>::_EnsureCapacity(unsigned __int64,unsigned __int64)
0x18007e550  test    eax, eax
0x18007e552  js      short loc_18007E577
0x18007e554  inc     qword ptr [r15+8]
0x18007e558  mov     rcx, [r15+8]
0x18007e55c  mov     rax, [r15]
0x18007e55f  dec     rcx
0x18007e562  lea     rcx, [rax+rcx*8]
0x18007e566  test    rcx, rcx
0x18007e569  jz      short loc_18007E577
0x18007e56b  mov     rax, qword ptr [rbp+57h+length]
0x18007e56f  mov     [rcx], rax
0x18007e572  call    ?InternalAddRef@?$ComPtr@UIExtensionListItem@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IExtensionListItem>::InternalAddRef(void)
0x18007e577  lea     rcx, [rbp+57h+length]
0x18007e57b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007e580  inc     rdi
0x18007e583  cmp     rdi, rsi
0x18007e586  jb      short loc_18007E515
0x18007e588  lea     rcx, [rbp+57h+var_88]; this
0x18007e58c  call    ??1CExtensionStateLock@@QEAA@XZ; CExtensionStateLock::~CExtensionStateLock(void)
0x18007e591  lea     rcx, [rbp+57h+var_98]
0x18007e595  call    ?InternalRelease@?$ComPtr@UICoreWindowInterop@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(void)
0x18007e59a  test    r14, r14
0x18007e59d  jz      short loc_18007E5C0
0x18007e59f  xor     edi, edi
0x18007e5a1  test    rsi, rsi
0x18007e5a4  jz      short loc_18007E5B7
0x18007e5a6  lea     rcx, [r14+rdi*8]
0x18007e5aa  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007e5af  inc     rdi
0x18007e5b2  cmp     rdi, rsi
0x18007e5b5  jb      short loc_18007E5A6
0x18007e5b7  mov     rcx, r14; pv
0x18007e5ba  call    cs:__imp_CoTaskMemFree
0x18007e5c0  lea     rcx, [rbp+57h+var_A0]
0x18007e5c4  call    ?InternalRelease@?$ComPtr@UICoreWindowInterop@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(void)
0x18007e5c9  lea     rcx, [rbp+57h+var_90]
0x18007e5cd  call    ?InternalRelease@?$ComPtr@UICoreWindowInterop@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(void)
0x18007e5d2  mov     eax, ebx
0x18007e5d4  mov     rcx, [rbp+57h+var_40]
0x18007e5d8  xor     rcx, rsp; StackCookie
0x18007e5db  call    __security_check_cookie
0x18007e5e0  add     rsp, 0B8h
0x18007e5e7  pop     r15
0x18007e5e9  pop     r14
0x18007e5eb  pop     rdi
0x18007e5ec  pop     rsi
0x18007e5ed  pop     rbx
0x18007e5ee  pop     rbp
0x18007e5ef  retn
```
