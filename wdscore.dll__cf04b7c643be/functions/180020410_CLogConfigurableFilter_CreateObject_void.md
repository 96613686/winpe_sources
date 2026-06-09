# CLogConfigurableFilter::CreateObject(void)

- ea: `0x180020410`
- end: `0x180020488`
- name: `?CreateObject@CLogConfigurableFilter@@SAPEAVILogProvider@@XZ`
- size: `120`
- prototype: `struct ILogProvider *(void)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x180001144`
- `0x18001fe2c`
- `0x180020410`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
struct ILogProvider *CLogConfigurableFilter::CreateObject(void)
{
  _QWORD *v0; // rbx

  v0 = operator new(0x30u);
  if ( !v0 )
    return 0;
  *v0 = &CLogConfigurableFilter::`vftable';
  v0[3] = 0;
  v0[4] = 0;
  v0[2] = 0;
  v0[1] = 0;
  CPtrList<tagLOG_OUTPUT_STACK *>::SetSize(v0 + 1, 100);
  *((_DWORD *)v0 + 10) = 0;
  return (struct ILogProvider *)v0;
}

```

## disassembly

```asm
0x180020410  push    rbx
0x180020412  sub     rsp, 30h
0x180020416  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x18002041f  mov     ecx, 30h ; '0'; Size
0x180020424  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180020429  mov     rbx, rax
0x18002042c  mov     [rsp+38h+arg_0], rax
0x180020431  test    rax, rax
0x180020434  jz      short loc_18002047C
0x180020436  lea     rax, ??_7CLogConfigurableFilter@@6B@; const CLogConfigurableFilter::`vftable'
0x18002043d  mov     [rbx], rax
0x180020440  lea     rcx, [rbx+8]
0x180020444  mov     [rsp+38h+arg_8], rcx
0x180020449  mov     qword ptr [rcx+10h], 0
0x180020451  mov     qword ptr [rcx+18h], 0
0x180020459  mov     qword ptr [rcx+8], 0
0x180020461  mov     qword ptr [rcx], 0
0x180020468  mov     edx, 64h ; 'd'
0x18002046d  call    ?SetSize@?$CPtrList@PEAUtagLOG_OUTPUT_STACK@@@@QEAAHI@Z; CPtrList<tagLOG_OUTPUT_STACK *>::SetSize(uint)
0x180020472  nop
0x180020473  mov     dword ptr [rbx+28h], 0
0x18002047a  jmp     short loc_18002047E
0x18002047c  xor     ebx, ebx
0x18002047e  mov     rax, rbx
0x180020481  add     rsp, 30h
0x180020485  pop     rbx
0x180020486  retn
```
