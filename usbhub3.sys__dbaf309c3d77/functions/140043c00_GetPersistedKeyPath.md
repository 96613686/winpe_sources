# GetPersistedKeyPath

- ea: `0x140043c00`
- end: `0x140043db1`
- name: `GetPersistedKeyPath`
- size: `433`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x140044054`

## callees

- `0x1400024b8`
- `0x140029714`
- `0x140043c00`

## import_xrefs

- `ntoskrnl!RtlGetPersistedStateLocation` at `0x140043c46`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x140043d3a`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x140043c46`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x140043d3a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140043d8d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140043d8d`
- `ntoskrnl!ExAllocatePool2` at `0x140043caf`
- `ntoskrnl!ExAllocatePool2` at `0x140043caf`

## string_xrefs

- `0x140043c20`: `\Registry\Machine\SYSTEM\CurrentControlSet\Control\USB`
- `0x140043d15`: `\Registry\Machine\SYSTEM\CurrentControlSet\Control\USB`

## pseudocode

```c
__int64 __fastcall GetPersistedKeyPath(_QWORD *a1)
{
  int v2; // edx
  int PersistedStateLocation; // ebx
  int v4; // edx
  void *Pool2; // rdi
  int v6; // edx
  unsigned int v8; // [rsp+58h] [rbp+10h] BYREF

  v8 = 0;
  PersistedStateLocation = RtlGetPersistedStateLocation(
                             L"USB",
                             0,
                             L"\\Registry\\Machine\\SYSTEM\\CurrentControlSet\\Control\\USB",
                             0,
                             0,
                             0,
                             &v8);
  if ( PersistedStateLocation == -2147483643 )
  {
    Pool2 = (void *)ExAllocatePool2(64, v8, 1430540870);
    if ( Pool2 )
    {
      PersistedStateLocation = RtlGetPersistedStateLocation(
                                 L"USB",
                                 0,
                                 L"\\Registry\\Machine\\SYSTEM\\CurrentControlSet\\Control\\USB",
                                 0,
                                 Pool2,
                                 v8,
                                 0);
      if ( PersistedStateLocation >= 0 )
      {
        *a1 = Pool2;
      }
      else
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v6) = 2;
          WPP_RECORDER_SF_d(
            WPP_GLOBAL_Control->DeviceExtension,
            v6,
            1,
            12,
            (__int64)WPP_5169c4c8089132207a438b4341aed5b6_Traceguids,
            PersistedStateLocation);
        }
        ExFreePoolWithTag(Pool2, 0);
      }
    }
    else
    {
      PersistedStateLocation = -1073741670;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_Ld(
          WPP_GLOBAL_Control->DeviceExtension,
          v4,
          1,
          11,
          (__int64)WPP_5169c4c8089132207a438b4341aed5b6_Traceguids,
          v8,
          154);
    }
  }
  else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v2) = 2;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v2,
      1,
      10,
      (__int64)WPP_5169c4c8089132207a438b4341aed5b6_Traceguids,
      PersistedStateLocation);
  }
  return (unsigned int)PersistedStateLocation;
}

```

## disassembly

```asm
0x140043c00  mov     r11, rsp
0x140043c03  mov     [r11+8], rbx
0x140043c07  mov     [r11+18h], rsi
0x140043c0b  push    rdi
0x140043c0c  sub     rsp, 40h
0x140043c10  lea     rax, [r11+10h]
0x140043c14  mov     [rsp+48h+arg_8], 0
0x140043c1c  mov     [r11-18h], rax
0x140043c20  lea     r8, aRegistryMachin_11; "\\Registry\\Machine\\SYSTEM\\CurrentCon"...
0x140043c27  mov     rsi, rcx
0x140043c2a  mov     [rsp+48h+var_20], 0
0x140043c32  xor     r9d, r9d
0x140043c35  mov     qword ptr [r11-28h], 0
0x140043c3d  xor     edx, edx
0x140043c3f  lea     rcx, aUsb; "USB"
0x140043c46  call    cs:__imp_RtlGetPersistedStateLocation
0x140043c4d  nop     dword ptr [rax+rax+00h]
0x140043c52  mov     ebx, eax
0x140043c54  cmp     eax, 80000005h
0x140043c59  jz      short loc_140043CA0
0x140043c5b  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140043c62  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140043c69  jz      loc_140043D9E
0x140043c6f  mov     rcx, cs:WPP_GLOBAL_Control
0x140043c76  lea     rax, WPP_5169c4c8089132207a438b4341aed5b6_Traceguids
0x140043c7d  mov     r9d, 0Ah
0x140043c83  mov     [rsp+48h+var_20], ebx
0x140043c87  mov     dl, 2
0x140043c89  mov     [rsp+48h+var_28], rax
0x140043c8e  mov     rcx, [rcx+40h]
0x140043c92  lea     r8d, [r9-9]
0x140043c96  call    WPP_RECORDER_SF_d
0x140043c9b  jmp     loc_140043D9E
0x140043ca0  mov     edx, [rsp+48h+arg_8]
0x140043ca4  mov     ecx, 40h ; '@'
0x140043ca9  mov     r8d, 55445246h
0x140043caf  call    cs:__imp_ExAllocatePool2
0x140043cb6  nop     dword ptr [rax+rax+00h]
0x140043cbb  mov     rdi, rax
0x140043cbe  test    rax, rax
0x140043cc1  jnz     short loc_140043D11
0x140043cc3  mov     ebx, 0C000009Ah
0x140043cc8  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140043ccf  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140043cd6  jz      loc_140043D9E
0x140043cdc  mov     eax, [rsp+48h+arg_8]
0x140043ce0  lea     r9d, [rdi+0Bh]
0x140043ce4  mov     rcx, cs:WPP_GLOBAL_Control
0x140043ceb  lea     r8d, [rdi+1]
0x140043cef  mov     dword ptr [rsp+48h+var_18], ebx
0x140043cf3  mov     [rsp+48h+var_20], eax
0x140043cf7  lea     rax, WPP_5169c4c8089132207a438b4341aed5b6_Traceguids
0x140043cfe  mov     [rsp+48h+var_28], rax
0x140043d03  mov     rcx, [rcx+40h]
0x140043d07  call    WPP_RECORDER_SF_Ld
0x140043d0c  jmp     loc_140043D9E
0x140043d11  mov     eax, [rsp+48h+arg_8]
0x140043d15  lea     r8, aRegistryMachin_11; "\\Registry\\Machine\\SYSTEM\\CurrentCon"...
0x140043d1c  mov     [rsp+48h+var_18], 0
0x140043d25  lea     rcx, aUsb; "USB"
0x140043d2c  mov     [rsp+48h+var_20], eax
0x140043d30  xor     r9d, r9d
0x140043d33  xor     edx, edx
0x140043d35  mov     [rsp+48h+var_28], rdi
0x140043d3a  call    cs:__imp_RtlGetPersistedStateLocation
0x140043d41  nop     dword ptr [rax+rax+00h]
0x140043d46  mov     ebx, eax
0x140043d48  test    eax, eax
0x140043d4a  jns     short loc_140043D9B
0x140043d4c  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140043d53  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140043d5a  jz      short loc_140043D88
0x140043d5c  mov     rcx, cs:WPP_GLOBAL_Control
0x140043d63  lea     rax, WPP_5169c4c8089132207a438b4341aed5b6_Traceguids
0x140043d6a  mov     r9d, 0Ch
0x140043d70  mov     [rsp+48h+var_20], ebx
0x140043d74  mov     dl, 2
0x140043d76  mov     [rsp+48h+var_28], rax
0x140043d7b  mov     rcx, [rcx+40h]
0x140043d7f  lea     r8d, [r9-0Bh]
0x140043d83  call    WPP_RECORDER_SF_d
0x140043d88  xor     edx, edx; Tag
0x140043d8a  mov     rcx, rdi; P
0x140043d8d  call    cs:__imp_ExFreePoolWithTag
0x140043d94  nop     dword ptr [rax+rax+00h]
0x140043d99  jmp     short loc_140043D9E
0x140043d9b  mov     [rsi], rdi
0x140043d9e  mov     rsi, [rsp+48h+arg_10]
0x140043da3  mov     eax, ebx
0x140043da5  mov     rbx, [rsp+48h+arg_0]
0x140043daa  add     rsp, 40h
0x140043dae  pop     rdi
0x140043daf  retn
```
