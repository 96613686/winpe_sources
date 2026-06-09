# utl::default_delete<LAUNCH_URL_PARAMETERS>::operator()(LAUNCH_URL_PARAMETERS *)

- ea: `0x18000b000`
- end: `0x18000b023`
- name: `??R?$default_delete@ULAUNCH_URL_PARAMETERS@@@utl@@QEBAXPEAULAUNCH_URL_PARAMETERS@@@Z`
- size: `35`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000afbc`

## callees

- `0x18000302c`
- `0x18000afd8`
- `0x18000b000`

## pseudocode

```c
void __fastcall utl::default_delete<LAUNCH_URL_PARAMETERS>::operator()(__int64 a1, LAUNCH_URL_PARAMETERS *a2)
{
  if ( a2 )
  {
    LAUNCH_URL_PARAMETERS::~LAUNCH_URL_PARAMETERS(a2);
    operator delete(a2);
  }
}

```

## disassembly

```asm
0x18000b000  test    rdx, rdx
0x18000b003  jz      short locret_18000B022
0x18000b005  push    rbx
0x18000b006  sub     rsp, 20h
0x18000b00a  mov     rcx, rdx; this
0x18000b00d  mov     rbx, rdx
0x18000b010  call    ??1LAUNCH_URL_PARAMETERS@@QEAA@XZ; LAUNCH_URL_PARAMETERS::~LAUNCH_URL_PARAMETERS(void)
0x18000b015  mov     rcx, rbx; Block
0x18000b018  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000b01d  add     rsp, 20h
0x18000b021  pop     rbx
0x18000b022  retn
```
