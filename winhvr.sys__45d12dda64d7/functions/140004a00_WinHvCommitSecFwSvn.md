# WinHvCommitSecFwSvn

- ea: `0x140004a00`
- end: `0x140004b14`
- name: `WinHvCommitSecFwSvn`
- size: `276`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x140002240`
- `0x140002358`
- `0x140003610`
- `0x140004a00`
- `0x140004b1c`
- `0x140007d70`
- `0x140007da4`
- `0x140009c90`
- `0x14000a040`

## pseudocode

```c
__int64 WinHvCommitSecFwSvn()
{
  int v0; // edi
  __int64 *v1; // rax
  int v2; // ebx
  _QWORD v4[8]; // [rsp+30h] [rbp-40h] BYREF
  __int64 *v5; // [rsp+80h] [rbp+10h] BYREF

  memset(v4, 0, sizeof(v4));
  v0 = 0;
  v5 = 0;
  while ( 1 )
  {
    if ( !v4[0] )
    {
      WinHvpSetupHypercall(&v5, 0, (__int64)v4);
      v1 = v5;
      *(_OWORD *)v5 = 0;
      *((_OWORD *)v1 + 1) = 0;
      *((_DWORD *)v1 + 6) = 4;
    }
    WinHvpAcquireAsyncMessage(0);
    v2 = WinHvpSimplePoolHypercall_CallViaMacro(v4, 7);
    if ( (__int64 (__fastcall *)())v4[7] == WinHvpReleaseFallbackBuffers )
    {
      ((void (__fastcall *)(_QWORD))v4[7])(v4[0]);
      v4[0] = 0;
    }
    if ( v2 == -1070268295 )
      break;
    WinHvpReleaseAsyncMessage(0);
    if ( v2 != -1070268405 && v2 != -1070268299 )
      goto LABEL_12;
    v2 = WinHvpLowMemoryHandler(-1, -2147418113, v2, 2, v0, 0);
    if ( v2 < 0 )
      goto LABEL_12;
    ++v0;
  }
  v2 = WinHvpWaitForAsyncCall(0, 0, 0);
  WinHvpReleaseAsyncMessage(0);
LABEL_12:
  if ( v4[0] )
    ((void (*)(void))v4[7])();
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x140004a00  mov     [rsp-8+arg_8], rbx
0x140004a05  mov     [rsp-8+arg_10], rdi
0x140004a0a  push    rbp
0x140004a0b  mov     rbp, rsp
0x140004a0e  sub     rsp, 70h
0x140004a12  xor     edx, edx; Val
0x140004a14  lea     rcx, [rbp+var_40]; void *
0x140004a18  lea     r8d, [rdx+40h]; Size
0x140004a1c  call    memset
0x140004a21  xor     edi, edi
0x140004a23  mov     [rbp+arg_0], 0
0x140004a2b  cmp     [rbp+var_40], 0
0x140004a30  jnz     short loc_140004A56
0x140004a32  lea     r8, [rbp+var_40]
0x140004a36  xor     edx, edx
0x140004a38  lea     rcx, [rbp+arg_0]
0x140004a3c  call    WinHvpSetupHypercall
0x140004a41  mov     rax, [rbp+arg_0]
0x140004a45  xorps   xmm0, xmm0
0x140004a48  movups  xmmword ptr [rax], xmm0
0x140004a4b  movups  xmmword ptr [rax+10h], xmm0
0x140004a4f  mov     dword ptr [rax+18h], 4
0x140004a56  xor     ecx, ecx
0x140004a58  call    WinHvpAcquireAsyncMessage
0x140004a5d  mov     edx, 7
0x140004a62  lea     rcx, [rbp+var_40]
0x140004a66  call    WinHvpSimplePoolHypercall_CallViaMacro
0x140004a6b  mov     ebx, eax
0x140004a6d  lea     rcx, WinHvpReleaseFallbackBuffers
0x140004a74  mov     rax, [rbp+var_8]
0x140004a78  cmp     rax, rcx
0x140004a7b  jnz     short loc_140004A8E
0x140004a7d  mov     rcx, [rbp+var_40]
0x140004a81  call    _guard_dispatch_icall
0x140004a86  mov     [rbp+var_40], 0
0x140004a8e  xor     ecx, ecx
0x140004a90  cmp     ebx, 0C0350079h
0x140004a96  jz      short loc_140004ADA
0x140004a98  call    WinHvpReleaseAsyncMessage
0x140004a9d  cmp     ebx, 0C035000Bh
0x140004aa3  jz      short loc_140004AAD
0x140004aa5  cmp     ebx, 0C0350075h
0x140004aab  jnz     short loc_140004AED
0x140004aad  mov     [rsp+70h+var_48], 0
0x140004ab2  mov     r9d, 2
0x140004ab8  mov     r8d, ebx
0x140004abb  mov     [rsp+70h+var_50], edi
0x140004abf  mov     edx, 8000FFFFh
0x140004ac4  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140004ac8  call    WinHvpLowMemoryHandler
0x140004acd  mov     ebx, eax
0x140004acf  test    eax, eax
0x140004ad1  js      short loc_140004AED
0x140004ad3  inc     edi
0x140004ad5  jmp     loc_140004A2B
0x140004ada  xor     r8d, r8d
0x140004add  xor     edx, edx
0x140004adf  call    WinHvpWaitForAsyncCall
0x140004ae4  xor     ecx, ecx
0x140004ae6  mov     ebx, eax
0x140004ae8  call    WinHvpReleaseAsyncMessage
0x140004aed  mov     rcx, [rbp+var_40]
0x140004af1  test    rcx, rcx
0x140004af4  jz      short loc_140004AFF
0x140004af6  mov     rax, [rbp+var_8]
0x140004afa  call    _guard_dispatch_icall
0x140004aff  lea     r11, [rsp+70h+var_s0]
0x140004b04  mov     eax, ebx
0x140004b06  mov     rbx, [r11+18h]
0x140004b0a  mov     rdi, [r11+20h]
0x140004b0e  mov     rsp, r11
0x140004b11  pop     rbp
0x140004b12  retn
```
