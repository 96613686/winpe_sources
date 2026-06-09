# OncRpcConnMgrpConnectionFree

- ea: `0x1400082a8`
- end: `0x1400083b1`
- name: `OncRpcConnMgrpConnectionFree`
- size: `265`
- prototype: ``
- caller_count: `7`
- callee_count: `5`
- tags: ``

## callers

- `0x140006228`
- `0x140006aa0`
- `0x140006ad0`
- `0x1400070c4`
- `0x140007394`
- `0x14000d300`
- `0x140010080`

## callees

- `0x1400020c0`
- `0x1400082a8`
- `0x1400083b8`
- `0x14000880c`
- `0x140015680`

## pseudocode

```c

```

## disassembly

```asm
0x1400082a8  mov     [rsp+arg_0], rbx
0x1400082ad  mov     [rsp+arg_8], rsi
0x1400082b2  push    rdi
0x1400082b3  sub     rsp, 30h
0x1400082b7  mov     rbx, rcx
0x1400082ba  xor     ecx, ecx
0x1400082bc  cmp     [rbx+0D8h], rcx
0x1400082c3  jz      loc_140008398
0x1400082c9  lea     rdi, [rbx+0E8h]
0x1400082d0  and     dword ptr [rdi], 0FFFFFFFEh
0x1400082d3  mov     rax, [rbx+0E0h]
0x1400082da  mov     [rdi+28h], rax
0x1400082de  lea     rax, OncRpcConnMgrpConnectionClosePostIrpCompletionCallback
0x1400082e5  mov     [rdi+30h], rax
0x1400082e9  mov     [rdi+8], rcx
0x1400082ed  mov     [rdi+10h], rcx
0x1400082f1  mov     [rdi+38h], rbx
0x1400082f5  mov     rax, cs:WPP_GLOBAL_Control
0x1400082fc  lea     rsi, WPP_GLOBAL_Control
0x140008303  cmp     rax, rsi
0x140008306  jz      short loc_140008335
0x140008308  mov     eax, [rax+2Ch]
0x14000830b  test    al, 8
0x14000830d  jz      short loc_140008335
0x14000830f  mov     ecx, [rbx+4]
0x140008312  mov     edx, 0Dh
0x140008317  mov     eax, [rbx+50h]
0x14000831a  mov     r9, rbx
0x14000831d  mov     [rsp+38h+var_10], eax
0x140008321  mov     [rsp+38h+var_18], ecx
0x140008325  mov     rcx, cs:WPP_GLOBAL_Control
0x14000832c  mov     rcx, [rcx+18h]
0x140008330  call    WPP_SF_qdL
0x140008335  mov     rax, [rdi+28h]
0x140008339  mov     rcx, [rbx+0D8h]
0x140008340  mov     rdx, [rax+0B8h]
0x140008347  lea     rax, OncRpcConnMgrpWskAsynchronousIrpCompletion
0x14000834e  mov     r8, [rcx]
0x140008351  mov     [rdx-10h], rax
0x140008355  mov     [rdx-8], rdi
0x140008359  mov     byte ptr [rdx-45h], 0E0h
0x14000835d  mov     rax, [r8+8]
0x140008361  mov     rdx, [rdi+28h]
0x140008365  call    _guard_dispatch_icall
0x14000836a  mov     rcx, cs:WPP_GLOBAL_Control
0x140008371  cmp     rcx, rsi
0x140008374  jz      short loc_1400083A0
0x140008376  mov     edx, [rcx+2Ch]
0x140008379  test    dl, 1
0x14000837c  jz      short loc_1400083A0
0x14000837e  mov     rcx, [rcx+18h]
0x140008382  lea     r8, WPP_ea71b91709de3d359d9afa6debb6deb4_Traceguids
0x140008389  mov     edx, 49h ; 'I'
0x14000838e  mov     r9d, eax
0x140008391  call    WPP_SF_d
0x140008396  jmp     short loc_1400083A0
0x140008398  mov     rcx, rbx
0x14000839b  call    OncRpcConnMgrpConnectionFreeInternal
0x1400083a0  mov     rbx, [rsp+38h+arg_0]
0x1400083a5  mov     rsi, [rsp+38h+arg_8]
0x1400083aa  add     rsp, 30h
0x1400083ae  pop     rdi
0x1400083af  retn
```
