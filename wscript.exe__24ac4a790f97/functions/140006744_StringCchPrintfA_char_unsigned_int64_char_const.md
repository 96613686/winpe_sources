# StringCchPrintfA(char *,unsigned __int64,char const *,...)

- ea: `0x140006744`
- end: `0x1400067be`
- name: `?StringCchPrintfA@@YAJPEAD_KPEBDZZ`
- size: `122`
- prototype: `__int64(char *, unsigned __int64, const char *, ...)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x140006004`
- `0x1400067c4`
- `0x140009888`
- `0x140014958`

## callees

- `0x140006744`

## import_xrefs

- `msvcrt!_vsnprintf` at `0x140006781`
- `msvcrt!_vsnprintf` at `0x140006781`

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
0x140006744  mov     [rsp+arg_10], r8
0x140006749  mov     qword ptr [rsp+ArgList], r9
0x14000674e  push    rbx
0x14000674f  push    rdi
0x140006750  sub     rsp, 38h
0x140006754  mov     rdi, rcx
0x140006757  test    rdx, rdx
0x14000675a  jz      short loc_1400067AA
0x14000675c  cmp     rdx, 7FFFFFFFh
0x140006763  jbe     short loc_14000676C
0x140006765  mov     eax, 80070057h
0x14000676a  jmp     short loc_1400067B4
0x14000676c  lea     rbx, [rdx-1]
0x140006770  mov     [rsp+48h+var_28], 0
0x140006779  mov     rdx, rbx; BufferCount
0x14000677c  lea     r9, [rsp+48h+ArgList]; ArgList
0x140006781  call    cs:__imp__vsnprintf
0x140006787  test    eax, eax
0x140006789  js      short loc_14000679F
0x14000678b  movsxd  rcx, eax
0x14000678e  cmp     rcx, rbx
0x140006791  ja      short loc_14000679F
0x140006793  xor     eax, eax
0x140006795  cmp     rcx, rbx
0x140006798  jnz     short loc_1400067B7
0x14000679a  mov     [rbx+rdi], al
0x14000679d  jmp     short loc_1400067B7
0x14000679f  mov     byte ptr [rbx+rdi], 0
0x1400067a3  mov     eax, 8007007Ah
0x1400067a8  jmp     short loc_1400067B7
0x1400067aa  mov     eax, 80070057h
0x1400067af  test    rdx, rdx
0x1400067b2  jz      short loc_1400067B7
0x1400067b4  mov     byte ptr [rcx], 0
0x1400067b7  add     rsp, 38h
0x1400067bb  pop     rdi
0x1400067bc  pop     rbx
0x1400067bd  retn
```
