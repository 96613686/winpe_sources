# wil::details::GetLastErrorFailHr(void)

- ea: `0x140004760`
- end: `0x1400047ba`
- name: `?GetLastErrorFailHr@details@wil@@YAJXZ`
- size: `90`
- prototype: `signed int __fastcall(wil::details *this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140003bd0`
- `0x140003f74`

## callees

- `0x140003030`
- `0x140004760`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140004774`
- `KERNEL32!GetLastError` at `0x140004774`

## pseudocode

```c
signed int __fastcall wil::details::GetLastErrorFailHr(wil::details *this)
{
  signed int result; // eax
  wil::details *v2; // [rsp+30h] [rbp-28h]
  __int64 retaddr; // [rsp+58h] [rbp+0h]

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
0x140004760  push    rbx
0x140004762  sub     rsp, 50h
0x140004766  mov     [rsp+58h+var_18], 0FFFFFFFFFFFFFFFEh
0x14000476f  mov     rbx, [rsp+58h]
0x140004774  call    cs:__imp_GetLastError
0x14000477a  test    eax, eax
0x14000477c  jnz     short loc_1400047A8
0x14000477e  mov     dword ptr [rsp+58h+var_28], 8007029Ch; wil::details *
0x140004786  mov     [rsp+58h+var_30], rbx; __int64
0x14000478b  mov     [rsp+58h+var_38], 0; __int64
0x140004794  xor     r9d, r9d; int
0x140004797  xor     r8d, r8d; int
0x14000479a  xor     edx, edx; int
0x14000479c  xor     ecx, ecx; int
0x14000479e  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1400047a3  mov     eax, 29Ch
0x1400047a8  test    eax, eax
0x1400047aa  jle     short loc_1400047B4
0x1400047ac  movzx   eax, ax
0x1400047af  or      eax, 80070000h
0x1400047b4  add     rsp, 50h
0x1400047b8  pop     rbx
0x1400047b9  retn
```
