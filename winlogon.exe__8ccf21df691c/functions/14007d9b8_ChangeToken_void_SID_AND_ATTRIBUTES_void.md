# ChangeToken(void *,_SID_AND_ATTRIBUTES *,void * *)

- ea: `0x14007d9b8`
- end: `0x14007e071`
- name: `?ChangeToken@@YAHPEAXPEAU_SID_AND_ATTRIBUTES@@PEAPEAX@Z`
- size: `1721`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, struct _SID_AND_ATTRIBUTES *, void **)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x14007e468`

## callees

- `0x1400057f4`
- `0x140041c34`
- `0x140053720`
- `0x14007d9b8`
- `0x14007e518`
- `0x14009cc54`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14007dac9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14007dac9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14007dfa9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14007dfc6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14007dfdf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14007dff8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14007e015`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14007e032`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14007dfa9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14007dfc6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14007dfdf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14007dff8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14007e015`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14007e032`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14007daba`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14007df9b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14007dfb8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14007dfd1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14007dfea`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14007e007`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14007e024`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14007daba`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14007df9b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14007dfb8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14007dfd1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14007dfea`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14007e007`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14007e024`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007da8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007db02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007dba6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007dc13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007dc65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007dcba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007dd1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007dd7a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007da8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007db02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007dba6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007dc13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007dc65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007dcba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007dd1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007dd7a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14007e041`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14007e041`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14007dce5`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14007dd45`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14007dce5`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14007dd45`
- `ntdll!NtSetInformationToken` at `0x14007df21`
- `ntdll!NtSetInformationToken` at `0x14007df21`
- `ntdll!NtCreateToken` at `0x14007de61`
- `ntdll!NtCreateToken` at `0x14007de61`
- `ntdll!RtlAdjustPrivilege` at `0x14007ddc9`
- `ntdll!RtlAdjustPrivilege` at `0x14007ddc9`
- `ntdll!NtQueryInformationToken` at `0x14007decf`
- `ntdll!NtQueryInformationToken` at `0x14007decf`

## pseudocode

```c
__int64 __fastcall ChangeToken(HANDLE TokenHandle, struct _SID_AND_ATTRIBUTES *a2, void **a3)
{
  struct _TOKEN_DEFAULT_DACL *TokenDefaultDacl; // r15
  unsigned int v7; // r13d
  int TokenInformationWithAlloc; // eax
  unsigned int *v9; // r12
  DWORD LastError; // eax
  __int64 v11; // rbx
  HANDLE ProcessHeap; // rax
  struct _TOKEN_GROUPS *v13; // rax
  struct _TOKEN_GROUPS *TokenGroups; // rbx
  DWORD v15; // eax
  int v16; // eax
  DWORD v17; // eax
  __int64 v18; // rdx
  CUser *v19; // rcx
  __int64 v20; // r9
  NTSTATUS v21; // eax
  NTSTATUS v22; // eax
  NTSTATUS v23; // eax
  NTSTATUS v24; // eax
  void *v25; // rax
  HANDLE v26; // rax
  PTOKEN_PRIMARY_GROUP v27; // rbx
  HANDLE v28; // rax
  HANDLE v29; // rax
  HANDLE v30; // rax
  PTOKEN_PRIVILEGES v31; // rbx
  HANDLE v32; // rax
  PTOKEN_USER v33; // rbx
  HANDLE v34; // rax
  unsigned int Size; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int8 Size_4; // [rsp+74h] [rbp-8Ch] BYREF
  int v38; // [rsp+78h] [rbp-88h] BYREF
  void *TokenHandlea; // [rsp+80h] [rbp-80h] BYREF
  PTOKEN_PRIMARY_GROUP TokenPrimaryGroup; // [rsp+88h] [rbp-78h] BYREF
  PTOKEN_PRIVILEGES TokenPrivileges; // [rsp+90h] [rbp-70h] BYREF
  PTOKEN_USER TokenUser; // [rsp+98h] [rbp-68h] BYREF
  void *Src; // [rsp+A0h] [rbp-60h] BYREF
  PTOKEN_DEFAULT_DACL v44; // [rsp+A8h] [rbp-58h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v46; // [rsp+E0h] [rbp-20h] BYREF
  int v47; // [rsp+E8h] [rbp-18h]
  struct _TOKEN_SOURCE TokenSource; // [rsp+F0h] [rbp-10h] BYREF
  __int128 TokenInformation; // [rsp+100h] [rbp+0h] BYREF
  union _LARGE_INTEGER ExpirationTime[2]; // [rsp+110h] [rbp+10h] BYREF
  __int128 v51; // [rsp+120h] [rbp+20h]
  __int64 v52; // [rsp+130h] [rbp+30h]

  v52 = 0;
  *a3 = 0;
  TokenPrimaryGroup = 0;
  TokenDefaultDacl = 0;
  v44 = 0;
  Src = 0;
  TokenPrivileges = 0;
  TokenUser = 0;
  v7 = 0;
  TokenHandlea = 0;
  v38 = 0;
  Size = 0;
  Size_4 = 0;
  TokenInformation = 0;
  v46 = 0;
  *(_OWORD *)&ExpirationTime[0].LowPart = 0;
  v47 = 0;
  v51 = 0;
  TokenSource = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  TokenInformationWithAlloc = GetTokenInformationWithAlloc(TokenHandle, TokenGroups, &Src, &Size);
  v9 = (unsigned int *)Src;
  if ( !TokenInformationWithAlloc )
  {
    if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_f970564fce7b32792e727784e751b97c_Traceguids, LastError);
    }
    goto LABEL_72;
  }
  v11 = Size;
  ProcessHeap = GetProcessHeap();
  v13 = (struct _TOKEN_GROUPS *)HeapAlloc(ProcessHeap, 0, v11 + 16);
  TokenGroups = v13;
  if ( !v13 )
  {
    if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v15 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_f970564fce7b32792e727784e751b97c_Traceguids, v15);
    }
    goto LABEL_68;
  }
  memcpy_0(v13, v9, Size);
  TokenGroups->Groups[*v9].Attributes = a2->Attributes;
  TokenGroups->Groups[*v9].Sid = a2->Sid;
  ++TokenGroups->GroupCount;
  v16 = GetTokenInformationWithAlloc(TokenHandle, TokenDefaultDacl, (void **)&v44, &Size);
  TokenDefaultDacl = v44;
  if ( !v16 )
  {
    if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_67;
    }
    v17 = GetLastError();
    v18 = 18;
    goto LABEL_16;
  }
  if ( !(unsigned int)GetTokenInformationWithAlloc(TokenHandle, TokenUser, (void **)&TokenUser, &Size) )
  {
    if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_67;
    }
    v17 = GetLastError();
    v18 = 19;
    goto LABEL_16;
  }
  if ( !(unsigned int)GetTokenInformationWithAlloc(TokenHandle, TokenPrivileges, (void **)&TokenPrivileges, &Size) )
  {
    if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_67;
    }
    v17 = GetLastError();
    v18 = 20;
    goto LABEL_16;
  }
  if ( !(unsigned int)GetTokenInformationWithAlloc(TokenHandle, TokenPrimaryGroup, (void **)&TokenPrimaryGroup, &Size) )
  {
    if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_67;
    }
    v17 = GetLastError();
    v18 = 21;
    goto LABEL_16;
  }
  if ( !GetTokenInformation(TokenHandle, TokenStatistics, &TokenInformation, 0x38u, &Size) )
  {
    if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_67;
    }
    v17 = GetLastError();
    v18 = 22;
    goto LABEL_16;
  }
  if ( !GetTokenInformation(TokenHandle, TokenSource, &TokenSource, 0x10u, &Size) )
  {
    if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_67;
    }
    v17 = GetLastError();
    v18 = 23;
LABEL_16:
    v19 = WPP_GLOBAL_Control;
    v20 = v17;
LABEL_17:
    WPP_SF_d(*((_QWORD *)v19 + 2), v18, WPP_f970564fce7b32792e727784e751b97c_Traceguids, v20);
    goto LABEL_67;
  }
  memset(&ObjectAttributes.RootDirectory, 0, 20);
  ObjectAttributes.SecurityDescriptor = 0;
  ObjectAttributes.Length = 48;
  LOWORD(v47) = 1;
  v46 = 0x20000000CLL;
  ObjectAttributes.SecurityQualityOfService = &v46;
  v21 = RtlAdjustPrivilege(2u, 1u, 0, &Size_4);
  v20 = (unsigned int)v21;
  if ( v21 < 0 )
  {
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_67;
    }
    v18 = 24;
    goto LABEL_17;
  }
  v22 = NtCreateToken(
          &TokenHandlea,
          0xF01FFu,
          &ObjectAttributes,
          TokenPrimary,
          (PLUID)&TokenInformation + 1,
          ExpirationTime,
          TokenUser,
          TokenGroups,
          TokenPrivileges,
          0,
          TokenPrimaryGroup,
          TokenDefaultDacl,
          &TokenSource);
  v20 = (unsigned int)v22;
  if ( v22 < 0 )
  {
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_67;
    }
    v18 = 25;
    goto LABEL_17;
  }
  v23 = NtQueryInformationToken(TokenHandle, TokenSessionId, &v38, 4u, &Size);
  v20 = (unsigned int)v23;
  if ( v23 < 0 )
  {
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_67;
    }
    v18 = 26;
    goto LABEL_17;
  }
  v24 = NtSetInformationToken(TokenHandlea, TokenSessionId, &v38, 4u);
  v20 = (unsigned int)v24;
  if ( v24 >= 0 )
  {
    v25 = TokenHandlea;
    TokenHandlea = 0;
    v7 = 1;
    *a3 = v25;
    if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_f970564fce7b32792e727784e751b97c_Traceguids);
    }
    goto LABEL_67;
  }
  v19 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v18 = 27;
    goto LABEL_17;
  }
LABEL_67:
  v26 = GetProcessHeap();
  HeapFree(v26, 0, TokenGroups);
LABEL_68:
  v27 = TokenPrimaryGroup;
  if ( TokenPrimaryGroup )
  {
    v28 = GetProcessHeap();
    HeapFree(v28, 0, v27);
  }
  if ( TokenDefaultDacl )
  {
    v29 = GetProcessHeap();
    HeapFree(v29, 0, TokenDefaultDacl);
  }
LABEL_72:
  if ( v9 )
  {
    v30 = GetProcessHeap();
    HeapFree(v30, 0, v9);
  }
  v31 = TokenPrivileges;
  if ( TokenPrivileges )
  {
    v32 = GetProcessHeap();
    HeapFree(v32, 0, v31);
  }
  v33 = TokenUser;
  if ( TokenUser )
  {
    v34 = GetProcessHeap();
    HeapFree(v34, 0, v33);
  }
  if ( TokenHandlea )
    CloseHandle(TokenHandlea);
  return v7;
}

```

## disassembly

```asm
0x14007d9b8  mov     [rsp-8+arg_8], rbx
0x14007d9bd  push    rbp
0x14007d9be  push    rsi
0x14007d9bf  push    rdi
0x14007d9c0  push    r12
0x14007d9c2  push    r13
0x14007d9c4  push    r14
0x14007d9c6  push    r15
0x14007d9c8  lea     rbp, [rsp-40h]
0x14007d9cd  sub     rsp, 140h
0x14007d9d4  mov     rax, cs:__security_cookie
0x14007d9db  xor     rax, rsp
0x14007d9de  mov     [rbp+70h+var_38], rax
0x14007d9e2  xorps   xmm0, xmm0
0x14007d9e5  lea     r9, [rsp+170h+Size]; unsigned int *
0x14007d9ea  xor     eax, eax
0x14007d9ec  mov     rdi, rcx
0x14007d9ef  xor     ecx, ecx
0x14007d9f1  mov     [rbp+70h+var_40], rax
0x14007d9f5  mov     [r8], rcx
0x14007d9f8  mov     r14, r8
0x14007d9fb  mov     rsi, rdx
0x14007d9fe  mov     [rbp+70h+var_E8], rcx
0x14007da02  mov     r15d, ecx
0x14007da05  mov     [rbp+70h+var_C8], rcx
0x14007da09  mov     [rbp+70h+Src], rcx
0x14007da0d  lea     edx, [rax+2]; TokenInformationClass
0x14007da10  mov     [rbp+70h+var_E0], rcx
0x14007da14  lea     r8, [rbp+70h+Src]; void **
0x14007da18  mov     [rbp+70h+var_D8], rcx
0x14007da1c  mov     r13d, ecx
0x14007da1f  mov     [rbp+70h+TokenHandle], rcx
0x14007da23  mov     [rsp+170h+var_F8], ecx
0x14007da27  mov     dword ptr [rsp+170h+Size], ecx
0x14007da2b  mov     byte ptr [rsp+170h+Size+4], cl
0x14007da2f  mov     rcx, rdi; TokenHandle
0x14007da32  movups  [rbp+70h+TokenInformation], xmm0
0x14007da36  mov     [rbp+70h+var_90], rax
0x14007da3a  movups  xmmword ptr [rbp+70h+var_60], xmm0
0x14007da3e  mov     [rbp+70h+var_88], eax
0x14007da41  movups  [rbp+70h+var_50], xmm0
0x14007da45  movups  xmmword ptr [rbp+70h+var_80.SourceName], xmm0
0x14007da49  movups  xmmword ptr [rbp+70h+ObjectAttributes.Length], xmm0
0x14007da4d  movups  xmmword ptr [rbp+70h+ObjectAttributes.ObjectName], xmm0
0x14007da51  movups  xmmword ptr [rbp+70h+ObjectAttributes.SecurityDescriptor], xmm0
0x14007da55  call    ?GetTokenInformationWithAlloc@@YAHPEAXW4_TOKEN_INFORMATION_CLASS@@PEAPEAXPEAK@Z; GetTokenInformationWithAlloc(void *,_TOKEN_INFORMATION_CLASS,void * *,ulong *)
0x14007da5a  mov     r12, [rbp+70h+Src]
0x14007da5e  test    eax, eax
0x14007da60  jnz     short loc_14007DAB6
0x14007da62  mov     rcx, cs:WPP_GLOBAL_Control
0x14007da69  lea     rax, WPP_GLOBAL_Control
0x14007da70  cmp     rcx, rax
0x14007da73  jz      loc_14007DFE5
0x14007da79  test    byte ptr [rcx+1Ch], 2
0x14007da7d  jz      loc_14007DFE5
0x14007da83  cmp     byte ptr [rcx+19h], 2
0x14007da87  jb      loc_14007DFE5
0x14007da8d  call    cs:__imp_GetLastError
0x14007da93  mov     rcx, cs:WPP_GLOBAL_Control
0x14007da9a  lea     edx, [r15+10h]
0x14007da9e  mov     r9d, eax
0x14007daa1  lea     r8, WPP_f970564fce7b32792e727784e751b97c_Traceguids
0x14007daa8  mov     rcx, [rcx+10h]
0x14007daac  call    WPP_SF_d
0x14007dab1  jmp     loc_14007DFE5
0x14007dab6  mov     ebx, dword ptr [rsp+170h+Size]
0x14007daba  call    cs:__imp_GetProcessHeap
0x14007dac0  lea     r8, [rbx+10h]; dwBytes
0x14007dac4  xor     edx, edx; dwFlags
0x14007dac6  mov     rcx, rax; hHeap
0x14007dac9  call    cs:__imp_HeapAlloc
0x14007dacf  mov     rbx, rax
0x14007dad2  test    rax, rax
0x14007dad5  jnz     short loc_14007DB2A
0x14007dad7  mov     rcx, cs:WPP_GLOBAL_Control
0x14007dade  lea     rax, WPP_GLOBAL_Control
0x14007dae5  cmp     rcx, rax
0x14007dae8  jz      loc_14007DFAF
0x14007daee  test    byte ptr [rcx+1Ch], 2
0x14007daf2  jz      loc_14007DFAF
0x14007daf8  cmp     byte ptr [rcx+19h], 2
0x14007dafc  jb      loc_14007DFAF
0x14007db02  call    cs:__imp_GetLastError
0x14007db08  mov     rcx, cs:WPP_GLOBAL_Control
0x14007db0f  lea     edx, [rbx+11h]
0x14007db12  mov     r9d, eax
0x14007db15  lea     r8, WPP_f970564fce7b32792e727784e751b97c_Traceguids
0x14007db1c  mov     rcx, [rcx+10h]
0x14007db20  call    WPP_SF_d
0x14007db25  jmp     loc_14007DFAF
0x14007db2a  mov     r8d, dword ptr [rsp+170h+Size]; Size
0x14007db2f  mov     rdx, r12; Src
0x14007db32  mov     rcx, rbx; void *
0x14007db35  call    memcpy_0
0x14007db3a  mov     ecx, [r12]
0x14007db3e  lea     r9, [rsp+170h+Size]; unsigned int *
0x14007db43  mov     eax, [rsi+8]
0x14007db46  lea     r8, [rbp+70h+var_C8]; void **
0x14007db4a  inc     rcx
0x14007db4d  mov     edx, 6; TokenInformationClass
0x14007db52  add     rcx, rcx
0x14007db55  mov     [rbx+rcx*8], eax
0x14007db58  mov     ecx, [r12]
0x14007db5c  mov     rax, [rsi]
0x14007db5f  add     rcx, rcx
0x14007db62  mov     [rbx+rcx*8+8], rax
0x14007db67  mov     rcx, rdi; TokenHandle
0x14007db6a  inc     dword ptr [rbx]
0x14007db6c  call    ?GetTokenInformationWithAlloc@@YAHPEAXW4_TOKEN_INFORMATION_CLASS@@PEAPEAXPEAK@Z; GetTokenInformationWithAlloc(void *,_TOKEN_INFORMATION_CLASS,void * *,ulong *)
0x14007db71  mov     r15, [rbp+70h+var_C8]
0x14007db75  xor     esi, esi
0x14007db77  test    eax, eax
0x14007db79  jnz     short loc_14007DBCE
0x14007db7b  mov     rcx, cs:WPP_GLOBAL_Control
0x14007db82  lea     rax, WPP_GLOBAL_Control
0x14007db89  cmp     rcx, rax
0x14007db8c  jz      loc_14007DF9B
0x14007db92  test    byte ptr [rcx+1Ch], 2
0x14007db96  jz      loc_14007DF9B
0x14007db9c  cmp     byte ptr [rcx+19h], 2
0x14007dba0  jb      loc_14007DF9B
0x14007dba6  call    cs:__imp_GetLastError
0x14007dbac  lea     edx, [rsi+12h]
0x14007dbaf  mov     rcx, cs:WPP_GLOBAL_Control
0x14007dbb6  mov     r9d, eax
0x14007dbb9  mov     rcx, [rcx+10h]
0x14007dbbd  lea     r8, WPP_f970564fce7b32792e727784e751b97c_Traceguids
0x14007dbc4  call    WPP_SF_d
0x14007dbc9  jmp     loc_14007DF9B
0x14007dbce  lea     r9, [rsp+170h+Size]; unsigned int *
0x14007dbd3  mov     edx, 1; TokenInformationClass
0x14007dbd8  lea     r8, [rbp+70h+var_D8]; void **
0x14007dbdc  mov     rcx, rdi; TokenHandle
0x14007dbdf  call    ?GetTokenInformationWithAlloc@@YAHPEAXW4_TOKEN_INFORMATION_CLASS@@PEAPEAXPEAK@Z; GetTokenInformationWithAlloc(void *,_TOKEN_INFORMATION_CLASS,void * *,ulong *)
0x14007dbe4  test    eax, eax
0x14007dbe6  jnz     short loc_14007DC20
0x14007dbe8  mov     rcx, cs:WPP_GLOBAL_Control
0x14007dbef  lea     rax, WPP_GLOBAL_Control
0x14007dbf6  cmp     rcx, rax
0x14007dbf9  jz      loc_14007DF9B
0x14007dbff  test    byte ptr [rcx+1Ch], 2
0x14007dc03  jz      loc_14007DF9B
0x14007dc09  cmp     byte ptr [rcx+19h], 2
0x14007dc0d  jb      loc_14007DF9B
0x14007dc13  call    cs:__imp_GetLastError
0x14007dc19  mov     edx, 13h
0x14007dc1e  jmp     short loc_14007DBAF
0x14007dc20  lea     r9, [rsp+170h+Size]; unsigned int *
0x14007dc25  mov     edx, 3; TokenInformationClass
0x14007dc2a  lea     r8, [rbp+70h+var_E0]; void **
0x14007dc2e  mov     rcx, rdi; TokenHandle
0x14007dc31  call    ?GetTokenInformationWithAlloc@@YAHPEAXW4_TOKEN_INFORMATION_CLASS@@PEAPEAXPEAK@Z; GetTokenInformationWithAlloc(void *,_TOKEN_INFORMATION_CLASS,void * *,ulong *)
0x14007dc36  test    eax, eax
0x14007dc38  jnz     short loc_14007DC75
0x14007dc3a  mov     rcx, cs:WPP_GLOBAL_Control
0x14007dc41  lea     rax, WPP_GLOBAL_Control
0x14007dc48  cmp     rcx, rax
0x14007dc4b  jz      loc_14007DF9B
0x14007dc51  test    byte ptr [rcx+1Ch], 2
0x14007dc55  jz      loc_14007DF9B
0x14007dc5b  cmp     byte ptr [rcx+19h], 2
0x14007dc5f  jb      loc_14007DF9B
0x14007dc65  call    cs:__imp_GetLastError
0x14007dc6b  mov     edx, 14h
0x14007dc70  jmp     loc_14007DBAF
0x14007dc75  lea     r9, [rsp+170h+Size]; unsigned int *
0x14007dc7a  mov     edx, 5; TokenInformationClass
0x14007dc7f  lea     r8, [rbp+70h+var_E8]; void **
0x14007dc83  mov     rcx, rdi; TokenHandle
0x14007dc86  call    ?GetTokenInformationWithAlloc@@YAHPEAXW4_TOKEN_INFORMATION_CLASS@@PEAPEAXPEAK@Z; GetTokenInformationWithAlloc(void *,_TOKEN_INFORMATION_CLASS,void * *,ulong *)
0x14007dc8b  test    eax, eax
0x14007dc8d  jnz     short loc_14007DCCA
0x14007dc8f  mov     rcx, cs:WPP_GLOBAL_Control
0x14007dc96  lea     rax, WPP_GLOBAL_Control
0x14007dc9d  cmp     rcx, rax
0x14007dca0  jz      loc_14007DF9B
0x14007dca6  test    byte ptr [rcx+1Ch], 2
0x14007dcaa  jz      loc_14007DF9B
0x14007dcb0  cmp     byte ptr [rcx+19h], 2
0x14007dcb4  jb      loc_14007DF9B
0x14007dcba  call    cs:__imp_GetLastError
0x14007dcc0  mov     edx, 15h
0x14007dcc5  jmp     loc_14007DBAF
0x14007dcca  mov     r9d, 38h ; '8'; TokenInformationLength
0x14007dcd0  lea     rax, [rsp+170h+Size]
0x14007dcd5  lea     r8, [rbp+70h+TokenInformation]; TokenInformation
0x14007dcd9  mov     [rsp+170h+ReturnLength], rax; ReturnLength
0x14007dcde  mov     rcx, rdi; TokenHandle
0x14007dce1  lea     edx, [r9-2Eh]; TokenInformationClass
0x14007dce5  call    cs:__imp_GetTokenInformation
0x14007dceb  test    eax, eax
0x14007dced  jnz     short loc_14007DD2A
0x14007dcef  mov     rcx, cs:WPP_GLOBAL_Control
0x14007dcf6  lea     rax, WPP_GLOBAL_Control
0x14007dcfd  cmp     rcx, rax
0x14007dd00  jz      loc_14007DF9B
0x14007dd06  test    byte ptr [rcx+1Ch], 2
0x14007dd0a  jz      loc_14007DF9B
0x14007dd10  cmp     byte ptr [rcx+19h], 2
0x14007dd14  jb      loc_14007DF9B
0x14007dd1a  call    cs:__imp_GetLastError
0x14007dd20  mov     edx, 16h
0x14007dd25  jmp     loc_14007DBAF
0x14007dd2a  mov     r9d, 10h; TokenInformationLength
0x14007dd30  lea     rax, [rsp+170h+Size]
0x14007dd35  lea     r8, [rbp+70h+var_80]; TokenInformation
0x14007dd39  mov     [rsp+170h+ReturnLength], rax; ReturnLength
0x14007dd3e  mov     rcx, rdi; TokenHandle
0x14007dd41  lea     edx, [r9-9]; TokenInformationClass
0x14007dd45  call    cs:__imp_GetTokenInformation
0x14007dd4b  test    eax, eax
0x14007dd4d  jnz     short loc_14007DD8A
0x14007dd4f  mov     rcx, cs:WPP_GLOBAL_Control
0x14007dd56  lea     rax, WPP_GLOBAL_Control
0x14007dd5d  cmp     rcx, rax
0x14007dd60  jz      loc_14007DF9B
0x14007dd66  test    byte ptr [rcx+1Ch], 2
0x14007dd6a  jz      loc_14007DF9B
0x14007dd70  cmp     byte ptr [rcx+19h], 2
0x14007dd74  jb      loc_14007DF9B
0x14007dd7a  call    cs:__imp_GetLastError
0x14007dd80  mov     edx, 17h
0x14007dd85  jmp     loc_14007DBAF
0x14007dd8a  mov     [rbp+70h+ObjectAttributes.RootDirectory], rsi
0x14007dd8e  lea     rax, [rbp+70h+var_90]
0x14007dd92  mov     [rbp+70h+ObjectAttributes.Attributes], esi
0x14007dd95  lea     r9, [rsp+170h+Size+4]; OldValue
0x14007dd9a  mov     [rbp+70h+ObjectAttributes.ObjectName], rsi
0x14007dd9e  xor     r8d, r8d; ForThread
0x14007dda1  mov     [rbp+70h+ObjectAttributes.SecurityDescriptor], rsi
0x14007dda5  mov     dl, 1; NewValue
0x14007dda7  mov     esi, 2
0x14007ddac  mov     [rbp+70h+ObjectAttributes.Length], 30h ; '0'
0x14007ddb3  mov     ecx, esi; Privilege
0x14007ddb5  mov     dword ptr [rbp+70h+var_90+4], esi
0x14007ddb8  mov     word ptr [rbp+70h+var_88], 1
0x14007ddbe  mov     dword ptr [rbp+70h+var_90], 0Ch
0x14007ddc5  mov     [rbp+70h+ObjectAttributes.SecurityQualityOfService], rax
0x14007ddc9  call    cs:__imp_RtlAdjustPrivilege
0x14007ddcf  mov     r9d, eax
0x14007ddd2  test    eax, eax
0x14007ddd4  jns     short loc_14007DE09
0x14007ddd6  mov     rcx, cs:WPP_GLOBAL_Control
0x14007dddd  lea     rax, WPP_GLOBAL_Control
0x14007dde4  cmp     rcx, rax
0x14007dde7  jz      loc_14007DF9B
0x14007dded  test    [rcx+1Ch], sil
0x14007ddf1  jz      loc_14007DF9B
0x14007ddf7  cmp     [rcx+19h], sil
0x14007ddfb  jb      loc_14007DF9B
0x14007de01  lea     edx, [rsi+16h]
0x14007de04  jmp     loc_14007DBB9
0x14007de09  lea     rax, [rbp+70h+var_80]
0x14007de0d  mov     r9d, 1; TokenType
0x14007de13  mov     [rsp+170h+TokenSource], rax; TokenSource
0x14007de18  lea     r8, [rbp+70h+ObjectAttributes]; ObjectAttributes
0x14007de1c  mov     rax, [rbp+70h+var_E8]
0x14007de20  lea     rcx, [rbp+70h+TokenHandle]; TokenHandle
0x14007de24  mov     [rsp+170h+TokenDefaultDacl], r15; TokenDefaultDacl
0x14007de29  mov     edx, 0F01FFh; DesiredAccess
0x14007de2e  mov     [rsp+170h+TokenPrimaryGroup], rax; TokenPrimaryGroup
0x14007de33  mov     rax, [rbp+70h+var_E0]
0x14007de37  mov     [rsp+170h+TokenOwner], r13; TokenOwner
0x14007de3c  mov     [rsp+170h+TokenPrivileges], rax; TokenPrivileges
0x14007de41  mov     rax, [rbp+70h+var_D8]
0x14007de45  mov     [rsp+170h+TokenGroups], rbx; TokenGroups
0x14007de4a  mov     [rsp+170h+TokenUser], rax; TokenUser
0x14007de4f  lea     rax, [rbp+70h+var_60]
0x14007de53  mov     [rsp+170h+ExpirationTime], rax; ExpirationTime
0x14007de58  lea     rax, [rbp+70h+TokenInformation+8]
0x14007de5c  mov     [rsp+170h+ReturnLength], rax; AuthenticationId
0x14007de61  call    cs:__imp_NtCreateToken
0x14007de67  mov     r9d, eax
0x14007de6a  test    eax, eax
0x14007de6c  jns     short loc_14007DEB3
0x14007de6e  mov     rcx, cs:WPP_GLOBAL_Control
0x14007de75  lea     rax, WPP_GLOBAL_Control
0x14007de7c  cmp     rcx, rax
0x14007de7f  jz      loc_14007DF9B
0x14007de85  test    [rcx+1Ch], sil
0x14007de89  jz      loc_14007DF9B
0x14007de8f  cmp     [rcx+19h], sil
0x14007de93  jb      loc_14007DF9B
0x14007de99  mov     edx, 19h
0x14007de9e  mov     rcx, [rcx+10h]
0x14007dea2  lea     r8, WPP_f970564fce7b32792e727784e751b97c_Traceguids
0x14007dea9  call    WPP_SF_d
0x14007deae  jmp     loc_14007DF9B
0x14007deb3  mov     r9d, 4; TokenInformationLength
0x14007deb9  lea     rax, [rsp+170h+Size]
0x14007debe  lea     r8, [rsp+170h+var_F8]; TokenInformation
0x14007dec3  mov     [rsp+170h+ReturnLength], rax; ReturnLength
0x14007dec8  mov     rcx, rdi; TokenHandle
0x14007decb  lea     edx, [r9+8]; TokenInformationClass
0x14007decf  call    cs:__imp_NtQueryInformationToken
0x14007ded5  mov     r9d, eax
0x14007ded8  test    eax, eax
0x14007deda  jns     short loc_14007DF0E
0x14007dedc  mov     rcx, cs:WPP_GLOBAL_Control
0x14007dee3  lea     rax, WPP_GLOBAL_Control
  ... truncated ...
```
