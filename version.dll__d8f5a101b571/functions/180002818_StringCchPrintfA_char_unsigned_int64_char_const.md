# StringCchPrintfA(char *,unsigned __int64,char const *,...)

- ea: `0x180002818`
- end: `0x180002892`
- name: `?StringCchPrintfA@@YAJPEAD_KPEBDZZ`
- size: `122`
- prototype: `__int64(char *, unsigned __int64, const char *, ...)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180002198`

## callees

- `0x180002818`

## import_xrefs

- `msvcrt!_vsnprintf` at `0x180002855`
- `msvcrt!_vsnprintf` at `0x180002855`

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
0x180002818  mov     [rsp+arg_10], r8
0x18000281d  mov     qword ptr [rsp+ArgList], r9
0x180002822  push    rbx
0x180002823  push    rdi
0x180002824  sub     rsp, 38h
0x180002828  mov     rdi, rcx
0x18000282b  test    rdx, rdx
0x18000282e  jz      short loc_18000287E
0x180002830  cmp     rdx, 7FFFFFFFh
0x180002837  jbe     short loc_180002840
0x180002839  mov     eax, 80070057h
0x18000283e  jmp     short loc_180002888
0x180002840  lea     rbx, [rdx-1]
0x180002844  mov     [rsp+48h+var_28], 0
0x18000284d  mov     rdx, rbx; BufferCount
0x180002850  lea     r9, [rsp+48h+ArgList]; ArgList
0x180002855  call    cs:__imp__vsnprintf
0x18000285b  test    eax, eax
0x18000285d  js      short loc_180002873
0x18000285f  movsxd  rcx, eax
0x180002862  cmp     rcx, rbx
0x180002865  ja      short loc_180002873
0x180002867  xor     eax, eax
0x180002869  cmp     rcx, rbx
0x18000286c  jnz     short loc_18000288B
0x18000286e  mov     [rbx+rdi], al
0x180002871  jmp     short loc_18000288B
0x180002873  mov     byte ptr [rbx+rdi], 0
0x180002877  mov     eax, 8007007Ah
0x18000287c  jmp     short loc_18000288B
0x18000287e  mov     eax, 80070057h
0x180002883  test    rdx, rdx
0x180002886  jz      short loc_18000288B
0x180002888  mov     byte ptr [rcx], 0
0x18000288b  add     rsp, 38h
0x18000288f  pop     rdi
0x180002890  pop     rbx
0x180002891  retn
```
