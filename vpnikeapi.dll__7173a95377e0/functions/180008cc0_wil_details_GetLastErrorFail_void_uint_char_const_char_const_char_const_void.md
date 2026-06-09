# wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x180008cc0`
- end: `0x180008d21`
- name: `?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z`
- size: `97`
- prototype: `DWORD __fastcall(wil::details *this, void *, int, const char *, const char *, const char *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180006e14`
- `0x180006e94`
- `0x180008d28`

## callees

- `0x180006f5c`
- `0x180008cc0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008cd7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008cd7`

## pseudocode

```c
DWORD __fastcall wil::details::GetLastErrorFail(
        wil::details *this,
        void *a2,
        int a3,
        const char *a4,
        const char *a5,
        const char *a6)
{
  int v7; // edi
  int v8; // esi
  DWORD result; // eax
  wil::details *v10; // [rsp+30h] [rbp-18h]

  v7 = (int)a2;
  v8 = (int)this;
  result = GetLastError();
  if ( !result )
  {
    LODWORD(v10) = -2147024228;
    wil::details::ReportFailure_Hr<2>(v8, v7, a3, 0, 0, (__int64)a6, v10);
    return 668;
  }
  return result;
}

```

## disassembly

```asm
0x180008cc0  mov     [rsp+arg_0], rbx
0x180008cc5  mov     [rsp+arg_8], rsi
0x180008cca  push    rdi
0x180008ccb  sub     rsp, 40h
0x180008ccf  mov     rbx, r8
0x180008cd2  mov     edi, edx
0x180008cd4  mov     rsi, rcx
0x180008cd7  call    cs:__imp_GetLastError
0x180008cdd  test    eax, eax
0x180008cdf  jnz     short loc_180008D11
0x180008ce1  mov     rax, [rsp+48h+arg_28]
0x180008ce6  xor     r9d, r9d; int
0x180008ce9  mov     dword ptr [rsp+48h+var_18], 8007029Ch; wil::details *
0x180008cf1  mov     r8, rbx; int
0x180008cf4  mov     [rsp+48h+var_20], rax; __int64
0x180008cf9  mov     edx, edi; int
0x180008cfb  mov     rcx, rsi; int
0x180008cfe  mov     [rsp+48h+var_28], 0; __int64
0x180008d07  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180008d0c  mov     eax, 29Ch
0x180008d11  mov     rbx, [rsp+48h+arg_0]
0x180008d16  mov     rsi, [rsp+48h+arg_8]
0x180008d1b  add     rsp, 40h
0x180008d1f  pop     rdi
0x180008d20  retn
```
