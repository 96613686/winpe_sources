# NCoreLibrary::TGenericSP<DeviceObject,NCoreLibrary::TAutoPtrCOM<DeviceObject>,DeviceObject *,0,DeviceObject const *>::Reset(void)

- ea: `0x180013c2c`
- end: `0x180013c4f`
- name: `?Reset@?$TGenericSP@VDeviceObject@@V?$TAutoPtrCOM@VDeviceObject@@@NCoreLibrary@@PEAV1@$0A@PEBV1@@NCoreLibrary@@QEAAXXZ`
- size: `35`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180013238`
- `0x1800133ec`

## callees

- `0x180012234`
- `0x180013c2c`

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
0x180013c2c  push    rbx
0x180013c2e  sub     rsp, 20h
0x180013c32  mov     rbx, rcx
0x180013c35  mov     rcx, [rcx]; this
0x180013c38  test    rcx, rcx
0x180013c3b  jz      short loc_180013C49
0x180013c3d  call    ?Release@TReferenceCount@NCoreLibrary@@QEBAJXZ; NCoreLibrary::TReferenceCount::Release(void)
0x180013c42  mov     qword ptr [rbx], 0
0x180013c49  add     rsp, 20h
0x180013c4d  pop     rbx
0x180013c4e  retn
```
