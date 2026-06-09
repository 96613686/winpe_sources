# CVaultMemoryStore::SubmitCredentialToStore(IVaultCredential *,ushort *,int)

- ea: `0x18000e570`
- end: `0x18000eb1e`
- name: `?SubmitCredentialToStore@CVaultMemoryStore@@UEAAKPEAUIVaultCredential@@PEAGH@Z`
- size: `1454`
- prototype: `unsigned int __fastcall(CVaultMemoryStore *__hidden this, struct IVaultCredential *, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18000f7d0`

## callees

- `0x180003140`
- `0x18000e570`
- `0x180012210`
- `0x180024b08`
- `0x18003a580`
- `0x18003b7d8`
- `0x18004b430`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000e62b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000e62b`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000e90e`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000e90e`
- `ntdll!RtlReleaseResource` at `0x18000e88a`
- `ntdll!RtlReleaseResource` at `0x18000e94b`
- `ntdll!RtlReleaseResource` at `0x18000e9a0`
- `ntdll!RtlReleaseResource` at `0x18000e9e2`
- `ntdll!RtlReleaseResource` at `0x18000eafc`
- `ntdll!RtlReleaseResource` at `0x18000e88a`
- `ntdll!RtlReleaseResource` at `0x18000e94b`
- `ntdll!RtlReleaseResource` at `0x18000e9a0`
- `ntdll!RtlReleaseResource` at `0x18000e9e2`
- `ntdll!RtlReleaseResource` at `0x18000eafc`
- `ntdll!RtlAcquireResourceExclusive` at `0x18000e6e7`
- `ntdll!RtlAcquireResourceExclusive` at `0x18000e6e7`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CVaultMemoryStore::SubmitCredentialToStore(
        CVaultMemoryStore *this,
        struct IVaultCredential *a2,
        unsigned __int16 *a3,
        int a4)
{
  struct _RTL_RESOURCE *v7; // r14
  __int64 v8; // rax
  __int64 v9; // rcx
  unsigned __int64 v10; // rbx
  _WORD *v11; // rax
  unsigned __int64 v12; // rsi
  char v13; // r15
  __int64 v14; // rax
  unsigned __int16 *v15; // rcx
  unsigned __int16 *v16; // rdx
  unsigned __int16 v17; // r8
  unsigned int v18; // edi
  unsigned __int16 *v19; // rcx
  unsigned int v20; // ebx
  unsigned int v21; // eax
  __int64 *v22; // r13
  __int64 *v23; // rdi
  __int64 *v24; // rbx
  __int128 v25; // xmm6
  char v26; // cl
  __int64 *v27; // rax
  unsigned int v28; // edi
  struct IVaultCredential *v29; // rbx
  FILETIME FileTime1; // [rsp+28h] [rbp-B9h] BYREF
  __int64 v32; // [rsp+30h] [rbp-B1h]
  FILETIME FileTime2; // [rsp+38h] [rbp-A9h] BYREF
  __int64 (__fastcall *v34)(_QWORD); // [rsp+40h] [rbp-A1h] BYREF
  __int64 v35; // [rsp+48h] [rbp-99h] BYREF
  __int64 v36; // [rsp+50h] [rbp-91h]
  __int64 v37; // [rsp+58h] [rbp-89h] BYREF
  __int64 v38; // [rsp+60h] [rbp-81h]
  int v39; // [rsp+68h] [rbp-79h]
  __int64 (__fastcall *v40)(_QWORD); // [rsp+70h] [rbp-71h] BYREF
  __int64 v41; // [rsp+78h] [rbp-69h]
  int v42; // [rsp+80h] [rbp-61h]
  __int128 Buf2; // [rsp+88h] [rbp-59h] BYREF
  _OWORD Buf1[2]; // [rsp+98h] [rbp-49h] BYREF
  char *v45; // [rsp+B8h] [rbp-29h]
  char v46; // [rsp+C0h] [rbp-21h]
  struct _RTL_RESOURCE *v47; // [rsp+C8h] [rbp-19h]
  char v48; // [rsp+D0h] [rbp-11h]
  __int128 v49; // [rsp+D8h] [rbp-9h] BYREF

  LODWORD(v32) = a4;
  FileTime2 = (FILETIME)a3;
  FileTime1 = (FILETIME)a2;
  v38 = 0;
  v39 = 0;
  v37 = 0;
  v34 = AutoDereference<IVaultKeyManager>;
  v35 = 0;
  LODWORD(v36) = 0;
  v7 = (struct _RTL_RESOURCE *)((char *)this + 192);
  v45 = (char *)this + 192;
  v46 = 0;
  v40 = AutoDereference<IVaultKeyManager>;
  v41 = 0;
  v42 = 0;
  v49 = 0;
  v8 = -1;
  do
    ++v8;
  while ( a3[v8] );
  v9 = (unsigned int)(v8 + 1);
  if ( (unsigned int)v9 < (unsigned int)v8 )
  {
    v20 = 534;
    goto LABEL_37;
  }
  v10 = (unsigned int)v9;
  v11 = LocalAlloc(0x40u, 2 * v9);
  v12 = (unsigned __int64)v11;
  v38 = (__int64)v11;
  if ( !v11 )
  {
    v20 = 14;
    goto LABEL_37;
  }
  v13 = 1;
  if ( v10 )
  {
    if ( v10 > 0x7FFFFFFF )
    {
      v18 = -2147024809;
      *v11 = 0;
    }
    else
    {
      v14 = 2147483646;
      v15 = a3;
      v16 = (unsigned __int16 *)v12;
      do
      {
        if ( !v14 )
          break;
        v17 = *v15;
        if ( !*v15 )
          break;
        ++v15;
        *v16++ = v17;
        --v14;
        --v10;
      }
      while ( v10 );
      v18 = v10 == 0 ? 0x8007007A : 0;
      v19 = v16 - 1;
      if ( v10 )
        v19 = v16;
      *v19 = 0;
      if ( v10 )
      {
        v20 = 0;
        goto LABEL_16;
      }
    }
  }
  else
  {
    v18 = -2147024809;
  }
  VaultFreeInternal((HLOCAL)v12);
  v12 = 0;
  v38 = 0;
  v20 = (unsigned __int16)v18;
  if ( (v18 & 0x1FFF0000) != 0x70000 )
    v20 = v18;
LABEL_16:
  if ( v20 )
  {
LABEL_37:
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v40);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v34);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v37);
    return v20;
  }
  RtlAcquireResourceExclusive(v7, 1u);
  v46 = 1;
  v21 = (*(__int64 (__fastcall **)(struct IVaultCredential *, __int128 *))(*(_QWORD *)a2 + 24LL))(a2, &v49);
  v20 = v21;
  if ( v21 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_88c39a8abb2e32ad80f44de23670705e_Traceguids, v21);
    goto LABEL_47;
  }
  v47 = v7;
  v48 = 0;
  if ( *((_BYTE *)this + 288) )
  {
    v20 = 55;
LABEL_46:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_88c39a8abb2e32ad80f44de23670705e_Traceguids, v20);
LABEL_47:
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v40);
    RtlReleaseResource(v7);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v34);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v37);
    return v20;
  }
  v22 = (__int64 *)*((_QWORD *)this + 1);
  v23 = (__int64 *)v22[1];
  HIDWORD(Buf1[0]) = 0;
  v24 = v22;
  v25 = v49;
  if ( !*((_BYTE *)v23 + 25) )
  {
    do
    {
      Buf2 = v25;
      Buf1[0] = *((_OWORD *)v23 + 2);
      if ( memcmp_0(Buf1, &Buf2, 0x10u) < 0 )
      {
        v26 = 1;
      }
      else
      {
        v26 = 0;
        v24 = v23;
      }
      v27 = v23 + 2;
      if ( !v26 )
        v27 = v23;
      v23 = (__int64 *)*v27;
    }
    while ( !*(_BYTE *)(*v27 + 25) );
  }
  if ( *((_BYTE *)v24 + 25) || (Buf1[0] = *((_OWORD *)v24 + 2), Buf2 = v25, memcmp_0(&Buf2, Buf1, 0x10u) < 0) )
    v13 = 0;
  if ( !v13 )
    v24 = v22;
  if ( v24 == v22 )
  {
    v20 = 1168;
    goto LABEL_46;
  }
  (**(void (__fastcall ***)(__int64))v24[6])(v24[6]);
  v41 = v24[6];
  if ( !(_DWORD)v32 )
  {
LABEL_50:
    v29 = (struct IVaultCredential *)FileTime1;
LABEL_33:
    v20 = CVaultMemoryStore::SubmitCredentialToStoreNoAlloc(this, v29, (unsigned __int16 *)v12);
    v38 = v12 & -(__int64)(v20 != 0);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v40);
    RtlReleaseResource(v7);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v34);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v37);
    return v20;
  }
  v28 = (*(__int64 (__fastcall **)(CVaultMemoryStore *, FILETIME, __int64 *))(*(_QWORD *)this + 168LL))(
          this,
          FileTime2,
          &v35);
  if ( v28 )
  {
    if ( v28 != 1168 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_88c39a8abb2e32ad80f44de23670705e_Traceguids, v28);
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v40);
      RtlReleaseResource(v7);
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v34);
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v37);
      return v28;
    }
    goto LABEL_50;
  }
  v29 = (struct IVaultCredential *)FileTime1;
  (*(void (__fastcall **)(FILETIME, FILETIME *))(**(_QWORD **)&FileTime1 + 192LL))(FileTime1, &FileTime1);
  (*(void (__fastcall **)(__int64, FILETIME *))(*(_QWORD *)v35 + 192LL))(v35, &FileTime2);
  if ( ((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v35 + 160LL))(v35) & 0x100) == 0
    || CompareFileTime(&FileTime1, &FileTime2) > 0 )
  {
    goto LABEL_33;
  }
  v28 = -2147221136;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_88c39a8abb2e32ad80f44de23670705e_Traceguids, 2147746160LL);
  CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v40);
  RtlReleaseResource(v7);
  CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v34);
  CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v37);
  return v28;
}

```

## disassembly

```asm
0x18000e570  mov     rax, rsp
0x18000e573  mov     [rax+20h], rbx
0x18000e577  push    rbp
0x18000e578  push    rsi
0x18000e579  push    rdi
0x18000e57a  push    r12
0x18000e57c  push    r13
0x18000e57e  push    r14
0x18000e580  push    r15
0x18000e582  lea     rbp, [rax-5Fh]
0x18000e586  sub     rsp, 100h
0x18000e58d  movaps  xmmword ptr [rax-48h], xmm6
0x18000e591  mov     rax, cs:__security_cookie
0x18000e598  xor     rax, rsp
0x18000e59b  mov     [rbp+57h+var_50], rax
0x18000e59f  mov     dword ptr [rsp+130h+var_108], r9d
0x18000e5a4  mov     rdi, r8
0x18000e5a7  mov     qword ptr [rsp+130h+FileTime2.dwLowDateTime], r8
0x18000e5ac  mov     r13, rdx
0x18000e5af  mov     qword ptr [rsp+130h+FileTime1.dwLowDateTime], rdx
0x18000e5b4  mov     r12, rcx
0x18000e5b7  xor     r15d, r15d
0x18000e5ba  mov     [rsp+130h+var_D8], r15
0x18000e5bf  mov     [rbp+57h+var_D0], r15d
0x18000e5c3  mov     [rsp+130h+var_E0], r15
0x18000e5c8  lea     rax, ??$AutoDereference@UIVaultKeyManager@@@@YAXPEAUIVaultKeyManager@@@Z; AutoDereference<IVaultKeyManager>(IVaultKeyManager *)
0x18000e5cf  mov     [rsp+130h+var_F8], rax
0x18000e5d4  mov     [rsp+130h+var_F0], r15
0x18000e5d9  mov     dword ptr [rsp+130h+var_E8], r15d
0x18000e5de  lea     r14, [rcx+0C0h]
0x18000e5e5  mov     [rbp+57h+var_80], r14
0x18000e5e9  mov     [rbp+57h+var_78], r15b
0x18000e5ed  lea     rax, ??$AutoDereference@UIVaultKeyManager@@@@YAXPEAUIVaultKeyManager@@@Z; AutoDereference<IVaultKeyManager>(IVaultKeyManager *)
0x18000e5f4  mov     [rbp+57h+var_C8], rax
0x18000e5f8  mov     [rbp+57h+var_C0], r15
0x18000e5fc  mov     [rbp+57h+var_B8], r15d
0x18000e600  xorps   xmm0, xmm0
0x18000e603  movups  [rbp+57h+var_60], xmm0
0x18000e607  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000e60b  inc     rax
0x18000e60e  cmp     [r8+rax*2], r15w
0x18000e613  jnz     short loc_18000E60B
0x18000e615  lea     ecx, [rax+1]
0x18000e618  cmp     ecx, eax
0x18000e61a  jb      loc_18000E8DD
0x18000e620  mov     ebx, ecx
0x18000e622  lea     rdx, [rcx+rcx]; uBytes
0x18000e626  mov     ecx, 40h ; '@'; uFlags
0x18000e62b  call    cs:__imp_LocalAlloc
0x18000e631  mov     rsi, rax
0x18000e634  mov     [rsp+130h+var_D8], rax
0x18000e639  test    rax, rax
0x18000e63c  jz      loc_18000EA0E
0x18000e642  mov     r15d, 1
0x18000e648  xor     r9d, r9d
0x18000e64b  test    rbx, rbx
0x18000e64e  jz      loc_18000EA1F
0x18000e654  cmp     rbx, 7FFFFFFFh
0x18000e65b  ja      loc_18000EA18
0x18000e661  mov     eax, 7FFFFFFEh
0x18000e666  mov     rcx, rdi
0x18000e669  mov     rdx, rsi
0x18000e66c  test    rax, rax
0x18000e66f  jz      short loc_18000E68F
0x18000e671  movzx   r8d, word ptr [rcx]
0x18000e675  test    r8w, r8w
0x18000e679  jz      short loc_18000E68F
0x18000e67b  add     rcx, 2
0x18000e67f  mov     [rdx], r8w
0x18000e683  add     rdx, 2
0x18000e687  sub     rax, r15
0x18000e68a  sub     rbx, r15
0x18000e68d  jnz     short loc_18000E66C
0x18000e68f  mov     rax, rbx
0x18000e692  neg     rax
0x18000e695  sbb     edi, edi
0x18000e697  not     edi
0x18000e699  and     edi, 8007007Ah
0x18000e69f  lea     rcx, [rdx-2]
0x18000e6a3  test    rbx, rbx
0x18000e6a6  cmovnz  rcx, rdx
0x18000e6aa  mov     [rcx], r9w
0x18000e6ae  jnz     loc_18000E96F
0x18000e6b4  mov     rcx, rsi; hMem
0x18000e6b7  call    ?VaultFreeInternal@@YAXPEAE@Z; VaultFreeInternal(uchar *)
0x18000e6bc  xor     r9d, r9d
0x18000e6bf  mov     esi, r9d
0x18000e6c2  mov     [rsp+130h+var_D8], r9
0x18000e6c7  mov     eax, edi
0x18000e6c9  and     eax, 1FFF0000h
0x18000e6ce  movzx   ebx, di
0x18000e6d1  cmp     eax, 70000h
0x18000e6d6  cmovnz  ebx, edi
0x18000e6d9  test    ebx, ebx
0x18000e6db  jnz     loc_18000E8E2
0x18000e6e1  mov     dl, r15b; Wait
0x18000e6e4  mov     rcx, r14; Resource
0x18000e6e7  call    cs:__imp_RtlAcquireResourceExclusive
0x18000e6ed  mov     [rbp+57h+var_78], r15b
0x18000e6f1  mov     rax, [r13+0]
0x18000e6f5  lea     rdx, [rbp+57h+var_60]
0x18000e6f9  mov     rcx, r13
0x18000e6fc  mov     rax, [rax+18h]
0x18000e700  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e705  mov     ebx, eax
0x18000e707  test    eax, eax
0x18000e709  jnz     loc_18000E9C2
0x18000e70f  mov     [rbp+57h+var_70], r14
0x18000e713  mov     [rbp+57h+var_68], al
0x18000e716  cmp     [r12+120h], al
0x18000e71e  jnz     loc_18000E977
0x18000e724  mov     r13, [r12+8]
0x18000e729  mov     rdi, [r13+8]
0x18000e72d  xor     eax, eax
0x18000e72f  mov     dword ptr [rbp+57h+Buf1+0Ch], eax
0x18000e732  mov     rbx, r13
0x18000e735  movaps  xmm6, [rbp+57h+var_60]
0x18000e739  cmp     [rdi+19h], al
0x18000e73c  jnz     short loc_18000E77F
0x18000e73e  movdqa  [rbp+57h+Buf2], xmm6
0x18000e743  movups  xmm0, xmmword ptr [rdi+20h]
0x18000e747  movdqu  [rbp+57h+Buf1], xmm0
0x18000e74c  mov     r8d, 10h; Size
0x18000e752  lea     rdx, [rbp+57h+Buf2]; Buf2
0x18000e756  lea     rcx, [rbp+57h+Buf1]; Buf1
0x18000e75a  call    memcmp_0
0x18000e75f  test    eax, eax
0x18000e761  js      loc_18000E8D5
0x18000e767  xor     cl, cl
0x18000e769  mov     rbx, rdi
0x18000e76c  lea     rax, [rdi+10h]
0x18000e770  test    cl, cl
0x18000e772  cmovz   rax, rdi
0x18000e776  mov     rdi, [rax]
0x18000e779  cmp     byte ptr [rdi+19h], 0
0x18000e77d  jz      short loc_18000E73E
0x18000e77f  cmp     byte ptr [rbx+19h], 0
0x18000e783  jnz     loc_18000EA5A
0x18000e789  movups  xmm0, xmmword ptr [rbx+20h]
0x18000e78d  movdqu  [rbp+57h+Buf1], xmm0
0x18000e792  movdqa  [rbp+57h+Buf2], xmm6
0x18000e797  mov     r8d, 10h; Size
0x18000e79d  lea     rdx, [rbp+57h+Buf1]; Buf2
0x18000e7a1  lea     rcx, [rbp+57h+Buf2]; Buf1
0x18000e7a5  call    memcmp_0
0x18000e7aa  test    eax, eax
0x18000e7ac  js      loc_18000EA5A
0x18000e7b2  test    r15b, r15b
0x18000e7b5  cmovz   rbx, r13
0x18000e7b9  cmp     rbx, r13
0x18000e7bc  jz      loc_18000EA62
0x18000e7c2  mov     rcx, [rbx+30h]
0x18000e7c6  mov     rax, [rcx]
0x18000e7c9  mov     rax, [rax]
0x18000e7cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e7d1  mov     rax, [rbx+30h]
0x18000e7d5  mov     [rbp+57h+var_C0], rax
0x18000e7d9  cmp     dword ptr [rsp+130h+var_108], 0
0x18000e7de  jz      loc_18000EA04
0x18000e7e4  mov     rax, [r12]
0x18000e7e8  lea     r8, [rsp+130h+var_F0]
0x18000e7ed  mov     rdx, qword ptr [rsp+130h+FileTime2.dwLowDateTime]
0x18000e7f2  mov     rcx, r12
0x18000e7f5  mov     rax, [rax+0A8h]
0x18000e7fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e801  mov     edi, eax
0x18000e803  test    eax, eax
0x18000e805  jnz     loc_18000EAB0
0x18000e80b  mov     rbx, qword ptr [rsp+130h+FileTime1.dwLowDateTime]
0x18000e810  mov     rax, [rbx]
0x18000e813  lea     rdx, [rsp+130h+FileTime1]
0x18000e818  mov     rcx, rbx
0x18000e81b  mov     rax, [rax+0C0h]
0x18000e822  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e827  mov     rcx, [rsp+130h+var_F0]
0x18000e82c  mov     rax, [rcx]
0x18000e82f  lea     rdx, [rsp+130h+FileTime2]
0x18000e834  mov     rax, [rax+0C0h]
0x18000e83b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e840  mov     rcx, [rsp+130h+var_F0]
0x18000e845  mov     rax, [rcx]
0x18000e848  mov     rax, [rax+0A0h]
0x18000e84f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e854  bt      eax, 8
0x18000e858  jb      loc_18000E904
0x18000e85e  mov     r8, rsi; unsigned __int16 *
0x18000e861  mov     rdx, rbx; struct IVaultCredential *
0x18000e864  mov     rcx, r12; this
0x18000e867  call    ?SubmitCredentialToStoreNoAlloc@CVaultMemoryStore@@IEAAKPEAUIVaultCredential@@PEAG@Z; CVaultMemoryStore::SubmitCredentialToStoreNoAlloc(IVaultCredential *,ushort *)
0x18000e86c  mov     ebx, eax
0x18000e86e  mov     ecx, eax
0x18000e870  neg     ecx
0x18000e872  sbb     rdx, rdx
0x18000e875  and     rdx, rsi
0x18000e878  mov     [rsp+130h+var_D8], rdx
0x18000e87d  lea     rcx, [rbp+57h+var_C8]
0x18000e881  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18000e886  nop
0x18000e887  mov     rcx, r14; Resource
0x18000e88a  call    cs:__imp_RtlReleaseResource
0x18000e890  nop
0x18000e891  lea     rcx, [rsp+130h+var_F8]
0x18000e896  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18000e89b  nop
0x18000e89c  lea     rcx, [rsp+130h+var_E0]
0x18000e8a1  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18000e8a6  nop
0x18000e8a7  mov     eax, ebx
0x18000e8a9  mov     rcx, [rbp+57h+var_50]
0x18000e8ad  xor     rcx, rsp; StackCookie
0x18000e8b0  call    __security_check_cookie
0x18000e8b5  lea     r11, [rsp+130h+var_30]
0x18000e8bd  mov     rbx, [r11+58h]
0x18000e8c1  movaps  xmm6, xmmword ptr [r11-10h]
0x18000e8c6  mov     rsp, r11
0x18000e8c9  pop     r15
0x18000e8cb  pop     r14
0x18000e8cd  pop     r13
0x18000e8cf  pop     r12
0x18000e8d1  pop     rdi
0x18000e8d2  pop     rsi
0x18000e8d3  pop     rbp
0x18000e8d4  retn
0x18000e8d5  mov     cl, r15b
0x18000e8d8  jmp     loc_18000E76C
0x18000e8dd  mov     ebx, 216h
0x18000e8e2  lea     rcx, [rbp+57h+var_C8]
0x18000e8e6  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18000e8eb  nop
0x18000e8ec  lea     rcx, [rsp+130h+var_F8]
0x18000e8f1  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18000e8f6  nop
0x18000e8f7  lea     rcx, [rsp+130h+var_E0]
0x18000e8fc  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18000e901  nop
0x18000e902  jmp     short loc_18000E8A7
0x18000e904  lea     rdx, [rsp+130h+FileTime2]; lpFileTime2
0x18000e909  lea     rcx, [rsp+130h+FileTime1]; lpFileTime1
0x18000e90e  call    cs:__imp_CompareFileTime
0x18000e914  test    eax, eax
0x18000e916  jg      loc_18000E85E
0x18000e91c  lea     rcx, WPP_GLOBAL_Control
0x18000e923  mov     edi, 80040170h
0x18000e928  mov     rax, cs:WPP_GLOBAL_Control
0x18000e92f  cmp     rax, rcx
0x18000e932  jz      short loc_18000E93E
0x18000e934  test    byte ptr [rax+1Ch], 8
0x18000e938  jnz     loc_18000EA93
0x18000e93e  lea     rcx, [rbp+57h+var_C8]
0x18000e942  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18000e947  nop
0x18000e948  mov     rcx, r14; Resource
0x18000e94b  call    cs:__imp_RtlReleaseResource
0x18000e951  nop
0x18000e952  lea     rcx, [rsp+130h+var_F8]
0x18000e957  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18000e95c  nop
0x18000e95d  lea     rcx, [rsp+130h+var_E0]
0x18000e962  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18000e967  nop
0x18000e968  mov     eax, edi
0x18000e96a  jmp     loc_18000E8A9
0x18000e96f  mov     ebx, r9d
0x18000e972  jmp     loc_18000E6D9
0x18000e977  mov     ebx, 37h ; '7'
0x18000e97c  lea     rcx, WPP_GLOBAL_Control
0x18000e983  mov     rax, cs:WPP_GLOBAL_Control
0x18000e98a  cmp     rax, rcx
0x18000e98d  jnz     loc_18000EA6C
0x18000e993  lea     rcx, [rbp+57h+var_C8]
0x18000e997  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18000e99c  nop
0x18000e99d  mov     rcx, r14; Resource
0x18000e9a0  call    cs:__imp_RtlReleaseResource
0x18000e9a6  nop
0x18000e9a7  lea     rcx, [rsp+130h+var_F8]
0x18000e9ac  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18000e9b1  nop
0x18000e9b2  lea     rcx, [rsp+130h+var_E0]
0x18000e9b7  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18000e9bc  nop
0x18000e9bd  jmp     loc_18000E8A7
0x18000e9c2  lea     rcx, WPP_GLOBAL_Control
0x18000e9c9  mov     r10, cs:WPP_GLOBAL_Control
0x18000e9d0  cmp     r10, rcx
0x18000e9d3  jnz     short loc_18000EA36
0x18000e9d5  lea     rcx, [rbp+57h+var_C8]
0x18000e9d9  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18000e9de  nop
0x18000e9df  mov     rcx, r14; Resource
0x18000e9e2  call    cs:__imp_RtlReleaseResource
0x18000e9e8  nop
0x18000e9e9  lea     rcx, [rsp+130h+var_F8]
0x18000e9ee  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18000e9f3  nop
0x18000e9f4  lea     rcx, [rsp+130h+var_E0]
0x18000e9f9  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18000e9fe  nop
0x18000e9ff  jmp     loc_18000E8A7
0x18000ea04  mov     rbx, qword ptr [rsp+130h+FileTime1.dwLowDateTime]
  ... truncated ...
```
