# AuthenticateUser

- ea: `0x1800e79c4`
- end: `0x1800e7d02`
- name: `AuthenticateUser`
- size: `830`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18015abb0`

## callees

- `0x1800e73c0`
- `0x1800e743c`
- `0x1800e79c4`
- `0x18014b3b4`
- `0x180154882`
- `0x180158c2c`
- `0x180159150`
- `0x18015b868`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800e7c4b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800e7c4b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800e7b61`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800e7cae`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800e7b61`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800e7cae`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800e7b09`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800e7b09`
- `SspiCli!DeleteSecurityContext` at `0x1800e7b3c`
- `SspiCli!DeleteSecurityContext` at `0x1800e7c89`
- `SspiCli!DeleteSecurityContext` at `0x1800e7b3c`
- `SspiCli!DeleteSecurityContext` at `0x1800e7c89`

## pseudocode

```c
unsigned int __fastcall AuthenticateUser(
        struct _WINCONTEXT **a1,
        char *a2,
        int a3,
        unsigned __int16 *a4,
        int a5,
        int a6,
        unsigned __int64 a7,
        unsigned int dwBytes,
        unsigned __int16 *a9,
        unsigned __int16 *a10,
        const CHAR *a11,
        void *Src,
        unsigned int a13,
        SECURITY_STATUS *a14,
        _DWORD *a15)
{
  const CHAR *v19; // rcx
  int PkgId; // eax
  unsigned int v21; // r12d
  struct _WINCONTEXT *v22; // rbx
  const void *v23; // rbp
  unsigned int result; // eax
  const WCHAR *v25; // r8
  struct _SecHandle *v26; // rcx
  void *v27; // r8
  __int64 v28; // r9
  int SecAuthMsg; // eax
  LPVOID v30; // rax
  struct _SecHandle *v31; // rcx
  void *v32; // r8
  int cchCount2[2]; // [rsp+28h] [rbp-90h]
  struct _WINCONTEXT *v34; // [rsp+70h] [rbp-48h] BYREF

  v34 = 0;
  *a15 = 0;
  if ( !SSPI_InitGlobals() )
    return 87;
  v19 = "Negotiate";
  if ( !a3 )
    v19 = a2;
  PkgId = GetPkgId(v19);
  v21 = PkgId;
  if ( PkgId == -1 )
    return 87;
  v22 = *a1;
  if ( v22 )
  {
    if ( *((_DWORD *)v22 + 12) == PkgId )
    {
      if ( dwBytes )
      {
        v23 = (const void *)a7;
        goto LABEL_23;
      }
      v25 = (const WCHAR *)*((_QWORD *)v22 + 13);
      if ( !v25 || CompareStringW(dwBytes + 127, 1u, v25, -1, a4, -1) == 2 )
      {
        if ( SaveSPN(v22, a4, a5) )
        {
          v26 = (struct _SecHandle *)*((_QWORD *)v22 + 12);
          if ( v26 )
          {
            DeleteSecurityContext(v26);
            *((_QWORD *)v22 + 12) = 0;
            *a15 = 1;
          }
          v27 = (void *)*((_QWORD *)v22 + 4);
          if ( v27 && v27 != *((void **)v22 + 2) )
            HeapFree(g_hWxProcessHeap, 0, v27);
          *((_QWORD *)v22 + 4) = 0;
          *((_DWORD *)v22 + 10) = 0;
          *((_DWORD *)v22 + 3) = 0;
          return 12014;
        }
        return 8;
      }
    }
    return 87;
  }
  if ( !a3 && a7 )
    return 87;
  v23 = (const void *)(a7 & -(__int64)(a3 != 0));
  result = NewWinContext(PkgId, a2, a3, &v34, a6, a9, a10, Src, a13);
  if ( result )
    return result;
  v22 = v34;
  *a1 = v34;
  *a15 = 1;
LABEL_23:
  *((_DWORD *)v22 + 3) = *((_DWORD *)v22 + 2);
  memset_0(*(void **)v22, 0, *((unsigned int *)v22 + 2));
  cchCount2[0] = dwBytes;
  SecAuthMsg = GetSecAuthMsg(
                 (__int64)v22,
                 v21,
                 *((struct _SecHandle **)v22 + 12),
                 v28,
                 (__int64)v23,
                 *(SIZE_T *)cchCount2,
                 *(char **)v22,
                 (_DWORD *)v22 + 3,
                 a4,
                 a5,
                 a2,
                 a11,
                 a14);
  if ( SecAuthMsg )
  {
    *((_DWORD *)v22 + 3) = 0;
    if ( SecAuthMsg == 2 )
    {
      if ( SaveSPN(v22, a4, a5) )
      {
        if ( v23 && dwBytes && !a3 )
        {
          if ( dwBytes <= 0x32C8 )
          {
            *((_QWORD *)v22 + 4) = *((_QWORD *)v22 + 2);
          }
          else
          {
            v30 = HeapAlloc(g_hWxProcessHeap, 0, dwBytes);
            *((_QWORD *)v22 + 4) = v30;
            if ( !v30 )
              return 8;
          }
          memcpy_0(*((void **)v22 + 2), v23, dwBytes);
          *((_DWORD *)v22 + 10) = dwBytes;
        }
        else
        {
          v31 = (struct _SecHandle *)*((_QWORD *)v22 + 12);
          if ( v31 )
          {
            DeleteSecurityContext(v31);
            *((_QWORD *)v22 + 12) = 0;
            *a15 = 1;
          }
          v32 = (void *)*((_QWORD *)v22 + 4);
          if ( v32 )
          {
            if ( v32 != *((void **)v22 + 2) )
              HeapFree(g_hWxProcessHeap, 0, v32);
          }
          *((_QWORD *)v22 + 4) = 0;
          *((_DWORD *)v22 + 10) = 0;
        }
        *((_DWORD *)v22 + 3) = 0;
        return 12014;
      }
      return 8;
    }
    return 12015;
  }
  else
  {
    if ( !*((_QWORD *)v22 + 12) )
      *((_QWORD *)v22 + 12) = (char *)v22 + 80;
    return 12032;
  }
}

```

## disassembly

```asm
0x1800e79c4  mov     rax, rsp
0x1800e79c7  mov     [rax+18h], rbx
0x1800e79cb  mov     [rax+10h], rdx
0x1800e79cf  mov     [rax+8], rcx
0x1800e79d3  push    rbp
0x1800e79d4  push    rsi
0x1800e79d5  push    rdi
0x1800e79d6  push    r12
0x1800e79d8  push    r13
0x1800e79da  push    r14
0x1800e79dc  push    r15
0x1800e79de  sub     rsp, 80h
0x1800e79e5  mov     r15, [rsp+0B8h+arg_70]
0x1800e79ed  xor     ebp, ebp
0x1800e79ef  mov     r13, r9
0x1800e79f2  mov     [rax-48h], rbp
0x1800e79f6  mov     r14d, r8d
0x1800e79f9  mov     rdi, rdx
0x1800e79fc  mov     rbx, rcx
0x1800e79ff  mov     [r15], ebp
0x1800e7a02  call    SSPI_InitGlobals
0x1800e7a07  test    rax, rax
0x1800e7a0a  jz      loc_1800E7CE2
0x1800e7a10  test    r14d, r14d
0x1800e7a13  lea     rcx, aNegotiate_1; "Negotiate"
0x1800e7a1a  cmovz   rcx, rdi; lpString2
0x1800e7a1e  call    GetPkgId
0x1800e7a23  or      r9d, 0FFFFFFFFh; cchCount1
0x1800e7a27  mov     r12d, eax
0x1800e7a2a  cmp     eax, r9d
0x1800e7a2d  jz      loc_1800E7CE2
0x1800e7a33  mov     rbx, [rbx]
0x1800e7a36  lea     esi, [rbp+1]
0x1800e7a39  mov     edi, dword ptr [rsp+0B8h+dwBytes]
0x1800e7a40  test    rbx, rbx
0x1800e7a43  jnz     loc_1800E7ADF
0x1800e7a49  mov     rcx, [rsp+0B8h+arg_30]
0x1800e7a51  test    r14d, r14d
0x1800e7a54  jnz     short loc_1800E7A5F
0x1800e7a56  test    rcx, rcx
0x1800e7a59  jnz     loc_1800E7CE2
0x1800e7a5f  mov     rdx, [rsp+0B8h+arg_8]; char *
0x1800e7a67  lea     r9, [rsp+0B8h+var_48]; struct _WINCONTEXT **
0x1800e7a6c  mov     eax, r14d
0x1800e7a6f  mov     r8d, r14d; int
0x1800e7a72  neg     eax
0x1800e7a74  mov     eax, [rsp+0B8h+arg_60]
0x1800e7a7b  mov     [rsp+0B8h+var_78], eax; unsigned int
0x1800e7a7f  sbb     rbp, rbp
0x1800e7a82  mov     rax, [rsp+0B8h+arg_58]
0x1800e7a8a  and     rbp, rcx
0x1800e7a8d  mov     [rsp+0B8h+Src], rax; Src
0x1800e7a92  mov     ecx, r12d; int
0x1800e7a95  mov     rax, [rsp+0B8h+arg_48]
0x1800e7a9d  mov     [rsp+0B8h+var_88], rax; unsigned __int16 *
0x1800e7aa2  mov     rax, [rsp+0B8h+arg_40]
0x1800e7aaa  mov     qword ptr [rsp+0B8h+cchCount2], rax; unsigned __int16 *
0x1800e7aaf  mov     eax, [rsp+0B8h+arg_28]
0x1800e7ab6  mov     dword ptr [rsp+0B8h+lpString2], eax; int
0x1800e7aba  call    ?NewWinContext@@YAKHPEADHPEAPEAU_WINCONTEXT@@HPEAG2PEAXK@Z; NewWinContext(int,char *,int,_WINCONTEXT * *,int,ushort *,ushort *,void *,ulong)
0x1800e7abf  test    eax, eax
0x1800e7ac1  jnz     loc_1800E7CE7
0x1800e7ac7  mov     rax, [rsp+0B8h+arg_0]
0x1800e7acf  mov     rbx, [rsp+0B8h+var_48]
0x1800e7ad4  mov     [rax], rbx
0x1800e7ad7  mov     [r15], esi
0x1800e7ada  jmp     loc_1800E7B83
0x1800e7adf  cmp     [rbx+30h], r12d
0x1800e7ae3  jnz     loc_1800E7CE2
0x1800e7ae9  test    edi, edi
0x1800e7aeb  jnz     loc_1800E7B7B
0x1800e7af1  mov     r8, [rbx+68h]; lpString1
0x1800e7af5  test    r8, r8
0x1800e7af8  jz      short loc_1800E7B18
0x1800e7afa  mov     [rsp+0B8h+cchCount2], r9d; cchCount2
0x1800e7aff  lea     ecx, [rdi+7Fh]; Locale
0x1800e7b02  mov     edx, esi; dwCmpFlags
0x1800e7b04  mov     [rsp+0B8h+lpString2], r13; lpString2
0x1800e7b09  call    cs:__imp_CompareStringW
0x1800e7b0f  cmp     eax, 2
0x1800e7b12  jnz     loc_1800E7CE2
0x1800e7b18  mov     r8d, [rsp+0B8h+arg_20]; int
0x1800e7b20  mov     rdx, r13; unsigned __int16 *
0x1800e7b23  mov     rcx, rbx; struct _WINCONTEXT *
0x1800e7b26  call    ?SaveSPN@@YAHPEAU_WINCONTEXT@@PEBGH@Z; SaveSPN(_WINCONTEXT *,ushort const *,int)
0x1800e7b2b  test    eax, eax
0x1800e7b2d  jz      loc_1800E7C5A
0x1800e7b33  mov     rcx, [rbx+60h]; phContext
0x1800e7b37  test    rcx, rcx
0x1800e7b3a  jz      short loc_1800E7B49
0x1800e7b3c  call    cs:__imp_DeleteSecurityContext
0x1800e7b42  mov     [rbx+60h], rbp
0x1800e7b46  mov     [r15], esi
0x1800e7b49  mov     r8, [rbx+20h]; lpMem
0x1800e7b4d  test    r8, r8
0x1800e7b50  jz      short loc_1800E7B67
0x1800e7b52  cmp     r8, [rbx+10h]
0x1800e7b56  jz      short loc_1800E7B67
0x1800e7b58  mov     rcx, cs:g_hWxProcessHeap; hHeap
0x1800e7b5f  xor     edx, edx; dwFlags
0x1800e7b61  call    cs:__imp_HeapFree
0x1800e7b67  mov     [rbx+20h], rbp
0x1800e7b6b  mov     [rbx+28h], ebp
0x1800e7b6e  mov     [rbx+0Ch], ebp
0x1800e7b71  mov     eax, 2EEEh
0x1800e7b76  jmp     loc_1800E7CE7
0x1800e7b7b  mov     rbp, [rsp+0B8h+arg_30]
0x1800e7b83  mov     eax, [rbx+8]
0x1800e7b86  xor     edx, edx; Val
0x1800e7b88  mov     [rbx+0Ch], eax
0x1800e7b8b  mov     r8d, [rbx+8]; Size
0x1800e7b8f  mov     rcx, [rbx]; void *
0x1800e7b92  call    memset_0
0x1800e7b97  mov     rax, [rsp+0B8h+arg_68]
0x1800e7b9f  mov     edx, r12d; int
0x1800e7ba2  mov     r8, [rbx+60h]; int
0x1800e7ba6  mov     rcx, rbx; int
0x1800e7ba9  mov     [rsp+0B8h+var_58], rax; __int64
0x1800e7bae  mov     rax, [rsp+0B8h+arg_50]
0x1800e7bb6  mov     [rsp+0B8h+var_60], rax; __int64
0x1800e7bbb  mov     rax, [rsp+0B8h+arg_8]
0x1800e7bc3  mov     [rsp+0B8h+var_68], rax; __int64
0x1800e7bc8  mov     eax, [rsp+0B8h+arg_20]
0x1800e7bcf  mov     [rsp+0B8h+var_70], eax; int
0x1800e7bd3  lea     rax, [rbx+0Ch]
0x1800e7bd7  mov     qword ptr [rsp+0B8h+var_78], r13; __int64
0x1800e7bdc  mov     [rsp+0B8h+Src], rax; __int64
0x1800e7be1  mov     rax, [rbx]
0x1800e7be4  mov     [rsp+0B8h+var_88], rax; char *
0x1800e7be9  mov     [rsp+0B8h+cchCount2], edi; dwBytes
0x1800e7bed  mov     [rsp+0B8h+lpString2], rbp; __int64
0x1800e7bf2  call    GetSecAuthMsg
0x1800e7bf7  test    eax, eax
0x1800e7bf9  jz      loc_1800E7CCC
0x1800e7bff  mov     dword ptr [rbx+0Ch], 0
0x1800e7c06  cmp     eax, 2
0x1800e7c09  jnz     loc_1800E7CC5
0x1800e7c0f  mov     r8d, [rsp+0B8h+arg_20]; int
0x1800e7c17  mov     rdx, r13; unsigned __int16 *
0x1800e7c1a  mov     rcx, rbx; struct _WINCONTEXT *
0x1800e7c1d  call    ?SaveSPN@@YAHPEAU_WINCONTEXT@@PEBGH@Z; SaveSPN(_WINCONTEXT *,ushort const *,int)
0x1800e7c22  xor     r13d, r13d
0x1800e7c25  test    eax, eax
0x1800e7c27  jz      short loc_1800E7C5A
0x1800e7c29  test    rbp, rbp
0x1800e7c2c  jz      short loc_1800E7C80
0x1800e7c2e  test    edi, edi
0x1800e7c30  jz      short loc_1800E7C80
0x1800e7c32  test    r14d, r14d
0x1800e7c35  jnz     short loc_1800E7C80
0x1800e7c37  cmp     edi, 32C8h
0x1800e7c3d  jbe     short loc_1800E7C64
0x1800e7c3f  mov     rcx, cs:g_hWxProcessHeap; hHeap
0x1800e7c46  mov     r8, rdi; dwBytes
0x1800e7c49  xor     edx, edx; dwFlags
0x1800e7c4b  call    cs:__imp_HeapAlloc
0x1800e7c51  mov     [rbx+20h], rax
0x1800e7c55  test    rax, rax
0x1800e7c58  jnz     short loc_1800E7C6C
0x1800e7c5a  mov     eax, 8
0x1800e7c5f  jmp     loc_1800E7CE7
0x1800e7c64  mov     rax, [rbx+10h]
0x1800e7c68  mov     [rbx+20h], rax
0x1800e7c6c  mov     rcx, [rbx+10h]; void *
0x1800e7c70  mov     r8, rdi; Size
0x1800e7c73  mov     rdx, rbp; Src
0x1800e7c76  call    memcpy_0
0x1800e7c7b  mov     [rbx+28h], edi
0x1800e7c7e  jmp     short loc_1800E7CBC
0x1800e7c80  mov     rcx, [rbx+60h]; phContext
0x1800e7c84  test    rcx, rcx
0x1800e7c87  jz      short loc_1800E7C96
0x1800e7c89  call    cs:__imp_DeleteSecurityContext
0x1800e7c8f  mov     [rbx+60h], r13
0x1800e7c93  mov     [r15], esi
0x1800e7c96  mov     r8, [rbx+20h]; lpMem
0x1800e7c9a  test    r8, r8
0x1800e7c9d  jz      short loc_1800E7CB4
0x1800e7c9f  cmp     r8, [rbx+10h]
0x1800e7ca3  jz      short loc_1800E7CB4
0x1800e7ca5  mov     rcx, cs:g_hWxProcessHeap; hHeap
0x1800e7cac  xor     edx, edx; dwFlags
0x1800e7cae  call    cs:__imp_HeapFree
0x1800e7cb4  mov     [rbx+20h], r13
0x1800e7cb8  mov     [rbx+28h], r13d
0x1800e7cbc  mov     [rbx+0Ch], r13d
0x1800e7cc0  jmp     loc_1800E7B71
0x1800e7cc5  mov     eax, 2EEFh
0x1800e7cca  jmp     short loc_1800E7CE7
0x1800e7ccc  cmp     qword ptr [rbx+60h], 0
0x1800e7cd1  jnz     short loc_1800E7CDB
0x1800e7cd3  lea     rax, [rbx+50h]
0x1800e7cd7  mov     [rbx+60h], rax
0x1800e7cdb  mov     eax, 2F00h
0x1800e7ce0  jmp     short loc_1800E7CE7
0x1800e7ce2  mov     eax, 57h ; 'W'
0x1800e7ce7  mov     rbx, [rsp+0B8h+arg_10]
0x1800e7cef  add     rsp, 80h
0x1800e7cf6  pop     r15
0x1800e7cf8  pop     r14
0x1800e7cfa  pop     r13
0x1800e7cfc  pop     r12
0x1800e7cfe  pop     rdi
0x1800e7cff  pop     rsi
0x1800e7d00  pop     rbp
0x1800e7d01  retn
```
