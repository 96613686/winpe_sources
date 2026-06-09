# HUBCONNECTOR_DeRegisterPort

- ea: `0x1400838ec`
- end: `0x140083af9`
- name: `HUBCONNECTOR_DeRegisterPort`
- size: `525`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140084798`

## callees

- `0x1400024b8`
- `0x1400067ac`
- `0x140045570`
- `0x1400838ec`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140083ad9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140083ad9`
- `ntoskrnl!RtlCompareMemory` at `0x14008398d`
- `ntoskrnl!RtlCompareMemory` at `0x14008398d`

## pseudocode

```c
__int64 __fastcall HUBCONNECTOR_DeRegisterPort(__int64 a1)
{
  unsigned int v2; // r14d
  __int64 v3; // rax
  int v4; // edx
  _QWORD *v5; // rsi
  _QWORD *i; // rax
  _QWORD *v7; // rbx
  __int64 v8; // rax
  int v10; // ecx
  __int64 v11; // rcx
  _QWORD *v12; // rdx

  v2 = 0;
  v3 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, WDFDRIVER__ *, __int64 *))(WdfFunctions_01015 + 1616))(
         WdfDriverGlobals,
         WdfDriverGlobals->Driver,
         off_14006B2C0);
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, _QWORD))(WdfFunctions_01015 + 2504))(
    WdfDriverGlobals,
    *(_QWORD *)(v3 + 56),
    0);
  if ( (*(_DWORD *)(a1 + 204) & 0x20) == 0 )
    goto LABEL_9;
  v5 = (_QWORD *)((*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, WDFDRIVER__ *, __int64 *))(WdfFunctions_01015 + 1616))(
                    WdfDriverGlobals,
                    WdfDriverGlobals->Driver,
                    off_14006B2C0)
                + 40);
  for ( i = (_QWORD *)*v5; ; i = (_QWORD *)v7[10] )
  {
    v7 = i - 10;
    if ( v5 == i )
      goto LABEL_6;
    if ( RtlCompareMemory(i - 10, (const void *)(a1 + 1368), 0x38u) == 56 )
      break;
  }
  if ( !v7 )
  {
LABEL_6:
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v4) = 2;
      WPP_RECORDER_SF_(*(_QWORD *)(a1 + 1432), v4, 4, 19, (__int64)WPP_e747a75ab0a43332580ac19f3a627527_Traceguids);
    }
    v2 = -1073741823;
    goto LABEL_9;
  }
  v10 = *(_DWORD *)(a1 + 208);
  if ( v10 == 512 )
  {
    v7[7] = 0;
  }
  else
  {
    if ( v10 != 768 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v4) = 2;
        WPP_RECORDER_SF_d(
          *(_QWORD *)(a1 + 1432),
          v4,
          6,
          20,
          (__int64)WPP_e747a75ab0a43332580ac19f3a627527_Traceguids,
          *(_DWORD *)(a1 + 208));
      }
      goto LABEL_9;
    }
    v7[8] = 0;
  }
  if ( !v7[7] && !v7[8] )
  {
    v11 = v7[10];
    if ( *(_QWORD **)(v11 + 8) != v7 + 10 || (v12 = (_QWORD *)v7[11], (_QWORD *)*v12 != v7 + 10) )
      __fastfail(3u);
    *v12 = v11;
    *(_QWORD *)(v11 + 8) = v12;
    ExFreePoolWithTag(v7, 0x70334855u);
  }
  _InterlockedAnd((volatile signed __int32 *)(a1 + 204), 0xFFFFFFDF);
LABEL_9:
  v8 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, WDFDRIVER__ *, __int64 *))(WdfFunctions_01015 + 1616))(
         WdfDriverGlobals,
         WdfDriverGlobals->Driver,
         off_14006B2C0);
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01015 + 2512))(
    WdfDriverGlobals,
    *(_QWORD *)(v8 + 56));
  return v2;
}

```

## disassembly

```asm
0x1400838ec  push    rbx
0x1400838ee  push    rbp
0x1400838ef  push    rsi
0x1400838f0  push    rdi
0x1400838f1  push    r14
0x1400838f3  sub     rsp, 30h
0x1400838f7  mov     rax, cs:WdfFunctions_01015
0x1400838fe  mov     rdi, rcx
0x140083901  mov     rcx, cs:WdfDriverGlobals
0x140083908  xor     r14d, r14d
0x14008390b  mov     r8, cs:off_14006B2C0
0x140083912  mov     rax, [rax+650h]
0x140083919  mov     rdx, [rcx]
0x14008391c  call    _guard_dispatch_icall
0x140083921  mov     rcx, cs:WdfDriverGlobals
0x140083928  xor     r8d, r8d
0x14008392b  mov     rdx, [rax+38h]
0x14008392f  mov     rax, cs:WdfFunctions_01015
0x140083936  mov     rax, [rax+9C8h]
0x14008393d  call    _guard_dispatch_icall
0x140083942  mov     eax, [rdi+0CCh]
0x140083948  test    al, 20h
0x14008394a  jz      loc_1400839EA
0x140083950  mov     rax, cs:WdfFunctions_01015
0x140083957  mov     rcx, cs:WdfDriverGlobals
0x14008395e  mov     r8, cs:off_14006B2C0
0x140083965  mov     rax, [rax+650h]
0x14008396c  mov     rdx, [rcx]
0x14008396f  call    _guard_dispatch_icall
0x140083974  lea     rsi, [rax+28h]
0x140083978  mov     rax, [rsi]
0x14008397b  jmp     short loc_1400839A7
0x14008397d  mov     r8d, 38h ; '8'; Length
0x140083983  lea     rdx, [rdi+558h]; Source2
0x14008398a  mov     rcx, rbx; Source1
0x14008398d  call    cs:__imp_RtlCompareMemory
0x140083994  nop     dword ptr [rax+rax+00h]
0x140083999  cmp     rax, 38h ; '8'
0x14008399d  jz      loc_140083A3E
0x1400839a3  mov     rax, [rbx+50h]
0x1400839a7  lea     rbx, [rax-50h]
0x1400839ab  cmp     rsi, rax
0x1400839ae  jnz     short loc_14008397D
0x1400839b0  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400839b7  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400839be  jz      short loc_1400839E4
0x1400839c0  mov     rcx, [rdi+598h]
0x1400839c7  lea     rax, WPP_e747a75ab0a43332580ac19f3a627527_Traceguids
0x1400839ce  mov     r9d, 13h
0x1400839d4  mov     [rsp+58h+var_38], rax
0x1400839d9  mov     dl, 2
0x1400839db  lea     r8d, [r9-0Fh]
0x1400839df  call    WPP_RECORDER_SF_
0x1400839e4  mov     r14d, 0C0000001h
0x1400839ea  mov     rax, cs:WdfFunctions_01015
0x1400839f1  mov     rcx, cs:WdfDriverGlobals
0x1400839f8  mov     r8, cs:off_14006B2C0
0x1400839ff  mov     rax, [rax+650h]
0x140083a06  mov     rdx, [rcx]
0x140083a09  call    _guard_dispatch_icall
0x140083a0e  mov     rcx, cs:WdfFunctions_01015
0x140083a15  mov     rdx, [rax+38h]
0x140083a19  mov     r8, [rcx+9D0h]
0x140083a20  mov     rcx, cs:WdfDriverGlobals
0x140083a27  mov     rax, r8
0x140083a2a  call    _guard_dispatch_icall
0x140083a2f  mov     eax, r14d
0x140083a32  add     rsp, 30h
0x140083a36  pop     r14
0x140083a38  pop     rdi
0x140083a39  pop     rsi
0x140083a3a  pop     rbp
0x140083a3b  pop     rbx
0x140083a3c  retn
0x140083a3e  test    rbx, rbx
0x140083a41  jz      loc_1400839B0
0x140083a47  mov     ecx, [rdi+0D0h]
0x140083a4d  cmp     ecx, 200h
0x140083a53  jz      short loc_140083AA4
0x140083a55  cmp     ecx, 300h
0x140083a5b  jz      short loc_140083A9E
0x140083a5d  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140083a64  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140083a6b  jz      loc_1400839EA
0x140083a71  mov     [rsp+58h+var_30], ecx
0x140083a75  lea     rax, WPP_e747a75ab0a43332580ac19f3a627527_Traceguids
0x140083a7c  mov     rcx, [rdi+598h]
0x140083a83  mov     r9d, 14h
0x140083a89  mov     dl, 2
0x140083a8b  mov     [rsp+58h+var_38], rax
0x140083a90  lea     r8d, [r9-0Eh]
0x140083a94  call    WPP_RECORDER_SF_d
0x140083a99  jmp     loc_1400839EA
0x140083a9e  mov     [rbx+40h], r14
0x140083aa2  jmp     short loc_140083AA8
0x140083aa4  mov     [rbx+38h], r14
0x140083aa8  cmp     [rbx+38h], r14
0x140083aac  jnz     short loc_140083AE5
0x140083aae  cmp     [rbx+40h], r14
0x140083ab2  jnz     short loc_140083AE5
0x140083ab4  lea     rax, [rbx+50h]
0x140083ab8  mov     rcx, [rax]
0x140083abb  cmp     [rcx+8], rax
0x140083abf  jnz     short loc_140083AF2
0x140083ac1  mov     rdx, [rax+8]
0x140083ac5  cmp     [rdx], rax
0x140083ac8  jnz     short loc_140083AF2
0x140083aca  mov     [rdx], rcx
0x140083acd  mov     [rcx+8], rdx
0x140083ad1  mov     edx, 70334855h; Tag
0x140083ad6  mov     rcx, rbx; P
0x140083ad9  call    cs:__imp_ExFreePoolWithTag
0x140083ae0  nop     dword ptr [rax+rax+00h]
0x140083ae5  lock and dword ptr [rdi+0CCh], 0FFFFFFDFh
0x140083aed  jmp     loc_1400839EA
0x140083af2  mov     ecx, 3
0x140083af7  int     29h; Win8: RtlFailFast(ecx)
```
