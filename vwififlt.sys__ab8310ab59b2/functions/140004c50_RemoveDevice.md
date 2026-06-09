# RemoveDevice

- ea: `0x140004c50`
- end: `0x140004d69`
- name: `RemoveDevice`
- size: `281`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *, int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140004568`

## callees

- `0x140004c50`
- `0x1400053c8`
- `0x14000d8ec`
- `0x14000d91c`
- `0x14000f110`

## pseudocode

```c
__int64 __fastcall RemoveDevice(struct _UNICODE_STRING *a1, int a2)
{
  unsigned int v4; // ebx
  __int128 InputBuffer; // [rsp+30h] [rbp-28h] BYREF

  InputBuffer = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 35, WPP_d5e31b45fa4f31b576e451b1be9986c5_Traceguids);
  LODWORD(InputBuffer) = 16;
  DWORD1(InputBuffer) = a2;
  v4 = SendIoctlToBus(a1 + 165, 0x2A4004u, &InputBuffer, 0x10u, 0, 0);
  if ( v4 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      return v4;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 36, WPP_d5e31b45fa4f31b576e451b1be9986c5_Traceguids);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 37, WPP_d5e31b45fa4f31b576e451b1be9986c5_Traceguids);
  return v4;
}

```

## disassembly

```asm
0x140004c50  mov     [rsp+arg_10], rbx
0x140004c55  mov     [rsp+arg_18], rsi
0x140004c5a  push    rdi
0x140004c5b  sub     rsp, 50h
0x140004c5f  mov     rax, cs:__security_cookie
0x140004c66  xor     rax, rsp
0x140004c69  mov     [rsp+58h+var_18], rax
0x140004c6e  xorps   xmm0, xmm0
0x140004c71  mov     edi, edx
0x140004c73  movups  [rsp+58h+InputBuffer], xmm0
0x140004c78  mov     rbx, rcx
0x140004c7b  mov     rcx, cs:WPP_GLOBAL_Control
0x140004c82  lea     rsi, WPP_GLOBAL_Control
0x140004c89  cmp     rcx, rsi
0x140004c8c  jnz     short loc_140004CF6
0x140004c8e  mov     r9d, 10h; InputBufferLength
0x140004c94  mov     [rsp+58h+var_30], 0; ULONG
0x140004c9c  lea     rcx, [rbx+0A50h]; ObjectName
0x140004ca3  mov     dword ptr [rsp+58h+InputBuffer], r9d
0x140004ca8  lea     r8, [rsp+58h+InputBuffer]; InputBuffer
0x140004cad  mov     dword ptr [rsp+58h+InputBuffer+4], edi
0x140004cb1  mov     edx, 2A4004h; IoControlCode
0x140004cb6  mov     [rsp+58h+var_38], 0; PVOID
0x140004cbf  call    SendIoctlToBus
0x140004cc4  mov     ebx, eax
0x140004cc6  test    eax, eax
0x140004cc8  jnz     short loc_140004D17
0x140004cca  mov     rcx, cs:WPP_GLOBAL_Control
0x140004cd1  cmp     rcx, rsi
0x140004cd4  jnz     short loc_140004D45
0x140004cd6  mov     eax, ebx
0x140004cd8  mov     rcx, [rsp+58h+var_18]
0x140004cdd  xor     rcx, rsp; StackCookie
0x140004ce0  call    __security_check_cookie
0x140004ce5  mov     rbx, [rsp+58h+arg_10]
0x140004cea  mov     rsi, [rsp+58h+arg_18]
0x140004cef  add     rsp, 50h
0x140004cf3  pop     rdi
0x140004cf4  retn
0x140004cf6  mov     eax, [rcx+2Ch]
0x140004cf9  test    al, 20h
0x140004cfb  jz      short loc_140004C8E
0x140004cfd  mov     rcx, [rcx+18h]
0x140004d01  lea     r8, WPP_d5e31b45fa4f31b576e451b1be9986c5_Traceguids
0x140004d08  mov     edx, 23h ; '#'
0x140004d0d  call    WPP_SF_
0x140004d12  jmp     loc_140004C8E
0x140004d17  mov     rcx, cs:WPP_GLOBAL_Control
0x140004d1e  cmp     rcx, rsi
0x140004d21  jz      short loc_140004CD6
0x140004d23  mov     edx, [rcx+2Ch]
0x140004d26  test    dl, 1
0x140004d29  jz      short loc_140004CCA
0x140004d2b  mov     rcx, [rcx+18h]
0x140004d2f  lea     r8, WPP_d5e31b45fa4f31b576e451b1be9986c5_Traceguids
0x140004d36  mov     edx, 24h ; '$'
0x140004d3b  mov     r9d, ebx
0x140004d3e  call    WPP_SF_d
0x140004d43  jmp     short loc_140004CCA
0x140004d45  mov     eax, [rcx+2Ch]
0x140004d48  test    al, 20h
0x140004d4a  jz      short loc_140004CD6
0x140004d4c  mov     rcx, [rcx+18h]
0x140004d50  lea     r8, WPP_d5e31b45fa4f31b576e451b1be9986c5_Traceguids
0x140004d57  mov     edx, 25h ; '%'
0x140004d5c  mov     r9d, ebx
0x140004d5f  call    WPP_SF_d
0x140004d64  jmp     loc_140004CD6
```
