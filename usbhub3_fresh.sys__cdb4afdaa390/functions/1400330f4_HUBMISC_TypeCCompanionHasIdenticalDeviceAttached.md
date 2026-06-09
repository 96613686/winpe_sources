# HUBMISC_TypeCCompanionHasIdenticalDeviceAttached

- ea: `0x1400330f4`
- end: `0x14003322b`
- name: `HUBMISC_TypeCCompanionHasIdenticalDeviceAttached`
- size: `311`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14001f3e0`

## callees

- `0x1400330f4`
- `0x140045570`
- `0x140083b00`

## pseudocode

```c
bool __fastcall HUBMISC_TypeCCompanionHasIdenticalDeviceAttached(__int64 a1)
{
  __int64 v1; // rdi
  bool v3; // si
  __int64 v4; // rax
  __int64 CompanionPort; // rax
  _WORD *v6; // rcx
  __int64 v7; // rax

  v1 = *(_QWORD *)(a1 + 8);
  if ( !v1 || (*(_DWORD *)(v1 + 204) & 0x200) == 0 || *(_DWORD *)(v1 + 208) == 512 )
    return 0;
  v3 = 0;
  v4 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, WDFDRIVER__ *, __int64 *))(WdfFunctions_01015 + 1616))(
         WdfDriverGlobals,
         WdfDriverGlobals->Driver,
         off_14006B2C0);
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, _QWORD))(WdfFunctions_01015 + 2504))(
    WdfDriverGlobals,
    *(_QWORD *)(v4 + 56),
    0);
  CompanionPort = HUBCONNECTOR_GetCompanionPort(v1, 1);
  if ( CompanionPort )
  {
    if ( (*(_DWORD *)(CompanionPort + 1336) & 0x40) != 0 )
    {
      v6 = *(_WORD **)(CompanionPort + 1328);
      if ( v6 )
      {
        if ( v6[1002] == *(_WORD *)(a1 + 2004) && v6[1003] == *(_WORD *)(a1 + 2006) )
          v3 = v6[1004] == *(_WORD *)(a1 + 2008);
      }
    }
  }
  v7 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, WDFDRIVER__ *, __int64 *))(WdfFunctions_01015 + 1616))(
         WdfDriverGlobals,
         WdfDriverGlobals->Driver,
         off_14006B2C0);
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01015 + 2512))(
    WdfDriverGlobals,
    *(_QWORD *)(v7 + 56));
  return v3;
}

```

## disassembly

```asm
0x1400330f4  push    rbx
0x1400330f6  push    rbp
0x1400330f7  push    rsi
0x1400330f8  push    rdi
0x1400330f9  sub     rsp, 28h
0x1400330fd  mov     rdi, [rcx+8]
0x140033101  mov     rbx, rcx
0x140033104  test    rdi, rdi
0x140033107  jz      loc_14003321F
0x14003310d  mov     ecx, 200h
0x140033112  test    [rdi+0CCh], ecx
0x140033118  jz      loc_14003321F
0x14003311e  cmp     [rdi+0D0h], ecx
0x140033124  jz      loc_14003321F
0x14003312a  mov     rax, cs:WdfFunctions_01015
0x140033131  xor     sil, sil
0x140033134  mov     rcx, cs:WdfDriverGlobals
0x14003313b  mov     r8, cs:off_14006B2C0
0x140033142  mov     rax, [rax+650h]
0x140033149  mov     rdx, [rcx]
0x14003314c  call    _guard_dispatch_icall
0x140033151  mov     rdx, cs:WdfFunctions_01015
0x140033158  xor     r8d, r8d
0x14003315b  mov     rcx, cs:WdfDriverGlobals
0x140033162  mov     r9, [rdx+9C8h]
0x140033169  mov     rdx, [rax+38h]
0x14003316d  mov     rax, r9
0x140033170  call    _guard_dispatch_icall
0x140033175  mov     ebp, 1
0x14003317a  mov     rcx, rdi
0x14003317d  mov     edx, ebp
0x14003317f  call    HUBCONNECTOR_GetCompanionPort
0x140033184  test    rax, rax
0x140033187  jz      short loc_1400331D5
0x140033189  mov     ecx, [rax+538h]
0x14003318f  test    cl, 40h
0x140033192  jz      short loc_1400331D5
0x140033194  mov     rcx, [rax+530h]
0x14003319b  test    rcx, rcx
0x14003319e  jz      short loc_1400331D5
0x1400331a0  movzx   eax, word ptr [rbx+7D4h]
0x1400331a7  cmp     [rcx+7D4h], ax
0x1400331ae  jnz     short loc_1400331D5
0x1400331b0  movzx   eax, word ptr [rbx+7D6h]
0x1400331b7  cmp     [rcx+7D6h], ax
0x1400331be  jnz     short loc_1400331D5
0x1400331c0  movzx   eax, word ptr [rbx+7D8h]
0x1400331c7  cmp     [rcx+7D8h], ax
0x1400331ce  movzx   esi, sil
0x1400331d2  cmovz   esi, ebp
0x1400331d5  mov     rax, cs:WdfFunctions_01015
0x1400331dc  mov     rcx, cs:WdfDriverGlobals
0x1400331e3  mov     r8, cs:off_14006B2C0
0x1400331ea  mov     rax, [rax+650h]
0x1400331f1  mov     rdx, [rcx]
0x1400331f4  call    _guard_dispatch_icall
0x1400331f9  mov     rcx, cs:WdfFunctions_01015
0x140033200  mov     rdx, [rax+38h]
0x140033204  mov     r8, [rcx+9D0h]
0x14003320b  mov     rcx, cs:WdfDriverGlobals
0x140033212  mov     rax, r8
0x140033215  call    _guard_dispatch_icall
0x14003321a  mov     al, sil
0x14003321d  jmp     short loc_140033221
0x14003321f  xor     al, al
0x140033221  add     rsp, 28h
0x140033225  pop     rdi
0x140033226  pop     rsi
0x140033227  pop     rbp
0x140033228  pop     rbx
0x140033229  retn
```
