# HUBREG_WriteStringToDeviceHardwareKey

- ea: `0x14008b20c`
- end: `0x14008b34d`
- name: `HUBREG_WriteStringToDeviceHardwareKey`
- size: `321`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path`

## callers

- `0x140080590`

## callees

- `0x1400024b8`
- `0x140045570`
- `0x14008b20c`

## pseudocode

```c
__int64 __fastcall HUBREG_WriteStringToDeviceHardwareKey(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rdx
  __int64 v6; // rax
  int v7; // edx
  int v8; // ebx
  int v9; // r9d
  __int64 v11; // [rsp+28h] [rbp-20h]
  __int64 v12; // [rsp+58h] [rbp+10h] BYREF

  v12 = a2;
  v3 = *(_QWORD *)(a1 + 16);
  v12 = 0;
  v6 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 1632))(WdfDriverGlobals, v3);
  v8 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64, __int64, _QWORD, __int64 *))(WdfFunctions_01015 + 384))(
         WdfDriverGlobals,
         v6,
         1,
         131078,
         0,
         &v12);
  if ( v8 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_8;
    v9 = 98;
    goto LABEL_7;
  }
  v8 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *, __int64))(WdfFunctions_01015 + 1960))(
         WdfDriverGlobals,
         v12,
         &g_SymbolicName,
         a3);
  if ( v8 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v9 = 99;
LABEL_7:
    LODWORD(v11) = v8;
    LOBYTE(v7) = 2;
    WPP_RECORDER_SF_d(
      *(_QWORD *)(*(_QWORD *)(a1 + 8) + 1432LL),
      v7,
      5,
      v9,
      (__int64)WPP_fe827790944537bbfef1c01f2ab82bc9_Traceguids,
      v11);
  }
LABEL_8:
  if ( v12 )
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS))(WdfFunctions_01015 + 1848))(WdfDriverGlobals);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x14008b20c  mov     rax, rsp
0x14008b20f  mov     [rax+8], rbx
0x14008b213  mov     [rax+18h], rsi
0x14008b217  mov     [rax+10h], rdx
0x14008b21b  push    rdi
0x14008b21c  sub     rsp, 40h
0x14008b220  mov     rdx, [rcx+10h]
0x14008b224  mov     rdi, rcx
0x14008b227  mov     rcx, cs:WdfDriverGlobals
0x14008b22e  mov     rsi, r8
0x14008b231  mov     qword ptr [rax+10h], 0
0x14008b239  mov     rax, cs:WdfFunctions_01015
0x14008b240  mov     rax, [rax+660h]
0x14008b247  call    _guard_dispatch_icall
0x14008b24c  mov     rdx, cs:WdfFunctions_01015
0x14008b253  lea     rcx, [rsp+48h+arg_8]
0x14008b258  mov     [rsp+48h+var_20], rcx
0x14008b25d  mov     r9d, 20006h
0x14008b263  mov     rcx, cs:WdfDriverGlobals
0x14008b26a  mov     r8d, 1
0x14008b270  mov     [rsp+48h+var_28], 0
0x14008b279  mov     r10, [rdx+180h]
0x14008b280  mov     rdx, rax
0x14008b283  mov     rax, r10
0x14008b286  call    _guard_dispatch_icall
0x14008b28b  mov     ebx, eax
0x14008b28d  test    eax, eax
0x14008b28f  jns     short loc_14008B2A9
0x14008b291  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14008b298  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14008b29f  jz      short loc_14008B316
0x14008b2a1  mov     r9d, 62h ; 'b'
0x14008b2a7  jmp     short loc_14008B2EE
0x14008b2a9  mov     rax, cs:WdfFunctions_01015
0x14008b2b0  lea     r8, g_SymbolicName
0x14008b2b7  mov     rdx, [rsp+48h+arg_8]
0x14008b2bc  mov     r9, rsi
0x14008b2bf  mov     rcx, cs:WdfDriverGlobals
0x14008b2c6  mov     rax, [rax+7A8h]
0x14008b2cd  call    _guard_dispatch_icall
0x14008b2d2  mov     ebx, eax
0x14008b2d4  test    eax, eax
0x14008b2d6  jns     short loc_14008B316
0x14008b2d8  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14008b2df  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14008b2e6  jz      short loc_14008B316
0x14008b2e8  mov     r9d, 63h ; 'c'
0x14008b2ee  mov     rcx, [rdi+8]
0x14008b2f2  lea     rax, WPP_fe827790944537bbfef1c01f2ab82bc9_Traceguids
0x14008b2f9  mov     dword ptr [rsp+48h+var_20], ebx
0x14008b2fd  mov     r8d, 5
0x14008b303  mov     dl, 2
0x14008b305  mov     [rsp+48h+var_28], rax
0x14008b30a  mov     rcx, [rcx+598h]
0x14008b311  call    WPP_RECORDER_SF_d
0x14008b316  mov     rdx, [rsp+48h+arg_8]
0x14008b31b  test    rdx, rdx
0x14008b31e  jz      short loc_14008B33A
0x14008b320  mov     rax, cs:WdfFunctions_01015
0x14008b327  mov     rcx, cs:WdfDriverGlobals
0x14008b32e  mov     rax, [rax+738h]
0x14008b335  call    _guard_dispatch_icall
0x14008b33a  mov     rsi, [rsp+48h+arg_10]
0x14008b33f  mov     eax, ebx
0x14008b341  mov     rbx, [rsp+48h+arg_0]
0x14008b346  add     rsp, 40h
0x14008b34a  pop     rdi
0x14008b34b  retn
```
