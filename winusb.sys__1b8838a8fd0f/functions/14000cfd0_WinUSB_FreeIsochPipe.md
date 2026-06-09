# WinUSB_FreeIsochPipe

- ea: `0x14000cfd0`
- end: `0x14000d265`
- name: `WinUSB_FreeIsochPipe`
- size: `661`
- prototype: `__int128 *__fastcall(_QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x140006acc`
- `0x14000d3ac`

## callees

- `0x140001020`
- `0x1400013d0`
- `0x14000cfd0`
- `0x140010700`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000d0a6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000d0a6`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000d17b`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000d17b`

## pseudocode

```c
__int128 *__fastcall WinUSB_FreeIsochPipe(_QWORD *a1)
{
  __int64 *v2; // rdx
  KSPIN_LOCK *v3; // r14
  _QWORD *v4; // rsi
  KIRQL v5; // r15
  _QWORD *v6; // rcx
  _QWORD *v7; // rdi
  __int64 v8; // rbx
  __int64 v9; // rax
  _QWORD *v10; // rax
  __int64 v11; // rcx
  _QWORD *v12; // rdx
  __int64 v13; // rdx
  _QWORD *v14; // rax
  int v15; // edx
  __int64 v16; // rbx
  __int128 *result; // rax
  __int64 v18; // rax
  __int64 v19; // r8
  _QWORD *v20; // rdx
  __int64 v21; // rdi
  __int128 v22; // [rsp+30h] [rbp-18h] BYREF

  v22 = 0;
  v2 = WPP_0eec754a616436344c523d073d150c9e_Traceguids;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(v2) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)v2,
      1,
      19,
      (__int64)WPP_0eec754a616436344c523d073d150c9e_Traceguids);
    v2 = WPP_0eec754a616436344c523d073d150c9e_Traceguids;
  }
  *((_QWORD *)&v22 + 1) = &v22;
  *(_QWORD *)&v22 = &v22;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v2) = 4;
    WPP_RECORDER_SF_q(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)v2,
      3,
      20,
      (__int64)WPP_0eec754a616436344c523d073d150c9e_Traceguids,
      (char)a1);
  }
  if ( a1[24] )
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS))(WdfFunctions_01015 + 1664))(WdfDriverGlobals);
  v3 = a1 + 27;
  v4 = a1 + 22;
  v5 = KeAcquireSpinLockRaiseToDpc(a1 + 27);
  v6 = (_QWORD *)a1[22];
  v7 = v6 - 6;
  v8 = *v6 - 48LL;
  if ( v4 != v6 )
  {
    do
    {
      v9 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD *))(WdfFunctions_01015 + 1632))(WdfDriverGlobals, v7);
      if ( !(*(unsigned int (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 2048))(
              WdfDriverGlobals,
              v9) )
      {
        v10 = v7 + 6;
        v11 = v7[6];
        if ( *(_QWORD **)(v11 + 8) != v7 + 6
          || (v12 = (_QWORD *)v7[7], (_QWORD *)*v12 != v10)
          || (*v12 = v11, *(_QWORD *)(v11 + 8) = v12, v13 = v22, *(__int128 **)(v22 + 8) != &v22) )
        {
LABEL_24:
          __fastfail(3u);
        }
        *v10 = v22;
        v7[7] = &v22;
        *(_QWORD *)(v13 + 8) = v10;
        *(_QWORD *)&v22 = v7 + 6;
      }
      v14 = (_QWORD *)(v8 + 48);
      v7 = (_QWORD *)v8;
      v8 = *(_QWORD *)(v8 + 48) - 48LL;
    }
    while ( v4 != v14 );
  }
  KeReleaseSpinLock(v3, v5);
  v16 = v22 - 48;
  result = (__int128 *)v22;
  while ( 1 )
  {
    v21 = *(_QWORD *)result - 48LL;
    if ( &v22 == result )
      break;
    v18 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 1632))(WdfDriverGlobals, v16);
    v19 = *(_QWORD *)(v16 + 48);
    if ( *(_QWORD *)(v19 + 8) != v16 + 48 )
      goto LABEL_24;
    v20 = *(_QWORD **)(v16 + 56);
    if ( *v20 != v16 + 48 )
      goto LABEL_24;
    *v20 = v19;
    *(_QWORD *)(v19 + 8) = v20;
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64))(WdfFunctions_01015 + 2104))(
      WdfDriverGlobals,
      v18,
      3221225760LL);
    result = (__int128 *)(v21 + 48);
    v16 = v21;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(v15) = 5;
      return (__int128 *)WPP_RECORDER_SF_(
                           WPP_GLOBAL_Control->DeviceExtension,
                           v15,
                           1,
                           21,
                           (__int64)WPP_0eec754a616436344c523d073d150c9e_Traceguids);
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000cfd0  push    rbp
0x14000cfd2  push    rbx
0x14000cfd3  push    rsi
0x14000cfd4  push    rdi
0x14000cfd5  push    r12
0x14000cfd7  push    r13
0x14000cfd9  push    r14
0x14000cfdb  push    r15
0x14000cfdd  mov     rbp, rsp
0x14000cfe0  sub     rsp, 48h
0x14000cfe4  xorps   xmm0, xmm0
0x14000cfe7  mov     rbx, rcx
0x14000cfea  movups  [rbp+var_18], xmm0
0x14000cfee  lea     r13, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000cff5  xor     r12d, r12d
0x14000cff8  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14000cfff  lea     rdx, WPP_0eec754a616436344c523d073d150c9e_Traceguids
0x14000d006  jz      short loc_14000D037
0x14000d008  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d00f  cmp     [rcx+48h], r12w
0x14000d014  jz      short loc_14000D037
0x14000d016  mov     rcx, [rcx+40h]
0x14000d01a  lea     r9d, [r12+13h]
0x14000d01f  mov     [rsp+48h+var_28], rdx
0x14000d024  lea     r8d, [r12+1]
0x14000d029  mov     dl, 5
0x14000d02b  call    WPP_RECORDER_SF_
0x14000d030  lea     rdx, WPP_0eec754a616436344c523d073d150c9e_Traceguids
0x14000d037  lea     rax, [rbp+var_18]
0x14000d03b  mov     qword ptr [rbp+var_18+8], rax
0x14000d03f  lea     rax, [rbp+var_18]
0x14000d043  mov     qword ptr [rbp+var_18], rax
0x14000d047  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x14000d04e  jz      short loc_14000D076
0x14000d050  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d057  mov     r9d, 14h
0x14000d05d  mov     [rsp+48h+var_20], rbx
0x14000d062  mov     [rsp+48h+var_28], rdx
0x14000d067  mov     dl, 4
0x14000d069  mov     rcx, [rcx+40h]
0x14000d06d  lea     r8d, [r9-11h]
0x14000d071  call    WPP_RECORDER_SF_q
0x14000d076  mov     rdx, [rbx+0C0h]
0x14000d07d  test    rdx, rdx
0x14000d080  jz      short loc_14000D09C
0x14000d082  mov     rax, cs:WdfFunctions_01015
0x14000d089  mov     rcx, cs:WdfDriverGlobals
0x14000d090  mov     rax, [rax+680h]
0x14000d097  call    _guard_dispatch_icall
0x14000d09c  lea     r14, [rbx+0D8h]
0x14000d0a3  mov     rcx, r14; SpinLock
0x14000d0a6  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000d0ad  nop     dword ptr [rax+rax+00h]
0x14000d0b2  lea     rsi, [rbx+0B0h]
0x14000d0b9  mov     r15b, al
0x14000d0bc  mov     rcx, [rsi]
0x14000d0bf  mov     rbx, [rcx]
0x14000d0c2  lea     rdi, [rcx-30h]
0x14000d0c6  sub     rbx, 30h ; '0'
0x14000d0ca  cmp     rsi, rcx
0x14000d0cd  jz      loc_14000D175
0x14000d0d3  mov     rcx, cs:WdfFunctions_01015
0x14000d0da  mov     rdx, rdi
0x14000d0dd  mov     rax, [rcx+660h]
0x14000d0e4  mov     rcx, cs:WdfDriverGlobals
0x14000d0eb  call    _guard_dispatch_icall
0x14000d0f0  mov     rcx, cs:WdfFunctions_01015
0x14000d0f7  mov     rdx, rax
0x14000d0fa  mov     r8, [rcx+800h]
0x14000d101  mov     rcx, cs:WdfDriverGlobals
0x14000d108  mov     rax, r8
0x14000d10b  call    _guard_dispatch_icall
0x14000d110  test    eax, eax
0x14000d112  jnz     short loc_14000D15E
0x14000d114  lea     rax, [rdi+30h]
0x14000d118  mov     rcx, [rax]
0x14000d11b  cmp     [rcx+8], rax
0x14000d11f  jnz     loc_14000D25E
0x14000d125  mov     rdx, [rdi+38h]
0x14000d129  cmp     [rdx], rax
0x14000d12c  jnz     loc_14000D25E
0x14000d132  mov     [rdx], rcx
0x14000d135  mov     [rcx+8], rdx
0x14000d139  lea     rcx, [rbp+var_18]
0x14000d13d  mov     rdx, qword ptr [rbp+var_18]
0x14000d141  cmp     [rdx+8], rcx
0x14000d145  jnz     loc_14000D25E
0x14000d14b  mov     [rax], rdx
0x14000d14e  lea     rcx, [rbp+var_18]
0x14000d152  mov     [rax+8], rcx
0x14000d156  mov     [rdx+8], rax
0x14000d15a  mov     qword ptr [rbp+var_18], rax
0x14000d15e  lea     rax, [rbx+30h]
0x14000d162  mov     rdi, rbx
0x14000d165  mov     rbx, [rax]
0x14000d168  sub     rbx, 30h ; '0'
0x14000d16c  cmp     rsi, rax
0x14000d16f  jnz     loc_14000D0D3
0x14000d175  mov     dl, r15b; NewIrql
0x14000d178  mov     rcx, r14; SpinLock
0x14000d17b  call    cs:__imp_KeReleaseSpinLock
0x14000d182  nop     dword ptr [rax+rax+00h]
0x14000d187  mov     rbx, qword ptr [rbp+var_18]
0x14000d18b  add     rbx, 0FFFFFFFFFFFFFFD0h
0x14000d18f  lea     rax, [rbx+30h]
0x14000d193  jmp     short loc_14000D204
0x14000d195  mov     rax, cs:WdfFunctions_01015
0x14000d19c  mov     rdx, rbx
0x14000d19f  mov     rcx, cs:WdfDriverGlobals
0x14000d1a6  mov     rax, [rax+660h]
0x14000d1ad  call    _guard_dispatch_icall
0x14000d1b2  lea     rcx, [rbx+30h]
0x14000d1b6  mov     r9, rax
0x14000d1b9  mov     r8, [rcx]
0x14000d1bc  cmp     [r8+8], rcx
0x14000d1c0  jnz     loc_14000D25E
0x14000d1c6  mov     rdx, [rbx+38h]
0x14000d1ca  cmp     [rdx], rcx
0x14000d1cd  jnz     loc_14000D25E
0x14000d1d3  mov     [rdx], r8
0x14000d1d6  mov     [r8+8], rdx
0x14000d1da  mov     r8d, 0C0000120h
0x14000d1e0  mov     rcx, cs:WdfFunctions_01015
0x14000d1e7  mov     rdx, r9
0x14000d1ea  mov     rax, [rcx+838h]
0x14000d1f1  mov     rcx, cs:WdfDriverGlobals
0x14000d1f8  call    _guard_dispatch_icall
0x14000d1fd  lea     rax, [rdi+30h]
0x14000d201  mov     rbx, rdi
0x14000d204  mov     rdi, [rax]
0x14000d207  lea     rcx, [rbp+var_18]
0x14000d20b  sub     rdi, 30h ; '0'
0x14000d20f  cmp     rcx, rax
0x14000d212  jnz     short loc_14000D195
0x14000d214  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x14000d21b  jz      short loc_14000D24C
0x14000d21d  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d224  cmp     [rcx+48h], r12w
0x14000d229  jz      short loc_14000D24C
0x14000d22b  mov     rcx, [rcx+40h]
0x14000d22f  lea     rax, WPP_0eec754a616436344c523d073d150c9e_Traceguids
0x14000d236  mov     r9d, 15h
0x14000d23c  mov     [rsp+48h+var_28], rax
0x14000d241  mov     dl, 5
0x14000d243  lea     r8d, [r9-14h]
0x14000d247  call    WPP_RECORDER_SF_
0x14000d24c  add     rsp, 48h
0x14000d250  pop     r15
0x14000d252  pop     r14
0x14000d254  pop     r13
0x14000d256  pop     r12
0x14000d258  pop     rdi
0x14000d259  pop     rsi
0x14000d25a  pop     rbx
0x14000d25b  pop     rbp
0x14000d25c  retn
0x14000d25e  mov     ecx, 3
0x14000d263  int     29h; Win8: RtlFailFast(ecx)
```
