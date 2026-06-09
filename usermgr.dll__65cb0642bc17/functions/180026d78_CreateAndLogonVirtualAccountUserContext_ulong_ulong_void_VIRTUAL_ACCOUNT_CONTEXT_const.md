# CreateAndLogonVirtualAccountUserContext(ulong,ulong,void *,_VIRTUAL_ACCOUNT_CONTEXT const * *)

- ea: `0x180026d78`
- end: `0x18002717a`
- name: `?CreateAndLogonVirtualAccountUserContext@@YAJKKPEAXPEAPEBU_VIRTUAL_ACCOUNT_CONTEXT@@@Z`
- size: `1026`
- prototype: `int(unsigned int, unsigned int, void *, const struct _VIRTUAL_ACCOUNT_CONTEXT **)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800269c4`

## callees

- `0x180026d78`
- `0x180039c78`
- `0x1800d5cfc`
- `0x1800d5da4`
- `0x1800d60ec`
- `0x1800de450`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x18002712c`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x18002712c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180026e27`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180027080`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800270c3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180026e27`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180027080`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800270c3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180026ee8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180026f3d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180026ee8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180026f3d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180026e13`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180026eda`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180026f2f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002706e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800270b1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180026e13`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180026eda`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180026f2f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002706e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800270b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027136`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027136`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026f24`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026f24`
- `ntdll!RtlCopySid` at `0x1800270a3`
- `ntdll!RtlCopySid` at `0x1800270a3`
- `ntdll!RtlFreeSid` at `0x180026ef7`
- `ntdll!RtlFreeSid` at `0x180026f06`
- `ntdll!RtlFreeSid` at `0x180026f15`
- `ntdll!RtlFreeSid` at `0x180026ef7`
- `ntdll!RtlFreeSid` at `0x180026f06`
- `ntdll!RtlFreeSid` at `0x180026f15`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180026ec3`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180026fa5`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180026fef`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180026ec3`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180026fa5`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180026fef`
- `ntdll!RtlInitUnicodeString` at `0x180026e71`
- `ntdll!RtlInitUnicodeString` at `0x180026e80`
- `ntdll!RtlInitUnicodeString` at `0x180026e8d`
- `ntdll!RtlInitUnicodeString` at `0x180026e71`
- `ntdll!RtlInitUnicodeString` at `0x180026e80`
- `ntdll!RtlInitUnicodeString` at `0x180026e8d`

## pseudocode

```c
__int64 __fastcall CreateAndLogonVirtualAccountUserContext(
        __int64 a1,
        ULONG a2,
        void *a3,
        const struct _VIRTUAL_ACCOUNT_CONTEXT **a4)
{
  __int64 v4; // r14
  unsigned int v6; // esi
  signed int v7; // ebx
  const struct _VIRTUAL_ACCOUNT_CONTEXT *v8; // rdi
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v10; // rax
  WCHAR *v11; // r12
  __int64 v12; // r15
  NTSTATUS v13; // eax
  HANDLE v14; // rax
  PSID v15; // rcx
  HANDLE v16; // rax
  void *v18; // rbx
  HANDLE v19; // rax
  void *v20; // rax
  HANDLE v21; // rax
  const struct _VIRTUAL_ACCOUNT_CONTEXT *v22; // rax
  int v23; // eax
  signed int LastError; // eax
  const struct _VIRTUAL_ACCOUNT_CONTEXT **v25; // rax
  int v26; // [rsp+60h] [rbp-59h] BYREF
  ULONG TokenInformation; // [rsp+68h] [rbp-51h] BYREF
  PSID v28; // [rsp+70h] [rbp-49h] BYREF
  PSID Sid; // [rsp+78h] [rbp-41h] BYREF
  PSID v30; // [rsp+80h] [rbp-39h] BYREF
  HANDLE TokenHandle; // [rsp+88h] [rbp-31h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+90h] [rbp-29h] BYREF
  const struct _VIRTUAL_ACCOUNT_CONTEXT **v33; // [rsp+A0h] [rbp-19h]
  struct _UNICODE_STRING v34; // [rsp+A8h] [rbp-11h] BYREF
  struct _UNICODE_STRING v35; // [rsp+B8h] [rbp-1h] BYREF
  _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+C8h] [rbp+Fh] BYREF

  v33 = a4;
  TokenInformation = a2;
  v4 = -1;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  TokenHandle = (HANDLE)-1LL;
  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  v26 = 0;
  DestinationString = 0;
  Sid = 0;
  v6 = 0;
  v34 = 0;
  v28 = 0;
  v35 = 0;
  v30 = 0;
  while ( *((_DWORD *)&g_virtualAccountDomainMap + 8 * v6 + 6) != 256 )
  {
    if ( ++v6 )
    {
      if ( v6 == 1 )
        return (unsigned int)-2147024809;
      break;
    }
  }
  v8 = 0;
  ProcessHeap = GetProcessHeap();
  v10 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 8u, 0x404u);
  v11 = v10;
  if ( v10 )
  {
    v12 = 32LL * v6;
    v7 = StringCchPrintfW(
           v10,
           0x202u,
           *(const unsigned __int16 **)((char *)&g_virtualAccountDomainMap + v12 + 16),
           TokenInformation);
    if ( v7 >= 0 )
    {
      RtlInitUnicodeString(&DestinationString, *(PCWSTR *)((char *)&g_virtualAccountDomainMap + v12));
      RtlInitUnicodeString(&v34, *(PCWSTR *)((char *)&g_virtualAccountDomainMap + v12 + 8));
      RtlInitUnicodeString(&v35, v11);
      v13 = RtlAllocateAndInitializeSid(&IdentifierAuthority, 1u, 0x5Du, 0, 0, 0, 0, 0, 0, 0, &Sid);
      if ( v13 >= 0 )
      {
        v13 = RtlAllocateAndInitializeSid(
                &IdentifierAuthority,
                3u,
                0x5Du,
                *(_DWORD *)((char *)&g_virtualAccountDomainMap + v12 + 24),
                0,
                0,
                0,
                0,
                0,
                0,
                &v28);
        if ( v13 >= 0 )
        {
          v13 = RtlAllocateAndInitializeSid(
                  &IdentifierAuthority,
                  4u,
                  0x5Du,
                  *(_DWORD *)((char *)&g_virtualAccountDomainMap + v12 + 24),
                  0,
                  TokenInformation,
                  0,
                  0,
                  0,
                  0,
                  &v30);
          if ( v13 >= 0 )
          {
            v7 = AddSidMappingToLsa(&DestinationString, 0, Sid, (enum _LSA_SID_NAME_MAPPING_OPERATION_ERROR *)&v26);
            if ( v7 < 0 )
              goto LABEL_11;
            if ( (unsigned int)(v26 - 2) > 1 )
            {
              v7 = AddSidMappingToLsa(&DestinationString, &v34, v28, (enum _LSA_SID_NAME_MAPPING_OPERATION_ERROR *)&v26);
              if ( v7 < 0 )
                goto LABEL_11;
            }
            v7 = AddSidMappingToLsa(&DestinationString, &v35, v30, (enum _LSA_SID_NAME_MAPPING_OPERATION_ERROR *)&v26);
            if ( v7 < 0 )
              goto LABEL_11;
            v18 = 0;
            if ( !a3 )
              goto LABEL_34;
            v19 = GetProcessHeap();
            v20 = HeapAlloc(v19, 8u, 0x44u);
            v18 = v20;
            if ( !v20 )
            {
LABEL_32:
              v7 = -2147024882;
              goto LABEL_11;
            }
            v13 = RtlCopySid(0x44u, v20, a3);
            if ( v13 >= 0 )
            {
LABEL_34:
              v21 = GetProcessHeap();
              v22 = (const struct _VIRTUAL_ACCOUNT_CONTEXT *)HeapAlloc(v21, 8u, 0x38u);
              v8 = v22;
              if ( v22 )
              {
                *(_DWORD *)v22 = v6;
                *((_DWORD *)v22 + 1) = TokenInformation;
                *((_QWORD *)v22 + 1) = v11;
                *((_QWORD *)v22 + 2) = Sid;
                *((_QWORD *)v22 + 3) = v28;
                *((_QWORD *)v22 + 4) = v30;
                *((_QWORD *)v22 + 5) = v18;
                *((_QWORD *)v22 + 6) = -1;
                v23 = LogonVirtualAccountUser(v22, &TokenHandle);
                v4 = (__int64)TokenHandle;
                v7 = v23;
                if ( v23 >= 0 )
                {
                  if ( SetTokenInformation(TokenHandle, TokenSessionId, &TokenInformation, 4u) )
                  {
                    v25 = v33;
                    v15 = 0;
                    *((_QWORD *)v8 + 6) = v4;
                    v4 = -1;
                    Sid = 0;
                    v28 = 0;
                    *v25 = v8;
                    v8 = 0;
                    v30 = 0;
                    goto LABEL_13;
                  }
                  LastError = GetLastError();
                  v7 = LastError;
                  if ( LastError > 0 )
                    v7 = (unsigned __int16)LastError | 0x80070000;
                }
                goto LABEL_11;
              }
              goto LABEL_32;
            }
          }
        }
      }
      v7 = ResultFromWin32FromStatus(v13);
    }
LABEL_11:
    v14 = GetProcessHeap();
    HeapFree(v14, 0, v11);
    goto LABEL_12;
  }
  v7 = -2147024882;
LABEL_12:
  v15 = v28;
LABEL_13:
  if ( v15 )
    RtlFreeSid(v15);
  if ( Sid )
    RtlFreeSid(Sid);
  if ( v30 )
    RtlFreeSid(v30);
  if ( v4 != -1 )
    CloseHandle((HANDLE)v4);
  if ( v8 )
  {
    v16 = GetProcessHeap();
    HeapFree(v16, 0, v8);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180026d78  mov     [rsp-8+arg_0], rbx
0x180026d7d  push    rbp
0x180026d7e  push    rsi
0x180026d7f  push    rdi
0x180026d80  push    r12
0x180026d82  push    r13
0x180026d84  push    r14
0x180026d86  push    r15
0x180026d88  lea     rbp, [rsp-27h]
0x180026d8d  sub     rsp, 0E0h
0x180026d94  mov     rax, cs:__security_cookie
0x180026d9b  xor     rax, rsp
0x180026d9e  mov     [rbp+57h+var_40], rax
0x180026da2  xor     r15d, r15d
0x180026da5  mov     [rbp+57h+var_70], r9
0x180026da9  xorps   xmm0, xmm0
0x180026dac  mov     [rbp+57h+TokenInformation], edx
0x180026daf  or      r14, 0FFFFFFFFFFFFFFFFh
0x180026db3  mov     dword ptr [rbp+57h+IdentifierAuthority.Value], r15d
0x180026db7  xorps   xmm1, xmm1
0x180026dba  mov     [rbp+57h+TokenHandle], r14
0x180026dbe  mov     r13, r8
0x180026dc1  mov     word ptr [rbp+57h+IdentifierAuthority.Value+4], 500h
0x180026dc7  mov     [rbp+57h+var_B0], r15d
0x180026dcb  lea     rbx, ?g_virtualAccountDomainMap@@3PAU_VIRTUAL_ACCOUNT_DOMAIN_MAP@@A; _VIRTUAL_ACCOUNT_DOMAIN_MAP near * g_virtualAccountDomainMap
0x180026dd2  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x180026dd6  mov     [rbp+57h+var_98], r15
0x180026dda  mov     esi, r15d
0x180026ddd  movups  xmmword ptr [rbp+57h+var_68.Length], xmm1
0x180026de1  mov     [rbp+57h+var_A0], r15
0x180026de5  movups  xmmword ptr [rbp+57h+var_58.Length], xmm0
0x180026de9  mov     [rbp+57h+var_90], r15
0x180026ded  mov     eax, esi
0x180026def  shl     rax, 5
0x180026df3  cmp     dword ptr [rax+rbx+18h], 100h
0x180026dfb  jz      short loc_180026E10
0x180026dfd  inc     esi
0x180026dff  cmp     esi, 1
0x180026e02  jb      short loc_180026DED
0x180026e04  jnz     short loc_180026E10
0x180026e06  mov     ebx, 80070057h
0x180026e0b  jmp     loc_180026F43
0x180026e10  mov     rdi, r15
0x180026e13  call    cs:__imp_GetProcessHeap
0x180026e19  mov     edx, 8; dwFlags
0x180026e1e  mov     r8d, 404h; dwBytes
0x180026e24  mov     rcx, rax; hHeap
0x180026e27  call    cs:__imp_HeapAlloc
0x180026e2d  mov     r12, rax
0x180026e30  test    rax, rax
0x180026e33  jnz     short loc_180026E3F
0x180026e35  mov     ebx, 8007000Eh
0x180026e3a  jmp     loc_180026EEE
0x180026e3f  mov     r9d, [rbp+57h+TokenInformation]
0x180026e43  mov     edx, 202h; unsigned __int64
0x180026e48  mov     r15d, esi
0x180026e4b  mov     rcx, r12; unsigned __int16 *
0x180026e4e  shl     r15, 5
0x180026e52  mov     r8, [r15+rbx+10h]; unsigned __int16 *
0x180026e57  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180026e5c  mov     ebx, eax
0x180026e5e  test    eax, eax
0x180026e60  js      short loc_180026EDA
0x180026e62  lea     rbx, ?g_virtualAccountDomainMap@@3PAU_VIRTUAL_ACCOUNT_DOMAIN_MAP@@A; _VIRTUAL_ACCOUNT_DOMAIN_MAP near * g_virtualAccountDomainMap
0x180026e69  mov     rdx, [r15+rbx]; SourceString
0x180026e6d  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180026e71  call    cs:__imp_RtlInitUnicodeString
0x180026e77  mov     rdx, [r15+rbx+8]; SourceString
0x180026e7c  lea     rcx, [rbp+57h+var_68]; DestinationString
0x180026e80  call    cs:__imp_RtlInitUnicodeString
0x180026e86  mov     rdx, r12; SourceString
0x180026e89  lea     rcx, [rbp+57h+var_58]; DestinationString
0x180026e8d  call    cs:__imp_RtlInitUnicodeString
0x180026e93  xor     ebx, ebx
0x180026e95  lea     rax, [rbp+57h+var_98]
0x180026e99  mov     [rsp+110h+Sid], rax; Sid
0x180026e9e  lea     rcx, [rbp+57h+IdentifierAuthority]; IdentifierAuthority
0x180026ea2  mov     [rsp+110h+SubAuthority7], ebx; SubAuthority7
0x180026ea6  xor     r9d, r9d; SubAuthority1
0x180026ea9  mov     [rsp+110h+SubAuthority6], ebx; SubAuthority6
0x180026ead  mov     dl, 1; SubAuthorityCount
0x180026eaf  mov     [rsp+110h+SubAuthority5], ebx; SubAuthority5
0x180026eb3  lea     r8d, [rbx+5Dh]; SubAuthority0
0x180026eb7  mov     [rsp+110h+SubAuthority4], ebx; SubAuthority4
0x180026ebb  mov     [rsp+110h+SubAuthority3], ebx; SubAuthority3
0x180026ebf  mov     [rsp+110h+SubAuthority2], ebx; SubAuthority2
0x180026ec3  call    cs:__imp_RtlAllocateAndInitializeSid
0x180026ec9  test    eax, eax
0x180026ecb  jns     loc_180026F6C
0x180026ed1  mov     ecx, eax; int
0x180026ed3  call    ?ResultFromWin32FromStatus@@YAJJ@Z; ResultFromWin32FromStatus(long)
0x180026ed8  mov     ebx, eax
0x180026eda  call    cs:__imp_GetProcessHeap
0x180026ee0  mov     r8, r12; lpMem
0x180026ee3  xor     edx, edx; dwFlags
0x180026ee5  mov     rcx, rax; hHeap
0x180026ee8  call    cs:__imp_HeapFree
0x180026eee  mov     rcx, [rbp+57h+var_A0]; Sid
0x180026ef2  test    rcx, rcx
0x180026ef5  jz      short loc_180026EFD
0x180026ef7  call    cs:__imp_RtlFreeSid
0x180026efd  mov     rcx, [rbp+57h+var_98]; Sid
0x180026f01  test    rcx, rcx
0x180026f04  jz      short loc_180026F0C
0x180026f06  call    cs:__imp_RtlFreeSid
0x180026f0c  mov     rcx, [rbp+57h+var_90]; Sid
0x180026f10  test    rcx, rcx
0x180026f13  jz      short loc_180026F1B
0x180026f15  call    cs:__imp_RtlFreeSid
0x180026f1b  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x180026f1f  jz      short loc_180026F2A
0x180026f21  mov     rcx, r14; hObject
0x180026f24  call    cs:__imp_CloseHandle
0x180026f2a  test    rdi, rdi
0x180026f2d  jz      short loc_180026F43
0x180026f2f  call    cs:__imp_GetProcessHeap
0x180026f35  mov     r8, rdi; lpMem
0x180026f38  xor     edx, edx; dwFlags
0x180026f3a  mov     rcx, rax; hHeap
0x180026f3d  call    cs:__imp_HeapFree
0x180026f43  mov     eax, ebx
0x180026f45  mov     rcx, [rbp+57h+var_40]
0x180026f49  xor     rcx, rsp; StackCookie
0x180026f4c  call    __security_check_cookie
0x180026f51  mov     rbx, [rsp+110h+arg_0]
0x180026f59  add     rsp, 0E0h
0x180026f60  pop     r15
0x180026f62  pop     r14
0x180026f64  pop     r13
0x180026f66  pop     r12
0x180026f68  pop     rdi
0x180026f69  pop     rsi
0x180026f6a  pop     rbp
0x180026f6b  retn
0x180026f6c  lea     rax, [rbp+57h+var_A0]
0x180026f70  mov     r8d, 5Dh ; ']'; SubAuthority0
0x180026f76  mov     [rsp+110h+Sid], rax; Sid
0x180026f7b  lea     r9, ?g_virtualAccountDomainMap@@3PAU_VIRTUAL_ACCOUNT_DOMAIN_MAP@@A; _VIRTUAL_ACCOUNT_DOMAIN_MAP near * g_virtualAccountDomainMap
0x180026f82  mov     r9d, [r15+r9+18h]; SubAuthority1
0x180026f87  lea     rcx, [rbp+57h+IdentifierAuthority]; IdentifierAuthority
0x180026f8b  mov     [rsp+110h+SubAuthority7], ebx; SubAuthority7
0x180026f8f  mov     dl, 3; SubAuthorityCount
0x180026f91  mov     [rsp+110h+SubAuthority6], ebx; SubAuthority6
0x180026f95  mov     [rsp+110h+SubAuthority5], ebx; SubAuthority5
0x180026f99  mov     [rsp+110h+SubAuthority4], ebx; SubAuthority4
0x180026f9d  mov     [rsp+110h+SubAuthority3], ebx; SubAuthority3
0x180026fa1  mov     [rsp+110h+SubAuthority2], ebx; SubAuthority2
0x180026fa5  call    cs:__imp_RtlAllocateAndInitializeSid
0x180026fab  test    eax, eax
0x180026fad  js      loc_180026ED1
0x180026fb3  lea     rax, [rbp+57h+var_90]
0x180026fb7  mov     r8d, 5Dh ; ']'; SubAuthority0
0x180026fbd  mov     [rsp+110h+Sid], rax; Sid
0x180026fc2  lea     rcx, [rbp+57h+IdentifierAuthority]; IdentifierAuthority
0x180026fc6  mov     eax, [rbp+57h+TokenInformation]
0x180026fc9  mov     dl, 4; SubAuthorityCount
0x180026fcb  mov     [rsp+110h+SubAuthority7], ebx; SubAuthority7
0x180026fcf  mov     [rsp+110h+SubAuthority6], ebx; SubAuthority6
0x180026fd3  mov     [rsp+110h+SubAuthority5], ebx; SubAuthority5
0x180026fd7  mov     [rsp+110h+SubAuthority4], ebx; SubAuthority4
0x180026fdb  mov     [rsp+110h+SubAuthority3], eax; SubAuthority3
0x180026fdf  lea     rax, ?g_virtualAccountDomainMap@@3PAU_VIRTUAL_ACCOUNT_DOMAIN_MAP@@A; _VIRTUAL_ACCOUNT_DOMAIN_MAP near * g_virtualAccountDomainMap
0x180026fe6  mov     r9d, [r15+rax+18h]; SubAuthority1
0x180026feb  mov     [rsp+110h+SubAuthority2], ebx; SubAuthority2
0x180026fef  call    cs:__imp_RtlAllocateAndInitializeSid
0x180026ff5  xor     r15d, r15d
0x180026ff8  test    eax, eax
0x180026ffa  js      loc_180026ED1
0x180027000  mov     r8, [rbp+57h+var_98]; void *
0x180027004  lea     r9, [rbp+57h+var_B0]; enum _LSA_SID_NAME_MAPPING_OPERATION_ERROR *
0x180027008  xor     edx, edx; struct _UNICODE_STRING *
0x18002700a  lea     rcx, [rbp+57h+DestinationString]; struct _UNICODE_STRING *
0x18002700e  call    ?AddSidMappingToLsa@@YAJPEAU_UNICODE_STRING@@0PEAXPEAW4_LSA_SID_NAME_MAPPING_OPERATION_ERROR@@@Z; AddSidMappingToLsa(_UNICODE_STRING *,_UNICODE_STRING *,void *,_LSA_SID_NAME_MAPPING_OPERATION_ERROR *)
0x180027013  mov     ebx, eax
0x180027015  test    eax, eax
0x180027017  js      loc_180026EDA
0x18002701d  mov     eax, [rbp+57h+var_B0]
0x180027020  add     eax, 0FFFFFFFEh
0x180027023  cmp     eax, 1
0x180027026  jbe     short loc_180027047
0x180027028  mov     r8, [rbp+57h+var_A0]; void *
0x18002702c  lea     r9, [rbp+57h+var_B0]; enum _LSA_SID_NAME_MAPPING_OPERATION_ERROR *
0x180027030  lea     rdx, [rbp+57h+var_68]; struct _UNICODE_STRING *
0x180027034  lea     rcx, [rbp+57h+DestinationString]; struct _UNICODE_STRING *
0x180027038  call    ?AddSidMappingToLsa@@YAJPEAU_UNICODE_STRING@@0PEAXPEAW4_LSA_SID_NAME_MAPPING_OPERATION_ERROR@@@Z; AddSidMappingToLsa(_UNICODE_STRING *,_UNICODE_STRING *,void *,_LSA_SID_NAME_MAPPING_OPERATION_ERROR *)
0x18002703d  mov     ebx, eax
0x18002703f  test    eax, eax
0x180027041  js      loc_180026EDA
0x180027047  mov     r8, [rbp+57h+var_90]; void *
0x18002704b  lea     r9, [rbp+57h+var_B0]; enum _LSA_SID_NAME_MAPPING_OPERATION_ERROR *
0x18002704f  lea     rdx, [rbp+57h+var_58]; struct _UNICODE_STRING *
0x180027053  lea     rcx, [rbp+57h+DestinationString]; struct _UNICODE_STRING *
0x180027057  call    ?AddSidMappingToLsa@@YAJPEAU_UNICODE_STRING@@0PEAXPEAW4_LSA_SID_NAME_MAPPING_OPERATION_ERROR@@@Z; AddSidMappingToLsa(_UNICODE_STRING *,_UNICODE_STRING *,void *,_LSA_SID_NAME_MAPPING_OPERATION_ERROR *)
0x18002705c  mov     ebx, eax
0x18002705e  test    eax, eax
0x180027060  js      loc_180026EDA
0x180027066  mov     rbx, r15
0x180027069  test    r13, r13
0x18002706c  jz      short loc_1800270B1
0x18002706e  call    cs:__imp_GetProcessHeap
0x180027074  mov     edx, 8; dwFlags
0x180027079  mov     rcx, rax; hHeap
0x18002707c  lea     r8d, [rdx+3Ch]; dwBytes
0x180027080  call    cs:__imp_HeapAlloc
0x180027086  mov     rbx, rax
0x180027089  test    rax, rax
0x18002708c  jnz     short loc_180027098
0x18002708e  mov     ebx, 8007000Eh
0x180027093  jmp     loc_180026EDA
0x180027098  mov     r8, r13; SourceSid
0x18002709b  mov     rdx, rax; DestinationSid
0x18002709e  mov     ecx, 44h ; 'D'; DestinationSidLength
0x1800270a3  call    cs:__imp_RtlCopySid
0x1800270a9  test    eax, eax
0x1800270ab  js      loc_180026ED1
0x1800270b1  call    cs:__imp_GetProcessHeap
0x1800270b7  mov     edx, 8; dwFlags
0x1800270bc  mov     rcx, rax; hHeap
0x1800270bf  lea     r8d, [rdx+30h]; dwBytes
0x1800270c3  call    cs:__imp_HeapAlloc
0x1800270c9  mov     rdi, rax
0x1800270cc  test    rax, rax
0x1800270cf  jz      short loc_18002708E
0x1800270d1  mov     [rax], esi
0x1800270d3  lea     rdx, [rbp+57h+TokenHandle]; void **
0x1800270d7  mov     eax, [rbp+57h+TokenInformation]
0x1800270da  mov     rcx, rdi; struct _VIRTUAL_ACCOUNT_CONTEXT *
0x1800270dd  mov     [rdi+4], eax
0x1800270e0  mov     [rdi+8], r12
0x1800270e4  mov     rax, [rbp+57h+var_98]
0x1800270e8  mov     [rdi+10h], rax
0x1800270ec  mov     rax, [rbp+57h+var_A0]
0x1800270f0  mov     [rdi+18h], rax
0x1800270f4  mov     rax, [rbp+57h+var_90]
0x1800270f8  mov     [rdi+20h], rax
0x1800270fc  mov     [rdi+28h], rbx
0x180027100  mov     qword ptr [rdi+30h], 0FFFFFFFFFFFFFFFFh
0x180027108  call    ?LogonVirtualAccountUser@@YAJPEBU_VIRTUAL_ACCOUNT_CONTEXT@@PEAPEAX@Z; LogonVirtualAccountUser(_VIRTUAL_ACCOUNT_CONTEXT const *,void * *)
0x18002710d  mov     r14, [rbp+57h+TokenHandle]
0x180027111  mov     ebx, eax
0x180027113  test    eax, eax
0x180027115  js      loc_180026EDA
0x18002711b  mov     r9d, 4; TokenInformationLength
0x180027121  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x180027125  mov     rcx, r14; TokenHandle
0x180027128  lea     edx, [r9+8]; TokenInformationClass
0x18002712c  call    cs:__imp_SetTokenInformation
0x180027132  test    eax, eax
0x180027134  jnz     short loc_180027154
0x180027136  call    cs:__imp_GetLastError
0x18002713c  mov     ebx, eax
0x18002713e  test    eax, eax
0x180027140  jle     loc_180026EDA
0x180027146  movzx   ebx, ax
0x180027149  or      ebx, 80070000h
0x18002714f  jmp     loc_180026EDA
0x180027154  mov     rax, [rbp+57h+var_70]
0x180027158  mov     rcx, r15
0x18002715b  mov     [rdi+30h], r14
0x18002715f  or      r14, 0FFFFFFFFFFFFFFFFh
0x180027163  mov     [rbp+57h+var_98], r15
0x180027167  mov     [rbp+57h+var_A0], rcx
0x18002716b  mov     [rax], rdi
0x18002716e  mov     rdi, r15
0x180027171  mov     [rbp+57h+var_90], r15
0x180027175  jmp     loc_180026EF2
```
