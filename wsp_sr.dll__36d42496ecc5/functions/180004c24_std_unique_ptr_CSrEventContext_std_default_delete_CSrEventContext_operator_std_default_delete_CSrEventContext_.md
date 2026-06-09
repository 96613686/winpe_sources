# std::unique_ptr<CSrEventContext,std::default_delete<CSrEventContext>>::operator=<std::default_delete<CSrEventContext>,0>(std::unique_ptr<CSrEventContext,std::default_delete<CSrEventContext>> &&)

- ea: `0x180004c24`
- end: `0x180004c50`
- name: `??$?4U?$default_delete@VCSrEventContext@@@std@@$0A@@?$unique_ptr@VCSrEventContext@@U?$default_delete@VCSrEventContext@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z`
- size: `44`
- prototype: `__int64 *__fastcall(__int64 *, __int64 *)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x180004df0`
- `0x180004e80`
- `0x180005080`
- `0x180005110`
- `0x180005310`
- `0x1800053a0`

## callees

- `0x180004c24`
- `0x180004cfc`

## pseudocode

```c
__int64 *__fastcall std::unique_ptr<CSrEventContext>::operator=<std::default_delete<CSrEventContext>,0>(
        __int64 *a1,
        __int64 *a2)
{
  __int64 v2; // rax
  __int64 v4; // rdx

  v2 = *a2;
  *a2 = 0;
  v4 = *a1;
  *a1 = v2;
  if ( v4 )
    std::default_delete<CSrEventContext>::operator()();
  return a1;
}

```

## disassembly

```asm
0x180004c24  push    rbx
0x180004c26  sub     rsp, 20h
0x180004c2a  mov     rax, [rdx]
0x180004c2d  mov     rbx, rcx
0x180004c30  mov     qword ptr [rdx], 0
0x180004c37  mov     rdx, [rcx]
0x180004c3a  mov     [rcx], rax
0x180004c3d  test    rdx, rdx
0x180004c40  jz      short loc_180004C47
0x180004c42  call    ??R?$default_delete@VCSrEventContext@@@std@@QEBAXPEAVCSrEventContext@@@Z; std::default_delete<CSrEventContext>::operator()(CSrEventContext *)
0x180004c47  mov     rax, rbx
0x180004c4a  add     rsp, 20h
0x180004c4e  pop     rbx
0x180004c4f  retn
```
