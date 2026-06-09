# CWlanProfileStore::ReadAdapters(void)

- ea: `0x18002b8c0`
- end: `0x18002bb30`
- name: `?ReadAdapters@CWlanProfileStore@@MEAAJXZ`
- size: `624`
- prototype: `__int64 __fastcall(CWlanProfileStore *__hidden this)`
- caller_count: `0`
- callee_count: `16`
- tags: `broker_com_uri`

## callees

- `0x1800027d0`
- `0x180003014`
- `0x1800036ac`
- `0x180004c00`
- `0x1800054a0`
- `0x18000cd90`
- `0x18000cee0`
- `0x18000cf1c`
- `0x18000d264`
- `0x18000d650`
- `0x180029d18`
- `0x18002abf4`
- `0x18002b108`
- `0x18002b8c0`
- `0x18002be90`
- `0x18002c3ac`

## import_xrefs

- `msvcrt!memmove_s` at `0x18002baaf`
- `msvcrt!memmove_s` at `0x18002baaf`
- `wlanapi!WlanFreeMemory` at `0x18002bafd`
- `wlanapi!WlanFreeMemory` at `0x18002bafd`
- `wlanapi!WlanEnumInterfaces` at `0x18002b921`
- `wlanapi!WlanEnumInterfaces` at `0x18002b921`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CWlanProfileStore::ReadAdapters(CWlanProfileStore *this)
{
  _QWORD *v2; // rdi
  void *v3; // rcx
  signed int v4; // ebx
  signed int v5; // eax
  WLAN_INTERFACE_INFO *InterfaceInfo; // rsi
  DWORD dwNumberOfItems; // ebx
  DWORD i; // r14d
  GUID InterfaceGuid; // xmm6
  __int64 v11; // rax
  DWORD j; // r14d
  __int64 v13; // rsi
  __int64 v14; // rax
  const struct CAdapter *v15; // rax
  unsigned __int64 v16; // rbx
  unsigned __int64 v17; // r14
  __int64 v18; // rsi
  __int64 v19; // rdx
  unsigned __int64 v20; // r14
  errno_t v21; // eax
  PWLAN_INTERFACE_INFO_LIST ppInterfaceList; // [rsp+20h] [rbp-60h] BYREF
  _BYTE v23[24]; // [rsp+28h] [rbp-58h] BYREF
  __int128 v24; // [rsp+40h] [rbp-40h] BYREF
  int v25; // [rsp+50h] [rbp-30h]
  char v26[8]; // [rsp+58h] [rbp-28h] BYREF
  _BYTE v27[16]; // [rsp+60h] [rbp-20h] BYREF

  ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(
    v27,
    (char *)this + 24);
  v2 = (_QWORD *)((char *)this + 64);
  ATL::CAtlArray<CAdapter,ATL::CElementTraits<CAdapter>>::SetCount((char *)this + 64, 0);
  v3 = (void *)*((_QWORD *)this + 29);
  if ( !v3 )
  {
    v4 = -2147467259;
LABEL_6:
    ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(v27);
    return (unsigned int)v4;
  }
  ppInterfaceList = 0;
  v5 = WlanEnumInterfaces(v3, 0, &ppInterfaceList);
  v4 = v5;
  if ( v5 > 0 )
    v4 = (unsigned __int16)v5 | 0x80070000;
  if ( v4 < 0 )
    goto LABEL_6;
  InterfaceInfo = ppInterfaceList->InterfaceInfo;
  dwNumberOfItems = ppInterfaceList->dwNumberOfItems;
  ATL::CAtlArray<CAdapter,ATL::CElementTraits<CAdapter>>::SetCount((char *)this + 64, ppInterfaceList->dwNumberOfItems);
  for ( i = 0; i < dwNumberOfItems; ++InterfaceInfo )
  {
    InterfaceGuid = InterfaceInfo->InterfaceGuid;
    WTL::CString::CString((WTL::CString *)v26, InterfaceInfo->strInterfaceDescription);
    *(_QWORD *)v23 = &CAdapter::`vftable';
    *(GUID *)&v23[8] = InterfaceGuid;
    WTL::CString::CString((WTL::CString *)&v24, (const struct WTL::CString *)v26);
    v11 = ATL::CAtlArray<CAdapter,ATL::CElementTraits<CAdapter>>::GetAt((char *)this + 64, i);
    CAdapter::operator=(v11, v23);
    *(_QWORD *)v23 = &CAdapter::`vftable';
    WTL::CString::~CString((WTL::CString *)&v24);
    WTL::CString::~CString((WTL::CString *)v26);
    ++i;
  }
  if ( dwNumberOfItems > 1 )
  {
    for ( j = 0; j < dwNumberOfItems; ++j )
    {
      memset(v23, 0, sizeof(v23));
      v24 = 0;
      v25 = 10;
      v13 = j;
      v14 = ATL::CAtlArray<CAdapter,ATL::CElementTraits<CAdapter>>::GetAt((char *)this + 64, j);
      if ( (int)CWlanProfileStore::GetWlanProfiles(this, v14, v23) < 0 )
      {
        ATL::CAtlList<CWlanProfile,ATL::CElementTraits<CWlanProfile>>::RemoveAll(v23);
        break;
      }
      if ( *(_QWORD *)&v23[16] )
      {
        ATL::CAtlList<CWlanProfile,ATL::CElementTraits<CWlanProfile>>::RemoveAll(v23);
        if ( j )
        {
          v15 = (const struct CAdapter *)ATL::CAtlArray<CAdapter,ATL::CElementTraits<CAdapter>>::GetAt(
                                           (char *)this + 64,
                                           j);
          CAdapter::CAdapter((CAdapter *)v23, v15);
          v16 = j + 1LL;
          if ( v16 < j || (v17 = *((_QWORD *)this + 9), v16 > v17) )
            ATL::AtlThrowImpl(-2147024809);
          v18 = 32 * v13;
          ATL::CAtlArray<CAdapter,ATL::CElementTraits<CAdapter>>::CallDestructors(v18 + *v2, 1);
          v20 = v17 - v16;
          if ( v20 )
          {
            v21 = memmove_s((void *const)(*v2 + v18), 32 * v20, (const void *const)(*v2 + 32 * v16), 32 * v20);
            ATL::AtlCrtErrorCheck(v21);
          }
          --*((_QWORD *)this + 9);
          ATL::CAtlArray<CAdapter,ATL::CElementTraits<CAdapter>>::InsertAt((char *)this + 64, v19, v23, 1);
          *(_QWORD *)v23 = &CAdapter::`vftable';
          WTL::CString::~CString((WTL::CString *)&v24);
        }
        break;
      }
      ATL::CAtlList<CWlanProfile,ATL::CElementTraits<CWlanProfile>>::RemoveAll(v23);
    }
  }
  WlanFreeMemory(ppInterfaceList);
  ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(v27);
  return 0;
}

```

## disassembly

```asm
0x18002b8c0  mov     [rsp-28h+arg_8], rbx
0x18002b8c5  mov     [rsp-28h+arg_10], rsi
0x18002b8ca  push    rbp
0x18002b8cb  push    rdi
0x18002b8cc  push    r12
0x18002b8ce  push    r14
0x18002b8d0  push    r15
0x18002b8d2  mov     rbp, rsp
0x18002b8d5  sub     rsp, 80h
0x18002b8dc  movaps  [rsp+80h+var_10], xmm6
0x18002b8e1  mov     r15, rcx
0x18002b8e4  lea     rdx, [rcx+18h]
0x18002b8e8  lea     rcx, [rbp+var_20]
0x18002b8ec  call    ??0?$CComCritSecLock@VCComAutoCriticalSection@ATL@@@ATL@@QEAA@AEAVCComAutoCriticalSection@1@_N@Z; ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(ATL::CComAutoCriticalSection &,bool)
0x18002b8f1  nop
0x18002b8f2  lea     rdi, [r15+40h]
0x18002b8f6  xor     edx, edx
0x18002b8f8  mov     rcx, rdi
0x18002b8fb  call    ?SetCount@?$CAtlArray@VCAdapter@@V?$CElementTraits@VCAdapter@@@ATL@@@ATL@@QEAA_N_KH@Z; ATL::CAtlArray<CAdapter,ATL::CElementTraits<CAdapter>>::SetCount(unsigned __int64,int)
0x18002b900  nop
0x18002b901  mov     rcx, [r15+0E8h]; hClientHandle
0x18002b908  xor     r12d, r12d
0x18002b90b  test    rcx, rcx
0x18002b90e  jnz     short loc_18002B917
0x18002b910  mov     ebx, 80004005h
0x18002b915  jmp     short loc_18002B93A
0x18002b917  mov     [rbp+ppInterfaceList], r12
0x18002b91b  lea     r8, [rbp+ppInterfaceList]; ppInterfaceList
0x18002b91f  xor     edx, edx; pReserved
0x18002b921  call    cs:__imp_WlanEnumInterfaces
0x18002b927  mov     ebx, eax
0x18002b929  test    eax, eax
0x18002b92b  jle     short loc_18002B936
0x18002b92d  movzx   ebx, ax
0x18002b930  or      ebx, 80070000h
0x18002b936  test    ebx, ebx
0x18002b938  jns     short loc_18002B94A
0x18002b93a  lea     rcx, [rbp+var_20]
0x18002b93e  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x18002b943  mov     eax, ebx
0x18002b945  jmp     loc_18002BB0F
0x18002b94a  mov     rax, [rbp+ppInterfaceList]
0x18002b94e  lea     rsi, [rax+8]
0x18002b952  mov     ebx, [rax]
0x18002b954  mov     edx, ebx
0x18002b956  mov     rcx, rdi
0x18002b959  call    ?SetCount@?$CAtlArray@VCAdapter@@V?$CElementTraits@VCAdapter@@@ATL@@@ATL@@QEAA_N_KH@Z; ATL::CAtlArray<CAdapter,ATL::CElementTraits<CAdapter>>::SetCount(unsigned __int64,int)
0x18002b95e  mov     r14d, r12d
0x18002b961  test    ebx, ebx
0x18002b963  jz      short loc_18002B9D5
0x18002b965  lea     r12, ??_7CAdapter@@6B@; const CAdapter::`vftable'
0x18002b96c  movups  xmm6, xmmword ptr [rsi]
0x18002b96f  lea     rdx, [rsi+10h]; Source
0x18002b973  lea     rcx, [rbp+var_28]; this
0x18002b977  call    ??0CString@WTL@@QEAA@PEBG@Z; WTL::CString::CString(ushort const *)
0x18002b97c  nop
0x18002b97d  mov     qword ptr [rbp+var_58], r12
0x18002b981  movdqu  [rbp+var_58+8], xmm6
0x18002b986  lea     rdx, [rbp+var_28]; struct WTL::CString *
0x18002b98a  lea     rcx, [rbp+var_40]; this
0x18002b98e  call    ??0CString@WTL@@QEAA@AEBV01@@Z; WTL::CString::CString(WTL::CString const &)
0x18002b993  nop
0x18002b994  mov     edx, r14d
0x18002b997  mov     rcx, rdi
0x18002b99a  call    ?GetAt@?$CAtlArray@VCAdapter@@V?$CElementTraits@VCAdapter@@@ATL@@@ATL@@QEBAAEBVCAdapter@@_K@Z; ATL::CAtlArray<CAdapter,ATL::CElementTraits<CAdapter>>::GetAt(unsigned __int64)
0x18002b99f  mov     rcx, rax
0x18002b9a2  lea     rdx, [rbp+var_58]
0x18002b9a6  call    ??4CAdapter@@QEAAAEBV0@AEBV0@@Z; CAdapter::operator=(CAdapter const &)
0x18002b9ab  nop
0x18002b9ac  mov     qword ptr [rbp+var_58], r12
0x18002b9b0  lea     rcx, [rbp+var_40]; this
0x18002b9b4  call    ??1CString@WTL@@QEAA@XZ; WTL::CString::~CString(void)
0x18002b9b9  nop
0x18002b9ba  lea     rcx, [rbp+var_28]; this
0x18002b9be  call    ??1CString@WTL@@QEAA@XZ; WTL::CString::~CString(void)
0x18002b9c3  inc     r14d
0x18002b9c6  lea     rsi, [rsi+214h]
0x18002b9cd  cmp     r14d, ebx
0x18002b9d0  jb      short loc_18002B96C
0x18002b9d2  xor     r12d, r12d
0x18002b9d5  cmp     ebx, 1
0x18002b9d8  jbe     loc_18002BAF9
0x18002b9de  mov     r14d, r12d
0x18002b9e1  cmp     r14d, ebx
0x18002b9e4  jnb     loc_18002BAF9
0x18002b9ea  xorps   xmm0, xmm0
0x18002b9ed  movdqu  [rbp+var_58], xmm0
0x18002b9f2  mov     [rbp+var_48], r12
0x18002b9f6  xorps   xmm1, xmm1
0x18002b9f9  movdqu  [rbp+var_40], xmm1
0x18002b9fe  mov     [rbp+var_30], 0Ah
0x18002ba05  mov     esi, r14d
0x18002ba08  mov     edx, r14d
0x18002ba0b  mov     rcx, rdi
0x18002ba0e  call    ?GetAt@?$CAtlArray@VCAdapter@@V?$CElementTraits@VCAdapter@@@ATL@@@ATL@@QEBAAEBVCAdapter@@_K@Z; ATL::CAtlArray<CAdapter,ATL::CElementTraits<CAdapter>>::GetAt(unsigned __int64)
0x18002ba13  mov     rdx, rax
0x18002ba16  lea     r8, [rbp+var_58]
0x18002ba1a  mov     rcx, r15
0x18002ba1d  call    ?GetWlanProfiles@CWlanProfileStore@@IEAAJAEBVCAdapter@@AEAV?$CAtlList@VCWlanProfile@@V?$CElementTraits@VCWlanProfile@@@ATL@@@ATL@@@Z; CWlanProfileStore::GetWlanProfiles(CAdapter const &,ATL::CAtlList<CWlanProfile,ATL::CElementTraits<CWlanProfile>> &)
0x18002ba22  nop
0x18002ba23  lea     rcx, [rbp+var_58]
0x18002ba27  test    eax, eax
0x18002ba29  js      loc_18002BAF4
0x18002ba2f  cmp     [rbp+var_48], r12
0x18002ba33  jnz     short loc_18002BA3F
0x18002ba35  call    ?RemoveAll@?$CAtlList@VCWlanProfile@@V?$CElementTraits@VCWlanProfile@@@ATL@@@ATL@@QEAAXXZ; ATL::CAtlList<CWlanProfile,ATL::CElementTraits<CWlanProfile>>::RemoveAll(void)
0x18002ba3a  inc     r14d
0x18002ba3d  jmp     short loc_18002B9E1
0x18002ba3f  call    ?RemoveAll@?$CAtlList@VCWlanProfile@@V?$CElementTraits@VCWlanProfile@@@ATL@@@ATL@@QEAAXXZ; ATL::CAtlList<CWlanProfile,ATL::CElementTraits<CWlanProfile>>::RemoveAll(void)
0x18002ba44  test    r14d, r14d
0x18002ba47  jz      loc_18002BAF9
0x18002ba4d  mov     rdx, rsi
0x18002ba50  mov     rcx, rdi
0x18002ba53  call    ?GetAt@?$CAtlArray@VCAdapter@@V?$CElementTraits@VCAdapter@@@ATL@@@ATL@@QEBAAEBVCAdapter@@_K@Z; ATL::CAtlArray<CAdapter,ATL::CElementTraits<CAdapter>>::GetAt(unsigned __int64)
0x18002ba58  mov     rdx, rax; struct CAdapter *
0x18002ba5b  lea     rcx, [rbp+var_58]; this
0x18002ba5f  call    ??0CAdapter@@QEAA@AEBV0@@Z; CAdapter::CAdapter(CAdapter const &)
0x18002ba64  nop
0x18002ba65  lea     rbx, [rsi+1]
0x18002ba69  cmp     rbx, rsi
0x18002ba6c  jb      short loc_18002BAE9
0x18002ba6e  cmp     rbx, 1
0x18002ba72  jb      short loc_18002BAE9
0x18002ba74  mov     r14, [rdi+8]
0x18002ba78  cmp     rbx, r14
0x18002ba7b  ja      short loc_18002BAE9
0x18002ba7d  shl     rsi, 5
0x18002ba81  mov     rcx, [rdi]
0x18002ba84  add     rcx, rsi
0x18002ba87  mov     edx, 1
0x18002ba8c  call    ?CallDestructors@?$CAtlArray@VCAdapter@@V?$CElementTraits@VCAdapter@@@ATL@@@ATL@@CAXPEAVCAdapter@@_K@Z; ATL::CAtlArray<CAdapter,ATL::CElementTraits<CAdapter>>::CallDestructors(CAdapter *,unsigned __int64)
0x18002ba91  sub     r14, rbx
0x18002ba94  jz      short loc_18002BABC
0x18002ba96  mov     rax, [rdi]
0x18002ba99  shl     r14, 5
0x18002ba9d  shl     rbx, 5
0x18002baa1  lea     r8, [rax+rbx]; Source
0x18002baa5  lea     rcx, [rax+rsi]; Destination
0x18002baa9  mov     r9, r14; SourceSize
0x18002baac  mov     rdx, r14; DestinationSize
0x18002baaf  call    cs:__imp_memmove_s
0x18002bab5  mov     ecx, eax; int
0x18002bab7  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18002babc  dec     qword ptr [rdi+8]
0x18002bac0  mov     r9d, 1
0x18002bac6  lea     r8, [rbp+var_58]
0x18002baca  mov     rcx, rdi
0x18002bacd  call    ?InsertAt@?$CAtlArray@VCAdapter@@V?$CElementTraits@VCAdapter@@@ATL@@@ATL@@QEAAX_KAEBVCAdapter@@0@Z; ATL::CAtlArray<CAdapter,ATL::CElementTraits<CAdapter>>::InsertAt(unsigned __int64,CAdapter const &,unsigned __int64)
0x18002bad2  nop
0x18002bad3  lea     rax, ??_7CAdapter@@6B@; const CAdapter::`vftable'
0x18002bada  mov     qword ptr [rbp+var_58], rax
0x18002bade  lea     rcx, [rbp+var_40]; this
0x18002bae2  call    ??1CString@WTL@@QEAA@XZ; WTL::CString::~CString(void)
0x18002bae7  jmp     short loc_18002BAF9
0x18002bae9  mov     ecx, 80070057h; int
0x18002baee  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18002baf4  call    ?RemoveAll@?$CAtlList@VCWlanProfile@@V?$CElementTraits@VCWlanProfile@@@ATL@@@ATL@@QEAAXXZ; ATL::CAtlList<CWlanProfile,ATL::CElementTraits<CWlanProfile>>::RemoveAll(void)
0x18002baf9  mov     rcx, [rbp+ppInterfaceList]; pMemory
0x18002bafd  call    cs:__imp_WlanFreeMemory
0x18002bb03  nop
0x18002bb04  lea     rcx, [rbp+var_20]
0x18002bb08  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x18002bb0d  xor     eax, eax
0x18002bb0f  lea     r11, [rsp+80h+var_s0]
0x18002bb17  mov     rbx, [r11+38h]
0x18002bb1b  mov     rsi, [r11+40h]
0x18002bb1f  movaps  xmm6, [rsp+80h+var_10]
0x18002bb24  mov     rsp, r11
0x18002bb27  pop     r15
0x18002bb29  pop     r14
0x18002bb2b  pop     r12
0x18002bb2d  pop     rdi
0x18002bb2e  pop     rbp
0x18002bb2f  retn
```
