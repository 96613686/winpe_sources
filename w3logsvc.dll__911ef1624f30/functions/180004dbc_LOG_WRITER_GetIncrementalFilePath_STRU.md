# LOG_WRITER::GetIncrementalFilePath(STRU *)

- ea: `0x180004dbc`
- end: `0x180004f1d`
- name: `?GetIncrementalFilePath@LOG_WRITER@@AEAAJPEAVSTRU@@@Z`
- size: `353`
- prototype: `__int64 __fastcall(LOG_WRITER *__hidden this, struct STRU *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180005458`

## callees

- `0x180004dbc`
- `0x180004f24`
- `0x18000e9a0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180004e40`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180004e40`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004e55`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004e84`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004eda`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004ef0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004e55`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004e84`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004eda`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004ef0`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180004ec9`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180004ec9`

## pseudocode

```c
__int64 __fastcall LOG_WRITER::GetIncrementalFilePath(LOG_WRITER *this, struct STRU *a2)
{
  unsigned int v2; // r9d
  WCHAR *v3; // rbx
  int v6; // r14d
  unsigned int v7; // esi
  int IncrementalFilePath; // edi
  const unsigned __int16 *v9; // rdx
  LPCWSTR lpFileName; // [rsp+30h] [rbp-30h] BYREF
  unsigned __int16 v12[8]; // [rsp+38h] [rbp-28h] BYREF
  __int64 v13; // [rsp+48h] [rbp-18h]

  v2 = *((_DWORD *)this + 156);
  v3 = 0;
  lpFileName = 0;
  v13 = 0;
  *(_OWORD *)v12 = 0;
  if ( v2 )
  {
    IncrementalFilePath = LOG_WRITER::GetIncrementalFilePath(this, a2, v12, v2, (unsigned __int16 **)&lpFileName);
    if ( IncrementalFilePath >= 0 )
    {
      v9 = lpFileName;
LABEL_18:
      IncrementalFilePath = STRU::Copy(a2, v9);
    }
  }
  else
  {
    v6 = 1;
    v7 = 1;
    while ( 1 )
    {
      IncrementalFilePath = LOG_WRITER::GetIncrementalFilePath(this, a2, v12, v7, (unsigned __int16 **)&lpFileName);
      if ( IncrementalFilePath < 0 )
        break;
      if ( GetFileAttributesW(lpFileName) == -1 )
      {
        if ( v3 )
        {
          if ( lpFileName )
            LocalFree((HLOCAL)lpFileName);
          v9 = v3;
          lpFileName = v3;
          v3 = 0;
          v6 = v7 - 1;
        }
        else
        {
          v9 = lpFileName;
        }
        *((_DWORD *)this + 156) = v6;
        if ( !v9 )
        {
LABEL_15:
          IncrementalFilePath = -2147467259;
          goto LABEL_21;
        }
        goto LABEL_18;
      }
      if ( v3 )
        LocalFree(v3);
      v3 = (WCHAR *)lpFileName;
      ++v7;
      lpFileName = 0;
      if ( v7 == -1 )
        goto LABEL_15;
    }
  }
  if ( lpFileName )
  {
    LocalFree((HLOCAL)lpFileName);
    lpFileName = 0;
  }
LABEL_21:
  if ( v3 )
    LocalFree(v3);
  return (unsigned int)IncrementalFilePath;
}

```

## disassembly

```asm
0x180004dbc  mov     [rsp-28h+arg_10], rbx
0x180004dc1  mov     [rsp-28h+arg_18], rsi
0x180004dc6  push    rbp
0x180004dc7  push    rdi
0x180004dc8  push    r12
0x180004dca  push    r14
0x180004dcc  push    r15
0x180004dce  mov     rbp, rsp
0x180004dd1  sub     rsp, 60h
0x180004dd5  mov     rax, cs:__security_cookie
0x180004ddc  xor     rax, rsp
0x180004ddf  mov     [rbp+var_10], rax
0x180004de3  mov     r9d, [rcx+270h]; unsigned int
0x180004dea  xor     eax, eax
0x180004dec  xor     ebx, ebx
0x180004dee  mov     [rbp+lpFileName], 0
0x180004df6  mov     [rbp+var_18], rax
0x180004dfa  xorps   xmm0, xmm0
0x180004dfd  mov     r12, rdx
0x180004e00  mov     r15, rcx
0x180004e03  movups  xmmword ptr [rbp+var_28], xmm0
0x180004e07  test    r9d, r9d
0x180004e0a  jnz     loc_180004EAA
0x180004e10  lea     r14d, [rax+1]
0x180004e14  mov     esi, r14d
0x180004e17  lea     rax, [rbp+lpFileName]
0x180004e1b  mov     r9d, esi; unsigned int
0x180004e1e  lea     r8, [rbp+var_28]; unsigned __int16 *
0x180004e22  mov     [rsp+60h+var_40], rax; unsigned __int16 **
0x180004e27  mov     rdx, r12; struct STRU *
0x180004e2a  mov     rcx, r15; this
0x180004e2d  call    ?GetIncrementalFilePath@LOG_WRITER@@AEAAJPEAVSTRU@@PEAGKPEAPEAG@Z; LOG_WRITER::GetIncrementalFilePath(STRU *,ushort *,ulong,ushort * *)
0x180004e32  mov     edi, eax
0x180004e34  test    eax, eax
0x180004e36  js      loc_180004ED1
0x180004e3c  mov     rcx, [rbp+lpFileName]; lpFileName
0x180004e40  call    cs:__imp_GetFileAttributesW
0x180004e46  or      edi, 0FFFFFFFFh
0x180004e49  cmp     eax, edi
0x180004e4b  jz      short loc_180004E70
0x180004e4d  test    rbx, rbx
0x180004e50  jz      short loc_180004E5B
0x180004e52  mov     rcx, rbx; hMem
0x180004e55  call    cs:__imp_LocalFree
0x180004e5b  mov     rbx, [rbp+lpFileName]
0x180004e5f  add     esi, r14d
0x180004e62  mov     [rbp+lpFileName], 0
0x180004e6a  cmp     esi, edi
0x180004e6c  jb      short loc_180004E17
0x180004e6e  jmp     short loc_180004EA3
0x180004e70  test    rbx, rbx
0x180004e73  jnz     short loc_180004E7B
0x180004e75  mov     rdx, [rbp+lpFileName]
0x180004e79  jmp     short loc_180004E97
0x180004e7b  mov     rcx, [rbp+lpFileName]; hMem
0x180004e7f  test    rcx, rcx
0x180004e82  jz      short loc_180004E8A
0x180004e84  call    cs:__imp_LocalFree
0x180004e8a  mov     rdx, rbx; struct STRU *
0x180004e8d  mov     [rbp+lpFileName], rbx
0x180004e91  xor     ebx, ebx
0x180004e93  lea     r14d, [rsi-1]
0x180004e97  mov     [r15+270h], r14d
0x180004e9e  test    rdx, rdx
0x180004ea1  jnz     short loc_180004EC6
0x180004ea3  mov     edi, 80004005h
0x180004ea8  jmp     short loc_180004EE8
0x180004eaa  lea     rax, [rbp+lpFileName]
0x180004eae  lea     r8, [rbp+var_28]; unsigned __int16 *
0x180004eb2  mov     [rsp+60h+var_40], rax; unsigned __int16 **
0x180004eb7  call    ?GetIncrementalFilePath@LOG_WRITER@@AEAAJPEAVSTRU@@PEAGKPEAPEAG@Z; LOG_WRITER::GetIncrementalFilePath(STRU *,ushort *,ulong,ushort * *)
0x180004ebc  mov     edi, eax
0x180004ebe  test    eax, eax
0x180004ec0  js      short loc_180004ED1
0x180004ec2  mov     rdx, [rbp+lpFileName]
0x180004ec6  mov     rcx, r12
0x180004ec9  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180004ecf  mov     edi, eax
0x180004ed1  mov     rcx, [rbp+lpFileName]; hMem
0x180004ed5  test    rcx, rcx
0x180004ed8  jz      short loc_180004EE8
0x180004eda  call    cs:__imp_LocalFree
0x180004ee0  mov     [rbp+lpFileName], 0
0x180004ee8  test    rbx, rbx
0x180004eeb  jz      short loc_180004EF6
0x180004eed  mov     rcx, rbx; hMem
0x180004ef0  call    cs:__imp_LocalFree
0x180004ef6  mov     eax, edi
0x180004ef8  mov     rcx, [rbp+var_10]
0x180004efc  xor     rcx, rsp; StackCookie
0x180004eff  call    __security_check_cookie
0x180004f04  lea     r11, [rsp+60h+var_s0]
0x180004f09  mov     rbx, [r11+40h]
0x180004f0d  mov     rsi, [r11+48h]
0x180004f11  mov     rsp, r11
0x180004f14  pop     r15
0x180004f16  pop     r14
0x180004f18  pop     r12
0x180004f1a  pop     rdi
0x180004f1b  pop     rbp
0x180004f1c  retn
```
