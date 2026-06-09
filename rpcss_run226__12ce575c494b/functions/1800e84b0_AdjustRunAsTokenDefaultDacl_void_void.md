# AdjustRunAsTokenDefaultDacl(void *,void *)

- ea: `0x1800e84b0`
- end: `0x1800e8720`
- name: `?AdjustRunAsTokenDefaultDacl@@YAJPEAX0@Z`
- size: `624`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, PSID pSid)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800501cc`

## callees

- `0x180034540`
- `0x18007e3d4`
- `0x1800e84b0`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x1800e84cf`
- `ntdll!RtlLengthSid` at `0x1800e84de`
- `ntdll!RtlLengthSid` at `0x1800e84e9`
- `ntdll!RtlLengthSid` at `0x1800e84cf`
- `ntdll!RtlLengthSid` at `0x1800e84de`
- `ntdll!RtlLengthSid` at `0x1800e84e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e8525`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e858b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e85ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e864c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e86ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e8525`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e858b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e85ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e864c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e86ae`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x1800e86a4`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x1800e86a4`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1800e8581`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1800e85e5`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1800e8642`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1800e8581`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1800e85e5`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1800e8642`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800e851b`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800e851b`
- `KERNELBASE!LocalAlloc` at `0x1800e84f8`
- `KERNELBASE!LocalAlloc` at `0x1800e84f8`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1800e870f`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1800e870f`

## string_xrefs

- `0x1800e8700`: `onecore\com\combase\rpcss\olescm\security.cxx`
- `0x1800e86f9`: `AdjustRunAsTokenDefaultDacl`

## pseudocode

```c
__int64 __fastcall AdjustRunAsTokenDefaultDacl(HANDLE TokenHandle, PSID pSid)
{
  ULONG v4; // ebx
  ULONG v5; // ebx
  DWORD v6; // ebx
  struct _ACL *v7; // rax
  struct _ACL *v8; // rdi
  unsigned int v9; // ebx
  signed int v10; // eax
  int v11; // r8d
  signed int v12; // eax
  signed int v13; // eax
  signed int v14; // eax
  signed int LastError; // eax
  struct _ACL *TokenInformation; // [rsp+70h] [rbp+18h] BYREF

  TokenInformation = 0;
  v4 = RtlLengthSid(gSidOwnerRights);
  v5 = RtlLengthSid(gSidLocalSystem) + v4;
  v6 = RtlLengthSid(pSid) + 44 + v5;
  v7 = (struct _ACL *)LocalAlloc(0, v6);
  v8 = v7;
  if ( v7 )
  {
    if ( InitializeAcl(v7, v6, 2u) )
    {
      if ( AddAccessAllowedAce(v8, 2u, 0x10000000u, gSidLocalSystem) )
      {
        if ( AddAccessAllowedAce(v8, 2u, 0x20000u, gSidOwnerRights) )
        {
          if ( AddAccessAllowedAce(v8, 2u, 0x10000000u, pSid) )
          {
            v9 = 0;
            TokenInformation = v8;
            if ( SetTokenInformation(TokenHandle, TokenDefaultDacl, &TokenInformation, 8u) )
              goto LABEL_39;
            LastError = GetLastError();
            v9 = LastError;
            if ( LastError > 0 )
              v9 = (unsigned __int16)LastError | 0x80070000;
            if ( !dword_18014E4B8 && (!gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled(0)) )
              goto LABEL_39;
            v11 = 748;
          }
          else
          {
            v14 = GetLastError();
            v9 = v14;
            if ( v14 > 0 )
              v9 = (unsigned __int16)v14 | 0x80070000;
            if ( !dword_18014E4B8 && (!gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled(0)) )
              goto LABEL_39;
            v11 = 736;
          }
        }
        else
        {
          v13 = GetLastError();
          v9 = v13;
          if ( v13 > 0 )
            v9 = (unsigned __int16)v13 | 0x80070000;
          if ( !dword_18014E4B8 && (!gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled(0)) )
            goto LABEL_39;
          v11 = 727;
        }
      }
      else
      {
        v12 = GetLastError();
        v9 = v12;
        if ( v12 > 0 )
          v9 = (unsigned __int16)v12 | 0x80070000;
        if ( !dword_18014E4B8 && (!gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled(0)) )
          goto LABEL_39;
        v11 = 717;
      }
    }
    else
    {
      v10 = GetLastError();
      v9 = v10;
      if ( v10 > 0 )
        v9 = (unsigned __int16)v10 | 0x80070000;
      if ( !dword_18014E4B8 && (!gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled(0)) )
        goto LABEL_39;
      v11 = 707;
    }
    ComTraceMessageT<long>(
      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\security.cxx",
      (unsigned int)"AdjustRunAsTokenDefaultDacl",
      v11,
      0,
      (__int64)L"%!HRESULT!",
      v9);
LABEL_39:
    LocalFree(v8);
    return v9;
  }
  return (unsigned int)-2147024882;
}

```

## disassembly

```asm
0x1800e84b0  push    rbx
0x1800e84b2  push    rbp
0x1800e84b3  push    rsi
0x1800e84b4  push    rdi
0x1800e84b5  sub     rsp, 38h
0x1800e84b9  mov     rbp, rcx
0x1800e84bc  mov     [rsp+58h+TokenInformation], 0
0x1800e84c5  mov     rcx, cs:?gSidOwnerRights@@3PEAXEA; Sid
0x1800e84cc  mov     rsi, rdx
0x1800e84cf  call    cs:__imp_RtlLengthSid
0x1800e84d5  mov     rcx, cs:?gSidLocalSystem@@3PEAXEA; Sid
0x1800e84dc  mov     ebx, eax
0x1800e84de  call    cs:__imp_RtlLengthSid
0x1800e84e4  mov     rcx, rsi; Sid
0x1800e84e7  add     ebx, eax
0x1800e84e9  call    cs:__imp_RtlLengthSid
0x1800e84ef  add     eax, 2Ch ; ','
0x1800e84f2  xor     ecx, ecx; uFlags
0x1800e84f4  add     ebx, eax
0x1800e84f6  mov     edx, ebx; uBytes
0x1800e84f8  call    cs:__imp_LocalAlloc
0x1800e84fe  mov     rdi, rax
0x1800e8501  test    rax, rax
0x1800e8504  jnz     short loc_1800E8510
0x1800e8506  mov     ebx, 8007000Eh
0x1800e850b  jmp     loc_1800E8715
0x1800e8510  mov     r8d, 2; dwAclRevision
0x1800e8516  mov     edx, ebx; nAclLength
0x1800e8518  mov     rcx, rdi; pAcl
0x1800e851b  call    cs:__imp_InitializeAcl
0x1800e8521  test    eax, eax
0x1800e8523  jnz     short loc_1800E856A
0x1800e8525  call    cs:__imp_GetLastError
0x1800e852b  mov     ebx, eax
0x1800e852d  test    eax, eax
0x1800e852f  jle     short loc_1800E853A
0x1800e8531  movzx   ebx, ax
0x1800e8534  or      ebx, 80070000h
0x1800e853a  mov     eax, cs:dword_18014E4B8
0x1800e8540  test    eax, eax
0x1800e8542  jnz     short loc_1800E855F
0x1800e8544  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x1800e854a  jz      loc_1800E870C
0x1800e8550  xor     ecx, ecx
0x1800e8552  call    IsWppLevelEnabled
0x1800e8557  test    al, al
0x1800e8559  jz      loc_1800E870C
0x1800e855f  mov     r8d, 2C3h
0x1800e8565  jmp     loc_1800E86E6
0x1800e856a  mov     r9, cs:?gSidLocalSystem@@3PEAXEA; pSid
0x1800e8571  mov     ebx, 10000000h
0x1800e8576  mov     r8d, ebx; AccessMask
0x1800e8579  mov     edx, 2; dwAceRevision
0x1800e857e  mov     rcx, rdi; pAcl
0x1800e8581  call    cs:__imp_AddAccessAllowedAce
0x1800e8587  test    eax, eax
0x1800e8589  jnz     short loc_1800E85D0
0x1800e858b  call    cs:__imp_GetLastError
0x1800e8591  mov     ebx, eax
0x1800e8593  test    eax, eax
0x1800e8595  jle     short loc_1800E85A0
0x1800e8597  movzx   ebx, ax
0x1800e859a  or      ebx, 80070000h
0x1800e85a0  mov     eax, cs:dword_18014E4B8
0x1800e85a6  test    eax, eax
0x1800e85a8  jnz     short loc_1800E85C5
0x1800e85aa  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x1800e85b0  jz      loc_1800E870C
0x1800e85b6  xor     ecx, ecx
0x1800e85b8  call    IsWppLevelEnabled
0x1800e85bd  test    al, al
0x1800e85bf  jz      loc_1800E870C
0x1800e85c5  mov     r8d, 2CDh
0x1800e85cb  jmp     loc_1800E86E6
0x1800e85d0  mov     r9, cs:?gSidOwnerRights@@3PEAXEA; pSid
0x1800e85d7  mov     edx, 2; dwAceRevision
0x1800e85dc  mov     r8d, 20000h; AccessMask
0x1800e85e2  mov     rcx, rdi; pAcl
0x1800e85e5  call    cs:__imp_AddAccessAllowedAce
0x1800e85eb  test    eax, eax
0x1800e85ed  jnz     short loc_1800E8634
0x1800e85ef  call    cs:__imp_GetLastError
0x1800e85f5  mov     ebx, eax
0x1800e85f7  test    eax, eax
0x1800e85f9  jle     short loc_1800E8604
0x1800e85fb  movzx   ebx, ax
0x1800e85fe  or      ebx, 80070000h
0x1800e8604  mov     eax, cs:dword_18014E4B8
0x1800e860a  test    eax, eax
0x1800e860c  jnz     short loc_1800E8629
0x1800e860e  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x1800e8614  jz      loc_1800E870C
0x1800e861a  xor     ecx, ecx
0x1800e861c  call    IsWppLevelEnabled
0x1800e8621  test    al, al
0x1800e8623  jz      loc_1800E870C
0x1800e8629  mov     r8d, 2D7h
0x1800e862f  jmp     loc_1800E86E6
0x1800e8634  mov     r9, rsi; pSid
0x1800e8637  mov     r8d, ebx; AccessMask
0x1800e863a  mov     edx, 2; dwAceRevision
0x1800e863f  mov     rcx, rdi; pAcl
0x1800e8642  call    cs:__imp_AddAccessAllowedAce
0x1800e8648  test    eax, eax
0x1800e864a  jnz     short loc_1800E868E
0x1800e864c  call    cs:__imp_GetLastError
0x1800e8652  mov     ebx, eax
0x1800e8654  test    eax, eax
0x1800e8656  jle     short loc_1800E8661
0x1800e8658  movzx   ebx, ax
0x1800e865b  or      ebx, 80070000h
0x1800e8661  mov     eax, cs:dword_18014E4B8
0x1800e8667  test    eax, eax
0x1800e8669  jnz     short loc_1800E8686
0x1800e866b  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x1800e8671  jz      loc_1800E870C
0x1800e8677  xor     ecx, ecx
0x1800e8679  call    IsWppLevelEnabled
0x1800e867e  test    al, al
0x1800e8680  jz      loc_1800E870C
0x1800e8686  mov     r8d, 2E0h
0x1800e868c  jmp     short loc_1800E86E6
0x1800e868e  xor     ebx, ebx
0x1800e8690  mov     [rsp+58h+TokenInformation], rdi
0x1800e8695  lea     r8, [rsp+58h+TokenInformation]; TokenInformation
0x1800e869a  mov     rcx, rbp; TokenHandle
0x1800e869d  lea     r9d, [rbx+8]; TokenInformationLength
0x1800e86a1  lea     edx, [rbx+6]; TokenInformationClass
0x1800e86a4  call    cs:__imp_SetTokenInformation
0x1800e86aa  test    eax, eax
0x1800e86ac  jnz     short loc_1800E870C
0x1800e86ae  call    cs:__imp_GetLastError
0x1800e86b4  mov     ebx, eax
0x1800e86b6  test    eax, eax
0x1800e86b8  jle     short loc_1800E86C3
0x1800e86ba  movzx   ebx, ax
0x1800e86bd  or      ebx, 80070000h
0x1800e86c3  mov     eax, cs:dword_18014E4B8
0x1800e86c9  test    eax, eax
0x1800e86cb  jnz     short loc_1800E86E0
0x1800e86cd  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x1800e86d3  jz      short loc_1800E870C
0x1800e86d5  xor     ecx, ecx
0x1800e86d7  call    IsWppLevelEnabled
0x1800e86dc  test    al, al
0x1800e86de  jz      short loc_1800E870C
0x1800e86e0  mov     r8d, 2ECh
0x1800e86e6  lea     rax, aHresult; "%!HRESULT!"
0x1800e86ed  mov     [rsp+58h+var_30], ebx
0x1800e86f1  xor     r9d, r9d
0x1800e86f4  mov     [rsp+58h+var_38], rax
0x1800e86f9  lea     rdx, aAdjustrunastok; "AdjustRunAsTokenDefaultDacl"
0x1800e8700  lea     rcx, aOnecoreComComb_86; "onecore\\com\\combase\\rpcss\\olescm\\s"...
0x1800e8707  call    ??$ComTraceMessageT@J@@YAXPEBD0HW4TraceLevel@@PEBGJ@Z; ComTraceMessageT<long>(char const *,char const *,int,TraceLevel,ushort const *,long)
0x1800e870c  mov     rcx, rdi; hMem
0x1800e870f  call    cs:__imp_LocalFree
0x1800e8715  mov     eax, ebx
0x1800e8717  add     rsp, 38h
0x1800e871b  pop     rdi
0x1800e871c  pop     rsi
0x1800e871d  pop     rbp
0x1800e871e  pop     rbx
0x1800e871f  retn
```
