# CExtensionStateManager::_LoadSortedPinnedList(CCoSimpleArray<EXTENSION_STATE,4294967294,CSimpleArrayStandardCompareHelper<EXTENSION_STATE>> *,IExtensionListItem *)

- ea: `0x18007f140`
- end: `0x18007f358`
- name: `?_LoadSortedPinnedList@CExtensionStateManager@@AEAAJPEAV?$CCoSimpleArray@UEXTENSION_STATE@@$0PPPPPPPO@V?$CSimpleArrayStandardCompareHelper@UEXTENSION_STATE@@@@@@PEAUIExtensionListItem@@@Z`
- size: `536`
- prototype: `__int64 __fastcall(CExtensionStateManager *this)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180078310`
- `0x18007b210`

## callees

- `0x180013c80`
- `0x180016694`
- `0x180020e10`
- `0x180026ee0`
- `0x18002b1b0`
- `0x18002bc68`
- `0x180077618`
- `0x1800777fc`
- `0x18007d0f8`
- `0x18007dae8`
- `0x18007f020`
- `0x18007f140`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007f213`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007f213`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18007f1e3`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18007f1e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007f325`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007f325`

## pseudocode

```c
__int64 __fastcall CExtensionStateManager::_LoadSortedPinnedList(
        CExtensionStateManager *this,
        __int64 a2,
        struct IExtensionListItem *a3)
{
  signed int ExtensionIdFromExtensionItem; // ebx
  DWORD v7; // esi
  HKEY v8; // rcx
  LSTATUS v9; // eax
  PCWSTR StringRawBuffer; // rax
  WCHAR *v11; // rcx
  signed __int64 v12; // rax
  int v13; // r8d
  int v14; // edx
  __int64 v15; // rdx
  __int64 v16; // rdx
  unsigned __int64 v17; // rcx
  LPVOID *v18; // rsi
  unsigned int v19; // edx
  void *v20; // rcx
  _BYTE v22[8]; // [rsp+40h] [rbp-C0h] BYREF
  HSTRING string; // [rsp+48h] [rbp-B8h] BYREF
  DWORD cchName[4]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v25[528]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Name[264]; // [rsp+270h] [rbp+170h] BYREF

  CTSimpleArray<CServiceHostComponent::ISC_SERVICE,4294967294,CTPolicyCoTaskMem<CServiceHostComponent::ISC_SERVICE>,CSimpleArrayStandardCompareHelper<CServiceHostComponent::ISC_SERVICE>,CSimpleArrayStandardMergeHelper<CServiceHostComponent::ISC_SERVICE>>::RemoveAll(a2);
  if ( *((_QWORD *)this + 2) )
  {
    string = 0;
    ExtensionIdFromExtensionItem = _GetExtensionIdFromExtensionItem(a3, (struct Windows::Internal::String *)&string);
    v7 = 0;
    while ( ExtensionIdFromExtensionItem >= 0 )
    {
      v8 = (HKEY)*((_QWORD *)this + 2);
      cchName[0] = 260;
      v9 = RegEnumKeyExW(v8, v7, Name, cchName, 0, 0, 0, 0);
      ExtensionIdFromExtensionItem = v9;
      if ( v9 > 0 )
        ExtensionIdFromExtensionItem = (unsigned __int16)v9 | 0x80070000;
      if ( ExtensionIdFromExtensionItem == -2147024637 )
      {
        ExtensionIdFromExtensionItem = 0;
        break;
      }
      if ( ExtensionIdFromExtensionItem >= 0 )
      {
        StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
        v11 = Name;
        v12 = (char *)StringRawBuffer - (char *)Name;
        do
        {
          v13 = *(WCHAR *)((char *)v11 + v12);
          v14 = *v11 - v13;
          if ( v14 )
            break;
          ++v11;
        }
        while ( v13 );
        if ( v14 )
        {
          memset_0(v25, 0, sizeof(v25));
          ExtensionIdFromExtensionItem = CExtensionStateManager::_LoadExtensionState(
                                           this,
                                           Name,
                                           (struct EXTENSION_STATE *)v25);
          if ( ExtensionIdFromExtensionItem >= 0 && (v25[520] & 1) != 0 )
          {
            v15 = *(_QWORD *)(a2 + 8);
            ExtensionIdFromExtensionItem = 0;
            if ( v15 != *(_QWORD *)(a2 + 24)
              || (ExtensionIdFromExtensionItem = CTSimpleArray<EXTENSION_STATE,4294967294,CTPolicyCoTaskMem<EXTENSION_STATE>,CSimpleArrayStandardCompareHelper<EXTENSION_STATE>,CSimpleArrayStandardMergeHelper<EXTENSION_STATE>>::_EnsureCapacity(
                                                   a2,
                                                   v15 + 1),
                  ExtensionIdFromExtensionItem >= 0) )
            {
              v16 = *(_QWORD *)(a2 + 8);
              *(_QWORD *)(a2 + 8) = v16 + 1;
              CTSimpleArray<EXTENSION_STATE,4294967294,CTPolicyCoTaskMem<EXTENSION_STATE>,CSimpleArrayStandardCompareHelper<EXTENSION_STATE>,CSimpleArrayStandardMergeHelper<EXTENSION_STATE>>::_InternalSetAtIndex<EXTENSION_STATE const &>(
                a2,
                v16,
                v25);
            }
          }
        }
      }
      ++v7;
    }
    Windows::Internal::String::~String((Windows::Internal::String *)&string);
    if ( ExtensionIdFromExtensionItem >= 0 )
    {
      v17 = *(_QWORD *)(a2 + 8);
      v22[0] = 0;
      if ( v17 > 1 )
      {
        v18 = (LPVOID *)(a2 + 16);
        *(_QWORD *)(a2 + 16) = 0;
        string = 0;
        if ( (int)ULongLongMult(v17 >> 1, 0x210u, (unsigned __int64 *)&string) >= 0
          && CTCoAllocPolicy::Realloc(v20, v19, 0, (unsigned __int64)string, (void **)(a2 + 16)) >= 0 )
        {
          CTSimpleArray<EXTENSION_STATE,4294967294,CTPolicyCoTaskMem<EXTENSION_STATE>,CSimpleArrayStandardCompareHelper<EXTENSION_STATE>,CSimpleArrayStandardMergeHelper<EXTENSION_STATE>>::_MergeSort<CExtensionStateManager::PinnedOrderCompare>(
            a2,
            v22,
            0,
            *(_QWORD *)(a2 + 8));
          CoTaskMemFree(*v18);
          *v18 = 0;
        }
      }
    }
  }
  else
  {
    return (unsigned int)-2147418113;
  }
  return (unsigned int)ExtensionIdFromExtensionItem;
}

```

## disassembly

```asm
0x18007f140  push    rbp
0x18007f142  push    rbx
0x18007f143  push    rsi
0x18007f144  push    rdi
0x18007f145  push    r14
0x18007f147  lea     rbp, [rsp-390h]
0x18007f14f  sub     rsp, 490h
0x18007f156  mov     rax, cs:__security_cookie
0x18007f15d  xor     rax, rsp
0x18007f160  mov     [rbp+3B0h+var_30], rax
0x18007f167  mov     r14, rcx
0x18007f16a  mov     rbx, r8
0x18007f16d  mov     rcx, rdx
0x18007f170  mov     rdi, rdx
0x18007f173  call    ?RemoveAll@?$CTSimpleArray@UISC_SERVICE@CServiceHostComponent@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@UISC_SERVICE@CServiceHostComponent@@@@V?$CSimpleArrayStandardCompareHelper@UISC_SERVICE@CServiceHostComponent@@@@V?$CSimpleArrayStandardMergeHelper@UISC_SERVICE@CServiceHostComponent@@@@@@QEAAXXZ; CTSimpleArray<CServiceHostComponent::ISC_SERVICE,4294967294,CTPolicyCoTaskMem<CServiceHostComponent::ISC_SERVICE>,CSimpleArrayStandardCompareHelper<CServiceHostComponent::ISC_SERVICE>,CSimpleArrayStandardMergeHelper<CServiceHostComponent::ISC_SERVICE>>::RemoveAll(void)
0x18007f178  cmp     qword ptr [r14+10h], 0
0x18007f17d  jz      loc_18007F334
0x18007f183  lea     rdx, [rsp+4B0h+string]; struct Windows::Internal::String *
0x18007f188  mov     [rsp+4B0h+string], 0
0x18007f191  mov     rcx, rbx; struct IExtensionListItem *
0x18007f194  call    ?_GetExtensionIdFromExtensionItem@@YAJPEAUIExtensionListItem@@PEAVString@Internal@Windows@@@Z; _GetExtensionIdFromExtensionItem(IExtensionListItem *,Windows::Internal::String *)
0x18007f199  mov     ebx, eax
0x18007f19b  xor     esi, esi
0x18007f19d  test    ebx, ebx
0x18007f19f  js      loc_18007F2B1
0x18007f1a5  mov     rcx, [r14+10h]; hKey
0x18007f1a9  lea     r9, [rsp+4B0h+cchName]; lpcchName
0x18007f1ae  mov     [rsp+4B0h+lpftLastWriteTime], 0; lpftLastWriteTime
0x18007f1b7  lea     r8, [rbp+3B0h+Name]; lpName
0x18007f1be  mov     [rsp+4B0h+lpcchClass], 0; lpcchClass
0x18007f1c7  mov     edx, esi; dwIndex
0x18007f1c9  mov     [rsp+4B0h+lpClass], 0; lpClass
0x18007f1d2  mov     [rsp+4B0h+lpReserved], 0; lpReserved
0x18007f1db  mov     [rsp+4B0h+cchName], 104h
0x18007f1e3  call    cs:__imp_RegEnumKeyExW
0x18007f1e9  mov     ebx, eax
0x18007f1eb  test    eax, eax
0x18007f1ed  jle     short loc_18007F1F8
0x18007f1ef  movzx   ebx, ax
0x18007f1f2  or      ebx, 80070000h
0x18007f1f8  cmp     ebx, 80070103h
0x18007f1fe  jz      loc_18007F2AF
0x18007f204  test    ebx, ebx
0x18007f206  js      loc_18007F2A8
0x18007f20c  mov     rcx, [rsp+4B0h+string]; string
0x18007f211  xor     edx, edx; length
0x18007f213  call    cs:__imp_WindowsGetStringRawBuffer
0x18007f219  lea     rcx, [rbp+3B0h+Name]
0x18007f220  sub     rax, rcx
0x18007f223  movzx   edx, word ptr [rcx]
0x18007f226  movzx   r8d, word ptr [rcx+rax]
0x18007f22b  sub     edx, r8d
0x18007f22e  jnz     short loc_18007F239
0x18007f230  add     rcx, 2
0x18007f234  test    r8d, r8d
0x18007f237  jnz     short loc_18007F223
0x18007f239  test    edx, edx
0x18007f23b  jz      short loc_18007F2A8
0x18007f23d  xor     edx, edx; Val
0x18007f23f  lea     rcx, [rsp+4B0h+var_450]; void *
0x18007f244  mov     r8d, 210h; Size
0x18007f24a  call    memset_0
0x18007f24f  lea     r8, [rsp+4B0h+var_450]; struct EXTENSION_STATE *
0x18007f254  mov     rcx, r14; this
0x18007f257  lea     rdx, [rbp+3B0h+Name]; unsigned __int16 *
0x18007f25e  call    ?_LoadExtensionState@CExtensionStateManager@@AEAAJPEBGPEAUEXTENSION_STATE@@@Z; CExtensionStateManager::_LoadExtensionState(ushort const *,EXTENSION_STATE *)
0x18007f263  mov     ebx, eax
0x18007f265  test    eax, eax
0x18007f267  js      short loc_18007F2A8
0x18007f269  test    [rbp+3B0h+var_248], 1
0x18007f270  jz      short loc_18007F2A8
0x18007f272  mov     rdx, [rdi+8]
0x18007f276  xor     ebx, ebx
0x18007f278  cmp     rdx, [rdi+18h]
0x18007f27c  jnz     short loc_18007F28F
0x18007f27e  inc     rdx
0x18007f281  mov     rcx, rdi
0x18007f284  call    ?_EnsureCapacity@?$CTSimpleArray@UEXTENSION_STATE@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@UEXTENSION_STATE@@@@V?$CSimpleArrayStandardCompareHelper@UEXTENSION_STATE@@@@V?$CSimpleArrayStandardMergeHelper@UEXTENSION_STATE@@@@@@QEAAJ_K0@Z; CTSimpleArray<EXTENSION_STATE,4294967294,CTPolicyCoTaskMem<EXTENSION_STATE>,CSimpleArrayStandardCompareHelper<EXTENSION_STATE>,CSimpleArrayStandardMergeHelper<EXTENSION_STATE>>::_EnsureCapacity(unsigned __int64,unsigned __int64)
0x18007f289  mov     ebx, eax
0x18007f28b  test    eax, eax
0x18007f28d  js      short loc_18007F2A8
0x18007f28f  mov     rdx, [rdi+8]
0x18007f293  lea     r8, [rsp+4B0h+var_450]
0x18007f298  mov     rcx, rdi
0x18007f29b  lea     rax, [rdx+1]
0x18007f29f  mov     [rdi+8], rax
0x18007f2a3  call    ??$_InternalSetAtIndex@AEBUEXTENSION_STATE@@@?$CTSimpleArray@UEXTENSION_STATE@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@UEXTENSION_STATE@@@@V?$CSimpleArrayStandardCompareHelper@UEXTENSION_STATE@@@@V?$CSimpleArrayStandardMergeHelper@UEXTENSION_STATE@@@@@@QEAAX_KAEBUEXTENSION_STATE@@@Z; CTSimpleArray<EXTENSION_STATE,4294967294,CTPolicyCoTaskMem<EXTENSION_STATE>,CSimpleArrayStandardCompareHelper<EXTENSION_STATE>,CSimpleArrayStandardMergeHelper<EXTENSION_STATE>>::_InternalSetAtIndex<EXTENSION_STATE const &>(unsigned __int64,EXTENSION_STATE const &)
0x18007f2a8  inc     esi
0x18007f2aa  jmp     loc_18007F19D
0x18007f2af  xor     ebx, ebx
0x18007f2b1  lea     rcx, [rsp+4B0h+string]; this
0x18007f2b6  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18007f2bb  test    ebx, ebx
0x18007f2bd  js      short loc_18007F339
0x18007f2bf  mov     rcx, [rdi+8]
0x18007f2c3  mov     [rsp+4B0h+var_470], 0
0x18007f2c8  cmp     rcx, 1
0x18007f2cc  jbe     short loc_18007F339
0x18007f2ce  lea     rsi, [rdi+10h]
0x18007f2d2  shr     rcx, 1; unsigned __int64
0x18007f2d5  lea     r8, [rsp+4B0h+string]; unsigned __int64 *
0x18007f2da  mov     qword ptr [rsi], 0
0x18007f2e1  mov     edx, 210h; unsigned __int64
0x18007f2e6  mov     [rsp+4B0h+string], 0
0x18007f2ef  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18007f2f4  test    eax, eax
0x18007f2f6  js      short loc_18007F339
0x18007f2f8  mov     r9, [rsp+4B0h+string]; unsigned __int64
0x18007f2fd  xor     r8d, r8d; void *
0x18007f300  mov     [rsp+4B0h+lpReserved], rsi; void **
0x18007f305  call    ?Realloc@CTCoAllocPolicy@@SAJPEAXK0_KPEAPEAX@Z; CTCoAllocPolicy::Realloc(void *,ulong,void *,unsigned __int64,void * *)
0x18007f30a  test    eax, eax
0x18007f30c  js      short loc_18007F339
0x18007f30e  mov     r9, [rdi+8]
0x18007f312  lea     rdx, [rsp+4B0h+var_470]
0x18007f317  xor     r8d, r8d
0x18007f31a  mov     rcx, rdi
0x18007f31d  call    ??$_MergeSort@VPinnedOrderCompare@CExtensionStateManager@@@?$CTSimpleArray@UEXTENSION_STATE@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@UEXTENSION_STATE@@@@V?$CSimpleArrayStandardCompareHelper@UEXTENSION_STATE@@@@V?$CSimpleArrayStandardMergeHelper@UEXTENSION_STATE@@@@@@QEAAXAEBVPinnedOrderCompare@CExtensionStateManager@@_K1@Z; CTSimpleArray<EXTENSION_STATE,4294967294,CTPolicyCoTaskMem<EXTENSION_STATE>,CSimpleArrayStandardCompareHelper<EXTENSION_STATE>,CSimpleArrayStandardMergeHelper<EXTENSION_STATE>>::_MergeSort<CExtensionStateManager::PinnedOrderCompare>(CExtensionStateManager::PinnedOrderCompare const &,unsigned __int64,unsigned __int64)
0x18007f322  mov     rcx, [rsi]; pv
0x18007f325  call    cs:__imp_CoTaskMemFree
0x18007f32b  mov     qword ptr [rsi], 0
0x18007f332  jmp     short loc_18007F339
0x18007f334  mov     ebx, 8000FFFFh
0x18007f339  mov     eax, ebx
0x18007f33b  mov     rcx, [rbp+3B0h+var_30]
0x18007f342  xor     rcx, rsp; StackCookie
0x18007f345  call    __security_check_cookie
0x18007f34a  add     rsp, 490h
0x18007f351  pop     r14
0x18007f353  pop     rdi
0x18007f354  pop     rsi
0x18007f355  pop     rbx
0x18007f356  pop     rbp
0x18007f357  retn
```
