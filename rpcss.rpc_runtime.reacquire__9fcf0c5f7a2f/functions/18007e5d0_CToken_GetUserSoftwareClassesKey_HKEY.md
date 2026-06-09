# CToken::GetUserSoftwareClassesKey(HKEY__ * *)

- ea: `0x18007e5d0`
- end: `0x18007e986`
- name: `?GetUserSoftwareClassesKey@CToken@@UEAAJPEAPEAUHKEY__@@@Z`
- size: `950`
- prototype: `__int64 __fastcall(CToken *__hidden this, HKEY *)`
- caller_count: `0`
- callee_count: `13`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x18001037c`
- `0x18002f5a0`
- `0x18002f670`
- `0x180034260`
- `0x180058880`
- `0x180063244`
- `0x180067748`
- `0x18006aa84`
- `0x18006e930`
- `0x18006f614`
- `0x18007e5d0`
- `0x18008172c`
- `0x1800a7388`

## import_xrefs

- `ntdll!NtOpenKey` at `0x18007e88f`
- `ntdll!NtOpenKey` at `0x18007e88f`
- `ntdll!RtlNtStatusToDosError` at `0x18007e8f2`
- `ntdll!RtlNtStatusToDosError` at `0x18007e8f2`
- `ntdll!RtlInitUnicodeString` at `0x18007e836`
- `ntdll!RtlInitUnicodeString` at `0x18007e836`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007e715`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007e715`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007e924`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007e924`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007e7f4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007e7f4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007e653`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007e653`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18007e634`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18007e634`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18007e705`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18007e705`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18007e93b`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18007e93b`

## string_xrefs

- `0x18007e6d9`: `onecore\com\combase\rpcss\objex\token.cxx`
- `0x18007e761`: `onecore\com\combase\rpcss\objex\token.cxx`
- `0x18007e8e4`: `onecore\com\combase\rpcss\objex\token.cxx`
- `0x18007e6d2`: `CToken::GetUserSoftwareClassesKey`
- `0x18007e75a`: `CToken::GetUserSoftwareClassesKey`
- `0x18007e8dd`: `CToken::GetUserSoftwareClassesKey`
- `0x18007e741`: `ConvertSidToStringSid failed: %!WINERROR!`
- `0x18007e8c4`: `NtOpenKey failed, %!STATUS!`
- `0x18007e816`: `\REGISTRY\USER\%s_Classes`

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
      if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled((unsigned int)dword_1801574B8) )
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
                    && (dword_1801574B8
                     || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled((unsigned int)dword_1801574B8)) )
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
      if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
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
0x18007e5d0  mov     [rsp-38h+arg_0], rbx
0x18007e5d5  push    rbp
0x18007e5d6  push    rsi
0x18007e5d7  push    rdi
0x18007e5d8  push    r12
0x18007e5da  push    r13
0x18007e5dc  push    r14
0x18007e5de  push    r15
0x18007e5e0  mov     rbp, rsp
0x18007e5e3  sub     rsp, 80h
0x18007e5ea  xor     r12d, r12d
0x18007e5ed  mov     r15, rdx
0x18007e5f0  mov     [rdx], r12
0x18007e5f3  mov     rdi, rcx
0x18007e5f6  call    ?IsLocalSystem@CToken@@QEAAHXZ; CToken::IsLocalSystem(void)
0x18007e5fb  test    eax, eax
0x18007e5fd  jnz     loc_18007E965
0x18007e603  mov     rcx, rdi; this
0x18007e606  call    ?IsLocalService@CToken@@QEAAHXZ; CToken::IsLocalService(void)
0x18007e60b  test    eax, eax
0x18007e60d  jnz     loc_18007E965
0x18007e613  mov     rcx, rdi; this
0x18007e616  call    ?IsNetworkService@CToken@@QEAAHXZ; CToken::IsNetworkService(void)
0x18007e61b  test    eax, eax
0x18007e61d  jnz     loc_18007E965
0x18007e623  mov     rdx, cs:?gSidAnonymous@@3PEAXEA; pSid2
0x18007e62a  lea     rsi, [rdi+9Ch]
0x18007e631  mov     rcx, rsi; pSid1
0x18007e634  call    cs:__imp_EqualSid
0x18007e63b  nop     dword ptr [rax+rax+00h]
0x18007e640  test    eax, eax
0x18007e642  jnz     loc_18007E965
0x18007e648  lea     rcx, ?gcsTokenLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18007e64f  mov     [rbp+var_40], rcx
0x18007e653  call    cs:__imp_EnterCriticalSection
0x18007e65a  nop     dword ptr [rax+rax+00h]
0x18007e65f  mov     ecx, [rdi+10h]
0x18007e662  mov     ebx, r12d
0x18007e665  mov     [rbp+var_38], 1
0x18007e66c  lea     eax, [rcx+1]
0x18007e66f  mov     [rdi+10h], eax
0x18007e672  test    ecx, ecx
0x18007e674  jnz     loc_18007E951
0x18007e67a  mov     rcx, [rdi+48h]; void *
0x18007e67e  lea     rdx, [rbp+arg_8]
0x18007e682  mov     [rbp+arg_8], r12d
0x18007e686  call    IsUserHiveOK
0x18007e68b  or      r13, 0FFFFFFFFFFFFFFFFh
0x18007e68f  mov     ebx, eax
0x18007e691  test    eax, eax
0x18007e693  jns     short loc_18007E6EA
0x18007e695  mov     ecx, cs:dword_1801574B8
0x18007e69b  test    ecx, ecx
0x18007e69d  jnz     short loc_18007E6B9
0x18007e69f  cmp     cs:?gfEnableTracing@@3HA, r12d; int gfEnableTracing
0x18007e6a6  jz      loc_18007E94B
0x18007e6ac  call    IsWppLevelEnabled
0x18007e6b1  test    al, al
0x18007e6b3  jz      loc_18007E94B
0x18007e6b9  lea     rax, aIsuserhiveokFa; "IsUserHiveOK failed: %!HRESULT!"
0x18007e6c0  mov     [rsp+80h+var_58], ebx
0x18007e6c4  xor     r9d, r9d
0x18007e6c7  mov     [rsp+80h+var_60], rax
0x18007e6cc  mov     r8d, 46Ch
0x18007e6d2  lea     rdx, aCtokenGetusers; "CToken::GetUserSoftwareClassesKey"
0x18007e6d9  lea     rcx, aOnecoreComComb_100; "onecore\\com\\combase\\rpcss\\objex\\to"...
0x18007e6e0  call    ??$ComTraceMessageT@J@@YAXPEBD0HW4TraceLevel@@PEBGJ@Z; ComTraceMessageT<long>(char const *,char const *,int,TraceLevel,ushort const *,long)
0x18007e6e5  jmp     loc_18007E94B
0x18007e6ea  cmp     [rbp+arg_8], r12d
0x18007e6ee  jnz     short loc_18007E6FA
0x18007e6f0  mov     ebx, 80070002h
0x18007e6f5  jmp     loc_18007E94B
0x18007e6fa  lea     rdx, [rbp+StringSid]; StringSid
0x18007e6fe  mov     [rbp+StringSid], r12
0x18007e702  mov     rcx, rsi; Sid
0x18007e705  call    cs:__imp_ConvertSidToStringSidW
0x18007e70c  nop     dword ptr [rax+rax+00h]
0x18007e711  test    eax, eax
0x18007e713  jnz     short loc_18007E783
0x18007e715  call    cs:__imp_GetLastError
0x18007e71c  nop     dword ptr [rax+rax+00h]
0x18007e721  mov     ebx, eax
0x18007e723  mov     eax, cs:dword_1801574B8
0x18007e729  test    eax, eax
0x18007e72b  jnz     short loc_18007E741
0x18007e72d  cmp     cs:?gfEnableTracing@@3HA, r12d; int gfEnableTracing
0x18007e734  jz      short loc_18007E76D
0x18007e736  xor     ecx, ecx
0x18007e738  call    IsWppLevelEnabled
0x18007e73d  test    al, al
0x18007e73f  jz      short loc_18007E76D
0x18007e741  lea     rax, aConvertsidtost; "ConvertSidToStringSid failed: %!WINERRO"...
0x18007e748  mov     [rsp+80h+var_58], ebx
0x18007e74c  xor     r9d, r9d
0x18007e74f  mov     [rsp+80h+var_60], rax
0x18007e754  mov     r8d, 47Fh
0x18007e75a  lea     rdx, aCtokenGetusers; "CToken::GetUserSoftwareClassesKey"
0x18007e761  lea     rcx, aOnecoreComComb_100; "onecore\\com\\combase\\rpcss\\objex\\to"...
0x18007e768  call    ??$ComTraceMessageT@H@@YAXPEBD0HW4TraceLevel@@PEBGH@Z; ComTraceMessageT<int>(char const *,char const *,int,TraceLevel,ushort const *,int)
0x18007e76d  test    ebx, ebx
0x18007e76f  jle     loc_18007E949
0x18007e775  movzx   ebx, bx
0x18007e778  or      ebx, 80070000h
0x18007e77e  jmp     loc_18007E947
0x18007e783  mov     rax, [rbp+StringSid]
0x18007e787  mov     rdx, r13
0x18007e78a  mov     word ptr [rbp+arg_8], r12w
0x18007e78f  inc     rdx; unsigned __int16
0x18007e792  cmp     [rax+rdx*2], r12w
0x18007e797  jnz     short loc_18007E78F
0x18007e799  mov     r9d, 0FFFFh
0x18007e79f  cmp     rdx, r9
0x18007e7a2  ja      loc_18007E932
0x18007e7a8  mov     ecx, 1Ah; unsigned __int16
0x18007e7ad  lea     r8, [rbp+arg_8]; unsigned __int16 *
0x18007e7b1  call    ?UShortAdd@@YAJGGPEAG@Z; UShortAdd(ushort,ushort,ushort *)
0x18007e7b6  mov     ebx, eax
0x18007e7b8  test    eax, eax
0x18007e7ba  js      loc_18007E937
0x18007e7c0  movzx   eax, word ptr [rbp+arg_8]
0x18007e7c4  add     eax, eax
0x18007e7c6  cmp     r9d, eax
0x18007e7c9  sbb     ebx, ebx
0x18007e7cb  and     ebx, 80070216h
0x18007e7d1  cmp     eax, r9d
0x18007e7d4  ja      loc_18007E937
0x18007e7da  movzx   ebx, word ptr [rbp+arg_8]
0x18007e7de  lea     eax, [rcx-18h]
0x18007e7e1  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x18007e7e8  mul     rbx
0x18007e7eb  cmovb   rax, r13
0x18007e7ef  xor     edx, edx; dwFlags
0x18007e7f1  mov     r8, rax; dwBytes
0x18007e7f4  call    cs:__imp_HeapAlloc
0x18007e7fb  nop     dword ptr [rax+rax+00h]
0x18007e800  mov     r14, rax
0x18007e803  test    rax, rax
0x18007e806  jnz     short loc_18007E812
0x18007e808  mov     ebx, 8007000Eh
0x18007e80d  jmp     loc_18007E937
0x18007e812  mov     r9, [rbp+StringSid]
0x18007e816  lea     r8, aRegistryUserSC; "\\REGISTRY\\USER\\%s_Classes"
0x18007e81d  mov     rdx, rbx; unsigned __int64
0x18007e820  mov     rcx, r14; unsigned __int16 *
0x18007e823  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18007e828  xorps   xmm0, xmm0
0x18007e82b  lea     rcx, [rbp+DestinationString]; DestinationString
0x18007e82f  mov     rdx, r14; SourceString
0x18007e832  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18007e836  call    cs:__imp_RtlInitUnicodeString
0x18007e83d  nop     dword ptr [rax+rax+00h]
0x18007e842  lea     rax, [rbp+DestinationString]
0x18007e846  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x18007e84e  xorps   xmm0, xmm0
0x18007e851  mov     [rbp+ObjectAttributes.ObjectName], rax
0x18007e855  lea     r8, [rbp+arg_8]; int *
0x18007e859  mov     qword ptr [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x18007e861  xor     edx, edx; int
0x18007e863  mov     [rbp+ObjectAttributes.RootDirectory], r12
0x18007e867  mov     rcx, rdi; this
0x18007e86a  mov     [rbp+arg_8], r12d
0x18007e86e  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18007e873  call    ?Impersonate@CToken@@UEAAJHPEAH@Z; CToken::Impersonate(int,int *)
0x18007e878  mov     ebx, eax
0x18007e87a  test    eax, eax
0x18007e87c  js      loc_18007E918
0x18007e882  lea     rcx, [rdi+20h]; KeyHandle
0x18007e886  mov     edx, 20019h; DesiredAccess
0x18007e88b  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18007e88f  call    cs:__imp_NtOpenKey
0x18007e896  nop     dword ptr [rax+rax+00h]
0x18007e89b  mov     esi, eax
0x18007e89d  test    eax, eax
0x18007e89f  jns     short loc_18007E90D
0x18007e8a1  cmp     eax, 0C0000034h
0x18007e8a6  jz      short loc_18007E8F0
0x18007e8a8  mov     ecx, cs:dword_1801574B8
0x18007e8ae  test    ecx, ecx
0x18007e8b0  jnz     short loc_18007E8C4
0x18007e8b2  cmp     cs:?gfEnableTracing@@3HA, r12d; int gfEnableTracing
0x18007e8b9  jz      short loc_18007E8F0
0x18007e8bb  call    IsWppLevelEnabled
0x18007e8c0  test    al, al
0x18007e8c2  jz      short loc_18007E8F0
0x18007e8c4  lea     rax, aNtopenkeyFaile; "NtOpenKey failed, %!STATUS!"
0x18007e8cb  mov     [rsp+80h+var_58], esi
0x18007e8cf  xor     r9d, r9d
0x18007e8d2  mov     [rsp+80h+var_60], rax
0x18007e8d7  mov     r8d, 4BBh
0x18007e8dd  lea     rdx, aCtokenGetusers; "CToken::GetUserSoftwareClassesKey"
0x18007e8e4  lea     rcx, aOnecoreComComb_100; "onecore\\com\\combase\\rpcss\\objex\\to"...
0x18007e8eb  call    ??$ComTraceMessageT@J@@YAXPEBD0HW4TraceLevel@@PEBGJ@Z; ComTraceMessageT<long>(char const *,char const *,int,TraceLevel,ushort const *,long)
0x18007e8f0  mov     ecx, esi; Status
0x18007e8f2  call    cs:__imp_RtlNtStatusToDosError
0x18007e8f9  nop     dword ptr [rax+rax+00h]
0x18007e8fe  mov     ebx, eax
0x18007e900  test    eax, eax
0x18007e902  jle     short loc_18007E90D
0x18007e904  movzx   ebx, ax
0x18007e907  or      ebx, 80070000h
0x18007e90d  mov     edx, [rbp+arg_8]; int
0x18007e910  mov     rcx, rdi; this
0x18007e913  call    ?Revert@CToken@@UEAAJH@Z; CToken::Revert(int)
0x18007e918  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x18007e91f  mov     r8, r14; lpMem
0x18007e922  xor     edx, edx; dwFlags
0x18007e924  call    cs:__imp_HeapFree
0x18007e92b  nop     dword ptr [rax+rax+00h]
0x18007e930  jmp     short loc_18007E937
0x18007e932  mov     ebx, 80070216h
0x18007e937  mov     rcx, [rbp+StringSid]; hMem
0x18007e93b  call    cs:__imp_LocalFree
0x18007e942  nop     dword ptr [rax+rax+00h]
0x18007e947  test    ebx, ebx
0x18007e949  jns     short loc_18007E951
0x18007e94b  add     [rdi+10h], r13d
0x18007e94f  jmp     short loc_18007E958
0x18007e951  mov     rax, [rdi+20h]
0x18007e955  mov     [r15], rax
0x18007e958  lea     rcx, [rbp+var_40]; this
0x18007e95c  call    ??1CMutexLock@@QEAA@XZ; CMutexLock::~CMutexLock(void)
0x18007e961  mov     eax, ebx
0x18007e963  jmp     short loc_18007E96A
0x18007e965  mov     eax, 80070002h
0x18007e96a  mov     rbx, [rsp+80h+arg_0]
0x18007e972  add     rsp, 80h
0x18007e979  pop     r15
0x18007e97b  pop     r14
0x18007e97d  pop     r13
0x18007e97f  pop     r12
0x18007e981  pop     rdi
0x18007e982  pop     rsi
0x18007e983  pop     rbp
0x18007e984  retn
```
