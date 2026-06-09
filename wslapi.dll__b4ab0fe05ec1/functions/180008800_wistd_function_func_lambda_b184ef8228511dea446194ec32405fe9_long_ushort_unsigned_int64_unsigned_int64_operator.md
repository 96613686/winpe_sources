# wistd::__function::__func<_lambda_b184ef8228511dea446194ec32405fe9_,long (ushort *,unsigned __int64,unsigned __int64 *)>::operator()(ushort * &&,unsigned __int64 &&,unsigned __int64 * &&)

- ea: `0x180008800`
- end: `0x180008855`
- name: `??R?$__func@V_lambda_b184ef8228511dea446194ec32405fe9_@@$$A6AJPEAG_KPEA_K@Z@__function@wistd@@UEAAJ$$QEAPEAG$$QEA_K$$QEAPEA_K@Z`
- size: `85`
- prototype: `__int64 __fastcall(__int64, LPWSTR *, unsigned __int64 *, _QWORD **)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180004fb4`
- `0x180008800`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180008815`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180008815`

## string_xrefs

- `0x18000882a`: `onecore\internal\sdk\inc\wil\opensource\wil\win32_helpers.h`

## pseudocode

```c
__int64 __fastcall wistd::__function::__func<_lambda_b184ef8228511dea446194ec32405fe9_,long (unsigned short *,unsigned __int64,unsigned __int64 *)>::operator()(
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
0x180008800  mov     [rsp+arg_0], rbx
0x180008805  push    rdi
0x180008806  sub     rsp, 20h
0x18000880a  mov     rbx, [r8]
0x18000880d  mov     rcx, [rdx]; lpBuffer
0x180008810  mov     edx, ebx; uSize
0x180008812  mov     rdi, [r9]
0x180008815  call    cs:__imp_GetSystemDirectoryW
0x18000881b  mov     eax, eax
0x18000881d  mov     [rdi], rax
0x180008820  test    rax, rax
0x180008823  jnz     short loc_18000883D
0x180008825  mov     rcx, [rsp+28h]; this
0x18000882a  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180008831  mov     edx, 230h; void *
0x180008836  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000883b  jmp     short loc_18000884A
0x18000883d  cmp     rax, rbx
0x180008840  jnb     short loc_180008848
0x180008842  inc     rax
0x180008845  mov     [rdi], rax
0x180008848  xor     eax, eax
0x18000884a  mov     rbx, [rsp+28h+arg_0]
0x18000884f  add     rsp, 20h
0x180008853  pop     rdi
0x180008854  retn
```
