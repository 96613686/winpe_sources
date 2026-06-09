# VssGetVolumeDisplayName(ushort *,ushort *,long)

- ea: `0x1800275b4`
- end: `0x1800279e5`
- name: `?VssGetVolumeDisplayName@@YAXPEAG0J@Z`
- size: `1073`
- prototype: `void __fastcall(unsigned __int16 *, unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x180026da0`
- `0x18002d1f0`

## callees

- `0x18000212c`
- `0x180007604`
- `0x1800171dc`
- `0x1800275b4`
- `0x180033a8c`
- `0x180033c78`
- `0x18003649c`
- `0x180037080`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027674`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027685`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027756`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027674`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027685`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027756`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x180027666`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x18002773a`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x180027666`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x18002773a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027947`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027947`

## string_xrefs

- `0x1800276ee`: `GetVolumePathNamesForVolumeName(%s, 0, 0, %p)`
- `0x1800277c2`: `GetVolumePathNamesForVolumeName(%s, %p, %lu, 0)`
- `0x180027846`: `StringCchCopyW`
- `0x1800278e2`: `StringCchCopyW`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall VssGetVolumeDisplayName(unsigned __int16 *a1, unsigned __int16 *a2, DWORD a3)
{
  signed int LastError; // eax
  unsigned int v6; // edi
  unsigned __int16 *v7; // rdi
  signed int v8; // eax
  unsigned int v9; // esi
  int v10; // edi
  const unsigned __int16 *v11; // r8
  __int64 v12; // r9
  __int64 v13; // rdx
  int v14; // edi
  const unsigned __int16 *v15; // rax
  unsigned int v16; // edi
  __int64 v17; // [rsp+20h] [rbp-198h]
  __int64 v18; // [rsp+30h] [rbp-188h]
  const unsigned __int16 *v19; // [rsp+40h] [rbp-178h] BYREF
  const unsigned __int16 *v20; // [rsp+48h] [rbp-170h]
  const unsigned __int16 *v21; // [rsp+50h] [rbp-168h]
  int v22; // [rsp+58h] [rbp-160h]
  int v23; // [rsp+5Ch] [rbp-15Ch]
  int v24; // [rsp+60h] [rbp-158h]
  _BYTE v25[120]; // [rsp+68h] [rbp-150h] BYREF
  int v26; // [rsp+E0h] [rbp-D8h]
  LPVOID pv; // [rsp+E8h] [rbp-D0h]
  unsigned int v28; // [rsp+F0h] [rbp-C8h] BYREF
  LPVOID v29; // [rsp+100h] [rbp-B8h] BYREF
  int v30; // [rsp+108h] [rbp-B0h]
  unsigned int v31; // [rsp+124h] [rbp-94h]
  _com_error *v32; // [rsp+178h] [rbp-40h] BYREF
  const std::exception *v33; // [rsp+180h] [rbp-38h] BYREF
  DWORD cchReturnLength; // [rsp+1D0h] [rbp+18h] BYREF
  DWORD v35; // [rsp+1D8h] [rbp+20h]

  cchReturnLength = a3;
  v19 = L"base\\stor\\vss\\inc\\vs_vol.hxx";
  v20 = L"VssGetVolumeDisplayName";
  v21 = L"INCVOLH";
  v22 = 256;
  v23 = 11;
  v24 = 255;
  v26 = 0x1000000;
  memset_0(v25, 0, sizeof(v25));
  CVssFunctionTracer::CVssFunctionTracer((__int64)&v29, (__int64)&v19, 0);
  pv = 0;
  cchReturnLength = 0;
  if ( !GetVolumePathNamesForVolumeNameW(a1, 0, 0, &cchReturnLength) && GetLastError() != 234 )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    v19 = L"base\\stor\\vss\\inc\\vs_vol.hxx";
    v20 = L"VssGetVolumeDisplayName";
    v21 = L"INCVOLH";
    v22 = 274;
    v23 = 11;
    v24 = 255;
    v26 = 0x1000000;
    memset_0(v25, 0, sizeof(v25));
    try
    {
      CVssFunctionTracer::TranslateGenericError(
        &v29,
        &v19,
        v6,
        L"GetVolumePathNamesForVolumeName(%s, 0, 0, %p)",
        a1,
        &cchReturnLength);
    }
    catch ( long v28 )
    {
      CVssFunctionTracer::HandleHresultException(
        (CVssFunctionTracer *)&v29,
        v28,
        L"base\\stor\\vss\\inc\\vs_vol.hxx",
        L"INCVOLH",
        L"VssGetVolumeDisplayName",
        0x144u,
        v31);
      goto LABEL_25;
    }
    catch ( _com_error *v32 )
    {
      CVssFunctionTracer::HandleComException(
        (CVssFunctionTracer *)&v29,
        v32,
        L"base\\stor\\vss\\inc\\vs_vol.hxx",
        L"INCVOLH",
        L"VssGetVolumeDisplayName",
        0x144u,
        v31);
    }
    catch ( std::bad_alloc )
    {
      CVssFunctionTracer::HandleStdBadAllocException(
        (CVssFunctionTracer *)&v29,
        L"base\\stor\\vss\\inc\\vs_vol.hxx",
        L"INCVOLH",
        L"VssGetVolumeDisplayName",
        0x144u,
        v31);
      goto LABEL_25;
    }
    catch ( const std::exception *v33 )
    {
      CVssFunctionTracer::HandleStdGenericException(
        (CVssFunctionTracer *)&v29,
        v33,
        L"base\\stor\\vss\\inc\\vs_vol.hxx",
        L"INCVOLH",
        L"VssGetVolumeDisplayName",
        0x144u,
        v31);
    }
  }
  v7 = VssAllocString((struct CVssFunctionTracer *)&v29, cchReturnLength);
  pv = v7;
  if ( !GetVolumePathNamesForVolumeNameW(a1, v7, cchReturnLength, 0) )
  {
    v35 = cchReturnLength;
    v8 = GetLastError();
    v9 = v8;
    if ( v8 > 0 )
      v9 = (unsigned __int16)v8 | 0x80070000;
    v19 = L"base\\stor\\vss\\inc\\vs_vol.hxx";
    v20 = L"VssGetVolumeDisplayName";
    v21 = L"INCVOLH";
    v22 = 283;
    v23 = 11;
    v24 = 255;
    v26 = 0x1000000;
    memset_0(v25, 0, sizeof(v25));
    LODWORD(v18) = v35;
    CVssFunctionTracer::TranslateGenericError(
      &v29,
      &v19,
      v9,
      L"GetVolumePathNamesForVolumeName(%s, %p, %lu, 0)",
      a1,
      v7,
      v18);
  }
  if ( *v7 )
  {
    v11 = v7;
    v12 = -1;
    do
      ++v12;
    while ( v7[v12] );
    while ( 1 )
    {
      v13 = -1;
      do
        ++v13;
      while ( v7[v13] );
      if ( !(_DWORD)v13 )
        break;
      v15 = v7;
      if ( (int)v13 >= (int)v12 )
        v15 = v11;
      v11 = v15;
      v7 += (int)v13 + 1;
      if ( (int)v13 >= (int)v12 )
        LODWORD(v13) = v12;
      LODWORD(v12) = v13;
    }
    v14 = StringCchCopyW(a2, 0x104u, v11);
    v30 = v14;
    if ( v14 < 0 )
    {
      v19 = L"base\\stor\\vss\\inc\\vs_vol.hxx";
      v20 = L"VssGetVolumeDisplayName";
      v21 = L"INCVOLH";
      v22 = 321;
      v23 = 11;
      v24 = 255;
      v26 = 0x1000000;
      memset_0(v25, 0, sizeof(v25));
      CVssFunctionTracer::TranslateGenericError(&v29, &v19, (unsigned int)v14, L"StringCchCopyW");
    }
  }
  else
  {
    v10 = StringCchCopyW(a2, 0x104u, a1);
    v30 = v10;
    if ( v10 < 0 )
    {
      v19 = L"base\\stor\\vss\\inc\\vs_vol.hxx";
      v20 = L"VssGetVolumeDisplayName";
      v21 = L"INCVOLH";
      v22 = 291;
      v23 = 11;
      v24 = 255;
      v26 = 0x1000000;
      memset_0(v25, 0, sizeof(v25));
      CVssFunctionTracer::TranslateGenericError(&v29, &v19, (unsigned int)v10, L"StringCchCopyW");
    }
  }
LABEL_25:
  CoTaskMemFree(pv);
  v16 = v30;
  if ( v30 < 0 )
  {
    v19 = L"base\\stor\\vss\\inc\\vs_vol.hxx";
    v20 = L"VssGetVolumeDisplayName";
    v21 = L"INCVOLH";
    v22 = 329;
    v23 = 11;
    v24 = 255;
    v26 = 0x1000000;
    memset_0(v25, 0, sizeof(v25));
    LODWORD(v17) = v16;
    CVssFunctionTracer::Throw(&v29, &v19, v16, L"Rethrowing 0x%08lx", v17);
  }
  CVssFunctionTracer::~CVssFunctionTracer(&v29);
}

```

## disassembly

```asm
0x1800275b4  mov     rax, rsp
0x1800275b7  mov     [rax+8], rbx
0x1800275bb  mov     [rax+10h], rsi
0x1800275bf  mov     [rax+18h], r8d
0x1800275c3  push    rdi
0x1800275c4  push    r12
0x1800275c6  push    r13
0x1800275c8  push    r14
0x1800275ca  push    r15
0x1800275cc  sub     rsp, 190h
0x1800275d3  mov     rsi, rdx
0x1800275d6  mov     r13, rcx
0x1800275d9  lea     r14, aBaseStorVssInc; "base\\stor\\vss\\inc\\vs_vol.hxx"
0x1800275e0  mov     [rsp+1B8h+var_178], r14
0x1800275e5  lea     r15, aVssgetvolumedi; "VssGetVolumeDisplayName"
0x1800275ec  mov     [rsp+1B8h+var_170], r15
0x1800275f1  lea     r12, aIncvolh; "INCVOLH"
0x1800275f8  mov     [rsp+1B8h+var_168], r12
0x1800275fd  mov     [rsp+1B8h+var_160], 100h
0x180027605  mov     [rsp+1B8h+var_15C], 0Bh
0x18002760d  mov     [rsp+1B8h+var_158], 0FFh
0x180027615  xor     ebx, ebx
0x180027617  mov     dword ptr [rax-0D8h], 1000000h
0x180027621  xor     edx, edx; Val
0x180027623  lea     r8d, [rbx+78h]; Size
0x180027627  lea     rcx, [rsp+1B8h+var_150]; void *
0x18002762c  call    memset_0
0x180027631  xor     r8d, r8d
0x180027634  lea     rdx, [rsp+1B8h+var_178]
0x180027639  lea     rcx, [rsp+1B8h+var_B8]
0x180027641  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x180027646  nop
0x180027647  mov     [rsp+1B8h+pv], rbx
0x18002764f  mov     [rsp+1B8h+cchReturnLength], ebx
0x180027656  lea     r9, [rsp+1B8h+cchReturnLength]; lpcchReturnLength
0x18002765e  xor     r8d, r8d; cchBufferLength
0x180027661  xor     edx, edx; lpszVolumePathNames
0x180027663  mov     rcx, r13; lpszVolumeName
0x180027666  call    cs:__imp_GetVolumePathNamesForVolumeNameW
0x18002766c  test    eax, eax
0x18002766e  jnz     loc_18002770A
0x180027674  call    cs:__imp_GetLastError
0x18002767a  cmp     eax, 0EAh
0x18002767f  jz      loc_18002770A
0x180027685  call    cs:__imp_GetLastError
0x18002768b  mov     edi, eax
0x18002768d  test    eax, eax
0x18002768f  jle     short loc_18002769A
0x180027691  movzx   edi, ax
0x180027694  or      edi, 80070000h
0x18002769a  mov     [rsp+1B8h+var_178], r14
0x18002769f  mov     [rsp+1B8h+var_170], r15
0x1800276a4  mov     [rsp+1B8h+var_168], r12
0x1800276a9  mov     [rsp+1B8h+var_160], 112h
0x1800276b1  mov     [rsp+1B8h+var_15C], 0Bh
0x1800276b9  mov     [rsp+1B8h+var_158], 0FFh
0x1800276c1  mov     [rsp+1B8h+var_D8], 1000000h
0x1800276cc  xor     edx, edx; Val
0x1800276ce  lea     r8d, [rdx+78h]; Size
0x1800276d2  lea     rcx, [rsp+1B8h+var_150]; void *
0x1800276d7  call    memset_0
0x1800276dc  lea     rax, [rsp+1B8h+cchReturnLength]
0x1800276e4  mov     [rsp+1B8h+var_190], rax
0x1800276e9  mov     [rsp+1B8h+var_198], r13
0x1800276ee  lea     r9, aGetvolumepathn; "GetVolumePathNamesForVolumeName(%s, 0, "...
0x1800276f5  mov     r8d, edi
0x1800276f8  lea     rdx, [rsp+1B8h+var_178]
0x1800276fd  lea     rcx, [rsp+1B8h+var_B8]
0x180027705  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
0x18002770a  mov     edx, [rsp+1B8h+cchReturnLength]; unsigned __int64
0x180027711  lea     rcx, [rsp+1B8h+var_B8]; struct CVssFunctionTracer *
0x180027719  call    ?VssAllocString@@YAPEAGAEAVCVssFunctionTracer@@_K@Z; VssAllocString(CVssFunctionTracer &,unsigned __int64)
0x18002771e  mov     rdi, rax
0x180027721  mov     [rsp+1B8h+pv], rax
0x180027729  xor     r9d, r9d; lpcchReturnLength
0x18002772c  mov     r8d, [rsp+1B8h+cchReturnLength]; cchBufferLength
0x180027734  mov     rdx, rax; lpszVolumePathNames
0x180027737  mov     rcx, r13; lpszVolumeName
0x18002773a  call    cs:__imp_GetVolumePathNamesForVolumeNameW
0x180027740  test    eax, eax
0x180027742  jnz     loc_1800277DE
0x180027748  mov     eax, [rsp+1B8h+cchReturnLength]
0x18002774f  mov     [rsp+1B8h+arg_18], eax
0x180027756  call    cs:__imp_GetLastError
0x18002775c  mov     esi, eax
0x18002775e  test    eax, eax
0x180027760  jle     short loc_18002776B
0x180027762  movzx   esi, ax
0x180027765  or      esi, 80070000h
0x18002776b  mov     [rsp+1B8h+var_178], r14
0x180027770  mov     [rsp+1B8h+var_170], r15
0x180027775  mov     [rsp+1B8h+var_168], r12
0x18002777a  mov     [rsp+1B8h+var_160], 11Bh
0x180027782  mov     [rsp+1B8h+var_15C], 0Bh
0x18002778a  mov     [rsp+1B8h+var_158], 0FFh
0x180027792  mov     [rsp+1B8h+var_D8], 1000000h
0x18002779d  xor     edx, edx; Val
0x18002779f  lea     r8d, [rdx+78h]; Size
0x1800277a3  lea     rcx, [rsp+1B8h+var_150]; void *
0x1800277a8  call    memset_0
0x1800277ad  mov     eax, [rsp+1B8h+arg_18]
0x1800277b4  mov     dword ptr [rsp+1B8h+var_188], eax
0x1800277b8  mov     [rsp+1B8h+var_190], rdi
0x1800277bd  mov     [rsp+1B8h+var_198], r13
0x1800277c2  lea     r9, aGetvolumepathn_0; "GetVolumePathNamesForVolumeName(%s, %p,"...
0x1800277c9  mov     r8d, esi
0x1800277cc  lea     rdx, [rsp+1B8h+var_178]
0x1800277d1  lea     rcx, [rsp+1B8h+var_B8]
0x1800277d9  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
0x1800277de  cmp     [rdi], bx
0x1800277e1  jnz     short loc_180027862
0x1800277e3  mov     r8, r13; unsigned __int16 *
0x1800277e6  mov     edx, 104h; unsigned __int64
0x1800277eb  mov     rcx, rsi; unsigned __int16 *
0x1800277ee  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800277f3  mov     edi, eax
0x1800277f5  mov     [rsp+1B8h+var_B0], eax
0x1800277fc  test    eax, eax
0x1800277fe  jns     loc_1800278FF
0x180027804  mov     [rsp+1B8h+var_178], r14
0x180027809  mov     [rsp+1B8h+var_170], r15
0x18002780e  mov     [rsp+1B8h+var_168], r12
0x180027813  mov     [rsp+1B8h+var_160], 123h
0x18002781b  mov     [rsp+1B8h+var_15C], 0Bh
0x180027823  mov     [rsp+1B8h+var_158], 0FFh
0x18002782b  mov     [rsp+1B8h+var_D8], 1000000h
0x180027836  xor     edx, edx; Val
0x180027838  lea     r8d, [rdx+78h]; Size
0x18002783c  lea     rcx, [rsp+1B8h+var_150]; void *
0x180027841  call    memset_0
0x180027846  lea     r9, aStringcchcopyw; "StringCchCopyW"
0x18002784d  mov     r8d, edi
0x180027850  lea     rdx, [rsp+1B8h+var_178]
0x180027855  lea     rcx, [rsp+1B8h+var_B8]
0x18002785d  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
0x180027862  mov     r8, rdi; unsigned __int16 *
0x180027865  or      r10, 0FFFFFFFFFFFFFFFFh
0x180027869  mov     r9, r10
0x18002786c  inc     r9
0x18002786f  cmp     [rdi+r9*2], bx
0x180027874  jnz     short loc_18002786C
0x180027876  mov     rdx, r10
0x180027879  inc     rdx
0x18002787c  cmp     [rdi+rdx*2], bx
0x180027880  jnz     short loc_180027879
0x180027882  test    edx, edx
0x180027884  jnz     short loc_180027901
0x180027886  mov     edx, 104h; unsigned __int64
0x18002788b  mov     rcx, rsi; unsigned __int16 *
0x18002788e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180027893  mov     edi, eax
0x180027895  mov     [rsp+1B8h+var_B0], eax
0x18002789c  test    eax, eax
0x18002789e  jns     short loc_1800278FF
0x1800278a0  mov     [rsp+1B8h+var_178], r14
0x1800278a5  mov     [rsp+1B8h+var_170], r15
0x1800278aa  mov     [rsp+1B8h+var_168], r12
0x1800278af  mov     [rsp+1B8h+var_160], 141h
0x1800278b7  mov     [rsp+1B8h+var_15C], 0Bh
0x1800278bf  mov     [rsp+1B8h+var_158], 0FFh
0x1800278c7  mov     [rsp+1B8h+var_D8], 1000000h
0x1800278d2  xor     edx, edx; Val
0x1800278d4  lea     r8d, [rdx+78h]; Size
0x1800278d8  lea     rcx, [rsp+1B8h+var_150]; void *
0x1800278dd  call    memset_0
0x1800278e2  lea     r9, aStringcchcopyw; "StringCchCopyW"
0x1800278e9  mov     r8d, edi
0x1800278ec  lea     rdx, [rsp+1B8h+var_178]
0x1800278f1  lea     rcx, [rsp+1B8h+var_B8]
0x1800278f9  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
0x1800278ff  jmp     short loc_18002793F
0x180027901  mov     rax, rdi
0x180027904  cmp     edx, r9d
0x180027907  cmovge  rax, r8
0x18002790b  mov     r8, rax
0x18002790e  lea     eax, [rdx+1]
0x180027911  movsxd  rcx, eax
0x180027914  lea     rdi, [rdi+rcx*2]
0x180027918  cmovge  edx, r9d
0x18002791c  mov     r9d, edx
0x18002791f  jmp     loc_180027876
0x180027924  jmp     short loc_18002792A
0x180027926  jmp     short loc_18002792A
0x180027928  jmp     short $+2
0x18002792a  lea     r12, aIncvolh; "INCVOLH"
0x180027931  lea     r15, aVssgetvolumedi; "VssGetVolumeDisplayName"
0x180027938  lea     r14, aBaseStorVssInc; "base\\stor\\vss\\inc\\vs_vol.hxx"
0x18002793f  mov     rcx, [rsp+1B8h+pv]; pv
0x180027947  call    cs:__imp_CoTaskMemFree
0x18002794d  mov     edi, [rsp+1B8h+var_B0]
0x180027954  test    edi, edi
0x180027956  jns     short loc_1800279BB
0x180027958  mov     [rsp+1B8h+var_178], r14
0x18002795d  mov     [rsp+1B8h+var_170], r15
0x180027962  mov     [rsp+1B8h+var_168], r12
0x180027967  mov     [rsp+1B8h+var_160], 149h
0x18002796f  mov     [rsp+1B8h+var_15C], 0Bh
0x180027977  mov     [rsp+1B8h+var_158], 0FFh
0x18002797f  mov     [rsp+1B8h+var_D8], 1000000h
0x18002798a  xor     edx, edx; Val
0x18002798c  lea     r8d, [rdx+78h]; Size
0x180027990  lea     rcx, [rsp+1B8h+var_150]; void *
0x180027995  call    memset_0
0x18002799a  mov     dword ptr [rsp+1B8h+var_198], edi
0x18002799e  lea     r9, aRethrowing0x08; "Rethrowing 0x%08lx"
0x1800279a5  mov     r8d, edi
0x1800279a8  lea     rdx, [rsp+1B8h+var_178]
0x1800279ad  lea     rcx, [rsp+1B8h+var_B8]
0x1800279b5  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x1800279bb  lea     rcx, [rsp+1B8h+var_B8]; this
0x1800279c3  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x1800279c8  lea     r11, [rsp+1B8h+var_28]
0x1800279d0  mov     rbx, [r11+30h]
0x1800279d4  mov     rsi, [r11+38h]
0x1800279d8  mov     rsp, r11
0x1800279db  pop     r15
0x1800279dd  pop     r14
0x1800279df  pop     r13
0x1800279e1  pop     r12
0x1800279e3  pop     rdi
0x1800279e4  retn
```
