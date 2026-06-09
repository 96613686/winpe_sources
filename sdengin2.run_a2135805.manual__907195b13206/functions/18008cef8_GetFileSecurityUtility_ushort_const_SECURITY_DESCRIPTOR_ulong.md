# GetFileSecurityUtility(ushort const *,_SECURITY_DESCRIPTOR * *,ulong *)

- ea: `0x18008cef8`
- end: `0x18008d147`
- name: `?GetFileSecurityUtility@@YAJPEBGPEAPEAU_SECURITY_DESCRIPTOR@@PEAK@Z`
- size: `591`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, struct _SECURITY_DESCRIPTOR **, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18001dd8c`

## callees

- `0x180072e08`
- `0x180072f14`
- `0x18008cef8`
- `0x1800935fc`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x18008cf9e`
- `KERNEL32!CreateFileW` at `0x18008cf9e`
- `KERNEL32!GetLastError` at `0x18008d032`
- `KERNEL32!GetLastError` at `0x18008d032`
- `KERNEL32!CloseHandle` at `0x18008d11f`
- `KERNEL32!CloseHandle` at `0x18008d11f`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x18008d01e`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x18008d0be`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x18008d01e`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x18008d0be`
- `ole32!CoTaskMemFree` at `0x18008d06c`
- `ole32!CoTaskMemFree` at `0x18008d103`
- `ole32!CoTaskMemFree` at `0x18008d06c`
- `ole32!CoTaskMemFree` at `0x18008d103`
- `ole32!CoTaskMemAlloc` at `0x18008cfd7`
- `ole32!CoTaskMemAlloc` at `0x18008d07f`
- `ole32!CoTaskMemAlloc` at `0x18008cfd7`
- `ole32!CoTaskMemAlloc` at `0x18008d07f`

## string_xrefs

- `0x18008cf16`: `GetFileSecurityUtility`

## pseudocode

```c
__int64 __fastcall GetFileSecurityUtility(LPCWSTR lpFileName, struct _SECURITY_DESCRIPTOR **a2, unsigned int *a3)
{
  struct _SECURITY_DESCRIPTOR *v6; // rdi
  __int64 FileW; // rbx
  __int16 v8; // ax
  __int64 v9; // rcx
  __int64 v10; // rcx
  DWORD v11; // r15d
  unsigned int v12; // edi
  int LastFailureAsHRESULT; // [rsp+40h] [rbp-19h] BYREF
  __int16 v15; // [rsp+44h] [rbp-15h]
  __int16 v16; // [rsp+46h] [rbp-13h]
  DWORD nLengthNeeded; // [rsp+C0h] [rbp+67h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT, "GetFileSecurityUtility", 0x114u, 1u);
  v6 = 0;
  FileW = -1;
  nLengthNeeded = 0;
  if ( a3 )
    *a3 = 0;
  if ( a2 )
    *a2 = 0;
  v8 = 287;
  if ( !lpFileName || (v15 = 287, v8 = 288, !a2) )
  {
    LastFailureAsHRESULT = -2147024809;
LABEL_7:
    v16 = v8;
    goto LABEL_22;
  }
  LastFailureAsHRESULT = 0;
  v15 = 288;
  FileW = (__int64)CreateFileW(lpFileName, 0x1020000u, 1u, 0, 3u, 0x2000000u, 0);
  if ( FileW == -1 )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v9);
    v8 = 291;
    goto LABEL_7;
  }
  LastFailureAsHRESULT = 0;
  v15 = 291;
  v6 = (struct _SECURITY_DESCRIPTOR *)CoTaskMemAlloc(0x400u);
  v8 = 294;
  if ( !v6 )
  {
LABEL_12:
    LastFailureAsHRESULT = -2147024882;
    goto LABEL_7;
  }
  v15 = 294;
  LastFailureAsHRESULT = 0;
  if ( !GetKernelObjectSecurity((HANDLE)FileW, 0x1Fu, v6, 0x400u, &nLengthNeeded) )
  {
    if ( GetLastError() != 122 )
      goto LABEL_19;
    v8 = 300;
    if ( nLengthNeeded <= 0x400 )
    {
      LastFailureAsHRESULT = -2147467259;
      goto LABEL_7;
    }
    LastFailureAsHRESULT = 0;
    v15 = 300;
    CoTaskMemFree(v6);
    v11 = nLengthNeeded;
    v6 = (struct _SECURITY_DESCRIPTOR *)CoTaskMemAlloc(nLengthNeeded);
    v8 = 306;
    if ( !v6 )
      goto LABEL_12;
    v15 = 306;
    LastFailureAsHRESULT = 0;
    if ( !GetKernelObjectSecurity((HANDLE)FileW, 0x1Fu, v6, v11, &nLengthNeeded) )
    {
LABEL_19:
      LastFailureAsHRESULT = GetLastFailureAsHRESULT(v10);
      v8 = 310;
      goto LABEL_7;
    }
  }
  *a2 = v6;
  v6 = 0;
  LastFailureAsHRESULT = 0;
  v15 = 310;
  if ( a3 )
    *a3 = nLengthNeeded;
LABEL_22:
  CoTaskMemFree(v6);
  v12 = LastFailureAsHRESULT;
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)FileW);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT);
  return v12;
}

```

## disassembly

```asm
0x18008cef8  push    rbp
0x18008cefa  push    rbx
0x18008cefb  push    rsi
0x18008cefc  push    rdi
0x18008cefd  push    r14
0x18008ceff  push    r15
0x18008cf01  lea     rbp, [rsp-2Fh]
0x18008cf06  sub     rsp, 88h
0x18008cf0d  mov     r14, r8
0x18008cf10  mov     rsi, rdx
0x18008cf13  mov     r15, rcx
0x18008cf16  lea     rdx, aGetfilesecurit; "GetFileSecurityUtility"
0x18008cf1d  mov     r8d, 114h; unsigned __int16
0x18008cf23  lea     rcx, [rbp+57h+var_70]; this
0x18008cf27  mov     r9d, 1; unsigned __int16
0x18008cf2d  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18008cf32  xor     edi, edi
0x18008cf34  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18008cf38  mov     [rbp+57h+nLengthNeeded], edi
0x18008cf3b  test    r14, r14
0x18008cf3e  jz      short loc_18008CF43
0x18008cf40  mov     [r14], edi
0x18008cf43  test    rsi, rsi
0x18008cf46  jz      short loc_18008CF4B
0x18008cf48  mov     [rsi], rdi
0x18008cf4b  mov     eax, 11Fh
0x18008cf50  test    r15, r15
0x18008cf53  jnz     short loc_18008CF65
0x18008cf55  mov     [rbp+57h+var_70], 80070057h
0x18008cf5c  mov     [rbp+57h+var_6A], ax
0x18008cf60  jmp     loc_18008D100
0x18008cf65  mov     [rbp+57h+var_6C], ax
0x18008cf69  mov     eax, 120h
0x18008cf6e  test    rsi, rsi
0x18008cf71  jz      short loc_18008CF55
0x18008cf73  xor     r9d, r9d; lpSecurityAttributes
0x18008cf76  mov     [rsp+0B0h+hTemplateFile], rdi; hTemplateFile
0x18008cf7b  mov     [rsp+0B0h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x18008cf83  mov     edx, 1020000h; dwDesiredAccess
0x18008cf88  mov     rcx, r15; lpFileName
0x18008cf8b  mov     [rbp+57h+var_70], edi
0x18008cf8e  mov     [rbp+57h+var_6C], ax
0x18008cf92  lea     r8d, [r9+1]; dwShareMode
0x18008cf96  mov     [rsp+0B0h+dwCreationDisposition], 3; dwCreationDisposition
0x18008cf9e  call    cs:__imp_CreateFileW
0x18008cfa5  nop     dword ptr [rax+rax+00h]
0x18008cfaa  mov     rbx, rax
0x18008cfad  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18008cfb1  jnz     short loc_18008CFC2
0x18008cfb3  call    GetLastFailureAsHRESULT
0x18008cfb8  mov     [rbp+57h+var_70], eax
0x18008cfbb  mov     eax, 123h
0x18008cfc0  jmp     short loc_18008CF5C
0x18008cfc2  mov     eax, 123h
0x18008cfc7  mov     [rbp+57h+var_70], edi
0x18008cfca  mov     r15d, 400h
0x18008cfd0  mov     [rbp+57h+var_6C], ax
0x18008cfd4  mov     ecx, r15d; cb
0x18008cfd7  call    cs:__imp_CoTaskMemAlloc
0x18008cfde  nop     dword ptr [rax+rax+00h]
0x18008cfe3  mov     rdi, rax
0x18008cfe6  test    rax, rax
0x18008cfe9  mov     eax, 126h
0x18008cfee  jnz     short loc_18008CFFC
0x18008cff0  mov     [rbp+57h+var_70], 8007000Eh
0x18008cff7  jmp     loc_18008CF5C
0x18008cffc  mov     [rbp+57h+var_6C], ax
0x18008d000  mov     r9d, r15d; nLength
0x18008d003  lea     rax, [rbp+57h+nLengthNeeded]
0x18008d007  mov     [rbp+57h+var_70], 0
0x18008d00e  mov     r8, rdi; pSecurityDescriptor
0x18008d011  mov     qword ptr [rsp+0B0h+dwCreationDisposition], rax; lpnLengthNeeded
0x18008d016  mov     edx, 1Fh; RequestedInformation
0x18008d01b  mov     rcx, rbx; Handle
0x18008d01e  call    cs:__imp_GetKernelObjectSecurity
0x18008d025  nop     dword ptr [rax+rax+00h]
0x18008d02a  test    eax, eax
0x18008d02c  jnz     loc_18008D0E0
0x18008d032  call    cs:__imp_GetLastError
0x18008d039  nop     dword ptr [rax+rax+00h]
0x18008d03e  cmp     eax, 7Ah ; 'z'
0x18008d041  jnz     loc_18008D0CE
0x18008d047  mov     eax, 12Ch
0x18008d04c  cmp     [rbp+57h+nLengthNeeded], r15d
0x18008d050  ja      short loc_18008D05E
0x18008d052  mov     [rbp+57h+var_70], 80004005h
0x18008d059  jmp     loc_18008CF5C
0x18008d05e  mov     rcx, rdi; pv
0x18008d061  mov     [rbp+57h+var_70], 0
0x18008d068  mov     [rbp+57h+var_6C], ax
0x18008d06c  call    cs:__imp_CoTaskMemFree
0x18008d073  nop     dword ptr [rax+rax+00h]
0x18008d078  mov     r15d, [rbp+57h+nLengthNeeded]
0x18008d07c  mov     ecx, r15d; cb
0x18008d07f  call    cs:__imp_CoTaskMemAlloc
0x18008d086  nop     dword ptr [rax+rax+00h]
0x18008d08b  mov     rdi, rax
0x18008d08e  test    rax, rax
0x18008d091  mov     eax, 132h
0x18008d096  jz      loc_18008CFF0
0x18008d09c  mov     [rbp+57h+var_6C], ax
0x18008d0a0  mov     r9d, r15d; nLength
0x18008d0a3  lea     rax, [rbp+57h+nLengthNeeded]
0x18008d0a7  mov     [rbp+57h+var_70], 0
0x18008d0ae  mov     r8, rdi; pSecurityDescriptor
0x18008d0b1  mov     qword ptr [rsp+0B0h+dwCreationDisposition], rax; lpnLengthNeeded
0x18008d0b6  mov     edx, 1Fh; RequestedInformation
0x18008d0bb  mov     rcx, rbx; Handle
0x18008d0be  call    cs:__imp_GetKernelObjectSecurity
0x18008d0c5  nop     dword ptr [rax+rax+00h]
0x18008d0ca  test    eax, eax
0x18008d0cc  jnz     short loc_18008D0E0
0x18008d0ce  call    GetLastFailureAsHRESULT
0x18008d0d3  mov     [rbp+57h+var_70], eax
0x18008d0d6  mov     eax, 136h
0x18008d0db  jmp     loc_18008CF5C
0x18008d0e0  mov     [rsi], rdi
0x18008d0e3  mov     eax, 136h
0x18008d0e8  xor     edi, edi
0x18008d0ea  mov     [rbp+57h+var_70], 0
0x18008d0f1  mov     [rbp+57h+var_6C], ax
0x18008d0f5  test    r14, r14
0x18008d0f8  jz      short loc_18008D100
0x18008d0fa  mov     eax, [rbp+57h+nLengthNeeded]
0x18008d0fd  mov     [r14], eax
0x18008d100  mov     rcx, rdi; pv
0x18008d103  call    cs:__imp_CoTaskMemFree
0x18008d10a  nop     dword ptr [rax+rax+00h]
0x18008d10f  mov     edi, [rbp+57h+var_70]
0x18008d112  lea     rcx, [rbx-1]
0x18008d116  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18008d11a  ja      short loc_18008D12B
0x18008d11c  mov     rcx, rbx; hObject
0x18008d11f  call    cs:__imp_CloseHandle
0x18008d126  nop     dword ptr [rax+rax+00h]
0x18008d12b  lea     rcx, [rbp+57h+var_70]; this
0x18008d12f  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18008d134  mov     eax, edi
0x18008d136  add     rsp, 88h
0x18008d13d  pop     r15
0x18008d13f  pop     r14
0x18008d141  pop     rdi
0x18008d142  pop     rsi
0x18008d143  pop     rbx
0x18008d144  pop     rbp
0x18008d145  retn
```
