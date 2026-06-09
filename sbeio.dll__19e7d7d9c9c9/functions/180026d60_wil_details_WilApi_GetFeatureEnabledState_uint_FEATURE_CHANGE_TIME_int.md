# wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)

- ea: `0x180026d60`
- end: `0x180026d83`
- name: `?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z`
- size: `35`
- prototype: `enum FEATURE_ENABLED_STATE __fastcall(wil::details *__hidden this, unsigned int, enum FEATURE_CHANGE_TIME, int *)`
- caller_count: `10`
- callee_count: `2`
- tags: ``

## callers

- `0x18001bb4c`
- `0x18001bc14`
- `0x18001bc88`
- `0x18001bcfc`
- `0x18001bd70`
- `0x18001bde4`
- `0x18001bec8`
- `0x18001bfac`
- `0x18001c090`
- `0x18001c164`

## callees

- `0x180026d60`
- `0x18002b010`

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
0x180026d60  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180026d67  test    rax, rax
0x180026d6a  jz      short loc_180026D76
0x180026d6c  mov     edx, 3
0x180026d71  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180026d76  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180026d7d  test    rax, rax
0x180026d80  jnz     short loc_180026D6C
0x180026d82  retn
```
