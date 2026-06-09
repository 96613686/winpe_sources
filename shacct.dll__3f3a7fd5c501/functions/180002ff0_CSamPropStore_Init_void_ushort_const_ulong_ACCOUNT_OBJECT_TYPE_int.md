# CSamPropStore::_Init(void *,ushort const *,ulong,_ACCOUNT_OBJECT_TYPE,int)

- ea: `0x180002ff0`
- end: `0x180003656`
- name: `?_Init@CSamPropStore@@QEAAJPEAXPEBGKW4_ACCOUNT_OBJECT_TYPE@@H@Z`
- size: `1638`
- prototype: `int __high(void *, const unsigned __int16 *, unsigned int, enum _ACCOUNT_OBJECT_TYPE, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180001940`
- `0x180002bf0`

## callees

- `0x1800020d0`
- `0x180002ff0`
- `0x1800037e0`
- `0x180008c10`
- `0x18000cb84`
- `0x1800123c0`
- `0x180012f18`
- `0x180013534`

## import_xrefs

- `SHCORE!SHStrDupW` at `0x180003411`
- `SHCORE!SHStrDupW` at `0x1800035ce`
- `SHCORE!SHStrDupW` at `0x180003411`
- `SHCORE!SHStrDupW` at `0x1800035ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003065`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003065`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180003049`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180003049`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180003024`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180003024`
- `ntdll!RtlInitUnicodeString` at `0x18000342c`
- `ntdll!RtlInitUnicodeString` at `0x18000349e`
- `ntdll!RtlInitUnicodeString` at `0x1800035e2`
- `ntdll!RtlInitUnicodeString` at `0x18000342c`
- `ntdll!RtlInitUnicodeString` at `0x18000349e`
- `ntdll!RtlInitUnicodeString` at `0x1800035e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003057`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800031eb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800032fa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800034d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800035f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003057`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800031eb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800032fa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800034d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800035f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000302e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000326e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800033af`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800033d6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003577`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000359f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000302e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000326e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800033af`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800033d6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003577`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000359f`
- `SAMLIB!SamOpenDomain` at `0x180003156`
- `SAMLIB!SamOpenDomain` at `0x180003156`
- `SAMLIB!SamConnect` at `0x180003132`
- `SAMLIB!SamConnect` at `0x180003132`
- `SAMLIB!SamCloseHandle` at `0x18000317b`
- `SAMLIB!SamCloseHandle` at `0x18000332d`
- `SAMLIB!SamCloseHandle` at `0x180003336`
- `SAMLIB!SamCloseHandle` at `0x180003479`
- `SAMLIB!SamCloseHandle` at `0x180003482`
- `SAMLIB!SamCloseHandle` at `0x18000317b`
- `SAMLIB!SamCloseHandle` at `0x18000332d`
- `SAMLIB!SamCloseHandle` at `0x180003336`
- `SAMLIB!SamCloseHandle` at `0x180003479`
- `SAMLIB!SamCloseHandle` at `0x180003482`
- `SAMLIB!SamLookupIdsInDomain` at `0x18000322e`
- `SAMLIB!SamLookupIdsInDomain` at `0x18000322e`
- `SAMLIB!SamFreeMemory` at `0x180003304`
- `SAMLIB!SamFreeMemory` at `0x18000330e`
- `SAMLIB!SamFreeMemory` at `0x180003304`
- `SAMLIB!SamFreeMemory` at `0x18000330e`

## pseudocode

```c
__int64 __fastcall CSamPropStore::_Init(__int64 a1, void *a2, const WCHAR *a3, unsigned int a4, int a5, int a6)
{
  DWORD LengthSid; // ebx
  void *v11; // rax
  signed int LastError; // eax
  int v13; // ebx
  int v14; // eax
  void *v15; // r15
  __int64 v16; // r13
  __int64 v17; // r14
  int v18; // eax
  int v19; // r12d
  int v20; // ebx
  int v21; // ebx
  _QWORD *v22; // rcx
  __int64 v23; // rdx
  unsigned int v24; // r15d
  WCHAR *v25; // r12
  int v26; // ebx
  unsigned __int64 v27; // rbx
  void *v28; // rax
  WCHAR *v29; // rcx
  _WORD *v30; // rdx
  _WORD *v31; // r9
  __int64 v32; // rax
  unsigned __int64 v33; // r8
  struct _UNICODE_STRING **v34; // rdi
  _QWORD *v35; // r14
  struct _UNICODE_STRING *v36; // rax
  void *v37; // rax
  void *v38; // rcx
  __int64 v39; // rdx
  __int64 v40; // rdx
  __int64 v41; // r9
  struct _DPA *v42; // rax
  int v43; // eax
  _OWORD *v44; // rax
  _QWORD *v45; // rax
  __int64 v47; // [rsp+28h] [rbp-81h]
  __int64 v48; // [rsp+30h] [rbp-79h]
  __int64 v49; // [rsp+40h] [rbp-69h] BYREF
  unsigned __int16 *v50; // [rsp+48h] [rbp-61h] BYREF
  struct _UNICODE_STRING **v51; // [rsp+50h] [rbp-59h]
  _DWORD *v52; // [rsp+58h] [rbp-51h] BYREF
  _QWORD *v53; // [rsp+60h] [rbp-49h]
  __int64 v54; // [rsp+68h] [rbp-41h] BYREF
  LPVOID v55; // [rsp+70h] [rbp-39h]
  struct _UNICODE_STRING DestinationString; // [rsp+78h] [rbp-31h] BYREF
  _QWORD v57[4]; // [rsp+88h] [rbp-21h] BYREF
  __int128 v58; // [rsp+A8h] [rbp-1h]
  LPVOID pv; // [rsp+108h] [rbp+5Fh] BYREF
  LPCWSTR psz; // [rsp+110h] [rbp+67h]
  unsigned int v61; // [rsp+118h] [rbp+6Fh]

  v61 = a4;
  psz = a3;
  if ( !a2 )
    goto LABEL_7;
  LengthSid = GetLengthSid(a2);
  v11 = CoTaskMemAlloc(LengthSid);
  *(_QWORD *)(a1 + 88) = v11;
  if ( !v11 )
    return (unsigned int)-2147024882;
  if ( CopySid(LengthSid, v11, a2) )
    goto LABEL_7;
  CoTaskMemFree(*(LPVOID *)(a1 + 88));
  *(_QWORD *)(a1 + 88) = 0;
  LastError = GetLastError();
  v13 = LastError;
  if ( LastError > 0 )
    v13 = (unsigned __int16)LastError | 0x80070000;
  if ( v13 >= 0 )
  {
LABEL_7:
    v14 = a5;
    *(_DWORD *)(a1 + 80) = a4;
    *(_DWORD *)(a1 + 84) = v14;
    if ( v14 == 1 )
    {
      *(_QWORD *)(a1 + 24) = 0;
      *(_QWORD *)(a1 + 32) = 0;
      v15 = a2;
      v53 = (_QWORD *)(a1 + 32);
      v16 = 0;
      v51 = (struct _UNICODE_STRING **)(a1 + 24);
      v17 = 0;
      pv = a2;
      if ( a2 )
      {
        v19 = 0;
      }
      else
      {
        v18 = CSGetAccountDomainSid(&pv, 0);
        v15 = pv;
        v13 = v18;
        v19 = 1;
        if ( v18 < 0 )
        {
LABEL_24:
          CoTaskMemFree(v15);
          v22 = WPP_GLOBAL_Control;
LABEL_25:
          v24 = v61;
          if ( v13 < 0 )
            goto LABEL_48;
          v25 = 0;
          v50 = 0;
          v52 = 0;
          LODWORD(pv) = v61;
          v26 = SamLookupIdsInDomain(v17, 1, &pv, &v50, &v52);
          if ( v26 < 0 )
          {
            if ( v26 == -1073741709 )
            {
              v13 = -2147023728;
              SamCloseHandle(v17);
              SamCloseHandle(v16);
LABEL_47:
              v22 = WPP_GLOBAL_Control;
LABEL_48:
              if ( v22 != &WPP_GLOBAL_Control && (*((_BYTE *)v22 + 28) & 4) != 0 )
              {
                WPP_SF_dD(v22[2], 56, WPP_b7edbcfa3c6c396011b8fcbeff20f182_Traceguids, v24, v13);
                v22 = WPP_GLOBAL_Control;
              }
              v34 = v51;
              v35 = v53;
              goto LABEL_52;
            }
            v13 = v26 | 0x10000000;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              WPP_SF_dD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                67,
                WPP_b7edbcfa3c6c396011b8fcbeff20f182_Traceguids,
                v24,
                v13);
LABEL_62:
            SamCloseHandle(v17);
            SamCloseHandle(v16);
            if ( v13 >= 0 )
            {
              DestinationString = 0;
              RtlInitUnicodeString(&DestinationString, v25);
              v39 = a1 + 72;
              v48 = a1 + 76;
              v35 = (_QWORD *)(a1 + 32);
              v47 = a1 + 72;
              v34 = v51;
              v13 = CSGetUserAccountInfo(a2, v39, &DestinationString, v51, v35, v47, v48);
              CoTaskMemFree(v25);
              v22 = WPP_GLOBAL_Control;
LABEL_52:
              if ( a6 && v13 == -2147023728 )
              {
                v13 = -2147024882;
                v36 = (struct _UNICODE_STRING *)CoTaskMemAlloc(0x13Cu);
                *v34 = v36;
                if ( v36 )
                {
                  memset_0(v36, 0, 0x13Cu);
                  v37 = CoTaskMemAlloc(0xA8u);
                  *v35 = v37;
                  if ( v37 )
                  {
                    memset_0(v37, 0, 0xA8u);
                    if ( psz )
                    {
                      pv = 0;
                      v13 = SHStrDupW(psz, (LPWSTR *)&pv);
                      if ( v13 >= 0 )
                      {
                        RtlInitUnicodeString(*v34 + 3, (PCWSTR)pv);
                        v38 = 0;
                        pv = 0;
LABEL_78:
                        CoTaskMemFree(v38);
                        return (unsigned int)v13;
                      }
                      goto LABEL_77;
                    }
                  }
                }
                return (unsigned int)v13;
              }
              if ( v13 >= 0 || v22 == &WPP_GLOBAL_Control || (*((_BYTE *)v22 + 28) & 2) == 0 )
                return (unsigned int)v13;
              v40 = 19;
              v41 = v24;
LABEL_83:
              WPP_SF_dD(v22[2], v40, WPP_7df418057efb386bc095915f6151cd01_Traceguids, v41, v13);
              return (unsigned int)v13;
            }
            goto LABEL_47;
          }
          if ( *v52 == 4 || *v52 == 1 )
          {
            v27 = ((unsigned __int64)*v50 + 2) >> 1;
            *(_QWORD *)&DestinationString.Length = v27;
            v28 = CoTaskMemAlloc(2 * v27);
            v55 = v28;
            if ( v28 )
            {
              memset_0(v28, 0, 2 * v27);
              v29 = (WCHAR *)v55;
              if ( v27 )
              {
                v30 = v55;
                v31 = (_WORD *)*((_QWORD *)v50 + 1);
                v32 = *(_QWORD *)&DestinationString.Length;
                v33 = (unsigned __int64)*v50 >> 1;
                v13 = 0;
                while ( v33 )
                {
                  if ( !*v31 )
                  {
                    if ( v32 )
                      break;
LABEL_39:
                    --v30;
                    v13 = -2147024774;
                    break;
                  }
                  *v30++ = *v31++;
                  --v33;
                  if ( !--v32 )
                    goto LABEL_39;
                }
                *v30 = 0;
                if ( v13 >= 0 )
                {
                  v25 = v29;
                  goto LABEL_44;
                }
              }
              else
              {
                v13 = -2147024809;
              }
              CoTaskMemFree(v29);
              goto LABEL_44;
            }
            v13 = -2147024882;
          }
          else
          {
            v13 = -805306230;
          }
LABEL_44:
          SamFreeMemory(v52);
          SamFreeMemory(v50);
          goto LABEL_62;
        }
      }
      v49 = 0;
      memset(&v57[1], 0, 24);
      v57[0] = 48;
      v58 = 0;
      v20 = SamConnect(0, &v49, 131105, v57);
      if ( v20 < 0 )
      {
        v13 = v20 | 0x10000000;
        v22 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          v23 = 35;
          goto LABEL_22;
        }
      }
      else
      {
        v54 = 0;
        v21 = SamOpenDomain(v49, 131973, v15, &v54);
        if ( v21 >= 0 )
        {
          v17 = v54;
          v16 = v49;
          v13 = 0;
          v22 = WPP_GLOBAL_Control;
          goto LABEL_23;
        }
        SamCloseHandle(v49);
        v13 = v21 | 0x10000000;
        v22 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          v23 = 34;
LABEL_22:
          WPP_SF_d(v22[2], v23, WPP_b7edbcfa3c6c396011b8fcbeff20f182_Traceguids, (unsigned int)v13);
          v22 = WPP_GLOBAL_Control;
        }
      }
LABEL_23:
      if ( !v19 )
        goto LABEL_25;
      goto LABEL_24;
    }
    if ( v14 != 2 )
      return (unsigned int)-805306230;
    v13 = -2147024882;
    v42 = g_pfn_DPA_Create(1);
    *(_QWORD *)(a1 + 56) = v42;
    if ( !v42 )
      return (unsigned int)v13;
    v43 = CSGetGroupAccountInfoByRID((int)a2, v42);
    v13 = v43;
    if ( !a6 || v43 != -2147023728 )
    {
      if ( v43 >= 0 )
        return (unsigned int)v13;
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        return (unsigned int)v13;
      v40 = 20;
      v41 = a4;
      goto LABEL_83;
    }
    v13 = -2147024882;
    v44 = CoTaskMemAlloc(0x28u);
    *(_QWORD *)(a1 + 40) = v44;
    if ( v44 )
    {
      *v44 = 0;
      v44[1] = 0;
      *((_QWORD *)v44 + 4) = 0;
      v45 = CoTaskMemAlloc(0x18u);
      *(_QWORD *)(a1 + 48) = v45;
      if ( v45 )
      {
        *(_OWORD *)v45 = 0;
        v45[2] = 0;
        if ( a3 )
        {
          pv = 0;
          v13 = SHStrDupW(a3, (LPWSTR *)&pv);
          if ( v13 >= 0 )
          {
            RtlInitUnicodeString(*(PUNICODE_STRING *)(a1 + 40), (PCWSTR)pv);
            v38 = 0;
            pv = 0;
            goto LABEL_78;
          }
LABEL_77:
          v38 = pv;
          goto LABEL_78;
        }
      }
    }
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180002ff0  mov     [rsp-8+arg_18], r9d
0x180002ff5  mov     [rsp-8+psz], r8
0x180002ffa  push    rbp
0x180002ffb  push    rbx
0x180002ffc  push    rsi
0x180002ffd  push    rdi
0x180002ffe  push    r12
0x180003000  push    r14
0x180003002  lea     rbp, [rsp-1Fh]
0x180003007  sub     rsp, 0C8h
0x18000300e  mov     rsi, rdx
0x180003011  mov     r14d, r9d
0x180003014  xor     edx, edx
0x180003016  mov     r12, r8
0x180003019  mov     rdi, rcx
0x18000301c  test    rsi, rsi
0x18000301f  jz      short loc_180003084
0x180003021  mov     rcx, rsi; pSid
0x180003024  call    cs:__imp_GetLengthSid
0x18000302a  mov     ecx, eax; cb
0x18000302c  mov     ebx, eax
0x18000302e  call    cs:__imp_CoTaskMemAlloc
0x180003034  mov     [rdi+58h], rax
0x180003038  test    rax, rax
0x18000303b  jz      loc_1800030F1
0x180003041  mov     r8, rsi; pSourceSid
0x180003044  mov     rdx, rax; pDestinationSid
0x180003047  mov     ecx, ebx; nDestinationSidLength
0x180003049  call    cs:__imp_CopySid
0x18000304f  test    eax, eax
0x180003051  jnz     short loc_180003082
0x180003053  mov     rcx, [rdi+58h]; pv
0x180003057  call    cs:__imp_CoTaskMemFree
0x18000305d  mov     qword ptr [rdi+58h], 0
0x180003065  call    cs:__imp_GetLastError
0x18000306b  mov     ebx, eax
0x18000306d  test    eax, eax
0x18000306f  jle     short loc_18000307A
0x180003071  movzx   ebx, ax
0x180003074  or      ebx, 80070000h
0x18000307a  test    ebx, ebx
0x18000307c  js      loc_180003644
0x180003082  xor     edx, edx
0x180003084  mov     eax, [rbp+47h+arg_20]
0x180003087  mov     [rsp+0F0h+var_30], r15
0x18000308f  mov     [rdi+50h], r14d
0x180003093  mov     [rdi+54h], eax
0x180003096  cmp     eax, 1
0x180003099  jnz     loc_180003518
0x18000309f  mov     [rdi+18h], rdx
0x1800030a3  lea     rax, [rdi+18h]
0x1800030a7  mov     [rsp+0F0h+arg_0], r13
0x1800030af  lea     rcx, [rdi+20h]
0x1800030b3  mov     [rcx], rdx
0x1800030b6  mov     r15, rsi
0x1800030b9  mov     [rbp+47h+var_90], rcx
0x1800030bd  mov     r13, rdx
0x1800030c0  mov     [rbp+47h+var_A0], rax
0x1800030c4  mov     r14, rdx
0x1800030c7  mov     [rbp+47h+pv], rsi
0x1800030cb  test    rsi, rsi
0x1800030ce  jnz     short loc_1800030FB
0x1800030d0  lea     rcx, [rbp+47h+pv]
0x1800030d4  call    CSGetAccountDomainSid
0x1800030d9  mov     r15, [rbp+47h+pv]
0x1800030dd  mov     ebx, eax
0x1800030df  mov     r12d, 1
0x1800030e5  test    eax, eax
0x1800030e7  js      loc_1800031E8
0x1800030ed  xor     edx, edx
0x1800030ef  jmp     short loc_1800030FE
0x1800030f1  mov     ebx, 8007000Eh
0x1800030f6  jmp     loc_180003644
0x1800030fb  mov     r12d, edx
0x1800030fe  mov     [rbp+47h+var_B0], rdx
0x180003102  lea     r9, [rbp+47h+var_68]
0x180003106  mov     [rbp+47h+var_60], rdx
0x18000310a  xorps   xmm0, xmm0
0x18000310d  mov     [rbp+47h+var_58], rdx
0x180003111  mov     r8d, 20021h
0x180003117  lea     rdx, [rbp+47h+var_B0]
0x18000311b  mov     [rbp+47h+var_68], 30h ; '0'
0x180003123  xor     ecx, ecx
0x180003125  mov     [rbp+47h+var_50], 0
0x18000312d  movdqu  [rbp+47h+var_48], xmm0
0x180003132  call    cs:__imp_SamConnect
0x180003138  mov     ebx, eax
0x18000313a  test    eax, eax
0x18000313c  js      short loc_1800031A5
0x18000313e  mov     rcx, [rbp+47h+var_B0]
0x180003142  lea     r9, [rbp+47h+var_88]
0x180003146  mov     r8, r15
0x180003149  mov     [rbp+47h+var_88], 0
0x180003151  mov     edx, 20385h
0x180003156  call    cs:__imp_SamOpenDomain
0x18000315c  mov     ebx, eax
0x18000315e  test    eax, eax
0x180003160  js      short loc_180003177
0x180003162  mov     r14, [rbp+47h+var_88]
0x180003166  xor     eax, eax
0x180003168  mov     r13, [rbp+47h+var_B0]
0x18000316c  mov     ebx, eax
0x18000316e  mov     rcx, cs:WPP_GLOBAL_Control
0x180003175  jmp     short loc_1800031E3
0x180003177  mov     rcx, [rbp+47h+var_B0]
0x18000317b  call    cs:__imp_SamCloseHandle
0x180003181  bts     ebx, 1Ch
0x180003185  mov     rcx, cs:WPP_GLOBAL_Control
0x18000318c  lea     rax, WPP_GLOBAL_Control
0x180003193  cmp     rcx, rax
0x180003196  jz      short loc_1800031E1
0x180003198  test    byte ptr [rcx+1Ch], 2
0x18000319c  jz      short loc_1800031E1
0x18000319e  mov     edx, 22h ; '"'
0x1800031a3  jmp     short loc_1800031C7
0x1800031a5  bts     ebx, 1Ch
0x1800031a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800031b0  lea     rax, WPP_GLOBAL_Control
0x1800031b7  cmp     rcx, rax
0x1800031ba  jz      short loc_1800031E1
0x1800031bc  test    byte ptr [rcx+1Ch], 2
0x1800031c0  jz      short loc_1800031E1
0x1800031c2  mov     edx, 23h ; '#'
0x1800031c7  mov     rcx, [rcx+10h]
0x1800031cb  lea     r8, WPP_b7edbcfa3c6c396011b8fcbeff20f182_Traceguids
0x1800031d2  mov     r9d, ebx
0x1800031d5  call    WPP_SF_d
0x1800031da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800031e1  xor     eax, eax
0x1800031e3  test    r12d, r12d
0x1800031e6  jz      short loc_1800031FA
0x1800031e8  mov     rcx, r15; pv
0x1800031eb  call    cs:__imp_CoTaskMemFree
0x1800031f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800031f8  xor     eax, eax
0x1800031fa  mov     r15d, [rbp+47h+arg_18]
0x1800031fe  test    ebx, ebx
0x180003200  js      loc_180003343
0x180003206  mov     r12, rax
0x180003209  mov     [rbp+47h+var_A8], rax
0x18000320d  mov     [rbp+47h+var_98], rax
0x180003211  lea     r9, [rbp+47h+var_A8]
0x180003215  lea     rax, [rbp+47h+var_98]
0x180003219  mov     dword ptr [rbp+47h+pv], r15d
0x18000321d  lea     r8, [rbp+47h+pv]
0x180003221  mov     [rsp+0F0h+var_D0], rax
0x180003226  mov     edx, 1
0x18000322b  mov     rcx, r14
0x18000322e  call    cs:__imp_SamLookupIdsInDomain
0x180003234  mov     ebx, eax
0x180003236  test    eax, eax
0x180003238  js      loc_180003319
0x18000323e  mov     rax, [rbp+47h+var_98]
0x180003242  mov     ecx, [rax]
0x180003244  cmp     ecx, 4
0x180003247  jz      short loc_180003258
0x180003249  cmp     ecx, 1
0x18000324c  jz      short loc_180003258
0x18000324e  mov     ebx, 0D000008Ah
0x180003253  jmp     loc_180003300
0x180003258  mov     rax, [rbp+47h+var_A8]
0x18000325c  movzx   ebx, word ptr [rax]
0x18000325f  add     rbx, 2
0x180003263  shr     rbx, 1
0x180003266  mov     qword ptr [rbp+47h+DestinationString.Length], rbx
0x18000326a  lea     rcx, [rbx+rbx]; cb
0x18000326e  call    cs:__imp_CoTaskMemAlloc
0x180003274  mov     [rbp+47h+var_80], rax
0x180003278  test    rax, rax
0x18000327b  jnz     short loc_180003284
0x18000327d  mov     ebx, 8007000Eh
0x180003282  jmp     short loc_180003300
0x180003284  lea     r8, [rbx+rbx]; Size
0x180003288  xor     edx, edx; Val
0x18000328a  mov     rcx, rax; void *
0x18000328d  call    memset_0
0x180003292  mov     rcx, [rbp+47h+var_80]; pv
0x180003296  test    rbx, rbx
0x180003299  jz      short loc_1800032F5
0x18000329b  mov     rax, [rbp+47h+var_A8]
0x18000329f  mov     rdx, rcx
0x1800032a2  movzx   r8d, word ptr [rax]
0x1800032a6  mov     r9, [rax+8]
0x1800032aa  mov     rax, qword ptr [rbp+47h+DestinationString.Length]
0x1800032ae  shr     r8, 1
0x1800032b1  xor     ebx, ebx
0x1800032b3  test    r8, r8
0x1800032b6  jz      short loc_1800032E7
0x1800032b8  movzx   r10d, word ptr [r9]
0x1800032bc  test    r10w, r10w
0x1800032c0  jz      short loc_1800032D9
0x1800032c2  mov     [rdx], r10w
0x1800032c6  add     r9, 2
0x1800032ca  add     rdx, 2
0x1800032ce  dec     r8
0x1800032d1  sub     rax, 1
0x1800032d5  jnz     short loc_1800032B3
0x1800032d7  jmp     short loc_1800032DE
0x1800032d9  test    rax, rax
0x1800032dc  jnz     short loc_1800032E7
0x1800032de  sub     rdx, 2
0x1800032e2  mov     ebx, 8007007Ah
0x1800032e7  xor     eax, eax
0x1800032e9  mov     [rdx], ax
0x1800032ec  test    ebx, ebx
0x1800032ee  js      short loc_1800032FA
0x1800032f0  mov     r12, rcx
0x1800032f3  jmp     short loc_180003300
0x1800032f5  mov     ebx, 80070057h
0x1800032fa  call    cs:__imp_CoTaskMemFree
0x180003300  mov     rcx, [rbp+47h+var_98]
0x180003304  call    cs:__imp_SamFreeMemory
0x18000330a  mov     rcx, [rbp+47h+var_A8]
0x18000330e  call    cs:__imp_SamFreeMemory
0x180003314  jmp     loc_180003476
0x180003319  cmp     ebx, 0C0000073h
0x18000331f  jnz     loc_18000343D
0x180003325  mov     rcx, r14
0x180003328  mov     ebx, 80070490h
0x18000332d  call    cs:__imp_SamCloseHandle
0x180003333  mov     rcx, r13
0x180003336  call    cs:__imp_SamCloseHandle
0x18000333c  mov     rcx, cs:WPP_GLOBAL_Control
0x180003343  lea     rax, WPP_GLOBAL_Control
0x18000334a  cmp     rcx, rax
0x18000334d  jz      short loc_18000337F
0x18000334f  test    byte ptr [rcx+1Ch], 4
0x180003353  jz      short loc_18000337F
0x180003355  mov     rcx, [rcx+10h]
0x180003359  lea     r8, WPP_b7edbcfa3c6c396011b8fcbeff20f182_Traceguids
0x180003360  mov     edx, 38h ; '8'
0x180003365  mov     dword ptr [rsp+0F0h+var_D0], ebx
0x180003369  mov     r9d, r15d
0x18000336c  call    WPP_SF_dD
0x180003371  mov     rcx, cs:WPP_GLOBAL_Control
0x180003378  lea     rax, WPP_GLOBAL_Control
0x18000337f  mov     rdi, [rbp+47h+var_A0]
0x180003383  mov     r14, [rbp+47h+var_90]
0x180003387  cmp     [rbp+47h+arg_28], 0
0x18000338b  mov     r13, [rsp+0F0h+arg_0]
0x180003393  jz      loc_1800034F0
0x180003399  cmp     ebx, 80070490h
0x18000339f  jnz     loc_1800034F0
0x1800033a5  mov     ecx, 13Ch; cb
0x1800033aa  mov     ebx, 8007000Eh
0x1800033af  call    cs:__imp_CoTaskMemAlloc
0x1800033b5  mov     [rdi], rax
0x1800033b8  test    rax, rax
0x1800033bb  jz      loc_18000363C
0x1800033c1  xor     edx, edx; Val
0x1800033c3  mov     r8d, 13Ch; Size
0x1800033c9  mov     rcx, rax; void *
0x1800033cc  call    memset_0
0x1800033d1  mov     ecx, 0A8h; cb
0x1800033d6  call    cs:__imp_CoTaskMemAlloc
0x1800033dc  mov     [r14], rax
0x1800033df  test    rax, rax
0x1800033e2  jz      loc_18000363C
0x1800033e8  xor     edx, edx; Val
0x1800033ea  mov     r8d, 0A8h; Size
0x1800033f0  mov     rcx, rax; void *
0x1800033f3  call    memset_0
0x1800033f8  mov     rcx, [rbp+47h+psz]; psz
0x1800033fc  test    rcx, rcx
0x1800033ff  jz      loc_18000363C
0x180003405  lea     rdx, [rbp+47h+pv]; ppwsz
0x180003409  mov     [rbp+47h+pv], 0
0x180003411  call    cs:__imp_SHStrDupW
0x180003417  mov     ebx, eax
0x180003419  test    eax, eax
0x18000341b  js      loc_1800035F0
0x180003421  mov     rcx, [rdi]
0x180003424  mov     rdx, [rbp+47h+pv]; SourceString
0x180003428  add     rcx, 30h ; '0'; DestinationString
0x18000342c  call    cs:__imp_RtlInitUnicodeString
0x180003432  xor     ecx, ecx
0x180003434  mov     [rbp+47h+pv], rcx
0x180003438  jmp     loc_1800035F4
0x18000343d  bts     ebx, 1Ch
0x180003441  mov     rcx, cs:WPP_GLOBAL_Control
0x180003448  lea     rax, WPP_GLOBAL_Control
0x18000344f  cmp     rcx, rax
0x180003452  jz      short loc_180003476
0x180003454  test    byte ptr [rcx+1Ch], 2
0x180003458  jz      short loc_180003476
0x18000345a  mov     rcx, [rcx+10h]
0x18000345e  lea     r8, WPP_b7edbcfa3c6c396011b8fcbeff20f182_Traceguids
0x180003465  mov     edx, 43h ; 'C'
0x18000346a  mov     dword ptr [rsp+0F0h+var_D0], ebx
0x18000346e  mov     r9d, r15d
0x180003471  call    WPP_SF_dD
0x180003476  mov     rcx, r14
0x180003479  call    cs:__imp_SamCloseHandle
0x18000347f  mov     rcx, r13
0x180003482  call    cs:__imp_SamCloseHandle
0x180003488  test    ebx, ebx
0x18000348a  js      loc_18000333C
0x180003490  xorps   xmm0, xmm0
0x180003493  lea     rcx, [rbp+47h+DestinationString]; DestinationString
0x180003497  mov     rdx, r12; SourceString
  ... truncated ...
```
