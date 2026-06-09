# CompleteForkVirtualDisk

- ea: `0x180008b70`
- end: `0x180008bd9`
- name: `CompleteForkVirtualDisk`
- size: `105`
- prototype: `__int64 __fastcall(char *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180008b70`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008bbb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008bbb`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180008bab`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180008bab`

## pseudocode

```c
__int64 __fastcall CompleteForkVirtualDisk(char *a1)
{
  unsigned int v1; // ebx
  DWORD v3; // [rsp+50h] [rbp+8h] BYREF

  v3 = 0;
  if ( (unsigned __int64)(a1 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    return 6;
  }
  else
  {
    v1 = 0;
    if ( !DeviceIoControl(a1, 0x2D1978u, 0, 0, 0, 0, &v3, 0) )
      return GetLastError();
  }
  return v1;
}

```

## disassembly

```asm
0x180008b70  mov     r11, rsp
0x180008b73  push    rbx
0x180008b74  sub     rsp, 40h
0x180008b78  lea     rax, [rcx-1]
0x180008b7c  mov     [rsp+48h+arg_0], 0
0x180008b84  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180008b88  ja      short loc_180008BCB
0x180008b8a  xor     ebx, ebx
0x180008b8c  lea     rax, [r11+8]
0x180008b90  mov     [r11-10h], rbx
0x180008b94  xor     r9d, r9d; nInBufferSize
0x180008b97  mov     [r11-18h], rax
0x180008b9b  xor     r8d, r8d; lpInBuffer
0x180008b9e  mov     [rsp+48h+nOutBufferSize], ebx; nOutBufferSize
0x180008ba2  mov     edx, 2D1978h; dwIoControlCode
0x180008ba7  mov     [r11-28h], rbx
0x180008bab  call    cs:__imp_DeviceIoControl
0x180008bb2  nop     dword ptr [rax+rax+00h]
0x180008bb7  test    eax, eax
0x180008bb9  jnz     short loc_180008BD0
0x180008bbb  call    cs:__imp_GetLastError
0x180008bc2  nop     dword ptr [rax+rax+00h]
0x180008bc7  mov     ebx, eax
0x180008bc9  jmp     short loc_180008BD0
0x180008bcb  mov     ebx, 6
0x180008bd0  mov     eax, ebx
0x180008bd2  add     rsp, 40h
0x180008bd6  pop     rbx
0x180008bd7  retn
```
