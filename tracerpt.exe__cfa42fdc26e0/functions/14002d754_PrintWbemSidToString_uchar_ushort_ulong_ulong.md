# PrintWbemSidToString(uchar *,ushort *,ulong,ulong)

- ea: `0x14002d754`
- end: `0x14002d7d7`
- name: `?PrintWbemSidToString@@YAKPEAEPEAGKK@Z`
- size: `131`
- prototype: `__int64 __fastcall(unsigned __int8 *, unsigned __int16 *, __int64, char)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, installer_update`

## callers

- `0x14002da1c`

## callees

- `0x140009c78`
- `0x14002d650`
- `0x14002d754`

## pseudocode

```c
__int64 __fastcall PrintWbemSidToString(unsigned __int8 *a1, unsigned __int16 *a2, __int64 a3, char a4)
{
  int v5; // eax
  int v6; // eax
  unsigned int v7; // ecx
  __int64 v9; // rcx

  if ( (a4 & 0x40) != 0 )
  {
    v5 = 64;
  }
  else
  {
    v5 = 32;
    if ( (a4 & 0x20) == 0 )
    {
      v5 = 64;
      if ( *((_DWORD *)g_TraceContext + 2170) )
        v5 = *((_DWORD *)g_TraceContext + 2170);
    }
  }
  if ( *(_DWORD *)a1 )
  {
    v9 = 16;
    if ( v5 != 64 )
      v9 = 8;
    return PrintSidToString(&a1[v9], a2);
  }
  else
  {
    v6 = StringCchPrintfW(a2, 0x800u, L"0");
    v7 = 0;
    if ( v6 < 0 )
      return 1359;
    return v7;
  }
}

```

## disassembly

```asm
0x14002d754  sub     rsp, 28h
0x14002d758  mov     r11d, 40h ; '@'
0x14002d75e  mov     r10, rdx
0x14002d761  mov     r8, rcx; unsigned int
0x14002d764  test    r11b, r9b
0x14002d767  jz      short loc_14002D76E
0x14002d769  mov     eax, r11d
0x14002d76c  jmp     short loc_14002D78D
0x14002d76e  mov     eax, 20h ; ' '
0x14002d773  test    al, r9b
0x14002d776  jnz     short loc_14002D78D
0x14002d778  mov     rax, cs:?g_TraceContext@@3PEAU_TRACE_CONTEXT_BLOCK@@EA; _TRACE_CONTEXT_BLOCK * g_TraceContext
0x14002d77f  mov     ecx, [rax+21E8h]
0x14002d785  test    ecx, ecx
0x14002d787  mov     eax, r11d
0x14002d78a  cmovnz  eax, ecx
0x14002d78d  cmp     dword ptr [r8], 0
0x14002d791  jnz     short loc_14002D7BA
0x14002d793  lea     r8, a0; "0"
0x14002d79a  mov     edx, 800h; unsigned __int64
0x14002d79f  mov     rcx, r10; unsigned __int16 *
0x14002d7a2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14002d7a7  xor     ecx, ecx
0x14002d7a9  mov     edx, 54Fh
0x14002d7ae  test    eax, eax
0x14002d7b0  cmovs   ecx, edx
0x14002d7b3  mov     eax, ecx
0x14002d7b5  add     rsp, 28h
0x14002d7b9  retn
0x14002d7ba  mov     ecx, 10h
0x14002d7bf  cmp     eax, r11d
0x14002d7c2  lea     edx, [rcx-8]
0x14002d7c5  cmovnz  ecx, edx
0x14002d7c8  mov     rdx, r10; unsigned __int16 *
0x14002d7cb  add     rcx, r8; unsigned __int8 *
0x14002d7ce  add     rsp, 28h
0x14002d7d2  jmp     ?PrintSidToString@@YAKPEAEPEAGK@Z; PrintSidToString(uchar *,ushort *,ulong)
```
