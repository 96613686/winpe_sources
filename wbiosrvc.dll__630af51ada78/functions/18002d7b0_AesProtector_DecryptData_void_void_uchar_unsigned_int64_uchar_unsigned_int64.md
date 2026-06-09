# AesProtector::DecryptData(void *,void *,uchar *,unsigned __int64,uchar * *,unsigned __int64 *)

- ea: `0x18002d7b0`
- end: `0x18002da30`
- name: `?DecryptData@AesProtector@@AEAAJPEAX0PEAE_KPEAPEAEPEA_K@Z`
- size: `640`
- prototype: `int __fastcall(AesProtector *this, void *, void *, unsigned __int8 *, unsigned __int64 pcbResult, unsigned __int8 **, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002d6a0`

## callees

- `0x18002c420`
- `0x18002d7b0`
- `0x18002dd70`
- `0x18002ddb0`
- `0x180069cc8`
- `0x18006b0b5`
- `0x1800d2010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18002d9be`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18002d9be`
- `bcrypt!BCryptDecrypt` at `0x18002d8e0`
- `bcrypt!BCryptDecrypt` at `0x18002d960`
- `bcrypt!BCryptDecrypt` at `0x18002d8e0`
- `bcrypt!BCryptDecrypt` at `0x18002d960`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int __fastcall AesProtector::DecryptData(
        AesProtector *this,
        void *a2,
        void *a3,
        unsigned __int8 *a4,
        unsigned __int64 pcbResult,
        unsigned __int8 **a6,
        unsigned __int64 *a7)
{
  unsigned int v11; // r9d
  unsigned int v12; // ecx
  unsigned int v13; // ebx
  unsigned int v14; // ebx
  __int64 v15; // r8
  NTSTATUS v16; // eax
  NTSTATUS v17; // ecx
  int result; // eax
  UCHAR *pbOutput; // rdi
  ULONG v20; // r8d
  NTSTATUS v21; // eax
  AesProtector *v22; // rcx
  int v23; // ebx
  unsigned __int8 *v24; // rax
  unsigned __int8 *v25; // rsi
  unsigned __int64 *v26; // rax
  _DWORD pPaddingInfo[2]; // [rsp+50h] [rbp-41h] BYREF
  unsigned __int8 *v28; // [rsp+58h] [rbp-39h]
  int v29; // [rsp+60h] [rbp-31h]
  unsigned __int8 *v30; // [rsp+68h] [rbp-29h]
  int v31; // [rsp+70h] [rbp-21h]
  unsigned __int8 *v32; // [rsp+78h] [rbp-19h]
  unsigned int v33; // [rsp+80h] [rbp-11h]
  int v34; // [rsp+A0h] [rbp+Fh]
  ULONG v35; // [rsp+F8h] [rbp+67h] BYREF

  if ( pcbResult < 0x14 )
    return -2147024883;
  v11 = *((_DWORD *)a4 + 1) + *((_DWORD *)a4 + 3);
  if ( v11 < *((_DWORD *)a4 + 1) )
    return -2147024883;
  v12 = v11 + *((_DWORD *)a4 + 4);
  if ( v12 < v11 )
    return -2147024883;
  if ( v12 > pcbResult )
    return -2147024883;
  v13 = *(_DWORD *)a4;
  if ( __PAIR64__(*((_DWORD *)a4 + 1), v13) != ((*(unsigned int (__fastcall **)(AesProtector *))(*(_QWORD *)this + 24LL))(this)
                                              | 0x2000000000LL) )
    return -2147024883;
  if ( *((_DWORD *)a4 + 2) != 12 )
    return -2147024883;
  v14 = *((_DWORD *)a4 + 4);
  if ( v14 > *((_DWORD *)this + 7) )
    return -2147024883;
  LODWORD(pcbResult) = 0;
  memset_0(pPaddingInfo, 0, 0x58u);
  v15 = *((unsigned int *)a4 + 3);
  v28 = a4 + 20;
  pPaddingInfo[0] = 88;
  pPaddingInfo[1] = 1;
  v32 = &a4[v15 + 32];
  v30 = a4;
  v31 = 32;
  v29 = 12;
  v33 = v14;
  v34 = 0;
  v16 = BCryptDecrypt(a2, a4 + 32, v15, pPaddingInfo, 0, 0, 0, 0, (ULONG *)&pcbResult, 0);
  v17 = v16;
  if ( v16 >= 0 )
  {
    pbOutput = (UCHAR *)AesProtector::MemAllocate((AesProtector *)(unsigned int)v16, (unsigned int)pcbResult);
    if ( pbOutput )
    {
      v20 = *((_DWORD *)a4 + 3);
      v35 = 0;
      v21 = BCryptDecrypt(a2, a4 + 32, v20, pPaddingInfo, 0, 0, pbOutput, pcbResult, &v35, 0);
      v22 = (AesProtector *)(unsigned int)pcbResult;
      if ( v21 < 0 )
      {
        if ( v21 == -1073700862 )
          v23 = -2146860986;
        else
          v23 = v21 | 0x10000000;
      }
      else
      {
        v23 = 0;
        if ( v35 == (_DWORD)pcbResult
          && (unsigned int)pcbResult >= 0x48
          && *((_DWORD *)pbOutput + 17) < 0xFFFFFFB8
          && *((_DWORD *)pbOutput + 17) + 72 <= (unsigned int)pcbResult )
        {
          if ( EqualSid(a3, pbOutput) )
          {
            v24 = (unsigned __int8 *)MIDL_user_allocate(*((unsigned int *)pbOutput + 17));
            v25 = v24;
            if ( v24 )
            {
              memcpy_0(v24, pbOutput + 72, *((unsigned int *)pbOutput + 17));
              v26 = a7;
              *a6 = v25;
              *v26 = *((unsigned int *)pbOutput + 17);
            }
            else
            {
              v23 = -2147024882;
            }
          }
          else
          {
            v23 = -2147024891;
          }
          v22 = (AesProtector *)(unsigned int)pcbResult;
        }
        else
        {
          v23 = -2147024883;
        }
      }
      AesProtector::MemZeroAndRelease(v22, pbOutput, (unsigned int)v22);
      return v23;
    }
    else
    {
      return -2147024882;
    }
  }
  else
  {
    result = v16 | 0x10000000;
    if ( v17 == -1073700862 )
      return -2146860986;
  }
  return result;
}

```

## disassembly

```asm
0x18002d7b0  mov     [rsp-8+arg_0], rbx
0x18002d7b5  mov     [rsp-8+arg_8], rsi
0x18002d7ba  push    rbp
0x18002d7bb  push    rdi
0x18002d7bc  push    r12
0x18002d7be  push    r14
0x18002d7c0  push    r15
0x18002d7c2  lea     rbp, [rsp-1Fh]
0x18002d7c7  sub     rsp, 0B0h
0x18002d7ce  cmp     [rbp+3Fh+arg_20], 14h
0x18002d7d3  mov     rsi, r9
0x18002d7d6  mov     r12, r8
0x18002d7d9  mov     r14, rdx
0x18002d7dc  mov     rdi, rcx
0x18002d7df  jb      loc_18002DA0F
0x18002d7e5  mov     r9d, [r9+0Ch]
0x18002d7e9  add     r9d, [rsi+4]
0x18002d7ed  cmp     r9d, [rsi+4]
0x18002d7f1  jb      loc_18002DA0F
0x18002d7f7  mov     ecx, [rsi+10h]
0x18002d7fa  add     ecx, r9d
0x18002d7fd  cmp     ecx, r9d
0x18002d800  jb      loc_18002DA0F
0x18002d806  mov     eax, ecx
0x18002d808  cmp     rax, [rbp+3Fh+arg_20]
0x18002d80c  ja      loc_18002DA0F
0x18002d812  mov     rax, [rdi]
0x18002d815  mov     rcx, rdi
0x18002d818  mov     ebx, [rsi]
0x18002d81a  mov     rax, [rax+18h]
0x18002d81e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d823  cmp     ebx, eax
0x18002d825  jnz     loc_18002DA0F
0x18002d82b  cmp     dword ptr [rsi+4], 20h ; ' '
0x18002d82f  jnz     loc_18002DA0F
0x18002d835  cmp     dword ptr [rsi+8], 0Ch
0x18002d839  jnz     loc_18002DA0F
0x18002d83f  mov     ebx, [rsi+10h]
0x18002d842  cmp     ebx, [rdi+1Ch]
0x18002d845  ja      loc_18002DA0F
0x18002d84b  mov     edi, 58h ; 'X'
0x18002d850  mov     dword ptr [rbp+3Fh+arg_20], 0
0x18002d857  mov     r8d, edi; Size
0x18002d85a  lea     rcx, [rbp+3Fh+pPaddingInfo]; void *
0x18002d85e  xor     edx, edx; Val
0x18002d860  lea     r15, [rsi+20h]
0x18002d864  call    memset_0
0x18002d869  mov     r8d, [rsi+0Ch]; cbInput
0x18002d86d  lea     rax, [rsi+14h]
0x18002d871  mov     [rsp+0D0h+dwFlags], 0; dwFlags
0x18002d879  lea     r9, [rbp+3Fh+pPaddingInfo]; pPaddingInfo
0x18002d87d  mov     [rbp+3Fh+var_78], rax
0x18002d881  mov     rdx, r15; pbInput
0x18002d884  mov     rcx, r14; hKey
0x18002d887  mov     [rbp+3Fh+pPaddingInfo], edi
0x18002d88a  lea     rax, [r15+r8]
0x18002d88e  mov     [rbp+3Fh+var_7C], 1
0x18002d895  mov     [rbp+3Fh+var_58], rax
0x18002d899  lea     rax, [rbp+3Fh+arg_20]
0x18002d89d  mov     [rsp+0D0h+pcbResult], rax; pcbResult
0x18002d8a2  mov     [rsp+0D0h+cbOutput], 0; cbOutput
0x18002d8aa  mov     [rsp+0D0h+pbOutput], 0; pbOutput
0x18002d8b3  mov     [rsp+0D0h+cbIV], 0; cbIV
0x18002d8bb  mov     [rsp+0D0h+pbIV], 0; pbIV
0x18002d8c4  mov     [rbp+3Fh+var_68], rsi
0x18002d8c8  mov     [rbp+3Fh+var_60], 20h ; ' '
0x18002d8cf  mov     [rbp+3Fh+var_70], 0Ch
0x18002d8d6  mov     [rbp+3Fh+var_50], ebx
0x18002d8d9  mov     [rbp+3Fh+var_30], 0
0x18002d8e0  call    cs:__imp_BCryptDecrypt
0x18002d8e6  mov     ecx, eax; this
0x18002d8e8  test    eax, eax
0x18002d8ea  jns     short loc_18002D903
0x18002d8ec  bts     eax, 1Ch
0x18002d8f0  mov     ebx, 80098046h
0x18002d8f5  cmp     ecx, 0C000A002h
0x18002d8fb  cmovz   eax, ebx
0x18002d8fe  jmp     loc_18002DA14
0x18002d903  mov     edx, dword ptr [rbp+3Fh+arg_20]; unsigned __int64
0x18002d906  call    ?MemAllocate@AesProtector@@AEAAPEAX_K@Z; AesProtector::MemAllocate(unsigned __int64)
0x18002d90b  mov     rdi, rax
0x18002d90e  test    rax, rax
0x18002d911  jnz     short loc_18002D91D
0x18002d913  mov     eax, 8007000Eh
0x18002d918  jmp     loc_18002DA14
0x18002d91d  mov     r8d, [rsi+0Ch]; cbInput
0x18002d921  lea     rax, [rbp+3Fh+arg_18]
0x18002d925  mov     [rsp+0D0h+dwFlags], 0; dwFlags
0x18002d92d  lea     r9, [rbp+3Fh+pPaddingInfo]; pPaddingInfo
0x18002d931  mov     [rsp+0D0h+pcbResult], rax; pcbResult
0x18002d936  mov     rdx, r15; pbInput
0x18002d939  mov     eax, dword ptr [rbp+3Fh+arg_20]
0x18002d93c  mov     rcx, r14; hKey
0x18002d93f  mov     [rsp+0D0h+cbOutput], eax; cbOutput
0x18002d943  mov     [rsp+0D0h+pbOutput], rdi; pbOutput
0x18002d948  mov     [rsp+0D0h+cbIV], 0; cbIV
0x18002d950  mov     [rsp+0D0h+pbIV], 0; pbIV
0x18002d959  mov     [rbp+3Fh+arg_18], 0
0x18002d960  call    cs:__imp_BCryptDecrypt
0x18002d966  mov     ecx, dword ptr [rbp+3Fh+arg_20]; this
0x18002d969  mov     ebx, eax
0x18002d96b  test    eax, eax
0x18002d96d  js      short loc_18002D98D
0x18002d96f  xor     ebx, ebx
0x18002d971  cmp     [rbp+3Fh+arg_18], ecx
0x18002d974  jz      short loc_18002D9A4
0x18002d976  mov     ebx, 8007000Dh
0x18002d97b  mov     r8d, ecx; unsigned __int64
0x18002d97e  mov     rdx, rdi; void *
0x18002d981  call    ?MemZeroAndRelease@AesProtector@@AEAAXPEAX_K@Z; AesProtector::MemZeroAndRelease(void *,unsigned __int64)
0x18002d986  mov     eax, ebx
0x18002d988  jmp     loc_18002DA14
0x18002d98d  cmp     ebx, 0C000A002h
0x18002d993  jnz     short loc_18002D99C
0x18002d995  mov     ebx, 80098046h
0x18002d99a  jmp     short loc_18002D97B
0x18002d99c  or      ebx, 10000000h
0x18002d9a2  jl      short loc_18002D97B
0x18002d9a4  cmp     ecx, 48h ; 'H'
0x18002d9a7  jb      short loc_18002D976
0x18002d9a9  mov     eax, [rdi+44h]
0x18002d9ac  add     eax, 48h ; 'H'
0x18002d9af  cmp     eax, 48h ; 'H'
0x18002d9b2  jb      short loc_18002D976
0x18002d9b4  cmp     eax, ecx
0x18002d9b6  ja      short loc_18002D976
0x18002d9b8  mov     rdx, rdi; pSid2
0x18002d9bb  mov     rcx, r12; pSid1
0x18002d9be  call    cs:__imp_EqualSid
0x18002d9c4  test    eax, eax
0x18002d9c6  jz      short loc_18002DA08
0x18002d9c8  mov     ecx, [rdi+44h]; size
0x18002d9cb  call    MIDL_user_allocate
0x18002d9d0  mov     rsi, rax
0x18002d9d3  test    rax, rax
0x18002d9d6  jz      short loc_18002D9FB
0x18002d9d8  mov     r8d, [rdi+44h]; Size
0x18002d9dc  lea     rdx, [rdi+48h]; Src
0x18002d9e0  mov     rcx, rax; void *
0x18002d9e3  call    memcpy_0
0x18002d9e8  mov     rcx, [rbp+3Fh+arg_28]
0x18002d9ec  mov     rax, [rbp+3Fh+arg_30]
0x18002d9f0  mov     [rcx], rsi
0x18002d9f3  mov     ecx, [rdi+44h]
0x18002d9f6  mov     [rax], rcx
0x18002d9f9  jmp     short loc_18002DA00
0x18002d9fb  mov     ebx, 8007000Eh
0x18002da00  mov     ecx, dword ptr [rbp+3Fh+arg_20]
0x18002da03  jmp     loc_18002D97B
0x18002da08  mov     ebx, 80070005h
0x18002da0d  jmp     short loc_18002DA00
0x18002da0f  mov     eax, 8007000Dh
0x18002da14  lea     r11, [rsp+0D0h+var_20]
0x18002da1c  mov     rbx, [r11+30h]
0x18002da20  mov     rsi, [r11+38h]
0x18002da24  mov     rsp, r11
0x18002da27  pop     r15
0x18002da29  pop     r14
0x18002da2b  pop     r12
0x18002da2d  pop     rdi
0x18002da2e  pop     rbp
0x18002da2f  retn
```
