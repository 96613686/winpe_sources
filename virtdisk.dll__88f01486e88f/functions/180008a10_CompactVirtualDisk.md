# CompactVirtualDisk

- ea: `0x180008a10`
- end: `0x180008b5d`
- name: `CompactVirtualDisk`
- size: `333`
- prototype: `DWORD __stdcall(HANDLE VirtualDiskHandle, COMPACT_VIRTUAL_DISK_FLAG Flags, PCOMPACT_VIRTUAL_DISK_PARAMETERS Parameters, LPOVERLAPPED Overlapped)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800063a8`
- `0x180006fac`
- `0x180008a10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008b00`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008b00`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180008af0`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180008af0`

## pseudocode

```c
DWORD __stdcall CompactVirtualDisk(
        HANDLE VirtualDiskHandle,
        COMPACT_VIRTUAL_DISK_FLAG Flags,
        PCOMPACT_VIRTUAL_DISK_PARAMETERS Parameters,
        LPOVERLAPPED Overlapped)
{
  _QWORD *v8; // rcx
  DWORD LastError; // ebx
  DWORD *lpBytesReturned; // rcx
  int v12; // [rsp+40h] [rbp-28h] BYREF
  __int16 InBuffer; // [rsp+70h] [rbp+8h] BYREF
  bool v14; // [rsp+72h] [rbp+Ah]

  v12 = 0;
  InBuffer = 0;
  v14 = 0;
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_07b0a0fedd933a8d25d6c786f795482b_Traceguids);
    v8 = WPP_GLOBAL_Control;
  }
  if ( (char *)VirtualDiskHandle - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    LastError = 6;
  }
  else if ( (Flags & 0xFFFFFFFC) != 0 || Parameters && Parameters->Version != COMPACT_VIRTUAL_DISK_VERSION_1 )
  {
    LastError = 87;
  }
  else
  {
    LastError = 0;
    HIBYTE(InBuffer) = Flags & 1;
    LOBYTE(InBuffer) = 0;
    lpBytesReturned = (DWORD *)&v12;
    v14 = (Flags & 2) != 0;
    if ( Overlapped )
      lpBytesReturned = 0;
    if ( !DeviceIoControl(VirtualDiskHandle, 0x2D1948u, &InBuffer, 3u, 0, 0, lpBytesReturned, Overlapped) )
      LastError = GetLastError();
    v8 = WPP_GLOBAL_Control;
  }
  if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 0x20) != 0 && *((_BYTE *)v8 + 25) >= 4u )
    WPP_SF_d(v8[2], 11, WPP_07b0a0fedd933a8d25d6c786f795482b_Traceguids, LastError);
  return LastError;
}

```

## disassembly

```asm
0x180008a10  mov     [rsp+arg_8], rbx
0x180008a15  mov     [rsp+arg_10], rbp
0x180008a1a  push    rsi
0x180008a1b  push    rdi
0x180008a1c  push    r15
0x180008a1e  sub     rsp, 50h
0x180008a22  xor     eax, eax
0x180008a24  mov     [rsp+68h+var_28], 0
0x180008a2c  mov     [rsp+68h+InBuffer], ax
0x180008a31  mov     rbp, r9
0x180008a34  mov     [rsp+68h+arg_2], al
0x180008a38  mov     rbx, r8
0x180008a3b  mov     edi, edx
0x180008a3d  mov     rsi, rcx
0x180008a40  mov     rcx, cs:WPP_GLOBAL_Control
0x180008a47  lea     r15, WPP_GLOBAL_Control
0x180008a4e  cmp     rcx, r15
0x180008a51  jz      short loc_180008A79
0x180008a53  test    byte ptr [rcx+1Ch], 20h
0x180008a57  jz      short loc_180008A79
0x180008a59  cmp     byte ptr [rcx+19h], 4
0x180008a5d  jb      short loc_180008A79
0x180008a5f  mov     rcx, [rcx+10h]
0x180008a63  lea     edx, [rax+0Ah]
0x180008a66  lea     r8, WPP_07b0a0fedd933a8d25d6c786f795482b_Traceguids
0x180008a6d  call    WPP_SF_
0x180008a72  mov     rcx, cs:WPP_GLOBAL_Control
0x180008a79  lea     rax, [rsi-1]
0x180008a7d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180008a81  ja      loc_180008B17
0x180008a87  test    edi, 0FFFFFFFCh
0x180008a8d  jz      short loc_180008A99
0x180008a8f  mov     ebx, 57h ; 'W'
0x180008a94  jmp     loc_180008B1C
0x180008a99  test    rbx, rbx
0x180008a9c  jz      short loc_180008AA3
0x180008a9e  cmp     dword ptr [rbx], 1
0x180008aa1  jnz     short loc_180008A8F
0x180008aa3  mov     al, dil
0x180008aa6  mov     [rsp+68h+lpOverlapped], rbp; lpOverlapped
0x180008aab  and     al, 1
0x180008aad  shr     dil, 1
0x180008ab0  xor     ebx, ebx
0x180008ab2  mov     byte ptr [rsp+68h+InBuffer+1], al
0x180008ab6  xor     eax, eax
0x180008ab8  mov     byte ptr [rsp+68h+InBuffer], bl
0x180008abc  and     dil, 1
0x180008ac0  lea     rcx, [rsp+68h+var_28]
0x180008ac5  test    rbp, rbp
0x180008ac8  mov     [rsp+68h+arg_2], dil
0x180008acd  lea     r9d, [rbx+3]; nInBufferSize
0x180008ad1  mov     edx, 2D1948h; dwIoControlCode
0x180008ad6  cmovnz  rcx, rax
0x180008ada  lea     r8, [rsp+68h+InBuffer]; lpInBuffer
0x180008adf  mov     [rsp+68h+lpBytesReturned], rcx; lpBytesReturned
0x180008ae4  mov     rcx, rsi; hDevice
0x180008ae7  mov     [rsp+68h+nOutBufferSize], eax; nOutBufferSize
0x180008aeb  mov     [rsp+68h+lpOutBuffer], rax; lpOutBuffer
0x180008af0  call    cs:__imp_DeviceIoControl
0x180008af7  nop     dword ptr [rax+rax+00h]
0x180008afc  test    eax, eax
0x180008afe  jnz     short loc_180008B0E
0x180008b00  call    cs:__imp_GetLastError
0x180008b07  nop     dword ptr [rax+rax+00h]
0x180008b0c  mov     ebx, eax
0x180008b0e  mov     rcx, cs:WPP_GLOBAL_Control
0x180008b15  jmp     short loc_180008B1C
0x180008b17  mov     ebx, 6
0x180008b1c  cmp     rcx, r15
0x180008b1f  jz      short loc_180008B45
0x180008b21  test    byte ptr [rcx+1Ch], 20h
0x180008b25  jz      short loc_180008B45
0x180008b27  cmp     byte ptr [rcx+19h], 4
0x180008b2b  jb      short loc_180008B45
0x180008b2d  mov     rcx, [rcx+10h]
0x180008b31  lea     r8, WPP_07b0a0fedd933a8d25d6c786f795482b_Traceguids
0x180008b38  mov     edx, 0Bh
0x180008b3d  mov     r9d, ebx
0x180008b40  call    WPP_SF_d
0x180008b45  lea     r11, [rsp+68h+var_18]
0x180008b4a  mov     eax, ebx
0x180008b4c  mov     rbx, [r11+28h]
0x180008b50  mov     rbp, [r11+30h]
0x180008b54  mov     rsp, r11
0x180008b57  pop     r15
0x180008b59  pop     rdi
0x180008b5a  pop     rsi
0x180008b5b  retn
```
