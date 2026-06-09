# HUBPDO_CompleteClientSerialRequestWithLastStatus

- ea: `0x140014710`
- end: `0x1400148b6`
- name: `HUBPDO_CompleteClientSerialRequestWithLastStatus`
- size: `422`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140020ba0`
- `0x140020c30`

## callees

- `0x14000f304`
- `0x140014710`
- `0x140045530`
- `0x140045570`

## pseudocode

```c
__int64 __fastcall HUBPDO_CompleteClientSerialRequestWithLastStatus(__int64 a1)
{
  __int64 v1; // r14
  int v2; // ebp
  __int64 v4; // rcx
  _QWORD *v5; // rsi
  unsigned __int16 *v6; // rdi
  unsigned __int16 v7; // ax
  __int64 v9; // [rsp+20h] [rbp-78h]
  __int64 v10; // [rsp+28h] [rbp-70h]
  __int128 v11; // [rsp+30h] [rbp-68h] BYREF
  __int128 v12; // [rsp+40h] [rbp-58h]
  __int64 v13; // [rsp+50h] [rbp-48h]

  v1 = *(_QWORD *)(a1 + 464);
  v2 = *(_DWORD *)(a1 + 1568);
  v13 = 0;
  v11 = 0;
  LOWORD(v11) = 40;
  v12 = 0;
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int128 *))(WdfFunctions_01015 + 2128))(
    WdfDriverGlobals,
    v1,
    &v11);
  if ( DWORD2(v12) == 2228227 )
  {
    v5 = (_QWORD *)*((_QWORD *)&v11 + 1);
    v4 = *(unsigned int *)(a1 + 1572);
    *(_DWORD *)(*((_QWORD *)&v11 + 1) + 4LL) = v4;
    v6 = (unsigned __int16 *)v5 + 1;
    if ( (byte_14006ED41 & 4) != 0 )
      McTemplateK0pqq_EtwWriteTransfer(
        v4,
        (const EVENT_DESCRIPTOR *)USBHUB3_ETW_EVENT_DEVICE_URB_COMPLETE,
        (const GUID *)(a1 + 1524),
        *(_QWORD *)(a1 + 24),
        *v6,
        v4);
    if ( *v6 == 1 || *v6 == 59 )
      _InterlockedOr((volatile signed __int32 *)(a1 + 1644), 0x10u);
    v7 = *v6;
    if ( *v6 )
    {
      if ( v7 == 1 )
      {
        v5[5] = -1;
      }
      else if ( v7 == 59 )
      {
        v5[7] = -1;
      }
    }
    else
    {
      v5[4] = 0;
    }
  }
  *(_QWORD *)(a1 + 464) = 0;
  *(_DWORD *)(a1 + 148) = 0;
  *(_QWORD *)(a1 + 152) = 0;
  *(_QWORD *)(a1 + 1568) = 0;
  if ( (byte_14006ED41 & 4) != 0 )
  {
    LODWORD(v10) = v2;
    LODWORD(v9) = DWORD2(v12);
    McTemplateK0pqq_EtwWriteTransfer(
      v4,
      (const EVENT_DESCRIPTOR *)USBHUB3_ETW_EVENT_DEVICE_INTERNAL_IOCTL_COMPLETE,
      (const GUID *)(a1 + 1524),
      *(_QWORD *)(a1 + 24),
      v9,
      v10);
  }
  if ( (*(_DWORD *)(a1 + 1644) & 0x40) != 0 )
  {
    *(_OWORD *)(a1 + 1524) = 0;
    _InterlockedAnd((volatile signed __int32 *)(a1 + 1644), 0xFFFFFFBF);
  }
  if ( v2 >= 0 )
    v2 = -1073741823;
  return (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD))(WdfFunctions_01015 + 2104))(
           WdfDriverGlobals,
           v1,
           (unsigned int)v2);
}

```

## disassembly

```asm
0x140014710  push    rbx
0x140014712  push    rbp
0x140014713  push    rsi
0x140014714  push    rdi
0x140014715  push    r14
0x140014717  push    r15
0x140014719  sub     rsp, 68h
0x14001471d  mov     rax, cs:__security_cookie
0x140014724  xor     rax, rsp
0x140014727  mov     [rsp+98h+var_40], rax
0x14001472c  mov     r14, [rcx+1D0h]
0x140014733  lea     r8, [rsp+98h+var_68]
0x140014738  mov     ebp, [rcx+620h]
0x14001473e  xor     eax, eax
0x140014740  mov     [rsp+98h+var_48], rax
0x140014745  xorps   xmm0, xmm0
0x140014748  movups  [rsp+98h+var_68], xmm0
0x14001474d  mov     eax, 28h ; '('
0x140014752  mov     rbx, rcx
0x140014755  mov     rcx, cs:WdfDriverGlobals
0x14001475c  mov     rdx, r14
0x14001475f  mov     word ptr [rsp+98h+var_68], ax
0x140014764  mov     rax, cs:WdfFunctions_01015
0x14001476b  movups  [rsp+98h+var_58], xmm0
0x140014770  mov     rax, [rax+850h]
0x140014777  call    _guard_dispatch_icall
0x14001477c  xor     r15d, r15d
0x14001477f  cmp     dword ptr [rsp+98h+var_58+8], 220003h
0x140014787  jnz     loc_14001480D
0x14001478d  mov     rsi, qword ptr [rsp+98h+var_68+8]
0x140014792  mov     ecx, [rbx+624h]
0x140014798  mov     [rsi+4], ecx
0x14001479b  lea     rdi, [rsi+2]
0x14001479f  test    cs:byte_14006ED41, 4
0x1400147a6  jz      short loc_1400147CA
0x1400147a8  movzx   eax, word ptr [rdi]
0x1400147ab  lea     r8, [rbx+5F4h]
0x1400147b2  mov     r9, [rbx+18h]
0x1400147b6  lea     rdx, USBHUB3_ETW_EVENT_DEVICE_URB_COMPLETE
0x1400147bd  mov     dword ptr [rsp+98h+var_70], ecx
0x1400147c1  mov     dword ptr [rsp+98h+var_78], eax
0x1400147c5  call    McTemplateK0pqq_EtwWriteTransfer
0x1400147ca  movzx   eax, word ptr [rdi]
0x1400147cd  cmp     ax, 1
0x1400147d1  jz      short loc_1400147D9
0x1400147d3  cmp     ax, 3Bh ; ';'
0x1400147d7  jnz     short loc_1400147E1
0x1400147d9  lock or dword ptr [rbx+66Ch], 10h
0x1400147e1  movzx   eax, word ptr [rdi]
0x1400147e4  test    ax, ax
0x1400147e7  jnz     short loc_1400147EF
0x1400147e9  mov     [rsi+20h], r15
0x1400147ed  jmp     short loc_14001480D
0x1400147ef  cmp     ax, 1
0x1400147f3  jnz     short loc_1400147FF
0x1400147f5  mov     qword ptr [rsi+28h], 0FFFFFFFFFFFFFFFFh
0x1400147fd  jmp     short loc_14001480D
0x1400147ff  cmp     ax, 3Bh ; ';'
0x140014803  jnz     short loc_14001480D
0x140014805  mov     qword ptr [rsi+38h], 0FFFFFFFFFFFFFFFFh
0x14001480d  mov     [rbx+1D0h], r15
0x140014814  mov     [rbx+94h], r15d
0x14001481b  mov     [rbx+98h], r15
0x140014822  mov     [rbx+620h], r15
0x140014829  test    cs:byte_14006ED41, 4
0x140014830  jz      short loc_140014855
0x140014832  mov     eax, dword ptr [rsp+98h+var_58+8]
0x140014836  lea     r8, [rbx+5F4h]
0x14001483d  mov     r9, [rbx+18h]
0x140014841  lea     rdx, USBHUB3_ETW_EVENT_DEVICE_INTERNAL_IOCTL_COMPLETE
0x140014848  mov     dword ptr [rsp+98h+var_70], ebp
0x14001484c  mov     dword ptr [rsp+98h+var_78], eax
0x140014850  call    McTemplateK0pqq_EtwWriteTransfer
0x140014855  mov     eax, [rbx+66Ch]
0x14001485b  test    al, 40h
0x14001485d  jz      short loc_140014871
0x14001485f  xorps   xmm0, xmm0
0x140014862  movups  xmmword ptr [rbx+5F4h], xmm0
0x140014869  lock and dword ptr [rbx+66Ch], 0FFFFFFBFh
0x140014871  mov     rcx, cs:WdfDriverGlobals
0x140014878  test    ebp, ebp
0x14001487a  mov     eax, 0C0000001h
0x14001487f  mov     rdx, r14
0x140014882  cmovns  ebp, eax
0x140014885  mov     rax, cs:WdfFunctions_01015
0x14001488c  mov     r8d, ebp
0x14001488f  mov     rax, [rax+838h]
0x140014896  call    _guard_dispatch_icall
0x14001489b  mov     rcx, [rsp+98h+var_40]
0x1400148a0  xor     rcx, rsp; StackCookie
0x1400148a3  call    __security_check_cookie
0x1400148a8  add     rsp, 68h
0x1400148ac  pop     r15
0x1400148ae  pop     r14
0x1400148b0  pop     rdi
0x1400148b1  pop     rsi
0x1400148b2  pop     rbp
0x1400148b3  pop     rbx
0x1400148b4  retn
```
