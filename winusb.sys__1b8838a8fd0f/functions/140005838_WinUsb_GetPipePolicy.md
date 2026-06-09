# WinUsb_GetPipePolicy

- ea: `0x140005838`
- end: `0x140005fdf`
- name: `WinUsb_GetPipePolicy`
- size: `1959`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _BYTE *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting`

## callers

- `0x1400026d0`

## callees

- `0x140001020`
- `0x1400011c8`
- `0x14000193c`
- `0x140001a4c`
- `0x140001c30`
- `0x140005838`
- `0x14000751c`
- `0x1400075d8`
- `0x140010700`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400059eb`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400059eb`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005f79`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005f79`

## pseudocode

```c
__int64 __fastcall WinUsb_GetPipePolicy(__int64 a1, __int64 a2, __int64 a3, _BYTE *a4)
{
  __int64 v7; // rax
  PWDF_DRIVER_GLOBALS v8; // rcx
  int v9; // eax
  int v10; // edx
  int v11; // r8d
  unsigned int v12; // ebx
  int v13; // edx
  unsigned __int8 v14; // cl
  __int64 v15; // r8
  char v16; // r14
  __int64 v17; // rdx
  __int64 v18; // rdx
  __int64 v19; // rdi
  KIRQL v20; // r13
  int v21; // edx
  int v22; // r9d
  int v23; // ecx
  int v24; // eax
  char v25; // cl
  int v26; // ecx
  char v28; // [rsp+28h] [rbp-28h]
  char v29; // [rsp+30h] [rbp-20h]
  unsigned __int8 *v30; // [rsp+40h] [rbp-10h] BYREF
  __int64 v31; // [rsp+48h] [rbp-8h] BYREF
  _BYTE *v32; // [rsp+98h] [rbp+48h] BYREF
  __int64 v33; // [rsp+A8h] [rbp+58h] BYREF

  v30 = 0;
  v31 = 0;
  v32 = 0;
  v33 = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      1,
      98,
      (__int64)WPP_1ea4bda7f8b23cafb6f0c7d9f6a1b177_Traceguids);
  v7 = WdfFunctions_01015;
  v8 = WdfDriverGlobals;
  *a4 = 1;
  v9 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64, unsigned __int8 **, __int64 *))(v7 + 2152))(
         v8,
         a3,
         12,
         &v30,
         &v31);
  v12 = v9;
  if ( v9 >= 0 )
  {
    v14 = *(_BYTE *)(a1 + 128);
    v15 = *v30;
    if ( (unsigned __int8)v15 >= v14 )
    {
      v12 = -1073741811;
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return v12;
      WPP_RECORDER_SF_ddd(
        WPP_GLOBAL_Control->DeviceExtension,
        v10,
        v15,
        100,
        (__int64)WPP_1ea4bda7f8b23cafb6f0c7d9f6a1b177_Traceguids,
        v15,
        v14);
      goto LABEL_94;
    }
    v16 = v30[1];
    v17 = (v16 & 0xF) + 16LL;
    if ( v16 >= 0 )
      v17 = v30[1] & 0xF;
    v18 = 35 * v15 + v17;
    v19 = *(_QWORD *)(*(_QWORD *)(a1 + 136) + 8 * v18 + 24);
    if ( !v19 )
    {
      v12 = -1073741811;
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return v12;
      LOBYTE(v18) = 2;
      WPP_RECORDER_SF_dD(
        WPP_GLOBAL_Control->DeviceExtension,
        v18,
        3,
        101,
        (__int64)WPP_1ea4bda7f8b23cafb6f0c7d9f6a1b177_Traceguids,
        v16,
        13);
      goto LABEL_94;
    }
    v20 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v19 + 40));
    v21 = *((_DWORD *)v30 + 1);
    if ( v21 == 1 )
    {
      if ( WinUSB_IsInterruptOrBulkOutPipe(v19) )
      {
        v24 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64, _BYTE **, __int64 *))(WdfFunctions_01015 + 2160))(
                WdfDriverGlobals,
                a3,
                1,
                &v32,
                &v33);
        v12 = v24;
        if ( v24 >= 0 )
        {
          *v32 = *(_BYTE *)(v19 + 20);
          goto LABEL_92;
        }
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_93;
        v22 = 105;
      }
      else
      {
        LOBYTE(v24) = 13;
        v12 = -1073741811;
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_93;
        v22 = 104;
      }
    }
    else
    {
      switch ( *((_DWORD *)v30 + 1) )
      {
        case 2:
          v23 = *(_DWORD *)(v19 + 12);
          if ( (unsigned int)(v23 - 3) > 1 )
          {
            v12 = -1073741811;
            if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              goto LABEL_93;
            v22 = 106;
LABEL_30:
            v29 = 13;
            v28 = v23;
LABEL_31:
            LOBYTE(v21) = 2;
            goto LABEL_26;
          }
          v24 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64, _BYTE **, __int64 *))(WdfFunctions_01015 + 2160))(
                  WdfDriverGlobals,
                  a3,
                  1,
                  &v32,
                  &v33);
          v12 = v24;
          if ( v24 >= 0 )
          {
            v25 = *(_BYTE *)(v19 + 21);
            goto LABEL_37;
          }
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            goto LABEL_93;
          v22 = 107;
          break;
        case 3:
          if ( *(_DWORD *)(v19 + 12) == 2 )
          {
            v12 = -1073741811;
            if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              goto LABEL_93;
            v29 = 13;
            v22 = 108;
            v28 = 2;
            goto LABEL_31;
          }
          v24 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64, _BYTE **, __int64 *))(WdfFunctions_01015 + 2160))(
                  WdfDriverGlobals,
                  a3,
                  4,
                  &v32,
                  &v33);
          v12 = v24;
          if ( v24 >= 0 )
          {
            v26 = *(_DWORD *)(v19 + 24);
            goto LABEL_42;
          }
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            goto LABEL_93;
          v22 = 109;
          break;
        case 4:
          if ( WinUSB_IsInterruptOrBulkInPipe(v19) )
          {
            v24 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64, _BYTE **, __int64 *))(WdfFunctions_01015 + 2160))(
                    WdfDriverGlobals,
                    a3,
                    1,
                    &v32,
                    &v33);
            v12 = v24;
            if ( v24 >= 0 )
            {
              v25 = *(_BYTE *)(v19 + 28);
              goto LABEL_37;
            }
            if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              goto LABEL_93;
            v22 = 111;
          }
          else
          {
            LOBYTE(v24) = 13;
            v12 = -1073741811;
            if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              goto LABEL_93;
            v22 = 110;
          }
          break;
        case 5:
          if ( WinUSB_IsInterruptOrBulkInPipe(v19) )
          {
            v24 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64, _BYTE **, __int64 *))(WdfFunctions_01015 + 2160))(
                    WdfDriverGlobals,
                    a3,
                    1,
                    &v32,
                    &v33);
            v12 = v24;
            if ( v24 >= 0 )
            {
              v25 = *(_BYTE *)(v19 + 29);
              goto LABEL_37;
            }
            if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              goto LABEL_93;
            v22 = 113;
          }
          else
          {
            LOBYTE(v24) = 13;
            v12 = -1073741811;
            if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              goto LABEL_93;
            v22 = 112;
          }
          break;
        case 6:
          if ( WinUSB_IsInterruptOrBulkInPipe(v19) )
          {
            v24 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64, _BYTE **, __int64 *))(WdfFunctions_01015 + 2160))(
                    WdfDriverGlobals,
                    a3,
                    1,
                    &v32,
                    &v33);
            v12 = v24;
            if ( v24 >= 0 )
            {
              v25 = *(_BYTE *)(v19 + 30);
              goto LABEL_37;
            }
            if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              goto LABEL_93;
            v22 = 115;
          }
          else
          {
            LOBYTE(v24) = 13;
            v12 = -1073741811;
            if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              goto LABEL_93;
            v22 = 114;
          }
          break;
        case 7:
          v23 = *(_DWORD *)(v19 + 12);
          if ( (unsigned int)(v23 - 3) > 1 )
          {
            v12 = -1073741811;
            if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              goto LABEL_93;
            v22 = 116;
            goto LABEL_30;
          }
          v24 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64, _BYTE **, __int64 *))(WdfFunctions_01015 + 2160))(
                  WdfDriverGlobals,
                  a3,
                  1,
                  &v32,
                  &v33);
          v12 = v24;
          if ( v24 < 0 )
          {
            if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              goto LABEL_93;
            v22 = 117;
            break;
          }
          v25 = *(_BYTE *)(v19 + 31);
LABEL_37:
          *v32 = v25;
LABEL_92:
          (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64))(WdfFunctions_01015 + 2200))(
            WdfDriverGlobals,
            a3,
            1);
          goto LABEL_93;
        case 8:
          v24 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64, _BYTE **, __int64 *))(WdfFunctions_01015 + 2160))(
                  WdfDriverGlobals,
                  a3,
                  4,
                  &v32,
                  &v33);
          v12 = v24;
          if ( v24 < 0 )
          {
            if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              goto LABEL_93;
            v22 = 120;
            break;
          }
          v26 = *(_DWORD *)(v19 + 112);
LABEL_42:
          *(_DWORD *)v32 = v26;
          (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64))(WdfFunctions_01015 + 2200))(
            WdfDriverGlobals,
            a3,
            4);
          goto LABEL_93;
        case 9:
          v23 = *(_DWORD *)(v19 + 12);
          if ( (unsigned int)(v23 - 3) > 1 )
          {
            v12 = -1073741811;
            if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              goto LABEL_93;
            v22 = 118;
            goto LABEL_30;
          }
          v24 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64, _BYTE **, __int64 *))(WdfFunctions_01015 + 2160))(
                  WdfDriverGlobals,
                  a3,
                  1,
                  &v32,
                  &v33);
          v12 = v24;
          if ( v24 < 0 )
          {
            if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              goto LABEL_93;
            v22 = 119;
            break;
          }
          v25 = *(_BYTE *)(v19 + 32);
          goto LABEL_37;
        default:
          v12 = -1073741811;
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
LABEL_93:
            KeReleaseSpinLock((PKSPIN_LOCK)(v19 + 40), v20);
            goto LABEL_94;
          }
          v22 = 121;
          v29 = 13;
          v28 = v21;
          LOBYTE(v21) = 3;
LABEL_26:
          WPP_RECORDER_SF_dD(
            WPP_GLOBAL_Control->DeviceExtension,
            v21,
            3,
            v22,
            (__int64)WPP_1ea4bda7f8b23cafb6f0c7d9f6a1b177_Traceguids,
            v28,
            v29);
          goto LABEL_93;
      }
    }
    v29 = v24;
    v28 = v16;
    goto LABEL_31;
  }
  if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    return v12;
  LOBYTE(v10) = 2;
  WPP_RECORDER_SF_did(
    WPP_GLOBAL_Control->DeviceExtension,
    v10,
    v11,
    99,
    (__int64)WPP_1ea4bda7f8b23cafb6f0c7d9f6a1b177_Traceguids,
    12,
    v31,
    v9);
LABEL_94:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(v13) = 5;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v13,
      1,
      122,
      (__int64)WPP_1ea4bda7f8b23cafb6f0c7d9f6a1b177_Traceguids,
      v12);
  }
  return v12;
}

```

## disassembly

```asm
0x140005838  mov     [rsp-38h+arg_0], rbx
0x14000583d  mov     [rsp-38h+arg_8], rdx
0x140005842  push    rbp
0x140005843  push    rsi
0x140005844  push    rdi
0x140005845  push    r12
0x140005847  push    r13
0x140005849  push    r14
0x14000584b  push    r15
0x14000584d  mov     rbp, rsp
0x140005850  sub     rsp, 50h
0x140005854  xor     r13d, r13d
0x140005857  mov     rbx, r9
0x14000585a  mov     [rbp+var_10], r13
0x14000585e  mov     rsi, r8
0x140005861  mov     [rbp+var_8], r13
0x140005865  mov     rdi, rcx
0x140005868  mov     [rbp+arg_8], r13
0x14000586c  mov     [rbp+arg_18], r13
0x140005870  lea     r15, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140005877  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14000587e  lea     r12, WPP_1ea4bda7f8b23cafb6f0c7d9f6a1b177_Traceguids
0x140005885  jz      short loc_1400058AD
0x140005887  mov     rcx, cs:WPP_GLOBAL_Control
0x14000588e  cmp     [rcx+48h], r13w
0x140005893  jz      short loc_1400058AD
0x140005895  mov     rcx, [rcx+40h]
0x140005899  lea     r9d, [r13+62h]
0x14000589d  lea     r8d, [r13+1]
0x1400058a1  mov     [rsp+50h+var_30], r12
0x1400058a6  mov     dl, 5
0x1400058a8  call    WPP_RECORDER_SF_
0x1400058ad  mov     rax, cs:WdfFunctions_01015
0x1400058b4  lea     rcx, [rbp+var_8]
0x1400058b8  mov     [rsp+50h+var_30], rcx
0x1400058bd  lea     r9, [rbp+var_10]
0x1400058c1  mov     rcx, cs:WdfDriverGlobals
0x1400058c8  mov     r14d, 0Ch
0x1400058ce  mov     r8d, r14d
0x1400058d1  mov     byte ptr [rbx], 1
0x1400058d4  mov     rax, [rax+868h]
0x1400058db  mov     rdx, rsi
0x1400058de  call    _guard_dispatch_icall
0x1400058e3  mov     ebx, eax
0x1400058e5  test    eax, eax
0x1400058e7  jns     short loc_140005928
0x1400058e9  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x1400058f0  jz      loc_140005FC4
0x1400058f6  mov     rcx, [rbp+var_8]
0x1400058fa  lea     r9d, [r14+57h]
0x1400058fe  mov     [rsp+50h+var_18], eax
0x140005902  mov     dl, 2
0x140005904  mov     [rsp+50h+var_20], rcx
0x140005909  mov     rcx, cs:WPP_GLOBAL_Control
0x140005910  mov     dword ptr [rsp+50h+var_28], r14d
0x140005915  mov     [rsp+50h+var_30], r12
0x14000591a  mov     rcx, [rcx+40h]
0x14000591e  call    WPP_RECORDER_SF_did
0x140005923  jmp     loc_140005F8F
0x140005928  mov     rax, [rbp+var_10]
0x14000592c  movzx   ecx, byte ptr [rdi+80h]
0x140005933  movzx   r8d, byte ptr [rax]
0x140005937  cmp     r8b, cl
0x14000593a  jb      short loc_140005977
0x14000593c  mov     ebx, 0C000000Dh
0x140005941  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x140005948  jz      loc_140005FC4
0x14000594e  mov     dword ptr [rsp+50h+var_20], ecx
0x140005952  mov     r9d, 64h ; 'd'
0x140005958  mov     rcx, cs:WPP_GLOBAL_Control
0x14000595f  mov     dword ptr [rsp+50h+var_28], r8d
0x140005964  mov     [rsp+50h+var_30], r12
0x140005969  mov     rcx, [rcx+40h]
0x14000596d  call    WPP_RECORDER_SF_ddd
0x140005972  jmp     loc_140005F8F
0x140005977  movzx   ecx, byte ptr [rax+1]
0x14000597b  mov     r14d, ecx
0x14000597e  mov     eax, r14d
0x140005981  and     eax, 0Fh
0x140005984  test    cl, cl
0x140005986  lea     rdx, [rax+10h]
0x14000598a  cmovns  rdx, rax
0x14000598e  mov     rax, [rdi+88h]
0x140005995  imul    rcx, r8, 23h ; '#'
0x140005999  add     rdx, rcx
0x14000599c  mov     rdi, [rax+rdx*8+18h]
0x1400059a1  test    rdi, rdi
0x1400059a4  jnz     short loc_1400059E7
0x1400059a6  mov     eax, 0C000000Dh
0x1400059ab  mov     ebx, eax
0x1400059ad  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x1400059b4  jz      loc_140005FC4
0x1400059ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1400059c1  lea     r9d, [rdi+65h]
0x1400059c5  mov     dword ptr [rsp+50h+var_20], eax
0x1400059c9  lea     r8d, [rdi+3]
0x1400059cd  mov     dword ptr [rsp+50h+var_28], r14d
0x1400059d2  mov     dl, 2
0x1400059d4  mov     [rsp+50h+var_30], r12
0x1400059d9  mov     rcx, [rcx+40h]
0x1400059dd  call    WPP_RECORDER_SF_dD
0x1400059e2  jmp     loc_140005F8F
0x1400059e7  lea     rcx, [rdi+28h]; SpinLock
0x1400059eb  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400059f2  nop     dword ptr [rax+rax+00h]
0x1400059f7  mov     rcx, [rbp+var_10]
0x1400059fb  mov     r13b, al
0x1400059fe  mov     edx, [rcx+4]
0x140005a01  mov     ecx, edx
0x140005a03  sub     ecx, 1
0x140005a06  jz      loc_140005ED1
0x140005a0c  sub     ecx, 1
0x140005a0f  jz      loc_140005E51
0x140005a15  sub     ecx, 1
0x140005a18  jz      loc_140005DC0
0x140005a1e  sub     ecx, 1
0x140005a21  jz      loc_140005D3F
0x140005a27  sub     ecx, 1
0x140005a2a  jz      loc_140005CBE
0x140005a30  sub     ecx, 1
0x140005a33  jz      loc_140005C3D
0x140005a39  sub     ecx, 1
0x140005a3c  jz      loc_140005BBD
0x140005a42  sub     ecx, 1
0x140005a45  jz      loc_140005B33
0x140005a4b  cmp     ecx, 1
0x140005a4e  jz      short loc_140005A9A
0x140005a50  mov     eax, 0C000000Dh
0x140005a55  mov     ebx, eax
0x140005a57  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x140005a5e  jz      loc_140005F72
0x140005a64  mov     r9d, 79h ; 'y'
0x140005a6a  mov     dword ptr [rsp+50h+var_20], eax
0x140005a6e  mov     dword ptr [rsp+50h+var_28], edx
0x140005a72  lea     r8d, [r9-76h]
0x140005a76  mov     dl, r8b
0x140005a79  mov     rcx, cs:WPP_GLOBAL_Control
0x140005a80  lea     rax, WPP_1ea4bda7f8b23cafb6f0c7d9f6a1b177_Traceguids
0x140005a87  mov     [rsp+50h+var_30], rax
0x140005a8c  mov     rcx, [rcx+40h]
0x140005a90  call    WPP_RECORDER_SF_dD
0x140005a95  jmp     loc_140005F72
0x140005a9a  mov     ecx, [rdi+0Ch]
0x140005a9d  lea     eax, [rcx-3]
0x140005aa0  cmp     eax, 1
0x140005aa3  jbe     short loc_140005AD1
0x140005aa5  mov     eax, 0C000000Dh
0x140005aaa  mov     ebx, eax
0x140005aac  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x140005ab3  jz      loc_140005F72
0x140005ab9  mov     r9d, 76h ; 'v'
0x140005abf  mov     dword ptr [rsp+50h+var_20], eax
0x140005ac3  mov     dword ptr [rsp+50h+var_28], ecx
0x140005ac7  mov     r8d, 3
0x140005acd  mov     dl, 2
0x140005acf  jmp     short loc_140005A79
0x140005ad1  mov     rax, cs:WdfFunctions_01015
0x140005ad8  lea     rcx, [rbp+arg_18]
0x140005adc  mov     [rsp+50h+var_30], rcx
0x140005ae1  lea     r9, [rbp+arg_8]
0x140005ae5  mov     rcx, cs:WdfDriverGlobals
0x140005aec  mov     r8d, 1
0x140005af2  mov     rdx, rsi
0x140005af5  mov     rax, [rax+870h]
0x140005afc  call    _guard_dispatch_icall
0x140005b01  mov     ebx, eax
0x140005b03  test    eax, eax
0x140005b05  jns     short loc_140005B25
0x140005b07  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x140005b0e  jz      loc_140005F72
0x140005b14  mov     r9d, 77h ; 'w'
0x140005b1a  mov     dword ptr [rsp+50h+var_20], eax
0x140005b1e  mov     dword ptr [rsp+50h+var_28], r14d
0x140005b23  jmp     short loc_140005AC7
0x140005b25  mov     cl, [rdi+20h]
0x140005b28  mov     rax, [rbp+arg_8]
0x140005b2c  mov     [rax], cl
0x140005b2e  jmp     loc_140005F4F
0x140005b33  mov     rax, cs:WdfFunctions_01015
0x140005b3a  lea     rcx, [rbp+arg_18]
0x140005b3e  mov     [rsp+50h+var_30], rcx
0x140005b43  lea     r9, [rbp+arg_8]
0x140005b47  mov     rcx, cs:WdfDriverGlobals
0x140005b4e  mov     r15d, 4
0x140005b54  mov     r8d, r15d
0x140005b57  mov     rdx, rsi
0x140005b5a  mov     rax, [rax+870h]
0x140005b61  call    _guard_dispatch_icall
0x140005b66  mov     ebx, eax
0x140005b68  test    eax, eax
0x140005b6a  jns     short loc_140005B88
0x140005b6c  lea     r15, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140005b73  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140005b7a  jz      loc_140005F72
0x140005b80  mov     r9d, 78h ; 'x'
0x140005b86  jmp     short loc_140005B1A
0x140005b88  mov     ecx, [rdi+70h]
0x140005b8b  mov     rax, [rbp+arg_8]
0x140005b8f  mov     r8, r15
0x140005b92  mov     rdx, rsi
0x140005b95  mov     [rax], ecx
0x140005b97  mov     rax, cs:WdfFunctions_01015
0x140005b9e  mov     rcx, cs:WdfDriverGlobals
0x140005ba5  mov     rax, [rax+898h]
0x140005bac  call    _guard_dispatch_icall
0x140005bb1  lea     r15, WPP_RECORDER_INITIALIZED
0x140005bb8  jmp     loc_140005F72
0x140005bbd  mov     ecx, [rdi+0Ch]
0x140005bc0  lea     eax, [rcx-3]
0x140005bc3  cmp     eax, 1
0x140005bc6  jbe     short loc_140005BE7
0x140005bc8  mov     eax, 0C000000Dh
0x140005bcd  mov     ebx, eax
0x140005bcf  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x140005bd6  jz      loc_140005F72
0x140005bdc  mov     r9d, 74h ; 't'
0x140005be2  jmp     loc_140005ABF
0x140005be7  mov     rax, cs:WdfFunctions_01015
0x140005bee  lea     rcx, [rbp+arg_18]
0x140005bf2  mov     [rsp+50h+var_30], rcx
0x140005bf7  lea     r9, [rbp+arg_8]
0x140005bfb  mov     rcx, cs:WdfDriverGlobals
0x140005c02  mov     r8d, 1
0x140005c08  mov     rdx, rsi
0x140005c0b  mov     rax, [rax+870h]
0x140005c12  call    _guard_dispatch_icall
0x140005c17  mov     ebx, eax
0x140005c19  test    eax, eax
0x140005c1b  jns     short loc_140005C35
0x140005c1d  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x140005c24  jz      loc_140005F72
0x140005c2a  mov     r9d, 75h ; 'u'
0x140005c30  jmp     loc_140005B1A
0x140005c35  mov     cl, [rdi+1Fh]
0x140005c38  jmp     loc_140005B28
0x140005c3d  mov     rcx, rdi
0x140005c40  call    WinUSB_IsInterruptOrBulkInPipe
0x140005c45  test    al, al
0x140005c47  jnz     short loc_140005C68
0x140005c49  mov     eax, 0C000000Dh
0x140005c4e  mov     ebx, eax
0x140005c50  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x140005c57  jz      loc_140005F72
0x140005c5d  mov     r9d, 72h ; 'r'
0x140005c63  jmp     loc_140005B1A
0x140005c68  mov     rax, cs:WdfFunctions_01015
0x140005c6f  lea     rcx, [rbp+arg_18]
0x140005c73  mov     [rsp+50h+var_30], rcx
0x140005c78  lea     r9, [rbp+arg_8]
0x140005c7c  mov     rcx, cs:WdfDriverGlobals
0x140005c83  mov     r8d, 1
0x140005c89  mov     rdx, rsi
0x140005c8c  mov     rax, [rax+870h]
0x140005c93  call    _guard_dispatch_icall
0x140005c98  mov     ebx, eax
0x140005c9a  test    eax, eax
0x140005c9c  jns     short loc_140005CB6
0x140005c9e  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x140005ca5  jz      loc_140005F72
0x140005cab  mov     r9d, 73h ; 's'
0x140005cb1  jmp     loc_140005B1A
0x140005cb6  mov     cl, [rdi+1Eh]
0x140005cb9  jmp     loc_140005B28
0x140005cbe  mov     rcx, rdi
0x140005cc1  call    WinUSB_IsInterruptOrBulkInPipe
0x140005cc6  test    al, al
0x140005cc8  jnz     short loc_140005CE9
0x140005cca  mov     eax, 0C000000Dh
0x140005ccf  mov     ebx, eax
0x140005cd1  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x140005cd8  jz      loc_140005F72
0x140005cde  mov     r9d, 70h ; 'p'
0x140005ce4  jmp     loc_140005B1A
0x140005ce9  mov     rax, cs:WdfFunctions_01015
0x140005cf0  lea     rcx, [rbp+arg_18]
0x140005cf4  mov     [rsp+50h+var_30], rcx
0x140005cf9  lea     r9, [rbp+arg_8]
0x140005cfd  mov     rcx, cs:WdfDriverGlobals
0x140005d04  mov     r8d, 1
0x140005d0a  mov     rdx, rsi
0x140005d0d  mov     rax, [rax+870h]
0x140005d14  call    _guard_dispatch_icall
0x140005d19  mov     ebx, eax
0x140005d1b  test    eax, eax
0x140005d1d  jns     short loc_140005D37
0x140005d1f  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x140005d26  jz      loc_140005F72
0x140005d2c  mov     r9d, 71h ; 'q'
0x140005d32  jmp     loc_140005B1A
0x140005d37  mov     cl, [rdi+1Dh]
0x140005d3a  jmp     loc_140005B28
0x140005d3f  mov     rcx, rdi
0x140005d42  call    WinUSB_IsInterruptOrBulkInPipe
0x140005d47  test    al, al
0x140005d49  jnz     short loc_140005D6A
0x140005d4b  mov     eax, 0C000000Dh
0x140005d50  mov     ebx, eax
0x140005d52  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x140005d59  jz      loc_140005F72
0x140005d5f  mov     r9d, 6Eh ; 'n'
  ... truncated ...
```
