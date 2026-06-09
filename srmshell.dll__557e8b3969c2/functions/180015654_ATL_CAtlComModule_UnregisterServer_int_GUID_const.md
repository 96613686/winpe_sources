# ATL::CAtlComModule::UnregisterServer(int,_GUID const *)

- ea: `0x180015654`
- end: `0x180015788`
- name: `?UnregisterServer@CAtlComModule@ATL@@QEAAJHPEBU_GUID@@@Z`
- size: `308`
- prototype: `__int64 __fastcall(GUID *this, const unsigned __int16 *, struct ITypeLib *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180015d20`

## callees

- `0x180012e58`
- `0x180013004`
- `0x180015654`
- `0x180020010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180015773`
- `OLEAUT32!__imp_SysFreeString` at `0x180015773`
- `OLEAUT32!__imp_UnRegisterTypeLib` at `0x18001573c`
- `OLEAUT32!__imp_UnRegisterTypeLib` at `0x18001573c`

## pseudocode

```c
__int64 __fastcall ATL::CAtlComModule::UnregisterServer(GUID *this, const unsigned __int16 *a2, struct ITypeLib *a3)
{
  struct ATL::_ATL_OBJMAP_ENTRY30 **v3; // rdi
  __int64 *i; // rax
  struct ATL::_ATL_OBJMAP_ENTRY30 *v5; // rsi
  const struct ATL::_ATL_CATMAP_ENTRY *v6; // rax
  HRESULT v7; // ebx
  GUID *libID; // [rsp+50h] [rbp+20h] BYREF
  struct ITypeLib *v10; // [rsp+60h] [rbp+30h] BYREF
  BSTR bstrString; // [rsp+68h] [rbp+38h] BYREF

  v10 = a3;
  libID = this;
  v3 = off_18002B290;
  for ( i = off_18002B298; v3 < (struct ATL::_ATL_OBJMAP_ENTRY30 **)i; ++v3 )
  {
    v5 = *v3;
    if ( *v3 )
    {
      v6 = (const struct ATL::_ATL_CATMAP_ENTRY *)(*((__int64 (**)(void))v5 + 7))();
      v7 = ATL::AtlRegisterClassCategoriesHelper(*(GUID **)v5, v6, 0);
      if ( v7 < 0 )
        return (unsigned int)v7;
      v7 = (*((__int64 (__fastcall **)(_QWORD))v5 + 1))(0);
      if ( v7 < 0 )
        return (unsigned int)v7;
      i = off_18002B298;
    }
  }
  bstrString = 0;
  v10 = 0;
  v7 = ATL::AtlLoadTypeLib(off_18002B288, a2, &bstrString, &v10);
  if ( v7 >= 0 )
  {
    libID = 0;
    v7 = ((__int64 (__fastcall *)(struct ITypeLib *, GUID **))v10->lpVtbl->GetLibAttr)(v10, &libID);
    if ( v7 >= 0 )
    {
      v7 = UnRegisterTypeLib(
             libID,
             *(_WORD *)libID[1].Data4,
             *(_WORD *)&libID[1].Data4[2],
             libID[1].Data1,
             *(SYSKIND *)&libID[1].Data2);
      ((void (__fastcall *)(struct ITypeLib *, GUID *))v10->lpVtbl->ReleaseTLibAttr)(v10, libID);
    }
  }
  if ( v10 )
    ((void (__fastcall *)(struct ITypeLib *))v10->lpVtbl->Release)(v10);
  SysFreeString(bstrString);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180015654  mov     [rsp-18h+arg_8], rbx
0x180015659  mov     [rsp-18h+arg_10], r8
0x18001565e  mov     [rsp-18h+libID], rcx
0x180015663  push    rbp
0x180015664  push    rsi
0x180015665  push    rdi
0x180015666  mov     rbp, rsp
0x180015669  sub     rsp, 30h
0x18001566d  xor     ebx, ebx
0x18001566f  mov     rdi, cs:off_18002B290
0x180015676  mov     rax, cs:off_18002B298
0x18001567d  cmp     rdi, rax
0x180015680  jnb     short loc_1800156D8
0x180015682  mov     rsi, [rdi]
0x180015685  test    rsi, rsi
0x180015688  jz      short loc_1800156C7
0x18001568a  mov     rax, [rsi+38h]
0x18001568e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015693  xor     r8d, r8d; int
0x180015696  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x180015699  mov     rcx, [rsi]; rguid
0x18001569c  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x1800156a1  mov     ebx, eax
0x1800156a3  test    eax, eax
0x1800156a5  js      loc_180015779
0x1800156ab  xor     ecx, ecx
0x1800156ad  mov     rax, [rsi+8]
0x1800156b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800156b6  mov     ebx, eax
0x1800156b8  test    eax, eax
0x1800156ba  js      loc_180015779
0x1800156c0  mov     rax, cs:off_18002B298
0x1800156c7  add     rdi, 8
0x1800156cb  cmp     rdi, rax
0x1800156ce  jb      short loc_180015682
0x1800156d0  test    ebx, ebx
0x1800156d2  js      loc_180015779
0x1800156d8  mov     rcx, cs:off_18002B288; HINSTANCE
0x1800156df  mov     [rbp+bstrString], 0
0x1800156e7  mov     [rbp+arg_10], 0
0x1800156ef  lea     r9, [rbp+arg_10]; struct ITypeLib **
0x1800156f3  lea     r8, [rbp+bstrString]; unsigned __int16 **
0x1800156f7  call    ?AtlLoadTypeLib@ATL@@YAJPEAUHINSTANCE__@@PEBGPEAPEAGPEAPEAUITypeLib@@@Z; ATL::AtlLoadTypeLib(HINSTANCE__ *,ushort const *,ushort * *,ITypeLib * *)
0x1800156fc  mov     ebx, eax
0x1800156fe  test    eax, eax
0x180015700  js      short loc_180015759
0x180015702  mov     [rbp+libID], 0
0x18001570a  mov     rcx, [rbp+arg_10]
0x18001570e  mov     rax, [rcx]
0x180015711  lea     rdx, [rbp+libID]
0x180015715  mov     rax, [rax+38h]
0x180015719  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001571e  mov     ebx, eax
0x180015720  test    eax, eax
0x180015722  js      short loc_180015759
0x180015724  mov     rcx, [rbp+libID]; libID
0x180015728  mov     eax, [rcx+14h]
0x18001572b  mov     [rsp+30h+syskind], eax; syskind
0x18001572f  mov     r9d, [rcx+10h]; lcid
0x180015733  movzx   r8d, word ptr [rcx+1Ah]; wVerMinor
0x180015738  movzx   edx, word ptr [rcx+18h]; wVerMajor
0x18001573c  call    cs:__imp_UnRegisterTypeLib
0x180015742  mov     ebx, eax
0x180015744  mov     rcx, [rbp+arg_10]
0x180015748  mov     rax, [rcx]
0x18001574b  mov     rdx, [rbp+libID]
0x18001574f  mov     rax, [rax+60h]
0x180015753  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015758  nop
0x180015759  mov     rcx, [rbp+arg_10]
0x18001575d  test    rcx, rcx
0x180015760  jz      short loc_18001576F
0x180015762  mov     rax, [rcx]
0x180015765  mov     rax, [rax+10h]
0x180015769  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001576e  nop
0x18001576f  mov     rcx, [rbp+bstrString]; bstrString
0x180015773  call    cs:__imp_SysFreeString
0x180015779  mov     eax, ebx
0x18001577b  mov     rbx, [rsp+30h+arg_8]
0x180015780  add     rsp, 30h
0x180015784  pop     rdi
0x180015785  pop     rsi
0x180015786  pop     rbp
0x180015787  retn
```
