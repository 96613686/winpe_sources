# wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)

- ea: `0x1800162fc`
- end: `0x18001631f`
- name: `?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z`
- size: `35`
- prototype: `enum FEATURE_ENABLED_STATE __fastcall(wil::details *__hidden this, unsigned int, enum FEATURE_CHANGE_TIME, int *)`
- caller_count: `13`
- callee_count: `2`
- tags: ``

## callers

- `0x18001441c`
- `0x18001b81c`
- `0x18001b8e4`
- `0x18001b9cc`
- `0x18001ba94`
- `0x18001bb08`
- `0x18001bb7c`
- `0x18001bbf0`
- `0x18001bc64`
- `0x18001bd48`
- `0x18001be2c`
- `0x18001bf10`
- `0x18001bfe4`

## callees

- `0x1800162fc`
- `0x180021010`

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
0x1800162fc  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180016303  test    rax, rax
0x180016306  jz      short loc_180016312
0x180016308  mov     edx, 3
0x18001630d  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180016312  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180016319  test    rax, rax
0x18001631c  jnz     short loc_180016308
0x18001631e  retn
```
