# CDlpActionRecoverCrypto::WimIoCallbackOpenFile(ushort const *)

- ea: `0x18002f4a0`
- end: `0x18002f846`
- name: `?WimIoCallbackOpenFile@CDlpActionRecoverCrypto@@SAPEAXPEBG@Z`
- size: `934`
- prototype: `void *__fastcall(LPCWSTR lpFileName)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, registry_config`

## callees

- `0x180002898`
- `0x18000aba4`
- `0x18000ea20`
- `0x18001fd60`
- `0x18002f4a0`
- `0x18007ec76`
- `0x18007ec9a`
- `0x18007ed40`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18002f568`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18002f5fc`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18002f568`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18002f5fc`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002f504`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002f504`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002f63c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002f65d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002f799`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002f7ba`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002f7ef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002f810`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002f63c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002f65d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002f799`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002f7ba`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002f7ef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002f810`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002f64b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002f66c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002f7a8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002f7c9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002f7fe`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002f81f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002f64b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002f66c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002f7a8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002f7c9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002f7fe`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002f81f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f518`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f60a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f518`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f60a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f787`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f839`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f787`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f839`

## pseudocode

```c
__int64 __fastcall CDlpActionRecoverCrypto::WimIoCallbackOpenFile(LPCWSTR lpFileName)
{
  _DWORD *v1; // rsi
  char *v2; // rdi
  __int64 FileW; // rbx
  signed int LastError; // eax
  unsigned int v6; // edx
  int StringCch; // eax
  int v8; // r14d
  int Internal; // eax
  __int64 v10; // rcx
  signed int v11; // eax
  int v12; // edx
  HANDLE ProcessHeap; // rax
  HANDLE v14; // rax
  int v16; // eax
  int v17; // eax
  const void *v18; // r14
  unsigned int v19; // r15d
  int v20; // r12d
  BOOL v21; // r14d
  __int64 v22; // r14
  char *v23; // rcx
  HANDLE v24; // rax
  HANDLE v25; // rax
  HANDLE v26; // rax
  HANDLE v27; // rax
  int v28; // [rsp+40h] [rbp-C0h] BYREF
  _DWORD *v29; // [rsp+48h] [rbp-B8h]
  char *v30; // [rsp+50h] [rbp-B0h]
  WCHAR Buffer[520]; // [rsp+60h] [rbp-A0h] BYREF

  v1 = 0;
  v2 = 0;
  v29 = 0;
  v30 = 0;
  FileW = (__int64)CreateFileW(lpFileName, 0x80000000, 7u, 0, 3u, 0x8000000u, 0);
  if ( ((FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v6 = -2147467259;
    }
    FileW = -1;
    goto LABEL_20;
  }
  memset_0(Buffer, 0, sizeof(Buffer));
  if ( !GetFullPathNameW(lpFileName, 0x208u, Buffer, 0) )
    goto LABEL_16;
  v28 = 0;
  StringCch = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(Buffer, &v28);
  v8 = StringCch;
  if ( StringCch >= 0 )
  {
    Internal = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(Buffer);
    v8 = Internal;
    if ( Internal < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)Internal);
    v1 = v29;
  }
  else
  {
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)StringCch);
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v8);
  if ( v8 < 0 )
    goto LABEL_14;
  memset_0(Buffer, 0, sizeof(Buffer));
  if ( !GetFullPathNameW(*(LPCWSTR *)(g_spWimIoCallbackInstance + 552), 0x208u, Buffer, 0) )
  {
LABEL_16:
    v11 = GetLastError();
    v6 = v11;
    if ( v11 )
    {
      if ( v11 > 0 )
        v6 = (unsigned __int16)v11 | 0x80070000;
    }
    else
    {
      v6 = -2147467259;
    }
LABEL_20:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v6);
    if ( v12 >= 0 )
    {
LABEL_21:
      if ( v2 )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v2 - 4);
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
      }
      if ( v1 )
      {
        v14 = GetProcessHeap();
        HeapFree(v14, 0, v1 - 1);
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
      }
      return FileW;
    }
    goto LABEL_52;
  }
  v28 = 0;
  v16 = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(Buffer, &v28);
  v8 = v16;
  if ( v16 >= 0 )
  {
    v17 = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(Buffer);
    v8 = v17;
    if ( v17 < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v17);
    v2 = v30;
  }
  else
  {
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v16);
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v8);
  if ( v8 < 0 )
  {
LABEL_14:
    v10 = (unsigned int)v8;
LABEL_51:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v10);
LABEL_52:
    if ( v2 )
    {
      v26 = GetProcessHeap();
      HeapFree(v26, 0, v2 - 4);
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    }
    if ( v1 )
    {
      v27 = GetProcessHeap();
      HeapFree(v27, 0, v1 - 1);
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    }
    if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle((HANDLE)FileW);
    return 0;
  }
  if ( v2 )
  {
    v18 = v2;
    v19 = *((_DWORD *)v2 - 1);
  }
  else
  {
    v18 = 0;
    v19 = 0;
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  if ( v1 )
    v20 = *(v1 - 1);
  else
    v20 = 0;
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  v21 = v19 == v20 && memcmp_0(v18, v1, 2LL * v19) == 0;
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  if ( !v21 )
    goto LABEL_21;
  v22 = g_spWimIoCallbackInstance;
  if ( !g_spWimIoCallbackInstance )
  {
    v10 = 2147483658LL;
    goto LABEL_51;
  }
  v23 = *(char **)(g_spWimIoCallbackInstance + 656);
  if ( (unsigned __int64)(v23 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v23);
  *(_QWORD *)(v22 + 656) = FileW;
  if ( v2 )
  {
    v24 = GetProcessHeap();
    HeapFree(v24, 0, v2 - 4);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v1 )
  {
    v25 = GetProcessHeap();
    HeapFree(v25, 0, v1 - 1);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  return 2882342948LL;
}

```

## disassembly

```asm
0x18002f4a0  mov     [rsp-8+arg_8], rbx
0x18002f4a5  mov     [rsp-8+arg_10], rsi
0x18002f4aa  push    rbp
0x18002f4ab  push    rdi
0x18002f4ac  push    r12
0x18002f4ae  push    r14
0x18002f4b0  push    r15
0x18002f4b2  lea     rbp, [rsp-380h]
0x18002f4ba  sub     rsp, 480h
0x18002f4c1  mov     rax, cs:__security_cookie
0x18002f4c8  xor     rax, rsp
0x18002f4cb  mov     [rbp+3A0h+var_30], rax
0x18002f4d2  xor     esi, esi
0x18002f4d4  xor     edi, edi
0x18002f4d6  mov     [rsp+4A0h+hTemplateFile], rsi; hTemplateFile
0x18002f4db  xor     r9d, r9d; lpSecurityAttributes
0x18002f4de  mov     [rsp+4A0h+dwFlagsAndAttributes], 8000000h; dwFlagsAndAttributes
0x18002f4e6  mov     edx, 80000000h; dwDesiredAccess
0x18002f4eb  mov     r14, rcx
0x18002f4ee  mov     [rsp+4A0h+var_458], rsi
0x18002f4f3  lea     r8d, [rsi+7]; dwShareMode
0x18002f4f7  mov     [rsp+4A0h+var_450], rdi
0x18002f4fc  mov     [rsp+4A0h+dwCreationDisposition], 3; dwCreationDisposition
0x18002f504  call    cs:__imp_CreateFileW
0x18002f50a  mov     rbx, rax
0x18002f50d  inc     rax
0x18002f510  test    rax, 0FFFFFFFFFFFFFFFEh
0x18002f516  jnz     short loc_18002F53F
0x18002f518  call    cs:__imp_GetLastError
0x18002f51e  mov     edx, eax
0x18002f520  test    eax, eax
0x18002f522  jnz     short loc_18002F52B
0x18002f524  mov     edx, 80004005h
0x18002f529  jmp     short loc_18002F536
0x18002f52b  jle     short loc_18002F536
0x18002f52d  movzx   edx, ax
0x18002f530  or      edx, 80070000h
0x18002f536  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002f53a  jmp     loc_18002F628
0x18002f53f  mov     r15d, 410h
0x18002f545  lea     rcx, [rsp+4A0h+Buffer]; void *
0x18002f54a  mov     r8d, r15d; Size
0x18002f54d  xor     edx, edx; Val
0x18002f54f  call    memset_0
0x18002f554  mov     r12d, 208h
0x18002f55a  lea     r8, [rsp+4A0h+Buffer]; lpBuffer
0x18002f55f  mov     edx, r12d; nBufferLength
0x18002f562  xor     r9d, r9d; lpFilePart
0x18002f565  mov     rcx, r14; lpFileName
0x18002f568  call    cs:__imp_GetFullPathNameW
0x18002f56e  test    eax, eax
0x18002f570  jz      loc_18002F60A
0x18002f576  lea     rdx, [rsp+4A0h+var_460]
0x18002f57b  mov     [rsp+4A0h+var_460], esi
0x18002f57f  lea     rcx, [rsp+4A0h+Buffer]
0x18002f584  call    ??$GetStringCchLength@K@?$CGlobalHelpersT@VCEmptyType@@@@SAJPEBGPEAKK@Z; CGlobalHelpersT<CEmptyType>::GetStringCchLength<ulong>(ushort const *,ulong *,ulong)
0x18002f589  mov     r14d, eax
0x18002f58c  test    eax, eax
0x18002f58e  jns     short loc_18002F599
0x18002f590  mov     ecx, eax
0x18002f592  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18002f597  jmp     short loc_18002F5BF
0x18002f599  mov     edx, [rsp+4A0h+var_460]
0x18002f59d  lea     r8, [rsp+4A0h+var_458]
0x18002f5a2  lea     rcx, [rsp+4A0h+Buffer]; Src
0x18002f5a7  call    ?CreateInternal@?$CImmutableStringsT@GVCImmutableStringsPolicyDefault@@@@KAJPEBGKPEAPEAG@Z; CImmutableStringsT<ushort,CImmutableStringsPolicyDefault>::CreateInternal(ushort const *,ulong,ushort * *)
0x18002f5ac  mov     r14d, eax
0x18002f5af  test    eax, eax
0x18002f5b1  jns     short loc_18002F5BA
0x18002f5b3  mov     ecx, eax
0x18002f5b5  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18002f5ba  mov     rsi, [rsp+4A0h+var_458]
0x18002f5bf  mov     ecx, r14d
0x18002f5c2  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002f5c7  test    r14d, r14d
0x18002f5ca  jns     short loc_18002F5D4
0x18002f5cc  mov     ecx, r14d
0x18002f5cf  jmp     loc_18002F7E5
0x18002f5d4  mov     r8, r15; Size
0x18002f5d7  lea     rcx, [rsp+4A0h+Buffer]; void *
0x18002f5dc  xor     edx, edx; Val
0x18002f5de  call    memset_0
0x18002f5e3  mov     rax, cs:?g_spWimIoCallbackInstance@@3V?$SP_COM@VCDlpActionRecoverCrypto@@@@A; SP_COM<CDlpActionRecoverCrypto> g_spWimIoCallbackInstance
0x18002f5ea  lea     r8, [rsp+4A0h+Buffer]; lpBuffer
0x18002f5ef  xor     r9d, r9d; lpFilePart
0x18002f5f2  mov     edx, r12d; nBufferLength
0x18002f5f5  mov     rcx, [rax+228h]; lpFileName
0x18002f5fc  call    cs:__imp_GetFullPathNameW
0x18002f602  test    eax, eax
0x18002f604  jnz     loc_18002F6A7
0x18002f60a  call    cs:__imp_GetLastError
0x18002f610  mov     edx, eax
0x18002f612  test    eax, eax
0x18002f614  jnz     short loc_18002F61D
0x18002f616  mov     edx, 80004005h
0x18002f61b  jmp     short loc_18002F628
0x18002f61d  jle     short loc_18002F628
0x18002f61f  movzx   edx, ax
0x18002f622  or      edx, 80070000h
0x18002f628  mov     ecx, edx
0x18002f62a  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18002f62f  test    edx, edx
0x18002f631  js      loc_18002F7EA
0x18002f637  test    rdi, rdi
0x18002f63a  jz      short loc_18002F658
0x18002f63c  call    cs:__imp_GetProcessHeap
0x18002f642  lea     r8, [rdi-4]; lpMem
0x18002f646  xor     edx, edx; dwFlags
0x18002f648  mov     rcx, rax; hHeap
0x18002f64b  call    cs:__imp_HeapFree
0x18002f651  xor     ecx, ecx
0x18002f653  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002f658  test    rsi, rsi
0x18002f65b  jz      short loc_18002F679
0x18002f65d  call    cs:__imp_GetProcessHeap
0x18002f663  lea     r8, [rsi-4]; lpMem
0x18002f667  xor     edx, edx; dwFlags
0x18002f669  mov     rcx, rax; hHeap
0x18002f66c  call    cs:__imp_HeapFree
0x18002f672  xor     ecx, ecx
0x18002f674  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002f679  mov     rax, rbx
0x18002f67c  mov     rcx, [rbp+3A0h+var_30]
0x18002f683  xor     rcx, rsp; StackCookie
0x18002f686  call    __security_check_cookie
0x18002f68b  lea     r11, [rsp+4A0h+var_20]
0x18002f693  mov     rbx, [r11+38h]
0x18002f697  mov     rsi, [r11+40h]
0x18002f69b  mov     rsp, r11
0x18002f69e  pop     r15
0x18002f6a0  pop     r14
0x18002f6a2  pop     r12
0x18002f6a4  pop     rdi
0x18002f6a5  pop     rbp
0x18002f6a6  retn
0x18002f6a7  lea     rdx, [rsp+4A0h+var_460]
0x18002f6ac  mov     [rsp+4A0h+var_460], edi
0x18002f6b0  lea     rcx, [rsp+4A0h+Buffer]
0x18002f6b5  call    ??$GetStringCchLength@K@?$CGlobalHelpersT@VCEmptyType@@@@SAJPEBGPEAKK@Z; CGlobalHelpersT<CEmptyType>::GetStringCchLength<ulong>(ushort const *,ulong *,ulong)
0x18002f6ba  mov     r14d, eax
0x18002f6bd  test    eax, eax
0x18002f6bf  jns     short loc_18002F6CA
0x18002f6c1  mov     ecx, eax
0x18002f6c3  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18002f6c8  jmp     short loc_18002F6F0
0x18002f6ca  mov     edx, [rsp+4A0h+var_460]
0x18002f6ce  lea     r8, [rsp+4A0h+var_450]
0x18002f6d3  lea     rcx, [rsp+4A0h+Buffer]; Src
0x18002f6d8  call    ?CreateInternal@?$CImmutableStringsT@GVCImmutableStringsPolicyDefault@@@@KAJPEBGKPEAPEAG@Z; CImmutableStringsT<ushort,CImmutableStringsPolicyDefault>::CreateInternal(ushort const *,ulong,ushort * *)
0x18002f6dd  mov     r14d, eax
0x18002f6e0  test    eax, eax
0x18002f6e2  jns     short loc_18002F6EB
0x18002f6e4  mov     ecx, eax
0x18002f6e6  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18002f6eb  mov     rdi, [rsp+4A0h+var_450]
0x18002f6f0  mov     ecx, r14d
0x18002f6f3  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002f6f8  test    r14d, r14d
0x18002f6fb  js      loc_18002F5CC
0x18002f701  test    rdi, rdi
0x18002f704  jnz     short loc_18002F71E
0x18002f706  xor     r14d, r14d
0x18002f709  xor     r15d, r15d
0x18002f70c  xor     ecx, ecx
0x18002f70e  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002f713  test    rsi, rsi
0x18002f716  jz      short loc_18002F72C
0x18002f718  mov     r12d, [rsi-4]
0x18002f71c  jmp     short loc_18002F72F
0x18002f71e  mov     r14, rdi
0x18002f721  test    rdi, rdi
0x18002f724  jz      short loc_18002F709
0x18002f726  mov     r15d, [rdi-4]
0x18002f72a  jmp     short loc_18002F70C
0x18002f72c  xor     r12d, r12d
0x18002f72f  xor     ecx, ecx
0x18002f731  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002f736  cmp     r15d, r12d
0x18002f739  jnz     short loc_18002F757
0x18002f73b  mov     r8d, r15d
0x18002f73e  mov     rdx, rsi; Buf2
0x18002f741  add     r8, r8; Size
0x18002f744  mov     rcx, r14; Buf1
0x18002f747  call    memcmp_0
0x18002f74c  xor     r14d, r14d
0x18002f74f  test    eax, eax
0x18002f751  setz    r14b
0x18002f755  jmp     short loc_18002F75A
0x18002f757  xor     r14d, r14d
0x18002f75a  xor     ecx, ecx
0x18002f75c  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002f761  test    r14d, r14d
0x18002f764  jz      loc_18002F637
0x18002f76a  mov     r14, cs:?g_spWimIoCallbackInstance@@3V?$SP_COM@VCDlpActionRecoverCrypto@@@@A; SP_COM<CDlpActionRecoverCrypto> g_spWimIoCallbackInstance
0x18002f771  test    r14, r14
0x18002f774  jz      short loc_18002F7E0
0x18002f776  mov     rcx, [r14+290h]; hObject
0x18002f77d  lea     rax, [rcx-1]
0x18002f781  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002f785  ja      short loc_18002F78D
0x18002f787  call    cs:__imp_CloseHandle
0x18002f78d  mov     [r14+290h], rbx
0x18002f794  test    rdi, rdi
0x18002f797  jz      short loc_18002F7B5
0x18002f799  call    cs:__imp_GetProcessHeap
0x18002f79f  lea     r8, [rdi-4]; lpMem
0x18002f7a3  xor     edx, edx; dwFlags
0x18002f7a5  mov     rcx, rax; hHeap
0x18002f7a8  call    cs:__imp_HeapFree
0x18002f7ae  xor     ecx, ecx
0x18002f7b0  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002f7b5  test    rsi, rsi
0x18002f7b8  jz      short loc_18002F7D6
0x18002f7ba  call    cs:__imp_GetProcessHeap
0x18002f7c0  lea     r8, [rsi-4]; lpMem
0x18002f7c4  xor     edx, edx; dwFlags
0x18002f7c6  mov     rcx, rax; hHeap
0x18002f7c9  call    cs:__imp_HeapFree
0x18002f7cf  xor     ecx, ecx
0x18002f7d1  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002f7d6  mov     eax, 0ABCD1024h
0x18002f7db  jmp     loc_18002F67C
0x18002f7e0  mov     ecx, 8000000Ah
0x18002f7e5  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18002f7ea  test    rdi, rdi
0x18002f7ed  jz      short loc_18002F80B
0x18002f7ef  call    cs:__imp_GetProcessHeap
0x18002f7f5  lea     r8, [rdi-4]; lpMem
0x18002f7f9  xor     edx, edx; dwFlags
0x18002f7fb  mov     rcx, rax; hHeap
0x18002f7fe  call    cs:__imp_HeapFree
0x18002f804  xor     ecx, ecx
0x18002f806  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002f80b  test    rsi, rsi
0x18002f80e  jz      short loc_18002F82C
0x18002f810  call    cs:__imp_GetProcessHeap
0x18002f816  lea     r8, [rsi-4]; lpMem
0x18002f81a  xor     edx, edx; dwFlags
0x18002f81c  mov     rcx, rax; hHeap
0x18002f81f  call    cs:__imp_HeapFree
0x18002f825  xor     ecx, ecx
0x18002f827  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002f82c  lea     rax, [rbx-1]
0x18002f830  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002f834  ja      short loc_18002F83F
0x18002f836  mov     rcx, rbx; hObject
0x18002f839  call    cs:__imp_CloseHandle
0x18002f83f  xor     eax, eax
0x18002f841  jmp     loc_18002F67C
```
