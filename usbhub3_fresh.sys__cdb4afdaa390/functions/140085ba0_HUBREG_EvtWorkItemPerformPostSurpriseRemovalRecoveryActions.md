# HUBREG_EvtWorkItemPerformPostSurpriseRemovalRecoveryActions

- ea: `0x140085ba0`
- end: `0x140085eda`
- name: `HUBREG_EvtWorkItemPerformPostSurpriseRemovalRecoveryActions`
- size: `826`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x1400024b8`
- `0x140045570`
- `0x140085ba0`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140085cda`
- `ntoskrnl!RtlInitUnicodeString` at `0x140085cf1`
- `ntoskrnl!RtlInitUnicodeString` at `0x140085cda`
- `ntoskrnl!RtlInitUnicodeString` at `0x140085cf1`

## string_xrefs

- `0x140085ce6`: `BootPathSurpriseRemovalCount`
- `0x140085cc7`: `\Registry\Machine\System\CurrentControlSet\Control\Usb\Ceip`

## pseudocode

```c
__int64 __fastcall HUBREG_EvtWorkItemPerformPostSurpriseRemovalRecoveryActions(__int64 a1)
{
  __int64 v2; // rbx
  __int64 v3; // rax
  unsigned int v4; // edi
  int v5; // ebx
  __int64 v6; // rax
  int v7; // edx
  int v8; // ebx
  __int64 v9; // rax
  int v10; // edx
  int v11; // r9d
  __int64 v13; // [rsp+28h] [rbp-48h]
  struct _UNICODE_STRING v14; // [rsp+50h] [rbp-20h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-10h] BYREF
  unsigned int v16; // [rsp+98h] [rbp+28h] BYREF
  __int64 v17; // [rsp+A0h] [rbp+30h] BYREF

  v17 = 0;
  v16 = 0;
  DestinationString = 0;
  v14 = 0;
  v2 = *(_QWORD *)((*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, WDFDRIVER__ *, __int64 *))(WdfFunctions_01015 + 1616))(
                     WdfDriverGlobals,
                     WdfDriverGlobals->Driver,
                     off_14006B2C0)
                 + 80);
  v3 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 3016))(WdfDriverGlobals, v2);
  v4 = 1;
  if ( (*(unsigned __int8 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64))(WdfFunctions_01015 + 2968))(
         WdfDriverGlobals,
         v3,
         1) )
  {
    v5 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD, _QWORD))(WdfFunctions_01015 + 3024))(
           WdfDriverGlobals,
           v2,
           0,
           0);
    if ( v5 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v6 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, WDFDRIVER__ *, __int64 *))(WdfFunctions_01015 + 1616))(
             WdfDriverGlobals,
             WdfDriverGlobals->Driver,
             off_14006B2C0);
      LOBYTE(v7) = 2;
      WPP_RECORDER_SF_d(*(_QWORD *)(v6 + 64), v7, 2, 24, (__int64)WPP_b48bfb8efb7f3208dce8b8d3052aa366_Traceguids, v5);
    }
  }
  v17 = 0;
  RtlInitUnicodeString(&DestinationString, L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\Usb\\Ceip");
  RtlInitUnicodeString(&v14, L"BootPathSurpriseRemovalCount");
  v8 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, struct _UNICODE_STRING *, __int64, _DWORD, _QWORD, _QWORD, __int64 *))(WdfFunctions_01015 + 1840))(
         WdfDriverGlobals,
         0,
         &DestinationString,
         131103,
         0,
         0,
         0,
         &v17);
  if ( v8 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_14;
    v9 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, WDFDRIVER__ *, __int64 *))(WdfFunctions_01015 + 1616))(
           WdfDriverGlobals,
           WdfDriverGlobals->Driver,
           off_14006B2C0);
    v11 = 116;
    goto LABEL_13;
  }
  v8 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, struct _UNICODE_STRING *, unsigned int *))(WdfFunctions_01015 + 1920))(
         WdfDriverGlobals,
         v17,
         &v14,
         &v16);
  if ( v8 >= 0 )
  {
    v4 = v16 + 1;
LABEL_10:
    v16 = v4;
    v8 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, struct _UNICODE_STRING *, _QWORD))(WdfFunctions_01015 + 1968))(
           WdfDriverGlobals,
           v17,
           &v14,
           v4);
    if ( v8 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v9 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, WDFDRIVER__ *, __int64 *))(WdfFunctions_01015 + 1616))(
             WdfDriverGlobals,
             WdfDriverGlobals->Driver,
             off_14006B2C0);
      v11 = 118;
LABEL_13:
      LODWORD(v13) = v8;
      LOBYTE(v10) = 2;
      WPP_RECORDER_SF_d(
        *(_QWORD *)(v9 + 64),
        v10,
        2,
        v11,
        (__int64)WPP_fe827790944537bbfef1c01f2ab82bc9_Traceguids,
        v13);
      goto LABEL_14;
    }
    goto LABEL_14;
  }
  if ( v8 == -1073741772 )
    goto LABEL_10;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v9 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, WDFDRIVER__ *, __int64 *))(WdfFunctions_01015 + 1616))(
           WdfDriverGlobals,
           WdfDriverGlobals->Driver,
           off_14006B2C0);
    v11 = 117;
    goto LABEL_13;
  }
LABEL_14:
  if ( v17 )
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS))(WdfFunctions_01015 + 1848))(WdfDriverGlobals);
  return (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 1664))(WdfDriverGlobals, a1);
}

```

## disassembly

```asm
0x140085ba0  mov     [rsp-18h+arg_0], rbx
0x140085ba5  mov     [rsp-18h+arg_18], rsi
0x140085baa  push    rbp
0x140085bab  push    rdi
0x140085bac  push    r12
0x140085bae  mov     rbp, rsp
0x140085bb1  sub     rsp, 70h
0x140085bb5  mov     rax, cs:WdfFunctions_01015
0x140085bbc  mov     rsi, rcx
0x140085bbf  mov     rcx, cs:WdfDriverGlobals
0x140085bc6  xorps   xmm0, xmm0
0x140085bc9  mov     r8, cs:off_14006B2C0
0x140085bd0  xorps   xmm1, xmm1
0x140085bd3  mov     [rbp+arg_10], 0
0x140085bdb  mov     [rbp+arg_8], 0
0x140085be2  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140085be6  movups  xmmword ptr [rbp+var_20.Length], xmm1
0x140085bea  mov     rdx, [rcx]
0x140085bed  mov     rax, [rax+650h]
0x140085bf4  call    _guard_dispatch_icall
0x140085bf9  mov     rcx, cs:WdfDriverGlobals
0x140085c00  mov     rbx, [rax+50h]
0x140085c04  mov     rax, cs:WdfFunctions_01015
0x140085c0b  mov     rdx, rbx
0x140085c0e  mov     rax, [rax+0BC8h]
0x140085c15  call    _guard_dispatch_icall
0x140085c1a  mov     rcx, cs:WdfFunctions_01015
0x140085c21  mov     rdx, rax
0x140085c24  mov     edi, 1
0x140085c29  mov     r8d, edi
0x140085c2c  mov     r9, [rcx+0B98h]
0x140085c33  mov     rcx, cs:WdfDriverGlobals
0x140085c3a  mov     rax, r9
0x140085c3d  call    _guard_dispatch_icall
0x140085c42  lea     r12, WPP_RECORDER_INITIALIZED
0x140085c49  test    al, al
0x140085c4b  jz      short loc_140085CC7
0x140085c4d  mov     rax, cs:WdfFunctions_01015
0x140085c54  xor     r9d, r9d
0x140085c57  mov     rcx, cs:WdfDriverGlobals
0x140085c5e  xor     r8d, r8d
0x140085c61  mov     rdx, rbx
0x140085c64  mov     rax, [rax+0BD0h]
0x140085c6b  call    _guard_dispatch_icall
0x140085c70  mov     ebx, eax
0x140085c72  test    eax, eax
0x140085c74  jns     short loc_140085CC7
0x140085c76  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x140085c7d  jz      short loc_140085CC7
0x140085c7f  mov     rcx, cs:WdfFunctions_01015
0x140085c86  mov     r8, cs:off_14006B2C0
0x140085c8d  mov     rax, [rcx+650h]
0x140085c94  mov     rcx, cs:WdfDriverGlobals
0x140085c9b  mov     rdx, [rcx]
0x140085c9e  call    _guard_dispatch_icall
0x140085ca3  lea     rcx, WPP_b48bfb8efb7f3208dce8b8d3052aa366_Traceguids
0x140085caa  mov     dword ptr [rsp+70h+var_48], ebx
0x140085cae  lea     r8d, [rdi+1]
0x140085cb2  mov     [rsp+70h+var_50], rcx
0x140085cb7  lea     r9d, [rdi+17h]
0x140085cbb  mov     dl, r8b
0x140085cbe  mov     rcx, [rax+40h]
0x140085cc2  call    WPP_RECORDER_SF_d
0x140085cc7  lea     rdx, aRegistryMachin_0; "\\Registry\\Machine\\System\\CurrentCon"...
0x140085cce  mov     [rbp+arg_10], 0
0x140085cd6  lea     rcx, [rbp+DestinationString]; DestinationString
0x140085cda  call    cs:__imp_RtlInitUnicodeString
0x140085ce1  nop     dword ptr [rax+rax+00h]
0x140085ce6  lea     rdx, aBootpathsurpri; "BootPathSurpriseRemovalCount"
0x140085ced  lea     rcx, [rbp+var_20]; DestinationString
0x140085cf1  call    cs:__imp_RtlInitUnicodeString
0x140085cf8  nop     dword ptr [rax+rax+00h]
0x140085cfd  mov     rax, cs:WdfFunctions_01015
0x140085d04  lea     rcx, [rbp+arg_10]
0x140085d08  mov     [rsp+70h+var_38], rcx
0x140085d0d  lea     r8, [rbp+DestinationString]
0x140085d11  mov     rcx, cs:WdfDriverGlobals
0x140085d18  mov     r9d, 2001Fh
0x140085d1e  mov     [rsp+70h+var_40], 0
0x140085d27  xor     edx, edx
0x140085d29  mov     rax, [rax+730h]
0x140085d30  mov     [rsp+70h+var_48], 0
0x140085d39  mov     dword ptr [rsp+70h+var_50], 0
0x140085d41  call    _guard_dispatch_icall
0x140085d46  mov     ebx, eax
0x140085d48  test    eax, eax
0x140085d4a  jns     short loc_140085D88
0x140085d4c  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x140085d53  jz      loc_140085E40
0x140085d59  mov     rcx, cs:WdfFunctions_01015
0x140085d60  mov     r8, cs:off_14006B2C0
0x140085d67  mov     rax, [rcx+650h]
0x140085d6e  mov     rcx, cs:WdfDriverGlobals
0x140085d75  mov     rdx, [rcx]
0x140085d78  call    _guard_dispatch_icall
0x140085d7d  mov     r9d, 74h ; 't'
0x140085d83  jmp     loc_140085E1E
0x140085d88  mov     rax, cs:WdfFunctions_01015
0x140085d8f  lea     r9, [rbp+arg_8]
0x140085d93  mov     rdx, [rbp+arg_10]
0x140085d97  lea     r8, [rbp+var_20]
0x140085d9b  mov     rcx, cs:WdfDriverGlobals
0x140085da2  mov     rax, [rax+780h]
0x140085da9  call    _guard_dispatch_icall
0x140085dae  mov     ebx, eax
0x140085db0  test    eax, eax
0x140085db2  js      loc_140085E96
0x140085db8  mov     edi, [rbp+arg_8]
0x140085dbb  inc     edi
0x140085dbd  mov     rax, cs:WdfFunctions_01015
0x140085dc4  lea     r8, [rbp+var_20]
0x140085dc8  mov     rdx, [rbp+arg_10]
0x140085dcc  mov     r9d, edi
0x140085dcf  mov     rcx, cs:WdfDriverGlobals
0x140085dd6  mov     [rbp+arg_8], edi
0x140085dd9  mov     rax, [rax+7B0h]
0x140085de0  call    _guard_dispatch_icall
0x140085de5  mov     ebx, eax
0x140085de7  test    eax, eax
0x140085de9  jns     short loc_140085E40
0x140085deb  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x140085df2  jz      short loc_140085E40
0x140085df4  mov     rcx, cs:WdfFunctions_01015
0x140085dfb  mov     r8, cs:off_14006B2C0
0x140085e02  mov     rax, [rcx+650h]
0x140085e09  mov     rcx, cs:WdfDriverGlobals
0x140085e10  mov     rdx, [rcx]
0x140085e13  call    _guard_dispatch_icall
0x140085e18  mov     r9d, 76h ; 'v'
0x140085e1e  lea     rcx, WPP_fe827790944537bbfef1c01f2ab82bc9_Traceguids
0x140085e25  mov     dword ptr [rsp+70h+var_48], ebx
0x140085e29  mov     r8d, 2
0x140085e2f  mov     [rsp+70h+var_50], rcx
0x140085e34  mov     rcx, [rax+40h]
0x140085e38  mov     dl, r8b
0x140085e3b  call    WPP_RECORDER_SF_d
0x140085e40  mov     rdx, [rbp+arg_10]
0x140085e44  test    rdx, rdx
0x140085e47  jz      short loc_140085E63
0x140085e49  mov     rax, cs:WdfFunctions_01015
0x140085e50  mov     rcx, cs:WdfDriverGlobals
0x140085e57  mov     rax, [rax+738h]
0x140085e5e  call    _guard_dispatch_icall
0x140085e63  mov     rax, cs:WdfFunctions_01015
0x140085e6a  mov     rdx, rsi
0x140085e6d  mov     rcx, cs:WdfDriverGlobals
0x140085e74  mov     rax, [rax+680h]
0x140085e7b  call    _guard_dispatch_icall
0x140085e80  lea     r11, [rsp+70h+var_s0]
0x140085e85  mov     rbx, [r11+20h]
0x140085e89  mov     rsi, [r11+38h]
0x140085e8d  mov     rsp, r11
0x140085e90  pop     r12
0x140085e92  pop     rdi
0x140085e93  pop     rbp
0x140085e94  retn
0x140085e96  cmp     ebx, 0C0000034h
0x140085e9c  jz      loc_140085DBD
0x140085ea2  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x140085ea9  jz      short loc_140085E40
0x140085eab  mov     rax, cs:WdfFunctions_01015
0x140085eb2  mov     rcx, cs:WdfDriverGlobals
0x140085eb9  mov     r8, cs:off_14006B2C0
0x140085ec0  mov     rax, [rax+650h]
0x140085ec7  mov     rdx, [rcx]
0x140085eca  call    _guard_dispatch_icall
0x140085ecf  mov     r9d, 75h ; 'u'
0x140085ed5  jmp     loc_140085E1E
```
