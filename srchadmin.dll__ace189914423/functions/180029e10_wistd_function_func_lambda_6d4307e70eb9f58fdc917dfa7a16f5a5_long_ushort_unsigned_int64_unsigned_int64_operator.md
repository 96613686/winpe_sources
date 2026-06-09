# wistd::__function::__func<_lambda_6d4307e70eb9f58fdc917dfa7a16f5a5_,long (ushort *,unsigned __int64,unsigned __int64 *)>::operator()(ushort * &&,unsigned __int64 &&,unsigned __int64 * &&)

- ea: `0x180029e10`
- end: `0x180029e65`
- name: `??R?$__func@V_lambda_6d4307e70eb9f58fdc917dfa7a16f5a5_@@$$A6AJPEAG_KPEA_K@Z@__function@wistd@@UEAAJ$$QEAPEAG$$QEA_K$$QEAPEA_K@Z`
- size: `85`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180008fd4`
- `0x180029e10`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180029e25`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180029e25`

## string_xrefs

- `0x180029e3a`: `onecore\internal\sdk\inc\wil\opensource\wil\win32_helpers.h`

## pseudocode

```c
__int64 __fastcall wistd::__function::__func<_lambda_6d4307e70eb9f58fdc917dfa7a16f5a5_,long (unsigned short *,unsigned __int64,unsigned __int64 *)>::operator()(
        __int64 a1,
        LPWSTR *a2,
        unsigned __int64 *a3,
        _QWORD **a4)
{
  unsigned __int64 v4; // rbx
  _QWORD *v5; // rdi
  UINT SystemDirectoryW; // eax
  const char *v7; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v4 = *a3;
  v5 = *a4;
  SystemDirectoryW = GetSystemDirectoryW(*a2, *a3);
  *v5 = SystemDirectoryW;
  if ( !SystemDirectoryW )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x230,
             (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\win32_helpers.h",
             v7);
  if ( SystemDirectoryW < v4 )
    *v5 = SystemDirectoryW + 1LL;
  return 0;
}

```

## disassembly

```asm
0x180029e10  mov     [rsp+arg_0], rbx
0x180029e15  push    rdi
0x180029e16  sub     rsp, 20h
0x180029e1a  mov     rbx, [r8]
0x180029e1d  mov     rcx, [rdx]; lpBuffer
0x180029e20  mov     edx, ebx; uSize
0x180029e22  mov     rdi, [r9]
0x180029e25  call    cs:__imp_GetSystemDirectoryW
0x180029e2b  mov     eax, eax
0x180029e2d  mov     [rdi], rax
0x180029e30  test    rax, rax
0x180029e33  jnz     short loc_180029E4D
0x180029e35  mov     rcx, [rsp+28h]; this
0x180029e3a  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180029e41  mov     edx, 230h; void *
0x180029e46  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180029e4b  jmp     short loc_180029E5A
0x180029e4d  cmp     rax, rbx
0x180029e50  jnb     short loc_180029E58
0x180029e52  inc     rax
0x180029e55  mov     [rdi], rax
0x180029e58  xor     eax, eax
0x180029e5a  mov     rbx, [rsp+28h+arg_0]
0x180029e5f  add     rsp, 20h
0x180029e63  pop     rdi
0x180029e64  retn
```
