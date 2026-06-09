# WDiagCheckRPCAccess(ulong)

- ea: `0x1801c875c`
- end: `0x1801c89ca`
- name: `?WDiagCheckRPCAccess@@YAKK@Z`
- size: `622`
- prototype: `__int64 __fastcall()`
- caller_count: `4`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1801c9940`
- `0x1801c9b50`
- `0x1801c9cd0`
- `0x1801ca360`

## callees

- `0x18000aa0c`
- `0x18000c800`
- `0x180011530`
- `0x18002f3d8`
- `0x18003e4c0`
- `0x1801c875c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801c88ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801c8928`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801c88ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801c8928`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801c8976`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801c8976`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1801c88c4`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1801c891e`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1801c88c4`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1801c891e`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1801c8874`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1801c888c`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1801c88a4`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1801c8874`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1801c888c`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1801c88a4`

## pseudocode

```c
__int64 __fastcall WDiagCheckRPCAccess()
{
  struct _TOKEN_USER *v0; // rdi
  DWORD LastError; // eax
  unsigned int v2; // ebx
  PVOID *v3; // rcx
  __int64 v4; // rdx
  unsigned int TokenUserInfo; // eax
  WINBOOL IsMember; // [rsp+50h] [rbp+30h] BYREF
  HANDLE TokenHandle; // [rsp+58h] [rbp+38h] BYREF
  struct _TOKEN_USER *v9; // [rsp+60h] [rbp+40h] BYREF

  v0 = 0;
  TokenHandle = 0;
  v9 = 0;
  IsMember = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 57) & 0x200) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 27), 21, &WPP_64982771a25e3baeccda56f411c86d84_Traceguids);
  LastError = LocalQueryRpcClientToken(&TokenHandle);
  v2 = LastError;
  if ( LastError )
  {
    v3 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 225)
      && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 2) != 0 )
    {
      v4 = 22;
LABEL_9:
      WPP_SF_d(v3[27], v4, &WPP_64982771a25e3baeccda56f411c86d84_Traceguids, LastError);
      goto LABEL_32;
    }
  }
  else
  {
    TokenUserInfo = GetTokenUserInfo(TokenHandle, &v9);
    v2 = TokenUserInfo;
    if ( TokenUserInfo )
    {
      v3 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || !*((_BYTE *)WPP_GLOBAL_Control + 225)
        || (*((_BYTE *)WPP_GLOBAL_Control + 228) & 2) == 0 )
      {
        v0 = v9;
        goto LABEL_33;
      }
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        23,
        &WPP_64982771a25e3baeccda56f411c86d84_Traceguids,
        TokenUserInfo);
      v0 = v9;
      goto LABEL_32;
    }
    v0 = v9;
    if ( EqualSid(v9->User.Sid, lpMem)
      || EqualSid(v0->User.Sid, qword_1802A35B8)
      || EqualSid(v0->User.Sid, qword_1802A35C0) )
    {
LABEL_32:
      v3 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_33;
    }
    IsMember = 0;
    if ( CheckTokenMembership(TokenHandle, SidToCheck, &IsMember) )
    {
      if ( IsMember )
        goto LABEL_32;
      IsMember = 0;
      if ( CheckTokenMembership(TokenHandle, qword_1802A35D0, &IsMember) )
      {
        if ( !IsMember )
          v2 = 740;
        goto LABEL_32;
      }
      LastError = GetLastError();
      v2 = LastError;
      v3 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 225)
        && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 2) != 0 )
      {
        v4 = 25;
        goto LABEL_9;
      }
    }
    else
    {
      LastError = GetLastError();
      v2 = LastError;
      v3 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 225)
        && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 2) != 0 )
      {
        v4 = 24;
        goto LABEL_9;
      }
    }
  }
LABEL_33:
  if ( TokenHandle )
  {
    CloseHandle(TokenHandle);
    v3 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v0 )
  {
    WDiagFreeMem(v0);
    v3 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v3 != &WPP_GLOBAL_Control && (*((_DWORD *)v3 + 57) & 0x200) != 0 )
    WPP_SF_(v3[27], 26, &WPP_64982771a25e3baeccda56f411c86d84_Traceguids);
  return v2;
}

```

## disassembly

```asm
0x1801c875c  mov     [rsp-28h+IsMember], ecx
0x1801c8760  push    rbp
0x1801c8761  push    rbx
0x1801c8762  push    rdi
0x1801c8763  push    r12
0x1801c8765  push    r15
0x1801c8767  mov     rbp, rsp
0x1801c876a  sub     rsp, 20h
0x1801c876e  xor     edi, edi
0x1801c8770  mov     [rbp+TokenHandle], 0
0x1801c8778  mov     [rbp+arg_10], rdi
0x1801c877c  mov     [rbp+IsMember], edi
0x1801c877f  mov     rcx, cs:WPP_GLOBAL_Control
0x1801c8786  lea     r15, WPP_GLOBAL_Control
0x1801c878d  lea     r12, WPP_64982771a25e3baeccda56f411c86d84_Traceguids
0x1801c8794  cmp     rcx, r15
0x1801c8797  jz      short loc_1801C87B7
0x1801c8799  test    dword ptr [rcx+0E4h], 200h
0x1801c87a3  jz      short loc_1801C87B7
0x1801c87a5  mov     rcx, [rcx+0D8h]
0x1801c87ac  lea     edx, [rdi+15h]
0x1801c87af  mov     r8, r12
0x1801c87b2  call    WPP_SF_
0x1801c87b7  lea     rcx, [rbp+TokenHandle]; void **
0x1801c87bb  call    ?LocalQueryRpcClientToken@@YAKPEAPEAX@Z; LocalQueryRpcClientToken(void * *)
0x1801c87c0  mov     ebx, eax
0x1801c87c2  test    eax, eax
0x1801c87c4  jz      short loc_1801C880C
0x1801c87c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1801c87cd  cmp     rcx, r15
0x1801c87d0  jz      loc_1801C896B
0x1801c87d6  cmp     byte ptr [rcx+0E1h], 1
0x1801c87dd  jb      loc_1801C896B
0x1801c87e3  test    byte ptr [rcx+0E4h], 2
0x1801c87ea  jz      loc_1801C896B
0x1801c87f0  mov     edx, 16h
0x1801c87f5  mov     rcx, [rcx+0D8h]
0x1801c87fc  mov     r9d, eax
0x1801c87ff  mov     r8, r12
0x1801c8802  call    WPP_SF_d
0x1801c8807  jmp     loc_1801C8964
0x1801c880c  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1801c8810  lea     rdx, [rbp+arg_10]; struct _TOKEN_USER **
0x1801c8814  call    ?GetTokenUserInfo@@YAKPEAXPEAPEAU_TOKEN_USER@@@Z; GetTokenUserInfo(void *,_TOKEN_USER * *)
0x1801c8819  mov     ebx, eax
0x1801c881b  test    eax, eax
0x1801c881d  jz      short loc_1801C8866
0x1801c881f  mov     rcx, cs:WPP_GLOBAL_Control
0x1801c8826  cmp     rcx, r15
0x1801c8829  jz      short loc_1801C885D
0x1801c882b  cmp     byte ptr [rcx+0E1h], 1
0x1801c8832  jb      short loc_1801C885D
0x1801c8834  test    byte ptr [rcx+0E4h], 2
0x1801c883b  jz      short loc_1801C885D
0x1801c883d  mov     rcx, [rcx+0D8h]
0x1801c8844  mov     edx, 17h
0x1801c8849  mov     r9d, eax
0x1801c884c  mov     r8, r12
0x1801c884f  call    WPP_SF_d
0x1801c8854  mov     rdi, [rbp+arg_10]
0x1801c8858  jmp     loc_1801C8964
0x1801c885d  mov     rdi, [rbp+arg_10]
0x1801c8861  jmp     loc_1801C896B
0x1801c8866  mov     rdi, [rbp+arg_10]
0x1801c886a  mov     rdx, cs:lpMem; pSid2
0x1801c8871  mov     rcx, [rdi]; pSid1
0x1801c8874  call    cs:__imp_EqualSid
0x1801c887a  test    eax, eax
0x1801c887c  jnz     loc_1801C8964
0x1801c8882  mov     rdx, cs:qword_1802A35B8; pSid2
0x1801c8889  mov     rcx, [rdi]; pSid1
0x1801c888c  call    cs:__imp_EqualSid
0x1801c8892  test    eax, eax
0x1801c8894  jnz     loc_1801C8964
0x1801c889a  mov     rdx, cs:qword_1802A35C0; pSid2
0x1801c88a1  mov     rcx, [rdi]; pSid1
0x1801c88a4  call    cs:__imp_EqualSid
0x1801c88aa  test    eax, eax
0x1801c88ac  jnz     loc_1801C8964
0x1801c88b2  mov     rdx, cs:SidToCheck; SidToCheck
0x1801c88b9  lea     r8, [rbp+IsMember]; IsMember
0x1801c88bd  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1801c88c1  mov     [rbp+IsMember], eax
0x1801c88c4  call    cs:__imp_CheckTokenMembership
0x1801c88ca  test    eax, eax
0x1801c88cc  jnz     short loc_1801C8902
0x1801c88ce  call    cs:__imp_GetLastError
0x1801c88d4  mov     ebx, eax
0x1801c88d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1801c88dd  cmp     rcx, r15
0x1801c88e0  jz      loc_1801C896B
0x1801c88e6  cmp     byte ptr [rcx+0E1h], 1
0x1801c88ed  jb      short loc_1801C896B
0x1801c88ef  test    byte ptr [rcx+0E4h], 2
0x1801c88f6  jz      short loc_1801C896B
0x1801c88f8  mov     edx, 18h
0x1801c88fd  jmp     loc_1801C87F5
0x1801c8902  cmp     [rbp+IsMember], 0
0x1801c8906  jnz     short loc_1801C8964
0x1801c8908  mov     rdx, cs:qword_1802A35D0; SidToCheck
0x1801c890f  lea     r8, [rbp+IsMember]; IsMember
0x1801c8913  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1801c8917  mov     [rbp+IsMember], 0
0x1801c891e  call    cs:__imp_CheckTokenMembership
0x1801c8924  test    eax, eax
0x1801c8926  jnz     short loc_1801C8958
0x1801c8928  call    cs:__imp_GetLastError
0x1801c892e  mov     ebx, eax
0x1801c8930  mov     rcx, cs:WPP_GLOBAL_Control
0x1801c8937  cmp     rcx, r15
0x1801c893a  jz      short loc_1801C896B
0x1801c893c  cmp     byte ptr [rcx+0E1h], 1
0x1801c8943  jb      short loc_1801C896B
0x1801c8945  test    byte ptr [rcx+0E4h], 2
0x1801c894c  jz      short loc_1801C896B
0x1801c894e  mov     edx, 19h
0x1801c8953  jmp     loc_1801C87F5
0x1801c8958  cmp     [rbp+IsMember], 0
0x1801c895c  mov     eax, 2E4h
0x1801c8961  cmovz   ebx, eax
0x1801c8964  mov     rcx, cs:WPP_GLOBAL_Control
0x1801c896b  cmp     [rbp+TokenHandle], 0
0x1801c8970  jz      short loc_1801C8983
0x1801c8972  mov     rcx, [rbp+TokenHandle]; hObject
0x1801c8976  call    cs:__imp_CloseHandle
0x1801c897c  mov     rcx, cs:WPP_GLOBAL_Control
0x1801c8983  test    rdi, rdi
0x1801c8986  jz      short loc_1801C8997
0x1801c8988  mov     rcx, rdi; lpMem
0x1801c898b  call    ?WDiagFreeMem@@YAXPEAX@Z; WDiagFreeMem(void *)
0x1801c8990  mov     rcx, cs:WPP_GLOBAL_Control
0x1801c8997  cmp     rcx, r15
0x1801c899a  jz      short loc_1801C89BC
0x1801c899c  test    dword ptr [rcx+0E4h], 200h
0x1801c89a6  jz      short loc_1801C89BC
0x1801c89a8  mov     rcx, [rcx+0D8h]
0x1801c89af  mov     edx, 1Ah
0x1801c89b4  mov     r8, r12
0x1801c89b7  call    WPP_SF_
0x1801c89bc  mov     eax, ebx
0x1801c89be  add     rsp, 20h
0x1801c89c2  pop     r15
0x1801c89c4  pop     r12
0x1801c89c6  pop     rdi
0x1801c89c7  pop     rbx
0x1801c89c8  pop     rbp
0x1801c89c9  retn
```
