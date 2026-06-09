# FWUPDATE_SetMMIO

- ea: `0x140041780`
- end: `0x140041849`
- name: `FWUPDATE_SetMMIO`
- size: `201`
- prototype: `__int64 __fastcall(__int64, __int16, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14000a450`
- `0x14000a4c0`

## callees

- `0x1400024b8`
- `0x14002e270`
- `0x140041780`

## pseudocode

```c
__int64 __fastcall FWUPDATE_SetMMIO(__int64 a1, __int16 a2, __int64 a3)
{
  char v3; // al
  int v5; // edx
  int v6; // edi
  __int64 v8; // [rsp+28h] [rbp-30h]

  v3 = *(_BYTE *)(a1 + 968);
  *(_BYTE *)(a1 + 969) = 65;
  *(_WORD *)(a1 + 970) = 1024;
  *(_BYTE *)(a1 + 968) = v3 & 0x1C | 0x40;
  *(_WORD *)(a1 + 972) = a2;
  *(_WORD *)(a1 + 974) = 4;
  v6 = HUBMISC_ControlTransfer(
         a1,
         *(_QWORD *)(a1 + 248),
         a1,
         (_QWORD *)(a1 + 816),
         (__int64)FWUPDATE_HubVendorControlTransferComplete,
         a3,
         4,
         0,
         *(_BYTE *)(a1 + 2288));
  if ( v6 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LODWORD(v8) = v6;
    LOBYTE(v5) = 2;
    WPP_RECORDER_SF_d(*(_QWORD *)(a1 + 2536), v5, 3, 49, (__int64)WPP_2fd11ae104fa34a9334eddada324a17a_Traceguids, v8);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140041780  mov     r11, rsp
0x140041783  mov     [r11+8], rbx
0x140041787  push    rdi
0x140041788  sub     rsp, 50h
0x14004178c  mov     al, [rcx+3C8h]
0x140041792  mov     rbx, rcx
0x140041795  mov     byte ptr [rcx+3C9h], 41h ; 'A'
0x14004179c  and     al, 1Ch
0x14004179e  mov     word ptr [rcx+3CAh], 400h
0x1400417a7  or      al, 40h
0x1400417a9  mov     [rcx+3C8h], al
0x1400417af  mov     [rcx+3CCh], dx
0x1400417b6  lea     r9, [rbx+330h]
0x1400417bd  mov     ecx, 4
0x1400417c2  mov     [rbx+3CEh], cx
0x1400417c9  mov     al, [rbx+8F0h]
0x1400417cf  mov     rdx, [rbx+0F8h]
0x1400417d6  mov     [rsp+58h+var_18], al
0x1400417da  lea     rax, FWUPDATE_HubVendorControlTransferComplete
0x1400417e1  mov     [rsp+58h+var_20], 0
0x1400417e6  mov     [r11-28h], rcx
0x1400417ea  mov     rcx, rbx
0x1400417ed  mov     [r11-30h], r8
0x1400417f1  mov     r8, rbx
0x1400417f4  mov     [r11-38h], rax
0x1400417f8  call    HUBMISC_ControlTransfer
0x1400417fd  mov     edi, eax
0x1400417ff  test    eax, eax
0x140041801  jns     short loc_14004183B
0x140041803  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14004180a  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140041811  jz      short loc_14004183B
0x140041813  mov     rcx, [rbx+9E8h]
0x14004181a  lea     rax, WPP_2fd11ae104fa34a9334eddada324a17a_Traceguids
0x140041821  mov     r9d, 31h ; '1'
0x140041827  mov     [rsp+58h+var_30], edi
0x14004182b  mov     dl, 2
0x14004182d  mov     [rsp+58h+var_38], rax
0x140041832  lea     r8d, [r9-2Eh]
0x140041836  call    WPP_RECORDER_SF_d
0x14004183b  mov     rbx, [rsp+58h+arg_0]
0x140041840  mov     eax, edi
0x140041842  add     rsp, 50h
0x140041846  pop     rdi
0x140041847  retn
```
