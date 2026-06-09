# wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x180003e90`
- end: `0x180003ef1`
- name: `?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z`
- size: `97`
- prototype: `DWORD __fastcall(wil::details *this, void *, int, const char *, const char *, const char *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180002c24`
- `0x180002c98`
- `0x180003ef8`
- `0x1800080ac`

## callees

- `0x180002d74`
- `0x180003e90`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003ea7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003ea7`

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
0x180003e90  mov     [rsp+arg_0], rbx
0x180003e95  mov     [rsp+arg_8], rsi
0x180003e9a  push    rdi
0x180003e9b  sub     rsp, 40h
0x180003e9f  mov     rbx, r8
0x180003ea2  mov     edi, edx
0x180003ea4  mov     rsi, rcx
0x180003ea7  call    cs:__imp_GetLastError
0x180003ead  test    eax, eax
0x180003eaf  jnz     short loc_180003EE1
0x180003eb1  mov     dword ptr [rsp+48h+var_18], 8007029Ch; wil::details *
0x180003eb9  mov     rax, [rsp+48h+arg_28]
0x180003ebe  mov     [rsp+48h+var_20], rax; __int64
0x180003ec3  mov     [rsp+48h+var_28], 0; __int64
0x180003ecc  xor     r9d, r9d; int
0x180003ecf  mov     r8, rbx; int
0x180003ed2  mov     edx, edi; int
0x180003ed4  mov     rcx, rsi; int
0x180003ed7  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180003edc  mov     eax, 29Ch
0x180003ee1  mov     rbx, [rsp+48h+arg_0]
0x180003ee6  mov     rsi, [rsp+48h+arg_8]
0x180003eeb  add     rsp, 40h
0x180003eef  pop     rdi
0x180003ef0  retn
```
