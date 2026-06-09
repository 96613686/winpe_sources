# PMCIWrapper::EnsureTypeLib(void)

- ea: `0x180062cb0`
- end: `0x180062dea`
- name: `?EnsureTypeLib@PMCIWrapper@@AEAAJXZ`
- size: `314`
- prototype: `__int64 __fastcall(PMCIWrapper *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180062760`

## callees

- `0x180062cb0`
- `0x18007a010`

## import_xrefs

- `OLEAUT32!__imp_CreateTypeLib2` at `0x180062ce5`
- `OLEAUT32!__imp_CreateTypeLib2` at `0x180062ce5`

## pseudocode

```c
__int64 __fastcall PMCIWrapper::EnsureTypeLib(PMCIWrapper *this)
{
  HRESULT v3; // ebx
  ICreateTypeLib2 *v4; // rcx
  ICreateTypeLib2 *ppctlib; // [rsp+30h] [rbp+8h] BYREF

  if ( *((_QWORD *)this + 3) )
    return 0;
  ppctlib = 0;
  v3 = CreateTypeLib2(SYS_WIN32, L"VBSSig.tlb", &ppctlib);
  if ( v3 < 0
    || (v3 = ((__int64 (__fastcall *)(ICreateTypeLib2 *, __int64))ppctlib->lpVtbl->SetLcid)(ppctlib, 1024), v3 < 0)
    || (v3 = ((__int64 (__fastcall *)(ICreateTypeLib2 *, const wchar_t *))ppctlib->lpVtbl->SetName)(
               ppctlib,
               L"ScrGlobTlib"),
        v3 < 0)
    || (v3 = ((__int64 (__fastcall *)(ICreateTypeLib2 *, const wchar_t *))ppctlib->lpVtbl->SetDocString)(
               ppctlib,
               L"Scripting Global Type Library"),
        v3 < 0)
    || (v3 = ((__int64 (__fastcall *)(ICreateTypeLib2 *, __int64, __int64))ppctlib->lpVtbl->SetVersion)(ppctlib, 10, 8),
        v3 < 0)
    || (v3 = ((__int64 (__fastcall *)(ICreateTypeLib2 *, GUID *))ppctlib->lpVtbl->SetGuid)(ppctlib, &IID_IScriptTypeLib),
        v3 < 0)
    || (v3 = ((__int64 (__fastcall *)(ICreateTypeLib2 *, _QWORD))ppctlib->lpVtbl->SetLibFlags)(ppctlib, 0), v3 < 0) )
  {
    v4 = ppctlib;
  }
  else
  {
    v4 = 0;
    *((_QWORD *)this + 3) = ppctlib;
    v3 = 0;
    ppctlib = 0;
  }
  if ( v4 )
    ((void (__fastcall *)(ICreateTypeLib2 *))v4->lpVtbl->Release)(v4);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180062cb0  mov     [rsp+arg_8], rbx
0x180062cb5  push    rdi
0x180062cb6  sub     rsp, 20h
0x180062cba  cmp     qword ptr [rcx+18h], 0
0x180062cbf  mov     rdi, rcx
0x180062cc2  jz      short loc_180062CCB
0x180062cc4  xor     eax, eax
0x180062cc6  jmp     loc_180062DDE
0x180062ccb  lea     r8, [rsp+28h+ppctlib]; ppctlib
0x180062cd0  mov     [rsp+28h+ppctlib], 0
0x180062cd9  lea     rdx, aVbssigTlb; "VBSSig.tlb"
0x180062ce0  mov     ecx, 1; syskind
0x180062ce5  call    cs:__imp_CreateTypeLib2
0x180062cec  nop     dword ptr [rax+rax+00h]
0x180062cf1  mov     ebx, eax
0x180062cf3  test    eax, eax
0x180062cf5  js      loc_180062DC6
0x180062cfb  mov     rcx, [rsp+28h+ppctlib]
0x180062d00  mov     edx, 400h
0x180062d05  mov     rax, [rcx]
0x180062d08  mov     rax, [rax+50h]
0x180062d0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062d11  mov     ebx, eax
0x180062d13  test    eax, eax
0x180062d15  js      loc_180062DC6
0x180062d1b  mov     rcx, [rsp+28h+ppctlib]
0x180062d20  lea     rdx, aScrglobtlib; "ScrGlobTlib"
0x180062d27  mov     rax, [rcx]
0x180062d2a  mov     rax, [rax+20h]
0x180062d2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062d33  mov     ebx, eax
0x180062d35  test    eax, eax
0x180062d37  js      loc_180062DC6
0x180062d3d  mov     rcx, [rsp+28h+ppctlib]
0x180062d42  lea     rdx, aScriptingGloba_0; "Scripting Global Type Library"
0x180062d49  mov     rax, [rcx]
0x180062d4c  mov     rax, [rax+38h]
0x180062d50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062d55  mov     ebx, eax
0x180062d57  test    eax, eax
0x180062d59  js      short loc_180062DC6
0x180062d5b  mov     rcx, [rsp+28h+ppctlib]
0x180062d60  mov     edx, 0Ah
0x180062d65  mov     rax, [rcx]
0x180062d68  lea     r8d, [rdx-2]
0x180062d6c  mov     rax, [rax+28h]
0x180062d70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062d75  mov     ebx, eax
0x180062d77  test    eax, eax
0x180062d79  js      short loc_180062DC6
0x180062d7b  mov     rcx, [rsp+28h+ppctlib]
0x180062d80  lea     rdx, IID_IScriptTypeLib
0x180062d87  mov     rax, [rcx]
0x180062d8a  mov     rax, [rax+30h]
0x180062d8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062d93  mov     ebx, eax
0x180062d95  test    eax, eax
0x180062d97  js      short loc_180062DC6
0x180062d99  mov     rcx, [rsp+28h+ppctlib]
0x180062d9e  xor     edx, edx
0x180062da0  mov     rax, [rcx]
0x180062da3  mov     rax, [rax+58h]
0x180062da7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062dac  mov     ebx, eax
0x180062dae  test    eax, eax
0x180062db0  js      short loc_180062DC6
0x180062db2  mov     rax, [rsp+28h+ppctlib]
0x180062db7  xor     ecx, ecx
0x180062db9  mov     [rdi+18h], rax
0x180062dbd  xor     ebx, ebx
0x180062dbf  mov     [rsp+28h+ppctlib], rcx
0x180062dc4  jmp     short loc_180062DCB
0x180062dc6  mov     rcx, [rsp+28h+ppctlib]
0x180062dcb  test    rcx, rcx
0x180062dce  jz      short loc_180062DDC
0x180062dd0  mov     rax, [rcx]
0x180062dd3  mov     rax, [rax+10h]
0x180062dd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062ddc  mov     eax, ebx
0x180062dde  mov     rbx, [rsp+28h+arg_8]
0x180062de3  add     rsp, 20h
0x180062de7  pop     rdi
0x180062de8  retn
```
