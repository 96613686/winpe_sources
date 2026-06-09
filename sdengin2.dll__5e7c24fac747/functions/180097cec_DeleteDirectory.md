# _DeleteDirectory

- ea: `0x180097cec`
- end: `0x180097f27`
- name: `_DeleteDirectory`
- size: `571`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x180096c1c`
- `0x180097f30`

## callees

- `0x1800081d8`
- `0x180008240`
- `0x18006fe84`
- `0x18006ff8c`
- `0x18008f5d0`
- `0x180096b20`
- `0x180097370`
- `0x180097cec`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x180097e2b`
- `KERNEL32!CreateFileW` at `0x180097e2b`
- `KERNEL32!GetLastError` at `0x180097dda`
- `KERNEL32!GetLastError` at `0x180097de9`
- `KERNEL32!GetLastError` at `0x180097df8`
- `KERNEL32!GetLastError` at `0x180097e3f`
- `KERNEL32!GetLastError` at `0x180097e4a`
- `KERNEL32!GetLastError` at `0x180097dda`
- `KERNEL32!GetLastError` at `0x180097de9`
- `KERNEL32!GetLastError` at `0x180097df8`
- `KERNEL32!GetLastError` at `0x180097e3f`
- `KERNEL32!GetLastError` at `0x180097e4a`
- `KERNEL32!CloseHandle` at `0x180097e62`
- `KERNEL32!CloseHandle` at `0x180097efe`
- `KERNEL32!CloseHandle` at `0x180097e62`
- `KERNEL32!CloseHandle` at `0x180097efe`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x180097db2`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x180097ea6`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x180097db2`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x180097ea6`

## string_xrefs

- `0x180097d3e`: `_DeleteDirectory`

## pseudocode

```c
__int64 __fastcall DeleteDirectory(LPCWSTR lpFileName)
{
  unsigned int v2; // r14d
  int LastFailureAsHRESULT; // edi
  __int64 FileW; // rbx
  __int16 v5; // ax
  __int16 v6; // ax
  __int64 v7; // rcx
  int v9; // [rsp+40h] [rbp-40h] BYREF
  __int16 v10; // [rsp+44h] [rbp-3Ch]
  __int16 v11; // [rsp+46h] [rbp-3Ah]
  int v12; // [rsp+48h] [rbp-38h]
  unsigned int v13; // [rsp+A0h] [rbp+20h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, WPP_b1bfb7512cf23544267720d0f520c3da_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v9, "_DeleteDirectory", 1908, 1);
  v2 = -1;
  v13 = -1;
  if ( !lpFileName )
  {
    LastFailureAsHRESULT = -2147024809;
    v11 = 1913;
    v9 = -2147024809;
    goto LABEL_31;
  }
  v9 = 0;
  v10 = 1913;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, WPP_b1bfb7512cf23544267720d0f520c3da_Traceguids, lpFileName);
  if ( RemoveDirectoryW(lpFileName) )
  {
    v9 = 0;
    v10 = 1919;
    LastFailureAsHRESULT = 0;
    goto LABEL_31;
  }
  FileW = -1;
  if ( GetLastError() == 2 || GetLastError() == 3 )
  {
    LastFailureAsHRESULT = 0;
    v9 = 0;
    v10 = 1924;
LABEL_27:
    if ( v2 != -1 )
    {
      SxSetFileAttributes(lpFileName, v2);
      LastFailureAsHRESULT = v9;
    }
    goto LABEL_29;
  }
  if ( GetLastError() == 5 )
  {
    FileW = (__int64)CreateFileW(lpFileName, 0x100000u, 7u, 0, 3u, 0x2000000u, 0);
    if ( ((FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
      goto LABEL_18;
    if ( GetLastError() == 2 || GetLastError() == 3 )
    {
      v6 = 1938;
      goto LABEL_22;
    }
    if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
LABEL_18:
      CloseHandle((HANDLE)FileW);
      FileW = -1;
    }
  }
  LastFailureAsHRESULT = SxClearDifficultAttributes(lpFileName, &v13);
  v9 = LastFailureAsHRESULT;
  v5 = 1947;
  if ( LastFailureAsHRESULT < 0 )
  {
LABEL_20:
    v2 = v13;
    v11 = v5;
    goto LABEL_27;
  }
  v10 = 1947;
  if ( !RemoveDirectoryW(lpFileName) )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v7);
    v9 = LastFailureAsHRESULT;
    v5 = 1952;
    v12 = 1;
    goto LABEL_20;
  }
  v6 = 1952;
LABEL_22:
  LastFailureAsHRESULT = 0;
  v10 = v6;
  v9 = 0;
LABEL_29:
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)FileW);
LABEL_31:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v9);
  return (unsigned int)LastFailureAsHRESULT;
}

```

## disassembly

```asm
0x180097cec  mov     [rsp-18h+arg_8], rbx
0x180097cf1  mov     [rsp-18h+arg_10], rsi
0x180097cf6  push    rbp
0x180097cf7  push    rdi
0x180097cf8  push    r14
0x180097cfa  mov     rbp, rsp
0x180097cfd  sub     rsp, 80h
0x180097d04  mov     rsi, rcx
0x180097d07  mov     rcx, cs:WPP_GLOBAL_Control
0x180097d0e  lea     rbx, WPP_GLOBAL_Control
0x180097d15  cmp     rcx, rbx
0x180097d18  jz      short loc_180097D38
0x180097d1a  test    dword ptr [rcx+1Ch], 20000000h
0x180097d21  jz      short loc_180097D38
0x180097d23  mov     rcx, [rcx+10h]
0x180097d27  lea     r8, WPP_b1bfb7512cf23544267720d0f520c3da_Traceguids
0x180097d2e  mov     edx, 34h ; '4'
0x180097d33  call    WPP_SF_
0x180097d38  mov     r9d, 1; unsigned __int16
0x180097d3e  lea     rdx, aDeletedirector_0; "_DeleteDirectory"
0x180097d45  mov     r8d, 774h; unsigned __int16
0x180097d4b  lea     rcx, [rbp+var_40]; this
0x180097d4f  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180097d54  or      r14d, 0FFFFFFFFh
0x180097d58  mov     eax, 779h
0x180097d5d  mov     [rbp+arg_0], r14d
0x180097d61  test    rsi, rsi
0x180097d64  jnz     short loc_180097D77
0x180097d66  mov     edi, 80070057h
0x180097d6b  mov     [rbp+var_3A], ax
0x180097d6f  mov     [rbp+var_40], edi
0x180097d72  jmp     loc_180097F04
0x180097d77  mov     [rbp+var_40], 0
0x180097d7e  mov     [rbp+var_3C], ax
0x180097d82  mov     rcx, cs:WPP_GLOBAL_Control
0x180097d89  cmp     rcx, rbx
0x180097d8c  jz      short loc_180097DAF
0x180097d8e  test    dword ptr [rcx+1Ch], 10000000h
0x180097d95  jz      short loc_180097DAF
0x180097d97  mov     rcx, [rcx+10h]
0x180097d9b  lea     r8, WPP_b1bfb7512cf23544267720d0f520c3da_Traceguids
0x180097da2  mov     edx, 35h ; '5'
0x180097da7  mov     r9, rsi
0x180097daa  call    WPP_SF_S
0x180097daf  mov     rcx, rsi; lpPathName
0x180097db2  call    cs:__imp_RemoveDirectoryW
0x180097db8  test    eax, eax
0x180097dba  jz      short loc_180097DD3
0x180097dbc  mov     eax, 77Fh
0x180097dc1  mov     [rbp+var_40], 0
0x180097dc8  mov     [rbp+var_3C], ax
0x180097dcc  xor     edi, edi
0x180097dce  jmp     loc_180097F04
0x180097dd3  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180097dd7  mov     rbx, rdi
0x180097dda  call    cs:__imp_GetLastError
0x180097de0  cmp     eax, 2
0x180097de3  jz      loc_180097ECF
0x180097de9  call    cs:__imp_GetLastError
0x180097def  cmp     eax, 3
0x180097df2  jz      loc_180097ECF
0x180097df8  call    cs:__imp_GetLastError
0x180097dfe  cmp     eax, 5
0x180097e01  jnz     short loc_180097E6B
0x180097e03  mov     [rsp+80h+hTemplateFile], 0; hTemplateFile
0x180097e0c  lea     r8d, [rdi+8]; dwShareMode
0x180097e10  mov     [rsp+80h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x180097e18  xor     r9d, r9d; lpSecurityAttributes
0x180097e1b  mov     edx, 100000h; dwDesiredAccess
0x180097e20  mov     [rsp+80h+dwCreationDisposition], 3; dwCreationDisposition
0x180097e28  mov     rcx, rsi; lpFileName
0x180097e2b  call    cs:__imp_CreateFileW
0x180097e31  mov     rbx, rax
0x180097e34  inc     rax
0x180097e37  test    rax, 0FFFFFFFFFFFFFFFEh
0x180097e3d  jnz     short loc_180097E5F
0x180097e3f  call    cs:__imp_GetLastError
0x180097e45  cmp     eax, 2
0x180097e48  jz      short loc_180097E8F
0x180097e4a  call    cs:__imp_GetLastError
0x180097e50  cmp     eax, 3
0x180097e53  jz      short loc_180097E8F
0x180097e55  lea     rax, [rbx-1]
0x180097e59  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180097e5d  ja      short loc_180097E6B
0x180097e5f  mov     rcx, rbx; hObject
0x180097e62  call    cs:__imp_CloseHandle
0x180097e68  mov     rbx, rdi
0x180097e6b  lea     rdx, [rbp+arg_0]; unsigned int *
0x180097e6f  mov     rcx, rsi; lpFileName
0x180097e72  call    ?SxClearDifficultAttributes@@YAJPEBGPEAK@Z; SxClearDifficultAttributes(ushort const *,ulong *)
0x180097e77  mov     edi, eax
0x180097e79  mov     [rbp+var_40], eax
0x180097e7c  test    eax, eax
0x180097e7e  mov     eax, 79Bh
0x180097e83  jns     short loc_180097E9F
0x180097e85  mov     r14d, [rbp+arg_0]
0x180097e89  mov     [rbp+var_3A], ax
0x180097e8d  jmp     short loc_180097EDD
0x180097e8f  mov     eax, 792h
0x180097e94  xor     edi, edi
0x180097e96  mov     [rbp+var_3C], ax
0x180097e9a  mov     [rbp+var_40], edi
0x180097e9d  jmp     short loc_180097EF1
0x180097e9f  mov     rcx, rsi; lpPathName
0x180097ea2  mov     [rbp+var_3C], ax
0x180097ea6  call    cs:__imp_RemoveDirectoryW
0x180097eac  test    eax, eax
0x180097eae  jnz     short loc_180097EC8
0x180097eb0  call    GetLastFailureAsHRESULT
0x180097eb5  mov     edi, eax
0x180097eb7  mov     [rbp+var_40], eax
0x180097eba  mov     eax, 7A0h
0x180097ebf  mov     [rbp+var_38], 1
0x180097ec6  jmp     short loc_180097E85
0x180097ec8  mov     eax, 7A0h
0x180097ecd  jmp     short loc_180097E94
0x180097ecf  xor     edi, edi
0x180097ed1  mov     eax, 784h
0x180097ed6  mov     [rbp+var_40], edi
0x180097ed9  mov     [rbp+var_3C], ax
0x180097edd  cmp     r14d, 0FFFFFFFFh
0x180097ee1  jz      short loc_180097EF1
0x180097ee3  mov     edx, r14d; unsigned int
0x180097ee6  mov     rcx, rsi; lpFileName
0x180097ee9  call    ?SxSetFileAttributes@@YAJPEBGK@Z; SxSetFileAttributes(ushort const *,ulong)
0x180097eee  mov     edi, [rbp+var_40]
0x180097ef1  lea     rcx, [rbx-1]
0x180097ef5  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180097ef9  ja      short loc_180097F04
0x180097efb  mov     rcx, rbx; hObject
0x180097efe  call    cs:__imp_CloseHandle
0x180097f04  lea     rcx, [rbp+var_40]; this
0x180097f08  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180097f0d  lea     r11, [rsp+80h+var_s0]
0x180097f15  mov     eax, edi
0x180097f17  mov     rbx, [r11+28h]
0x180097f1b  mov     rsi, [r11+30h]
0x180097f1f  mov     rsp, r11
0x180097f22  pop     r14
0x180097f24  pop     rdi
0x180097f25  pop     rbp
0x180097f26  retn
```
