# WinUSB_SubmitWrite

- ea: `0x14000af00`
- end: `0x14000b3f6`
- name: `WinUSB_SubmitWrite`
- size: `1270`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140001020`
- `0x1400011c8`
- `0x14000193c`
- `0x14000264c`
- `0x140003990`
- `0x14000866c`
- `0x14000af00`
- `0x1400106c0`
- `0x140010700`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000b17f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000b17f`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000b195`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000b195`

## pseudocode

```c
__int64 __fastcall WinUSB_SubmitWrite(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v3; // r12d
  __int64 v4; // rdi
  __int64 v6; // rax
  __int64 v7; // r14
  __int64 v8; // rsi
  int v9; // eax
  int v10; // edx
  unsigned int v11; // ebx
  __int64 result; // rax
  int v13; // edx
  unsigned __int8 *v14; // r8
  char v15; // r15
  unsigned __int8 v16; // cl
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // rax
  __int64 v20; // r14
  unsigned int v21; // ecx
  __int64 v22; // r13
  KIRQL v23; // al
  __int64 v24; // r12
  int v25; // eax
  int v26; // edx
  int v27; // r9d
  __int64 v28; // r12
  int v29; // eax
  __int64 v30; // rsi
  char v31; // [rsp+28h] [rbp-49h]
  unsigned __int8 *v32; // [rsp+40h] [rbp-31h] BYREF
  __int64 v33; // [rsp+48h] [rbp-29h] BYREF
  __int64 v34; // [rsp+50h] [rbp-21h]
  __int64 v35; // [rsp+58h] [rbp-19h]
  __int64 v36; // [rsp+60h] [rbp-11h]
  __int128 v37; // [rsp+68h] [rbp-9h] BYREF
  __int128 v38; // [rsp+78h] [rbp+7h] BYREF

  v35 = a3;
  v3 = a3;
  v37 = 0;
  v32 = 0;
  v4 = a2;
  v33 = 0;
  v38 = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      1,
      30,
      (__int64)WPP_8fea48f46a3838764f6f48a247805a06_Traceguids);
  }
  v6 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 1256))(WdfDriverGlobals, a1);
  v7 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
         WdfDriverGlobals,
         v6,
         off_1400150F0);
  v36 = v7;
  v8 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
         WdfDriverGlobals,
         v4,
         off_140015040);
  v9 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64, unsigned __int8 **, _QWORD))(WdfFunctions_01015 + 2152))(
         WdfDriverGlobals,
         v4,
         2,
         &v32,
         0);
  v11 = v9;
  if ( v9 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v10) = 2;
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        v10,
        3,
        31,
        (__int64)WPP_8fea48f46a3838764f6f48a247805a06_Traceguids,
        v9);
    }
    goto LABEL_7;
  }
  v14 = v32;
  v15 = v32[1];
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v10) = 4;
    WPP_RECORDER_SF_dD(
      WPP_GLOBAL_Control->DeviceExtension,
      v10,
      5,
      32,
      (__int64)WPP_8fea48f46a3838764f6f48a247805a06_Traceguids,
      v15,
      *(_DWORD *)(v8 + 28));
    v14 = v32;
  }
  v16 = (v15 & 0xF) + 16;
  if ( v15 >= 0 )
    v16 = v15 & 0xF;
  v17 = v16;
  v18 = 35LL * *v14;
  v19 = *(_QWORD *)(v7 + 136);
  v34 = v17;
  v20 = *(_QWORD *)(v19 + 8 * (v17 + v18) + 24);
  _InterlockedExchange64((volatile __int64 *)(v20 + 80), v4);
  v21 = *(_DWORD *)(v20 + 112);
  if ( v3 <= v21 )
    v21 = v3;
  v22 = v21;
  v23 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v20 + 40));
  v24 = *(unsigned int *)(v20 + 24);
  KeReleaseSpinLock((PKSPIN_LOCK)(v20 + 40), v23);
  *((_QWORD *)&v38 + 1) = v22;
  *(_QWORD *)&v38 = 0;
  if ( (_DWORD)v22 )
  {
    v25 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 2144))(
            WdfDriverGlobals,
            v4,
            &v33);
    v11 = v25;
    if ( v25 < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v27 = 33;
LABEL_22:
        v31 = v25;
LABEL_36:
        LOBYTE(v26) = 2;
        WPP_RECORDER_SF_d(
          WPP_GLOBAL_Control->DeviceExtension,
          v26,
          3,
          v27,
          (__int64)WPP_8fea48f46a3838764f6f48a247805a06_Traceguids,
          v31);
        goto LABEL_37;
      }
      goto LABEL_37;
    }
  }
  v25 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, __int64, __int64, __int128 *))(WdfFunctions_01015 + 2776))(
          WdfDriverGlobals,
          *(_QWORD *)(v20 + 160),
          v4,
          v33,
          &v38);
  v11 = v25;
  if ( v25 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v27 = 34;
      goto LABEL_22;
    }
LABEL_37:
    _InterlockedExchange64((volatile __int64 *)(v20 + 80), 0);
LABEL_7:
    result = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD, _QWORD))(WdfFunctions_01015 + 2120))(
               WdfDriverGlobals,
               v4,
               v11,
               0);
    v13 = 0;
    goto LABEL_8;
  }
  v28 = -10000 * v24;
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _UNKNOWN **(__fastcall *)(__int64, __int64, __int64, unsigned int *), __int64))(WdfFunctions_01015 + 2080))(
    WdfDriverGlobals,
    v4,
    WinUSB_WritePipeCompletion,
    v8);
  *(_BYTE *)(v8 + 24) = v34;
  v29 = v35;
  *(_BYTE *)(v8 + 25) = *v32;
  *(_DWORD *)v8 = 0;
  *(_DWORD *)(v8 + 4) = v29;
  *(_DWORD *)(v8 + 8) = v22;
  *(_QWORD *)(v8 + 16) = v28;
  if ( v28 )
  {
    *(_QWORD *)&v37 = 0x100000010LL;
    *((_QWORD *)&v37 + 1) = v28;
    v25 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 2096))(WdfDriverGlobals, v4);
    v11 = v25;
    if ( v25 < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v27 = 35;
        goto LABEL_22;
      }
      goto LABEL_37;
    }
  }
  else
  {
    v37 = 0x10u;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v26) = 4;
    WPP_RECORDER_SF_dDd(
      WPP_GLOBAL_Control->DeviceExtension,
      v26,
      5,
      36,
      (__int64)WPP_8fea48f46a3838764f6f48a247805a06_Traceguids,
      v15,
      *(_DWORD *)(v8 + 28),
      v22);
  }
  v30 = v36;
  WinUSB_IncrementKeepAliveCount(v36, v4);
  result = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD, __int128 *))(WdfFunctions_01015 + 2024))(
             WdfDriverGlobals,
             v4,
             *(_QWORD *)(v20 + 160),
             &v37);
  v13 = 0;
  if ( !(_BYTE)result )
  {
    v11 = -1073741823;
    WinUSB_DecrementKeepAliveCount(v30, v4);
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v27 = 37;
      v31 = 1;
      goto LABEL_36;
    }
    goto LABEL_37;
  }
LABEL_8:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(v13) = 5;
      return WPP_RECORDER_SF_d(
               WPP_GLOBAL_Control->DeviceExtension,
               v13,
               1,
               38,
               (__int64)WPP_8fea48f46a3838764f6f48a247805a06_Traceguids,
               v11);
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000af00  mov     [rsp-8+arg_18], rbx
0x14000af05  push    rbp
0x14000af06  push    rsi
0x14000af07  push    rdi
0x14000af08  push    r12
0x14000af0a  push    r13
0x14000af0c  push    r14
0x14000af0e  push    r15
0x14000af10  lea     rbp, [rsp-1Fh]
0x14000af15  sub     rsp, 90h
0x14000af1c  mov     rax, cs:__security_cookie
0x14000af23  xor     rax, rsp
0x14000af26  mov     [rbp+4Fh+var_38], rax
0x14000af2a  xorps   xmm0, xmm0
0x14000af2d  mov     [rbp+4Fh+var_68], r8
0x14000af31  xor     eax, eax
0x14000af33  mov     r12, r8
0x14000af36  movups  [rbp+4Fh+var_58], xmm0
0x14000af3a  mov     [rbp+4Fh+var_80], rax
0x14000af3e  mov     rdi, rdx
0x14000af41  mov     [rbp+4Fh+var_78], rax
0x14000af45  mov     rbx, rcx
0x14000af48  movups  [rbp+4Fh+var_48], xmm0
0x14000af4c  lea     r13, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000af53  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14000af5a  lea     r15, WPP_8fea48f46a3838764f6f48a247805a06_Traceguids
0x14000af61  jz      short loc_14000AF88
0x14000af63  mov     rcx, cs:WPP_GLOBAL_Control
0x14000af6a  cmp     [rcx+48h], ax
0x14000af6e  jz      short loc_14000AF88
0x14000af70  mov     rcx, [rcx+40h]
0x14000af74  lea     r9d, [rax+1Eh]
0x14000af78  lea     r8d, [rax+1]
0x14000af7c  mov     [rsp+0C0h+var_A0], r15
0x14000af81  mov     dl, 5
0x14000af83  call    WPP_RECORDER_SF_
0x14000af88  mov     rax, cs:WdfFunctions_01015
0x14000af8f  mov     rdx, rbx
0x14000af92  mov     rcx, cs:WdfDriverGlobals
0x14000af99  mov     rax, [rax+4E8h]
0x14000afa0  call    _guard_dispatch_icall
0x14000afa5  mov     rcx, cs:WdfFunctions_01015
0x14000afac  mov     rdx, rax
0x14000afaf  mov     r8, cs:off_1400150F0
0x14000afb6  mov     r9, [rcx+650h]
0x14000afbd  mov     rcx, cs:WdfDriverGlobals
0x14000afc4  mov     rax, r9
0x14000afc7  call    _guard_dispatch_icall
0x14000afcc  mov     rcx, cs:WdfFunctions_01015
0x14000afd3  mov     r14, rax
0x14000afd6  mov     r8, cs:off_140015040
0x14000afdd  mov     rdx, rdi
0x14000afe0  mov     [rbp+4Fh+var_60], rax
0x14000afe4  mov     rax, [rcx+650h]
0x14000afeb  mov     rcx, cs:WdfDriverGlobals
0x14000aff2  call    _guard_dispatch_icall
0x14000aff7  mov     rcx, cs:WdfFunctions_01015
0x14000affe  lea     r9, [rbp+4Fh+var_80]
0x14000b002  mov     rsi, rax
0x14000b005  mov     [rsp+0C0h+var_A0], 0
0x14000b00e  mov     r8d, 2
0x14000b014  mov     rdx, rdi
0x14000b017  mov     rax, [rcx+868h]
0x14000b01e  mov     rcx, cs:WdfDriverGlobals
0x14000b025  call    _guard_dispatch_icall
0x14000b02a  mov     ebx, eax
0x14000b02c  test    eax, eax
0x14000b02e  jns     loc_14000B0EA
0x14000b034  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x14000b03b  jz      short loc_14000B062
0x14000b03d  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b044  mov     r9d, 1Fh
0x14000b04a  mov     dword ptr [rsp+0C0h+var_98], eax
0x14000b04e  mov     dl, 2
0x14000b050  mov     [rsp+0C0h+var_A0], r15
0x14000b055  mov     rcx, [rcx+40h]
0x14000b059  lea     r8d, [r9-1Ch]
0x14000b05d  call    WPP_RECORDER_SF_d
0x14000b062  lea     r12, WPP_RECORDER_INITIALIZED
0x14000b069  mov     rax, cs:WdfFunctions_01015
0x14000b070  xor     r9d, r9d
0x14000b073  mov     rcx, cs:WdfDriverGlobals
0x14000b07a  mov     r8d, ebx
0x14000b07d  mov     rdx, rdi
0x14000b080  mov     rax, [rax+848h]
0x14000b087  call    _guard_dispatch_icall
0x14000b08c  xor     edx, edx
0x14000b08e  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x14000b095  jz      short loc_14000B0C2
0x14000b097  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b09e  cmp     [rcx+48h], dx
0x14000b0a2  jz      short loc_14000B0C2
0x14000b0a4  mov     rcx, [rcx+40h]
0x14000b0a8  mov     r9d, 26h ; '&'
0x14000b0ae  mov     dword ptr [rsp+0C0h+var_98], ebx
0x14000b0b2  mov     dl, 5
0x14000b0b4  mov     [rsp+0C0h+var_A0], r15
0x14000b0b9  lea     r8d, [r9-25h]
0x14000b0bd  call    WPP_RECORDER_SF_d
0x14000b0c2  mov     rcx, [rbp+4Fh+var_38]
0x14000b0c6  xor     rcx, rsp; StackCookie
0x14000b0c9  call    __security_check_cookie
0x14000b0ce  mov     rbx, [rsp+0C0h+arg_18]
0x14000b0d6  add     rsp, 90h
0x14000b0dd  pop     r15
0x14000b0df  pop     r14
0x14000b0e1  pop     r13
0x14000b0e3  pop     r12
0x14000b0e5  pop     rdi
0x14000b0e6  pop     rsi
0x14000b0e7  pop     rbp
0x14000b0e8  retn
0x14000b0ea  mov     r8, [rbp+4Fh+var_80]
0x14000b0ee  movzx   r15d, byte ptr [r8+1]
0x14000b0f3  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x14000b0fa  jz      short loc_14000B134
0x14000b0fc  mov     eax, [rsi+1Ch]
0x14000b0ff  mov     r9d, 20h ; ' '
0x14000b105  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b10c  mov     dl, 4
0x14000b10e  mov     [rsp+0C0h+var_90], eax
0x14000b112  lea     rax, WPP_8fea48f46a3838764f6f48a247805a06_Traceguids
0x14000b119  mov     dword ptr [rsp+0C0h+var_98], r15d
0x14000b11e  lea     r8d, [r9-1Bh]
0x14000b122  mov     [rsp+0C0h+var_A0], rax
0x14000b127  mov     rcx, [rcx+40h]
0x14000b12b  call    WPP_RECORDER_SF_dD
0x14000b130  mov     r8, [rbp+4Fh+var_80]
0x14000b134  mov     al, r15b
0x14000b137  and     al, 0Fh
0x14000b139  movzx   edx, al
0x14000b13c  test    r15b, r15b
0x14000b13f  lea     eax, [rdx+10h]
0x14000b142  movzx   ecx, al
0x14000b145  movzx   eax, byte ptr [r8]
0x14000b149  cmovns  ecx, edx
0x14000b14c  movzx   edx, cl
0x14000b14f  imul    rcx, rax, 23h ; '#'
0x14000b153  mov     rax, [r14+88h]
0x14000b15a  add     rcx, rdx
0x14000b15d  mov     [rbp+4Fh+var_70], rdx
0x14000b161  mov     r14, [rax+rcx*8+18h]
0x14000b166  mov     rax, rdi
0x14000b169  xchg    rax, [r14+50h]
0x14000b16d  mov     ecx, [r14+70h]
0x14000b171  cmp     r12d, ecx
0x14000b174  cmovbe  ecx, r12d
0x14000b178  mov     r13d, ecx
0x14000b17b  lea     rcx, [r14+28h]; SpinLock
0x14000b17f  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000b186  nop     dword ptr [rax+rax+00h]
0x14000b18b  mov     r12d, [r14+18h]
0x14000b18f  lea     rcx, [r14+28h]; SpinLock
0x14000b193  mov     dl, al; NewIrql
0x14000b195  call    cs:__imp_KeReleaseSpinLock
0x14000b19c  nop     dword ptr [rax+rax+00h]
0x14000b1a1  xor     eax, eax
0x14000b1a3  mov     qword ptr [rbp+4Fh+var_48+8], r13
0x14000b1a7  mov     qword ptr [rbp+4Fh+var_48], rax
0x14000b1ab  test    r13d, r13d
0x14000b1ae  jz      short loc_14000B201
0x14000b1b0  mov     rax, cs:WdfFunctions_01015
0x14000b1b7  lea     r8, [rbp+4Fh+var_78]
0x14000b1bb  mov     rcx, cs:WdfDriverGlobals
0x14000b1c2  mov     rdx, rdi
0x14000b1c5  mov     rax, [rax+860h]
0x14000b1cc  call    _guard_dispatch_icall
0x14000b1d1  mov     ebx, eax
0x14000b1d3  test    eax, eax
0x14000b1d5  jns     short loc_14000B201
0x14000b1d7  lea     r12, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000b1de  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14000b1e5  lea     r15, WPP_8fea48f46a3838764f6f48a247805a06_Traceguids
0x14000b1ec  jz      loc_14000B3EB
0x14000b1f2  mov     r9d, 21h ; '!'
0x14000b1f8  mov     dword ptr [rsp+0C0h+var_98], eax
0x14000b1fc  jmp     loc_14000B3CE
0x14000b201  mov     rax, cs:WdfFunctions_01015
0x14000b208  lea     rcx, [rbp+4Fh+var_48]
0x14000b20c  mov     r9, [rbp+4Fh+var_78]
0x14000b210  mov     r8, rdi
0x14000b213  mov     rdx, [r14+0A0h]
0x14000b21a  mov     [rsp+0C0h+var_A0], rcx
0x14000b21f  mov     rax, [rax+0AD8h]
0x14000b226  mov     rcx, cs:WdfDriverGlobals
0x14000b22d  call    _guard_dispatch_icall
0x14000b232  mov     ebx, eax
0x14000b234  test    eax, eax
0x14000b236  jns     short loc_14000B25B
0x14000b238  lea     r12, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000b23f  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14000b246  lea     r15, WPP_8fea48f46a3838764f6f48a247805a06_Traceguids
0x14000b24d  jz      loc_14000B3EB
0x14000b253  mov     r9d, 22h ; '"'
0x14000b259  jmp     short loc_14000B1F8
0x14000b25b  mov     rax, cs:WdfFunctions_01015
0x14000b262  lea     r8, WinUSB_WritePipeCompletion
0x14000b269  mov     rcx, cs:WdfDriverGlobals
0x14000b270  mov     r9, rsi
0x14000b273  mov     rdx, rdi
0x14000b276  imul    r12, 0FFFFFFFFFFFFD8F0h
0x14000b27d  mov     rax, [rax+820h]
0x14000b284  call    _guard_dispatch_icall
0x14000b289  mov     rax, [rbp+4Fh+var_70]
0x14000b28d  mov     [rsi+18h], al
0x14000b290  mov     rax, [rbp+4Fh+var_80]
0x14000b294  mov     cl, [rax]
0x14000b296  mov     rax, [rbp+4Fh+var_68]
0x14000b29a  mov     [rsi+19h], cl
0x14000b29d  xor     ecx, ecx
0x14000b29f  mov     [rsi], ecx
0x14000b2a1  mov     [rsi+4], eax
0x14000b2a4  mov     [rsi+8], r13d
0x14000b2a8  mov     [rsi+10h], r12
0x14000b2ac  test    r12, r12
0x14000b2af  jz      short loc_14000B30C
0x14000b2b1  mov     rax, cs:WdfFunctions_01015
0x14000b2b8  mov     rdx, rdi
0x14000b2bb  mov     rcx, cs:WdfDriverGlobals
0x14000b2c2  mov     dword ptr [rbp+4Fh+var_58], 10h
0x14000b2c9  mov     dword ptr [rbp+4Fh+var_58+4], 1
0x14000b2d0  mov     qword ptr [rbp+4Fh+var_58+8], r12
0x14000b2d4  mov     rax, [rax+830h]
0x14000b2db  call    _guard_dispatch_icall
0x14000b2e0  mov     ebx, eax
0x14000b2e2  test    eax, eax
0x14000b2e4  jns     short loc_14000B318
0x14000b2e6  lea     r12, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000b2ed  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14000b2f4  lea     r15, WPP_8fea48f46a3838764f6f48a247805a06_Traceguids
0x14000b2fb  jz      loc_14000B3EB
0x14000b301  mov     r9d, 23h ; '#'
0x14000b307  jmp     loc_14000B1F8
0x14000b30c  mov     qword ptr [rbp+4Fh+var_58+8], rcx
0x14000b310  mov     qword ptr [rbp+4Fh+var_58], 10h
0x14000b318  lea     r12, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000b31f  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14000b326  jz      short loc_14000B363
0x14000b328  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b32f  mov     r9d, 24h ; '$'
0x14000b335  mov     eax, [rsi+1Ch]
0x14000b338  mov     dl, 4
0x14000b33a  mov     [rsp+0C0h+var_88], r13d
0x14000b33f  mov     [rsp+0C0h+var_90], eax
0x14000b343  mov     rcx, [rcx+40h]
0x14000b347  lea     r8d, [r9-1Fh]
0x14000b34b  mov     dword ptr [rsp+0C0h+var_98], r15d
0x14000b350  lea     r15, WPP_8fea48f46a3838764f6f48a247805a06_Traceguids
0x14000b357  mov     [rsp+0C0h+var_A0], r15
0x14000b35c  call    WPP_RECORDER_SF_dDd
0x14000b361  jmp     short loc_14000B36A
0x14000b363  lea     r15, WPP_8fea48f46a3838764f6f48a247805a06_Traceguids
0x14000b36a  mov     rsi, [rbp+4Fh+var_60]
0x14000b36e  mov     rdx, rdi
0x14000b371  mov     rcx, rsi
0x14000b374  call    WinUSB_IncrementKeepAliveCount
0x14000b379  mov     rax, cs:WdfFunctions_01015
0x14000b380  lea     r9, [rbp+4Fh+var_58]
0x14000b384  mov     r8, [r14+0A0h]
0x14000b38b  mov     rdx, rdi
0x14000b38e  mov     rcx, cs:WdfDriverGlobals
0x14000b395  mov     rax, [rax+7E8h]
0x14000b39c  call    _guard_dispatch_icall
0x14000b3a1  xor     edx, edx
0x14000b3a3  test    al, al
0x14000b3a5  jnz     loc_14000B08E
0x14000b3ab  mov     rdx, rdi
0x14000b3ae  mov     rcx, rsi
0x14000b3b1  mov     ebx, 0C0000001h
0x14000b3b6  call    WinUSB_DecrementKeepAliveCount
0x14000b3bb  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x14000b3c2  jz      short loc_14000B3EB
0x14000b3c4  mov     r9d, 25h ; '%'
0x14000b3ca  mov     dword ptr [rsp+0C0h+var_98], ebx
0x14000b3ce  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b3d5  mov     r8d, 3
0x14000b3db  mov     dl, 2
0x14000b3dd  mov     [rsp+0C0h+var_A0], r15
0x14000b3e2  mov     rcx, [rcx+40h]
0x14000b3e6  call    WPP_RECORDER_SF_d
0x14000b3eb  xor     eax, eax
0x14000b3ed  xchg    rax, [r14+50h]
0x14000b3f1  jmp     loc_14000B069
```
