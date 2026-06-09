# CMcTpOptions::CreateOptions(_WDSMCTP_OPTIONS *,ulong,ulong,...)

- ea: `0x180020350`
- end: `0x18002037b`
- name: `?CreateOptions@CMcTpOptions@@SAKPEAU_WDSMCTP_OPTIONS@@KKZZ`
- size: `43`
- prototype: `unsigned int(struct _WDSMCTP_OPTIONS *, unsigned int, unsigned int, ...)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180008040`
- `0x18001bd40`

## callees

- `0x180020258`

## pseudocode

```c
__int64 CMcTpOptions::CreateOptions(struct _WDSMCTP_OPTIONS *a1, unsigned int a2, unsigned int a3, ...)
{
  va_list va; // [rsp+58h] [rbp+20h] BYREF

  va_start(va, a3);
  return CMcTpOptions::CreateOptions(a3, (u_short *)va, a1, a2);
}

```

## disassembly

```asm
0x180020350  mov     [rsp+arg_10], r8d
0x180020355  mov     qword ptr [rsp+arg_18], r9
0x18002035a  sub     rsp, 38h
0x18002035e  mov     eax, r8d
0x180020361  lea     r10, [rsp+38h+arg_18]
0x180020366  mov     r8, rcx; struct _WDSMCTP_OPTIONS *
0x180020369  mov     r9d, edx; unsigned int
0x18002036c  mov     rdx, r10; char *
0x18002036f  mov     ecx, eax; unsigned int
0x180020371  call    ?CreateOptions@CMcTpOptions@@SAKKPEADPEAU_WDSMCTP_OPTIONS@@K@Z; CMcTpOptions::CreateOptions(ulong,char *,_WDSMCTP_OPTIONS *,ulong)
0x180020376  add     rsp, 38h
0x18002037a  retn
```
