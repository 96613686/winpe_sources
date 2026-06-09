# WinHvUpdateSecFw

- ea: `0x140024110`
- end: `0x140024259`
- name: `WinHvUpdateSecFw`
- size: `329`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, installer_update`

## callees

- `0x140002240`
- `0x140002358`
- `0x140003610`
- `0x1400043f0`
- `0x140004b1c`
- `0x140007d70`
- `0x140007da4`
- `0x140009c90`
- `0x14000a040`
- `0x140024110`

## pseudocode

```c
__int64 __fastcall WinHvUpdateSecFw(char a1, int a2, int a3, __int64 a4, int a5)
{
  int v9; // esi
  int i; // edi
  __int64 *v11; // rax
  int v12; // ebx
  __int64 *v14; // [rsp+30h] [rbp-41h] BYREF
  _QWORD v15[16]; // [rsp+40h] [rbp-31h] BYREF

  memset(v15, 0, 0x40u);
  v14 = 0;
  v9 = (a1 != 0) + 2;
  for ( i = 0; ; ++i )
  {
    if ( !v15[0] )
    {
      WinHvpSetupHypercall(&v14, 0, (__int64)v15);
      v11 = v14;
      *(_OWORD *)v14 = 0;
      *((_OWORD *)v11 + 1) = 0;
      *((_DWORD *)v11 + 6) = v9;
      *(_DWORD *)v11 = a2;
      *((_DWORD *)v11 + 1) = a3;
      v11[1] = a4;
      *((_DWORD *)v11 + 4) = a5;
    }
    WinHvpAcquireAsyncMessage(0);
    v12 = WinHvpSimplePoolHypercall_CallViaMacro(v15, 7);
    if ( (unsigned __int8)WinHvpIsHypercallFallbackBuffer(v15) )
    {
      ((void (__fastcall *)(_QWORD))v15[7])(v15[0]);
      v15[0] = 0;
    }
    if ( v12 == -1070268295 )
      break;
    WinHvpReleaseAsyncMessage(0);
    if ( v12 != -1070268299 && v12 != -1070268405 && (unsigned int)(v12 + 1070268287) > 1 )
      goto LABEL_13;
    v12 = WinHvpLowMemoryHandler(-1, -2147418113, v12, v9, i, 0);
    if ( v12 < 0 )
      goto LABEL_13;
  }
  v12 = WinHvpWaitForAsyncCall(0, 0, 0);
  WinHvpReleaseAsyncMessage(0);
LABEL_13:
  if ( v15[0] )
    ((void (*)(void))v15[7])();
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x140024110  push    rbp
0x140024112  push    rbx
0x140024113  push    rsi
0x140024114  push    rdi
0x140024115  push    r12
0x140024117  push    r13
0x140024119  push    r14
0x14002411b  push    r15
0x14002411d  lea     rbp, [rsp-17h]
0x140024122  sub     rsp, 88h
0x140024129  mov     r12d, edx
0x14002412c  mov     r15d, r8d
0x14002412f  xor     edx, edx; Val
0x140024131  mov     bl, cl
0x140024133  lea     rcx, [rbp+4Fh+var_80]; void *
0x140024137  mov     r14, r9
0x14002413a  lea     r8d, [rdx+40h]; Size
0x14002413e  call    memset
0x140024143  mov     r13d, [rbp+4Fh+arg_20]
0x140024147  neg     bl
0x140024149  mov     [rbp+4Fh+var_90], 0
0x140024151  sbb     esi, esi
0x140024153  neg     esi
0x140024155  add     esi, 2
0x140024158  xor     edi, edi
0x14002415a  cmp     [rbp+4Fh+var_80], 0
0x14002415f  jnz     short loc_140024190
0x140024161  lea     r8, [rbp+4Fh+var_80]
0x140024165  xor     edx, edx
0x140024167  lea     rcx, [rbp+4Fh+var_90]
0x14002416b  call    WinHvpSetupHypercall
0x140024170  mov     rax, [rbp+4Fh+var_90]
0x140024174  xorps   xmm0, xmm0
0x140024177  movups  xmmword ptr [rax], xmm0
0x14002417a  movups  xmmword ptr [rax+10h], xmm0
0x14002417e  mov     [rax+18h], esi
0x140024181  mov     [rax], r12d
0x140024184  mov     [rax+4], r15d
0x140024188  mov     [rax+8], r14
0x14002418c  mov     [rax+10h], r13d
0x140024190  xor     ecx, ecx
0x140024192  call    WinHvpAcquireAsyncMessage
0x140024197  mov     edx, 7
0x14002419c  lea     rcx, [rbp+4Fh+var_80]
0x1400241a0  call    WinHvpSimplePoolHypercall_CallViaMacro
0x1400241a5  lea     rcx, [rbp+4Fh+var_80]
0x1400241a9  mov     ebx, eax
0x1400241ab  call    WinHvpIsHypercallFallbackBuffer
0x1400241b0  test    al, al
0x1400241b2  jz      short loc_1400241C9
0x1400241b4  mov     rcx, [rbp+4Fh+var_80]
0x1400241b8  mov     rax, [rbp+4Fh+var_48]
0x1400241bc  call    _guard_dispatch_icall
0x1400241c1  mov     [rbp+4Fh+var_80], 0
0x1400241c9  xor     ecx, ecx
0x1400241cb  cmp     ebx, 0C0350079h
0x1400241d1  jz      short loc_14002421D
0x1400241d3  call    WinHvpReleaseAsyncMessage
0x1400241d8  cmp     ebx, 0C0350075h
0x1400241de  jz      short loc_1400241F3
0x1400241e0  cmp     ebx, 0C035000Bh
0x1400241e6  jz      short loc_1400241F3
0x1400241e8  lea     eax, [rbx+3FCAFF7Fh]
0x1400241ee  cmp     eax, 1
0x1400241f1  ja      short loc_140024230
0x1400241f3  mov     [rsp+0C0h+var_98], 0
0x1400241f8  mov     r9d, esi
0x1400241fb  mov     r8d, ebx
0x1400241fe  mov     [rsp+0C0h+var_A0], edi
0x140024202  mov     edx, 8000FFFFh
0x140024207  or      rcx, 0FFFFFFFFFFFFFFFFh
0x14002420b  call    WinHvpLowMemoryHandler
0x140024210  mov     ebx, eax
0x140024212  test    eax, eax
0x140024214  js      short loc_140024230
0x140024216  inc     edi
0x140024218  jmp     loc_14002415A
0x14002421d  xor     r8d, r8d
0x140024220  xor     edx, edx
0x140024222  call    WinHvpWaitForAsyncCall
0x140024227  xor     ecx, ecx
0x140024229  mov     ebx, eax
0x14002422b  call    WinHvpReleaseAsyncMessage
0x140024230  mov     rcx, [rbp+4Fh+var_80]
0x140024234  test    rcx, rcx
0x140024237  jz      short loc_140024242
0x140024239  mov     rax, [rbp+4Fh+var_48]
0x14002423d  call    _guard_dispatch_icall
0x140024242  mov     eax, ebx
0x140024244  add     rsp, 88h
0x14002424b  pop     r15
0x14002424d  pop     r14
0x14002424f  pop     r13
0x140024251  pop     r12
0x140024253  pop     rdi
0x140024254  pop     rsi
0x140024255  pop     rbx
0x140024256  pop     rbp
0x140024257  retn
```
