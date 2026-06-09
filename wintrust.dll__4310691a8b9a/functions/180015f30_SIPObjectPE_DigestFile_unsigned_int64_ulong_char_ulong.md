# SIPObjectPE_::DigestFile(unsigned __int64,ulong,char *,ulong *)

- ea: `0x180015f30`
- end: `0x18001630c`
- name: `?DigestFile@SIPObjectPE_@@MEAAPEAE_KKPEADPEAK@Z`
- size: `988`
- prototype: `unsigned __int8 *__fastcall(SIPObjectPE_ *this, __int64, __int64, char *, unsigned int *)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting`

## callees

- `0x180015f30`
- `0x180016314`
- `0x1800163d8`
- `0x180016640`
- `0x18004de6a`
- `0x18004deb0`

## import_xrefs

- `msvcrt!free` at `0x180016165`
- `msvcrt!free` at `0x180016165`
- `msvcrt!malloc` at `0x180016044`
- `msvcrt!malloc` at `0x180016044`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001610c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180016265`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001610c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180016265`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800162e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800162e9`
- `ntdll!RtlNtStatusToDosError` at `0x18001622b`
- `ntdll!RtlNtStatusToDosError` at `0x18001629d`
- `ntdll!RtlNtStatusToDosError` at `0x18001622b`
- `ntdll!RtlNtStatusToDosError` at `0x18001629d`
- `CRYPT32!CryptFindOIDInfo` at `0x180015fae`
- `CRYPT32!CryptFindOIDInfo` at `0x1800161a6`
- `CRYPT32!CryptFindOIDInfo` at `0x18001624b`
- `CRYPT32!CryptFindOIDInfo` at `0x1800162c4`
- `CRYPT32!CryptFindOIDInfo` at `0x180015fae`
- `CRYPT32!CryptFindOIDInfo` at `0x1800161a6`
- `CRYPT32!CryptFindOIDInfo` at `0x18001624b`
- `CRYPT32!CryptFindOIDInfo` at `0x1800162c4`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180015fd6`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800161cc`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180015fd6`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800161cc`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180016122`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180016286`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180016122`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180016286`
- `bcrypt!BCryptGetProperty` at `0x18001602b`
- `bcrypt!BCryptGetProperty` at `0x18001602b`

## pseudocode

```c
unsigned __int8 *__fastcall SIPObjectPE_::DigestFile(
        SIPObjectPE_ *this,
        __int64 a2,
        __int64 a3,
        char *a4,
        unsigned int *a5)
{
  unsigned int *v7; // r14
  PCCRYPT_OID_INFO OIDInfo; // rax
  int v9; // eax
  BCRYPT_ALG_HANDLE v10; // rcx
  int v11; // edi
  void *v12; // rax
  void *v13; // rbx
  _DWORD *v14; // rax
  unsigned __int64 i; // rdi
  unsigned int *v17; // r14
  void *v18; // r12
  PCCRYPT_OID_INFO v19; // rax
  int v20; // eax
  BCRYPT_ALG_HANDLE v21; // rcx
  ULONG v22; // eax
  unsigned int j; // eax
  __int64 v24; // rax
  DWORD LastError; // eax
  DWORD dwErrCode; // [rsp+30h] [rbp-D0h] BYREF
  char v27; // [rsp+34h] [rbp-CCh] BYREF
  UCHAR pbOutput[4]; // [rsp+38h] [rbp-C8h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+40h] [rbp-C0h] BYREF
  BCRYPT_ALG_HANDLE hAlgorithm[2]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v31; // [rsp+58h] [rbp-A8h]
  unsigned int v32; // [rsp+60h] [rbp-A0h]
  ULONG pcbResult; // [rsp+68h] [rbp-98h] BYREF
  int v34; // [rsp+6Ch] [rbp-94h] BYREF
  unsigned int *v35; // [rsp+70h] [rbp-90h]
  _QWORD v36[7]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v37[16]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v38; // [rsp+C0h] [rbp-40h]
  int v39; // [rsp+110h] [rbp+10h] BYREF
  __int64 v40; // [rsp+114h] [rbp+14h]
  void *v41; // [rsp+120h] [rbp+20h] BYREF
  __int128 v42; // [rsp+128h] [rbp+28h]

  v7 = a5;
  v35 = a5;
  *a5 = 0;
  dwErrCode = 0;
  v34 = 0;
  memset_0(v37, 0, 0x58u);
  *(_OWORD *)hAlgorithm = 0;
  v31 = 0;
  v32 = 0;
  OIDInfo = CryptFindOIDInfo(1u, a4, 1u);
  if ( OIDInfo || (OIDInfo = CryptFindOIDInfo(1u, a4, 4u)) != 0 )
  {
    phAlgorithm = 0;
    v9 = BCryptOpenAlgorithmProvider(&phAlgorithm, *(LPCWSTR *)&OIDInfo[1].cbSize, 0, 0);
    if ( v9 < 0 )
    {
      v22 = RtlNtStatusToDosError(v9);
      dwErrCode = v22;
      v10 = 0;
      if ( v22 )
        goto LABEL_34;
    }
    else
    {
      v10 = phAlgorithm;
      dwErrCode = 0;
    }
    if ( v32 < 3 )
      hAlgorithm[v32++] = v10;
    *(_DWORD *)pbOutput = 0;
    pcbResult = 0;
    if ( BCryptGetProperty(v10, L"HashDigestLength", pbOutput, 4u, &pcbResult, 0) )
    {
      v13 = 0;
LABEL_40:
      LastError = -2146893816;
      goto LABEL_41;
    }
    v11 = *(_DWORD *)pbOutput;
    v12 = malloc(*(unsigned int *)pbOutput);
    v13 = v12;
    if ( v12 )
    {
      v42 = 0;
      v40 = 0;
      v41 = v12;
      v39 = v11;
      v14 = (_DWORD *)*((_QWORD *)this + 13);
      if ( !v14 )
      {
LABEL_9:
        if ( (unsigned int)BigFileHeaderMap(*((HANDLE *)this + 1), (struct _BIG_FILE_MAP_INFO *)v37) )
        {
          if ( v38 > 0xFFFFFFFFLL )
          {
            dwErrCode = -2147024809;
          }
          else
          {
            v27 = 1;
            v36[0] = &v34;
            v36[1] = hAlgorithm;
            v36[2] = v37;
            v36[3] = &v41;
            v36[4] = &v39;
            v36[5] = &v27;
            v36[6] = &dwErrCode;
            seh_invoke__lambda_1d653bcfe0339cc48737c4b1b12f8c8a_(&dwErrCode, v36);
            if ( !dwErrCode )
            {
              if ( v27 )
              {
                *v7 = *(_DWORD *)pbOutput;
                goto LABEL_14;
              }
              dwErrCode = -2147418113;
            }
          }
LABEL_19:
          free(v13);
          v13 = 0;
LABEL_14:
          BigFileUnmap((struct _BIG_FILE_MAP_INFO *)v37);
          SetLastError(dwErrCode);
          while ( v32 )
            BCryptCloseAlgorithmProvider(hAlgorithm[--v32], 0);
          return (unsigned __int8 *)v13;
        }
        LastError = GetLastError();
LABEL_41:
        dwErrCode = LastError;
        goto LABEL_19;
      }
      if ( (unsigned int)(*v14 + 1) <= 3 )
      {
        for ( i = 1; ; ++i )
        {
          v17 = (unsigned int *)*((_QWORD *)this + 13);
          if ( i > *v17 )
            break;
          v18 = *(void **)(*(_QWORD *)&v17[18 * i - 16] + 8LL);
          v19 = CryptFindOIDInfo(1u, v18, 1u);
          if ( !v19 )
          {
            v19 = CryptFindOIDInfo(1u, v18, 4u);
            if ( !v19 )
              goto LABEL_40;
          }
          phAlgorithm = 0;
          v20 = BCryptOpenAlgorithmProvider(&phAlgorithm, *(LPCWSTR *)&v19[1].cbSize, 0, 0);
          if ( v20 < 0 )
          {
            dwErrCode = RtlNtStatusToDosError(v20);
            v21 = 0;
            if ( dwErrCode )
              goto LABEL_19;
          }
          else
          {
            v21 = phAlgorithm;
            dwErrCode = 0;
          }
          if ( v32 < 3 )
            hAlgorithm[v32++] = v21;
          *(&v41 + i) = &v17[18 * i - 14];
          *(&v39 + i) = *(_DWORD *)(*(_QWORD *)&v17[18 * i - 16] + 20LL);
        }
        v7 = v35;
        goto LABEL_9;
      }
    }
    dwErrCode = -2147024882;
    goto LABEL_19;
  }
  v22 = -2146893816;
  dwErrCode = -2146893816;
LABEL_34:
  SetLastError(v22);
  for ( j = v32; v32; j = v32 )
  {
    v24 = j - 1;
    v32 = v24;
    BCryptCloseAlgorithmProvider(hAlgorithm[v24], 0);
  }
  return 0;
}

```

## disassembly

```asm
0x180015f30  mov     [rsp-8+arg_8], rbx
0x180015f35  push    rbp
0x180015f36  push    rsi
0x180015f37  push    rdi
0x180015f38  push    r12
0x180015f3a  push    r13
0x180015f3c  push    r14
0x180015f3e  push    r15
0x180015f40  lea     rbp, [rsp-40h]
0x180015f45  sub     rsp, 140h
0x180015f4c  mov     rax, cs:__security_cookie
0x180015f53  xor     rax, rsp
0x180015f56  mov     [rbp+70h+var_38], rax
0x180015f5a  mov     rbx, r9
0x180015f5d  mov     r13, rcx
0x180015f60  mov     r14, [rbp+70h+arg_20]
0x180015f67  mov     [rsp+170h+var_100], r14
0x180015f6c  xor     r12d, r12d
0x180015f6f  mov     [r14], r12d
0x180015f72  mov     [rsp+170h+dwErrCode], r12d
0x180015f77  mov     [rsp+170h+var_104], r12d
0x180015f7c  xor     edx, edx; Val
0x180015f7e  lea     r8d, [r12+58h]; Size
0x180015f83  lea     rcx, [rbp+70h+var_C0]; void *
0x180015f87  call    memset_0
0x180015f8c  xorps   xmm0, xmm0
0x180015f8f  xor     eax, eax
0x180015f91  movups  xmmword ptr [rsp+170h+hAlgorithm], xmm0
0x180015f96  mov     [rsp+170h+var_118], rax
0x180015f9b  mov     [rsp+170h+var_110], r12d
0x180015fa0  lea     r15d, [r12+1]
0x180015fa5  mov     r8d, r15d; dwGroupId
0x180015fa8  mov     rdx, rbx; pvKey
0x180015fab  mov     ecx, r15d; dwKeyType
0x180015fae  call    cs:__imp_CryptFindOIDInfo
0x180015fb4  lea     edi, [r12+4]
0x180015fb9  test    rax, rax
0x180015fbc  jz      loc_180016242
0x180015fc2  mov     [rsp+170h+phAlgorithm], r12
0x180015fc7  xor     r9d, r9d; dwFlags
0x180015fca  xor     r8d, r8d; pszImplementation
0x180015fcd  mov     rdx, [rax+30h]; pszAlgId
0x180015fd1  lea     rcx, [rsp+170h+phAlgorithm]; phAlgorithm
0x180015fd6  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180015fdc  test    eax, eax
0x180015fde  js      loc_180016229
0x180015fe4  mov     rcx, [rsp+170h+phAlgorithm]; hObject
0x180015fe9  mov     [rsp+170h+dwErrCode], r12d
0x180015fee  cmp     [rsp+170h+var_110], 3
0x180015ff3  jnb     short loc_180016003
0x180015ff5  mov     eax, [rsp+170h+var_110]
0x180015ff9  mov     [rsp+rax*8+170h+hAlgorithm], rcx
0x180015ffe  add     [rsp+170h+var_110], r15d
0x180016003  mov     dword ptr [rsp+170h+pbOutput], r12d
0x180016008  mov     [rsp+170h+var_108], r12d
0x18001600d  mov     [rsp+170h+dwFlags], r12d; dwFlags
0x180016012  lea     rax, [rsp+170h+var_108]
0x180016017  mov     [rsp+170h+pcbResult], rax; pcbResult
0x18001601c  mov     r9d, edi; cbOutput
0x18001601f  lea     r8, [rsp+170h+pbOutput]; pbOutput
0x180016024  lea     rdx, pszProperty; "HashDigestLength"
0x18001602b  call    cs:__imp_BCryptGetProperty
0x180016031  mov     esi, 0FFFFFFFFh
0x180016036  test    eax, eax
0x180016038  jnz     loc_1800162E4
0x18001603e  mov     edi, dword ptr [rsp+170h+pbOutput]
0x180016042  mov     ecx, edi; Size
0x180016044  call    cs:__imp_malloc
0x18001604a  mov     rbx, rax
0x18001604d  test    rax, rax
0x180016050  jz      loc_18001615A
0x180016056  xorps   xmm0, xmm0
0x180016059  movdqu  [rbp+70h+var_48], xmm0
0x18001605e  mov     [rbp+70h+var_5C], r12
0x180016062  mov     [rbp+70h+var_50], rax
0x180016066  mov     [rbp+70h+var_60], edi
0x180016069  mov     rax, [r13+68h]
0x18001606d  test    rax, rax
0x180016070  jnz     loc_180016170
0x180016076  lea     rdx, [rbp+70h+var_C0]; struct _BIG_FILE_MAP_INFO *
0x18001607a  mov     rcx, [r13+8]; hFile
0x18001607e  call    ?BigFileHeaderMap@@YAHPEAXPEAU_BIG_FILE_MAP_INFO@@@Z; BigFileHeaderMap(void *,_BIG_FILE_MAP_INFO *)
0x180016083  test    eax, eax
0x180016085  jz      loc_1800162E9
0x18001608b  cmp     [rbp+70h+var_B0], rsi
0x18001608f  jg      loc_1800162F1
0x180016095  mov     [rsp+170h+var_13C], r15b
0x18001609a  lea     rax, [rsp+170h+var_104]
0x18001609f  mov     [rsp+170h+var_F8], rax
0x1800160a4  lea     rax, [rsp+170h+hAlgorithm]
0x1800160a9  mov     [rbp+70h+var_F0], rax
0x1800160ad  lea     rax, [rbp+70h+var_C0]
0x1800160b1  mov     [rbp+70h+var_E8], rax
0x1800160b5  lea     rax, [rbp+70h+var_50]
0x1800160b9  mov     [rbp+70h+var_E0], rax
0x1800160bd  lea     rax, [rbp+70h+var_60]
0x1800160c1  mov     [rbp+70h+var_D8], rax
0x1800160c5  lea     rax, [rsp+170h+var_13C]
0x1800160ca  mov     [rbp+70h+var_D0], rax
0x1800160ce  lea     rax, [rsp+170h+dwErrCode]
0x1800160d3  mov     [rbp+70h+var_C8], rax
0x1800160d7  lea     rdx, [rsp+170h+var_F8]
0x1800160dc  lea     rcx, [rsp+170h+dwErrCode]
0x1800160e1  call    seh_invoke__lambda_1d653bcfe0339cc48737c4b1b12f8c8a___; seh_invoke__lambda_1d653bcfe0339cc48737c4b1b12f8c8a_
0x1800160e6  cmp     [rsp+170h+dwErrCode], r12d
0x1800160eb  jnz     short loc_180016162
0x1800160ed  cmp     [rsp+170h+var_13C], r12b
0x1800160f2  jz      loc_1800162FE
0x1800160f8  mov     eax, dword ptr [rsp+170h+pbOutput]
0x1800160fc  mov     [r14], eax
0x1800160ff  lea     rcx, [rbp+70h+var_C0]; struct _BIG_FILE_MAP_INFO *
0x180016103  call    ?BigFileUnmap@@YAXPEAU_BIG_FILE_MAP_INFO@@@Z; BigFileUnmap(_BIG_FILE_MAP_INFO *)
0x180016108  mov     ecx, [rsp+170h+dwErrCode]; dwErrCode
0x18001610c  call    cs:__imp_SetLastError
0x180016112  nop
0x180016113  jmp     short loc_180016128
0x180016115  add     eax, esi
0x180016117  mov     [rsp+170h+var_110], eax
0x18001611b  xor     edx, edx; dwFlags
0x18001611d  mov     rcx, [rsp+rax*8+170h+hAlgorithm]; hAlgorithm
0x180016122  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180016128  mov     eax, [rsp+170h+var_110]
0x18001612c  test    eax, eax
0x18001612e  jnz     short loc_180016115
0x180016130  mov     rax, rbx
0x180016133  mov     rcx, [rbp+70h+var_38]
0x180016137  xor     rcx, rsp; StackCookie
0x18001613a  call    __security_check_cookie
0x18001613f  mov     rbx, [rsp+170h+arg_8]
0x180016147  add     rsp, 140h
0x18001614e  pop     r15
0x180016150  pop     r14
0x180016152  pop     r13
0x180016154  pop     r12
0x180016156  pop     rdi
0x180016157  pop     rsi
0x180016158  pop     rbp
0x180016159  retn
0x18001615a  mov     [rsp+170h+dwErrCode], 8007000Eh
0x180016162  mov     rcx, rbx; Block
0x180016165  call    cs:__imp_free
0x18001616b  mov     rbx, r12
0x18001616e  jmp     short loc_1800160FF
0x180016170  mov     eax, [rax]
0x180016172  add     eax, r15d
0x180016175  cmp     eax, 3
0x180016178  ja      short loc_18001615A
0x18001617a  mov     rdi, r15
0x18001617d  mov     r14, [r13+68h]
0x180016181  mov     eax, [r14]
0x180016184  cmp     rdi, rax
0x180016187  ja      loc_18001621F
0x18001618d  lea     r15, [rdi+rdi*8]
0x180016191  mov     rax, [r14+r15*8-40h]
0x180016196  mov     r12, [rax+8]
0x18001619a  mov     r8d, 1; dwGroupId
0x1800161a0  mov     rdx, r12; pvKey
0x1800161a3  mov     ecx, r8d; dwKeyType
0x1800161a6  call    cs:__imp_CryptFindOIDInfo
0x1800161ac  test    rax, rax
0x1800161af  jz      loc_1800162B7
0x1800161b5  xor     r12d, r12d
0x1800161b8  mov     [rsp+170h+phAlgorithm], r12
0x1800161bd  xor     r9d, r9d; dwFlags
0x1800161c0  xor     r8d, r8d; pszImplementation
0x1800161c3  mov     rdx, [rax+30h]; pszAlgId
0x1800161c7  lea     rcx, [rsp+170h+phAlgorithm]; phAlgorithm
0x1800161cc  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1800161d2  test    eax, eax
0x1800161d4  js      loc_18001629B
0x1800161da  mov     rcx, [rsp+170h+phAlgorithm]
0x1800161df  mov     [rsp+170h+dwErrCode], r12d
0x1800161e4  cmp     [rsp+170h+var_110], 3
0x1800161e9  jnb     short loc_1800161F8
0x1800161eb  mov     eax, [rsp+170h+var_110]
0x1800161ef  mov     [rsp+rax*8+170h+hAlgorithm], rcx
0x1800161f4  inc     [rsp+170h+var_110]
0x1800161f8  lea     rax, [r14-38h]
0x1800161fc  lea     rax, [rax+r15*8]
0x180016200  mov     [rbp+rdi*8+70h+var_50], rax
0x180016205  mov     rax, [r14+r15*8-40h]
0x18001620a  mov     ecx, [rax+14h]
0x18001620d  mov     [rbp+rdi*4+70h+var_60], ecx
0x180016211  mov     r15d, 1
0x180016217  add     rdi, r15
0x18001621a  jmp     loc_18001617D
0x18001621f  mov     r14, [rsp+170h+var_100]
0x180016224  jmp     loc_180016076
0x180016229  mov     ecx, eax; Status
0x18001622b  call    cs:__imp_RtlNtStatusToDosError
0x180016231  mov     [rsp+170h+dwErrCode], eax
0x180016235  mov     rcx, r12
0x180016238  test    eax, eax
0x18001623a  jz      loc_180015FEE
0x180016240  jmp     short loc_180016263
0x180016242  mov     r8d, edi; dwGroupId
0x180016245  mov     rdx, rbx; pvKey
0x180016248  mov     ecx, r15d; dwKeyType
0x18001624b  call    cs:__imp_CryptFindOIDInfo
0x180016251  test    rax, rax
0x180016254  jnz     loc_180015FC2
0x18001625a  mov     eax, 80090008h
0x18001625f  mov     [rsp+170h+dwErrCode], eax
0x180016263  mov     ecx, eax; dwErrCode
0x180016265  call    cs:__imp_SetLastError
0x18001626b  nop
0x18001626c  mov     eax, [rsp+170h+var_110]
0x180016270  test    eax, eax
0x180016272  jz      short loc_180016294
0x180016274  mov     esi, 0FFFFFFFFh
0x180016279  add     eax, esi
0x18001627b  mov     [rsp+170h+var_110], eax
0x18001627f  xor     edx, edx; dwFlags
0x180016281  mov     rcx, [rsp+rax*8+170h+hAlgorithm]; hAlgorithm
0x180016286  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18001628c  mov     eax, [rsp+170h+var_110]
0x180016290  test    eax, eax
0x180016292  jnz     short loc_180016279
0x180016294  xor     eax, eax
0x180016296  jmp     loc_180016133
0x18001629b  mov     ecx, eax; Status
0x18001629d  call    cs:__imp_RtlNtStatusToDosError
0x1800162a3  mov     [rsp+170h+dwErrCode], eax
0x1800162a7  mov     rcx, r12
0x1800162aa  test    eax, eax
0x1800162ac  jz      loc_1800161E4
0x1800162b2  jmp     loc_180016162
0x1800162b7  mov     r8d, 4; dwGroupId
0x1800162bd  mov     rdx, r12; pvKey
0x1800162c0  lea     ecx, [r8-3]; dwKeyType
0x1800162c4  call    cs:__imp_CryptFindOIDInfo
0x1800162ca  xor     r12d, r12d
0x1800162cd  test    rax, rax
0x1800162d0  jnz     loc_1800161B8
0x1800162d6  mov     eax, 80090008h
0x1800162db  mov     [rsp+170h+dwErrCode], eax
0x1800162df  jmp     loc_180016162
0x1800162e4  mov     rbx, r12
0x1800162e7  jmp     short loc_1800162D6
0x1800162e9  call    cs:__imp_GetLastError
0x1800162ef  jmp     short loc_1800162DB
0x1800162f1  mov     [rsp+170h+dwErrCode], 80070057h
0x1800162f9  jmp     loc_180016162
0x1800162fe  mov     [rsp+170h+dwErrCode], 8000FFFFh
0x180016306  jmp     loc_180016162
```
