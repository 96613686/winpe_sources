# ATL::CAtlComModule::UnregisterServer(int,_GUID const *)

- ea: `0x1400053a0`
- end: `0x1400054d2`
- name: `?UnregisterServer@CAtlComModule@ATL@@QEAAJHPEBU_GUID@@@Z`
- size: `306`
- prototype: `__int64 __fastcall(GUID *this, const unsigned __int16 *, struct ITypeLib *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140005c80`

## callees

- `0x140002a54`
- `0x140002bfc`
- `0x1400053a0`
- `0x140007010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1400054bd`
- `OLEAUT32!__imp_SysFreeString` at `0x1400054bd`
- `OLEAUT32!__imp_UnRegisterTypeLib` at `0x140005488`
- `OLEAUT32!__imp_UnRegisterTypeLib` at `0x140005488`

## pseudocode

```c
__int64 __fastcall ATL::CAtlComModule::UnregisterServer(GUID *this, const unsigned __int16 *a2, struct ITypeLib *a3)
{
  __int64 *v3; // rdi
  __int64 *i; // rax
  __int64 v5; // rsi
  const struct ATL::_ATL_CATMAP_ENTRY *v6; // rax
  HRESULT v7; // ebx
  GUID *libID; // [rsp+50h] [rbp+20h] BYREF
  struct ITypeLib *v10; // [rsp+60h] [rbp+30h] BYREF
  BSTR bstrString; // [rsp+68h] [rbp+38h] BYREF

  v10 = a3;
  libID = this;
  v3 = off_14000B0B0[0];
  for ( i = off_14000B0B8; v3 < i; ++v3 )
  {
    v5 = *v3;
    if ( *v3 )
    {
      v6 = (const struct ATL::_ATL_CATMAP_ENTRY *)(*(__int64 (**)(void))(v5 + 56))();
      v7 = ATL::AtlRegisterClassCategoriesHelper(*(GUID **)v5, v6, 0);
      if ( v7 < 0 )
        return (unsigned int)v7;
      v7 = (*(__int64 (__fastcall **)(_QWORD))(v5 + 8))(0);
      if ( v7 < 0 )
        return (unsigned int)v7;
      i = off_14000B0B8;
    }
  }
  bstrString = 0;
  v10 = 0;
  v7 = ATL::AtlLoadTypeLib(off_14000B0A8, a2, &bstrString, &v10);
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
0x1400053a0  mov     [rsp-18h+arg_8], rbx
0x1400053a5  mov     [rsp-18h+arg_10], r8
0x1400053aa  mov     [rsp-18h+libID], rcx
0x1400053af  push    rbp
0x1400053b0  push    rsi
0x1400053b1  push    rdi
0x1400053b2  mov     rbp, rsp
0x1400053b5  sub     rsp, 30h
0x1400053b9  mov     rdi, cs:off_14000B0B0
0x1400053c0  xor     ebx, ebx
0x1400053c2  mov     rax, cs:off_14000B0B8
0x1400053c9  cmp     rdi, rax
0x1400053cc  jnb     short loc_140005424
0x1400053ce  mov     rsi, [rdi]
0x1400053d1  test    rsi, rsi
0x1400053d4  jz      short loc_140005413
0x1400053d6  mov     rax, [rsi+38h]
0x1400053da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400053df  mov     rcx, [rsi]; rguid
0x1400053e2  xor     r8d, r8d; int
0x1400053e5  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x1400053e8  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x1400053ed  mov     ebx, eax
0x1400053ef  test    eax, eax
0x1400053f1  js      loc_1400054C3
0x1400053f7  mov     rax, [rsi+8]
0x1400053fb  xor     ecx, ecx
0x1400053fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005402  mov     ebx, eax
0x140005404  test    eax, eax
0x140005406  js      loc_1400054C3
0x14000540c  mov     rax, cs:off_14000B0B8
0x140005413  add     rdi, 8
0x140005417  cmp     rdi, rax
0x14000541a  jb      short loc_1400053CE
0x14000541c  test    ebx, ebx
0x14000541e  js      loc_1400054C3
0x140005424  mov     rcx, cs:off_14000B0A8; HINSTANCE
0x14000542b  lea     r9, [rbp+arg_10]; struct ITypeLib **
0x14000542f  lea     r8, [rbp+bstrString]; unsigned __int16 **
0x140005433  mov     [rbp+bstrString], 0
0x14000543b  mov     [rbp+arg_10], 0
0x140005443  call    ?AtlLoadTypeLib@ATL@@YAJPEAUHINSTANCE__@@PEBGPEAPEAGPEAPEAUITypeLib@@@Z; ATL::AtlLoadTypeLib(HINSTANCE__ *,ushort const *,ushort * *,ITypeLib * *)
0x140005448  mov     ebx, eax
0x14000544a  test    eax, eax
0x14000544c  js      short loc_1400054A4
0x14000544e  mov     rcx, [rbp+arg_10]
0x140005452  lea     rdx, [rbp+libID]
0x140005456  mov     [rbp+libID], 0
0x14000545e  mov     rax, [rcx]
0x140005461  mov     rax, [rax+38h]
0x140005465  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000546a  mov     ebx, eax
0x14000546c  test    eax, eax
0x14000546e  js      short loc_1400054A4
0x140005470  mov     rcx, [rbp+libID]; libID
0x140005474  mov     eax, [rcx+14h]
0x140005477  mov     r9d, [rcx+10h]; lcid
0x14000547b  movzx   r8d, word ptr [rcx+1Ah]; wVerMinor
0x140005480  movzx   edx, word ptr [rcx+18h]; wVerMajor
0x140005484  mov     [rsp+30h+syskind], eax; syskind
0x140005488  call    cs:__imp_UnRegisterTypeLib
0x14000548e  mov     rcx, [rbp+arg_10]
0x140005492  mov     ebx, eax
0x140005494  mov     rdx, [rbp+libID]
0x140005498  mov     rax, [rcx]
0x14000549b  mov     rax, [rax+60h]
0x14000549f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400054a4  mov     rcx, [rbp+arg_10]
0x1400054a8  test    rcx, rcx
0x1400054ab  jz      short loc_1400054B9
0x1400054ad  mov     rax, [rcx]
0x1400054b0  mov     rax, [rax+10h]
0x1400054b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400054b9  mov     rcx, [rbp+bstrString]; bstrString
0x1400054bd  call    cs:__imp_SysFreeString
0x1400054c3  mov     eax, ebx
0x1400054c5  mov     rbx, [rsp+30h+arg_8]
0x1400054ca  add     rsp, 30h
0x1400054ce  pop     rdi
0x1400054cf  pop     rsi
0x1400054d0  pop     rbp
0x1400054d1  retn
```
