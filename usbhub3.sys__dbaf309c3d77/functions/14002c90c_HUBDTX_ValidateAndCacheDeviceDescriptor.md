# HUBDTX_ValidateAndCacheDeviceDescriptor

- ea: `0x14002c90c`
- end: `0x14002cbd8`
- name: `HUBDTX_ValidateAndCacheDeviceDescriptor`
- size: `716`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x140024950`

## callees

- `0x1400024b8`
- `0x1400025a4`
- `0x1400067ac`
- `0x1400083b4`
- `0x14002c90c`
- `0x14002d940`
- `0x14003d160`
- `0x140045570`
- `0x140045940`

## pseudocode

```c
__int64 __fastcall HUBDTX_ValidateAndCacheDeviceDescriptor(__int64 *a1, __int16 a2)
{
  __int64 v2; // rdi
  _WORD *v4; // rsi
  __int64 v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // rcx
  int v8; // eax
  __int64 v9; // rax
  int v10; // edx
  bool v11; // cf
  unsigned int v12; // edx
  bool v13; // zf
  __int64 v14; // rcx
  int v15; // edx
  unsigned int v16; // edi
  _WORD v18[2]; // [rsp+50h] [rbp-19h] BYREF
  int v19; // [rsp+54h] [rbp-15h]
  __int64 v20; // [rsp+58h] [rbp-11h]
  int v21; // [rsp+60h] [rbp-9h]
  int v22; // [rsp+64h] [rbp-5h]
  void (__fastcall *v23)(__int64, ULONG); // [rsp+68h] [rbp-1h]
  void (__fastcall *v24)(__int64, ULONG); // [rsp+70h] [rbp+7h]
  __int64 *v25; // [rsp+78h] [rbp+Fh]
  _BOOL8 v26; // [rsp+80h] [rbp+17h]
  char v27; // [rsp+D0h] [rbp+67h] BYREF

  v2 = (__int64)(a1 + 1);
  v27 = 0;
  v4 = (_WORD *)a1 + 870;
  v5 = a1[1];
  if ( *(_BYTE *)(v5 + 1472) )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v6 = *a1;
      LOBYTE(v6) = 2;
      WPP_RECORDER_SF_DDDD(
        *(_QWORD *)(v5 + 1432),
        v6,
        5,
        82,
        (__int64)WPP_736cb17edbb73fe74dd9f642bb1bec68_Traceguids,
        v4[4],
        v4[5],
        *(_DWORD *)(*a1 + 96),
        *(_WORD *)(v5 + 200));
    }
    *((_DWORD *)a1 + 66) = 0;
    memset(v4, 0, 0x100u);
    v7 = (__int64)(a1 + 1);
  }
  else
  {
    v7 = v2;
  }
  v8 = *((_DWORD *)a1 + 66);
  if ( v8 != 18 )
  {
    if ( v8 )
    {
      *((_DWORD *)a1 + 610) = 1073807365;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(a2) = 2;
        WPP_RECORDER_SF_dD(
          *(_QWORD *)(*(_QWORD *)v7 + 1432LL),
          a2,
          5,
          83,
          (__int64)WPP_736cb17edbb73fe74dd9f642bb1bec68_Traceguids,
          v8,
          18);
      }
    }
    else
    {
      *((_DWORD *)a1 + 610) = 1073807360;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(a2) = 2;
        WPP_RECORDER_SF_(
          *(_QWORD *)(*(_QWORD *)v2 + 1432LL),
          a2,
          5,
          84,
          (__int64)WPP_736cb17edbb73fe74dd9f642bb1bec68_Traceguids);
      }
    }
LABEL_15:
    v16 = 4065;
    if ( (byte_14006ED41 & 1) != 0 )
      McTemplateK0p_EtwWriteTransfer(
        v7,
        (const EVENT_DESCRIPTOR *)USBHUB3_ETW_EVENT_INVALID_DEVICE_DESCRIPTOR,
        (const GUID *)((char *)a1 + 1524),
        a1[3]);
    return v16;
  }
  v9 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, WDFDRIVER__ *, __int64 *))(WdfFunctions_01015 + 1616))(
         WdfDriverGlobals,
         WdfDriverGlobals->Driver,
         off_14006B2C0);
  v25 = a1;
  v26 = 0;
  v10 = *(_DWORD *)(v9 + 4);
  v20 = 0;
  v18[1] = 0;
  v22 = 0;
  v18[0] = *((_WORD *)a1 + 999);
  v19 = *((_DWORD *)a1 + 43);
  *(_WORD *)((char *)&v20 + 5) = (v10 & 0x20) != 0;
  LOBYTE(v9) = (v10 & 0x2000) != 0;
  v11 = (v10 & 0x4000) != 0;
  v12 = *((_DWORD *)a1 + 66);
  HIBYTE(v20) = v9;
  v13 = (*((_DWORD *)a1 + 413) & 0x200000) == 0;
  BYTE4(v20) = v11;
  v26 = !v13;
  v14 = *(_QWORD *)v2;
  v21 = *(_DWORD *)(*(_QWORD *)v2 + 220LL);
  v23 = HUBMISC_LogDescriptorValidationErrorForDevice;
  v24 = HUBMISC_LogDescriptorValidationWarningForDevice;
  if ( !HUBDESC_ValidateDeviceDescriptor((__int64)v4, v12, (__int64)v18, &v27, *(_QWORD *)(v14 + 1432)) )
  {
    *((_DWORD *)a1 + 610) = 1073807365;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v15) = 2;
      WPP_RECORDER_SF_d(
        *(_QWORD *)(*(_QWORD *)v2 + 1432LL),
        v15,
        5,
        85,
        (__int64)WPP_736cb17edbb73fe74dd9f642bb1bec68_Traceguids,
        *((_DWORD *)a1 + 66));
    }
    goto LABEL_15;
  }
  v13 = v27 == 0;
  v16 = 4077;
  *(_OWORD *)((char *)a1 + 1996) = *(_OWORD *)v4;
  *((_WORD *)a1 + 1006) = v4[8];
  if ( !v13 )
    _InterlockedOr((volatile signed __int32 *)a1 + 410, 0x20000u);
  return v16;
}

```

## disassembly

```asm
0x14002c90c  push    rbp
0x14002c90e  push    rbx
0x14002c90f  push    rsi
0x14002c910  push    rdi
0x14002c911  push    r13
0x14002c913  push    r15
0x14002c915  lea     rbp, [rsp-2Fh]
0x14002c91a  sub     rsp, 98h
0x14002c921  lea     rdi, [rcx+8]
0x14002c925  mov     [rbp+57h+arg_0], 0
0x14002c929  mov     rbx, rcx
0x14002c92c  lea     rsi, [rcx+6CCh]
0x14002c933  mov     rcx, [rdi]
0x14002c936  lea     r15, WPP_RECORDER_INITIALIZED
0x14002c93d  lea     r13, WPP_736cb17edbb73fe74dd9f642bb1bec68_Traceguids
0x14002c944  cmp     byte ptr [rcx+5C0h], 0
0x14002c94b  jz      short loc_14002C9BC
0x14002c94d  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x14002c954  jz      short loc_14002C99C
0x14002c956  movzx   eax, word ptr [rcx+0C8h]
0x14002c95d  mov     r9d, 52h ; 'R'
0x14002c963  mov     rdx, [rbx]
0x14002c966  movzx   r8d, word ptr [rsi+0Ah]
0x14002c96b  movzx   r10d, word ptr [rsi+8]
0x14002c970  mov     rcx, [rcx+598h]
0x14002c977  mov     [rsp+0C0h+var_80], eax
0x14002c97b  mov     eax, [rdx+60h]
0x14002c97e  mov     dl, 2
0x14002c980  mov     [rsp+0C0h+var_88], eax
0x14002c984  mov     [rsp+0C0h+var_90], r8d
0x14002c989  lea     r8d, [r9-4Dh]
0x14002c98d  mov     [rsp+0C0h+var_98], r10d
0x14002c992  mov     [rsp+0C0h+var_A0], r13
0x14002c997  call    WPP_RECORDER_SF_DDDD
0x14002c99c  xor     edx, edx; Val
0x14002c99e  mov     dword ptr [rbx+108h], 0
0x14002c9a8  mov     r8d, 100h; Size
0x14002c9ae  mov     rcx, rsi; void *
0x14002c9b1  call    memset
0x14002c9b6  lea     rcx, [rbx+8]
0x14002c9ba  jmp     short loc_14002C9BF
0x14002c9bc  mov     rcx, rdi
0x14002c9bf  mov     eax, [rbx+108h]
0x14002c9c5  cmp     eax, 12h
0x14002c9c8  jz      loc_14002CA56
0x14002c9ce  test    eax, eax
0x14002c9d0  jz      short loc_14002CA1A
0x14002c9d2  mov     dword ptr [rbx+988h], 40010005h
0x14002c9dc  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x14002c9e3  jz      loc_14002CB73
0x14002c9e9  mov     rcx, [rcx]
0x14002c9ec  mov     r9d, 53h ; 'S'
0x14002c9f2  mov     [rsp+0C0h+var_90], 12h
0x14002c9fa  mov     dl, 2
0x14002c9fc  mov     [rsp+0C0h+var_98], eax
0x14002ca00  mov     [rsp+0C0h+var_A0], r13
0x14002ca05  mov     rcx, [rcx+598h]
0x14002ca0c  lea     r8d, [r9-4Eh]
0x14002ca10  call    WPP_RECORDER_SF_dD
0x14002ca15  jmp     loc_14002CB73
0x14002ca1a  mov     dword ptr [rbx+988h], 40010000h
0x14002ca24  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x14002ca2b  jz      loc_14002CB73
0x14002ca31  mov     rcx, [rdi]
0x14002ca34  mov     r9d, 54h ; 'T'
0x14002ca3a  mov     dl, 2
0x14002ca3c  mov     [rsp+0C0h+var_A0], r13
0x14002ca41  mov     rcx, [rcx+598h]
0x14002ca48  lea     r8d, [r9-4Fh]
0x14002ca4c  call    WPP_RECORDER_SF_
0x14002ca51  jmp     loc_14002CB73
0x14002ca56  mov     rax, cs:WdfFunctions_01015
0x14002ca5d  mov     rcx, cs:WdfDriverGlobals
0x14002ca64  mov     r8, cs:off_14006B2C0
0x14002ca6b  mov     rax, [rax+650h]
0x14002ca72  mov     rdx, [rcx]
0x14002ca75  call    _guard_dispatch_icall
0x14002ca7a  xor     r8d, r8d
0x14002ca7d  mov     [rbp+57h+var_48], rbx
0x14002ca81  movzx   ecx, r8b
0x14002ca85  mov     [rbp+57h+var_40], r8
0x14002ca89  mov     edx, [rax+4]
0x14002ca8c  xor     eax, eax
0x14002ca8e  mov     [rbp+57h+var_68], rax
0x14002ca92  lea     r9d, [r8+1]
0x14002ca96  mov     [rbp+57h+var_6E], ax
0x14002ca9a  lea     r8, [rbp+57h+var_70]
0x14002ca9e  mov     [rbp+57h+var_5C], eax
0x14002caa1  test    dl, 20h
0x14002caa4  movzx   eax, word ptr [rbx+7CEh]
0x14002caab  mov     [rbp+57h+var_70], ax
0x14002caaf  mov     eax, [rbx+0ACh]
0x14002cab5  mov     [rbp+57h+var_6C], eax
0x14002cab8  movzx   eax, byte ptr [rbp+57h+var_68+5]
0x14002cabc  cmovnz  eax, r9d
0x14002cac0  bt      edx, 0Dh
0x14002cac4  mov     byte ptr [rbp+57h+var_68+5], al
0x14002cac7  movzx   eax, byte ptr [rbp+57h+var_68+7]
0x14002cacb  cmovb   eax, r9d
0x14002cacf  bt      edx, 0Eh
0x14002cad3  mov     edx, [rbx+108h]
0x14002cad9  mov     byte ptr [rbp+57h+var_68+7], al
0x14002cadc  movzx   eax, byte ptr [rbp+57h+var_68+4]
0x14002cae0  cmovb   eax, r9d
0x14002cae4  test    dword ptr [rbx+674h], 200000h
0x14002caee  mov     byte ptr [rbp+57h+var_68+4], al
0x14002caf1  cmovnz  ecx, r9d
0x14002caf5  lea     r9, [rbp+57h+arg_0]
0x14002caf9  mov     byte ptr [rbp+57h+var_40], cl
0x14002cafc  mov     rcx, [rdi]
0x14002caff  mov     eax, [rcx+0DCh]
0x14002cb05  mov     [rbp+57h+var_60], eax
0x14002cb08  lea     rax, HUBMISC_LogDescriptorValidationErrorForDevice
0x14002cb0f  mov     [rbp+57h+var_58], rax
0x14002cb13  lea     rax, HUBMISC_LogDescriptorValidationWarningForDevice
0x14002cb1a  mov     [rbp+57h+var_50], rax
0x14002cb1e  mov     rax, [rcx+598h]
0x14002cb25  mov     rcx, rsi
0x14002cb28  mov     [rsp+0C0h+var_A0], rax
0x14002cb2d  call    HUBDESC_ValidateDeviceDescriptor
0x14002cb32  test    al, al
0x14002cb34  jnz     short loc_14002CB9A
0x14002cb36  mov     dword ptr [rbx+988h], 40010005h
0x14002cb40  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x14002cb47  jz      short loc_14002CB73
0x14002cb49  mov     rcx, [rdi]
0x14002cb4c  mov     r9d, 55h ; 'U'
0x14002cb52  mov     eax, [rbx+108h]
0x14002cb58  mov     dl, 2
0x14002cb5a  mov     [rsp+0C0h+var_98], eax
0x14002cb5e  mov     [rsp+0C0h+var_A0], r13
0x14002cb63  mov     rcx, [rcx+598h]
0x14002cb6a  lea     r8d, [r9-50h]
0x14002cb6e  call    WPP_RECORDER_SF_d
0x14002cb73  test    cs:byte_14006ED41, 1
0x14002cb7a  mov     edi, 0FE1h
0x14002cb7f  jz      short loc_14002CBC5
0x14002cb81  mov     r9, [rbx+18h]
0x14002cb85  lea     r8, [rbx+5F4h]
0x14002cb8c  lea     rdx, USBHUB3_ETW_EVENT_INVALID_DEVICE_DESCRIPTOR
0x14002cb93  call    McTemplateK0p_EtwWriteTransfer
0x14002cb98  jmp     short loc_14002CBC5
0x14002cb9a  cmp     [rbp+57h+arg_0], 0
0x14002cb9e  mov     edi, 0FEDh
0x14002cba3  movups  xmm0, xmmword ptr [rsi]
0x14002cba6  movups  xmmword ptr [rbx+7CCh], xmm0
0x14002cbad  movzx   ecx, word ptr [rsi+10h]
0x14002cbb1  mov     [rbx+7DCh], cx
0x14002cbb8  jz      short loc_14002CBC5
0x14002cbba  lock or dword ptr [rbx+668h], 20000h
0x14002cbc5  mov     eax, edi
0x14002cbc7  add     rsp, 98h
0x14002cbce  pop     r15
0x14002cbd0  pop     r13
0x14002cbd2  pop     rdi
0x14002cbd3  pop     rsi
0x14002cbd4  pop     rbx
0x14002cbd5  pop     rbp
0x14002cbd6  retn
```
