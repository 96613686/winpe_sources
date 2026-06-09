# std::unique_ptr<CSrEventContext,std::default_delete<CSrEventContext>>::operator=<std::default_delete<CSrEventContext>,0>(std::unique_ptr<CSrEventContext,std::default_delete<CSrEventContext>> &&)

- ea: `0x180004bd4`
- end: `0x180004bf9`
- name: `??$?4U?$default_delete@VCSrEventContext@@@std@@$0A@@?$unique_ptr@VCSrEventContext@@U?$default_delete@VCSrEventContext@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z`
- size: `37`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180004dc0`
- `0x180004e50`
- `0x180005090`
- `0x180005120`
- `0x180005330`
- `0x1800053c0`

## callees

- `0x180004d1c`

## pseudocode

```c
__int64 *__fastcall std::unique_ptr<CSrEventContext>::operator=<std::default_delete<CSrEventContext>,0>(
        __int64 *a1,
        __int64 *a2)
{
  __int64 v4; // rdx

  v4 = *a2;
  *a2 = 0;
  std::unique_ptr<CSrEventContext>::reset(a1, v4);
  return a1;
}

```

## disassembly

```asm
0x180004bd4  push    rbx
0x180004bd6  sub     rsp, 20h
0x180004bda  mov     rax, rdx
0x180004bdd  mov     rbx, rcx
0x180004be0  mov     rdx, [rdx]
0x180004be3  mov     qword ptr [rax], 0
0x180004bea  call    ?reset@?$unique_ptr@VCSrEventContext@@U?$default_delete@VCSrEventContext@@@std@@@std@@QEAAXPEAVCSrEventContext@@@Z; std::unique_ptr<CSrEventContext>::reset(CSrEventContext *)
0x180004bef  mov     rax, rbx
0x180004bf2  add     rsp, 20h
0x180004bf6  pop     rbx
0x180004bf7  retn
```
