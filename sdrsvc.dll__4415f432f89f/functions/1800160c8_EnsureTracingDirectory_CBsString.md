# EnsureTracingDirectory(CBsString *)

- ea: `0x1800160c8`
- end: `0x18001631d`
- name: `?EnsureTracingDirectory@@YAJPEAVCBsString@@@Z`
- size: `597`
- prototype: `__int64 __fastcall(const WCHAR **)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180016520`

## callees

- `0x180014f70`
- `0x1800150f4`
- `0x18001586c`
- `0x180015974`
- `0x1800160c8`
- `0x18001c58c`
- `0x180020488`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016252`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016252`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800162ef`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800162ef`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800161ff`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800161ff`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180016248`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180016248`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180016171`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180016171`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180016146`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180016146`

## string_xrefs

- `0x1800160e0`: `EnsureTracingDirectory`
- `0x1800161b4`: `::DeleteFile( *pstrDir )`

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
  v18 = qword_180028260;
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
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
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
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
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
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
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
  CBsString::_Release((LPVOID *)&v18);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v21);
  return v15;
}

```

## disassembly

```asm
0x1800160c8  mov     [rsp-8+arg_8], rbx
0x1800160cd  push    rbp
0x1800160ce  lea     rbp, [rsp-57h]
0x1800160d3  sub     rsp, 90h
0x1800160da  mov     r9d, 1; unsigned __int16
0x1800160e0  lea     rdx, aEnsuretracingd; "EnsureTracingDirectory"
0x1800160e7  mov     rbx, rcx
0x1800160ea  lea     rcx, [rbp+57h+var_38]; this
0x1800160ee  lea     r8d, [r9+58h]; unsigned __int16
0x1800160f2  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1800160f7  lea     rax, qword_180028260
0x1800160fe  mov     [rbp+57h+var_58], 0
0x180016106  mov     [rbp+57h+var_60], rax
0x18001610a  xorps   xmm0, xmm0
0x18001610d  xor     eax, eax
0x18001610f  mov     [rbp+57h+SecurityDescriptor], 0
0x180016117  mov     qword ptr [rbp+57h+SecurityAttributes.bInheritHandle], rax
0x18001611b  movups  xmmword ptr [rbp+57h+SecurityAttributes.nLength], xmm0
0x18001611f  test    rbx, rbx
0x180016122  jnz     short loc_180016137
0x180016124  mov     [rbp+57h+var_38], 80070057h
0x18001612b  lea     eax, [rbx+60h]
0x18001612e  mov     [rbp+57h+var_32], ax
0x180016132  jmp     loc_1800162EB
0x180016137  mov     rcx, [rbx]; lpFileName
0x18001613a  mov     [rbp+57h+var_38], eax
0x18001613d  mov     eax, 60h ; '`'
0x180016142  mov     [rbp+57h+var_34], ax
0x180016146  call    cs:__imp_GetFileAttributesW
0x18001614c  cmp     eax, 0FFFFFFFFh
0x18001614f  jz      loc_1800161ED
0x180016155  test    al, 10h
0x180016157  jz      short loc_18001616E
0x180016159  mov     [rbp+57h+var_38], 0
0x180016160  mov     eax, 68h ; 'h'
0x180016165  mov     [rbp+57h+var_34], ax
0x180016169  jmp     loc_1800162EB
0x18001616e  mov     rcx, [rbx]; lpFileName
0x180016171  call    cs:__imp_DeleteFileW
0x180016177  test    eax, eax
0x180016179  jnz     short loc_1800161DD
0x18001617b  call    GetLastFailureAsHRESULT
0x180016180  mov     ecx, 72h ; 'r'
0x180016185  mov     [rbp+57h+var_38], eax
0x180016188  mov     [rbp+57h+var_32], cx
0x18001618c  mov     rcx, cs:WPP_GLOBAL_Control
0x180016193  lea     rdx, WPP_GLOBAL_Control
0x18001619a  cmp     rcx, rdx
0x18001619d  jz      loc_1800162EB
0x1800161a3  test    dword ptr [rcx+1Ch], 2000000h
0x1800161aa  jz      loc_1800162EB
0x1800161b0  mov     rcx, [rcx+10h]
0x1800161b4  lea     r9, aDeletefilePstr; "::DeleteFile( *pstrDir )"
0x1800161bb  mov     edx, 0Ah
0x1800161c0  mov     [rsp+90h+var_68], eax
0x1800161c4  mov     rax, [rbx]
0x1800161c7  lea     r8, WPP_785c5ee6e04d30c0f81efb3b33a9d6e6_Traceguids
0x1800161ce  mov     [rsp+90h+var_70], rax
0x1800161d3  call    WPP_SF_sSd
0x1800161d8  jmp     loc_1800162EB
0x1800161dd  mov     ecx, 72h ; 'r'
0x1800161e2  mov     [rbp+57h+var_38], 0
0x1800161e9  mov     [rbp+57h+var_34], cx
0x1800161ed  xor     r9d, r9d; SecurityDescriptorSize
0x1800161f0  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x1800161f4  lea     rcx, aOBagBadPAOiciG; "O:BAG:BAD:P(A;OICI;GA;;;BA)(A;OICI;GA;;"...
0x1800161fb  lea     edx, [r9+1]; StringSDRevision
0x1800161ff  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180016205  test    eax, eax
0x180016207  jnz     short loc_18001621B
0x180016209  call    GetLastFailureAsHRESULT
0x18001620e  mov     [rbp+57h+var_38], eax
0x180016211  mov     eax, 7Dh ; '}'
0x180016216  jmp     loc_18001612E
0x18001621b  mov     rcx, [rbx]; lpPathName
0x18001621e  lea     rdx, [rbp+57h+SecurityAttributes]; lpSecurityAttributes
0x180016222  mov     eax, 7Dh ; '}'
0x180016227  mov     [rbp+57h+var_38], 0
0x18001622e  mov     [rbp+57h+var_34], ax
0x180016232  mov     rax, [rbp+57h+SecurityDescriptor]
0x180016236  mov     [rbp+57h+SecurityAttributes.lpSecurityDescriptor], rax
0x18001623a  mov     [rbp+57h+SecurityAttributes.nLength], 18h
0x180016241  mov     [rbp+57h+SecurityAttributes.bInheritHandle], 0
0x180016248  call    cs:__imp_CreateDirectoryW
0x18001624e  test    eax, eax
0x180016250  jnz     short loc_1800162B7
0x180016252  call    cs:__imp_GetLastError
0x180016258  xor     ecx, ecx
0x18001625a  cmp     eax, 0B7h
0x18001625f  cmovnz  ecx, eax
0x180016262  test    ecx, ecx
0x180016264  jle     short loc_18001626F
0x180016266  movzx   ecx, cx
0x180016269  or      ecx, 80070000h
0x18001626f  mov     [rbp+57h+var_38], ecx
0x180016272  mov     eax, 8Ah
0x180016277  test    ecx, ecx
0x180016279  jns     loc_180016165
0x18001627f  mov     [rbp+57h+var_32], ax
0x180016283  mov     r10, cs:WPP_GLOBAL_Control
0x18001628a  lea     rdx, WPP_GLOBAL_Control
0x180016291  cmp     r10, rdx
0x180016294  jz      short loc_1800162EB
0x180016296  test    dword ptr [r10+1Ch], 2000000h
0x18001629e  jz      short loc_1800162EB
0x1800162a0  mov     [rsp+90h+var_68], ecx
0x1800162a4  lea     edx, [rax-7Fh]
0x1800162a7  mov     rcx, [r10+10h]
0x1800162ab  lea     r9, aDwerr; "dwErr"
0x1800162b2  jmp     loc_1800161C4
0x1800162b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800162be  lea     rdx, WPP_GLOBAL_Control
0x1800162c5  cmp     rcx, rdx
0x1800162c8  jz      short loc_1800162EB
0x1800162ca  test    dword ptr [rcx+1Ch], 8000000h
0x1800162d1  jz      short loc_1800162EB
0x1800162d3  mov     r9, [rbx]
0x1800162d6  lea     r8, WPP_785c5ee6e04d30c0f81efb3b33a9d6e6_Traceguids
0x1800162dd  mov     rcx, [rcx+10h]
0x1800162e1  mov     edx, 0Ch
0x1800162e6  call    WPP_SF_S
0x1800162eb  mov     rcx, [rbp+57h+SecurityDescriptor]; hMem
0x1800162ef  call    cs:__imp_LocalFree
0x1800162f5  mov     ebx, [rbp+57h+var_38]
0x1800162f8  lea     rcx, [rbp+57h+var_60]; this
0x1800162fc  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x180016301  lea     rcx, [rbp+57h+var_38]; this
0x180016305  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18001630a  mov     eax, ebx
0x18001630c  mov     rbx, [rsp+90h+arg_8]
0x180016314  add     rsp, 90h
0x18001631b  pop     rbp
0x18001631c  retn
```
