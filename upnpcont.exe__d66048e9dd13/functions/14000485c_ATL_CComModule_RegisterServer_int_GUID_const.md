# ATL::CComModule::RegisterServer(int,_GUID const *)

- ea: `0x14000485c`
- end: `0x14000494d`
- name: `?RegisterServer@CComModule@ATL@@QEAAJHPEBU_GUID@@@Z`
- size: `241`
- prototype: `__int64 __fastcall(ATL::CComModule *this, const unsigned __int16 *, const struct _GUID *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140005c80`

## callees

- `0x140002bfc`
- `0x1400030b8`
- `0x14000485c`
- `0x140007010`

## pseudocode

```c
__int64 __fastcall ATL::CComModule::RegisterServer(
        ATL::CComModule *this,
        const unsigned __int16 *a2,
        const struct _GUID *a3)
{
  __int64 v3; // rbx
  __int64 result; // rax
  const struct ATL::_ATL_CATMAP_ENTRY *v5; // rax
  __int64 *v6; // rbx
  __int64 *i; // rcx
  __int64 v8; // rdi
  const struct ATL::_ATL_CATMAP_ENTRY *v9; // rax

  v3 = qword_14000B378;
  if ( qword_14000B378 )
  {
    while ( *(_QWORD *)v3 )
    {
      result = (*(__int64 (__fastcall **)(__int64))(v3 + 8))(1);
      if ( (int)result < 0 )
        return result;
      v5 = (const struct ATL::_ATL_CATMAP_ENTRY *)(*(__int64 (**)(void))(v3 + 56))();
      result = ATL::AtlRegisterClassCategoriesHelper(*(GUID **)v3, v5, 1);
      if ( (int)result < 0 )
        return result;
      v3 += 72;
    }
  }
  v6 = off_14000B0B0[0];
  for ( i = off_14000B0B8; v6 < i; ++v6 )
  {
    v8 = *v6;
    if ( *v6 )
    {
      result = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, const struct _GUID *))(v8 + 8))(1, a2, a3);
      if ( (int)result < 0 )
        return result;
      v9 = (const struct ATL::_ATL_CATMAP_ENTRY *)(*(__int64 (**)(void))(v8 + 56))();
      result = ATL::AtlRegisterClassCategoriesHelper(*(GUID **)v8, v9, 1);
      if ( (int)result < 0 )
        return result;
      i = off_14000B0B8;
    }
  }
  result = ATL::AtlRegisterTypeLib(off_14000B0A8, a2);
  if ( (int)result >= 0 )
  {
    if ( ATL::_pPerfRegFunc )
      return ((__int64 (__fastcall *)(HMODULE))ATL::_pPerfRegFunc)(hModule);
  }
  return result;
}

```

## disassembly

```asm
0x14000485c  mov     [rsp+arg_0], rbx
0x140004861  push    rdi
0x140004862  sub     rsp, 20h
0x140004866  mov     rbx, cs:qword_14000B378
0x14000486d  test    rbx, rbx
0x140004870  jz      short loc_1400048B6
0x140004872  jmp     short loc_1400048B0
0x140004874  mov     rax, [rbx+8]
0x140004878  mov     ecx, 1
0x14000487d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004882  test    eax, eax
0x140004884  js      loc_140004942
0x14000488a  mov     rax, [rbx+38h]
0x14000488e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004893  mov     rcx, [rbx]; rguid
0x140004896  mov     r8d, 1; int
0x14000489c  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x14000489f  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x1400048a4  test    eax, eax
0x1400048a6  js      loc_140004942
0x1400048ac  add     rbx, 48h ; 'H'
0x1400048b0  cmp     qword ptr [rbx], 0
0x1400048b4  jnz     short loc_140004874
0x1400048b6  mov     rbx, cs:off_14000B0B0
0x1400048bd  xor     eax, eax
0x1400048bf  mov     rcx, cs:off_14000B0B8
0x1400048c6  cmp     rbx, rcx
0x1400048c9  jnb     short loc_140004917
0x1400048cb  mov     rdi, [rbx]
0x1400048ce  test    rdi, rdi
0x1400048d1  jz      short loc_14000490A
0x1400048d3  mov     rax, [rdi+8]
0x1400048d7  mov     ecx, 1
0x1400048dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400048e1  test    eax, eax
0x1400048e3  js      short loc_140004942
0x1400048e5  mov     rax, [rdi+38h]
0x1400048e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400048ee  mov     rcx, [rdi]; rguid
0x1400048f1  mov     r8d, 1; int
0x1400048f7  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x1400048fa  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x1400048ff  test    eax, eax
0x140004901  js      short loc_140004942
0x140004903  mov     rcx, cs:off_14000B0B8
0x14000490a  add     rbx, 8
0x14000490e  cmp     rbx, rcx
0x140004911  jb      short loc_1400048CB
0x140004913  test    eax, eax
0x140004915  js      short loc_140004942
0x140004917  mov     rcx, cs:off_14000B0A8; HINSTANCE
0x14000491e  call    ?AtlRegisterTypeLib@ATL@@YAJPEAUHINSTANCE__@@PEBG@Z; ATL::AtlRegisterTypeLib(HINSTANCE__ *,ushort const *)
0x140004923  test    eax, eax
0x140004925  js      short loc_140004942
0x140004927  mov     rdx, cs:?_pPerfRegFunc@ATL@@3P6AJPEAUHINSTANCE__@@@ZEA; long (*ATL::_pPerfRegFunc)(HINSTANCE__ *)
0x14000492e  test    rdx, rdx
0x140004931  jz      short loc_140004942
0x140004933  mov     rcx, cs:hModule
0x14000493a  mov     rax, rdx
0x14000493d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004942  mov     rbx, [rsp+28h+arg_0]
0x140004947  add     rsp, 20h
0x14000494b  pop     rdi
0x14000494c  retn
```
