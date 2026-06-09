# CopyThreadProc(void *)

- ea: `0x18000c380`
- end: `0x18000c826`
- name: `?CopyThreadProc@@YAKPEAX@Z`
- size: `1190`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `20`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000b0bc`
- `0x18000b430`
- `0x18000bfe0`
- `0x18000c07c`
- `0x18000c0d4`
- `0x18000c1b0`
- `0x18000c25c`
- `0x18000c2e4`
- `0x18000c314`
- `0x18000c380`
- `0x18000c82c`
- `0x18000d9b0`
- `0x180010c30`
- `0x18001860c`
- `0x180026590`
- `0x180036f50`
- `0x180037350`
- `0x1800390fd`
- `0x1800405b4`
- `0x180071010`

## import_xrefs

- `SHELL32!SHChangeNotifySuspendResume` at `0x18000c56e`
- `SHELL32!SHChangeNotifySuspendResume` at `0x18000c73a`
- `SHELL32!SHChangeNotifySuspendResume` at `0x18000c56e`
- `SHELL32!SHChangeNotifySuspendResume` at `0x18000c73a`
- `SHELL32!SHChangeNotify` at `0x18000c55a`
- `SHELL32!SHChangeNotify` at `0x18000c5f5`
- `SHELL32!SHChangeNotify` at `0x18000c618`
- `SHELL32!SHChangeNotify` at `0x18000c74f`
- `SHELL32!SHChangeNotify` at `0x18000c55a`
- `SHELL32!SHChangeNotify` at `0x18000c5f5`
- `SHELL32!SHChangeNotify` at `0x18000c618`
- `SHELL32!SHChangeNotify` at `0x18000c74f`
- `SHELL32!__imp_ILClone` at `0x18000c771`
- `SHELL32!__imp_ILClone` at `0x18000c771`
- `SHELL32!__imp_SHILCreateFromPath` at `0x18000c53f`
- `SHELL32!__imp_SHILCreateFromPath` at `0x18000c53f`
- `SHELL32!__imp_ILFree` at `0x18000c75a`
- `SHELL32!__imp_ILFree` at `0x18000c7a0`
- `SHELL32!__imp_ILFree` at `0x18000c75a`
- `SHELL32!__imp_ILFree` at `0x18000c7a0`
- `SHELL32!__imp_ILCreateFromPathW` at `0x18000c7ae`
- `SHELL32!__imp_ILCreateFromPathW` at `0x18000c7ae`
- `SHLWAPI!PathRemoveFileSpecW` at `0x18000c481`
- `SHLWAPI!PathRemoveFileSpecW` at `0x18000c481`
- `api-ms-win-core-com-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x18000c409`
- `api-ms-win-core-com-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x18000c409`
- `KERNEL32!lstrlenW` at `0x18000c57f`
- `KERNEL32!lstrlenW` at `0x18000c58d`
- `KERNEL32!lstrlenW` at `0x18000c707`
- `KERNEL32!lstrlenW` at `0x18000c71b`
- `KERNEL32!lstrlenW` at `0x18000c57f`
- `KERNEL32!lstrlenW` at `0x18000c58d`
- `KERNEL32!lstrlenW` at `0x18000c707`
- `KERNEL32!lstrlenW` at `0x18000c71b`

## pseudocode

```c
__int64 __fastcall CopyThreadProc(char *Parameter, __int64 a2, int a3, int a4)
{
  IStream *v5; // rcx
  const WCHAR *v6; // rdi
  int v7; // r12d
  unsigned int v8; // r13d
  __int64 v9; // rcx
  WCHAR *v10; // r8
  WCHAR *v11; // rax
  __int64 v12; // rdx
  WCHAR *v13; // rcx
  unsigned int v14; // edi
  unsigned __int64 v15; // rax
  unsigned __int16 *v16; // rax
  unsigned __int16 *v17; // r14
  unsigned __int16 *v18; // rdi
  unsigned __int16 *v19; // rsi
  int v20; // eax
  char *v21; // r8
  UINT v22; // edx
  LONG v23; // ecx
  LPVOID v24; // rcx
  int v25; // ecx
  int v26; // r8d
  int v27; // r9d
  int v29; // eax
  int v30; // eax
  const ITEMIDLIST *v31; // rcx
  LPITEMIDLIST v32; // rax
  ITEMIDLIST *v33; // rsi
  unsigned int v34; // [rsp+28h] [rbp-D8h]
  int v35; // [rsp+40h] [rbp-C0h] BYREF
  LPITEMIDLIST ppidl; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID ppv; // [rsp+50h] [rbp-B0h] BYREF
  void **v38; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v39[272]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v40[8]; // [rsp+178h] [rbp+78h] BYREF
  _BYTE v41[24]; // [rsp+180h] [rbp+80h] BYREF
  int v42; // [rsp+198h] [rbp+98h]
  struct _EVENT_DATA_DESCRIPTOR v43; // [rsp+1B0h] [rbp+B0h] BYREF
  WCHAR pszPath[264]; // [rsp+1C0h] [rbp+C0h] BYREF

  if ( (Microsoft_Windows_Shell_ZipFolderEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer((int)Parameter, (int)&ShellTraceId_ZipFolder_DropIn_Start, a3, a4, &v43);
  wil::ActivityBase<FileExplorerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<FileExplorerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(
    &v38,
    "ZipOperation");
  v38 = &FileExplorerTelemetry::ZipOperation::`vftable';
  FileExplorerTelemetry::ZipOperation::StartActivity((FileExplorerTelemetry::ZipOperation *)&v38);
  ZipInit();
  v5 = (IStream *)*((_QWORD *)Parameter + 135);
  ppv = 0;
  CoGetInterfaceAndReleaseStream(v5, &GUID_dcb07fdc_3bb5_451c_90be_966644fed7b0, &ppv);
  v6 = (const WCHAR *)*((_QWORD *)Parameter + 132);
  v7 = 0;
  *((_QWORD *)Parameter + 135) = 0;
  v8 = 0;
  while ( *v6 )
  {
    ++v7;
    v8 += lstrlenW(v6) + 1;
    v6 += lstrlenW(v6) + 1;
  }
  v9 = 2147483646;
  v10 = (WCHAR *)(Parameter + 8);
  v11 = pszPath;
  v12 = 260;
  do
  {
    if ( !v9 )
      break;
    if ( !*v10 )
      break;
    *v11++ = *v10++;
    --v9;
    --v12;
  }
  while ( v12 );
  ppidl = 0;
  v13 = v11 - 1;
  if ( v12 )
    v13 = v11;
  *v13 = 0;
  if ( PathRemoveFileSpecW(pszPath) && SHILCreateFromPath(pszPath, &ppidl, 0) >= 0 )
  {
    SHChangeNotify(0, 0x1000u, 0, 0);
    SHChangeNotifySuspendResume(1, ppidl);
  }
  v14 = -2147024882;
  v15 = 2LL * (v8 + 1);
  if ( !is_mul_ok(v8 + 1, 2u) )
    v15 = -1;
  v16 = (unsigned __int16 *)operator new[](v15, (const struct std::nothrow_t *)&std::nothrow);
  v17 = v16;
  if ( v16 )
  {
    memcpy_0(v16, *((const void **)Parameter + 132), 2LL * (v8 + 1));
    v18 = (unsigned __int16 *)*((_QWORD *)Parameter + 132);
    v19 = v17;
    while ( *v18 )
    {
      v35 = 0;
      v20 = CheckSameFileInZip(
              (const unsigned __int16 *)Parameter + 4,
              (const unsigned __int16 *)Parameter + 264,
              v18,
              v7,
              *(HWND *)Parameter,
              v34,
              &v35)
          - 2;
      if ( !v20 )
      {
        v14 = 1;
        goto LABEL_27;
      }
      v29 = v20 - 4;
      if ( v29 )
      {
        if ( v29 != 1 )
        {
          v14 = -2147467259;
          goto LABEL_27;
        }
      }
      else
      {
        StringCchCopyW(v19, v8, v18);
        v30 = lstrlenW(v18) + 1;
        v8 -= v30;
        v19 += v30;
      }
      --v7;
      v18 += lstrlenW(v18) + 1;
    }
    if ( v19 == v17 )
    {
      v14 = 1;
    }
    else
    {
      *v19 = 0;
      v14 = TempFilesToZip(
              *(HWND *)Parameter,
              (unsigned __int16 *)Parameter + 4,
              v17,
              (unsigned __int16 *)Parameter + 264,
              *((unsigned __int16 **)Parameter + 131),
              *((_DWORD *)Parameter + 267),
              *((_DWORD *)Parameter + 266));
      if ( !v14 )
      {
        SHChangeNotify(0, 0x1000u, 0, 0);
        v21 = (char *)*((_QWORD *)Parameter + 134);
        if ( v21 )
        {
          v22 = 4096;
          v23 = 0x2000;
        }
        else
        {
          v21 = Parameter + 8;
          v22 = 4101;
          v23 = 2;
        }
        SHChangeNotify(v23, v22, v21, 0);
        if ( ppv )
        {
          v31 = (const ITEMIDLIST *)*((_QWORD *)Parameter + 134);
          v32 = v31 ? ILClone(v31) : ILCreateFromPathW((PCWSTR)Parameter + 4);
          v33 = v32;
          if ( v32 )
          {
            (*(void (__fastcall **)(LPVOID, LPITEMIDLIST, __int64))(*(_QWORD *)ppv + 32LL))(ppv, v32, 3);
            ILFree(v33);
          }
        }
      }
    }
LABEL_27:
    if ( ppidl )
    {
      SHChangeNotifySuspendResume(0, ppidl);
      SHChangeNotify(4096, 0, ppidl, 0);
      ILFree(ppidl);
    }
    operator delete(v17);
  }
  wil::ActivityBase<FileExplorerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(&v38, v14);
  v24 = ppv;
  ppv = 0;
  if ( v24 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v24 + 16LL))(v24);
  FreeThreadParams((struct THREADPARAMS *)Parameter);
  ZipDeInit();
  if ( (Microsoft_Windows_Shell_ZipFolderEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(v25, (int)&ShellTraceId_ZipFolder_DropIn_Stop, v26, v27, &v43);
  v38 = &FileExplorerTelemetry::ZipOperation::`vftable';
  wil::ActivityBase<FileExplorerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v38);
  if ( v42 )
    wil::details::ThreadFailureCallbackHolder::StopWatching((wil::details::ThreadFailureCallbackHolder *)v41);
  wil::details::shared_object<wil::ActivityBase<FileExplorerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<FileExplorerLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(v40);
  wil::ActivityBase<FileExplorerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<FileExplorerLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<FileExplorerLogging,_TlgReflectorTag_Param0IsProviderType>(v39);
  return 0;
}

```

## disassembly

```asm
0x18000c380  push    rbp
0x18000c382  push    rbx
0x18000c383  push    rsi
0x18000c384  push    rdi
0x18000c385  push    r12
0x18000c387  push    r13
0x18000c389  push    r14
0x18000c38b  push    r15
0x18000c38d  lea     rbp, [rsp-2E8h]
0x18000c395  sub     rsp, 3E8h
0x18000c39c  mov     rax, cs:__security_cookie
0x18000c3a3  xor     rax, rsp
0x18000c3a6  mov     [rbp+320h+var_50], rax
0x18000c3ad  mov     r14d, 1
0x18000c3b3  mov     rbx, rcx
0x18000c3b6  test    cs:Microsoft_Windows_Shell_ZipFolderEnableBits, r14b
0x18000c3bd  jnz     loc_18000C7C9
0x18000c3c3  lea     rdx, aZipoperation; "ZipOperation"
0x18000c3ca  lea     rcx, [rsp+420h+var_3C0]
0x18000c3cf  call    ??0?$ActivityBase@VFileExplorerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<FileExplorerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<FileExplorerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18000c3d4  lea     rax, ??_7ZipOperation@FileExplorerTelemetry@@6B@; const FileExplorerTelemetry::ZipOperation::`vftable'
0x18000c3db  lea     rcx, [rsp+420h+var_3C0]; this
0x18000c3e0  mov     [rsp+420h+var_3C0], rax
0x18000c3e5  call    ?StartActivity@ZipOperation@FileExplorerTelemetry@@QEAAXXZ; FileExplorerTelemetry::ZipOperation::StartActivity(void)
0x18000c3ea  call    ?ZipInit@@YAXXZ; ZipInit(void)
0x18000c3ef  mov     rcx, [rbx+438h]; pStm
0x18000c3f6  lea     r8, [rsp+420h+ppv]; ppv
0x18000c3fb  xor     esi, esi
0x18000c3fd  lea     rdx, _GUID_dcb07fdc_3bb5_451c_90be_966644fed7b0; iid
0x18000c404  mov     [rsp+420h+ppv], rsi
0x18000c409  call    cs:__imp_CoGetInterfaceAndReleaseStream
0x18000c40f  mov     rdi, [rbx+420h]
0x18000c416  mov     r12d, esi
0x18000c419  mov     [rbx+438h], rsi
0x18000c420  mov     r13d, esi
0x18000c423  cmp     [rdi], si
0x18000c426  jnz     loc_18000C579
0x18000c42c  lea     r15, [rbx+8]
0x18000c430  mov     ecx, 7FFFFFFEh
0x18000c435  mov     r8, r15
0x18000c438  lea     rax, [rbp+320h+pszPath]
0x18000c43f  mov     edx, 104h
0x18000c444  test    rcx, rcx
0x18000c447  jz      short loc_18000C467
0x18000c449  movzx   r9d, word ptr [r8]
0x18000c44d  test    r9w, r9w
0x18000c451  jz      short loc_18000C467
0x18000c453  mov     [rax], r9w
0x18000c457  add     r8, 2
0x18000c45b  add     rax, 2
0x18000c45f  sub     rcx, r14
0x18000c462  sub     rdx, r14
0x18000c465  jnz     short loc_18000C444
0x18000c467  test    rdx, rdx
0x18000c46a  mov     [rsp+420h+ppidl], rsi
0x18000c46f  lea     rcx, [rax-2]
0x18000c473  cmovnz  rcx, rax
0x18000c477  mov     [rcx], si
0x18000c47a  lea     rcx, [rbp+320h+pszPath]; pszPath
0x18000c481  call    cs:__imp_PathRemoveFileSpecW
0x18000c487  test    eax, eax
0x18000c489  jnz     loc_18000C530
0x18000c48f  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000c496  lea     esi, [r13+1]
0x18000c49a  mov     eax, 2
0x18000c49f  mov     edi, 8007000Eh
0x18000c4a4  mul     rsi
0x18000c4a7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000c4ae  cmovb   rax, rcx
0x18000c4b2  mov     rcx, rax; unsigned __int64
0x18000c4b5  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000c4ba  mov     r14, rax
0x18000c4bd  test    rax, rax
0x18000c4c0  jz      loc_18000C7F0
0x18000c4c6  mov     rdx, [rbx+420h]; Src
0x18000c4cd  lea     r8, [rsi+rsi]; Size
0x18000c4d1  mov     rcx, rax; void *
0x18000c4d4  call    memcpy_0
0x18000c4d9  mov     rdi, [rbx+420h]
0x18000c4e0  mov     rsi, r14
0x18000c4e3  xor     eax, eax
0x18000c4e5  lea     rcx, [rbx+210h]
0x18000c4ec  cmp     [rdi], ax
0x18000c4ef  jz      loc_18000C5A1
0x18000c4f5  mov     [rsp+420h+var_3E0], eax
0x18000c4f9  mov     rdx, rcx; unsigned __int16 *
0x18000c4fc  lea     rax, [rsp+420h+var_3E0]
0x18000c501  mov     r9d, r12d; unsigned int
0x18000c504  mov     [rsp+420h+var_3F0], rax; int *
0x18000c509  mov     r8, rdi; unsigned __int16 *
0x18000c50c  mov     rax, [rbx]
0x18000c50f  mov     rcx, r15; unsigned __int16 *
0x18000c512  mov     [rsp+420h+var_400], rax; HWND
0x18000c517  call    ?CheckSameFileInZip@@YAKPEBG0PEAGIPEAUHWND__@@HPEAH@Z; CheckSameFileInZip(ushort const *,ushort const *,ushort *,uint,HWND__ *,int,int *)
0x18000c51c  sub     eax, 2
0x18000c51f  jnz     loc_18000C6ED
0x18000c525  lea     edi, [rax+1]
0x18000c528  xor     r12d, r12d
0x18000c52b  jmp     loc_18000C629
0x18000c530  xor     r8d, r8d; rgfInOut
0x18000c533  lea     rdx, [rsp+420h+ppidl]; ppidl
0x18000c538  lea     rcx, [rbp+320h+pszPath]; pszPath
0x18000c53f  call    cs:__imp_SHILCreateFromPath
0x18000c545  test    eax, eax
0x18000c547  js      loc_18000C48F
0x18000c54d  xor     r9d, r9d; dwItem2
0x18000c550  xor     r8d, r8d; dwItem1
0x18000c553  mov     edx, 1000h; uFlags
0x18000c558  xor     ecx, ecx; wEventId
0x18000c55a  call    cs:__imp_SHChangeNotify
0x18000c560  mov     rdx, [rsp+420h+ppidl]
0x18000c565  xor     r9d, r9d
0x18000c568  mov     r8d, r14d
0x18000c56b  mov     ecx, r14d
0x18000c56e  call    cs:__imp_SHChangeNotifySuspendResume
0x18000c574  jmp     loc_18000C48F
0x18000c579  mov     rcx, rdi; lpString
0x18000c57c  add     r12d, r14d
0x18000c57f  call    cs:__imp_lstrlenW
0x18000c585  inc     eax
0x18000c587  mov     rcx, rdi; lpString
0x18000c58a  add     r13d, eax
0x18000c58d  call    cs:__imp_lstrlenW
0x18000c593  add     eax, r14d
0x18000c596  cdqe
0x18000c598  lea     rdi, [rdi+rax*2]
0x18000c59c  jmp     loc_18000C423
0x18000c5a1  xor     r12d, r12d
0x18000c5a4  cmp     rsi, r14
0x18000c5a7  jz      loc_18000C7E6
0x18000c5ad  mov     [rsi], r12w
0x18000c5b1  mov     r9, rcx; unsigned __int16 *
0x18000c5b4  mov     eax, [rbx+428h]
0x18000c5ba  mov     r8, r14; unsigned __int16 *
0x18000c5bd  mov     rcx, [rbx]; HWND
0x18000c5c0  mov     rdx, r15; unsigned __int16 *
0x18000c5c3  mov     dword ptr [rsp+420h+var_3F0], eax; int
0x18000c5c7  mov     eax, [rbx+42Ch]
0x18000c5cd  mov     [rsp+420h+var_3F8], eax; unsigned int
0x18000c5d1  mov     rax, [rbx+418h]
0x18000c5d8  mov     [rsp+420h+var_400], rax; unsigned __int16 *
0x18000c5dd  call    ?TempFilesToZip@@YAJPEAUHWND__@@PEBG11PEAGIH@Z; TempFilesToZip(HWND__ *,ushort const *,ushort const *,ushort const *,ushort *,uint,int)
0x18000c5e2  mov     edi, eax
0x18000c5e4  test    eax, eax
0x18000c5e6  jnz     short loc_18000C629
0x18000c5e8  xor     r9d, r9d; dwItem2
0x18000c5eb  xor     r8d, r8d; dwItem1
0x18000c5ee  mov     edx, 1000h; uFlags
0x18000c5f3  xor     ecx, ecx; wEventId
0x18000c5f5  call    cs:__imp_SHChangeNotify
0x18000c5fb  mov     r8, [rbx+430h]; dwItem1
0x18000c602  xor     r9d, r9d; dwItem2
0x18000c605  test    r8, r8
0x18000c608  jz      loc_18000C6DB
0x18000c60e  mov     edx, 1000h; uFlags
0x18000c613  mov     ecx, 2000h; wEventId
0x18000c618  call    cs:__imp_SHChangeNotify
0x18000c61e  cmp     [rsp+420h+ppv], r12
0x18000c623  jnz     loc_18000C765
0x18000c629  mov     rdx, [rsp+420h+ppidl]
0x18000c62e  test    rdx, rdx
0x18000c631  jnz     loc_18000C731
0x18000c637  mov     rcx, r14; lpMem
0x18000c63a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000c63f  mov     edx, edi
0x18000c641  lea     rcx, [rsp+420h+var_3C0]
0x18000c646  call    ?Stop@?$ActivityBase@VFileExplorerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<FileExplorerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18000c64b  mov     rcx, [rsp+420h+ppv]
0x18000c650  mov     [rsp+420h+ppv], r12
0x18000c655  test    rcx, rcx
0x18000c658  jz      short loc_18000C666
0x18000c65a  mov     rax, [rcx]
0x18000c65d  mov     rax, [rax+10h]
0x18000c661  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c666  mov     rcx, rbx; struct THREADPARAMS *
0x18000c669  call    ?FreeThreadParams@@YAXPEAUTHREADPARAMS@@@Z; FreeThreadParams(THREADPARAMS *)
0x18000c66e  call    ?ZipDeInit@@YAXXZ; ZipDeInit(void)
0x18000c673  test    cs:Microsoft_Windows_Shell_ZipFolderEnableBits, 1
0x18000c67a  jnz     loc_18000C7F8
0x18000c680  lea     rax, ??_7ZipOperation@FileExplorerTelemetry@@6B@; const FileExplorerTelemetry::ZipOperation::`vftable'
0x18000c687  lea     rcx, [rsp+420h+var_3C0]
0x18000c68c  mov     [rsp+420h+var_3C0], rax
0x18000c691  call    ?Destroy@?$ActivityBase@VFileExplorerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<FileExplorerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18000c696  cmp     [rbp+320h+var_288], r12d
0x18000c69d  jnz     loc_18000C815
0x18000c6a3  lea     rcx, [rbp+320h+var_2A8]
0x18000c6a7  call    ?reset@?$shared_object@V?$ActivityData@VFileExplorerLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VFileExplorerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<FileExplorerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<FileExplorerLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x18000c6ac  lea     rcx, [rsp+420h+var_3B8]
0x18000c6b1  call    ??1?$ActivityData@VFileExplorerLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VFileExplorerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<FileExplorerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<FileExplorerLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<FileExplorerLogging,_TlgReflectorTag_Param0IsProviderType>(void)
0x18000c6b6  xor     eax, eax
0x18000c6b8  mov     rcx, [rbp+320h+var_50]
0x18000c6bf  xor     rcx, rsp; StackCookie
0x18000c6c2  call    __security_check_cookie
0x18000c6c7  add     rsp, 3E8h
0x18000c6ce  pop     r15
0x18000c6d0  pop     r14
0x18000c6d2  pop     r13
0x18000c6d4  pop     r12
0x18000c6d6  pop     rdi
0x18000c6d7  pop     rsi
0x18000c6d8  pop     rbx
0x18000c6d9  pop     rbp
0x18000c6da  retn
0x18000c6db  mov     r8, r15
0x18000c6de  mov     edx, 1005h
0x18000c6e3  mov     ecx, 2
0x18000c6e8  jmp     loc_18000C618
0x18000c6ed  sub     eax, 4
0x18000c6f0  jnz     loc_18000C7B6
0x18000c6f6  mov     edx, r13d; unsigned __int64
0x18000c6f9  mov     r8, rdi; unsigned __int16 *
0x18000c6fc  mov     rcx, rsi; unsigned __int16 *
0x18000c6ff  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000c704  mov     rcx, rdi; lpString
0x18000c707  call    cs:__imp_lstrlenW
0x18000c70d  inc     eax
0x18000c70f  sub     r13d, eax
0x18000c712  cdqe
0x18000c714  lea     rsi, [rsi+rax*2]
0x18000c718  mov     rcx, rdi; lpString
0x18000c71b  call    cs:__imp_lstrlenW
0x18000c721  inc     eax
0x18000c723  cdqe
0x18000c725  dec     r12d
0x18000c728  lea     rdi, [rdi+rax*2]
0x18000c72c  jmp     loc_18000C4E3
0x18000c731  xor     r9d, r9d
0x18000c734  xor     ecx, ecx
0x18000c736  lea     r8d, [r9+1]
0x18000c73a  call    cs:__imp_SHChangeNotifySuspendResume
0x18000c740  mov     r8, [rsp+420h+ppidl]; dwItem1
0x18000c745  xor     r9d, r9d; dwItem2
0x18000c748  xor     edx, edx; uFlags
0x18000c74a  mov     ecx, 1000h; wEventId
0x18000c74f  call    cs:__imp_SHChangeNotify
0x18000c755  mov     rcx, [rsp+420h+ppidl]; pidl
0x18000c75a  call    cs:__imp_ILFree
0x18000c760  jmp     loc_18000C637
0x18000c765  mov     rcx, [rbx+430h]; pidl
0x18000c76c  test    rcx, rcx
0x18000c76f  jz      short loc_18000C7AB
0x18000c771  call    cs:__imp_ILClone
0x18000c777  mov     rsi, rax
0x18000c77a  test    rax, rax
0x18000c77d  jz      loc_18000C629
0x18000c783  mov     rcx, [rsp+420h+ppv]
0x18000c788  mov     r8d, 3
0x18000c78e  mov     rdx, rsi
0x18000c791  mov     rax, [rcx]
0x18000c794  mov     rax, [rax+20h]
0x18000c798  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c79d  mov     rcx, rsi; pidl
0x18000c7a0  call    cs:__imp_ILFree
0x18000c7a6  jmp     loc_18000C629
0x18000c7ab  mov     rcx, r15; pszPath
0x18000c7ae  call    cs:__imp_ILCreateFromPathW
0x18000c7b4  jmp     short loc_18000C777
0x18000c7b6  cmp     eax, 1
0x18000c7b9  jz      loc_18000C718
0x18000c7bf  mov     edi, 80004005h
0x18000c7c4  jmp     loc_18000C528
0x18000c7c9  lea     rax, [rbp+320h+var_270]
0x18000c7d0  lea     rdx, ShellTraceId_ZipFolder_DropIn_Start; int
0x18000c7d7  mov     [rsp+420h+var_400], rax; PEVENT_DATA_DESCRIPTOR
0x18000c7dc  call    McGenEventWrite_EventWriteTransfer
0x18000c7e1  jmp     loc_18000C3C3
0x18000c7e6  mov     edi, 1
0x18000c7eb  jmp     loc_18000C629
0x18000c7f0  xor     r12d, r12d
0x18000c7f3  jmp     loc_18000C63F
0x18000c7f8  lea     rax, [rbp+320h+var_270]
0x18000c7ff  lea     rdx, ShellTraceId_ZipFolder_DropIn_Stop; int
0x18000c806  mov     [rsp+420h+var_400], rax; PEVENT_DATA_DESCRIPTOR
0x18000c80b  call    McGenEventWrite_EventWriteTransfer
0x18000c810  jmp     loc_18000C680
0x18000c815  lea     rcx, [rbp+320h+var_2A0]; this
0x18000c81c  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x18000c821  jmp     loc_18000C6A3
```
