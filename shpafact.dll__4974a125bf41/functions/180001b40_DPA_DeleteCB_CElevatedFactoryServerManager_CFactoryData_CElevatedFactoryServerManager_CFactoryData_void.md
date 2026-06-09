# DPA_DeleteCB<CElevatedFactoryServerManager::CFactoryData>(CElevatedFactoryServerManager::CFactoryData *,void *)

- ea: `0x180001b40`
- end: `0x180001b63`
- name: `??$DPA_DeleteCB@VCFactoryData@CElevatedFactoryServerManager@@@@YAHPEAVCFactoryData@CElevatedFactoryServerManager@@PEAX@Z`
- size: `35`
- prototype: `int __stdcall(void *p, void *pData)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180001b40`
- `0x180004010`

## pseudocode

```c
__int64 __fastcall DPA_DeleteCB<CElevatedFactoryServerManager::CFactoryData>(
        void (__fastcall ***p)(_QWORD, __int64),
        void *pData)
{
  if ( p )
    (**p)(p, 1);
  return 1;
}

```

## disassembly

```asm
0x180001b40  sub     rsp, 28h
0x180001b44  test    rcx, rcx
0x180001b47  jz      short loc_180001B59
0x180001b49  mov     rdx, [rcx]
0x180001b4c  mov     rax, [rdx]
0x180001b4f  mov     edx, 1
0x180001b54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001b59  mov     eax, 1
0x180001b5e  add     rsp, 28h
0x180001b62  retn
```
