# WinUSB_SetPowerPolicy

- ea: `0x140004ea4`
- end: `0x140005294`
- name: `WinUSB_SetPowerPolicy`
- size: `1008`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x1400026d0`

## callees

- `0x140001020`
- `0x1400011c8`
- `0x14000193c`
- `0x140001d24`
- `0x140004ea4`
- `0x140010700`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140004fb5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140004fb5`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000522f`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000522f`

## pseudocode

```c
__int64 __fastcall WinUSB_SetPowerPolicy(__int64 a1, __int64 a2, __int64 a3, _BYTE *a4)
{
  unsigned int v8; // ebx
  unsigned __int16 v9; // r9
  int v10; // eax
  KIRQL v11; // r15
  unsigned __int16 v12; // r9
  char v13; // al
  int v14; // r9d
  int v15; // esi
  int v16; // eax
  __int64 v17; // rax
  int v18; // eax
  char v19; // r8
  char v20; // cl
  __int64 (__fastcall *v21)(PWDF_DRIVER_GLOBALS, __int64); // rax
  __int64 v22; // rax
  __int64 v23; // rax
  unsigned __int64 *v25; // [rsp+20h] [rbp-58h]
  __int64 v26; // [rsp+28h] [rbp-50h]
  int v27; // [rsp+28h] [rbp-50h]
  int v28; // [rsp+28h] [rbp-50h]
  int v29; // [rsp+30h] [rbp-48h]
  unsigned __int64 v30; // [rsp+80h] [rbp+8h] BYREF
  __int64 v31; // [rsp+98h] [rbp+20h] BYREF

  v30 = 0;
  v31 = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    WPP_RECORDER_SF_(
      (__int64)WPP_GLOBAL_Control->DeviceExtension,
      5u,
      1u,
      0xB2u,
      (__int64)WPP_1ea4bda7f8b23cafb6f0c7d9f6a1b177_Traceguids);
  *a4 = 1;
  if ( !*(_BYTE *)(a1 + 160) )
  {
    v8 = -1073741808;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return v8;
    v9 = 179;
    v27 = -1073741808;
    goto LABEL_7;
  }
  v25 = &v30;
  v10 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64, __int64 *))(WdfFunctions_01015 + 2152))(
          WdfDriverGlobals,
          a3,
          12,
          &v31);
  v8 = v10;
  if ( v10 >= 0 )
  {
    v11 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 40));
    if ( *(_DWORD *)(v31 + 4) == 129 )
    {
      v13 = v30;
      if ( v30 >= 0xD )
      {
        v19 = *(_BYTE *)(v31 + 12);
        v20 = *(_BYTE *)(a1 + 164);
        *(_BYTE *)(a1 + 164) = v19 != 0;
        if ( v20 == (v19 != 0) )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            WPP_RECORDER_SF_(
              (__int64)WPP_GLOBAL_Control->DeviceExtension,
              4u,
              2u,
              0xB6u,
              (__int64)WPP_1ea4bda7f8b23cafb6f0c7d9f6a1b177_Traceguids);
        }
        else
        {
          v21 = *(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 1256);
          if ( v19 )
          {
            v22 = v21(WdfDriverGlobals, a2);
            (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD, __int64, const char *))(WdfFunctions_01015
                                                                                                + 3512))(
              WdfDriverGlobals,
              v22,
              0,
              3853,
              "onecore\\drivers\\wdm\\usb\\driver\\winusb\\sys\\ioctl.c");
          }
          else
          {
            v23 = v21(WdfDriverGlobals, a2);
            LODWORD(v25) = 3866;
            v8 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD, _QWORD, unsigned __int64 *, const char *))(WdfFunctions_01015 + 3504))(
                   WdfDriverGlobals,
                   v23,
                   0,
                   0,
                   v25,
                   "onecore\\drivers\\wdm\\usb\\driver\\winusb\\sys\\ioctl.c");
            if ( v8 == 259 )
              v8 = 0;
          }
        }
        goto LABEL_34;
      }
      v8 = -1073741811;
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_34;
      v14 = 181;
    }
    else
    {
      if ( *(_DWORD *)(v31 + 4) != 131 )
      {
        v8 = -1073741811;
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v29 = -1073741811;
          v12 = 185;
          v28 = *(_DWORD *)(v31 + 4);
LABEL_15:
          WPP_RECORDER_SF_dD(
            (__int64)WPP_GLOBAL_Control->DeviceExtension,
            2u,
            3u,
            v12,
            (__int64)WPP_1ea4bda7f8b23cafb6f0c7d9f6a1b177_Traceguids,
            v28,
            v29);
        }
LABEL_34:
        KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 40), v11);
        goto LABEL_35;
      }
      v13 = v30;
      if ( v30 >= 0x10 )
      {
        v15 = *(_DWORD *)(a1 + 168);
        v16 = *(_DWORD *)(v31 + 12);
        *(_DWORD *)(a1 + 168) = v16;
        if ( !*(_BYTE *)(a1 + 232) )
          goto LABEL_34;
        *(_DWORD *)(a1 + 192) = v16;
        v17 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 1256))(
                WdfDriverGlobals,
                a2);
        v18 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64))(WdfFunctions_01015 + 368))(
                WdfDriverGlobals,
                v17,
                a1 + 180);
        v8 = v18;
        if ( v18 >= 0 )
          goto LABEL_34;
        *(_DWORD *)(a1 + 168) = v15;
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_34;
        v29 = v18;
        v12 = 184;
        v28 = v15;
        goto LABEL_15;
      }
      v8 = -1073741811;
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_34;
      v14 = 183;
    }
    WPP_RECORDER_SF_id(WPP_GLOBAL_Control->DeviceExtension, v31, *(_DWORD *)(v31 + 4), v14, (unsigned int)&v30, v13);
    goto LABEL_34;
  }
  if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    return v8;
  v9 = 180;
  v27 = v10;
LABEL_7:
  WPP_RECORDER_SF_d(
    (__int64)WPP_GLOBAL_Control->DeviceExtension,
    2u,
    2u,
    v9,
    (__int64)WPP_1ea4bda7f8b23cafb6f0c7d9f6a1b177_Traceguids,
    v27);
LABEL_35:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LODWORD(v26) = v8;
    WPP_RECORDER_SF_d(
      (__int64)WPP_GLOBAL_Control->DeviceExtension,
      5u,
      1u,
      0xBAu,
      (__int64)WPP_1ea4bda7f8b23cafb6f0c7d9f6a1b177_Traceguids,
      v26);
  }
  return v8;
}

```

## disassembly

```asm
0x140004ea4  mov     rax, rsp
0x140004ea7  mov     [rax+10h], rbx
0x140004eab  push    rbp
0x140004eac  push    rsi
0x140004ead  push    rdi
0x140004eae  push    r12
0x140004eb0  push    r13
0x140004eb2  push    r14
0x140004eb4  push    r15
0x140004eb6  sub     rsp, 40h
0x140004eba  xor     r13d, r13d
0x140004ebd  mov     rbx, r9
0x140004ec0  mov     [rax+8], r13
0x140004ec4  mov     rsi, r8
0x140004ec7  mov     [rax+20h], r13
0x140004ecb  mov     r14, rdx
0x140004ece  mov     rdi, rcx
0x140004ed1  lea     r12, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140004ed8  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140004edf  lea     rbp, WPP_1ea4bda7f8b23cafb6f0c7d9f6a1b177_Traceguids
0x140004ee6  jz      short loc_140004F0F
0x140004ee8  mov     rcx, cs:WPP_GLOBAL_Control
0x140004eef  cmp     [rcx+48h], r13w
0x140004ef4  jz      short loc_140004F0F
0x140004ef6  mov     rcx, [rcx+40h]
0x140004efa  lea     r8d, [r13+1]
0x140004efe  mov     r9d, 0B2h
0x140004f04  mov     [rax-58h], rbp
0x140004f08  mov     dl, 5
0x140004f0a  call    WPP_RECORDER_SF_
0x140004f0f  mov     byte ptr [rbx], 1
0x140004f12  cmp     [rdi+0A0h], r13b
0x140004f19  jnz     short loc_140004F5A
0x140004f1b  mov     ebx, 0C0000010h
0x140004f20  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x140004f27  jz      loc_140005279
0x140004f2d  mov     r9d, 0B3h
0x140004f33  mov     dword ptr [rsp+78h+var_50], ebx
0x140004f37  mov     rcx, cs:WPP_GLOBAL_Control
0x140004f3e  mov     r8d, 2
0x140004f44  mov     dl, r8b
0x140004f47  mov     [rsp+78h+var_58], rbp
0x140004f4c  mov     rcx, [rcx+40h]
0x140004f50  call    WPP_RECORDER_SF_d
0x140004f55  jmp     loc_140005242
0x140004f5a  mov     rax, cs:WdfFunctions_01015
0x140004f61  lea     rcx, [rsp+78h+arg_0]
0x140004f69  mov     [rsp+78h+var_58], rcx
0x140004f6e  lea     r9, [rsp+78h+arg_18]
0x140004f76  mov     rcx, cs:WdfDriverGlobals
0x140004f7d  mov     r8d, 0Ch
0x140004f83  mov     rdx, rsi
0x140004f86  mov     rax, [rax+868h]
0x140004f8d  call    _guard_dispatch_icall
0x140004f92  mov     ebx, eax
0x140004f94  test    eax, eax
0x140004f96  jns     short loc_140004FB1
0x140004f98  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x140004f9f  jz      loc_140005279
0x140004fa5  mov     r9d, 0B4h
0x140004fab  mov     dword ptr [rsp+78h+var_50], eax
0x140004faf  jmp     short loc_140004F37
0x140004fb1  lea     rcx, [rdi+28h]; SpinLock
0x140004fb5  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140004fbc  nop     dword ptr [rax+rax+00h]
0x140004fc1  mov     rdx, [rsp+78h+arg_18]
0x140004fc9  mov     r15b, al
0x140004fcc  mov     r8d, [rdx+4]
0x140004fd0  mov     ecx, r8d
0x140004fd3  sub     ecx, 81h
0x140004fd9  jz      loc_140005104
0x140004fdf  cmp     ecx, 2
0x140004fe2  jz      short loc_14000502E
0x140004fe4  mov     ebx, 0C000000Dh
0x140004fe9  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x140004ff0  jz      loc_140005228
0x140004ff6  mov     [rsp+78h+var_48], ebx
0x140004ffa  mov     r9d, 0B9h
0x140005000  mov     dword ptr [rsp+78h+var_50], r8d
0x140005005  mov     rcx, cs:WPP_GLOBAL_Control
0x14000500c  lea     rax, WPP_1ea4bda7f8b23cafb6f0c7d9f6a1b177_Traceguids
0x140005013  mov     r8d, 3
0x140005019  mov     [rsp+78h+var_58], rax
0x14000501e  mov     dl, 2
0x140005020  mov     rcx, [rcx+40h]
0x140005024  call    WPP_RECORDER_SF_dD
0x140005029  jmp     loc_140005228
0x14000502e  mov     rax, [rsp+78h+arg_0]
0x140005036  cmp     rax, 10h
0x14000503a  jnb     short loc_14000506E
0x14000503c  mov     ebx, 0C000000Dh
0x140005041  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x140005048  jz      loc_140005228
0x14000504e  mov     r9d, 0B7h
0x140005054  mov     rcx, cs:WPP_GLOBAL_Control
0x14000505b  mov     [rsp+78h+var_50], rax
0x140005060  mov     rcx, [rcx+40h]
0x140005064  call    WPP_RECORDER_SF_id
0x140005069  jmp     loc_140005228
0x14000506e  mov     esi, [rdi+0A8h]
0x140005074  mov     eax, [rdx+0Ch]
0x140005077  mov     [rdi+0A8h], eax
0x14000507d  cmp     [rdi+0E8h], r13b
0x140005084  jz      loc_140005228
0x14000508a  lea     rbx, [rdi+0B4h]
0x140005091  mov     rdx, r14
0x140005094  mov     [rbx+0Ch], eax
0x140005097  mov     rax, cs:WdfFunctions_01015
0x14000509e  mov     rcx, cs:WdfDriverGlobals
0x1400050a5  mov     rax, [rax+4E8h]
0x1400050ac  call    _guard_dispatch_icall
0x1400050b1  mov     rcx, cs:WdfFunctions_01015
0x1400050b8  mov     rdx, rax
0x1400050bb  mov     r8, rbx
0x1400050be  mov     r9, [rcx+170h]
0x1400050c5  mov     rcx, cs:WdfDriverGlobals
0x1400050cc  mov     rax, r9
0x1400050cf  call    _guard_dispatch_icall
0x1400050d4  mov     ebx, eax
0x1400050d6  test    eax, eax
0x1400050d8  jns     loc_140005228
0x1400050de  mov     [rdi+0A8h], esi
0x1400050e4  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x1400050eb  jz      loc_140005228
0x1400050f1  mov     [rsp+78h+var_48], eax
0x1400050f5  mov     r9d, 0B8h
0x1400050fb  mov     dword ptr [rsp+78h+var_50], esi
0x1400050ff  jmp     loc_140005005
0x140005104  mov     rax, [rsp+78h+arg_0]
0x14000510c  cmp     rax, 0Dh
0x140005110  jnb     short loc_14000512F
0x140005112  mov     ebx, 0C000000Dh
0x140005117  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x14000511e  jz      loc_140005228
0x140005124  mov     r9d, 0B5h
0x14000512a  jmp     loc_140005054
0x14000512f  mov     r8b, [rdx+0Ch]
0x140005133  mov     cl, [rdi+0A4h]
0x140005139  test    r8b, r8b
0x14000513c  setnz   al
0x14000513f  mov     [rdi+0A4h], al
0x140005145  cmp     cl, al
0x140005147  jnz     short loc_140005185
0x140005149  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x140005150  jz      loc_140005228
0x140005156  mov     rcx, cs:WPP_GLOBAL_Control
0x14000515d  lea     rax, WPP_1ea4bda7f8b23cafb6f0c7d9f6a1b177_Traceguids
0x140005164  mov     r9d, 0B6h
0x14000516a  mov     [rsp+78h+var_58], rax
0x14000516f  mov     r8d, 2
0x140005175  mov     dl, 4
0x140005177  mov     rcx, [rcx+40h]
0x14000517b  call    WPP_RECORDER_SF_
0x140005180  jmp     loc_140005228
0x140005185  mov     rax, cs:WdfFunctions_01015
0x14000518c  mov     rdx, r14
0x14000518f  mov     rcx, cs:WdfDriverGlobals
0x140005196  mov     rax, [rax+4E8h]
0x14000519d  test    r8b, r8b
0x1400051a0  jz      short loc_1400051DE
0x1400051a2  call    _guard_dispatch_icall
0x1400051a7  mov     rcx, cs:WdfFunctions_01015
0x1400051ae  mov     rdx, rax
0x1400051b1  mov     r9d, 0F0Dh
0x1400051b7  xor     r8d, r8d
0x1400051ba  mov     r10, [rcx+0DB8h]
0x1400051c1  lea     rcx, aOnecoreDrivers_3; "onecore\\drivers\\wdm\\usb\\driver\\win"...
0x1400051c8  mov     [rsp+78h+var_58], rcx
0x1400051cd  mov     rax, r10
0x1400051d0  mov     rcx, cs:WdfDriverGlobals
0x1400051d7  call    _guard_dispatch_icall
0x1400051dc  jmp     short loc_140005228
0x1400051de  call    _guard_dispatch_icall
0x1400051e3  mov     rcx, cs:WdfFunctions_01015
0x1400051ea  mov     rdx, rax
0x1400051ed  xor     r9d, r9d
0x1400051f0  xor     r8d, r8d
0x1400051f3  mov     r10, [rcx+0DB0h]
0x1400051fa  lea     rcx, aOnecoreDrivers_3; "onecore\\drivers\\wdm\\usb\\driver\\win"...
0x140005201  mov     [rsp+78h+var_50], rcx
0x140005206  mov     rax, r10
0x140005209  mov     rcx, cs:WdfDriverGlobals
0x140005210  mov     dword ptr [rsp+78h+var_58], 0F1Ah
0x140005218  call    _guard_dispatch_icall
0x14000521d  cmp     eax, 103h
0x140005222  mov     ebx, eax
0x140005224  cmovz   ebx, r13d
0x140005228  mov     dl, r15b; NewIrql
0x14000522b  lea     rcx, [rdi+28h]; SpinLock
0x14000522f  call    cs:__imp_KeReleaseSpinLock
0x140005236  nop     dword ptr [rax+rax+00h]
0x14000523b  lea     rbp, WPP_1ea4bda7f8b23cafb6f0c7d9f6a1b177_Traceguids
0x140005242  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x140005249  jz      short loc_140005279
0x14000524b  mov     rcx, cs:WPP_GLOBAL_Control
0x140005252  cmp     [rcx+48h], r13w
0x140005257  jz      short loc_140005279
0x140005259  mov     rcx, [rcx+40h]
0x14000525d  mov     r9d, 0BAh
0x140005263  mov     dword ptr [rsp+78h+var_50], ebx
0x140005267  mov     r8d, 1
0x14000526d  mov     dl, 5
0x14000526f  mov     [rsp+78h+var_58], rbp
0x140005274  call    WPP_RECORDER_SF_d
0x140005279  mov     eax, ebx
0x14000527b  mov     rbx, [rsp+78h+arg_8]
0x140005283  add     rsp, 40h
0x140005287  pop     r15
0x140005289  pop     r14
0x14000528b  pop     r13
0x14000528d  pop     r12
0x14000528f  pop     rdi
0x140005290  pop     rsi
0x140005291  pop     rbp
0x140005292  retn
```
