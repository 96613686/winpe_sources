# DeleteVirtualDiskMetadata

- ea: `0x18000b620`
- end: `0x18000b699`
- name: `DeleteVirtualDiskMetadata`
- size: `121`
- prototype: `DWORD __fastcall(char *, __int128 *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180004110`
- `0x180005730`
- `0x18000b620`

## pseudocode

```c
DWORD __fastcall DeleteVirtualDiskMetadata(char *a1, __int128 *a2)
{
  __int128 v3; // xmm0
  __int128 InBuffer; // [rsp+40h] [rbp-28h] BYREF
  int v5; // [rsp+50h] [rbp-18h]

  if ( (unsigned __int64)(a1 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    return 6;
  if ( !a2 )
    return 87;
  v3 = *a2;
  v5 = 0;
  InBuffer = v3;
  return IssueSynchronousDeviceIoControl(a1, 0x2D19CCu, &InBuffer, 0x14u, 0, 0, 0);
}

```

## disassembly

```asm
0x18000b620  sub     rsp, 68h
0x18000b624  mov     rax, cs:__security_cookie
0x18000b62b  xor     rax, rsp
0x18000b62e  mov     [rsp+68h+var_10], rax
0x18000b633  lea     rax, [rcx-1]
0x18000b637  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000b63b  ja      short loc_18000B681
0x18000b63d  test    rdx, rdx
0x18000b640  jnz     short loc_18000B647
0x18000b642  lea     eax, [rdx+57h]
0x18000b645  jmp     short loc_18000B686
0x18000b647  movups  xmm0, xmmword ptr [rdx]
0x18000b64a  xor     eax, eax
0x18000b64c  lea     r8, [rsp+68h+InBuffer]; lpInBuffer
0x18000b651  mov     [rsp+68h+lpNumberOfBytesTransferred], rax; lpNumberOfBytesTransferred
0x18000b656  mov     edx, 2D19CCh; dwIoControlCode
0x18000b65b  mov     [rsp+68h+var_18], eax
0x18000b65f  mov     [rsp+68h+var_40], eax; DWORD
0x18000b663  lea     r9d, [rax+14h]; nInBufferSize
0x18000b667  mov     byte ptr [rsp+68h+var_18], al
0x18000b66b  movdqu  [rsp+68h+InBuffer], xmm0
0x18000b671  mov     [rsp+68h+var_48], rax; LPVOID
0x18000b676  call    IssueSynchronousDeviceIoControl
0x18000b67b  test    eax, eax
0x18000b67d  jnz     short loc_18000B686
0x18000b67f  jmp     short loc_18000B686
0x18000b681  mov     eax, 6
0x18000b686  mov     rcx, [rsp+68h+var_10]
0x18000b68b  xor     rcx, rsp; StackCookie
0x18000b68e  call    __security_check_cookie
0x18000b693  add     rsp, 68h
0x18000b697  retn
```
