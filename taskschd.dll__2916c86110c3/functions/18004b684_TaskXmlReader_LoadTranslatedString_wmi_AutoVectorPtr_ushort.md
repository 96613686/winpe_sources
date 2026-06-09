# TaskXmlReader::LoadTranslatedString(wmi::AutoVectorPtr<ushort> &)

- ea: `0x18004b684`
- end: `0x18004b8df`
- name: `?LoadTranslatedString@TaskXmlReader@@SAJAEAV?$AutoVectorPtr@G@wmi@@@Z`
- size: `603`
- prototype: `__int64 __fastcall(const wchar_t **)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, loader_planting, service_task`

## callers

- `0x180015f60`

## callees

- `0x180007aa0`
- `0x180009a78`
- `0x1800226d0`
- `0x180030d7c`
- `0x18004b568`
- `0x18004b684`

## import_xrefs

- `msvcrt!_wtol` at `0x18004b7cc`
- `msvcrt!_wtol` at `0x18004b7cc`
- `msvcrt!wcschr` at `0x18004b6e4`
- `msvcrt!wcschr` at `0x18004b6f5`
- `msvcrt!wcschr` at `0x18004b6e4`
- `msvcrt!wcschr` at `0x18004b6f5`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18004b841`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18004b841`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18004b890`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18004b890`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18004b82e`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18004b82e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x18004b684  push    rbx
0x18004b686  push    rbp
0x18004b687  push    rsi
0x18004b688  push    rdi
0x18004b689  push    r12
0x18004b68b  push    r13
0x18004b68d  push    r14
0x18004b68f  push    r15
0x18004b691  sub     rsp, 28h
0x18004b695  mov     r14, rcx
0x18004b698  mov     rcx, [rcx]; Str
0x18004b69b  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18004b69f  xor     r12d, r12d
0x18004b6a2  inc     rdi
0x18004b6a5  cmp     [rcx+rdi*2], r12w
0x18004b6aa  jnz     short loc_18004B6A2
0x18004b6ac  cmp     edi, 8
0x18004b6af  jb      loc_18004B80C
0x18004b6b5  mov     eax, 24h ; '$'
0x18004b6ba  cmp     ax, [rcx]
0x18004b6bd  jnz     loc_18004B80C
0x18004b6c3  mov     eax, 28h ; '('
0x18004b6c8  cmp     ax, [rcx+2]
0x18004b6cc  jnz     loc_18004B80C
0x18004b6d2  mov     eax, 40h ; '@'
0x18004b6d7  cmp     ax, [rcx+4]
0x18004b6db  jnz     loc_18004B80C
0x18004b6e1  lea     edx, [rax-14h]; Ch
0x18004b6e4  call    cs:__imp_wcschr
0x18004b6ea  mov     rbx, rax
0x18004b6ed  mov     edx, 2Dh ; '-'; Ch
0x18004b6f2  mov     rcx, [r14]; Str
0x18004b6f5  call    cs:__imp_wcschr
0x18004b6fb  mov     r15, rax
0x18004b6fe  test    rbx, rbx
0x18004b701  jz      loc_18004B80C
0x18004b707  test    rax, rax
0x18004b70a  jz      loc_18004B80C
0x18004b710  mov     rcx, rax
0x18004b713  sub     rcx, rbx
0x18004b716  mov     r13d, 2
0x18004b71c  cmp     rcx, r13
0x18004b71f  jnz     loc_18004B80C
0x18004b725  sub     rbx, [r14]
0x18004b728  sar     rbx, 1
0x18004b72b  lea     rsi, [rbx-3]
0x18004b72f  lea     rbp, [rsi+1]
0x18004b733  mov     eax, r13d
0x18004b736  mul     rbp
0x18004b739  lea     rcx, [r13-3]
0x18004b73d  cmovb   rax, rcx
0x18004b741  mov     rcx, rax; unsigned __int64
0x18004b744  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004b749  mov     rbx, rax
0x18004b74c  mov     [rsp+68h+arg_8], rax
0x18004b751  test    rax, rax
0x18004b754  jnz     short loc_18004B75D
0x18004b756  xor     ecx, ecx
0x18004b758  jmp     loc_18004B807
0x18004b75d  mov     r8, [r14]
0x18004b760  add     r8, 6; unsigned __int16 *
0x18004b764  mov     r9, rsi; unsigned __int64
0x18004b767  mov     rdx, rbp; unsigned __int64
0x18004b76a  mov     rcx, rbx; unsigned __int16 *
0x18004b76d  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18004b772  test    eax, eax
0x18004b774  js      loc_18004B804
0x18004b77a  mov     rax, r15
0x18004b77d  sub     rax, [r14]
0x18004b780  sar     rax, 1
0x18004b783  mov     ebp, edi
0x18004b785  sub     rbp, rax
0x18004b788  lea     rdi, [rbp+1]
0x18004b78c  mov     rax, r13
0x18004b78f  mul     rdi
0x18004b792  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18004b799  cmovb   rax, rcx
0x18004b79d  mov     rcx, rax; unsigned __int64
0x18004b7a0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004b7a5  mov     rsi, rax
0x18004b7a8  mov     [rsp+68h+arg_10], rax
0x18004b7b0  lea     r8, [r15+2]; unsigned __int16 *
0x18004b7b4  mov     r9, rbp; unsigned __int64
0x18004b7b7  mov     rdx, rdi; unsigned __int64
0x18004b7ba  mov     rcx, rax; unsigned __int16 *
0x18004b7bd  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18004b7c2  mov     r13d, eax
0x18004b7c5  test    eax, eax
0x18004b7c7  js      short loc_18004B7FB
0x18004b7c9  mov     rcx, rsi; String
0x18004b7cc  call    cs:__imp__wtol
0x18004b7d2  mov     r12d, eax
0x18004b7d5  test    eax, eax
0x18004b7d7  jz      short loc_18004B7FB
0x18004b7d9  mov     ecx, 208h; unsigned __int64
0x18004b7de  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004b7e3  mov     rdi, rax
0x18004b7e6  mov     [rsp+68h+arg_18], rax
0x18004b7ee  test    rax, rax
0x18004b7f1  jnz     short loc_18004B822
0x18004b7f3  xor     ecx, ecx; void *
0x18004b7f5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004b7fa  nop
0x18004b7fb  mov     rcx, rsi; void *
0x18004b7fe  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004b803  nop
0x18004b804  mov     rcx, rbx; void *
0x18004b807  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004b80c  mov     eax, 1
0x18004b811  add     rsp, 28h
0x18004b815  pop     r15
0x18004b817  pop     r14
0x18004b819  pop     r13
0x18004b81b  pop     r12
0x18004b81d  pop     rdi
0x18004b81e  pop     rsi
0x18004b81f  pop     rbp
0x18004b820  pop     rbx
0x18004b821  retn
0x18004b822  mov     r8d, 103h; nSize
0x18004b828  mov     rdx, rdi; lpDst
0x18004b82b  mov     rcx, rbx; lpSrc
0x18004b82e  call    cs:__imp_ExpandEnvironmentStringsW
0x18004b834  test    eax, eax
0x18004b836  jz      short loc_18004B879
0x18004b838  xor     edx, edx; hFile
0x18004b83a  lea     r8d, [rdx+2]; dwFlags
0x18004b83e  mov     rcx, rdi; lpLibFileName
0x18004b841  call    cs:__imp_LoadLibraryExW
0x18004b847  mov     r15, rax
0x18004b84a  test    rax, rax
0x18004b84d  jz      short loc_18004B879
0x18004b84f  mov     [rsp+68h+arg_0], rax
0x18004b854  mov     ecx, 0A000h; unsigned __int64
0x18004b859  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004b85e  mov     rbp, rax
0x18004b861  test    rax, rax
0x18004b864  jnz     short loc_18004B881
0x18004b866  xor     ecx, ecx; void *
0x18004b868  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004b86d  nop
0x18004b86e  lea     rcx, [rsp+68h+arg_0]; this
0x18004b873  call    ??1LibLock@tsched@@QEAA@XZ; tsched::LibLock::~LibLock(void)
0x18004b878  nop
0x18004b879  mov     rcx, rdi
0x18004b87c  jmp     loc_18004B7F5
0x18004b881  mov     r9d, 4FFFh; cchBufferMax
0x18004b887  mov     r8, rbp; lpBuffer
0x18004b88a  mov     edx, r12d; uID
0x18004b88d  mov     rcx, r15; hInstance
0x18004b890  call    cs:__imp_LoadStringW
0x18004b896  test    eax, eax
0x18004b898  jnz     short loc_18004B89F
0x18004b89a  mov     rcx, rbp
0x18004b89d  jmp     short loc_18004B868
0x18004b89f  mov     rdx, rbp
0x18004b8a2  mov     rcx, r14
0x18004b8a5  call    ??4?$AutoVectorPtr@G@wmi@@QEAAAEAV01@PEAG@Z; wmi::AutoVectorPtr<ushort>::operator=(ushort *)
0x18004b8aa  xor     ecx, ecx; void *
0x18004b8ac  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004b8b1  nop
0x18004b8b2  lea     rcx, [rsp+68h+arg_0]; this
0x18004b8b7  call    ??1LibLock@tsched@@QEAA@XZ; tsched::LibLock::~LibLock(void)
0x18004b8bc  nop
0x18004b8bd  mov     rcx, rdi; void *
0x18004b8c0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004b8c5  nop
0x18004b8c6  mov     rcx, rsi; void *
0x18004b8c9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004b8ce  nop
0x18004b8cf  mov     rcx, rbx; void *
0x18004b8d2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004b8d7  mov     eax, r13d
0x18004b8da  jmp     loc_18004B811
```
