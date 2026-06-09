# Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)

- ea: `0x180016da0`
- end: `0x180016dbc`
- name: `?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z`
- size: `28`
- prototype: `__int64 __fastcall(unsigned int *, __int64, unsigned int)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180016740`
- `0x180016840`
- `0x1800168e0`
- `0x180016a5c`
- `0x180016f70`
- `0x180017028`

## callees

- `0x180016e7c`

## pseudocode

```c
__int64 __fastcall Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
        unsigned int *a1,
        __int64 a2,
        unsigned int a3)
{
  *a1 = a3;
  RtlReportErrorOrigination(a2);
  return *a1;
}

```

## disassembly

```asm
0x180016da0  push    rbx
0x180016da2  sub     rsp, 20h
0x180016da6  mov     rbx, rcx
0x180016da9  mov     [rcx], r8d
0x180016dac  mov     rcx, rdx
0x180016daf  call    RtlReportErrorOrigination
0x180016db4  mov     eax, [rbx]
0x180016db6  add     rsp, 20h
0x180016dba  pop     rbx
0x180016dbb  retn
```
