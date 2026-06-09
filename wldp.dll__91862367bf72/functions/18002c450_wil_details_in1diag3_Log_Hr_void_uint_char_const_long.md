# wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)

- ea: `0x18002c450`
- end: `0x18002c48c`
- name: `?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z`
- size: `60`
- prototype: `int(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18001bb98`

## callees

- `0x180024894`

## string_xrefs

- `0x18002c473`: `onecore\base\ngscb\wldp\dll\filetrust.cpp`

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
    339,
    (int)"onecore\\base\\ngscb\\wldp\\dll\\filetrust.cpp",
    0,
    0,
    retaddr,
    v6);
  return v4;
}

```

## disassembly

```asm
0x18002c450  push    rbx
0x18002c452  sub     rsp, 40h
0x18002c456  mov     ebx, r9d
0x18002c459  mov     rax, [rsp+48h]
0x18002c45e  mov     dword ptr [rsp+48h+var_18], ebx; wil::details *
0x18002c462  mov     [rsp+48h+var_20], rax; __int64
0x18002c467  mov     [rsp+48h+var_28], 0; __int64
0x18002c470  xor     r9d, r9d; int
0x18002c473  lea     r8, aOnecoreBaseNgs_4; "onecore\\base\\ngscb\\wldp\\dll\\filetr"...
0x18002c47a  mov     edx, 153h; int
0x18002c47f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18002c484  mov     eax, ebx
0x18002c486  add     rsp, 40h
0x18002c48a  pop     rbx
0x18002c48b  retn
```
