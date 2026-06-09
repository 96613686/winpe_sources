# DllMain

- ea: `0x18001f9f8`
- end: `0x18001fb65`
- name: `DllMain`
- size: `365`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180005b34`

## callees

- `0x1800034b0`
- `0x18001f9f8`
- `0x18001fb6c`
- `0x18001fba4`
- `0x18002faf8`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18001fa1b`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18001fa1b`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x18001fb30`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x18001fb30`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  __int64 v4; // rcx
  void (__fastcall **v5)(_QWORD); // rdi
  __int64 *v6; // rdi
  __int64 *v7; // rax
  __int64 v8; // rdi
  __int64 v9; // rcx
  __int64 *v10; // rdi
  __int64 *v11; // rax

  if ( fdwReason == 1 )
  {
    SHFusionInitializeFromModuleID(hinstDLL, 0x7Bu);
    DisableThreadLibraryCalls(hinstDLL);
    Globals = hinstDLL;
    v5 = (void (__fastcall **)(_QWORD))&off_180041000;
    if ( &off_180041000 != (_UNKNOWN *)-1LL )
    {
      qword_180041F68 = (__int64)&off_180041000;
      if ( off_180041000 )
      {
        do
        {
          LOBYTE(v4) = 1;
          v5[8](v4);
          v5 += 9;
        }
        while ( *v5 );
      }
    }
    v6 = off_180041520[0];
    v7 = off_180041528;
    while ( v6 < v7 )
    {
      if ( *v6 )
      {
        LOBYTE(v4) = 1;
        (*(void (__fastcall **)(__int64))(*v6 + 64))(v4);
        v7 = off_180041528;
      }
      ++v6;
    }
    McGenEventRegister_EtwEventRegister();
  }
  else if ( !fdwReason )
  {
    McGenEventUnregister_EtwEventUnregister(hinstDLL, fdwReason, lpvReserved);
    v8 = qword_180041F68;
    if ( qword_180041F68 )
    {
      while ( *(_QWORD *)v8 )
      {
        v9 = *(_QWORD *)(v8 + 32);
        if ( v9 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
        *(_QWORD *)(v8 + 32) = 0;
        (*(void (__fastcall **)(_QWORD))(v8 + 64))(0);
        v8 += 72;
      }
    }
    v10 = off_180041520[0];
    v11 = off_180041528;
    while ( v10 < v11 )
    {
      if ( *v10 )
      {
        (*(void (__fastcall **)(_QWORD))(*v10 + 64))(0);
        v11 = off_180041528;
      }
      ++v10;
    }
    ATL::CAtlModule::Term((ATL::CAtlModule *)&Module);
    if ( g_hActCtx != (HANDLE)-1LL )
    {
      ReleaseActCtx(g_hActCtx);
      g_hActCtx = (HANDLE)-1LL;
    }
    if ( hModule )
      hModule = (HMODULE)-1LL;
  }
  return 1;
}

```

## disassembly

```asm
0x18001f9f8  mov     [rsp+arg_0], rbx
0x18001f9fd  push    rdi
0x18001f9fe  sub     rsp, 20h
0x18001fa02  mov     rbx, rcx
0x18001fa05  cmp     edx, 1
0x18001fa08  jnz     loc_18001FA98
0x18001fa0e  mov     edx, 7Bh ; '{'
0x18001fa13  call    SHFusionInitializeFromModuleID
0x18001fa18  mov     rcx, rbx; hLibModule
0x18001fa1b  call    cs:__imp_DisableThreadLibraryCalls
0x18001fa21  mov     cs:Globals, rbx
0x18001fa28  lea     rdi, off_180041000
0x18001fa2f  xor     ebx, ebx
0x18001fa31  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18001fa35  jz      short loc_18001FA5B
0x18001fa37  mov     cs:qword_180041F68, rdi
0x18001fa3e  cmp     cs:off_180041000, rbx
0x18001fa45  jz      short loc_18001FA5B
0x18001fa47  mov     cl, 1
0x18001fa49  mov     rax, [rdi+40h]
0x18001fa4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fa52  lea     rdi, [rdi+48h]
0x18001fa56  cmp     [rdi], rbx
0x18001fa59  jnz     short loc_18001FA47
0x18001fa5b  mov     rdi, cs:off_180041520
0x18001fa62  mov     rax, cs:off_180041528
0x18001fa69  jmp     short loc_18001FA89
0x18001fa6b  mov     rdx, [rdi]
0x18001fa6e  test    rdx, rdx
0x18001fa71  jz      short loc_18001FA85
0x18001fa73  mov     cl, 1
0x18001fa75  mov     rax, [rdx+40h]
0x18001fa79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fa7e  mov     rax, cs:off_180041528
0x18001fa85  add     rdi, 8
0x18001fa89  cmp     rdi, rax
0x18001fa8c  jb      short loc_18001FA6B
0x18001fa8e  call    McGenEventRegister_EtwEventRegister
0x18001fa93  jmp     loc_18001FB55
0x18001fa98  xor     ebx, ebx
0x18001fa9a  test    edx, edx
0x18001fa9c  jnz     loc_18001FB55
0x18001faa2  call    McGenEventUnregister_EtwEventUnregister
0x18001faa7  nop
0x18001faa8  mov     rdi, cs:qword_180041F68
0x18001faaf  test    rdi, rdi
0x18001fab2  jz      short loc_18001FAE3
0x18001fab4  jmp     short loc_18001FADE
0x18001fab6  mov     rcx, [rdi+20h]
0x18001faba  test    rcx, rcx
0x18001fabd  jz      short loc_18001FACB
0x18001fabf  mov     rax, [rcx]
0x18001fac2  mov     rax, [rax+10h]
0x18001fac6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001facb  mov     [rdi+20h], rbx
0x18001facf  xor     ecx, ecx
0x18001fad1  mov     rax, [rdi+40h]
0x18001fad5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fada  add     rdi, 48h ; 'H'
0x18001fade  cmp     [rdi], rbx
0x18001fae1  jnz     short loc_18001FAB6
0x18001fae3  mov     rdi, cs:off_180041520
0x18001faea  mov     rax, cs:off_180041528
0x18001faf1  jmp     short loc_18001FB11
0x18001faf3  mov     rdx, [rdi]
0x18001faf6  test    rdx, rdx
0x18001faf9  jz      short loc_18001FB0D
0x18001fafb  xor     ecx, ecx
0x18001fafd  mov     rax, [rdx+40h]
0x18001fb01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fb06  mov     rax, cs:off_180041528
0x18001fb0d  add     rdi, 8
0x18001fb11  cmp     rdi, rax
0x18001fb14  jb      short loc_18001FAF3
0x18001fb16  lea     rcx, _Module; this
0x18001fb1d  call    ?Term@CAtlModule@ATL@@QEAAXXZ; ATL::CAtlModule::Term(void)
0x18001fb22  nop
0x18001fb23  mov     rcx, cs:g_hActCtx; hActCtx
0x18001fb2a  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18001fb2e  jz      short loc_18001FB41
0x18001fb30  call    cs:__imp_ReleaseActCtx
0x18001fb36  mov     cs:g_hActCtx, 0FFFFFFFFFFFFFFFFh
0x18001fb41  cmp     cs:hModule, rbx
0x18001fb48  jz      short loc_18001FB55
0x18001fb4a  mov     cs:hModule, 0FFFFFFFFFFFFFFFFh
0x18001fb55  mov     eax, 1
0x18001fb5a  mov     rbx, [rsp+28h+arg_0]
0x18001fb5f  add     rsp, 20h
0x18001fb63  pop     rdi
0x18001fb64  retn
```
