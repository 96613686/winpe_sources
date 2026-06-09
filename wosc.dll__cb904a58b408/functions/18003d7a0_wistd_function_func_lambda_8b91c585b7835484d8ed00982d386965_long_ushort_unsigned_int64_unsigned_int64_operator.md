# wistd::__function::__func<_lambda_8b91c585b7835484d8ed00982d386965_,long (ushort *,unsigned __int64,unsigned __int64 *)>::operator()(ushort * &&,unsigned __int64 &&,unsigned __int64 * &&)

- ea: `0x18003d7a0`
- end: `0x18003d802`
- name: `??R?$__func@V_lambda_8b91c585b7835484d8ed00982d386965_@@$$A6AJPEAG_KPEA_K@Z@__function@wistd@@UEAAJ$$QEAPEAG$$QEA_K$$QEAPEA_K@Z`
- size: `98`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18001e06c`
- `0x18003d7a0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18003d7c2`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18003d7c2`

## string_xrefs

- `0x18003d7d7`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`

## pseudocode

```c
__int64 __fastcall wistd::__function::__func<_lambda_8b91c585b7835484d8ed00982d386965_,long (unsigned short *,unsigned __int64,unsigned __int64 *)>::operator()(
        __int64 a1,
        LPWSTR *a2,
        unsigned __int64 *a3,
        _QWORD **a4)
{
  unsigned __int64 v4; // rbx
  _QWORD *v5; // rdi
  DWORD FullPathNameW; // eax
  const char *v7; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v4 = *a3;
  v5 = *a4;
  FullPathNameW = GetFullPathNameW(**(LPCWSTR **)(a1 + 8), *a3, *a2, 0);
  *v5 = FullPathNameW;
  if ( !FullPathNameW )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0xAA,
             (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/filesystem.h",
             v7);
  if ( FullPathNameW < v4 )
    *v5 = FullPathNameW + 1LL;
  return 0;
}

```

## disassembly

```asm
0x18003d7a0  mov     [rsp+arg_0], rbx
0x18003d7a5  push    rdi
0x18003d7a6  sub     rsp, 20h
0x18003d7aa  mov     rbx, [r8]
0x18003d7ad  mov     rax, rdx
0x18003d7b0  mov     rcx, [rcx+8]
0x18003d7b4  mov     edx, ebx; nBufferLength
0x18003d7b6  mov     rdi, [r9]
0x18003d7b9  xor     r9d, r9d; lpFilePart
0x18003d7bc  mov     r8, [rax]; lpBuffer
0x18003d7bf  mov     rcx, [rcx]; lpFileName
0x18003d7c2  call    cs:__imp_GetFullPathNameW
0x18003d7c8  mov     eax, eax
0x18003d7ca  mov     [rdi], rax
0x18003d7cd  test    rax, rax
0x18003d7d0  jnz     short loc_18003D7EA
0x18003d7d2  mov     rcx, [rsp+28h]; this
0x18003d7d7  lea     r8, aOnecoreInterna_6; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18003d7de  mov     edx, 0AAh; void *
0x18003d7e3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003d7e8  jmp     short loc_18003D7F7
0x18003d7ea  cmp     rax, rbx
0x18003d7ed  jnb     short loc_18003D7F5
0x18003d7ef  inc     rax
0x18003d7f2  mov     [rdi], rax
0x18003d7f5  xor     eax, eax
0x18003d7f7  mov     rbx, [rsp+28h+arg_0]
0x18003d7fc  add     rsp, 20h
0x18003d800  pop     rdi
0x18003d801  retn
```
