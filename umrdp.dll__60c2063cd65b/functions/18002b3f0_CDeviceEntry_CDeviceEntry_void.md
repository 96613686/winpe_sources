# CDeviceEntry::~CDeviceEntry(void)

- ea: `0x18002b3f0`
- end: `0x18002b470`
- name: `??1CDeviceEntry@@UEAA@XZ`
- size: `128`
- prototype: `void __fastcall(CDeviceEntry *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18002b490`

## callees

- `0x18000ab84`
- `0x18000abc0`
- `0x18002b3f0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b41c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b41c`

## pseudocode

```c
void __fastcall CDeviceEntry::~CDeviceEntry(CDeviceEntry *this)
{
  void *v2; // rcx

  *((_DWORD *)this + 18) |= 0x1000u;
  *(_QWORD *)this = &CServerVCChannel::`vftable'{for `INonDelegatingUnknown'};
  *((_QWORD *)this + 1) = &CDeviceEntry::`vftable'{for `CTSObject'};
  v2 = (void *)*((_QWORD *)this + 12);
  if ( v2 )
  {
    CoTaskMemFree(v2);
    *((_QWORD *)this + 12) = 0;
  }
  CTSCriticalSection::Terminate((CDeviceEntry *)((char *)this + 128));
  TCntPtr<IDispatch>::SafeRelease((char *)this + 120);
  TCntPtr<IDispatch>::SafeRelease((char *)this + 112);
  TCntPtr<IDispatch>::SafeRelease((char *)this + 80);
  *(_QWORD *)this = &CServerVCChannel::`vftable'{for `INonDelegatingUnknown'};
  *((_QWORD *)this + 1) = &CTSObject::`vftable';
  *((_DWORD *)this + 7) |= 8u;
}

```

## disassembly

```asm
0x18002b3f0  push    rbx
0x18002b3f2  sub     rsp, 20h
0x18002b3f6  bts     dword ptr [rcx+48h], 0Ch
0x18002b3fb  lea     rax, ??_7CServerVCChannel@@6BINonDelegatingUnknown@@@; const CServerVCChannel::`vftable'{for `INonDelegatingUnknown'}
0x18002b402  mov     [rcx], rax
0x18002b405  mov     rbx, rcx
0x18002b408  lea     rax, ??_7CDeviceEntry@@6BCTSObject@@@; const CDeviceEntry::`vftable'{for `CTSObject'}
0x18002b40f  mov     [rcx+8], rax
0x18002b413  mov     rcx, [rcx+60h]; pv
0x18002b417  test    rcx, rcx
0x18002b41a  jz      short loc_18002B42A
0x18002b41c  call    cs:__imp_CoTaskMemFree
0x18002b422  mov     qword ptr [rbx+60h], 0
0x18002b42a  lea     rcx, [rbx+80h]; this
0x18002b431  call    ?Terminate@CTSCriticalSection@@QEAAHXZ; CTSCriticalSection::Terminate(void)
0x18002b436  lea     rcx, [rbx+78h]
0x18002b43a  call    ?SafeRelease@?$TCntPtr@UIDispatch@@@@AEAAXXZ; TCntPtr<IDispatch>::SafeRelease(void)
0x18002b43f  lea     rcx, [rbx+70h]
0x18002b443  call    ?SafeRelease@?$TCntPtr@UIDispatch@@@@AEAAXXZ; TCntPtr<IDispatch>::SafeRelease(void)
0x18002b448  lea     rcx, [rbx+50h]
0x18002b44c  call    ?SafeRelease@?$TCntPtr@UIDispatch@@@@AEAAXXZ; TCntPtr<IDispatch>::SafeRelease(void)
0x18002b451  lea     rax, ??_7CServerVCChannel@@6BINonDelegatingUnknown@@@; const CServerVCChannel::`vftable'{for `INonDelegatingUnknown'}
0x18002b458  mov     [rbx], rax
0x18002b45b  lea     rax, ??_7CTSObject@@6B@; const CTSObject::`vftable'
0x18002b462  mov     [rbx+8], rax
0x18002b466  or      dword ptr [rbx+1Ch], 8
0x18002b46a  add     rsp, 20h
0x18002b46e  pop     rbx
0x18002b46f  retn
```
