# ResExtract

- ea: `0x180022010`
- end: `0x1800226dd`
- name: `ResExtract`
- size: `1741`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, __int64, __int64, __int64, int)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180021db0`

## callees

- `0x18000da6c`
- `0x18000ec88`
- `0x18000fd58`
- `0x1800100c8`
- `0x180010658`
- `0x180011bb8`
- `0x180012934`
- `0x180013308`
- `0x180017344`
- `0x18001879c`
- `0x18001bd1c`
- `0x18001f74c`
- `0x180021260`
- `0x1800219c4`
- `0x180022010`
- `0x18003d564`
- `0x1800607b0`
- `0x180060e5a`
- `0x180060e70`

## import_xrefs

- `KERNEL32!Sleep` at `0x18002255c`
- `KERNEL32!Sleep` at `0x18002255c`
- `KERNEL32!HeapFree` at `0x1800222c6`
- `KERNEL32!HeapFree` at `0x1800222c6`
- `KERNEL32!GetLastError` at `0x18002218b`
- `KERNEL32!GetLastError` at `0x1800221aa`
- `KERNEL32!GetLastError` at `0x1800222d2`
- `KERNEL32!GetLastError` at `0x1800222f1`
- `KERNEL32!GetLastError` at `0x1800223ba`
- `KERNEL32!GetLastError` at `0x1800223d9`
- `KERNEL32!GetLastError` at `0x180022577`
- `KERNEL32!GetLastError` at `0x180022598`
- `KERNEL32!GetLastError` at `0x18002218b`
- `KERNEL32!GetLastError` at `0x1800221aa`
- `KERNEL32!GetLastError` at `0x1800222d2`
- `KERNEL32!GetLastError` at `0x1800222f1`
- `KERNEL32!GetLastError` at `0x1800223ba`
- `KERNEL32!GetLastError` at `0x1800223d9`
- `KERNEL32!GetLastError` at `0x180022577`
- `KERNEL32!GetLastError` at `0x180022598`
- `KERNEL32!GetProcessHeap` at `0x1800222b2`
- `KERNEL32!GetProcessHeap` at `0x1800222b2`
- `ntdll!RtlNtStatusToDosError` at `0x18002245f`
- `ntdll!RtlNtStatusToDosError` at `0x180022478`
- `ntdll!RtlNtStatusToDosError` at `0x1800224f5`
- `ntdll!RtlNtStatusToDosError` at `0x18002250e`
- `ntdll!RtlNtStatusToDosError` at `0x18002245f`
- `ntdll!RtlNtStatusToDosError` at `0x180022478`
- `ntdll!RtlNtStatusToDosError` at `0x1800224f5`
- `ntdll!RtlNtStatusToDosError` at `0x18002250e`

## string_xrefs

- `0x180022125`: `DecompressChunkedFile failed`
- `0x1800221ec`: `UncompressFile failed`
- `0x18002224d`: `failed to extract file from reference extension`
- `0x18002241b`: `WIMCopyFileEx failed`

## pseudocode

```c
__int64 __fastcall ResExtract(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 *a7,
        int a8)
{
  __int64 v8; // rsi
  __int64 *v10; // r15
  __int64 v13; // rax
  __int64 v14; // rcx
  wchar_t *Status; // rbx
  __int64 v16; // rdx
  signed int LastError; // ecx
  signed int v18; // eax
  signed int v19; // eax
  int v20; // eax
  HANDLE ProcessHeap; // rax
  __int64 v22; // rdx
  signed int v23; // ecx
  signed int v24; // eax
  signed int v25; // eax
  union _LARGE_INTEGER v26; // rdx
  __int64 v27; // r8
  __int64 v28; // r9
  __int64 QuadPart; // rax
  __int64 v30; // rdx
  signed int v31; // ecx
  signed int v32; // eax
  signed int v33; // eax
  __int64 v34; // rdx
  int v35; // r15d
  void *WimFileHandle; // rax
  __int64 v37; // rax
  ULONG v38; // edx
  int WimFile; // eax
  int v40; // esi
  __int64 v42; // rdx
  signed int v43; // ecx
  signed int v44; // eax
  signed int v45; // eax
  __int64 v46; // rcx
  bool v47; // zf
  __int64 v48; // rax
  __int64 v49; // r9
  __int64 v50; // r10
  __int64 v52; // [rsp+30h] [rbp-D0h]
  __int64 v53; // [rsp+38h] [rbp-C8h]
  int v54; // [rsp+40h] [rbp-C0h]
  int v55; // [rsp+48h] [rbp-B8h]
  __int64 FileSize; // [rsp+50h] [rbp-B0h]
  unsigned int v57; // [rsp+70h] [rbp-90h]
  DWORD dwMilliseconds; // [rsp+74h] [rbp-8Ch] BYREF
  __int64 v59; // [rsp+78h] [rbp-88h] BYREF
  STRSAFE_LPCWSTR pszSrc; // [rsp+80h] [rbp-80h] BYREF
  __int64 v61; // [rsp+88h] [rbp-78h]
  __int64 v62; // [rsp+90h] [rbp-70h]
  __int64 v63; // [rsp+98h] [rbp-68h]
  __int64 v64; // [rsp+A0h] [rbp-60h]
  __int64 v65; // [rsp+A8h] [rbp-58h]
  wchar_t pszDest[256]; // [rsp+B0h] [rbp-50h] BYREF

  v8 = a5;
  v10 = a7;
  v63 = a5;
  v64 = (__int64)a7;
  v65 = a4;
  dwMilliseconds = 1000;
  v57 = 1;
  if ( a3 )
    v13 = *(_BYTE *)(a3 + 15) & 4;
  else
    v13 = 0;
  v61 = v13;
  if ( a3 )
    v14 = *(_BYTE *)(a3 + 15) & 0x10;
  else
    v14 = 0;
  v59 = 0;
  v62 = v14;
  if ( !a1 || !a2 && !a4 || !a6 )
    return 2147942487LL;
  do
  {
    Status = 0;
    if ( v14 )
    {
      LODWORD(Status) = DecompressChunkedFile(a1, v10[1], *v10, a8, v53, (__int64)&v59);
      if ( (int)Status >= 0 )
        goto LABEL_98;
      WIMLogMsg(2, a1, a6, (int)L"DecompressChunkedFile failed", (NTSTATUS)Status, (__int64)L"ResExtract", 486);
    }
    else if ( v13 )
    {
      if ( (unsigned int)UncompressFile(a1, *(_QWORD *)(a3 + 24), a6, v10[1], *v10, a8, v55, FileSize, (__int64)&v59) )
        goto LABEL_98;
      LastError = GetLastError();
      v18 = (unsigned __int16)LastError | 0x80070000;
      if ( LastError <= 0 )
        v18 = LastError;
      if ( v18 >= 0 )
      {
        LODWORD(Status) = -2147467259;
      }
      else
      {
        v19 = GetLastError();
        LODWORD(Status) = (unsigned __int16)v19 | 0x80070000;
        if ( v19 <= 0 )
          LODWORD(Status) = v19;
      }
      if ( (int)Status < 0 )
        UtilReportError((__int64)L"ResExtract", v16, 0x201u, (int)Status);
      WIMLogMsg(2, a1, a6, (int)L"UncompressFile failed", (NTSTATUS)Status, (__int64)L"ResExtract", 515);
    }
    else if ( v8 )
    {
      if ( (unsigned int)ExtractOneFileFromRefExtBasedOnHash(a1, a4, v8, a4, v10[1], *v10, a8, v53, v54, (__int64)&v59) )
        goto LABEL_98;
      memset_0(pszDest, 0, sizeof(pszDest));
      pszSrc = 0;
      StringCchCopyW(pszDest, 0x100u, L"failed to extract file from reference extension");
      if ( v8 == -16 )
      {
        v20 = -2147024809;
      }
      else
      {
        v20 = WimBufferToHexString(v8 + 16, &pszSrc);
        Status = (wchar_t *)pszSrc;
      }
      if ( v20 >= 0 )
      {
        StringCchCatW(pszDest, 0x100u, L"; hash = ");
        StringCchCatW(pszDest, 0x100u, Status);
        if ( Status )
        {
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, Status);
        }
      }
      v23 = GetLastError();
      v24 = (unsigned __int16)v23 | 0x80070000;
      if ( v23 <= 0 )
        v24 = v23;
      if ( v24 >= 0 )
      {
        LODWORD(Status) = -2147467259;
      }
      else
      {
        v25 = GetLastError();
        LODWORD(Status) = (unsigned __int16)v25 | 0x80070000;
        if ( v25 <= 0 )
          LODWORD(Status) = v25;
      }
      if ( (int)Status < 0 )
        UtilReportError((__int64)L"ResExtract", v22, 0x226u, (int)Status);
      WIMLogMsg(2, a1, a6, (int)pszDest, (NTSTATUS)Status, (__int64)L"ResExtract", 552);
    }
    else
    {
      pszSrc = (STRSAFE_LPCWSTR)GetWimFileHandle(a2);
      if ( a3 )
      {
        QuadPart = *(_QWORD *)(a3 + 16);
        v26.QuadPart = v27 & *(_QWORD *)(a3 + 8);
      }
      else
      {
        QuadPart = g_liZero.QuadPart;
      }
      if ( (unsigned int)WIMCopyFileEx(
                           a1,
                           (__int64 *)&pszSrc,
                           v10[1],
                           v28,
                           v10,
                           a6,
                           v52,
                           1243611136,
                           QuadPart,
                           g_liZero.QuadPart,
                           v26,
                           v10[1],
                           a8,
                           &v59) )
        goto LABEL_98;
      v31 = GetLastError();
      v32 = (unsigned __int16)v31 | 0x80070000;
      if ( v31 <= 0 )
        v32 = v31;
      if ( v32 >= 0 )
      {
        LODWORD(Status) = -2147467259;
      }
      else
      {
        v33 = GetLastError();
        LODWORD(Status) = (unsigned __int16)v33 | 0x80070000;
        if ( v33 <= 0 )
          LODWORD(Status) = v33;
      }
      if ( (int)Status < 0 )
        UtilReportError((__int64)L"ResExtract", v30, 0x25Fu, (int)Status);
      WIMLogMsg(2, a1, a6, (int)L"WIMCopyFileEx failed", (NTSTATUS)Status, (__int64)L"ResExtract", 608);
    }
    if ( (int)Status >= 0 )
      goto LABEL_98;
    if ( !a2 )
      break;
    if ( ((unsigned int)Status & 0x10000000) != 0 )
    {
      if ( RtlNtStatusToDosError((NTSTATUS)Status) == 317 )
        v34 = (unsigned int)Status;
      else
        v34 = RtlNtStatusToDosError((NTSTATUS)Status);
    }
    else
    {
      v34 = (unsigned int)Status;
      if ( ((unsigned int)Status & 0x1FFF0000) == 0x70000 )
        v34 = (unsigned __int16)Status;
    }
    if ( !(unsigned int)WdsShouldRetryFailedCopy(v57, v34, &dwMilliseconds) )
    {
      v8 = v63;
      break;
    }
    v35 = 1;
    WimFileHandle = (void *)GetWimFileHandle(a2);
    WIMFileCloseHandle(WimFileHandle);
    if ( *(_DWORD *)a2 == -17960959 )
    {
      v37 = a2;
    }
    else
    {
      if ( *(_DWORD *)a2 != -17960958 )
        goto LABEL_73;
      v37 = *(_QWORD *)(a2 + 8);
    }
    if ( v37 )
      *(_QWORD *)(v37 + 8) = -1;
LABEL_73:
    if ( ((unsigned int)Status & 0x10000000) != 0 )
    {
      if ( RtlNtStatusToDosError((NTSTATUS)Status) == 317 )
        v38 = (unsigned int)Status;
      else
        v38 = RtlNtStatusToDosError((NTSTATUS)Status);
    }
    else
    {
      v38 = (unsigned int)Status;
      if ( ((unsigned int)Status & 0x1FFF0000) == 0x70000 )
        v38 = (unsigned __int16)Status;
    }
    WIMSendMessage(a1, 38017, a6, v38);
    WimFile = 0;
    v40 = 5;
    while ( !WimFile )
    {
      if ( !v40-- )
      {
        v35 = 0;
        v43 = GetLastError();
        v44 = (unsigned __int16)v43 | 0x80070000;
        if ( v43 <= 0 )
          v44 = v43;
        if ( v44 >= 0 )
        {
          LODWORD(Status) = -2147467259;
        }
        else
        {
          v45 = GetLastError();
          LODWORD(Status) = (unsigned __int16)v45 | 0x80070000;
          if ( v45 <= 0 )
            LODWORD(Status) = v45;
        }
        if ( (int)Status < 0 )
          UtilReportError((__int64)L"ResExtract", v42, 0x289u, (int)Status);
        break;
      }
      Sleep(dwMilliseconds);
      WimFile = CreateWimFile(a2, 0);
    }
    SynchronizeCallback(a1, 0, 38008);
    v46 = *(_QWORD *)(a1 + 64);
    if ( !v46 )
      v46 = a1;
    *(_QWORD *)(v46 + 128) += v59;
    SynchronizeCallback(a1, 1, 38008);
    ++v57;
    v8 = v63;
    v47 = v35 == 0;
    v10 = (__int64 *)v64;
    v13 = v61;
    v14 = v62;
    LODWORD(a4) = v65;
  }
  while ( !v47 );
  if ( (int)Status < 0 )
    return (unsigned int)Status;
LABEL_98:
  if ( (a3 || v8) && v10[2] )
  {
    v48 = a1;
    if ( *(_QWORD *)(a1 + 64) )
      v48 = *(_QWORD *)(a1 + 64);
    if ( (*(_BYTE *)(v48 + 36) & 2) != 0 )
    {
      if ( a3 )
      {
        if ( (*(_BYTE *)(a3 + 15) & 0x10) != 0 )
          v49 = *(_QWORD *)(a3 + 8) & 0xFFFFFFFFFFFFFFLL;
        else
          v49 = *(_QWORD *)(a3 + 24);
      }
      else
      {
        v49 = *(_QWORD *)(v8 + 8);
      }
      v50 = v8 + 16;
      if ( a3 )
        v50 = a3 + 40;
      LODWORD(Status) = ((__int64 (__fastcall *)(__int64, __int64, __int64, __int64, __int64))v10[2])(
                          a1,
                          *v10,
                          a6,
                          v49,
                          v50);
    }
  }
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x180022010  push    rbp
0x180022012  push    rbx
0x180022013  push    rsi
0x180022014  push    rdi
0x180022015  push    r12
0x180022017  push    r13
0x180022019  push    r14
0x18002201b  push    r15
0x18002201d  lea     rbp, [rsp-1C8h]
0x180022025  sub     rsp, 2C8h
0x18002202c  mov     rax, cs:__security_cookie
0x180022033  xor     rax, rsp
0x180022036  mov     [rbp+200h+var_50], rax
0x18002203d  mov     rsi, [rbp+200h+arg_20]
0x180022044  mov     rdi, r8
0x180022047  mov     r15, [rbp+200h+arg_30]
0x18002204e  mov     r13, rdx
0x180022051  mov     r12, [rbp+200h+arg_28]
0x180022058  mov     r14, rcx
0x18002205b  mov     [rbp+200h+var_268], rsi
0x18002205f  mov     [rbp+200h+var_260], r15
0x180022063  mov     [rbp+200h+var_258], r9
0x180022067  mov     [rsp+300h+dwMilliseconds], 3E8h
0x18002206f  mov     [rsp+300h+var_290], 1
0x180022077  test    r8, r8
0x18002207a  jz      short loc_180022086
0x18002207c  movzx   eax, byte ptr [r8+0Fh]
0x180022081  and     eax, 4
0x180022084  jmp     short loc_180022088
0x180022086  xor     eax, eax
0x180022088  mov     [rbp+200h+var_278], rax
0x18002208c  test    rdi, rdi
0x18002208f  jz      short loc_18002209B
0x180022091  movzx   ecx, byte ptr [r8+0Fh]
0x180022096  and     ecx, 10h
0x180022099  jmp     short loc_18002209D
0x18002209b  xor     ecx, ecx
0x18002209d  and     [rsp+300h+var_288], 0
0x1800220a3  mov     [rbp+200h+var_270], rcx
0x1800220a7  test    r14, r14
0x1800220aa  jz      loc_1800226B5
0x1800220b0  test    r13, r13
0x1800220b3  jnz     short loc_1800220BE
0x1800220b5  test    r9, r9
0x1800220b8  jz      loc_1800226B5
0x1800220be  test    r12, r12
0x1800220c1  jz      loc_1800226B5
0x1800220c7  mov     r8, 0FFFFFFFFFFFFFFh
0x1800220d1  xor     ebx, ebx
0x1800220d3  test    rcx, rcx
0x1800220d6  jz      short loc_180022131
0x1800220d8  mov     r9, [rdi+8]
0x1800220dc  lea     rax, [rsp+300h+var_288]
0x1800220e1  mov     [rsp+300h+var_2C0], rax; __int64
0x1800220e6  and     r9, r8
0x1800220e9  mov     eax, [rbp+200h+arg_38]
0x1800220ef  mov     rdx, r13
0x1800220f2  mov     r8, [rdi+10h]
0x1800220f6  mov     rcx, r14; int
0x1800220f9  mov     dword ptr [rsp+300h+var_2D0], eax; int
0x1800220fd  mov     rax, [r15]
0x180022100  mov     [rsp+300h+var_2D8], rax; __int64
0x180022105  mov     rax, [r15+8]
0x180022109  mov     qword ptr [rsp+300h+Status], rax; __int64
0x18002210e  call    DecompressChunkedFile
0x180022113  mov     ebx, eax
0x180022115  test    eax, eax
0x180022117  jns     loc_18002263C
0x18002211d  mov     dword ptr [rsp+300h+var_2D0], 1E6h
0x180022125  lea     r9, aDecompresschun_0; "DecompressChunkedFile failed"
0x18002212c  jmp     loc_180022422
0x180022131  test    rax, rax
0x180022134  jz      loc_1800221F8
0x18002213a  mov     r9, [rdi+8]
0x18002213e  lea     rax, [rsp+300h+var_288]
0x180022143  mov     [rsp+300h+var_2A8], rax; __int64
0x180022148  and     r9, r8
0x18002214b  mov     eax, [rbp+200h+arg_38]
0x180022151  mov     rdx, r13
0x180022154  mov     r8, [rdi+10h]
0x180022158  mov     rcx, r14; int
0x18002215b  mov     dword ptr [rsp+300h+var_2C0], eax; int
0x18002215f  mov     rax, [r15]
0x180022162  mov     [rsp+300h+var_2C8], rax; __int64
0x180022167  mov     rax, [r15+8]
0x18002216b  mov     [rsp+300h+var_2D0], rax; __int64
0x180022170  mov     rax, [rdi+18h]
0x180022174  mov     [rsp+300h+var_2D8], r12; int
0x180022179  mov     qword ptr [rsp+300h+Status], rax; __int64
0x18002217e  call    UncompressFile
0x180022183  test    eax, eax
0x180022185  jnz     loc_18002263C
0x18002218b  call    cs:__imp_GetLastError
0x180022192  nop     dword ptr [rax+rax+00h]
0x180022197  mov     ecx, eax
0x180022199  movzx   eax, ax
0x18002219c  or      eax, 80070000h
0x1800221a1  test    ecx, ecx
0x1800221a3  cmovle  eax, ecx
0x1800221a6  test    eax, eax
0x1800221a8  jns     short loc_1800221C6
0x1800221aa  call    cs:__imp_GetLastError
0x1800221b1  nop     dword ptr [rax+rax+00h]
0x1800221b6  movzx   ebx, ax
0x1800221b9  or      ebx, 80070000h
0x1800221bf  test    eax, eax
0x1800221c1  cmovle  ebx, eax
0x1800221c4  jmp     short loc_1800221CB
0x1800221c6  mov     ebx, 80004005h
0x1800221cb  test    ebx, ebx
0x1800221cd  jns     short loc_1800221E4
0x1800221cf  mov     r9d, ebx
0x1800221d2  lea     rcx, aResextract; "ResExtract"
0x1800221d9  mov     r8d, 201h
0x1800221df  call    UtilReportError
0x1800221e4  mov     dword ptr [rsp+300h+var_2D0], 203h
0x1800221ec  lea     r9, aUncompressfile_1; "UncompressFile failed"
0x1800221f3  jmp     loc_180022422
0x1800221f8  test    rsi, rsi
0x1800221fb  jz      loc_18002233C
0x180022201  lea     rax, [rsp+300h+var_288]
0x180022206  mov     r8, rsi
0x180022209  mov     [rsp+300h+var_2B8], rax
0x18002220e  mov     rdx, r9
0x180022211  mov     eax, [rbp+200h+arg_38]
0x180022217  mov     rcx, r14
0x18002221a  mov     dword ptr [rsp+300h+var_2D0], eax
0x18002221e  mov     rax, [r15]
0x180022221  mov     [rsp+300h+var_2D8], rax
0x180022226  mov     rax, [r15+8]
0x18002222a  mov     qword ptr [rsp+300h+Status], rax
0x18002222f  call    ExtractOneFileFromRefExtBasedOnHash
0x180022234  test    eax, eax
0x180022236  jnz     loc_18002263C
0x18002223c  xor     edx, edx; Val
0x18002223e  lea     rcx, [rbp+200h+pszDest]; void *
0x180022242  mov     r8d, 200h; Size
0x180022248  call    memset_0
0x18002224d  lea     r8, aFailedToExtrac; "failed to extract file from reference e"...
0x180022254  mov     [rbp+200h+pszSrc], rbx
0x180022258  mov     edx, 100h; unsigned __int64
0x18002225d  lea     rcx, [rbp+200h+pszDest]; unsigned __int16 *
0x180022261  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180022266  lea     rcx, [rsi+10h]
0x18002226a  test    rcx, rcx
0x18002226d  jz      short loc_18002227E
0x18002226f  lea     rdx, [rbp+200h+pszSrc]
0x180022273  call    WimBufferToHexString
0x180022278  mov     rbx, [rbp+200h+pszSrc]
0x18002227c  jmp     short loc_180022283
0x18002227e  mov     eax, 80070057h
0x180022283  test    eax, eax
0x180022285  js      short loc_1800222D2
0x180022287  lea     r8, aHash; "; hash = "
0x18002228e  mov     edx, 100h; cchDest
0x180022293  lea     rcx, [rbp+200h+pszDest]; pszDest
0x180022297  call    StringCchCatW
0x18002229c  mov     r8, rbx; pszSrc
0x18002229f  lea     rcx, [rbp+200h+pszDest]; pszDest
0x1800222a3  mov     edx, 100h; cchDest
0x1800222a8  call    StringCchCatW
0x1800222ad  test    rbx, rbx
0x1800222b0  jz      short loc_1800222D2
0x1800222b2  call    cs:__imp_GetProcessHeap
0x1800222b9  nop     dword ptr [rax+rax+00h]
0x1800222be  mov     r8, rbx; lpMem
0x1800222c1  xor     edx, edx; dwFlags
0x1800222c3  mov     rcx, rax; hHeap
0x1800222c6  call    cs:__imp_HeapFree
0x1800222cd  nop     dword ptr [rax+rax+00h]
0x1800222d2  call    cs:__imp_GetLastError
0x1800222d9  nop     dword ptr [rax+rax+00h]
0x1800222de  mov     ecx, eax
0x1800222e0  movzx   eax, ax
0x1800222e3  or      eax, 80070000h
0x1800222e8  test    ecx, ecx
0x1800222ea  cmovle  eax, ecx
0x1800222ed  test    eax, eax
0x1800222ef  jns     short loc_18002230D
0x1800222f1  call    cs:__imp_GetLastError
0x1800222f8  nop     dword ptr [rax+rax+00h]
0x1800222fd  movzx   ebx, ax
0x180022300  or      ebx, 80070000h
0x180022306  test    eax, eax
0x180022308  cmovle  ebx, eax
0x18002230b  jmp     short loc_180022312
0x18002230d  mov     ebx, 80004005h
0x180022312  test    ebx, ebx
0x180022314  jns     short loc_18002232B
0x180022316  mov     r9d, ebx
0x180022319  lea     rcx, aResextract; "ResExtract"
0x180022320  mov     r8d, 226h
0x180022326  call    UtilReportError
0x18002232b  mov     dword ptr [rsp+300h+var_2D0], 228h
0x180022333  lea     r9, [rbp+200h+pszDest]
0x180022337  jmp     loc_180022422
0x18002233c  mov     rcx, r13
0x18002233f  xor     edx, edx
0x180022341  call    GetWimFileHandle
0x180022346  mov     rcx, qword ptr cs:g_liZero
0x18002234d  mov     [rbp+200h+pszSrc], rax
0x180022351  test    rdi, rdi
0x180022354  jz      short loc_180022363
0x180022356  mov     rdx, [rdi+8]
0x18002235a  mov     rax, [rdi+10h]
0x18002235e  and     rdx, r8
0x180022361  jmp     short loc_180022366
0x180022363  mov     rax, rcx
0x180022366  lea     r8, [rsp+300h+var_288]
0x18002236b  mov     [rsp+300h+var_298], r8; __int64
0x180022370  mov     r8d, [rbp+200h+arg_38]
0x180022377  mov     [rsp+300h+var_2A0], r8d; int
0x18002237c  mov     r8, [r15+8]; int
0x180022380  mov     [rsp+300h+var_2A8], r8; __int64
0x180022385  mov     qword ptr [rsp+300h+FileSize], rdx; FileSize
0x18002238a  lea     rdx, [rbp+200h+pszSrc]; int
0x18002238e  mov     [rsp+300h+var_2B8], rcx; __int64
0x180022393  mov     rcx, r14; int
0x180022396  mov     [rsp+300h+var_2C0], rax; __int64
0x18002239b  mov     dword ptr [rsp+300h+var_2C8], 4A200000h; int
0x1800223a3  mov     [rsp+300h+var_2D8], r12; __int64
0x1800223a8  mov     qword ptr [rsp+300h+Status], r15; __int64
0x1800223ad  call    WIMCopyFileEx
0x1800223b2  test    eax, eax
0x1800223b4  jnz     loc_18002263C
0x1800223ba  call    cs:__imp_GetLastError
0x1800223c1  nop     dword ptr [rax+rax+00h]
0x1800223c6  mov     ecx, eax
0x1800223c8  movzx   eax, ax
0x1800223cb  or      eax, 80070000h
0x1800223d0  test    ecx, ecx
0x1800223d2  cmovle  eax, ecx
0x1800223d5  test    eax, eax
0x1800223d7  jns     short loc_1800223F5
0x1800223d9  call    cs:__imp_GetLastError
0x1800223e0  nop     dword ptr [rax+rax+00h]
0x1800223e5  movzx   ebx, ax
0x1800223e8  or      ebx, 80070000h
0x1800223ee  test    eax, eax
0x1800223f0  cmovle  ebx, eax
0x1800223f3  jmp     short loc_1800223FA
0x1800223f5  mov     ebx, 80004005h
0x1800223fa  test    ebx, ebx
0x1800223fc  jns     short loc_180022413
0x1800223fe  mov     r9d, ebx
0x180022401  lea     rcx, aResextract; "ResExtract"
0x180022408  mov     r8d, 25Fh
0x18002240e  call    UtilReportError
0x180022413  mov     dword ptr [rsp+300h+var_2D0], 260h; int
0x18002241b  lea     r9, aWimcopyfileexF; "WIMCopyFileEx failed"
0x180022422  lea     rax, aResextract; "ResExtract"
0x180022429  mov     r8, r12; int
0x18002242c  mov     [rsp+300h+var_2D8], rax; __int64
0x180022431  mov     rdx, r14; int
0x180022434  mov     ecx, 2; int
0x180022439  mov     [rsp+300h+Status], ebx; Status
0x18002243d  call    _WIMLogMsg
0x180022442  test    ebx, ebx
0x180022444  jns     loc_18002263C
0x18002244a  test    r13, r13
0x18002244d  jz      loc_180022638
0x180022453  mov     esi, ebx
0x180022455  mov     ecx, ebx; Status
0x180022457  and     esi, 10000000h
0x18002245d  jz      short loc_180022488
0x18002245f  call    cs:__imp_RtlNtStatusToDosError
0x180022466  nop     dword ptr [rax+rax+00h]
0x18002246b  cmp     eax, 13Dh
0x180022470  jnz     short loc_180022476
0x180022472  mov     edx, ebx
0x180022474  jmp     short loc_18002249C
0x180022476  mov     ecx, ebx; Status
0x180022478  call    cs:__imp_RtlNtStatusToDosError
0x18002247f  nop     dword ptr [rax+rax+00h]
0x180022484  mov     edx, eax
0x180022486  jmp     short loc_18002249C
0x180022488  and     ecx, 1FFF0000h
0x18002248e  movzx   eax, bx
0x180022491  cmp     ecx, 70000h
0x180022497  mov     edx, ebx
0x180022499  cmovz   edx, eax
0x18002249c  mov     ecx, [rsp+300h+var_290]
0x1800224a0  lea     r8, [rsp+300h+dwMilliseconds]
0x1800224a5  call    WdsShouldRetryFailedCopy
0x1800224aa  test    eax, eax
0x1800224ac  jz      loc_180022634
0x1800224b2  mov     rcx, r13
0x1800224b5  mov     r15d, 1
0x1800224bb  call    GetWimFileHandle
0x1800224c0  mov     rcx, rax; hObject
0x1800224c3  call    WIMFileCloseHandle
0x1800224c8  cmp     dword ptr [r13+0], 0FEEDF001h
0x1800224d0  jnz     short loc_1800224D7
0x1800224d2  mov     rax, r13
0x1800224d5  jmp     short loc_1800224E5
0x1800224d7  cmp     dword ptr [r13+0], 0FEEDF002h
0x1800224df  jnz     short loc_1800224EF
0x1800224e1  mov     rax, [r13+8]
0x1800224e5  test    rax, rax
0x1800224e8  jz      short loc_1800224EF
  ... truncated ...
```
