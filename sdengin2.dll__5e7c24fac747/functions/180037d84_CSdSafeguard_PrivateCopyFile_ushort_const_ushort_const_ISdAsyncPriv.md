# CSdSafeguard::_PrivateCopyFile(ushort const *,ushort const *,ISdAsyncPriv *)

- ea: `0x180037d84`
- end: `0x180038017`
- name: `?_PrivateCopyFile@CSdSafeguard@@AEAAJPEBG0PEAUISdAsyncPriv@@@Z`
- size: `659`
- prototype: `__int64 __fastcall(CSdSafeguard *__hidden this, LPCWSTR lpExistingFileName, const unsigned __int16 *, struct ISdAsyncPriv *)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180036470`
- `0x180036730`

## callees

- `0x180003b60`
- `0x180014394`
- `0x180037a20`
- `0x180037d84`
- `0x18006fe84`
- `0x18006ff8c`
- `0x180086ef8`
- `0x18008f5d0`

## import_xrefs

- `KERNEL32!FlushFileBuffers` at `0x180037efc`
- `KERNEL32!FlushFileBuffers` at `0x180037efc`
- `KERNEL32!CopyFileExW` at `0x180037e57`
- `KERNEL32!CopyFileExW` at `0x180037e57`
- `KERNEL32!CreateFileW` at `0x180037eea`
- `KERNEL32!CreateFileW` at `0x180037eea`
- `KERNEL32!GetLastError` at `0x180037e61`
- `KERNEL32!GetLastError` at `0x180037f2d`
- `KERNEL32!GetLastError` at `0x180037e61`
- `KERNEL32!GetLastError` at `0x180037f2d`
- `KERNEL32!CloseHandle` at `0x180037ff2`
- `KERNEL32!CloseHandle` at `0x180037ff2`

## string_xrefs

- `0x180037db5`: `CSdSafeguard::_PrivateCopyFile`

## pseudocode

```c
__int64 __fastcall CSdSafeguard::_PrivateCopyFile(
        CSdSafeguard *this,
        LPCWSTR lpExistingFileName,
        const unsigned __int16 *a3,
        struct ISdAsyncPriv *a4)
{
  __int64 v8; // rbx
  __int16 v9; // ax
  signed int v10; // edi
  unsigned int v11; // r12d
  unsigned int i; // r14d
  DWORD LastError; // eax
  CSdSafeguard *v14; // rcx
  bool v15; // sf
  HANDLE FileW; // rax
  signed int v17; // eax
  signed int v18; // edi
  unsigned int v19; // edi
  int IsCopyFileErrorRetryable; // [rsp+40h] [rbp-29h] BYREF
  __int16 v22; // [rsp+44h] [rbp-25h]
  __int16 v23; // [rsp+46h] [rbp-23h]

  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&IsCopyFileErrorRetryable,
    "CSdSafeguard::_PrivateCopyFile",
    0x38Du,
    1u);
  v8 = -1;
  v9 = 917;
  if ( !lpExistingFileName || (v22 = 917, v9 = 918, !a3) || (v22 = 918, v9 = 919, !a4) )
  {
    IsCopyFileErrorRetryable = -2147024809;
    goto LABEL_34;
  }
  v10 = 0;
  IsCopyFileErrorRetryable = 0;
  v22 = 919;
  ATL::CComPtr<ISdBackupSetRecord>::operator=((char *)this + 104, a4);
  *((_QWORD *)this + 12) = 0;
  *((_DWORD *)this + 28) = 0;
  v11 = 2 - ((unsigned int)SdIsPathUNC(a3) != 0);
  for ( i = 0; i < v11; ++i )
  {
    if ( CopyFileExW(lpExistingFileName, a3, CSdSafeguard::_StaticCopyProgressRoutine, this, 0, 8u) )
      goto LABEL_16;
    LastError = GetLastError();
    v10 = LastError;
    if ( LastError == 1235 )
    {
      IsCopyFileErrorRetryable = *((_DWORD *)this + 28);
      v9 = 969;
      v15 = IsCopyFileErrorRetryable < 0;
    }
    else
    {
      IsCopyFileErrorRetryable = CSdSafeguard::_IsCopyFileErrorRetryable(v14, LastError);
      v15 = IsCopyFileErrorRetryable < 0;
      v9 = 973;
    }
    if ( v15 )
      goto LABEL_34;
    v22 = v9;
  }
  if ( v10 )
  {
    if ( v10 > 0 )
      v10 = (unsigned __int16)v10 | 0x80070000;
    IsCopyFileErrorRetryable = v10;
    v9 = 983;
    goto LABEL_34;
  }
LABEL_16:
  FileW = CreateFileW(a3, 0x40000000u, 3u, 0, 3u, 0x80u, 0);
  v8 = (__int64)FileW;
  if ( FileW != (HANDLE)-1LL )
  {
    if ( !FlushFileBuffers(FileW) )
    {
      IsCopyFileErrorRetryable = GetLastFailureAsHRESULT();
      v9 = 1000;
      goto LABEL_34;
    }
    IsCopyFileErrorRetryable = 0;
    v9 = 1000;
    goto LABEL_20;
  }
  v17 = GetLastError();
  v18 = v17;
  if ( v17 > 0 )
    v18 = (unsigned __int16)v17 | 0x80070000;
  if ( v18 != -2147024864 && v18 != -2147024891 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        25,
        (unsigned int)WPP_2818ddfe77cb3e37cabd910f13877d81_Traceguids,
        (_DWORD)a3,
        v18);
    IsCopyFileErrorRetryable = v18;
    v9 = 1013;
    if ( v18 >= 0 )
    {
LABEL_20:
      v22 = v9;
      goto LABEL_35;
    }
LABEL_34:
    v23 = v9;
    goto LABEL_35;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      24,
      (unsigned int)WPP_2818ddfe77cb3e37cabd910f13877d81_Traceguids,
      (_DWORD)a3,
      v18);
LABEL_35:
  ATL::CComPtr<ISdBackupSetRecord>::operator=((char *)this + 104, 0);
  v19 = IsCopyFileErrorRetryable;
  if ( (unsigned __int64)(v8 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)v8);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&IsCopyFileErrorRetryable);
  return v19;
}

```

## disassembly

```asm
0x180037d84  push    rbp
0x180037d86  push    rbx
0x180037d87  push    rsi
0x180037d88  push    rdi
0x180037d89  push    r12
0x180037d8b  push    r13
0x180037d8d  push    r14
0x180037d8f  push    r15
0x180037d91  lea     rbp, [rsp-1Fh]
0x180037d96  sub     rsp, 88h
0x180037d9d  mov     r14, r9
0x180037da0  mov     rsi, r8
0x180037da3  mov     r13, rdx
0x180037da6  mov     r15, rcx
0x180037da9  mov     r9d, 1; unsigned __int16
0x180037daf  mov     r8d, 38Dh; unsigned __int16
0x180037db5  lea     rdx, aCsdsafeguardPr; "CSdSafeguard::_PrivateCopyFile"
0x180037dbc  lea     rcx, [rbp+57h+var_80]; this
0x180037dc0  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180037dc5  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180037dc9  xor     r12d, r12d
0x180037dcc  mov     eax, 395h
0x180037dd1  test    r13, r13
0x180037dd4  jz      loc_180037FCC
0x180037dda  mov     [rbp+57h+var_7C], ax
0x180037dde  mov     eax, 396h
0x180037de3  test    rsi, rsi
0x180037de6  jz      loc_180037FCC
0x180037dec  mov     [rbp+57h+var_7C], ax
0x180037df0  mov     eax, 397h
0x180037df5  test    r14, r14
0x180037df8  jz      loc_180037FCC
0x180037dfe  mov     edi, r12d
0x180037e01  mov     [rbp+57h+var_80], r12d
0x180037e05  mov     [rbp+57h+var_7C], ax
0x180037e09  lea     rcx, [r15+68h]
0x180037e0d  mov     rdx, r14
0x180037e10  call    ??4?$CComPtr@UISdBackupSetRecord@@@ATL@@QEAAPEAUISdBackupSetRecord@@PEAU2@@Z; ATL::CComPtr<ISdBackupSetRecord>::operator=(ISdBackupSetRecord *)
0x180037e15  mov     [r15+60h], r12
0x180037e19  mov     [r15+70h], r12d
0x180037e1d  mov     rcx, rsi; unsigned __int16 *
0x180037e20  call    ?SdIsPathUNC@@YAJPEBG@Z; SdIsPathUNC(ushort const *)
0x180037e25  neg     eax
0x180037e27  sbb     r12d, r12d
0x180037e2a  add     r12d, 2
0x180037e2e  xor     r14d, r14d
0x180037e31  cmp     r14d, r12d
0x180037e34  jnb     short loc_180037EA0
0x180037e36  mov     [rsp+0C0h+dwCopyFlags], 8; dwCopyFlags
0x180037e3e  mov     [rsp+0C0h+pbCancel], 0; pbCancel
0x180037e47  mov     r9, r15; lpData
0x180037e4a  lea     r8, ?_StaticCopyProgressRoutine@CSdSafeguard@@CAKT_LARGE_INTEGER@@000KKPEAX11@Z; lpProgressRoutine
0x180037e51  mov     rdx, rsi; lpNewFileName
0x180037e54  mov     rcx, r13; lpExistingFileName
0x180037e57  call    cs:__imp_CopyFileExW
0x180037e5d  test    eax, eax
0x180037e5f  jnz     short loc_180037EC3
0x180037e61  call    cs:__imp_GetLastError
0x180037e67  mov     edi, eax
0x180037e69  cmp     eax, 4D3h
0x180037e6e  jnz     short loc_180037E80
0x180037e70  mov     ecx, [r15+70h]
0x180037e74  mov     [rbp+57h+var_80], ecx
0x180037e77  mov     eax, 3C9h
0x180037e7c  test    ecx, ecx
0x180037e7e  jmp     short loc_180037E91
0x180037e80  mov     edx, eax; unsigned int
0x180037e82  call    ?_IsCopyFileErrorRetryable@CSdSafeguard@@AEAAJK@Z; CSdSafeguard::_IsCopyFileErrorRetryable(ulong)
0x180037e87  mov     [rbp+57h+var_80], eax
0x180037e8a  test    eax, eax
0x180037e8c  mov     eax, 3CDh
0x180037e91  js      loc_180037FD3
0x180037e97  mov     [rbp+57h+var_7C], ax
0x180037e9b  inc     r14d
0x180037e9e  jmp     short loc_180037E31
0x180037ea0  test    edi, edi
0x180037ea2  jz      short loc_180037EC3
0x180037ea4  jle     short loc_180037EAF
0x180037ea6  movzx   edi, di
0x180037ea9  or      edi, 80070000h
0x180037eaf  mov     [rbp+57h+var_80], edi
0x180037eb2  mov     eax, 3D7h
0x180037eb7  test    edi, edi
0x180037eb9  js      loc_180037FD3
0x180037ebf  mov     [rbp+57h+var_7C], ax
0x180037ec3  mov     [rsp+0C0h+hTemplateFile], 0; hTemplateFile
0x180037ecc  mov     [rsp+0C0h+dwCopyFlags], 80h; dwFlagsAndAttributes
0x180037ed4  mov     r8d, 3; dwShareMode
0x180037eda  mov     dword ptr [rsp+0C0h+pbCancel], r8d; dwCreationDisposition
0x180037edf  xor     r9d, r9d; lpSecurityAttributes
0x180037ee2  mov     edx, 40000000h; dwDesiredAccess
0x180037ee7  mov     rcx, rsi; lpFileName
0x180037eea  call    cs:__imp_CreateFileW
0x180037ef0  mov     rbx, rax
0x180037ef3  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180037ef7  jz      short loc_180037F2D
0x180037ef9  mov     rcx, rax; hFile
0x180037efc  call    cs:__imp_FlushFileBuffers
0x180037f02  test    eax, eax
0x180037f04  jnz     short loc_180037F18
0x180037f06  call    GetLastFailureAsHRESULT
0x180037f0b  mov     [rbp+57h+var_80], eax
0x180037f0e  mov     eax, 3E8h
0x180037f13  jmp     loc_180037FD3
0x180037f18  mov     [rbp+57h+var_80], 0
0x180037f1f  mov     eax, 3E8h
0x180037f24  mov     [rbp+57h+var_7C], ax
0x180037f28  jmp     loc_180037FD7
0x180037f2d  call    cs:__imp_GetLastError
0x180037f33  mov     edi, eax
0x180037f35  test    eax, eax
0x180037f37  jle     short loc_180037F42
0x180037f39  movzx   edi, ax
0x180037f3c  or      edi, 80070000h
0x180037f42  cmp     edi, 80070020h
0x180037f48  jz      short loc_180037F95
0x180037f4a  cmp     edi, 80070005h
0x180037f50  jz      short loc_180037F95
0x180037f52  lea     rax, WPP_GLOBAL_Control
0x180037f59  mov     rcx, cs:WPP_GLOBAL_Control
0x180037f60  cmp     rcx, rax
0x180037f63  jz      short loc_180037F87
0x180037f65  test    byte ptr [rcx+1Ch], 20h
0x180037f69  jz      short loc_180037F87
0x180037f6b  mov     edx, 19h
0x180037f70  mov     dword ptr [rsp+0C0h+pbCancel], edi
0x180037f74  mov     r9, rsi
0x180037f77  lea     r8, WPP_2818ddfe77cb3e37cabd910f13877d81_Traceguids
0x180037f7e  mov     rcx, [rcx+10h]
0x180037f82  call    WPP_SF_Sd
0x180037f87  mov     [rbp+57h+var_80], edi
0x180037f8a  mov     eax, 3F5h
0x180037f8f  test    edi, edi
0x180037f91  js      short loc_180037FD3
0x180037f93  jmp     short loc_180037F24
0x180037f95  lea     rax, WPP_GLOBAL_Control
0x180037f9c  mov     rcx, cs:WPP_GLOBAL_Control
0x180037fa3  cmp     rcx, rax
0x180037fa6  jz      short loc_180037FD7
0x180037fa8  test    byte ptr [rcx+1Ch], 20h
0x180037fac  jz      short loc_180037FD7
0x180037fae  mov     edx, 18h
0x180037fb3  mov     dword ptr [rsp+0C0h+pbCancel], edi
0x180037fb7  mov     r9, rsi
0x180037fba  lea     r8, WPP_2818ddfe77cb3e37cabd910f13877d81_Traceguids
0x180037fc1  mov     rcx, [rcx+10h]
0x180037fc5  call    WPP_SF_Sd
0x180037fca  jmp     short loc_180037FD7
0x180037fcc  mov     [rbp+57h+var_80], 80070057h
0x180037fd3  mov     [rbp+57h+var_7A], ax
0x180037fd7  lea     rcx, [r15+68h]
0x180037fdb  xor     edx, edx
0x180037fdd  call    ??4?$CComPtr@UISdBackupSetRecord@@@ATL@@QEAAPEAUISdBackupSetRecord@@PEAU2@@Z; ATL::CComPtr<ISdBackupSetRecord>::operator=(ISdBackupSetRecord *)
0x180037fe2  mov     edi, [rbp+57h+var_80]
0x180037fe5  lea     rcx, [rbx-1]
0x180037fe9  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180037fed  ja      short loc_180037FF8
0x180037fef  mov     rcx, rbx; hObject
0x180037ff2  call    cs:__imp_CloseHandle
0x180037ff8  lea     rcx, [rbp+57h+var_80]; this
0x180037ffc  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180038001  mov     eax, edi
0x180038003  add     rsp, 88h
0x18003800a  pop     r15
0x18003800c  pop     r14
0x18003800e  pop     r13
0x180038010  pop     r12
0x180038012  pop     rdi
0x180038013  pop     rsi
0x180038014  pop     rbx
0x180038015  pop     rbp
0x180038016  retn
```
