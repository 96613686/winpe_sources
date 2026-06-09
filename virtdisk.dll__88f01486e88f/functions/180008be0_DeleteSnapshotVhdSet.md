# DeleteSnapshotVhdSet

- ea: `0x180008be0`
- end: `0x180008c9e`
- name: `DeleteSnapshotVhdSet`
- size: `190`
- prototype: `DWORD __fastcall(void *, __int64, int)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180005730`
- `0x180008be0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008c74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008c74`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180008c64`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180008c64`

## pseudocode

```c
DWORD __fastcall DeleteSnapshotVhdSet(void *a1, __int64 a2, int a3)
{
  __int128 v3; // xmm0
  int v4; // eax
  __int128 v6; // [rsp+40h] [rbp-28h] BYREF
  __int64 v7; // [rsp+50h] [rbp-18h]

  v6 = 0;
  v7 = 0;
  if ( *(_DWORD *)a2 != 1 || (a3 & 0xFFFFFFFE) != 0 )
    return 87;
  v3 = *(_OWORD *)(a2 + 4);
  v4 = HIDWORD(v7);
  if ( (a3 & 1) != 0 )
    v4 = 2;
  HIDWORD(v7) = v4;
  v6 = v3;
  LOWORD(v7) = 1;
  if ( DeviceIoControl(a1, 0x2D1A4Cu, &v6, 0x18u, 0, 0, 0, 0) )
    return 0;
  else
    return GetLastError();
}

```

## disassembly

```asm
0x180008be0  mov     r11, rsp
0x180008be3  sub     rsp, 68h
0x180008be7  mov     rax, cs:__security_cookie
0x180008bee  xor     rax, rsp
0x180008bf1  mov     [rsp+68h+var_10], rax
0x180008bf6  xor     eax, eax
0x180008bf8  xorps   xmm0, xmm0
0x180008bfb  movups  [rsp+68h+var_28], xmm0
0x180008c00  mov     [r11-18h], rax
0x180008c04  lea     r9d, [rax+1]
0x180008c08  cmp     [rdx], r9d
0x180008c0b  jnz     short loc_180008C86
0x180008c0d  test    r8d, 0FFFFFFFEh
0x180008c14  jnz     short loc_180008C86
0x180008c16  movups  xmm0, xmmword ptr [rdx+4]
0x180008c1a  mov     eax, [rsp+68h+var_14]
0x180008c1e  lea     edx, [r9+1]
0x180008c22  test    r9b, r8b
0x180008c25  mov     qword ptr [r11-30h], 0
0x180008c2d  mov     qword ptr [r11-38h], 0
0x180008c35  lea     r8, [r11-28h]; lpInBuffer
0x180008c39  cmovnz  eax, edx
0x180008c3c  mov     [rsp+68h+nOutBufferSize], 0; nOutBufferSize
0x180008c44  mov     [rsp+68h+var_14], eax
0x180008c48  movdqu  [rsp+68h+var_28], xmm0
0x180008c4e  mov     [r11-18h], r9w
0x180008c53  lea     r9d, [rdx+16h]; nInBufferSize
0x180008c57  mov     edx, 2D1A4Ch; dwIoControlCode
0x180008c5c  mov     qword ptr [r11-48h], 0
0x180008c64  call    cs:__imp_DeviceIoControl
0x180008c6b  nop     dword ptr [rax+rax+00h]
0x180008c70  test    eax, eax
0x180008c72  jnz     short loc_180008C82
0x180008c74  call    cs:__imp_GetLastError
0x180008c7b  nop     dword ptr [rax+rax+00h]
0x180008c80  jmp     short loc_180008C8B
0x180008c82  xor     eax, eax
0x180008c84  jmp     short loc_180008C8B
0x180008c86  mov     eax, 57h ; 'W'
0x180008c8b  mov     rcx, [rsp+68h+var_10]
0x180008c90  xor     rcx, rsp; StackCookie
0x180008c93  call    __security_check_cookie
0x180008c98  add     rsp, 68h
0x180008c9c  retn
```
