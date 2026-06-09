# AdjustRunAsTokenDefaultDacl(void *,void *)

- ea: `0x1800efb88`
- end: `0x1800efe53`
- name: `?AdjustRunAsTokenDefaultDacl@@YAJPEAX0@Z`
- size: `715`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, PSID pSid)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18004dee8`

## callees

- `0x180034260`
- `0x18008172c`
- `0x1800efb88`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x1800efba7`
- `ntdll!RtlLengthSid` at `0x1800efbbc`
- `ntdll!RtlLengthSid` at `0x1800efbcd`
- `ntdll!RtlLengthSid` at `0x1800efba7`
- `ntdll!RtlLengthSid` at `0x1800efbbc`
- `ntdll!RtlLengthSid` at `0x1800efbcd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800efc1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800efc8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800efcfd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800efd66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800efdd4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800efc1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800efc8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800efcfd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800efd66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800efdd4`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x1800efdc4`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x1800efdc4`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1800efc7d`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1800efced`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1800efd56`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1800efc7d`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1800efced`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1800efd56`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800efc0b`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800efc0b`
- `KERNELBASE!LocalAlloc` at `0x1800efbe2`
- `KERNELBASE!LocalAlloc` at `0x1800efbe2`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1800efe3b`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1800efe3b`

## string_xrefs

- `0x1800efe2c`: `onecore\com\combase\rpcss\olescm\security.cxx`
- `0x1800efe25`: `AdjustRunAsTokenDefaultDacl`

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
            if ( !dword_1801574B8 && (!gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled(0)) )
              goto LABEL_39;
            v11 = 748;
          }
          else
          {
            v14 = GetLastError();
            v9 = v14;
            if ( v14 > 0 )
              v9 = (unsigned __int16)v14 | 0x80070000;
            if ( !dword_1801574B8 && (!gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled(0)) )
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
          if ( !dword_1801574B8 && (!gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled(0)) )
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
        if ( !dword_1801574B8 && (!gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled(0)) )
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
      if ( !dword_1801574B8 && (!gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled(0)) )
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
0x1800efb88  push    rbx
0x1800efb8a  push    rbp
0x1800efb8b  push    rsi
0x1800efb8c  push    rdi
0x1800efb8d  sub     rsp, 38h
0x1800efb91  mov     rbp, rcx
0x1800efb94  mov     [rsp+58h+TokenInformation], 0
0x1800efb9d  mov     rcx, cs:?gSidOwnerRights@@3PEAXEA; Sid
0x1800efba4  mov     rsi, rdx
0x1800efba7  call    cs:__imp_RtlLengthSid
0x1800efbae  nop     dword ptr [rax+rax+00h]
0x1800efbb3  mov     rcx, cs:?gSidLocalSystem@@3PEAXEA; Sid
0x1800efbba  mov     ebx, eax
0x1800efbbc  call    cs:__imp_RtlLengthSid
0x1800efbc3  nop     dword ptr [rax+rax+00h]
0x1800efbc8  mov     rcx, rsi; Sid
0x1800efbcb  add     ebx, eax
0x1800efbcd  call    cs:__imp_RtlLengthSid
0x1800efbd4  nop     dword ptr [rax+rax+00h]
0x1800efbd9  add     eax, 2Ch ; ','
0x1800efbdc  xor     ecx, ecx; uFlags
0x1800efbde  add     ebx, eax
0x1800efbe0  mov     edx, ebx; uBytes
0x1800efbe2  call    cs:__imp_LocalAlloc
0x1800efbe9  nop     dword ptr [rax+rax+00h]
0x1800efbee  mov     rdi, rax
0x1800efbf1  test    rax, rax
0x1800efbf4  jnz     short loc_1800EFC00
0x1800efbf6  mov     ebx, 8007000Eh
0x1800efbfb  jmp     loc_1800EFE47
0x1800efc00  mov     r8d, 2; dwAclRevision
0x1800efc06  mov     edx, ebx; nAclLength
0x1800efc08  mov     rcx, rdi; pAcl
0x1800efc0b  call    cs:__imp_InitializeAcl
0x1800efc12  nop     dword ptr [rax+rax+00h]
0x1800efc17  test    eax, eax
0x1800efc19  jnz     short loc_1800EFC66
0x1800efc1b  call    cs:__imp_GetLastError
0x1800efc22  nop     dword ptr [rax+rax+00h]
0x1800efc27  mov     ebx, eax
0x1800efc29  test    eax, eax
0x1800efc2b  jle     short loc_1800EFC36
0x1800efc2d  movzx   ebx, ax
0x1800efc30  or      ebx, 80070000h
0x1800efc36  mov     eax, cs:dword_1801574B8
0x1800efc3c  test    eax, eax
0x1800efc3e  jnz     short loc_1800EFC5B
0x1800efc40  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x1800efc46  jz      loc_1800EFE38
0x1800efc4c  xor     ecx, ecx
0x1800efc4e  call    IsWppLevelEnabled
0x1800efc53  test    al, al
0x1800efc55  jz      loc_1800EFE38
0x1800efc5b  mov     r8d, 2C3h
0x1800efc61  jmp     loc_1800EFE12
0x1800efc66  mov     r9, cs:?gSidLocalSystem@@3PEAXEA; pSid
0x1800efc6d  mov     ebx, 10000000h
0x1800efc72  mov     r8d, ebx; AccessMask
0x1800efc75  mov     edx, 2; dwAceRevision
0x1800efc7a  mov     rcx, rdi; pAcl
0x1800efc7d  call    cs:__imp_AddAccessAllowedAce
0x1800efc84  nop     dword ptr [rax+rax+00h]
0x1800efc89  test    eax, eax
0x1800efc8b  jnz     short loc_1800EFCD8
0x1800efc8d  call    cs:__imp_GetLastError
0x1800efc94  nop     dword ptr [rax+rax+00h]
0x1800efc99  mov     ebx, eax
0x1800efc9b  test    eax, eax
0x1800efc9d  jle     short loc_1800EFCA8
0x1800efc9f  movzx   ebx, ax
0x1800efca2  or      ebx, 80070000h
0x1800efca8  mov     eax, cs:dword_1801574B8
0x1800efcae  test    eax, eax
0x1800efcb0  jnz     short loc_1800EFCCD
0x1800efcb2  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x1800efcb8  jz      loc_1800EFE38
0x1800efcbe  xor     ecx, ecx
0x1800efcc0  call    IsWppLevelEnabled
0x1800efcc5  test    al, al
0x1800efcc7  jz      loc_1800EFE38
0x1800efccd  mov     r8d, 2CDh
0x1800efcd3  jmp     loc_1800EFE12
0x1800efcd8  mov     r9, cs:?gSidOwnerRights@@3PEAXEA; pSid
0x1800efcdf  mov     edx, 2; dwAceRevision
0x1800efce4  mov     r8d, 20000h; AccessMask
0x1800efcea  mov     rcx, rdi; pAcl
0x1800efced  call    cs:__imp_AddAccessAllowedAce
0x1800efcf4  nop     dword ptr [rax+rax+00h]
0x1800efcf9  test    eax, eax
0x1800efcfb  jnz     short loc_1800EFD48
0x1800efcfd  call    cs:__imp_GetLastError
0x1800efd04  nop     dword ptr [rax+rax+00h]
0x1800efd09  mov     ebx, eax
0x1800efd0b  test    eax, eax
0x1800efd0d  jle     short loc_1800EFD18
0x1800efd0f  movzx   ebx, ax
0x1800efd12  or      ebx, 80070000h
0x1800efd18  mov     eax, cs:dword_1801574B8
0x1800efd1e  test    eax, eax
0x1800efd20  jnz     short loc_1800EFD3D
0x1800efd22  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x1800efd28  jz      loc_1800EFE38
0x1800efd2e  xor     ecx, ecx
0x1800efd30  call    IsWppLevelEnabled
0x1800efd35  test    al, al
0x1800efd37  jz      loc_1800EFE38
0x1800efd3d  mov     r8d, 2D7h
0x1800efd43  jmp     loc_1800EFE12
0x1800efd48  mov     r9, rsi; pSid
0x1800efd4b  mov     r8d, ebx; AccessMask
0x1800efd4e  mov     edx, 2; dwAceRevision
0x1800efd53  mov     rcx, rdi; pAcl
0x1800efd56  call    cs:__imp_AddAccessAllowedAce
0x1800efd5d  nop     dword ptr [rax+rax+00h]
0x1800efd62  test    eax, eax
0x1800efd64  jnz     short loc_1800EFDAE
0x1800efd66  call    cs:__imp_GetLastError
0x1800efd6d  nop     dword ptr [rax+rax+00h]
0x1800efd72  mov     ebx, eax
0x1800efd74  test    eax, eax
0x1800efd76  jle     short loc_1800EFD81
0x1800efd78  movzx   ebx, ax
0x1800efd7b  or      ebx, 80070000h
0x1800efd81  mov     eax, cs:dword_1801574B8
0x1800efd87  test    eax, eax
0x1800efd89  jnz     short loc_1800EFDA6
0x1800efd8b  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x1800efd91  jz      loc_1800EFE38
0x1800efd97  xor     ecx, ecx
0x1800efd99  call    IsWppLevelEnabled
0x1800efd9e  test    al, al
0x1800efda0  jz      loc_1800EFE38
0x1800efda6  mov     r8d, 2E0h
0x1800efdac  jmp     short loc_1800EFE12
0x1800efdae  xor     ebx, ebx
0x1800efdb0  mov     [rsp+58h+TokenInformation], rdi
0x1800efdb5  lea     r8, [rsp+58h+TokenInformation]; TokenInformation
0x1800efdba  mov     rcx, rbp; TokenHandle
0x1800efdbd  lea     r9d, [rbx+8]; TokenInformationLength
0x1800efdc1  lea     edx, [rbx+6]; TokenInformationClass
0x1800efdc4  call    cs:__imp_SetTokenInformation
0x1800efdcb  nop     dword ptr [rax+rax+00h]
0x1800efdd0  test    eax, eax
0x1800efdd2  jnz     short loc_1800EFE38
0x1800efdd4  call    cs:__imp_GetLastError
0x1800efddb  nop     dword ptr [rax+rax+00h]
0x1800efde0  mov     ebx, eax
0x1800efde2  test    eax, eax
0x1800efde4  jle     short loc_1800EFDEF
0x1800efde6  movzx   ebx, ax
0x1800efde9  or      ebx, 80070000h
0x1800efdef  mov     eax, cs:dword_1801574B8
0x1800efdf5  test    eax, eax
0x1800efdf7  jnz     short loc_1800EFE0C
0x1800efdf9  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x1800efdff  jz      short loc_1800EFE38
0x1800efe01  xor     ecx, ecx
0x1800efe03  call    IsWppLevelEnabled
0x1800efe08  test    al, al
0x1800efe0a  jz      short loc_1800EFE38
0x1800efe0c  mov     r8d, 2ECh
0x1800efe12  lea     rax, aHresult; "%!HRESULT!"
0x1800efe19  mov     [rsp+58h+var_30], ebx
0x1800efe1d  xor     r9d, r9d
0x1800efe20  mov     [rsp+58h+var_38], rax
0x1800efe25  lea     rdx, aAdjustrunastok; "AdjustRunAsTokenDefaultDacl"
0x1800efe2c  lea     rcx, aOnecoreComComb_86; "onecore\\com\\combase\\rpcss\\olescm\\s"...
0x1800efe33  call    ??$ComTraceMessageT@J@@YAXPEBD0HW4TraceLevel@@PEBGJ@Z; ComTraceMessageT<long>(char const *,char const *,int,TraceLevel,ushort const *,long)
0x1800efe38  mov     rcx, rdi; hMem
0x1800efe3b  call    cs:__imp_LocalFree
0x1800efe42  nop     dword ptr [rax+rax+00h]
0x1800efe47  mov     eax, ebx
0x1800efe49  add     rsp, 38h
0x1800efe4d  pop     rdi
0x1800efe4e  pop     rsi
0x1800efe4f  pop     rbp
0x1800efe50  pop     rbx
0x1800efe51  retn
```
