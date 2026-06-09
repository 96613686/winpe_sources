# std::unique_ptr<PIN_MAPS_MEM,std::default_delete<PIN_MAPS_MEM>>::operator=<std::default_delete<PIN_MAPS_MEM>,0>(std::unique_ptr<PIN_MAPS_MEM,std::default_delete<PIN_MAPS_MEM>> &&)

- ea: `0x18000c7e8`
- end: `0x18000c814`
- name: `??$?4U?$default_delete@UPIN_MAPS_MEM@@@std@@$0A@@?$unique_ptr@UPIN_MAPS_MEM@@U?$default_delete@UPIN_MAPS_MEM@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z`
- size: `44`
- prototype: `__int64 *__fastcall(__int64 *, __int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180012990`

## callees

- `0x18000c7e8`
- `0x18000f3a4`

## pseudocode

```c
__int64 *__fastcall std::unique_ptr<PIN_MAPS_MEM>::operator=<std::default_delete<PIN_MAPS_MEM>,0>(
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
    std::default_delete<PIN_MAPS_MEM>::operator()();
  return a1;
}

```

## disassembly

```asm
0x18000c7e8  push    rbx
0x18000c7ea  sub     rsp, 20h
0x18000c7ee  mov     rax, [rdx]
0x18000c7f1  mov     rbx, rcx
0x18000c7f4  mov     qword ptr [rdx], 0
0x18000c7fb  mov     rdx, [rcx]
0x18000c7fe  mov     [rcx], rax
0x18000c801  test    rdx, rdx
0x18000c804  jz      short loc_18000C80B
0x18000c806  call    ??R?$default_delete@UPIN_MAPS_MEM@@@std@@QEBAXPEAUPIN_MAPS_MEM@@@Z; std::default_delete<PIN_MAPS_MEM>::operator()(PIN_MAPS_MEM *)
0x18000c80b  mov     rax, rbx
0x18000c80e  add     rsp, 20h
0x18000c812  pop     rbx
0x18000c813  retn
```
