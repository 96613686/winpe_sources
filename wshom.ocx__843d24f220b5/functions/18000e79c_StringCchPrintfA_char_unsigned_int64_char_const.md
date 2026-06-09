# StringCchPrintfA(char *,unsigned __int64,char const *,...)

- ea: `0x18000e79c`
- end: `0x18000e816`
- name: `?StringCchPrintfA@@YAJPEAD_KPEBDZZ`
- size: `122`
- prototype: `__int64(char *, unsigned __int64, const char *, ...)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180002d10`
- `0x18000ebac`
- `0x18000ecec`

## callees

- `0x18000e79c`

## import_xrefs

- `msvcrt!_vsnprintf` at `0x18000e7d9`
- `msvcrt!_vsnprintf` at `0x18000e7d9`

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
0x18000e79c  mov     [rsp+arg_10], r8
0x18000e7a1  mov     qword ptr [rsp+ArgList], r9
0x18000e7a6  push    rbx
0x18000e7a7  push    rdi
0x18000e7a8  sub     rsp, 38h
0x18000e7ac  mov     rdi, rcx
0x18000e7af  test    rdx, rdx
0x18000e7b2  jz      short loc_18000E802
0x18000e7b4  cmp     rdx, 7FFFFFFFh
0x18000e7bb  jbe     short loc_18000E7C4
0x18000e7bd  mov     eax, 80070057h
0x18000e7c2  jmp     short loc_18000E80C
0x18000e7c4  lea     rbx, [rdx-1]
0x18000e7c8  mov     [rsp+48h+var_28], 0
0x18000e7d1  mov     rdx, rbx; BufferCount
0x18000e7d4  lea     r9, [rsp+48h+ArgList]; ArgList
0x18000e7d9  call    cs:__imp__vsnprintf
0x18000e7df  test    eax, eax
0x18000e7e1  js      short loc_18000E7F7
0x18000e7e3  movsxd  rcx, eax
0x18000e7e6  cmp     rcx, rbx
0x18000e7e9  ja      short loc_18000E7F7
0x18000e7eb  xor     eax, eax
0x18000e7ed  cmp     rcx, rbx
0x18000e7f0  jnz     short loc_18000E80F
0x18000e7f2  mov     [rbx+rdi], al
0x18000e7f5  jmp     short loc_18000E80F
0x18000e7f7  mov     byte ptr [rbx+rdi], 0
0x18000e7fb  mov     eax, 8007007Ah
0x18000e800  jmp     short loc_18000E80F
0x18000e802  mov     eax, 80070057h
0x18000e807  test    rdx, rdx
0x18000e80a  jz      short loc_18000E80F
0x18000e80c  mov     byte ptr [rcx], 0
0x18000e80f  add     rsp, 38h
0x18000e813  pop     rdi
0x18000e814  pop     rbx
0x18000e815  retn
```
