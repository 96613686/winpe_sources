# WinUSB_SetDeviceInterfaceProperties

- ea: `0x14001ba24`
- end: `0x14001bfd4`
- name: `WinUSB_SetDeviceInterfaceProperties`
- size: `1456`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14001b370`

## callees

- `0x140001020`
- `0x1400011c8`
- `0x1400106c0`
- `0x140010700`
- `0x1400108c0`
- `0x14001ba24`

## import_xrefs

- `ntoskrnl!IoSetDeviceInterfacePropertyData` at `0x14001bbb2`
- `ntoskrnl!IoSetDeviceInterfacePropertyData` at `0x14001bc27`
- `ntoskrnl!IoSetDeviceInterfacePropertyData` at `0x14001bca5`
- `ntoskrnl!IoSetDeviceInterfacePropertyData` at `0x14001bcf9`
- `ntoskrnl!IoSetDeviceInterfacePropertyData` at `0x14001bd4d`
- `ntoskrnl!IoSetDeviceInterfacePropertyData` at `0x14001bef8`
- `ntoskrnl!IoSetDeviceInterfacePropertyData` at `0x14001bbb2`
- `ntoskrnl!IoSetDeviceInterfacePropertyData` at `0x14001bc27`
- `ntoskrnl!IoSetDeviceInterfacePropertyData` at `0x14001bca5`
- `ntoskrnl!IoSetDeviceInterfacePropertyData` at `0x14001bcf9`
- `ntoskrnl!IoSetDeviceInterfacePropertyData` at `0x14001bd4d`
- `ntoskrnl!IoSetDeviceInterfacePropertyData` at `0x14001bef8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001bf70`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001bf70`
- `ntoskrnl!ExAllocatePool2` at `0x14001be0b`
- `ntoskrnl!ExAllocatePool2` at `0x14001be0b`

## pseudocode

```c
__int64 __fastcall WinUSB_SetDeviceInterfaceProperties(__int64 a1)
{
  _BYTE *Pool2; // rsi
  int v3; // ebx
  __int64 v4; // r14
  int v5; // eax
  unsigned __int16 v6; // r9
  __int64 v7; // r8
  __int64 v8; // rdx
  unsigned int v9; // r15d
  int v10; // ebx
  __int64 v11; // rdx
  __int64 v12; // rax
  unsigned int v13; // ebx
  unsigned int v14; // r12d
  unsigned int i; // r14d
  __int64 v16; // rdx
  __int64 v17; // rax
  __int64 v18; // rcx
  int v19; // eax
  __int64 v21; // [rsp+28h] [rbp-41h]
  __int64 v22; // [rsp+40h] [rbp-29h] BYREF
  __int128 v23; // [rsp+48h] [rbp-21h] BYREF
  void *Src[2]; // [rsp+58h] [rbp-11h] BYREF
  __int64 v25; // [rsp+68h] [rbp-1h] BYREF
  char v26; // [rsp+70h] [rbp+7h]

  v25 = 0;
  v22 = 0;
  Pool2 = 0;
  v26 = 0;
  v23 = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    WPP_RECORDER_SF_(
      (__int64)WPP_GLOBAL_Control->DeviceExtension,
      5u,
      1u,
      0x2Du,
      (__int64)WPP_dfc8c3b72f8a394434c5f6e53dada427_Traceguids);
  if ( !*(_BYTE *)(a1 + 408)
    || !(*(unsigned __int8 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01015 + 2632))(
          WdfDriverGlobals,
          *(_QWORD *)(a1 + 8)) )
  {
    v3 = 0;
    goto LABEL_37;
  }
  v4 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 1632))(WdfDriverGlobals, a1);
  v3 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, _QWORD, __int64 *))(WdfFunctions_01015 + 2464))(
         WdfDriverGlobals,
         0,
         0,
         &v22);
  if ( v3 >= 0 )
  {
    v3 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, GUID *, _QWORD, __int64))(WdfFunctions_01015 + 632))(
           WdfDriverGlobals,
           v4,
           &GUID_DEVINTERFACE_WINUSB_WINRT,
           0,
           v22);
    if ( v3 >= 0 )
    {
      (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int128 *))(WdfFunctions_01015 + 2472))(
        WdfDriverGlobals,
        v22,
        &v23);
      v5 = IoSetDeviceInterfacePropertyData(&v23, DEVPKEY_Winusb_Device_VID, 0, 0, 5, 2, *(_QWORD *)(a1 + 48) + 8LL);
      v3 = v5;
      if ( v5 < 0 )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_37;
        v6 = 46;
        goto LABEL_12;
      }
      v5 = IoSetDeviceInterfacePropertyData(&v23, DEVPKEY_Winusb_Device_PID, 0, 0, 5, 2, *(_QWORD *)(a1 + 48) + 10LL);
      v3 = v5;
      if ( v5 >= 0 )
      {
        v8 = *(_QWORD *)(a1 + 136);
        LOBYTE(v7) = *(_BYTE *)(v8 + 1);
        (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, __int64, __int64 *))(WdfFunctions_01015 + 2872))(
          WdfDriverGlobals,
          *(_QWORD *)(v8 + 8),
          v7,
          &v25);
        v5 = IoSetDeviceInterfacePropertyData(&v23, DEVPKEY_Winusb_Device_Class, 0, 0, 3, 1, (char *)&v25 + 5);
        v3 = v5;
        if ( v5 >= 0 )
        {
          v5 = IoSetDeviceInterfacePropertyData(&v23, DEVPKEY_Winusb_Device_SubClass, 0, 0, 3, 1, (char *)&v25 + 6);
          v3 = v5;
          if ( v5 >= 0 )
          {
            v5 = IoSetDeviceInterfacePropertyData(&v23, DEVPKEY_Winusb_Device_Protocol, 0, 0, 3, 1, (char *)&v25 + 7);
            v3 = v5;
            if ( v5 >= 0 )
            {
              v9 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01015 + 112))(
                     WdfDriverGlobals,
                     *(_QWORD *)(a1 + 152));
              v10 = 0;
              if ( v9 )
              {
                do
                {
                  v11 = *(_QWORD *)(a1 + 152);
                  *(_OWORD *)Src = 0;
                  v12 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD))(WdfFunctions_01015 + 144))(
                          WdfDriverGlobals,
                          v11,
                          (unsigned int)Pool2);
                  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, void **))(WdfFunctions_01015 + 2472))(
                    WdfDriverGlobals,
                    v12,
                    Src);
                  LODWORD(Pool2) = (_DWORD)Pool2 + 1;
                  v10 += LOWORD(Src[0]) + 2;
                }
                while ( (unsigned int)Pool2 < v9 );
              }
              v13 = v10 + 2;
              Pool2 = (_BYTE *)ExAllocatePool2(256, v13, 1112757591);
              if ( Pool2 )
              {
                v14 = 0;
                for ( i = 0; v14 < v9; i = v18 + 2 )
                {
                  if ( i >= v13 )
                    break;
                  v16 = *(_QWORD *)(a1 + 152);
                  *(_OWORD *)Src = 0;
                  v17 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD))(WdfFunctions_01015 + 144))(
                          WdfDriverGlobals,
                          v16,
                          v14);
                  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, void **))(WdfFunctions_01015 + 2472))(
                    WdfDriverGlobals,
                    v17,
                    Src);
                  memmove(&Pool2[i], Src[1], LOWORD(Src[0]));
                  ++v14;
                  v18 = i + LOWORD(Src[0]);
                  Pool2[v18] = 0;
                }
                Pool2[i] = 0;
                v19 = IoSetDeviceInterfacePropertyData(
                        &v23,
                        DEVPKEY_Winusb_Device_Custom_Interface_GUIDs,
                        0,
                        0,
                        8210,
                        v13,
                        Pool2);
                v3 = v19;
                if ( v19 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                {
                  v6 = 52;
                  LODWORD(v21) = v19;
                  goto LABEL_13;
                }
              }
              else
              {
                v3 = -1073741670;
                if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                {
                  v6 = 51;
                  LODWORD(v21) = -1073741670;
                  goto LABEL_13;
                }
              }
            }
            else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              v6 = 50;
              goto LABEL_12;
            }
          }
          else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            v6 = 49;
            goto LABEL_12;
          }
        }
        else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v6 = 48;
          goto LABEL_12;
        }
      }
      else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v6 = 47;
LABEL_12:
        LODWORD(v21) = v5;
LABEL_13:
        WPP_RECORDER_SF_d(
          (__int64)WPP_GLOBAL_Control->DeviceExtension,
          2u,
          0xEu,
          v6,
          (__int64)WPP_dfc8c3b72f8a394434c5f6e53dada427_Traceguids,
          v21);
      }
    }
  }
LABEL_37:
  if ( v22 )
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS))(WdfFunctions_01015 + 1664))(WdfDriverGlobals);
  if ( Pool2 )
    ExFreePoolWithTag(Pool2, 0x42535557u);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LODWORD(v21) = v3;
    WPP_RECORDER_SF_d(
      (__int64)WPP_GLOBAL_Control->DeviceExtension,
      5u,
      1u,
      0x35u,
      (__int64)WPP_dfc8c3b72f8a394434c5f6e53dada427_Traceguids,
      v21);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x14001ba24  push    rbp
0x14001ba26  push    rbx
0x14001ba27  push    rsi
0x14001ba28  push    rdi
0x14001ba29  push    r12
0x14001ba2b  push    r13
0x14001ba2d  push    r14
0x14001ba2f  push    r15
0x14001ba31  lea     rbp, [rsp-1Fh]
0x14001ba36  sub     rsp, 88h
0x14001ba3d  mov     rax, cs:__security_cookie
0x14001ba44  xor     rax, rsp
0x14001ba47  mov     [rbp+57h+var_48], rax
0x14001ba4b  xor     eax, eax
0x14001ba4d  xorps   xmm0, xmm0
0x14001ba50  xor     r13d, r13d
0x14001ba53  mov     [rbp+57h+var_58], rax
0x14001ba57  mov     [rbp+57h+var_80], r13
0x14001ba5b  mov     esi, r13d
0x14001ba5e  mov     rdi, rcx
0x14001ba61  mov     [rbp+57h+var_50], al
0x14001ba64  movups  [rbp+57h+var_78], xmm0
0x14001ba68  lea     r12, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14001ba6f  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14001ba76  lea     r15, WPP_dfc8c3b72f8a394434c5f6e53dada427_Traceguids
0x14001ba7d  jz      short loc_14001BAA5
0x14001ba7f  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ba86  cmp     [rcx+48h], r13w
0x14001ba8b  jz      short loc_14001BAA5
0x14001ba8d  mov     rcx, [rcx+40h]
0x14001ba91  lea     r9d, [rax+2Dh]
0x14001ba95  lea     r8d, [rax+1]
0x14001ba99  mov     [rsp+0C0h+var_A0], r15
0x14001ba9e  mov     dl, 5
0x14001baa0  call    WPP_RECORDER_SF_
0x14001baa5  cmp     [rdi+198h], r13b
0x14001baac  jnz     short loc_14001BAB6
0x14001baae  mov     ebx, r13d
0x14001bab1  jmp     loc_14001BF40
0x14001bab6  mov     rax, cs:WdfFunctions_01015
0x14001babd  mov     rdx, [rdi+8]
0x14001bac1  mov     rcx, cs:WdfDriverGlobals
0x14001bac8  mov     rax, [rax+0A48h]
0x14001bacf  call    _guard_dispatch_icall
0x14001bad4  test    al, al
0x14001bad6  jz      short loc_14001BAAE
0x14001bad8  mov     rax, cs:WdfFunctions_01015
0x14001badf  mov     rdx, rdi
0x14001bae2  mov     rcx, cs:WdfDriverGlobals
0x14001bae9  mov     rax, [rax+660h]
0x14001baf0  call    _guard_dispatch_icall
0x14001baf5  mov     rcx, cs:WdfDriverGlobals
0x14001bafc  lea     r9, [rbp+57h+var_80]
0x14001bb00  mov     r14, rax
0x14001bb03  xor     r8d, r8d
0x14001bb06  mov     rax, cs:WdfFunctions_01015
0x14001bb0d  xor     edx, edx
0x14001bb0f  mov     rax, [rax+9A0h]
0x14001bb16  call    _guard_dispatch_icall
0x14001bb1b  mov     ebx, eax
0x14001bb1d  test    eax, eax
0x14001bb1f  js      loc_14001BF40
0x14001bb25  mov     rcx, [rbp+57h+var_80]
0x14001bb29  lea     r8, GUID_DEVINTERFACE_WINUSB_WINRT
0x14001bb30  mov     rax, cs:WdfFunctions_01015
0x14001bb37  xor     r9d, r9d
0x14001bb3a  mov     [rsp+0C0h+var_A0], rcx
0x14001bb3f  mov     rdx, r14
0x14001bb42  mov     rcx, cs:WdfDriverGlobals
0x14001bb49  mov     rax, [rax+278h]
0x14001bb50  call    _guard_dispatch_icall
0x14001bb55  mov     ebx, eax
0x14001bb57  test    eax, eax
0x14001bb59  js      loc_14001BF40
0x14001bb5f  mov     rax, cs:WdfFunctions_01015
0x14001bb66  lea     r8, [rbp+57h+var_78]
0x14001bb6a  mov     rdx, [rbp+57h+var_80]
0x14001bb6e  mov     rcx, cs:WdfDriverGlobals
0x14001bb75  mov     rax, [rax+9A8h]
0x14001bb7c  call    _guard_dispatch_icall
0x14001bb81  mov     rax, [rdi+30h]
0x14001bb85  lea     rdx, DEVPKEY_Winusb_Device_VID
0x14001bb8c  add     rax, 8
0x14001bb90  lea     rcx, [rbp+57h+var_78]
0x14001bb94  mov     [rsp+0C0h+var_90], rax
0x14001bb99  mov     r14d, 2
0x14001bb9f  mov     dword ptr [rsp+0C0h+var_98], r14d
0x14001bba4  xor     r9d, r9d
0x14001bba7  xor     r8d, r8d
0x14001bbaa  mov     dword ptr [rsp+0C0h+var_A0], 5
0x14001bbb2  call    cs:__imp_IoSetDeviceInterfacePropertyData
0x14001bbb9  nop     dword ptr [rax+rax+00h]
0x14001bbbe  mov     ebx, eax
0x14001bbc0  test    eax, eax
0x14001bbc2  jns     short loc_14001BBFC
0x14001bbc4  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x14001bbcb  jz      loc_14001BF40
0x14001bbd1  lea     r9d, [r14+2Ch]
0x14001bbd5  mov     dword ptr [rsp+0C0h+var_98], eax
0x14001bbd9  mov     dl, r14b
0x14001bbdc  mov     rcx, cs:WPP_GLOBAL_Control
0x14001bbe3  mov     r8d, 0Eh
0x14001bbe9  mov     [rsp+0C0h+var_A0], r15
0x14001bbee  mov     rcx, [rcx+40h]
0x14001bbf2  call    WPP_RECORDER_SF_d
0x14001bbf7  jmp     loc_14001BF40
0x14001bbfc  mov     rax, [rdi+30h]
0x14001bc00  lea     rdx, DEVPKEY_Winusb_Device_PID
0x14001bc07  add     rax, 0Ah
0x14001bc0b  lea     rcx, [rbp+57h+var_78]
0x14001bc0f  mov     [rsp+0C0h+var_90], rax
0x14001bc14  xor     r9d, r9d
0x14001bc17  mov     dword ptr [rsp+0C0h+var_98], r14d
0x14001bc1c  xor     r8d, r8d
0x14001bc1f  mov     dword ptr [rsp+0C0h+var_A0], 5
0x14001bc27  call    cs:__imp_IoSetDeviceInterfacePropertyData
0x14001bc2e  nop     dword ptr [rax+rax+00h]
0x14001bc33  mov     ebx, eax
0x14001bc35  test    eax, eax
0x14001bc37  jns     short loc_14001BC4E
0x14001bc39  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x14001bc40  jz      loc_14001BF40
0x14001bc46  mov     r9d, 2Fh ; '/'
0x14001bc4c  jmp     short loc_14001BBD5
0x14001bc4e  mov     rdx, [rdi+88h]
0x14001bc55  lea     r9, [rbp+57h+var_58]
0x14001bc59  mov     rax, cs:WdfFunctions_01015
0x14001bc60  mov     rcx, cs:WdfDriverGlobals
0x14001bc67  mov     r8b, [rdx+1]
0x14001bc6b  mov     rdx, [rdx+8]
0x14001bc6f  mov     rax, [rax+0B38h]
0x14001bc76  call    _guard_dispatch_icall
0x14001bc7b  lea     rax, [rbp+57h+var_58+5]
0x14001bc7f  xor     r9d, r9d
0x14001bc82  mov     [rsp+0C0h+var_90], rax
0x14001bc87  lea     rdx, DEVPKEY_Winusb_Device_Class
0x14001bc8e  mov     dword ptr [rsp+0C0h+var_98], 1
0x14001bc96  lea     rcx, [rbp+57h+var_78]
0x14001bc9a  xor     r8d, r8d
0x14001bc9d  mov     dword ptr [rsp+0C0h+var_A0], 3
0x14001bca5  call    cs:__imp_IoSetDeviceInterfacePropertyData
0x14001bcac  nop     dword ptr [rax+rax+00h]
0x14001bcb1  mov     ebx, eax
0x14001bcb3  test    eax, eax
0x14001bcb5  jns     short loc_14001BCCF
0x14001bcb7  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x14001bcbe  jz      loc_14001BF40
0x14001bcc4  mov     r9d, 30h ; '0'
0x14001bcca  jmp     loc_14001BBD5
0x14001bccf  lea     rax, [rbp+57h+var_58+6]
0x14001bcd3  xor     r9d, r9d
0x14001bcd6  mov     [rsp+0C0h+var_90], rax
0x14001bcdb  lea     rdx, DEVPKEY_Winusb_Device_SubClass
0x14001bce2  mov     dword ptr [rsp+0C0h+var_98], 1
0x14001bcea  lea     rcx, [rbp+57h+var_78]
0x14001bcee  xor     r8d, r8d
0x14001bcf1  mov     dword ptr [rsp+0C0h+var_A0], 3
0x14001bcf9  call    cs:__imp_IoSetDeviceInterfacePropertyData
0x14001bd00  nop     dword ptr [rax+rax+00h]
0x14001bd05  mov     ebx, eax
0x14001bd07  test    eax, eax
0x14001bd09  jns     short loc_14001BD23
0x14001bd0b  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x14001bd12  jz      loc_14001BF40
0x14001bd18  mov     r9d, 31h ; '1'
0x14001bd1e  jmp     loc_14001BBD5
0x14001bd23  lea     rax, [rbp+57h+var_58+7]
0x14001bd27  xor     r9d, r9d
0x14001bd2a  mov     [rsp+0C0h+var_90], rax
0x14001bd2f  lea     rdx, DEVPKEY_Winusb_Device_Protocol
0x14001bd36  mov     dword ptr [rsp+0C0h+var_98], 1
0x14001bd3e  lea     rcx, [rbp+57h+var_78]
0x14001bd42  xor     r8d, r8d
0x14001bd45  mov     dword ptr [rsp+0C0h+var_A0], 3
0x14001bd4d  call    cs:__imp_IoSetDeviceInterfacePropertyData
0x14001bd54  nop     dword ptr [rax+rax+00h]
0x14001bd59  mov     ebx, eax
0x14001bd5b  test    eax, eax
0x14001bd5d  jns     short loc_14001BD77
0x14001bd5f  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x14001bd66  jz      loc_14001BF40
0x14001bd6c  mov     r9d, 32h ; '2'
0x14001bd72  jmp     loc_14001BBD5
0x14001bd77  mov     rax, cs:WdfFunctions_01015
0x14001bd7e  mov     rdx, [rdi+98h]
0x14001bd85  mov     rcx, cs:WdfDriverGlobals
0x14001bd8c  mov     rax, [rax+70h]
0x14001bd90  call    _guard_dispatch_icall
0x14001bd95  mov     r15d, eax
0x14001bd98  mov     ebx, r13d
0x14001bd9b  test    eax, eax
0x14001bd9d  jz      short loc_14001BDFB
0x14001bd9f  mov     rax, cs:WdfFunctions_01015
0x14001bda6  xorps   xmm0, xmm0
0x14001bda9  mov     rdx, [rdi+98h]
0x14001bdb0  mov     r8d, esi
0x14001bdb3  mov     rcx, cs:WdfDriverGlobals
0x14001bdba  movups  xmmword ptr [rbp+57h+Src], xmm0
0x14001bdbe  mov     rax, [rax+90h]
0x14001bdc5  call    _guard_dispatch_icall
0x14001bdca  mov     rcx, cs:WdfDriverGlobals
0x14001bdd1  lea     r8, [rbp+57h+Src]
0x14001bdd5  mov     rdx, rax
0x14001bdd8  mov     rax, cs:WdfFunctions_01015
0x14001bddf  mov     rax, [rax+9A8h]
0x14001bde6  call    _guard_dispatch_icall
0x14001bdeb  movzx   eax, word ptr [rbp+57h+Src]
0x14001bdef  inc     esi
0x14001bdf1  add     eax, r14d
0x14001bdf4  add     ebx, eax
0x14001bdf6  cmp     esi, r15d
0x14001bdf9  jb      short loc_14001BD9F
0x14001bdfb  add     ebx, r14d
0x14001bdfe  mov     ecx, 100h
0x14001be03  mov     edx, ebx
0x14001be05  mov     r8d, 42535557h
0x14001be0b  call    cs:__imp_ExAllocatePool2
0x14001be12  nop     dword ptr [rax+rax+00h]
0x14001be17  mov     rsi, rax
0x14001be1a  test    rax, rax
0x14001be1d  jnz     short loc_14001BE45
0x14001be1f  mov     ebx, 0C000009Ah
0x14001be24  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x14001be2b  lea     r15, WPP_dfc8c3b72f8a394434c5f6e53dada427_Traceguids
0x14001be32  jz      loc_14001BF40
0x14001be38  lea     r9d, [rax+33h]
0x14001be3c  mov     dword ptr [rsp+0C0h+var_98], ebx
0x14001be40  jmp     loc_14001BBD9
0x14001be45  mov     r12d, r13d
0x14001be48  mov     r14d, r13d
0x14001be4b  test    r15d, r15d
0x14001be4e  jz      short loc_14001BECF
0x14001be50  cmp     r14d, ebx
0x14001be53  jnb     short loc_14001BECF
0x14001be55  mov     rax, cs:WdfFunctions_01015
0x14001be5c  xorps   xmm0, xmm0
0x14001be5f  mov     rdx, [rdi+98h]
0x14001be66  mov     r8d, r12d
0x14001be69  mov     rcx, cs:WdfDriverGlobals
0x14001be70  movups  xmmword ptr [rbp+57h+Src], xmm0
0x14001be74  mov     rax, [rax+90h]
0x14001be7b  call    _guard_dispatch_icall
0x14001be80  mov     rcx, cs:WdfFunctions_01015
0x14001be87  lea     r8, [rbp+57h+Src]
0x14001be8b  mov     rdx, rax
0x14001be8e  mov     r9, [rcx+9A8h]
0x14001be95  mov     rcx, cs:WdfDriverGlobals
0x14001be9c  mov     rax, r9
0x14001be9f  call    _guard_dispatch_icall
0x14001bea4  movzx   r8d, word ptr [rbp+57h+Src]; Size
0x14001bea9  mov     rdx, [rbp+57h+Src+8]; Src
0x14001bead  mov     ecx, r14d
0x14001beb0  add     rcx, rsi; void *
0x14001beb3  call    memmove
0x14001beb8  movzx   ecx, word ptr [rbp+57h+Src]
0x14001bebc  inc     r12d
0x14001bebf  add     ecx, r14d
0x14001bec2  mov     [rcx+rsi], r13b
0x14001bec6  lea     r14d, [rcx+2]
0x14001beca  cmp     r12d, r15d
0x14001becd  jb      short loc_14001BE50
0x14001becf  mov     eax, r14d
0x14001bed2  lea     rdx, DEVPKEY_Winusb_Device_Custom_Interface_GUIDs
0x14001bed9  mov     [rsp+0C0h+var_90], rsi
0x14001bede  lea     rcx, [rbp+57h+var_78]
0x14001bee2  mov     dword ptr [rsp+0C0h+var_98], ebx
0x14001bee6  xor     r9d, r9d
0x14001bee9  xor     r8d, r8d
0x14001beec  mov     dword ptr [rsp+0C0h+var_A0], 2012h
0x14001bef4  mov     [rax+rsi], r13b
0x14001bef8  call    cs:__imp_IoSetDeviceInterfacePropertyData
0x14001beff  nop     dword ptr [rax+rax+00h]
0x14001bf04  mov     ebx, eax
0x14001bf06  test    eax, eax
0x14001bf08  jns     short loc_14001BF32
0x14001bf0a  lea     r12, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14001bf11  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14001bf18  lea     r15, WPP_dfc8c3b72f8a394434c5f6e53dada427_Traceguids
0x14001bf1f  jz      short loc_14001BF40
0x14001bf21  mov     r9d, 34h ; '4'
0x14001bf27  mov     dword ptr [rsp+0C0h+var_98], eax
0x14001bf2b  mov     dl, 2
0x14001bf2d  jmp     loc_14001BBDC
0x14001bf32  lea     r12, WPP_RECORDER_INITIALIZED
0x14001bf39  lea     r15, WPP_dfc8c3b72f8a394434c5f6e53dada427_Traceguids
0x14001bf40  mov     rdx, [rbp+57h+var_80]
0x14001bf44  test    rdx, rdx
0x14001bf47  jz      short loc_14001BF63
0x14001bf49  mov     rax, cs:WdfFunctions_01015
0x14001bf50  mov     rcx, cs:WdfDriverGlobals
0x14001bf57  mov     rax, [rax+680h]
0x14001bf5e  call    _guard_dispatch_icall
0x14001bf63  test    rsi, rsi
0x14001bf66  jz      short loc_14001BF7C
0x14001bf68  mov     edx, 42535557h; Tag
0x14001bf6d  mov     rcx, rsi; P
0x14001bf70  call    cs:__imp_ExFreePoolWithTag
0x14001bf77  nop     dword ptr [rax+rax+00h]
0x14001bf7c  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x14001bf83  jz      short loc_14001BFB1
  ... truncated ...
```
