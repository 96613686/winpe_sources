# wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)

- ea: `0x18002762c`
- end: `0x180027667`
- name: `?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z`
- size: `59`
- prototype: `__int64 __fastcall(wil::details::in1diag3 *this, void *, __int64, const char *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180038c07`

## callees

- `0x18000b820`

## string_xrefs

- `0x18002764f`: `C:\__w\1\s\src\Client\policy\src\helpers\PolicyRegistryHelper.cpp`

## pseudocode

```c
__int64 __fastcall wil::details::in1diag3::Log_Hr(wil::details::in1diag3 *this, void *a2, __int64 a3, const char *a4)
{
  unsigned int v4; // ebx
  wil::details *v6; // [rsp+30h] [rbp-18h]
  __int64 retaddr; // [rsp+48h] [rbp+0h]

  v4 = (unsigned int)a4;
  LODWORD(v6) = (_DWORD)a4;
  wil::details::ReportFailure_Hr<2>(
    (int)this,
    48,
    (int)"C:\\__w\\1\\s\\src\\Client\\policy\\src\\helpers\\PolicyRegistryHelper.cpp",
    0,
    0,
    retaddr,
    v6);
  return v4;
}

```

## disassembly

```asm
0x18002762c  push    rbx
0x18002762e  sub     rsp, 40h
0x180027632  mov     ebx, r9d
0x180027635  mov     rax, [rsp+48h]
0x18002763a  mov     dword ptr [rsp+48h+var_18], ebx; wil::details *
0x18002763e  mov     [rsp+48h+var_20], rax; __int64
0x180027643  mov     [rsp+48h+var_28], 0; __int64
0x18002764c  xor     r9d, r9d; int
0x18002764f  lea     r8, aCW1SSrcClientP_8; "C:\\__w\\1\\s\\src\\Client\\policy\\src"...
0x180027656  lea     edx, [r9+30h]; int
0x18002765a  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18002765f  mov     eax, ebx
0x180027661  add     rsp, 40h
0x180027665  pop     rbx
0x180027666  retn
```
