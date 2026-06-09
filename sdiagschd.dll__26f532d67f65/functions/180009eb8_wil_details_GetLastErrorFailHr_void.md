# wil::details::GetLastErrorFailHr(void)

- ea: `0x180009eb8`
- end: `0x180009f0d`
- name: `?GetLastErrorFailHr@details@wil@@YAJXZ`
- size: `85`
- prototype: `__int64 __fastcall(wil::details *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180009600`
- `0x18000a904`

## callees

- `0x180008878`
- `0x180009eb8`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180009ec3`
- `KERNEL32!GetLastError` at `0x180009ec3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
signed int __fastcall wil::details::GetLastErrorFailHr(wil::details *this)
{
  signed int result; // eax
  wil::details *v2; // [rsp+30h] [rbp-18h]
  __int64 retaddr; // [rsp+48h] [rbp+0h]

  result = GetLastError();
  if ( !result )
  {
    LODWORD(v2) = -2147024228;
    wil::details::ReportFailure_Hr<2>(0, 0, 0, 0, 0, retaddr, v2);
    result = 668;
  }
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180009eb8  push    rbx
0x180009eba  sub     rsp, 40h
0x180009ebe  mov     rbx, [rsp+48h]
0x180009ec3  call    cs:__imp_GetLastError
0x180009eca  nop     dword ptr [rax+rax+00h]
0x180009ecf  test    eax, eax
0x180009ed1  jnz     short loc_180009EFA
0x180009ed3  mov     dword ptr [rsp+48h+var_18], 8007029Ch; wil::details *
0x180009edb  mov     [rsp+48h+var_20], rbx; __int64
0x180009ee0  and     [rsp+48h+var_28], 0
0x180009ee6  xor     r9d, r9d; int
0x180009ee9  xor     r8d, r8d; int
0x180009eec  xor     edx, edx; int
0x180009eee  xor     ecx, ecx; int
0x180009ef0  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110J@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long)
0x180009ef5  mov     eax, 29Ch
0x180009efa  test    eax, eax
0x180009efc  jle     short loc_180009F06
0x180009efe  movzx   eax, ax
0x180009f01  or      eax, 80070000h
0x180009f06  add     rsp, 40h
0x180009f0a  pop     rbx
0x180009f0b  retn
```
