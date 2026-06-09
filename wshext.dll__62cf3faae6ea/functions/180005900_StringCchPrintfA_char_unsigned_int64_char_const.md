# StringCchPrintfA(char *,unsigned __int64,char const *,...)

- ea: `0x180005900`
- end: `0x18000597a`
- name: `?StringCchPrintfA@@YAJPEAD_KPEBDZZ`
- size: `122`
- prototype: `__int64(char *, unsigned __int64, const char *, ...)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1800028e0`
- `0x1800051a8`
- `0x180005980`
- `0x18000aacc`

## callees

- `0x180005900`

## import_xrefs

- `msvcrt!_vsnprintf` at `0x18000593d`
- `msvcrt!_vsnprintf` at `0x18000593d`

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
0x180005900  mov     [rsp+arg_10], r8
0x180005905  mov     qword ptr [rsp+ArgList], r9
0x18000590a  push    rbx
0x18000590b  push    rdi
0x18000590c  sub     rsp, 38h
0x180005910  mov     rdi, rcx
0x180005913  test    rdx, rdx
0x180005916  jz      short loc_180005966
0x180005918  cmp     rdx, 7FFFFFFFh
0x18000591f  jbe     short loc_180005928
0x180005921  mov     eax, 80070057h
0x180005926  jmp     short loc_180005970
0x180005928  lea     rbx, [rdx-1]
0x18000592c  mov     [rsp+48h+var_28], 0
0x180005935  mov     rdx, rbx; BufferCount
0x180005938  lea     r9, [rsp+48h+ArgList]; ArgList
0x18000593d  call    cs:__imp__vsnprintf
0x180005943  test    eax, eax
0x180005945  js      short loc_18000595B
0x180005947  movsxd  rcx, eax
0x18000594a  cmp     rcx, rbx
0x18000594d  ja      short loc_18000595B
0x18000594f  xor     eax, eax
0x180005951  cmp     rcx, rbx
0x180005954  jnz     short loc_180005973
0x180005956  mov     [rbx+rdi], al
0x180005959  jmp     short loc_180005973
0x18000595b  mov     byte ptr [rbx+rdi], 0
0x18000595f  mov     eax, 8007007Ah
0x180005964  jmp     short loc_180005973
0x180005966  mov     eax, 80070057h
0x18000596b  test    rdx, rdx
0x18000596e  jz      short loc_180005973
0x180005970  mov     byte ptr [rcx], 0
0x180005973  add     rsp, 38h
0x180005977  pop     rdi
0x180005978  pop     rbx
0x180005979  retn
```
