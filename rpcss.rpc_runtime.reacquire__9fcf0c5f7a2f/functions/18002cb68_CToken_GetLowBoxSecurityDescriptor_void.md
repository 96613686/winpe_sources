# CToken::GetLowBoxSecurityDescriptor(void * *)

- ea: `0x18002cb68`
- end: `0x18002d043`
- name: `?GetLowBoxSecurityDescriptor@CToken@@QEAAJPEAPEAX@Z`
- size: `1243`
- prototype: `int(CToken *__hidden this, void **)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002c9b0`
- `0x180060d34`

## callees

- `0x18002cb68`
- `0x18002f3e0`
- `0x180034260`
- `0x18004a3f4`
- `0x18006bdc4`
- `0x180074190`
- `0x1800a7388`
- `0x1800b7ac0`
- `0x180112d00`
- `0x180114010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cc81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ccb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cd3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cf5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cf94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cc81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ccb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cd3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cf5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cf94`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002cfc0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002cfc0`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002cf2e`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002cf2e`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18002cc53`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18002cd09`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18002cc53`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18002cd09`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18002cfd5`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18002cfea`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18002cfd5`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18002cfea`

## string_xrefs

- `0x18002cca8`: `onecore\com\combase\rpcss\objex\token.cxx`
- `0x18002cf83`: `onecore\com\combase\rpcss\objex\token.cxx`
- `0x18002cc9a`: `CToken::GetLowBoxSecurityDescriptor`
- `0x18002cf72`: `CToken::GetLowBoxSecurityDescriptor`

## pseudocode

```c
__int64 __fastcall CToken::GetLowBoxSecurityDescriptor(CToken *this, void **a2)
{
  unsigned __int16 *p_StringSid; // rdi
  void *v5; // rcx
  PSID v6; // r14
  signed int v7; // ebx
  __int64 v8; // rdx
  signed int LastError; // eax
  int PackageSidFromToken; // eax
  DWORD v11; // eax
  int v12; // r8d
  __int64 v13; // rax
  __int64 v14; // rcx
  LPWSTR v15; // rdx
  int v16; // eax
  __int64 v17; // rsi
  unsigned __int64 v18; // rbx
  unsigned __int64 v19; // rcx
  __int64 v20; // rcx
  unsigned __int64 v21; // rcx
  void *v22; // rsp
  void *v23; // rsp
  unsigned __int16 *v24; // rax
  __int64 v25; // rax
  __int64 v26; // rsi
  unsigned __int64 v27; // rbx
  unsigned __int64 v28; // rcx
  __int64 v29; // rcx
  void *v30; // rsp
  void *v31; // rsp
  unsigned __int16 *v32; // rax
  signed int v33; // eax
  _BYTE v35[32]; // [rsp+0h] [rbp-30h] BYREF
  __int64 v36; // [rsp+28h] [rbp-8h]
  LPWSTR StringSid; // [rsp+30h] [rbp+0h] BYREF
  int v38; // [rsp+38h] [rbp+8h] BYREF
  PSID Sid; // [rsp+40h] [rbp+10h] BYREF
  LPWSTR v40; // [rsp+48h] [rbp+18h] BYREF
  unsigned __int16 v41[8]; // [rsp+50h] [rbp+20h] BYREF
  __int128 v42; // [rsp+60h] [rbp+30h]
  _OWORD v43[2]; // [rsp+70h] [rbp+40h]
  unsigned __int16 v44[8]; // [rsp+90h] [rbp+60h] BYREF
  __int128 v45; // [rsp+A0h] [rbp+70h]
  __int128 v46; // [rsp+B0h] [rbp+80h]
  _OWORD v47[2]; // [rsp+C0h] [rbp+90h]

  *a2 = 0;
  p_StringSid = 0;
  v5 = (void *)*((_QWORD *)this + 9);
  *(_OWORD *)v44 = *(_OWORD *)L"D:(A;;GR;;;RC)(A;;GR;;;%s)(A;;GR;;;%s)";
  v6 = 0;
  v45 = *(_OWORD *)L";;;RC)(A;;GR;;;%s)(A;;GR;;;%s)";
  v46 = *(_OWORD *)L";;GR;;;%s)(A;;GR;;;%s)";
  StringSid = 0;
  v47[0] = *(_OWORD *)L"s)(A;;GR;;;%s)";
  v40 = 0;
  *(_OWORD *)((char *)v47 + 14) = *(_OWORD *)L"R;;;%s)";
  v38 = 0;
  Sid = 0;
  *(_OWORD *)v41 = *(_OWORD *)L"D:(A;;GR;;;RC)(A;;GR;;;%s)";
  v42 = *(_OWORD *)L";;;RC)(A;;GR;;;%s)";
  v43[0] = *(_OWORD *)L";;GR;;;%s)";
  *(_QWORD *)((char *)v43 + 14) = *(_QWORD *)L"%s)";
  v7 = IsTokenBoolPresent(v5, TokenIsAppContainer, &v38);
  if ( v7 < 0 )
    goto LABEL_61;
  if ( !ConvertSidToStringSidW((char *)this + 156, &StringSid) )
  {
    if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
    {
      LODWORD(v36) = GetLastError();
      ComTraceMessageT<int>(
        (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\token.cxx",
        (unsigned int)"CToken::GetLowBoxSecurityDescriptor",
        2923,
        0,
        (__int64)L"%!WINERROR!",
        v36);
    }
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_61;
  }
  if ( v38 )
  {
    PackageSidFromToken = GetPackageSidFromToken(*((HANDLE *)this + 9), &Sid);
    v6 = Sid;
    v7 = PackageSidFromToken;
    if ( PackageSidFromToken < 0 )
      goto LABEL_59;
    if ( !ConvertSidToStringSidW(Sid, &v40) )
    {
      if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
      {
        v11 = GetLastError();
        v12 = 2937;
LABEL_56:
        LODWORD(v36) = v11;
        ComTraceMessageT<int>(
          (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\token.cxx",
          (unsigned int)"CToken::GetLowBoxSecurityDescriptor",
          v12,
          0,
          (__int64)L"%!WINERROR!",
          v36);
        goto LABEL_57;
      }
      goto LABEL_57;
    }
    v13 = -1;
    v14 = -1;
    do
      ++v14;
    while ( StringSid[v14] );
    v15 = v40;
    do
      ++v13;
    while ( v40[v13] );
    v16 = v14 + v13;
    v17 = (unsigned int)(2 * v16 + 78);
    if ( 2 * v16 == -78 )
      goto LABEL_28;
    v18 = (unsigned int)v17;
    if ( (unsigned int)v17 > (unsigned __int64)g_ulMaxStackAllocSize )
      goto LABEL_28;
    v19 = (unsigned int)v17 + g_ulAdditionalProbeSize + 8;
    if ( v19 < (unsigned int)v17 || !(unsigned int)VerifyStackAvailable(v19, v40) )
      goto LABEL_28;
    v20 = v17 + 23;
    if ( v17 + 23 <= (unsigned __int64)(v17 + 8) )
      v20 = 0xFFFFFFFFFFFFFF0LL;
    v21 = v20 & 0xFFFFFFFFFFFFFFF0uLL;
    v22 = alloca(v21);
    v23 = alloca(v21);
    p_StringSid = (unsigned __int16 *)&StringSid;
    if ( v35 == (_BYTE *)-48LL || (LODWORD(StringSid) = 1801679955, (p_StringSid = (unsigned __int16 *)&v38) == 0) )
    {
LABEL_28:
      v18 = (unsigned int)v17;
      if ( v17 + 8 >= (unsigned __int64)(unsigned int)v17 )
      {
        v24 = (unsigned __int16 *)((__int64 (__fastcall *)(__int64, LPWSTR))g_pfnAllocate)(v17 + 8, v15);
        p_StringSid = v24;
        if ( v24 )
        {
          *(_DWORD *)v24 = 1885431112;
          p_StringSid = v24 + 4;
        }
      }
    }
    if ( !p_StringSid )
    {
      v7 = -2147024882;
      goto LABEL_59;
    }
    v7 = StringCbPrintfW(p_StringSid, v18, v44, StringSid, v40);
    if ( v7 < 0 )
    {
LABEL_59:
      if ( v6 )
        HeapFree(g_hHeap, 0, v6);
      goto LABEL_61;
    }
LABEL_51:
    if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(p_StringSid, 1u, a2, 0) )
    {
      if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
      {
        v11 = GetLastError();
        v12 = 3001;
        goto LABEL_56;
      }
LABEL_57:
      v33 = GetLastError();
      v7 = v33;
      if ( v33 > 0 )
        v7 = (unsigned __int16)v33 | 0x80070000;
      goto LABEL_59;
    }
    goto LABEL_59;
  }
  v25 = -1;
  do
    ++v25;
  while ( StringSid[v25] );
  v26 = (unsigned int)(2 * v25 + 54);
  if ( 2 * (_DWORD)v25 == -54 )
    goto LABEL_45;
  v27 = (unsigned int)v26;
  if ( (unsigned int)v26 > (unsigned __int64)g_ulMaxStackAllocSize )
    goto LABEL_45;
  v28 = (unsigned int)v26 + g_ulAdditionalProbeSize + 8;
  if ( v28 < (unsigned int)v26 || !(unsigned int)VerifyStackAvailable(v28, v8) )
    goto LABEL_45;
  v29 = v26 + 23;
  if ( v26 + 23 <= (unsigned __int64)(v26 + 8) )
    v29 = 0xFFFFFFFFFFFFFF0LL;
  v30 = alloca(v29 & 0xFFFFFFFFFFFFFFF0uLL);
  v31 = alloca(v29 & 0xFFFFFFFFFFFFFFF0uLL);
  p_StringSid = (unsigned __int16 *)&StringSid;
  if ( v35 == (_BYTE *)-48LL || (LODWORD(StringSid) = 1801679955, (p_StringSid = (unsigned __int16 *)&v38) == 0) )
  {
LABEL_45:
    v27 = (unsigned int)v26;
    if ( v26 + 8 >= (unsigned __int64)(unsigned int)v26 )
    {
      v32 = (unsigned __int16 *)((__int64 (*)(void))g_pfnAllocate)();
      p_StringSid = v32;
      if ( v32 )
      {
        *(_DWORD *)v32 = 1885431112;
        p_StringSid = v32 + 4;
      }
    }
  }
  if ( !p_StringSid )
  {
    v7 = -2147024882;
    goto LABEL_61;
  }
  v7 = StringCbPrintfW(p_StringSid, v27, v41, StringSid);
  if ( v7 >= 0 )
    goto LABEL_51;
LABEL_61:
  if ( StringSid )
    LocalFree(StringSid);
  if ( v40 )
    LocalFree(v40);
  if ( p_StringSid && *((_DWORD *)p_StringSid - 2) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18002cb68  push    rbp
0x18002cb6a  push    rdi
0x18002cb6b  push    r12
0x18002cb6d  push    r14
0x18002cb6f  push    r15
0x18002cb71  sub     rsp, 0F0h
0x18002cb78  lea     rbp, [rsp+30h]
0x18002cb7d  mov     [rbp+0E0h+arg_10], rbx
0x18002cb84  mov     [rbp+0E0h+arg_18], rsi
0x18002cb8b  mov     rax, cs:__security_cookie
0x18002cb92  xor     rax, rbp
0x18002cb95  mov     [rbp+0E0h+var_30], rax
0x18002cb9c  xor     r12d, r12d
0x18002cb9f  lea     r8, [rbp+0E0h+var_D8]; int *
0x18002cba3  mov     [rdx], r12
0x18002cba6  mov     r15, rdx
0x18002cba9  movaps  xmm0, xmmword ptr cs:aDAGrRcAGrSAGrS; "D:(A;;GR;;;RC)(A;;GR;;;%s)(A;;GR;;;%s)"
0x18002cbb0  mov     rsi, rcx
0x18002cbb3  movaps  xmm1, xmmword ptr cs:aDAGrRcAGrSAGrS+10h; ";;;RC)(A;;GR;;;%s)(A;;GR;;;%s)"
0x18002cbba  mov     edi, r12d
0x18002cbbd  mov     rcx, [rcx+48h]; void *
0x18002cbc1  lea     edx, [r12+1Dh]; enum _TOKEN_INFORMATION_CLASS
0x18002cbc6  movaps  xmmword ptr [rbp+0E0h+var_80], xmm0
0x18002cbca  mov     r14d, r12d
0x18002cbcd  movaps  xmm0, xmmword ptr cs:aDAGrRcAGrSAGrS+20h; ";;GR;;;%s)(A;;GR;;;%s)"
0x18002cbd4  movaps  [rbp+0E0h+var_70], xmm1
0x18002cbd8  movaps  xmm1, xmmword ptr cs:aDAGrRcAGrSAGrS+30h; "s)(A;;GR;;;%s)"
0x18002cbdf  movaps  [rbp+0E0h+var_60], xmm0
0x18002cbe6  movups  xmm0, xmmword ptr cs:aDAGrRcAGrSAGrS+3Eh; "R;;;%s)"
0x18002cbed  mov     [rbp+0E0h+StringSid], r12
0x18002cbf1  movaps  xmmword ptr [rbp+0E0h+var_50], xmm1
0x18002cbf8  movups  xmm1, xmmword ptr cs:aDAGrRcAGrS; "D:(A;;GR;;;RC)(A;;GR;;;%s)"
0x18002cbff  mov     [rbp+0E0h+var_C8], r12
0x18002cc03  movups  xmmword ptr [rbp+0E0h+var_50+0Eh], xmm0
0x18002cc0a  mov     [rbp+0E0h+var_D8], r12d
0x18002cc0e  movups  xmm0, xmmword ptr cs:aDAGrRcAGrS+10h; ";;;RC)(A;;GR;;;%s)"
0x18002cc15  mov     [rbp+0E0h+Sid], r12
0x18002cc19  movups  xmmword ptr [rbp+0E0h+var_C0], xmm1
0x18002cc1d  movups  xmm1, xmmword ptr cs:aDAGrRcAGrS+20h; ";;GR;;;%s)"
0x18002cc24  movups  [rbp+0E0h+var_B0], xmm0
0x18002cc28  movsd   xmm0, qword ptr cs:aDAGrRcAGrS+2Eh; "%s)"
0x18002cc30  movups  xmmword ptr [rbp+0E0h+var_A0], xmm1
0x18002cc34  movsd   qword ptr [rbp+0E0h+var_A0+0Eh], xmm0
0x18002cc39  call    ?IsTokenBoolPresent@@YAJPEAXW4_TOKEN_INFORMATION_CLASS@@PEAH@Z; IsTokenBoolPresent(void *,_TOKEN_INFORMATION_CLASS,int *)
0x18002cc3e  mov     ebx, eax
0x18002cc40  test    eax, eax
0x18002cc42  js      loc_18002CFCC
0x18002cc48  lea     rcx, [rsi+9Ch]; Sid
0x18002cc4f  lea     rdx, [rbp+0E0h+StringSid]; StringSid
0x18002cc53  call    cs:__imp_ConvertSidToStringSidW
0x18002cc5a  nop     dword ptr [rax+rax+00h]
0x18002cc5f  test    eax, eax
0x18002cc61  jnz     short loc_18002CCDD
0x18002cc63  mov     eax, cs:dword_1801574B8
0x18002cc69  test    eax, eax
0x18002cc6b  jnz     short loc_18002CC81
0x18002cc6d  cmp     cs:?gfEnableTracing@@3HA, r12d; int gfEnableTracing
0x18002cc74  jz      short loc_18002CCB9
0x18002cc76  xor     ecx, ecx
0x18002cc78  call    IsWppLevelEnabled
0x18002cc7d  test    al, al
0x18002cc7f  jz      short loc_18002CCB9
0x18002cc81  call    cs:__imp_GetLastError
0x18002cc88  nop     dword ptr [rax+rax+00h]
0x18002cc8d  mov     dword ptr [rsp+110h+var_E8], eax
0x18002cc91  xor     r9d, r9d
0x18002cc94  mov     r8d, 0B6Bh
0x18002cc9a  lea     rdx, aCtokenGetlowbo; "CToken::GetLowBoxSecurityDescriptor"
0x18002cca1  lea     rax, aWinerror; "%!WINERROR!"
0x18002cca8  lea     rcx, aOnecoreComComb_100; "onecore\\com\\combase\\rpcss\\objex\\to"...
0x18002ccaf  mov     [rsp+110h+var_F0], rax
0x18002ccb4  call    ??$ComTraceMessageT@H@@YAXPEBD0HW4TraceLevel@@PEBGH@Z; ComTraceMessageT<int>(char const *,char const *,int,TraceLevel,ushort const *,int)
0x18002ccb9  call    cs:__imp_GetLastError
0x18002ccc0  nop     dword ptr [rax+rax+00h]
0x18002ccc5  mov     ebx, eax
0x18002ccc7  test    eax, eax
0x18002ccc9  jle     loc_18002CFCC
0x18002cccf  movzx   ebx, ax
0x18002ccd2  or      ebx, 80070000h
0x18002ccd8  jmp     loc_18002CFCC
0x18002ccdd  cmp     [rbp+0E0h+var_D8], r12d
0x18002cce1  jz      loc_18002CE4C
0x18002cce7  mov     rcx, [rsi+48h]; TokenHandle
0x18002cceb  lea     rdx, [rbp+0E0h+Sid]; void **
0x18002ccef  call    ?GetPackageSidFromToken@@YAJPEAXPEAPEAX@Z; GetPackageSidFromToken(void *,void * *)
0x18002ccf4  mov     r14, [rbp+0E0h+Sid]
0x18002ccf8  mov     ebx, eax
0x18002ccfa  test    eax, eax
0x18002ccfc  js      loc_18002CFAF
0x18002cd02  lea     rdx, [rbp+0E0h+var_C8]; StringSid
0x18002cd06  mov     rcx, r14; Sid
0x18002cd09  call    cs:__imp_ConvertSidToStringSidW
0x18002cd10  nop     dword ptr [rax+rax+00h]
0x18002cd15  test    eax, eax
0x18002cd17  jnz     short loc_18002CD56
0x18002cd19  mov     eax, cs:dword_1801574B8
0x18002cd1f  test    eax, eax
0x18002cd21  jnz     short loc_18002CD3F
0x18002cd23  cmp     cs:?gfEnableTracing@@3HA, r12d; int gfEnableTracing
0x18002cd2a  jz      loc_18002CF94
0x18002cd30  xor     ecx, ecx
0x18002cd32  call    IsWppLevelEnabled
0x18002cd37  test    al, al
0x18002cd39  jz      loc_18002CF94
0x18002cd3f  call    cs:__imp_GetLastError
0x18002cd46  nop     dword ptr [rax+rax+00h]
0x18002cd4b  mov     r8d, 0B79h
0x18002cd51  jmp     loc_18002CF6E
0x18002cd56  mov     rdx, [rbp+0E0h+StringSid]
0x18002cd5a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002cd5e  mov     rcx, rax
0x18002cd61  inc     rcx
0x18002cd64  cmp     [rdx+rcx*2], r12w
0x18002cd69  jnz     short loc_18002CD61
0x18002cd6b  mov     rdx, [rbp+0E0h+var_C8]
0x18002cd6f  inc     rax
0x18002cd72  cmp     [rdx+rax*2], r12w
0x18002cd77  jnz     short loc_18002CD6F
0x18002cd79  add     eax, ecx
0x18002cd7b  lea     esi, ds:4Eh[rax*2]
0x18002cd82  test    esi, esi
0x18002cd84  jz      short loc_18002CDE9
0x18002cd86  mov     ebx, esi
0x18002cd88  cmp     rbx, cs:g_ulMaxStackAllocSize
0x18002cd8f  ja      short loc_18002CDE9
0x18002cd91  mov     rcx, cs:g_ulAdditionalProbeSize
0x18002cd98  add     rcx, 8
0x18002cd9c  add     rcx, rbx
0x18002cd9f  cmp     rcx, rbx
0x18002cda2  jb      short loc_18002CDE9
0x18002cda4  call    VerifyStackAvailable
0x18002cda9  test    eax, eax
0x18002cdab  jz      short loc_18002CDE9
0x18002cdad  lea     rax, [rsi+8]
0x18002cdb1  lea     rcx, [rax+0Fh]
0x18002cdb5  cmp     rcx, rax
0x18002cdb8  ja      short loc_18002CDC4
0x18002cdba  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18002cdc4  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18002cdc8  mov     rax, rcx
0x18002cdcb  call    _alloca_probe
0x18002cdd0  sub     rsp, rcx
0x18002cdd3  lea     rdi, [rsp+110h+StringSid]
0x18002cdd8  test    rdi, rdi
0x18002cddb  jz      short loc_18002CDE9
0x18002cddd  mov     dword ptr [rdi], 6B637453h
0x18002cde3  add     rdi, 8
0x18002cde7  jnz     short loc_18002CE12
0x18002cde9  mov     ebx, esi
0x18002cdeb  lea     rcx, [rsi+8]
0x18002cdef  cmp     rcx, rbx
0x18002cdf2  jb      short loc_18002CE12
0x18002cdf4  mov     rax, cs:g_pfnAllocate
0x18002cdfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ce00  mov     rdi, rax
0x18002ce03  test    rax, rax
0x18002ce06  jz      short loc_18002CE12
0x18002ce08  mov     dword ptr [rax], 70616548h
0x18002ce0e  add     rdi, 8
0x18002ce12  test    rdi, rdi
0x18002ce15  jnz     short loc_18002CE21
0x18002ce17  mov     ebx, 8007000Eh
0x18002ce1c  jmp     loc_18002CFAF
0x18002ce21  mov     rax, [rbp+0E0h+var_C8]
0x18002ce25  lea     r8, [rbp+0E0h+var_80]; unsigned __int16 *
0x18002ce29  mov     r9, [rbp+0E0h+StringSid]
0x18002ce2d  mov     rdx, rbx; unsigned __int64
0x18002ce30  mov     rcx, rdi; unsigned __int16 *
0x18002ce33  mov     [rsp+110h+var_F0], rax
0x18002ce38  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002ce3d  mov     ebx, eax
0x18002ce3f  test    eax, eax
0x18002ce41  js      loc_18002CFAF
0x18002ce47  jmp     loc_18002CF21
0x18002ce4c  mov     rcx, [rbp+0E0h+StringSid]
0x18002ce50  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002ce54  inc     rax
0x18002ce57  cmp     [rcx+rax*2], r12w
0x18002ce5c  jnz     short loc_18002CE54
0x18002ce5e  lea     esi, ds:36h[rax*2]
0x18002ce65  test    esi, esi
0x18002ce67  jz      short loc_18002CECC
0x18002ce69  mov     ebx, esi
0x18002ce6b  cmp     rbx, cs:g_ulMaxStackAllocSize
0x18002ce72  ja      short loc_18002CECC
0x18002ce74  mov     rcx, cs:g_ulAdditionalProbeSize
0x18002ce7b  add     rcx, 8
0x18002ce7f  add     rcx, rbx
0x18002ce82  cmp     rcx, rbx
0x18002ce85  jb      short loc_18002CECC
0x18002ce87  call    VerifyStackAvailable
0x18002ce8c  test    eax, eax
0x18002ce8e  jz      short loc_18002CECC
0x18002ce90  lea     rax, [rsi+8]
0x18002ce94  lea     rcx, [rax+0Fh]
0x18002ce98  cmp     rcx, rax
0x18002ce9b  ja      short loc_18002CEA7
0x18002ce9d  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18002cea7  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18002ceab  mov     rax, rcx
0x18002ceae  call    _alloca_probe
0x18002ceb3  sub     rsp, rcx
0x18002ceb6  lea     rdi, [rsp+110h+StringSid]
0x18002cebb  test    rdi, rdi
0x18002cebe  jz      short loc_18002CECC
0x18002cec0  mov     dword ptr [rdi], 6B637453h
0x18002cec6  add     rdi, 8
0x18002ceca  jnz     short loc_18002CEF5
0x18002cecc  mov     ebx, esi
0x18002cece  lea     rcx, [rsi+8]
0x18002ced2  cmp     rcx, rbx
0x18002ced5  jb      short loc_18002CEF5
0x18002ced7  mov     rax, cs:g_pfnAllocate
0x18002cede  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cee3  mov     rdi, rax
0x18002cee6  test    rax, rax
0x18002cee9  jz      short loc_18002CEF5
0x18002ceeb  mov     dword ptr [rax], 70616548h
0x18002cef1  add     rdi, 8
0x18002cef5  test    rdi, rdi
0x18002cef8  jnz     short loc_18002CF04
0x18002cefa  mov     ebx, 8007000Eh
0x18002ceff  jmp     loc_18002CFCC
0x18002cf04  mov     r9, [rbp+0E0h+StringSid]
0x18002cf08  lea     r8, [rbp+0E0h+var_C0]; unsigned __int16 *
0x18002cf0c  mov     rdx, rbx; unsigned __int64
0x18002cf0f  mov     rcx, rdi; unsigned __int16 *
0x18002cf12  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002cf17  mov     ebx, eax
0x18002cf19  test    eax, eax
0x18002cf1b  js      loc_18002CFCC
0x18002cf21  xor     r9d, r9d; SecurityDescriptorSize
0x18002cf24  mov     r8, r15; SecurityDescriptor
0x18002cf27  mov     rcx, rdi; StringSecurityDescriptor
0x18002cf2a  lea     edx, [r9+1]; StringSDRevision
0x18002cf2e  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18002cf35  nop     dword ptr [rax+rax+00h]
0x18002cf3a  test    eax, eax
0x18002cf3c  jnz     short loc_18002CFAF
0x18002cf3e  mov     eax, cs:dword_1801574B8
0x18002cf44  test    eax, eax
0x18002cf46  jnz     short loc_18002CF5C
0x18002cf48  cmp     cs:?gfEnableTracing@@3HA, r12d; int gfEnableTracing
0x18002cf4f  jz      short loc_18002CF94
0x18002cf51  xor     ecx, ecx
0x18002cf53  call    IsWppLevelEnabled
0x18002cf58  test    al, al
0x18002cf5a  jz      short loc_18002CF94
0x18002cf5c  call    cs:__imp_GetLastError
0x18002cf63  nop     dword ptr [rax+rax+00h]
0x18002cf68  mov     r8d, 0BB9h
0x18002cf6e  mov     dword ptr [rsp+110h+var_E8], eax
0x18002cf72  lea     rdx, aCtokenGetlowbo; "CToken::GetLowBoxSecurityDescriptor"
0x18002cf79  lea     rax, aWinerror; "%!WINERROR!"
0x18002cf80  xor     r9d, r9d
0x18002cf83  lea     rcx, aOnecoreComComb_100; "onecore\\com\\combase\\rpcss\\objex\\to"...
0x18002cf8a  mov     [rsp+110h+var_F0], rax
0x18002cf8f  call    ??$ComTraceMessageT@H@@YAXPEBD0HW4TraceLevel@@PEBGH@Z; ComTraceMessageT<int>(char const *,char const *,int,TraceLevel,ushort const *,int)
0x18002cf94  call    cs:__imp_GetLastError
0x18002cf9b  nop     dword ptr [rax+rax+00h]
0x18002cfa0  mov     ebx, eax
0x18002cfa2  test    eax, eax
0x18002cfa4  jle     short loc_18002CFAF
0x18002cfa6  movzx   ebx, ax
0x18002cfa9  or      ebx, 80070000h
0x18002cfaf  test    r14, r14
0x18002cfb2  jz      short loc_18002CFCC
0x18002cfb4  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x18002cfbb  mov     r8, r14; lpMem
0x18002cfbe  xor     edx, edx; dwFlags
0x18002cfc0  call    cs:__imp_HeapFree
0x18002cfc7  nop     dword ptr [rax+rax+00h]
0x18002cfcc  mov     rcx, [rbp+0E0h+StringSid]; hMem
0x18002cfd0  test    rcx, rcx
0x18002cfd3  jz      short loc_18002CFE1
0x18002cfd5  call    cs:__imp_LocalFree
0x18002cfdc  nop     dword ptr [rax+rax+00h]
0x18002cfe1  mov     rcx, [rbp+0E0h+var_C8]; hMem
0x18002cfe5  test    rcx, rcx
0x18002cfe8  jz      short loc_18002CFF6
0x18002cfea  call    cs:__imp_LocalFree
0x18002cff1  nop     dword ptr [rax+rax+00h]
0x18002cff6  test    rdi, rdi
0x18002cff9  jz      short loc_18002D013
0x18002cffb  lea     rcx, [rdi-8]
0x18002cfff  cmp     dword ptr [rcx], 70616548h
0x18002d005  jnz     short loc_18002D013
0x18002d007  mov     rax, cs:g_pfnFree
0x18002d00e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d013  mov     eax, ebx
0x18002d015  mov     rcx, [rbp+0E0h+var_30]
0x18002d01c  xor     rcx, rbp; StackCookie
0x18002d01f  call    __security_check_cookie
0x18002d024  mov     rbx, [rbp+0E0h+arg_10]
0x18002d02b  mov     rsi, [rbp+0E0h+arg_18]
0x18002d032  lea     rsp, [rbp+0C0h]
0x18002d039  pop     r15
0x18002d03b  pop     r14
0x18002d03d  pop     r12
0x18002d03f  pop     rdi
  ... truncated ...
```
