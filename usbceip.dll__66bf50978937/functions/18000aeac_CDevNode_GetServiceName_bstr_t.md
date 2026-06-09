# CDevNode::GetServiceName(_bstr_t &)

- ea: `0x18000aeac`
- end: `0x18000aefa`
- name: `?GetServiceName@CDevNode@@QEAAXAEAV_bstr_t@@@Z`
- size: `78`
- prototype: `void __fastcall(CDevNode *__hidden this, struct _bstr_t *)`
- caller_count: `4`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180005a48`
- `0x180006d2c`
- `0x180007b44`
- `0x180008610`

## callees

- `0x180007afc`
- `0x18000a618`
- `0x18000ae48`
- `0x18000aeac`

## pseudocode

```c
void __fastcall CDevNode::GetServiceName(CDevNode *this, struct _bstr_t *a2)
{
  if ( CDevNode::DevicePropertyExists(this, &DEVPKEY_Device_Service) )
    CDevNode::GetProperty(this, &DEVPKEY_Device_Service, a2);
  else
    _bstr_t::operator=(a2, (const unsigned __int16 *)byte_180013A54);
}

```

## disassembly

```asm
0x18000aeac  mov     [rsp+arg_0], rbx
0x18000aeb1  push    rdi
0x18000aeb2  sub     rsp, 20h
0x18000aeb6  mov     rbx, rdx
0x18000aeb9  mov     rdi, rcx
0x18000aebc  lea     rdx, DEVPKEY_Device_Service; struct _DEVPROPKEY *
0x18000aec3  call    ?DevicePropertyExists@CDevNode@@QEAAEAEBU_DEVPROPKEY@@@Z; CDevNode::DevicePropertyExists(_DEVPROPKEY const &)
0x18000aec8  test    al, al
0x18000aeca  jz      short loc_18000AEE0
0x18000aecc  mov     r8, rbx; struct _bstr_t *
0x18000aecf  lea     rdx, DEVPKEY_Device_Service; struct _DEVPROPKEY *
0x18000aed6  mov     rcx, rdi; this
0x18000aed9  call    ?GetProperty@CDevNode@@QEAAXAEBU_DEVPROPKEY@@AEAV_bstr_t@@@Z; CDevNode::GetProperty(_DEVPROPKEY const &,_bstr_t &)
0x18000aede  jmp     short loc_18000AEEF
0x18000aee0  lea     rdx, byte_180013A54
0x18000aee7  mov     rcx, rbx
0x18000aeea  call    ??4_bstr_t@@QEAAAEAV0@PEBG@Z; _bstr_t::operator=(ushort const *)
0x18000aeef  mov     rbx, [rsp+28h+arg_0]
0x18000aef4  add     rsp, 20h
0x18000aef8  pop     rdi
0x18000aef9  retn
```
