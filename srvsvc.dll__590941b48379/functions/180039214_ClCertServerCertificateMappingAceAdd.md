# ClCertServerCertificateMappingAceAdd

- ea: `0x180039214`
- end: `0x18003959e`
- name: `ClCertServerCertificateMappingAceAdd`
- size: `906`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180032370`

## callees

- `0x180020de8`
- `0x1800215e8`
- `0x180026e5c`
- `0x180036b4c`
- `0x1800373e0`
- `0x1800375e4`
- `0x180037fd0`
- `0x180038d98`
- `0x180038e20`
- `0x180038e94`
- `0x180039214`
- `0x180039a34`
- `0x18003a45c`
- `0x18003ab44`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180039354`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180039354`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180039448`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180039448`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800393c2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800393c2`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180039287`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180039287`

## pseudocode

```c
__int64 __fastcall ClCertServerCertificateMappingAceAdd(__int64 a1, _QWORD *a2)
{
  const WCHAR *v3; // rdi
  void *v4; // r15
  unsigned int v5; // eax
  __int64 v6; // rbx
  const WCHAR *v7; // rsi
  unsigned int v8; // r13d
  __int64 v9; // r12
  unsigned int v11; // ebx
  __int64 v12; // rcx
  unsigned int v13; // eax
  LPCWSTR v14; // r13
  LSTATUS Value; // eax
  int v16; // edx
  int v17; // r8d
  int v18; // edx
  int v19; // r8d
  LPCWSTR lpSubKey; // [rsp+50h] [rbp-19h] BYREF
  void *v21; // [rsp+58h] [rbp-11h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-9h] BYREF
  UCHAR pbOutput[8]; // [rsp+68h] [rbp-1h] BYREF
  BYTE *lpData; // [rsp+70h] [rbp+7h] BYREF
  __int64 v25; // [rsp+78h] [rbp+Fh]
  unsigned int v26; // [rsp+D0h] [rbp+67h]
  int v28; // [rsp+E0h] [rbp+77h] BYREF
  LPCWSTR lpValueName; // [rsp+E8h] [rbp+7Fh] BYREF

  v28 = 0;
  v3 = 0;
  *(_QWORD *)pbOutput = 0;
  v4 = 0;
  v5 = *(_DWORD *)(a1 + 28);
  v6 = *(_QWORD *)(a1 + 8);
  v7 = *(const WCHAR **)a1;
  v8 = *(_DWORD *)(a1 + 24);
  v9 = *(_QWORD *)(a1 + 16);
  *a2 = 0;
  lpValueName = 0;
  lpData = 0;
  lpSubKey = 0;
  hKey = 0;
  v21 = 0;
  v26 = v5;
  v25 = v6;
  if ( !InitOnceExecuteOnce(&ClCertInitOnce, ClCertInitOnceFn, 0, 0) )
    return 1359;
  v11 = ClCertValidateAce(v7, v6, (UCHAR)pbOutput);
  if ( v11 )
    goto LABEL_38;
  if ( v8 == 1 )
    v9 = *(_QWORD *)pbOutput;
  v11 = ClCertCalculateCertSid(v26, v8, v9, &lpValueName);
  if ( v11 || (v11 = ClCertFormatCertSidData(v8, v9, v25, &lpData, &v28)) != 0 )
  {
    v3 = lpValueName;
LABEL_38:
    v14 = lpSubKey;
    goto LABEL_39;
  }
  v13 = ClCertRegConcatKeyToPath(v12, v7, &lpSubKey);
  v14 = lpSubKey;
  v11 = v13;
  if ( !v13 )
  {
    v11 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0, 0, 3u, 0, &hKey, 0);
    if ( !v11 )
    {
      v3 = lpValueName;
      Value = RegQueryValueExW(hKey, lpValueName, 0, 0, 0, 0);
      v11 = Value;
      if ( Value )
      {
        if ( Value == 2 )
        {
          v11 = RegSetValueExW(hKey, v3, 0, 7u, lpData, lpData != 0 ? v28 : 0);
          if ( v11 )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) )
            {
              WPP_SF_SDS(*((_QWORD *)WPP_GLOBAL_Control + 2), v18, v19, (_DWORD)v3, v11, (__int64)v7);
            }
          }
          else
          {
            v11 = ClCertCreateOutputAce(a1, v9, *(_QWORD *)(a1 + 8), &v21);
            if ( v11 )
            {
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) )
              {
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_053b19d310c5352633ee666709ba12ba_Traceguids, v11);
              }
              v4 = v21;
            }
            else
            {
              *a2 = v21;
            }
          }
        }
        else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
               && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
               && *((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          WPP_SF_DSS(*((_QWORD *)WPP_GLOBAL_Control + 2), v16, v17, Value, (__int64)v7, (__int64)v3);
        }
      }
      else
      {
        v11 = 183;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          WPP_SF_SS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            15,
            (unsigned int)WPP_053b19d310c5352633ee666709ba12ba_Traceguids,
            (_DWORD)v7,
            (__int64)v3);
        }
      }
      goto LABEL_39;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        14,
        (unsigned int)WPP_053b19d310c5352633ee666709ba12ba_Traceguids,
        (_DWORD)v7,
        v11);
    }
  }
  v3 = lpValueName;
LABEL_39:
  ClCertLocalFree(*(_QWORD *)pbOutput);
  ClCertLocalFree(v3);
  ClCertLocalFree(lpData);
  ClCertLocalFree(v14);
  if ( hKey )
    ClCertRegCloseKey();
  ClCertFreeOutputAce(v4);
  return v11;
}

```

## disassembly

```asm
0x180039214  mov     [rsp-8+arg_8], rdx
0x180039219  push    rbp
0x18003921a  push    rbx
0x18003921b  push    rsi
0x18003921c  push    rdi
0x18003921d  push    r12
0x18003921f  push    r13
0x180039221  push    r14
0x180039223  push    r15
0x180039225  lea     rbp, [rsp-1Fh]
0x18003922a  sub     rsp, 88h
0x180039231  mov     r14, rcx
0x180039234  xor     r9d, r9d; Context
0x180039237  xor     ecx, ecx
0x180039239  xor     r8d, r8d; Parameter
0x18003923c  mov     [rbp+57h+arg_10], ecx
0x18003923f  mov     edi, ecx
0x180039241  mov     qword ptr [rbp+57h+pbOutput], rcx
0x180039245  mov     r15d, ecx
0x180039248  mov     eax, [r14+1Ch]
0x18003924c  mov     rbx, [r14+8]
0x180039250  mov     rsi, [r14]
0x180039253  mov     r13d, [r14+18h]
0x180039257  mov     r12, [r14+10h]
0x18003925b  mov     [rdx], rcx
0x18003925e  lea     rdx, ClCertInitOnceFn; InitFn
0x180039265  mov     [rbp+57h+lpValueName], rcx
0x180039269  mov     [rbp+57h+lpData], rcx
0x18003926d  mov     [rbp+57h+lpSubKey], rcx
0x180039271  mov     [rbp+57h+hKey], rcx
0x180039275  mov     [rbp+57h+var_68], rcx
0x180039279  lea     rcx, ClCertInitOnce; InitOnce
0x180039280  mov     [rbp+57h+arg_0], eax
0x180039283  mov     [rbp+57h+var_48], rbx
0x180039287  call    cs:__imp_InitOnceExecuteOnce
0x18003928d  test    eax, eax
0x18003928f  jnz     short loc_18003929B
0x180039291  mov     eax, 54Fh
0x180039296  jmp     loc_18003958A
0x18003929b  mov     edx, [rbp+57h+arg_0]
0x18003929e  lea     rax, [rbp+57h+pbOutput]
0x1800392a2  mov     qword ptr [rsp+0C0h+samDesired], rax; pbOutput
0x1800392a7  mov     r9, r12
0x1800392aa  mov     r8d, r13d
0x1800392ad  mov     qword ptr [rsp+0C0h+dwOptions], rbx; __int64
0x1800392b2  mov     rcx, rsi; lpValue
0x1800392b5  call    ClCertValidateAce
0x1800392ba  mov     ebx, eax
0x1800392bc  test    eax, eax
0x1800392be  jnz     loc_18003954C
0x1800392c4  mov     ecx, [rbp+57h+arg_0]
0x1800392c7  lea     r9, [rbp+57h+lpValueName]
0x1800392cb  cmp     r13d, 1
0x1800392cf  mov     edx, r13d
0x1800392d2  cmovz   r12, qword ptr [rbp+57h+pbOutput]
0x1800392d7  mov     r8, r12
0x1800392da  call    ClCertCalculateCertSid
0x1800392df  mov     ebx, eax
0x1800392e1  test    eax, eax
0x1800392e3  jnz     loc_180039548
0x1800392e9  mov     r8, [rbp+57h+var_48]
0x1800392ed  lea     rax, [rbp+57h+arg_10]
0x1800392f1  lea     r9, [rbp+57h+lpData]
0x1800392f5  mov     qword ptr [rsp+0C0h+dwOptions], rax
0x1800392fa  mov     rdx, r12
0x1800392fd  mov     ecx, r13d
0x180039300  call    ClCertFormatCertSidData
0x180039305  mov     ebx, eax
0x180039307  test    eax, eax
0x180039309  jnz     loc_180039548
0x18003930f  lea     r8, [rbp+57h+lpSubKey]
0x180039313  mov     rdx, rsi
0x180039316  call    ClCertRegConcatKeyToPath
0x18003931b  mov     r13, [rbp+57h+lpSubKey]
0x18003931f  mov     ebx, eax
0x180039321  test    eax, eax
0x180039323  jnz     short loc_18003939E
0x180039325  mov     [rsp+0C0h+lpdwDisposition], rdi; lpdwDisposition
0x18003932a  lea     rax, [rbp+57h+hKey]
0x18003932e  mov     [rsp+0C0h+phkResult], rax; phkResult
0x180039333  xor     r9d, r9d; lpClass
0x180039336  mov     [rsp+0C0h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x18003933b  xor     r8d, r8d; Reserved
0x18003933e  mov     [rsp+0C0h+samDesired], 3; samDesired
0x180039346  mov     rdx, r13; lpSubKey
0x180039349  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180039350  mov     [rsp+0C0h+dwOptions], edi; dwOptions
0x180039354  call    cs:__imp_RegCreateKeyExW
0x18003935a  mov     ebx, eax
0x18003935c  test    eax, eax
0x18003935e  jz      short loc_1800393A7
0x180039360  mov     rcx, cs:WPP_GLOBAL_Control
0x180039367  lea     rax, WPP_GLOBAL_Control
0x18003936e  cmp     rcx, rax
0x180039371  jz      short loc_18003939E
0x180039373  test    dword ptr [rcx+1Ch], 800h
0x18003937a  jz      short loc_18003939E
0x18003937c  cmp     byte ptr [rcx+19h], 1
0x180039380  jb      short loc_18003939E
0x180039382  mov     rcx, [rcx+10h]
0x180039386  lea     r8, WPP_053b19d310c5352633ee666709ba12ba_Traceguids
0x18003938d  mov     edx, 0Eh
0x180039392  mov     [rsp+0C0h+dwOptions], ebx
0x180039396  mov     r9, rsi
0x180039399  call    WPP_SF_Sd
0x18003939e  mov     rdi, [rbp+57h+lpValueName]
0x1800393a2  jmp     loc_180039550
0x1800393a7  mov     rcx, [rbp+57h+hKey]; hKey
0x1800393ab  xor     r9d, r9d; lpType
0x1800393ae  mov     qword ptr [rsp+0C0h+samDesired], rdi; lpcbData
0x1800393b3  xor     r8d, r8d; lpReserved
0x1800393b6  mov     qword ptr [rsp+0C0h+dwOptions], rdi; lpData
0x1800393bb  mov     rdi, [rbp+57h+lpValueName]
0x1800393bf  mov     rdx, rdi; lpValueName
0x1800393c2  call    cs:__imp_RegQueryValueExW
0x1800393c8  mov     ebx, eax
0x1800393ca  test    eax, eax
0x1800393cc  jz      loc_180039502
0x1800393d2  cmp     eax, 2
0x1800393d5  jz      short loc_180039420
0x1800393d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800393de  lea     rax, WPP_GLOBAL_Control
0x1800393e5  cmp     rcx, rax
0x1800393e8  jz      loc_180039550
0x1800393ee  test    dword ptr [rcx+1Ch], 800h
0x1800393f5  jz      loc_180039550
0x1800393fb  cmp     byte ptr [rcx+19h], 1
0x1800393ff  jb      loc_180039550
0x180039405  mov     rcx, [rcx+10h]
0x180039409  mov     r9d, ebx
0x18003940c  mov     qword ptr [rsp+0C0h+samDesired], rdi
0x180039411  mov     qword ptr [rsp+0C0h+dwOptions], rsi
0x180039416  call    WPP_SF_DSS
0x18003941b  jmp     loc_180039550
0x180039420  mov     rdx, [rbp+57h+lpData]
0x180039424  mov     r9d, 7; dwType
0x18003942a  mov     rax, rdx
0x18003942d  neg     rax
0x180039430  sbb     ecx, ecx
0x180039432  xor     r8d, r8d; Reserved
0x180039435  and     ecx, [rbp+57h+arg_10]
0x180039438  mov     [rsp+0C0h+samDesired], ecx; cbData
0x18003943c  mov     rcx, [rbp+57h+hKey]; hKey
0x180039440  mov     qword ptr [rsp+0C0h+dwOptions], rdx; lpData
0x180039445  mov     rdx, rdi; lpValueName
0x180039448  call    cs:__imp_RegSetValueExW
0x18003944e  mov     ebx, eax
0x180039450  test    eax, eax
0x180039452  jz      short loc_18003949C
0x180039454  mov     rcx, cs:WPP_GLOBAL_Control
0x18003945b  lea     rax, WPP_GLOBAL_Control
0x180039462  cmp     rcx, rax
0x180039465  jz      loc_180039550
0x18003946b  test    dword ptr [rcx+1Ch], 800h
0x180039472  jz      loc_180039550
0x180039478  cmp     byte ptr [rcx+19h], 1
0x18003947c  jb      loc_180039550
0x180039482  mov     rcx, [rcx+10h]
0x180039486  mov     r9, rdi
0x180039489  mov     qword ptr [rsp+0C0h+samDesired], rsi
0x18003948e  mov     [rsp+0C0h+dwOptions], ebx
0x180039492  call    WPP_SF_SDS
0x180039497  jmp     loc_180039550
0x18003949c  mov     r8, [r14+8]
0x1800394a0  lea     r9, [rbp+57h+var_68]
0x1800394a4  mov     rdx, r12
0x1800394a7  mov     rcx, r14
0x1800394aa  call    ClCertCreateOutputAce
0x1800394af  mov     ebx, eax
0x1800394b1  test    eax, eax
0x1800394b3  jz      short loc_1800394F5
0x1800394b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800394bc  lea     rax, WPP_GLOBAL_Control
0x1800394c3  cmp     rcx, rax
0x1800394c6  jz      short loc_1800394EF
0x1800394c8  test    dword ptr [rcx+1Ch], 800h
0x1800394cf  jz      short loc_1800394EF
0x1800394d1  cmp     byte ptr [rcx+19h], 1
0x1800394d5  jb      short loc_1800394EF
0x1800394d7  mov     rcx, [rcx+10h]
0x1800394db  lea     r8, WPP_053b19d310c5352633ee666709ba12ba_Traceguids
0x1800394e2  mov     edx, 12h
0x1800394e7  mov     r9d, ebx
0x1800394ea  call    WPP_SF_d
0x1800394ef  mov     r15, [rbp+57h+var_68]
0x1800394f3  jmp     short loc_180039550
0x1800394f5  mov     rcx, [rbp+57h+arg_8]
0x1800394f9  mov     rax, [rbp+57h+var_68]
0x1800394fd  mov     [rcx], rax
0x180039500  jmp     short loc_180039550
0x180039502  mov     ebx, 0B7h
0x180039507  mov     rcx, cs:WPP_GLOBAL_Control
0x18003950e  lea     rax, WPP_GLOBAL_Control
0x180039515  cmp     rcx, rax
0x180039518  jz      short loc_180039550
0x18003951a  test    dword ptr [rcx+1Ch], 800h
0x180039521  jz      short loc_180039550
0x180039523  cmp     byte ptr [rcx+19h], 1
0x180039527  jb      short loc_180039550
0x180039529  mov     rcx, [rcx+10h]
0x18003952d  lea     r8, WPP_053b19d310c5352633ee666709ba12ba_Traceguids
0x180039534  mov     edx, 0Fh
0x180039539  mov     qword ptr [rsp+0C0h+dwOptions], rdi
0x18003953e  mov     r9, rsi
0x180039541  call    WPP_SF_SS
0x180039546  jmp     short loc_180039550
0x180039548  mov     rdi, [rbp+57h+lpValueName]
0x18003954c  mov     r13, [rbp+57h+lpSubKey]
0x180039550  mov     rcx, qword ptr [rbp+57h+pbOutput]
0x180039554  call    ClCertLocalFree
0x180039559  mov     rcx, rdi
0x18003955c  call    ClCertLocalFree
0x180039561  mov     rcx, [rbp+57h+lpData]
0x180039565  call    ClCertLocalFree
0x18003956a  mov     rcx, r13
0x18003956d  call    ClCertLocalFree
0x180039572  mov     rcx, [rbp+57h+hKey]
0x180039576  test    rcx, rcx
0x180039579  jz      short loc_180039580
0x18003957b  call    ClCertRegCloseKey
0x180039580  mov     rcx, r15; hMem
0x180039583  call    ClCertFreeOutputAce
0x180039588  mov     eax, ebx
0x18003958a  add     rsp, 88h
0x180039591  pop     r15
0x180039593  pop     r14
0x180039595  pop     r13
0x180039597  pop     r12
0x180039599  pop     rdi
0x18003959a  pop     rsi
0x18003959b  pop     rbx
0x18003959c  pop     rbp
0x18003959d  retn
```
