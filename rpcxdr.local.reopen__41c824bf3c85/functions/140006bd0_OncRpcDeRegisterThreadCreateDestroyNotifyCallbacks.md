# OncRpcDeRegisterThreadCreateDestroyNotifyCallbacks

- ea: `0x140006bd0`
- end: `0x140006be9`
- name: `OncRpcDeRegisterThreadCreateDestroyNotifyCallbacks`
- size: `25`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 OncRpcDeRegisterThreadCreateDestroyNotifyCallbacks()
{
  __int64 result; // rax

  qword_14001A488 = 0;
  result = 0;
  qword_14001A490 = 0;
  return result;
}

```

## disassembly

```asm
0x140006bd0  mov     cs:qword_14001A488, 0
0x140006bdb  xor     eax, eax
0x140006bdd  mov     cs:qword_14001A490, 0
0x140006be8  retn
```
