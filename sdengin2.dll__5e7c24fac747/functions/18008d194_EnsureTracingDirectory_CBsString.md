# EnsureTracingDirectory(CBsString *)

- ea: `0x18008d194`
- end: `0x18008d3e9`
- name: `?EnsureTracingDirectory@@YAJPEAVCBsString@@@Z`
- size: `597`
- prototype: `__int64 __fastcall(struct CBsString *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18008d710`

## callees

- `0x180008240`
- `0x1800145f4`
- `0x18006fe84`
- `0x18006ff8c`
- `0x18008d194`
- `0x18008f5d0`
- `0x18009ae34`

## import_xrefs

- `KERNEL32!DeleteFileW` at `0x18008d23d`
- `KERNEL32!DeleteFileW` at `0x18008d23d`
- `KERNEL32!LocalFree` at `0x18008d3bb`
- `KERNEL32!LocalFree` at `0x18008d3bb`
- `KERNEL32!GetLastError` at `0x18008d31e`
- `KERNEL32!GetLastError` at `0x18008d31e`
- `KERNEL32!GetFileAttributesW` at `0x18008d212`
- `KERNEL32!GetFileAttributesW` at `0x18008d212`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18008d2cb`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18008d2cb`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18008d314`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18008d314`

## string_xrefs

- `0x18008d1ac`: `EnsureTracingDirectory`
- `0x18008d280`: `::DeleteFile( *pstrDir )`

## pseudocode

```c
__int64 __fastcall EnsureTracingDirectory(const WCHAR **a1)
{
  __int16 v2; // ax
  const WCHAR *v3; // rcx
  DWORD FileAttributesW; // eax
  __int16 v5; // ax
  __int64 v6; // rcx
  int LastFailureAsHRESULT; // eax
  __int64 v8; // rcx
  const char *v9; // r9
  int v10; // edx
  __int64 v11; // rcx
  const WCHAR *v12; // rcx
  DWORD LastError; // eax
  signed int v14; // ecx
  unsigned int v15; // ebx
  signed int v17; // [rsp+28h] [rbp-11h]
  __int64 *v18; // [rsp+30h] [rbp-9h] BYREF
  __int64 v19; // [rsp+38h] [rbp-1h]
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+40h] [rbp+7h] BYREF
  int v21; // [rsp+58h] [rbp+1Fh] BYREF
  __int16 v22; // [rsp+5Ch] [rbp+23h]
  __int16 v23; // [rsp+5Eh] [rbp+25h]
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+A0h] [rbp+67h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v21, "EnsureTracingDirectory", 89, 1);
  v19 = 0;
  v18 = qword_1800E8530;
  SecurityDescriptor = 0;
  memset(&SecurityAttributes, 0, sizeof(SecurityAttributes));
  if ( !a1 )
  {
    v21 = -2147024809;
    v2 = 96;
LABEL_3:
    v23 = v2;
    goto LABEL_28;
  }
  v3 = *a1;
  v21 = 0;
  v22 = 96;
  FileAttributesW = GetFileAttributesW(v3);
  if ( FileAttributesW != -1 )
  {
    if ( (FileAttributesW & 0x10) != 0 )
    {
      v21 = 0;
      v5 = 104;
LABEL_7:
      v22 = v5;
      goto LABEL_28;
    }
    if ( !DeleteFileW(*a1) )
    {
      LastFailureAsHRESULT = GetLastFailureAsHRESULT(v6);
      v21 = LastFailureAsHRESULT;
      v23 = 114;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
      {
        v8 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        v9 = "::DeleteFile( *pstrDir )";
        v10 = 10;
        v17 = LastFailureAsHRESULT;
LABEL_12:
        WPP_SF_sSd(
          v8,
          v10,
          (unsigned int)WPP_785c5ee6e04d30c0f81efb3b33a9d6e6_Traceguids,
          (_DWORD)v9,
          (__int64)*a1,
          v17,
          v18,
          v19,
          *(_QWORD *)&SecurityAttributes.nLength,
          SecurityAttributes.lpSecurityDescriptor,
          *(_QWORD *)&SecurityAttributes.bInheritHandle);
        goto LABEL_28;
      }
      goto LABEL_28;
    }
    v21 = 0;
    v22 = 114;
  }
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
          L"O:BAG:BAD:P(A;OICI;GA;;;BA)(A;OICI;GA;;;SY)",
          1u,
          &SecurityDescriptor,
          0) )
  {
    v21 = GetLastFailureAsHRESULT(v11);
    v2 = 125;
    goto LABEL_3;
  }
  v12 = *a1;
  v21 = 0;
  v22 = 125;
  SecurityAttributes.lpSecurityDescriptor = SecurityDescriptor;
  SecurityAttributes.nLength = 24;
  SecurityAttributes.bInheritHandle = 0;
  if ( CreateDirectoryW(v12, &SecurityAttributes) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_785c5ee6e04d30c0f81efb3b33a9d6e6_Traceguids, *a1);
  }
  else
  {
    LastError = GetLastError();
    v14 = 0;
    if ( LastError != 183 )
      v14 = LastError;
    if ( v14 > 0 )
      v14 = (unsigned __int16)v14 | 0x80070000;
    v21 = v14;
    v5 = 138;
    if ( v14 >= 0 )
      goto LABEL_7;
    v23 = 138;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
    {
      v17 = v14;
      v10 = 11;
      v8 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v9 = "dwErr";
      goto LABEL_12;
    }
  }
LABEL_28:
  LocalFree(SecurityDescriptor);
  v15 = v21;
  CBsString::_Release((CBsString *)&v18);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v21);
  return v15;
}

```

## disassembly

```asm
0x18008d194  mov     [rsp-8+arg_8], rbx
0x18008d199  push    rbp
0x18008d19a  lea     rbp, [rsp-57h]
0x18008d19f  sub     rsp, 90h
0x18008d1a6  mov     r9d, 1; unsigned __int16
0x18008d1ac  lea     rdx, aEnsuretracingd; "EnsureTracingDirectory"
0x18008d1b3  mov     rbx, rcx
0x18008d1b6  lea     rcx, [rbp+57h+var_38]; this
0x18008d1ba  lea     r8d, [r9+58h]; unsigned __int16
0x18008d1be  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18008d1c3  lea     rax, qword_1800E8530
0x18008d1ca  mov     [rbp+57h+var_58], 0
0x18008d1d2  mov     [rbp+57h+var_60], rax
0x18008d1d6  xorps   xmm0, xmm0
0x18008d1d9  xor     eax, eax
0x18008d1db  mov     [rbp+57h+SecurityDescriptor], 0
0x18008d1e3  mov     qword ptr [rbp+57h+SecurityAttributes.bInheritHandle], rax
0x18008d1e7  movups  xmmword ptr [rbp+57h+SecurityAttributes.nLength], xmm0
0x18008d1eb  test    rbx, rbx
0x18008d1ee  jnz     short loc_18008D203
0x18008d1f0  mov     [rbp+57h+var_38], 80070057h
0x18008d1f7  lea     eax, [rbx+60h]
0x18008d1fa  mov     [rbp+57h+var_32], ax
0x18008d1fe  jmp     loc_18008D3B7
0x18008d203  mov     rcx, [rbx]; lpFileName
0x18008d206  mov     [rbp+57h+var_38], eax
0x18008d209  mov     eax, 60h ; '`'
0x18008d20e  mov     [rbp+57h+var_34], ax
0x18008d212  call    cs:__imp_GetFileAttributesW
0x18008d218  cmp     eax, 0FFFFFFFFh
0x18008d21b  jz      loc_18008D2B9
0x18008d221  test    al, 10h
0x18008d223  jz      short loc_18008D23A
0x18008d225  mov     [rbp+57h+var_38], 0
0x18008d22c  mov     eax, 68h ; 'h'
0x18008d231  mov     [rbp+57h+var_34], ax
0x18008d235  jmp     loc_18008D3B7
0x18008d23a  mov     rcx, [rbx]; lpFileName
0x18008d23d  call    cs:__imp_DeleteFileW
0x18008d243  test    eax, eax
0x18008d245  jnz     short loc_18008D2A9
0x18008d247  call    GetLastFailureAsHRESULT
0x18008d24c  mov     ecx, 72h ; 'r'
0x18008d251  mov     [rbp+57h+var_38], eax
0x18008d254  mov     [rbp+57h+var_32], cx
0x18008d258  mov     rcx, cs:WPP_GLOBAL_Control
0x18008d25f  lea     rdx, WPP_GLOBAL_Control
0x18008d266  cmp     rcx, rdx
0x18008d269  jz      loc_18008D3B7
0x18008d26f  test    dword ptr [rcx+1Ch], 2000000h
0x18008d276  jz      loc_18008D3B7
0x18008d27c  mov     rcx, [rcx+10h]
0x18008d280  lea     r9, aDeletefilePstr; "::DeleteFile( *pstrDir )"
0x18008d287  mov     edx, 0Ah
0x18008d28c  mov     [rsp+90h+var_68], eax
0x18008d290  mov     rax, [rbx]
0x18008d293  lea     r8, WPP_785c5ee6e04d30c0f81efb3b33a9d6e6_Traceguids
0x18008d29a  mov     [rsp+90h+var_70], rax
0x18008d29f  call    WPP_SF_sSd
0x18008d2a4  jmp     loc_18008D3B7
0x18008d2a9  mov     ecx, 72h ; 'r'
0x18008d2ae  mov     [rbp+57h+var_38], 0
0x18008d2b5  mov     [rbp+57h+var_34], cx
0x18008d2b9  xor     r9d, r9d; SecurityDescriptorSize
0x18008d2bc  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x18008d2c0  lea     rcx, StringSecurityDescriptor; "O:BAG:BAD:P(A;OICI;GA;;;BA)(A;OICI;GA;;"...
0x18008d2c7  lea     edx, [r9+1]; StringSDRevision
0x18008d2cb  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18008d2d1  test    eax, eax
0x18008d2d3  jnz     short loc_18008D2E7
0x18008d2d5  call    GetLastFailureAsHRESULT
0x18008d2da  mov     [rbp+57h+var_38], eax
0x18008d2dd  mov     eax, 7Dh ; '}'
0x18008d2e2  jmp     loc_18008D1FA
0x18008d2e7  mov     rcx, [rbx]; lpPathName
0x18008d2ea  lea     rdx, [rbp+57h+SecurityAttributes]; lpSecurityAttributes
0x18008d2ee  mov     eax, 7Dh ; '}'
0x18008d2f3  mov     [rbp+57h+var_38], 0
0x18008d2fa  mov     [rbp+57h+var_34], ax
0x18008d2fe  mov     rax, [rbp+57h+SecurityDescriptor]
0x18008d302  mov     [rbp+57h+SecurityAttributes.lpSecurityDescriptor], rax
0x18008d306  mov     [rbp+57h+SecurityAttributes.nLength], 18h
0x18008d30d  mov     [rbp+57h+SecurityAttributes.bInheritHandle], 0
0x18008d314  call    cs:__imp_CreateDirectoryW
0x18008d31a  test    eax, eax
0x18008d31c  jnz     short loc_18008D383
0x18008d31e  call    cs:__imp_GetLastError
0x18008d324  xor     ecx, ecx
0x18008d326  cmp     eax, 0B7h
0x18008d32b  cmovnz  ecx, eax
0x18008d32e  test    ecx, ecx
0x18008d330  jle     short loc_18008D33B
0x18008d332  movzx   ecx, cx
0x18008d335  or      ecx, 80070000h
0x18008d33b  mov     [rbp+57h+var_38], ecx
0x18008d33e  mov     eax, 8Ah
0x18008d343  test    ecx, ecx
0x18008d345  jns     loc_18008D231
0x18008d34b  mov     [rbp+57h+var_32], ax
0x18008d34f  mov     r10, cs:WPP_GLOBAL_Control
0x18008d356  lea     rdx, WPP_GLOBAL_Control
0x18008d35d  cmp     r10, rdx
0x18008d360  jz      short loc_18008D3B7
0x18008d362  test    dword ptr [r10+1Ch], 2000000h
0x18008d36a  jz      short loc_18008D3B7
0x18008d36c  mov     [rsp+90h+var_68], ecx
0x18008d370  lea     edx, [rax-7Fh]
0x18008d373  mov     rcx, [r10+10h]
0x18008d377  lea     r9, aDwerr; "dwErr"
0x18008d37e  jmp     loc_18008D290
0x18008d383  mov     rcx, cs:WPP_GLOBAL_Control
0x18008d38a  lea     rdx, WPP_GLOBAL_Control
0x18008d391  cmp     rcx, rdx
0x18008d394  jz      short loc_18008D3B7
0x18008d396  test    dword ptr [rcx+1Ch], 8000000h
0x18008d39d  jz      short loc_18008D3B7
0x18008d39f  mov     r9, [rbx]
0x18008d3a2  lea     r8, WPP_785c5ee6e04d30c0f81efb3b33a9d6e6_Traceguids
0x18008d3a9  mov     rcx, [rcx+10h]
0x18008d3ad  mov     edx, 0Ch
0x18008d3b2  call    WPP_SF_S
0x18008d3b7  mov     rcx, [rbp+57h+SecurityDescriptor]; hMem
0x18008d3bb  call    cs:__imp_LocalFree
0x18008d3c1  mov     ebx, [rbp+57h+var_38]
0x18008d3c4  lea     rcx, [rbp+57h+var_60]; this
0x18008d3c8  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x18008d3cd  lea     rcx, [rbp+57h+var_38]; this
0x18008d3d1  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18008d3d6  mov     eax, ebx
0x18008d3d8  mov     rbx, [rsp+90h+arg_8]
0x18008d3e0  add     rsp, 90h
0x18008d3e7  pop     rbp
0x18008d3e8  retn
```
