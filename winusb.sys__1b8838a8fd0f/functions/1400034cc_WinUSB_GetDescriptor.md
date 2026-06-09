# WinUSB_GetDescriptor

- ea: `0x1400034cc`
- end: `0x14000398a`
- name: `WinUSB_GetDescriptor`
- size: `1214`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _BYTE *)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x1400026d0`

## callees

- `0x140001020`
- `0x1400011c8`
- `0x14000193c`
- `0x140001c30`
- `0x14000264c`
- `0x1400034cc`
- `0x140003990`
- `0x1400106c0`
- `0x140010700`
- `0x1400108c0`

## pseudocode

```c
__int64 __fastcall WinUSB_GetDescriptor(__int64 a1, __int64 a2, __int64 a3, _BYTE *a4)
{
  int v7; // eax
  int v8; // edx
  int v9; // r8d
  int v10; // edi
  int v11; // edx
  int v12; // r9d
  unsigned __int16 *v13; // rdx
  size_t v14; // rbx
  size_t v15; // r8
  unsigned __int8 *v16; // rax
  int v17; // edx
  int v18; // r9d
  int v19; // r8d
  int v20; // eax
  int v21; // edx
  char v23; // [rsp+28h] [rbp-41h]
  __int64 v24; // [rsp+40h] [rbp-29h] BYREF
  __int64 v25; // [rsp+48h] [rbp-21h] BYREF
  size_t Size; // [rsp+50h] [rbp-19h] BYREF
  void *v27; // [rsp+58h] [rbp-11h] BYREF
  __int64 v28; // [rsp+60h] [rbp-9h] BYREF
  __int64 v29; // [rsp+68h] [rbp-1h] BYREF
  __int128 v30; // [rsp+70h] [rbp+7h] BYREF

  v24 = 0;
  v25 = 0;
  v30 = 0;
  v28 = 0;
  v27 = 0;
  Size = 0;
  v29 = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      1,
      54,
      (__int64)WPP_1ea4bda7f8b23cafb6f0c7d9f6a1b177_Traceguids);
  *a4 = 1;
  v7 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64, __int64 *, __int64 *))(WdfFunctions_01015 + 2152))(
         WdfDriverGlobals,
         a3,
         4,
         &v25,
         &v28);
  v10 = v7;
  if ( v7 >= 0 )
  {
    if ( *(_BYTE *)v25 == 1 )
    {
      v16 = *(unsigned __int8 **)(a1 + 48);
      if ( v16 )
      {
        v10 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD, void **, size_t *))(WdfFunctions_01015
                                                                                                 + 2160))(
                WdfDriverGlobals,
                a3,
                *v16,
                &v27,
                &Size);
        if ( v10 < 0 )
        {
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            goto LABEL_39;
          v12 = 56;
          goto LABEL_20;
        }
        memmove(v27, *(const void **)(a1 + 48), **(unsigned __int8 **)(a1 + 48));
        v15 = **(unsigned __int8 **)(a1 + 48);
LABEL_38:
        (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, size_t))(WdfFunctions_01015 + 2200))(
          WdfDriverGlobals,
          a3,
          v15);
        goto LABEL_39;
      }
    }
    else if ( *(_BYTE *)v25 == 2 && *(_QWORD *)(a1 + 56) )
    {
      v10 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD, void **, size_t *))(WdfFunctions_01015
                                                                                               + 2160))(
              WdfDriverGlobals,
              a3,
              0,
              &v27,
              &Size);
      if ( v10 < 0 )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_39;
        v12 = 57;
LABEL_20:
        LOBYTE(v11) = 2;
        WPP_RECORDER_SF_dD(
          WPP_GLOBAL_Control->DeviceExtension,
          v11,
          3,
          v12,
          (__int64)WPP_1ea4bda7f8b23cafb6f0c7d9f6a1b177_Traceguids,
          *(_BYTE *)v25,
          v10);
        goto LABEL_39;
      }
      v13 = *(unsigned __int16 **)(a1 + 56);
      v14 = v13[1];
      if ( Size < v14 )
        v14 = Size;
      memmove(v27, v13, v14);
      v15 = v14;
      goto LABEL_38;
    }
    if ( (*(int (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, _QWORD, __int64 *, __int64 *))(WdfFunctions_01015 + 3384))(
           WdfDriverGlobals,
           *(_QWORD *)(a1 + 8),
           0,
           &v29,
           &v24) < 0 )
    {
      v10 = -1073741670;
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_39;
      v18 = 58;
      v23 = -102;
      v19 = 2;
      LOBYTE(v17) = 2;
      goto LABEL_25;
    }
    v20 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD, void **, size_t *))(WdfFunctions_01015 + 2160))(
            WdfDriverGlobals,
            a3,
            0,
            &v27,
            &Size);
    v10 = v20;
    if ( v20 >= 0 )
    {
      *(_WORD *)(v24 + 2) = 11;
      *(_WORD *)v24 = 136;
      *(_DWORD *)(v24 + 36) = Size;
      *(_QWORD *)(v24 + 48) = 0;
      *(_QWORD *)(v24 + 40) = v27;
      *(_BYTE *)(v24 + 131) = *(_BYTE *)v25;
      *(_BYTE *)(v24 + 130) = *(_BYTE *)(v25 + 1);
      *(_WORD *)(v24 + 132) = *(_WORD *)(v25 + 2);
      *(_QWORD *)(v24 + 56) = 0;
      *(_QWORD *)&v30 = 0x100000010LL;
      *((_QWORD *)&v30 + 1) = -50000000;
      v20 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 2096))(WdfDriverGlobals, a3);
      v10 = v20;
      if ( v20 >= 0 )
      {
        WinUSB_IncrementKeepAliveCount(a1, a3);
        v10 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, _QWORD, __int128 *, __int64))(WdfFunctions_01015
                                                                                                  + 2712))(
                WdfDriverGlobals,
                *(_QWORD *)(a1 + 8),
                0,
                &v30,
                v24);
        WinUSB_DecrementKeepAliveCount(a1, a3);
        if ( v10 >= 0 )
        {
          v15 = *(unsigned int *)(v24 + 36);
          goto LABEL_38;
        }
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_39;
        v18 = 61;
        v23 = v10;
        goto LABEL_30;
      }
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_39;
      v18 = 60;
    }
    else
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_39;
      v18 = 59;
    }
    v23 = v20;
LABEL_30:
    v19 = 3;
    LOBYTE(v17) = 2;
LABEL_25:
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v17,
      v19,
      v18,
      (__int64)WPP_1ea4bda7f8b23cafb6f0c7d9f6a1b177_Traceguids,
      v23);
    goto LABEL_39;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v8) = 2;
    WPP_RECORDER_SF_did(
      WPP_GLOBAL_Control->DeviceExtension,
      v8,
      v9,
      55,
      (__int64)WPP_1ea4bda7f8b23cafb6f0c7d9f6a1b177_Traceguids,
      4,
      v28,
      v7);
  }
LABEL_39:
  v21 = v29;
  if ( v29 )
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS))(WdfFunctions_01015 + 1664))(WdfDriverGlobals);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(v21) = 5;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v21,
      1,
      62,
      (__int64)WPP_1ea4bda7f8b23cafb6f0c7d9f6a1b177_Traceguids,
      v10);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1400034cc  push    rbp
0x1400034ce  push    rbx
0x1400034cf  push    rsi
0x1400034d0  push    rdi
0x1400034d1  push    r12
0x1400034d3  push    r14
0x1400034d5  push    r15
0x1400034d7  lea     rbp, [rsp-27h]
0x1400034dc  sub     rsp, 90h
0x1400034e3  mov     rax, cs:__security_cookie
0x1400034ea  xor     rax, rsp
0x1400034ed  mov     [rbp+57h+var_40], rax
0x1400034f1  xor     r14d, r14d
0x1400034f4  xorps   xmm0, xmm0
0x1400034f7  mov     [rbp+57h+var_80], r14
0x1400034fb  mov     rdi, r9
0x1400034fe  mov     [rbp+57h+var_78], r14
0x140003502  mov     rsi, r8
0x140003505  movups  [rbp+57h+var_50], xmm0
0x140003509  mov     [rbp+57h+var_60], r14
0x14000350d  mov     rbx, rcx
0x140003510  mov     [rbp+57h+var_68], r14
0x140003514  mov     [rbp+57h+Size], r14
0x140003518  mov     [rbp+57h+var_58], r14
0x14000351c  lea     r15, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140003523  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14000352a  lea     r12, WPP_1ea4bda7f8b23cafb6f0c7d9f6a1b177_Traceguids
0x140003531  jz      short loc_140003559
0x140003533  mov     rcx, cs:WPP_GLOBAL_Control
0x14000353a  cmp     [rcx+48h], r14w
0x14000353f  jz      short loc_140003559
0x140003541  mov     rcx, [rcx+40h]
0x140003545  lea     r9d, [r14+36h]
0x140003549  lea     r8d, [r14+1]
0x14000354d  mov     [rsp+0C0h+var_A0], r12
0x140003552  mov     dl, 5
0x140003554  call    WPP_RECORDER_SF_
0x140003559  mov     byte ptr [rdi], 1
0x14000355c  lea     rcx, [rbp+57h+var_60]
0x140003560  mov     rax, cs:WdfFunctions_01015
0x140003567  lea     r9, [rbp+57h+var_78]
0x14000356b  mov     [rsp+0C0h+var_A0], rcx
0x140003570  mov     r8d, 4
0x140003576  mov     rcx, cs:WdfDriverGlobals
0x14000357d  mov     rdx, rsi
0x140003580  mov     rax, [rax+868h]
0x140003587  call    _guard_dispatch_icall
0x14000358c  mov     edi, eax
0x14000358e  test    eax, eax
0x140003590  jns     short loc_1400035D6
0x140003592  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x140003599  jz      loc_140003911
0x14000359f  mov     rcx, [rbp+57h+var_60]
0x1400035a3  mov     r9d, 37h ; '7'
0x1400035a9  mov     [rsp+0C0h+var_88], eax
0x1400035ad  mov     dl, 2
0x1400035af  mov     [rsp+0C0h+var_90], rcx
0x1400035b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400035bb  mov     dword ptr [rsp+0C0h+var_98], 4
0x1400035c3  mov     [rsp+0C0h+var_A0], r12
0x1400035c8  mov     rcx, [rcx+40h]
0x1400035cc  call    WPP_RECORDER_SF_did
0x1400035d1  jmp     loc_140003911
0x1400035d6  mov     rax, [rbp+57h+var_78]
0x1400035da  movzx   ecx, byte ptr [rax]
0x1400035dd  sub     ecx, 1
0x1400035e0  jz      loc_140003666
0x1400035e6  cmp     ecx, 1
0x1400035e9  jnz     loc_140003709
0x1400035ef  cmp     [rbx+38h], r14
0x1400035f3  jz      loc_140003709
0x1400035f9  mov     rax, cs:WdfFunctions_01015
0x140003600  lea     rcx, [rbp+57h+Size]
0x140003604  mov     [rsp+0C0h+var_A0], rcx
0x140003609  lea     r9, [rbp+57h+var_68]
0x14000360d  mov     rcx, cs:WdfDriverGlobals
0x140003614  xor     r8d, r8d
0x140003617  mov     rdx, rsi
0x14000361a  mov     rax, [rax+870h]
0x140003621  call    _guard_dispatch_icall
0x140003626  mov     edi, eax
0x140003628  test    eax, eax
0x14000362a  jns     short loc_140003641
0x14000362c  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x140003633  jz      loc_140003911
0x140003639  mov     r9d, 39h ; '9'
0x14000363f  jmp     short loc_1400036BA
0x140003641  mov     rdx, [rbx+38h]; Src
0x140003645  mov     rcx, [rbp+57h+var_68]; void *
0x140003649  movzx   ebx, word ptr [rdx+2]
0x14000364d  cmp     [rbp+57h+Size], rbx
0x140003651  cmovb   rbx, [rbp+57h+Size]
0x140003656  mov     r8, rbx; Size
0x140003659  call    memmove
0x14000365e  mov     r8, rbx
0x140003661  jmp     loc_1400038F4
0x140003666  mov     rax, [rbx+30h]
0x14000366a  test    rax, rax
0x14000366d  jz      loc_140003709
0x140003673  movzx   r8d, byte ptr [rax]
0x140003677  lea     rcx, [rbp+57h+Size]
0x14000367b  mov     rax, cs:WdfFunctions_01015
0x140003682  lea     r9, [rbp+57h+var_68]
0x140003686  mov     [rsp+0C0h+var_A0], rcx
0x14000368b  mov     rdx, rsi
0x14000368e  mov     rcx, cs:WdfDriverGlobals
0x140003695  mov     rax, [rax+870h]
0x14000369c  call    _guard_dispatch_icall
0x1400036a1  mov     edi, eax
0x1400036a3  test    eax, eax
0x1400036a5  jns     short loc_1400036EB
0x1400036a7  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x1400036ae  jz      loc_140003911
0x1400036b4  mov     r9d, 38h ; '8'
0x1400036ba  mov     rax, [rbp+57h+var_78]
0x1400036be  mov     r8d, 3
0x1400036c4  mov     dword ptr [rsp+0C0h+var_90], edi
0x1400036c8  mov     dl, 2
0x1400036ca  movzx   ecx, byte ptr [rax]
0x1400036cd  mov     dword ptr [rsp+0C0h+var_98], ecx
0x1400036d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400036d8  mov     [rsp+0C0h+var_A0], r12
0x1400036dd  mov     rcx, [rcx+40h]
0x1400036e1  call    WPP_RECORDER_SF_dD
0x1400036e6  jmp     loc_140003911
0x1400036eb  mov     rdx, [rbx+30h]; Src
0x1400036ef  mov     rcx, [rbp+57h+var_68]; void *
0x1400036f3  movzx   r8d, byte ptr [rdx]; Size
0x1400036f7  call    memmove
0x1400036fc  mov     rax, [rbx+30h]
0x140003700  movzx   r8d, byte ptr [rax]
0x140003704  jmp     loc_1400038F4
0x140003709  mov     rax, cs:WdfFunctions_01015
0x140003710  lea     rcx, [rbp+57h+var_80]
0x140003714  mov     rdx, [rbx+8]
0x140003718  lea     r9, [rbp+57h+var_58]
0x14000371c  mov     [rsp+0C0h+var_A0], rcx
0x140003721  xor     r8d, r8d
0x140003724  mov     rcx, cs:WdfDriverGlobals
0x14000372b  mov     rax, [rax+0D38h]
0x140003732  call    _guard_dispatch_icall
0x140003737  test    eax, eax
0x140003739  jns     short loc_140003778
0x14000373b  mov     edi, 0C000009Ah
0x140003740  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x140003747  jz      loc_140003911
0x14000374d  mov     r9d, 3Ah ; ':'
0x140003753  mov     dword ptr [rsp+0C0h+var_98], edi
0x140003757  lea     r8d, [r9-38h]
0x14000375b  mov     dl, r8b
0x14000375e  mov     rcx, cs:WPP_GLOBAL_Control
0x140003765  mov     [rsp+0C0h+var_A0], r12
0x14000376a  mov     rcx, [rcx+40h]
0x14000376e  call    WPP_RECORDER_SF_d
0x140003773  jmp     loc_140003911
0x140003778  mov     rax, cs:WdfFunctions_01015
0x14000377f  lea     rcx, [rbp+57h+Size]
0x140003783  mov     [rsp+0C0h+var_A0], rcx
0x140003788  lea     r9, [rbp+57h+var_68]
0x14000378c  mov     rcx, cs:WdfDriverGlobals
0x140003793  xor     r8d, r8d
0x140003796  mov     rdx, rsi
0x140003799  mov     rax, [rax+870h]
0x1400037a0  call    _guard_dispatch_icall
0x1400037a5  mov     edi, eax
0x1400037a7  test    eax, eax
0x1400037a9  jns     short loc_1400037CC
0x1400037ab  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x1400037b2  jz      loc_140003911
0x1400037b8  mov     r9d, 3Bh ; ';'
0x1400037be  mov     dword ptr [rsp+0C0h+var_98], eax
0x1400037c2  mov     r8d, 3
0x1400037c8  mov     dl, 2
0x1400037ca  jmp     short loc_14000375E
0x1400037cc  mov     rax, [rbp+57h+var_80]
0x1400037d0  mov     rdx, rsi
0x1400037d3  mov     word ptr [rax+2], 0Bh
0x1400037d9  mov     rax, [rbp+57h+var_80]
0x1400037dd  mov     word ptr [rax], 88h
0x1400037e2  mov     rcx, [rbp+57h+var_80]
0x1400037e6  mov     eax, dword ptr [rbp+57h+Size]
0x1400037e9  mov     [rcx+24h], eax
0x1400037ec  mov     rax, [rbp+57h+var_80]
0x1400037f0  mov     [rax+30h], r14
0x1400037f4  mov     rcx, [rbp+57h+var_80]
0x1400037f8  mov     rax, [rbp+57h+var_68]
0x1400037fc  mov     [rcx+28h], rax
0x140003800  mov     rax, [rbp+57h+var_78]
0x140003804  mov     cl, [rax]
0x140003806  mov     rax, [rbp+57h+var_80]
0x14000380a  mov     [rax+83h], cl
0x140003810  mov     rax, [rbp+57h+var_78]
0x140003814  mov     cl, [rax+1]
0x140003817  mov     rax, [rbp+57h+var_80]
0x14000381b  mov     [rax+82h], cl
0x140003821  mov     rax, [rbp+57h+var_78]
0x140003825  movzx   ecx, word ptr [rax+2]
0x140003829  mov     rax, [rbp+57h+var_80]
0x14000382d  mov     [rax+84h], cx
0x140003834  mov     rax, [rbp+57h+var_80]
0x140003838  mov     [rax+38h], r14
0x14000383c  mov     rax, cs:WdfFunctions_01015
0x140003843  mov     rcx, cs:WdfDriverGlobals
0x14000384a  mov     dword ptr [rbp+57h+var_50], 10h
0x140003851  mov     dword ptr [rbp+57h+var_50+4], 1
0x140003858  mov     qword ptr [rbp+57h+var_50+8], 0FFFFFFFFFD050F80h
0x140003860  mov     rax, [rax+830h]
0x140003867  call    _guard_dispatch_icall
0x14000386c  mov     edi, eax
0x14000386e  test    eax, eax
0x140003870  jns     short loc_14000388A
0x140003872  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x140003879  jz      loc_140003911
0x14000387f  mov     r9d, 3Ch ; '<'
0x140003885  jmp     loc_1400037BE
0x14000388a  mov     rdx, rsi
0x14000388d  mov     rcx, rbx
0x140003890  call    WinUSB_IncrementKeepAliveCount
0x140003895  mov     rdx, [rbp+57h+var_80]
0x140003899  lea     r9, [rbp+57h+var_50]
0x14000389d  mov     rax, cs:WdfFunctions_01015
0x1400038a4  xor     r8d, r8d
0x1400038a7  mov     rcx, cs:WdfDriverGlobals
0x1400038ae  mov     [rsp+0C0h+var_A0], rdx
0x1400038b3  mov     rdx, [rbx+8]
0x1400038b7  mov     rax, [rax+0A98h]
0x1400038be  call    _guard_dispatch_icall
0x1400038c3  mov     rdx, rsi
0x1400038c6  mov     rcx, rbx
0x1400038c9  mov     edi, eax
0x1400038cb  call    WinUSB_DecrementKeepAliveCount
0x1400038d0  test    edi, edi
0x1400038d2  jns     short loc_1400038EC
0x1400038d4  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x1400038db  jz      short loc_140003911
0x1400038dd  mov     r9d, 3Dh ; '='
0x1400038e3  mov     dword ptr [rsp+0C0h+var_98], edi
0x1400038e7  jmp     loc_1400037C2
0x1400038ec  mov     rax, [rbp+57h+var_80]
0x1400038f0  mov     r8d, [rax+24h]
0x1400038f4  mov     rax, cs:WdfFunctions_01015
0x1400038fb  mov     rdx, rsi
0x1400038fe  mov     rcx, cs:WdfDriverGlobals
0x140003905  mov     rax, [rax+898h]
0x14000390c  call    _guard_dispatch_icall
0x140003911  mov     rdx, [rbp+57h+var_58]
0x140003915  test    rdx, rdx
0x140003918  jz      short loc_140003934
0x14000391a  mov     rax, cs:WdfFunctions_01015
0x140003921  mov     rcx, cs:WdfDriverGlobals
0x140003928  mov     rax, [rax+680h]
0x14000392f  call    _guard_dispatch_icall
0x140003934  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x14000393b  jz      short loc_140003969
0x14000393d  mov     rcx, cs:WPP_GLOBAL_Control
0x140003944  cmp     [rcx+48h], r14w
0x140003949  jz      short loc_140003969
0x14000394b  mov     rcx, [rcx+40h]
0x14000394f  mov     r9d, 3Eh ; '>'
0x140003955  mov     dword ptr [rsp+0C0h+var_98], edi
0x140003959  mov     dl, 5
0x14000395b  mov     [rsp+0C0h+var_A0], r12
0x140003960  lea     r8d, [r9-3Dh]
0x140003964  call    WPP_RECORDER_SF_d
0x140003969  mov     eax, edi
0x14000396b  mov     rcx, [rbp+57h+var_40]
0x14000396f  xor     rcx, rsp; StackCookie
0x140003972  call    __security_check_cookie
0x140003977  add     rsp, 90h
0x14000397e  pop     r15
0x140003980  pop     r14
0x140003982  pop     r12
0x140003984  pop     rdi
0x140003985  pop     rsi
0x140003986  pop     rbx
0x140003987  pop     rbp
0x140003988  retn
```
