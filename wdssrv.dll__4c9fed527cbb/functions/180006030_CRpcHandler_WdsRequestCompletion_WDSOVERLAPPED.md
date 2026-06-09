# CRpcHandler::WdsRequestCompletion(_WDSOVERLAPPED *)

- ea: `0x180006030`
- end: `0x180006085`
- name: `?WdsRequestCompletion@CRpcHandler@@UEAAXPEAU_WDSOVERLAPPED@@@Z`
- size: `85`
- prototype: `void(CRpcHandler *__hidden this, struct _WDSOVERLAPPED *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180005560`
- `0x18001d010`

## pseudocode

```c
void __fastcall CRpcHandler::WdsRequestCompletion(CRpcHandler *this, struct _WDSOVERLAPPED *a2)
{
  (*(void (__fastcall **)(_QWORD, struct _WDSOVERLAPPED *, char *, char *, char *, _QWORD))(**((_QWORD **)a2 + 280)
                                                                                          + 72LL))(
    *((_QWORD *)a2 + 280),
    a2,
    (char *)this - 16,
    (char *)a2 + 1156,
    (char *)a2 + 104,
    *((_QWORD *)a2 + 276));
  RpcRequest::Release(a2);
}

```

## disassembly

```asm
0x180006030  mov     [rsp+arg_0], rbx
0x180006035  push    rdi
0x180006036  sub     rsp, 40h
0x18000603a  mov     rbx, [rdx+8C0h]
0x180006041  lea     r11, [rdx+68h]
0x180006045  mov     r10, [rdx+8A0h]
0x18000604c  lea     r8, [rcx-10h]
0x180006050  mov     [rsp+48h+var_20], r10
0x180006055  lea     r9, [rdx+484h]
0x18000605c  mov     rcx, rbx
0x18000605f  mov     [rsp+48h+var_28], r11
0x180006064  mov     rax, [rbx]
0x180006067  mov     rdi, rdx
0x18000606a  mov     rax, [rax+48h]
0x18000606e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006073  mov     rcx, rdi; this
0x180006076  mov     rbx, [rsp+48h+arg_0]
0x18000607b  add     rsp, 40h
0x18000607f  pop     rdi
0x180006080  jmp     ?Release@RpcRequest@@QEAAKXZ; RpcRequest::Release(void)
```
