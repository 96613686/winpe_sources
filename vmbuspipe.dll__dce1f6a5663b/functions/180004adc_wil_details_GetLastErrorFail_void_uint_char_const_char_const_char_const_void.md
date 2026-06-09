# wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x180004adc`
- end: `0x180004b3d`
- name: `?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z`
- size: `97`
- prototype: `unsigned int __usercall@<eax>(wil::details *__hidden this@<rcx>, void *@<rdx>, unsigned int@<r8d>, const char *@<r9>, const char *, const char *, void *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1800031dc`
- `0x180003254`
- `0x1800032d8`
- `0x180004b44`

## callees

- `0x1800033c4`
- `0x180004adc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004af3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004af3`

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
0x180004adc  mov     [rsp+arg_0], rbx
0x180004ae1  mov     [rsp+arg_8], rsi
0x180004ae6  push    rdi
0x180004ae7  sub     rsp, 40h
0x180004aeb  mov     rbx, r8
0x180004aee  mov     edi, edx
0x180004af0  mov     rsi, rcx
0x180004af3  call    cs:__imp_GetLastError
0x180004af9  test    eax, eax
0x180004afb  jnz     short loc_180004B2D
0x180004afd  mov     dword ptr [rsp+48h+var_18], 8007029Ch; wil::details *
0x180004b05  mov     rax, [rsp+48h+arg_28]
0x180004b0a  mov     [rsp+48h+var_20], rax; __int64
0x180004b0f  mov     [rsp+48h+var_28], 0; __int64
0x180004b18  xor     r9d, r9d; int
0x180004b1b  mov     r8, rbx; int
0x180004b1e  mov     edx, edi; int
0x180004b20  mov     rcx, rsi; int
0x180004b23  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180004b28  mov     eax, 29Ch
0x180004b2d  mov     rbx, [rsp+48h+arg_0]
0x180004b32  mov     rsi, [rsp+48h+arg_8]
0x180004b37  add     rsp, 40h
0x180004b3b  pop     rdi
0x180004b3c  retn
```
