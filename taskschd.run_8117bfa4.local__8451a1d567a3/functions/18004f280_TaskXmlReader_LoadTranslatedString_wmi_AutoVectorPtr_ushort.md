# TaskXmlReader::LoadTranslatedString(wmi::AutoVectorPtr<ushort> &)

- ea: `0x18004f280`
- end: `0x18004f500`
- name: `?LoadTranslatedString@TaskXmlReader@@SAJAEAV?$AutoVectorPtr@G@wmi@@@Z`
- size: `640`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, loader_planting, service_task`

## callers

- `0x1800170a0`

## callees

- `0x180007e90`
- `0x18000a460`
- `0x180024300`
- `0x1800336f8`
- `0x18004f15c`
- `0x18004f280`

## import_xrefs

- `msvcrt!_wtol` at `0x18004f3d4`
- `msvcrt!_wtol` at `0x18004f3d4`
- `msvcrt!wcschr` at `0x18004f2e0`
- `msvcrt!wcschr` at `0x18004f2f7`
- `msvcrt!wcschr` at `0x18004f2e0`
- `msvcrt!wcschr` at `0x18004f2f7`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18004f456`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18004f456`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18004f4ab`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18004f4ab`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18004f43d`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18004f43d`

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
  v8 = (unsigned __int16 *)operator new(saturated_mul(v7 + 1, 2u));
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
  v12 = (unsigned __int16 *)operator new(saturated_mul(v11 + 1, 2u));
  v26 = v12;
  v13 = StringCchCopyNW(v12, v11 + 1, v6 + 1, v11);
  if ( v13 < 0 || (v14 = _wtol(v12)) == 0 )
  {
LABEL_18:
    operator delete(v12);
    goto LABEL_19;
  }
  v15 = (WCHAR *)operator new(0x208u);
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
  v21 = (WCHAR *)operator new(0xA000u);
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
  wmi::AutoVectorPtr<unsigned short>::operator=(a1, v22);
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
0x18004f280  push    rbx
0x18004f282  push    rbp
0x18004f283  push    rsi
0x18004f284  push    rdi
0x18004f285  push    r12
0x18004f287  push    r13
0x18004f289  push    r14
0x18004f28b  push    r15
0x18004f28d  sub     rsp, 28h
0x18004f291  mov     r14, rcx
0x18004f294  mov     rcx, [rcx]; Str
0x18004f297  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18004f29b  xor     r12d, r12d
0x18004f29e  inc     rdi
0x18004f2a1  cmp     [rcx+rdi*2], r12w
0x18004f2a6  jnz     short loc_18004F29E
0x18004f2a8  cmp     edi, 8
0x18004f2ab  jb      loc_18004F41A
0x18004f2b1  mov     eax, 24h ; '$'
0x18004f2b6  cmp     ax, [rcx]
0x18004f2b9  jnz     loc_18004F41A
0x18004f2bf  mov     eax, 28h ; '('
0x18004f2c4  cmp     ax, [rcx+2]
0x18004f2c8  jnz     loc_18004F41A
0x18004f2ce  mov     eax, 40h ; '@'
0x18004f2d3  cmp     ax, [rcx+4]
0x18004f2d7  jnz     loc_18004F41A
0x18004f2dd  lea     edx, [rax-14h]; Ch
0x18004f2e0  call    cs:__imp_wcschr
0x18004f2e7  nop     dword ptr [rax+rax+00h]
0x18004f2ec  mov     rbx, rax
0x18004f2ef  mov     edx, 2Dh ; '-'; Ch
0x18004f2f4  mov     rcx, [r14]; Str
0x18004f2f7  call    cs:__imp_wcschr
0x18004f2fe  nop     dword ptr [rax+rax+00h]
0x18004f303  mov     r15, rax
0x18004f306  test    rbx, rbx
0x18004f309  jz      loc_18004F41A
0x18004f30f  test    rax, rax
0x18004f312  jz      loc_18004F41A
0x18004f318  mov     rcx, rax
0x18004f31b  sub     rcx, rbx
0x18004f31e  mov     r13d, 2
0x18004f324  cmp     rcx, r13
0x18004f327  jnz     loc_18004F41A
0x18004f32d  sub     rbx, [r14]
0x18004f330  sar     rbx, 1
0x18004f333  lea     rsi, [rbx-3]
0x18004f337  lea     rbp, [rsi+1]
0x18004f33b  mov     eax, r13d
0x18004f33e  mul     rbp
0x18004f341  lea     rcx, [r13-3]
0x18004f345  cmovb   rax, rcx
0x18004f349  mov     rcx, rax; unsigned __int64
0x18004f34c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004f351  mov     rbx, rax
0x18004f354  mov     [rsp+68h+arg_8], rax
0x18004f359  test    rax, rax
0x18004f35c  jnz     short loc_18004F365
0x18004f35e  xor     ecx, ecx
0x18004f360  jmp     loc_18004F415
0x18004f365  mov     r8, [r14]
0x18004f368  add     r8, 6; unsigned __int16 *
0x18004f36c  mov     r9, rsi; unsigned __int64
0x18004f36f  mov     rdx, rbp; unsigned __int64
0x18004f372  mov     rcx, rbx; unsigned __int16 *
0x18004f375  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18004f37a  test    eax, eax
0x18004f37c  js      loc_18004F412
0x18004f382  mov     rax, r15
0x18004f385  sub     rax, [r14]
0x18004f388  sar     rax, 1
0x18004f38b  mov     ebp, edi
0x18004f38d  sub     rbp, rax
0x18004f390  lea     rdi, [rbp+1]
0x18004f394  mov     rax, r13
0x18004f397  mul     rdi
0x18004f39a  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18004f3a1  cmovb   rax, rcx
0x18004f3a5  mov     rcx, rax; unsigned __int64
0x18004f3a8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004f3ad  mov     rsi, rax
0x18004f3b0  mov     [rsp+68h+arg_10], rax
0x18004f3b8  lea     r8, [r15+2]; unsigned __int16 *
0x18004f3bc  mov     r9, rbp; unsigned __int64
0x18004f3bf  mov     rdx, rdi; unsigned __int64
0x18004f3c2  mov     rcx, rax; unsigned __int16 *
0x18004f3c5  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18004f3ca  mov     r13d, eax
0x18004f3cd  test    eax, eax
0x18004f3cf  js      short loc_18004F409
0x18004f3d1  mov     rcx, rsi; String
0x18004f3d4  call    cs:__imp__wtol
0x18004f3db  nop     dword ptr [rax+rax+00h]
0x18004f3e0  mov     r12d, eax
0x18004f3e3  test    eax, eax
0x18004f3e5  jz      short loc_18004F409
0x18004f3e7  mov     ecx, 208h; unsigned __int64
0x18004f3ec  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004f3f1  mov     rdi, rax
0x18004f3f4  mov     [rsp+68h+arg_18], rax
0x18004f3fc  test    rax, rax
0x18004f3ff  jnz     short loc_18004F431
0x18004f401  xor     ecx, ecx; void *
0x18004f403  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004f408  nop
0x18004f409  mov     rcx, rsi; void *
0x18004f40c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004f411  nop
0x18004f412  mov     rcx, rbx; void *
0x18004f415  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004f41a  mov     eax, 1
0x18004f41f  add     rsp, 28h
0x18004f423  pop     r15
0x18004f425  pop     r14
0x18004f427  pop     r13
0x18004f429  pop     r12
0x18004f42b  pop     rdi
0x18004f42c  pop     rsi
0x18004f42d  pop     rbp
0x18004f42e  pop     rbx
0x18004f42f  retn
0x18004f431  mov     r8d, 103h; nSize
0x18004f437  mov     rdx, rdi; lpDst
0x18004f43a  mov     rcx, rbx; lpSrc
0x18004f43d  call    cs:__imp_ExpandEnvironmentStringsW
0x18004f444  nop     dword ptr [rax+rax+00h]
0x18004f449  test    eax, eax
0x18004f44b  jz      short loc_18004F494
0x18004f44d  xor     edx, edx; hFile
0x18004f44f  lea     r8d, [rdx+2]; dwFlags
0x18004f453  mov     rcx, rdi; lpLibFileName
0x18004f456  call    cs:__imp_LoadLibraryExW
0x18004f45d  nop     dword ptr [rax+rax+00h]
0x18004f462  mov     r15, rax
0x18004f465  test    rax, rax
0x18004f468  jz      short loc_18004F494
0x18004f46a  mov     [rsp+68h+arg_0], rax
0x18004f46f  mov     ecx, 0A000h; unsigned __int64
0x18004f474  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004f479  mov     rbp, rax
0x18004f47c  test    rax, rax
0x18004f47f  jnz     short loc_18004F49C
0x18004f481  xor     ecx, ecx; void *
0x18004f483  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004f488  nop
0x18004f489  lea     rcx, [rsp+68h+arg_0]; this
0x18004f48e  call    ??1LibLock@tsched@@QEAA@XZ; tsched::LibLock::~LibLock(void)
0x18004f493  nop
0x18004f494  mov     rcx, rdi
0x18004f497  jmp     loc_18004F403
0x18004f49c  mov     r9d, 4FFFh; cchBufferMax
0x18004f4a2  mov     r8, rbp; lpBuffer
0x18004f4a5  mov     edx, r12d; uID
0x18004f4a8  mov     rcx, r15; hInstance
0x18004f4ab  call    cs:__imp_LoadStringW
0x18004f4b2  nop     dword ptr [rax+rax+00h]
0x18004f4b7  test    eax, eax
0x18004f4b9  jnz     short loc_18004F4C0
0x18004f4bb  mov     rcx, rbp
0x18004f4be  jmp     short loc_18004F483
0x18004f4c0  mov     rdx, rbp
0x18004f4c3  mov     rcx, r14
0x18004f4c6  call    ??4?$AutoVectorPtr@G@wmi@@QEAAAEAV01@PEAG@Z; wmi::AutoVectorPtr<ushort>::operator=(ushort *)
0x18004f4cb  xor     ecx, ecx; void *
0x18004f4cd  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004f4d2  nop
0x18004f4d3  lea     rcx, [rsp+68h+arg_0]; this
0x18004f4d8  call    ??1LibLock@tsched@@QEAA@XZ; tsched::LibLock::~LibLock(void)
0x18004f4dd  nop
0x18004f4de  mov     rcx, rdi; void *
0x18004f4e1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004f4e6  nop
0x18004f4e7  mov     rcx, rsi; void *
0x18004f4ea  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004f4ef  nop
0x18004f4f0  mov     rcx, rbx; void *
0x18004f4f3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004f4f8  mov     eax, r13d
0x18004f4fb  jmp     loc_18004F41F
```
