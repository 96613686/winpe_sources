# ATL::CAtlComModule::UnregisterServer(int,_GUID const *)

- ea: `0x1800085d4`
- end: `0x180008713`
- name: `?UnregisterServer@CAtlComModule@ATL@@QEAAJHPEBU_GUID@@@Z`
- size: `319`
- prototype: `__int64 __fastcall(ATL::CAtlComModule *__hidden this, int, const struct _GUID *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180008ab0`

## callees

- `0x180007b54`
- `0x180007d28`
- `0x1800085d4`
- `0x18000d010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800086f7`
- `OLEAUT32!__imp_SysFreeString` at `0x1800086f7`
- `OLEAUT32!__imp_UnRegisterTypeLib` at `0x1800086bc`
- `OLEAUT32!__imp_UnRegisterTypeLib` at `0x1800086bc`

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
  v3 = off_180012140;
  for ( i = off_180012148; v3 < (struct ATL::_ATL_OBJMAP_ENTRY30 **)i; ++v3 )
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
      i = off_180012148;
    }
  }
  bstrString = 0;
  v10 = 0;
  v7 = ATL::AtlLoadTypeLib(off_180012138, a2, &bstrString, &v10);
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
0x1800085d4  mov     [rsp-18h+arg_8], rbx
0x1800085d9  mov     [rsp-18h+arg_10], r8
0x1800085de  mov     [rsp-18h+libID], rcx
0x1800085e3  push    rbp
0x1800085e4  push    rsi
0x1800085e5  push    rdi
0x1800085e6  mov     rbp, rsp
0x1800085e9  sub     rsp, 30h
0x1800085ed  mov     rdi, cs:off_180012140
0x1800085f4  xor     ebx, ebx
0x1800085f6  mov     rax, cs:off_180012148
0x1800085fd  cmp     rdi, rax
0x180008600  jnb     short loc_180008658
0x180008602  mov     rsi, [rdi]
0x180008605  test    rsi, rsi
0x180008608  jz      short loc_180008647
0x18000860a  mov     rax, [rsi+38h]
0x18000860e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008613  mov     rcx, [rsi]; rguid
0x180008616  xor     r8d, r8d; int
0x180008619  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x18000861c  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x180008621  mov     ebx, eax
0x180008623  test    eax, eax
0x180008625  js      loc_180008703
0x18000862b  mov     rax, [rsi+8]
0x18000862f  xor     ecx, ecx
0x180008631  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008636  mov     ebx, eax
0x180008638  test    eax, eax
0x18000863a  js      loc_180008703
0x180008640  mov     rax, cs:off_180012148
0x180008647  add     rdi, 8
0x18000864b  cmp     rdi, rax
0x18000864e  jb      short loc_180008602
0x180008650  test    ebx, ebx
0x180008652  js      loc_180008703
0x180008658  mov     rcx, cs:off_180012138; HINSTANCE
0x18000865f  lea     r9, [rbp+arg_10]; struct ITypeLib **
0x180008663  lea     r8, [rbp+bstrString]; unsigned __int16 **
0x180008667  mov     [rbp+bstrString], 0
0x18000866f  mov     [rbp+arg_10], 0
0x180008677  call    ?AtlLoadTypeLib@ATL@@YAJPEAUHINSTANCE__@@PEBGPEAPEAGPEAPEAUITypeLib@@@Z; ATL::AtlLoadTypeLib(HINSTANCE__ *,ushort const *,ushort * *,ITypeLib * *)
0x18000867c  mov     ebx, eax
0x18000867e  test    eax, eax
0x180008680  js      short loc_1800086DE
0x180008682  mov     rcx, [rbp+arg_10]
0x180008686  lea     rdx, [rbp+libID]
0x18000868a  mov     [rbp+libID], 0
0x180008692  mov     rax, [rcx]
0x180008695  mov     rax, [rax+38h]
0x180008699  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000869e  mov     ebx, eax
0x1800086a0  test    eax, eax
0x1800086a2  js      short loc_1800086DE
0x1800086a4  mov     rcx, [rbp+libID]; libID
0x1800086a8  mov     eax, [rcx+14h]
0x1800086ab  mov     r9d, [rcx+10h]; lcid
0x1800086af  movzx   r8d, word ptr [rcx+1Ah]; wVerMinor
0x1800086b4  movzx   edx, word ptr [rcx+18h]; wVerMajor
0x1800086b8  mov     [rsp+30h+syskind], eax; syskind
0x1800086bc  call    cs:__imp_UnRegisterTypeLib
0x1800086c3  nop     dword ptr [rax+rax+00h]
0x1800086c8  mov     rcx, [rbp+arg_10]
0x1800086cc  mov     ebx, eax
0x1800086ce  mov     rdx, [rbp+libID]
0x1800086d2  mov     rax, [rcx]
0x1800086d5  mov     rax, [rax+60h]
0x1800086d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800086de  mov     rcx, [rbp+arg_10]
0x1800086e2  test    rcx, rcx
0x1800086e5  jz      short loc_1800086F3
0x1800086e7  mov     rax, [rcx]
0x1800086ea  mov     rax, [rax+10h]
0x1800086ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800086f3  mov     rcx, [rbp+bstrString]; bstrString
0x1800086f7  call    cs:__imp_SysFreeString
0x1800086fe  nop     dword ptr [rax+rax+00h]
0x180008703  mov     eax, ebx
0x180008705  mov     rbx, [rsp+30h+arg_8]
0x18000870a  add     rsp, 30h
0x18000870e  pop     rdi
0x18000870f  pop     rsi
0x180008710  pop     rbp
0x180008711  retn
```
