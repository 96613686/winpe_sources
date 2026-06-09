# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Tidy_deallocate(void)

- ea: `0x18000a4d4`
- end: `0x18000a538`
- name: `?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ`
- size: `100`
- prototype: `__int64 __fastcall(char **)`
- caller_count: `5`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000955c`
- `0x180009ddc`
- `0x180009e38`
- `0x18000a054`
- `0x18000a540`

## callees

- `0x180002190`
- `0x18000a4d4`

## pseudocode

```c
__int64 __fastcall std::wstring::_Tidy_deallocate(char **a1)
{
  unsigned __int64 v1; // rdx
  char *v3; // rax
  const struct std::nothrow_t *v4; // rdx
  char *v5; // rcx
  __int64 result; // rax

  v1 = (unsigned __int64)a1[3];
  if ( v1 > 7 )
  {
    v3 = *a1;
    v4 = (const struct std::nothrow_t *)(2 * v1 + 2);
    if ( (unsigned __int64)v4 < 0x1000 )
    {
      v5 = *a1;
    }
    else
    {
      v5 = (char *)*((_QWORD *)v3 - 1);
      if ( (unsigned __int64)(v3 - v5 - 8) > 0x1F )
        __fastfail(5u);
      v4 = (const struct std::nothrow_t *)((char *)v4 + 39);
    }
    operator delete(v5, v4);
  }
  result = 0;
  a1[3] = (char *)7;
  a1[2] = 0;
  *(_WORD *)a1 = 0;
  return result;
}

```

## disassembly

```asm
0x18000a4d4  push    rbx
0x18000a4d6  sub     rsp, 20h
0x18000a4da  mov     rdx, [rcx+18h]
0x18000a4de  mov     rbx, rcx
0x18000a4e1  cmp     rdx, 7
0x18000a4e5  jbe     short loc_18000A521
0x18000a4e7  mov     rax, [rcx]
0x18000a4ea  lea     rdx, ds:2[rdx*2]; struct std::nothrow_t *
0x18000a4f2  cmp     rdx, 1000h
0x18000a4f9  jb      short loc_18000A519
0x18000a4fb  mov     rcx, [rax-8]
0x18000a4ff  sub     rax, rcx
0x18000a502  sub     rax, 8
0x18000a506  cmp     rax, 1Fh
0x18000a50a  ja      short loc_18000A512
0x18000a50c  add     rdx, 27h ; '''
0x18000a510  jmp     short loc_18000A51C
0x18000a512  mov     ecx, 5
0x18000a517  int     29h; Win8: RtlFailFast(ecx)
0x18000a519  mov     rcx, rax; void *
0x18000a51c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000a521  xor     eax, eax
0x18000a523  mov     qword ptr [rbx+18h], 7
0x18000a52b  mov     [rbx+10h], rax
0x18000a52f  mov     [rbx], ax
0x18000a532  add     rsp, 20h
0x18000a536  pop     rbx
0x18000a537  retn
```
