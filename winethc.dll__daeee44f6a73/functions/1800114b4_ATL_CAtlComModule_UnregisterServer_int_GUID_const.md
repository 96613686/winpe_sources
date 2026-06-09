# ATL::CAtlComModule::UnregisterServer(int,_GUID const *)

- ea: `0x1800114b4`
- end: `0x1800115f3`
- name: `?UnregisterServer@CAtlComModule@ATL@@QEAAJHPEBU_GUID@@@Z`
- size: `319`
- prototype: `__int64 __fastcall(ATL::CAtlComModule *__hidden this, int, const struct _GUID *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180011910`

## callees

- `0x180010ae4`
- `0x180010cb8`
- `0x1800114b4`
- `0x180014010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800115d7`
- `OLEAUT32!__imp_SysFreeString` at `0x1800115d7`
- `OLEAUT32!__imp_UnRegisterTypeLib` at `0x18001159c`
- `OLEAUT32!__imp_UnRegisterTypeLib` at `0x18001159c`

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
  v3 = off_18001B540;
  for ( i = off_18001B548; v3 < (struct ATL::_ATL_OBJMAP_ENTRY30 **)i; ++v3 )
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
      i = off_18001B548;
    }
  }
  bstrString = 0;
  v10 = 0;
  v7 = ATL::AtlLoadTypeLib(off_18001B538, a2, &bstrString, &v10);
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
0x1800114b4  mov     [rsp-18h+arg_8], rbx
0x1800114b9  mov     [rsp-18h+arg_10], r8
0x1800114be  mov     [rsp-18h+libID], rcx
0x1800114c3  push    rbp
0x1800114c4  push    rsi
0x1800114c5  push    rdi
0x1800114c6  mov     rbp, rsp
0x1800114c9  sub     rsp, 30h
0x1800114cd  mov     rdi, cs:off_18001B540
0x1800114d4  xor     ebx, ebx
0x1800114d6  mov     rax, cs:off_18001B548
0x1800114dd  cmp     rdi, rax
0x1800114e0  jnb     short loc_180011538
0x1800114e2  mov     rsi, [rdi]
0x1800114e5  test    rsi, rsi
0x1800114e8  jz      short loc_180011527
0x1800114ea  mov     rax, [rsi+38h]
0x1800114ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800114f3  mov     rcx, [rsi]; rguid
0x1800114f6  xor     r8d, r8d; int
0x1800114f9  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x1800114fc  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x180011501  mov     ebx, eax
0x180011503  test    eax, eax
0x180011505  js      loc_1800115E3
0x18001150b  mov     rax, [rsi+8]
0x18001150f  xor     ecx, ecx
0x180011511  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011516  mov     ebx, eax
0x180011518  test    eax, eax
0x18001151a  js      loc_1800115E3
0x180011520  mov     rax, cs:off_18001B548
0x180011527  add     rdi, 8
0x18001152b  cmp     rdi, rax
0x18001152e  jb      short loc_1800114E2
0x180011530  test    ebx, ebx
0x180011532  js      loc_1800115E3
0x180011538  mov     rcx, cs:off_18001B538; HINSTANCE
0x18001153f  lea     r9, [rbp+arg_10]; struct ITypeLib **
0x180011543  lea     r8, [rbp+bstrString]; unsigned __int16 **
0x180011547  mov     [rbp+bstrString], 0
0x18001154f  mov     [rbp+arg_10], 0
0x180011557  call    ?AtlLoadTypeLib@ATL@@YAJPEAUHINSTANCE__@@PEBGPEAPEAGPEAPEAUITypeLib@@@Z; ATL::AtlLoadTypeLib(HINSTANCE__ *,ushort const *,ushort * *,ITypeLib * *)
0x18001155c  mov     ebx, eax
0x18001155e  test    eax, eax
0x180011560  js      short loc_1800115BE
0x180011562  mov     rcx, [rbp+arg_10]
0x180011566  lea     rdx, [rbp+libID]
0x18001156a  mov     [rbp+libID], 0
0x180011572  mov     rax, [rcx]
0x180011575  mov     rax, [rax+38h]
0x180011579  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001157e  mov     ebx, eax
0x180011580  test    eax, eax
0x180011582  js      short loc_1800115BE
0x180011584  mov     rcx, [rbp+libID]; libID
0x180011588  mov     eax, [rcx+14h]
0x18001158b  mov     r9d, [rcx+10h]; lcid
0x18001158f  movzx   r8d, word ptr [rcx+1Ah]; wVerMinor
0x180011594  movzx   edx, word ptr [rcx+18h]; wVerMajor
0x180011598  mov     [rsp+30h+syskind], eax; syskind
0x18001159c  call    cs:__imp_UnRegisterTypeLib
0x1800115a3  nop     dword ptr [rax+rax+00h]
0x1800115a8  mov     rcx, [rbp+arg_10]
0x1800115ac  mov     ebx, eax
0x1800115ae  mov     rdx, [rbp+libID]
0x1800115b2  mov     rax, [rcx]
0x1800115b5  mov     rax, [rax+60h]
0x1800115b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800115be  mov     rcx, [rbp+arg_10]
0x1800115c2  test    rcx, rcx
0x1800115c5  jz      short loc_1800115D3
0x1800115c7  mov     rax, [rcx]
0x1800115ca  mov     rax, [rax+10h]
0x1800115ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800115d3  mov     rcx, [rbp+bstrString]; bstrString
0x1800115d7  call    cs:__imp_SysFreeString
0x1800115de  nop     dword ptr [rax+rax+00h]
0x1800115e3  mov     eax, ebx
0x1800115e5  mov     rbx, [rsp+30h+arg_8]
0x1800115ea  add     rsp, 30h
0x1800115ee  pop     rdi
0x1800115ef  pop     rsi
0x1800115f0  pop     rbp
0x1800115f1  retn
```
