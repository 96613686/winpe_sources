# SetInetOffline

- ea: `0x180001a10`
- end: `0x180001a65`
- name: `SetInetOffline`
- size: `85`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180001a10`

## import_xrefs

- `WININET!InternetSetOptionA` at `0x180001a50`
- `WININET!InternetSetOptionA` at `0x180001a50`

## pseudocode

```c
__int64 __fastcall SetInetOffline(unsigned int a1)
{
  __int64 Buffer; // [rsp+38h] [rbp+10h] BYREF

  Buffer = 0;
  if ( a1 )
    Buffer = 0x100000010LL;
  else
    LODWORD(Buffer) = 1;
  InternetSetOptionA(0, 0x32u, &Buffer, 8u);
  return a1;
}

```

## disassembly

```asm
0x180001a10  push    rbx
0x180001a12  sub     rsp, 20h
0x180001a16  mov     [rsp+28h+Buffer], 0
0x180001a1f  mov     ebx, ecx
0x180001a21  test    ecx, ecx
0x180001a23  jz      short loc_180001A37
0x180001a25  mov     dword ptr [rsp+28h+Buffer], 10h
0x180001a2d  mov     dword ptr [rsp+28h+Buffer+4], 1
0x180001a35  jmp     short loc_180001A3F
0x180001a37  mov     dword ptr [rsp+28h+Buffer], 1
0x180001a3f  mov     r9d, 8; dwBufferLength
0x180001a45  lea     r8, [rsp+28h+Buffer]; lpBuffer
0x180001a4a  xor     ecx, ecx; hInternet
0x180001a4c  lea     edx, [r9+2Ah]; dwOption
0x180001a50  call    cs:__imp_InternetSetOptionA
0x180001a57  nop     dword ptr [rax+rax+00h]
0x180001a5c  mov     eax, ebx
0x180001a5e  add     rsp, 20h
0x180001a62  pop     rbx
0x180001a63  retn
```
