# CPreflistFolder::CompareIDs(__int64,_ITEMIDLIST const *,_ITEMIDLIST const *)

- ea: `0x18000d6b0`
- end: `0x18000d82a`
- name: `?CompareIDs@CPreflistFolder@@UEAAJ_JPEFBU_ITEMIDLIST@@1@Z`
- size: `378`
- prototype: `__int64 __fastcall(CPreflistFolder *__hidden this, __int64, const struct _ITEMIDLIST *, const struct _ITEMIDLIST *)`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x18000d494`
- `0x18000d6b0`
- `0x18000d830`
- `0x1800110a4`
- `0x180027594`
- `0x180027754`
- `0x180027d84`
- `0x18002868c`
- `0x1800289a8`
- `0x180028a60`
- `0x18002d840`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CPreflistFolder::CompareIDs(
        CPreflistFolder *this,
        int a2,
        const struct _ITEMIDLIST *a3,
        const struct _ITEMIDLIST *a4)
{
  __int64 StartPosition; // rax
  __int64 v9; // rbx
  unsigned __int16 v10; // di
  __int64 *i; // rbx
  int v12; // eax
  __int128 v13; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v14; // [rsp+30h] [rbp-D0h]
  __int128 v15; // [rsp+38h] [rbp-C8h]
  int v16; // [rsp+48h] [rbp-B8h]
  _BYTE v17[232]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v18[72]; // [rsp+138h] [rbp+38h] BYREF
  _BYTE v19[96]; // [rsp+180h] [rbp+80h] BYREF
  _BYTE v20[96]; // [rsp+1E0h] [rbp+E0h] BYREF

  if ( (unsigned __int16)a2 >= 6u )
    return 2147942487LL;
  StructToProfile((CProfile *)v20, (const struct WPLDATA *)a3->mkid.abID);
  StructToProfile((CProfile *)v19, (const struct WPLDATA *)a4->mkid.abID);
  if ( a2 >= 0 )
  {
    v10 = CPreflistFolder::CompareProfiles(
            (CPreflistFolder *)((char *)this - 8),
            (const struct CProfile *)v20,
            (const struct CProfile *)v19,
            &stru_1800354C0);
  }
  else
  {
    CProfileProps::CProfileProps((CProfileProps *)v17);
    v13 = 0;
    v14 = 0;
    v15 = 0;
    v16 = 10;
    ATL::CAtlList<_InterfaceInfo *,ATL::CElementTraits<_InterfaceInfo *>>::RemoveAll(&v13);
    StartPosition = ATL::CAtlMap<_tagpropertykey,WTL::CString,CStructTraits<_tagpropertykey>,CStringTraits>::GetStartPosition(v18);
    v9 = StartPosition;
    while ( StartPosition )
    {
      ATL::CAtlList<_tagpropertykey,ATL::CElementTraits<_tagpropertykey>>::AddTail(&v13, v9);
      StartPosition = ATL::CAtlMap<_tagpropertykey,WTL::CString,CStructTraits<_tagpropertykey>,CStringTraits>::FindNextNode(
                        v18,
                        v9);
      v9 = StartPosition;
    }
    v10 = 0;
    for ( i = (__int64 *)v13; i; i = (__int64 *)*i )
    {
      v12 = CPreflistFolder::CompareProfiles(
              (CPreflistFolder *)((char *)this - 8),
              (const struct CProfile *)v20,
              (const struct CProfile *)v19,
              (const struct _tagpropertykey *)(i + 2));
      v10 = v12;
      if ( v12 )
        break;
    }
    ATL::CAtlList<_InterfaceInfo *,ATL::CElementTraits<_InterfaceInfo *>>::RemoveAll(&v13);
    CProfileProps::~CProfileProps((CProfileProps *)v17);
  }
  CProfile::~CProfile((CProfile *)v19);
  CProfile::~CProfile((CProfile *)v20);
  return v10;
}

```

## disassembly

```asm
0x18000d6b0  mov     [rsp-8+arg_8], rbx
0x18000d6b5  push    rbp
0x18000d6b6  push    rsi
0x18000d6b7  push    rdi
0x18000d6b8  lea     rbp, [rsp-150h]
0x18000d6c0  sub     rsp, 250h
0x18000d6c7  mov     rax, cs:__security_cookie
0x18000d6ce  xor     rax, rsp
0x18000d6d1  mov     [rbp+160h+var_20], rax
0x18000d6d8  mov     rdi, r9
0x18000d6db  mov     rbx, rdx
0x18000d6de  mov     rsi, rcx
0x18000d6e1  cmp     dx, 6
0x18000d6e5  jb      short loc_18000D6F1
0x18000d6e7  mov     eax, 80070057h
0x18000d6ec  jmp     loc_18000D808
0x18000d6f1  lea     rdx, [r8+2]
0x18000d6f5  lea     rcx, [rbp+160h+var_80]
0x18000d6fc  call    ?StructToProfile@@YA?AVCProfile@@AEBUWPLDATA@@@Z; StructToProfile(WPLDATA const &)
0x18000d701  nop
0x18000d702  lea     rdx, [rdi+2]
0x18000d706  lea     rcx, [rbp+160h+var_E0]
0x18000d70d  call    ?StructToProfile@@YA?AVCProfile@@AEBUWPLDATA@@@Z; StructToProfile(WPLDATA const &)
0x18000d712  nop
0x18000d713  test    ebx, ebx
0x18000d715  jns     loc_18000D7CC
0x18000d71b  lea     rcx, [rsp+260h+var_210]; this
0x18000d720  call    ??0CProfileProps@@QEAA@XZ; CProfileProps::CProfileProps(void)
0x18000d725  nop
0x18000d726  xorps   xmm0, xmm0
0x18000d729  movdqu  [rsp+260h+var_240], xmm0
0x18000d72f  mov     [rsp+260h+var_230], 0
0x18000d738  xorps   xmm1, xmm1
0x18000d73b  movdqu  [rsp+260h+var_228], xmm1
0x18000d741  mov     [rsp+260h+var_218], 0Ah
0x18000d749  lea     rcx, [rsp+260h+var_240]
0x18000d74e  call    ?RemoveAll@?$CAtlList@PEAU_InterfaceInfo@@V?$CElementTraits@PEAU_InterfaceInfo@@@ATL@@@ATL@@QEAAXXZ; ATL::CAtlList<_InterfaceInfo *,ATL::CElementTraits<_InterfaceInfo *>>::RemoveAll(void)
0x18000d753  lea     rcx, [rbp+160h+var_128]
0x18000d757  call    ?GetStartPosition@?$CAtlMap@U_tagpropertykey@@VCString@WTL@@V?$CStructTraits@U_tagpropertykey@@@@VCStringTraits@@@ATL@@QEBAPEAU__POSITION@@XZ; ATL::CAtlMap<_tagpropertykey,WTL::CString,CStructTraits<_tagpropertykey>,CStringTraits>::GetStartPosition(void)
0x18000d75c  mov     rbx, rax
0x18000d75f  jmp     short loc_18000D77E
0x18000d761  mov     rdx, rbx
0x18000d764  lea     rcx, [rsp+260h+var_240]
0x18000d769  call    ?AddTail@?$CAtlList@U_tagpropertykey@@V?$CElementTraits@U_tagpropertykey@@@ATL@@@ATL@@QEAAPEAU__POSITION@@AEBU_tagpropertykey@@@Z; ATL::CAtlList<_tagpropertykey,ATL::CElementTraits<_tagpropertykey>>::AddTail(_tagpropertykey const &)
0x18000d76e  nop
0x18000d76f  mov     rdx, rbx
0x18000d772  lea     rcx, [rbp+160h+var_128]
0x18000d776  call    ?FindNextNode@?$CAtlMap@U_tagpropertykey@@VCString@WTL@@V?$CStructTraits@U_tagpropertykey@@@@VCStringTraits@@@ATL@@AEBAPEAVCNode@12@PEAV312@@Z; ATL::CAtlMap<_tagpropertykey,WTL::CString,CStructTraits<_tagpropertykey>,CStringTraits>::FindNextNode(ATL::CAtlMap<_tagpropertykey,WTL::CString,CStructTraits<_tagpropertykey>,CStringTraits>::CNode *)
0x18000d77b  mov     rbx, rax
0x18000d77e  test    rax, rax
0x18000d781  jnz     short loc_18000D761
0x18000d783  xor     edi, edi
0x18000d785  mov     rbx, qword ptr [rsp+260h+var_240]
0x18000d78a  test    rbx, rbx
0x18000d78d  jz      short loc_18000D7B5
0x18000d78f  lea     r9, [rbx+10h]; struct _tagpropertykey *
0x18000d793  lea     rcx, [rsi-8]; this
0x18000d797  lea     r8, [rbp+160h+var_E0]; struct CProfile *
0x18000d79e  lea     rdx, [rbp+160h+var_80]; struct CProfile *
0x18000d7a5  call    ?CompareProfiles@CPreflistFolder@@IEAAHAEBVCProfile@@0AEBU_tagpropertykey@@@Z; CPreflistFolder::CompareProfiles(CProfile const &,CProfile const &,_tagpropertykey const &)
0x18000d7aa  mov     edi, eax
0x18000d7ac  test    eax, eax
0x18000d7ae  jnz     short loc_18000D7B5
0x18000d7b0  mov     rbx, [rbx]
0x18000d7b3  jmp     short loc_18000D78A
0x18000d7b5  lea     rcx, [rsp+260h+var_240]
0x18000d7ba  call    ?RemoveAll@?$CAtlList@PEAU_InterfaceInfo@@V?$CElementTraits@PEAU_InterfaceInfo@@@ATL@@@ATL@@QEAAXXZ; ATL::CAtlList<_InterfaceInfo *,ATL::CElementTraits<_InterfaceInfo *>>::RemoveAll(void)
0x18000d7bf  nop
0x18000d7c0  lea     rcx, [rsp+260h+var_210]; this
0x18000d7c5  call    ??1CProfileProps@@UEAA@XZ; CProfileProps::~CProfileProps(void)
0x18000d7ca  jmp     short loc_18000D7EC
0x18000d7cc  lea     rcx, [rsi-8]; this
0x18000d7d0  lea     r9, stru_1800354C0; struct _tagpropertykey *
0x18000d7d7  lea     r8, [rbp+160h+var_E0]; struct CProfile *
0x18000d7de  lea     rdx, [rbp+160h+var_80]; struct CProfile *
0x18000d7e5  call    ?CompareProfiles@CPreflistFolder@@IEAAHAEBVCProfile@@0AEBU_tagpropertykey@@@Z; CPreflistFolder::CompareProfiles(CProfile const &,CProfile const &,_tagpropertykey const &)
0x18000d7ea  mov     edi, eax
0x18000d7ec  lea     rcx, [rbp+160h+var_E0]; this
0x18000d7f3  call    ??1CProfile@@UEAA@XZ; CProfile::~CProfile(void)
0x18000d7f8  nop
0x18000d7f9  lea     rcx, [rbp+160h+var_80]; this
0x18000d800  call    ??1CProfile@@UEAA@XZ; CProfile::~CProfile(void)
0x18000d805  movzx   eax, di
0x18000d808  mov     rcx, [rbp+160h+var_20]
0x18000d80f  xor     rcx, rsp; StackCookie
0x18000d812  call    __security_check_cookie
0x18000d817  mov     rbx, [rsp+260h+arg_8]
0x18000d81f  add     rsp, 250h
0x18000d826  pop     rdi
0x18000d827  pop     rsi
0x18000d828  pop     rbp
0x18000d829  retn
```
