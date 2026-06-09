# EnsureTracingDirectory(CBsString *)

- ea: `0x180091058`
- end: `0x1800912d2`
- name: `?EnsureTracingDirectory@@YAJPEAVCBsString@@@Z`
- size: `634`
- prototype: `__int64 __fastcall(struct CBsString *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180091600`

## callees

- `0x1800083e4`
- `0x180014eac`
- `0x180072e08`
- `0x180072f14`
- `0x180091058`
- `0x1800935fc`
- `0x18009f560`

## import_xrefs

- `KERNEL32!DeleteFileW` at `0x180091107`
- `KERNEL32!DeleteFileW` at `0x180091107`
- `KERNEL32!LocalFree` at `0x18009129d`
- `KERNEL32!LocalFree` at `0x18009129d`
- `KERNEL32!GetLastError` at `0x1800911fa`
- `KERNEL32!GetLastError` at `0x1800911fa`
- `KERNEL32!GetFileAttributesW` at `0x1800910d6`
- `KERNEL32!GetFileAttributesW` at `0x1800910d6`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18009119b`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18009119b`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800911ea`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800911ea`

## string_xrefs

- `0x180091070`: `EnsureTracingDirectory`
- `0x180091150`: `::DeleteFile( *pstrDir )`

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

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v21, "EnsureTracingDirectory", 0x59u, 1u);
  v19 = 0;
  v18 = qword_1800EE510;
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
0x180091058  mov     [rsp-8+arg_8], rbx
0x18009105d  push    rbp
0x18009105e  lea     rbp, [rsp-57h]
0x180091063  sub     rsp, 90h
0x18009106a  mov     r9d, 1; unsigned __int16
0x180091070  lea     rdx, aEnsuretracingd; "EnsureTracingDirectory"
0x180091077  mov     rbx, rcx
0x18009107a  lea     rcx, [rbp+57h+var_38]; this
0x18009107e  lea     r8d, [r9+58h]; unsigned __int16
0x180091082  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180091087  lea     rax, qword_1800EE510
0x18009108e  mov     [rbp+57h+var_58], 0
0x180091096  mov     [rbp+57h+var_60], rax
0x18009109a  xorps   xmm0, xmm0
0x18009109d  xor     eax, eax
0x18009109f  mov     [rbp+57h+SecurityDescriptor], 0
0x1800910a7  mov     qword ptr [rbp+57h+SecurityAttributes.bInheritHandle], rax
0x1800910ab  movups  xmmword ptr [rbp+57h+SecurityAttributes.nLength], xmm0
0x1800910af  test    rbx, rbx
0x1800910b2  jnz     short loc_1800910C7
0x1800910b4  mov     [rbp+57h+var_38], 80070057h
0x1800910bb  lea     eax, [rbx+60h]
0x1800910be  mov     [rbp+57h+var_32], ax
0x1800910c2  jmp     loc_180091299
0x1800910c7  mov     rcx, [rbx]; lpFileName
0x1800910ca  mov     [rbp+57h+var_38], eax
0x1800910cd  mov     eax, 60h ; '`'
0x1800910d2  mov     [rbp+57h+var_34], ax
0x1800910d6  call    cs:__imp_GetFileAttributesW
0x1800910dd  nop     dword ptr [rax+rax+00h]
0x1800910e2  cmp     eax, 0FFFFFFFFh
0x1800910e5  jz      loc_180091189
0x1800910eb  test    al, 10h
0x1800910ed  jz      short loc_180091104
0x1800910ef  mov     [rbp+57h+var_38], 0
0x1800910f6  mov     eax, 68h ; 'h'
0x1800910fb  mov     [rbp+57h+var_34], ax
0x1800910ff  jmp     loc_180091299
0x180091104  mov     rcx, [rbx]; lpFileName
0x180091107  call    cs:__imp_DeleteFileW
0x18009110e  nop     dword ptr [rax+rax+00h]
0x180091113  test    eax, eax
0x180091115  jnz     short loc_180091179
0x180091117  call    GetLastFailureAsHRESULT
0x18009111c  mov     ecx, 72h ; 'r'
0x180091121  mov     [rbp+57h+var_38], eax
0x180091124  mov     [rbp+57h+var_32], cx
0x180091128  mov     rcx, cs:WPP_GLOBAL_Control
0x18009112f  lea     rdx, WPP_GLOBAL_Control
0x180091136  cmp     rcx, rdx
0x180091139  jz      loc_180091299
0x18009113f  test    dword ptr [rcx+1Ch], 2000000h
0x180091146  jz      loc_180091299
0x18009114c  mov     rcx, [rcx+10h]
0x180091150  lea     r9, aDeletefilePstr; "::DeleteFile( *pstrDir )"
0x180091157  mov     edx, 0Ah
0x18009115c  mov     [rsp+90h+var_68], eax
0x180091160  mov     rax, [rbx]
0x180091163  lea     r8, WPP_785c5ee6e04d30c0f81efb3b33a9d6e6_Traceguids
0x18009116a  mov     [rsp+90h+var_70], rax
0x18009116f  call    WPP_SF_sSd
0x180091174  jmp     loc_180091299
0x180091179  mov     ecx, 72h ; 'r'
0x18009117e  mov     [rbp+57h+var_38], 0
0x180091185  mov     [rbp+57h+var_34], cx
0x180091189  xor     r9d, r9d; SecurityDescriptorSize
0x18009118c  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x180091190  lea     rcx, StringSecurityDescriptor; "O:BAG:BAD:P(A;OICI;GA;;;BA)(A;OICI;GA;;"...
0x180091197  lea     edx, [r9+1]; StringSDRevision
0x18009119b  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800911a2  nop     dword ptr [rax+rax+00h]
0x1800911a7  test    eax, eax
0x1800911a9  jnz     short loc_1800911BD
0x1800911ab  call    GetLastFailureAsHRESULT
0x1800911b0  mov     [rbp+57h+var_38], eax
0x1800911b3  mov     eax, 7Dh ; '}'
0x1800911b8  jmp     loc_1800910BE
0x1800911bd  mov     rcx, [rbx]; lpPathName
0x1800911c0  lea     rdx, [rbp+57h+SecurityAttributes]; lpSecurityAttributes
0x1800911c4  mov     eax, 7Dh ; '}'
0x1800911c9  mov     [rbp+57h+var_38], 0
0x1800911d0  mov     [rbp+57h+var_34], ax
0x1800911d4  mov     rax, [rbp+57h+SecurityDescriptor]
0x1800911d8  mov     [rbp+57h+SecurityAttributes.lpSecurityDescriptor], rax
0x1800911dc  mov     [rbp+57h+SecurityAttributes.nLength], 18h
0x1800911e3  mov     [rbp+57h+SecurityAttributes.bInheritHandle], 0
0x1800911ea  call    cs:__imp_CreateDirectoryW
0x1800911f1  nop     dword ptr [rax+rax+00h]
0x1800911f6  test    eax, eax
0x1800911f8  jnz     short loc_180091265
0x1800911fa  call    cs:__imp_GetLastError
0x180091201  nop     dword ptr [rax+rax+00h]
0x180091206  xor     ecx, ecx
0x180091208  cmp     eax, 0B7h
0x18009120d  cmovnz  ecx, eax
0x180091210  test    ecx, ecx
0x180091212  jle     short loc_18009121D
0x180091214  movzx   ecx, cx
0x180091217  or      ecx, 80070000h
0x18009121d  mov     [rbp+57h+var_38], ecx
0x180091220  mov     eax, 8Ah
0x180091225  test    ecx, ecx
0x180091227  jns     loc_1800910FB
0x18009122d  mov     [rbp+57h+var_32], ax
0x180091231  mov     r10, cs:WPP_GLOBAL_Control
0x180091238  lea     rdx, WPP_GLOBAL_Control
0x18009123f  cmp     r10, rdx
0x180091242  jz      short loc_180091299
0x180091244  test    dword ptr [r10+1Ch], 2000000h
0x18009124c  jz      short loc_180091299
0x18009124e  mov     [rsp+90h+var_68], ecx
0x180091252  lea     edx, [rax-7Fh]
0x180091255  mov     rcx, [r10+10h]
0x180091259  lea     r9, aDwerr; "dwErr"
0x180091260  jmp     loc_180091160
0x180091265  mov     rcx, cs:WPP_GLOBAL_Control
0x18009126c  lea     rdx, WPP_GLOBAL_Control
0x180091273  cmp     rcx, rdx
0x180091276  jz      short loc_180091299
0x180091278  test    dword ptr [rcx+1Ch], 8000000h
0x18009127f  jz      short loc_180091299
0x180091281  mov     r9, [rbx]
0x180091284  lea     r8, WPP_785c5ee6e04d30c0f81efb3b33a9d6e6_Traceguids
0x18009128b  mov     rcx, [rcx+10h]
0x18009128f  mov     edx, 0Ch
0x180091294  call    WPP_SF_S
0x180091299  mov     rcx, [rbp+57h+SecurityDescriptor]; hMem
0x18009129d  call    cs:__imp_LocalFree
0x1800912a4  nop     dword ptr [rax+rax+00h]
0x1800912a9  mov     ebx, [rbp+57h+var_38]
0x1800912ac  lea     rcx, [rbp+57h+var_60]; this
0x1800912b0  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x1800912b5  lea     rcx, [rbp+57h+var_38]; this
0x1800912b9  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1800912be  mov     eax, ebx
0x1800912c0  mov     rbx, [rsp+90h+arg_8]
0x1800912c8  add     rsp, 90h
0x1800912cf  pop     rbp
0x1800912d0  retn
```
