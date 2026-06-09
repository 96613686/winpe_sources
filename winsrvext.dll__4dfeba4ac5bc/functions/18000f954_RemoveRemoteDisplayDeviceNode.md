# RemoveRemoteDisplayDeviceNode

- ea: `0x18000f954`
- end: `0x18000fa88`
- name: `RemoveRemoteDisplayDeviceNode`
- size: `308`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000e928`
- `0x180010220`

## callees

- `0x180001090`
- `0x18000f954`
- `0x1800138f0`

## import_xrefs

- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceClose` at `0x18000f987`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceClose` at `0x18000f987`

## string_xrefs

- `0x18000fa19`: `Device node was successfully removed`

## pseudocode

```c
__int64 __fastcall RemoveRemoteDisplayDeviceNode(__int64 a1)
{
  __int64 result; // rax
  __int64 v3; // [rsp+30h] [rbp-39h] BYREF
  __int64 v4; // [rsp+38h] [rbp-31h] BYREF
  _BYTE v5[32]; // [rsp+40h] [rbp-29h] BYREF
  __int64 v6; // [rsp+60h] [rbp-9h]
  __int64 v7; // [rsp+68h] [rbp-1h]
  __int128 *v8; // [rsp+70h] [rbp+7h]
  __int64 v9; // [rsp+78h] [rbp+Fh]
  __int64 *v10; // [rsp+80h] [rbp+17h]
  __int64 v11; // [rsp+88h] [rbp+1Fh]
  const char *v12; // [rsp+90h] [rbp+27h]
  __int64 v13; // [rsp+98h] [rbp+2Fh]
  __int64 *v14; // [rsp+A0h] [rbp+37h]
  __int64 v15; // [rsp+A8h] [rbp+3Fh]

  if ( ghSwDevice )
  {
    SwDeviceClose();
    result = (unsigned int)dword_18001D0D8;
    ghSwDevice = 0;
    if ( (unsigned int)dword_18001D0D8 > 4 )
    {
      result = qword_18001D0E8;
      if ( (qword_18001D0E8 & 0x400000000000LL) != 0 )
      {
        result = qword_18001D0F0 & 0x400000000000LL;
        if ( (qword_18001D0F0 & 0x400000000000LL) == qword_18001D0F0 )
        {
          v6 = a1;
          v8 = &gRelatedActivityId;
          LODWORD(v3) = gSessionId;
          v7 = 16;
          v10 = &v3;
          v9 = 16;
          v12 = "Device node was successfully removed";
          v14 = &v4;
          v11 = 4;
          v13 = 37;
          v15 = 8;
          return tlgWriteTransfer_EventWriteTransfer(&dword_18001D0D8, byte_1800185AD, 0, 0, 7, v5, v3, 0x1000000);
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000f954  mov     [rsp-8+arg_0], rbx
0x18000f959  push    rbp
0x18000f95a  lea     rbp, [rsp-57h]
0x18000f95f  sub     rsp, 0C0h
0x18000f966  mov     rax, cs:__security_cookie
0x18000f96d  xor     rax, rsp
0x18000f970  mov     [rbp+57h+var_10], rax
0x18000f974  mov     rbx, rcx
0x18000f977  mov     rcx, cs:ghSwDevice
0x18000f97e  test    rcx, rcx
0x18000f981  jz      loc_18000FA6A
0x18000f987  call    cs:__imp_SwDeviceClose
0x18000f98e  nop     dword ptr [rax+rax+00h]
0x18000f993  mov     eax, cs:dword_18001D0D8
0x18000f999  mov     cs:ghSwDevice, 0
0x18000f9a4  cmp     eax, 4
0x18000f9a7  jbe     loc_18000FA6A
0x18000f9ad  mov     rcx, cs:qword_18001D0F0
0x18000f9b4  mov     rdx, 400000000000h
0x18000f9be  mov     rax, cs:qword_18001D0E8
0x18000f9c5  test    rdx, rax
0x18000f9c8  jz      loc_18000FA6A
0x18000f9ce  mov     rax, rcx
0x18000f9d1  and     rax, rdx
0x18000f9d4  cmp     rax, rcx
0x18000f9d7  jnz     loc_18000FA6A
0x18000f9dd  lea     rax, gRelatedActivityId
0x18000f9e4  mov     [rbp+57h+var_60], rbx
0x18000f9e8  mov     [rbp+57h+var_50], rax
0x18000f9ec  lea     rdx, byte_1800185AD
0x18000f9f3  mov     eax, cs:gSessionId
0x18000f9f9  lea     rcx, dword_18001D0D8
0x18000fa00  mov     dword ptr [rbp+57h+var_90], eax
0x18000fa03  xor     r9d, r9d
0x18000fa06  lea     rax, [rbp+57h+var_90]
0x18000fa0a  mov     [rbp+57h+var_58], 10h
0x18000fa12  mov     [rbp+57h+var_40], rax
0x18000fa16  xor     r8d, r8d
0x18000fa19  lea     rax, aDeviceNodeWasS; "Device node was successfully removed"
0x18000fa20  mov     [rbp+57h+var_48], 10h
0x18000fa28  mov     [rbp+57h+var_30], rax
0x18000fa2c  lea     rax, [rbp+57h+var_88]
0x18000fa30  mov     [rbp+57h+var_20], rax
0x18000fa34  lea     rax, [rbp+57h+var_80]
0x18000fa38  mov     [rsp+0C0h+var_98], rax
0x18000fa3d  mov     [rsp+0C0h+var_A0], 7
0x18000fa45  mov     [rbp+57h+var_38], 4
0x18000fa4d  mov     [rbp+57h+var_28], 25h ; '%'
0x18000fa55  mov     [rbp+57h+var_88], 1000000h
0x18000fa5d  mov     [rbp+57h+var_18], 8
0x18000fa65  call    _tlgWriteTransfer_EventWriteTransfer
0x18000fa6a  mov     rcx, [rbp+57h+var_10]
0x18000fa6e  xor     rcx, rsp; StackCookie
0x18000fa71  call    __security_check_cookie
0x18000fa76  mov     rbx, [rsp+0C0h+arg_0]
0x18000fa7e  add     rsp, 0C0h
0x18000fa85  pop     rbp
0x18000fa86  retn
```
