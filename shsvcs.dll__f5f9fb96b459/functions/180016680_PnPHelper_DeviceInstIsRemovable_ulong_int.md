# PnPHelper::DeviceInstIsRemovable(ulong,int *)

- ea: `0x180016680`
- end: `0x1800166d7`
- name: `?DeviceInstIsRemovable@PnPHelper@@YAJKPEAH@Z`
- size: `87`
- prototype: `__int64 __fastcall(PnPHelper *this, int *, int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18002cf90`

## callees

- `0x180016680`

## import_xrefs

- `CFGMGR32!CM_Get_DevNode_Registry_Property_ExW` at `0x1800166b9`
- `CFGMGR32!CM_Get_DevNode_Registry_Property_ExW` at `0x1800166b9`

## pseudocode

```c
__int64 __fastcall PnPHelper::DeviceInstIsRemovable(PnPHelper *this, int *a2, int *a3)
{
  unsigned int Buffer; // [rsp+58h] [rbp+10h] BYREF
  ULONG pulLength; // [rsp+60h] [rbp+18h] BYREF

  pulLength = 4;
  *a2 = 0;
  Buffer = 0;
  if ( !CM_Get_DevNode_Registry_Property_ExW((DEVINST)this, 0x10u, 0, &Buffer, &pulLength, 0, 0) )
    *a2 = (Buffer >> 2) & 1;
  return 0;
}

```

## disassembly

```asm
0x180016680  push    rbx
0x180016682  sub     rsp, 40h
0x180016686  xor     eax, eax
0x180016688  mov     [rsp+48h+arg_10], 4
0x180016690  mov     [rsp+48h+hMachine], rax; hMachine
0x180016695  lea     r9, [rsp+48h+Buffer]; Buffer
0x18001669a  mov     [rsp+48h+ulFlags], eax; ulFlags
0x18001669e  mov     rbx, rdx
0x1800166a1  mov     [rdx], eax
0x1800166a3  xor     r8d, r8d; pulRegDataType
0x1800166a6  mov     [rsp+48h+Buffer], eax
0x1800166aa  mov     edx, 10h; ulProperty
0x1800166af  lea     rax, [rsp+48h+arg_10]
0x1800166b4  mov     [rsp+48h+pulLength], rax; pulLength
0x1800166b9  call    cs:__imp_CM_Get_DevNode_Registry_Property_ExW
0x1800166bf  test    eax, eax
0x1800166c1  jnz     short loc_1800166CF
0x1800166c3  mov     eax, [rsp+48h+Buffer]
0x1800166c7  shr     eax, 2
0x1800166ca  and     eax, 1
0x1800166cd  mov     [rbx], eax
0x1800166cf  xor     eax, eax
0x1800166d1  add     rsp, 40h
0x1800166d5  pop     rbx
0x1800166d6  retn
```
