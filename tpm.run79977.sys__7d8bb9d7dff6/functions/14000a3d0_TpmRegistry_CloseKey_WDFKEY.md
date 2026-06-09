# TpmRegistry::CloseKey(WDFKEY__ *)

- ea: `0x14000a3d0`
- end: `0x14000a3fc`
- name: `?CloseKey@TpmRegistry@@CAXPEAUWDFKEY__@@@Z`
- size: `44`
- prototype: `void __fastcall(struct WDFKEY__ *)`
- caller_count: `10`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140009db0`
- `0x140009fc8`
- `0x14000a4f0`
- `0x14000b0a8`
- `0x14000b6c8`
- `0x14000b7a8`
- `0x14000bf68`
- `0x14002f7a4`
- `0x1400300e0`
- `0x140030218`

## callees

- `0x14000a3d0`
- `0x140039780`

## pseudocode

```c
void __fastcall TpmRegistry::CloseKey(struct WDFKEY__ *a1)
{
  if ( a1 )
    (*((void (__fastcall **)(PKDPC, struct WDFKEY__ *))WPP_MAIN_CB.Queue.Wcb.CurrentIrp + 231))(
      WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc,
      a1);
}

```

## disassembly

```asm
0x14000a3d0  sub     rsp, 28h
0x14000a3d4  test    rcx, rcx
0x14000a3d7  jz      short loc_14000A3F6
0x14000a3d9  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+38h
0x14000a3e0  mov     rdx, rcx
0x14000a3e3  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+40h
0x14000a3ea  mov     rax, [rax+738h]
0x14000a3f1  call    _guard_dispatch_icall
0x14000a3f6  add     rsp, 28h
0x14000a3fa  retn
```
