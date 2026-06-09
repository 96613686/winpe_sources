# OncRpcRegisterThreadCreateDestroyNotifyCallbacks

- ea: `0x140006e40`
- end: `0x140006e51`
- name: `OncRpcRegisterThreadCreateDestroyNotifyCallbacks`
- size: `17`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 __fastcall OncRpcRegisterThreadCreateDestroyNotifyCallbacks(__int64 (*a1)(void), __int64 (*a2)(void))
{
  __int64 result; // rax

  qword_14001A488 = a1;
  result = 0;
  qword_14001A490 = a2;
  return result;
}

```

## disassembly

```asm
0x140006e40  mov     cs:qword_14001A488, rcx
0x140006e47  xor     eax, eax
0x140006e49  mov     cs:qword_14001A490, rdx
0x140006e50  retn
```
