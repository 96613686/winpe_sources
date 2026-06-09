# DllUnregisterServer

- ea: `0x180013890`
- end: `0x180013970`
- name: `DllUnregisterServer`
- size: `224`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180010440`
- `0x180013890`
- `0x180015010`

## import_xrefs

- `OLEAUT32!__imp_UnRegisterTypeLib` at `0x18001395f`
- `OLEAUT32!__imp_UnRegisterTypeLib` at `0x18001395f`

## pseudocode

```c
HRESULT __stdcall DllUnregisterServer()
{
  __int64 v0; // rbx
  const struct ATL::_ATL_CATMAP_ENTRY *v1; // rax
  __int64 *v2; // rbx
  __int64 *v3; // rax
  __int64 v4; // rdi
  const struct ATL::_ATL_CATMAP_ENTRY *v5; // rax

  v0 = qword_18001BDB8;
  if ( qword_18001BDB8 )
  {
    while ( *(_QWORD *)v0 )
    {
      v1 = (const struct ATL::_ATL_CATMAP_ENTRY *)(*(__int64 (**)(void))(v0 + 56))();
      if ( (int)ATL::AtlRegisterClassCategoriesHelper(*(GUID **)v0, v1, 0) < 0
        || (*(int (__fastcall **)(_QWORD))(v0 + 8))(0) < 0 )
      {
        return UnRegisterTypeLib(&LIBID_TDCLib, 1u, 1u, 0, SYS_WIN32);
      }
      v0 += 72;
    }
  }
  if ( !ATL::_pPerfUnRegFunc || ATL::_pPerfUnRegFunc() >= 0 )
  {
    v2 = (__int64 *)off_18001B630[0];
    v3 = (__int64 *)off_18001B638;
    while ( v2 < v3 )
    {
      v4 = *v2;
      if ( *v2 )
      {
        v5 = (const struct ATL::_ATL_CATMAP_ENTRY *)(*(__int64 (**)(void))(v4 + 56))();
        if ( (int)ATL::AtlRegisterClassCategoriesHelper(*(GUID **)v4, v5, 0) < 0
          || (*(int (__fastcall **)(_QWORD))(v4 + 8))(0) < 0 )
        {
          return UnRegisterTypeLib(&LIBID_TDCLib, 1u, 1u, 0, SYS_WIN32);
        }
        v3 = (__int64 *)off_18001B638;
      }
      ++v2;
    }
  }
  return UnRegisterTypeLib(&LIBID_TDCLib, 1u, 1u, 0, SYS_WIN32);
}

```

## disassembly

```asm
0x180013890  mov     [rsp+arg_0], rbx
0x180013895  push    rdi
0x180013896  sub     rsp, 30h
0x18001389a  mov     rbx, cs:qword_18001BDB8
0x1800138a1  test    rbx, rbx
0x1800138a4  jz      short loc_1800138E0
0x1800138a6  jmp     short loc_1800138DA
0x1800138a8  mov     rax, [rbx+38h]
0x1800138ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800138b1  mov     rcx, [rbx]; rguid
0x1800138b4  xor     r8d, r8d; int
0x1800138b7  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x1800138ba  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x1800138bf  test    eax, eax
0x1800138c1  js      loc_180013947
0x1800138c7  mov     rax, [rbx+8]
0x1800138cb  xor     ecx, ecx
0x1800138cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800138d2  test    eax, eax
0x1800138d4  js      short loc_180013947
0x1800138d6  add     rbx, 48h ; 'H'
0x1800138da  cmp     qword ptr [rbx], 0
0x1800138de  jnz     short loc_1800138A8
0x1800138e0  mov     rax, cs:?_pPerfUnRegFunc@ATL@@3P6AJXZEA; long (*ATL::_pPerfUnRegFunc)(void)
0x1800138e7  test    rax, rax
0x1800138ea  jz      short loc_1800138F5
0x1800138ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800138f1  test    eax, eax
0x1800138f3  js      short loc_180013947
0x1800138f5  mov     rbx, cs:off_18001B630
0x1800138fc  mov     rax, cs:off_18001B638
0x180013903  jmp     short loc_180013942
0x180013905  mov     rdi, [rbx]
0x180013908  test    rdi, rdi
0x18001390b  jz      short loc_18001393E
0x18001390d  mov     rax, [rdi+38h]
0x180013911  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013916  mov     rcx, [rdi]; rguid
0x180013919  xor     r8d, r8d; int
0x18001391c  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x18001391f  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x180013924  test    eax, eax
0x180013926  js      short loc_180013947
0x180013928  mov     rax, [rdi+8]
0x18001392c  xor     ecx, ecx
0x18001392e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013933  test    eax, eax
0x180013935  js      short loc_180013947
0x180013937  mov     rax, cs:off_18001B638
0x18001393e  add     rbx, 8
0x180013942  cmp     rbx, rax
0x180013945  jb      short loc_180013905
0x180013947  mov     eax, 1
0x18001394c  lea     rcx, LIBID_TDCLib; libID
0x180013953  mov     r8d, eax; wVerMinor
0x180013956  mov     [rsp+38h+syskind], eax; syskind
0x18001395a  mov     edx, eax; wVerMajor
0x18001395c  xor     r9d, r9d; lcid
0x18001395f  call    cs:__imp_UnRegisterTypeLib
0x180013965  mov     rbx, [rsp+38h+arg_0]
0x18001396a  add     rsp, 30h
0x18001396e  pop     rdi
0x18001396f  retn
```
