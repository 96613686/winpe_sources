# GetHMACSHA1Hash(uchar *,ulong,ulong,uchar *,ulong,uchar *,ulong,uchar *,ulong,uchar *,ulong)

- ea: `0x180050580`
- end: `0x18005081b`
- name: `?GetHMACSHA1Hash@@YAJPEAEKK0K0K0K0K@Z`
- size: `667`
- prototype: `__int64 __fastcall(unsigned __int8 *, int, DWORD, unsigned __int8 *, DWORD, unsigned __int8 *pbData, DWORD dwDataLen, unsigned __int8 *, DWORD, unsigned __int8 *, unsigned int Size)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x18004d030`
- `0x18004d350`
- `0x180050514`
- `0x180050580`
- `0x180050944`
- `0x1800653ba`

## import_xrefs

- `ADVAPI32!CryptDestroyHash` at `0x1800507c6`
- `ADVAPI32!CryptDestroyHash` at `0x1800507e1`
- `ADVAPI32!CryptDestroyHash` at `0x1800507c6`
- `ADVAPI32!CryptDestroyHash` at `0x1800507e1`
- `ADVAPI32!CryptHashData` at `0x1800506a8`
- `ADVAPI32!CryptHashData` at `0x1800506c8`
- `ADVAPI32!CryptHashData` at `0x1800506e6`
- `ADVAPI32!CryptHashData` at `0x180050758`
- `ADVAPI32!CryptHashData` at `0x180050778`
- `ADVAPI32!CryptHashData` at `0x1800506a8`
- `ADVAPI32!CryptHashData` at `0x1800506c8`
- `ADVAPI32!CryptHashData` at `0x1800506e6`
- `ADVAPI32!CryptHashData` at `0x180050758`
- `ADVAPI32!CryptHashData` at `0x180050778`
- `ADVAPI32!CryptCreateHash` at `0x180050684`
- `ADVAPI32!CryptCreateHash` at `0x180050738`
- `ADVAPI32!CryptCreateHash` at `0x180050684`
- `ADVAPI32!CryptCreateHash` at `0x180050738`
- `ADVAPI32!CryptGetHashParam` at `0x18005070f`
- `ADVAPI32!CryptGetHashParam` at `0x18005079f`
- `ADVAPI32!CryptGetHashParam` at `0x18005070f`
- `ADVAPI32!CryptGetHashParam` at `0x18005079f`

## pseudocode

```c
__int64 __fastcall GetHMACSHA1Hash(
        unsigned __int8 *a1,
        int a2,
        DWORD a3,
        unsigned __int8 *a4,
        DWORD a5,
        unsigned __int8 *pbData,
        DWORD dwDataLen,
        unsigned __int8 *a8,
        DWORD a9,
        unsigned __int8 *a10,
        unsigned int Size)
{
  unsigned int AlgorithmBasedOnHashSize; // ebx
  ALG_ID Algid; // [rsp+30h] [rbp-C1h] BYREF
  DWORD pdwDataLen; // [rsp+34h] [rbp-BDh] BYREF
  HCRYPTHASH hHash; // [rsp+38h] [rbp-B9h] BYREF
  unsigned int v17; // [rsp+40h] [rbp-B1h] BYREF
  DWORD v18; // [rsp+44h] [rbp-ADh] BYREF
  HCRYPTHASH phHash; // [rsp+48h] [rbp-A9h] BYREF
  int v20; // [rsp+50h] [rbp-A1h]
  DWORD v21; // [rsp+54h] [rbp-9Dh]
  unsigned __int8 *v22; // [rsp+58h] [rbp-99h]
  BYTE v23[64]; // [rsp+60h] [rbp-91h] BYREF
  BYTE Src[64]; // [rsp+A0h] [rbp-51h] BYREF

  v22 = a1;
  v21 = a3;
  v20 = a2;
  v17 = 0;
  Algid = 0;
  pdwDataLen = 9;
  phHash = 0;
  hHash = 0;
  v18 = 0;
  if ( a1 && pbData && a10 && a8 && dwDataLen == a9 )
  {
    if ( Size < 0x10 )
      return 2147942522LL;
    AlgorithmBasedOnHashSize = GetAlgorithmBasedOnHashSize(Size, &Algid, &v17);
    if ( AlgorithmBasedOnHashSize )
      return AlgorithmBasedOnHashSize;
    if ( v17 == dwDataLen )
    {
      AlgorithmBasedOnHashSize = OpenCSP();
      if ( !AlgorithmBasedOnHashSize )
      {
        if ( CryptCreateHash(g_hCSP, Algid, 0, 0, &hHash)
          && CryptHashData(hHash, pbData, dwDataLen, 0)
          && CryptHashData(hHash, &v22[v20], v21, 0)
          && (!a4 || CryptHashData(hHash, a4, a5, 0))
          && (pdwDataLen = Size, CryptGetHashParam(hHash, 2u, v23, &pdwDataLen, 0))
          && CryptCreateHash(g_hCSP, Algid, 0, 0, &phHash)
          && CryptHashData(phHash, a8, a9, 0)
          && CryptHashData(phHash, v23, pdwDataLen, 0)
          && (v18 = Size, CryptGetHashParam(phHash, 2u, Src, &v18, 0)) )
        {
          memcpy_0(a10, Src, Size);
        }
        else
        {
          AlgorithmBasedOnHashSize = GetLastWin32Error();
        }
      }
      if ( hHash && !CryptDestroyHash(hHash) )
        AlgorithmBasedOnHashSize = GetLastWin32Error();
      if ( phHash )
      {
        if ( !CryptDestroyHash(phHash) )
          return (unsigned int)GetLastWin32Error();
      }
      return AlgorithmBasedOnHashSize;
    }
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x180050580  push    rbp
0x180050582  push    rbx
0x180050583  push    rsi
0x180050584  push    rdi
0x180050585  push    r12
0x180050587  push    r13
0x180050589  push    r14
0x18005058b  push    r15
0x18005058d  lea     rbp, [rsp-7]
0x180050592  sub     rsp, 0F8h
0x180050599  mov     rax, cs:__security_cookie
0x1800505a0  xor     rax, rsp
0x1800505a3  mov     [rbp+3Fh+var_50], rax
0x1800505a7  mov     r14, [rbp+3Fh+pbData]
0x1800505ab  mov     rax, rcx
0x1800505ae  mov     r13, [rbp+3Fh+arg_38]
0x1800505b5  mov     r15, r9
0x1800505b8  mov     r12, [rbp+3Fh+arg_48]
0x1800505bf  mov     [rsp+130h+var_D8], rcx
0x1800505c4  xor     ecx, ecx
0x1800505c6  mov     [rsp+130h+var_DC], r8d
0x1800505cb  mov     [rsp+130h+var_E0], edx
0x1800505cf  mov     [rsp+130h+var_F0], ecx
0x1800505d3  mov     [rsp+130h+Algid], ecx
0x1800505d7  mov     [rsp+130h+pdwDataLen], 9
0x1800505df  mov     [rsp+130h+var_E8], rcx
0x1800505e4  mov     [rsp+130h+hHash], rcx
0x1800505e9  mov     [rsp+130h+var_EC], ecx
0x1800505ed  test    rax, rax
0x1800505f0  jz      loc_1800507F6
0x1800505f6  test    r14, r14
0x1800505f9  jz      loc_1800507F6
0x1800505ff  test    r12, r12
0x180050602  jz      loc_1800507F6
0x180050608  test    r13, r13
0x18005060b  jz      loc_1800507F6
0x180050611  mov     esi, [rbp+3Fh+dwDataLen]
0x180050614  cmp     esi, [rbp+3Fh+arg_40]
0x18005061a  jnz     loc_1800507F6
0x180050620  mov     edi, dword ptr [rbp+3Fh+Size]
0x180050626  cmp     edi, 10h
0x180050629  jnb     short loc_180050635
0x18005062b  mov     eax, 8007007Ah
0x180050630  jmp     loc_1800507FB
0x180050635  lea     r8, [rsp+130h+var_F0]; unsigned int *
0x18005063a  mov     ecx, edi; unsigned int
0x18005063c  lea     rdx, [rsp+130h+Algid]; unsigned int *
0x180050641  call    ?GetAlgorithmBasedOnHashSize@@YAJKPEAK0@Z; GetAlgorithmBasedOnHashSize(ulong,ulong *,ulong *)
0x180050646  mov     ebx, eax
0x180050648  test    eax, eax
0x18005064a  jnz     loc_1800507F2
0x180050650  cmp     [rsp+130h+var_F0], esi
0x180050654  jnz     loc_1800507F6
0x18005065a  call    ?OpenCSP@@YAJXZ; OpenCSP(void)
0x18005065f  mov     ebx, eax
0x180050661  test    eax, eax
0x180050663  jnz     loc_1800507BC
0x180050669  mov     edx, [rsp+130h+Algid]; Algid
0x18005066d  lea     rax, [rsp+130h+hHash]
0x180050672  mov     rcx, cs:?g_hCSP@@3_KA; hProv
0x180050679  xor     r9d, r9d; dwFlags
0x18005067c  xor     r8d, r8d; hKey
0x18005067f  mov     [rsp+130h+phHash], rax; dwFlags
0x180050684  call    cs:__imp_CryptCreateHash
0x18005068a  test    eax, eax
0x18005068c  jnz     short loc_18005069A
0x18005068e  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x180050693  mov     ebx, eax
0x180050695  jmp     loc_1800507BC
0x18005069a  mov     rcx, [rsp+130h+hHash]; hHash
0x18005069f  xor     r9d, r9d; dwFlags
0x1800506a2  mov     r8d, esi; dwDataLen
0x1800506a5  mov     rdx, r14; pbData
0x1800506a8  call    cs:__imp_CryptHashData
0x1800506ae  test    eax, eax
0x1800506b0  jz      short loc_18005068E
0x1800506b2  mov     edx, [rsp+130h+var_E0]
0x1800506b6  xor     r9d, r9d; dwFlags
0x1800506b9  add     rdx, [rsp+130h+var_D8]; pbData
0x1800506be  mov     r8d, [rsp+130h+var_DC]; dwDataLen
0x1800506c3  mov     rcx, [rsp+130h+hHash]; hHash
0x1800506c8  call    cs:__imp_CryptHashData
0x1800506ce  test    eax, eax
0x1800506d0  jz      short loc_18005068E
0x1800506d2  test    r15, r15
0x1800506d5  jz      short loc_1800506F0
0x1800506d7  mov     r8d, [rbp+3Fh+arg_20]; dwDataLen
0x1800506db  xor     r9d, r9d; dwFlags
0x1800506de  mov     rcx, [rsp+130h+hHash]; hHash
0x1800506e3  mov     rdx, r15; pbData
0x1800506e6  call    cs:__imp_CryptHashData
0x1800506ec  test    eax, eax
0x1800506ee  jz      short loc_18005068E
0x1800506f0  mov     rcx, [rsp+130h+hHash]; hHash
0x1800506f5  lea     r9, [rsp+130h+pdwDataLen]; pdwDataLen
0x1800506fa  and     dword ptr [rsp+130h+phHash], 0
0x1800506ff  lea     r8, [rsp+130h+var_D0]; pbData
0x180050704  mov     esi, 2
0x180050709  mov     [rsp+130h+pdwDataLen], edi
0x18005070d  mov     edx, esi; dwParam
0x18005070f  call    cs:__imp_CryptGetHashParam
0x180050715  test    eax, eax
0x180050717  jz      loc_18005068E
0x18005071d  mov     edx, [rsp+130h+Algid]; Algid
0x180050721  lea     rax, [rsp+130h+var_E8]
0x180050726  mov     rcx, cs:?g_hCSP@@3_KA; hProv
0x18005072d  xor     r9d, r9d; dwFlags
0x180050730  xor     r8d, r8d; hKey
0x180050733  mov     [rsp+130h+phHash], rax; dwFlags
0x180050738  call    cs:__imp_CryptCreateHash
0x18005073e  test    eax, eax
0x180050740  jz      loc_18005068E
0x180050746  mov     r8d, [rbp+3Fh+arg_40]; dwDataLen
0x18005074d  xor     r9d, r9d; dwFlags
0x180050750  mov     rcx, [rsp+130h+var_E8]; hHash
0x180050755  mov     rdx, r13; pbData
0x180050758  call    cs:__imp_CryptHashData
0x18005075e  test    eax, eax
0x180050760  jz      loc_18005068E
0x180050766  mov     r8d, [rsp+130h+pdwDataLen]; dwDataLen
0x18005076b  lea     rdx, [rsp+130h+var_D0]; pbData
0x180050770  mov     rcx, [rsp+130h+var_E8]; hHash
0x180050775  xor     r9d, r9d; dwFlags
0x180050778  call    cs:__imp_CryptHashData
0x18005077e  test    eax, eax
0x180050780  jz      loc_18005068E
0x180050786  mov     rcx, [rsp+130h+var_E8]; hHash
0x18005078b  lea     r9, [rsp+130h+var_EC]; pdwDataLen
0x180050790  and     dword ptr [rsp+130h+phHash], 0
0x180050795  lea     r8, [rbp+3Fh+Src]; pbData
0x180050799  mov     edx, esi; dwParam
0x18005079b  mov     [rsp+130h+var_EC], edi
0x18005079f  call    cs:__imp_CryptGetHashParam
0x1800507a5  test    eax, eax
0x1800507a7  jz      loc_18005068E
0x1800507ad  mov     r8, rdi; Size
0x1800507b0  lea     rdx, [rbp+3Fh+Src]; Src
0x1800507b4  mov     rcx, r12; void *
0x1800507b7  call    memcpy_0
0x1800507bc  mov     rcx, [rsp+130h+hHash]; hHash
0x1800507c1  test    rcx, rcx
0x1800507c4  jz      short loc_1800507D7
0x1800507c6  call    cs:__imp_CryptDestroyHash
0x1800507cc  test    eax, eax
0x1800507ce  jnz     short loc_1800507D7
0x1800507d0  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x1800507d5  mov     ebx, eax
0x1800507d7  mov     rcx, [rsp+130h+var_E8]; hHash
0x1800507dc  test    rcx, rcx
0x1800507df  jz      short loc_1800507F2
0x1800507e1  call    cs:__imp_CryptDestroyHash
0x1800507e7  test    eax, eax
0x1800507e9  jnz     short loc_1800507F2
0x1800507eb  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x1800507f0  mov     ebx, eax
0x1800507f2  mov     eax, ebx
0x1800507f4  jmp     short loc_1800507FB
0x1800507f6  mov     eax, 80070057h
0x1800507fb  mov     rcx, [rbp+3Fh+var_50]
0x1800507ff  xor     rcx, rsp; StackCookie
0x180050802  call    __security_check_cookie
0x180050807  add     rsp, 0F8h
0x18005080e  pop     r15
0x180050810  pop     r14
0x180050812  pop     r13
0x180050814  pop     r12
0x180050816  pop     rdi
0x180050817  pop     rsi
0x180050818  pop     rbx
0x180050819  pop     rbp
0x18005081a  retn
```
