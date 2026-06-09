# CLogConfigurableFilter::DestroyRules(void)

- ea: `0x180025a4c`
- end: `0x180025aac`
- name: `?DestroyRules@CLogConfigurableFilter@@IEAAXXZ`
- size: `96`
- prototype: `void __fastcall(CLogConfigurableFilter *__hidden this)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180025604`
- `0x180025ae0`
- `0x180026110`

## callees

- `0x18001f81c`
- `0x1800259d8`
- `0x180025a4c`
- `0x1800274de`

## pseudocode

```c
void __fastcall CLogConfigurableFilter::DestroyRules(CLogConfigurableFilter *this)
{
  char *v1; // rbx
  struct tagLOG_FILTER_RULE *v3; // rax
  CLogConfigurableFilter *v4; // rcx

  v1 = (char *)this + 8;
  *((_DWORD *)this + 5) = 0;
  while ( 1 )
  {
    v3 = (struct tagLOG_FILTER_RULE *)CPtrList<tagLOG_OUTPUT_STACK *>::Next(v1);
    if ( !v3 )
      break;
    CLogConfigurableFilter::DestroyRule(v4, v3);
  }
  if ( *(_QWORD *)v1 )
  {
    memset_0(*(void **)v1, 0, 8LL * *((unsigned int *)v1 + 2));
    *((_DWORD *)v1 + 2) = 0;
  }
  *((_DWORD *)this + 10) = 0;
}

```

## disassembly

```asm
0x180025a4c  mov     [rsp+arg_0], rbx
0x180025a51  push    rdi
0x180025a52  sub     rsp, 20h
0x180025a56  lea     rbx, [rcx+8]
0x180025a5a  mov     rdi, rcx
0x180025a5d  mov     dword ptr [rbx+0Ch], 0
0x180025a64  jmp     short loc_180025A6E
0x180025a66  mov     rdx, rax; struct tagLOG_FILTER_RULE *
0x180025a69  call    ?DestroyRule@CLogConfigurableFilter@@IEAAXPEAUtagLOG_FILTER_RULE@@@Z; CLogConfigurableFilter::DestroyRule(tagLOG_FILTER_RULE *)
0x180025a6e  mov     rcx, rbx
0x180025a71  call    ?Next@?$CPtrList@PEAUtagLOG_OUTPUT_STACK@@@@QEAAPEAUtagLOG_OUTPUT_STACK@@XZ; CPtrList<tagLOG_OUTPUT_STACK *>::Next(void)
0x180025a76  test    rax, rax
0x180025a79  jnz     short loc_180025A66
0x180025a7b  mov     rcx, [rbx]; void *
0x180025a7e  test    rcx, rcx
0x180025a81  jz      short loc_180025A99
0x180025a83  mov     r8d, [rbx+8]
0x180025a87  xor     edx, edx; Val
0x180025a89  shl     r8, 3; Size
0x180025a8d  call    memset_0
0x180025a92  mov     dword ptr [rbx+8], 0
0x180025a99  mov     rbx, [rsp+28h+arg_0]
0x180025a9e  mov     dword ptr [rdi+28h], 0
0x180025aa5  add     rsp, 20h
0x180025aa9  pop     rdi
0x180025aaa  retn
```
