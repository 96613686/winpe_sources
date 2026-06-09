# WinUSB_ReadPipe

- ea: `0x140009634`
- end: `0x1400099c6`
- name: `WinUSB_ReadPipe`
- size: `914`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _BYTE *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x1400026d0`

## callees

- `0x140001020`
- `0x1400011c8`
- `0x14000193c`
- `0x140001a4c`
- `0x14000751c`
- `0x140009634`
- `0x140010700`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140009801`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140009801`
- `ntoskrnl!KeReleaseSpinLock` at `0x140009816`
- `ntoskrnl!KeReleaseSpinLock` at `0x140009816`

## pseudocode

```c
__int64 __fastcall WinUSB_ReadPipe(__int64 a1, __int64 a2, __int64 a3, _BYTE *a4)
{
  __int64 v7; // rax
  __int64 *v8; // r8
  PWDF_DRIVER_GLOBALS v9; // rcx
  __int64 v10; // rbp
  int v11; // eax
  int v12; // edx
  unsigned int v13; // ebx
  int v14; // ecx
  int v15; // r9d
  __int64 v16; // r9
  char v17; // r8
  unsigned __int8 v18; // cl
  __int64 v19; // rsi
  KIRQL v20; // al
  char v21; // bl
  int v22; // edx
  char v24; // [rsp+30h] [rbp-58h]
  unsigned __int8 *v25; // [rsp+98h] [rbp+10h] BYREF

  v25 = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      1,
      28,
      (__int64)WPP_54c280395e213bf831c2a4b77063b8cf_Traceguids);
  v7 = WdfFunctions_01015;
  v8 = off_140015040;
  v9 = WdfDriverGlobals;
  *a4 = 1;
  v10 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(v7 + 1616))(v9, a3, v8);
  v11 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64, unsigned __int8 **, _QWORD))(WdfFunctions_01015 + 2152))(
          WdfDriverGlobals,
          a3,
          2,
          &v25,
          0);
  v13 = v11;
  if ( v11 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return v13;
    v14 = *(_DWORD *)(v10 + 28);
    v15 = 29;
    v24 = v11;
    goto LABEL_7;
  }
  v16 = *v25;
  if ( (unsigned __int8)v16 >= *(_BYTE *)(a1 + 128) )
  {
    v13 = -1073741811;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return v13;
    WPP_RECORDER_SF_ddd(
      WPP_GLOBAL_Control->DeviceExtension,
      v12,
      (_DWORD)v25,
      30,
      (__int64)WPP_54c280395e213bf831c2a4b77063b8cf_Traceguids,
      v16,
      v25[1]);
    goto LABEL_29;
  }
  v17 = v25[1];
  v18 = (v17 & 0xF) + 16;
  if ( v17 >= 0 )
    v18 = v17 & 0xF;
  v19 = *(_QWORD *)(*(_QWORD *)(a1 + 136) + 8 * (35 * v16 + v18) + 24);
  if ( !WinUSB_IsInterruptOrBulkInPipe(v19) )
  {
    v13 = -1073741811;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return v13;
    v15 = 32;
    goto LABEL_16;
  }
  v20 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v19 + 40));
  v21 = *(_BYTE *)(v19 + 31);
  KeReleaseSpinLock((PKSPIN_LOCK)(v19 + 40), v20);
  if ( v21 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v22) = 4;
      WPP_RECORDER_SF_dD(
        WPP_GLOBAL_Control->DeviceExtension,
        v22,
        4,
        33,
        (__int64)WPP_54c280395e213bf831c2a4b77063b8cf_Traceguids,
        v25[1],
        *(_DWORD *)(v10 + 28));
    }
    v13 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD))(WdfFunctions_01015 + 2248))(
            WdfDriverGlobals,
            a3,
            *(_QWORD *)(v19 + 56));
    if ( (v13 & 0x80000000) != 0 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return v13;
      LOBYTE(v12) = 2;
      WPP_RECORDER_SF_dD(
        WPP_GLOBAL_Control->DeviceExtension,
        v12,
        4,
        34,
        (__int64)WPP_54c280395e213bf831c2a4b77063b8cf_Traceguids,
        v25[1],
        *(_DWORD *)(v10 + 28));
      goto LABEL_29;
    }
    goto LABEL_28;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v22) = 4;
    WPP_RECORDER_SF_dD(
      WPP_GLOBAL_Control->DeviceExtension,
      v22,
      4,
      35,
      (__int64)WPP_54c280395e213bf831c2a4b77063b8cf_Traceguids,
      v25[1],
      *(_DWORD *)(v10 + 28));
  }
  v13 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD))(WdfFunctions_01015 + 2248))(
          WdfDriverGlobals,
          a3,
          *(_QWORD *)(v19 + 48));
  if ( (v13 & 0x80000000) == 0 )
  {
LABEL_28:
    *a4 = 0;
    goto LABEL_29;
  }
  if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    return v13;
  v15 = 36;
LABEL_16:
  v24 = v13;
  LOBYTE(v14) = v25[1];
LABEL_7:
  LOBYTE(v12) = 2;
  WPP_RECORDER_SF_dD(
    WPP_GLOBAL_Control->DeviceExtension,
    v12,
    3,
    v15,
    (__int64)WPP_54c280395e213bf831c2a4b77063b8cf_Traceguids,
    v14,
    v24);
LABEL_29:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(v12) = 5;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v12,
      1,
      37,
      (__int64)WPP_54c280395e213bf831c2a4b77063b8cf_Traceguids,
      v13);
  }
  return v13;
}

```

## disassembly

```asm
0x140009634  mov     rax, rsp
0x140009637  mov     [rax+10h], rdx
0x14000963b  push    rbx
0x14000963c  push    rbp
0x14000963d  push    rsi
0x14000963e  push    rdi
0x14000963f  push    r12
0x140009641  push    r13
0x140009643  push    r14
0x140009645  push    r15
0x140009647  sub     rsp, 48h
0x14000964b  xor     r13d, r13d
0x14000964e  mov     r15, r9
0x140009651  mov     [rax+10h], r13
0x140009655  mov     r14, r8
0x140009658  mov     rdi, rcx
0x14000965b  lea     r12, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140009662  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140009669  lea     rsi, WPP_54c280395e213bf831c2a4b77063b8cf_Traceguids
0x140009670  jz      short loc_140009697
0x140009672  mov     rcx, cs:WPP_GLOBAL_Control
0x140009679  cmp     [rcx+48h], r13w
0x14000967e  jz      short loc_140009697
0x140009680  mov     rcx, [rcx+40h]
0x140009684  lea     r9d, [r13+1Ch]
0x140009688  lea     r8d, [r13+1]
0x14000968c  mov     [rax-68h], rsi
0x140009690  mov     dl, 5
0x140009692  call    WPP_RECORDER_SF_
0x140009697  mov     rax, cs:WdfFunctions_01015
0x14000969e  mov     rdx, r14
0x1400096a1  mov     r8, cs:off_140015040
0x1400096a8  mov     rcx, cs:WdfDriverGlobals
0x1400096af  mov     byte ptr [r15], 1
0x1400096b3  mov     rax, [rax+650h]
0x1400096ba  call    _guard_dispatch_icall
0x1400096bf  mov     rcx, cs:WdfFunctions_01015
0x1400096c6  lea     r9, [rsp+88h+arg_8]
0x1400096ce  mov     rbp, rax
0x1400096d1  mov     [rsp+88h+var_68], r13
0x1400096d6  mov     r8d, 2
0x1400096dc  mov     rdx, r14
0x1400096df  mov     rax, [rcx+868h]
0x1400096e6  mov     rcx, cs:WdfDriverGlobals
0x1400096ed  call    _guard_dispatch_icall
0x1400096f2  mov     ebx, eax
0x1400096f4  test    eax, eax
0x1400096f6  jns     short loc_140009738
0x1400096f8  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x1400096ff  jz      loc_1400099B2
0x140009705  mov     ecx, [rbp+1Ch]
0x140009708  mov     r9d, 1Dh
0x14000970e  mov     dword ptr [rsp+88h+var_58], eax
0x140009712  mov     [rsp+88h+var_60], ecx
0x140009716  mov     r8d, 3
0x14000971c  mov     rcx, cs:WPP_GLOBAL_Control
0x140009723  mov     dl, 2
0x140009725  mov     [rsp+88h+var_68], rsi
0x14000972a  mov     rcx, [rcx+40h]
0x14000972e  call    WPP_RECORDER_SF_dD
0x140009733  jmp     loc_14000997D
0x140009738  mov     r8, [rsp+88h+arg_8]
0x140009740  movzx   r9d, byte ptr [r8]
0x140009744  cmp     r9b, [rdi+80h]
0x14000974b  jb      short loc_14000978F
0x14000974d  mov     ebx, 0C000000Dh
0x140009752  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x140009759  jz      loc_1400099B2
0x14000975f  movzx   eax, byte ptr [r8+1]
0x140009764  mov     ecx, r9d
0x140009767  mov     dword ptr [rsp+88h+var_58], eax
0x14000976b  mov     r9d, 1Eh
0x140009771  mov     [rsp+88h+var_60], ecx
0x140009775  mov     rcx, cs:WPP_GLOBAL_Control
0x14000977c  mov     [rsp+88h+var_68], rsi
0x140009781  mov     rcx, [rcx+40h]
0x140009785  call    WPP_RECORDER_SF_ddd
0x14000978a  jmp     loc_14000997D
0x14000978f  mov     r8b, [r8+1]
0x140009793  mov     al, r8b
0x140009796  and     al, 0Fh
0x140009798  movzx   edx, al
0x14000979b  test    r8b, r8b
0x14000979e  lea     eax, [rdx+10h]
0x1400097a1  movzx   ecx, al
0x1400097a4  mov     rax, [rdi+88h]
0x1400097ab  cmovns  ecx, edx
0x1400097ae  movzx   edx, cl
0x1400097b1  imul    rcx, r9, 23h ; '#'
0x1400097b5  add     rdx, rcx
0x1400097b8  mov     rsi, [rax+rdx*8+18h]
0x1400097bd  mov     rcx, rsi
0x1400097c0  call    WinUSB_IsInterruptOrBulkInPipe
0x1400097c5  test    al, al
0x1400097c7  jnz     short loc_1400097FD
0x1400097c9  mov     ebx, 0C000000Dh
0x1400097ce  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x1400097d5  jz      loc_1400099B2
0x1400097db  mov     r9d, 20h ; ' '
0x1400097e1  mov     rax, [rsp+88h+arg_8]
0x1400097e9  lea     rsi, WPP_54c280395e213bf831c2a4b77063b8cf_Traceguids
0x1400097f0  mov     dword ptr [rsp+88h+var_58], ebx
0x1400097f4  movzx   ecx, byte ptr [rax+1]
0x1400097f8  jmp     loc_140009712
0x1400097fd  lea     rcx, [rsi+28h]; SpinLock
0x140009801  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140009808  nop     dword ptr [rax+rax+00h]
0x14000980d  mov     bl, [rsi+1Fh]
0x140009810  lea     rcx, [rsi+28h]; SpinLock
0x140009814  mov     dl, al; NewIrql
0x140009816  call    cs:__imp_KeReleaseSpinLock
0x14000981d  nop     dword ptr [rax+rax+00h]
0x140009822  test    bl, bl
0x140009824  jz      loc_1400098EF
0x14000982a  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x140009831  jz      short loc_140009873
0x140009833  mov     rax, [rsp+88h+arg_8]
0x14000983b  mov     r9d, 21h ; '!'
0x140009841  movzx   ecx, byte ptr [rax+1]
0x140009845  lea     r8d, [r9-1Dh]
0x140009849  mov     eax, [rbp+1Ch]
0x14000984c  mov     dl, r8b
0x14000984f  mov     dword ptr [rsp+88h+var_58], eax
0x140009853  lea     rax, WPP_54c280395e213bf831c2a4b77063b8cf_Traceguids
0x14000985a  mov     [rsp+88h+var_60], ecx
0x14000985e  mov     rcx, cs:WPP_GLOBAL_Control
0x140009865  mov     [rsp+88h+var_68], rax
0x14000986a  mov     rcx, [rcx+40h]
0x14000986e  call    WPP_RECORDER_SF_dD
0x140009873  mov     rax, cs:WdfFunctions_01015
0x14000987a  mov     rdx, r14
0x14000987d  mov     r8, [rsi+38h]
0x140009881  mov     rcx, cs:WdfDriverGlobals
0x140009888  mov     rax, [rax+8C8h]
0x14000988f  call    _guard_dispatch_icall
0x140009894  mov     ebx, eax
0x140009896  test    eax, eax
0x140009898  jns     loc_140009973
0x14000989e  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x1400098a5  jz      loc_1400099B2
0x1400098ab  mov     rax, [rsp+88h+arg_8]
0x1400098b3  lea     rsi, WPP_54c280395e213bf831c2a4b77063b8cf_Traceguids
0x1400098ba  mov     r9d, 22h ; '"'
0x1400098c0  mov     dl, 2
0x1400098c2  movzx   ecx, byte ptr [rax+1]
0x1400098c6  mov     eax, [rbp+1Ch]
0x1400098c9  lea     r8d, [r9-1Eh]
0x1400098cd  mov     dword ptr [rsp+88h+var_58], eax
0x1400098d1  mov     [rsp+88h+var_60], ecx
0x1400098d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400098dc  mov     [rsp+88h+var_68], rsi
0x1400098e1  mov     rcx, [rcx+40h]
0x1400098e5  call    WPP_RECORDER_SF_dD
0x1400098ea  jmp     loc_14000997D
0x1400098ef  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x1400098f6  jz      short loc_140009938
0x1400098f8  mov     rax, [rsp+88h+arg_8]
0x140009900  mov     r9d, 23h ; '#'
0x140009906  movzx   ecx, byte ptr [rax+1]
0x14000990a  lea     r8d, [r9-1Fh]
0x14000990e  mov     eax, [rbp+1Ch]
0x140009911  mov     dl, r8b
0x140009914  mov     dword ptr [rsp+88h+var_58], eax
0x140009918  lea     rax, WPP_54c280395e213bf831c2a4b77063b8cf_Traceguids
0x14000991f  mov     [rsp+88h+var_60], ecx
0x140009923  mov     rcx, cs:WPP_GLOBAL_Control
0x14000992a  mov     [rsp+88h+var_68], rax
0x14000992f  mov     rcx, [rcx+40h]
0x140009933  call    WPP_RECORDER_SF_dD
0x140009938  mov     rax, cs:WdfFunctions_01015
0x14000993f  mov     rdx, r14
0x140009942  mov     r8, [rsi+30h]
0x140009946  mov     rcx, cs:WdfDriverGlobals
0x14000994d  mov     rax, [rax+8C8h]
0x140009954  call    _guard_dispatch_icall
0x140009959  mov     ebx, eax
0x14000995b  test    eax, eax
0x14000995d  jns     short loc_140009973
0x14000995f  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x140009966  jz      short loc_1400099B2
0x140009968  mov     r9d, 24h ; '$'
0x14000996e  jmp     loc_1400097E1
0x140009973  mov     [r15], r13b
0x140009976  lea     rsi, WPP_54c280395e213bf831c2a4b77063b8cf_Traceguids
0x14000997d  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x140009984  jz      short loc_1400099B2
0x140009986  mov     rcx, cs:WPP_GLOBAL_Control
0x14000998d  cmp     [rcx+48h], r13w
0x140009992  jz      short loc_1400099B2
0x140009994  mov     rcx, [rcx+40h]
0x140009998  mov     r9d, 25h ; '%'
0x14000999e  mov     [rsp+88h+var_60], ebx
0x1400099a2  mov     dl, 5
0x1400099a4  mov     [rsp+88h+var_68], rsi
0x1400099a9  lea     r8d, [r9-24h]
0x1400099ad  call    WPP_RECORDER_SF_d
0x1400099b2  mov     eax, ebx
0x1400099b4  add     rsp, 48h
0x1400099b8  pop     r15
0x1400099ba  pop     r14
0x1400099bc  pop     r13
0x1400099be  pop     r12
0x1400099c0  pop     rdi
0x1400099c1  pop     rsi
0x1400099c2  pop     rbp
0x1400099c3  pop     rbx
0x1400099c4  retn
```
