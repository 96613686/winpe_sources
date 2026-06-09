# CPreflistFolder::GetTitle(ushort * *)

- ea: `0x18000f630`
- end: `0x18000f764`
- name: `?GetTitle@CPreflistFolder@@UEAAJPEAPEAG@Z`
- size: `308`
- prototype: `__int64 __fastcall(CPreflistFolder *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800036ac`
- `0x180008484`
- `0x18000cfd4`
- `0x18000e164`
- `0x18000f130`
- `0x18000f630`
- `0x180011630`
- `0x18002d840`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000f711`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000f711`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CPreflistFolder::GetTitle(CPreflistFolder *this, unsigned __int16 **a2)
{
  unsigned __int16 *v3; // rbx
  __int64 v4; // rdi
  unsigned __int16 *v5; // rax
  unsigned int v6; // ebx
  unsigned __int16 *v8; // [rsp+20h] [rbp-29h] BYREF
  __int64 v9; // [rsp+28h] [rbp-21h] BYREF
  __int64 v10; // [rsp+30h] [rbp-19h] BYREF
  __int64 v11; // [rsp+38h] [rbp-11h]
  __int64 v12; // [rsp+40h] [rbp-9h]
  int v13; // [rsp+48h] [rbp-1h]
  _QWORD v14[3]; // [rsp+50h] [rbp+7h] BYREF
  _BYTE v15[8]; // [rsp+68h] [rbp+1Fh] BYREF

  v8 = (unsigned __int16 *)WTL::_atltmpPchNil;
  v10 = 0;
  v11 = 0;
  v12 = 0;
  v13 = 0;
  (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)CSingletonPtr<CWlanProfileStore>::s_pInstance + 72LL))(
    CSingletonPtr<CWlanProfileStore>::s_pInstance,
    &v10);
  if ( v11 )
  {
    (*(void (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)CSingletonPtr<CWlanProfileStore>::s_pInstance + 80LL))(
      CSingletonPtr<CWlanProfileStore>::s_pInstance,
      v14);
    CAdapter::GetFriendlyName((__int64)v14, (WTL::CString *)&v9);
    WTL::CString::FormatMessageW((WTL::CString *)&v8, 0x4E23u, v9);
    WTL::CString::~CString((WTL::CString *)&v9);
    v14[0] = &CAdapter::`vftable';
    WTL::CString::~CString((WTL::CString *)v15);
  }
  else
  {
    WTL::CString::LoadStringW((WTL::CString *)&v8, 0x4E24u);
  }
  v3 = v8;
  v4 = *((int *)v8 - 2);
  v5 = (unsigned __int16 *)CoTaskMemAlloc(2 * v4 + 2);
  *a2 = v5;
  if ( v5 )
    v6 = StringCchCopyW(v5, v4 + 1, v3);
  else
    v6 = -2147024882;
  ATL::CAtlArray<CAdapter,ATL::CElementTraits<CAdapter>>::~CAtlArray<CAdapter,ATL::CElementTraits<CAdapter>>(&v10);
  WTL::CString::~CString((WTL::CString *)&v8);
  return v6;
}

```

## disassembly

```asm
0x18000f630  push    rbp
0x18000f632  push    rbx
0x18000f633  push    rsi
0x18000f634  push    rdi
0x18000f635  lea     rbp, [rsp-3Fh]
0x18000f63a  sub     rsp, 88h
0x18000f641  mov     rax, cs:__security_cookie
0x18000f648  xor     rax, rsp
0x18000f64b  mov     [rbp+57h+var_30], rax
0x18000f64f  mov     rsi, rdx
0x18000f652  mov     rax, cs:?_atltmpPchNil@WTL@@3PEBGEB; ushort const * const WTL::_atltmpPchNil
0x18000f659  mov     [rbp+57h+var_80], rax
0x18000f65d  mov     [rbp+57h+var_70], 0
0x18000f665  mov     [rbp+57h+var_68], 0
0x18000f66d  mov     [rbp+57h+var_60], 0
0x18000f675  mov     [rbp+57h+var_58], 0
0x18000f67c  mov     rcx, cs:?s_pInstance@?$CSingletonPtr@VCWlanProfileStore@@@@0PEAVCWlanProfileStore@@EA; CWlanProfileStore * CSingletonPtr<CWlanProfileStore>::s_pInstance
0x18000f683  mov     rax, [rcx]
0x18000f686  lea     rdx, [rbp+57h+var_70]
0x18000f68a  mov     rax, [rax+48h]
0x18000f68e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f693  cmp     [rbp+57h+var_68], 0
0x18000f698  jbe     short loc_18000F6F3
0x18000f69a  mov     rcx, cs:?s_pInstance@?$CSingletonPtr@VCWlanProfileStore@@@@0PEAVCWlanProfileStore@@EA; CWlanProfileStore * CSingletonPtr<CWlanProfileStore>::s_pInstance
0x18000f6a1  mov     rax, [rcx]
0x18000f6a4  lea     rdx, [rbp+57h+var_50]
0x18000f6a8  mov     rax, [rax+50h]
0x18000f6ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f6b1  nop
0x18000f6b2  lea     rdx, [rbp+57h+var_78]
0x18000f6b6  lea     rcx, [rbp+57h+var_50]
0x18000f6ba  call    ?GetFriendlyName@CAdapter@@QEBA?AVCString@WTL@@XZ; CAdapter::GetFriendlyName(void)
0x18000f6bf  nop
0x18000f6c0  mov     r8, [rbp+57h+var_78]
0x18000f6c4  mov     edx, 4E23h; unsigned int
0x18000f6c9  lea     rcx, [rbp+57h+var_80]; this
0x18000f6cd  call    ?FormatMessageW@CString@WTL@@QEAAHIZZ; WTL::CString::FormatMessageW(uint,...)
0x18000f6d2  nop
0x18000f6d3  lea     rcx, [rbp+57h+var_78]; this
0x18000f6d7  call    ??1CString@WTL@@QEAA@XZ; WTL::CString::~CString(void)
0x18000f6dc  nop
0x18000f6dd  lea     rax, ??_7CAdapter@@6B@; const CAdapter::`vftable'
0x18000f6e4  mov     [rbp+57h+var_50], rax
0x18000f6e8  lea     rcx, [rbp+57h+var_38]; this
0x18000f6ec  call    ??1CString@WTL@@QEAA@XZ; WTL::CString::~CString(void)
0x18000f6f1  jmp     short loc_18000F701
0x18000f6f3  mov     edx, 4E24h; uID
0x18000f6f8  lea     rcx, [rbp+57h+var_80]; this
0x18000f6fc  call    ?LoadStringW@CString@WTL@@QEAAHI@Z; WTL::CString::LoadStringW(uint)
0x18000f701  mov     rbx, [rbp+57h+var_80]
0x18000f705  movsxd  rdi, dword ptr [rbx-8]
0x18000f709  lea     rcx, ds:2[rdi*2]; cb
0x18000f711  call    cs:__imp_CoTaskMemAlloc
0x18000f717  mov     [rsi], rax
0x18000f71a  test    rax, rax
0x18000f71d  jnz     short loc_18000F726
0x18000f71f  mov     ebx, 8007000Eh
0x18000f724  jmp     short loc_18000F737
0x18000f726  lea     rdx, [rdi+1]; unsigned __int64
0x18000f72a  mov     r8, rbx; unsigned __int16 *
0x18000f72d  mov     rcx, rax; unsigned __int16 *
0x18000f730  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000f735  mov     ebx, eax
0x18000f737  lea     rcx, [rbp+57h+var_70]
0x18000f73b  call    ??1?$CAtlArray@VCAdapter@@V?$CElementTraits@VCAdapter@@@ATL@@@ATL@@QEAA@XZ; ATL::CAtlArray<CAdapter,ATL::CElementTraits<CAdapter>>::~CAtlArray<CAdapter,ATL::CElementTraits<CAdapter>>(void)
0x18000f740  nop
0x18000f741  lea     rcx, [rbp+57h+var_80]; this
0x18000f745  call    ??1CString@WTL@@QEAA@XZ; WTL::CString::~CString(void)
0x18000f74a  mov     eax, ebx
0x18000f74c  mov     rcx, [rbp+57h+var_30]
0x18000f750  xor     rcx, rsp; StackCookie
0x18000f753  call    __security_check_cookie
0x18000f758  add     rsp, 88h
0x18000f75f  pop     rdi
0x18000f760  pop     rsi
0x18000f761  pop     rbx
0x18000f762  pop     rbp
0x18000f763  retn
```
