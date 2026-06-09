# _DeleteDirectory

- ea: `0x18009c17c`
- end: `0x18009c3f8`
- name: `_DeleteDirectory`
- size: `636`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x18009b044`
- `0x18009c400`

## callees

- `0x180008370`
- `0x1800083e4`
- `0x180072e08`
- `0x180072f14`
- `0x1800935fc`
- `0x18009af48`
- `0x18009b7c8`
- `0x18009c17c`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x18009c2d7`
- `KERNEL32!CreateFileW` at `0x18009c2d7`
- `KERNEL32!GetLastError` at `0x18009c270`
- `KERNEL32!GetLastError` at `0x18009c285`
- `KERNEL32!GetLastError` at `0x18009c29a`
- `KERNEL32!GetLastError` at `0x18009c2f1`
- `KERNEL32!GetLastError` at `0x18009c302`
- `KERNEL32!GetLastError` at `0x18009c270`
- `KERNEL32!GetLastError` at `0x18009c285`
- `KERNEL32!GetLastError` at `0x18009c29a`
- `KERNEL32!GetLastError` at `0x18009c2f1`
- `KERNEL32!GetLastError` at `0x18009c302`
- `KERNEL32!CloseHandle` at `0x18009c320`
- `KERNEL32!CloseHandle` at `0x18009c3c8`
- `KERNEL32!CloseHandle` at `0x18009c320`
- `KERNEL32!CloseHandle` at `0x18009c3c8`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18009c242`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18009c36a`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18009c242`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18009c36a`

## string_xrefs

- `0x18009c1ce`: `_DeleteDirectory`

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
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v9, "_DeleteDirectory", 0x774u, 1u);
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
0x18009c17c  mov     [rsp-18h+arg_8], rbx
0x18009c181  mov     [rsp-18h+arg_10], rsi
0x18009c186  push    rbp
0x18009c187  push    rdi
0x18009c188  push    r14
0x18009c18a  mov     rbp, rsp
0x18009c18d  sub     rsp, 80h
0x18009c194  mov     rsi, rcx
0x18009c197  mov     rcx, cs:WPP_GLOBAL_Control
0x18009c19e  lea     rbx, WPP_GLOBAL_Control
0x18009c1a5  cmp     rcx, rbx
0x18009c1a8  jz      short loc_18009C1C8
0x18009c1aa  test    dword ptr [rcx+1Ch], 20000000h
0x18009c1b1  jz      short loc_18009C1C8
0x18009c1b3  mov     rcx, [rcx+10h]
0x18009c1b7  lea     r8, WPP_b1bfb7512cf23544267720d0f520c3da_Traceguids
0x18009c1be  mov     edx, 34h ; '4'
0x18009c1c3  call    WPP_SF_
0x18009c1c8  mov     r9d, 1; unsigned __int16
0x18009c1ce  lea     rdx, aDeletedirector_0; "_DeleteDirectory"
0x18009c1d5  mov     r8d, 774h; unsigned __int16
0x18009c1db  lea     rcx, [rbp+var_40]; this
0x18009c1df  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18009c1e4  or      r14d, 0FFFFFFFFh
0x18009c1e8  mov     eax, 779h
0x18009c1ed  mov     [rbp+arg_0], r14d
0x18009c1f1  test    rsi, rsi
0x18009c1f4  jnz     short loc_18009C207
0x18009c1f6  mov     edi, 80070057h
0x18009c1fb  mov     [rbp+var_3A], ax
0x18009c1ff  mov     [rbp+var_40], edi
0x18009c202  jmp     loc_18009C3D4
0x18009c207  mov     [rbp+var_40], 0
0x18009c20e  mov     [rbp+var_3C], ax
0x18009c212  mov     rcx, cs:WPP_GLOBAL_Control
0x18009c219  cmp     rcx, rbx
0x18009c21c  jz      short loc_18009C23F
0x18009c21e  test    dword ptr [rcx+1Ch], 10000000h
0x18009c225  jz      short loc_18009C23F
0x18009c227  mov     rcx, [rcx+10h]
0x18009c22b  lea     r8, WPP_b1bfb7512cf23544267720d0f520c3da_Traceguids
0x18009c232  mov     edx, 35h ; '5'
0x18009c237  mov     r9, rsi
0x18009c23a  call    WPP_SF_S
0x18009c23f  mov     rcx, rsi; lpPathName
0x18009c242  call    cs:__imp_RemoveDirectoryW
0x18009c249  nop     dword ptr [rax+rax+00h]
0x18009c24e  test    eax, eax
0x18009c250  jz      short loc_18009C269
0x18009c252  mov     eax, 77Fh
0x18009c257  mov     [rbp+var_40], 0
0x18009c25e  mov     [rbp+var_3C], ax
0x18009c262  xor     edi, edi
0x18009c264  jmp     loc_18009C3D4
0x18009c269  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18009c26d  mov     rbx, rdi
0x18009c270  call    cs:__imp_GetLastError
0x18009c277  nop     dword ptr [rax+rax+00h]
0x18009c27c  cmp     eax, 2
0x18009c27f  jz      loc_18009C399
0x18009c285  call    cs:__imp_GetLastError
0x18009c28c  nop     dword ptr [rax+rax+00h]
0x18009c291  cmp     eax, 3
0x18009c294  jz      loc_18009C399
0x18009c29a  call    cs:__imp_GetLastError
0x18009c2a1  nop     dword ptr [rax+rax+00h]
0x18009c2a6  cmp     eax, 5
0x18009c2a9  jnz     loc_18009C32F
0x18009c2af  mov     [rsp+80h+hTemplateFile], 0; hTemplateFile
0x18009c2b8  lea     r8d, [rdi+8]; dwShareMode
0x18009c2bc  mov     [rsp+80h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x18009c2c4  xor     r9d, r9d; lpSecurityAttributes
0x18009c2c7  mov     edx, 100000h; dwDesiredAccess
0x18009c2cc  mov     [rsp+80h+dwCreationDisposition], 3; dwCreationDisposition
0x18009c2d4  mov     rcx, rsi; lpFileName
0x18009c2d7  call    cs:__imp_CreateFileW
0x18009c2de  nop     dword ptr [rax+rax+00h]
0x18009c2e3  mov     rbx, rax
0x18009c2e6  inc     rax
0x18009c2e9  test    rax, 0FFFFFFFFFFFFFFFEh
0x18009c2ef  jnz     short loc_18009C31D
0x18009c2f1  call    cs:__imp_GetLastError
0x18009c2f8  nop     dword ptr [rax+rax+00h]
0x18009c2fd  cmp     eax, 2
0x18009c300  jz      short loc_18009C353
0x18009c302  call    cs:__imp_GetLastError
0x18009c309  nop     dword ptr [rax+rax+00h]
0x18009c30e  cmp     eax, 3
0x18009c311  jz      short loc_18009C353
0x18009c313  lea     rax, [rbx-1]
0x18009c317  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18009c31b  ja      short loc_18009C32F
0x18009c31d  mov     rcx, rbx; hObject
0x18009c320  call    cs:__imp_CloseHandle
0x18009c327  nop     dword ptr [rax+rax+00h]
0x18009c32c  mov     rbx, rdi
0x18009c32f  lea     rdx, [rbp+arg_0]; unsigned int *
0x18009c333  mov     rcx, rsi; lpFileName
0x18009c336  call    ?SxClearDifficultAttributes@@YAJPEBGPEAK@Z; SxClearDifficultAttributes(ushort const *,ulong *)
0x18009c33b  mov     edi, eax
0x18009c33d  mov     [rbp+var_40], eax
0x18009c340  test    eax, eax
0x18009c342  mov     eax, 79Bh
0x18009c347  jns     short loc_18009C363
0x18009c349  mov     r14d, [rbp+arg_0]
0x18009c34d  mov     [rbp+var_3A], ax
0x18009c351  jmp     short loc_18009C3A7
0x18009c353  mov     eax, 792h
0x18009c358  xor     edi, edi
0x18009c35a  mov     [rbp+var_3C], ax
0x18009c35e  mov     [rbp+var_40], edi
0x18009c361  jmp     short loc_18009C3BB
0x18009c363  mov     rcx, rsi; lpPathName
0x18009c366  mov     [rbp+var_3C], ax
0x18009c36a  call    cs:__imp_RemoveDirectoryW
0x18009c371  nop     dword ptr [rax+rax+00h]
0x18009c376  test    eax, eax
0x18009c378  jnz     short loc_18009C392
0x18009c37a  call    GetLastFailureAsHRESULT
0x18009c37f  mov     edi, eax
0x18009c381  mov     [rbp+var_40], eax
0x18009c384  mov     eax, 7A0h
0x18009c389  mov     [rbp+var_38], 1
0x18009c390  jmp     short loc_18009C349
0x18009c392  mov     eax, 7A0h
0x18009c397  jmp     short loc_18009C358
0x18009c399  xor     edi, edi
0x18009c39b  mov     eax, 784h
0x18009c3a0  mov     [rbp+var_40], edi
0x18009c3a3  mov     [rbp+var_3C], ax
0x18009c3a7  cmp     r14d, 0FFFFFFFFh
0x18009c3ab  jz      short loc_18009C3BB
0x18009c3ad  mov     edx, r14d; unsigned int
0x18009c3b0  mov     rcx, rsi; lpFileName
0x18009c3b3  call    ?SxSetFileAttributes@@YAJPEBGK@Z; SxSetFileAttributes(ushort const *,ulong)
0x18009c3b8  mov     edi, [rbp+var_40]
0x18009c3bb  lea     rcx, [rbx-1]
0x18009c3bf  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18009c3c3  ja      short loc_18009C3D4
0x18009c3c5  mov     rcx, rbx; hObject
0x18009c3c8  call    cs:__imp_CloseHandle
0x18009c3cf  nop     dword ptr [rax+rax+00h]
0x18009c3d4  lea     rcx, [rbp+var_40]; this
0x18009c3d8  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18009c3dd  lea     r11, [rsp+80h+var_s0]
0x18009c3e5  mov     eax, edi
0x18009c3e7  mov     rbx, [r11+28h]
0x18009c3eb  mov     rsi, [r11+30h]
0x18009c3ef  mov     rsp, r11
0x18009c3f2  pop     r14
0x18009c3f4  pop     rdi
0x18009c3f5  pop     rbp
0x18009c3f6  retn
```
