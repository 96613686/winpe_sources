# WsRestoreGlobalMapping

- ea: `0x18002be90`
- end: `0x18002c2bd`
- name: `WsRestoreGlobalMapping`
- size: `1069`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000e57c`

## callees

- `0x180002640`
- `0x180004d30`
- `0x180008b50`
- `0x180009110`
- `0x18000a830`
- `0x18000b900`
- `0x18000c100`
- `0x18000c24c`
- `0x18000d3dc`
- `0x18001fbd0`
- `0x18002be90`
- `0x180031774`

## import_xrefs

- `ntdll!DbgPrint` at `0x18002befc`
- `ntdll!DbgPrint` at `0x18002bf97`
- `ntdll!DbgPrint` at `0x18002befc`
- `ntdll!DbgPrint` at `0x18002bf97`
- `ntdll!RtlAcquireResourceExclusive` at `0x18002c0b4`
- `ntdll!RtlAcquireResourceExclusive` at `0x18002c0b4`
- `ntdll!NtClose` at `0x18002c2aa`
- `ntdll!NtClose` at `0x18002c2aa`
- `ntdll!RtlReleaseResource` at `0x18002c13d`
- `ntdll!RtlReleaseResource` at `0x18002c13d`
- `ntdll!RtlInitUnicodeString` at `0x18002c16c`
- `ntdll!RtlInitUnicodeString` at `0x18002c188`
- `ntdll!RtlInitUnicodeString` at `0x18002c16c`
- `ntdll!RtlInitUnicodeString` at `0x18002c188`
- `ntdll!RtlValidRelativeSecurityDescriptor` at `0x18002c00f`
- `ntdll!RtlValidRelativeSecurityDescriptor` at `0x18002c00f`

## pseudocode

```c
__int64 __fastcall WsRestoreGlobalMapping(__int64 a1)
{
  int v1; // r15d
  unsigned int v3; // r14d
  _WORD *v4; // rax
  __int64 v5; // rdx
  int v6; // r13d
  __int64 v7; // rcx
  _WORD *v9; // rcx
  const WCHAR *v10; // rdi
  ULONG v11; // edx
  char *hMem; // rsi
  int v13; // r9d
  unsigned int v14; // r12d
  unsigned int v15; // ebx
  __int64 v16; // rcx
  DWORD v17; // eax
  struct _LUID SourceLuid; // [rsp+90h] [rbp-80h] BYREF
  struct _UNICODE_STRING v19; // [rsp+98h] [rbp-78h] BYREF
  HANDLE Handle; // [rsp+A8h] [rbp-68h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+B0h] [rbp-60h] BYREF
  __int64 v22; // [rsp+C0h] [rbp-50h] BYREF
  __int64 v23; // [rsp+C8h] [rbp-48h] BYREF
  __int64 v24; // [rsp+D0h] [rbp-40h] BYREF
  __int64 v25; // [rsp+D8h] [rbp-38h] BYREF
  struct _LUID v26; // [rsp+E0h] [rbp-30h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+E8h] [rbp-28h] BYREF
  int v28; // [rsp+100h] [rbp-10h] BYREF
  __int64 *v29; // [rsp+108h] [rbp-8h]
  __int64 v30; // [rsp+110h] [rbp+0h]
  int v31; // [rsp+118h] [rbp+8h]
  __int64 *v32; // [rsp+120h] [rbp+10h]
  __int64 v33; // [rsp+128h] [rbp+18h]
  int v34; // [rsp+130h] [rbp+20h]
  __int64 *v35; // [rsp+138h] [rbp+28h]
  __int64 v36; // [rsp+140h] [rbp+30h]
  int v37; // [rsp+148h] [rbp+38h]
  __int64 *v38; // [rsp+150h] [rbp+40h]
  __int64 v39; // [rsp+158h] [rbp+48h]
  _BYTE v40[176]; // [rsp+160h] [rbp+50h] BYREF
  WCHAR v41[264]; // [rsp+210h] [rbp+100h] BYREF
  WCHAR SourceString[344]; // [rsp+420h] [rbp+310h] BYREF

  v1 = *(_DWORD *)(a1 + 20);
  SourceLuid = 0;
  v26 = 0;
  *(_DWORD *)&v19.Length = 0;
  v3 = 0;
  *(_DWORD *)&DestinationString.Length = 0;
  Handle = 0;
  Destination = 0;
  v25 = 0;
  v24 = 0;
  v23 = 0;
  v22 = 0;
  DbgPrint("WsRestoreGlobalMapping\n");
  v4 = *(_WORD **)(a1 + 8);
  if ( !v4 || !*v4 )
    return 87;
  v5 = *(unsigned int *)(a1 + 32);
  v6 = *(_DWORD *)(a1 + 16);
  v29 = &v25;
  v36 = 16;
  v32 = &v24;
  v35 = &v23;
  v39 = 16;
  v7 = *(_QWORD *)(a1 + 24);
  v38 = &v22;
  v28 = 1130784068;
  v30 = 124;
  v31 = 1348563540;
  v33 = 24;
  v34 = 1349349187;
  v37 = 1315925058;
  if ( !(unsigned __int8)LmPopulateAndValidateUseOptionInfo(v7, v5, &v28) )
  {
    DbgPrint("Invalid value specified for a UseOption\n");
    return 87;
  }
  v9 = *(_WORD **)a1;
  v10 = 0;
  if ( *(_QWORD *)a1 && *v9 )
  {
    if ( (unsigned int)WsUseCheckLocal((__int64)v9, (__int64)v40, &DestinationString) )
      return 87;
    v3 = *(_DWORD *)&DestinationString.Length;
    v10 = (const WCHAR *)v40;
  }
  v11 = *(_DWORD *)(a1 + 48);
  hMem = 0;
  if ( v11 )
  {
    hMem = *(char **)(a1 + 40);
    if ( hMem )
    {
      if ( !RtlValidRelativeSecurityDescriptor(*(PSECURITY_DESCRIPTOR *)(a1 + 40), v11, 0) )
        return 87;
    }
  }
  if ( (unsigned int)WsUseCheckRemote(*(_QWORD *)(a1 + 8), (__int64)v41, &v19) )
    return 87;
  v14 = *(_DWORD *)&v19.Length;
  SourceLuid = (struct _LUID)-1LL;
  LOBYTE(v13) = 1;
  v26 = (struct _LUID)-1LL;
  v15 = WsCreateTreeConnectName((int)v41, *(int *)&v19.Length, (int)v10, v13, &Destination);
  if ( !v15 )
  {
    if ( !v1 || (unsigned int)ComputeTargetNameFromUncName(v41, SourceString) )
    {
      if ( v10 )
      {
        *(_DWORD *)&v19.Length = 0;
        if ( !RtlAcquireResourceExclusive(&Resource, 1u) )
          return 2140;
        if ( !(unsigned int)WsGetUserEntry((__int64)&Use, &SourceLuid, (unsigned int *)&v19.Length, 0, 0) )
        {
          v16 = *(_QWORD *)(Use + 24LL * *(unsigned int *)&v19.Length);
          if ( v16 )
          {
            *(_QWORD *)&v19.Length = 0;
            *(_QWORD *)&DestinationString.Length = 0;
            WsFindLocal(v16, v10, &v19, &DestinationString);
            if ( *(_QWORD *)&v19.Length )
              v15 = 85;
          }
        }
        RtlReleaseResource(&Resource);
        if ( v15 )
          return v15;
      }
      DestinationString = 0;
      v19 = 0;
      RtlInitUnicodeString(&DestinationString, v10);
      if ( v1 )
        RtlInitUnicodeString(&v19, SourceString);
      v17 = WsOpenCreateConnectionSpecifyImpersonation(
              &Destination,
              (const void **)&DestinationString,
              0,
              0,
              (const void **)((unsigned __int64)&v19 & -(__int64)(v1 != 0)),
              hMem,
              v25,
              v24,
              v23,
              v22,
              v6 | 1,
              3u,
              0,
              1,
              0,
              1,
              &Handle);
      v15 = v17;
      if ( v17 )
      {
        if ( v17 == 2250 )
          return 55;
      }
      else
      {
        v15 = WsAddUse(
                &SourceLuid,
                &v26,
                Handle,
                (__int64)v10,
                v3,
                v41,
                v14,
                (__int64)&Destination,
                v6,
                (_OWORD *)v24,
                (_QWORD *)v23,
                (_QWORD *)v22);
        if ( v15 && (unsigned int)WsDeleteConnectionEx(&SourceLuid, Handle, 2u, 1) )
          NtClose(Handle);
      }
      return v15;
    }
    return 87;
  }
  return v15;
}

```

## disassembly

```asm
0x18002be90  push    rbp
0x18002be92  push    rbx
0x18002be93  push    rsi
0x18002be94  push    rdi
0x18002be95  push    r12
0x18002be97  push    r13
0x18002be99  push    r14
0x18002be9b  push    r15
0x18002be9d  lea     rbp, [rsp-5D8h]
0x18002bea5  sub     rsp, 6E8h
0x18002beac  mov     rax, cs:__security_cookie
0x18002beb3  xor     rax, rsp
0x18002beb6  mov     [rbp+610h+var_50], rax
0x18002bebd  mov     r15d, [rcx+14h]
0x18002bec1  xor     r12d, r12d
0x18002bec4  mov     rbx, rcx
0x18002bec7  mov     qword ptr [rbp+610h+SourceLuid.LowPart], r12
0x18002becb  xorps   xmm0, xmm0
0x18002bece  mov     qword ptr [rbp+610h+var_640.LowPart], r12
0x18002bed2  lea     rcx, aWsrestoregloba; "WsRestoreGlobalMapping\n"
0x18002bed9  mov     dword ptr [rbp+610h+var_688.Length], r12d
0x18002bedd  mov     r14d, r12d
0x18002bee0  mov     dword ptr [rbp+610h+DestinationString.Length], r12d
0x18002bee4  mov     [rbp+610h+Handle], r12
0x18002bee8  movups  xmmword ptr [rbp+610h+var_638.Length], xmm0
0x18002beec  mov     [rbp+610h+var_648], r12
0x18002bef0  mov     [rbp+610h+var_650], r12
0x18002bef4  mov     [rbp+610h+var_658], r12
0x18002bef8  mov     [rbp+610h+var_660], r12
0x18002befc  call    cs:__imp_DbgPrint
0x18002bf03  nop     dword ptr [rax+rax+00h]
0x18002bf08  mov     rax, [rbx+8]
0x18002bf0c  test    rax, rax
0x18002bf0f  jz      loc_18002BFA3
0x18002bf15  cmp     [rax], r12w
0x18002bf19  jz      loc_18002BFA3
0x18002bf1f  mov     edx, [rbx+20h]
0x18002bf22  lea     ecx, [r12+10h]
0x18002bf27  mov     r13d, [rbx+10h]
0x18002bf2b  lea     rax, [rbp+610h+var_648]
0x18002bf2f  mov     [rbp+610h+var_618], rax
0x18002bf33  lea     r8, [rbp+610h+var_620]
0x18002bf37  lea     rax, [rbp+610h+var_650]
0x18002bf3b  mov     [rbp+610h+var_5E0], rcx
0x18002bf3f  mov     [rbp+610h+var_600], rax
0x18002bf43  lea     rax, [rbp+610h+var_658]
0x18002bf47  mov     [rbp+610h+var_5E8], rax
0x18002bf4b  lea     rax, [rbp+610h+var_660]
0x18002bf4f  mov     [rbp+610h+var_5C8], rcx
0x18002bf53  mov     rcx, [rbx+18h]
0x18002bf57  mov     [rbp+610h+var_5D0], rax
0x18002bf5b  mov     [rbp+610h+var_620], 43666544h
0x18002bf62  mov     [rbp+610h+var_610], 7Ch ; '|'
0x18002bf6a  mov     [rbp+610h+var_608], 50617254h
0x18002bf71  mov     [rbp+610h+var_5F8], 18h
0x18002bf79  mov     [rbp+610h+var_5F0], 506D6F43h
0x18002bf80  mov     [rbp+610h+var_5D8], 4E6F6C42h
0x18002bf87  call    LmPopulateAndValidateUseOptionInfo
0x18002bf8c  test    al, al
0x18002bf8e  jnz     short loc_18002BFCC
0x18002bf90  lea     rcx, aInvalidValueSp; "Invalid value specified for a UseOption"...
0x18002bf97  call    cs:__imp_DbgPrint
0x18002bf9e  nop     dword ptr [rax+rax+00h]
0x18002bfa3  mov     eax, 57h ; 'W'
0x18002bfa8  mov     rcx, [rbp+610h+var_50]
0x18002bfaf  xor     rcx, rsp; StackCookie
0x18002bfb2  call    __security_check_cookie
0x18002bfb7  add     rsp, 6E8h
0x18002bfbe  pop     r15
0x18002bfc0  pop     r14
0x18002bfc2  pop     r13
0x18002bfc4  pop     r12
0x18002bfc6  pop     rdi
0x18002bfc7  pop     rsi
0x18002bfc8  pop     rbx
0x18002bfc9  pop     rbp
0x18002bfca  retn
0x18002bfcc  mov     rcx, [rbx]
0x18002bfcf  mov     rdi, r12
0x18002bfd2  test    rcx, rcx
0x18002bfd5  jz      short loc_18002BFF6
0x18002bfd7  cmp     [rcx], r12w
0x18002bfdb  jz      short loc_18002BFF6
0x18002bfdd  lea     r8, [rbp+610h+DestinationString]
0x18002bfe1  lea     rdx, [rbp+610h+var_5C0]
0x18002bfe5  call    WsUseCheckLocal
0x18002bfea  test    eax, eax
0x18002bfec  jnz     short loc_18002BFA3
0x18002bfee  mov     r14d, dword ptr [rbp+610h+DestinationString.Length]
0x18002bff2  lea     rdi, [rbp+610h+var_5C0]
0x18002bff6  mov     edx, [rbx+30h]; SecurityDescriptorLength
0x18002bff9  mov     rsi, r12
0x18002bffc  test    edx, edx
0x18002bffe  jz      short loc_18002C01F
0x18002c000  mov     rsi, [rbx+28h]
0x18002c004  test    rsi, rsi
0x18002c007  jz      short loc_18002C01F
0x18002c009  xor     r8d, r8d; RequiredInformation
0x18002c00c  mov     rcx, rsi; SecurityDescriptorInput
0x18002c00f  call    cs:__imp_RtlValidRelativeSecurityDescriptor
0x18002c016  nop     dword ptr [rax+rax+00h]
0x18002c01b  test    al, al
0x18002c01d  jz      short loc_18002BFA3
0x18002c01f  mov     rcx, [rbx+8]
0x18002c023  lea     r8, [rbp+610h+var_688]
0x18002c027  lea     rdx, [rbp+610h+var_510]
0x18002c02e  call    WsUseCheckRemote
0x18002c033  test    eax, eax
0x18002c035  jnz     loc_18002BFA3
0x18002c03b  mov     r12d, dword ptr [rbp+610h+var_688.Length]
0x18002c03f  lea     rcx, [rbp+610h+var_510]; int
0x18002c046  mov     qword ptr [rbp+610h+SourceLuid.LowPart], 0FFFFFFFFFFFFFFFFh
0x18002c04e  mov     r9b, 1; int
0x18002c051  mov     rax, qword ptr [rbp+610h+SourceLuid.LowPart]
0x18002c055  mov     r8, rdi; int
0x18002c058  mov     qword ptr [rbp+610h+var_640.LowPart], rax
0x18002c05c  mov     edx, r12d; int
0x18002c05f  lea     rax, [rbp+610h+var_638]
0x18002c063  mov     [rsp+720h+Destination], rax; Destination
0x18002c068  call    WsCreateTreeConnectName
0x18002c06d  mov     ebx, eax
0x18002c06f  test    eax, eax
0x18002c071  jnz     loc_18002C2B6
0x18002c077  test    r15d, r15d
0x18002c07a  jz      short loc_18002C09B
0x18002c07c  lea     rdx, [rbp+610h+SourceString]
0x18002c083  lea     rcx, [rbp+610h+var_510]
0x18002c08a  call    ComputeTargetNameFromUncName
0x18002c08f  test    eax, eax
0x18002c091  jnz     short loc_18002C09B
0x18002c093  lea     ebx, [rax+57h]
0x18002c096  jmp     loc_18002C2B6
0x18002c09b  test    rdi, rdi
0x18002c09e  jz      loc_18002C151
0x18002c0a4  mov     dl, 1; Wait
0x18002c0a6  mov     dword ptr [rbp+610h+var_688.Length], 0
0x18002c0ad  lea     rcx, Resource; Resource
0x18002c0b4  call    cs:__imp_RtlAcquireResourceExclusive
0x18002c0bb  nop     dword ptr [rax+rax+00h]
0x18002c0c0  test    al, al
0x18002c0c2  jnz     short loc_18002C0CE
0x18002c0c4  mov     ebx, 85Ch
0x18002c0c9  jmp     loc_18002C2B6
0x18002c0ce  xor     r9d, r9d
0x18002c0d1  mov     [rsp+720h+Destination], 0
0x18002c0da  lea     r8, [rbp+610h+var_688]
0x18002c0de  lea     rdx, [rbp+610h+SourceLuid]
0x18002c0e2  lea     rcx, Use
0x18002c0e9  call    WsGetUserEntry
0x18002c0ee  test    eax, eax
0x18002c0f0  jnz     short loc_18002C136
0x18002c0f2  mov     eax, dword ptr [rbp+610h+var_688.Length]
0x18002c0f5  lea     rcx, [rax+rax*2]
0x18002c0f9  mov     rax, cs:Use
0x18002c100  mov     rcx, [rax+rcx*8]
0x18002c104  test    rcx, rcx
0x18002c107  jz      short loc_18002C136
0x18002c109  lea     r9, [rbp+610h+DestinationString]
0x18002c10d  mov     qword ptr [rbp+610h+var_688.Length], 0
0x18002c115  lea     r8, [rbp+610h+var_688]
0x18002c119  mov     qword ptr [rbp+610h+DestinationString.Length], 0
0x18002c121  mov     rdx, rdi
0x18002c124  call    WsFindLocal
0x18002c129  cmp     qword ptr [rbp+610h+var_688.Length], 0
0x18002c12e  mov     eax, 55h ; 'U'
0x18002c133  cmovnz  ebx, eax
0x18002c136  lea     rcx, Resource; Resource
0x18002c13d  call    cs:__imp_RtlReleaseResource
0x18002c144  nop     dword ptr [rax+rax+00h]
0x18002c149  test    ebx, ebx
0x18002c14b  jnz     loc_18002C2B6
0x18002c151  xorps   xmm0, xmm0
0x18002c154  lea     rcx, [rbp+610h+DestinationString]; DestinationString
0x18002c158  xorps   xmm1, xmm1
0x18002c15b  mov     ebx, r13d
0x18002c15e  mov     rdx, rdi; SourceString
0x18002c161  or      ebx, 1
0x18002c164  movups  xmmword ptr [rbp+610h+DestinationString.Length], xmm0
0x18002c168  movups  xmmword ptr [rbp+610h+var_688.Length], xmm1
0x18002c16c  call    cs:__imp_RtlInitUnicodeString
0x18002c173  nop     dword ptr [rax+rax+00h]
0x18002c178  test    r15d, r15d
0x18002c17b  jz      short loc_18002C194
0x18002c17d  lea     rdx, [rbp+610h+SourceString]; SourceString
0x18002c184  lea     rcx, [rbp+610h+var_688]; DestinationString
0x18002c188  call    cs:__imp_RtlInitUnicodeString
0x18002c18f  nop     dword ptr [rax+rax+00h]
0x18002c194  neg     r15d
0x18002c197  lea     rax, [rbp+610h+var_688]
0x18002c19b  lea     rdx, [rbp+610h+DestinationString]; int
0x18002c19f  sbb     rcx, rcx
0x18002c1a2  xor     r15d, r15d
0x18002c1a5  mov     [rsp+720h+var_698], r15
0x18002c1ad  and     rcx, rax
0x18002c1b0  lea     rax, [rbp+610h+Handle]
0x18002c1b4  xor     r9d, r9d; int
0x18002c1b7  mov     [rsp+720h+FileHandle], rax; FileHandle
0x18002c1bf  xor     r8d, r8d; int
0x18002c1c2  mov     rax, [rbp+610h+var_660]
0x18002c1c6  mov     [rsp+720h+var_6A8], 1; char
0x18002c1cb  mov     [rsp+720h+var_6B0], r15b; char
0x18002c1d0  mov     [rsp+720h+var_6B8], 1; char
0x18002c1d5  mov     [rsp+720h+var_6C0], r15d; int
0x18002c1da  mov     [rsp+720h+var_6C8], 3; ULONG
0x18002c1e2  mov     [rsp+720h+var_6D0], ebx; ULONG
0x18002c1e6  mov     [rsp+720h+var_6D8], rax; __int64
0x18002c1eb  mov     rax, [rbp+610h+var_658]
0x18002c1ef  mov     [rsp+720h+var_6E0], rax; __int64
0x18002c1f4  mov     rax, [rbp+610h+var_650]
0x18002c1f8  mov     [rsp+720h+var_6E8], rax; __int64
0x18002c1fd  mov     rax, [rbp+610h+var_648]
0x18002c201  mov     [rsp+720h+var_6F0], rax; __int64
0x18002c206  mov     [rsp+720h+hMem], rsi; hMem
0x18002c20b  mov     [rsp+720h+Destination], rcx; __int64
0x18002c210  lea     rcx, [rbp+610h+var_638]; int
0x18002c214  call    WsOpenCreateConnectionSpecifyImpersonation
0x18002c219  mov     ebx, eax
0x18002c21b  test    eax, eax
0x18002c21d  jz      short loc_18002C233
0x18002c21f  cmp     eax, 8CAh
0x18002c224  jnz     loc_18002C2B6
0x18002c22a  lea     ebx, [r15+37h]
0x18002c22e  jmp     loc_18002C2B6
0x18002c233  mov     rax, [rbp+610h+var_660]
0x18002c237  lea     rdx, [rbp+610h+var_640]; PLUID
0x18002c23b  mov     r8, [rbp+610h+Handle]
0x18002c23f  lea     rcx, [rbp+610h+SourceLuid]; SourceLuid
0x18002c243  mov     qword ptr [rsp+720h+var_6C8], rax; __int64
0x18002c248  mov     r9, rdi
0x18002c24b  mov     rax, [rbp+610h+var_658]
0x18002c24f  mov     qword ptr [rsp+720h+var_6D0], rax; __int64
0x18002c254  mov     rax, [rbp+610h+var_650]
0x18002c258  mov     [rsp+720h+var_6D8], rax; __int64
0x18002c25d  lea     rax, [rbp+610h+var_638]
0x18002c261  mov     dword ptr [rsp+720h+var_6E0], r13d; int
0x18002c266  mov     [rsp+720h+var_6E8], rax; __int64
0x18002c26b  lea     rax, [rbp+610h+var_510]
0x18002c272  mov     dword ptr [rsp+720h+var_6F0], r12d; int
0x18002c277  mov     [rsp+720h+hMem], rax; __int64
0x18002c27c  mov     dword ptr [rsp+720h+Destination], r14d; int
0x18002c281  call    WsAddUse
0x18002c286  mov     ebx, eax
0x18002c288  test    eax, eax
0x18002c28a  jz      short loc_18002C2B6
0x18002c28c  mov     rdx, [rbp+610h+Handle]; Handle
0x18002c290  lea     rcx, [rbp+610h+SourceLuid]; SourceLuid
0x18002c294  mov     r9b, 1
0x18002c297  mov     r8d, 2
0x18002c29d  call    WsDeleteConnectionEx
0x18002c2a2  test    eax, eax
0x18002c2a4  jz      short loc_18002C2B6
0x18002c2a6  mov     rcx, [rbp+610h+Handle]; Handle
0x18002c2aa  call    cs:__imp_NtClose
0x18002c2b1  nop     dword ptr [rax+rax+00h]
0x18002c2b6  mov     eax, ebx
0x18002c2b8  jmp     loc_18002BFA8
```
