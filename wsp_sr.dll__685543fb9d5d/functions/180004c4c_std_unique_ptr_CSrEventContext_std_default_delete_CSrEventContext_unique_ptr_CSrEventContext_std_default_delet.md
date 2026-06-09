# std::unique_ptr<CSrEventContext,std::default_delete<CSrEventContext>>::~unique_ptr<CSrEventContext,std::default_delete<CSrEventContext>>(void)

- ea: `0x180004c4c`
- end: `0x180004c63`
- name: `??1?$unique_ptr@VCSrEventContext@@U?$default_delete@VCSrEventContext@@@std@@@std@@QEAA@XZ`
- size: `23`
- prototype: ``
- caller_count: `9`
- callee_count: `2`
- tags: ``

## callers

- `0x180004dc0`
- `0x180004e50`
- `0x180005090`
- `0x180005120`
- `0x180005330`
- `0x1800053c0`
- `0x18002c9f0`
- `0x18002ca10`
- `0x18002ca30`

## callees

- `0x180004c4c`
- `0x180004cb0`

## pseudocode

```c
__int64 __fastcall std::unique_ptr<CSrEventContext>::~unique_ptr<CSrEventContext>(_QWORD *a1)
{
  __int64 result; // rax

  if ( *a1 )
    return std::default_delete<CSrEventContext>::operator()();
  return result;
}

```

## disassembly

```asm
0x180004c4c  sub     rsp, 28h
0x180004c50  mov     rdx, [rcx]
0x180004c53  test    rdx, rdx
0x180004c56  jz      short loc_180004C5D
0x180004c58  call    ??R?$default_delete@VCSrEventContext@@@std@@QEBAXPEAVCSrEventContext@@@Z; std::default_delete<CSrEventContext>::operator()(CSrEventContext *)
0x180004c5d  add     rsp, 28h
0x180004c61  retn
```
