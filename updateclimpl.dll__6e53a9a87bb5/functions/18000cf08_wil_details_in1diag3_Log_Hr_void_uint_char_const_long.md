# wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)

- ea: `0x18000cf08`
- end: `0x18000cf44`
- name: `?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z`
- size: `60`
- prototype: `__int64 __fastcall(wil::details::in1diag3 *this, void *, __int64, const char *)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000c3d0`
- `0x18000cbb0`
- `0x18000cf4c`

## callees

- `0x180006bb4`

## string_xrefs

- `0x18000cf2b`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\result.h`

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
    (__int64)this,
    958,
    (__int64)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\result.h",
    0,
    0,
    retaddr,
    v6);
  return v4;
}

```

## disassembly

```asm
0x18000cf08  push    rbx
0x18000cf0a  sub     rsp, 40h
0x18000cf0e  mov     ebx, r9d
0x18000cf11  mov     rax, [rsp+48h]
0x18000cf16  mov     dword ptr [rsp+48h+var_18], ebx; wil::details *
0x18000cf1a  mov     [rsp+48h+var_20], rax; __int64
0x18000cf1f  mov     [rsp+48h+var_28], 0; __int64
0x18000cf28  xor     r9d, r9d; int
0x18000cf2b  lea     r8, aCW1SPackagesMi_1; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x18000cf32  mov     edx, 3BEh; int
0x18000cf37  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000cf3c  mov     eax, ebx
0x18000cf3e  add     rsp, 40h
0x18000cf42  pop     rbx
0x18000cf43  retn
```
