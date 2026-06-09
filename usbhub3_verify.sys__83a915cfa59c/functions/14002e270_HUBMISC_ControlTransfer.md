# HUBMISC_ControlTransfer

- ea: `0x14002e270`
- end: `0x14002e4a2`
- name: `HUBMISC_ControlTransfer`
- size: `562`
- prototype: ``
- caller_count: `48`
- callee_count: `6`
- tags: ``

## callers

- `0x140002910`
- `0x140002e30`
- `0x1400035a0`
- `0x1400046c0`
- `0x14000497c`
- `0x140004d68`
- `0x140004f74`
- `0x1400050b4`
- `0x140005998`
- `0x140005f18`
- `0x140006038`
- `0x140006158`
- `0x140006294`
- `0x140008df0`
- `0x140009ae0`
- `0x140009c90`
- `0x14000dec8`
- `0x140012630`
- `0x140013100`
- `0x140013510`
- `0x1400136f0`
- `0x140013850`
- `0x140013980`
- `0x140013fb0`
- `0x140014100`
- `0x14001f5d0`
- `0x140020f00`
- `0x1400217c0`
- `0x1400218f0`
- `0x140021ab0`
- `0x140021b90`
- `0x140021c70`
- `0x140022850`
- `0x1400238b0`
- `0x140023980`
- `0x140023b00`
- `0x1400243c0`
- `0x140029b1c`
- `0x14002a874`
- `0x14002ad20`
- `0x14002b128`
- `0x14002b618`
- `0x14002b6fc`
- `0x14002b810`
- `0x14002b8d8`
- `0x14002b9b8`
- `0x140041328`
- `0x140041780`

## callees

- `0x1400024b8`
- `0x1400067ac`
- `0x14002e270`
- `0x140045530`
- `0x140045570`
- `0x140045940`

## pseudocode

```c
__int64 __fastcall HUBMISC_ControlTransfer(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4,
        __int64 a5,
        __int64 a6,
        int a7,
        char a8,
        char a9)
{
  _QWORD *v9; // rbx
  int v10; // esi
  int v14; // ecx
  __int64 v15; // rdx
  int v16; // edx
  __int64 v17; // rdx
  int v18; // ebx
  __int64 v19; // rax
  int v20; // edx
  int v22; // [rsp+28h] [rbp-71h]
  __int64 v23; // [rsp+30h] [rbp-69h] BYREF
  int v24; // [rsp+38h] [rbp-61h]
  __int64 v25; // [rsp+3Ch] [rbp-5Dh]
  int v26; // [rsp+44h] [rbp-55h]
  _QWORD v27[9]; // [rsp+48h] [rbp-51h] BYREF

  v9 = a4 + 3;
  v10 = 0;
  a4[4] = a2;
  *((_DWORD *)a4 + 6) = 3276936;
  v14 = 8;
  *((_DWORD *)a4 + 14) = 8;
  if ( a8 )
  {
    v14 = 10;
    *((_DWORD *)a4 + 14) = 10;
  }
  if ( *((char *)a4 + 152) < 0 )
  {
    v14 |= 1u;
    *((_DWORD *)a4 + 14) = v14;
  }
  if ( a9 )
    *((_DWORD *)a4 + 14) = v14 | 0x10;
  *((_DWORD *)a4 + 15) = a7;
  a4[8] = a6;
  a4[9] = 0;
  *((_DWORD *)a4 + 20) = 5000;
  *((_DWORD *)a4 + 10) = *((_DWORD *)a4 + 40);
  memset(v27, 0, sizeof(v27));
  v15 = *a4;
  LOBYTE(v27[0]) = 15;
  LODWORD(v27[3]) = 2228227;
  v27[1] = v9;
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD *))(WdfFunctions_01015 + 2016))(
    WdfDriverGlobals,
    v15,
    v27);
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, __int64, __int64))(WdfFunctions_01015 + 2080))(
    WdfDriverGlobals,
    *a4,
    a5,
    a3);
  if ( !(*(unsigned __int8 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, _QWORD, _QWORD))(WdfFunctions_01015 + 2024))(
          WdfDriverGlobals,
          *a4,
          *(_QWORD *)(a1 + 32),
          0) )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v16) = 2;
      WPP_RECORDER_SF_(*(_QWORD *)(a1 + 2536), v16, 3, 58, (__int64)WPP_dde998bf8bb3310d95d4227a99ba80b7_Traceguids);
    }
    v10 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01015 + 2032))(WdfDriverGlobals, *a4);
    if ( v10 < 0 )
    {
      v17 = *a4;
      v25 = 0;
      v26 = 0;
      v23 = 24;
      v24 = 0;
      v18 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1992))(
              WdfDriverGlobals,
              v17,
              &v23);
      if ( v18 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v19 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, WDFDRIVER__ *, __int64 *))(WdfFunctions_01015 + 1616))(
                WdfDriverGlobals,
                WdfDriverGlobals->Driver,
                off_14006B2C0);
        v22 = v18;
        LOBYTE(v20) = 2;
        WPP_RECORDER_SF_d(
          *(_QWORD *)(v19 + 64),
          v20,
          2,
          59,
          (__int64)WPP_dde998bf8bb3310d95d4227a99ba80b7_Traceguids,
          v22);
      }
    }
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x14002e270  push    rbp
0x14002e272  push    rbx
0x14002e273  push    rsi
0x14002e274  push    rdi
0x14002e275  push    r12
0x14002e277  push    r14
0x14002e279  push    r15
0x14002e27b  lea     rbp, [rsp-7]
0x14002e280  sub     rsp, 0A0h
0x14002e287  mov     rax, cs:__security_cookie
0x14002e28e  xor     rax, rsp
0x14002e291  mov     [rbp+37h+var_40], rax
0x14002e295  mov     r12, [rbp+37h+arg_20]
0x14002e299  lea     rbx, [r9+18h]
0x14002e29d  xor     esi, esi
0x14002e29f  mov     [rbx+8], rdx
0x14002e2a3  mov     r14, rcx
0x14002e2a6  mov     rdi, r9
0x14002e2a9  mov     r15, r8
0x14002e2ac  mov     dword ptr [rbx], 320088h
0x14002e2b2  lea     ecx, [rsi+8]
0x14002e2b5  mov     [rbx+20h], ecx
0x14002e2b8  cmp     [rbp+37h+arg_38], sil
0x14002e2bc  jz      short loc_14002E2C4
0x14002e2be  lea     ecx, [rsi+0Ah]
0x14002e2c1  mov     [rbx+20h], ecx
0x14002e2c4  mov     al, [r9+98h]
0x14002e2cb  test    al, al
0x14002e2cd  jns     short loc_14002E2D5
0x14002e2cf  or      ecx, 1
0x14002e2d2  mov     [rbx+20h], ecx
0x14002e2d5  cmp     [rbp+37h+arg_40], sil
0x14002e2dc  jz      short loc_14002E2E4
0x14002e2de  or      ecx, 10h
0x14002e2e1  mov     [rbx+20h], ecx
0x14002e2e4  mov     eax, [rbp+37h+arg_30]
0x14002e2e7  lea     rcx, [rbp+37h+var_88]; void *
0x14002e2eb  mov     [rbx+24h], eax
0x14002e2ee  xor     edx, edx; Val
0x14002e2f0  mov     rax, [rbp+37h+arg_28]
0x14002e2f4  mov     [rbx+28h], rax
0x14002e2f8  mov     [rbx+30h], rsi
0x14002e2fc  mov     dword ptr [rbx+38h], 1388h
0x14002e303  lea     r8d, [rdx+48h]; Size
0x14002e307  mov     eax, [r9+0A0h]
0x14002e30e  mov     [rbx+10h], eax
0x14002e311  call    memset
0x14002e316  mov     rax, cs:WdfFunctions_01015
0x14002e31d  lea     r8, [rbp+37h+var_88]
0x14002e321  mov     rdx, [rdi]
0x14002e324  mov     rcx, cs:WdfDriverGlobals
0x14002e32b  mov     [rbp+37h+var_88], 0Fh
0x14002e32f  mov     [rbp+37h+var_70], 220003h
0x14002e336  mov     [rbp+37h+var_80], rbx
0x14002e33a  mov     rax, [rax+7E0h]
0x14002e341  call    _guard_dispatch_icall
0x14002e346  mov     rax, cs:WdfFunctions_01015
0x14002e34d  mov     r9, r15
0x14002e350  mov     rdx, [rdi]
0x14002e353  mov     r8, r12
0x14002e356  mov     rcx, cs:WdfDriverGlobals
0x14002e35d  mov     rax, [rax+820h]
0x14002e364  call    _guard_dispatch_icall
0x14002e369  mov     rax, cs:WdfFunctions_01015
0x14002e370  xor     r9d, r9d
0x14002e373  mov     r8, [r14+20h]
0x14002e377  mov     rdx, [rdi]
0x14002e37a  mov     rcx, cs:WdfDriverGlobals
0x14002e381  mov     rax, [rax+7E8h]
0x14002e388  call    _guard_dispatch_icall
0x14002e38d  test    al, al
0x14002e38f  jnz     loc_14002E481
0x14002e395  lea     r15, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14002e39c  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14002e3a3  lea     r12, WPP_dde998bf8bb3310d95d4227a99ba80b7_Traceguids
0x14002e3aa  jz      short loc_14002E3C9
0x14002e3ac  mov     rcx, [r14+9E8h]
0x14002e3b3  mov     r9d, 3Ah ; ':'
0x14002e3b9  mov     dl, 2
0x14002e3bb  mov     [rsp+0D0h+var_B0], r12
0x14002e3c0  lea     r8d, [r9-37h]
0x14002e3c4  call    WPP_RECORDER_SF_
0x14002e3c9  mov     rax, cs:WdfFunctions_01015
0x14002e3d0  mov     rdx, [rdi]
0x14002e3d3  mov     rcx, cs:WdfDriverGlobals
0x14002e3da  mov     rax, [rax+7F0h]
0x14002e3e1  call    _guard_dispatch_icall
0x14002e3e6  mov     esi, eax
0x14002e3e8  test    eax, eax
0x14002e3ea  jns     loc_14002E481
0x14002e3f0  mov     rcx, cs:WdfFunctions_01015
0x14002e3f7  lea     r8, [rbp+37h+var_A0]
0x14002e3fb  mov     rdx, [rdi]
0x14002e3fe  mov     [rbp+37h+var_94], 0
0x14002e406  mov     [rbp+37h+var_8C], 0
0x14002e40d  mov     [rbp+37h+var_A0], 18h
0x14002e415  mov     [rbp+37h+var_98], 0
0x14002e41c  mov     rax, [rcx+7C8h]
0x14002e423  mov     rcx, cs:WdfDriverGlobals
0x14002e42a  call    _guard_dispatch_icall
0x14002e42f  mov     ebx, eax
0x14002e431  test    eax, eax
0x14002e433  jns     short loc_14002E481
0x14002e435  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x14002e43c  jz      short loc_14002E481
0x14002e43e  mov     rcx, cs:WdfFunctions_01015
0x14002e445  mov     r8, cs:off_14006B2C0
0x14002e44c  mov     rax, [rcx+650h]
0x14002e453  mov     rcx, cs:WdfDriverGlobals
0x14002e45a  mov     rdx, [rcx]
0x14002e45d  call    _guard_dispatch_icall
0x14002e462  mov     r9d, 3Bh ; ';'
0x14002e468  mov     [rsp+0D0h+var_A8], ebx
0x14002e46c  mov     [rsp+0D0h+var_B0], r12
0x14002e471  mov     rcx, [rax+40h]
0x14002e475  lea     r8d, [r9-39h]
0x14002e479  mov     dl, r8b
0x14002e47c  call    WPP_RECORDER_SF_d
0x14002e481  mov     eax, esi
0x14002e483  mov     rcx, [rbp+37h+var_40]
0x14002e487  xor     rcx, rsp; StackCookie
0x14002e48a  call    __security_check_cookie
0x14002e48f  add     rsp, 0A0h
0x14002e496  pop     r15
0x14002e498  pop     r14
0x14002e49a  pop     r12
0x14002e49c  pop     rdi
0x14002e49d  pop     rsi
0x14002e49e  pop     rbx
0x14002e49f  pop     rbp
0x14002e4a0  retn
```
