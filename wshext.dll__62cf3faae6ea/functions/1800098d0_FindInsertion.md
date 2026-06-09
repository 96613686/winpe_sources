# FindInsertion

- ea: `0x1800098d0`
- end: `0x180009961`
- name: `FindInsertion`
- size: `145`
- prototype: `OLECHAR *__fastcall(int, OLECHAR *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800021d0`
- `0x180008f7c`
- `0x1800093c0`

## callees

- `0x1800098d0`

## import_xrefs

- `msvcrt!wcsstr` at `0x1800098f8`
- `msvcrt!wcsstr` at `0x180009911`
- `msvcrt!wcsstr` at `0x180009937`
- `msvcrt!wcsstr` at `0x1800098f8`
- `msvcrt!wcsstr` at `0x180009911`
- `msvcrt!wcsstr` at `0x180009937`
- `OLEAUT32!__imp_SysStringLen` at `0x180009947`
- `OLEAUT32!__imp_SysStringLen` at `0x180009947`

## pseudocode

```c
OLECHAR *__fastcall FindInsertion(int a1, OLECHAR *a2)
{
  OLECHAR *v2; // rdi
  wchar_t *v3; // rbx
  wchar_t *v4; // rax
  const wchar_t *i; // rcx
  wchar_t *v6; // rax

  v2 = a2;
  if ( a1 != 3 )
    return &a2[SysStringLen(a2)];
  v3 = 0;
  v4 = wcsstr(a2, L"</package");
  if ( v4 )
  {
    do
    {
      v3 = v4;
      v4 = wcsstr(v4 + 1, L"</package");
    }
    while ( v4 );
    v2 = v3;
  }
  for ( i = v2; ; i = v6 + 1 )
  {
    v6 = wcsstr(i, L"</job");
    if ( !v6 )
      break;
    v3 = v6;
  }
  return v3;
}

```

## disassembly

```asm
0x1800098d0  mov     [rsp+arg_0], rbx
0x1800098d5  push    rdi
0x1800098d6  sub     rsp, 20h
0x1800098da  mov     rdi, rdx
0x1800098dd  sub     ecx, 1
0x1800098e0  jz      short loc_180009944
0x1800098e2  sub     ecx, 1
0x1800098e5  jz      short loc_180009944
0x1800098e7  cmp     ecx, 1
0x1800098ea  jnz     short loc_180009944
0x1800098ec  lea     rdx, aPackage; "</package"
0x1800098f3  mov     rcx, rdi; Str
0x1800098f6  xor     ebx, ebx
0x1800098f8  call    cs:__imp_wcsstr
0x1800098fe  test    rax, rax
0x180009901  jz      short loc_180009924
0x180009903  lea     rcx, [rax+2]; Str
0x180009907  mov     rbx, rax
0x18000990a  lea     rdx, aPackage; "</package"
0x180009911  call    cs:__imp_wcsstr
0x180009917  test    rax, rax
0x18000991a  jnz     short loc_180009903
0x18000991c  test    rbx, rbx
0x18000991f  jz      short loc_180009924
0x180009921  mov     rdi, rbx
0x180009924  mov     rcx, rdi
0x180009927  jmp     short loc_180009930
0x180009929  mov     rbx, rax
0x18000992c  lea     rcx, [rax+2]; Str
0x180009930  lea     rdx, aJob; "</job"
0x180009937  call    cs:__imp_wcsstr
0x18000993d  test    rax, rax
0x180009940  jnz     short loc_180009929
0x180009942  jmp     short loc_180009953
0x180009944  mov     rcx, rdi; pbstr
0x180009947  call    cs:__imp_SysStringLen
0x18000994d  mov     eax, eax
0x18000994f  lea     rbx, [rdi+rax*2]
0x180009953  mov     rax, rbx
0x180009956  mov     rbx, [rsp+28h+arg_0]
0x18000995b  add     rsp, 20h
0x18000995f  pop     rdi
0x180009960  retn
```
