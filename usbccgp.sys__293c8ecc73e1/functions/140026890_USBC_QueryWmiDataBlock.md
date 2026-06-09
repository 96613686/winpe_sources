# USBC_QueryWmiDataBlock

- ea: `0x140026890`
- end: `0x1400268f3`
- name: `USBC_QueryWmiDataBlock`
- size: `99`
- prototype: `__int64 __usercall@<rax>(PDEVICE_OBJECT DeviceObject@<rcx>, PIRP Irp@<rdx>, int, int, int, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140026890`
- `0x14002db28`

## import_xrefs

- `WMILIB!WmiCompleteRequest` at `0x1400268db`
- `WMILIB!WmiCompleteRequest` at `0x1400268db`

## pseudocode

```c
NTSTATUS __fastcall USBC_QueryWmiDataBlock(
        PDEVICE_OBJECT DeviceObject,
        PIRP Irp,
        int a3,
        __int64 a4,
        int a5,
        int a6,
        unsigned int a7,
        __int64 a8)
{
  ULONG v8; // r9d
  NTSTATUS ParentNodeInfo; // eax
  ULONG BufferUsed; // [rsp+50h] [rbp+18h] BYREF

  v8 = 0;
  BufferUsed = 0;
  if ( a3 )
  {
    ParentNodeInfo = -1073741163;
  }
  else
  {
    ParentNodeInfo = GetParentNodeInfo(DeviceObject, a8, a7, &BufferUsed);
    v8 = BufferUsed;
  }
  return WmiCompleteRequest(DeviceObject, Irp, ParentNodeInfo, v8, 0);
}

```

## disassembly

```asm
0x140026890  mov     [rsp+arg_0], rbx
0x140026895  push    rdi
0x140026896  sub     rsp, 30h
0x14002689a  xor     r9d, r9d
0x14002689d  mov     rdi, rdx
0x1400268a0  mov     [rsp+38h+BufferUsed], r9d
0x1400268a5  mov     rbx, rcx
0x1400268a8  test    r8d, r8d
0x1400268ab  jz      short loc_1400268B4
0x1400268ad  mov     eax, 0C0000295h
0x1400268b2  jmp     short loc_1400268CD
0x1400268b4  mov     r8d, [rsp+38h+arg_30]
0x1400268b9  lea     r9, [rsp+38h+BufferUsed]
0x1400268be  mov     rdx, [rsp+38h+arg_38]
0x1400268c3  call    GetParentNodeInfo
0x1400268c8  mov     r9d, [rsp+38h+BufferUsed]; BufferUsed
0x1400268cd  mov     r8d, eax; Status
0x1400268d0  mov     [rsp+38h+PriorityBoost], 0; PriorityBoost
0x1400268d5  mov     rdx, rdi; Irp
0x1400268d8  mov     rcx, rbx; DeviceObject
0x1400268db  call    cs:__imp_WmiCompleteRequest
0x1400268e2  nop     dword ptr [rax+rax+00h]
0x1400268e7  mov     rbx, [rsp+38h+arg_0]
0x1400268ec  add     rsp, 30h
0x1400268f0  pop     rdi
0x1400268f1  retn
```
