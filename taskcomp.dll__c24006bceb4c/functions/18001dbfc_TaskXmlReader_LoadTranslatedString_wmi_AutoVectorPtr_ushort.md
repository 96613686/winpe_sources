# TaskXmlReader::LoadTranslatedString(wmi::AutoVectorPtr<ushort> &)

- ea: `0x18001dbfc`
- end: `0x18001de57`
- name: `?LoadTranslatedString@TaskXmlReader@@SAJAEAV?$AutoVectorPtr@G@wmi@@@Z`
- size: `603`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, loader_planting, service_task`

## callers

- `0x18001f380`

## callees

- `0x180004f88`
- `0x1800074c8`
- `0x1800074d4`
- `0x18000e4d8`
- `0x18001d0ac`
- `0x18001dbfc`

## import_xrefs

- `msvcrt!_wtol` at `0x18001dd44`
- `msvcrt!_wtol` at `0x18001dd44`
- `msvcrt!wcschr` at `0x18001dc5c`
- `msvcrt!wcschr` at `0x18001dc6d`
- `msvcrt!wcschr` at `0x18001dc5c`
- `msvcrt!wcschr` at `0x18001dc6d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001ddb9`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001ddb9`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18001de08`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18001de08`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18001dda6`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18001dda6`

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
  wmi::AutoVectorPtr<unsigned char>::operator=((void **)a1, v22);
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
0x18001dbfc  push    rbx
0x18001dbfe  push    rbp
0x18001dbff  push    rsi
0x18001dc00  push    rdi
0x18001dc01  push    r12
0x18001dc03  push    r13
0x18001dc05  push    r14
0x18001dc07  push    r15
0x18001dc09  sub     rsp, 28h
0x18001dc0d  mov     r14, rcx
0x18001dc10  mov     rcx, [rcx]; Str
0x18001dc13  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18001dc17  xor     r12d, r12d
0x18001dc1a  inc     rdi
0x18001dc1d  cmp     [rcx+rdi*2], r12w
0x18001dc22  jnz     short loc_18001DC1A
0x18001dc24  cmp     edi, 8
0x18001dc27  jb      loc_18001DD84
0x18001dc2d  mov     eax, 24h ; '$'
0x18001dc32  cmp     ax, [rcx]
0x18001dc35  jnz     loc_18001DD84
0x18001dc3b  mov     eax, 28h ; '('
0x18001dc40  cmp     ax, [rcx+2]
0x18001dc44  jnz     loc_18001DD84
0x18001dc4a  mov     eax, 40h ; '@'
0x18001dc4f  cmp     ax, [rcx+4]
0x18001dc53  jnz     loc_18001DD84
0x18001dc59  lea     edx, [rax-14h]; Ch
0x18001dc5c  call    cs:__imp_wcschr
0x18001dc62  mov     rbx, rax
0x18001dc65  mov     edx, 2Dh ; '-'; Ch
0x18001dc6a  mov     rcx, [r14]; Str
0x18001dc6d  call    cs:__imp_wcschr
0x18001dc73  mov     r15, rax
0x18001dc76  test    rbx, rbx
0x18001dc79  jz      loc_18001DD84
0x18001dc7f  test    rax, rax
0x18001dc82  jz      loc_18001DD84
0x18001dc88  mov     rcx, rax
0x18001dc8b  sub     rcx, rbx
0x18001dc8e  mov     r13d, 2
0x18001dc94  cmp     rcx, r13
0x18001dc97  jnz     loc_18001DD84
0x18001dc9d  sub     rbx, [r14]
0x18001dca0  sar     rbx, 1
0x18001dca3  lea     rsi, [rbx-3]
0x18001dca7  lea     rbp, [rsi+1]
0x18001dcab  mov     eax, r13d
0x18001dcae  mul     rbp
0x18001dcb1  lea     rcx, [r13-3]
0x18001dcb5  cmovb   rax, rcx
0x18001dcb9  mov     rcx, rax; unsigned __int64
0x18001dcbc  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001dcc1  mov     rbx, rax
0x18001dcc4  mov     [rsp+68h+arg_8], rax
0x18001dcc9  test    rax, rax
0x18001dccc  jnz     short loc_18001DCD5
0x18001dcce  xor     ecx, ecx
0x18001dcd0  jmp     loc_18001DD7F
0x18001dcd5  mov     r8, [r14]
0x18001dcd8  add     r8, 6; unsigned __int16 *
0x18001dcdc  mov     r9, rsi; unsigned __int64
0x18001dcdf  mov     rdx, rbp; unsigned __int64
0x18001dce2  mov     rcx, rbx; unsigned __int16 *
0x18001dce5  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18001dcea  test    eax, eax
0x18001dcec  js      loc_18001DD7C
0x18001dcf2  mov     rax, r15
0x18001dcf5  sub     rax, [r14]
0x18001dcf8  sar     rax, 1
0x18001dcfb  mov     ebp, edi
0x18001dcfd  sub     rbp, rax
0x18001dd00  lea     rdi, [rbp+1]
0x18001dd04  mov     rax, r13
0x18001dd07  mul     rdi
0x18001dd0a  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18001dd11  cmovb   rax, rcx
0x18001dd15  mov     rcx, rax; unsigned __int64
0x18001dd18  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001dd1d  mov     rsi, rax
0x18001dd20  mov     [rsp+68h+arg_10], rax
0x18001dd28  lea     r8, [r15+2]; unsigned __int16 *
0x18001dd2c  mov     r9, rbp; unsigned __int64
0x18001dd2f  mov     rdx, rdi; unsigned __int64
0x18001dd32  mov     rcx, rax; unsigned __int16 *
0x18001dd35  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18001dd3a  mov     r13d, eax
0x18001dd3d  test    eax, eax
0x18001dd3f  js      short loc_18001DD73
0x18001dd41  mov     rcx, rsi; String
0x18001dd44  call    cs:__imp__wtol
0x18001dd4a  mov     r12d, eax
0x18001dd4d  test    eax, eax
0x18001dd4f  jz      short loc_18001DD73
0x18001dd51  mov     ecx, 208h; unsigned __int64
0x18001dd56  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001dd5b  mov     rdi, rax
0x18001dd5e  mov     [rsp+68h+arg_18], rax
0x18001dd66  test    rax, rax
0x18001dd69  jnz     short loc_18001DD9A
0x18001dd6b  xor     ecx, ecx; Block
0x18001dd6d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001dd72  nop
0x18001dd73  mov     rcx, rsi; Block
0x18001dd76  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001dd7b  nop
0x18001dd7c  mov     rcx, rbx; Block
0x18001dd7f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001dd84  mov     eax, 1
0x18001dd89  add     rsp, 28h
0x18001dd8d  pop     r15
0x18001dd8f  pop     r14
0x18001dd91  pop     r13
0x18001dd93  pop     r12
0x18001dd95  pop     rdi
0x18001dd96  pop     rsi
0x18001dd97  pop     rbp
0x18001dd98  pop     rbx
0x18001dd99  retn
0x18001dd9a  mov     r8d, 103h; nSize
0x18001dda0  mov     rdx, rdi; lpDst
0x18001dda3  mov     rcx, rbx; lpSrc
0x18001dda6  call    cs:__imp_ExpandEnvironmentStringsW
0x18001ddac  test    eax, eax
0x18001ddae  jz      short loc_18001DDF1
0x18001ddb0  xor     edx, edx; hFile
0x18001ddb2  lea     r8d, [rdx+2]; dwFlags
0x18001ddb6  mov     rcx, rdi; lpLibFileName
0x18001ddb9  call    cs:__imp_LoadLibraryExW
0x18001ddbf  mov     r15, rax
0x18001ddc2  test    rax, rax
0x18001ddc5  jz      short loc_18001DDF1
0x18001ddc7  mov     [rsp+68h+arg_0], rax
0x18001ddcc  mov     ecx, 0A000h; unsigned __int64
0x18001ddd1  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001ddd6  mov     rbp, rax
0x18001ddd9  test    rax, rax
0x18001dddc  jnz     short loc_18001DDF9
0x18001ddde  xor     ecx, ecx; Block
0x18001dde0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001dde5  nop
0x18001dde6  lea     rcx, [rsp+68h+arg_0]; this
0x18001ddeb  call    ??1LibLock@tsched@@QEAA@XZ; tsched::LibLock::~LibLock(void)
0x18001ddf0  nop
0x18001ddf1  mov     rcx, rdi
0x18001ddf4  jmp     loc_18001DD6D
0x18001ddf9  mov     r9d, 4FFFh; cchBufferMax
0x18001ddff  mov     r8, rbp; lpBuffer
0x18001de02  mov     edx, r12d; uID
0x18001de05  mov     rcx, r15; hInstance
0x18001de08  call    cs:__imp_LoadStringW
0x18001de0e  test    eax, eax
0x18001de10  jnz     short loc_18001DE17
0x18001de12  mov     rcx, rbp
0x18001de15  jmp     short loc_18001DDE0
0x18001de17  mov     rdx, rbp
0x18001de1a  mov     rcx, r14
0x18001de1d  call    ??4?$AutoVectorPtr@E@wmi@@QEAAAEAV01@PEAE@Z; wmi::AutoVectorPtr<uchar>::operator=(uchar *)
0x18001de22  xor     ecx, ecx; Block
0x18001de24  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001de29  nop
0x18001de2a  lea     rcx, [rsp+68h+arg_0]; this
0x18001de2f  call    ??1LibLock@tsched@@QEAA@XZ; tsched::LibLock::~LibLock(void)
0x18001de34  nop
0x18001de35  mov     rcx, rdi; Block
0x18001de38  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001de3d  nop
0x18001de3e  mov     rcx, rsi; Block
0x18001de41  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001de46  nop
0x18001de47  mov     rcx, rbx; Block
0x18001de4a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001de4f  mov     eax, r13d
0x18001de52  jmp     loc_18001DD89
```
