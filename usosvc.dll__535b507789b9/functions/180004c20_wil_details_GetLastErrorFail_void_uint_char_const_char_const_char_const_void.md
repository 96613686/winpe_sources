# wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x180004c20`
- end: `0x180004c81`
- name: `?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z`
- size: `97`
- prototype: `DWORD __fastcall(wil::details *this, void *, __int64, const char *, const char *, const char *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800032a4`
- `0x180006ea0`
- `0x180006f18`

## callees

- `0x18000341c`
- `0x180004c20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004c37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004c37`

## pseudocode

```c
DWORD __fastcall wil::details::GetLastErrorFail(
        wil::details *this,
        void *a2,
        __int64 a3,
        const char *a4,
        const char *a5,
        const char *a6)
{
  int v7; // edi
  DWORD result; // eax
  wil::details *v10; // [rsp+30h] [rbp-18h]

  v7 = (int)a2;
  result = GetLastError();
  if ( !result )
  {
    LODWORD(v10) = -2147024228;
    wil::details::ReportFailure_Hr<2>((__int64)this, v7, a3, 0, 0, (__int64)a6, v10);
    return 668;
  }
  return result;
}

```

## disassembly

```asm
0x180004c20  mov     [rsp+arg_0], rbx
0x180004c25  mov     [rsp+arg_8], rsi
0x180004c2a  push    rdi
0x180004c2b  sub     rsp, 40h
0x180004c2f  mov     rbx, r8
0x180004c32  mov     edi, edx
0x180004c34  mov     rsi, rcx
0x180004c37  call    cs:__imp_GetLastError
0x180004c3d  test    eax, eax
0x180004c3f  jnz     short loc_180004C71
0x180004c41  mov     dword ptr [rsp+48h+var_18], 8007029Ch; wil::details *
0x180004c49  mov     rax, [rsp+48h+arg_28]
0x180004c4e  mov     [rsp+48h+var_20], rax; __int64
0x180004c53  mov     [rsp+48h+var_28], 0; __int64
0x180004c5c  xor     r9d, r9d; int
0x180004c5f  mov     r8, rbx; int
0x180004c62  mov     edx, edi; int
0x180004c64  mov     rcx, rsi; int
0x180004c67  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180004c6c  mov     eax, 29Ch
0x180004c71  mov     rbx, [rsp+48h+arg_0]
0x180004c76  mov     rsi, [rsp+48h+arg_8]
0x180004c7b  add     rsp, 40h
0x180004c7f  pop     rdi
0x180004c80  retn
```
