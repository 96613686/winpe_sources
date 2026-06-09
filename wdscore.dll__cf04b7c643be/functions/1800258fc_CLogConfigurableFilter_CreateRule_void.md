# CLogConfigurableFilter::CreateRule(void)

- ea: `0x1800258fc`
- end: `0x180025972`
- name: `?CreateRule@CLogConfigurableFilter@@IEAAPEAUtagLOG_FILTER_RULE@@XZ`
- size: `118`
- prototype: `struct tagLOG_FILTER_RULE *__fastcall(CLogConfigurableFilter *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180025ce8`

## callees

- `0x180001144`
- `0x18001fe2c`
- `0x1800258fc`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
struct tagLOG_FILTER_RULE *__fastcall CLogConfigurableFilter::CreateRule(CLogConfigurableFilter *this)
{
  _QWORD *v1; // rax
  _DWORD *v2; // rbx

  v1 = operator new(0x28u);
  v2 = v1;
  if ( v1 )
  {
    v1[3] = 0;
    v1[4] = 0;
    v1[2] = 0;
    v1[1] = 0;
    CPtrList<tagLOG_OUTPUT_STACK *>::SetSize(v1 + 1, 100);
  }
  else
  {
    v2 = 0;
  }
  if ( v2 )
    *v2 = 0;
  return (struct tagLOG_FILTER_RULE *)v2;
}

```

## disassembly

```asm
0x1800258fc  mov     [rsp+arg_0], rcx
0x180025901  push    rbx
0x180025902  sub     rsp, 30h
0x180025906  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x18002590f  mov     ecx, 28h ; '('; Size
0x180025914  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180025919  mov     rbx, rax
0x18002591c  mov     [rsp+38h+arg_0], rax
0x180025921  test    rax, rax
0x180025924  jz      short loc_18002595B
0x180025926  lea     rcx, [rax+8]
0x18002592a  mov     [rsp+38h+arg_8], rcx
0x18002592f  mov     qword ptr [rcx+10h], 0
0x180025937  mov     qword ptr [rcx+18h], 0
0x18002593f  mov     qword ptr [rcx+8], 0
0x180025947  mov     qword ptr [rcx], 0
0x18002594e  mov     edx, 64h ; 'd'
0x180025953  call    ?SetSize@?$CPtrList@PEAUtagLOG_OUTPUT_STACK@@@@QEAAHI@Z; CPtrList<tagLOG_OUTPUT_STACK *>::SetSize(uint)
0x180025958  nop
0x180025959  jmp     short loc_18002595D
0x18002595b  xor     ebx, ebx
0x18002595d  test    rbx, rbx
0x180025960  jz      short loc_180025968
0x180025962  mov     dword ptr [rbx], 0
0x180025968  mov     rax, rbx
0x18002596b  add     rsp, 30h
0x18002596f  pop     rbx
0x180025970  retn
```
