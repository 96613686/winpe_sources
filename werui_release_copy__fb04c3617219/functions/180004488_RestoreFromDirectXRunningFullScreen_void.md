# RestoreFromDirectXRunningFullScreen(void *)

- ea: `0x180004488`
- end: `0x1800045c5`
- name: `?RestoreFromDirectXRunningFullScreen@@YAJPEAX@Z`
- size: `317`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x180006ee0`

## callees

- `0x1800035dc`
- `0x180003604`
- `0x180003fc4`
- `0x180004488`
- `0x180018010`

## import_xrefs

- `KERNEL32!LoadLibraryW` at `0x18000449c`
- `KERNEL32!LoadLibraryW` at `0x18000449c`
- `KERNEL32!GetProcAddress` at `0x1800044f4`
- `KERNEL32!GetProcAddress` at `0x1800044f4`
- `USER32!ChangeDisplaySettingsW` at `0x180004571`
- `USER32!ChangeDisplaySettingsW` at `0x180004571`

## string_xrefs

- `0x180004495`: `gdi32.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RestoreFromDirectXRunningFullScreen(void *a1)
{
  HMODULE LibraryW; // rax
  unsigned int v3; // edi
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  FARPROC ProcAddress; // rax
  int v7; // eax
  unsigned int v8; // eax
  HMODULE v10; // [rsp+38h] [rbp+10h] BYREF

  LibraryW = LoadLibraryW(L"gdi32.dll");
  v10 = LibraryW;
  if ( LibraryW )
  {
    ProcAddress = GetProcAddress(LibraryW, "D3DKMTReleaseProcessVidPnSourceOwners");
    if ( ProcAddress )
    {
      v7 = ((__int64 (__fastcall *)(void *))ProcAddress)(a1) | 0x10000000;
      if ( v7 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          13,
          WPP_da26f2d1156739261f61a97d8df66789_Traceguids,
          (unsigned int)v7);
      v8 = ChangeDisplaySettingsW(0, 0x40000000u);
      if ( v8 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_da26f2d1156739261f61a97d8df66789_Traceguids, v8);
        v3 = -2147467259;
      }
      else
      {
        v3 = 0;
      }
    }
    else
    {
      v3 = -2147024769;
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v5 = 12;
        goto LABEL_5;
      }
    }
  }
  else
  {
    v3 = -2147024770;
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v5 = 11;
LABEL_5:
      WPP_SF_(v4[2], v5, WPP_da26f2d1156739261f61a97d8df66789_Traceguids);
    }
  }
  tlx::unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),0>>::~unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),0>>(&v10);
  return v3;
}

```

## disassembly

```asm
0x180004488  mov     [rsp+arg_0], rbx
0x18000448d  push    rdi
0x18000448e  sub     rsp, 20h
0x180004492  mov     rbx, rcx
0x180004495  lea     rcx, LibFileName; "gdi32.dll"
0x18000449c  call    cs:__imp_LoadLibraryW
0x1800044a2  mov     [rsp+28h+arg_8], rax
0x1800044a7  test    rax, rax
0x1800044aa  jnz     short loc_1800044EA
0x1800044ac  mov     edi, 8007007Eh
0x1800044b1  lea     rbx, WPP_GLOBAL_Control
0x1800044b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800044bf  cmp     rcx, rbx
0x1800044c2  jz      loc_1800045AE
0x1800044c8  test    byte ptr [rcx+1Ch], 1
0x1800044cc  jz      loc_1800045AE
0x1800044d2  lea     edx, [rax+0Bh]
0x1800044d5  lea     r8, WPP_da26f2d1156739261f61a97d8df66789_Traceguids
0x1800044dc  mov     rcx, [rcx+10h]
0x1800044e0  call    WPP_SF_
0x1800044e5  jmp     loc_1800045AE
0x1800044ea  lea     rdx, aD3dkmtreleasep; "D3DKMTReleaseProcessVidPnSourceOwners"
0x1800044f1  mov     rcx, rax; hModule
0x1800044f4  call    cs:__imp_GetProcAddress
0x1800044fa  test    rax, rax
0x1800044fd  jnz     short loc_18000452A
0x1800044ff  mov     edi, 8007007Fh
0x180004504  lea     rbx, WPP_GLOBAL_Control
0x18000450b  mov     rcx, cs:WPP_GLOBAL_Control
0x180004512  cmp     rcx, rbx
0x180004515  jz      loc_1800045AE
0x18000451b  test    byte ptr [rcx+1Ch], 1
0x18000451f  jz      loc_1800045AE
0x180004525  lea     edx, [rax+0Ch]
0x180004528  jmp     short loc_1800044D5
0x18000452a  mov     rcx, rbx
0x18000452d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004532  lea     rbx, WPP_GLOBAL_Control
0x180004539  or      eax, 10000000h
0x18000453e  jge     short loc_18000456A
0x180004540  mov     rcx, cs:WPP_GLOBAL_Control
0x180004547  cmp     rcx, rbx
0x18000454a  jz      short loc_18000456A
0x18000454c  test    byte ptr [rcx+1Ch], 1
0x180004550  jz      short loc_18000456A
0x180004552  mov     edx, 0Dh
0x180004557  mov     r9d, eax
0x18000455a  lea     r8, WPP_da26f2d1156739261f61a97d8df66789_Traceguids
0x180004561  mov     rcx, [rcx+10h]
0x180004565  call    WPP_SF_d
0x18000456a  mov     edx, 40000000h; dwFlags
0x18000456f  xor     ecx, ecx; lpDevMode
0x180004571  call    cs:__imp_ChangeDisplaySettingsW
0x180004577  test    eax, eax
0x180004579  jz      short loc_1800045AC
0x18000457b  mov     rcx, cs:WPP_GLOBAL_Control
0x180004582  cmp     rcx, rbx
0x180004585  jz      short loc_1800045A5
0x180004587  test    byte ptr [rcx+1Ch], 1
0x18000458b  jz      short loc_1800045A5
0x18000458d  mov     edx, 0Eh
0x180004592  mov     r9d, eax
0x180004595  lea     r8, WPP_da26f2d1156739261f61a97d8df66789_Traceguids
0x18000459c  mov     rcx, [rcx+10h]
0x1800045a0  call    WPP_SF_d
0x1800045a5  mov     edi, 80004005h
0x1800045aa  jmp     short loc_1800045AE
0x1800045ac  xor     edi, edi
0x1800045ae  lea     rcx, [rsp+28h+arg_8]
0x1800045b3  call    ??1?$unique_any@U?$handle_traits@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),0>>::~unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),0>>(void)
0x1800045b8  mov     eax, edi
0x1800045ba  mov     rbx, [rsp+28h+arg_0]
0x1800045bf  add     rsp, 20h
0x1800045c3  pop     rdi
0x1800045c4  retn
```
