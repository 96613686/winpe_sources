# HTTP2Channel::RuntimeSwapTokenIfNecessary(void * *,int *)

- ea: `0x1800174f0`
- end: `0x180017501`
- name: `?RuntimeSwapTokenIfNecessary@HTTP2Channel@@UEAAJPEAPEAXPEAH@Z`
- size: `17`
- prototype: `__int64 __fastcall(HTTP2Channel *__hidden this, void **, int *)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 __fastcall HTTP2Channel::RuntimeSwapTokenIfNecessary(HTTP2Channel *this, void **a2, int *a3)
{
  __int64 result; // rax

  *a3 = 0;
  result = 0;
  *a2 = 0;
  return result;
}

```

## disassembly

```asm
0x1800174f0  mov     dword ptr [r8], 0
0x1800174f7  xor     eax, eax
0x1800174f9  mov     qword ptr [rdx], 0
0x180017500  retn
```
