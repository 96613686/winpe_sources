# StringCchPrintfA(char *,unsigned __int64,char const *,...)

- ea: `0x180004e58`
- end: `0x180004ed2`
- name: `?StringCchPrintfA@@YAJPEAD_KPEBDZZ`
- size: `122`
- prototype: `__int64(char *, unsigned __int64, const char *, ...)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180004704`

## callees

- `0x180004e58`

## import_xrefs

- `msvcrt!_vsnprintf` at `0x180004e95`
- `msvcrt!_vsnprintf` at `0x180004e95`

## pseudocode

```c
__int64 StringCchPrintfA(char *a1, unsigned __int64 a2, const char *a3, ...)
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
    v6 = _vsnprintf(a1, a2 - 1, a3, ArgList);
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
0x180004e58  mov     [rsp+arg_10], r8
0x180004e5d  mov     qword ptr [rsp+ArgList], r9
0x180004e62  push    rbx
0x180004e63  push    rdi
0x180004e64  sub     rsp, 38h
0x180004e68  mov     rdi, rcx
0x180004e6b  test    rdx, rdx
0x180004e6e  jz      short loc_180004EBE
0x180004e70  cmp     rdx, 7FFFFFFFh
0x180004e77  jbe     short loc_180004E80
0x180004e79  mov     eax, 80070057h
0x180004e7e  jmp     short loc_180004EC8
0x180004e80  lea     rbx, [rdx-1]
0x180004e84  mov     [rsp+48h+var_28], 0
0x180004e8d  mov     rdx, rbx; BufferCount
0x180004e90  lea     r9, [rsp+48h+ArgList]; ArgList
0x180004e95  call    cs:__imp__vsnprintf
0x180004e9b  test    eax, eax
0x180004e9d  js      short loc_180004EB3
0x180004e9f  movsxd  rcx, eax
0x180004ea2  cmp     rcx, rbx
0x180004ea5  ja      short loc_180004EB3
0x180004ea7  xor     eax, eax
0x180004ea9  cmp     rcx, rbx
0x180004eac  jnz     short loc_180004ECB
0x180004eae  mov     [rbx+rdi], al
0x180004eb1  jmp     short loc_180004ECB
0x180004eb3  mov     byte ptr [rbx+rdi], 0
0x180004eb7  mov     eax, 8007007Ah
0x180004ebc  jmp     short loc_180004ECB
0x180004ebe  mov     eax, 80070057h
0x180004ec3  test    rdx, rdx
0x180004ec6  jz      short loc_180004ECB
0x180004ec8  mov     byte ptr [rcx], 0
0x180004ecb  add     rsp, 38h
0x180004ecf  pop     rdi
0x180004ed0  pop     rbx
0x180004ed1  retn
```
