# std::_Init_locks::~_Init_locks(void)

- ea: `0x18002ed88`
- end: `0x18002edc4`
- name: `??1_Init_locks@std@@QEAA@XZ`
- size: `60`
- prototype: `void __fastcall(std::_Init_locks *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800398a0`
- `0x1800398c0`

## callees

- `0x18002ed88`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002eda8`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002eda8`

## pseudocode

```c
void __fastcall std::_Init_locks::~_Init_locks(std::_Init_locks *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rbx

  if ( _InterlockedDecrement(&dword_18004B490) < 0 )
  {
    v1 = &stru_18004EFE0;
    do
      DeleteCriticalSection(v1++);
    while ( v1 != (struct _RTL_CRITICAL_SECTION *)`wil::Feature<__WilFeatureTraits_Feature_MaintenanceWindow_RepeatIntervals>::GetImpl'::`2'::impl );
  }
}

```

## disassembly

```asm
0x18002ed88  push    rbx
0x18002ed8a  sub     rsp, 20h
0x18002ed8e  or      eax, 0FFFFFFFFh
0x18002ed91  lock xadd cs:dword_18004B490, eax
0x18002ed99  cmp     eax, 1
0x18002ed9c  jns     short loc_18002EDBE
0x18002ed9e  lea     rbx, stru_18004EFE0
0x18002eda5  mov     rcx, rbx; lpCriticalSection
0x18002eda8  call    cs:__imp_DeleteCriticalSection
0x18002edae  lea     rax, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_MaintenanceWindow_RepeatIntervals@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_MaintenanceWindow_RepeatIntervals@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MaintenanceWindow_RepeatIntervals> `wil::Feature<__WilFeatureTraits_Feature_MaintenanceWindow_RepeatIntervals>::GetImpl(void)'::`2'::impl
0x18002edb5  add     rbx, 28h ; '('
0x18002edb9  cmp     rbx, rax
0x18002edbc  jnz     short loc_18002EDA5
0x18002edbe  add     rsp, 20h
0x18002edc2  pop     rbx
0x18002edc3  retn
```
