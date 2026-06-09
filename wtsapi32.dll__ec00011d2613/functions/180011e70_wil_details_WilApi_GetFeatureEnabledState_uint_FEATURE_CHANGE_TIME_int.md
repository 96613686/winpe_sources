# wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)

- ea: `0x180011e70`
- end: `0x180011e93`
- name: `?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z`
- size: `35`
- prototype: `enum FEATURE_ENABLED_STATE __fastcall(wil::details *__hidden this, unsigned int, enum FEATURE_CHANGE_TIME, int *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18000f8a0`
- `0x18000fae4`
- `0x18000fba4`
- `0x1800129b8`

## callees

- `0x180011e70`
- `0x180016010`

## pseudocode

```c
__int64 (__fastcall *__fastcall wil::details::WilApi_GetFeatureEnabledState(
        wil::details *this,
        __int64 a2,
        __int64 a3,
        int *a4))(wil::details *, __int64, __int64, int *)
{
  __int64 (__fastcall *result)(wil::details *, __int64, __int64, int *); // rax

  result = (__int64 (__fastcall *)(wil::details *, __int64, __int64, int *))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState )
    return (__int64 (__fastcall *)(wil::details *, __int64, __int64, int *))result(this, 3, a3, a4);
  result = (__int64 (__fastcall *)(wil::details *, __int64, __int64, int *))g_wil_details_apiGetFeatureEnabledState;
  if ( g_wil_details_apiGetFeatureEnabledState )
    return (__int64 (__fastcall *)(wil::details *, __int64, __int64, int *))result(this, 3, a3, a4);
  return result;
}

```

## disassembly

```asm
0x180011e70  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180011e77  test    rax, rax
0x180011e7a  jz      short loc_180011E86
0x180011e7c  mov     edx, 3
0x180011e81  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180011e86  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180011e8d  test    rax, rax
0x180011e90  jnz     short loc_180011E7C
0x180011e92  retn
```
