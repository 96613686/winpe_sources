# CUpdate::~CUpdate(void)

- ea: `0x180039f90`
- end: `0x18003a0b7`
- name: `??1CUpdate@@UEAA@XZ`
- size: `295`
- prototype: `void __fastcall(CUpdate *__hidden this)`
- caller_count: `3`
- callee_count: `6`
- tags: `file_ops, installer_update`

## callers

- `0x180037dfc`
- `0x180037edc`
- `0x18005dd28`

## callees

- `0x1800054bc`
- `0x180039dac`
- `0x180039f48`
- `0x180039f90`
- `0x18009b0b8`
- `0x1800a1960`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180039fc6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003a0a1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180039fc6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003a0a1`
- `OLEAUT32!__imp_SysFreeString` at `0x180039fd3`
- `OLEAUT32!__imp_SysFreeString` at `0x180039feb`
- `OLEAUT32!__imp_SysFreeString` at `0x18003a003`
- `OLEAUT32!__imp_SysFreeString` at `0x18003a01b`
- `OLEAUT32!__imp_SysFreeString` at `0x180039fd3`
- `OLEAUT32!__imp_SysFreeString` at `0x180039feb`
- `OLEAUT32!__imp_SysFreeString` at `0x18003a003`
- `OLEAUT32!__imp_SysFreeString` at `0x18003a01b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CUpdate::~CUpdate(CUpdate *this)
{
  void *v2; // rcx
  void *v3; // rcx
  __int64 v4; // rcx

  CSusArrayList<CSusMap<wchar_t *,wchar_t *,CSusSortedArrayListItemOpsLPWSTR,CSusSortedArrayListItemOpsLPWSTR>::_tagMapEntry,CSusMap<wchar_t *,wchar_t *,CSusSortedArrayListItemOpsLPWSTR,CSusSortedArrayListItemOpsLPWSTR>::CMapEntryOps>::~CSusArrayList<CSusMap<wchar_t *,wchar_t *,CSusSortedArrayListItemOpsLPWSTR,CSusSortedArrayListItemOpsLPWSTR>::_tagMapEntry,CSusMap<wchar_t *,wchar_t *,CSusSortedArrayListItemOpsLPWSTR,CSusSortedArrayListItemOpsLPWSTR>::CMapEntryOps>((char *)this + 1176);
  CSusArrayList<CSusMap<wchar_t *,__int64,CSusSortedArrayListItemOpsLPWSTR,CSusSortedArrayListItemOpsBasic<__int64>>::_tagMapEntry,CSusMap<wchar_t *,__int64,CSusSortedArrayListItemOpsLPWSTR,CSusSortedArrayListItemOpsBasic<__int64>>::CMapEntryOps>::~CSusArrayList<CSusMap<wchar_t *,__int64,CSusSortedArrayListItemOpsLPWSTR,CSusSortedArrayListItemOpsBasic<__int64>>::_tagMapEntry,CSusMap<wchar_t *,__int64,CSusSortedArrayListItemOpsLPWSTR,CSusSortedArrayListItemOpsBasic<__int64>>::CMapEntryOps>((char *)this + 1144);
  *((_QWORD *)this + 137) = &CSusLock::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 1104));
  SysFreeString(*((BSTR *)this + 136));
  *((_QWORD *)this + 136) = 0;
  SysFreeString(*((BSTR *)this + 135));
  *((_QWORD *)this + 135) = 0;
  SysFreeString(*((BSTR *)this + 134));
  *((_QWORD *)this + 134) = 0;
  SysFreeString(*((BSTR *)this + 133));
  *((_QWORD *)this + 133) = 0;
  v2 = (void *)*((_QWORD *)this + 131);
  if ( v2 )
  {
    operator delete(v2);
    *((_QWORD *)this + 131) = 0;
  }
  v3 = (void *)*((_QWORD *)this + 130);
  if ( v3 )
  {
    operator delete(v3);
    *((_QWORD *)this + 130) = 0;
  }
  v4 = *((_QWORD *)this + 41);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  CSusInternalWrapper::~CSusInternalWrapper((CUpdate *)((char *)this + 72));
  if ( *((_BYTE *)this + 304) )
  {
    *((_BYTE *)this + 304) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 264));
  }
  *(_QWORD *)this = &CSusBaseAllocTag<1752326505>::`vftable';
}

```

## disassembly

```asm
0x180039f90  push    rbx
0x180039f92  sub     rsp, 20h
0x180039f96  mov     rbx, rcx
0x180039f99  add     rcx, 498h
0x180039fa0  call    ??1?$CSusArrayList@U_tagMapEntry@?$CSusMap@PEA_WPEA_WVCSusSortedArrayListItemOpsLPWSTR@@V1@@@VCMapEntryOps@2@@@UEAA@XZ; CSusArrayList<CSusMap<wchar_t *,wchar_t *,CSusSortedArrayListItemOpsLPWSTR,CSusSortedArrayListItemOpsLPWSTR>::_tagMapEntry,CSusMap<wchar_t *,wchar_t *,CSusSortedArrayListItemOpsLPWSTR,CSusSortedArrayListItemOpsLPWSTR>::CMapEntryOps>::~CSusArrayList<CSusMap<wchar_t *,wchar_t *,CSusSortedArrayListItemOpsLPWSTR,CSusSortedArrayListItemOpsLPWSTR>::_tagMapEntry,CSusMap<wchar_t *,wchar_t *,CSusSortedArrayListItemOpsLPWSTR,CSusSortedArrayListItemOpsLPWSTR>::CMapEntryOps>(void)
0x180039fa5  lea     rcx, [rbx+478h]
0x180039fac  call    ??1?$CSusArrayList@U_tagMapEntry@?$CSusMap@PEA_W_JVCSusSortedArrayListItemOpsLPWSTR@@V?$CSusSortedArrayListItemOpsBasic@_J@@@@VCMapEntryOps@2@@@UEAA@XZ; CSusArrayList<CSusMap<wchar_t *,__int64,CSusSortedArrayListItemOpsLPWSTR,CSusSortedArrayListItemOpsBasic<__int64>>::_tagMapEntry,CSusMap<wchar_t *,__int64,CSusSortedArrayListItemOpsLPWSTR,CSusSortedArrayListItemOpsBasic<__int64>>::CMapEntryOps>::~CSusArrayList<CSusMap<wchar_t *,__int64,CSusSortedArrayListItemOpsLPWSTR,CSusSortedArrayListItemOpsBasic<__int64>>::_tagMapEntry,CSusMap<wchar_t *,__int64,CSusSortedArrayListItemOpsLPWSTR,CSusSortedArrayListItemOpsBasic<__int64>>::CMapEntryOps>(void)
0x180039fb1  lea     rax, ??_7CSusLock@@6B@; const CSusLock::`vftable'
0x180039fb8  mov     [rbx+448h], rax
0x180039fbf  lea     rcx, [rbx+450h]; lpCriticalSection
0x180039fc6  call    cs:__imp_DeleteCriticalSection
0x180039fcc  mov     rcx, [rbx+440h]; bstrString
0x180039fd3  call    cs:__imp_SysFreeString
0x180039fd9  mov     qword ptr [rbx+440h], 0
0x180039fe4  mov     rcx, [rbx+438h]; bstrString
0x180039feb  call    cs:__imp_SysFreeString
0x180039ff1  mov     qword ptr [rbx+438h], 0
0x180039ffc  mov     rcx, [rbx+430h]; bstrString
0x18003a003  call    cs:__imp_SysFreeString
0x18003a009  mov     qword ptr [rbx+430h], 0
0x18003a014  mov     rcx, [rbx+428h]; bstrString
0x18003a01b  call    cs:__imp_SysFreeString
0x18003a021  mov     qword ptr [rbx+428h], 0
0x18003a02c  mov     rcx, [rbx+418h]; Block
0x18003a033  test    rcx, rcx
0x18003a036  jz      short loc_18003A04D
0x18003a038  mov     edx, 90h
0x18003a03d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003a042  mov     qword ptr [rbx+418h], 0
0x18003a04d  mov     rcx, [rbx+410h]; Block
0x18003a054  test    rcx, rcx
0x18003a057  jz      short loc_18003A06E
0x18003a059  mov     edx, 90h
0x18003a05e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003a063  mov     qword ptr [rbx+410h], 0
0x18003a06e  mov     rcx, [rbx+148h]
0x18003a075  test    rcx, rcx
0x18003a078  jz      short loc_18003A087
0x18003a07a  mov     rax, [rcx]
0x18003a07d  mov     rax, [rax+10h]
0x18003a081  call    _guard_dispatch_icall
0x18003a086  nop
0x18003a087  lea     rcx, [rbx+48h]; this
0x18003a08b  call    ??1CSusInternalWrapper@@UEAA@XZ; CSusInternalWrapper::~CSusInternalWrapper(void)
0x18003a090  lea     rcx, [rbx+108h]; lpCriticalSection
0x18003a097  cmp     byte ptr [rcx+28h], 0
0x18003a09b  jz      short loc_18003A0A7
0x18003a09d  mov     byte ptr [rcx+28h], 0
0x18003a0a1  call    cs:__imp_DeleteCriticalSection
0x18003a0a7  lea     rax, ??_7?$CSusBaseAllocTag@$0GIHCGBGJ@@@6B@; const CSusBaseAllocTag<1752326505>::`vftable'
0x18003a0ae  mov     [rbx], rax
0x18003a0b1  add     rsp, 20h
0x18003a0b5  pop     rbx
0x18003a0b6  retn
```
