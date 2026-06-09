# Storage::CVolume::_UpdateTrackInfo(void *)

- ea: `0x18002d66c`
- end: `0x18002d82e`
- name: `?_UpdateTrackInfo@CVolume@Storage@@AEAAJPEAX@Z`
- size: `450`
- prototype: `__int64 __fastcall(Storage::CVolume *this, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x18002d4d8`

## callees

- `0x18002d66c`
- `0x180032c6a`
- `0x180032c90`

## import_xrefs

- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18002d6e0`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18002d74e`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18002d7a6`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18002d6e0`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18002d74e`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18002d7a6`

## pseudocode

```c
__int64 __fastcall Storage::CVolume::_UpdateTrackInfo(Storage::CVolume *this, void *a2)
{
  int v4; // eax
  int v5; // eax
  __int64 v6; // r8
  int v7; // edx
  int v8; // eax
  __int16 InBuffer[2]; // [rsp+40h] [rbp-C0h] BYREF
  int OutBuffer; // [rsp+44h] [rbp-BCh] BYREF
  DWORD BytesReturned; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v13[32]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE lpOutBuffer[816]; // [rsp+70h] [rbp-90h] BYREF

  OutBuffer = 0;
  BytesReturned = 0;
  if ( DeviceIoControl(a2, 0x20040u, 0, 0, &OutBuffer, 4u, &BytesReturned, 0) )
  {
    if ( (OutBuffer & 1) != 0 )
      *((_DWORD *)this + 11) |= 0x10u;
    if ( (OutBuffer & 2) != 0 )
      *((_DWORD *)this + 11) |= 0x20u;
  }
  else
  {
    memset_0(lpOutBuffer, 0, 0x324u);
    if ( DeviceIoControl(a2, 0x24000u, 0, 0, lpOutBuffer, 0x324u, &BytesReturned, 0) )
    {
      v6 = 0;
      v7 = lpOutBuffer[3] - lpOutBuffer[2] + 1;
      if ( v7 > 0 )
      {
        do
        {
          if ( (*((_BYTE *)this + 44) & 0x30) == 0x30 )
            break;
          v8 = -((lpOutBuffer[8 * v6 + 5] & 4) != 0);
          v6 = (unsigned int)(v6 + 1);
          *((_DWORD *)this + 11) |= (v8 & 0x10) + 16;
        }
        while ( (int)v6 < v7 );
      }
    }
    else
    {
      memset(v13, 0, 24);
      InBuffer[0] = 1;
      if ( DeviceIoControl(a2, 0x2402Cu, InBuffer, 2u, v13, 0x18u, &BytesReturned, 0) )
      {
        v4 = *((_DWORD *)this + 11);
        if ( (v13[5] & 4) != 0 )
          v5 = v4 | 0x20;
        else
          v5 = v4 | 0x10;
        *((_DWORD *)this + 11) = v5;
      }
      *((_DWORD *)this + 11) |= 0x80u;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18002d66c  mov     [rsp-8+arg_10], rbx
0x18002d671  mov     [rsp-8+arg_18], rdi
0x18002d676  push    rbp
0x18002d677  lea     rbp, [rsp-2B0h]
0x18002d67f  sub     rsp, 3B0h
0x18002d686  mov     rax, cs:__security_cookie
0x18002d68d  xor     rax, rsp
0x18002d690  mov     [rbp+2B0h+var_10], rax
0x18002d697  mov     [rsp+3B0h+lpOverlapped], 0; lpOverlapped
0x18002d6a0  lea     rax, [rsp+3B0h+BytesReturned]
0x18002d6a5  mov     [rsp+3B0h+lpBytesReturned], rax; lpBytesReturned
0x18002d6aa  mov     rdi, rdx
0x18002d6ad  lea     rax, [rsp+3B0h+OutBuffer]
0x18002d6b2  mov     [rsp+3B0h+nOutBufferSize], 4; nOutBufferSize
0x18002d6ba  mov     rbx, rcx
0x18002d6bd  mov     [rsp+3B0h+lpOutBuffer], rax; lpOutBuffer
0x18002d6c2  xor     r9d, r9d; nInBufferSize
0x18002d6c5  mov     [rsp+3B0h+OutBuffer], 0
0x18002d6cd  xor     r8d, r8d; lpInBuffer
0x18002d6d0  mov     [rsp+3B0h+BytesReturned], 0
0x18002d6d8  mov     edx, 20040h; dwIoControlCode
0x18002d6dd  mov     rcx, rdi; hDevice
0x18002d6e0  call    cs:__imp_DeviceIoControl
0x18002d6e6  test    eax, eax
0x18002d6e8  jz      short loc_18002D709
0x18002d6ea  test    byte ptr [rsp+3B0h+OutBuffer], 1
0x18002d6ef  jz      short loc_18002D6F5
0x18002d6f1  or      dword ptr [rbx+2Ch], 10h
0x18002d6f5  test    byte ptr [rsp+3B0h+OutBuffer], 2
0x18002d6fa  jz      loc_18002D808
0x18002d700  or      dword ptr [rbx+2Ch], 20h
0x18002d704  jmp     loc_18002D808
0x18002d709  xor     edx, edx; Val
0x18002d70b  lea     rcx, [rsp+3B0h+var_340]; void *
0x18002d710  mov     r8d, 324h; Size
0x18002d716  call    memset_0
0x18002d71b  mov     [rsp+3B0h+lpOverlapped], 0; lpOverlapped
0x18002d724  lea     rax, [rsp+3B0h+BytesReturned]
0x18002d729  mov     [rsp+3B0h+lpBytesReturned], rax; lpBytesReturned
0x18002d72e  xor     r9d, r9d; nInBufferSize
0x18002d731  lea     rax, [rsp+3B0h+var_340]
0x18002d736  mov     [rsp+3B0h+nOutBufferSize], 324h; nOutBufferSize
0x18002d73e  xor     r8d, r8d; lpInBuffer
0x18002d741  mov     [rsp+3B0h+lpOutBuffer], rax; lpOutBuffer
0x18002d746  mov     edx, 24000h; dwIoControlCode
0x18002d74b  mov     rcx, rdi; hDevice
0x18002d74e  call    cs:__imp_DeviceIoControl
0x18002d754  test    eax, eax
0x18002d756  jnz     short loc_18002D7CC
0x18002d758  mov     [rsp+3B0h+var_360], al
0x18002d75c  lea     r8, [rsp+3B0h+InBuffer]; lpInBuffer
0x18002d761  xor     eax, eax
0x18002d763  mov     [rsp+3B0h+InBuffer], 1
0x18002d76a  mov     [rsp+3B0h+lpOverlapped], rax; lpOverlapped
0x18002d76f  xorps   xmm0, xmm0
0x18002d772  movups  xmmword ptr [rsp+3B0h+var_35F], xmm0
0x18002d777  mov     qword ptr [rsp+3B0h+var_35F+0Fh], rax
0x18002d77c  mov     r9d, 2; nInBufferSize
0x18002d782  lea     rax, [rsp+3B0h+BytesReturned]
0x18002d787  mov     edx, 2402Ch; dwIoControlCode
0x18002d78c  mov     [rsp+3B0h+lpBytesReturned], rax; lpBytesReturned
0x18002d791  mov     rcx, rdi; hDevice
0x18002d794  lea     rax, [rsp+3B0h+var_360]
0x18002d799  mov     [rsp+3B0h+nOutBufferSize], 18h; nOutBufferSize
0x18002d7a1  mov     [rsp+3B0h+lpOutBuffer], rax; lpOutBuffer
0x18002d7a6  call    cs:__imp_DeviceIoControl
0x18002d7ac  test    eax, eax
0x18002d7ae  jz      short loc_18002D7C5
0x18002d7b0  test    [rsp+3B0h+var_35F+4], 4
0x18002d7b5  mov     eax, [rbx+2Ch]
0x18002d7b8  jz      short loc_18002D7BF
0x18002d7ba  or      eax, 20h
0x18002d7bd  jmp     short loc_18002D7C2
0x18002d7bf  or      eax, 10h
0x18002d7c2  mov     [rbx+2Ch], eax
0x18002d7c5  bts     dword ptr [rbx+2Ch], 7
0x18002d7ca  jmp     short loc_18002D808
0x18002d7cc  movzx   eax, [rsp+3B0h+var_33E]
0x18002d7d1  xor     r8d, r8d
0x18002d7d4  movzx   edx, [rsp+3B0h+var_33D]
0x18002d7d9  sub     edx, eax
0x18002d7db  inc     edx
0x18002d7dd  test    edx, edx
0x18002d7df  jle     short loc_18002D808
0x18002d7e1  mov     eax, [rbx+2Ch]
0x18002d7e4  and     eax, 30h
0x18002d7e7  cmp     al, 30h ; '0'
0x18002d7e9  jz      short loc_18002D808
0x18002d7eb  mov     cl, [rsp+r8*8+3B0h+var_33B]
0x18002d7f0  and     cl, 4
0x18002d7f3  neg     cl
0x18002d7f5  sbb     eax, eax
0x18002d7f7  inc     r8d
0x18002d7fa  and     eax, 10h
0x18002d7fd  add     eax, 10h
0x18002d800  or      [rbx+2Ch], eax
0x18002d803  cmp     r8d, edx
0x18002d806  jl      short loc_18002D7E1
0x18002d808  xor     eax, eax
0x18002d80a  mov     rcx, [rbp+2B0h+var_10]
0x18002d811  xor     rcx, rsp; StackCookie
0x18002d814  call    __security_check_cookie
0x18002d819  lea     r11, [rsp+3B0h+var_s0]
0x18002d821  mov     rbx, [r11+20h]
0x18002d825  mov     rdi, [r11+28h]
0x18002d829  mov     rsp, r11
0x18002d82c  pop     rbp
0x18002d82d  retn
```
