# SxDeleteFile(ushort const *)

- ea: `0x18002eb80`
- end: `0x18002ecc8`
- name: `?SxDeleteFile@@YAJPEBG@Z`
- size: `328`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x18001cd8c`
- `0x18001faf8`

## callees

- `0x180020710`
- `0x180020908`
- `0x1800268b4`
- `0x1800269ac`
- `0x18002d6e8`
- `0x18002ea8c`
- `0x18002eb80`
- `0x18002eed4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18002ec33`
- `KERNEL32!GetLastError` at `0x18002ec33`
- `KERNEL32!DeleteFileW` at `0x18002ec19`
- `KERNEL32!DeleteFileW` at `0x18002ec6f`
- `KERNEL32!DeleteFileW` at `0x18002ec19`
- `KERNEL32!DeleteFileW` at `0x18002ec6f`

## string_xrefs

- `0x18002ebcc`: `SxDeleteFile`

## pseudocode

```c
__int64 __fastcall SxDeleteFile(LPCWSTR lpFileName)
{
  __int64 v2; // rdx
  __int64 v3; // r8
  __int16 v4; // ax
  int LastFailureAsHRESULT; // ebx
  __int16 v6; // ax
  __int64 v7; // rcx
  int v9; // [rsp+20h] [rbp-40h] BYREF
  __int16 v10; // [rsp+24h] [rbp-3Ch]
  __int16 v11; // [rsp+26h] [rbp-3Ah]
  unsigned int v12; // [rsp+78h] [rbp+18h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, &WPP_b1bfb7512cf23544267720d0f520c3da_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v9, "SxDeleteFile", 1311, 1);
  v12 = -1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, &WPP_b1bfb7512cf23544267720d0f520c3da_Traceguids, lpFileName);
  if ( DeleteFileW(lpFileName) )
  {
    v4 = 1319;
LABEL_9:
    LastFailureAsHRESULT = 0;
    v10 = v4;
    v9 = 0;
    goto LABEL_19;
  }
  if ( GetLastError() == 2 )
  {
    v4 = 1323;
    goto LABEL_9;
  }
  LastFailureAsHRESULT = SxClearDifficultAttributes(lpFileName, &v12);
  v9 = LastFailureAsHRESULT;
  v6 = 1329;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_13;
  v10 = 1329;
  if ( !DeleteFileW(lpFileName) )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v7);
    v9 = LastFailureAsHRESULT;
    v6 = 1334;
LABEL_13:
    v2 = v12;
    v11 = v6;
    goto LABEL_17;
  }
  LastFailureAsHRESULT = 0;
  v9 = 0;
  v2 = 0xFFFFFFFFLL;
  v10 = 1334;
LABEL_17:
  if ( (_DWORD)v2 != -1 )
  {
    SxSetFileAttributes(lpFileName, v2);
    LastFailureAsHRESULT = v9;
  }
LABEL_19:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v9, v2, v3);
  return (unsigned int)LastFailureAsHRESULT;
}

```

## disassembly

```asm
0x18002eb80  mov     [rsp-8+arg_0], rbx
0x18002eb85  mov     [rsp-8+arg_10], rdi
0x18002eb8a  push    rbp
0x18002eb8b  mov     rbp, rsp
0x18002eb8e  sub     rsp, 60h
0x18002eb92  mov     rdi, rcx
0x18002eb95  mov     rcx, cs:WPP_GLOBAL_Control
0x18002eb9c  lea     rbx, WPP_GLOBAL_Control
0x18002eba3  cmp     rcx, rbx
0x18002eba6  jz      short loc_18002EBC6
0x18002eba8  test    dword ptr [rcx+1Ch], 20000000h
0x18002ebaf  jz      short loc_18002EBC6
0x18002ebb1  mov     rcx, [rcx+10h]
0x18002ebb5  lea     r8, WPP_b1bfb7512cf23544267720d0f520c3da_Traceguids
0x18002ebbc  mov     edx, 29h ; ')'
0x18002ebc1  call    WPP_SF_
0x18002ebc6  mov     r9d, 1; unsigned __int16
0x18002ebcc  lea     rdx, aSxdeletefile; "SxDeleteFile"
0x18002ebd3  mov     r8d, 51Fh; unsigned __int16
0x18002ebd9  lea     rcx, [rbp+var_40]; this
0x18002ebdd  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18002ebe2  mov     [rbp+arg_8], 0FFFFFFFFh
0x18002ebe9  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ebf0  cmp     rcx, rbx
0x18002ebf3  jz      short loc_18002EC16
0x18002ebf5  test    dword ptr [rcx+1Ch], 10000000h
0x18002ebfc  jz      short loc_18002EC16
0x18002ebfe  mov     rcx, [rcx+10h]
0x18002ec02  lea     r8, WPP_b1bfb7512cf23544267720d0f520c3da_Traceguids
0x18002ec09  mov     edx, 2Ah ; '*'
0x18002ec0e  mov     r9, rdi
0x18002ec11  call    WPP_SF_S
0x18002ec16  mov     rcx, rdi; lpFileName
0x18002ec19  call    cs:__imp_DeleteFileW
0x18002ec1f  test    eax, eax
0x18002ec21  jz      short loc_18002EC33
0x18002ec23  mov     eax, 527h
0x18002ec28  xor     ebx, ebx
0x18002ec2a  mov     [rbp+var_3C], ax
0x18002ec2e  mov     [rbp+var_40], ebx
0x18002ec31  jmp     short loc_18002ECAB
0x18002ec33  call    cs:__imp_GetLastError
0x18002ec39  cmp     eax, 2
0x18002ec3c  jnz     short loc_18002EC45
0x18002ec3e  mov     eax, 52Bh
0x18002ec43  jmp     short loc_18002EC28
0x18002ec45  lea     rdx, [rbp+arg_8]; unsigned int *
0x18002ec49  mov     rcx, rdi; lpFileName
0x18002ec4c  call    ?SxClearDifficultAttributes@@YAJPEBGPEAK@Z; SxClearDifficultAttributes(ushort const *,ulong *)
0x18002ec51  mov     ebx, eax
0x18002ec53  mov     [rbp+var_40], eax
0x18002ec56  test    eax, eax
0x18002ec58  mov     eax, 531h
0x18002ec5d  jns     short loc_18002EC68
0x18002ec5f  mov     edx, [rbp+arg_8]
0x18002ec62  mov     [rbp+var_3A], ax
0x18002ec66  jmp     short loc_18002EC9B
0x18002ec68  mov     rcx, rdi; lpFileName
0x18002ec6b  mov     [rbp+var_3C], ax
0x18002ec6f  call    cs:__imp_DeleteFileW
0x18002ec75  test    eax, eax
0x18002ec77  jnz     short loc_18002EC8A
0x18002ec79  call    GetLastFailureAsHRESULT
0x18002ec7e  mov     ebx, eax
0x18002ec80  mov     [rbp+var_40], eax
0x18002ec83  mov     eax, 536h
0x18002ec88  jmp     short loc_18002EC5F
0x18002ec8a  xor     ebx, ebx
0x18002ec8c  mov     eax, 536h
0x18002ec91  mov     [rbp+var_40], ebx
0x18002ec94  or      edx, 0FFFFFFFFh; unsigned int
0x18002ec97  mov     [rbp+var_3C], ax
0x18002ec9b  cmp     edx, 0FFFFFFFFh
0x18002ec9e  jz      short loc_18002ECAB
0x18002eca0  mov     rcx, rdi; lpFileName
0x18002eca3  call    ?SxSetFileAttributes@@YAJPEBGK@Z; SxSetFileAttributes(ushort const *,ulong)
0x18002eca8  mov     ebx, [rbp+var_40]
0x18002ecab  lea     rcx, [rbp+var_40]; this
0x18002ecaf  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18002ecb4  lea     r11, [rsp+60h+var_s0]
0x18002ecb9  mov     eax, ebx
0x18002ecbb  mov     rbx, [r11+10h]
0x18002ecbf  mov     rdi, [r11+20h]
0x18002ecc3  mov     rsp, r11
0x18002ecc6  pop     rbp
0x18002ecc7  retn
```
