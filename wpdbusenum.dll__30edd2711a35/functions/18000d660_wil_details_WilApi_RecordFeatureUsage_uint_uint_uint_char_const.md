# wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x18000d660`
- end: `0x18000d689`
- name: `?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `41`
- prototype: `void __fastcall(wil::details *this, __int64, __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18000cc00`
- `0x18000cce0`
- `0x18000d690`
- `0x180014ed8`

## callees

- `0x18000d660`
- `0x180016010`

## pseudocode

```c
void __fastcall wil::details::WilApi_RecordFeatureUsage(wil::details *this, __int64 a2, __int64 a3)
{
  void (__fastcall *v3)(wil::details *, __int64, __int64, _QWORD); // rax

  v3 = (void (__fastcall *)(wil::details *, __int64, __int64, _QWORD))g_wil_details_internalRecordFeatureUsage;
  if ( g_wil_details_internalRecordFeatureUsage
    || (v3 = (void (__fastcall *)(wil::details *, __int64, __int64, _QWORD))g_wil_details_apiRecordFeatureUsage) != 0 )
  {
    v3(this, a2, a3, 0);
  }
}

```

## disassembly

```asm
0x18000d660  sub     rsp, 38h
0x18000d664  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18000d66b  test    rax, rax
0x18000d66e  jnz     short loc_18000D67C
0x18000d670  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x18000d677  test    rax, rax
0x18000d67a  jz      short loc_18000D684
0x18000d67c  xor     r9d, r9d
0x18000d67f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d684  add     rsp, 38h
0x18000d688  retn
```
