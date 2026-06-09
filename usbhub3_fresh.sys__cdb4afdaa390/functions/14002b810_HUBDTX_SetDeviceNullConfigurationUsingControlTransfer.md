# HUBDTX_SetDeviceNullConfigurationUsingControlTransfer

- ea: `0x14002b810`
- end: `0x14002b8d1`
- name: `HUBDTX_SetDeviceNullConfigurationUsingControlTransfer`
- size: `193`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400210c0`

## callees

- `0x1400024b8`
- `0x14000a53c`
- `0x14002b810`
- `0x14002e270`

## pseudocode

```c
__int64 __fastcall HUBDTX_SetDeviceNullConfigurationUsingControlTransfer(__int64 a1)
{
  __int64 result; // rax
  int v3; // edx
  __int64 v4; // [rsp+28h] [rbp-30h]

  *(_BYTE *)(a1 + 408) &= 0x1Cu;
  *(_BYTE *)(a1 + 409) = 9;
  *(_DWORD *)(a1 + 410) = 0;
  *(_WORD *)(a1 + 414) = 0;
  result = HUBMISC_ControlTransfer(
             *(_QWORD *)a1,
             *(_QWORD *)(a1 + 24),
             a1,
             (_QWORD *)(a1 + 256),
             (__int64)HUBDTX_ControlTransferComplete,
             0,
             0,
             0,
             *(_BYTE *)(a1 + 1520));
  if ( (int)result < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LODWORD(v4) = result;
      LOBYTE(v3) = 2;
      WPP_RECORDER_SF_d(
        *(_QWORD *)(*(_QWORD *)(a1 + 8) + 1432LL),
        v3,
        5,
        69,
        (__int64)WPP_736cb17edbb73fe74dd9f642bb1bec68_Traceguids,
        v4);
    }
    return HUBSM_AddEvent(a1 + 512, 4004);
  }
  return result;
}

```

## disassembly

```asm
0x14002b810  push    rbx
0x14002b812  sub     rsp, 50h
0x14002b816  and     byte ptr [rcx+198h], 1Ch
0x14002b81d  lea     r9, [rcx+100h]
0x14002b824  xor     eax, eax
0x14002b826  mov     byte ptr [rcx+199h], 9
0x14002b82d  mov     [rcx+19Ah], eax
0x14002b833  mov     rbx, rcx
0x14002b836  mov     [rcx+19Eh], ax
0x14002b83d  mov     r8, rcx
0x14002b840  mov     al, [rcx+5F0h]
0x14002b846  mov     rdx, [rcx+18h]
0x14002b84a  mov     rcx, [rcx]
0x14002b84d  mov     [rsp+58h+var_18], al
0x14002b851  lea     rax, HUBDTX_ControlTransferComplete
0x14002b858  mov     [rsp+58h+var_20], 0
0x14002b85d  mov     [rsp+58h+var_28], 0
0x14002b866  mov     [rsp+58h+var_30], 0
0x14002b86f  mov     [rsp+58h+var_38], rax
0x14002b874  call    HUBMISC_ControlTransfer
0x14002b879  test    eax, eax
0x14002b87b  jns     short loc_14002B8CA
0x14002b87d  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14002b884  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14002b88b  jz      short loc_14002B8B9
0x14002b88d  mov     rcx, [rbx+8]
0x14002b891  mov     r9d, 45h ; 'E'
0x14002b897  mov     dword ptr [rsp+58h+var_30], eax
0x14002b89b  mov     dl, 2
0x14002b89d  lea     rax, WPP_736cb17edbb73fe74dd9f642bb1bec68_Traceguids
0x14002b8a4  mov     [rsp+58h+var_38], rax
0x14002b8a9  mov     rcx, [rcx+598h]
0x14002b8b0  lea     r8d, [r9-40h]
0x14002b8b4  call    WPP_RECORDER_SF_d
0x14002b8b9  lea     rcx, [rbx+200h]
0x14002b8c0  mov     edx, 0FA4h
0x14002b8c5  call    HUBSM_AddEvent
0x14002b8ca  add     rsp, 50h
0x14002b8ce  pop     rbx
0x14002b8cf  retn
```
