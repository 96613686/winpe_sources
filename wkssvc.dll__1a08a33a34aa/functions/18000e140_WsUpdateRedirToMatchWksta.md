# WsUpdateRedirToMatchWksta

- ea: `0x18000e140`
- end: `0x18000e222`
- name: `WsUpdateRedirToMatchWksta`
- size: `226`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x18002ce00`
- `0x180030310`
- `0x180030360`

## callees

- `0x180005df0`
- `0x18000e140`
- `0x18001fbd0`

## import_xrefs

- `ntdll!NtFsControlFile` at `0x18000e1dc`
- `ntdll!NtFsControlFile` at `0x18000e1dc`

## pseudocode

```c
__int64 __fastcall WsUpdateRedirToMatchWksta(int a1, _DWORD *a2)
{
  NTSTATUS Status; // eax
  __int64 result; // rax
  struct _IO_STATUS_BLOCK v5; // [rsp+58h] [rbp+17h] BYREF
  _DWORD v6[3]; // [rsp+68h] [rbp+27h] BYREF
  __int64 v7; // [rsp+74h] [rbp+33h]
  int v8; // [rsp+7Ch] [rbp+3Bh]
  __int64 v9; // [rsp+80h] [rbp+3Fh]
  int v10; // [rsp+88h] [rbp+47h]

  v8 = a1;
  v7 = 0;
  v9 = 0;
  v10 = 0;
  v6[1] = 6;
  v6[2] = 502;
  v6[0] = 0;
  v5 = 0;
  Status = NtFsControlFile(WsRedirDeviceHandle, 0, 0, 0, &v5, 0x140199u, v6, 0x24u, &xmmword_180051F80, 0x8Cu);
  if ( Status >= 0 )
    Status = v5.Status;
  result = WsMapStatus((unsigned int)Status);
  if ( (_DWORD)result == 87 )
  {
    if ( a2 )
      *a2 = v8;
  }
  return result;
}

```

## disassembly

```asm
0x18000e140  mov     r11, rsp
0x18000e143  mov     [r11+18h], rbx
0x18000e147  push    rbp
0x18000e148  lea     rbp, [r11-5Fh]
0x18000e14c  sub     rsp, 90h
0x18000e153  mov     rax, cs:__security_cookie
0x18000e15a  xor     rax, rsp
0x18000e15d  mov     [rbp+57h+var_8], rax
0x18000e161  mov     dword ptr [rsp+48h], 8Ch; OutputBufferLength
0x18000e169  lea     rax, xmmword_180051F80
0x18000e170  mov     [r11-58h], rax
0x18000e174  mov     rbx, rdx
0x18000e177  mov     dword ptr [rsp+38h], 24h ; '$'; InputBufferLength
0x18000e17f  lea     rax, [rbp+57h+var_30]
0x18000e183  mov     [r11-68h], rax
0x18000e187  xorps   xmm0, xmm0
0x18000e18a  lea     rax, [rbp+57h+var_40]
0x18000e18e  mov     [rbp+57h+var_1C], ecx
0x18000e191  mov     rcx, cs:WsRedirDeviceHandle; FileHandle
0x18000e198  xor     r9d, r9d; ApcContext
0x18000e19b  mov     dword ptr [rsp+28h], 140199h; FsControlCode
0x18000e1a3  xor     r8d, r8d; ApcRoutine
0x18000e1a6  xor     edx, edx; Event
0x18000e1a8  mov     [r11-78h], rax
0x18000e1ac  mov     [rbp+57h+var_24], 0
0x18000e1b4  mov     [rbp+57h+var_18], 0
0x18000e1bc  mov     [rbp+57h+var_10], 0
0x18000e1c3  mov     [rbp+57h+var_2C], 6
0x18000e1ca  mov     [rbp+57h+var_28], 1F6h
0x18000e1d1  mov     [rbp+57h+var_30], 0
0x18000e1d8  movups  [rbp+57h+var_40], xmm0
0x18000e1dc  call    cs:__imp_NtFsControlFile
0x18000e1e3  nop     dword ptr [rax+rax+00h]
0x18000e1e8  test    eax, eax
0x18000e1ea  cmovns  eax, dword ptr [rbp+57h+var_40]
0x18000e1ee  mov     ecx, eax
0x18000e1f0  call    WsMapStatus
0x18000e1f5  cmp     eax, 57h ; 'W'
0x18000e1f8  jnz     short loc_18000E204
0x18000e1fa  test    rbx, rbx
0x18000e1fd  jz      short loc_18000E204
0x18000e1ff  mov     ecx, [rbp+57h+var_1C]
0x18000e202  mov     [rbx], ecx
0x18000e204  mov     rcx, [rbp+57h+var_8]
0x18000e208  xor     rcx, rsp; StackCookie
0x18000e20b  call    __security_check_cookie
0x18000e210  mov     rbx, [rsp+90h+arg_10]
0x18000e218  add     rsp, 90h
0x18000e21f  pop     rbp
0x18000e220  retn
```
