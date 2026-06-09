# ConnectToTerminalServer

- ea: `0x1800129f8`
- end: `0x180012b42`
- name: `ConnectToTerminalServer`
- size: `330`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180012918`
- `0x180012b48`
- `0x180012c5c`

## callees

- `0x1800129f8`
- `0x1800138c5`
- `0x1800138f0`

## import_xrefs

- `ntdll!NtAlpcConnectPort` at `0x180012b09`
- `ntdll!NtAlpcConnectPort` at `0x180012b09`
- `ntdll!RtlInitUnicodeString` at `0x180012a58`
- `ntdll!RtlInitUnicodeString` at `0x180012a58`

## pseudocode

```c
__int64 __fastcall ConnectToTerminalServer(__int64 a1, _QWORD *a2)
{
  __int64 result; // rax
  __int64 v4; // [rsp+60h] [rbp-A0h] BYREF
  _OWORD v5[2]; // [rsp+68h] [rbp-98h] BYREF
  __int64 v6; // [rsp+88h] [rbp-78h]
  __int64 v7; // [rsp+90h] [rbp-70h]
  __int64 v8; // [rsp+98h] [rbp-68h]
  struct _UNICODE_STRING DestinationString; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v10[8]; // [rsp+B0h] [rbp-50h] BYREF
  int v11; // [rsp+B8h] [rbp-48h]
  __int16 v12; // [rsp+BCh] [rbp-44h]
  __int64 v13; // [rsp+C0h] [rbp-40h]
  __int64 v14; // [rsp+D0h] [rbp-30h]

  DestinationString = 0;
  memset_0(v10, 0, 0x48u);
  RtlInitUnicodeString(&DestinationString, L"\\SmSsWinStationApiPort");
  memset_0(v10, 0, 0x48u);
  v11 = 2;
  v8 = 0;
  v4 = 56;
  v12 = 257;
  v6 = 0;
  v13 = 16496;
  v14 = 527872;
  v5[1] = 0;
  v5[0] = 0xA00380010uLL;
  v7 = 1;
  result = NtAlpcConnectPort(a2, &DestinationString, 0, v10, 0x20000, 0, v5, &v4, 0, 0, 0);
  if ( (int)result >= 0 )
    return 0;
  *a2 = 0;
  return result;
}

```

## disassembly

```asm
0x1800129f8  mov     [rsp-8+arg_0], rbx
0x1800129fd  push    rbp
0x1800129fe  lea     rbp, [rsp-10h]
0x180012a03  sub     rsp, 110h
0x180012a0a  mov     rax, cs:__security_cookie
0x180012a11  xor     rax, rsp
0x180012a14  mov     [rbp+10h+var_10], rax
0x180012a18  mov     rbx, rdx
0x180012a1b  lea     rcx, [rbp+10h+var_60]; void *
0x180012a1f  xor     edx, edx; Val
0x180012a21  xorps   xmm0, xmm0
0x180012a24  movups  xmmword ptr [rbp+10h+DestinationString.Length], xmm0
0x180012a28  lea     r8d, [rdx+48h]; Size
0x180012a2c  call    memset_0
0x180012a31  xorps   xmm0, xmm0
0x180012a34  lea     rdx, aSmsswinstation; "\\SmSsWinStationApiPort"
0x180012a3b  xor     eax, eax
0x180012a3d  lea     rcx, [rbp+10h+DestinationString]; DestinationString
0x180012a41  movups  [rsp+110h+var_A8], xmm0
0x180012a46  mov     [rbp+10h+var_78], rax
0x180012a4a  movups  [rsp+110h+var_98], xmm0
0x180012a4f  mov     [rsp+110h+var_B0], rax
0x180012a54  movups  [rbp+10h+var_88], xmm0
0x180012a58  call    cs:__imp_RtlInitUnicodeString
0x180012a5f  nop     dword ptr [rax+rax+00h]
0x180012a64  xor     edx, edx; Val
0x180012a66  lea     rcx, [rbp+10h+var_60]; void *
0x180012a6a  lea     r8d, [rdx+48h]; Size
0x180012a6e  call    memset_0
0x180012a73  xor     eax, eax
0x180012a75  mov     [rbp+10h+var_58], 2
0x180012a7c  mov     [rsp+110h+var_C0], rax
0x180012a81  lea     r9, [rbp+10h+var_60]
0x180012a85  mov     [rsp+110h+var_C8], rax
0x180012a8a  lea     rdx, [rbp+10h+DestinationString]
0x180012a8e  mov     [rsp+110h+var_D0], rax
0x180012a93  xorps   xmm0, xmm0
0x180012a96  lea     ecx, [rax+38h]
0x180012a99  mov     [rbp+10h+var_78], rax
0x180012a9d  movups  [rsp+110h+var_A8], xmm0
0x180012aa2  lea     rax, [rsp+110h+var_B0]
0x180012aa7  mov     [rsp+110h+var_B0], rcx
0x180012aac  mov     [rsp+110h+var_D8], rax
0x180012ab1  xor     r8d, r8d
0x180012ab4  lea     rax, [rsp+110h+var_A8]
0x180012ab9  mov     [rbp+10h+var_54], 101h
0x180012abf  mov     [rsp+110h+var_E0], rax
0x180012ac4  mov     rcx, rbx
0x180012ac7  movups  [rbp+10h+var_88], xmm0
0x180012acb  mov     [rsp+110h+var_E8], 0
0x180012ad4  mov     [rsp+110h+var_F0], 20000h
0x180012adc  mov     [rbp+10h+var_50], 4070h
0x180012ae4  mov     [rbp+10h+var_40], 80E00h
0x180012aec  movups  [rsp+110h+var_98], xmm0
0x180012af1  mov     dword ptr [rsp+110h+var_A8], 380010h
0x180012af9  mov     dword ptr [rsp+110h+var_A8+4], 0Ah
0x180012b01  mov     qword ptr [rbp+10h+var_88+8], 1
0x180012b09  call    cs:__imp_NtAlpcConnectPort
0x180012b10  nop     dword ptr [rax+rax+00h]
0x180012b15  test    eax, eax
0x180012b17  jns     short loc_180012B22
0x180012b19  mov     qword ptr [rbx], 0
0x180012b20  jmp     short loc_180012B24
0x180012b22  xor     eax, eax
0x180012b24  mov     rcx, [rbp+10h+var_10]
0x180012b28  xor     rcx, rsp; StackCookie
0x180012b2b  call    __security_check_cookie
0x180012b30  mov     rbx, [rsp+110h+arg_0]
0x180012b38  add     rsp, 110h
0x180012b3f  pop     rbp
0x180012b40  retn
```
