# PnpGetDeviceRegProp

- ea: `0x180009a20`
- end: `0x180009aa8`
- name: `PnpGetDeviceRegProp`
- size: `136`
- prototype: `CONFIGRET __fastcall(DEVINSTID_W pDeviceID, __int64, ULONG *, void *, PULONG pulLength, DEVNODE pdnDevInst)`
- caller_count: `5`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800083b0`
- `0x180009420`
- `0x180009690`
- `0x180009890`
- `0x1800099d0`

## callees

- `0x180009a20`
- `0x180013d90`

## import_xrefs

- `api-ms-win-devices-config-l1-1-1!CM_Get_DevNode_Registry_PropertyW` at `0x180009a7c`
- `api-ms-win-devices-config-l1-1-1!CM_Get_DevNode_Registry_PropertyW` at `0x180009a7c`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x180009a51`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x180009a51`

## pseudocode

```c
CONFIGRET __fastcall PnpGetDeviceRegProp(
        DEVINSTID_W pDeviceID,
        __int64 a2,
        ULONG *a3,
        void *a4,
        PULONG pulLength,
        DEVNODE pdnDevInst)
{
  CONFIGRET result; // eax

  pdnDevInst = 0;
  result = CM_Locate_DevNodeW(&pdnDevInst, pDeviceID, 5u);
  if ( !result )
    return CM_Get_DevNode_Registry_PropertyW(pdnDevInst, 0xBu, a3, a4, pulLength, 0);
  return result;
}

```

## disassembly

```asm
0x180009a20  mov     [rsp+arg_0], rbx
0x180009a25  mov     [rsp+arg_10], rsi
0x180009a2a  mov     [rsp+arg_8], edx
0x180009a2e  push    rdi
0x180009a2f  sub     rsp, 40h
0x180009a33  mov     rbx, r9
0x180009a36  mov     rdi, r8
0x180009a39  xor     esi, esi
0x180009a3b  mov     [rsp+48h+arg_8], esi
0x180009a3f  mov     [rsp+48h+pdnDevInst], esi
0x180009a43  mov     r8d, 5; ulFlags
0x180009a49  mov     rdx, rcx; pDeviceID
0x180009a4c  lea     rcx, [rsp+48h+pdnDevInst]; pdnDevInst
0x180009a51  call    cs:__imp_CM_Locate_DevNodeW
0x180009a57  mov     [rsp+48h+arg_8], eax
0x180009a5b  test    eax, eax
0x180009a5d  jnz     short loc_180009A86
0x180009a5f  mov     [rsp+48h+ulFlags], esi; ulFlags
0x180009a63  mov     rax, [rsp+48h+arg_20]
0x180009a68  mov     [rsp+48h+pulLength], rax; pulLength
0x180009a6d  mov     r9, rbx; Buffer
0x180009a70  mov     r8, rdi; pulRegDataType
0x180009a73  mov     edx, 0Bh; ulProperty
0x180009a78  mov     ecx, [rsp+48h+pdnDevInst]; dnDevInst
0x180009a7c  call    cs:__imp_CM_Get_DevNode_Registry_PropertyW
0x180009a82  mov     [rsp+48h+arg_8], eax
0x180009a86  jmp     short loc_180009A98
0x180009a88  mov     ecx, eax
0x180009a8a  lea     r8, [rsp+48h+arg_8]
0x180009a8f  call    PnPExceptionHandler
0x180009a94  mov     eax, [rsp+48h+arg_8]
0x180009a98  mov     rbx, [rsp+48h+arg_0]
0x180009a9d  mov     rsi, [rsp+48h+arg_10]
0x180009aa2  add     rsp, 40h
0x180009aa6  pop     rdi
0x180009aa7  retn
0x180018bc0  push    rbp
0x180018bc2  sub     rsp, 30h
0x180018bc6  mov     rbp, rdx
0x180018bc9  mov     eax, 1
0x180018bce  add     rsp, 30h
0x180018bd2  pop     rbp
0x180018bd3  retn
```
