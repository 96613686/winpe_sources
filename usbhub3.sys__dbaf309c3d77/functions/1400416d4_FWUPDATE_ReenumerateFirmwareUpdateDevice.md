# FWUPDATE_ReenumerateFirmwareUpdateDevice

- ea: `0x1400416d4`
- end: `0x140041778`
- name: `FWUPDATE_ReenumerateFirmwareUpdateDevice`
- size: `164`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x140007810`
- `0x14000a310`
- `0x14000a370`

## callees

- `0x1400024b8`
- `0x1400416d4`
- `0x140045570`

## pseudocode

```c
void __fastcall FWUPDATE_ReenumerateFirmwareUpdateDevice(__int64 a1)
{
  __int64 v1; // rdx
  int v3; // eax
  int v4; // edx
  int v5; // [rsp+28h] [rbp-10h]

  v1 = *(_QWORD *)(a1 + 2672);
  if ( v1 )
  {
    if ( *(_BYTE *)((*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
                      WdfDriverGlobals,
                      v1,
                      off_14006B248)
                  + 24) == 1 )
    {
      v3 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01015 + 1752))(
             WdfDriverGlobals,
             *(_QWORD *)(a1 + 2672));
      if ( v3 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v5 = v3;
        LOBYTE(v4) = 2;
        WPP_RECORDER_SF_d(
          *(_QWORD *)(a1 + 2536),
          v4,
          3,
          43,
          (__int64)WPP_2fd11ae104fa34a9334eddada324a17a_Traceguids,
          v5);
      }
    }
  }
}

```

## disassembly

```asm
0x1400416d4  push    rbx
0x1400416d6  sub     rsp, 30h
0x1400416da  mov     rdx, [rcx+0A70h]
0x1400416e1  mov     rbx, rcx
0x1400416e4  test    rdx, rdx
0x1400416e7  jz      loc_140041771
0x1400416ed  mov     rax, cs:WdfFunctions_01015
0x1400416f4  mov     r8, cs:off_14006B248
0x1400416fb  mov     rcx, cs:WdfDriverGlobals
0x140041702  mov     rax, [rax+650h]
0x140041709  call    _guard_dispatch_icall
0x14004170e  cmp     byte ptr [rax+18h], 1
0x140041712  jnz     short loc_140041771
0x140041714  mov     rax, cs:WdfFunctions_01015
0x14004171b  mov     rdx, [rbx+0A70h]
0x140041722  mov     rcx, cs:WdfDriverGlobals
0x140041729  mov     rax, [rax+6D8h]
0x140041730  call    _guard_dispatch_icall
0x140041735  test    eax, eax
0x140041737  jns     short loc_140041771
0x140041739  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140041740  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140041747  jz      short loc_140041771
0x140041749  mov     rcx, [rbx+9E8h]
0x140041750  mov     r9d, 2Bh ; '+'
0x140041756  mov     [rsp+38h+var_10], eax
0x14004175a  mov     dl, 2
0x14004175c  lea     rax, WPP_2fd11ae104fa34a9334eddada324a17a_Traceguids
0x140041763  mov     [rsp+38h+var_18], rax
0x140041768  lea     r8d, [r9-28h]
0x14004176c  call    WPP_RECORDER_SF_d
0x140041771  add     rsp, 30h
0x140041775  pop     rbx
0x140041776  retn
```
