# NtPnpOpenDeviceInterfaceKey

- ea: `0x14001c8a4`
- end: `0x14001c9bc`
- name: `NtPnpOpenDeviceInterfaceKey`
- size: `280`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140016190`

## callees

- `0x14001b8f0`
- `0x14001c8a4`

## import_xrefs

- `ntdll!NtDeviceIoControlFile` at `0x14001c988`
- `ntdll!NtDeviceIoControlFile` at `0x14001c988`

## pseudocode

```c
__int64 __fastcall NtPnpOpenDeviceInterfaceKey(const wchar_t *a1, __int64 a2, __int64 a3, _QWORD *a4)
{
  NTSTATUS v5; // ecx
  void *v6; // r11
  size_t pcchLength; // [rsp+50h] [rbp-11h] BYREF
  __int128 OutputBuffer; // [rsp+58h] [rbp-9h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+68h] [rbp+7h] BYREF
  _QWORD InputBuffer[3]; // [rsp+78h] [rbp+17h] BYREF
  int v12; // [rsp+90h] [rbp+2Fh]
  int v13; // [rsp+94h] [rbp+33h]
  __int64 v14; // [rsp+98h] [rbp+37h]
  __int64 v15; // [rsp+A0h] [rbp+3Fh]

  OutputBuffer = 0;
  IoStatusBlock = 0;
  if ( NtPnpDeviceApiDriverHandle )
  {
    if ( a1 && a4 )
    {
      *a4 = 0;
      pcchLength = 0;
      InputBuffer[1] = 4;
      v15 = 16;
      InputBuffer[0] = 48;
      v13 = 1;
      v14 = 2;
      InputBuffer[2] = a1;
      v5 = RtlStringCchLengthW(a1, 0x7FFFFFFFu, &pcchLength);
      if ( v5 >= 0 )
      {
        v12 = 2 * pcchLength + 2;
        v5 = NtDeviceIoControlFile(v6, 0, 0, 0, &IoStatusBlock, 0x470853u, InputBuffer, 0x30u, &OutputBuffer, 0x10u);
        if ( v5 >= 0 )
        {
          v5 = DWORD1(OutputBuffer);
          if ( (SDWORD1(OutputBuffer) & 0x80000000) == 0 )
            *a4 = *((_QWORD *)&OutputBuffer + 1);
        }
      }
    }
    else
    {
      return (unsigned int)-1073741811;
    }
  }
  else
  {
    return (unsigned int)-1073740759;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x14001c8a4  mov     [rsp-8+arg_0], rbx
0x14001c8a9  push    rbp
0x14001c8aa  lea     rbp, [rsp-4Fh]
0x14001c8af  sub     rsp, 0B0h
0x14001c8b6  mov     r11, cs:NtPnpDeviceApiDriverHandle
0x14001c8bd  xorps   xmm0, xmm0
0x14001c8c0  xorps   xmm1, xmm1
0x14001c8c3  mov     rbx, r9
0x14001c8c6  movups  [rbp+4Fh+var_58], xmm0
0x14001c8ca  movups  xmmword ptr [rbp+4Fh+var_48], xmm1
0x14001c8ce  test    r11, r11
0x14001c8d1  jnz     short loc_14001C8DD
0x14001c8d3  mov     ecx, 0C0000429h; psz
0x14001c8d8  jmp     loc_14001C9A9
0x14001c8dd  test    rcx, rcx
0x14001c8e0  jz      loc_14001C9A4
0x14001c8e6  test    rbx, rbx
0x14001c8e9  jz      loc_14001C9A4
0x14001c8ef  lea     r8, [rbp+4Fh+pcchLength]; pcchLength
0x14001c8f3  mov     qword ptr [r9], 0
0x14001c8fa  mov     edx, 7FFFFFFFh; cchMax
0x14001c8ff  mov     [rbp+4Fh+pcchLength], 0
0x14001c907  mov     [rbp+4Fh+var_30], 4
0x14001c90f  mov     [rbp+4Fh+var_10], 10h
0x14001c917  mov     [rbp+4Fh+var_38], 30h ; '0'
0x14001c91f  mov     [rbp+4Fh+var_1C], 1
0x14001c926  mov     [rbp+4Fh+var_18], 2
0x14001c92e  mov     [rbp+4Fh+var_28], rcx
0x14001c932  call    RtlStringCchLengthW
0x14001c937  mov     ecx, eax
0x14001c939  test    eax, eax
0x14001c93b  js      short loc_14001C9A9
0x14001c93d  mov     eax, dword ptr [rbp+4Fh+pcchLength]
0x14001c940  lea     eax, ds:2[rax*2]
0x14001c947  mov     [rbp+4Fh+var_20], eax
0x14001c94a  mov     [rsp+0B0h+OutputBufferLength], 10h; OutputBufferLength
0x14001c952  lea     rax, [rbp+4Fh+var_58]
0x14001c956  mov     [rsp+0B0h+OutputBuffer], rax; OutputBuffer
0x14001c95b  xor     r9d, r9d; ApcContext
0x14001c95e  mov     [rsp+0B0h+InputBufferLength], 30h ; '0'; InputBufferLength
0x14001c966  lea     rax, [rbp+4Fh+var_38]
0x14001c96a  mov     [rsp+0B0h+InputBuffer], rax; InputBuffer
0x14001c96f  xor     r8d, r8d; ApcRoutine
0x14001c972  lea     rax, [rbp+4Fh+var_48]
0x14001c976  mov     [rsp+0B0h+IoControlCode], 470853h; IoControlCode
0x14001c97e  xor     edx, edx; Event
0x14001c980  mov     [rsp+0B0h+IoStatusBlock], rax; IoStatusBlock
0x14001c985  mov     rcx, r11; FileHandle
0x14001c988  call    cs:__imp_NtDeviceIoControlFile
0x14001c98e  mov     ecx, eax
0x14001c990  test    eax, eax
0x14001c992  js      short loc_14001C9A9
0x14001c994  mov     ecx, dword ptr [rbp+4Fh+var_58+4]
0x14001c997  test    ecx, ecx
0x14001c999  js      short loc_14001C9A9
0x14001c99b  mov     rax, qword ptr [rbp+4Fh+var_58+8]
0x14001c99f  mov     [rbx], rax
0x14001c9a2  jmp     short loc_14001C9A9
0x14001c9a4  mov     ecx, 0C000000Dh
0x14001c9a9  mov     rbx, [rsp+0B0h+arg_0]
0x14001c9b1  mov     eax, ecx
0x14001c9b3  add     rsp, 0B0h
0x14001c9ba  pop     rbp
0x14001c9bb  retn
```
