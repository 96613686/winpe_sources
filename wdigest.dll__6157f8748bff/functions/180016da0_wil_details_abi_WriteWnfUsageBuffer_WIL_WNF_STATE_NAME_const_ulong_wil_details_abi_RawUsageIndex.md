# wil::details_abi::WriteWnfUsageBuffer(__WIL__WNF_STATE_NAME const *,ulong,wil::details_abi::RawUsageIndex &)

- ea: `0x180016da0`
- end: `0x180016e14`
- name: `?WriteWnfUsageBuffer@details_abi@wil@@YA_NPEBU__WIL__WNF_STATE_NAME@@KAEAVRawUsageIndex@12@@Z`
- size: `116`
- prototype: `bool __fastcall(wil::details_abi *__hidden this, const struct __WIL__WNF_STATE_NAME *, unsigned int, struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x18000e9fc`

## callees

- `0x180016da0`
- `0x180018cac`

## pseudocode

```c
char __fastcall wil::details_abi::WriteWnfUsageBuffer(
        wil::details_abi *this,
        const struct __WIL__WNF_STATE_NAME *a2,
        __int64 a3,
        struct wil::details_abi::RawUsageIndex *a4)
{
  int updated; // eax
  __int64 v7; // r9
  int v9; // [rsp+20h] [rbp-28h]
  int v10; // [rsp+20h] [rbp-28h]

  if ( *(_BYTE *)(a3 + 56) )
  {
    updated = wil_details_NtUpdateWnfStateData(
                (__int64)this,
                *(_QWORD *)(a3 + 24),
                *(_DWORD *)(a3 + 32) - (unsigned int)*(_QWORD *)(a3 + 24),
                (__int64)a4,
                v9,
                (int)a2,
                1);
    if ( updated == -1073741823 )
      return 0;
    if ( updated )
      wil_details_NtUpdateWnfStateData(
        (__int64)this,
        *(_QWORD *)(a3 + 24),
        *(_DWORD *)(a3 + 32) - *(_QWORD *)(a3 + 24),
        v7,
        v10,
        0,
        0);
  }
  return 1;
}

```

## disassembly

```asm
0x180016da0  mov     [rsp+arg_0], rbx
0x180016da5  push    rdi
0x180016da6  sub     rsp, 40h
0x180016daa  cmp     byte ptr [r8+38h], 0
0x180016daf  mov     rbx, r8
0x180016db2  mov     eax, edx
0x180016db4  mov     rdi, rcx
0x180016db7  jz      short loc_180016E07
0x180016db9  mov     rdx, [r8+18h]
0x180016dbd  mov     r8d, [r8+20h]
0x180016dc1  sub     r8d, edx
0x180016dc4  mov     [rsp+48h+var_18], 1
0x180016dcc  mov     [rsp+48h+var_20], eax
0x180016dd0  call    wil_details_NtUpdateWnfStateData
0x180016dd5  cmp     eax, 0C0000001h
0x180016dda  jnz     short loc_180016DE0
0x180016ddc  xor     al, al
0x180016dde  jmp     short loc_180016E09
0x180016de0  test    eax, eax
0x180016de2  jz      short loc_180016E07
0x180016de4  mov     rdx, [rbx+18h]
0x180016de8  mov     rcx, rdi
0x180016deb  mov     r8d, [rbx+20h]
0x180016def  sub     r8d, edx
0x180016df2  mov     [rsp+48h+var_18], 0
0x180016dfa  mov     [rsp+48h+var_20], 0
0x180016e02  call    wil_details_NtUpdateWnfStateData
0x180016e07  mov     al, 1
0x180016e09  mov     rbx, [rsp+48h+arg_0]
0x180016e0e  add     rsp, 40h
0x180016e12  pop     rdi
0x180016e13  retn
```
