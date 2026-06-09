# CommandLineBase::CopyData(wchar_t const * *,unsigned __int64,wchar_t const * *,unsigned __int64,unsigned __int64 *)

- ea: `0x180007d90`
- end: `0x180007dc9`
- name: `?CopyData@CommandLineBase@@SAJPEAPEB_W_K01PEA_K@Z`
- size: `57`
- prototype: `__int64 __fastcall(const wchar_t **, unsigned __int64, const wchar_t **, unsigned __int64, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180007d90`

## pseudocode

```c
__int64 __fastcall CommandLineBase::CopyData(
        const wchar_t **a1,
        unsigned __int64 a2,
        const wchar_t **a3,
        unsigned __int64 a4,
        unsigned __int64 *a5)
{
  signed __int64 v6; // rcx
  unsigned __int64 v7; // rdx

  if ( a2 < a4 )
    return 2147942424LL;
  *a3 = 0;
  if ( a4 )
  {
    v6 = (char *)a1 - (char *)a3;
    v7 = a4;
    do
    {
      *a3 = *(const wchar_t **)((char *)a3 + v6);
      ++a3;
      --v7;
    }
    while ( v7 );
  }
  *a5 = a4;
  return 0;
}

```

## disassembly

```asm
0x180007d90  cmp     rdx, r9
0x180007d93  jnb     short loc_180007D9B
0x180007d95  mov     eax, 80070018h
0x180007d9a  retn
0x180007d9b  mov     qword ptr [r8], 0
0x180007da2  test    r9, r9
0x180007da5  jz      short loc_180007DBE
0x180007da7  sub     rcx, r8
0x180007daa  mov     rdx, r9
0x180007dad  mov     rax, [rcx+r8]
0x180007db1  mov     [r8], rax
0x180007db4  lea     r8, [r8+8]
0x180007db8  sub     rdx, 1
0x180007dbc  jnz     short loc_180007DAD
0x180007dbe  mov     rax, [rsp+arg_20]
0x180007dc3  mov     [rax], r9
0x180007dc6  xor     eax, eax
0x180007dc8  retn
```
