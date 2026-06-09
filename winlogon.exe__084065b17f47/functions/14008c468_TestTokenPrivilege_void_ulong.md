# TestTokenPrivilege(void *,ulong)

- ea: `0x14008c468`
- end: `0x14008c64e`
- name: `?TestTokenPrivilege@@YAHPEAXK@Z`
- size: `486`
- prototype: `__int64 __fastcall(void *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1400833a0`

## callees

- `0x1400057f4`
- `0x1400198e0`
- `0x14001a200`
- `0x140041c34`
- `0x14008c468`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x14008c504`
- `ntdll!NtQueryInformationToken` at `0x14008c5bd`
- `ntdll!NtQueryInformationToken` at `0x14008c504`
- `ntdll!NtQueryInformationToken` at `0x14008c5bd`
- `ntdll!NtOpenProcessToken` at `0x14008c499`
- `ntdll!NtOpenProcessToken` at `0x14008c499`
- `ntdll!NtClose` at `0x14008c59a`
- `ntdll!NtClose` at `0x14008c5cd`
- `ntdll!NtClose` at `0x14008c59a`
- `ntdll!NtClose` at `0x14008c5cd`

## pseudocode

```c
__int64 __fastcall TestTokenPrivilege(void *a1)
{
  int v1; // ebx
  __int64 v2; // r9
  NTSTATUS v3; // eax
  __int64 v4; // r9
  _DWORD *v5; // rdi
  NTSTATUS v7; // esi
  __int64 v8; // r9
  unsigned int v9; // ebx
  __int64 i; // rcx
  void *TokenHandle; // [rsp+50h] [rbp+20h] BYREF
  ULONG TokenInformationLength; // [rsp+58h] [rbp+28h] BYREF
  _DWORD *v13; // [rsp+60h] [rbp+30h] BYREF

  TokenHandle = a1;
  v1 = 0;
  TokenInformationLength = 0;
  if ( !a1 )
  {
    if ( NtOpenProcessToken((HANDLE)0xFFFFFFFFFFFFFFFFLL, 8u, &TokenHandle) < 0 )
    {
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids, v2);
      }
      return 0;
    }
    a1 = TokenHandle;
    v1 = 1;
  }
  v3 = NtQueryInformationToken(a1, TokenPrivileges, 0, 0, &TokenInformationLength);
  if ( v3 != -1073741789 )
  {
    if ( v3 < 0
      && WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        54,
        WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids,
        (unsigned int)v3);
    }
LABEL_19:
    if ( v1 )
      NtClose(TokenHandle);
    return 0;
  }
  v13 = WLAlloc(TokenInformationLength);
  v5 = v13;
  if ( !v13 )
  {
    if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids, v4);
    }
    goto LABEL_19;
  }
  v7 = NtQueryInformationToken(TokenHandle, TokenPrivileges, v13, TokenInformationLength, &TokenInformationLength);
  if ( v1 )
    NtClose(TokenHandle);
  if ( v7 >= 0 )
  {
    v9 = 0;
    for ( i = 0; (unsigned int)i < *v5; i = (unsigned int)(i + 1) )
    {
      if ( *(_QWORD *)&v5[3 * i + 1] == 19 )
      {
        v9 = 1;
        break;
      }
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids, v8);
    }
    v9 = 0;
  }
  UHHeapFree((void **)&v13);
  return v9;
}

```

## disassembly

```asm
0x14008c468  mov     [rsp-18h+arg_18], rbx
0x14008c46d  mov     [rsp-18h+TokenInformationLength], edx
0x14008c471  mov     [rsp-18h+TokenHandle], rcx
0x14008c476  push    rbp
0x14008c477  push    rsi
0x14008c478  push    rdi
0x14008c479  mov     rbp, rsp
0x14008c47c  sub     rsp, 30h
0x14008c480  xor     ebx, ebx
0x14008c482  mov     [rbp+TokenInformationLength], 0
0x14008c489  test    rcx, rcx
0x14008c48c  jnz     short loc_14008C4EF
0x14008c48e  lea     r8, [rbp+TokenHandle]; TokenHandle
0x14008c492  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x14008c496  lea     edx, [rbx+8]; DesiredAccess
0x14008c499  call    cs:__imp_NtOpenProcessToken
0x14008c49f  test    eax, eax
0x14008c4a1  jns     short loc_14008C4E6
0x14008c4a3  mov     rcx, cs:WPP_GLOBAL_Control
0x14008c4aa  lea     rax, WPP_GLOBAL_Control
0x14008c4b1  cmp     rcx, rax
0x14008c4b4  jz      loc_14008C5A0
0x14008c4ba  test    byte ptr [rcx+1Ch], 1
0x14008c4be  jz      loc_14008C5A0
0x14008c4c4  cmp     byte ptr [rcx+19h], 2
0x14008c4c8  jb      loc_14008C5A0
0x14008c4ce  mov     rcx, [rcx+10h]
0x14008c4d2  lea     edx, [rbx+35h]
0x14008c4d5  lea     r8, WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids
0x14008c4dc  call    WPP_SF_
0x14008c4e1  jmp     loc_14008C5A0
0x14008c4e6  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x14008c4ea  mov     ebx, 1
0x14008c4ef  xor     r9d, r9d; TokenInformationLength
0x14008c4f2  lea     rax, [rbp+TokenInformationLength]
0x14008c4f6  xor     r8d, r8d; TokenInformation
0x14008c4f9  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x14008c4fe  lea     esi, [r9+3]
0x14008c502  mov     edx, esi; TokenInformationClass
0x14008c504  call    cs:__imp_NtQueryInformationToken
0x14008c50a  mov     r9d, eax
0x14008c50d  cmp     eax, 0C0000023h
0x14008c512  jz      short loc_14008C54C
0x14008c514  test    eax, eax
0x14008c516  jns     short loc_14008C592
0x14008c518  mov     rcx, cs:WPP_GLOBAL_Control
0x14008c51f  lea     rax, WPP_GLOBAL_Control
0x14008c526  cmp     rcx, rax
0x14008c529  jz      short loc_14008C592
0x14008c52b  test    byte ptr [rcx+1Ch], 1
0x14008c52f  jz      short loc_14008C592
0x14008c531  cmp     byte ptr [rcx+19h], 2
0x14008c535  jb      short loc_14008C592
0x14008c537  mov     rcx, [rcx+10h]
0x14008c53b  lea     edx, [rsi+33h]
0x14008c53e  lea     r8, WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids
0x14008c545  call    WPP_SF_d
0x14008c54a  jmp     short loc_14008C592
0x14008c54c  mov     ecx, [rbp+TokenInformationLength]; unsigned __int64
0x14008c54f  call    ?WLAlloc@@YAPEAX_K@Z; WLAlloc(unsigned __int64)
0x14008c554  mov     [rbp+arg_10], rax
0x14008c558  mov     rdi, rax
0x14008c55b  test    rax, rax
0x14008c55e  jnz     short loc_14008C5A7
0x14008c560  mov     rcx, cs:WPP_GLOBAL_Control
0x14008c567  lea     rax, WPP_GLOBAL_Control
0x14008c56e  cmp     rcx, rax
0x14008c571  jz      short loc_14008C592
0x14008c573  test    byte ptr [rcx+1Ch], 1
0x14008c577  jz      short loc_14008C592
0x14008c579  cmp     byte ptr [rcx+19h], 2
0x14008c57d  jb      short loc_14008C592
0x14008c57f  mov     rcx, [rcx+10h]
0x14008c583  lea     edx, [rdi+37h]
0x14008c586  lea     r8, WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids
0x14008c58d  call    WPP_SF_
0x14008c592  test    ebx, ebx
0x14008c594  jz      short loc_14008C5A0
0x14008c596  mov     rcx, [rbp+TokenHandle]; Handle
0x14008c59a  call    cs:__imp_NtClose
0x14008c5a0  xor     eax, eax
0x14008c5a2  jmp     loc_14008C641
0x14008c5a7  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x14008c5ab  lea     rax, [rbp+TokenInformationLength]
0x14008c5af  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x14008c5b3  mov     r8, rdi; TokenInformation
0x14008c5b6  mov     edx, esi; TokenInformationClass
0x14008c5b8  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x14008c5bd  call    cs:__imp_NtQueryInformationToken
0x14008c5c3  mov     esi, eax
0x14008c5c5  test    ebx, ebx
0x14008c5c7  jz      short loc_14008C5D3
0x14008c5c9  mov     rcx, [rbp+TokenHandle]; Handle
0x14008c5cd  call    cs:__imp_NtClose
0x14008c5d3  test    esi, esi
0x14008c5d5  jns     short loc_14008C60F
0x14008c5d7  mov     rcx, cs:WPP_GLOBAL_Control
0x14008c5de  lea     rax, WPP_GLOBAL_Control
0x14008c5e5  cmp     rcx, rax
0x14008c5e8  jz      short loc_14008C60B
0x14008c5ea  test    byte ptr [rcx+1Ch], 1
0x14008c5ee  jz      short loc_14008C60B
0x14008c5f0  cmp     byte ptr [rcx+19h], 2
0x14008c5f4  jb      short loc_14008C60B
0x14008c5f6  mov     rcx, [rcx+10h]
0x14008c5fa  lea     r8, WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids
0x14008c601  mov     edx, 38h ; '8'
0x14008c606  call    WPP_SF_
0x14008c60b  xor     ebx, ebx
0x14008c60d  jmp     short loc_14008C636
0x14008c60f  xor     ebx, ebx
0x14008c611  xor     ecx, ecx
0x14008c613  cmp     ecx, [rdi]
0x14008c615  jnb     short loc_14008C636
0x14008c617  lea     rax, [rcx+rcx*2]
0x14008c61b  mov     rax, [rdi+rax*4+4]
0x14008c620  cmp     eax, 13h
0x14008c623  jnz     short loc_14008C62D
0x14008c625  shr     rax, 20h
0x14008c629  test    eax, eax
0x14008c62b  jz      short loc_14008C631
0x14008c62d  inc     ecx
0x14008c62f  jmp     short loc_14008C613
0x14008c631  mov     ebx, 1
0x14008c636  lea     rcx, [rbp+arg_10]
0x14008c63a  call    UHHeapFree
0x14008c63f  mov     eax, ebx
0x14008c641  mov     rbx, [rsp+30h+arg_18]
0x14008c646  add     rsp, 30h
0x14008c64a  pop     rdi
0x14008c64b  pop     rsi
0x14008c64c  pop     rbp
0x14008c64d  retn
```
