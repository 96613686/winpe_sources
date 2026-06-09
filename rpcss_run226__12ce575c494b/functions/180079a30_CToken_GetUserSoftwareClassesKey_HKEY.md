# CToken::GetUserSoftwareClassesKey(HKEY__ * *)

- ea: `0x180079a30`
- end: `0x180079da9`
- name: `?GetUserSoftwareClassesKey@CToken@@UEAAJPEAPEAUHKEY__@@@Z`
- size: `889`
- prototype: `__int64 __fastcall(CToken *__hidden this, HKEY *)`
- caller_count: `0`
- callee_count: `13`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x18000bbe8`
- `0x180025250`
- `0x180025310`
- `0x180034540`
- `0x1800531a0`
- `0x18005e8d8`
- `0x1800621b8`
- `0x180065ed0`
- `0x180069b54`
- `0x18006a36c`
- `0x180079a30`
- `0x18007e3d4`
- `0x1800a1e98`

## import_xrefs

- `ntdll!NtOpenKey` at `0x180079ccb`
- `ntdll!NtOpenKey` at `0x180079ccb`
- `ntdll!RtlNtStatusToDosError` at `0x180079d28`
- `ntdll!RtlNtStatusToDosError` at `0x180079d28`
- `ntdll!RtlInitUnicodeString` at `0x180079c78`
- `ntdll!RtlInitUnicodeString` at `0x180079c78`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079b63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079b63`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180079d54`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180079d54`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180079c3c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180079c3c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180079aad`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180079aad`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180079a94`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180079a94`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180079b59`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180079b59`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180079d65`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180079d65`

## string_xrefs

- `0x180079b2d`: `onecore\com\combase\rpcss\objex\token.cxx`
- `0x180079ba9`: `onecore\com\combase\rpcss\objex\token.cxx`
- `0x180079d1a`: `onecore\com\combase\rpcss\objex\token.cxx`
- `0x180079b26`: `CToken::GetUserSoftwareClassesKey`
- `0x180079ba2`: `CToken::GetUserSoftwareClassesKey`
- `0x180079d13`: `CToken::GetUserSoftwareClassesKey`
- `0x180079b89`: `ConvertSidToStringSid failed: %!WINERROR!`
- `0x180079cfa`: `NtOpenKey failed, %!STATUS!`
- `0x180079c58`: `\REGISTRY\USER\%s_Classes`

## pseudocode

```c
__int64 __fastcall CToken::GetUserSoftwareClassesKey(CToken *this, HKEY *a2)
{
  int v4; // ecx
  signed int LastError; // ebx
  void *v6; // rcx
  bool v7; // sf
  unsigned __int64 v8; // rdx
  int v9; // ecx
  unsigned int v10; // r9d
  unsigned int v11; // eax
  unsigned __int64 v12; // rbx
  SIZE_T v13; // rax
  unsigned __int16 *v14; // rax
  WCHAR *v15; // r14
  NTSTATUS v16; // eax
  NTSTATUS v17; // esi
  signed int v18; // eax
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-50h] BYREF
  struct _RTL_CRITICAL_SECTION *v21; // [rsp+40h] [rbp-40h] BYREF
  int v22; // [rsp+48h] [rbp-38h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF
  int v24; // [rsp+C8h] [rbp+48h] BYREF
  LPWSTR StringSid; // [rsp+D0h] [rbp+50h] BYREF

  *a2 = 0;
  if ( !(unsigned int)CToken::IsLocalSystem(this)
    && !(unsigned int)CToken::IsLocalService(this)
    && !(unsigned int)CToken::IsNetworkService(this)
    && !EqualSid((char *)this + 156, gSidAnonymous) )
  {
    v21 = &gcsTokenLock;
    EnterCriticalSection(&gcsTokenLock);
    v4 = *((_DWORD *)this + 4);
    LastError = 0;
    v22 = 1;
    *((_DWORD *)this + 4) = v4 + 1;
    if ( v4 )
      goto LABEL_45;
    v6 = (void *)*((_QWORD *)this + 9);
    v24 = 0;
    LastError = IsUserHiveOK(v6);
    if ( LastError < 0 )
    {
      if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled((unsigned int)dword_18014E4B8) )
        ComTraceMessageT<long>(
          (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\token.cxx",
          (unsigned int)"CToken::GetUserSoftwareClassesKey",
          1132,
          0,
          (__int64)L"IsUserHiveOK failed: %!HRESULT!",
          LastError);
      goto LABEL_44;
    }
    if ( !v24 )
    {
      LastError = -2147024894;
LABEL_44:
      --*((_DWORD *)this + 4);
LABEL_46:
      CMutexLock::~CMutexLock((CMutexLock *)&v21);
      return (unsigned int)LastError;
    }
    StringSid = 0;
    if ( ConvertSidToStringSidW((char *)this + 156, &StringSid) )
    {
      v8 = -1;
      LOWORD(v24) = 0;
      do
        ++v8;
      while ( StringSid[v8] );
      if ( v8 > 0xFFFF )
      {
        LastError = -2147024362;
      }
      else
      {
        LastError = UShortAdd(0x1Au, v8, (unsigned __int16 *)&v24);
        if ( LastError >= 0 )
        {
          v11 = 2 * (unsigned __int16)v24;
          LastError = v10 < v11 ? 0x80070216 : 0;
          if ( v11 <= v10 )
          {
            v12 = (unsigned __int16)v24;
            v13 = (unsigned __int16)v24 * (unsigned __int64)(unsigned int)(v9 - 24);
            if ( !is_mul_ok((unsigned __int16)v24, (unsigned int)(v9 - 24)) )
              v13 = -1;
            v14 = (unsigned __int16 *)HeapAlloc(g_hHeap, 0, v13);
            v15 = v14;
            if ( v14 )
            {
              StringCchPrintfW(v14, v12, L"\\REGISTRY\\USER\\%s_Classes", StringSid);
              DestinationString = 0;
              RtlInitUnicodeString(&DestinationString, v15);
              *(_QWORD *)&ObjectAttributes.Length = 48;
              ObjectAttributes.ObjectName = &DestinationString;
              *(_QWORD *)&ObjectAttributes.Attributes = 64;
              ObjectAttributes.RootDirectory = 0;
              v24 = 0;
              *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
              LastError = CToken::Impersonate(this, 0, &v24);
              if ( LastError >= 0 )
              {
                v16 = NtOpenKey((PHANDLE)this + 4, 0x20019u, &ObjectAttributes);
                v17 = v16;
                if ( v16 < 0 )
                {
                  if ( v16 != -1073741772
                    && (dword_18014E4B8
                     || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled((unsigned int)dword_18014E4B8)) )
                  {
                    ComTraceMessageT<long>(
                      (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\token.cxx",
                      (unsigned int)"CToken::GetUserSoftwareClassesKey",
                      1211,
                      0,
                      (__int64)L"NtOpenKey failed, %!STATUS!",
                      v17);
                  }
                  v18 = RtlNtStatusToDosError(v17);
                  LastError = v18;
                  if ( v18 > 0 )
                    LastError = (unsigned __int16)v18 | 0x80070000;
                }
                CToken::Revert(this, v24);
              }
              HeapFree(g_hHeap, 0, v15);
            }
            else
            {
              LastError = -2147024882;
            }
          }
        }
      }
      LocalFree(StringSid);
    }
    else
    {
      LastError = GetLastError();
      if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
        ComTraceMessageT<int>(
          (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\token.cxx",
          (unsigned int)"CToken::GetUserSoftwareClassesKey",
          1151,
          0,
          (__int64)L"ConvertSidToStringSid failed: %!WINERROR!",
          LastError);
      v7 = LastError < 0;
      if ( LastError <= 0 )
      {
LABEL_43:
        if ( v7 )
          goto LABEL_44;
LABEL_45:
        *a2 = (HKEY)*((_QWORD *)this + 4);
        goto LABEL_46;
      }
      LastError = (unsigned __int16)LastError | 0x80070000;
    }
    v7 = LastError < 0;
    goto LABEL_43;
  }
  return 2147942402LL;
}

```

## disassembly

```asm
0x180079a30  mov     [rsp-38h+arg_0], rbx
0x180079a35  push    rbp
0x180079a36  push    rsi
0x180079a37  push    rdi
0x180079a38  push    r12
0x180079a3a  push    r13
0x180079a3c  push    r14
0x180079a3e  push    r15
0x180079a40  mov     rbp, rsp
0x180079a43  sub     rsp, 80h
0x180079a4a  xor     r12d, r12d
0x180079a4d  mov     r15, rdx
0x180079a50  mov     [rdx], r12
0x180079a53  mov     rdi, rcx
0x180079a56  call    ?IsLocalSystem@CToken@@QEAAHXZ; CToken::IsLocalSystem(void)
0x180079a5b  test    eax, eax
0x180079a5d  jnz     loc_180079D89
0x180079a63  mov     rcx, rdi; this
0x180079a66  call    ?IsLocalService@CToken@@QEAAHXZ; CToken::IsLocalService(void)
0x180079a6b  test    eax, eax
0x180079a6d  jnz     loc_180079D89
0x180079a73  mov     rcx, rdi; this
0x180079a76  call    ?IsNetworkService@CToken@@QEAAHXZ; CToken::IsNetworkService(void)
0x180079a7b  test    eax, eax
0x180079a7d  jnz     loc_180079D89
0x180079a83  mov     rdx, cs:?gSidAnonymous@@3PEAXEA; pSid2
0x180079a8a  lea     rsi, [rdi+9Ch]
0x180079a91  mov     rcx, rsi; pSid1
0x180079a94  call    cs:__imp_EqualSid
0x180079a9a  test    eax, eax
0x180079a9c  jnz     loc_180079D89
0x180079aa2  lea     rcx, ?gcsTokenLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180079aa9  mov     [rbp+var_40], rcx
0x180079aad  call    cs:__imp_EnterCriticalSection
0x180079ab3  mov     ecx, [rdi+10h]
0x180079ab6  mov     ebx, r12d
0x180079ab9  mov     [rbp+var_38], 1
0x180079ac0  lea     eax, [rcx+1]
0x180079ac3  mov     [rdi+10h], eax
0x180079ac6  test    ecx, ecx
0x180079ac8  jnz     loc_180079D75
0x180079ace  mov     rcx, [rdi+48h]; void *
0x180079ad2  lea     rdx, [rbp+arg_8]
0x180079ad6  mov     [rbp+arg_8], r12d
0x180079ada  call    IsUserHiveOK
0x180079adf  or      r13, 0FFFFFFFFFFFFFFFFh
0x180079ae3  mov     ebx, eax
0x180079ae5  test    eax, eax
0x180079ae7  jns     short loc_180079B3E
0x180079ae9  mov     ecx, cs:dword_18014E4B8
0x180079aef  test    ecx, ecx
0x180079af1  jnz     short loc_180079B0D
0x180079af3  cmp     cs:?gfEnableTracing@@3HA, r12d; int gfEnableTracing
0x180079afa  jz      loc_180079D6F
0x180079b00  call    IsWppLevelEnabled
0x180079b05  test    al, al
0x180079b07  jz      loc_180079D6F
0x180079b0d  lea     rax, aIsuserhiveokFa; "IsUserHiveOK failed: %!HRESULT!"
0x180079b14  mov     [rsp+80h+var_58], ebx
0x180079b18  xor     r9d, r9d
0x180079b1b  mov     [rsp+80h+var_60], rax
0x180079b20  mov     r8d, 46Ch
0x180079b26  lea     rdx, aCtokenGetusers; "CToken::GetUserSoftwareClassesKey"
0x180079b2d  lea     rcx, aOnecoreComComb_100; "onecore\\com\\combase\\rpcss\\objex\\to"...
0x180079b34  call    ??$ComTraceMessageT@J@@YAXPEBD0HW4TraceLevel@@PEBGJ@Z; ComTraceMessageT<long>(char const *,char const *,int,TraceLevel,ushort const *,long)
0x180079b39  jmp     loc_180079D6F
0x180079b3e  cmp     [rbp+arg_8], r12d
0x180079b42  jnz     short loc_180079B4E
0x180079b44  mov     ebx, 80070002h
0x180079b49  jmp     loc_180079D6F
0x180079b4e  lea     rdx, [rbp+StringSid]; StringSid
0x180079b52  mov     [rbp+StringSid], r12
0x180079b56  mov     rcx, rsi; Sid
0x180079b59  call    cs:__imp_ConvertSidToStringSidW
0x180079b5f  test    eax, eax
0x180079b61  jnz     short loc_180079BCB
0x180079b63  call    cs:__imp_GetLastError
0x180079b69  mov     ebx, eax
0x180079b6b  mov     eax, cs:dword_18014E4B8
0x180079b71  test    eax, eax
0x180079b73  jnz     short loc_180079B89
0x180079b75  cmp     cs:?gfEnableTracing@@3HA, r12d; int gfEnableTracing
0x180079b7c  jz      short loc_180079BB5
0x180079b7e  xor     ecx, ecx
0x180079b80  call    IsWppLevelEnabled
0x180079b85  test    al, al
0x180079b87  jz      short loc_180079BB5
0x180079b89  lea     rax, aConvertsidtost; "ConvertSidToStringSid failed: %!WINERRO"...
0x180079b90  mov     [rsp+80h+var_58], ebx
0x180079b94  xor     r9d, r9d
0x180079b97  mov     [rsp+80h+var_60], rax
0x180079b9c  mov     r8d, 47Fh
0x180079ba2  lea     rdx, aCtokenGetusers; "CToken::GetUserSoftwareClassesKey"
0x180079ba9  lea     rcx, aOnecoreComComb_100; "onecore\\com\\combase\\rpcss\\objex\\to"...
0x180079bb0  call    ??$ComTraceMessageT@H@@YAXPEBD0HW4TraceLevel@@PEBGH@Z; ComTraceMessageT<int>(char const *,char const *,int,TraceLevel,ushort const *,int)
0x180079bb5  test    ebx, ebx
0x180079bb7  jle     loc_180079D6D
0x180079bbd  movzx   ebx, bx
0x180079bc0  or      ebx, 80070000h
0x180079bc6  jmp     loc_180079D6B
0x180079bcb  mov     rax, [rbp+StringSid]
0x180079bcf  mov     rdx, r13
0x180079bd2  mov     word ptr [rbp+arg_8], r12w
0x180079bd7  inc     rdx; unsigned __int16
0x180079bda  cmp     [rax+rdx*2], r12w
0x180079bdf  jnz     short loc_180079BD7
0x180079be1  mov     r9d, 0FFFFh
0x180079be7  cmp     rdx, r9
0x180079bea  ja      loc_180079D5C
0x180079bf0  mov     ecx, 1Ah; unsigned __int16
0x180079bf5  lea     r8, [rbp+arg_8]; unsigned __int16 *
0x180079bf9  call    ?UShortAdd@@YAJGGPEAG@Z; UShortAdd(ushort,ushort,ushort *)
0x180079bfe  mov     ebx, eax
0x180079c00  test    eax, eax
0x180079c02  js      loc_180079D61
0x180079c08  movzx   eax, word ptr [rbp+arg_8]
0x180079c0c  add     eax, eax
0x180079c0e  cmp     r9d, eax
0x180079c11  sbb     ebx, ebx
0x180079c13  and     ebx, 80070216h
0x180079c19  cmp     eax, r9d
0x180079c1c  ja      loc_180079D61
0x180079c22  movzx   ebx, word ptr [rbp+arg_8]
0x180079c26  lea     eax, [rcx-18h]
0x180079c29  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x180079c30  mul     rbx
0x180079c33  cmovb   rax, r13
0x180079c37  xor     edx, edx; dwFlags
0x180079c39  mov     r8, rax; dwBytes
0x180079c3c  call    cs:__imp_HeapAlloc
0x180079c42  mov     r14, rax
0x180079c45  test    rax, rax
0x180079c48  jnz     short loc_180079C54
0x180079c4a  mov     ebx, 8007000Eh
0x180079c4f  jmp     loc_180079D61
0x180079c54  mov     r9, [rbp+StringSid]
0x180079c58  lea     r8, aRegistryUserSC; "\\REGISTRY\\USER\\%s_Classes"
0x180079c5f  mov     rdx, rbx; unsigned __int64
0x180079c62  mov     rcx, r14; unsigned __int16 *
0x180079c65  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180079c6a  xorps   xmm0, xmm0
0x180079c6d  lea     rcx, [rbp+DestinationString]; DestinationString
0x180079c71  mov     rdx, r14; SourceString
0x180079c74  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180079c78  call    cs:__imp_RtlInitUnicodeString
0x180079c7e  lea     rax, [rbp+DestinationString]
0x180079c82  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x180079c8a  xorps   xmm0, xmm0
0x180079c8d  mov     [rbp+ObjectAttributes.ObjectName], rax
0x180079c91  lea     r8, [rbp+arg_8]; int *
0x180079c95  mov     qword ptr [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x180079c9d  xor     edx, edx; int
0x180079c9f  mov     [rbp+ObjectAttributes.RootDirectory], r12
0x180079ca3  mov     rcx, rdi; this
0x180079ca6  mov     [rbp+arg_8], r12d
0x180079caa  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180079caf  call    ?Impersonate@CToken@@UEAAJHPEAH@Z; CToken::Impersonate(int,int *)
0x180079cb4  mov     ebx, eax
0x180079cb6  test    eax, eax
0x180079cb8  js      loc_180079D48
0x180079cbe  lea     rcx, [rdi+20h]; KeyHandle
0x180079cc2  mov     edx, 20019h; DesiredAccess
0x180079cc7  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180079ccb  call    cs:__imp_NtOpenKey
0x180079cd1  mov     esi, eax
0x180079cd3  test    eax, eax
0x180079cd5  jns     short loc_180079D3D
0x180079cd7  cmp     eax, 0C0000034h
0x180079cdc  jz      short loc_180079D26
0x180079cde  mov     ecx, cs:dword_18014E4B8
0x180079ce4  test    ecx, ecx
0x180079ce6  jnz     short loc_180079CFA
0x180079ce8  cmp     cs:?gfEnableTracing@@3HA, r12d; int gfEnableTracing
0x180079cef  jz      short loc_180079D26
0x180079cf1  call    IsWppLevelEnabled
0x180079cf6  test    al, al
0x180079cf8  jz      short loc_180079D26
0x180079cfa  lea     rax, aNtopenkeyFaile; "NtOpenKey failed, %!STATUS!"
0x180079d01  mov     [rsp+80h+var_58], esi
0x180079d05  xor     r9d, r9d
0x180079d08  mov     [rsp+80h+var_60], rax
0x180079d0d  mov     r8d, 4BBh
0x180079d13  lea     rdx, aCtokenGetusers; "CToken::GetUserSoftwareClassesKey"
0x180079d1a  lea     rcx, aOnecoreComComb_100; "onecore\\com\\combase\\rpcss\\objex\\to"...
0x180079d21  call    ??$ComTraceMessageT@J@@YAXPEBD0HW4TraceLevel@@PEBGJ@Z; ComTraceMessageT<long>(char const *,char const *,int,TraceLevel,ushort const *,long)
0x180079d26  mov     ecx, esi; Status
0x180079d28  call    cs:__imp_RtlNtStatusToDosError
0x180079d2e  mov     ebx, eax
0x180079d30  test    eax, eax
0x180079d32  jle     short loc_180079D3D
0x180079d34  movzx   ebx, ax
0x180079d37  or      ebx, 80070000h
0x180079d3d  mov     edx, [rbp+arg_8]; int
0x180079d40  mov     rcx, rdi; this
0x180079d43  call    ?Revert@CToken@@UEAAJH@Z; CToken::Revert(int)
0x180079d48  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x180079d4f  mov     r8, r14; lpMem
0x180079d52  xor     edx, edx; dwFlags
0x180079d54  call    cs:__imp_HeapFree
0x180079d5a  jmp     short loc_180079D61
0x180079d5c  mov     ebx, 80070216h
0x180079d61  mov     rcx, [rbp+StringSid]; hMem
0x180079d65  call    cs:__imp_LocalFree
0x180079d6b  test    ebx, ebx
0x180079d6d  jns     short loc_180079D75
0x180079d6f  add     [rdi+10h], r13d
0x180079d73  jmp     short loc_180079D7C
0x180079d75  mov     rax, [rdi+20h]
0x180079d79  mov     [r15], rax
0x180079d7c  lea     rcx, [rbp+var_40]; this
0x180079d80  call    ??1CMutexLock@@QEAA@XZ; CMutexLock::~CMutexLock(void)
0x180079d85  mov     eax, ebx
0x180079d87  jmp     short loc_180079D8E
0x180079d89  mov     eax, 80070002h
0x180079d8e  mov     rbx, [rsp+80h+arg_0]
0x180079d96  add     rsp, 80h
0x180079d9d  pop     r15
0x180079d9f  pop     r14
0x180079da1  pop     r13
0x180079da3  pop     r12
0x180079da5  pop     rdi
0x180079da6  pop     rsi
0x180079da7  pop     rbp
0x180079da8  retn
```
