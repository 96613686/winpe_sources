# CWdsDeviceControllerPacket::AddManagementController(ushort const *)

- ea: `0x180014f24`
- end: `0x180014f5a`
- name: `?AddManagementController@CWdsDeviceControllerPacket@@QEAAKPEBG@Z`
- size: `54`
- prototype: `unsigned int(CWdsDeviceControllerPacket *__hidden this, const unsigned __int16 *)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180013ed0`
- `0x180014050`
- `0x1800142e0`
- `0x180014590`
- `0x180014740`

## callees

- `0x180011e48`
- `0x1800153bc`

## pseudocode

```c
__int64 __fastcall CWdsDeviceControllerPacket::AddManagementController(
        CWdsDeviceControllerPacket *this,
        unsigned __int16 *a2)
{
  unsigned int v2; // ebx
  __int64 v3; // rdx
  __int64 v4; // r8

  v2 = CControlPacket::AddString(this, L"Controller", 0, 0xFFFFFFFF, a2);
  ElValidateWin32_11(v2, v3, v4, 0xDDu);
  return v2;
}

```

## disassembly

```asm
0x180014f24  push    rbx
0x180014f26  sub     rsp, 30h
0x180014f2a  mov     [rsp+38h+var_18], rdx; unsigned __int16 *
0x180014f2f  or      r9d, 0FFFFFFFFh; unsigned int
0x180014f33  lea     rdx, aController; "Controller"
0x180014f3a  xor     r8d, r8d; unsigned __int16 *
0x180014f3d  call    ?AddString@CControlPacket@@QEAAKPEBG0K0@Z; CControlPacket::AddString(ushort const *,ushort const *,ulong,ushort const *)
0x180014f42  mov     r9d, 0DDh
0x180014f48  mov     ecx, eax
0x180014f4a  mov     ebx, eax
0x180014f4c  call    ElValidateWin32_11
0x180014f51  mov     eax, ebx
0x180014f53  add     rsp, 30h
0x180014f57  pop     rbx
0x180014f58  retn
```
