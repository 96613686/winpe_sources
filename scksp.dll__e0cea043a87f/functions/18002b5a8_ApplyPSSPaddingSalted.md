# ApplyPSSPaddingSalted

- ea: `0x18002b5a8`
- end: `0x18002b830`
- name: `ApplyPSSPaddingSalted`
- size: `648`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18002b838`

## callees

- `0x180009e76`
- `0x180009e82`
- `0x18002b5a8`
- `0x18002be40`
- `0x18002c048`
- `0x18002c068`
- `0x18002c428`

## import_xrefs

- `bcrypt!BCryptGenRandom` at `0x18002b67c`
- `bcrypt!BCryptGenRandom` at `0x18002b67c`
- `bcrypt!BCryptFinishHash` at `0x18002b724`
- `bcrypt!BCryptFinishHash` at `0x18002b724`
- `bcrypt!BCryptDestroyHash` at `0x18002b803`
- `bcrypt!BCryptDestroyHash` at `0x18002b803`
- `bcrypt!BCryptHashData` at `0x18002b6ed`
- `bcrypt!BCryptHashData` at `0x18002b6ed`
- `bcrypt!BCryptCreateHash` at `0x18002b6b7`
- `bcrypt!BCryptCreateHash` at `0x18002b6b7`

## pseudocode

```c
__int64 __fastcall ApplyPSSPaddingSalted(
        void *a1,
        ULONG a2,
        unsigned int a3,
        __int64 a4,
        ULONG cbBuffer,
        void *Src,
        size_t Size,
        _BYTE *a8,
        ULONG a9)
{
  size_t v9; // r12
  ULONG v11; // r13d
  __int64 v12; // rdi
  NTSTATUS v13; // ebx
  size_t v14; // rbx
  unsigned int v15; // esi
  __int64 v16; // rax
  __int64 v17; // rdx
  __int64 v18; // r8
  UCHAR *v19; // r14
  __int64 v20; // rcx
  __int64 v21; // r9
  void *v22; // rdx
  UCHAR *v23; // rbp
  NTSTATUS v24; // eax
  _BYTE *v25; // rbp
  size_t v26; // rbx
  char *v27; // rdi
  __int64 i; // rdx
  UCHAR *v30; // [rsp+40h] [rbp-58h]
  UCHAR *v31; // [rsp+40h] [rbp-58h]
  UCHAR *v32; // [rsp+48h] [rbp-50h]
  UCHAR *v33; // [rsp+58h] [rbp-40h]
  BCRYPT_HASH_HANDLE phHash; // [rsp+B8h] [rbp+20h] BYREF

  v9 = cbBuffer;
  v11 = a9;
  phHash = 0;
  v12 = a3;
  if ( a9 < a2 + cbBuffer + 2 )
    return (unsigned int)-2146893822;
  v14 = (unsigned int)Size;
  v15 = a9 - a2 - 1;
  v16 = MSCryptAlloc(a3 + cbBuffer + (_DWORD)Size + 8 + 2 * v15);
  v19 = (UCHAR *)v16;
  if ( v16 )
  {
    v22 = Src;
    v23 = (UCHAR *)(v16 + v12);
    v30 = v23;
    *(_QWORD *)v23 = 0;
    memcpy_0((void *)(v16 + v12 + 8), v22, v14);
    v32 = &v23[v14 + 8];
    v13 = BCryptGenRandom(0, v32, v9, 2u);
    if ( v13 >= 0 )
    {
      v24 = BCryptCreateHash(a1, &phHash, v19, v12, 0, 0, 0);
      v13 = v24;
      if ( v24 >= 0 )
      {
        v24 = BCryptHashData(phHash, v23, v9 + Size + 8, 0);
        v13 = v24;
        if ( v24 >= 0 )
        {
          v25 = a8;
          v33 = &a8[v15];
          v24 = BCryptFinishHash(phHash, v33, a2, 0);
          v13 = v24;
          if ( v24 >= 0 )
          {
            v31 = &v30[(unsigned int)(v9 + Size + 8)];
            v26 = v15 - (unsigned int)v9 - 1;
            memset_0(v31, 0, v26);
            v31[v26] = 1;
            memcpy_0(&v31[v26 + 1], v32, v9);
            v27 = (char *)&v31[v15];
            v24 = MaskGeneration(a1, a2, a3, v33, a2, v27, v11 - a2 - 1);
            v13 = v24;
            if ( v24 >= 0 )
            {
              for ( i = 0; (unsigned int)i < v15; i = (unsigned int)(i + 1) )
                v25[i] = v31[i] ^ v27[i];
              *v25 &= ~0x80u;
              v25[v11 - 1] = -68;
              v13 = 0;
              goto LABEL_20;
            }
            v21 = 1024;
          }
          else
          {
            v21 = 1005;
          }
        }
        else
        {
          v21 = 995;
        }
      }
      else
      {
        v21 = 985;
      }
      v20 = (unsigned int)v24;
    }
    else
    {
      v21 = 965;
      v20 = (unsigned int)v13;
    }
  }
  else
  {
    v13 = -1073741801;
    v20 = 3221225495LL;
    v21 = 944;
  }
  DebugTraceError(v20, v17, v18, v21);
LABEL_20:
  if ( phHash )
    BCryptDestroyHash(phHash);
  if ( v19 )
    MSCryptFree(v19);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18002b5a8  mov     rax, rsp
0x18002b5ab  mov     [rax+10h], rbx
0x18002b5af  mov     [rax+20h], r9
0x18002b5b3  mov     [rax+18h], r8d
0x18002b5b7  mov     [rax+8], rcx
0x18002b5bb  push    rbp
0x18002b5bc  push    rsi
0x18002b5bd  push    rdi
0x18002b5be  push    r12
0x18002b5c0  push    r13
0x18002b5c2  push    r14
0x18002b5c4  push    r15
0x18002b5c6  sub     rsp, 60h
0x18002b5ca  mov     r12d, [rsp+98h+cbBuffer]
0x18002b5d2  mov     r15d, edx
0x18002b5d5  mov     r13d, [rsp+98h+arg_40]
0x18002b5dd  mov     qword ptr [rax+20h], 0
0x18002b5e5  mov     edi, r8d
0x18002b5e8  lea     eax, [r12+2]
0x18002b5ed  add     eax, edx
0x18002b5ef  cmp     r13d, eax
0x18002b5f2  jnb     short loc_18002B5FE
0x18002b5f4  mov     ebx, 80090002h
0x18002b5f9  jmp     loc_18002B816
0x18002b5fe  mov     ebx, dword ptr [rsp+98h+Size]
0x18002b605  mov     esi, r13d
0x18002b608  sub     esi, r15d
0x18002b60b  dec     esi
0x18002b60d  lea     eax, [rbx+8]
0x18002b610  add     eax, r12d
0x18002b613  lea     ecx, [rax+rsi*2]
0x18002b616  add     ecx, edi
0x18002b618  call    MSCryptAlloc
0x18002b61d  mov     r14, rax
0x18002b620  test    rax, rax
0x18002b623  jnz     short loc_18002B63F
0x18002b625  mov     ebx, 0C0000017h
0x18002b62a  mov     ecx, 0C0000017h
0x18002b62f  mov     r9d, 3B0h
0x18002b635  call    DebugTraceError
0x18002b63a  jmp     loc_18002B7F6
0x18002b63f  mov     rdx, [rsp+98h+Src]; Src
0x18002b647  lea     rbp, [rax+rdi]
0x18002b64b  xor     eax, eax
0x18002b64d  mov     [rsp+98h+var_58], rbp
0x18002b652  lea     rcx, [rbp+8]; void *
0x18002b656  mov     [rbp+0], rax
0x18002b65a  mov     r8, rbx; Size
0x18002b65d  call    memcpy_0
0x18002b662  lea     rax, [rbx+8]
0x18002b666  mov     r9d, 2; dwFlags
0x18002b66c  add     rax, rbp
0x18002b66f  mov     r8d, r12d; cbBuffer
0x18002b672  mov     rdx, rax; pbBuffer
0x18002b675  mov     [rsp+98h+var_50], rax
0x18002b67a  xor     ecx, ecx; hAlgorithm
0x18002b67c  call    cs:__imp_BCryptGenRandom
0x18002b682  mov     ebx, eax
0x18002b684  xor     eax, eax
0x18002b686  test    ebx, ebx
0x18002b688  jns     short loc_18002B694
0x18002b68a  mov     r9d, 3C5h
0x18002b690  mov     ecx, ebx
0x18002b692  jmp     short loc_18002B635
0x18002b694  mov     rcx, [rsp+98h+hAlgorithm]; hAlgorithm
0x18002b69c  lea     rdx, [rsp+98h+phHash]; phHash
0x18002b6a4  mov     [rsp+98h+dwFlags], eax; dwFlags
0x18002b6a8  mov     r9d, edi; cbHashObject
0x18002b6ab  mov     [rsp+98h+cbSecret], eax; cbSecret
0x18002b6af  mov     r8, r14; pbHashObject
0x18002b6b2  mov     [rsp+98h+pbSecret], rax; pbSecret
0x18002b6b7  call    cs:__imp_BCryptCreateHash
0x18002b6bd  mov     ebx, eax
0x18002b6bf  test    eax, eax
0x18002b6c1  jns     short loc_18002B6D0
0x18002b6c3  mov     r9d, 3D9h
0x18002b6c9  mov     ecx, eax
0x18002b6cb  jmp     loc_18002B635
0x18002b6d0  mov     r8d, dword ptr [rsp+98h+Size]
0x18002b6d8  xor     r9d, r9d; dwFlags
0x18002b6db  mov     rcx, [rsp+98h+phHash]; hHash
0x18002b6e3  add     r8d, 8
0x18002b6e7  add     r8d, r12d; cbInput
0x18002b6ea  mov     rdx, rbp; pbInput
0x18002b6ed  call    cs:__imp_BCryptHashData
0x18002b6f3  mov     ebx, eax
0x18002b6f5  test    eax, eax
0x18002b6f7  jns     short loc_18002B701
0x18002b6f9  mov     r9d, 3E3h
0x18002b6ff  jmp     short loc_18002B6C9
0x18002b701  mov     rbp, [rsp+98h+arg_38]
0x18002b709  xor     r9d, r9d; dwFlags
0x18002b70c  mov     rcx, [rsp+98h+phHash]; hHash
0x18002b714  mov     r8d, r15d; cbOutput
0x18002b717  mov     eax, esi
0x18002b719  add     rax, rbp
0x18002b71c  mov     rdx, rax; pbOutput
0x18002b71f  mov     [rsp+98h+var_40], rax
0x18002b724  call    cs:__imp_BCryptFinishHash
0x18002b72a  mov     ebx, eax
0x18002b72c  test    eax, eax
0x18002b72e  jns     short loc_18002B738
0x18002b730  mov     r9d, 3EDh
0x18002b736  jmp     short loc_18002B6C9
0x18002b738  mov     eax, dword ptr [rsp+98h+Size]
0x18002b73f  xor     edx, edx; Val
0x18002b741  mov     rcx, [rsp+98h+var_58]
0x18002b746  add     eax, 8
0x18002b749  add     eax, r12d
0x18002b74c  mov     rdi, r12
0x18002b74f  add     rcx, rax; void *
0x18002b752  mov     eax, esi
0x18002b754  add     rax, rcx
0x18002b757  mov     [rsp+98h+var_58], rcx
0x18002b75c  mov     [rsp+98h+var_48], rax
0x18002b761  mov     eax, esi
0x18002b763  sub     eax, r12d
0x18002b766  dec     eax
0x18002b768  mov     r8d, eax; Size
0x18002b76b  mov     ebx, eax
0x18002b76d  call    memset_0
0x18002b772  mov     r12, [rsp+98h+var_58]
0x18002b777  mov     r8, rdi; Size
0x18002b77a  mov     rdx, [rsp+98h+var_50]; Src
0x18002b77f  lea     rcx, [r12+1]
0x18002b784  mov     byte ptr [rbx+r12], 1
0x18002b789  add     rcx, rbx; void *
0x18002b78c  call    memcpy_0
0x18002b791  mov     rdi, [rsp+98h+var_48]
0x18002b796  mov     edx, r15d
0x18002b799  mov     r9, [rsp+98h+var_40]
0x18002b79e  mov     r8d, [rsp+98h+arg_10]
0x18002b7a6  mov     rcx, [rsp+98h+hAlgorithm]
0x18002b7ae  mov     [rsp+98h+dwFlags], esi
0x18002b7b2  mov     qword ptr [rsp+98h+cbSecret], rdi
0x18002b7b7  mov     dword ptr [rsp+98h+pbSecret], r15d
0x18002b7bc  call    MaskGeneration
0x18002b7c1  mov     ebx, eax
0x18002b7c3  test    eax, eax
0x18002b7c5  jns     short loc_18002B7D2
0x18002b7c7  mov     r9d, 400h
0x18002b7cd  jmp     loc_18002B6C9
0x18002b7d2  xor     edx, edx
0x18002b7d4  test    esi, esi
0x18002b7d6  jz      short loc_18002B7E8
0x18002b7d8  mov     al, [rdx+rdi]
0x18002b7db  xor     al, [rdx+r12]
0x18002b7df  mov     [rdx+rbp], al
0x18002b7e2  inc     edx
0x18002b7e4  cmp     edx, esi
0x18002b7e6  jb      short loc_18002B7D8
0x18002b7e8  and     byte ptr [rbp+0], 7Fh
0x18002b7ec  lea     eax, [r13-1]
0x18002b7f0  mov     byte ptr [rax+rbp], 0BCh
0x18002b7f4  xor     ebx, ebx
0x18002b7f6  mov     rcx, [rsp+98h+phHash]; hHash
0x18002b7fe  test    rcx, rcx
0x18002b801  jz      short loc_18002B809
0x18002b803  call    cs:__imp_BCryptDestroyHash
0x18002b809  test    r14, r14
0x18002b80c  jz      short loc_18002B816
0x18002b80e  mov     rcx, r14
0x18002b811  call    MSCryptFree
0x18002b816  mov     eax, ebx
0x18002b818  mov     rbx, [rsp+98h+arg_8]
0x18002b820  add     rsp, 60h
0x18002b824  pop     r15
0x18002b826  pop     r14
0x18002b828  pop     r13
0x18002b82a  pop     r12
0x18002b82c  pop     rdi
0x18002b82d  pop     rsi
0x18002b82e  pop     rbp
0x18002b82f  retn
```
