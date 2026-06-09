# CFveAutoPtr::Initialize(int,int *)

- ea: `0x18006c3f0`
- end: `0x18006c944`
- name: `?Initialize@CFveAutoPtr@@QEAAKHPEAH@Z`
- size: `1364`
- prototype: `unsigned int __fastcall(CFveAutoPtr *__hidden this, int, int *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18006a0a8`

## callees

- `0x180040c24`
- `0x18006a608`
- `0x18006a7e8`
- `0x18006c1a0`
- `0x18006c3f0`
- `0x18006c94c`
- `0x18006cbe0`
- `0x18006ce30`
- `0x18007728a`
- `0x1800772c0`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006c6c3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006c6c3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006c6d4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006c6d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006c4ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006c4ab`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x18006c49f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x18006c49f`

## string_xrefs

- `0x18006c52d`: `onecore\ds\security\eas\policyengine\extnlib\fvewrappers.cpp`
- `0x18006c709`: `onecore\ds\security\eas\policyengine\extnlib\fvewrappers.cpp`
- `0x18006c892`: `onecore\ds\security\eas\policyengine\extnlib\fvewrappers.cpp`
- `0x18006c8b2`: `onecore\ds\security\eas\policyengine\extnlib\fvewrappers.cpp`
- `0x18006c8ed`: `onecore\ds\security\eas\policyengine\extnlib\fvewrappers.cpp`
- `0x18006c5cd`: `EncryptHandle::CreateEncryptHandle`
- `0x18006c626`: `OpenVolume`
- `0x18006c8dc`: `Transforming the fvewarpper object to perform registry only check`

## pseudocode

```c
__int64 __fastcall CFveAutoPtr::Initialize(CFveAutoPtr *this, __int64 a2, int *a3)
{
  CFveAutoPtr *v4; // r14
  unsigned __int64 v5; // rdx
  const unsigned __int16 *v6; // r8
  int v7; // eax
  __int64 v8; // r8
  UINT v9; // ebx
  LPWSTR v10; // rdi
  UINT SystemWindowsDirectoryW; // ecx
  signed int LastError; // eax
  unsigned int v13; // ebx
  unsigned int v14; // eax
  int v15; // ebx
  BOOL v16; // eax
  bool v17; // zf
  _QWORD *v18; // rbx
  int EncryptHandle; // eax
  const wchar_t *v20; // r15
  int v21; // edx
  _QWORD *v22; // r15
  int v23; // eax
  int v24; // eax
  int *v25; // rsi
  int v26; // eax
  const wchar_t *v27; // rax
  unsigned int v28; // r12d
  HANDLE ProcessHeap; // rax
  LPVOID v30; // rax
  int v31; // eax
  int v32; // eax
  unsigned int v33; // r15d
  __int64 v34; // rsi
  int v35; // r14d
  int v36; // r12d
  WCHAR *v37; // rcx
  __int64 v38; // rbx
  WCHAR *v39; // r14
  __int128 v40; // xmm0
  __int64 v41; // rax
  __int64 v42; // rax
  unsigned int *v44; // [rsp+20h] [rbp-E0h]
  unsigned int *v45; // [rsp+20h] [rbp-E0h]
  unsigned int *v46; // [rsp+20h] [rbp-E0h]
  unsigned int *v47; // [rsp+20h] [rbp-E0h]
  unsigned int *v48; // [rsp+20h] [rbp-E0h]
  unsigned int v49; // [rsp+28h] [rbp-D8h]
  int v50; // [rsp+40h] [rbp-C0h] BYREF
  LPWSTR lpBuffer; // [rsp+48h] [rbp-B8h] BYREF
  UINT uSize[2]; // [rsp+50h] [rbp-B0h] BYREF
  CFveAutoPtr *v53; // [rsp+58h] [rbp-A8h]
  unsigned __int16 v54[264]; // [rsp+60h] [rbp-A0h] BYREF

  v53 = this;
  v4 = this;
  memset_0(v54, 0, 0x208u);
  v50 = 0;
  if ( a3 )
    *a3 = 0;
  *(_QWORD *)uSize = 0;
  lpBuffer = 0;
  v7 = StringCchCopyExW(v54, v5, v6, &lpBuffer, (unsigned __int64 *)uSize, v49);
  v8 = (unsigned int)v7;
  if ( v7 < 0 )
  {
LABEL_12:
    if ( (v8 & 0x1FFF0000) != 0x70000 )
    {
      v13 = v8;
      goto LABEL_64;
    }
LABEL_63:
    v13 = (unsigned __int16)v8;
    goto LABEL_64;
  }
  v9 = uSize[0];
  if ( *(_QWORD *)uSize > 0xFFFFFFFF )
  {
    v8 = 2147942934LL;
    goto LABEL_63;
  }
  v10 = lpBuffer;
  SystemWindowsDirectoryW = GetSystemWindowsDirectoryW(lpBuffer, uSize[0]);
  if ( SystemWindowsDirectoryW )
  {
    v10[2] = 0;
    v8 = v9 < SystemWindowsDirectoryW ? 0x80070057 : 0;
  }
  else
  {
    LastError = GetLastError();
    v8 = (unsigned int)LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
  }
  if ( (_DWORD)v8 )
  {
    if ( (int)v8 >= 0 )
    {
      v13 = 0;
LABEL_64:
      v50 = 708;
      v20 = L"EasGetOSVolume";
      v21 = 707;
LABEL_65:
      v27 = v20;
      goto LABEL_66;
    }
    goto LABEL_12;
  }
  v14 = CheckThirdPartyStatus(&v50);
  v13 = v14;
  if ( v14 )
  {
    LODWORD(v44) = 715;
    DbgPrintfW(
      1u,
      L"(0x%08x) %ws:%u : %ws:%ws\n",
      v14,
      L"onecore\\ds\\security\\eas\\policyengine\\extnlib\\fvewrappers.cpp",
      v44,
      L"CheckThirdPartyStatus",
      &Class);
    LODWORD(v45) = 716;
    DbgPrintfW(
      1u,
      L"(0x%08x) %ws:%u : %ws:%ws\n",
      v13,
      L"onecore\\ds\\security\\eas\\policyengine\\extnlib\\fvewrappers.cpp",
      v45,
      L"CheckThirdPartyStatus",
      &Class);
LABEL_67:
    LODWORD(v46) = 802;
    DbgPrintfW(
      1u,
      L"(0x%08x) %ws:%u : %ws:%ws\n",
      v13,
      L"onecore\\ds\\security\\eas\\policyengine\\extnlib\\fvewrappers.cpp",
      v46,
      L"Transforming the fvewarpper object to perform registry only check",
      &Class);
    *((_DWORD *)v4 + 1) = 0;
    goto LABEL_68;
  }
  v15 = v50;
  v16 = v50 == 0;
  *((_DWORD *)v4 + 27) = v16;
  if ( !v16 )
    SQMBitLockerIfNeeded();
  v17 = v15 == 0;
  v18 = (_QWORD *)((char *)v4 + 128);
  EncryptHandle = EncryptHandle::CreateEncryptHandle((char *)v4 + 128, v17);
  v8 = (unsigned int)EncryptHandle;
  if ( EncryptHandle )
  {
    if ( EncryptHandle < 0 )
    {
      v13 = (unsigned __int16)EncryptHandle;
      if ( (EncryptHandle & 0x1FFF0000) != 0x70000 )
        v13 = EncryptHandle;
      if ( v13 == 126 && a3 )
        *a3 = 1;
    }
    else
    {
      v13 = 0;
    }
    v50 = 733;
    v20 = L"EncryptHandle::CreateEncryptHandle";
    v21 = 732;
    goto LABEL_65;
  }
  v22 = (_QWORD *)((char *)v4 + 120);
  v23 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *, __int64, __int64))(*(_QWORD *)*v18 + 8LL))(
          *v18,
          v54,
          1,
          (__int64)v4 + 120);
  v8 = (unsigned int)v23;
  if ( v23 )
  {
    if ( v23 < 0 )
    {
      v13 = (unsigned __int16)v23;
      if ( (v23 & 0x1FFF0000) != 0x70000 )
        v13 = v23;
    }
    else
    {
      v13 = 0;
    }
    v50 = 741;
    v20 = L"OpenVolume";
    v21 = 740;
    goto LABEL_65;
  }
  v24 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(*(_QWORD *)*v18 + 16LL))(*v18, *v22, 0);
  *((_DWORD *)v4 + 1) = v24 == 0;
  if ( v24 )
  {
LABEL_61:
    v13 = 0;
    goto LABEL_68;
  }
  v25 = (int *)((char *)v4 + 16);
  v26 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64))(*(_QWORD *)*v18 + 40LL))(
          *v18,
          *v22,
          *((_QWORD *)v4 + 1),
          (__int64)v4 + 16);
  v8 = (unsigned int)v26;
  if ( v26 )
  {
    if ( v26 < 0 )
    {
      v13 = (unsigned __int16)v26;
      if ( (v26 & 0x1FFF0000) != 0x70000 )
        v13 = v26;
    }
    else
    {
      v13 = 0;
    }
    v27 = L"EasGetDeviceLockoutData";
    v50 = 755;
    v20 = L"EasGetDeviceLockoutData";
    v21 = 754;
    goto LABEL_66;
  }
  v28 = *v25;
  if ( !*v25 )
    goto LABEL_50;
  ProcessHeap = GetProcessHeap();
  v30 = HeapAlloc(ProcessHeap, 8u, v28);
  *((_QWORD *)v4 + 1) = v30;
  if ( !v30 )
  {
    v13 = 14;
    LODWORD(v44) = 764;
    DbgPrintfW(
      1u,
      L"(0x%08x) %ws:%u : %ws:%ws\n",
      14,
      L"onecore\\ds\\security\\eas\\policyengine\\extnlib\\fvewrappers.cpp",
      v44,
      L"HeapAlloc",
      &Class);
    goto LABEL_67;
  }
  v31 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, LPVOID, __int64))(*(_QWORD *)*v18 + 40LL))(
          *v18,
          *v22,
          v30,
          (__int64)v4 + 16);
  v8 = (unsigned int)v31;
  if ( !v31 )
  {
LABEL_50:
    v13 = UnpackEASLockoutData(
            *((unsigned __int8 **)v4 + 1),
            *v25,
            (struct _USER_COUNT_ENTRY **)v4 + 3,
            (unsigned int *)v4 + 8,
            (unsigned int *)v4 + 9);
    if ( v13 )
    {
      LODWORD(v47) = 783;
      DbgPrintfW(
        1u,
        L"(0x%08x) %ws:%u : %ws:%ws\n",
        v13,
        L"onecore\\ds\\security\\eas\\policyengine\\extnlib\\fvewrappers.cpp",
        v47,
        L"UnpackEASLockoutData",
        &Class);
      goto LABEL_67;
    }
    v32 = *((_DWORD *)v4 + 8);
    v33 = 1;
    v34 = *((_QWORD *)v4 + 3);
    v50 = v32;
    if ( v32 > 1 )
    {
      v35 = v32;
      do
      {
        v36 = v33 - 1;
        v37 = *(WCHAR **)(v34 + 16LL * v33 + 8);
        v38 = *(_QWORD *)(v34 + 16LL * v33);
        lpBuffer = v37;
        if ( (int)(v33 - 1) >= 0 )
        {
          v39 = v37;
          do
          {
            if ( (int)CompareSIDs(*(void **)(v34 + 16LL * (unsigned int)v36 + 8), v39) <= 0 )
              break;
            v40 = *(_OWORD *)(v34 + 16LL * (unsigned int)v36);
            v41 = 2 * ((unsigned int)v36-- + 1LL);
            *(_OWORD *)(v34 + 8 * v41) = v40;
          }
          while ( v36 >= 0 );
          v35 = v50;
          v37 = lpBuffer;
        }
        ++v33;
        v42 = 2 * (v36 + 1LL);
        *(_QWORD *)(v34 + 8 * v42) = v38;
        *(_QWORD *)(v34 + 8 * v42 + 8) = v37;
      }
      while ( (int)v33 < v35 );
      v4 = v53;
    }
    goto LABEL_61;
  }
  if ( v31 < 0 )
  {
    v13 = (unsigned __int16)v31;
    if ( (v31 & 0x1FFF0000) != 0x70000 )
      v13 = v31;
  }
  else
  {
    v13 = 0;
  }
  v27 = L"EasGetDeviceLockoutData";
  v50 = 772;
  v20 = L"EasGetDeviceLockoutData";
  v21 = 771;
LABEL_66:
  LODWORD(v44) = v21;
  DbgPrintfW(
    1u,
    L"(0x%08x) %ws:%u : %ws:%ws\n",
    v8,
    L"onecore\\ds\\security\\eas\\policyengine\\extnlib\\fvewrappers.cpp",
    v44,
    v27,
    &Class);
  LODWORD(v48) = v50;
  DbgPrintfW(
    1u,
    L"(0x%08x) %ws:%u : %ws:%ws\n",
    v13,
    L"onecore\\ds\\security\\eas\\policyengine\\extnlib\\fvewrappers.cpp",
    v48,
    v20,
    &Class);
  if ( v13 )
    goto LABEL_67;
LABEL_68:
  *(_DWORD *)v4 = 1;
  return v13;
}

```

## disassembly

```asm
0x18006c3f0  mov     [rsp-8+arg_8], rbx
0x18006c3f5  push    rbp
0x18006c3f6  push    rsi
0x18006c3f7  push    rdi
0x18006c3f8  push    r12
0x18006c3fa  push    r13
0x18006c3fc  push    r14
0x18006c3fe  push    r15
0x18006c400  lea     rbp, [rsp-180h]
0x18006c408  sub     rsp, 280h
0x18006c40f  mov     rax, cs:__security_cookie
0x18006c416  xor     rax, rsp
0x18006c419  mov     [rbp+1B0h+var_40], rax
0x18006c420  mov     rsi, r8
0x18006c423  mov     [rsp+2B0h+var_258], rcx
0x18006c428  mov     r14, rcx
0x18006c42b  mov     r8d, 208h; Size
0x18006c431  lea     rcx, [rsp+2B0h+var_250]; void *
0x18006c436  xor     edx, edx; Val
0x18006c438  call    memset_0
0x18006c43d  mov     [rsp+2B0h+var_270], 0
0x18006c445  test    rsi, rsi
0x18006c448  jz      short loc_18006C450
0x18006c44a  mov     dword ptr [rsi], 0
0x18006c450  lea     rax, [rsp+2B0h+uSize]
0x18006c455  mov     qword ptr [rsp+2B0h+uSize], 0
0x18006c45e  lea     r9, [rsp+2B0h+lpBuffer]; unsigned __int16 **
0x18006c463  mov     [rsp+2B0h+var_290], rax; unsigned __int64 *
0x18006c468  lea     rcx, [rsp+2B0h+var_250]; unsigned __int16 *
0x18006c46d  mov     [rsp+2B0h+lpBuffer], 0
0x18006c476  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x18006c47b  mov     r8d, eax
0x18006c47e  test    eax, eax
0x18006c480  js      short loc_18006C4E5
0x18006c482  mov     rbx, qword ptr [rsp+2B0h+uSize]
0x18006c487  mov     eax, 0FFFFFFFFh
0x18006c48c  cmp     rbx, rax
0x18006c48f  ja      loc_18006C855
0x18006c495  mov     rdi, [rsp+2B0h+lpBuffer]
0x18006c49a  mov     edx, ebx; uSize
0x18006c49c  mov     rcx, rdi; lpBuffer
0x18006c49f  call    cs:__imp_GetSystemWindowsDirectoryW
0x18006c4a5  mov     ecx, eax
0x18006c4a7  test    eax, eax
0x18006c4a9  jnz     short loc_18006C4C5
0x18006c4ab  call    cs:__imp_GetLastError
0x18006c4b1  mov     r8d, eax
0x18006c4b4  test    eax, eax
0x18006c4b6  jle     short loc_18006C4D7
0x18006c4b8  movzx   r8d, ax
0x18006c4bc  or      r8d, 80070000h
0x18006c4c3  jmp     short loc_18006C4D7
0x18006c4c5  xor     eax, eax
0x18006c4c7  cmp     ebx, ecx
0x18006c4c9  mov     [rdi+4], ax
0x18006c4cd  sbb     r8d, r8d
0x18006c4d0  and     r8d, 80070057h
0x18006c4d7  test    r8d, r8d
0x18006c4da  jz      short loc_18006C500
0x18006c4dc  js      short loc_18006C4E5
0x18006c4de  xor     ebx, ebx
0x18006c4e0  jmp     loc_18006C85F
0x18006c4e5  mov     eax, r8d
0x18006c4e8  and     eax, 1FFF0000h
0x18006c4ed  cmp     eax, 70000h
0x18006c4f2  jz      loc_18006C85B
0x18006c4f8  mov     ebx, r8d
0x18006c4fb  jmp     loc_18006C85F
0x18006c500  lea     rcx, [rsp+2B0h+var_270]; int *
0x18006c505  call    ?CheckThirdPartyStatus@@YAKPEAH@Z; CheckThirdPartyStatus(int *)
0x18006c50a  mov     ebx, eax
0x18006c50c  test    eax, eax
0x18006c50e  jz      short loc_18006C564
0x18006c510  lea     rsi, Class
0x18006c517  mov     edi, 1
0x18006c51c  mov     [rsp+2B0h+var_280], rsi
0x18006c521  lea     r15, aCheckthirdpart; "CheckThirdPartyStatus"
0x18006c528  mov     [rsp+2B0h+var_288], r15
0x18006c52d  lea     r9, aOnecoreDsSecur_1; "onecore\\ds\\security\\eas\\policyengin"...
0x18006c534  mov     r8d, eax
0x18006c537  mov     dword ptr [rsp+2B0h+var_290], 2CBh
0x18006c53f  lea     rdx, a0x08xWsUWsWs; "(0x%08x) %ws:%u : %ws:%ws\n"
0x18006c546  mov     ecx, edi; unsigned int
0x18006c548  call    ?DbgPrintfW@@YAXKPEBGZZ; DbgPrintfW(ulong,ushort const *,...)
0x18006c54d  mov     [rsp+2B0h+var_280], rsi
0x18006c552  mov     [rsp+2B0h+var_288], r15
0x18006c557  mov     dword ptr [rsp+2B0h+var_290], 2CCh
0x18006c55f  jmp     loc_18006C709
0x18006c564  mov     ebx, [rsp+2B0h+var_270]
0x18006c568  xor     eax, eax
0x18006c56a  test    ebx, ebx
0x18006c56c  setz    al
0x18006c56f  mov     [r14+6Ch], eax
0x18006c573  test    eax, eax
0x18006c575  jnz     short loc_18006C57C
0x18006c577  call    ?SQMBitLockerIfNeeded@@YAXXZ; SQMBitLockerIfNeeded(void)
0x18006c57c  xor     edx, edx
0x18006c57e  test    ebx, ebx
0x18006c580  lea     rbx, [r14+80h]
0x18006c587  mov     rcx, rbx
0x18006c58a  setz    dl
0x18006c58d  call    ?CreateEncryptHandle@EncryptHandle@@SAJPEAPEAV1@W4EncryptHandlerType@@@Z; EncryptHandle::CreateEncryptHandle(EncryptHandle * *,EncryptHandlerType)
0x18006c592  mov     r8d, eax
0x18006c595  mov     edi, 1
0x18006c59a  test    eax, eax
0x18006c59c  jz      short loc_18006C5DE
0x18006c59e  test    eax, eax
0x18006c5a0  js      short loc_18006C5A6
0x18006c5a2  xor     ebx, ebx
0x18006c5a4  jmp     short loc_18006C5C5
0x18006c5a6  and     eax, 1FFF0000h
0x18006c5ab  movzx   ebx, r8w
0x18006c5af  cmp     eax, 70000h
0x18006c5b4  jz      short loc_18006C5B9
0x18006c5b6  mov     ebx, r8d
0x18006c5b9  cmp     ebx, 7Eh ; '~'
0x18006c5bc  jnz     short loc_18006C5C5
0x18006c5be  test    rsi, rsi
0x18006c5c1  jz      short loc_18006C5C5
0x18006c5c3  mov     [rsi], edi
0x18006c5c5  mov     [rsp+2B0h+var_270], 2DDh
0x18006c5cd  lea     r15, aEncrypthandleC; "EncryptHandle::CreateEncryptHandle"
0x18006c5d4  mov     edx, 2DCh
0x18006c5d9  jmp     loc_18006C878
0x18006c5de  mov     rcx, [rbx]
0x18006c5e1  lea     r15, [r14+78h]
0x18006c5e5  mov     r9, r15
0x18006c5e8  lea     rdx, [rsp+2B0h+var_250]
0x18006c5ed  mov     r8d, edi
0x18006c5f0  mov     rax, [rcx]
0x18006c5f3  mov     rax, [rax+8]
0x18006c5f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c5fc  mov     r8d, eax
0x18006c5ff  test    eax, eax
0x18006c601  jz      short loc_18006C637
0x18006c603  test    eax, eax
0x18006c605  js      short loc_18006C60B
0x18006c607  xor     ebx, ebx
0x18006c609  jmp     short loc_18006C61E
0x18006c60b  and     eax, 1FFF0000h
0x18006c610  movzx   ebx, r8w
0x18006c614  cmp     eax, 70000h
0x18006c619  jz      short loc_18006C61E
0x18006c61b  mov     ebx, r8d
0x18006c61e  mov     [rsp+2B0h+var_270], 2E5h
0x18006c626  lea     r15, aOpenvolume; "OpenVolume"
0x18006c62d  mov     edx, 2E4h
0x18006c632  jmp     loc_18006C878
0x18006c637  mov     rcx, [rbx]
0x18006c63a  mov     rdx, [r15]
0x18006c63d  mov     rax, [rcx]
0x18006c640  mov     rax, [rax+10h]
0x18006c644  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c649  xor     ecx, ecx
0x18006c64b  test    eax, eax
0x18006c64d  setz    cl
0x18006c650  mov     [r14+4], ecx
0x18006c654  test    eax, eax
0x18006c656  jnz     loc_18006C84E
0x18006c65c  mov     rcx, [rbx]
0x18006c65f  lea     rsi, [r14+10h]
0x18006c663  mov     r8, [r14+8]
0x18006c667  mov     r9, rsi
0x18006c66a  mov     rdx, [r15]
0x18006c66d  mov     rax, [rcx]
0x18006c670  mov     rax, [rax+28h]
0x18006c674  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c679  mov     r8d, eax
0x18006c67c  test    eax, eax
0x18006c67e  jz      short loc_18006C6B7
0x18006c680  test    eax, eax
0x18006c682  js      short loc_18006C688
0x18006c684  xor     ebx, ebx
0x18006c686  jmp     short loc_18006C69B
0x18006c688  and     eax, 1FFF0000h
0x18006c68d  movzx   ebx, r8w
0x18006c691  cmp     eax, 70000h
0x18006c696  jz      short loc_18006C69B
0x18006c698  mov     ebx, r8d
0x18006c69b  lea     rax, aEasgetdevicelo; "EasGetDeviceLockoutData"
0x18006c6a2  mov     [rsp+2B0h+var_270], 2F3h
0x18006c6aa  mov     r15, rax
0x18006c6ad  mov     edx, 2F2h
0x18006c6b2  jmp     loc_18006C87B
0x18006c6b7  mov     r12d, [rsi]
0x18006c6ba  test    r12d, r12d
0x18006c6bd  jz      loc_18006C779
0x18006c6c3  call    cs:__imp_GetProcessHeap
0x18006c6c9  mov     r8d, r12d; dwBytes
0x18006c6cc  mov     edx, 8; dwFlags
0x18006c6d1  mov     rcx, rax; hHeap
0x18006c6d4  call    cs:__imp_HeapAlloc
0x18006c6da  mov     [r14+8], rax
0x18006c6de  mov     r8, rax
0x18006c6e1  test    rax, rax
0x18006c6e4  jnz     short loc_18006C726
0x18006c6e6  lea     ebx, [rax+0Eh]
0x18006c6e9  lea     rsi, Class
0x18006c6f0  mov     [rsp+2B0h+var_280], rsi
0x18006c6f5  lea     rax, aHeapalloc; "HeapAlloc"
0x18006c6fc  mov     [rsp+2B0h+var_288], rax
0x18006c701  mov     dword ptr [rsp+2B0h+var_290], 2FCh
0x18006c709  lea     r9, aOnecoreDsSecur_1; "onecore\\ds\\security\\eas\\policyengin"...
0x18006c710  mov     r8d, ebx
0x18006c713  lea     rdx, a0x08xWsUWsWs; "(0x%08x) %ws:%u : %ws:%ws\n"
0x18006c71a  mov     ecx, edi; unsigned int
0x18006c71c  call    ?DbgPrintfW@@YAXKPEBGZZ; DbgPrintfW(ulong,ushort const *,...)
0x18006c721  jmp     loc_18006C8DC
0x18006c726  mov     rcx, [rbx]
0x18006c729  mov     r9, rsi
0x18006c72c  mov     rdx, [r15]
0x18006c72f  mov     rax, [rcx]
0x18006c732  mov     rax, [rax+28h]
0x18006c736  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c73b  mov     r8d, eax
0x18006c73e  test    eax, eax
0x18006c740  jz      short loc_18006C779
0x18006c742  test    eax, eax
0x18006c744  js      short loc_18006C74A
0x18006c746  xor     ebx, ebx
0x18006c748  jmp     short loc_18006C75D
0x18006c74a  and     eax, 1FFF0000h
0x18006c74f  movzx   ebx, r8w
0x18006c753  cmp     eax, 70000h
0x18006c758  jz      short loc_18006C75D
0x18006c75a  mov     ebx, r8d
0x18006c75d  lea     rax, aEasgetdevicelo; "EasGetDeviceLockoutData"
0x18006c764  mov     [rsp+2B0h+var_270], 304h
0x18006c76c  mov     r15, rax
0x18006c76f  mov     edx, 303h
0x18006c774  jmp     loc_18006C87B
0x18006c779  mov     edx, [rsi]; unsigned int
0x18006c77b  lea     rax, [r14+24h]
0x18006c77f  mov     rcx, [r14+8]; unsigned __int8 *
0x18006c783  lea     r9, [r14+20h]; unsigned int *
0x18006c787  lea     r8, [r14+18h]; struct _USER_COUNT_ENTRY **
0x18006c78b  mov     [rsp+2B0h+var_290], rax; unsigned int *
0x18006c790  call    ?UnpackEASLockoutData@@YAKPEAEKPEAPEAU_USER_COUNT_ENTRY@@PEAK2@Z; UnpackEASLockoutData(uchar *,ulong,_USER_COUNT_ENTRY * *,ulong *,ulong *)
0x18006c795  mov     ebx, eax
0x18006c797  test    eax, eax
0x18006c799  jz      short loc_18006C7C0
0x18006c79b  lea     rsi, Class
0x18006c7a2  mov     [rsp+2B0h+var_280], rsi
0x18006c7a7  lea     rax, aUnpackeaslocko; "UnpackEASLockoutData"
0x18006c7ae  mov     [rsp+2B0h+var_288], rax
0x18006c7b3  mov     dword ptr [rsp+2B0h+var_290], 30Fh
0x18006c7bb  jmp     loc_18006C709
0x18006c7c0  mov     eax, [r14+20h]
0x18006c7c4  mov     r15d, edi
0x18006c7c7  mov     rsi, [r14+18h]
0x18006c7cb  mov     [rsp+2B0h+var_270], eax
0x18006c7cf  cmp     eax, edi
0x18006c7d1  jle     short loc_18006C84E
0x18006c7d3  mov     r14d, eax
0x18006c7d6  mov     eax, r15d
0x18006c7d9  lea     r12d, [r15-1]
0x18006c7dd  add     rax, rax
0x18006c7e0  mov     rcx, [rsi+rax*8+8]
0x18006c7e5  mov     rbx, [rsi+rax*8]
0x18006c7e9  mov     [rsp+2B0h+lpBuffer], rcx
0x18006c7ee  test    r12d, r12d
0x18006c7f1  js      short loc_18006C82F
0x18006c7f3  mov     r14, rcx
0x18006c7f6  mov     r13d, r12d
0x18006c7f9  mov     rdx, r14; Buf2
0x18006c7fc  add     r13, r13
0x18006c7ff  mov     rcx, [rsi+r13*8+8]; Buf1
0x18006c804  call    ?CompareSIDs@@YAHPEAX0@Z; CompareSIDs(void *,void *)
0x18006c809  test    eax, eax
0x18006c80b  jle     short loc_18006C825
0x18006c80d  movups  xmm0, xmmword ptr [rsi+r13*8]
0x18006c812  mov     eax, r12d
0x18006c815  inc     rax
0x18006c818  add     rax, rax
0x18006c81b  sub     r12d, edi
0x18006c81e  movdqu  xmmword ptr [rsi+rax*8], xmm0
0x18006c823  jns     short loc_18006C7F6
0x18006c825  mov     r14d, [rsp+2B0h+var_270]
0x18006c82a  mov     rcx, [rsp+2B0h+lpBuffer]
0x18006c82f  movsxd  rax, r12d
0x18006c832  add     r15d, edi
0x18006c835  add     rax, rdi
0x18006c838  add     rax, rax
0x18006c83b  mov     [rsi+rax*8], rbx
0x18006c83f  mov     [rsi+rax*8+8], rcx
0x18006c844  cmp     r15d, r14d
0x18006c847  jl      short loc_18006C7D6
0x18006c849  mov     r14, [rsp+2B0h+var_258]
0x18006c84e  xor     ebx, ebx
0x18006c850  jmp     loc_18006C915
0x18006c855  mov     r8d, 80070216h
0x18006c85b  movzx   ebx, r8w
0x18006c85f  mov     edi, 1
0x18006c864  mov     [rsp+2B0h+var_270], 2C4h
0x18006c86c  lea     r15, aEasgetosvolume; "EasGetOSVolume"
0x18006c873  mov     edx, 2C3h
0x18006c878  mov     rax, r15
0x18006c87b  lea     rsi, Class
0x18006c882  mov     r12d, edi
0x18006c885  mov     r9, rsi
  ... truncated ...
```
