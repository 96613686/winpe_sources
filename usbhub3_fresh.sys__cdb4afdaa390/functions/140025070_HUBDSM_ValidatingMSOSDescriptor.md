# HUBDSM_ValidatingMSOSDescriptor

- ea: `0x140025070`
- end: `0x14002515a`
- name: `HUBDSM_ValidatingMSOSDescriptor`
- size: `234`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1400024b8`
- `0x1400083b4`
- `0x140025070`
- `0x140045570`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x140025102`
- `ntoskrnl!RtlCompareMemory` at `0x140025102`

## pseudocode

```c
__int64 __fastcall HUBDSM_ValidatingMSOSDescriptor(__int64 a1)
{
  __int64 v1; // rbx
  _UNKNOWN **v2; // rcx
  unsigned int v3; // edi
  int v5; // [rsp+28h] [rbp-10h]

  v1 = *(_QWORD *)(a1 + 960);
  if ( *(_DWORD *)(v1 + 264) == 18 )
  {
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, WDFDRIVER__ *, __int64 *))(WdfFunctions_01015 + 1616))(
      WdfDriverGlobals,
      WdfDriverGlobals->Driver,
      off_14006B2C0);
    if ( RtlCompareMemory((const void *)(v1 + 2090), L"MSFT100", 0xEu) == 14 )
    {
      v3 = 4077;
      *(_BYTE *)(v1 + 2060) = *(_BYTE *)(v1 + 2104);
      return v3;
    }
  }
  else
  {
    v2 = &WPP_RECORDER_INITIALIZED;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v5 = *(_DWORD *)(v1 + 264);
      WPP_RECORDER_SF_d(
        *(_QWORD *)(*(_QWORD *)(v1 + 8) + 1432LL),
        2,
        5,
        91,
        (__int64)WPP_736cb17edbb73fe74dd9f642bb1bec68_Traceguids,
        v5);
    }
  }
  v3 = 4065;
  if ( (byte_14006ED41 & 1) != 0 )
    McTemplateK0p_EtwWriteTransfer(v2, USBHUB3_ETW_EVENT_INVALID_MSOS_DESCRIPTOR, v1 + 1524, *(_QWORD *)(v1 + 24));
  return v3;
}

```

## disassembly

```asm
0x140025070  mov     [rsp+arg_0], rbx
0x140025075  push    rdi
0x140025076  sub     rsp, 30h
0x14002507a  mov     rbx, [rcx+3C0h]
0x140025081  mov     eax, [rbx+108h]
0x140025087  cmp     eax, 12h
0x14002508a  jz      short loc_1400250CA
0x14002508c  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140025093  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14002509a  jz      short loc_140025114
0x14002509c  mov     rcx, [rbx+8]
0x1400250a0  mov     r9d, 5Bh ; '['
0x1400250a6  mov     [rsp+38h+var_10], eax
0x1400250aa  mov     dl, 2
0x1400250ac  lea     rax, WPP_736cb17edbb73fe74dd9f642bb1bec68_Traceguids
0x1400250b3  mov     [rsp+38h+var_18], rax
0x1400250b8  mov     rcx, [rcx+598h]
0x1400250bf  lea     r8d, [r9-56h]
0x1400250c3  call    WPP_RECORDER_SF_d
0x1400250c8  jmp     short loc_140025114
0x1400250ca  mov     rax, cs:WdfFunctions_01015
0x1400250d1  mov     rcx, cs:WdfDriverGlobals
0x1400250d8  mov     r8, cs:off_14006B2C0
0x1400250df  mov     rax, [rax+650h]
0x1400250e6  mov     rdx, [rcx]
0x1400250e9  call    _guard_dispatch_icall
0x1400250ee  lea     rcx, [rbx+82Ah]; Source1
0x1400250f5  mov     r8d, 0Eh; Length
0x1400250fb  lea     rdx, aMsft100; "MSFT100"
0x140025102  call    cs:__imp_RtlCompareMemory
0x140025109  nop     dword ptr [rax+rax+00h]
0x14002510e  cmp     rax, 0Eh
0x140025112  jz      short loc_14002513B
0x140025114  test    cs:byte_14006ED41, 1
0x14002511b  mov     edi, 0FE1h
0x140025120  jz      short loc_14002514C
0x140025122  mov     r9, [rbx+18h]
0x140025126  lea     r8, [rbx+5F4h]
0x14002512d  lea     rdx, USBHUB3_ETW_EVENT_INVALID_MSOS_DESCRIPTOR
0x140025134  call    McTemplateK0p_EtwWriteTransfer
0x140025139  jmp     short loc_14002514C
0x14002513b  mov     al, [rbx+838h]
0x140025141  mov     edi, 0FEDh
0x140025146  mov     [rbx+80Ch], al
0x14002514c  mov     rbx, [rsp+38h+arg_0]
0x140025151  mov     eax, edi
0x140025153  add     rsp, 30h
0x140025157  pop     rdi
0x140025158  retn
```
