# FWUPDATE_GetMMIO

- ea: `0x140041328`
- end: `0x1400413f1`
- name: `FWUPDATE_GetMMIO`
- size: `201`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140008f00`
- `0x1400097c0`

## callees

- `0x1400024b8`
- `0x14002e270`
- `0x140041328`

## pseudocode

```c
__int64 __fastcall FWUPDATE_GetMMIO(__int64 a1, __int16 a2, __int64 a3)
{
  char v3; // al
  int v5; // edx
  int v6; // edi
  __int64 v8; // [rsp+28h] [rbp-30h]

  v3 = *(_BYTE *)(a1 + 968);
  *(_BYTE *)(a1 + 969) = 64;
  *(_WORD *)(a1 + 970) = 1024;
  *(_BYTE *)(a1 + 968) = v3 & 0x1C | 0xC0;
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
    WPP_RECORDER_SF_d(*(_QWORD *)(a1 + 2536), v5, 3, 50, (__int64)WPP_2fd11ae104fa34a9334eddada324a17a_Traceguids, v8);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140041328  mov     r11, rsp
0x14004132b  mov     [r11+8], rbx
0x14004132f  push    rdi
0x140041330  sub     rsp, 50h
0x140041334  mov     al, [rcx+3C8h]
0x14004133a  mov     rbx, rcx
0x14004133d  mov     byte ptr [rcx+3C9h], 40h ; '@'
0x140041344  and     al, 1Ch
0x140041346  mov     word ptr [rcx+3CAh], 400h
0x14004134f  or      al, 0C0h
0x140041351  mov     [rcx+3C8h], al
0x140041357  mov     [rcx+3CCh], dx
0x14004135e  lea     r9, [rbx+330h]
0x140041365  mov     ecx, 4
0x14004136a  mov     [rbx+3CEh], cx
0x140041371  mov     al, [rbx+8F0h]
0x140041377  mov     rdx, [rbx+0F8h]
0x14004137e  mov     [rsp+58h+var_18], al
0x140041382  lea     rax, FWUPDATE_HubVendorControlTransferComplete
0x140041389  mov     [rsp+58h+var_20], 0
0x14004138e  mov     [r11-28h], rcx
0x140041392  mov     rcx, rbx
0x140041395  mov     [r11-30h], r8
0x140041399  mov     r8, rbx
0x14004139c  mov     [r11-38h], rax
0x1400413a0  call    HUBMISC_ControlTransfer
0x1400413a5  mov     edi, eax
0x1400413a7  test    eax, eax
0x1400413a9  jns     short loc_1400413E3
0x1400413ab  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400413b2  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400413b9  jz      short loc_1400413E3
0x1400413bb  mov     rcx, [rbx+9E8h]
0x1400413c2  lea     rax, WPP_2fd11ae104fa34a9334eddada324a17a_Traceguids
0x1400413c9  mov     r9d, 32h ; '2'
0x1400413cf  mov     [rsp+58h+var_30], edi
0x1400413d3  mov     dl, 2
0x1400413d5  mov     [rsp+58h+var_38], rax
0x1400413da  lea     r8d, [r9-2Fh]
0x1400413de  call    WPP_RECORDER_SF_d
0x1400413e3  mov     rbx, [rsp+58h+arg_0]
0x1400413e8  mov     eax, edi
0x1400413ea  add     rsp, 50h
0x1400413ee  pop     rdi
0x1400413ef  retn
```
