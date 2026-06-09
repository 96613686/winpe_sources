# wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x180008020`
- end: `0x180008081`
- name: `?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z`
- size: `97`
- prototype: `unsigned int __usercall@<eax>(wil::details *__hidden this@<rcx>, void *@<rdx>, unsigned int@<r8d>, const char *@<r9>, const char *, const char *, void *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180006cb4`
- `0x180006d2c`
- `0x180008088`

## callees

- `0x180006dfc`
- `0x180008020`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008037`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008037`

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
0x180008020  mov     [rsp+arg_0], rbx
0x180008025  mov     [rsp+arg_8], rsi
0x18000802a  push    rdi
0x18000802b  sub     rsp, 40h
0x18000802f  mov     rbx, r8
0x180008032  mov     edi, edx
0x180008034  mov     rsi, rcx
0x180008037  call    cs:__imp_GetLastError
0x18000803d  test    eax, eax
0x18000803f  jnz     short loc_180008071
0x180008041  mov     dword ptr [rsp+48h+var_18], 8007029Ch; wil::details *
0x180008049  mov     rax, [rsp+48h+arg_28]
0x18000804e  mov     [rsp+48h+var_20], rax; __int64
0x180008053  mov     [rsp+48h+var_28], 0; __int64
0x18000805c  xor     r9d, r9d; int
0x18000805f  mov     r8, rbx; int
0x180008062  mov     edx, edi; int
0x180008064  mov     rcx, rsi; int
0x180008067  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000806c  mov     eax, 29Ch
0x180008071  mov     rbx, [rsp+48h+arg_0]
0x180008076  mov     rsi, [rsp+48h+arg_8]
0x18000807b  add     rsp, 40h
0x18000807f  pop     rdi
0x180008080  retn
```
