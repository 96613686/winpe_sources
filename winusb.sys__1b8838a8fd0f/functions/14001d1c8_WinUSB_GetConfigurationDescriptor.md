# WinUSB_GetConfigurationDescriptor

- ea: `0x14001d1c8`
- end: `0x14001d39f`
- name: `WinUSB_GetConfigurationDescriptor`
- size: `471`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x14001b370`

## callees

- `0x140001020`
- `0x1400011c8`
- `0x140010700`
- `0x14001d1c8`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14001d38e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001d38e`
- `ntoskrnl!ExAllocatePool2` at `0x14001d2e1`
- `ntoskrnl!ExAllocatePool2` at `0x14001d2e1`

## pseudocode

```c
__int64 __fastcall WinUSB_GetConfigurationDescriptor(__int64 a1)
{
  __int64 v2; // rdx
  int v3; // eax
  int v4; // edx
  int v5; // ebx
  void *v6; // rdi
  __int64 Pool2; // rax
  int v9; // edx
  int v10; // eax
  unsigned __int16 v11; // [rsp+70h] [rbp+8h] BYREF

  v11 = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      1,
      13,
      (__int64)WPP_a773a5ed6750358f3f4fbf06697d601c_Traceguids);
  v2 = *(_QWORD *)(a1 + 8);
  v11 = 9;
  v3 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD, unsigned __int16 *))(WdfFunctions_01015 + 2600))(
         WdfDriverGlobals,
         v2,
         0,
         &v11);
  v5 = v3;
  if ( v3 != -1073741789 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v4) = 2;
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        v4,
        3,
        14,
        (__int64)WPP_a773a5ed6750358f3f4fbf06697d601c_Traceguids,
        v3);
    }
    if ( v5 < 0 )
      goto LABEL_10;
    v6 = 0;
    goto LABEL_9;
  }
  Pool2 = ExAllocatePool2(64, v11, 1112757591);
  v6 = (void *)Pool2;
  if ( Pool2 )
  {
    v10 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, __int64, unsigned __int16 *))(WdfFunctions_01015 + 2600))(
            WdfDriverGlobals,
            *(_QWORD *)(a1 + 8),
            Pool2,
            &v11);
    v5 = v10;
    if ( v10 < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v4) = 2;
        WPP_RECORDER_SF_d(
          WPP_GLOBAL_Control->DeviceExtension,
          v4,
          3,
          16,
          (__int64)WPP_a773a5ed6750358f3f4fbf06697d601c_Traceguids,
          v10);
      }
      ExFreePoolWithTag(v6, 0);
      goto LABEL_10;
    }
LABEL_9:
    *(_QWORD *)(a1 + 56) = v6;
    goto LABEL_10;
  }
  v5 = -1073741670;
  if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    return (unsigned int)v5;
  LOBYTE(v9) = 2;
  WPP_RECORDER_SF_d(
    WPP_GLOBAL_Control->DeviceExtension,
    v9,
    3,
    15,
    (__int64)WPP_a773a5ed6750358f3f4fbf06697d601c_Traceguids,
    154);
LABEL_10:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(v4) = 5;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v4,
      1,
      17,
      (__int64)WPP_a773a5ed6750358f3f4fbf06697d601c_Traceguids,
      v5);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x14001d1c8  push    rbx
0x14001d1ca  push    rbp
0x14001d1cb  push    rsi
0x14001d1cc  push    rdi
0x14001d1cd  push    r14
0x14001d1cf  push    r15
0x14001d1d1  sub     rsp, 38h
0x14001d1d5  xor     ebp, ebp
0x14001d1d7  mov     rsi, rcx
0x14001d1da  mov     [rsp+68h+arg_0], bp
0x14001d1df  lea     r14, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14001d1e6  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14001d1ed  lea     r15, WPP_a773a5ed6750358f3f4fbf06697d601c_Traceguids
0x14001d1f4  jz      short loc_14001D21B
0x14001d1f6  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d1fd  cmp     [rcx+48h], bp
0x14001d201  jz      short loc_14001D21B
0x14001d203  mov     rcx, [rcx+40h]
0x14001d207  lea     r9d, [rbp+0Dh]
0x14001d20b  lea     r8d, [rbp+1]
0x14001d20f  mov     [rsp+68h+var_48], r15
0x14001d214  mov     dl, 5
0x14001d216  call    WPP_RECORDER_SF_
0x14001d21b  mov     rdx, [rsi+8]
0x14001d21f  lea     r9, [rsp+68h+arg_0]
0x14001d224  mov     rcx, cs:WdfDriverGlobals
0x14001d22b  mov     eax, 9
0x14001d230  mov     [rsp+68h+arg_0], ax
0x14001d235  xor     r8d, r8d
0x14001d238  mov     rax, cs:WdfFunctions_01015
0x14001d23f  mov     rax, [rax+0A28h]
0x14001d246  call    _guard_dispatch_icall
0x14001d24b  mov     ebx, eax
0x14001d24d  cmp     eax, 0C0000023h
0x14001d252  jz      short loc_14001D2D1
0x14001d254  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x14001d25b  jz      short loc_14001D282
0x14001d25d  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d264  mov     r9d, 0Eh
0x14001d26a  mov     [rsp+68h+var_40], eax
0x14001d26e  mov     dl, 2
0x14001d270  mov     [rsp+68h+var_48], r15
0x14001d275  mov     rcx, [rcx+40h]
0x14001d279  lea     r8d, [r9-0Bh]
0x14001d27d  call    WPP_RECORDER_SF_d
0x14001d282  test    ebx, ebx
0x14001d284  js      short loc_14001D28D
0x14001d286  mov     rdi, rbp
0x14001d289  mov     [rsi+38h], rdi
0x14001d28d  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x14001d294  jz      short loc_14001D2C1
0x14001d296  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d29d  cmp     [rcx+48h], bp
0x14001d2a1  jz      short loc_14001D2C1
0x14001d2a3  mov     rcx, [rcx+40h]
0x14001d2a7  mov     r9d, 11h
0x14001d2ad  mov     [rsp+68h+var_40], ebx
0x14001d2b1  mov     dl, 5
0x14001d2b3  mov     [rsp+68h+var_48], r15
0x14001d2b8  lea     r8d, [r9-10h]
0x14001d2bc  call    WPP_RECORDER_SF_d
0x14001d2c1  mov     eax, ebx
0x14001d2c3  add     rsp, 38h
0x14001d2c7  pop     r15
0x14001d2c9  pop     r14
0x14001d2cb  pop     rdi
0x14001d2cc  pop     rsi
0x14001d2cd  pop     rbp
0x14001d2ce  pop     rbx
0x14001d2cf  retn
0x14001d2d1  movzx   edx, [rsp+68h+arg_0]
0x14001d2d6  mov     ecx, 40h ; '@'
0x14001d2db  mov     r8d, 42535557h
0x14001d2e1  call    cs:__imp_ExAllocatePool2
0x14001d2e8  nop     dword ptr [rax+rax+00h]
0x14001d2ed  mov     rdi, rax
0x14001d2f0  test    rax, rax
0x14001d2f3  jnz     short loc_14001D32B
0x14001d2f5  mov     ebx, 0C000009Ah
0x14001d2fa  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x14001d301  jz      short loc_14001D2C1
0x14001d303  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d30a  lea     r9d, [rax+0Fh]
0x14001d30e  mov     [rsp+68h+var_40], ebx
0x14001d312  lea     r8d, [rax+3]
0x14001d316  mov     dl, 2
0x14001d318  mov     [rsp+68h+var_48], r15
0x14001d31d  mov     rcx, [rcx+40h]
0x14001d321  call    WPP_RECORDER_SF_d
0x14001d326  jmp     loc_14001D28D
0x14001d32b  mov     rax, cs:WdfFunctions_01015
0x14001d332  lea     r9, [rsp+68h+arg_0]
0x14001d337  mov     rdx, [rsi+8]
0x14001d33b  mov     r8, rdi
0x14001d33e  mov     rcx, cs:WdfDriverGlobals
0x14001d345  mov     rax, [rax+0A28h]
0x14001d34c  call    _guard_dispatch_icall
0x14001d351  mov     ebx, eax
0x14001d353  test    eax, eax
0x14001d355  jns     loc_14001D289
0x14001d35b  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x14001d362  jz      short loc_14001D389
0x14001d364  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d36b  mov     r9d, 10h
0x14001d371  mov     [rsp+68h+var_40], eax
0x14001d375  mov     dl, 2
0x14001d377  mov     [rsp+68h+var_48], r15
0x14001d37c  mov     rcx, [rcx+40h]
0x14001d380  lea     r8d, [r9-0Dh]
0x14001d384  call    WPP_RECORDER_SF_d
0x14001d389  xor     edx, edx; Tag
0x14001d38b  mov     rcx, rdi; P
0x14001d38e  call    cs:__imp_ExFreePoolWithTag
0x14001d395  nop     dword ptr [rax+rax+00h]
0x14001d39a  jmp     loc_14001D28D
```
