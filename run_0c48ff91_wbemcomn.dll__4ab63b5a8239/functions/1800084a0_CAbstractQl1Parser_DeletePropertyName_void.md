# CAbstractQl1Parser::DeletePropertyName(void)

- ea: `0x1800084a0`
- end: `0x1800084f3`
- name: `?DeletePropertyName@CAbstractQl1Parser@@IEAAXXZ`
- size: `83`
- prototype: `void __fastcall(CAbstractQl1Parser *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180009950`

## callees

- `0x1800084a0`
- `0x18000ab30`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800084e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800084e4`

## pseudocode

```c
void __fastcall CAbstractQl1Parser::DeletePropertyName(CAbstractQl1Parser *this)
{
  void **v1; // rbx
  int i; // esi

  v1 = (void **)((char *)this + 96);
  for ( i = 0; i < *((_DWORD *)this + 22); ++i )
  {
    if ( !*((_WORD *)*v1 + 8 * i) )
      CoTaskMemFree(*((LPVOID *)*v1 + 2 * i + 1));
  }
  CMUILocale::_Free(*v1);
  *((_DWORD *)this + 22) = 0;
  *v1 = 0;
}

```

## disassembly

```asm
0x1800084a0  push    rbx
0x1800084a2  push    rbp
0x1800084a3  push    rsi
0x1800084a4  push    rdi
0x1800084a5  sub     rsp, 28h
0x1800084a9  xor     ebp, ebp
0x1800084ab  lea     rbx, [rcx+60h]
0x1800084af  mov     rdi, rcx
0x1800084b2  mov     esi, ebp
0x1800084b4  cmp     [rcx+58h], ebp
0x1800084b7  jg      short loc_1800084D0
0x1800084b9  mov     rcx, [rbx]; void *
0x1800084bc  call    ?_Free@CMUILocale@@SAHPEAX@Z; CMUILocale::_Free(void *)
0x1800084c1  mov     [rdi+58h], ebp
0x1800084c4  mov     [rbx], rbp
0x1800084c7  add     rsp, 28h
0x1800084cb  pop     rdi
0x1800084cc  pop     rsi
0x1800084cd  pop     rbp
0x1800084ce  pop     rbx
0x1800084cf  retn
0x1800084d0  mov     rax, [rbx]
0x1800084d3  movsxd  rcx, esi
0x1800084d6  add     rcx, rcx
0x1800084d9  cmp     [rax+rcx*8], bp
0x1800084dd  jnz     short loc_1800084EA
0x1800084df  mov     rcx, [rax+rcx*8+8]; pv
0x1800084e4  call    cs:__imp_CoTaskMemFree
0x1800084ea  inc     esi
0x1800084ec  cmp     esi, [rdi+58h]
0x1800084ef  jl      short loc_1800084D0
0x1800084f1  jmp     short loc_1800084B9
```
