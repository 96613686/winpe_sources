# VaultAccessCheckCommon

- ea: `0x180027630`
- end: `0x180027970`
- name: `VaultAccessCheckCommon`
- size: `832`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180027550`
- `0x180027610`

## callees

- `0x180003140`
- `0x180027630`
- `0x18003a580`
- `0x18003b7b0`
- `0x18003b7d8`
- `0x18004d010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x1800277f9`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x1800277f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002781c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002781c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002767f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800278c0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027940`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800278c0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027940`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x18002789f`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x18002791c`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x18002789f`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x18002791c`
- `ntdll!NtOpenThreadToken` at `0x1800276ff`
- `ntdll!NtOpenThreadToken` at `0x1800276ff`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall VaultAccessCheckCommon(int a1, __int64 a2)
{
  __int64 v3; // rdi
  __int64 *v4; // rsi
  void *v5; // rbx
  NTSTATUS v6; // eax
  DWORD LastError; // eax
  _BYTE *v9; // rbx
  __int64 v10; // rax
  SIZE_T v11; // rax
  _BYTE *v12; // rcx
  _BYTE *v13; // rbx
  __int64 v14; // rax
  SIZE_T v15; // rax
  _BYTE *v16; // rcx
  WINBOOL AccessStatus; // [rsp+40h] [rbp-19h] BYREF
  BOOL (__stdcall *v18)(HANDLE); // [rsp+48h] [rbp-11h] BYREF
  void *TokenHandle; // [rsp+50h] [rbp-9h] BYREF
  unsigned int v20; // [rsp+58h] [rbp-1h]
  DWORD GrantedAccess; // [rsp+60h] [rbp+7h] BYREF
  DWORD PrivilegeSetLength; // [rsp+64h] [rbp+Bh] BYREF
  _GENERIC_MAPPING GenericMapping; // [rsp+68h] [rbp+Fh] BYREF
  struct _PRIVILEGE_SET PrivilegeSet; // [rsp+78h] [rbp+1Fh] BYREF

  v3 = a1;
  v4 = (&off_18005F000)[4 * (*(int (__fastcall **)(__int64))(*(_QWORD *)a2 + 16LL))(a2)];
  v18 = CloseHandle;
  TokenHandle = 0;
  v20 = 0;
  v5 = (void *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a2 + 8LL))(a2);
  if ( !v5 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_653e4a66d85f3580d6303a4ded660c7b_Traceguids);
LABEL_15:
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v18);
    return 0;
  }
  v6 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 8u, 1u, &TokenHandle);
  if ( v6 < 0 )
  {
    if ( v6 == -1073741700 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_653e4a66d85f3580d6303a4ded660c7b_Traceguids, 3221225596LL);
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        17,
        WPP_653e4a66d85f3580d6303a4ded660c7b_Traceguids,
        (unsigned int)v6);
    }
    goto LABEL_15;
  }
  *(_QWORD *)&GenericMapping.GenericRead = 0;
  *(_QWORD *)&GenericMapping.GenericExecute = 0;
  GrantedAccess = 0;
  AccessStatus = 0;
  memset(&PrivilegeSet, 0, sizeof(PrivilegeSet));
  PrivilegeSetLength = 20;
  if ( AccessCheck(
         v5,
         TokenHandle,
         v4[2 * v3],
         &GenericMapping,
         &PrivilegeSet,
         &PrivilegeSetLength,
         &GrantedAccess,
         &AccessStatus) )
  {
    if ( AccessStatus )
    {
      v13 = TokenHandle;
      if ( TokenHandle )
      {
        v14 = v20;
        if ( v20 )
        {
          do
          {
            *v13++ = 0;
            --v14;
          }
          while ( v14 );
          v13 = TokenHandle;
        }
        if ( v18 )
        {
          ((void (__fastcall *)(_BYTE *))v18)(v13);
        }
        else if ( v13 )
        {
          v15 = LocalSize(v13);
          if ( v15 )
          {
            v16 = v13;
            do
            {
              *v16++ = 0;
              --v15;
            }
            while ( v15 );
          }
          LocalFree(v13);
        }
      }
      return 1;
    }
    else
    {
      v9 = TokenHandle;
      if ( TokenHandle )
      {
        v10 = v20;
        if ( v20 )
        {
          do
          {
            *v9++ = 0;
            --v10;
          }
          while ( v10 );
          v9 = TokenHandle;
        }
        if ( v18 )
        {
          ((void (__fastcall *)(_BYTE *))v18)(v9);
        }
        else if ( v9 )
        {
          v11 = LocalSize(v9);
          if ( v11 )
          {
            v12 = v9;
            do
            {
              *v12++ = 0;
              --v11;
            }
            while ( v11 );
          }
          LocalFree(v9);
        }
      }
      return 0;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_653e4a66d85f3580d6303a4ded660c7b_Traceguids, LastError);
    }
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v18);
    return 0;
  }
}

```

## disassembly

```asm
0x180027630  mov     [rsp-8+arg_10], rbx
0x180027635  mov     [rsp-8+arg_18], rsi
0x18002763a  push    rbp
0x18002763b  push    rdi
0x18002763c  push    r14
0x18002763e  lea     rbp, [rsp-47h]
0x180027643  sub     rsp, 0A0h
0x18002764a  mov     rax, cs:__security_cookie
0x180027651  xor     rax, rsp
0x180027654  mov     [rbp+57h+var_20], rax
0x180027658  mov     rbx, rdx
0x18002765b  movsxd  rdi, ecx
0x18002765e  mov     rax, [rdx]
0x180027661  mov     rcx, rdx
0x180027664  mov     rax, [rax+10h]
0x180027668  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002766d  movsxd  rdx, eax
0x180027670  shl     rdx, 5
0x180027674  lea     rsi, off_18005F000
0x18002767b  mov     rsi, [rdx+rsi]
0x18002767f  mov     rax, cs:__imp_CloseHandle
0x180027686  mov     [rbp+57h+var_68], rax
0x18002768a  xor     r14d, r14d
0x18002768d  mov     [rbp+57h+TokenHandle], r14
0x180027691  mov     [rbp+57h+var_58], r14d
0x180027695  mov     rax, [rbx]
0x180027698  mov     rcx, rbx
0x18002769b  mov     rax, [rax+8]
0x18002769f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800276a4  mov     rbx, rax
0x1800276a7  test    rax, rax
0x1800276aa  jnz     short loc_1800276EC
0x1800276ac  lea     rax, WPP_GLOBAL_Control
0x1800276b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800276ba  cmp     rcx, rax
0x1800276bd  jz      short loc_1800276DB
0x1800276bf  test    byte ptr [rcx+1Ch], 2
0x1800276c3  jz      short loc_1800276DB
0x1800276c5  mov     edx, 0Fh
0x1800276ca  lea     r8, WPP_653e4a66d85f3580d6303a4ded660c7b_Traceguids
0x1800276d1  mov     rcx, [rcx+10h]
0x1800276d5  call    WPP_SF_
0x1800276da  nop
0x1800276db  lea     rcx, [rbp+57h+var_68]
0x1800276df  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x1800276e4  nop
0x1800276e5  xor     eax, eax
0x1800276e7  jmp     loc_18002794C
0x1800276ec  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x1800276f0  mov     r8b, 1; OpenAsSelf
0x1800276f3  mov     edx, 8; DesiredAccess
0x1800276f8  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x1800276ff  call    cs:__imp_NtOpenThreadToken
0x180027705  mov     r9d, eax
0x180027708  test    eax, eax
0x18002770a  jns     loc_18002779D
0x180027710  cmp     eax, 0C000007Ch
0x180027715  jnz     short loc_18002775D
0x180027717  lea     rax, WPP_GLOBAL_Control
0x18002771e  mov     rcx, cs:WPP_GLOBAL_Control
0x180027725  cmp     rcx, rax
0x180027728  jz      short loc_18002774C
0x18002772a  test    byte ptr [rcx+1Ch], 2
0x18002772e  jz      short loc_18002774C
0x180027730  mov     edx, 10h
0x180027735  mov     r9d, 0C000007Ch
0x18002773b  lea     r8, WPP_653e4a66d85f3580d6303a4ded660c7b_Traceguids
0x180027742  mov     rcx, [rcx+10h]
0x180027746  call    WPP_SF_d
0x18002774b  nop
0x18002774c  lea     rcx, [rbp+57h+var_68]
0x180027750  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180027755  nop
0x180027756  xor     eax, eax
0x180027758  jmp     loc_18002794C
0x18002775d  lea     rax, WPP_GLOBAL_Control
0x180027764  mov     rcx, cs:WPP_GLOBAL_Control
0x18002776b  cmp     rcx, rax
0x18002776e  jz      short loc_18002778C
0x180027770  test    byte ptr [rcx+1Ch], 2
0x180027774  jz      short loc_18002778C
0x180027776  mov     edx, 11h
0x18002777b  lea     r8, WPP_653e4a66d85f3580d6303a4ded660c7b_Traceguids
0x180027782  mov     rcx, [rcx+10h]
0x180027786  call    WPP_SF_d
0x18002778b  nop
0x18002778c  lea     rcx, [rbp+57h+var_68]
0x180027790  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180027795  nop
0x180027796  xor     eax, eax
0x180027798  jmp     loc_18002794C
0x18002779d  mov     qword ptr [rbp+57h+GenericMapping.GenericRead], r14
0x1800277a1  mov     qword ptr [rbp+57h+GenericMapping.GenericExecute], r14
0x1800277a5  mov     [rbp+57h+var_50], r14d
0x1800277a9  mov     [rbp+57h+var_70], r14d
0x1800277ad  xorps   xmm0, xmm0
0x1800277b0  xor     eax, eax
0x1800277b2  movups  xmmword ptr [rbp+57h+var_38.PrivilegeCount], xmm0
0x1800277b6  mov     [rbp+57h+var_38.Privilege.Attributes], eax
0x1800277b9  mov     [rbp+57h+var_4C], 14h
0x1800277c0  mov     r8, rdi
0x1800277c3  add     r8, r8
0x1800277c6  lea     rax, [rbp+57h+var_70]
0x1800277ca  mov     [rsp+0B0h+AccessStatus], rax; AccessStatus
0x1800277cf  lea     rax, [rbp+57h+var_50]
0x1800277d3  mov     [rsp+0B0h+GrantedAccess], rax; GrantedAccess
0x1800277d8  lea     rax, [rbp+57h+var_4C]
0x1800277dc  mov     [rsp+0B0h+PrivilegeSetLength], rax; PrivilegeSetLength
0x1800277e1  lea     rax, [rbp+57h+var_38]
0x1800277e5  mov     [rsp+0B0h+PrivilegeSet], rax; PrivilegeSet
0x1800277ea  lea     r9, [rbp+57h+GenericMapping]; GenericMapping
0x1800277ee  mov     r8d, [rsi+r8*8]; DesiredAccess
0x1800277f2  mov     rdx, [rbp+57h+TokenHandle]; ClientToken
0x1800277f6  mov     rcx, rbx; pSecurityDescriptor
0x1800277f9  call    cs:__imp_AccessCheck
0x1800277ff  test    eax, eax
0x180027801  jnz     short loc_180027853
0x180027803  lea     rax, WPP_GLOBAL_Control
0x18002780a  mov     rcx, cs:WPP_GLOBAL_Control
0x180027811  cmp     rcx, rax
0x180027814  jz      short loc_180027842
0x180027816  test    byte ptr [rcx+1Ch], 2
0x18002781a  jz      short loc_180027842
0x18002781c  call    cs:__imp_GetLastError
0x180027822  mov     edx, 12h
0x180027827  mov     r9d, eax
0x18002782a  lea     r8, WPP_653e4a66d85f3580d6303a4ded660c7b_Traceguids
0x180027831  mov     rcx, cs:WPP_GLOBAL_Control
0x180027838  mov     rcx, [rcx+10h]
0x18002783c  call    WPP_SF_d
0x180027841  nop
0x180027842  lea     rcx, [rbp+57h+var_68]
0x180027846  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18002784b  nop
0x18002784c  xor     eax, eax
0x18002784e  jmp     loc_18002794C
0x180027853  cmp     [rbp+57h+var_70], 0
0x180027857  jnz     short loc_1800278CE
0x180027859  mov     rbx, [rbp+57h+TokenHandle]
0x18002785d  test    rbx, rbx
0x180027860  jz      short loc_1800278C7
0x180027862  mov     eax, [rbp+57h+var_58]
0x180027865  test    eax, eax
0x180027867  jz      short loc_180027884
0x180027869  test    rbx, rbx
0x18002786c  jz      short loc_180027884
0x18002786e  test    rax, rax
0x180027871  jz      short loc_180027884
0x180027873  mov     byte ptr [rbx], 0
0x180027876  lea     rbx, [rbx+1]
0x18002787a  sub     rax, 1
0x18002787e  jnz     short loc_180027873
0x180027880  mov     rbx, [rbp+57h+TokenHandle]
0x180027884  mov     rax, [rbp+57h+var_68]
0x180027888  test    rax, rax
0x18002788b  jz      short loc_180027897
0x18002788d  mov     rcx, rbx
0x180027890  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027895  jmp     short loc_1800278C7
0x180027897  test    rbx, rbx
0x18002789a  jz      short loc_1800278C7
0x18002789c  mov     rcx, rbx; hMem
0x18002789f  call    cs:__imp_LocalSize
0x1800278a5  test    rax, rax
0x1800278a8  jz      short loc_1800278BD
0x1800278aa  mov     rcx, rbx
0x1800278ad  nop     dword ptr [rax]
0x1800278b0  mov     byte ptr [rcx], 0
0x1800278b3  lea     rcx, [rcx+1]
0x1800278b7  sub     rax, 1
0x1800278bb  jnz     short loc_1800278B0
0x1800278bd  mov     rcx, rbx; hMem
0x1800278c0  call    cs:__imp_LocalFree
0x1800278c6  nop
0x1800278c7  xor     eax, eax
0x1800278c9  jmp     loc_18002794C
0x1800278ce  mov     rbx, [rbp+57h+TokenHandle]
0x1800278d2  test    rbx, rbx
0x1800278d5  jz      short loc_180027947
0x1800278d7  mov     eax, [rbp+57h+var_58]
0x1800278da  test    eax, eax
0x1800278dc  jz      short loc_180027901
0x1800278de  test    rbx, rbx
0x1800278e1  jz      short loc_180027901
0x1800278e3  test    rax, rax
0x1800278e6  jz      short loc_180027901
0x1800278e8  nop     dword ptr [rax+rax+00000000h]
0x1800278f0  mov     byte ptr [rbx], 0
0x1800278f3  lea     rbx, [rbx+1]
0x1800278f7  sub     rax, 1
0x1800278fb  jnz     short loc_1800278F0
0x1800278fd  mov     rbx, [rbp+57h+TokenHandle]
0x180027901  mov     rax, [rbp+57h+var_68]
0x180027905  test    rax, rax
0x180027908  jz      short loc_180027914
0x18002790a  mov     rcx, rbx
0x18002790d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027912  jmp     short loc_180027947
0x180027914  test    rbx, rbx
0x180027917  jz      short loc_180027947
0x180027919  mov     rcx, rbx; hMem
0x18002791c  call    cs:__imp_LocalSize
0x180027922  test    rax, rax
0x180027925  jz      short loc_18002793D
0x180027927  mov     rcx, rbx
0x18002792a  nop     word ptr [rax+rax+00h]
0x180027930  mov     byte ptr [rcx], 0
0x180027933  lea     rcx, [rcx+1]
0x180027937  sub     rax, 1
0x18002793b  jnz     short loc_180027930
0x18002793d  mov     rcx, rbx; hMem
0x180027940  call    cs:__imp_LocalFree
0x180027946  nop
0x180027947  mov     eax, 1
0x18002794c  mov     rcx, [rbp+57h+var_20]
0x180027950  xor     rcx, rsp; StackCookie
0x180027953  call    __security_check_cookie
0x180027958  lea     r11, [rsp+0B0h+var_10]
0x180027960  mov     rbx, [r11+30h]
0x180027964  mov     rsi, [r11+38h]
0x180027968  mov     rsp, r11
0x18002796b  pop     r14
0x18002796d  pop     rdi
0x18002796e  pop     rbp
0x18002796f  retn
```
