# GetFileSecurityUtility(ushort const *,_SECURITY_DESCRIPTOR * *,ulong *)

- ea: `0x1800893f0`
- end: `0x180089604`
- name: `?GetFileSecurityUtility@@YAJPEBGPEAPEAU_SECURITY_DESCRIPTOR@@PEAK@Z`
- size: `532`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, struct _SECURITY_DESCRIPTOR **, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18001d298`

## callees

- `0x18006fe84`
- `0x18006ff8c`
- `0x1800893f0`
- `0x18008f5d0`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x180089496`
- `KERNEL32!CreateFileW` at `0x180089496`
- `KERNEL32!GetLastError` at `0x180089518`
- `KERNEL32!GetLastError` at `0x180089518`
- `KERNEL32!CloseHandle` at `0x1800895e3`
- `KERNEL32!CloseHandle` at `0x1800895e3`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x18008950a`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x18008958e`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x18008950a`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x18008958e`
- `ole32!CoTaskMemFree` at `0x180089548`
- `ole32!CoTaskMemFree` at `0x1800895cd`
- `ole32!CoTaskMemFree` at `0x180089548`
- `ole32!CoTaskMemFree` at `0x1800895cd`
- `ole32!CoTaskMemAlloc` at `0x1800894c9`
- `ole32!CoTaskMemAlloc` at `0x180089555`
- `ole32!CoTaskMemAlloc` at `0x1800894c9`
- `ole32!CoTaskMemAlloc` at `0x180089555`

## string_xrefs

- `0x18008940e`: `GetFileSecurityUtility`

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

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT, "GetFileSecurityUtility", 276, 1);
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
0x1800893f0  push    rbp
0x1800893f2  push    rbx
0x1800893f3  push    rsi
0x1800893f4  push    rdi
0x1800893f5  push    r14
0x1800893f7  push    r15
0x1800893f9  lea     rbp, [rsp-2Fh]
0x1800893fe  sub     rsp, 88h
0x180089405  mov     r14, r8
0x180089408  mov     rsi, rdx
0x18008940b  mov     r15, rcx
0x18008940e  lea     rdx, aGetfilesecurit; "GetFileSecurityUtility"
0x180089415  mov     r8d, 114h; unsigned __int16
0x18008941b  lea     rcx, [rbp+57h+var_70]; this
0x18008941f  mov     r9d, 1; unsigned __int16
0x180089425  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18008942a  xor     edi, edi
0x18008942c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180089430  mov     [rbp+57h+nLengthNeeded], edi
0x180089433  test    r14, r14
0x180089436  jz      short loc_18008943B
0x180089438  mov     [r14], edi
0x18008943b  test    rsi, rsi
0x18008943e  jz      short loc_180089443
0x180089440  mov     [rsi], rdi
0x180089443  mov     eax, 11Fh
0x180089448  test    r15, r15
0x18008944b  jnz     short loc_18008945D
0x18008944d  mov     [rbp+57h+var_70], 80070057h
0x180089454  mov     [rbp+57h+var_6A], ax
0x180089458  jmp     loc_1800895CA
0x18008945d  mov     [rbp+57h+var_6C], ax
0x180089461  mov     eax, 120h
0x180089466  test    rsi, rsi
0x180089469  jz      short loc_18008944D
0x18008946b  xor     r9d, r9d; lpSecurityAttributes
0x18008946e  mov     [rsp+0B0h+hTemplateFile], rdi; hTemplateFile
0x180089473  mov     [rsp+0B0h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x18008947b  mov     edx, 1020000h; dwDesiredAccess
0x180089480  mov     rcx, r15; lpFileName
0x180089483  mov     [rbp+57h+var_70], edi
0x180089486  mov     [rbp+57h+var_6C], ax
0x18008948a  lea     r8d, [r9+1]; dwShareMode
0x18008948e  mov     [rsp+0B0h+dwCreationDisposition], 3; dwCreationDisposition
0x180089496  call    cs:__imp_CreateFileW
0x18008949c  mov     rbx, rax
0x18008949f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800894a3  jnz     short loc_1800894B4
0x1800894a5  call    GetLastFailureAsHRESULT
0x1800894aa  mov     [rbp+57h+var_70], eax
0x1800894ad  mov     eax, 123h
0x1800894b2  jmp     short loc_180089454
0x1800894b4  mov     eax, 123h
0x1800894b9  mov     [rbp+57h+var_70], edi
0x1800894bc  mov     r15d, 400h
0x1800894c2  mov     [rbp+57h+var_6C], ax
0x1800894c6  mov     ecx, r15d; cb
0x1800894c9  call    cs:__imp_CoTaskMemAlloc
0x1800894cf  mov     rdi, rax
0x1800894d2  test    rax, rax
0x1800894d5  mov     eax, 126h
0x1800894da  jnz     short loc_1800894E8
0x1800894dc  mov     [rbp+57h+var_70], 8007000Eh
0x1800894e3  jmp     loc_180089454
0x1800894e8  mov     [rbp+57h+var_6C], ax
0x1800894ec  mov     r9d, r15d; nLength
0x1800894ef  lea     rax, [rbp+57h+nLengthNeeded]
0x1800894f3  mov     [rbp+57h+var_70], 0
0x1800894fa  mov     r8, rdi; pSecurityDescriptor
0x1800894fd  mov     qword ptr [rsp+0B0h+dwCreationDisposition], rax; lpnLengthNeeded
0x180089502  mov     edx, 1Fh; RequestedInformation
0x180089507  mov     rcx, rbx; Handle
0x18008950a  call    cs:__imp_GetKernelObjectSecurity
0x180089510  test    eax, eax
0x180089512  jnz     loc_1800895AA
0x180089518  call    cs:__imp_GetLastError
0x18008951e  cmp     eax, 7Ah ; 'z'
0x180089521  jnz     short loc_180089598
0x180089523  mov     eax, 12Ch
0x180089528  cmp     [rbp+57h+nLengthNeeded], r15d
0x18008952c  ja      short loc_18008953A
0x18008952e  mov     [rbp+57h+var_70], 80004005h
0x180089535  jmp     loc_180089454
0x18008953a  mov     rcx, rdi; pv
0x18008953d  mov     [rbp+57h+var_70], 0
0x180089544  mov     [rbp+57h+var_6C], ax
0x180089548  call    cs:__imp_CoTaskMemFree
0x18008954e  mov     r15d, [rbp+57h+nLengthNeeded]
0x180089552  mov     ecx, r15d; cb
0x180089555  call    cs:__imp_CoTaskMemAlloc
0x18008955b  mov     rdi, rax
0x18008955e  test    rax, rax
0x180089561  mov     eax, 132h
0x180089566  jz      loc_1800894DC
0x18008956c  mov     [rbp+57h+var_6C], ax
0x180089570  mov     r9d, r15d; nLength
0x180089573  lea     rax, [rbp+57h+nLengthNeeded]
0x180089577  mov     [rbp+57h+var_70], 0
0x18008957e  mov     r8, rdi; pSecurityDescriptor
0x180089581  mov     qword ptr [rsp+0B0h+dwCreationDisposition], rax; lpnLengthNeeded
0x180089586  mov     edx, 1Fh; RequestedInformation
0x18008958b  mov     rcx, rbx; Handle
0x18008958e  call    cs:__imp_GetKernelObjectSecurity
0x180089594  test    eax, eax
0x180089596  jnz     short loc_1800895AA
0x180089598  call    GetLastFailureAsHRESULT
0x18008959d  mov     [rbp+57h+var_70], eax
0x1800895a0  mov     eax, 136h
0x1800895a5  jmp     loc_180089454
0x1800895aa  mov     [rsi], rdi
0x1800895ad  mov     eax, 136h
0x1800895b2  xor     edi, edi
0x1800895b4  mov     [rbp+57h+var_70], 0
0x1800895bb  mov     [rbp+57h+var_6C], ax
0x1800895bf  test    r14, r14
0x1800895c2  jz      short loc_1800895CA
0x1800895c4  mov     eax, [rbp+57h+nLengthNeeded]
0x1800895c7  mov     [r14], eax
0x1800895ca  mov     rcx, rdi; pv
0x1800895cd  call    cs:__imp_CoTaskMemFree
0x1800895d3  mov     edi, [rbp+57h+var_70]
0x1800895d6  lea     rcx, [rbx-1]
0x1800895da  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x1800895de  ja      short loc_1800895E9
0x1800895e0  mov     rcx, rbx; hObject
0x1800895e3  call    cs:__imp_CloseHandle
0x1800895e9  lea     rcx, [rbp+57h+var_70]; this
0x1800895ed  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1800895f2  mov     eax, edi
0x1800895f4  add     rsp, 88h
0x1800895fb  pop     r15
0x1800895fd  pop     r14
0x1800895ff  pop     rdi
0x180089600  pop     rsi
0x180089601  pop     rbx
0x180089602  pop     rbp
0x180089603  retn
```
