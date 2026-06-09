# SXWriter::get_version(wchar_t * *)

- ea: `0x100408610`
- end: `0x100408668`
- name: `?get_version@SXWriter@@UEAAJPEAPEA_W@Z`
- size: `88`
- prototype: `__int64 __fastcall(SXWriter *__hidden this, wchar_t **)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x100408610`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x100408647`
- `OLEAUT32!__imp_SysAllocString` at `0x100408647`

## pseudocode

```c
__int64 __fastcall SXWriter::get_version(SXWriter *this, wchar_t **a2)
{
  unsigned int v2; // ebx
  const OLECHAR *v5; // rcx
  wchar_t *v6; // rax

  v2 = 0;
  if ( !a2 )
    return 2147500035LL;
  v5 = (const OLECHAR *)((char *)this + 188);
  if ( !*v5 )
    v5 = L"1.0";
  v6 = SysAllocString(v5);
  *a2 = v6;
  if ( !v6 )
    return (unsigned int)-2147024882;
  return v2;
}

```

## disassembly

```asm
0x100408610  mov     [rsp+arg_0], rbx
0x100408615  push    rdi
0x100408616  sub     rsp, 20h
0x10040861a  xor     ebx, ebx
0x10040861c  mov     rdi, rdx
0x10040861f  test    rdx, rdx
0x100408622  jnz     short loc_100408634
0x100408624  mov     eax, 80004003h
0x100408629  mov     rbx, [rsp+28h+arg_0]
0x10040862e  add     rsp, 20h
0x100408632  pop     rdi
0x100408633  retn
0x100408634  add     rcx, 0BCh
0x10040863b  cmp     [rcx], bx
0x10040863e  jnz     short loc_100408647
0x100408640  lea     rcx, psz; "1.0"
0x100408647  call    cs:__imp_SysAllocString
0x10040864d  test    rax, rax
0x100408650  mov     [rdi], rax
0x100408653  mov     ecx, 8007000Eh
0x100408658  cmovz   ebx, ecx
0x10040865b  mov     eax, ebx
0x10040865d  mov     rbx, [rsp+28h+arg_0]
0x100408662  add     rsp, 20h
0x100408666  pop     rdi
0x100408667  retn
```
