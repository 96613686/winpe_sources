# StringCbPrintfA(char *,unsigned __int64,char const *,...)

- ea: `0x180006bc4`
- end: `0x180006c3d`
- name: `?StringCbPrintfA@@YAJPEAD_KPEBDZZ`
- size: `121`
- prototype: `__int64(char *, unsigned __int64, const char *, ...)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180006868`
- `0x180007ac8`

## callees

- `0x180001cf8`
- `0x180006bc4`

## pseudocode

```c
__int64 StringCbPrintfA(char *a1, unsigned __int64 a2, const char *a3, ...)
{
  __int64 result; // rax
  unsigned __int64 v5; // rbx
  int v6; // eax
  __int64 v7; // rcx
  va_list ArgList; // [rsp+68h] [rbp+20h] BYREF

  va_start(ArgList, a3);
  if ( !a2 )
    return 2147942487LL;
  if ( a2 <= 0x7FFFFFFF )
  {
    v5 = a2 - 1;
    v6 = vsnprintf(a1, a2 - 1, a3, ArgList);
    if ( v6 < 0 || (v7 = v6, v6 > v5) )
    {
      a1[v5] = 0;
      return 2147942522LL;
    }
    else
    {
      result = 0;
      if ( v7 == v5 )
        a1[v5] = 0;
    }
  }
  else
  {
    result = 2147942487LL;
    *a1 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180006bc4  mov     [rsp+arg_10], r8
0x180006bc9  mov     qword ptr [rsp+ArgList], r9
0x180006bce  push    rbx
0x180006bcf  push    rdi
0x180006bd0  sub     rsp, 38h
0x180006bd4  mov     rdi, rcx
0x180006bd7  test    rdx, rdx
0x180006bda  jz      short loc_180006C29
0x180006bdc  cmp     rdx, 7FFFFFFFh
0x180006be3  jbe     short loc_180006BEC
0x180006be5  mov     eax, 80070057h
0x180006bea  jmp     short loc_180006C33
0x180006bec  lea     rbx, [rdx-1]
0x180006bf0  mov     [rsp+48h+var_28], 0
0x180006bf9  mov     rdx, rbx; BufferCount
0x180006bfc  lea     r9, [rsp+48h+ArgList]; ArgList
0x180006c01  call    _vsnprintf
0x180006c06  test    eax, eax
0x180006c08  js      short loc_180006C1E
0x180006c0a  movsxd  rcx, eax
0x180006c0d  cmp     rcx, rbx
0x180006c10  ja      short loc_180006C1E
0x180006c12  xor     eax, eax
0x180006c14  cmp     rcx, rbx
0x180006c17  jnz     short loc_180006C36
0x180006c19  mov     [rbx+rdi], al
0x180006c1c  jmp     short loc_180006C36
0x180006c1e  mov     byte ptr [rbx+rdi], 0
0x180006c22  mov     eax, 8007007Ah
0x180006c27  jmp     short loc_180006C36
0x180006c29  mov     eax, 80070057h
0x180006c2e  test    rdx, rdx
0x180006c31  jz      short loc_180006C36
0x180006c33  mov     byte ptr [rcx], 0
0x180006c36  add     rsp, 38h
0x180006c3a  pop     rdi
0x180006c3b  pop     rbx
0x180006c3c  retn
```
