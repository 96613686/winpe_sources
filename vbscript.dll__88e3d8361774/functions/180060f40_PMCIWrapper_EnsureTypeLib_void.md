# PMCIWrapper::EnsureTypeLib(void)

- ea: `0x180060f40`
- end: `0x180061073`
- name: `?EnsureTypeLib@PMCIWrapper@@AEAAJXZ`
- size: `307`
- prototype: `__int64 __fastcall(PMCIWrapper *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180060a04`

## callees

- `0x180060f40`
- `0x180077010`

## import_xrefs

- `OLEAUT32!__imp_CreateTypeLib2` at `0x180060f75`
- `OLEAUT32!__imp_CreateTypeLib2` at `0x180060f75`

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
0x180060f40  mov     [rsp+arg_8], rbx
0x180060f45  push    rdi
0x180060f46  sub     rsp, 20h
0x180060f4a  cmp     qword ptr [rcx+18h], 0
0x180060f4f  mov     rdi, rcx
0x180060f52  jz      short loc_180060F5B
0x180060f54  xor     eax, eax
0x180060f56  jmp     loc_180061068
0x180060f5b  lea     r8, [rsp+28h+ppctlib]; ppctlib
0x180060f60  mov     [rsp+28h+ppctlib], 0
0x180060f69  lea     rdx, aVbssigTlb; "VBSSig.tlb"
0x180060f70  mov     ecx, 1; syskind
0x180060f75  call    cs:__imp_CreateTypeLib2
0x180060f7b  mov     ebx, eax
0x180060f7d  test    eax, eax
0x180060f7f  js      loc_180061050
0x180060f85  mov     rcx, [rsp+28h+ppctlib]
0x180060f8a  mov     edx, 400h
0x180060f8f  mov     rax, [rcx]
0x180060f92  mov     rax, [rax+50h]
0x180060f96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060f9b  mov     ebx, eax
0x180060f9d  test    eax, eax
0x180060f9f  js      loc_180061050
0x180060fa5  mov     rcx, [rsp+28h+ppctlib]
0x180060faa  lea     rdx, aScrglobtlib; "ScrGlobTlib"
0x180060fb1  mov     rax, [rcx]
0x180060fb4  mov     rax, [rax+20h]
0x180060fb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060fbd  mov     ebx, eax
0x180060fbf  test    eax, eax
0x180060fc1  js      loc_180061050
0x180060fc7  mov     rcx, [rsp+28h+ppctlib]
0x180060fcc  lea     rdx, aScriptingGloba_0; "Scripting Global Type Library"
0x180060fd3  mov     rax, [rcx]
0x180060fd6  mov     rax, [rax+38h]
0x180060fda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060fdf  mov     ebx, eax
0x180060fe1  test    eax, eax
0x180060fe3  js      short loc_180061050
0x180060fe5  mov     rcx, [rsp+28h+ppctlib]
0x180060fea  mov     edx, 0Ah
0x180060fef  mov     rax, [rcx]
0x180060ff2  lea     r8d, [rdx-2]
0x180060ff6  mov     rax, [rax+28h]
0x180060ffa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060fff  mov     ebx, eax
0x180061001  test    eax, eax
0x180061003  js      short loc_180061050
0x180061005  mov     rcx, [rsp+28h+ppctlib]
0x18006100a  lea     rdx, IID_IScriptTypeLib
0x180061011  mov     rax, [rcx]
0x180061014  mov     rax, [rax+30h]
0x180061018  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006101d  mov     ebx, eax
0x18006101f  test    eax, eax
0x180061021  js      short loc_180061050
0x180061023  mov     rcx, [rsp+28h+ppctlib]
0x180061028  xor     edx, edx
0x18006102a  mov     rax, [rcx]
0x18006102d  mov     rax, [rax+58h]
0x180061031  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061036  mov     ebx, eax
0x180061038  test    eax, eax
0x18006103a  js      short loc_180061050
0x18006103c  mov     rax, [rsp+28h+ppctlib]
0x180061041  xor     ecx, ecx
0x180061043  mov     [rdi+18h], rax
0x180061047  xor     ebx, ebx
0x180061049  mov     [rsp+28h+ppctlib], rcx
0x18006104e  jmp     short loc_180061055
0x180061050  mov     rcx, [rsp+28h+ppctlib]
0x180061055  test    rcx, rcx
0x180061058  jz      short loc_180061066
0x18006105a  mov     rax, [rcx]
0x18006105d  mov     rax, [rax+10h]
0x180061061  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061066  mov     eax, ebx
0x180061068  mov     rbx, [rsp+28h+arg_8]
0x18006106d  add     rsp, 20h
0x180061071  pop     rdi
0x180061072  retn
```
