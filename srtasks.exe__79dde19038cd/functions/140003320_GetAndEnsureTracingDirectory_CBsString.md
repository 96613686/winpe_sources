# GetAndEnsureTracingDirectory(CBsString *)

- ea: `0x140003320`
- end: `0x14000357b`
- name: `?GetAndEnsureTracingDirectory@@YAJPEAVCBsString@@@Z`
- size: `603`
- prototype: `__int64 __fastcall(struct CBsString *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1400039e4`

## callees

- `0x140003320`
- `0x140005658`
- `0x140006cc8`
- `0x14000e324`
- `0x14000e41c`
- `0x14000ffec`
- `0x14001036c`
- `0x140010744`

## import_xrefs

- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x14000346e`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x14000346e`
- `KERNEL32!CreateDirectoryW` at `0x1400034b7`
- `KERNEL32!CreateDirectoryW` at `0x1400034b7`
- `KERNEL32!DeleteFileW` at `0x1400033e3`
- `KERNEL32!DeleteFileW` at `0x1400033e3`
- `KERNEL32!GetFileAttributesW` at `0x1400033c9`
- `KERNEL32!GetFileAttributesW` at `0x1400033c9`
- `KERNEL32!LocalFree` at `0x140003549`
- `KERNEL32!LocalFree` at `0x140003549`
- `KERNEL32!GetLastError` at `0x1400034c1`
- `KERNEL32!GetLastError` at `0x1400034c1`

## string_xrefs

- `0x14000333a`: `GetAndEnsureTracingDirectory`
- `0x140003426`: `::DeleteFile( strTracingDirectory )`

## pseudocode

```c
// Creates fixed %SystemRoot%\Logs\SystemRestore with BA/SY-only SDDL; StandardUser cannot create/replace parent/path in default ACL state.
__int64 __fastcall GetAndEnsureTracingDirectory(struct CBsString *a1)
{
  const unsigned __int16 *v2; // rdx
  _WORD *v3; // rcx
  __int16 v4; // ax
  const WCHAR *v5; // rdi
  DWORD FileAttributesW; // eax
  int LastFailureAsHRESULT; // eax
  DWORD LastError; // eax
  signed int v9; // ecx
  unsigned int v10; // ebx
  LPCWSTR lpFileName[2]; // [rsp+30h] [rbp-9h] BYREF
  _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+40h] [rbp+7h] BYREF
  int v14; // [rsp+58h] [rbp+1Fh] BYREF
  __int16 v15; // [rsp+5Ch] [rbp+23h]
  __int16 v16; // [rsp+5Eh] [rbp+25h]
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+A0h] [rbp+67h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v14, "GetAndEnsureTracingDirectory", 0x3F9u, 1u);
  lpFileName[1] = 0;
  lpFileName[0] = (LPCWSTR)qword_140013960;
  SecurityDescriptor = 0;
  memset(&SecurityAttributes, 0, sizeof(SecurityAttributes));
  if ( !a1 )
  {
    v14 = -2147024809;
    v4 = 1026;
    goto LABEL_27;
  }
  if ( *((_DWORD *)a1 + 2) )
  {
    v3 = *(_WORD **)a1;
    *((_DWORD *)a1 + 2) = 0;
    *v3 = 0;
  }
  v14 = 0;
  v15 = 1026;
  v14 = CBsString::ExpandEnvironmentStringsW((CBsString *)lpFileName, v2);
  v4 = 1029;
  if ( v14 < 0 )
    goto LABEL_27;
  v5 = lpFileName[0];
  v15 = 1029;
  FileAttributesW = GetFileAttributesW(lpFileName[0]);
  if ( FileAttributesW != -1 )
  {
    if ( (FileAttributesW & 0x10) != 0 )
      goto LABEL_25;
    if ( !DeleteFileW(v5) )
    {
      LastFailureAsHRESULT = GetLastFailureAsHRESULT();
      v14 = LastFailureAsHRESULT;
      v16 = 1044;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
      {
        WPP_SF_sSd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          60,
          (unsigned int)&WPP_101e0a96400b3b07d1faa29ced9d8670_Traceguids,
          (unsigned int)"::DeleteFile( strTracingDirectory )",
          (__int64)v5,
          LastFailureAsHRESULT);
      }
      goto LABEL_28;
    }
    v14 = 0;
    v15 = 1044;
  }
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
          L"O:BAG:BAD:P(A;OICI;GA;;;BA)(A;OICI;GA;;;SY)",
          1u,
          &SecurityDescriptor,
          0) )
  {
    v14 = GetLastFailureAsHRESULT();
    v4 = 1055;
LABEL_27:
    v16 = v4;
    goto LABEL_28;
  }
  v14 = 0;
  v15 = 1055;
  SecurityAttributes.lpSecurityDescriptor = SecurityDescriptor;
  SecurityAttributes.nLength = 24;
  SecurityAttributes.bInheritHandle = 0;
  if ( CreateDirectoryW(v5, &SecurityAttributes) )
  {
LABEL_25:
    CBsString::Transfer((CBsString *)lpFileName, a1);
    goto LABEL_28;
  }
  LastError = GetLastError();
  v9 = 0;
  if ( LastError != 183 )
    v9 = LastError;
  if ( v9 > 0 )
    v9 = (unsigned __int16)v9 | 0x80070000;
  v14 = v9;
  if ( v9 >= 0 )
  {
    v15 = 1068;
    goto LABEL_25;
  }
  v16 = 1068;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
    WPP_SF_sSd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      61,
      (unsigned int)&WPP_101e0a96400b3b07d1faa29ced9d8670_Traceguids,
      (unsigned int)"dwErr",
      (__int64)v5,
      v9);
LABEL_28:
  LocalFree(SecurityDescriptor);
  v10 = v14;
  CBsString::_Release((CBsString *)lpFileName);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v14);
  return v10;
}

```

## disassembly

```asm
0x140003320  mov     [rsp-8+arg_8], rbx; Creates fixed %SystemRoot%\Logs\SystemRestore with BA/SY-only SDDL; StandardUser cannot create/replace parent/path in default ACL state.
0x140003325  mov     [rsp-8+arg_10], rdi
0x14000332a  push    rbp
0x14000332b  lea     rbp, [rsp-57h]
0x140003330  sub     rsp, 90h
0x140003337  mov     rbx, rcx
0x14000333a  lea     rdx, aGetandensuretr; "GetAndEnsureTracingDirectory"
0x140003341  lea     rcx, [rbp+57h+var_38]; this
0x140003345  mov     r9d, 1; unsigned __int16
0x14000334b  mov     r8d, 3F9h; unsigned __int16
0x140003351  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x140003356  lea     rax, qword_140013960
0x14000335d  mov     [rbp+57h+var_58], 0
0x140003365  mov     [rbp+57h+lpFileName], rax
0x140003369  xorps   xmm0, xmm0
0x14000336c  xor     eax, eax
0x14000336e  mov     [rbp+57h+SecurityDescriptor], 0
0x140003376  mov     qword ptr [rbp+57h+SecurityAttributes.bInheritHandle], rax
0x14000337a  movups  xmmword ptr [rbp+57h+SecurityAttributes.nLength], xmm0
0x14000337e  test    rbx, rbx
0x140003381  jz      loc_140003535
0x140003387  cmp     [rbx+8], eax
0x14000338a  jz      short loc_140003395
0x14000338c  mov     rcx, [rbx]
0x14000338f  mov     [rbx+8], eax
0x140003392  mov     [rcx], ax
0x140003395  mov     eax, 402h
0x14000339a  mov     [rbp+57h+var_38], 0
0x1400033a1  lea     rcx, [rbp+57h+lpFileName]; this
0x1400033a5  mov     [rbp+57h+var_34], ax
0x1400033a9  call    ?ExpandEnvironmentStringsW@CBsString@@QEAAJPEBG@Z; CBsString::ExpandEnvironmentStringsW(ushort const *)
0x1400033ae  mov     [rbp+57h+var_38], eax
0x1400033b1  test    eax, eax
0x1400033b3  mov     eax, 405h
0x1400033b8  js      loc_140003541
0x1400033be  mov     rdi, [rbp+57h+lpFileName]
0x1400033c2  mov     rcx, rdi; lpFileName
0x1400033c5  mov     [rbp+57h+var_34], ax
0x1400033c9  call    cs:__imp_GetFileAttributesW
0x1400033cf  cmp     eax, 0FFFFFFFFh
0x1400033d2  jz      loc_14000345C
0x1400033d8  test    al, 10h
0x1400033da  jnz     loc_140003527
0x1400033e0  mov     rcx, rdi; lpFileName
0x1400033e3  call    cs:__imp_DeleteFileW
0x1400033e9  test    eax, eax
0x1400033eb  jnz     short loc_14000344C
0x1400033ed  call    GetLastFailureAsHRESULT
0x1400033f2  mov     ecx, 414h
0x1400033f7  mov     [rbp+57h+var_38], eax
0x1400033fa  mov     [rbp+57h+var_32], cx
0x1400033fe  mov     rcx, cs:WPP_GLOBAL_Control
0x140003405  lea     rdx, WPP_GLOBAL_Control
0x14000340c  cmp     rcx, rdx
0x14000340f  jz      loc_140003545
0x140003415  test    dword ptr [rcx+1Ch], 2000000h
0x14000341c  jz      loc_140003545
0x140003422  mov     rcx, [rcx+10h]
0x140003426  lea     r9, aDeletefileStrt; "::DeleteFile( strTracingDirectory )"
0x14000342d  mov     edx, 3Ch ; '<'
0x140003432  mov     [rsp+90h+var_68], eax
0x140003436  lea     r8, WPP_101e0a96400b3b07d1faa29ced9d8670_Traceguids
0x14000343d  mov     [rsp+90h+var_70], rdi
0x140003442  call    WPP_SF_sSd
0x140003447  jmp     loc_140003545
0x14000344c  mov     ecx, 414h
0x140003451  mov     [rbp+57h+var_38], 0
0x140003458  mov     [rbp+57h+var_34], cx
0x14000345c  xor     r9d, r9d; SecurityDescriptorSize
0x14000345f  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x140003463  lea     rcx, StringSecurityDescriptor; "O:BAG:BAD:P(A;OICI;GA;;;BA)(A;OICI;GA;;"...
0x14000346a  lea     edx, [r9+1]; StringSDRevision
0x14000346e  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x140003474  test    eax, eax
0x140003476  jnz     short loc_14000348A
0x140003478  call    GetLastFailureAsHRESULT
0x14000347d  mov     [rbp+57h+var_38], eax
0x140003480  mov     eax, 41Fh
0x140003485  jmp     loc_140003541
0x14000348a  mov     eax, 41Fh
0x14000348f  mov     [rbp+57h+var_38], 0
0x140003496  mov     [rbp+57h+var_34], ax
0x14000349a  lea     rdx, [rbp+57h+SecurityAttributes]; lpSecurityAttributes
0x14000349e  mov     rax, [rbp+57h+SecurityDescriptor]
0x1400034a2  mov     rcx, rdi; lpPathName
0x1400034a5  mov     [rbp+57h+SecurityAttributes.lpSecurityDescriptor], rax
0x1400034a9  mov     [rbp+57h+SecurityAttributes.nLength], 18h
0x1400034b0  mov     [rbp+57h+SecurityAttributes.bInheritHandle], 0
0x1400034b7  call    cs:__imp_CreateDirectoryW
0x1400034bd  test    eax, eax
0x1400034bf  jnz     short loc_140003527
0x1400034c1  call    cs:__imp_GetLastError
0x1400034c7  xor     ecx, ecx
0x1400034c9  cmp     eax, 0B7h
0x1400034ce  cmovnz  ecx, eax
0x1400034d1  test    ecx, ecx
0x1400034d3  jle     short loc_1400034DE
0x1400034d5  movzx   ecx, cx
0x1400034d8  or      ecx, 80070000h
0x1400034de  mov     [rbp+57h+var_38], ecx
0x1400034e1  mov     eax, 42Ch
0x1400034e6  test    ecx, ecx
0x1400034e8  jns     short loc_140003523
0x1400034ea  mov     [rbp+57h+var_32], ax
0x1400034ee  mov     rax, cs:WPP_GLOBAL_Control
0x1400034f5  lea     rdx, WPP_GLOBAL_Control
0x1400034fc  cmp     rax, rdx
0x1400034ff  jz      short loc_140003545
0x140003501  test    dword ptr [rax+1Ch], 2000000h
0x140003508  jz      short loc_140003545
0x14000350a  mov     [rsp+90h+var_68], ecx
0x14000350e  lea     r9, aDwerr; "dwErr"
0x140003515  mov     rcx, [rax+10h]
0x140003519  mov     edx, 3Dh ; '='
0x14000351e  jmp     loc_140003436
0x140003523  mov     [rbp+57h+var_34], ax
0x140003527  mov     rdx, rbx; struct CBsString *
0x14000352a  lea     rcx, [rbp+57h+lpFileName]; this
0x14000352e  call    ?Transfer@CBsString@@QEAAXPEAV1@@Z; CBsString::Transfer(CBsString *)
0x140003533  jmp     short loc_140003545
0x140003535  mov     [rbp+57h+var_38], 80070057h
0x14000353c  mov     eax, 402h
0x140003541  mov     [rbp+57h+var_32], ax
0x140003545  mov     rcx, [rbp+57h+SecurityDescriptor]; hMem
0x140003549  call    cs:__imp_LocalFree
0x14000354f  mov     ebx, [rbp+57h+var_38]
0x140003552  lea     rcx, [rbp+57h+lpFileName]; this
0x140003556  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x14000355b  lea     rcx, [rbp+57h+var_38]; this
0x14000355f  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x140003564  lea     r11, [rsp+90h+var_s0]
0x14000356c  mov     eax, ebx
0x14000356e  mov     rbx, [r11+18h]
0x140003572  mov     rdi, [r11+20h]
0x140003576  mov     rsp, r11
0x140003579  pop     rbp
0x14000357a  retn
```
