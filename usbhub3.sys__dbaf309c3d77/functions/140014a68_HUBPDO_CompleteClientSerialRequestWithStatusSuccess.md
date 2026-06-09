# HUBPDO_CompleteClientSerialRequestWithStatusSuccess

- ea: `0x140014a68`
- end: `0x140014c33`
- name: `HUBPDO_CompleteClientSerialRequestWithStatusSuccess`
- size: `459`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140020b70`
- `0x140020c00`

## callees

- `0x14000f304`
- `0x140014a68`
- `0x140045530`
- `0x140045570`

## pseudocode

```c
__int64 __fastcall HUBPDO_CompleteClientSerialRequestWithStatusSuccess(__int64 a1)
{
  __int64 v1; // rdx
  __int64 v3; // rcx
  __int64 v4; // rsi
  __int16 v5; // ax
  _DWORD *v6; // rdx
  __int64 v7; // rdi
  __int64 v8; // rax
  __int64 v10; // [rsp+20h] [rbp-58h]
  __int64 v11; // [rsp+28h] [rbp-50h]
  __int128 v12; // [rsp+30h] [rbp-48h] BYREF
  __int128 v13; // [rsp+40h] [rbp-38h]
  __int64 v14; // [rsp+50h] [rbp-28h]

  v1 = *(_QWORD *)(a1 + 464);
  v12 = 0;
  v13 = 0;
  v14 = 0;
  LOWORD(v12) = 40;
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int128 *))(WdfFunctions_01015 + 2128))(
    WdfDriverGlobals,
    v1,
    &v12);
  if ( DWORD2(v13) == 2228227 )
  {
    v4 = *((_QWORD *)&v12 + 1);
    if ( (byte_14006ED41 & 4) != 0 )
      McTemplateK0pqq_EtwWriteTransfer(
        *(unsigned __int16 *)(*((_QWORD *)&v12 + 1) + 2LL),
        (const EVENT_DESCRIPTOR *)USBHUB3_ETW_EVENT_DEVICE_URB_COMPLETE,
        (const GUID *)(a1 + 1524),
        *(_QWORD *)(a1 + 24),
        *(unsigned __int16 *)(*((_QWORD *)&v12 + 1) + 2LL),
        *(_DWORD *)(*((_QWORD *)&v12 + 1) + 4LL));
    v5 = *(_WORD *)(v4 + 2);
    if ( !v5 && *(_QWORD *)(v4 + 24) || v5 == 1 || v5 == 59 )
      _InterlockedOr((volatile signed __int32 *)(a1 + 1644), 0x10u);
  }
  if ( DWORD2(v13) == 2232243 )
  {
    **((_DWORD **)&v12 + 1) = 0;
    v6 = (_DWORD *)*((_QWORD *)&v12 + 1);
    if ( (*(_DWORD *)(*(_QWORD *)(a1 + 16) + 32LL) & 0x100) != 0 )
    {
      **((_DWORD **)&v12 + 1) |= 2u;
      _InterlockedAnd((volatile signed __int32 *)(*(_QWORD *)(a1 + 16) + 32LL), 0xFFFFFEFF);
    }
    v3 = *(unsigned int *)(*(_QWORD *)(a1 + 16) + 32LL);
    if ( (v3 & 0x80u) != 0LL )
    {
      *v6 |= 1u;
      _InterlockedAnd((volatile signed __int32 *)(*(_QWORD *)(a1 + 16) + 32LL), 0xFFFFFF7F);
    }
  }
  v7 = *(_QWORD *)(a1 + 464);
  v8 = *(_QWORD *)(a1 + 8);
  *(_QWORD *)(a1 + 464) = 0;
  *(_DWORD *)(a1 + 148) = 0;
  *(_QWORD *)(a1 + 152) = 0;
  *(_DWORD *)(v8 + 1424) = 1;
  if ( (byte_14006ED41 & 4) != 0 )
  {
    LODWORD(v11) = 0;
    LODWORD(v10) = DWORD2(v13);
    McTemplateK0pqq_EtwWriteTransfer(
      v3,
      (const EVENT_DESCRIPTOR *)USBHUB3_ETW_EVENT_DEVICE_INTERNAL_IOCTL_COMPLETE,
      (const GUID *)(a1 + 1524),
      *(_QWORD *)(a1 + 24),
      v10,
      v11);
  }
  if ( (*(_DWORD *)(a1 + 1644) & 0x40) != 0 )
  {
    *(_OWORD *)(a1 + 1524) = 0;
    _InterlockedAnd((volatile signed __int32 *)(a1 + 1644), 0xFFFFFFBF);
  }
  return (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD))(WdfFunctions_01015 + 2104))(
           WdfDriverGlobals,
           v7,
           0);
}

```

## disassembly

```asm
0x140014a68  mov     r11, rsp
0x140014a6b  mov     [r11+10h], rbx
0x140014a6f  mov     [r11+18h], rbp
0x140014a73  push    rsi
0x140014a74  push    rdi
0x140014a75  push    r14
0x140014a77  sub     rsp, 60h
0x140014a7b  mov     rax, cs:__security_cookie
0x140014a82  xor     rax, rsp
0x140014a85  mov     [rsp+78h+var_20], rax
0x140014a8a  mov     rdx, [rcx+1D0h]
0x140014a91  lea     r8, [r11-48h]
0x140014a95  xor     eax, eax
0x140014a97  xorps   xmm0, xmm0
0x140014a9a  movups  [rsp+78h+var_48], xmm0
0x140014a9f  mov     rbx, rcx
0x140014aa2  mov     rcx, cs:WdfDriverGlobals
0x140014aa9  movups  [rsp+78h+var_38], xmm0
0x140014aae  mov     [r11-28h], rax
0x140014ab2  mov     eax, 28h ; '('
0x140014ab7  mov     word ptr [rsp+78h+var_48], ax
0x140014abc  mov     rax, cs:WdfFunctions_01015
0x140014ac3  mov     rax, [rax+850h]
0x140014aca  call    _guard_dispatch_icall
0x140014acf  xor     ebp, ebp
0x140014ad1  cmp     dword ptr [rsp+78h+var_38+8], 220003h
0x140014ad9  lea     r14d, [rbp+1]
0x140014add  jnz     short loc_140014B36
0x140014adf  test    cs:byte_14006ED41, 4
0x140014ae6  mov     rsi, qword ptr [rsp+78h+var_48+8]
0x140014aeb  jz      short loc_140014B13
0x140014aed  movzx   ecx, word ptr [rsi+2]
0x140014af1  lea     r8, [rbx+5F4h]
0x140014af8  mov     eax, [rsi+4]
0x140014afb  lea     rdx, USBHUB3_ETW_EVENT_DEVICE_URB_COMPLETE
0x140014b02  mov     r9, [rbx+18h]
0x140014b06  mov     dword ptr [rsp+78h+var_50], eax
0x140014b0a  mov     dword ptr [rsp+78h+var_58], ecx
0x140014b0e  call    McTemplateK0pqq_EtwWriteTransfer
0x140014b13  movzx   eax, word ptr [rsi+2]
0x140014b17  test    ax, ax
0x140014b1a  jnz     short loc_140014B22
0x140014b1c  cmp     [rsi+18h], rbp
0x140014b20  jnz     short loc_140014B2E
0x140014b22  cmp     ax, r14w
0x140014b26  jz      short loc_140014B2E
0x140014b28  cmp     ax, 3Bh ; ';'
0x140014b2c  jnz     short loc_140014B36
0x140014b2e  lock or dword ptr [rbx+66Ch], 10h
0x140014b36  cmp     dword ptr [rsp+78h+var_38+8], 220FB3h
0x140014b3e  jnz     short loc_140014B82
0x140014b40  mov     rax, qword ptr [rsp+78h+var_48+8]
0x140014b45  mov     [rax], ebp
0x140014b47  mov     rax, [rbx+10h]
0x140014b4b  mov     rdx, qword ptr [rsp+78h+var_48+8]
0x140014b50  test    dword ptr [rax+20h], 100h
0x140014b57  jz      short loc_140014B68
0x140014b59  or      dword ptr [rdx], 2
0x140014b5c  mov     rax, [rbx+10h]
0x140014b60  lock and dword ptr [rax+20h], 0FFFFFEFFh
0x140014b68  mov     rax, [rbx+10h]
0x140014b6c  mov     ecx, [rax+20h]
0x140014b6f  test    cl, cl
0x140014b71  jns     short loc_140014B82
0x140014b73  or      [rdx], r14d
0x140014b76  mov     rax, [rbx+10h]
0x140014b7a  lock and dword ptr [rax+20h], 0FFFFFF7Fh
0x140014b82  mov     rdi, [rbx+1D0h]
0x140014b89  mov     rax, [rbx+8]
0x140014b8d  mov     [rbx+1D0h], rbp
0x140014b94  mov     [rbx+94h], ebp
0x140014b9a  mov     [rbx+98h], rbp
0x140014ba1  mov     [rax+590h], r14d
0x140014ba8  test    cs:byte_14006ED41, 4
0x140014baf  jz      short loc_140014BD4
0x140014bb1  mov     eax, dword ptr [rsp+78h+var_38+8]
0x140014bb5  lea     r8, [rbx+5F4h]
0x140014bbc  mov     r9, [rbx+18h]
0x140014bc0  lea     rdx, USBHUB3_ETW_EVENT_DEVICE_INTERNAL_IOCTL_COMPLETE
0x140014bc7  mov     dword ptr [rsp+78h+var_50], ebp
0x140014bcb  mov     dword ptr [rsp+78h+var_58], eax
0x140014bcf  call    McTemplateK0pqq_EtwWriteTransfer
0x140014bd4  mov     eax, [rbx+66Ch]
0x140014bda  test    al, 40h
0x140014bdc  jz      short loc_140014BF0
0x140014bde  xorps   xmm0, xmm0
0x140014be1  movups  xmmword ptr [rbx+5F4h], xmm0
0x140014be8  lock and dword ptr [rbx+66Ch], 0FFFFFFBFh
0x140014bf0  mov     rax, cs:WdfFunctions_01015
0x140014bf7  xor     r8d, r8d
0x140014bfa  mov     rcx, cs:WdfDriverGlobals
0x140014c01  mov     rdx, rdi
0x140014c04  mov     rax, [rax+838h]
0x140014c0b  call    _guard_dispatch_icall
0x140014c10  mov     rcx, [rsp+78h+var_20]
0x140014c15  xor     rcx, rsp; StackCookie
0x140014c18  call    __security_check_cookie
0x140014c1d  lea     r11, [rsp+78h+var_18]
0x140014c22  mov     rbx, [r11+28h]
0x140014c26  mov     rbp, [r11+30h]
0x140014c2a  mov     rsp, r11
0x140014c2d  pop     r14
0x140014c2f  pop     rdi
0x140014c30  pop     rsi
0x140014c31  retn
```
