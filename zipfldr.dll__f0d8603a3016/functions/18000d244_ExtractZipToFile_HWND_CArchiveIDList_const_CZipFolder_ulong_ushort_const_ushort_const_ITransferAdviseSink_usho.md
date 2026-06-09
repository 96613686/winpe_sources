# ExtractZipToFile(HWND__ *,CArchiveIDList const *,CZipFolder *,ulong,ushort const *,ushort const *,ITransferAdviseSink *,ushort *,ulong)

- ea: `0x18000d244`
- end: `0x18000d4de`
- name: `?ExtractZipToFile@@YAJPEAUHWND__@@PEBVCArchiveIDList@@PEAVCZipFolder@@KPEBG3PEAUITransferAdviseSink@@PEAGK@Z`
- size: `666`
- prototype: `__int64 __fastcall(HWND, const struct CArchiveIDList *, struct CZipFolder *, unsigned int, unsigned __int16 *, const unsigned __int16 *, struct ITransferAdviseSink *, unsigned __int16 *)`
- caller_count: `3`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000cfd0`
- `0x1800284ec`
- `0x180047670`

## callees

- `0x18000d244`
- `0x18000f370`
- `0x180010c30`
- `0x180010d20`
- `0x18001f204`
- `0x180027a40`
- `0x18002b0b0`
- `0x180036f50`
- `0x180037958`
- `0x180043ab0`
- `0x180043e4c`
- `0x180071010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000d40c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000d40c`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000d441`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000d441`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000d41c`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000d41c`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000d436`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000d436`

## pseudocode

```c
// Hidden C++ exception states: #wind=7 #try_helpers=1
__int64 __fastcall ExtractZipToFile(
        HWND a1,
        const struct CArchiveIDList *a2,
        struct CZipFolder *a3,
        unsigned int a4,
        unsigned __int16 *a5,
        const unsigned __int16 *a6,
        struct ITransferAdviseSink *a7,
        unsigned __int16 *a8)
{
  int appended; // ebx
  const WCHAR *v12; // r9
  ASSOCKEY v13; // r15d
  const unsigned __int16 *v14; // r14
  int v15; // eax
  struct IUnknown *v16; // rdx
  CTempFileNameArray *v17; // rcx
  int v18; // edi
  DWORD FileAttributesW; // eax
  CTempFileNameArray *v20; // rcx
  void *v21; // rdx
  unsigned int v22; // r8d
  const char *v23; // r9
  struct ITransferAdviseSink *v24; // rcx
  int (*v26)(const unsigned __int16 *, unsigned __int64, unsigned __int64, int, void *); // [rsp+38h] [rbp-C8h]
  HWND v27; // [rsp+58h] [rbp-A8h] BYREF
  struct ITransferAdviseSink *v28; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR String2[260]; // [rsp+68h] [rbp-98h] BYREF
  WCHAR String1[264]; // [rsp+270h] [rbp+170h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4C8h] [rbp+3C8h]

  v27 = a1;
  *a8 = 0;
  if ( (*((_BYTE *)a2 + 32) & 0x10) != 0 )
    return (unsigned int)-2147467259;
  appended = StringCchCopyW(String1, 0x104u, a5);
  if ( appended >= 0 )
  {
    v13 = a4 & 1;
    appended = CArchiveIDList::AppendRelPathAndName(a2, v13, String1, v12);
    PathFixSeparators(String1);
    if ( appended >= 0 )
    {
      v28 = 0;
      memset_0(String2, 0, sizeof(String2));
      if ( a7 )
      {
        ((void (__fastcall *)(struct ITransferAdviseSink *))a7->lpVtbl->AddRef)(a7);
        v28 = a7;
      }
      v14 = (const unsigned __int16 *)((char *)a3 + 72);
      if ( (a4 & 8) != 0 )
        v15 = CArchiveIDList::ExtractFileByName(a2, v14, a5, v13, a4, a6, v27, v26, &v28);
      else
        v15 = CArchiveIDList::ExtractFileByIndex(a2, v14, a5, v13, a4, a6, v27, v26, &v28);
      appended = v15;
      v18 = a4 & 2;
      if ( v18 && (v15 == -2147024816 || v15 == -2147024864) )
        goto LABEL_25;
      if ( v15 )
      {
        LODWORD(v27) = 0;
        if ( (int)SHMapUrlToZone(v14, v16, 1u, (unsigned int *)&v27) >= 0
          && (unsigned int)v27 >= 3
          && CompareStringOrdinal(String1, -1, String2, -1, 1) != 2 )
        {
          FileAttributesW = GetFileAttributesW(String2);
          if ( FileAttributesW != -1 )
          {
            if ( (FileAttributesW & 1) != 0 )
              SetFileAttributesW(String2, FileAttributesW & 0xFFFFFFFE);
            if ( !DeleteFileW(String2) )
              wil::details::in1diag3::_Log_GetLastError(retaddr, v21, v22, v23);
          }
          if ( v18 )
            CTempFileNameArray::ReferenceTempFile(v20, a5, String2);
        }
        goto LABEL_27;
      }
      if ( v18 )
LABEL_25:
        CTempFileNameArray::ReferenceTempFile(v17, a5, String1);
      appended = StringCchCopyW(a8, 0x104u, String1);
LABEL_27:
      v24 = v28;
      if ( v28 )
      {
        v28 = 0;
        ((void (__fastcall *)(struct ITransferAdviseSink *))v24->lpVtbl->Release)(v24);
      }
    }
  }
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x18000d244  mov     [rsp-8+arg_18], rbx
0x18000d249  push    rbp
0x18000d24a  push    rsi
0x18000d24b  push    rdi
0x18000d24c  push    r12
0x18000d24e  push    r13
0x18000d250  push    r14
0x18000d252  push    r15
0x18000d254  lea     rbp, [rsp-390h]
0x18000d25c  sub     rsp, 490h
0x18000d263  mov     rax, cs:__security_cookie
0x18000d26a  xor     rax, rsp
0x18000d26d  mov     [rbp+3C0h+var_40], rax
0x18000d274  mov     rax, [rbp+3C0h+arg_28]
0x18000d27b  mov     edi, r9d
0x18000d27e  mov     r13, [rbp+3C0h+arg_38]
0x18000d285  mov     r14, r8
0x18000d288  mov     rsi, [rbp+3C0h+arg_20]
0x18000d28f  mov     r12, rdx
0x18000d292  mov     [rsp+4C0h+var_470], rax
0x18000d297  xor     eax, eax
0x18000d299  mov     [rsp+4C0h+var_468], rcx
0x18000d29e  mov     [r13+0], ax
0x18000d2a3  test    byte ptr [rdx+20h], 10h
0x18000d2a7  jz      short loc_18000D2B3
0x18000d2a9  mov     ebx, 80004005h
0x18000d2ae  jmp     loc_18000D4B2
0x18000d2b3  mov     r8, rsi; unsigned __int16 *
0x18000d2b6  lea     rcx, [rbp+3C0h+String1]; unsigned __int16 *
0x18000d2bd  mov     edx, 104h; unsigned __int64
0x18000d2c2  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000d2c7  mov     ebx, eax
0x18000d2c9  test    eax, eax
0x18000d2cb  js      loc_18000D4B2
0x18000d2d1  mov     r15d, edi
0x18000d2d4  lea     r8, [rbp+3C0h+String1]; unsigned __int16 *
0x18000d2db  and     r15d, 1
0x18000d2df  mov     rcx, r12; this
0x18000d2e2  mov     edx, r15d; int
0x18000d2e5  call    ?AppendRelPathAndName@CArchiveIDList@@QEBAJHPEAGI@Z; CArchiveIDList::AppendRelPathAndName(int,ushort *,uint)
0x18000d2ea  lea     rcx, [rbp+3C0h+String1]; unsigned __int16 *
0x18000d2f1  mov     ebx, eax
0x18000d2f3  call    ?PathFixSeparators@@YAXPEAG@Z; PathFixSeparators(ushort *)
0x18000d2f8  test    ebx, ebx
0x18000d2fa  js      loc_18000D4B2
0x18000d300  xor     edx, edx; Val
0x18000d302  mov     [rsp+4C0h+var_460], 0
0x18000d30b  mov     r8d, 208h; Size
0x18000d311  lea     rcx, [rsp+4C0h+String2]; void *
0x18000d316  call    memset_0
0x18000d31b  mov     rcx, [rsp+4C0h+var_460]
0x18000d320  mov     rbx, [rbp+3C0h+arg_30]
0x18000d327  cmp     rcx, rbx
0x18000d32a  jz      short loc_18000D35B
0x18000d32c  test    rbx, rbx
0x18000d32f  jz      short loc_18000D345
0x18000d331  mov     rax, [rbx]
0x18000d334  mov     rcx, rbx
0x18000d337  mov     rax, [rax+8]
0x18000d33b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d340  mov     rcx, [rsp+4C0h+var_460]
0x18000d345  mov     [rsp+4C0h+var_460], rbx
0x18000d34a  test    rcx, rcx
0x18000d34d  jz      short loc_18000D35B
0x18000d34f  mov     rax, [rcx]
0x18000d352  mov     rax, [rax+10h]
0x18000d356  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d35b  lea     rax, [rsp+4C0h+var_460]
0x18000d360  add     r14, 48h ; 'H'
0x18000d364  mov     [rsp+4C0h+var_480], rax; void *
0x18000d369  mov     r9d, r15d; int
0x18000d36c  mov     rax, [rsp+4C0h+var_468]
0x18000d371  mov     r8, rsi; unsigned __int16 *
0x18000d374  mov     [rsp+4C0h+var_490], rax; HWND
0x18000d379  mov     rdx, r14; unsigned __int16 *
0x18000d37c  mov     rax, [rsp+4C0h+var_470]
0x18000d381  mov     rcx, r12; this
0x18000d384  mov     [rsp+4C0h+var_498], rax; unsigned __int16 *
0x18000d389  mov     [rsp+4C0h+bIgnoreCase], edi; unsigned int
0x18000d38d  test    dil, 8
0x18000d391  jz      short loc_18000D39A
0x18000d393  call    ?ExtractFileByName@CArchiveIDList@@QEBAJPEBG0HK0PEAUHWND__@@P6AH0_K2JPEAX@Z3@Z; CArchiveIDList::ExtractFileByName(ushort const *,ushort const *,int,ulong,ushort const *,HWND__ *,int (*)(ushort const *,unsigned __int64,unsigned __int64,long,void *),void *)
0x18000d398  jmp     short loc_18000D39F
0x18000d39a  call    ?ExtractFileByIndex@CArchiveIDList@@QEBAJPEBG0HK0PEAUHWND__@@P6AH0_K2JPEAX@Z3@Z; CArchiveIDList::ExtractFileByIndex(ushort const *,ushort const *,int,ulong,ushort const *,HWND__ *,int (*)(ushort const *,unsigned __int64,unsigned __int64,long,void *),void *)
0x18000d39f  mov     ebx, eax
0x18000d3a1  and     edi, 2
0x18000d3a4  jz      short loc_18000D3BC
0x18000d3a6  cmp     eax, 80070050h
0x18000d3ab  jz      loc_18000D46E
0x18000d3b1  cmp     eax, 80070020h
0x18000d3b6  jz      loc_18000D46E
0x18000d3bc  test    ebx, ebx
0x18000d3be  jz      loc_18000D46A
0x18000d3c4  mov     r15d, 1
0x18000d3ca  mov     dword ptr [rsp+4C0h+var_468], 0
0x18000d3d2  mov     r8d, r15d; unsigned int
0x18000d3d5  lea     r9, [rsp+4C0h+var_468]; unsigned int *
0x18000d3da  mov     rcx, r14; unsigned __int16 *
0x18000d3dd  call    ?SHMapUrlToZone@@YAJPEBGPEAUIUnknown@@KPEAK@Z; SHMapUrlToZone(ushort const *,IUnknown *,ulong,ulong *)
0x18000d3e2  test    eax, eax
0x18000d3e4  js      loc_18000D493
0x18000d3ea  cmp     dword ptr [rsp+4C0h+var_468], 3
0x18000d3ef  jb      loc_18000D493
0x18000d3f5  or      edx, 0FFFFFFFFh; cchCount1
0x18000d3f8  mov     [rsp+4C0h+bIgnoreCase], r15d; bIgnoreCase
0x18000d3fd  mov     r9d, edx; cchCount2
0x18000d400  lea     r8, [rsp+4C0h+String2]; lpString2
0x18000d405  lea     rcx, [rbp+3C0h+String1]; lpString1
0x18000d40c  call    cs:__imp_CompareStringOrdinal
0x18000d412  cmp     eax, 2
0x18000d415  jz      short loc_18000D493
0x18000d417  lea     rcx, [rsp+4C0h+String2]; lpFileName
0x18000d41c  call    cs:__imp_GetFileAttributesW
0x18000d422  cmp     eax, 0FFFFFFFFh
0x18000d425  jz      short loc_18000D457
0x18000d427  test    r15b, al
0x18000d42a  jz      short loc_18000D43C
0x18000d42c  and     eax, 0FFFFFFFEh
0x18000d42f  lea     rcx, [rsp+4C0h+String2]; lpFileName
0x18000d434  mov     edx, eax; dwFileAttributes
0x18000d436  call    cs:__imp_SetFileAttributesW
0x18000d43c  lea     rcx, [rsp+4C0h+String2]; lpFileName
0x18000d441  call    cs:__imp_DeleteFileW
0x18000d447  test    eax, eax
0x18000d449  jnz     short loc_18000D457
0x18000d44b  mov     rcx, [rbp+3C8h]; this
0x18000d452  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18000d457  test    edi, edi
0x18000d459  jz      short loc_18000D493
0x18000d45b  lea     r8, [rsp+4C0h+String2]; unsigned __int16 *
0x18000d460  mov     rdx, rsi; unsigned __int16 *
0x18000d463  call    ?ReferenceTempFile@CTempFileNameArray@@QEAAXPEBG0@Z; CTempFileNameArray::ReferenceTempFile(ushort const *,ushort const *)
0x18000d468  jmp     short loc_18000D493
0x18000d46a  test    edi, edi
0x18000d46c  jz      short loc_18000D47D
0x18000d46e  lea     r8, [rbp+3C0h+String1]; unsigned __int16 *
0x18000d475  mov     rdx, rsi; unsigned __int16 *
0x18000d478  call    ?ReferenceTempFile@CTempFileNameArray@@QEAAXPEBG0@Z; CTempFileNameArray::ReferenceTempFile(ushort const *,ushort const *)
0x18000d47d  lea     r8, [rbp+3C0h+String1]; unsigned __int16 *
0x18000d484  mov     edx, 104h; unsigned __int64
0x18000d489  mov     rcx, r13; unsigned __int16 *
0x18000d48c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000d491  mov     ebx, eax
0x18000d493  mov     rcx, [rsp+4C0h+var_460]
0x18000d498  test    rcx, rcx
0x18000d49b  jz      short loc_18000D4B2
0x18000d49d  mov     [rsp+4C0h+var_460], 0
0x18000d4a6  mov     rax, [rcx]
0x18000d4a9  mov     rax, [rax+10h]
0x18000d4ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d4b2  mov     eax, ebx
0x18000d4b4  mov     rcx, [rbp+3C0h+var_40]
0x18000d4bb  xor     rcx, rsp; StackCookie
0x18000d4be  call    __security_check_cookie
0x18000d4c3  mov     rbx, [rsp+4C0h+arg_18]
0x18000d4cb  add     rsp, 490h
0x18000d4d2  pop     r15
0x18000d4d4  pop     r14
0x18000d4d6  pop     r13
0x18000d4d8  pop     r12
0x18000d4da  pop     rdi
0x18000d4db  pop     rsi
0x18000d4dc  pop     rbp
0x18000d4dd  retn
```
