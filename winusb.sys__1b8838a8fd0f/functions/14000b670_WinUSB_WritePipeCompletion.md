# WinUSB_WritePipeCompletion

- ea: `0x14000b670`
- end: `0x14000bc43`
- name: `WinUSB_WritePipeCompletion`
- size: `1491`
- prototype: `_UNKNOWN **__fastcall(__int64, __int64, __int64, unsigned int *)`
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
- `0x14000b670`
- `0x1400106c0`
- `0x140010700`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000b842`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000b842`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000b8d0`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000b8d0`

## pseudocode

```c
_UNKNOWN **__fastcall WinUSB_WritePipeCompletion(__int64 a1, __int64 a2, __int64 a3, unsigned int *a4)
{
  __int64 v4; // rdi
  __int64 *v9; // rdx
  __int64 v10; // rax
  __int64 v11; // r15
  int v12; // edx
  int v13; // r14d
  char v14; // cl
  unsigned int v15; // edx
  unsigned int *v16; // rsi
  __int64 v17; // r13
  unsigned int v18; // ecx
  unsigned int v19; // eax
  unsigned int v20; // ecx
  unsigned int v21; // r15d
  char v22; // r15
  KIRQL v23; // cl
  unsigned int v24; // eax
  int v25; // edx
  char v26; // cl
  int v27; // edx
  char v28; // cl
  int v29; // r9d
  int v30; // edx
  char v31; // cl
  __int64 v32; // r15
  int v33; // edx
  char v34; // cl
  _UNKNOWN **result; // rax
  KIRQL v36; // [rsp+40h] [rbp-29h]
  unsigned int v37; // [rsp+44h] [rbp-25h]
  __int64 v38; // [rsp+48h] [rbp-21h] BYREF
  __int64 v39; // [rsp+50h] [rbp-19h]
  __int64 v40; // [rsp+58h] [rbp-11h]
  __int128 v41; // [rsp+60h] [rbp-9h] BYREF
  __int64 v42; // [rsp+70h] [rbp+7h] BYREF
  __int64 v43; // [rsp+78h] [rbp+Fh]

  v4 = *((unsigned __int8 *)a4 + 24);
  v38 = 0;
  v41 = 0;
  v42 = 0;
  v43 = 0;
  v40 = a2;
  v9 = WPP_8fea48f46a3838764f6f48a247805a06_Traceguids;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(v9) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)v9,
      1,
      10,
      (__int64)WPP_8fea48f46a3838764f6f48a247805a06_Traceguids);
  }
  v10 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 1392))(WdfDriverGlobals, a2);
  v39 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
          WdfDriverGlobals,
          v10,
          off_1400150F0);
  v11 = v39;
  WinUSB_DecrementKeepAliveCount(v39, a1);
  *a4 += *(_DWORD *)(*(_QWORD *)(a3 + 24) + 16LL);
  v13 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 2032))(WdfDriverGlobals, a1);
  if ( v13 >= 0 )
  {
    v16 = a4 + 1;
    v15 = *a4;
    v17 = *(_QWORD *)(*(_QWORD *)(v11 + 136) + 8 * (v4 + 35LL * *((unsigned __int8 *)a4 + 25)) + 24);
    v18 = a4[1];
    if ( *a4 >= v18 )
    {
      if ( v15 != v18 || !a4[2] )
        goto LABEL_55;
      v22 = 0;
      v37 = *(_DWORD *)(v17 + 4);
      v36 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v17 + 40));
      v23 = v36;
      if ( *(_BYTE *)(v17 + 20) )
      {
        v24 = *a4;
        if ( *a4 )
        {
          v25 = v24 % v37;
          if ( !(v24 % v37) )
          {
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
              && LOWORD(WPP_GLOBAL_Control->DeviceType) )
            {
              v26 = v4 & 0xF;
              if ( (v4 & 0x10) != 0 )
                v26 += 0x80;
              LOBYTE(v25) = 5;
              WPP_RECORDER_SF_dD(
                WPP_GLOBAL_Control->DeviceExtension,
                v25,
                5,
                12,
                (__int64)WPP_8fea48f46a3838764f6f48a247805a06_Traceguids,
                v26,
                a4[7]);
              v23 = v36;
            }
            v22 = 1;
          }
        }
      }
      KeReleaseSpinLock((PKSPIN_LOCK)(v17 + 40), v23);
      if ( !v22 )
        goto LABEL_55;
      v21 = 0;
    }
    else
    {
      v19 = *(_DWORD *)(v17 + 112);
      v20 = v18 - v15;
      v42 = *a4;
      if ( v20 <= v19 )
        v19 = v20;
      v21 = v19;
      v43 = v19;
    }
    if ( v21
      && (v13 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 2144))(
                  WdfDriverGlobals,
                  a1,
                  &v38),
          v13 < 0) )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_59;
      v28 = v4 & 0xF;
      if ( (v4 & 0x10) != 0 )
        v28 += 0x80;
      v29 = 13;
    }
    else
    {
      v13 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, __int64, __int64, __int64 *))(WdfFunctions_01015
                                                                                                + 2776))(
              WdfDriverGlobals,
              *(_QWORD *)(v17 + 160),
              a1,
              v38,
              &v42);
      if ( v13 >= 0 )
      {
        a4[2] = v21;
        (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _UNKNOWN **(__fastcall *)(__int64, __int64, __int64, unsigned int *), unsigned int *))(WdfFunctions_01015 + 2080))(
          WdfDriverGlobals,
          a1,
          WinUSB_WritePipeCompletion,
          a4);
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
        {
          v31 = v4 & 0xF;
          if ( (v4 & 0x10) != 0 )
            v31 += 0x80;
          LOBYTE(v30) = 5;
          WPP_RECORDER_SF_dDd(
            WPP_GLOBAL_Control->DeviceExtension,
            v30,
            5,
            15,
            (__int64)WPP_8fea48f46a3838764f6f48a247805a06_Traceguids,
            v31,
            a4[7],
            v21);
        }
        if ( *((_QWORD *)a4 + 2) )
        {
          *((_QWORD *)&v41 + 1) = *((_QWORD *)a4 + 2);
          *(_QWORD *)&v41 = 0x100000010LL;
          v13 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 2096))(
                  WdfDriverGlobals,
                  a1);
          if ( v13 < 0 )
          {
            if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              goto LABEL_59;
            v28 = v4 & 0xF;
            if ( (v4 & 0x10) != 0 )
              v28 += 0x80;
            v29 = 16;
            goto LABEL_32;
          }
        }
        else
        {
          v41 = 0x10u;
        }
        v32 = v39;
        WinUSB_IncrementKeepAliveCount(v39, a1);
        if ( (*(unsigned __int8 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64, __int128 *))(WdfFunctions_01015
                                                                                                  + 2024))(
               WdfDriverGlobals,
               a1,
               v40,
               &v41) )
        {
          goto LABEL_60;
        }
        WinUSB_DecrementKeepAliveCount(v32, a1);
        v13 = -1073741823;
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_59;
        v28 = v4 & 0xF;
        if ( (v4 & 0x10) != 0 )
          v28 += 0x80;
        v29 = 17;
      }
      else
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_59;
        v28 = v4 & 0xF;
        if ( (v4 & 0x10) != 0 )
          v28 += 0x80;
        v29 = 14;
      }
    }
LABEL_32:
    LOBYTE(v27) = 2;
    WPP_RECORDER_SF_dDd(
      WPP_GLOBAL_Control->DeviceExtension,
      v27,
      5,
      v29,
      (__int64)WPP_8fea48f46a3838764f6f48a247805a06_Traceguids,
      v28,
      a4[7],
      v13);
LABEL_55:
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v34 = v4 & 0xF;
      if ( (v4 & 0x10) != 0 )
        v34 += 0x80;
      LOBYTE(v15) = 4;
      WPP_RECORDER_SF_dDd(
        WPP_GLOBAL_Control->DeviceExtension,
        v15,
        5,
        18,
        (__int64)WPP_8fea48f46a3838764f6f48a247805a06_Traceguids,
        v34,
        a4[7],
        *v16);
    }
    goto LABEL_59;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v14 = v4 & 0xF;
    if ( (v4 & 0x10) != 0 )
      v14 += 0x80;
    LOBYTE(v12) = 3;
    WPP_RECORDER_SF_dDd(
      WPP_GLOBAL_Control->DeviceExtension,
      v12,
      5,
      11,
      (__int64)WPP_8fea48f46a3838764f6f48a247805a06_Traceguids,
      v14,
      a4[7],
      v13);
    v16 = a4 + 1;
    goto LABEL_55;
  }
LABEL_59:
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD, _QWORD))(WdfFunctions_01015 + 2120))(
    WdfDriverGlobals,
    a1,
    (unsigned int)v13,
    *a4);
LABEL_60:
  result = &WPP_RECORDER_INITIALIZED;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(v33) = 5;
      return (_UNKNOWN **)WPP_RECORDER_SF_d(
                            WPP_GLOBAL_Control->DeviceExtension,
                            v33,
                            1,
                            19,
                            (__int64)WPP_8fea48f46a3838764f6f48a247805a06_Traceguids,
                            v13);
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000b670  mov     [rsp-8+arg_10], rbx
0x14000b675  push    rbp
0x14000b676  push    rsi
0x14000b677  push    rdi
0x14000b678  push    r12
0x14000b67a  push    r13
0x14000b67c  push    r14
0x14000b67e  push    r15
0x14000b680  lea     rbp, [rsp-27h]
0x14000b685  sub     rsp, 90h
0x14000b68c  mov     rax, cs:__security_cookie
0x14000b693  xor     rax, rsp
0x14000b696  mov     [rbp+57h+var_40], rax
0x14000b69a  movzx   edi, byte ptr [r9+18h]
0x14000b69f  xor     r13d, r13d
0x14000b6a2  xorps   xmm0, xmm0
0x14000b6a5  mov     [rbp+57h+var_78], r13
0x14000b6a9  movups  [rbp+57h+var_60], xmm0
0x14000b6ad  mov     [rbp+57h+var_50], r13
0x14000b6b1  mov     rbx, r9
0x14000b6b4  mov     [rbp+57h+var_48], r13
0x14000b6b8  mov     rsi, r8
0x14000b6bb  mov     r14, rdx
0x14000b6be  mov     [rbp+57h+var_68], rdx
0x14000b6c2  mov     r12, rcx
0x14000b6c5  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000b6cc  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000b6d3  lea     rdx, WPP_8fea48f46a3838764f6f48a247805a06_Traceguids
0x14000b6da  jz      short loc_14000B702
0x14000b6dc  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b6e3  cmp     [rcx+48h], r13w
0x14000b6e8  jz      short loc_14000B702
0x14000b6ea  mov     rcx, [rcx+40h]
0x14000b6ee  lea     r9d, [r13+0Ah]
0x14000b6f2  mov     [rsp+0C0h+var_A0], rdx
0x14000b6f7  lea     r8d, [r13+1]
0x14000b6fb  mov     dl, 5
0x14000b6fd  call    WPP_RECORDER_SF_
0x14000b702  mov     rax, cs:WdfFunctions_01015
0x14000b709  mov     rdx, r14
0x14000b70c  mov     rcx, cs:WdfDriverGlobals
0x14000b713  mov     rax, [rax+570h]
0x14000b71a  call    _guard_dispatch_icall
0x14000b71f  mov     rcx, cs:WdfFunctions_01015
0x14000b726  mov     rdx, rax
0x14000b729  mov     r8, cs:off_1400150F0
0x14000b730  mov     rax, [rcx+650h]
0x14000b737  mov     rcx, cs:WdfDriverGlobals
0x14000b73e  call    _guard_dispatch_icall
0x14000b743  mov     rdx, r12
0x14000b746  mov     [rbp+57h+var_70], rax
0x14000b74a  mov     rcx, rax
0x14000b74d  mov     r15, rax
0x14000b750  call    WinUSB_DecrementKeepAliveCount
0x14000b755  mov     rcx, [rsi+18h]
0x14000b759  mov     edx, [rcx+10h]
0x14000b75c  add     [rbx], edx
0x14000b75e  mov     rdx, r12
0x14000b761  mov     rcx, cs:WdfFunctions_01015
0x14000b768  mov     rax, [rcx+7F0h]
0x14000b76f  mov     rcx, cs:WdfDriverGlobals
0x14000b776  call    _guard_dispatch_icall
0x14000b77b  mov     r14d, eax
0x14000b77e  test    eax, eax
0x14000b780  jns     short loc_14000B7E5
0x14000b782  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000b789  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000b790  jz      loc_14000BBB1
0x14000b796  mov     ecx, edi
0x14000b798  and     ecx, 0Fh
0x14000b79b  test    dil, 10h
0x14000b79f  jz      short loc_14000B7A4
0x14000b7a1  sub     ecx, 0FFFFFF80h
0x14000b7a4  mov     eax, [rbx+1Ch]
0x14000b7a7  lea     r15, WPP_8fea48f46a3838764f6f48a247805a06_Traceguids
0x14000b7ae  mov     [rsp+0C0h+var_88], r14d
0x14000b7b3  mov     r9d, 0Bh
0x14000b7b9  mov     [rsp+0C0h+var_90], eax
0x14000b7bd  mov     dl, 3
0x14000b7bf  mov     [rsp+0C0h+var_98], ecx
0x14000b7c3  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b7ca  lea     r8d, [r9-6]
0x14000b7ce  mov     [rsp+0C0h+var_A0], r15
0x14000b7d3  mov     rcx, [rcx+40h]
0x14000b7d7  call    WPP_RECORDER_SF_dDd
0x14000b7dc  lea     rsi, [rbx+4]
0x14000b7e0  jmp     loc_14000BB61
0x14000b7e5  movzx   eax, byte ptr [rbx+19h]
0x14000b7e9  lea     rsi, [rbx+4]
0x14000b7ed  mov     edx, [rbx]
0x14000b7ef  imul    rcx, rax, 23h ; '#'
0x14000b7f3  mov     rax, [r15+88h]
0x14000b7fa  add     rcx, rdi
0x14000b7fd  mov     r13, [rax+rcx*8+18h]
0x14000b802  mov     ecx, [rsi]
0x14000b804  cmp     edx, ecx
0x14000b806  jnb     short loc_14000B823
0x14000b808  mov     eax, [r13+70h]
0x14000b80c  sub     ecx, edx
0x14000b80e  cmp     ecx, eax
0x14000b810  mov     [rbp+57h+var_50], rdx
0x14000b814  cmovbe  eax, ecx
0x14000b817  mov     r15d, eax
0x14000b81a  mov     [rbp+57h+var_48], r15
0x14000b81e  jmp     loc_14000B8EA
0x14000b823  jnz     loc_14000BB5A
0x14000b829  xor     eax, eax
0x14000b82b  cmp     [rbx+8], eax
0x14000b82e  jz      loc_14000BB5A
0x14000b834  mov     r15b, al
0x14000b837  lea     rcx, [r13+28h]; SpinLock
0x14000b83b  mov     eax, [r13+4]
0x14000b83f  mov     [rbp+57h+var_7C], eax
0x14000b842  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000b849  nop     dword ptr [rax+rax+00h]
0x14000b84e  xor     r8d, r8d
0x14000b851  mov     [rbp+57h+var_80], al
0x14000b854  mov     cl, al
0x14000b856  cmp     [r13+14h], r8b
0x14000b85a  jz      short loc_14000B8CA
0x14000b85c  mov     eax, [rbx]
0x14000b85e  test    eax, eax
0x14000b860  jz      short loc_14000B8CA
0x14000b862  xor     edx, edx
0x14000b864  div     [rbp+57h+var_7C]
0x14000b867  test    edx, edx
0x14000b869  jnz     short loc_14000B8CA
0x14000b86b  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000b872  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000b879  jz      short loc_14000B8C7
0x14000b87b  mov     r10, cs:WPP_GLOBAL_Control
0x14000b882  cmp     [r10+48h], r8w
0x14000b887  jz      short loc_14000B8C7
0x14000b889  mov     ecx, edi
0x14000b88b  and     ecx, 0Fh
0x14000b88e  test    dil, 10h
0x14000b892  jz      short loc_14000B897
0x14000b894  sub     ecx, 0FFFFFF80h
0x14000b897  mov     eax, [rbx+1Ch]
0x14000b89a  mov     r9d, 0Ch
0x14000b8a0  mov     [rsp+0C0h+var_90], eax
0x14000b8a4  lea     rax, WPP_8fea48f46a3838764f6f48a247805a06_Traceguids
0x14000b8ab  mov     [rsp+0C0h+var_98], ecx
0x14000b8af  mov     rcx, [r10+40h]
0x14000b8b3  lea     r8d, [r9-7]
0x14000b8b7  mov     [rsp+0C0h+var_A0], rax
0x14000b8bc  mov     dl, r8b
0x14000b8bf  call    WPP_RECORDER_SF_dD
0x14000b8c4  mov     cl, [rbp+57h+var_80]
0x14000b8c7  mov     r15b, 1
0x14000b8ca  mov     dl, cl; NewIrql
0x14000b8cc  lea     rcx, [r13+28h]; SpinLock
0x14000b8d0  call    cs:__imp_KeReleaseSpinLock
0x14000b8d7  nop     dword ptr [rax+rax+00h]
0x14000b8dc  xor     eax, eax
0x14000b8de  test    r15b, r15b
0x14000b8e1  jz      loc_14000BB5A
0x14000b8e7  mov     r15d, eax
0x14000b8ea  test    r15d, r15d
0x14000b8ed  jz      loc_14000B97C
0x14000b8f3  mov     rax, cs:WdfFunctions_01015
0x14000b8fa  lea     r8, [rbp+57h+var_78]
0x14000b8fe  mov     rcx, cs:WdfDriverGlobals
0x14000b905  mov     rdx, r12
0x14000b908  mov     rax, [rax+860h]
0x14000b90f  call    _guard_dispatch_icall
0x14000b914  mov     r14d, eax
0x14000b917  test    eax, eax
0x14000b919  jns     short loc_14000B97C
0x14000b91b  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000b922  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000b929  jz      loc_14000BBB1
0x14000b92f  mov     ecx, edi
0x14000b931  and     ecx, 0Fh
0x14000b934  test    dil, 10h
0x14000b938  jz      short loc_14000B93D
0x14000b93a  sub     ecx, 0FFFFFF80h
0x14000b93d  mov     r9d, 0Dh
0x14000b943  mov     eax, [rbx+1Ch]
0x14000b946  lea     r15, WPP_8fea48f46a3838764f6f48a247805a06_Traceguids
0x14000b94d  mov     [rsp+0C0h+var_88], r14d
0x14000b952  mov     r8d, 5
0x14000b958  mov     [rsp+0C0h+var_90], eax
0x14000b95c  mov     dl, 2
0x14000b95e  mov     [rsp+0C0h+var_98], ecx
0x14000b962  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b969  mov     [rsp+0C0h+var_A0], r15
0x14000b96e  mov     rcx, [rcx+40h]
0x14000b972  call    WPP_RECORDER_SF_dDd
0x14000b977  jmp     loc_14000BB61
0x14000b97c  mov     rax, cs:WdfFunctions_01015
0x14000b983  lea     rcx, [rbp+57h+var_50]
0x14000b987  mov     r9, [rbp+57h+var_78]
0x14000b98b  mov     r8, r12
0x14000b98e  mov     rdx, [r13+0A0h]
0x14000b995  mov     [rsp+0C0h+var_A0], rcx
0x14000b99a  mov     rax, [rax+0AD8h]
0x14000b9a1  mov     rcx, cs:WdfDriverGlobals
0x14000b9a8  call    _guard_dispatch_icall
0x14000b9ad  xor     r13d, r13d
0x14000b9b0  mov     r14d, eax
0x14000b9b3  test    eax, eax
0x14000b9b5  jns     short loc_14000B9E4
0x14000b9b7  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000b9be  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000b9c5  jz      loc_14000BBB1
0x14000b9cb  mov     ecx, edi
0x14000b9cd  and     ecx, 0Fh
0x14000b9d0  test    dil, 10h
0x14000b9d4  jz      short loc_14000B9D9
0x14000b9d6  sub     ecx, 0FFFFFF80h
0x14000b9d9  mov     r9d, 0Eh
0x14000b9df  jmp     loc_14000B943
0x14000b9e4  mov     [rbx+8], r15d
0x14000b9e8  lea     r8, WinUSB_WritePipeCompletion
0x14000b9ef  mov     rax, cs:WdfFunctions_01015
0x14000b9f6  mov     r9, rbx
0x14000b9f9  mov     rcx, cs:WdfDriverGlobals
0x14000ba00  mov     rdx, r12
0x14000ba03  mov     rax, [rax+820h]
0x14000ba0a  call    _guard_dispatch_icall
0x14000ba0f  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000ba16  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000ba1d  jz      short loc_14000BA6D
0x14000ba1f  mov     r10, cs:WPP_GLOBAL_Control
0x14000ba26  cmp     [r10+48h], r13w
0x14000ba2b  jz      short loc_14000BA6D
0x14000ba2d  mov     ecx, edi
0x14000ba2f  and     ecx, 0Fh
0x14000ba32  test    dil, 10h
0x14000ba36  jz      short loc_14000BA3B
0x14000ba38  sub     ecx, 0FFFFFF80h
0x14000ba3b  mov     eax, [rbx+1Ch]
0x14000ba3e  mov     r9d, 0Fh
0x14000ba44  mov     [rsp+0C0h+var_88], r15d
0x14000ba49  mov     [rsp+0C0h+var_90], eax
0x14000ba4d  lea     rax, WPP_8fea48f46a3838764f6f48a247805a06_Traceguids
0x14000ba54  mov     [rsp+0C0h+var_98], ecx
0x14000ba58  mov     rcx, [r10+40h]
0x14000ba5c  lea     r8d, [r9-0Ah]
0x14000ba60  mov     dl, r8b
0x14000ba63  mov     [rsp+0C0h+var_A0], rax
0x14000ba68  call    WPP_RECORDER_SF_dDd
0x14000ba6d  mov     rax, [rbx+10h]
0x14000ba71  test    rax, rax
0x14000ba74  jz      short loc_14000BAD8
0x14000ba76  mov     rcx, cs:WdfDriverGlobals
0x14000ba7d  mov     r15d, 10h
0x14000ba83  mov     qword ptr [rbp+57h+var_60+8], rax
0x14000ba87  mov     rdx, r12
0x14000ba8a  mov     rax, cs:WdfFunctions_01015
0x14000ba91  mov     dword ptr [rbp+57h+var_60], r15d
0x14000ba95  mov     dword ptr [rbp+57h+var_60+4], 1
0x14000ba9c  mov     rax, [rax+830h]
0x14000baa3  call    _guard_dispatch_icall
0x14000baa8  mov     r14d, eax
0x14000baab  test    eax, eax
0x14000baad  jns     short loc_14000BAE4
0x14000baaf  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000bab6  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000babd  jz      loc_14000BBB1
0x14000bac3  mov     ecx, edi
0x14000bac5  and     ecx, 0Fh
0x14000bac8  test    r15b, dil
0x14000bacb  jz      short loc_14000BAD0
0x14000bacd  sub     ecx, 0FFFFFF80h
0x14000bad0  mov     r9d, r15d
0x14000bad3  jmp     loc_14000B943
0x14000bad8  mov     qword ptr [rbp+57h+var_60+8], r13
0x14000badc  mov     qword ptr [rbp+57h+var_60], 10h
0x14000bae4  mov     r15, [rbp+57h+var_70]
0x14000bae8  mov     rdx, r12
0x14000baeb  mov     rcx, r15
0x14000baee  call    WinUSB_IncrementKeepAliveCount
0x14000baf3  mov     rax, cs:WdfFunctions_01015
0x14000bafa  lea     r9, [rbp+57h+var_60]
0x14000bafe  mov     r8, [rbp+57h+var_68]
0x14000bb02  mov     rdx, r12
0x14000bb05  mov     rcx, cs:WdfDriverGlobals
0x14000bb0c  mov     rax, [rax+7E8h]
0x14000bb13  call    _guard_dispatch_icall
0x14000bb18  test    al, al
0x14000bb1a  jnz     loc_14000BBD7
0x14000bb20  mov     rdx, r12
0x14000bb23  mov     rcx, r15
0x14000bb26  call    WinUSB_DecrementKeepAliveCount
0x14000bb2b  mov     r14d, 0C0000001h
0x14000bb31  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000bb38  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000bb3f  jz      short loc_14000BBB1
0x14000bb41  mov     ecx, edi
0x14000bb43  and     ecx, 0Fh
0x14000bb46  test    dil, 10h
0x14000bb4a  jz      short loc_14000BB4F
0x14000bb4c  sub     ecx, 0FFFFFF80h
0x14000bb4f  mov     r9d, 11h
0x14000bb55  jmp     loc_14000B943
0x14000bb5a  lea     r15, WPP_8fea48f46a3838764f6f48a247805a06_Traceguids
0x14000bb61  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000bb68  cmp     cs:WPP_RECORDER_INITIALIZED, rax
  ... truncated ...
```
