# XInterface<ITextServices>::~XInterface<ITextServices>(void)

- ea: `0x18000fbf0`
- end: `0x18000fc18`
- name: `??1?$XInterface@VITextServices@@@@QEAA@XZ`
- size: `40`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18001a67f`
- `0x18001a691`
- `0x18001a6b5`
- `0x18001a86a`

## callees

- `0x18000fbf0`
- `0x18001b010`

## pseudocode

```c
__int64 __fastcall XInterface<ITextServices>::~XInterface<ITextServices>(__int64 *a1)
{
  __int64 v1; // rdx
  __int64 result; // rax

  v1 = *a1;
  *a1 = 0;
  if ( v1 )
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
  return result;
}

```

## disassembly

```asm
0x18000fbf0  sub     rsp, 28h
0x18000fbf4  mov     rdx, [rcx]
0x18000fbf7  mov     qword ptr [rcx], 0
0x18000fbfe  test    rdx, rdx
0x18000fc01  jz      short loc_18000FC13
0x18000fc03  mov     rax, [rdx]
0x18000fc06  mov     rcx, rdx
0x18000fc09  mov     rax, [rax+10h]
0x18000fc0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fc12  nop
0x18000fc13  add     rsp, 28h
0x18000fc17  retn
```
