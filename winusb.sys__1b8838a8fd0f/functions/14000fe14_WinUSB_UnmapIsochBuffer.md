# WinUSB_UnmapIsochBuffer

- ea: `0x14000fe14`
- end: `0x14000fff4`
- name: `WinUSB_UnmapIsochBuffer`
- size: `480`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x14000c500`
- `0x14000da50`
- `0x14000fbe8`

## callees

- `0x140001020`
- `0x1400013d0`
- `0x1400015d8`
- `0x14000fe14`
- `0x140010700`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000fe6e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000fe6e`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000fee3`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000ff8d`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000fee3`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000ff8d`
- `ntoskrnl!IoFreeMdl` at `0x14000ffa6`
- `ntoskrnl!IoFreeMdl` at `0x14000ffa6`

## pseudocode

```c
void __fastcall WinUSB_UnmapIsochBuffer(_QWORD *a1)
{
  KIRQL v2; // bl
  __int64 v3; // rdx
  __int64 v4; // rbx
  struct _MDL *v5; // rcx
  __int64 v6; // [rsp+30h] [rbp-48h]

  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    WPP_RECORDER_SF_(
      (__int64)WPP_GLOBAL_Control->DeviceExtension,
      5u,
      1u,
      0x2Bu,
      (__int64)WPP_0eec754a616436344c523d073d150c9e_Traceguids);
  v2 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(*a1 + 216LL));
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v3 = a1[4];
    v6 = *(_QWORD *)(v3 + 16);
    LOBYTE(v3) = 4;
    WPP_RECORDER_SF_qq(
      WPP_GLOBAL_Control->DeviceExtension,
      v3,
      3,
      44,
      (__int64)WPP_0eec754a616436344c523d073d150c9e_Traceguids,
      a1[4],
      v6);
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1[4] + 44LL), 0xFFFFFFFF) == 1
    && *(_BYTE *)(a1[4] + 40LL) == 1 )
  {
    KeReleaseSpinLock((PKSPIN_LOCK)(*a1 + 216LL), v2);
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_q(
        (__int64)WPP_GLOBAL_Control->DeviceExtension,
        4u,
        3u,
        0x2Du,
        (__int64)WPP_0eec754a616436344c523d073d150c9e_Traceguids,
        a1[4]);
    v4 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01015 + 1632))(WdfDriverGlobals, a1[4]);
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 2048))(WdfDriverGlobals, v4);
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64))(WdfFunctions_01015 + 2104))(
      WdfDriverGlobals,
      v4,
      3221225760LL);
  }
  else
  {
    KeReleaseSpinLock((PKSPIN_LOCK)(*a1 + 216LL), v2);
  }
  v5 = (struct _MDL *)a1[2];
  a1[4] = 0;
  if ( v5 )
    IoFreeMdl(v5);
  a1[2] = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
      WPP_RECORDER_SF_(
        (__int64)WPP_GLOBAL_Control->DeviceExtension,
        5u,
        1u,
        0x2Eu,
        (__int64)WPP_0eec754a616436344c523d073d150c9e_Traceguids);
  }
}

```

## disassembly

```asm
0x14000fe14  push    rbx
0x14000fe16  push    rbp
0x14000fe17  push    rsi
0x14000fe18  push    rdi
0x14000fe19  push    r12
0x14000fe1b  push    r14
0x14000fe1d  sub     rsp, 48h
0x14000fe21  mov     rdi, rcx
0x14000fe24  lea     rbp, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000fe2b  xor     esi, esi
0x14000fe2d  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14000fe34  lea     r14, WPP_0eec754a616436344c523d073d150c9e_Traceguids
0x14000fe3b  jz      short loc_14000FE62
0x14000fe3d  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fe44  cmp     [rcx+48h], si
0x14000fe48  jz      short loc_14000FE62
0x14000fe4a  mov     rcx, [rcx+40h]
0x14000fe4e  lea     r9d, [rsi+2Bh]
0x14000fe52  lea     r8d, [rsi+1]
0x14000fe56  mov     [rsp+78h+var_58], r14
0x14000fe5b  mov     dl, 5
0x14000fe5d  call    WPP_RECORDER_SF_
0x14000fe62  mov     rcx, [rdi]
0x14000fe65  mov     r12d, 0D8h
0x14000fe6b  add     rcx, r12; SpinLock
0x14000fe6e  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000fe75  nop     dword ptr [rax+rax+00h]
0x14000fe7a  mov     bl, al
0x14000fe7c  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x14000fe83  jz      short loc_14000FEB8
0x14000fe85  mov     rdx, [rdi+20h]
0x14000fe89  mov     r9d, 2Ch ; ','
0x14000fe8f  mov     rcx, [rdx+10h]
0x14000fe93  lea     r8d, [r9-29h]
0x14000fe97  mov     [rsp+78h+var_48], rcx
0x14000fe9c  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fea3  mov     [rsp+78h+var_50], rdx
0x14000fea8  mov     dl, 4
0x14000feaa  mov     [rsp+78h+var_58], r14
0x14000feaf  mov     rcx, [rcx+40h]
0x14000feb3  call    WPP_RECORDER_SF_qq
0x14000feb8  mov     rcx, [rdi+20h]
0x14000febc  or      eax, 0FFFFFFFFh
0x14000febf  lock xadd [rcx+2Ch], eax
0x14000fec4  cmp     eax, 1
0x14000fec7  jnz     loc_14000FF85
0x14000fecd  mov     rax, [rdi+20h]
0x14000fed1  cmp     byte ptr [rax+28h], 1
0x14000fed5  jnz     loc_14000FF85
0x14000fedb  mov     rcx, [rdi]
0x14000fede  mov     dl, bl; NewIrql
0x14000fee0  add     rcx, r12; SpinLock
0x14000fee3  call    cs:__imp_KeReleaseSpinLock
0x14000feea  nop     dword ptr [rax+rax+00h]
0x14000feef  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x14000fef6  jz      short loc_14000FF22
0x14000fef8  mov     rcx, cs:WPP_GLOBAL_Control
0x14000feff  mov     r9d, 2Dh ; '-'
0x14000ff05  mov     rax, [rdi+20h]
0x14000ff09  mov     dl, 4
0x14000ff0b  mov     [rsp+78h+var_50], rax
0x14000ff10  mov     [rsp+78h+var_58], r14
0x14000ff15  mov     rcx, [rcx+40h]
0x14000ff19  lea     r8d, [r9-2Ah]
0x14000ff1d  call    WPP_RECORDER_SF_q
0x14000ff22  mov     rax, cs:WdfFunctions_01015
0x14000ff29  mov     rdx, [rdi+20h]
0x14000ff2d  mov     rcx, cs:WdfDriverGlobals
0x14000ff34  mov     rax, [rax+660h]
0x14000ff3b  call    _guard_dispatch_icall
0x14000ff40  mov     rcx, cs:WdfFunctions_01015
0x14000ff47  mov     rbx, rax
0x14000ff4a  mov     rdx, rbx
0x14000ff4d  mov     rax, [rcx+800h]
0x14000ff54  mov     rcx, cs:WdfDriverGlobals
0x14000ff5b  call    _guard_dispatch_icall
0x14000ff60  mov     rcx, cs:WdfFunctions_01015
0x14000ff67  mov     r8d, 0C0000120h
0x14000ff6d  mov     rdx, rbx
0x14000ff70  mov     rax, [rcx+838h]
0x14000ff77  mov     rcx, cs:WdfDriverGlobals
0x14000ff7e  call    _guard_dispatch_icall
0x14000ff83  jmp     short loc_14000FF99
0x14000ff85  mov     rcx, [rdi]
0x14000ff88  mov     dl, bl; NewIrql
0x14000ff8a  add     rcx, r12; SpinLock
0x14000ff8d  call    cs:__imp_KeReleaseSpinLock
0x14000ff94  nop     dword ptr [rax+rax+00h]
0x14000ff99  mov     rcx, [rdi+10h]; Mdl
0x14000ff9d  mov     [rdi+20h], rsi
0x14000ffa1  test    rcx, rcx
0x14000ffa4  jz      short loc_14000FFB2
0x14000ffa6  call    cs:__imp_IoFreeMdl
0x14000ffad  nop     dword ptr [rax+rax+00h]
0x14000ffb2  mov     [rdi+10h], rsi
0x14000ffb6  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x14000ffbd  jz      short loc_14000FFE6
0x14000ffbf  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ffc6  cmp     [rcx+48h], si
0x14000ffca  jz      short loc_14000FFE6
0x14000ffcc  mov     rcx, [rcx+40h]
0x14000ffd0  mov     r9d, 2Eh ; '.'
0x14000ffd6  mov     dl, 5
0x14000ffd8  mov     [rsp+78h+var_58], r14
0x14000ffdd  lea     r8d, [r9-2Dh]
0x14000ffe1  call    WPP_RECORDER_SF_
0x14000ffe6  add     rsp, 48h
0x14000ffea  pop     r14
0x14000ffec  pop     r12
0x14000ffee  pop     rdi
0x14000ffef  pop     rsi
0x14000fff0  pop     rbp
0x14000fff1  pop     rbx
0x14000fff2  retn
```
