# CToken::GetLowBoxSecurityDescriptor(void * *)

- ea: `0x1800229b4`
- end: `0x180022e4c`
- name: `?GetLowBoxSecurityDescriptor@CToken@@QEAAJPEAPEAX@Z`
- size: `1176`
- prototype: `int(CToken *__hidden this, void **)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180022810`
- `0x18005bac8`

## callees

- `0x1800229b4`
- `0x1800250b0`
- `0x180034540`
- `0x180040918`
- `0x1800672dc`
- `0x18006fa24`
- `0x1800a1e98`
- `0x1800b27e0`
- `0x18010a000`
- `0x18010b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022ac7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022af9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022b73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022d84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022db6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022ac7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022af9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022b73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022d84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022db6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022ddc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022ddc`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180022d5c`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180022d5c`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180022a9f`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180022b43`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180022a9f`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180022b43`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180022deb`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180022dfa`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180022deb`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180022dfa`

## string_xrefs

- `0x180022ae8`: `onecore\com\combase\rpcss\objex\token.cxx`
- `0x180022da5`: `onecore\com\combase\rpcss\objex\token.cxx`
- `0x180022ada`: `CToken::GetLowBoxSecurityDescriptor`
- `0x180022d94`: `CToken::GetLowBoxSecurityDescriptor`

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
    if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
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
      if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
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
      if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
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
0x1800229b4  push    rbp
0x1800229b6  push    rdi
0x1800229b7  push    r12
0x1800229b9  push    r14
0x1800229bb  push    r15
0x1800229bd  sub     rsp, 0F0h
0x1800229c4  lea     rbp, [rsp+30h]
0x1800229c9  mov     [rbp+0E0h+arg_10], rbx
0x1800229d0  mov     [rbp+0E0h+arg_18], rsi
0x1800229d7  mov     rax, cs:__security_cookie
0x1800229de  xor     rax, rbp
0x1800229e1  mov     [rbp+0E0h+var_30], rax
0x1800229e8  xor     r12d, r12d
0x1800229eb  lea     r8, [rbp+0E0h+var_D8]; int *
0x1800229ef  mov     [rdx], r12
0x1800229f2  mov     r15, rdx
0x1800229f5  movaps  xmm0, xmmword ptr cs:aDAGrRcAGrSAGrS; "D:(A;;GR;;;RC)(A;;GR;;;%s)(A;;GR;;;%s)"
0x1800229fc  mov     rsi, rcx
0x1800229ff  movaps  xmm1, xmmword ptr cs:aDAGrRcAGrSAGrS+10h; ";;;RC)(A;;GR;;;%s)(A;;GR;;;%s)"
0x180022a06  mov     edi, r12d
0x180022a09  mov     rcx, [rcx+48h]; void *
0x180022a0d  lea     edx, [r12+1Dh]; enum _TOKEN_INFORMATION_CLASS
0x180022a12  movaps  xmmword ptr [rbp+0E0h+var_80], xmm0
0x180022a16  mov     r14d, r12d
0x180022a19  movaps  xmm0, xmmword ptr cs:aDAGrRcAGrSAGrS+20h; ";;GR;;;%s)(A;;GR;;;%s)"
0x180022a20  movaps  [rbp+0E0h+var_70], xmm1
0x180022a24  movaps  xmm1, xmmword ptr cs:aDAGrRcAGrSAGrS+30h; "s)(A;;GR;;;%s)"
0x180022a2b  movaps  [rbp+0E0h+var_60], xmm0
0x180022a32  movups  xmm0, xmmword ptr cs:aDAGrRcAGrSAGrS+3Eh; "R;;;%s)"
0x180022a39  mov     [rbp+0E0h+StringSid], r12
0x180022a3d  movaps  xmmword ptr [rbp+0E0h+var_50], xmm1
0x180022a44  movups  xmm1, xmmword ptr cs:aDAGrRcAGrS; "D:(A;;GR;;;RC)(A;;GR;;;%s)"
0x180022a4b  mov     [rbp+0E0h+var_C8], r12
0x180022a4f  movups  xmmword ptr [rbp+0E0h+var_50+0Eh], xmm0
0x180022a56  mov     [rbp+0E0h+var_D8], r12d
0x180022a5a  movups  xmm0, xmmword ptr cs:aDAGrRcAGrS+10h; ";;;RC)(A;;GR;;;%s)"
0x180022a61  mov     [rbp+0E0h+Sid], r12
0x180022a65  movups  xmmword ptr [rbp+0E0h+var_C0], xmm1
0x180022a69  movups  xmm1, xmmword ptr cs:aDAGrRcAGrS+20h; ";;GR;;;%s)"
0x180022a70  movups  [rbp+0E0h+var_B0], xmm0
0x180022a74  movsd   xmm0, qword ptr cs:aDAGrRcAGrS+2Eh; "%s)"
0x180022a7c  movups  xmmword ptr [rbp+0E0h+var_A0], xmm1
0x180022a80  movsd   qword ptr [rbp+0E0h+var_A0+0Eh], xmm0
0x180022a85  call    ?IsTokenBoolPresent@@YAJPEAXW4_TOKEN_INFORMATION_CLASS@@PEAH@Z; IsTokenBoolPresent(void *,_TOKEN_INFORMATION_CLASS,int *)
0x180022a8a  mov     ebx, eax
0x180022a8c  test    eax, eax
0x180022a8e  js      loc_180022DE2
0x180022a94  lea     rcx, [rsi+9Ch]; Sid
0x180022a9b  lea     rdx, [rbp+0E0h+StringSid]; StringSid
0x180022a9f  call    cs:__imp_ConvertSidToStringSidW
0x180022aa5  test    eax, eax
0x180022aa7  jnz     short loc_180022B17
0x180022aa9  mov     eax, cs:dword_18014E4B8
0x180022aaf  test    eax, eax
0x180022ab1  jnz     short loc_180022AC7
0x180022ab3  cmp     cs:?gfEnableTracing@@3HA, r12d; int gfEnableTracing
0x180022aba  jz      short loc_180022AF9
0x180022abc  xor     ecx, ecx
0x180022abe  call    IsWppLevelEnabled
0x180022ac3  test    al, al
0x180022ac5  jz      short loc_180022AF9
0x180022ac7  call    cs:__imp_GetLastError
0x180022acd  mov     dword ptr [rsp+110h+var_E8], eax
0x180022ad1  xor     r9d, r9d
0x180022ad4  mov     r8d, 0B6Bh
0x180022ada  lea     rdx, aCtokenGetlowbo; "CToken::GetLowBoxSecurityDescriptor"
0x180022ae1  lea     rax, aWinerror; "%!WINERROR!"
0x180022ae8  lea     rcx, aOnecoreComComb_100; "onecore\\com\\combase\\rpcss\\objex\\to"...
0x180022aef  mov     [rsp+110h+var_F0], rax
0x180022af4  call    ??$ComTraceMessageT@H@@YAXPEBD0HW4TraceLevel@@PEBGH@Z; ComTraceMessageT<int>(char const *,char const *,int,TraceLevel,ushort const *,int)
0x180022af9  call    cs:__imp_GetLastError
0x180022aff  mov     ebx, eax
0x180022b01  test    eax, eax
0x180022b03  jle     loc_180022DE2
0x180022b09  movzx   ebx, ax
0x180022b0c  or      ebx, 80070000h
0x180022b12  jmp     loc_180022DE2
0x180022b17  cmp     [rbp+0E0h+var_D8], r12d
0x180022b1b  jz      loc_180022C7A
0x180022b21  mov     rcx, [rsi+48h]; TokenHandle
0x180022b25  lea     rdx, [rbp+0E0h+Sid]; void **
0x180022b29  call    ?GetPackageSidFromToken@@YAJPEAXPEAPEAX@Z; GetPackageSidFromToken(void *,void * *)
0x180022b2e  mov     r14, [rbp+0E0h+Sid]
0x180022b32  mov     ebx, eax
0x180022b34  test    eax, eax
0x180022b36  js      loc_180022DCB
0x180022b3c  lea     rdx, [rbp+0E0h+var_C8]; StringSid
0x180022b40  mov     rcx, r14; Sid
0x180022b43  call    cs:__imp_ConvertSidToStringSidW
0x180022b49  test    eax, eax
0x180022b4b  jnz     short loc_180022B84
0x180022b4d  mov     eax, cs:dword_18014E4B8
0x180022b53  test    eax, eax
0x180022b55  jnz     short loc_180022B73
0x180022b57  cmp     cs:?gfEnableTracing@@3HA, r12d; int gfEnableTracing
0x180022b5e  jz      loc_180022DB6
0x180022b64  xor     ecx, ecx
0x180022b66  call    IsWppLevelEnabled
0x180022b6b  test    al, al
0x180022b6d  jz      loc_180022DB6
0x180022b73  call    cs:__imp_GetLastError
0x180022b79  mov     r8d, 0B79h
0x180022b7f  jmp     loc_180022D90
0x180022b84  mov     rdx, [rbp+0E0h+StringSid]
0x180022b88  or      rax, 0FFFFFFFFFFFFFFFFh
0x180022b8c  mov     rcx, rax
0x180022b8f  inc     rcx
0x180022b92  cmp     [rdx+rcx*2], r12w
0x180022b97  jnz     short loc_180022B8F
0x180022b99  mov     rdx, [rbp+0E0h+var_C8]
0x180022b9d  inc     rax
0x180022ba0  cmp     [rdx+rax*2], r12w
0x180022ba5  jnz     short loc_180022B9D
0x180022ba7  add     eax, ecx
0x180022ba9  lea     esi, ds:4Eh[rax*2]
0x180022bb0  test    esi, esi
0x180022bb2  jz      short loc_180022C17
0x180022bb4  mov     ebx, esi
0x180022bb6  cmp     rbx, cs:g_ulMaxStackAllocSize
0x180022bbd  ja      short loc_180022C17
0x180022bbf  mov     rcx, cs:g_ulAdditionalProbeSize
0x180022bc6  add     rcx, 8
0x180022bca  add     rcx, rbx
0x180022bcd  cmp     rcx, rbx
0x180022bd0  jb      short loc_180022C17
0x180022bd2  call    VerifyStackAvailable
0x180022bd7  test    eax, eax
0x180022bd9  jz      short loc_180022C17
0x180022bdb  lea     rax, [rsi+8]
0x180022bdf  lea     rcx, [rax+0Fh]
0x180022be3  cmp     rcx, rax
0x180022be6  ja      short loc_180022BF2
0x180022be8  mov     rcx, 0FFFFFFFFFFFFFF0h
0x180022bf2  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180022bf6  mov     rax, rcx
0x180022bf9  call    _alloca_probe
0x180022bfe  sub     rsp, rcx
0x180022c01  lea     rdi, [rsp+110h+StringSid]
0x180022c06  test    rdi, rdi
0x180022c09  jz      short loc_180022C17
0x180022c0b  mov     dword ptr [rdi], 6B637453h
0x180022c11  add     rdi, 8
0x180022c15  jnz     short loc_180022C40
0x180022c17  mov     ebx, esi
0x180022c19  lea     rcx, [rsi+8]
0x180022c1d  cmp     rcx, rbx
0x180022c20  jb      short loc_180022C40
0x180022c22  mov     rax, cs:g_pfnAllocate
0x180022c29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022c2e  mov     rdi, rax
0x180022c31  test    rax, rax
0x180022c34  jz      short loc_180022C40
0x180022c36  mov     dword ptr [rax], 70616548h
0x180022c3c  add     rdi, 8
0x180022c40  test    rdi, rdi
0x180022c43  jnz     short loc_180022C4F
0x180022c45  mov     ebx, 8007000Eh
0x180022c4a  jmp     loc_180022DCB
0x180022c4f  mov     rax, [rbp+0E0h+var_C8]
0x180022c53  lea     r8, [rbp+0E0h+var_80]; unsigned __int16 *
0x180022c57  mov     r9, [rbp+0E0h+StringSid]
0x180022c5b  mov     rdx, rbx; unsigned __int64
0x180022c5e  mov     rcx, rdi; unsigned __int16 *
0x180022c61  mov     [rsp+110h+var_F0], rax
0x180022c66  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180022c6b  mov     ebx, eax
0x180022c6d  test    eax, eax
0x180022c6f  js      loc_180022DCB
0x180022c75  jmp     loc_180022D4F
0x180022c7a  mov     rcx, [rbp+0E0h+StringSid]
0x180022c7e  or      rax, 0FFFFFFFFFFFFFFFFh
0x180022c82  inc     rax
0x180022c85  cmp     [rcx+rax*2], r12w
0x180022c8a  jnz     short loc_180022C82
0x180022c8c  lea     esi, ds:36h[rax*2]
0x180022c93  test    esi, esi
0x180022c95  jz      short loc_180022CFA
0x180022c97  mov     ebx, esi
0x180022c99  cmp     rbx, cs:g_ulMaxStackAllocSize
0x180022ca0  ja      short loc_180022CFA
0x180022ca2  mov     rcx, cs:g_ulAdditionalProbeSize
0x180022ca9  add     rcx, 8
0x180022cad  add     rcx, rbx
0x180022cb0  cmp     rcx, rbx
0x180022cb3  jb      short loc_180022CFA
0x180022cb5  call    VerifyStackAvailable
0x180022cba  test    eax, eax
0x180022cbc  jz      short loc_180022CFA
0x180022cbe  lea     rax, [rsi+8]
0x180022cc2  lea     rcx, [rax+0Fh]
0x180022cc6  cmp     rcx, rax
0x180022cc9  ja      short loc_180022CD5
0x180022ccb  mov     rcx, 0FFFFFFFFFFFFFF0h
0x180022cd5  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180022cd9  mov     rax, rcx
0x180022cdc  call    _alloca_probe
0x180022ce1  sub     rsp, rcx
0x180022ce4  lea     rdi, [rsp+110h+StringSid]
0x180022ce9  test    rdi, rdi
0x180022cec  jz      short loc_180022CFA
0x180022cee  mov     dword ptr [rdi], 6B637453h
0x180022cf4  add     rdi, 8
0x180022cf8  jnz     short loc_180022D23
0x180022cfa  mov     ebx, esi
0x180022cfc  lea     rcx, [rsi+8]
0x180022d00  cmp     rcx, rbx
0x180022d03  jb      short loc_180022D23
0x180022d05  mov     rax, cs:g_pfnAllocate
0x180022d0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022d11  mov     rdi, rax
0x180022d14  test    rax, rax
0x180022d17  jz      short loc_180022D23
0x180022d19  mov     dword ptr [rax], 70616548h
0x180022d1f  add     rdi, 8
0x180022d23  test    rdi, rdi
0x180022d26  jnz     short loc_180022D32
0x180022d28  mov     ebx, 8007000Eh
0x180022d2d  jmp     loc_180022DE2
0x180022d32  mov     r9, [rbp+0E0h+StringSid]
0x180022d36  lea     r8, [rbp+0E0h+var_C0]; unsigned __int16 *
0x180022d3a  mov     rdx, rbx; unsigned __int64
0x180022d3d  mov     rcx, rdi; unsigned __int16 *
0x180022d40  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180022d45  mov     ebx, eax
0x180022d47  test    eax, eax
0x180022d49  js      loc_180022DE2
0x180022d4f  xor     r9d, r9d; SecurityDescriptorSize
0x180022d52  mov     r8, r15; SecurityDescriptor
0x180022d55  mov     rcx, rdi; StringSecurityDescriptor
0x180022d58  lea     edx, [r9+1]; StringSDRevision
0x180022d5c  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180022d62  test    eax, eax
0x180022d64  jnz     short loc_180022DCB
0x180022d66  mov     eax, cs:dword_18014E4B8
0x180022d6c  test    eax, eax
0x180022d6e  jnz     short loc_180022D84
0x180022d70  cmp     cs:?gfEnableTracing@@3HA, r12d; int gfEnableTracing
0x180022d77  jz      short loc_180022DB6
0x180022d79  xor     ecx, ecx
0x180022d7b  call    IsWppLevelEnabled
0x180022d80  test    al, al
0x180022d82  jz      short loc_180022DB6
0x180022d84  call    cs:__imp_GetLastError
0x180022d8a  mov     r8d, 0BB9h
0x180022d90  mov     dword ptr [rsp+110h+var_E8], eax
0x180022d94  lea     rdx, aCtokenGetlowbo; "CToken::GetLowBoxSecurityDescriptor"
0x180022d9b  lea     rax, aWinerror; "%!WINERROR!"
0x180022da2  xor     r9d, r9d
0x180022da5  lea     rcx, aOnecoreComComb_100; "onecore\\com\\combase\\rpcss\\objex\\to"...
0x180022dac  mov     [rsp+110h+var_F0], rax
0x180022db1  call    ??$ComTraceMessageT@H@@YAXPEBD0HW4TraceLevel@@PEBGH@Z; ComTraceMessageT<int>(char const *,char const *,int,TraceLevel,ushort const *,int)
0x180022db6  call    cs:__imp_GetLastError
0x180022dbc  mov     ebx, eax
0x180022dbe  test    eax, eax
0x180022dc0  jle     short loc_180022DCB
0x180022dc2  movzx   ebx, ax
0x180022dc5  or      ebx, 80070000h
0x180022dcb  test    r14, r14
0x180022dce  jz      short loc_180022DE2
0x180022dd0  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x180022dd7  mov     r8, r14; lpMem
0x180022dda  xor     edx, edx; dwFlags
0x180022ddc  call    cs:__imp_HeapFree
0x180022de2  mov     rcx, [rbp+0E0h+StringSid]; hMem
0x180022de6  test    rcx, rcx
0x180022de9  jz      short loc_180022DF1
0x180022deb  call    cs:__imp_LocalFree
0x180022df1  mov     rcx, [rbp+0E0h+var_C8]; hMem
0x180022df5  test    rcx, rcx
0x180022df8  jz      short loc_180022E00
0x180022dfa  call    cs:__imp_LocalFree
0x180022e00  test    rdi, rdi
0x180022e03  jz      short loc_180022E1D
0x180022e05  lea     rcx, [rdi-8]
0x180022e09  cmp     dword ptr [rcx], 70616548h
0x180022e0f  jnz     short loc_180022E1D
0x180022e11  mov     rax, cs:g_pfnFree
0x180022e18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022e1d  mov     eax, ebx
0x180022e1f  mov     rcx, [rbp+0E0h+var_30]
0x180022e26  xor     rcx, rbp; StackCookie
0x180022e29  call    __security_check_cookie
0x180022e2e  mov     rbx, [rbp+0E0h+arg_10]
0x180022e35  mov     rsi, [rbp+0E0h+arg_18]
0x180022e3c  lea     rsp, [rbp+0C0h]
0x180022e43  pop     r15
0x180022e45  pop     r14
0x180022e47  pop     r12
0x180022e49  pop     rdi
0x180022e4a  pop     rbp
0x180022e4b  retn
```
