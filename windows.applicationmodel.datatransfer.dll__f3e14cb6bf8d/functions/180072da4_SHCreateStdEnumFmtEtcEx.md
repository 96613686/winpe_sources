# SHCreateStdEnumFmtEtcEx

- ea: `0x180072da4`
- end: `0x180073067`
- name: `SHCreateStdEnumFmtEtcEx`
- size: `707`
- prototype: `__int64 __fastcall(size_t Count)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18002f0c0`

## callees

- `0x180072da4`
- `0x180081010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x180072e18`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x180072e18`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180072fa1`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180072fa1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180073021`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180073021`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18007303f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18007303f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180072e91`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180072f1e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180072e91`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180072f1e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180072ed5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180072ed5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007304e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007304e`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180073009`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180073009`
- `ext-ms-win-shell-shell32-l1-2-1!SHCreateStdEnumFmtEtc` at `0x180072ff3`
- `ext-ms-win-shell-shell32-l1-2-1!SHCreateStdEnumFmtEtc` at `0x180072ff3`

## string_xrefs

- `0x180073017`: `SHCreateStdEnumFmtEtc`
- `0x180073002`: `Windows.Storage.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SHCreateStdEnumFmtEtcEx(size_t Count, FORMATETC *a2, __int64 a3, IEnumFORMATETC **a4)
{
  IEnumFORMATETC **v4; // r12
  FORMATETC *v5; // rbx
  unsigned int v6; // r15d
  FORMATETC *v7; // rsi
  UINT v8; // r14d
  HRESULT v9; // edi
  char *v10; // rdi
  unsigned int v11; // r13d
  UINT i; // r12d
  __int64 v13; // rax
  char *v14; // rdx
  unsigned __int64 v15; // rax
  __int64 v16; // r15
  FORMATETC *v17; // rbx
  void *v18; // r8
  __int64 j; // rcx
  __int64 v20; // rax
  __int64 v21; // rdx
  __int64 v22; // rcx
  HMODULE LibraryW; // rax
  HMODULE v24; // rbx
  FARPROC ProcAddress; // rax
  void *Block; // [rsp+38h] [rbp-40h]
  __int64 v28; // [rsp+40h] [rbp-38h] BYREF
  LPVOID pv[2]; // [rsp+48h] [rbp-30h] BYREF
  __int128 v30; // [rsp+58h] [rbp-20h]
  unsigned int v31; // [rsp+C0h] [rbp+48h]
  int v33; // [rsp+D0h] [rbp+58h] BYREF
  IEnumFORMATETC **v34; // [rsp+D8h] [rbp+60h]

  v34 = a4;
  v31 = Count;
  v4 = a4;
  v5 = a2;
  v6 = Count;
  if ( !a3 )
    goto LABEL_38;
  v7 = 0;
  v8 = 0;
  v28 = 0;
  v9 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)a3 + 64LL))(a3, 1, &v28);
  if ( v9 >= 0 )
  {
    v33 = 0;
    *(_OWORD *)pv = 0;
    v30 = 0;
    v10 = (char *)calloc(v6, 4u);
    Block = v10;
    if ( !v10 )
    {
      v9 = -2147024882;
      goto LABEL_33;
    }
    v11 = v6;
    for ( i = 0; ; ++i )
    {
      v13 = (*(__int64 (__fastcall **)(__int64, __int64, LPVOID *, int *))(*(_QWORD *)v28 + 24LL))(v28, 1, pv, &v33);
      if ( (_DWORD)v13 )
        break;
      if ( v6 )
      {
        while ( 1 )
        {
          v14 = &v10[4 * v13];
          if ( !*(_DWORD *)v14 && v5[(unsigned int)v13].cfFormat == LOWORD(pv[0]) )
            break;
          v13 = (unsigned int)(v13 + 1);
          if ( (unsigned int)v13 >= v6 )
            goto LABEL_12;
        }
        *(_DWORD *)v14 = 1;
        --v11;
      }
LABEL_12:
      CoTaskMemFree(pv[1]);
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 40LL))(v28);
    v8 = i + v11;
    if ( i + v11 < v11 )
    {
      v8 = -1;
    }
    else
    {
      v15 = 32LL * v8;
      if ( v15 <= 0xFFFFFFFF )
      {
        v7 = (FORMATETC *)LocalAlloc(0x40u, (unsigned int)v15);
        if ( v7 )
        {
          v9 = 0;
          if ( i )
          {
            v16 = 0;
            do
            {
              v17 = &v7[v16];
              (*(void (__fastcall **)(__int64, __int64, FORMATETC *, int *))(*(_QWORD *)v28 + 24LL))(v28, 1, v17, &v33);
              CoTaskMemFree(v17->ptd);
              v17->ptd = 0;
              ++v9;
              ++v16;
            }
            while ( v9 < i );
            v9 = 0;
            v6 = v31;
            v5 = a2;
          }
          v18 = Block;
          if ( v11 )
          {
            for ( j = 0; (unsigned int)j < v6; j = (unsigned int)(j + 1) )
            {
              if ( !*((_DWORD *)Block + j) && i <= v8 )
              {
                v20 = i++;
                v21 = (unsigned int)j;
                *(_OWORD *)&v7[v20].cfFormat = *(_OWORD *)&v5[v21].cfFormat;
                *(_OWORD *)&v7[v20].dwAspect = *(_OWORD *)&v5[v21].dwAspect;
              }
            }
          }
          goto LABEL_31;
        }
        v9 = -2147024882;
LABEL_30:
        v18 = Block;
LABEL_31:
        free(v18);
        v4 = v34;
        goto LABEL_33;
      }
    }
    v9 = -2147024362;
    goto LABEL_30;
  }
LABEL_33:
  v22 = v28;
  if ( v28 )
  {
    v28 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
  }
  if ( v9 >= 0 )
    goto LABEL_39;
  if ( v9 == -2147024882 || v9 == -2147024362 )
    return (unsigned int)v9;
LABEL_38:
  v7 = v5;
  v8 = v6;
LABEL_39:
  v9 = SHCreateStdEnumFmtEtc(v8, v7, v4);
  if ( v9 == -2147467263 )
  {
    LibraryW = LoadLibraryW(L"Windows.Storage.dll");
    v24 = LibraryW;
    if ( LibraryW )
    {
      ProcAddress = GetProcAddress(LibraryW, "SHCreateStdEnumFmtEtc");
      if ( ProcAddress )
        v9 = ((__int64 (__fastcall *)(_QWORD, FORMATETC *, IEnumFORMATETC **))ProcAddress)(v8, v7, v4);
      FreeLibrary(v24);
    }
  }
  if ( v7 != a2 )
    LocalFree(v7);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180072da4  mov     [rsp-40h+arg_18], r9
0x180072da9  mov     [rsp-40h+arg_8], rdx
0x180072dae  mov     [rsp-40h+arg_0], ecx
0x180072db2  push    rbp
0x180072db3  push    rbx
0x180072db4  push    rsi
0x180072db5  push    rdi
0x180072db6  push    r12
0x180072db8  push    r13
0x180072dba  push    r14
0x180072dbc  push    r15
0x180072dbe  mov     rbp, rsp
0x180072dc1  sub     rsp, 78h
0x180072dc5  mov     r12, r9
0x180072dc8  mov     r10, r8
0x180072dcb  mov     rbx, rdx
0x180072dce  mov     r15d, ecx
0x180072dd1  test    r8, r8
0x180072dd4  jz      loc_180072FE4
0x180072dda  xor     esi, esi
0x180072ddc  xor     r14d, r14d
0x180072ddf  mov     [rbp+var_38], rsi
0x180072de3  mov     rax, [r8]
0x180072de6  lea     r8, [rbp+var_38]
0x180072dea  lea     edx, [rsi+1]
0x180072ded  mov     rcx, r10
0x180072df0  mov     rax, [rax+40h]
0x180072df4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072df9  mov     edi, eax
0x180072dfb  test    eax, eax
0x180072dfd  js      loc_180072FB2
0x180072e03  mov     [rbp+arg_10], r14d
0x180072e07  xorps   xmm0, xmm0
0x180072e0a  movups  xmmword ptr [rbp+pv], xmm0
0x180072e0e  movups  [rbp+var_20], xmm0
0x180072e12  mov     ecx, r15d; Count
0x180072e15  lea     edx, [rsi+4]; Size
0x180072e18  call    cs:__imp_calloc
0x180072e1e  mov     rdi, rax
0x180072e21  mov     [rbp+Block], rax
0x180072e25  test    rax, rax
0x180072e28  jz      loc_180072FAD
0x180072e2e  mov     r13d, r15d
0x180072e31  xor     r12d, r12d
0x180072e34  mov     r14d, 0FFFFFFFFh
0x180072e3a  mov     rcx, [rbp+var_38]
0x180072e3e  mov     rax, [rcx]
0x180072e41  lea     r9, [rbp+arg_10]
0x180072e45  lea     r8, [rbp+pv]
0x180072e49  mov     edx, 1
0x180072e4e  mov     rax, [rax+18h]
0x180072e52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072e57  test    eax, eax
0x180072e59  jnz     short loc_180072E9C
0x180072e5b  test    r15d, r15d
0x180072e5e  jz      short loc_180072E8D
0x180072e60  movzx   r8d, word ptr [rbp+pv]
0x180072e65  mov     ecx, eax
0x180072e67  lea     rdx, [rdi+rax*4]
0x180072e6b  cmp     dword ptr [rdx], 0
0x180072e6e  jnz     short loc_180072E7B
0x180072e70  shl     rcx, 5
0x180072e74  cmp     [rcx+rbx], r8w
0x180072e79  jz      short loc_180072E84
0x180072e7b  inc     eax
0x180072e7d  cmp     eax, r15d
0x180072e80  jb      short loc_180072E65
0x180072e82  jmp     short loc_180072E8D
0x180072e84  mov     dword ptr [rdx], 1
0x180072e8a  add     r13d, r14d
0x180072e8d  mov     rcx, [rbp+pv+8]; pv
0x180072e91  call    cs:__imp_CoTaskMemFree
0x180072e97  inc     r12d
0x180072e9a  jmp     short loc_180072E3A
0x180072e9c  mov     rcx, [rbp+var_38]
0x180072ea0  mov     rax, [rcx]
0x180072ea3  mov     rax, [rax+28h]
0x180072ea7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072eac  lea     r14d, [r12+r13]
0x180072eb0  cmp     r14d, r13d
0x180072eb3  jb      loc_180072F8F
0x180072eb9  mov     eax, r14d
0x180072ebc  shl     rax, 5
0x180072ec0  mov     ecx, 0FFFFFFFFh
0x180072ec5  cmp     rax, rcx
0x180072ec8  ja      loc_180072F95
0x180072ece  mov     edx, eax; uBytes
0x180072ed0  mov     ecx, 40h ; '@'; uFlags
0x180072ed5  call    cs:__imp_LocalAlloc
0x180072edb  mov     rsi, rax
0x180072ede  test    rax, rax
0x180072ee1  jz      loc_180072F88
0x180072ee7  xor     edi, edi
0x180072ee9  mov     [rbp+var_44], edi
0x180072eec  test    r12d, r12d
0x180072eef  jz      short loc_180072F41
0x180072ef1  xor     r15d, r15d
0x180072ef4  mov     rcx, [rbp+var_38]
0x180072ef8  mov     rbx, r15
0x180072efb  shl     rbx, 5
0x180072eff  add     rbx, rsi
0x180072f02  mov     rax, [rcx]
0x180072f05  lea     r9, [rbp+arg_10]
0x180072f09  mov     r8, rbx
0x180072f0c  mov     edx, 1
0x180072f11  mov     rax, [rax+18h]
0x180072f15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072f1a  mov     rcx, [rbx+8]; pv
0x180072f1e  call    cs:__imp_CoTaskMemFree
0x180072f24  mov     qword ptr [rbx+8], 0
0x180072f2c  inc     edi
0x180072f2e  inc     r15
0x180072f31  cmp     edi, r12d
0x180072f34  jb      short loc_180072EF4
0x180072f36  mov     edi, [rbp+var_44]
0x180072f39  mov     r15d, [rbp+arg_0]
0x180072f3d  mov     rbx, [rbp+arg_8]
0x180072f41  mov     r8, [rbp+Block]
0x180072f45  test    r13d, r13d
0x180072f48  jz      short loc_180072F9E
0x180072f4a  xor     ecx, ecx
0x180072f4c  test    r15d, r15d
0x180072f4f  jz      short loc_180072F9E
0x180072f51  mov     edx, ecx
0x180072f53  cmp     dword ptr [r8+rcx*4], 0
0x180072f58  jnz     short loc_180072F7F
0x180072f5a  cmp     r12d, r14d
0x180072f5d  ja      short loc_180072F7F
0x180072f5f  mov     eax, r12d
0x180072f62  shl     rax, 5
0x180072f66  inc     r12d
0x180072f69  shl     rdx, 5
0x180072f6d  movups  xmm0, xmmword ptr [rdx+rbx]
0x180072f71  movups  xmmword ptr [rax+rsi], xmm0
0x180072f75  movups  xmm1, xmmword ptr [rdx+rbx+10h]
0x180072f7a  movups  xmmword ptr [rax+rsi+10h], xmm1
0x180072f7f  inc     ecx
0x180072f81  cmp     ecx, r15d
0x180072f84  jb      short loc_180072F51
0x180072f86  jmp     short loc_180072F9E
0x180072f88  mov     edi, 8007000Eh
0x180072f8d  jmp     short loc_180072F9A
0x180072f8f  mov     r14d, 0FFFFFFFFh
0x180072f95  mov     edi, 80070216h
0x180072f9a  mov     r8, [rbp+Block]
0x180072f9e  mov     rcx, r8; Block
0x180072fa1  call    cs:__imp_free
0x180072fa7  mov     r12, [rbp+arg_18]
0x180072fab  jmp     short loc_180072FB2
0x180072fad  mov     edi, 8007000Eh
0x180072fb2  mov     rcx, [rbp+var_38]
0x180072fb6  test    rcx, rcx
0x180072fb9  jz      short loc_180072FD0
0x180072fbb  mov     [rbp+var_38], 0
0x180072fc3  mov     rax, [rcx]
0x180072fc6  mov     rax, [rax+10h]
0x180072fca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072fcf  nop
0x180072fd0  test    edi, edi
0x180072fd2  jns     short loc_180072FEA
0x180072fd4  cmp     edi, 8007000Eh
0x180072fda  jz      short loc_180073054
0x180072fdc  cmp     edi, 80070216h
0x180072fe2  jz      short loc_180073054
0x180072fe4  mov     rsi, rbx
0x180072fe7  mov     r14d, r15d
0x180072fea  mov     r8, r12; ppenumFormatEtc
0x180072fed  mov     rdx, rsi; afmt
0x180072ff0  mov     ecx, r14d; cfmt
0x180072ff3  call    cs:__imp_SHCreateStdEnumFmtEtc
0x180072ff9  mov     edi, eax
0x180072ffb  cmp     eax, 80004001h
0x180073000  jnz     short loc_180073045
0x180073002  lea     rcx, aWindowsStorage; "Windows.Storage.dll"
0x180073009  call    cs:__imp_LoadLibraryW
0x18007300f  mov     rbx, rax
0x180073012  test    rax, rax
0x180073015  jz      short loc_180073045
0x180073017  lea     rdx, aShcreatestdenu_0; "SHCreateStdEnumFmtEtc"
0x18007301e  mov     rcx, rax; hModule
0x180073021  call    cs:__imp_GetProcAddress
0x180073027  test    rax, rax
0x18007302a  jz      short loc_18007303C
0x18007302c  mov     r8, r12
0x18007302f  mov     rdx, rsi
0x180073032  mov     ecx, r14d
0x180073035  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007303a  mov     edi, eax
0x18007303c  mov     rcx, rbx; hLibModule
0x18007303f  call    cs:__imp_FreeLibrary
0x180073045  cmp     rsi, [rbp+arg_8]
0x180073049  jz      short loc_180073054
0x18007304b  mov     rcx, rsi; hMem
0x18007304e  call    cs:__imp_LocalFree
0x180073054  mov     eax, edi
0x180073056  add     rsp, 78h
0x18007305a  pop     r15
0x18007305c  pop     r14
0x18007305e  pop     r13
0x180073060  pop     r12
0x180073062  pop     rdi
0x180073063  pop     rsi
0x180073064  pop     rbx
0x180073065  pop     rbp
0x180073066  retn
```
