# wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x1800080d0`
- end: `0x180008138`
- name: `?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z`
- size: `104`
- prototype: `unsigned int __usercall@<eax>(wil::details *__hidden this@<rcx>, void *@<rdx>, unsigned int@<r8d>, const char *@<r9>, const char *, const char *, void *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180006cc4`
- `0x180006d3c`
- `0x180008140`

## callees

- `0x180006e0c`
- `0x1800080d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800080e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800080e7`

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
0x1800080d0  mov     [rsp+arg_0], rbx
0x1800080d5  mov     [rsp+arg_8], rsi
0x1800080da  push    rdi
0x1800080db  sub     rsp, 40h
0x1800080df  mov     rbx, r8
0x1800080e2  mov     edi, edx
0x1800080e4  mov     rsi, rcx
0x1800080e7  call    cs:__imp_GetLastError
0x1800080ee  nop     dword ptr [rax+rax+00h]
0x1800080f3  test    eax, eax
0x1800080f5  jnz     short loc_180008127
0x1800080f7  mov     dword ptr [rsp+48h+var_18], 8007029Ch; wil::details *
0x1800080ff  mov     rax, [rsp+48h+arg_28]
0x180008104  mov     [rsp+48h+var_20], rax; __int64
0x180008109  mov     [rsp+48h+var_28], 0; __int64
0x180008112  xor     r9d, r9d; int
0x180008115  mov     r8, rbx; int
0x180008118  mov     edx, edi; int
0x18000811a  mov     rcx, rsi; int
0x18000811d  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180008122  mov     eax, 29Ch
0x180008127  mov     rbx, [rsp+48h+arg_0]
0x18000812c  mov     rsi, [rsp+48h+arg_8]
0x180008131  add     rsp, 40h
0x180008135  pop     rdi
0x180008136  retn
```
