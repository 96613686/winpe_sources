# SxDeleteFile(ushort const *)

- ea: `0x18001d154`
- end: `0x18001d29c`
- name: `?SxDeleteFile@@YAJPEBG@Z`
- size: `328`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `3`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x1800148dc`
- `0x18001698c`
- `0x18001dfe0`

## callees

- `0x18000ea0c`
- `0x180014f70`
- `0x18001586c`
- `0x180015974`
- `0x18001c58c`
- `0x18001cecc`
- `0x18001d154`
- `0x18001d2a4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d207`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d207`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18001d1ed`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18001d243`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18001d1ed`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18001d243`

## string_xrefs

- `0x18001d1a0`: `SxDeleteFile`

## pseudocode

```c
__int64 __fastcall SxDeleteFile(LPCWSTR lpFileName)
{
  __int16 v2; // ax
  int LastFailureAsHRESULT; // ebx
  __int16 v4; // ax
  unsigned int v5; // edx
  __int64 v6; // rcx
  int v8; // [rsp+20h] [rbp-40h] BYREF
  __int16 v9; // [rsp+24h] [rbp-3Ch]
  __int16 v10; // [rsp+26h] [rbp-3Ah]
  unsigned int v11; // [rsp+78h] [rbp+18h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_b1bfb7512cf23544267720d0f520c3da_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v8, "SxDeleteFile", 1311, 1);
  v11 = -1;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, WPP_b1bfb7512cf23544267720d0f520c3da_Traceguids, lpFileName);
  if ( DeleteFileW(lpFileName) )
  {
    v2 = 1319;
LABEL_9:
    LastFailureAsHRESULT = 0;
    v9 = v2;
    v8 = 0;
    goto LABEL_19;
  }
  if ( GetLastError() == 2 )
  {
    v2 = 1323;
    goto LABEL_9;
  }
  LastFailureAsHRESULT = SxClearDifficultAttributes(lpFileName, &v11);
  v8 = LastFailureAsHRESULT;
  v4 = 1329;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_13;
  v9 = 1329;
  if ( !DeleteFileW(lpFileName) )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v6);
    v8 = LastFailureAsHRESULT;
    v4 = 1334;
LABEL_13:
    v5 = v11;
    v10 = v4;
    goto LABEL_17;
  }
  LastFailureAsHRESULT = 0;
  v8 = 0;
  v5 = -1;
  v9 = 1334;
LABEL_17:
  if ( v5 != -1 )
  {
    SxSetFileAttributes(lpFileName, v5);
    LastFailureAsHRESULT = v8;
  }
LABEL_19:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v8);
  return (unsigned int)LastFailureAsHRESULT;
}

```

## disassembly

```asm
0x18001d154  mov     [rsp-8+arg_0], rbx
0x18001d159  mov     [rsp-8+arg_10], rdi
0x18001d15e  push    rbp
0x18001d15f  mov     rbp, rsp
0x18001d162  sub     rsp, 60h
0x18001d166  mov     rdi, rcx
0x18001d169  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d170  lea     rbx, WPP_GLOBAL_Control
0x18001d177  cmp     rcx, rbx
0x18001d17a  jz      short loc_18001D19A
0x18001d17c  test    dword ptr [rcx+1Ch], 20000000h
0x18001d183  jz      short loc_18001D19A
0x18001d185  mov     rcx, [rcx+10h]
0x18001d189  lea     r8, WPP_b1bfb7512cf23544267720d0f520c3da_Traceguids
0x18001d190  mov     edx, 29h ; ')'
0x18001d195  call    WPP_SF_
0x18001d19a  mov     r9d, 1; unsigned __int16
0x18001d1a0  lea     rdx, aSxdeletefile; "SxDeleteFile"
0x18001d1a7  mov     r8d, 51Fh; unsigned __int16
0x18001d1ad  lea     rcx, [rbp+var_40]; this
0x18001d1b1  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18001d1b6  mov     [rbp+arg_8], 0FFFFFFFFh
0x18001d1bd  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d1c4  cmp     rcx, rbx
0x18001d1c7  jz      short loc_18001D1EA
0x18001d1c9  test    dword ptr [rcx+1Ch], 10000000h
0x18001d1d0  jz      short loc_18001D1EA
0x18001d1d2  mov     rcx, [rcx+10h]
0x18001d1d6  lea     r8, WPP_b1bfb7512cf23544267720d0f520c3da_Traceguids
0x18001d1dd  mov     edx, 2Ah ; '*'
0x18001d1e2  mov     r9, rdi
0x18001d1e5  call    WPP_SF_S
0x18001d1ea  mov     rcx, rdi; lpFileName
0x18001d1ed  call    cs:__imp_DeleteFileW
0x18001d1f3  test    eax, eax
0x18001d1f5  jz      short loc_18001D207
0x18001d1f7  mov     eax, 527h
0x18001d1fc  xor     ebx, ebx
0x18001d1fe  mov     [rbp+var_3C], ax
0x18001d202  mov     [rbp+var_40], ebx
0x18001d205  jmp     short loc_18001D27F
0x18001d207  call    cs:__imp_GetLastError
0x18001d20d  cmp     eax, 2
0x18001d210  jnz     short loc_18001D219
0x18001d212  mov     eax, 52Bh
0x18001d217  jmp     short loc_18001D1FC
0x18001d219  lea     rdx, [rbp+arg_8]; unsigned int *
0x18001d21d  mov     rcx, rdi; lpFileName
0x18001d220  call    ?SxClearDifficultAttributes@@YAJPEBGPEAK@Z; SxClearDifficultAttributes(ushort const *,ulong *)
0x18001d225  mov     ebx, eax
0x18001d227  mov     [rbp+var_40], eax
0x18001d22a  test    eax, eax
0x18001d22c  mov     eax, 531h
0x18001d231  jns     short loc_18001D23C
0x18001d233  mov     edx, [rbp+arg_8]
0x18001d236  mov     [rbp+var_3A], ax
0x18001d23a  jmp     short loc_18001D26F
0x18001d23c  mov     rcx, rdi; lpFileName
0x18001d23f  mov     [rbp+var_3C], ax
0x18001d243  call    cs:__imp_DeleteFileW
0x18001d249  test    eax, eax
0x18001d24b  jnz     short loc_18001D25E
0x18001d24d  call    GetLastFailureAsHRESULT
0x18001d252  mov     ebx, eax
0x18001d254  mov     [rbp+var_40], eax
0x18001d257  mov     eax, 536h
0x18001d25c  jmp     short loc_18001D233
0x18001d25e  xor     ebx, ebx
0x18001d260  mov     eax, 536h
0x18001d265  mov     [rbp+var_40], ebx
0x18001d268  or      edx, 0FFFFFFFFh; unsigned int
0x18001d26b  mov     [rbp+var_3C], ax
0x18001d26f  cmp     edx, 0FFFFFFFFh
0x18001d272  jz      short loc_18001D27F
0x18001d274  mov     rcx, rdi; lpFileName
0x18001d277  call    ?SxSetFileAttributes@@YAJPEBGK@Z; SxSetFileAttributes(ushort const *,ulong)
0x18001d27c  mov     ebx, [rbp+var_40]
0x18001d27f  lea     rcx, [rbp+var_40]; this
0x18001d283  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18001d288  lea     r11, [rsp+60h+var_s0]
0x18001d28d  mov     eax, ebx
0x18001d28f  mov     rbx, [r11+10h]
0x18001d293  mov     rdi, [r11+20h]
0x18001d297  mov     rsp, r11
0x18001d29a  pop     rbp
0x18001d29b  retn
```
