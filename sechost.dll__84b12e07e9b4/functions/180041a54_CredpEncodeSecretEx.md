# CredpEncodeSecretEx

- ea: `0x180041a54`
- end: `0x180041cda`
- name: `CredpEncodeSecretEx`
- size: `646`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18003fb50`
- `0x180040750`
- `0x180041a20`
- `0x180041ce0`

## callees

- `0x180041a54`
- `0x18004f902`
- `0x18004f91a`
- `0x18004fa50`

## import_xrefs

- `ntdll!NtOpenProcessToken` at `0x180041b80`
- `ntdll!NtOpenProcessToken` at `0x180041b80`
- `ntdll!NtQueryInformationToken` at `0x180041bcf`
- `ntdll!NtQueryInformationToken` at `0x180041bcf`
- `ntdll!NtClose` at `0x180041c75`
- `ntdll!NtClose` at `0x180041c84`
- `ntdll!NtClose` at `0x180041c75`
- `ntdll!NtClose` at `0x180041c84`
- `ntdll!NtOpenThreadToken` at `0x180041b30`
- `ntdll!NtOpenThreadToken` at `0x180041ba4`
- `ntdll!NtOpenThreadToken` at `0x180041b30`
- `ntdll!NtOpenThreadToken` at `0x180041ba4`
- `ntdll!NtSetInformationThread` at `0x180041b4f`
- `ntdll!NtSetInformationThread` at `0x180041c66`
- `ntdll!NtSetInformationThread` at `0x180041b4f`
- `ntdll!NtSetInformationThread` at `0x180041c66`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180041af2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180041af2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180041cab`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180041cab`
- `CRYPTBASE!SystemFunction040` at `0x180041c1e`
- `CRYPTBASE!SystemFunction040` at `0x180041c1e`

## pseudocode

```c
__int64 __fastcall CredpEncodeSecretEx(
        int a1,
        int a2,
        const void *a3,
        unsigned int a4,
        _QWORD *a5,
        ULONG *a6,
        _QWORD *a7)
{
  _QWORD *v7; // rax
  ULONG *v9; // rcx
  char v10; // r13
  size_t v12; // r15
  ULONG v13; // esi
  char *v14; // rdi
  NTSTATUS v15; // ebx
  void *v16; // rcx
  __int64 v17; // r14
  __int64 v18; // rcx
  _BYTE *v19; // rax
  void *TokenHandle; // [rsp+38h] [rbp-69h] BYREF
  ULONG ReturnLength; // [rsp+40h] [rbp-61h] BYREF
  HANDLE Handle; // [rsp+48h] [rbp-59h] BYREF
  __int64 ThreadInformation; // [rsp+50h] [rbp-51h] BYREF
  _QWORD *v26; // [rsp+58h] [rbp-49h]
  ULONG *v27; // [rsp+60h] [rbp-41h]
  _OWORD TokenInformation[3]; // [rsp+68h] [rbp-39h] BYREF
  __int64 v29; // [rsp+98h] [rbp-9h]

  v7 = a5;
  v9 = a6;
  v10 = 0;
  v12 = a4;
  v26 = a5;
  v27 = a6;
  TokenHandle = 0;
  Handle = 0;
  ThreadInformation = 0;
  v29 = 0;
  ReturnLength = 0;
  memset(TokenInformation, 0, sizeof(TokenInformation));
  if ( !a3 || !a4 )
  {
    v14 = 0;
    v13 = 0;
LABEL_22:
    *v7 = v14;
    *v9 = v13;
    if ( a7 )
      *a7 = *((_QWORD *)&TokenInformation[0] + 1);
    v15 = 0;
    goto LABEL_25;
  }
  v13 = (a4 + 11) & 0xFFFFFFF8;
  v14 = (char *)LocalAlloc(0x40u, v13);
  if ( !v14 )
  {
    v15 = -1073741801;
    goto LABEL_27;
  }
  if ( a1 && NtCurrentTeb()->IsImpersonating )
  {
    v15 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 0xCu, 1u, &TokenHandle);
    if ( v15 < 0 )
      goto LABEL_27;
    v15 = NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &ThreadInformation, 8u);
    if ( v15 < 0 )
      goto LABEL_27;
    v10 = 1;
  }
  if ( !a7 )
  {
LABEL_17:
    memcpy_0(v14, a3, v12);
    v17 = v13 - (unsigned int)v12 - 4;
    if ( v13 - (_DWORD)v12 != 4 )
      memset_0(&v14[v12], 0, (unsigned int)v17);
    *(_DWORD *)&v14[v17 + v12] = v12;
    v15 = SystemFunction040(v14, v13, a2 != 0 ? 4 : 2);
    if ( v15 < 0 )
      goto LABEL_25;
    v7 = v26;
    v9 = v27;
    goto LABEL_22;
  }
  if ( NtCurrentTeb()->IsImpersonating )
  {
    v15 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 0xCu, 1u, &TokenHandle);
    if ( v15 < 0 )
      goto LABEL_25;
    v16 = TokenHandle;
  }
  else
  {
    v15 = NtOpenProcessToken((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0xCu, &Handle);
    if ( v15 < 0 )
      goto LABEL_25;
    v16 = Handle;
  }
  v15 = NtQueryInformationToken(v16, TokenStatistics, TokenInformation, 0x38u, &ReturnLength);
  if ( v15 >= 0 )
    goto LABEL_17;
LABEL_25:
  if ( v10 )
    NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &TokenHandle, 8u);
LABEL_27:
  if ( TokenHandle )
    NtClose(TokenHandle);
  if ( Handle )
    NtClose(Handle);
  if ( v15 < 0 && v14 )
  {
    v18 = v13;
    v19 = v14;
    if ( v13 )
    {
      do
      {
        *v19++ = 0;
        --v18;
      }
      while ( v18 );
    }
    LocalFree(v14);
  }
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x180041a54  mov     [rsp-8+arg_0], rbx
0x180041a59  push    rbp
0x180041a5a  push    rsi
0x180041a5b  push    rdi
0x180041a5c  push    r12
0x180041a5e  push    r13
0x180041a60  push    r14
0x180041a62  push    r15
0x180041a64  lea     rbp, [rsp-0Fh]
0x180041a69  sub     rsp, 0B0h
0x180041a70  mov     rax, cs:__security_cookie
0x180041a77  xor     rax, rsp
0x180041a7a  mov     [rbp+3Fh+var_40], rax
0x180041a7e  mov     rax, [rbp+3Fh+arg_20]
0x180041a82  xorps   xmm0, xmm0
0x180041a85  mov     r12, [rbp+3Fh+arg_30]
0x180041a89  mov     ebx, ecx
0x180041a8b  mov     rcx, [rbp+3Fh+arg_28]
0x180041a8f  xor     r13b, r13b
0x180041a92  mov     [rbp+3Fh+var_B0], edx
0x180041a95  mov     r14, r8
0x180041a98  xor     edx, edx
0x180041a9a  mov     r15d, r9d
0x180041a9d  mov     [rbp+3Fh+var_88], rax
0x180041aa1  mov     [rbp+3Fh+var_80], rcx
0x180041aa5  mov     [rbp+3Fh+TokenHandle], 0
0x180041aad  mov     [rbp+3Fh+Handle], 0
0x180041ab5  mov     [rbp+3Fh+ThreadInformation], 0
0x180041abd  mov     [rbp+3Fh+var_48], rdx
0x180041ac1  mov     [rbp+3Fh+var_A0], edx
0x180041ac4  movups  [rbp+3Fh+TokenInformation], xmm0
0x180041ac8  movups  [rbp+3Fh+var_68], xmm0
0x180041acc  movups  [rbp+3Fh+var_58], xmm0
0x180041ad0  test    r8, r8
0x180041ad3  jz      loc_180041C34
0x180041ad9  test    r9d, r9d
0x180041adc  jz      loc_180041C34
0x180041ae2  lea     eax, [r15+0Bh]
0x180041ae6  mov     ecx, 40h ; '@'; uFlags
0x180041aeb  and     eax, 0FFFFFFF8h
0x180041aee  mov     edx, eax; uBytes
0x180041af0  mov     esi, eax
0x180041af2  call    cs:__imp_LocalAlloc
0x180041af8  mov     rdi, rax
0x180041afb  test    rax, rax
0x180041afe  jnz     short loc_180041B0A
0x180041b00  mov     ebx, 0C0000017h
0x180041b05  jmp     loc_180041C6C
0x180041b0a  test    ebx, ebx
0x180041b0c  jz      short loc_180041B62
0x180041b0e  mov     eax, gs:179Ch
0x180041b16  test    eax, eax
0x180041b18  jz      short loc_180041B62
0x180041b1a  mov     r13, 0FFFFFFFFFFFFFFFEh
0x180041b21  lea     r9, [rbp+3Fh+TokenHandle]; TokenHandle
0x180041b25  mov     rcx, r13; ThreadHandle
0x180041b28  mov     r8b, 1; OpenAsSelf
0x180041b2b  mov     edx, 0Ch; DesiredAccess
0x180041b30  call    cs:__imp_NtOpenThreadToken
0x180041b36  mov     ebx, eax
0x180041b38  test    eax, eax
0x180041b3a  js      loc_180041C6C
0x180041b40  lea     r9d, [r13+0Ah]; ThreadInformationLength
0x180041b44  mov     rcx, r13; ThreadHandle
0x180041b47  lea     r8, [rbp+3Fh+ThreadInformation]; ThreadInformation
0x180041b4b  lea     edx, [r13+7]; ThreadInformationClass
0x180041b4f  call    cs:__imp_NtSetInformationThread
0x180041b55  mov     ebx, eax
0x180041b57  test    eax, eax
0x180041b59  js      loc_180041C6C
0x180041b5f  mov     r13b, 1
0x180041b62  test    r12, r12
0x180041b65  jz      short loc_180041BDB
0x180041b67  mov     eax, gs:179Ch
0x180041b6f  mov     edx, 0Ch; DesiredAccess
0x180041b74  test    eax, eax
0x180041b76  jnz     short loc_180041B96
0x180041b78  lea     r8, [rbp+3Fh+Handle]; TokenHandle
0x180041b7c  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x180041b80  call    cs:__imp_NtOpenProcessToken
0x180041b86  mov     ebx, eax
0x180041b88  test    eax, eax
0x180041b8a  js      loc_180041C4C
0x180041b90  mov     rcx, [rbp+3Fh+Handle]
0x180041b94  jmp     short loc_180041BB8
0x180041b96  lea     r9, [rbp+3Fh+TokenHandle]; TokenHandle
0x180041b9a  mov     r8b, 1; OpenAsSelf
0x180041b9d  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x180041ba4  call    cs:__imp_NtOpenThreadToken
0x180041baa  mov     ebx, eax
0x180041bac  test    eax, eax
0x180041bae  js      loc_180041C4C
0x180041bb4  mov     rcx, [rbp+3Fh+TokenHandle]; TokenHandle
0x180041bb8  mov     r9d, 38h ; '8'; TokenInformationLength
0x180041bbe  lea     rax, [rbp+3Fh+var_A0]
0x180041bc2  lea     r8, [rbp+3Fh+TokenInformation]; TokenInformation
0x180041bc6  mov     [rsp+0E0h+ReturnLength], rax; ReturnLength
0x180041bcb  lea     edx, [r9-2Eh]; TokenInformationClass
0x180041bcf  call    cs:__imp_NtQueryInformationToken
0x180041bd5  mov     ebx, eax
0x180041bd7  test    eax, eax
0x180041bd9  js      short loc_180041C4C
0x180041bdb  mov     r8, r15; Size
0x180041bde  mov     rdx, r14; Src
0x180041be1  mov     rcx, rdi; void *
0x180041be4  call    memcpy_0
0x180041be9  mov     r14d, esi
0x180041bec  sub     r14d, r15d
0x180041bef  add     r14d, 0FFFFFFFCh
0x180041bf3  jz      short loc_180041C03
0x180041bf5  lea     rcx, [r15+rdi]; void *
0x180041bf9  mov     r8d, r14d; Size
0x180041bfc  xor     edx, edx; Val
0x180041bfe  call    memset_0
0x180041c03  neg     [rbp+3Fh+var_B0]
0x180041c06  lea     rax, [r14+r15]
0x180041c0a  mov     edx, esi; MemorySize
0x180041c0c  mov     [rax+rdi], r15d
0x180041c10  sbb     r8d, r8d
0x180041c13  mov     rcx, rdi; Memory
0x180041c16  and     r8d, 2
0x180041c1a  add     r8d, 2; OptionFlags
0x180041c1e  call    cs:__imp_SystemFunction040
0x180041c24  mov     ebx, eax
0x180041c26  test    eax, eax
0x180041c28  js      short loc_180041C4C
0x180041c2a  mov     rax, [rbp+3Fh+var_88]
0x180041c2e  mov     rcx, [rbp+3Fh+var_80]
0x180041c32  jmp     short loc_180041C38
0x180041c34  xor     edi, edi
0x180041c36  xor     esi, esi
0x180041c38  mov     [rax], rdi
0x180041c3b  mov     [rcx], esi
0x180041c3d  test    r12, r12
0x180041c40  jz      short loc_180041C4A
0x180041c42  mov     rax, qword ptr [rbp+3Fh+TokenInformation+8]
0x180041c46  mov     [r12], rax
0x180041c4a  xor     ebx, ebx
0x180041c4c  test    r13b, r13b
0x180041c4f  jz      short loc_180041C6C
0x180041c51  mov     r9d, 8; ThreadInformationLength
0x180041c57  lea     r8, [rbp+3Fh+TokenHandle]; ThreadInformation
0x180041c5b  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x180041c62  lea     edx, [r9-3]; ThreadInformationClass
0x180041c66  call    cs:__imp_NtSetInformationThread
0x180041c6c  mov     rcx, [rbp+3Fh+TokenHandle]; Handle
0x180041c70  test    rcx, rcx
0x180041c73  jz      short loc_180041C7B
0x180041c75  call    cs:__imp_NtClose
0x180041c7b  mov     rcx, [rbp+3Fh+Handle]; Handle
0x180041c7f  test    rcx, rcx
0x180041c82  jz      short loc_180041C8A
0x180041c84  call    cs:__imp_NtClose
0x180041c8a  test    ebx, ebx
0x180041c8c  jns     short loc_180041CB1
0x180041c8e  test    rdi, rdi
0x180041c91  jz      short loc_180041CB1
0x180041c93  mov     ecx, esi
0x180041c95  mov     rax, rdi
0x180041c98  test    esi, esi
0x180041c9a  jz      short loc_180041CA8
0x180041c9c  mov     byte ptr [rax], 0
0x180041c9f  inc     rax
0x180041ca2  sub     rcx, 1
0x180041ca6  jnz     short loc_180041C9C
0x180041ca8  mov     rcx, rdi; hMem
0x180041cab  call    cs:__imp_LocalFree
0x180041cb1  mov     eax, ebx
0x180041cb3  mov     rcx, [rbp+3Fh+var_40]
0x180041cb7  xor     rcx, rsp; StackCookie
0x180041cba  call    __security_check_cookie
0x180041cbf  mov     rbx, [rsp+0E0h+arg_0]
0x180041cc7  add     rsp, 0B0h
0x180041cce  pop     r15
0x180041cd0  pop     r14
0x180041cd2  pop     r13
0x180041cd4  pop     r12
0x180041cd6  pop     rdi
0x180041cd7  pop     rsi
0x180041cd8  pop     rbp
0x180041cd9  retn
```
