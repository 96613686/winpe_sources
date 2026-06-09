# Srv2InitializeNodes

- ea: `0x14005e794`
- end: `0x14005e939`
- name: `Srv2InitializeNodes`
- size: `421`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14005f538`

## callees

- `0x140038490`
- `0x14005e638`
- `0x14005e708`
- `0x14005e794`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14005e7df`
- `ntoskrnl!ExAllocatePool2` at `0x14005e86e`
- `ntoskrnl!ExAllocatePool2` at `0x14005e7df`
- `ntoskrnl!ExAllocatePool2` at `0x14005e86e`
- `ntoskrnl!KeQueryHighestNodeNumber` at `0x14005e7ae`
- `ntoskrnl!KeQueryHighestNodeNumber` at `0x14005e7ae`
- `ntoskrnl!KeQueryNodeActiveAffinity` at `0x14005e81a`
- `ntoskrnl!KeQueryNodeActiveAffinity` at `0x14005e81a`
- `ntoskrnl!KeSetSystemGroupAffinityThread` at `0x14005e841`
- `ntoskrnl!KeSetSystemGroupAffinityThread` at `0x14005e854`
- `ntoskrnl!KeSetSystemGroupAffinityThread` at `0x14005e841`
- `ntoskrnl!KeSetSystemGroupAffinityThread` at `0x14005e854`
- `ntoskrnl!KeRevertToUserGroupAffinityThread` at `0x14005e909`
- `ntoskrnl!KeRevertToUserGroupAffinityThread` at `0x14005e909`

## pseudocode

```c
__int64 Srv2InitializeNodes()
{
  USHORT v0; // si
  int v1; // ebx
  char v2; // bp
  USHORT i; // di
  void *Pool2; // rax
  PVOID v5; // rcx
  USHORT j; // cx
  _GROUP_AFFINITY Affinity; // [rsp+20h] [rbp-58h] BYREF
  struct _GROUP_AFFINITY PreviousAffinity; // [rsp+30h] [rbp-48h] BYREF

  Affinity = 0;
  v0 = KeQueryHighestNodeNumber() + 1;
  PreviousAffinity = 0;
  Srv2Nodes = (PVOID)ExAllocatePool2(72, 8LL * v0, 607277900);
  if ( !Srv2Nodes )
  {
    v1 = -1073741670;
LABEL_23:
    Srv2DeinitializeNodes();
    return (unsigned int)v1;
  }
  v2 = 0;
  for ( i = 0; i < v0; ++i )
  {
    KeQueryNodeActiveAffinity(i, &Affinity, 0);
    if ( Affinity.Mask )
    {
      if ( v2 )
      {
        KeSetSystemGroupAffinityThread(&Affinity, 0);
      }
      else
      {
        KeSetSystemGroupAffinityThread(&Affinity, &PreviousAffinity);
        v2 = 1;
      }
      Pool2 = (void *)ExAllocatePool2(74, 64, 607277900);
      v5 = Srv2Nodes;
      *((_QWORD *)Srv2Nodes + i) = Pool2;
      if ( !v5 )
      {
        v1 = -1073741670;
        goto LABEL_20;
      }
      v1 = Srv2InitializeNode(Pool2);
      if ( v1 < 0 )
        goto LABEL_20;
      if ( !Srv2ProxyNode )
        Srv2ProxyNode = *((_QWORD *)Srv2Nodes + i);
    }
  }
  for ( j = 0; j < v0; ++j )
  {
    if ( !*((_QWORD *)Srv2Nodes + j) )
      *((_QWORD *)Srv2Nodes + j) = Srv2ProxyNode;
  }
  v1 = 0;
LABEL_20:
  if ( v2 )
    KeRevertToUserGroupAffinityThread(&PreviousAffinity);
  if ( v1 < 0 )
    goto LABEL_23;
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x14005e794  push    rbx
0x14005e796  push    rbp
0x14005e797  push    rsi
0x14005e798  push    rdi
0x14005e799  push    r14
0x14005e79b  sub     rsp, 50h
0x14005e79f  mov     rax, cs:__security_cookie
0x14005e7a6  xor     rax, rsp
0x14005e7a9  mov     [rsp+78h+var_38], rax
0x14005e7ae  call    cs:__imp_KeQueryHighestNodeNumber
0x14005e7b5  nop     dword ptr [rax+rax+00h]
0x14005e7ba  xorps   xmm0, xmm0
0x14005e7bd  xorps   xmm1, xmm1
0x14005e7c0  mov     ecx, 48h ; 'H'
0x14005e7c5  mov     r8d, 2432534Ch
0x14005e7cb  movups  xmmword ptr [rsp+78h+Affinity.Mask], xmm0
0x14005e7d0  lea     esi, [rax+1]
0x14005e7d3  movzx   edx, si
0x14005e7d6  shl     rdx, 3
0x14005e7da  movups  xmmword ptr [rsp+78h+PreviousAffinity.Mask], xmm1
0x14005e7df  call    cs:__imp_ExAllocatePool2
0x14005e7e6  nop     dword ptr [rax+rax+00h]
0x14005e7eb  mov     cs:Srv2Nodes, rax
0x14005e7f2  test    rax, rax
0x14005e7f5  jnz     short loc_14005E801
0x14005e7f7  mov     ebx, 0C000009Ah
0x14005e7fc  jmp     loc_14005E919
0x14005e801  xor     bpl, bpl
0x14005e804  xor     edi, edi
0x14005e806  cmp     di, si
0x14005e809  jnb     loc_14005E8D0
0x14005e80f  xor     r8d, r8d; Count
0x14005e812  lea     rdx, [rsp+78h+Affinity]; Affinity
0x14005e817  movzx   ecx, di; NodeNumber
0x14005e81a  call    cs:__imp_KeQueryNodeActiveAffinity
0x14005e821  nop     dword ptr [rax+rax+00h]
0x14005e826  cmp     [rsp+78h+Affinity.Mask], 0
0x14005e82c  jz      loc_14005E8C1
0x14005e832  lea     rcx, [rsp+78h+Affinity]; Affinity
0x14005e837  test    bpl, bpl
0x14005e83a  jnz     short loc_14005E852
0x14005e83c  lea     rdx, [rsp+78h+PreviousAffinity]; PreviousAffinity
0x14005e841  call    cs:__imp_KeSetSystemGroupAffinityThread
0x14005e848  nop     dword ptr [rax+rax+00h]
0x14005e84d  mov     bpl, 1
0x14005e850  jmp     short loc_14005E860
0x14005e852  xor     edx, edx; PreviousAffinity
0x14005e854  call    cs:__imp_KeSetSystemGroupAffinityThread
0x14005e85b  nop     dword ptr [rax+rax+00h]
0x14005e860  mov     edx, 40h ; '@'
0x14005e865  mov     r8d, 2432534Ch
0x14005e86b  lea     ecx, [rdx+0Ah]
0x14005e86e  call    cs:__imp_ExAllocatePool2
0x14005e875  nop     dword ptr [rax+rax+00h]
0x14005e87a  mov     rcx, cs:Srv2Nodes
0x14005e881  movzx   r14d, di
0x14005e885  mov     [rcx+r14*8], rax
0x14005e889  test    rcx, rcx
0x14005e88c  jz      short loc_14005E8C9
0x14005e88e  movzx   r8d, di
0x14005e892  lea     rdx, [rsp+78h+Affinity]
0x14005e897  mov     rcx, rax; VirtualAddress
0x14005e89a  call    Srv2InitializeNode
0x14005e89f  mov     ebx, eax
0x14005e8a1  test    eax, eax
0x14005e8a3  js      short loc_14005E8FF
0x14005e8a5  cmp     cs:Srv2ProxyNode, 0
0x14005e8ad  jnz     short loc_14005E8C1
0x14005e8af  mov     rax, cs:Srv2Nodes
0x14005e8b6  mov     rcx, [rax+r14*8]
0x14005e8ba  mov     cs:Srv2ProxyNode, rcx
0x14005e8c1  inc     di
0x14005e8c4  jmp     loc_14005E806
0x14005e8c9  mov     ebx, 0C000009Ah
0x14005e8ce  jmp     short loc_14005E8FF
0x14005e8d0  xor     ecx, ecx
0x14005e8d2  xor     eax, eax
0x14005e8d4  cmp     ax, si
0x14005e8d7  jnb     short loc_14005E8FD
0x14005e8d9  mov     r8, cs:Srv2Nodes
0x14005e8e0  movzx   edx, cx
0x14005e8e3  cmp     qword ptr [r8+rdx*8], 0
0x14005e8e8  jnz     short loc_14005E8F5
0x14005e8ea  mov     rax, cs:Srv2ProxyNode
0x14005e8f1  mov     [r8+rdx*8], rax
0x14005e8f5  inc     cx
0x14005e8f8  cmp     cx, si
0x14005e8fb  jb      short loc_14005E8D9
0x14005e8fd  xor     ebx, ebx
0x14005e8ff  test    bpl, bpl
0x14005e902  jz      short loc_14005E915
0x14005e904  lea     rcx, [rsp+78h+PreviousAffinity]; PreviousAffinity
0x14005e909  call    cs:__imp_KeRevertToUserGroupAffinityThread
0x14005e910  nop     dword ptr [rax+rax+00h]
0x14005e915  test    ebx, ebx
0x14005e917  jns     short loc_14005E91E
0x14005e919  call    Srv2DeinitializeNodes
0x14005e91e  mov     eax, ebx
0x14005e920  mov     rcx, [rsp+78h+var_38]
0x14005e925  xor     rcx, rsp; StackCookie
0x14005e928  call    __security_check_cookie
0x14005e92d  add     rsp, 50h
0x14005e931  pop     r14
0x14005e933  pop     rdi
0x14005e934  pop     rsi
0x14005e935  pop     rbp
0x14005e936  pop     rbx
0x14005e937  retn
```
