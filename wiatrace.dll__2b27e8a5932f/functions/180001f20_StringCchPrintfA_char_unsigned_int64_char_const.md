# StringCchPrintfA(char *,unsigned __int64,char const *,...)

- ea: `0x180001f20`
- end: `0x180001fa4`
- name: `?StringCchPrintfA@@YAJPEAD_KPEBDZZ`
- size: `132`
- prototype: `__int64(char *, unsigned __int64, const char *, ...)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180001010`
- `0x180001300`
- `0x180001fb0`

## callees

- `0x180001f20`
- `0x180003208`

## pseudocode

```c
__int64 StringCchPrintfA(char *a1, unsigned __int64 a2, const char *a3, ...)
{
  unsigned __int64 v4; // rbx
  int v5; // eax
  unsigned int v6; // ecx
  __int64 result; // rax
  va_list ArgList; // [rsp+68h] [rbp+20h] BYREF

  va_start(ArgList, a3);
  if ( !a2 )
    return 2147942487LL;
  if ( a2 > 0x7FFFFFFF )
  {
    result = 2147942487LL;
    *a1 = 0;
  }
  else
  {
    v4 = a2 - 1;
    v5 = vsnprintf(a1, a2 - 1, a3, ArgList);
    if ( v5 < 0 || v5 > v4 )
    {
      a1[v4] = 0;
      return (unsigned int)-2147024774;
    }
    else
    {
      v6 = 0;
      if ( v5 == v4 )
        a1[v4] = 0;
    }
    return v6;
  }
  return result;
}

```

## disassembly

```asm
0x180001f20  mov     [rsp+arg_10], r8
0x180001f25  mov     qword ptr [rsp+ArgList], r9
0x180001f2a  push    rdi
0x180001f2b  sub     rsp, 40h
0x180001f2f  mov     rdi, rcx
0x180001f32  test    rdx, rdx
0x180001f35  jz      short loc_180001F95
0x180001f37  cmp     rdx, 7FFFFFFFh
0x180001f3e  ja      short loc_180001F7E
0x180001f40  mov     [rsp+48h+var_10], rbx
0x180001f45  lea     r9, [rsp+48h+ArgList]; ArgList
0x180001f4a  lea     rbx, [rdx-1]
0x180001f4e  mov     [rsp+48h+var_28], 0
0x180001f57  mov     rdx, rbx; BufferCount
0x180001f5a  call    _vsnprintf
0x180001f5f  test    eax, eax
0x180001f61  js      short loc_180001F8A
0x180001f63  cdqe
0x180001f65  cmp     rax, rbx
0x180001f68  ja      short loc_180001F8A
0x180001f6a  xor     ecx, ecx
0x180001f6c  cmp     rax, rbx
0x180001f6f  jz      short loc_180001F85
0x180001f71  mov     rbx, [rsp+48h+var_10]
0x180001f76  mov     eax, ecx
0x180001f78  add     rsp, 40h
0x180001f7c  pop     rdi
0x180001f7d  retn
0x180001f7e  mov     eax, 80070057h
0x180001f83  jmp     short loc_180001F9F
0x180001f85  mov     [rbx+rdi], cl
0x180001f88  jmp     short loc_180001F71
0x180001f8a  mov     byte ptr [rbx+rdi], 0
0x180001f8e  mov     ecx, 8007007Ah
0x180001f93  jmp     short loc_180001F71
0x180001f95  mov     eax, 80070057h
0x180001f9a  test    rdx, rdx
0x180001f9d  jz      short loc_180001F78
0x180001f9f  mov     byte ptr [rcx], 0
0x180001fa2  jmp     short loc_180001F78
```
