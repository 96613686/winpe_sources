# pLoadSetupPlatform

- ea: `0x1800123a0`
- end: `0x1800125b0`
- name: `pLoadSetupPlatform`
- size: `528`
- prototype: `__int64 __fastcall(wchar_t *this, _QWORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18001200c`

## callees

- `0x180003f00`
- `0x180009860`
- `0x18000ed8c`
- `0x180010a40`
- `0x180010ba0`
- `0x1800123a0`
- `0x180012d54`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012502`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001251a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012502`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001251a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800124cb`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800124cb`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18001241d`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18001241d`

## string_xrefs

- `0x1800123eb`: `SetupPlatform.dll`

## pseudocode

```c
__int64 __fastcall pLoadSetupPlatform(wchar_t *this, _QWORD *a2)
{
  wchar_t **v4; // rax
  int v5; // ebx
  const WCHAR *v6; // rax
  const unsigned __int16 *v7; // rax
  signed int v8; // eax
  unsigned int *v9; // r9
  int SetupPlatformVersion; // eax
  unsigned int v11; // edi
  void **v12; // rbx
  const WCHAR *v13; // rax
  HMODULE Library; // rax
  signed int LastError; // eax
  bool v16; // sf
  __int64 v18; // rax
  __int64 v19[2]; // [rsp+20h] [rbp-20h] BYREF
  void **v20; // [rsp+30h] [rbp-10h] BYREF
  __int64 v21; // [rsp+38h] [rbp-8h]
  __int64 v22; // [rsp+80h] [rbp+40h] BYREF
  unsigned int v23; // [rsp+88h] [rbp+48h] BYREF

  v21 = 0;
  v20 = &RAII::CAutoFreeLibrary::`vftable';
  v19[1] = 0;
  v19[0] = (__int64)&RAII::CAutoWdsLibFree<unsigned short *>::`vftable';
  v4 = (wchar_t **)RAII::CAutoCleanupBase<unsigned short *>::operator&((__int64)v19);
  v5 = BuildPathMultiHr(v4, 2u, this, L"SetupPlatform.dll", v19[0]);
  if ( v5 < 0 )
    goto LABEL_19;
  v6 = (const WCHAR *)(*(__int64 (__fastcall **)(__int64 *))(v19[0] + 32))(v19);
  if ( GetFileAttributesW(v6) == -1 )
  {
    v5 = -2147023728;
LABEL_19:
    v19[0] = (__int64)&RAII::CAutoWdsLibFree<unsigned short *>::`vftable';
    RAII::CAutoWdsLibFree<tagVS_FIXEDFILEINFO *>::Release((__int64)v19);
    v20 = &RAII::CAutoFreeLibrary::`vftable';
    RAII::CAutoFreeLibrary::Release((RAII::CAutoFreeLibrary *)&v20);
    return (unsigned int)v5;
  }
  LODWORD(v22) = 0;
  v7 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64 *))(v19[0] + 32))(v19);
  v8 = SPIsFileMicrosoftTrusted(v7, (int *)&v22);
  if ( v8 < 0 )
  {
LABEL_18:
    v5 = v8;
    goto LABEL_19;
  }
  if ( !(_DWORD)v22 )
  {
    v5 = -2147023106;
    goto LABEL_19;
  }
  LODWORD(v22) = 0;
  v23 = 0;
  SetupPlatformVersion = SetupPlatform::GetSetupPlatformVersion(
                           (SetupPlatform *)this,
                           (unsigned __int16 *)&v22,
                           &v23,
                           v9);
  v11 = SetupPlatformVersion;
  if ( SetupPlatformVersion < 0 )
  {
    v5 = SetupPlatformVersion;
    goto LABEL_19;
  }
  if ( (_DWORD)v22 == 1 && v23 == 103 )
  {
    v12 = v20;
    v13 = (const WCHAR *)(*(__int64 (__fastcall **)(__int64 *))(v19[0] + 32))(v19);
    Library = LoadLibraryExW(v13, 0, 8u);
    ((void (__fastcall *)(void ***, HMODULE))v12[6])(&v20, Library);
    v22 = 0;
    if ( ((unsigned __int8 (__fastcall *)(void ***, __int64 *))v20[7])(&v20, &v22) )
    {
      LastError = GetLastError();
      v16 = LastError < 0;
      if ( LastError > 0 )
        v16 = 1;
      if ( v16 )
      {
        v8 = GetLastError();
        if ( v8 > 0 )
          v8 = (unsigned __int16)v8 | 0x80070000;
      }
      else
      {
        v8 = -2147467259;
      }
      goto LABEL_18;
    }
    v18 = v21;
    v21 = 0;
    *a2 = v18;
    v19[0] = (__int64)&RAII::CAutoWdsLibFree<unsigned short *>::`vftable';
    RAII::CAutoWdsLibFree<tagVS_FIXEDFILEINFO *>::Release((__int64)v19);
    v20 = &RAII::CAutoFreeLibrary::`vftable';
    RAII::CAutoFreeLibrary::Release((RAII::CAutoFreeLibrary *)&v20);
    return v11;
  }
  else
  {
    v19[0] = (__int64)&RAII::CAutoWdsLibFree<unsigned short *>::`vftable';
    RAII::CAutoWdsLibFree<tagVS_FIXEDFILEINFO *>::Release((__int64)v19);
    v20 = &RAII::CAutoFreeLibrary::`vftable';
    RAII::CAutoFreeLibrary::Release((RAII::CAutoFreeLibrary *)&v20);
    return 2147944038LL;
  }
}

```

## disassembly

```asm
0x1800123a0  mov     [rsp-28h+arg_0], rbx
0x1800123a5  push    rbp
0x1800123a6  push    rsi
0x1800123a7  push    rdi
0x1800123a8  push    r12
0x1800123aa  push    r15
0x1800123ac  mov     rbp, rsp
0x1800123af  sub     rsp, 40h
0x1800123b3  mov     rsi, rdx
0x1800123b6  mov     rdi, rcx
0x1800123b9  mov     [rbp+var_8], 0
0x1800123c1  lea     r15, ??_7CAutoFreeLibrary@RAII@@6B@; const RAII::CAutoFreeLibrary::`vftable'
0x1800123c8  mov     [rbp+var_10], r15
0x1800123cc  mov     [rbp+var_18], 0
0x1800123d4  lea     r12, ??_7?$CAutoWdsLibFree@PEAG@RAII@@6B@; const RAII::CAutoWdsLibFree<ushort *>::`vftable'
0x1800123db  mov     [rbp+var_20], r12
0x1800123df  lea     rcx, [rbp+var_20]
0x1800123e3  call    ??I?$CAutoCleanupBase@PEAG@RAII@@UEBAPEBQEAGXZ; RAII::CAutoCleanupBase<ushort *>::operator&(void)
0x1800123e8  mov     rcx, rax
0x1800123eb  lea     r9, aSetupplatformD; "SetupPlatform.dll"
0x1800123f2  mov     r8, rdi
0x1800123f5  mov     edx, 2
0x1800123fa  call    BuildPathMultiHr
0x1800123ff  mov     ebx, eax
0x180012401  test    eax, eax
0x180012403  js      loc_180012532
0x180012409  mov     rax, [rbp+var_20]
0x18001240d  lea     rcx, [rbp+var_20]
0x180012411  mov     rax, [rax+20h]
0x180012415  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001241a  mov     rcx, rax; lpFileName
0x18001241d  call    cs:__imp_GetFileAttributesW
0x180012423  cmp     eax, 0FFFFFFFFh
0x180012426  jnz     short loc_180012432
0x180012428  mov     ebx, 80070490h
0x18001242d  jmp     loc_180012532
0x180012432  mov     dword ptr [rbp+arg_10], 0
0x180012439  mov     rax, [rbp+var_20]
0x18001243d  lea     rcx, [rbp+var_20]
0x180012441  mov     rax, [rax+20h]
0x180012445  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001244a  mov     rcx, rax; unsigned __int16 *
0x18001244d  lea     rdx, [rbp+arg_10]; int *
0x180012451  call    ?SPIsFileMicrosoftTrusted@@YAJPEBGPEAH@Z; SPIsFileMicrosoftTrusted(ushort const *,int *)
0x180012456  test    eax, eax
0x180012458  js      loc_180012530
0x18001245e  cmp     dword ptr [rbp+arg_10], 0
0x180012462  jnz     short loc_18001246E
0x180012464  mov     ebx, 800706FEh
0x180012469  jmp     loc_180012532
0x18001246e  mov     dword ptr [rbp+arg_10], 0
0x180012475  mov     [rbp+arg_18], 0
0x18001247c  lea     r8, [rbp+arg_18]; unsigned int *
0x180012480  lea     rdx, [rbp+arg_10]; unsigned __int16 *
0x180012484  mov     rcx, rdi; this
0x180012487  call    ?GetSetupPlatformVersion@SetupPlatform@@YAJPEBGPEAK11@Z; SetupPlatform::GetSetupPlatformVersion(ushort const *,ulong *,ulong *,ulong *)
0x18001248c  mov     edi, eax
0x18001248e  test    eax, eax
0x180012490  jns     short loc_180012499
0x180012492  mov     ebx, eax
0x180012494  jmp     loc_180012532
0x180012499  cmp     dword ptr [rbp+arg_10], 1
0x18001249d  jnz     loc_18001257F
0x1800124a3  cmp     [rbp+arg_18], 67h ; 'g'
0x1800124a7  jnz     loc_18001257F
0x1800124ad  mov     rbx, [rbp+var_10]
0x1800124b1  mov     rax, [rbp+var_20]
0x1800124b5  lea     rcx, [rbp+var_20]
0x1800124b9  mov     rax, [rax+20h]
0x1800124bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800124c2  mov     rcx, rax; lpLibFileName
0x1800124c5  xor     edx, edx; hFile
0x1800124c7  lea     r8d, [rdx+8]; dwFlags
0x1800124cb  call    cs:__imp_LoadLibraryExW
0x1800124d1  mov     rdx, rax
0x1800124d4  lea     rcx, [rbp+var_10]
0x1800124d8  mov     rax, [rbx+30h]
0x1800124dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800124e1  mov     [rbp+arg_10], 0
0x1800124e9  mov     rax, [rbp+var_10]
0x1800124ed  lea     rdx, [rbp+arg_10]
0x1800124f1  lea     rcx, [rbp+var_10]
0x1800124f5  mov     rax, [rax+38h]
0x1800124f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800124fe  test    al, al
0x180012500  jz      short loc_180012551
0x180012502  call    cs:__imp_GetLastError
0x180012508  mov     ebx, 80070000h
0x18001250d  test    eax, eax
0x18001250f  jle     short loc_180012518
0x180012511  movzx   eax, ax
0x180012514  or      eax, ebx
0x180012516  test    eax, eax
0x180012518  jns     short loc_18001252B
0x18001251a  call    cs:__imp_GetLastError
0x180012520  test    eax, eax
0x180012522  jle     short loc_180012530
0x180012524  movzx   eax, ax
0x180012527  or      eax, ebx
0x180012529  jmp     short loc_180012530
0x18001252b  mov     eax, 80004005h
0x180012530  mov     ebx, eax
0x180012532  mov     [rbp+var_20], r12
0x180012536  lea     rcx, [rbp+var_20]
0x18001253a  call    ?Release@?$CAutoWdsLibFree@PEAUtagVS_FIXEDFILEINFO@@@RAII@@UEAAXXZ; RAII::CAutoWdsLibFree<tagVS_FIXEDFILEINFO *>::Release(void)
0x18001253f  nop
0x180012540  mov     [rbp+var_10], r15
0x180012544  lea     rcx, [rbp+var_10]; this
0x180012548  call    ?Release@CAutoFreeLibrary@RAII@@UEAAXXZ; RAII::CAutoFreeLibrary::Release(void)
0x18001254d  mov     eax, ebx
0x18001254f  jmp     short loc_18001259F
0x180012551  mov     rax, [rbp+var_8]
0x180012555  mov     [rbp+var_8], 0
0x18001255d  mov     [rsi], rax
0x180012560  mov     [rbp+var_20], r12
0x180012564  lea     rcx, [rbp+var_20]
0x180012568  call    ?Release@?$CAutoWdsLibFree@PEAUtagVS_FIXEDFILEINFO@@@RAII@@UEAAXXZ; RAII::CAutoWdsLibFree<tagVS_FIXEDFILEINFO *>::Release(void)
0x18001256d  nop
0x18001256e  mov     [rbp+var_10], r15
0x180012572  lea     rcx, [rbp+var_10]; this
0x180012576  call    ?Release@CAutoFreeLibrary@RAII@@UEAAXXZ; RAII::CAutoFreeLibrary::Release(void)
0x18001257b  mov     eax, edi
0x18001257d  jmp     short loc_18001259F
0x18001257f  mov     [rbp+var_20], r12
0x180012583  lea     rcx, [rbp+var_20]
0x180012587  call    ?Release@?$CAutoWdsLibFree@PEAUtagVS_FIXEDFILEINFO@@@RAII@@UEAAXXZ; RAII::CAutoWdsLibFree<tagVS_FIXEDFILEINFO *>::Release(void)
0x18001258c  nop
0x18001258d  mov     [rbp+var_10], r15
0x180012591  lea     rcx, [rbp+var_10]; this
0x180012595  call    ?Release@CAutoFreeLibrary@RAII@@UEAAXXZ; RAII::CAutoFreeLibrary::Release(void)
0x18001259a  mov     eax, 80070666h
0x18001259f  mov     rbx, [rsp+40h+arg_0]
0x1800125a4  add     rsp, 40h
0x1800125a8  pop     r15
0x1800125aa  pop     r12
0x1800125ac  pop     rdi
0x1800125ad  pop     rsi
0x1800125ae  pop     rbp
0x1800125af  retn
```
