# _anonymous_namespace_::StartHash

- ea: `0x18006573c`
- end: `0x1800659b6`
- name: `_anonymous_namespace_::StartHash`
- size: `634`
- prototype: `__int64 __fastcall(BCRYPT_ALG_HANDLE *phAlgorithm)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180065b1c`

## callees

- `0x1800112d0`
- `0x180011534`
- `0x18006573c`
- `0x180065bf0`
- `0x180065cfc`
- `0x1800dd930`
- `0x1800e46b0`
- `0x1800e4a70`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006579f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800658e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006579f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800658e4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800657b4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800658f7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800657b4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800658f7`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800657cd`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800657cd`
- `bcrypt!BCryptGetProperty` at `0x180065809`
- `bcrypt!BCryptGetProperty` at `0x180065809`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800657ac`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800657ac`
- `bcrypt!BCryptCreateHash` at `0x18006591c`
- `bcrypt!BCryptCreateHash` at `0x18006591c`
- `bcrypt!BCryptDestroyHash` at `0x1800658ef`
- `bcrypt!BCryptDestroyHash` at `0x1800658ef`

## string_xrefs

- `0x1800659a4`: `C:\__w\1\s\src\orchestrator\system\windows\common\Hash.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
BCRYPT_ALG_HANDLE *__fastcall anonymous_namespace_::StartHash(BCRYPT_ALG_HANDLE *phAlgorithm)
{
  BCRYPT_ALG_HANDLE *v2; // r12
  BCRYPT_ALG_HANDLE *v3; // r14
  BCRYPT_ALG_HANDLE v4; // rdi
  DWORD LastError; // ebx
  NTSTATUS v6; // eax
  unsigned int v7; // r8d
  NTSTATUS Property; // eax
  unsigned int v9; // r8d
  ULONG v10; // ebp
  __int64 v11; // rdi
  _BYTE *v12; // rax
  _BYTE *v13; // rbx
  unsigned __int64 v14; // r15
  char *v15; // rax
  unsigned __int64 v16; // rcx
  unsigned __int64 v17; // rdx
  size_t v18; // rbp
  _QWORD *v19; // rbx
  UCHAR *v20; // r14
  BCRYPT_HASH_HANDLE v21; // rdi
  DWORD v22; // ebx
  NTSTATUS Hash; // eax
  unsigned int v24; // r8d
  int pcbResult; // [rsp+20h] [rbp-68h]
  int pcbResulta; // [rsp+20h] [rbp-68h]
  int pcbResultb; // [rsp+20h] [rbp-68h]
  UCHAR pbOutput[4]; // [rsp+50h] [rbp-38h] BYREF
  ULONG v30; // [rsp+54h] [rbp-34h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  *phAlgorithm = 0;
  v2 = phAlgorithm + 1;
  phAlgorithm[1] = 0;
  v3 = phAlgorithm + 2;
  phAlgorithm[2] = 0;
  phAlgorithm[3] = 0;
  phAlgorithm[4] = 0;
  v4 = *phAlgorithm;
  if ( *phAlgorithm )
  {
    LastError = GetLastError();
    BCryptCloseAlgorithmProvider(v4, 0);
    SetLastError(LastError);
  }
  *phAlgorithm = 0;
  v6 = BCryptOpenAlgorithmProvider(phAlgorithm, L"SHA256", 0, 0);
  if ( v6 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(retaddr, (void *)0x4D, v7, (const char *)(unsigned int)v6, pcbResult);
  *(_DWORD *)pbOutput = 0;
  v30 = 0;
  Property = BCryptGetProperty(*phAlgorithm, L"ObjectLength", pbOutput, 4u, &v30, 0);
  if ( Property < 0 )
    wil::details::in1diag3::_Throw_NtStatus(retaddr, (void *)0x51, v9, (const char *)(unsigned int)Property, pcbResulta);
  v10 = *(_DWORD *)pbOutput;
  if ( !*(_DWORD *)pbOutput )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x52,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\Hash.cpp",
      (const char *)0x8000FFFFLL,
      pcbResulta);
  v11 = *(unsigned int *)pbOutput;
  v12 = *v3;
  v13 = v3[1];
  v14 = v13 - (_BYTE *)*v3;
  if ( *(unsigned int *)pbOutput < v14 )
  {
    v15 = &v12[*(unsigned int *)pbOutput];
LABEL_15:
    v3[1] = v15;
    goto LABEL_16;
  }
  if ( *(unsigned int *)pbOutput <= v14 )
    goto LABEL_16;
  v16 = (_BYTE *)v3[2] - v12;
  if ( *(unsigned int *)pbOutput <= v16 )
  {
    memset(v3[1], 0, *(unsigned int *)pbOutput - v14);
    v15 = &v13[v10 - v14];
    v10 = *(_DWORD *)pbOutput;
    goto LABEL_15;
  }
  v17 = v16 >> 1;
  v18 = 0x7FFFFFFFFFFFFFFFLL;
  if ( v16 <= 0x7FFFFFFFFFFFFFFFLL - (v16 >> 1) )
  {
    v18 = v16 + v17;
    if ( v16 + v17 < *(unsigned int *)pbOutput )
      v18 = *(unsigned int *)pbOutput;
  }
  v19 = std::_Allocate<16,std::_Default_allocate_traits>(v18);
  memset((char *)v19 + v14, 0, v11 - v14);
  memmove(v19, *v3, (_BYTE *)v3[1] - (_BYTE *)*v3);
  std::vector<unsigned char>::_Change_array(v3, v19, v11, v18);
  v10 = *(_DWORD *)pbOutput;
LABEL_16:
  v20 = (UCHAR *)*v3;
  v21 = *v2;
  if ( *v2 )
  {
    v22 = GetLastError();
    BCryptDestroyHash(v21);
    SetLastError(v22);
  }
  *v2 = 0;
  Hash = BCryptCreateHash(*phAlgorithm, v2, v20, v10, 0, 0, 0);
  if ( Hash < 0 )
    wil::details::in1diag3::_Throw_NtStatus(retaddr, (void *)0x55, v24, (const char *)(unsigned int)Hash, pcbResultb);
  return phAlgorithm;
}

```

## disassembly

```asm
0x18006573c  mov     r11, rsp
0x18006573f  mov     [r11+10h], rbx
0x180065743  mov     [r11+18h], rbp
0x180065747  mov     [r11+20h], rsi
0x18006574b  push    rdi
0x18006574c  push    r12
0x18006574e  push    r13
0x180065750  push    r14
0x180065752  push    r15
0x180065754  sub     rsp, 60h
0x180065758  mov     rax, cs:__security_cookie
0x18006575f  xor     rax, rsp
0x180065762  mov     [rsp+88h+var_30], rax
0x180065767  mov     rsi, rcx
0x18006576a  mov     [r11-40h], rcx
0x18006576e  xor     r13d, r13d
0x180065771  mov     [r11-48h], r13d
0x180065775  mov     [rcx], r13
0x180065778  lea     r12, [rcx+8]
0x18006577c  mov     [r12], r13
0x180065780  lea     r14, [rcx+10h]
0x180065784  mov     [r14], r13
0x180065787  mov     [r14+8], r13
0x18006578b  mov     [r14+10h], r13
0x18006578f  mov     [rsp+88h+var_48], 1
0x180065797  mov     rdi, [rcx]
0x18006579a  test    rdi, rdi
0x18006579d  jz      short loc_1800657BA
0x18006579f  call    cs:__imp_GetLastError
0x1800657a5  mov     ebx, eax
0x1800657a7  xor     edx, edx; dwFlags
0x1800657a9  mov     rcx, rdi; hAlgorithm
0x1800657ac  call    cs:__imp_BCryptCloseAlgorithmProvider
0x1800657b2  mov     ecx, ebx; dwErrCode
0x1800657b4  call    cs:__imp_SetLastError
0x1800657ba  mov     [rsi], r13
0x1800657bd  xor     r9d, r9d; dwFlags
0x1800657c0  xor     r8d, r8d; pszImplementation
0x1800657c3  lea     rdx, pszAlgId; "SHA256"
0x1800657ca  mov     rcx, rsi; phAlgorithm
0x1800657cd  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1800657d3  test    eax, eax
0x1800657d5  js      loc_18006596A
0x1800657db  mov     dword ptr [rsp+88h+pbOutput], r13d
0x1800657e0  mov     [rsp+88h+var_34], r13d
0x1800657e5  mov     [rsp+88h+dwFlags], r13d; dwFlags
0x1800657ea  lea     rax, [rsp+88h+var_34]
0x1800657ef  mov     [rsp+88h+pcbResult], rax; int
0x1800657f4  mov     r9d, 4; cbOutput
0x1800657fa  lea     r8, [rsp+88h+pbOutput]; pbOutput
0x1800657ff  lea     rdx, pszProperty; "ObjectLength"
0x180065806  mov     rcx, [rsi]; hObject
0x180065809  call    cs:__imp_BCryptGetProperty
0x18006580f  test    eax, eax
0x180065811  js      loc_180065980
0x180065817  mov     ebp, dword ptr [rsp+88h+pbOutput]
0x18006581b  test    ebp, ebp
0x18006581d  jz      loc_180065996
0x180065823  mov     edi, ebp
0x180065825  mov     rax, [r14]
0x180065828  mov     rbx, [r14+8]
0x18006582c  mov     r15, rbx
0x18006582f  sub     r15, rax
0x180065832  cmp     rbp, r15
0x180065835  jnb     short loc_18006583F
0x180065837  add     rax, rbp
0x18006583a  jmp     loc_1800658D4
0x18006583f  jbe     loc_1800658D8
0x180065845  mov     rcx, [r14+10h]
0x180065849  sub     rcx, rax
0x18006584c  cmp     rdi, rcx
0x18006584f  jbe     short loc_1800658BC
0x180065851  mov     rdx, rcx
0x180065854  shr     rdx, 1
0x180065857  mov     rbp, 7FFFFFFFFFFFFFFFh
0x180065861  mov     rax, rbp
0x180065864  sub     rax, rdx
0x180065867  cmp     rcx, rax
0x18006586a  ja      short loc_180065877
0x18006586c  lea     rbp, [rcx+rdx]
0x180065870  cmp     rbp, rdi
0x180065873  cmovb   rbp, rdi
0x180065877  mov     rcx, rbp
0x18006587a  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18006587f  mov     rbx, rax
0x180065882  mov     r8, rdi
0x180065885  sub     r8, r15; Size
0x180065888  lea     rcx, [r15+rax]; void *
0x18006588c  xor     edx, edx; Val
0x18006588e  call    memset
0x180065893  mov     r8, [r14+8]
0x180065897  sub     r8, [r14]; Size
0x18006589a  mov     rdx, [r14]; Src
0x18006589d  mov     rcx, rbx; void *
0x1800658a0  call    memmove
0x1800658a5  mov     r9, rbp
0x1800658a8  mov     r8, rdi
0x1800658ab  mov     rdx, rbx
0x1800658ae  mov     rcx, r14
0x1800658b1  call    ?_Change_array@?$vector@EV?$allocator@E@std@@@std@@AEAAXQEAE_K1@Z; std::vector<uchar>::_Change_array(uchar * const,unsigned __int64,unsigned __int64)
0x1800658b6  mov     ebp, dword ptr [rsp+88h+pbOutput]
0x1800658ba  jmp     short loc_1800658D8
0x1800658bc  sub     rdi, r15
0x1800658bf  mov     r8, rdi; Size
0x1800658c2  xor     edx, edx; Val
0x1800658c4  mov     rcx, rbx; void *
0x1800658c7  call    memset
0x1800658cc  lea     rax, [rdi+rbx]
0x1800658d0  mov     ebp, dword ptr [rsp+88h+pbOutput]
0x1800658d4  mov     [r14+8], rax
0x1800658d8  mov     r14, [r14]
0x1800658db  mov     rdi, [r12]
0x1800658df  test    rdi, rdi
0x1800658e2  jz      short loc_1800658FD
0x1800658e4  call    cs:__imp_GetLastError
0x1800658ea  mov     ebx, eax
0x1800658ec  mov     rcx, rdi; hHash
0x1800658ef  call    cs:__imp_BCryptDestroyHash
0x1800658f5  mov     ecx, ebx; dwErrCode
0x1800658f7  call    cs:__imp_SetLastError
0x1800658fd  mov     [r12], r13
0x180065901  mov     [rsp+88h+var_58], r13d; dwFlags
0x180065906  mov     [rsp+88h+dwFlags], r13d; cbSecret
0x18006590b  mov     [rsp+88h+pcbResult], r13; int
0x180065910  mov     r9d, ebp; cbHashObject
0x180065913  mov     r8, r14; pbHashObject
0x180065916  mov     rdx, r12; phHash
0x180065919  mov     rcx, [rsi]; hAlgorithm
0x18006591c  call    cs:__imp_BCryptCreateHash
0x180065922  test    eax, eax
0x180065924  js      short loc_180065954
0x180065926  mov     rax, rsi
0x180065929  mov     rcx, [rsp+88h+var_30]
0x18006592e  xor     rcx, rsp; StackCookie
0x180065931  call    __security_check_cookie
0x180065936  lea     r11, [rsp+88h+var_28]
0x18006593b  mov     rbx, [r11+38h]
0x18006593f  mov     rbp, [r11+40h]
0x180065943  mov     rsi, [r11+48h]
0x180065947  mov     rsp, r11
0x18006594a  pop     r15
0x18006594c  pop     r14
0x18006594e  pop     r13
0x180065950  pop     r12
0x180065952  pop     rdi
0x180065953  retn
0x180065954  mov     rcx, [rsp+88h]; this
0x18006595c  mov     r9d, eax; char *
0x18006595f  mov     edx, 55h ; 'U'; void *
0x180065964  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x18006596a  mov     rcx, [rsp+88h]; this
0x180065972  mov     r9d, eax; char *
0x180065975  mov     edx, 4Dh ; 'M'; void *
0x18006597a  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x180065980  mov     rcx, [rsp+88h]; this
0x180065988  mov     r9d, eax; char *
0x18006598b  mov     edx, 51h ; 'Q'; void *
0x180065990  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x180065996  mov     rcx, [rsp+88h]; this
0x18006599e  mov     r9d, 8000FFFFh; char *
0x1800659a4  lea     r8, aCW1SSrcOrchest_6; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x1800659ab  mov     edx, 52h ; 'R'; void *
0x1800659b0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
