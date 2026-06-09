# HUBPDO_CompleteClientSerialRequestWithStatusFailed

- ea: `0x1400148bc`
- end: `0x140014a5f`
- name: `HUBPDO_CompleteClientSerialRequestWithStatusFailed`
- size: `419`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140020bd0`
- `0x140022b30`

## callees

- `0x14000f304`
- `0x1400148bc`
- `0x140045530`
- `0x140045570`

## pseudocode

```c
__int64 __fastcall HUBPDO_CompleteClientSerialRequestWithStatusFailed(__int64 a1)
{
  __int64 v1; // rbp
  __int64 v3; // rcx
  _QWORD *v4; // rdi
  unsigned __int16 *v5; // rsi
  unsigned __int16 v6; // ax
  __int64 v8; // [rsp+20h] [rbp-58h]
  __int64 v9; // [rsp+28h] [rbp-50h]
  __int128 v10; // [rsp+30h] [rbp-48h] BYREF
  __int128 v11; // [rsp+40h] [rbp-38h]
  __int64 v12; // [rsp+50h] [rbp-28h]

  v1 = *(_QWORD *)(a1 + 464);
  *(_QWORD *)(a1 + 464) = 0;
  v10 = 0;
  *(_DWORD *)(a1 + 148) = 0;
  *(_QWORD *)(a1 + 152) = 0;
  v11 = 0;
  v12 = 0;
  LOWORD(v10) = 40;
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int128 *))(WdfFunctions_01015 + 2128))(
    WdfDriverGlobals,
    v1,
    &v10);
  if ( DWORD2(v11) == 2228227 )
  {
    v4 = (_QWORD *)*((_QWORD *)&v10 + 1);
    *(_DWORD *)(*((_QWORD *)&v10 + 1) + 4LL) = -2147482880;
    v5 = (unsigned __int16 *)v4 + 1;
    if ( (byte_14006ED41 & 4) != 0 )
      McTemplateK0pqq_EtwWriteTransfer(
        v3,
        (const EVENT_DESCRIPTOR *)USBHUB3_ETW_EVENT_DEVICE_URB_COMPLETE,
        (const GUID *)(a1 + 1524),
        *(_QWORD *)(a1 + 24),
        *v5,
        -2147482880);
    if ( *v5 == 1 || *v5 == 59 )
      _InterlockedOr((volatile signed __int32 *)(a1 + 1644), 0x10u);
    v6 = *v5;
    if ( *v5 )
    {
      if ( v6 == 1 )
      {
        v4[5] = -1;
      }
      else if ( v6 == 59 )
      {
        v4[7] = -1;
      }
    }
    else
    {
      v4[4] = 0;
    }
  }
  if ( (byte_14006ED41 & 4) != 0 )
  {
    LODWORD(v9) = -1073741823;
    LODWORD(v8) = DWORD2(v11);
    McTemplateK0pqq_EtwWriteTransfer(
      v3,
      (const EVENT_DESCRIPTOR *)USBHUB3_ETW_EVENT_DEVICE_INTERNAL_IOCTL_COMPLETE,
      (const GUID *)(a1 + 1524),
      *(_QWORD *)(a1 + 24),
      v8,
      v9);
  }
  if ( (*(_DWORD *)(a1 + 1644) & 0x40) != 0 )
  {
    *(_OWORD *)(a1 + 1524) = 0;
    _InterlockedAnd((volatile signed __int32 *)(a1 + 1644), 0xFFFFFFBF);
  }
  return (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64))(WdfFunctions_01015 + 2104))(
           WdfDriverGlobals,
           v1,
           3221225473LL);
}

```

## disassembly

```asm
0x1400148bc  mov     r11, rsp
0x1400148bf  mov     [r11+10h], rbx
0x1400148c3  mov     [r11+18h], rbp
0x1400148c7  push    rsi
0x1400148c8  push    rdi
0x1400148c9  push    r14
0x1400148cb  sub     rsp, 60h
0x1400148cf  mov     rax, cs:__security_cookie
0x1400148d6  xor     rax, rsp
0x1400148d9  mov     [rsp+78h+var_20], rax
0x1400148de  mov     rbp, [rcx+1D0h]
0x1400148e5  lea     r8, [r11-48h]
0x1400148e9  xor     eax, eax
0x1400148eb  xor     r14d, r14d
0x1400148ee  mov     [rcx+1D0h], r14
0x1400148f5  xorps   xmm0, xmm0
0x1400148f8  movups  [rsp+78h+var_48], xmm0
0x1400148fd  mov     [rcx+94h], r14d
0x140014904  mov     rbx, rcx
0x140014907  mov     [rcx+98h], r14
0x14001490e  mov     rdx, rbp
0x140014911  mov     rcx, cs:WdfDriverGlobals
0x140014918  movups  [rsp+78h+var_38], xmm0
0x14001491d  mov     [r11-28h], rax
0x140014921  lea     eax, [r14+28h]
0x140014925  mov     word ptr [rsp+78h+var_48], ax
0x14001492a  mov     rax, cs:WdfFunctions_01015
0x140014931  mov     rax, [rax+850h]
0x140014938  call    _guard_dispatch_icall
0x14001493d  cmp     dword ptr [rsp+78h+var_38+8], 220003h
0x140014945  jnz     loc_1400149CD
0x14001494b  mov     rdi, qword ptr [rsp+78h+var_48+8]
0x140014950  mov     dword ptr [rdi+4], 80000300h
0x140014957  lea     rsi, [rdi+2]
0x14001495b  test    cs:byte_14006ED41, 4
0x140014962  jz      short loc_14001498A
0x140014964  movzx   eax, word ptr [rsi]
0x140014967  lea     r8, [rbx+5F4h]
0x14001496e  mov     r9, [rbx+18h]
0x140014972  lea     rdx, USBHUB3_ETW_EVENT_DEVICE_URB_COMPLETE
0x140014979  mov     dword ptr [rsp+78h+var_50], 80000300h
0x140014981  mov     dword ptr [rsp+78h+var_58], eax
0x140014985  call    McTemplateK0pqq_EtwWriteTransfer
0x14001498a  movzx   eax, word ptr [rsi]
0x14001498d  cmp     ax, 1
0x140014991  jz      short loc_140014999
0x140014993  cmp     ax, 3Bh ; ';'
0x140014997  jnz     short loc_1400149A1
0x140014999  lock or dword ptr [rbx+66Ch], 10h
0x1400149a1  movzx   eax, word ptr [rsi]
0x1400149a4  test    ax, ax
0x1400149a7  jnz     short loc_1400149AF
0x1400149a9  mov     [rdi+20h], r14
0x1400149ad  jmp     short loc_1400149CD
0x1400149af  cmp     ax, 1
0x1400149b3  jnz     short loc_1400149BF
0x1400149b5  mov     qword ptr [rdi+28h], 0FFFFFFFFFFFFFFFFh
0x1400149bd  jmp     short loc_1400149CD
0x1400149bf  cmp     ax, 3Bh ; ';'
0x1400149c3  jnz     short loc_1400149CD
0x1400149c5  mov     qword ptr [rdi+38h], 0FFFFFFFFFFFFFFFFh
0x1400149cd  test    cs:byte_14006ED41, 4
0x1400149d4  jz      short loc_1400149FD
0x1400149d6  mov     eax, dword ptr [rsp+78h+var_38+8]
0x1400149da  lea     r8, [rbx+5F4h]
0x1400149e1  mov     r9, [rbx+18h]
0x1400149e5  lea     rdx, USBHUB3_ETW_EVENT_DEVICE_INTERNAL_IOCTL_COMPLETE
0x1400149ec  mov     dword ptr [rsp+78h+var_50], 0C0000001h
0x1400149f4  mov     dword ptr [rsp+78h+var_58], eax
0x1400149f8  call    McTemplateK0pqq_EtwWriteTransfer
0x1400149fd  mov     eax, [rbx+66Ch]
0x140014a03  test    al, 40h
0x140014a05  jz      short loc_140014A19
0x140014a07  xorps   xmm0, xmm0
0x140014a0a  movups  xmmword ptr [rbx+5F4h], xmm0
0x140014a11  lock and dword ptr [rbx+66Ch], 0FFFFFFBFh
0x140014a19  mov     rax, cs:WdfFunctions_01015
0x140014a20  mov     r8d, 0C0000001h
0x140014a26  mov     rcx, cs:WdfDriverGlobals
0x140014a2d  mov     rdx, rbp
0x140014a30  mov     rax, [rax+838h]
0x140014a37  call    _guard_dispatch_icall
0x140014a3c  mov     rcx, [rsp+78h+var_20]
0x140014a41  xor     rcx, rsp; StackCookie
0x140014a44  call    __security_check_cookie
0x140014a49  lea     r11, [rsp+78h+var_18]
0x140014a4e  mov     rbx, [r11+28h]
0x140014a52  mov     rbp, [r11+30h]
0x140014a56  mov     rsp, r11
0x140014a59  pop     r14
0x140014a5b  pop     rdi
0x140014a5c  pop     rsi
0x140014a5d  retn
```
