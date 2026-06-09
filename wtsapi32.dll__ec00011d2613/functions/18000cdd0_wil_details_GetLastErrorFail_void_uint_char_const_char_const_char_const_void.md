# wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x18000cdd0`
- end: `0x18000ce31`
- name: `?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z`
- size: `97`
- prototype: `unsigned int __usercall@<eax>(wil::details *__hidden this@<rcx>, void *@<rdx>, unsigned int@<r8d>, const char *@<r9>, const char *, const char *, void *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000b5d0`
- `0x18000b640`
- `0x18000ce38`

## callees

- `0x18000b710`
- `0x18000cdd0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cde7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cde7`

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
  unsigned int v7; // edi
  DWORD result; // eax
  wil::details *v10; // [rsp+30h] [rbp-18h]

  v7 = (unsigned int)a2;
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
0x18000cdd0  mov     [rsp+arg_0], rbx
0x18000cdd5  mov     [rsp+arg_8], rsi
0x18000cdda  push    rdi
0x18000cddb  sub     rsp, 40h
0x18000cddf  mov     rbx, r8
0x18000cde2  mov     edi, edx
0x18000cde4  mov     rsi, rcx
0x18000cde7  call    cs:__imp_GetLastError
0x18000cded  test    eax, eax
0x18000cdef  jnz     short loc_18000CE21
0x18000cdf1  mov     rax, [rsp+48h+arg_28]
0x18000cdf6  xor     r9d, r9d; int
0x18000cdf9  mov     dword ptr [rsp+48h+var_18], 8007029Ch; wil::details *
0x18000ce01  mov     r8, rbx; int
0x18000ce04  mov     [rsp+48h+var_20], rax; __int64
0x18000ce09  mov     edx, edi; int
0x18000ce0b  mov     rcx, rsi; int
0x18000ce0e  mov     [rsp+48h+var_28], 0; __int64
0x18000ce17  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000ce1c  mov     eax, 29Ch
0x18000ce21  mov     rbx, [rsp+48h+arg_0]
0x18000ce26  mov     rsi, [rsp+48h+arg_8]
0x18000ce2b  add     rsp, 40h
0x18000ce2f  pop     rdi
0x18000ce30  retn
```
