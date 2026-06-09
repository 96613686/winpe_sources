# wil::details_abi::WriteWnfUsageBuffer(__WIL__WNF_STATE_NAME const *,ulong,wil::details_abi::RawUsageIndex &)

- ea: `0x18001969c`
- end: `0x180019710`
- name: `?WriteWnfUsageBuffer@details_abi@wil@@YA_NPEBU__WIL__WNF_STATE_NAME@@KAEAVRawUsageIndex@12@@Z`
- size: `116`
- prototype: `bool __fastcall(wil::details_abi *__hidden this, const struct __WIL__WNF_STATE_NAME *, unsigned int, struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180006a84`

## callees

- `0x18001969c`
- `0x18001a37c`

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
0x18001969c  mov     [rsp+arg_0], rbx
0x1800196a1  push    rdi
0x1800196a2  sub     rsp, 40h
0x1800196a6  cmp     byte ptr [r8+38h], 0
0x1800196ab  mov     rbx, r8
0x1800196ae  mov     eax, edx
0x1800196b0  mov     rdi, rcx
0x1800196b3  jz      short loc_180019703
0x1800196b5  mov     rdx, [r8+18h]
0x1800196b9  mov     r8d, [r8+20h]
0x1800196bd  sub     r8d, edx
0x1800196c0  mov     [rsp+48h+var_18], 1
0x1800196c8  mov     [rsp+48h+var_20], eax
0x1800196cc  call    wil_details_NtUpdateWnfStateData
0x1800196d1  cmp     eax, 0C0000001h
0x1800196d6  jnz     short loc_1800196DC
0x1800196d8  xor     al, al
0x1800196da  jmp     short loc_180019705
0x1800196dc  test    eax, eax
0x1800196de  jz      short loc_180019703
0x1800196e0  mov     rdx, [rbx+18h]
0x1800196e4  mov     rcx, rdi
0x1800196e7  mov     r8d, [rbx+20h]
0x1800196eb  sub     r8d, edx
0x1800196ee  mov     [rsp+48h+var_18], 0
0x1800196f6  mov     [rsp+48h+var_20], 0
0x1800196fe  call    wil_details_NtUpdateWnfStateData
0x180019703  mov     al, 1
0x180019705  mov     rbx, [rsp+48h+arg_0]
0x18001970a  add     rsp, 40h
0x18001970e  pop     rdi
0x18001970f  retn
```
