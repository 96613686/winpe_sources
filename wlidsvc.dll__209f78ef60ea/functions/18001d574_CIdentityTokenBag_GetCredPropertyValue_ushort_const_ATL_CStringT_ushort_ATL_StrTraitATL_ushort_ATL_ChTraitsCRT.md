# CIdentityTokenBag::GetCredPropertyValue(ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)

- ea: `0x18001d574`
- end: `0x18001daf1`
- name: `?GetCredPropertyValue@CIdentityTokenBag@@QEAAJPEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z`
- size: `1405`
- prototype: ``
- caller_count: `6`
- callee_count: `12`
- tags: `loader_planting`

## callers

- `0x18000f2a0`
- `0x180047b40`
- `0x1800855a4`
- `0x1800a2574`
- `0x180108d34`
- `0x1801094f8`

## callees

- `0x180014680`
- `0x18001a9c0`
- `0x18001b760`
- `0x18001d050`
- `0x18001d574`
- `0x18007c408`
- `0x180089bc0`
- `0x1800a3b60`
- `0x1800a46be`
- `0x1800a8798`
- `0x180116c40`
- `0x180128010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001da17`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001da17`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18001d601`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18001d7a8`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18001d804`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18001d860`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18001d8bc`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18001d918`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18001d974`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18001d601`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18001d7a8`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18001d804`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18001d860`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18001d8bc`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18001d918`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18001d974`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d723`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d723`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001d68e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001d68e`

## string_xrefs

- `0x18001d5b4`: `CIdentityTokenBag::GetCredPropertyValue`
- `0x18001d5f7`: `onecoreuap\ds\ext\Live\identity\Include\tokenbag.h`
- `0x18001d79e`: `onecoreuap\ds\ext\Live\identity\Include\tokenbag.h`
- `0x18001d7fa`: `onecoreuap\ds\ext\Live\identity\Include\tokenbag.h`
- `0x18001d856`: `onecoreuap\ds\ext\Live\identity\Include\tokenbag.h`
- `0x18001d8b2`: `onecoreuap\ds\ext\Live\identity\Include\tokenbag.h`
- `0x18001d90e`: `onecoreuap\ds\ext\Live\identity\Include\tokenbag.h`
- `0x18001d96a`: `onecoreuap\ds\ext\Live\identity\Include\tokenbag.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CIdentityTokenBag::GetCredPropertyValue(__int64 a1, void *a2, __int64 a3)
{
  const char *v5; // rbx
  char *v6; // rax
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // rax
  int v10; // eax
  __int64 *v11; // rdx
  __int64 (__fastcall **v12)(__int64, void **, __int64); // r13
  unsigned int *v13; // rax
  _QWORD *v14; // rdx
  unsigned int v15; // ebx
  char *v17; // rax
  __int64 v18; // rax
  char *v19; // rax
  __int64 v20; // rax
  char *v21; // rax
  __int64 v22; // rax
  char *v23; // rax
  __int64 v24; // rax
  char *v25; // rax
  __int64 v26; // rax
  char *v27; // rax
  __int64 v28; // rax
  __int64 v29; // rbx
  unsigned __int64 v30; // r14
  unsigned __int64 v31; // rsi
  __int64 v32; // rdi
  void *Destination; // [rsp+30h] [rbp-89h] BYREF
  unsigned int v34; // [rsp+38h] [rbp-81h] BYREF
  void *Src; // [rsp+40h] [rbp-79h]
  __int64 v36; // [rsp+48h] [rbp-71h]
  _QWORD v37[5]; // [rsp+50h] [rbp-69h] BYREF
  char v38; // [rsp+78h] [rbp-41h]
  _BYTE v39[16]; // [rsp+80h] [rbp-39h] BYREF
  const char *v40; // [rsp+90h] [rbp-29h]
  int v41; // [rsp+98h] [rbp-21h]
  int v42; // [rsp+9Ch] [rbp-1Dh]
  const char *v43; // [rsp+A0h] [rbp-19h]
  __int64 v44; // [rsp+A8h] [rbp-11h]
  void **p_Destination; // [rsp+B0h] [rbp-9h]
  __int64 v46; // [rsp+B8h] [rbp-1h]
  const wchar_t *v47; // [rsp+C0h] [rbp+7h]
  __int64 v48; // [rsp+C8h] [rbp+Fh]

  v36 = a3;
  Src = a2;
  v34 = 0;
  v37[0] = "CIdentityTokenBag::GetCredPropertyValue";
  v37[1] = &v34;
  v37[2] = 0;
  v37[3] = 0;
  switch ( dword_1801C3ABC )
  {
    case 4:
      if ( (byte_1801C36C4 & 4) == 0 )
        break;
      v5 = "onecoreuap\\ds\\ext\\Live\\identity\\Include\\tokenbag.h";
      v6 = strrchr("onecoreuap\\ds\\ext\\Live\\identity\\Include\\tokenbag.h", 92);
      if ( v6 )
        v5 = v6 + 1;
      LODWORD(Destination) = 129;
      if ( v5 )
      {
        v9 = -1;
        do
          ++v9;
        while ( v5[v9] );
        v10 = v9 + 1;
      }
      else
      {
        v5 = "NULL";
        v10 = 5;
      }
      v11 = WlidSvc_TraceFunction_Enter;
      goto LABEL_10;
    case 5:
      if ( byte_1801C36C5 < 0 )
      {
        v5 = "onecoreuap\\ds\\ext\\Live\\identity\\Include\\tokenbag.h";
        v27 = strrchr("onecoreuap\\ds\\ext\\Live\\identity\\Include\\tokenbag.h", 92);
        if ( v27 )
          v5 = v27 + 1;
        LODWORD(Destination) = 129;
        if ( v5 )
        {
          v28 = -1;
          do
            ++v28;
          while ( v5[v28] );
          v10 = v28 + 1;
        }
        else
        {
          v5 = "NULL";
          v10 = 5;
        }
        v11 = WlidModern_TraceFunction_Enter;
        goto LABEL_10;
      }
      break;
    case 6:
      if ( (byte_1801C36C7 & 8) != 0 )
      {
        v5 = "onecoreuap\\ds\\ext\\Live\\identity\\Include\\tokenbag.h";
        v25 = strrchr("onecoreuap\\ds\\ext\\Live\\identity\\Include\\tokenbag.h", 92);
        if ( v25 )
          v5 = v25 + 1;
        LODWORD(Destination) = 129;
        if ( v5 )
        {
          v26 = -1;
          do
            ++v26;
          while ( v5[v26] );
          v10 = v26 + 1;
        }
        else
        {
          v5 = "NULL";
          v10 = 5;
        }
        v11 = WlidCli_TraceFunction_Enter;
        goto LABEL_10;
      }
      break;
    case 7:
      if ( (byte_1801C36C8 & 8) != 0 )
      {
        v5 = "onecoreuap\\ds\\ext\\Live\\identity\\Include\\tokenbag.h";
        v23 = strrchr("onecoreuap\\ds\\ext\\Live\\identity\\Include\\tokenbag.h", 92);
        if ( v23 )
          v5 = v23 + 1;
        LODWORD(Destination) = 129;
        if ( v5 )
        {
          v24 = -1;
          do
            ++v24;
          while ( v5[v24] );
          v10 = v24 + 1;
        }
        else
        {
          v5 = "NULL";
          v10 = 5;
        }
        v11 = WlidProv_TraceFunction_Enter;
        goto LABEL_10;
      }
      break;
    case 8:
      if ( (byte_1801C36C9 & 0x10) != 0 )
      {
        v5 = "onecoreuap\\ds\\ext\\Live\\identity\\Include\\tokenbag.h";
        v21 = strrchr("onecoreuap\\ds\\ext\\Live\\identity\\Include\\tokenbag.h", 92);
        if ( v21 )
          v5 = v21 + 1;
        LODWORD(Destination) = 129;
        if ( v5 )
        {
          v22 = -1;
          do
            ++v22;
          while ( v5[v22] );
          v10 = v22 + 1;
        }
        else
        {
          v5 = "NULL";
          v10 = 5;
        }
        v11 = WlidBho_TraceFunction_Enter;
        goto LABEL_10;
      }
      break;
    case 9:
      if ( (byte_1801C36CA & 0x10) != 0 )
      {
        v5 = "onecoreuap\\ds\\ext\\Live\\identity\\Include\\tokenbag.h";
        v19 = strrchr("onecoreuap\\ds\\ext\\Live\\identity\\Include\\tokenbag.h", 92);
        if ( v19 )
          v5 = v19 + 1;
        LODWORD(Destination) = 129;
        if ( v5 )
        {
          v20 = -1;
          do
            ++v20;
          while ( v5[v20] );
          v10 = v20 + 1;
        }
        else
        {
          v5 = "NULL";
          v10 = 5;
        }
        v11 = TokenProvider_TraceFunction_Enter;
        goto LABEL_10;
      }
      break;
    default:
      if ( dword_1801C3ABC == 10 && (byte_1801C36CB & 0x10) != 0 )
      {
        v5 = "onecoreuap\\ds\\ext\\Live\\identity\\Include\\tokenbag.h";
        v17 = strrchr("onecoreuap\\ds\\ext\\Live\\identity\\Include\\tokenbag.h", 92);
        if ( v17 )
          v5 = v17 + 1;
        LODWORD(Destination) = 129;
        if ( v5 )
        {
          v18 = -1;
          do
            ++v18;
          while ( v5[v18] );
          v10 = v18 + 1;
        }
        else
        {
          v5 = "NULL";
          v10 = 5;
        }
        v11 = Extension_TraceFunction_Enter;
LABEL_10:
        v41 = v10;
        p_Destination = &Destination;
        v47 = L"NULL";
        v40 = v5;
        v42 = 0;
        v43 = "CIdentityTokenBag::GetCredPropertyValue";
        v44 = 40;
        v46 = 4;
        v48 = 10;
        McGenEventWrite_EventWriteTransfer(v7, v11, v8, 5, v39);
      }
      break;
  }
  v37[4] = a1 + 16;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
  v38 = 1;
  v12 = *(__int64 (__fastcall ***)(__int64, void **, __int64))(a1 + 128);
  v13 = (unsigned int *)((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr);
  Destination = v13 + 6;
  if ( !a2 )
  {
LABEL_12:
    ATL::CSimpleStringT<unsigned short,0>::Empty(&Destination);
    goto LABEL_13;
  }
  if ( (unsigned __int64)a2 < 0x10000 )
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::LoadStringW(
      &Destination,
      (unsigned __int16)a2);
  }
  else
  {
    v29 = -1;
    do
      ++v29;
    while ( *((_WORD *)a2 + v29) );
    if ( !(_DWORD)v29 )
      goto LABEL_12;
    v30 = v13[2];
    v31 = ((_BYTE *)a2 - (_BYTE *)(v13 + 6)) >> 1;
    if ( (int)((v13[3] - v29) | (1 - v13[4])) < 0 )
      ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(&Destination, (unsigned int)v29);
    v32 = 2LL * (int)v29;
    if ( v31 <= v30 )
    {
      memmove_s_0(Destination, 2LL * (int)v29, (char *)Destination + 2 * v31, 2LL * (int)v29);
    }
    else if ( v32 )
    {
      if ( Destination )
      {
        memcpy_0(Destination, Src, 2LL * (int)v29);
      }
      else
      {
        *(_DWORD *)_o__errno() = 22;
        invalid_parameter_noinfo();
      }
    }
    if ( (int)v29 < 0 || (int)v29 > *((_DWORD *)Destination - 3) )
      ATL::AtlThrowImpl(-2147024809);
    *((_DWORD *)Destination - 4) = v29;
    *(_WORD *)((char *)Destination + v32) = 0;
  }
LABEL_13:
  v34 = (*v12)(a1 + 128, &Destination, v36);
  v14 = (char *)Destination - 24;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)Destination - 2, 0xFFFFFFFF) <= 1 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v14 + 8LL))(*v14);
  v15 = v34;
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v37);
  return v15;
}

```

## disassembly

```asm
0x18001d574  mov     [rsp-8+arg_18], rbx
0x18001d579  push    rbp
0x18001d57a  push    rsi
0x18001d57b  push    rdi
0x18001d57c  push    r12
0x18001d57e  push    r13
0x18001d580  push    r14
0x18001d582  push    r15
0x18001d584  lea     rbp, [rsp-27h]
0x18001d589  sub     rsp, 0E0h
0x18001d590  mov     rax, cs:__security_cookie
0x18001d597  xor     rax, rsp
0x18001d59a  mov     [rbp+57h+var_40], rax
0x18001d59e  mov     [rbp+57h+var_C8], r8
0x18001d5a2  mov     rsi, rdx
0x18001d5a5  mov     [rbp+57h+Src], rdx
0x18001d5a9  mov     r12, rcx
0x18001d5ac  xor     r14d, r14d
0x18001d5af  mov     [rsp+110h+var_D8], r14d
0x18001d5b4  lea     r13, aCidentitytoken_14; "CIdentityTokenBag::GetCredPropertyValue"
0x18001d5bb  mov     [rbp+57h+var_C0], r13
0x18001d5bf  lea     rax, [rsp+110h+var_D8]
0x18001d5c4  mov     [rbp+57h+var_B8], rax
0x18001d5c8  mov     [rbp+57h+var_B0], r14
0x18001d5cc  mov     [rbp+57h+var_A8], r14
0x18001d5d0  mov     ecx, cs:dword_1801C3ABC
0x18001d5d6  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18001d5da  lea     r15d, [r14+4]
0x18001d5de  sub     ecx, r15d
0x18001d5e1  jnz     loc_18001D75C
0x18001d5e7  test    cs:byte_1801C36C4, r15b
0x18001d5ee  jz      loc_18001D682
0x18001d5f4  lea     edx, [rdi+5Dh]; Ch
0x18001d5f7  lea     rbx, aOnecoreuapDsEx_91; "onecoreuap\\ds\\ext\\Live\\identity\\In"...
0x18001d5fe  mov     rcx, rbx; Str
0x18001d601  call    cs:__imp_strrchr
0x18001d607  test    rax, rax
0x18001d60a  jz      short loc_18001D610
0x18001d60c  lea     rbx, [rax+1]
0x18001d610  mov     dword ptr [rsp+110h+Destination], 81h
0x18001d618  mov     r9d, 5
0x18001d61e  test    rbx, rbx
0x18001d621  jz      loc_18001DACF
0x18001d627  mov     rax, rdi
0x18001d62a  inc     rax
0x18001d62d  cmp     [rbx+rax], r14b
0x18001d631  jnz     short loc_18001D62A
0x18001d633  inc     eax
0x18001d635  lea     rdx, WlidSvc_TraceFunction_Enter
0x18001d63c  mov     [rbp+57h+var_78], eax
0x18001d63f  lea     rax, [rsp+110h+Destination]
0x18001d644  mov     [rbp+57h+var_60], rax
0x18001d648  lea     rax, aNull_2; "NULL"
0x18001d64f  mov     [rbp+57h+var_50], rax
0x18001d653  lea     rax, [rbp+57h+var_90]
0x18001d657  mov     [rsp+110h+var_F0], rax
0x18001d65c  mov     [rbp+57h+var_80], rbx
0x18001d660  mov     [rbp+57h+var_74], r14d
0x18001d664  mov     [rbp+57h+var_70], r13
0x18001d668  mov     [rbp+57h+var_68], 28h ; '('
0x18001d670  mov     [rbp+57h+var_58], r15
0x18001d674  mov     [rbp+57h+var_48], 0Ah
0x18001d67c  call    McGenEventWrite_EventWriteTransfer
0x18001d681  nop
0x18001d682  lea     r15, [r12+10h]
0x18001d687  mov     [rbp+57h+var_A0], r15
0x18001d68b  mov     rcx, r15; lpCriticalSection
0x18001d68e  call    cs:__imp_EnterCriticalSection
0x18001d694  mov     edi, 1
0x18001d699  mov     [rbp+57h+var_98], dil
0x18001d69d  mov     r13, [r12+80h]
0x18001d6a5  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18001d6ac  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18001d6b3  mov     rax, [rax+18h]
0x18001d6b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d6bc  lea     rcx, [rax+18h]
0x18001d6c0  mov     [rsp+110h+Destination], rcx
0x18001d6c5  test    rsi, rsi
0x18001d6c8  jnz     loc_18001D9B4
0x18001d6ce  lea     rcx, [rsp+110h+Destination]
0x18001d6d3  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x18001d6d8  nop
0x18001d6d9  mov     r8, [rbp+57h+var_C8]
0x18001d6dd  lea     rdx, [rsp+110h+Destination]
0x18001d6e2  lea     rcx, [r12+80h]
0x18001d6ea  mov     rax, [r13+0]
0x18001d6ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d6f3  mov     [rsp+110h+var_D8], eax
0x18001d6f7  mov     rdx, [rsp+110h+Destination]
0x18001d6fc  add     rdx, 0FFFFFFFFFFFFFFE8h
0x18001d700  or      eax, 0FFFFFFFFh
0x18001d703  lock xadd [rdx+10h], eax
0x18001d708  sub     eax, 1
0x18001d70b  jg      short loc_18001D71C
0x18001d70d  mov     rcx, [rdx]
0x18001d710  mov     rax, [rcx]
0x18001d713  mov     rax, [rax+8]
0x18001d717  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d71c  mov     ebx, [rsp+110h+var_D8]
0x18001d720  mov     rcx, r15; lpCriticalSection
0x18001d723  call    cs:__imp_LeaveCriticalSection
0x18001d729  nop
0x18001d72a  lea     rcx, [rbp+57h+var_C0]
0x18001d72e  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x18001d733  mov     eax, ebx
0x18001d735  mov     rcx, [rbp+57h+var_40]
0x18001d739  xor     rcx, rsp; StackCookie
0x18001d73c  call    __security_check_cookie
0x18001d741  mov     rbx, [rsp+110h+arg_18]
0x18001d749  add     rsp, 0E0h
0x18001d750  pop     r15
0x18001d752  pop     r14
0x18001d754  pop     r13
0x18001d756  pop     r12
0x18001d758  pop     rdi
0x18001d759  pop     rsi
0x18001d75a  pop     rbp
0x18001d75b  retn
0x18001d75c  sub     ecx, 1
0x18001d75f  jz      loc_18001D958
0x18001d765  sub     ecx, 1
0x18001d768  jz      loc_18001D8FC
0x18001d76e  sub     ecx, 1
0x18001d771  jz      loc_18001D8A0
0x18001d777  sub     ecx, 1
0x18001d77a  jz      loc_18001D844
0x18001d780  sub     ecx, 1
0x18001d783  jz      short loc_18001D7E8
0x18001d785  cmp     ecx, 1
0x18001d788  jnz     loc_18001D682
0x18001d78e  test    cs:byte_1801C36CB, 10h
0x18001d795  jz      loc_18001D682
0x18001d79b  lea     edx, [rcx+5Bh]; Ch
0x18001d79e  lea     rbx, aOnecoreuapDsEx_91; "onecoreuap\\ds\\ext\\Live\\identity\\In"...
0x18001d7a5  mov     rcx, rbx; Str
0x18001d7a8  call    cs:__imp_strrchr
0x18001d7ae  test    rax, rax
0x18001d7b1  jz      short loc_18001D7B7
0x18001d7b3  lea     rbx, [rax+1]
0x18001d7b7  mov     dword ptr [rsp+110h+Destination], 81h
0x18001d7bf  mov     r9d, 5
0x18001d7c5  test    rbx, rbx
0x18001d7c8  jz      loc_18001DA75
0x18001d7ce  mov     rax, rdi
0x18001d7d1  inc     rax
0x18001d7d4  cmp     [rbx+rax], r14b
0x18001d7d8  jnz     short loc_18001D7D1
0x18001d7da  inc     eax
0x18001d7dc  lea     rdx, Extension_TraceFunction_Enter
0x18001d7e3  jmp     loc_18001D63C
0x18001d7e8  test    cs:byte_1801C36CA, 10h
0x18001d7ef  jz      loc_18001D682
0x18001d7f5  mov     edx, 5Ch ; '\'; Ch
0x18001d7fa  lea     rbx, aOnecoreuapDsEx_91; "onecoreuap\\ds\\ext\\Live\\identity\\In"...
0x18001d801  mov     rcx, rbx; Str
0x18001d804  call    cs:__imp_strrchr
0x18001d80a  test    rax, rax
0x18001d80d  jz      short loc_18001D813
0x18001d80f  lea     rbx, [rax+1]
0x18001d813  mov     dword ptr [rsp+110h+Destination], 81h
0x18001d81b  mov     r9d, 5
0x18001d821  test    rbx, rbx
0x18001d824  jz      loc_18001DA84
0x18001d82a  mov     rax, rdi
0x18001d82d  inc     rax
0x18001d830  cmp     [rbx+rax], r14b
0x18001d834  jnz     short loc_18001D82D
0x18001d836  inc     eax
0x18001d838  lea     rdx, TokenProvider_TraceFunction_Enter
0x18001d83f  jmp     loc_18001D63C
0x18001d844  test    cs:byte_1801C36C9, 10h
0x18001d84b  jz      loc_18001D682
0x18001d851  mov     edx, 5Ch ; '\'; Ch
0x18001d856  lea     rbx, aOnecoreuapDsEx_91; "onecoreuap\\ds\\ext\\Live\\identity\\In"...
0x18001d85d  mov     rcx, rbx; Str
0x18001d860  call    cs:__imp_strrchr
0x18001d866  test    rax, rax
0x18001d869  jz      short loc_18001D86F
0x18001d86b  lea     rbx, [rax+1]
0x18001d86f  mov     dword ptr [rsp+110h+Destination], 81h
0x18001d877  mov     r9d, 5
0x18001d87d  test    rbx, rbx
0x18001d880  jz      loc_18001DA93
0x18001d886  mov     rax, rdi
0x18001d889  inc     rax
0x18001d88c  cmp     [rbx+rax], r14b
0x18001d890  jnz     short loc_18001D889
0x18001d892  inc     eax
0x18001d894  lea     rdx, WlidBho_TraceFunction_Enter
0x18001d89b  jmp     loc_18001D63C
0x18001d8a0  test    cs:byte_1801C36C8, 8
0x18001d8a7  jz      loc_18001D682
0x18001d8ad  mov     edx, 5Ch ; '\'; Ch
0x18001d8b2  lea     rbx, aOnecoreuapDsEx_91; "onecoreuap\\ds\\ext\\Live\\identity\\In"...
0x18001d8b9  mov     rcx, rbx; Str
0x18001d8bc  call    cs:__imp_strrchr
0x18001d8c2  test    rax, rax
0x18001d8c5  jz      short loc_18001D8CB
0x18001d8c7  lea     rbx, [rax+1]
0x18001d8cb  mov     dword ptr [rsp+110h+Destination], 81h
0x18001d8d3  mov     r9d, 5
0x18001d8d9  test    rbx, rbx
0x18001d8dc  jz      loc_18001DAA2
0x18001d8e2  mov     rax, rdi
0x18001d8e5  inc     rax
0x18001d8e8  cmp     [rbx+rax], r14b
0x18001d8ec  jnz     short loc_18001D8E5
0x18001d8ee  inc     eax
0x18001d8f0  lea     rdx, WlidProv_TraceFunction_Enter
0x18001d8f7  jmp     loc_18001D63C
0x18001d8fc  test    cs:byte_1801C36C7, 8
0x18001d903  jz      loc_18001D682
0x18001d909  mov     edx, 5Ch ; '\'; Ch
0x18001d90e  lea     rbx, aOnecoreuapDsEx_91; "onecoreuap\\ds\\ext\\Live\\identity\\In"...
0x18001d915  mov     rcx, rbx; Str
0x18001d918  call    cs:__imp_strrchr
0x18001d91e  test    rax, rax
0x18001d921  jz      short loc_18001D927
0x18001d923  lea     rbx, [rax+1]
0x18001d927  mov     dword ptr [rsp+110h+Destination], 81h
0x18001d92f  mov     r9d, 5
0x18001d935  test    rbx, rbx
0x18001d938  jz      loc_18001DAB1
0x18001d93e  mov     rax, rdi
0x18001d941  inc     rax
0x18001d944  cmp     [rbx+rax], r14b
0x18001d948  jnz     short loc_18001D941
0x18001d94a  inc     eax
0x18001d94c  lea     rdx, WlidCli_TraceFunction_Enter
0x18001d953  jmp     loc_18001D63C
0x18001d958  cmp     cs:byte_1801C36C5, r14b
0x18001d95f  jge     loc_18001D682
0x18001d965  mov     edx, 5Ch ; '\'; Ch
0x18001d96a  lea     rbx, aOnecoreuapDsEx_91; "onecoreuap\\ds\\ext\\Live\\identity\\In"...
0x18001d971  mov     rcx, rbx; Str
0x18001d974  call    cs:__imp_strrchr
0x18001d97a  test    rax, rax
0x18001d97d  jz      short loc_18001D983
0x18001d97f  lea     rbx, [rax+1]
0x18001d983  mov     dword ptr [rsp+110h+Destination], 81h
0x18001d98b  mov     r9d, 5
0x18001d991  test    rbx, rbx
0x18001d994  jz      loc_18001DAC0
0x18001d99a  mov     rax, rdi
0x18001d99d  inc     rax
0x18001d9a0  cmp     [rbx+rax], r14b
0x18001d9a4  jnz     short loc_18001D99D
0x18001d9a6  inc     eax
0x18001d9a8  lea     rdx, WlidModern_TraceFunction_Enter
0x18001d9af  jmp     loc_18001D63C
0x18001d9b4  cmp     rsi, 10000h
0x18001d9bb  jb      loc_18001DADE
0x18001d9c1  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001d9c5  inc     rbx
0x18001d9c8  cmp     [rsi+rbx*2], r14w
0x18001d9cd  jnz     short loc_18001D9C5
0x18001d9cf  test    ebx, ebx
0x18001d9d1  jz      loc_18001D6CE
0x18001d9d7  mov     r14d, [rcx-10h]
0x18001d9db  sub     rsi, rcx
0x18001d9de  sar     rsi, 1
0x18001d9e1  sub     edi, [rax+10h]
0x18001d9e4  mov     eax, [rax+0Ch]
0x18001d9e7  sub     eax, ebx
0x18001d9e9  or      edi, eax
0x18001d9eb  jge     short loc_18001D9F9
0x18001d9ed  mov     edx, ebx
0x18001d9ef  lea     rcx, [rsp+110h+Destination]
0x18001d9f4  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x18001d9f9  mov     rcx, [rsp+110h+Destination]; void *
0x18001d9fe  movsxd  rax, ebx
0x18001da01  lea     rdi, [rax+rax]
0x18001da05  cmp     rsi, r14
0x18001da08  jbe     short loc_18001DA56
0x18001da0a  xor     r14d, r14d
0x18001da0d  test    rdi, rdi
0x18001da10  jz      short loc_18001DA28
0x18001da12  test    rcx, rcx
0x18001da15  jnz     short loc_18001DA48
0x18001da17  call    cs:__imp__o__errno
0x18001da1d  mov     dword ptr [rax], 16h
0x18001da23  call    _invalid_parameter_noinfo
0x18001da28  test    ebx, ebx
0x18001da2a  js      short loc_18001DA6A
0x18001da2c  mov     rax, [rsp+110h+Destination]
0x18001da31  cmp     ebx, [rax-0Ch]
0x18001da34  jg      short loc_18001DA6A
0x18001da36  mov     [rax-10h], ebx
0x18001da39  mov     rax, [rsp+110h+Destination]
0x18001da3e  mov     [rdi+rax], r14w
0x18001da43  jmp     loc_18001D6D9
0x18001da48  mov     r8, rdi; Size
0x18001da4b  mov     rdx, [rbp+57h+Src]; Src
0x18001da4f  call    memcpy_0
0x18001da54  jmp     short loc_18001DA28
0x18001da56  lea     r8, [rcx+rsi*2]; Source
0x18001da5a  mov     r9, rdi; SourceSize
0x18001da5d  mov     rdx, rdi; DestinationSize
0x18001da60  call    memmove_s_0
0x18001da65  xor     r14d, r14d
  ... truncated ...
```
