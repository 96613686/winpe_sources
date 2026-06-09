# TaskXmlReader::LoadTranslatedString(wmi::AutoVectorPtr<ushort> &)

- ea: `0x18001f1a8`
- end: `0x18001f428`
- name: `?LoadTranslatedString@TaskXmlReader@@SAJAEAV?$AutoVectorPtr@G@wmi@@@Z`
- size: `640`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, loader_planting, service_task`

## callers

- `0x18002096c`

## callees

- `0x180005224`
- `0x180007988`
- `0x180007994`
- `0x18000edd8`
- `0x18001e628`
- `0x18001f1a8`

## import_xrefs

- `msvcrt!_wtol` at `0x18001f2fc`
- `msvcrt!_wtol` at `0x18001f2fc`
- `msvcrt!wcschr` at `0x18001f208`
- `msvcrt!wcschr` at `0x18001f21f`
- `msvcrt!wcschr` at `0x18001f208`
- `msvcrt!wcschr` at `0x18001f21f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001f37e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001f37e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18001f3d3`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18001f3d3`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18001f365`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18001f365`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall TaskXmlReader::LoadTranslatedString(const wchar_t **a1)
{
  const wchar_t *v2; // rcx
  __int64 v3; // rdi
  wchar_t *v4; // rbx
  wchar_t *v5; // rax
  wchar_t *v6; // r15
  unsigned __int64 v7; // rsi
  unsigned __int16 *v8; // rax
  WCHAR *v9; // rbx
  WCHAR *v10; // rcx
  unsigned __int64 v11; // rbp
  unsigned __int16 *v12; // rsi
  int v13; // r13d
  UINT v14; // r12d
  WCHAR *v15; // rax
  WCHAR *v16; // rdi
  WCHAR *v17; // rcx
  HMODULE Library; // rax
  HINSTANCE v20; // r15
  WCHAR *v21; // rax
  WCHAR *v22; // rbp
  WCHAR *v23; // rcx
  HMODULE v24; // [rsp+70h] [rbp+8h] BYREF
  unsigned __int16 *v25; // [rsp+78h] [rbp+10h]
  unsigned __int16 *v26; // [rsp+80h] [rbp+18h]
  WCHAR *v27; // [rsp+88h] [rbp+20h]

  v2 = *a1;
  v3 = -1;
  do
    ++v3;
  while ( v2[v3] );
  if ( (unsigned int)v3 < 8 )
    return 1;
  if ( *v2 != 36 )
    return 1;
  if ( v2[1] != 40 )
    return 1;
  if ( v2[2] != 64 )
    return 1;
  v4 = wcschr(v2, 0x2Cu);
  v5 = wcschr(*a1, 0x2Du);
  v6 = v5;
  if ( !v4 || !v5 || (char *)v5 - (char *)v4 != 2 )
    return 1;
  v7 = v4 - *a1 - 3;
  v8 = (unsigned __int16 *)operator new[](saturated_mul(v7 + 1, 2u));
  v9 = v8;
  v25 = v8;
  if ( !v8 )
  {
    v10 = 0;
LABEL_20:
    operator delete(v10);
    return 1;
  }
  if ( (int)StringCchCopyNW(v8, v7 + 1, *a1 + 3, v7) < 0 )
  {
LABEL_19:
    v10 = v9;
    goto LABEL_20;
  }
  v11 = (unsigned int)v3 - (v6 - *a1);
  v12 = (unsigned __int16 *)operator new[](saturated_mul(v11 + 1, 2u));
  v26 = v12;
  v13 = StringCchCopyNW(v12, v11 + 1, v6 + 1, v11);
  if ( v13 < 0 || (v14 = _wtol(v12)) == 0 )
  {
LABEL_18:
    operator delete(v12);
    goto LABEL_19;
  }
  v15 = (WCHAR *)operator new[](0x208u);
  v16 = v15;
  v27 = v15;
  if ( !v15 )
  {
    v17 = 0;
LABEL_17:
    operator delete(v17);
    goto LABEL_18;
  }
  if ( !ExpandEnvironmentStringsW(v9, v15, 0x103u) || (Library = LoadLibraryExW(v16, 0, 2u), (v20 = Library) == 0) )
  {
LABEL_27:
    v17 = v16;
    goto LABEL_17;
  }
  v24 = Library;
  v21 = (WCHAR *)operator new[](0xA000u);
  v22 = v21;
  if ( !v21 )
  {
    v23 = 0;
LABEL_26:
    operator delete(v23);
    tsched::LibLock::~LibLock((tsched::LibLock *)&v24);
    goto LABEL_27;
  }
  if ( !LoadStringW(v20, v14, v21, 20479) )
  {
    v23 = v22;
    goto LABEL_26;
  }
  wmi::AutoVectorPtr<unsigned char>::operator=(a1, v22);
  operator delete(0);
  tsched::LibLock::~LibLock((tsched::LibLock *)&v24);
  operator delete(v16);
  operator delete(v12);
  operator delete(v9);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18001f1a8  push    rbx
0x18001f1aa  push    rbp
0x18001f1ab  push    rsi
0x18001f1ac  push    rdi
0x18001f1ad  push    r12
0x18001f1af  push    r13
0x18001f1b1  push    r14
0x18001f1b3  push    r15
0x18001f1b5  sub     rsp, 28h
0x18001f1b9  mov     r14, rcx
0x18001f1bc  mov     rcx, [rcx]; Str
0x18001f1bf  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18001f1c3  xor     r12d, r12d
0x18001f1c6  inc     rdi
0x18001f1c9  cmp     [rcx+rdi*2], r12w
0x18001f1ce  jnz     short loc_18001F1C6
0x18001f1d0  cmp     edi, 8
0x18001f1d3  jb      loc_18001F342
0x18001f1d9  mov     eax, 24h ; '$'
0x18001f1de  cmp     ax, [rcx]
0x18001f1e1  jnz     loc_18001F342
0x18001f1e7  mov     eax, 28h ; '('
0x18001f1ec  cmp     ax, [rcx+2]
0x18001f1f0  jnz     loc_18001F342
0x18001f1f6  mov     eax, 40h ; '@'
0x18001f1fb  cmp     ax, [rcx+4]
0x18001f1ff  jnz     loc_18001F342
0x18001f205  lea     edx, [rax-14h]; Ch
0x18001f208  call    cs:__imp_wcschr
0x18001f20f  nop     dword ptr [rax+rax+00h]
0x18001f214  mov     rbx, rax
0x18001f217  mov     edx, 2Dh ; '-'; Ch
0x18001f21c  mov     rcx, [r14]; Str
0x18001f21f  call    cs:__imp_wcschr
0x18001f226  nop     dword ptr [rax+rax+00h]
0x18001f22b  mov     r15, rax
0x18001f22e  test    rbx, rbx
0x18001f231  jz      loc_18001F342
0x18001f237  test    rax, rax
0x18001f23a  jz      loc_18001F342
0x18001f240  mov     rcx, rax
0x18001f243  sub     rcx, rbx
0x18001f246  mov     r13d, 2
0x18001f24c  cmp     rcx, r13
0x18001f24f  jnz     loc_18001F342
0x18001f255  sub     rbx, [r14]
0x18001f258  sar     rbx, 1
0x18001f25b  lea     rsi, [rbx-3]
0x18001f25f  lea     rbp, [rsi+1]
0x18001f263  mov     eax, r13d
0x18001f266  mul     rbp
0x18001f269  lea     rcx, [r13-3]
0x18001f26d  cmovb   rax, rcx
0x18001f271  mov     rcx, rax; unsigned __int64
0x18001f274  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001f279  mov     rbx, rax
0x18001f27c  mov     [rsp+68h+arg_8], rax
0x18001f281  test    rax, rax
0x18001f284  jnz     short loc_18001F28D
0x18001f286  xor     ecx, ecx
0x18001f288  jmp     loc_18001F33D
0x18001f28d  mov     r8, [r14]
0x18001f290  add     r8, 6; unsigned __int16 *
0x18001f294  mov     r9, rsi; unsigned __int64
0x18001f297  mov     rdx, rbp; unsigned __int64
0x18001f29a  mov     rcx, rbx; unsigned __int16 *
0x18001f29d  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18001f2a2  test    eax, eax
0x18001f2a4  js      loc_18001F33A
0x18001f2aa  mov     rax, r15
0x18001f2ad  sub     rax, [r14]
0x18001f2b0  sar     rax, 1
0x18001f2b3  mov     ebp, edi
0x18001f2b5  sub     rbp, rax
0x18001f2b8  lea     rdi, [rbp+1]
0x18001f2bc  mov     rax, r13
0x18001f2bf  mul     rdi
0x18001f2c2  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18001f2c9  cmovb   rax, rcx
0x18001f2cd  mov     rcx, rax; unsigned __int64
0x18001f2d0  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001f2d5  mov     rsi, rax
0x18001f2d8  mov     [rsp+68h+arg_10], rax
0x18001f2e0  lea     r8, [r15+2]; unsigned __int16 *
0x18001f2e4  mov     r9, rbp; unsigned __int64
0x18001f2e7  mov     rdx, rdi; unsigned __int64
0x18001f2ea  mov     rcx, rax; unsigned __int16 *
0x18001f2ed  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18001f2f2  mov     r13d, eax
0x18001f2f5  test    eax, eax
0x18001f2f7  js      short loc_18001F331
0x18001f2f9  mov     rcx, rsi; String
0x18001f2fc  call    cs:__imp__wtol
0x18001f303  nop     dword ptr [rax+rax+00h]
0x18001f308  mov     r12d, eax
0x18001f30b  test    eax, eax
0x18001f30d  jz      short loc_18001F331
0x18001f30f  mov     ecx, 208h; unsigned __int64
0x18001f314  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001f319  mov     rdi, rax
0x18001f31c  mov     [rsp+68h+arg_18], rax
0x18001f324  test    rax, rax
0x18001f327  jnz     short loc_18001F359
0x18001f329  xor     ecx, ecx; Block
0x18001f32b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001f330  nop
0x18001f331  mov     rcx, rsi; Block
0x18001f334  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001f339  nop
0x18001f33a  mov     rcx, rbx; Block
0x18001f33d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001f342  mov     eax, 1
0x18001f347  add     rsp, 28h
0x18001f34b  pop     r15
0x18001f34d  pop     r14
0x18001f34f  pop     r13
0x18001f351  pop     r12
0x18001f353  pop     rdi
0x18001f354  pop     rsi
0x18001f355  pop     rbp
0x18001f356  pop     rbx
0x18001f357  retn
0x18001f359  mov     r8d, 103h; nSize
0x18001f35f  mov     rdx, rdi; lpDst
0x18001f362  mov     rcx, rbx; lpSrc
0x18001f365  call    cs:__imp_ExpandEnvironmentStringsW
0x18001f36c  nop     dword ptr [rax+rax+00h]
0x18001f371  test    eax, eax
0x18001f373  jz      short loc_18001F3BC
0x18001f375  xor     edx, edx; hFile
0x18001f377  lea     r8d, [rdx+2]; dwFlags
0x18001f37b  mov     rcx, rdi; lpLibFileName
0x18001f37e  call    cs:__imp_LoadLibraryExW
0x18001f385  nop     dword ptr [rax+rax+00h]
0x18001f38a  mov     r15, rax
0x18001f38d  test    rax, rax
0x18001f390  jz      short loc_18001F3BC
0x18001f392  mov     [rsp+68h+arg_0], rax
0x18001f397  mov     ecx, 0A000h; unsigned __int64
0x18001f39c  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001f3a1  mov     rbp, rax
0x18001f3a4  test    rax, rax
0x18001f3a7  jnz     short loc_18001F3C4
0x18001f3a9  xor     ecx, ecx; Block
0x18001f3ab  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001f3b0  nop
0x18001f3b1  lea     rcx, [rsp+68h+arg_0]; this
0x18001f3b6  call    ??1LibLock@tsched@@QEAA@XZ; tsched::LibLock::~LibLock(void)
0x18001f3bb  nop
0x18001f3bc  mov     rcx, rdi
0x18001f3bf  jmp     loc_18001F32B
0x18001f3c4  mov     r9d, 4FFFh; cchBufferMax
0x18001f3ca  mov     r8, rbp; lpBuffer
0x18001f3cd  mov     edx, r12d; uID
0x18001f3d0  mov     rcx, r15; hInstance
0x18001f3d3  call    cs:__imp_LoadStringW
0x18001f3da  nop     dword ptr [rax+rax+00h]
0x18001f3df  test    eax, eax
0x18001f3e1  jnz     short loc_18001F3E8
0x18001f3e3  mov     rcx, rbp
0x18001f3e6  jmp     short loc_18001F3AB
0x18001f3e8  mov     rdx, rbp
0x18001f3eb  mov     rcx, r14
0x18001f3ee  call    ??4?$AutoVectorPtr@E@wmi@@QEAAAEAV01@PEAE@Z; wmi::AutoVectorPtr<uchar>::operator=(uchar *)
0x18001f3f3  xor     ecx, ecx; Block
0x18001f3f5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001f3fa  nop
0x18001f3fb  lea     rcx, [rsp+68h+arg_0]; this
0x18001f400  call    ??1LibLock@tsched@@QEAA@XZ; tsched::LibLock::~LibLock(void)
0x18001f405  nop
0x18001f406  mov     rcx, rdi; Block
0x18001f409  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001f40e  nop
0x18001f40f  mov     rcx, rsi; Block
0x18001f412  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001f417  nop
0x18001f418  mov     rcx, rbx; Block
0x18001f41b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001f420  mov     eax, r13d
0x18001f423  jmp     loc_18001F347
```
