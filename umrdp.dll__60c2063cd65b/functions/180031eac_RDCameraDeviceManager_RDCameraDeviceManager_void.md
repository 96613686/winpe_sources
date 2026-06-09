# RDCameraDeviceManager::~RDCameraDeviceManager(void)

- ea: `0x180031eac`
- end: `0x180031efc`
- name: `??1RDCameraDeviceManager@@MEAA@XZ`
- size: `80`
- prototype: `void __fastcall(RDCameraDeviceManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180031820`

## callees

- `0x18000a4f0`
- `0x18000b5b8`
- `0x180030e48`
- `0x180031eac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180031ee9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180031ee9`

## pseudocode

```c
void __fastcall RDCameraDeviceManager::~RDCameraDeviceManager(RDCameraDeviceManager *this)
{
  __int64 v2; // rdx
  __int64 v3; // r8
  __int64 v4; // r9
  utl::_RefCountBase *v5; // rcx

  *(_QWORD *)this = &RDCameraDeviceManager::`vftable';
  DeviceIdentityList::Clear((RDCameraDeviceManager *)((char *)this + 608));
  Microsoft::WRL::ComPtr<IServerVCChannelManager>::InternalRelease((char *)this + 600, v2, v3, v4);
  v5 = (utl::_RefCountBase *)*((_QWORD *)this + 8);
  if ( v5 )
    utl::_RefCountBase::_DecStrong(v5);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  *((_DWORD *)this + 3) = -1073741823;
}

```

## disassembly

```asm
0x180031eac  push    rbx
0x180031eae  sub     rsp, 20h
0x180031eb2  lea     rax, ??_7RDCameraDeviceManager@@6B@; const RDCameraDeviceManager::`vftable'
0x180031eb9  mov     rbx, rcx
0x180031ebc  mov     [rcx], rax
0x180031ebf  add     rcx, 260h; this
0x180031ec6  call    ?Clear@DeviceIdentityList@@QEAAXXZ; DeviceIdentityList::Clear(void)
0x180031ecb  lea     rcx, [rbx+258h]
0x180031ed2  call    ?InternalRelease@?$ComPtr@UIServerVCChannelManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IServerVCChannelManager>::InternalRelease(void)
0x180031ed7  mov     rcx, [rbx+40h]; this
0x180031edb  test    rcx, rcx
0x180031ede  jz      short loc_180031EE5
0x180031ee0  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x180031ee5  lea     rcx, [rbx+10h]; lpCriticalSection
0x180031ee9  call    cs:__imp_DeleteCriticalSection
0x180031eef  mov     dword ptr [rbx+0Ch], 0C0000001h
0x180031ef6  add     rsp, 20h
0x180031efa  pop     rbx
0x180031efb  retn
```
