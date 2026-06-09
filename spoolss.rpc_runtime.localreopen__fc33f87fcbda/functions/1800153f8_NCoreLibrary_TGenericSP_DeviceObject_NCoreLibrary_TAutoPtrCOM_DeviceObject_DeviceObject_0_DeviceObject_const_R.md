# NCoreLibrary::TGenericSP<DeviceObject,NCoreLibrary::TAutoPtrCOM<DeviceObject>,DeviceObject *,0,DeviceObject const *>::Reset(void)

- ea: `0x1800153f8`
- end: `0x18001541c`
- name: `?Reset@?$TGenericSP@VDeviceObject@@V?$TAutoPtrCOM@VDeviceObject@@@NCoreLibrary@@PEAV1@$0A@PEBV1@@NCoreLibrary@@QEAAXXZ`
- size: `36`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800149ac`
- `0x180014b7c`

## callees

- `0x1800139b0`
- `0x1800153f8`

## pseudocode

```c
__int64 __fastcall NCoreLibrary::TGenericSP<DeviceObject,NCoreLibrary::TAutoPtrCOM<DeviceObject>,DeviceObject *,0,DeviceObject const *>::Reset(
        NCoreLibrary::TReferenceCount **a1)
{
  NCoreLibrary::TReferenceCount *v2; // rcx
  __int64 result; // rax

  v2 = *a1;
  if ( v2 )
  {
    result = NCoreLibrary::TReferenceCount::Release(v2);
    *a1 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800153f8  push    rbx
0x1800153fa  sub     rsp, 20h
0x1800153fe  mov     rbx, rcx
0x180015401  mov     rcx, [rcx]; this
0x180015404  test    rcx, rcx
0x180015407  jz      short loc_180015415
0x180015409  call    ?Release@TReferenceCount@NCoreLibrary@@QEBAJXZ; NCoreLibrary::TReferenceCount::Release(void)
0x18001540e  mov     qword ptr [rbx], 0
0x180015415  add     rsp, 20h
0x180015419  pop     rbx
0x18001541a  retn
```
