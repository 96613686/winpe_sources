# PnpSetDeviceRegProp

- ea: `0x180013bdc`
- end: `0x180013c4b`
- name: `PnpSetDeviceRegProp`
- size: `111`
- prototype: `CONFIGRET __fastcall(DEVINSTID_W pDeviceID, __int64, __int64, const void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800056d0`

## callees

- `0x180013bdc`
- `0x180013d90`

## import_xrefs

- `api-ms-win-devices-config-l1-1-1!CM_Set_DevNode_Registry_PropertyW` at `0x180013c29`
- `api-ms-win-devices-config-l1-1-1!CM_Set_DevNode_Registry_PropertyW` at `0x180013c29`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x180013c09`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x180013c09`

## pseudocode

```c
CONFIGRET __fastcall PnpSetDeviceRegProp(DEVINSTID_W pDeviceID, __int64 a2, __int64 a3, const void *a4)
{
  CONFIGRET result; // eax
  DEVINST dnDevInst; // [rsp+58h] [rbp+10h] BYREF
  CONFIGRET v7; // [rsp+60h] [rbp+18h]

  v7 = 0;
  dnDevInst = 0;
  result = CM_Locate_DevNodeW(&dnDevInst, pDeviceID, 5u);
  v7 = result;
  if ( !result )
    return CM_Set_DevNode_Registry_PropertyW(dnDevInst, 0xBu, a4, 4u, 0);
  return result;
}

```

## disassembly

```asm
0x180013bdc  mov     rax, rsp
0x180013bdf  mov     [rax+18h], r8d
0x180013be3  mov     [rax+10h], edx
0x180013be6  push    rbx
0x180013be7  sub     rsp, 40h
0x180013beb  mov     rbx, r9
0x180013bee  mov     dword ptr [rax+18h], 0
0x180013bf5  mov     dword ptr [rax+10h], 0
0x180013bfc  mov     r8d, 5; ulFlags
0x180013c02  mov     rdx, rcx; pDeviceID
0x180013c05  lea     rcx, [rax+10h]; pdnDevInst
0x180013c09  call    cs:__imp_CM_Locate_DevNodeW
0x180013c0f  mov     [rsp+48h+arg_10], eax
0x180013c13  test    eax, eax
0x180013c15  jnz     short loc_180013C33
0x180013c17  mov     [rsp+48h+ulFlags], eax; ulFlags
0x180013c1b  lea     r9d, [rax+4]; ulLength
0x180013c1f  mov     r8, rbx; Buffer
0x180013c22  lea     edx, [rax+0Bh]; ulProperty
0x180013c25  mov     ecx, [rsp+48h+dnDevInst]; dnDevInst
0x180013c29  call    cs:__imp_CM_Set_DevNode_Registry_PropertyW
0x180013c2f  mov     [rsp+48h+arg_10], eax
0x180013c33  jmp     short loc_180013C45
0x180013c35  mov     ecx, eax
0x180013c37  lea     r8, [rsp+48h+arg_10]
0x180013c3c  call    PnPExceptionHandler
0x180013c41  mov     eax, [rsp+48h+arg_10]
0x180013c45  add     rsp, 40h
0x180013c49  pop     rbx
0x180013c4a  retn
0x18001924a  push    rbp
0x18001924c  sub     rsp, 30h
0x180019250  mov     rbp, rdx
0x180019253  mov     eax, 1
0x180019258  add     rsp, 30h
0x18001925c  pop     rbp
0x18001925d  retn
```
