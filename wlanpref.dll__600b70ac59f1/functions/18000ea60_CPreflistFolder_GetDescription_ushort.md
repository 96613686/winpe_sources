# CPreflistFolder::GetDescription(ushort * *)

- ea: `0x18000ea60`
- end: `0x18000eb3d`
- name: `?GetDescription@CPreflistFolder@@UEAAJPEAPEAG@Z`
- size: `221`
- prototype: `__int64 __fastcall(CPreflistFolder *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800036ac`
- `0x180008484`
- `0x18000cfd4`
- `0x18000ea60`
- `0x180011630`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000eaf0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000eaf0`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CPreflistFolder::GetDescription(CPreflistFolder *this, unsigned __int16 **a2)
{
  UINT v3; // edx
  unsigned __int16 *v4; // rbx
  __int64 v5; // rdi
  unsigned __int16 *v6; // rax
  unsigned int v7; // ebx
  __int64 v9; // [rsp+20h] [rbp-28h] BYREF
  unsigned __int64 v10; // [rsp+28h] [rbp-20h]
  __int64 v11; // [rsp+30h] [rbp-18h]
  int v12; // [rsp+38h] [rbp-10h]
  unsigned __int16 *v13; // [rsp+58h] [rbp+10h] BYREF

  v13 = (unsigned __int16 *)WTL::_atltmpPchNil;
  v9 = 0;
  v10 = 0;
  v11 = 0;
  v12 = 0;
  (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)CSingletonPtr<CWlanProfileStore>::s_pInstance + 72LL))(
    CSingletonPtr<CWlanProfileStore>::s_pInstance,
    &v9);
  if ( v10 <= 1 )
    v3 = (v10 != 1) + 20006;
  else
    v3 = 20005;
  WTL::CString::LoadStringW((WTL::CString *)&v13, v3);
  v4 = v13;
  v5 = *((int *)v13 - 2);
  v6 = (unsigned __int16 *)CoTaskMemAlloc(2 * v5 + 2);
  *a2 = v6;
  if ( v6 )
    v7 = StringCchCopyW(v6, v5 + 1, v4);
  else
    v7 = -2147024882;
  ATL::CAtlArray<CAdapter,ATL::CElementTraits<CAdapter>>::~CAtlArray<CAdapter,ATL::CElementTraits<CAdapter>>(&v9);
  WTL::CString::~CString((WTL::CString *)&v13);
  return v7;
}

```

## disassembly

```asm
0x18000ea60  mov     r11, rsp
0x18000ea63  mov     [r11+8], rbx
0x18000ea67  mov     [r11+18h], rsi
0x18000ea6b  push    rdi
0x18000ea6c  sub     rsp, 40h
0x18000ea70  mov     rsi, rdx
0x18000ea73  mov     rax, cs:?_atltmpPchNil@WTL@@3PEBGEB; ushort const * const WTL::_atltmpPchNil
0x18000ea7a  mov     [r11+10h], rax
0x18000ea7e  mov     qword ptr [r11-28h], 0
0x18000ea86  mov     qword ptr [r11-20h], 0
0x18000ea8e  mov     qword ptr [r11-18h], 0
0x18000ea96  mov     [rsp+48h+var_10], 0
0x18000ea9e  mov     rcx, cs:?s_pInstance@?$CSingletonPtr@VCWlanProfileStore@@@@0PEAVCWlanProfileStore@@EA; CWlanProfileStore * CSingletonPtr<CWlanProfileStore>::s_pInstance
0x18000eaa5  mov     rax, [rcx]
0x18000eaa8  lea     rdx, [r11-28h]
0x18000eaac  mov     rax, [rax+48h]
0x18000eab0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eab5  cmp     [rsp+48h+var_20], 1
0x18000eabb  jbe     short loc_18000EAC4
0x18000eabd  mov     edx, 4E25h
0x18000eac2  jmp     short loc_18000EAD5
0x18000eac4  xor     edx, edx
0x18000eac6  cmp     [rsp+48h+var_20], 1
0x18000eacc  setnz   dl
0x18000eacf  add     edx, 4E26h; uID
0x18000ead5  lea     rcx, [rsp+48h+arg_8]; this
0x18000eada  call    ?LoadStringW@CString@WTL@@QEAAHI@Z; WTL::CString::LoadStringW(uint)
0x18000eadf  mov     rbx, [rsp+48h+arg_8]
0x18000eae4  movsxd  rdi, dword ptr [rbx-8]
0x18000eae8  lea     rcx, ds:2[rdi*2]; cb
0x18000eaf0  call    cs:__imp_CoTaskMemAlloc
0x18000eaf6  mov     [rsi], rax
0x18000eaf9  test    rax, rax
0x18000eafc  jnz     short loc_18000EB05
0x18000eafe  mov     ebx, 8007000Eh
0x18000eb03  jmp     short loc_18000EB16
0x18000eb05  lea     rdx, [rdi+1]; unsigned __int64
0x18000eb09  mov     r8, rbx; unsigned __int16 *
0x18000eb0c  mov     rcx, rax; unsigned __int16 *
0x18000eb0f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000eb14  mov     ebx, eax
0x18000eb16  lea     rcx, [rsp+48h+var_28]
0x18000eb1b  call    ??1?$CAtlArray@VCAdapter@@V?$CElementTraits@VCAdapter@@@ATL@@@ATL@@QEAA@XZ; ATL::CAtlArray<CAdapter,ATL::CElementTraits<CAdapter>>::~CAtlArray<CAdapter,ATL::CElementTraits<CAdapter>>(void)
0x18000eb20  nop
0x18000eb21  lea     rcx, [rsp+48h+arg_8]; this
0x18000eb26  call    ??1CString@WTL@@QEAA@XZ; WTL::CString::~CString(void)
0x18000eb2b  mov     eax, ebx
0x18000eb2d  mov     rbx, [rsp+48h+arg_0]
0x18000eb32  mov     rsi, [rsp+48h+arg_10]
0x18000eb37  add     rsp, 40h
0x18000eb3b  pop     rdi
0x18000eb3c  retn
```
