# DllUnregisterServer

- ea: `0x180013bd0`
- end: `0x180013c94`
- name: `DllUnregisterServer`
- size: `196`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180010dcc`
- `0x180013bd0`
- `0x180017010`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
HRESULT __stdcall DllUnregisterServer()
{
  __int64 v0; // rbx
  const struct ATL::_ATL_CATMAP_ENTRY *v1; // rax
  __int64 *v2; // rbx
  __int64 *v3; // rax
  __int64 v4; // rdi
  const struct ATL::_ATL_CATMAP_ENTRY *v5; // rax

  v0 = qword_180021C98;
  if ( qword_180021C98 )
  {
    while ( *(_QWORD *)v0 )
    {
      v1 = (const struct ATL::_ATL_CATMAP_ENTRY *)(*(__int64 (**)(void))(v0 + 56))();
      if ( (int)ATL::AtlRegisterClassCategoriesHelper(*(GUID **)v0, v1, 0) < 0
        || (*(int (__fastcall **)(_QWORD))(v0 + 8))(0) < 0 )
      {
        return 0;
      }
      v0 += 72;
    }
  }
  if ( !ATL::_pPerfUnRegFunc || ATL::_pPerfUnRegFunc() >= 0 )
  {
    v2 = off_180021270[0];
    v3 = off_180021278;
    while ( v2 < v3 )
    {
      v4 = *v2;
      if ( *v2 )
      {
        v5 = (const struct ATL::_ATL_CATMAP_ENTRY *)(*(__int64 (**)(void))(v4 + 56))();
        if ( (int)ATL::AtlRegisterClassCategoriesHelper(*(GUID **)v4, v5, 0) < 0
          || (*(int (__fastcall **)(_QWORD))(v4 + 8))(0) < 0 )
        {
          return 0;
        }
        v3 = off_180021278;
      }
      ++v2;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180013bd0  mov     [rsp+arg_0], rbx
0x180013bd5  push    rdi
0x180013bd6  sub     rsp, 20h
0x180013bda  mov     rbx, cs:qword_180021C98
0x180013be1  test    rbx, rbx
0x180013be4  jz      short loc_180013C20
0x180013be6  jmp     short loc_180013C1A
0x180013be8  mov     rax, [rbx+38h]
0x180013bec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013bf1  xor     r8d, r8d; int
0x180013bf4  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x180013bf7  mov     rcx, [rbx]; rguid
0x180013bfa  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x180013bff  test    eax, eax
0x180013c01  js      loc_180013C87
0x180013c07  xor     ecx, ecx
0x180013c09  mov     rax, [rbx+8]
0x180013c0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013c12  test    eax, eax
0x180013c14  js      short loc_180013C87
0x180013c16  add     rbx, 48h ; 'H'
0x180013c1a  cmp     qword ptr [rbx], 0
0x180013c1e  jnz     short loc_180013BE8
0x180013c20  mov     rax, cs:?_pPerfUnRegFunc@ATL@@3P6AJXZEA; long (*ATL::_pPerfUnRegFunc)(void)
0x180013c27  test    rax, rax
0x180013c2a  jz      short loc_180013C35
0x180013c2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013c31  test    eax, eax
0x180013c33  js      short loc_180013C87
0x180013c35  mov     rbx, cs:off_180021270
0x180013c3c  mov     rax, cs:off_180021278
0x180013c43  jmp     short loc_180013C82
0x180013c45  mov     rdi, [rbx]
0x180013c48  test    rdi, rdi
0x180013c4b  jz      short loc_180013C7E
0x180013c4d  mov     rax, [rdi+38h]
0x180013c51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013c56  xor     r8d, r8d; int
0x180013c59  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x180013c5c  mov     rcx, [rdi]; rguid
0x180013c5f  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x180013c64  test    eax, eax
0x180013c66  js      short loc_180013C87
0x180013c68  xor     ecx, ecx
0x180013c6a  mov     rax, [rdi+8]
0x180013c6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013c73  test    eax, eax
0x180013c75  js      short loc_180013C87
0x180013c77  mov     rax, cs:off_180021278
0x180013c7e  add     rbx, 8
0x180013c82  cmp     rbx, rax
0x180013c85  jb      short loc_180013C45
0x180013c87  xor     eax, eax
0x180013c89  mov     rbx, [rsp+28h+arg_0]
0x180013c8e  add     rsp, 20h
0x180013c92  pop     rdi
0x180013c93  retn
```
