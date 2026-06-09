# CredpDecodeSecretEx

- ea: `0x180041734`
- end: `0x180041a16`
- name: `CredpDecodeSecretEx`
- size: `738`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18004226c`

## callees

- `0x180041734`
- `0x18004f902`
- `0x18004fa50`

## import_xrefs

- `ntdll!NtOpenProcessToken` at `0x18004187e`
- `ntdll!NtOpenProcessToken` at `0x18004187e`
- `ntdll!NtQueryInformationToken` at `0x1800418cd`
- `ntdll!NtQueryInformationToken` at `0x1800418cd`
- `ntdll!NtClose` at `0x180041844`
- `ntdll!NtClose` at `0x1800419a1`
- `ntdll!NtClose` at `0x1800419b0`
- `ntdll!NtClose` at `0x180041844`
- `ntdll!NtClose` at `0x1800419a1`
- `ntdll!NtClose` at `0x1800419b0`
- `ntdll!NtOpenThreadToken` at `0x18004180f`
- `ntdll!NtOpenThreadToken` at `0x1800418a2`
- `ntdll!NtOpenThreadToken` at `0x18004180f`
- `ntdll!NtOpenThreadToken` at `0x1800418a2`
- `ntdll!NtSetInformationThread` at `0x180041834`
- `ntdll!NtSetInformationThread` at `0x180041935`
- `ntdll!NtSetInformationThread` at `0x180041992`
- `ntdll!NtSetInformationThread` at `0x180041834`
- `ntdll!NtSetInformationThread` at `0x180041935`
- `ntdll!NtSetInformationThread` at `0x180041992`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800417be`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800417be`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800419d9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800419d9`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x1800418ea`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x1800418ea`
- `CRYPTBASE!SystemFunction041` at `0x180041911`
- `CRYPTBASE!SystemFunction041` at `0x180041911`

## pseudocode

```c
__int64 __fastcall CredpDecodeSecretEx(
        int a1,
        int a2,
        const void *a3,
        unsigned int a4,
        void *Source1,
        _QWORD *a6,
        _DWORD *a7)
{
  _QWORD *v7; // rax
  size_t v9; // r15
  unsigned __int64 v11; // rdx
  _DWORD *v13; // rcx
  char *v14; // rax
  char *v15; // rdi
  NTSTATUS v16; // ebx
  void *v17; // rcx
  NTSTATUS v18; // esi
  size_t v19; // rcx
  _BYTE *v20; // rax
  char v22; // [rsp+30h] [rbp-71h]
  void *TokenHandle; // [rsp+38h] [rbp-69h] BYREF
  ULONG ReturnLength; // [rsp+40h] [rbp-61h] BYREF
  HANDLE Handle; // [rsp+48h] [rbp-59h] BYREF
  __int64 ThreadInformation; // [rsp+50h] [rbp-51h] BYREF
  _QWORD *v27; // [rsp+58h] [rbp-49h]
  _DWORD *v28; // [rsp+60h] [rbp-41h]
  _OWORD TokenInformation[3]; // [rsp+68h] [rbp-39h] BYREF
  __int64 v30; // [rsp+98h] [rbp-9h]

  v7 = a6;
  v9 = a4;
  v27 = a6;
  LODWORD(v11) = 0;
  TokenHandle = 0;
  Handle = 0;
  v13 = a7;
  v28 = a7;
  v22 = 0;
  v30 = 0;
  ReturnLength = 0;
  memset(TokenInformation, 0, sizeof(TokenInformation));
  if ( !a3 || !a4 )
  {
    v15 = 0;
LABEL_29:
    *v7 = v15;
    v16 = 0;
    *v13 = v11;
    goto LABEL_30;
  }
  v14 = (char *)LocalAlloc(0x40u, a4);
  v15 = v14;
  if ( !v14 )
  {
    v16 = -1073741801;
    goto LABEL_32;
  }
  memcpy_0(v14, a3, v9);
  if ( a1 && NtCurrentTeb()->IsImpersonating )
  {
    ThreadInformation = 0;
    v16 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 0xCu, 1u, &TokenHandle);
    if ( v16 < 0 )
      goto LABEL_32;
    v16 = NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &ThreadInformation, 8u);
    if ( v16 < 0 )
    {
      NtClose(TokenHandle);
      goto LABEL_32;
    }
    v22 = 1;
  }
  if ( Source1 && !a2 )
  {
    if ( NtCurrentTeb()->IsImpersonating )
    {
      v16 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 0xCu, 1u, &TokenHandle);
      if ( v16 < 0 )
        goto LABEL_30;
      v17 = TokenHandle;
    }
    else
    {
      v16 = NtOpenProcessToken((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0xCu, &Handle);
      if ( v16 < 0 )
        goto LABEL_30;
      v17 = Handle;
    }
    v16 = NtQueryInformationToken(v17, TokenStatistics, TokenInformation, 0x38u, &ReturnLength);
    if ( v16 < 0 )
      goto LABEL_30;
    if ( RtlCompareMemory(Source1, (char *)TokenInformation + 8, 8u) != 8 )
    {
      v16 = -1073740759;
      goto LABEL_30;
    }
  }
  v18 = SystemFunction041(v15, v9, a2 != 0 ? 4 : 2);
  if ( !TokenHandle
    || (v16 = NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &TokenHandle, 8u), v16 >= 0) )
  {
    if ( v18 >= 0 )
    {
      if ( (unsigned int)v9 < 4 || (v11 = *(unsigned int *)&v15[v9 - 4], !(_DWORD)v11) || v11 > v9 - 4 )
      {
        v16 = -1073741811;
        goto LABEL_30;
      }
      v7 = v27;
      v13 = v28;
      goto LABEL_29;
    }
    v16 = v18;
  }
LABEL_30:
  if ( v22 )
    NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &TokenHandle, 8u);
LABEL_32:
  if ( TokenHandle )
    NtClose(TokenHandle);
  if ( Handle )
    NtClose(Handle);
  if ( v16 < 0 && v15 )
  {
    v19 = v9;
    v20 = v15;
    if ( (_DWORD)v9 )
    {
      do
      {
        *v20++ = 0;
        --v19;
      }
      while ( v19 );
    }
    LocalFree(v15);
  }
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x180041734  mov     [rsp-8+arg_0], rbx
0x180041739  push    rbp
0x18004173a  push    rsi
0x18004173b  push    rdi
0x18004173c  push    r12
0x18004173e  push    r13
0x180041740  push    r14
0x180041742  push    r15
0x180041744  lea     rbp, [rsp-0Fh]
0x180041749  sub     rsp, 0B0h
0x180041750  mov     rax, cs:__security_cookie
0x180041757  xor     rax, rsp
0x18004175a  mov     [rbp+3Fh+var_40], rax
0x18004175e  mov     rax, [rbp+3Fh+arg_28]
0x180041762  xorps   xmm0, xmm0
0x180041765  mov     r13, [rbp+3Fh+Source1]
0x180041769  mov     rbx, r8
0x18004176c  xor     r8d, r8d
0x18004176f  mov     r15d, r9d
0x180041772  mov     r12d, edx
0x180041775  mov     [rbp+3Fh+var_88], rax
0x180041779  xor     edx, edx
0x18004177b  mov     [rbp+3Fh+TokenHandle], r8
0x18004177f  mov     [rbp+3Fh+Handle], r8
0x180041783  mov     esi, ecx
0x180041785  mov     rcx, [rbp+3Fh+arg_30]
0x180041789  mov     [rbp+3Fh+var_80], rcx
0x18004178d  mov     [rbp+3Fh+var_B0], r8b
0x180041791  mov     [rbp+3Fh+var_48], rdx
0x180041795  mov     [rbp+3Fh+var_A0], r8d
0x180041799  movups  [rbp+3Fh+TokenInformation], xmm0
0x18004179d  movups  [rbp+3Fh+var_68], xmm0
0x1800417a1  movups  [rbp+3Fh+var_58], xmm0
0x1800417a5  test    rbx, rbx
0x1800417a8  jz      loc_180041A0F
0x1800417ae  test    r9d, r9d
0x1800417b1  jz      loc_180041A0F
0x1800417b7  mov     edx, r15d; uBytes
0x1800417ba  lea     ecx, [r8+40h]; uFlags
0x1800417be  call    cs:__imp_LocalAlloc
0x1800417c4  mov     rdi, rax
0x1800417c7  test    rax, rax
0x1800417ca  jnz     short loc_1800417D6
0x1800417cc  mov     ebx, 0C0000017h
0x1800417d1  jmp     loc_180041998
0x1800417d6  mov     r8, r15; Size
0x1800417d9  mov     rdx, rbx; Src
0x1800417dc  mov     rcx, rdi; void *
0x1800417df  call    memcpy_0
0x1800417e4  test    esi, esi
0x1800417e6  jz      short loc_180041853
0x1800417e8  mov     eax, gs:179Ch
0x1800417f0  test    eax, eax
0x1800417f2  jz      short loc_180041853
0x1800417f4  lea     r9, [rbp+3Fh+TokenHandle]; TokenHandle
0x1800417f8  mov     [rbp+3Fh+ThreadInformation], 0
0x180041800  mov     r8b, 1; OpenAsSelf
0x180041803  mov     edx, 0Ch; DesiredAccess
0x180041808  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18004180f  call    cs:__imp_NtOpenThreadToken
0x180041815  mov     ebx, eax
0x180041817  test    eax, eax
0x180041819  js      loc_180041998
0x18004181f  mov     r9d, 8; ThreadInformationLength
0x180041825  lea     r8, [rbp+3Fh+ThreadInformation]; ThreadInformation
0x180041829  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x180041830  lea     edx, [r9-3]; ThreadInformationClass
0x180041834  call    cs:__imp_NtSetInformationThread
0x18004183a  mov     ebx, eax
0x18004183c  test    eax, eax
0x18004183e  jns     short loc_18004184F
0x180041840  mov     rcx, [rbp+3Fh+TokenHandle]; Handle
0x180041844  call    cs:__imp_NtClose
0x18004184a  jmp     loc_180041998
0x18004184f  mov     [rbp+3Fh+var_B0], 1
0x180041853  test    r13, r13
0x180041856  jz      loc_1800418FD
0x18004185c  test    r12d, r12d
0x18004185f  jnz     loc_1800418FD
0x180041865  mov     eax, gs:179Ch
0x18004186d  lea     edx, [r12+0Ch]; DesiredAccess
0x180041872  test    eax, eax
0x180041874  jnz     short loc_180041894
0x180041876  lea     r8, [rbp+3Fh+Handle]; TokenHandle
0x18004187a  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x18004187e  call    cs:__imp_NtOpenProcessToken
0x180041884  mov     ebx, eax
0x180041886  test    eax, eax
0x180041888  js      loc_180041977
0x18004188e  mov     rcx, [rbp+3Fh+Handle]
0x180041892  jmp     short loc_1800418B6
0x180041894  lea     r9, [rbp+3Fh+TokenHandle]; TokenHandle
0x180041898  mov     r8b, 1; OpenAsSelf
0x18004189b  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x1800418a2  call    cs:__imp_NtOpenThreadToken
0x1800418a8  mov     ebx, eax
0x1800418aa  test    eax, eax
0x1800418ac  js      loc_180041977
0x1800418b2  mov     rcx, [rbp+3Fh+TokenHandle]; TokenHandle
0x1800418b6  mov     r9d, 38h ; '8'; TokenInformationLength
0x1800418bc  lea     rax, [rbp+3Fh+var_A0]
0x1800418c0  lea     r8, [rbp+3Fh+TokenInformation]; TokenInformation
0x1800418c4  mov     [rsp+0E0h+ReturnLength], rax; ReturnLength
0x1800418c9  lea     edx, [r9-2Eh]; TokenInformationClass
0x1800418cd  call    cs:__imp_NtQueryInformationToken
0x1800418d3  mov     ebx, eax
0x1800418d5  test    eax, eax
0x1800418d7  js      loc_180041977
0x1800418dd  mov     r8d, 8; Length
0x1800418e3  lea     rdx, [rbp+3Fh+TokenInformation+8]; Source2
0x1800418e7  mov     rcx, r13; Source1
0x1800418ea  call    cs:__imp_RtlCompareMemory
0x1800418f0  cmp     rax, 8
0x1800418f4  jz      short loc_1800418FD
0x1800418f6  mov     ebx, 0C0000429h
0x1800418fb  jmp     short loc_180041977
0x1800418fd  neg     r12d
0x180041900  mov     edx, r15d; MemorySize
0x180041903  mov     rcx, rdi; Memory
0x180041906  sbb     r8d, r8d
0x180041909  and     r8d, 2
0x18004190d  add     r8d, 2; OptionFlags
0x180041911  call    cs:__imp_SystemFunction041
0x180041917  cmp     [rbp+3Fh+TokenHandle], 0
0x18004191c  mov     esi, eax
0x18004191e  jz      short loc_180041941
0x180041920  mov     r9d, 8; ThreadInformationLength
0x180041926  lea     r8, [rbp+3Fh+TokenHandle]; ThreadInformation
0x18004192a  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x180041931  lea     edx, [r9-3]; ThreadInformationClass
0x180041935  call    cs:__imp_NtSetInformationThread
0x18004193b  mov     ebx, eax
0x18004193d  test    eax, eax
0x18004193f  js      short loc_180041977
0x180041941  test    esi, esi
0x180041943  js      loc_180041A08
0x180041949  cmp     r15d, 4
0x18004194d  jnb     short loc_180041956
0x18004194f  mov     ebx, 0C000000Dh
0x180041954  jmp     short loc_180041977
0x180041956  mov     edx, [r15+rdi-4]
0x18004195b  test    edx, edx
0x18004195d  jz      short loc_18004194F
0x18004195f  lea     rcx, [r15-4]
0x180041963  cmp     rdx, rcx
0x180041966  ja      short loc_18004194F
0x180041968  mov     rax, [rbp+3Fh+var_88]
0x18004196c  mov     rcx, [rbp+3Fh+var_80]
0x180041970  mov     [rax], rdi
0x180041973  xor     ebx, ebx
0x180041975  mov     [rcx], edx
0x180041977  cmp     [rbp+3Fh+var_B0], 0
0x18004197b  jz      short loc_180041998
0x18004197d  mov     r9d, 8; ThreadInformationLength
0x180041983  lea     r8, [rbp+3Fh+TokenHandle]; ThreadInformation
0x180041987  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18004198e  lea     edx, [r9-3]; ThreadInformationClass
0x180041992  call    cs:__imp_NtSetInformationThread
0x180041998  mov     rcx, [rbp+3Fh+TokenHandle]; Handle
0x18004199c  test    rcx, rcx
0x18004199f  jz      short loc_1800419A7
0x1800419a1  call    cs:__imp_NtClose
0x1800419a7  mov     rcx, [rbp+3Fh+Handle]; Handle
0x1800419ab  test    rcx, rcx
0x1800419ae  jz      short loc_1800419B6
0x1800419b0  call    cs:__imp_NtClose
0x1800419b6  test    ebx, ebx
0x1800419b8  jns     short loc_1800419DF
0x1800419ba  test    rdi, rdi
0x1800419bd  jz      short loc_1800419DF
0x1800419bf  mov     rcx, r15
0x1800419c2  mov     rax, rdi
0x1800419c5  test    r15d, r15d
0x1800419c8  jz      short loc_1800419D6
0x1800419ca  mov     byte ptr [rax], 0
0x1800419cd  inc     rax
0x1800419d0  sub     rcx, 1
0x1800419d4  jnz     short loc_1800419CA
0x1800419d6  mov     rcx, rdi; hMem
0x1800419d9  call    cs:__imp_LocalFree
0x1800419df  mov     eax, ebx
0x1800419e1  mov     rcx, [rbp+3Fh+var_40]
0x1800419e5  xor     rcx, rsp; StackCookie
0x1800419e8  call    __security_check_cookie
0x1800419ed  mov     rbx, [rsp+0E0h+arg_0]
0x1800419f5  add     rsp, 0B0h
0x1800419fc  pop     r15
0x1800419fe  pop     r14
0x180041a00  pop     r13
0x180041a02  pop     r12
0x180041a04  pop     rdi
0x180041a05  pop     rsi
0x180041a06  pop     rbp
0x180041a07  retn
0x180041a08  mov     ebx, esi
0x180041a0a  jmp     loc_180041977
0x180041a0f  xor     edi, edi
0x180041a11  jmp     loc_180041970
```
