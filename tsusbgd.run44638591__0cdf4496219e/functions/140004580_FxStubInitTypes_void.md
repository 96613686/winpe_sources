# FxStubInitTypes(void)

- ea: `0x140004580`
- end: `0x140004645`
- name: `?FxStubInitTypes@@YAJXZ`
- size: `197`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140004244`

## callees

- `0x140004580`
- `0x140006370`

## import_xrefs

- `ntoskrnl!DbgPrintEx` at `0x1400045b6`
- `ntoskrnl!DbgPrintEx` at `0x140004629`
- `ntoskrnl!DbgPrintEx` at `0x1400045b6`
- `ntoskrnl!DbgPrintEx` at `0x140004629`

## pseudocode

```c
__int64 FxStubInitTypes(void)
{
  void **i; // rax
  void **v2; // rbx
  void **j; // rax
  __int64 (*v4)(void); // rax

  if ( &__KMDF_TYPE_INIT_START <= (_UNKNOWN *)&__KMDF_TYPE_INIT_END )
  {
    for ( i = &__KMDF_TYPE_INIT_END; ; i = (void **)((char *)v2 + *(unsigned int *)v2) )
    {
      v2 = i;
      for ( j = i + 1; j <= &__KMDF_TYPE_INIT_END && !*v2; j = v2 + 1 )
        ++v2;
      if ( v2 >= &__KMDF_TYPE_INIT_END )
        break;
      if ( v2 + 5 > &__KMDF_TYPE_INIT_END || *(_DWORD *)v2 != 40 || !v2 )
      {
        DbgPrintEx(0x4Du, 0, "FxGetNextObjectContextTypeInfo failed\n");
        return 3221225595LL;
      }
      v4 = (__int64 (*)(void))v2[4];
      if ( v4 )
        v2[3] = (void *)v4();
    }
    return 0;
  }
  else
  {
    DbgPrintEx(
      0x4Du,
      0,
      "FxStubInitTypes: invalid driver image, the address of symbol __KMDF_TYPE_INIT_START 0x%p is greater than the addre"
      "ss of symbol __KMDF_TYPE_INIT_END 0x%p, status 0x%x\n",
      &__KMDF_TYPE_INIT_START,
      &__KMDF_TYPE_INIT_END,
      -1073741701);
    return 3221225595LL;
  }
}

```

## disassembly

```asm
0x140004580  mov     [rsp+arg_0], rbx
0x140004585  push    rdi
0x140004586  sub     rsp, 30h
0x14000458a  lea     r9, ?__KMDF_TYPE_INIT_START@@3U_MARKER_TYPE@@A; _MARKER_TYPE __KMDF_TYPE_INIT_START
0x140004591  lea     rdi, ?__KMDF_TYPE_INIT_END@@3PEAXEA; void * __KMDF_TYPE_INIT_END
0x140004598  cmp     r9, rdi
0x14000459b  jbe     short loc_1400045C9
0x14000459d  xor     edx, edx; Level
0x14000459f  mov     [rsp+38h+var_10], 0C000007Bh
0x1400045a7  lea     r8, aFxstubinittype; "FxStubInitTypes: invalid driver image, "...
0x1400045ae  mov     [rsp+38h+var_18], rdi
0x1400045b3  lea     ecx, [rdx+4Dh]; ComponentId
0x1400045b6  call    cs:__imp_DbgPrintEx
0x1400045bd  nop     dword ptr [rax+rax+00h]
0x1400045c2  mov     eax, 0C000007Bh
0x1400045c7  jmp     short loc_140004639
0x1400045c9  lea     rax, ?__KMDF_TYPE_INIT_END@@3PEAXEA; void * __KMDF_TYPE_INIT_END
0x1400045d0  mov     rbx, rax
0x1400045d3  add     rax, 8
0x1400045d7  jmp     short loc_1400045E7
0x1400045d9  cmp     qword ptr [rbx], 0
0x1400045dd  jnz     short loc_1400045EC
0x1400045df  add     rbx, 8
0x1400045e3  lea     rax, [rbx+8]
0x1400045e7  cmp     rax, rdi
0x1400045ea  jbe     short loc_1400045D9
0x1400045ec  cmp     rbx, rdi
0x1400045ef  jnb     short loc_140004637
0x1400045f1  lea     rax, [rbx+28h]
0x1400045f5  cmp     rax, rdi
0x1400045f8  ja      short loc_14000461D
0x1400045fa  cmp     dword ptr [rbx], 28h ; '('
0x1400045fd  jnz     short loc_14000461D
0x1400045ff  test    rbx, rbx
0x140004602  jz      short loc_14000461D
0x140004604  mov     rax, [rbx+20h]
0x140004608  test    rax, rax
0x14000460b  jz      short loc_140004616
0x14000460d  call    _guard_dispatch_icall
0x140004612  mov     [rbx+18h], rax
0x140004616  mov     eax, [rbx]
0x140004618  add     rax, rbx
0x14000461b  jmp     short loc_1400045D0
0x14000461d  xor     edx, edx; Level
0x14000461f  lea     r8, aFxgetnextobjec; "FxGetNextObjectContextTypeInfo failed\n"
0x140004626  lea     ecx, [rdx+4Dh]; ComponentId
0x140004629  call    cs:__imp_DbgPrintEx
0x140004630  nop     dword ptr [rax+rax+00h]
0x140004635  jmp     short loc_1400045C2
0x140004637  xor     eax, eax
0x140004639  mov     rbx, [rsp+38h+arg_0]
0x14000463e  add     rsp, 30h
0x140004642  pop     rdi
0x140004643  retn
```
