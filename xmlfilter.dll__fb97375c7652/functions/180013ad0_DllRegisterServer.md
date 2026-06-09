# DllRegisterServer

- ea: `0x180013ad0`
- end: `0x180013bc2`
- name: `DllRegisterServer`
- size: `242`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180010dcc`
- `0x180011294`
- `0x180013ad0`
- `0x180017010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
HRESULT __stdcall DllRegisterServer()
{
  const wchar_t *v0; // rdx
  __int64 v1; // rbx
  HRESULT result; // eax
  const struct ATL::_ATL_CATMAP_ENTRY *v3; // rax
  __int64 *v4; // rbx
  __int64 *i; // rcx
  __int64 v6; // rdi
  const struct ATL::_ATL_CATMAP_ENTRY *v7; // rax

  v1 = qword_180021C98;
  if ( qword_180021C98 )
  {
    while ( *(_QWORD *)v1 )
    {
      result = (*(__int64 (__fastcall **)(__int64))(v1 + 8))(1);
      if ( result < 0 )
        return result;
      v3 = (const struct ATL::_ATL_CATMAP_ENTRY *)(*(__int64 (**)(void))(v1 + 56))();
      result = ATL::AtlRegisterClassCategoriesHelper(*(GUID **)v1, v3, 1);
      if ( result < 0 )
        return result;
      v1 += 72;
    }
  }
  v4 = off_180021270[0];
  for ( i = off_180021278; v4 < i; ++v4 )
  {
    v6 = *v4;
    if ( *v4 )
    {
      result = (*(__int64 (__fastcall **)(__int64))(v6 + 8))(1);
      if ( result < 0 )
        return result;
      v7 = (const struct ATL::_ATL_CATMAP_ENTRY *)(*(__int64 (**)(void))(v6 + 56))();
      result = ATL::AtlRegisterClassCategoriesHelper(*(GUID **)v6, v7, 1);
      if ( result < 0 )
        return result;
      i = off_180021278;
    }
  }
  result = ATL::AtlRegisterTypeLib(off_180021268, v0);
  if ( result >= 0 )
  {
    if ( ATL::_pPerfRegFunc )
      return ((__int64 (__fastcall *)(HMODULE))ATL::_pPerfRegFunc)(hModule);
  }
  return result;
}

```

## disassembly

```asm
0x180013ad0  mov     [rsp+arg_0], rbx
0x180013ad5  push    rdi
0x180013ad6  sub     rsp, 20h
0x180013ada  mov     rbx, cs:qword_180021C98
0x180013ae1  test    rbx, rbx
0x180013ae4  jz      short loc_180013B2A
0x180013ae6  jmp     short loc_180013B24
0x180013ae8  mov     ecx, 1
0x180013aed  mov     rax, [rbx+8]
0x180013af1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013af6  test    eax, eax
0x180013af8  js      loc_180013BB7
0x180013afe  mov     rax, [rbx+38h]
0x180013b02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013b07  mov     r8d, 1; int
0x180013b0d  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x180013b10  mov     rcx, [rbx]; rguid
0x180013b13  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x180013b18  test    eax, eax
0x180013b1a  js      loc_180013BB7
0x180013b20  add     rbx, 48h ; 'H'
0x180013b24  cmp     qword ptr [rbx], 0
0x180013b28  jnz     short loc_180013AE8
0x180013b2a  xor     eax, eax
0x180013b2c  mov     rbx, cs:off_180021270
0x180013b33  mov     rcx, cs:off_180021278
0x180013b3a  cmp     rbx, rcx
0x180013b3d  jnb     short loc_180013B8B
0x180013b3f  mov     rdi, [rbx]
0x180013b42  test    rdi, rdi
0x180013b45  jz      short loc_180013B7E
0x180013b47  mov     ecx, 1
0x180013b4c  mov     rax, [rdi+8]
0x180013b50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013b55  test    eax, eax
0x180013b57  js      short loc_180013BB7
0x180013b59  mov     rax, [rdi+38h]
0x180013b5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013b62  mov     r8d, 1; int
0x180013b68  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x180013b6b  mov     rcx, [rdi]; rguid
0x180013b6e  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x180013b73  test    eax, eax
0x180013b75  js      short loc_180013BB7
0x180013b77  mov     rcx, cs:off_180021278
0x180013b7e  add     rbx, 8
0x180013b82  cmp     rbx, rcx
0x180013b85  jb      short loc_180013B3F
0x180013b87  test    eax, eax
0x180013b89  js      short loc_180013BB7
0x180013b8b  mov     rcx, cs:off_180021268; HINSTANCE
0x180013b92  call    ?AtlRegisterTypeLib@ATL@@YAJPEAUHINSTANCE__@@PEB_W@Z; ATL::AtlRegisterTypeLib(HINSTANCE__ *,wchar_t const *)
0x180013b97  test    eax, eax
0x180013b99  js      short loc_180013BB7
0x180013b9b  mov     rdx, cs:?_pPerfRegFunc@ATL@@3P6AJPEAUHINSTANCE__@@@ZEA; long (*ATL::_pPerfRegFunc)(HINSTANCE__ *)
0x180013ba2  test    rdx, rdx
0x180013ba5  jz      short loc_180013BB7
0x180013ba7  mov     rcx, cs:hModule
0x180013bae  mov     rax, rdx
0x180013bb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013bb6  nop
0x180013bb7  mov     rbx, [rsp+28h+arg_0]
0x180013bbc  add     rsp, 20h
0x180013bc0  pop     rdi
0x180013bc1  retn
```
