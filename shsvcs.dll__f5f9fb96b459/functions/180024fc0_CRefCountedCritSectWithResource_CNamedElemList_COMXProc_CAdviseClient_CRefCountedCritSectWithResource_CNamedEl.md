# CRefCountedCritSectWithResource<CNamedElemList<COMXProc::CAdviseClient>>::~CRefCountedCritSectWithResource<CNamedElemList<COMXProc::CAdviseClient>>(void)

- ea: `0x180024fc0`
- end: `0x180024ff5`
- name: `??1?$CRefCountedCritSectWithResource@V?$CNamedElemList@VCAdviseClient@COMXProc@@@@@@UEAA@XZ`
- size: `53`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800251f0`

## callees

- `0x180024fc0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180024fea`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180024fea`

## pseudocode

```c
void __fastcall CRefCountedCritSectWithResource<CNamedElemList<COMXProc::CAdviseClient>>::~CRefCountedCritSectWithResource<CNamedElemList<COMXProc::CAdviseClient>>(
        __int64 a1)
{
  bool v1; // zf

  v1 = *(_DWORD *)(a1 + 48) == 0;
  *(_QWORD *)(a1 + 56) = &PnPServices::CPnPInterfaceEvent::`vftable';
  *(_QWORD *)a1 = &CCritSectWithResource<CNamedElemList<PnP::CMiscDeviceInterface>>::`vftable';
  if ( !v1 )
  {
    *(_DWORD *)(a1 + 48) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  }
}

```

## disassembly

```asm
0x180024fc0  sub     rsp, 28h
0x180024fc4  cmp     dword ptr [rcx+30h], 0
0x180024fc8  lea     rax, ??_7CPnPInterfaceEvent@PnPServices@@6B@; const PnPServices::CPnPInterfaceEvent::`vftable'
0x180024fcf  mov     [rcx+38h], rax
0x180024fd3  lea     rax, ??_7?$CCritSectWithResource@V?$CNamedElemList@VCMiscDeviceInterface@PnP@@@@@@6B@; const CCritSectWithResource<CNamedElemList<PnP::CMiscDeviceInterface>>::`vftable'
0x180024fda  mov     [rcx], rax
0x180024fdd  jz      short loc_180024FF0
0x180024fdf  mov     dword ptr [rcx+30h], 0
0x180024fe6  add     rcx, 8; lpCriticalSection
0x180024fea  call    cs:__imp_DeleteCriticalSection
0x180024ff0  add     rsp, 28h
0x180024ff4  retn
```
