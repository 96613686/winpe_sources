# __DllMainCRTStartup

- ea: `0x180001fa4`
- end: `0x1800021b0`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001f60`

## callees

- `0x180001d30`
- `0x180001fa4`
- `0x1800026d6`
- `0x180005950`
- `0x18001b090`

## pseudocode

```c
__int64 __fastcall _DllMainCRTStartup(HINSTANCE hinstDLL, __int64 fdwReason, void *a3)
{
  DWORD v3; // edi
  unsigned int v5; // ebx

  v3 = fdwReason;
  v5 = 1;
  if ( (unsigned int)fdwReason <= 1 )
    _native_dllmain_reason = fdwReason;
  if ( (_DWORD)fdwReason || dword_18002A5CC )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_18002A5D0 = 1;
      v5 = pRawDllMain(hinstDLL, fdwReason, a3);
    }
    if ( v5 )
    {
      v5 = CRT_INIT(hinstDLL, v3, a3);
      if ( v5 )
      {
LABEL_13:
        v5 = DllMain(hinstDLL, v3, a3);
        if ( v3 == 1 && !v5 )
        {
          DllMain(hinstDLL, 0, 0);
          CRT_INIT(hinstDLL, 0, 0);
          if ( pRawDllMain )
            pRawDllMain(hinstDLL, 0, 0);
        }
        if ( !v3 || v3 == 3 )
        {
          v5 = CRT_INIT(hinstDLL, v3, a3);
          if ( pRawDllMain )
          {
            if ( dword_18002A5D0 )
              v5 = pRawDllMain(hinstDLL, v3, a3);
          }
        }
      }
    }
  }
  else
  {
    v5 = 0;
  }
  if ( v3 <= 1 )
    _native_dllmain_reason = -1;
  return v5;
}

```

## disassembly

```asm
0x180001fa4  mov     [rsp+lpvReserved], r8
0x180001fa9  mov     [rsp+arg_8], edx
0x180001fad  mov     [rsp+arg_0], rcx
0x180001fb2  push    rbx
0x180001fb3  push    rsi
0x180001fb4  push    rdi
0x180001fb5  sub     rsp, 0F0h
0x180001fbc  mov     edi, edx
0x180001fbe  mov     rsi, rcx
0x180001fc1  mov     ebx, 1
0x180001fc6  cmp     edx, ebx
0x180001fc8  ja      short loc_180001FD0
0x180001fca  mov     cs:__native_dllmain_reason, edx
0x180001fd0  test    edx, edx
0x180001fd2  jnz     short loc_180001FE7
0x180001fd4  cmp     cs:dword_18002A5CC, edx
0x180001fda  jnz     short loc_180001FE7
0x180001fdc  xor     ebx, ebx
0x180001fde  mov     [rsp+108h+var_E8], ebx
0x180001fe2  jmp     loc_180002194
0x180001fe7  lea     eax, [rdx-1]
0x180001fea  cmp     eax, 1
0x180001fed  ja      loc_180002074
0x180001ff3  mov     rax, cs:_pRawDllMain
0x180001ffa  test    rax, rax
0x180001ffd  jz      short loc_180002035
0x180001fff  cmp     edx, 1
0x180002002  jnz     short loc_18000200A
0x180002004  mov     cs:dword_18002A5D0, edx
0x18000200a  mov     r8, [rsp+108h+lpvReserved]
0x180002012  call    cs:__guard_dispatch_icall_fptr
0x180002018  mov     ebx, eax
0x18000201a  mov     [rsp+108h+var_E8], eax
0x18000201e  jmp     short loc_180002035
0x180002020  xor     ebx, ebx
0x180002022  mov     [rsp+108h+var_E8], ebx
0x180002026  mov     edi, [rsp+108h+arg_8]
0x18000202d  mov     rsi, [rsp+108h+arg_0]
0x180002035  test    ebx, ebx
0x180002037  jz      loc_180002194
0x18000203d  mov     r8, [rsp+108h+lpvReserved]
0x180002045  mov     edx, edi
0x180002047  mov     rcx, rsi
0x18000204a  call    _CRT_INIT
0x18000204f  mov     ebx, eax
0x180002051  mov     [rsp+108h+var_E8], eax
0x180002055  jmp     short loc_18000206C
0x180002057  xor     ebx, ebx
0x180002059  mov     [rsp+108h+var_E8], ebx
0x18000205d  mov     edi, [rsp+108h+arg_8]
0x180002064  mov     rsi, [rsp+108h+arg_0]
0x18000206c  test    ebx, ebx
0x18000206e  jz      loc_180002194
0x180002074  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18000207c  mov     edx, edi; fdwReason
0x18000207e  mov     rcx, rsi; hinstDLL
0x180002081  call    DllMain
0x180002086  mov     ebx, eax
0x180002088  mov     [rsp+108h+var_E8], eax
0x18000208c  jmp     short loc_1800020A3
0x18000208e  xor     ebx, ebx
0x180002090  mov     [rsp+108h+var_E8], ebx
0x180002094  mov     edi, [rsp+108h+arg_8]
0x18000209b  mov     rsi, [rsp+108h+arg_0]
0x1800020a3  cmp     edi, 1
0x1800020a6  jnz     short loc_18000211F
0x1800020a8  test    ebx, ebx
0x1800020aa  jnz     short loc_18000211F
0x1800020ac  xor     r8d, r8d; lpvReserved
0x1800020af  xor     edx, edx; fdwReason
0x1800020b1  mov     rcx, rsi; hinstDLL
0x1800020b4  call    DllMain
0x1800020b9  jmp     short loc_1800020CE
0x1800020bb  mov     edi, [rsp+108h+arg_8]
0x1800020c2  mov     rsi, [rsp+108h+arg_0]
0x1800020ca  mov     ebx, [rsp+108h+var_E8]
0x1800020ce  xor     r8d, r8d
0x1800020d1  xor     edx, edx
0x1800020d3  mov     rcx, rsi
0x1800020d6  call    _CRT_INIT
0x1800020db  jmp     short loc_1800020F0
0x1800020dd  mov     edi, [rsp+108h+arg_8]
0x1800020e4  mov     rsi, [rsp+108h+arg_0]
0x1800020ec  mov     ebx, [rsp+108h+var_E8]
0x1800020f0  mov     rax, cs:_pRawDllMain
0x1800020f7  test    rax, rax
0x1800020fa  jz      short loc_18000211F
0x1800020fc  xor     r8d, r8d
0x1800020ff  xor     edx, edx
0x180002101  mov     rcx, rsi
0x180002104  call    cs:__guard_dispatch_icall_fptr
0x18000210a  jmp     short loc_18000211F
0x18000210c  mov     edi, [rsp+108h+arg_8]
0x180002113  mov     rsi, [rsp+108h+arg_0]
0x18000211b  mov     ebx, [rsp+108h+var_E8]
0x18000211f  test    edi, edi
0x180002121  jz      short loc_180002128
0x180002123  cmp     edi, 3
0x180002126  jnz     short loc_180002194
0x180002128  mov     r8, [rsp+108h+lpvReserved]
0x180002130  mov     edx, edi
0x180002132  mov     rcx, rsi
0x180002135  call    _CRT_INIT
0x18000213a  mov     ebx, eax
0x18000213c  mov     [rsp+108h+var_E8], eax
0x180002140  jmp     short loc_180002157
0x180002142  xor     ebx, ebx
0x180002144  mov     [rsp+108h+var_E8], ebx
0x180002148  mov     edi, [rsp+108h+arg_8]
0x18000214f  mov     rsi, [rsp+108h+arg_0]
0x180002157  mov     rax, cs:_pRawDllMain
0x18000215e  test    rax, rax
0x180002161  jz      short loc_180002194
0x180002163  cmp     cs:dword_18002A5D0, 0
0x18000216a  jz      short loc_180002194
0x18000216c  mov     r8, [rsp+108h+lpvReserved]
0x180002174  mov     edx, edi
0x180002176  mov     rcx, rsi
0x180002179  call    cs:__guard_dispatch_icall_fptr
0x18000217f  mov     ebx, eax
0x180002181  mov     [rsp+108h+var_E8], eax
0x180002185  jmp     short loc_180002194
0x180002187  xor     ebx, ebx
0x180002189  mov     [rsp+108h+var_E8], ebx
0x18000218d  mov     edi, [rsp+108h+arg_8]
0x180002194  cmp     edi, 1
0x180002197  ja      short loc_1800021A3
0x180002199  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x1800021a3  mov     eax, ebx
0x1800021a5  add     rsp, 0F0h
0x1800021ac  pop     rdi
0x1800021ad  pop     rsi
0x1800021ae  pop     rbx
0x1800021af  retn
0x18001b1a2  push    rbp
0x18001b1a4  sub     rsp, 20h
0x18001b1a8  mov     rbp, rdx
0x18001b1ab  mov     rax, [rcx]
0x18001b1ae  mov     edx, [rax]
0x18001b1b0  mov     [rbp+0A8h], rcx
0x18001b1b7  mov     [rbp+28h], edx
0x18001b1ba  mov     eax, [rbp+28h]
0x18001b1bd  cmp     eax, 0E06D7363h
0x18001b1c2  jnz     short loc_18001B1D8
0x18001b1c4  mov     rdx, [rbp+0A8h]
0x18001b1cb  mov     ecx, [rbp+28h]
0x18001b1ce  call    _XcptFilter_0
0x18001b1d3  mov     [rbp+30h], eax
0x18001b1d6  jmp     short loc_18001B1DF
0x18001b1d8  mov     dword ptr [rbp+30h], 0
0x18001b1df  mov     eax, [rbp+30h]
0x18001b1e2  add     rsp, 20h
0x18001b1e6  pop     rbp
0x18001b1e7  retn
0x18001b1e9  push    rbp
0x18001b1eb  sub     rsp, 20h
0x18001b1ef  mov     rbp, rdx
0x18001b1f2  mov     rax, [rcx]
0x18001b1f5  mov     edx, [rax]
0x18001b1f7  mov     [rbp+0B0h], rcx
0x18001b1fe  mov     [rbp+38h], edx
0x18001b201  mov     eax, [rbp+38h]
0x18001b204  cmp     eax, 0E06D7363h
0x18001b209  jnz     short loc_18001B21F
0x18001b20b  mov     rdx, [rbp+0B0h]
0x18001b212  mov     ecx, [rbp+38h]
0x18001b215  call    _XcptFilter_0
0x18001b21a  mov     [rbp+40h], eax
0x18001b21d  jmp     short loc_18001B226
0x18001b21f  mov     dword ptr [rbp+40h], 0
0x18001b226  mov     eax, [rbp+40h]
0x18001b229  add     rsp, 20h
0x18001b22d  pop     rbp
0x18001b22e  retn
0x18001b230  push    rbp
0x18001b232  sub     rsp, 20h
0x18001b236  mov     rbp, rdx
0x18001b239  mov     rax, [rcx]
0x18001b23c  mov     edx, [rax]
0x18001b23e  mov     [rbp+0B8h], rcx
0x18001b245  mov     [rbp+48h], edx
0x18001b248  mov     eax, [rbp+48h]
0x18001b24b  cmp     eax, 0E06D7363h
0x18001b250  jnz     short loc_18001B266
0x18001b252  mov     rdx, [rbp+0B8h]
0x18001b259  mov     ecx, [rbp+48h]
0x18001b25c  call    _XcptFilter_0
0x18001b261  mov     [rbp+50h], eax
0x18001b264  jmp     short loc_18001B26D
0x18001b266  mov     dword ptr [rbp+50h], 0
0x18001b26d  mov     eax, [rbp+50h]
0x18001b270  add     rsp, 20h
0x18001b274  pop     rbp
0x18001b275  retn
0x18001b277  push    rbp
0x18001b279  sub     rsp, 20h
0x18001b27d  mov     rbp, rdx
0x18001b280  mov     rax, [rcx]
0x18001b283  mov     edx, [rax]
0x18001b285  mov     [rbp+0C0h], rcx
0x18001b28c  mov     [rbp+58h], edx
0x18001b28f  mov     eax, [rbp+58h]
0x18001b292  cmp     eax, 0E06D7363h
0x18001b297  jnz     short loc_18001B2AD
0x18001b299  mov     rdx, [rbp+0C0h]
0x18001b2a0  mov     ecx, [rbp+58h]
0x18001b2a3  call    _XcptFilter_0
0x18001b2a8  mov     [rbp+60h], eax
0x18001b2ab  jmp     short loc_18001B2B4
0x18001b2ad  mov     dword ptr [rbp+60h], 0
0x18001b2b4  mov     eax, [rbp+60h]
0x18001b2b7  add     rsp, 20h
0x18001b2bb  pop     rbp
0x18001b2bc  retn
0x18001b2be  push    rbp
0x18001b2c0  sub     rsp, 20h
0x18001b2c4  mov     rbp, rdx
0x18001b2c7  mov     rax, [rcx]
0x18001b2ca  mov     edx, [rax]
0x18001b2cc  mov     [rbp+0C8h], rcx
0x18001b2d3  mov     [rbp+68h], edx
0x18001b2d6  mov     eax, [rbp+68h]
0x18001b2d9  cmp     eax, 0E06D7363h
0x18001b2de  jnz     short loc_18001B2F4
0x18001b2e0  mov     rdx, [rbp+0C8h]
0x18001b2e7  mov     ecx, [rbp+68h]
0x18001b2ea  call    _XcptFilter_0
0x18001b2ef  mov     [rbp+70h], eax
0x18001b2f2  jmp     short loc_18001B2FB
0x18001b2f4  mov     dword ptr [rbp+70h], 0
0x18001b2fb  mov     eax, [rbp+70h]
0x18001b2fe  add     rsp, 20h
0x18001b302  pop     rbp
0x18001b303  retn
0x18001b305  push    rbp
0x18001b307  sub     rsp, 20h
0x18001b30b  mov     rbp, rdx
0x18001b30e  mov     rax, [rcx]
0x18001b311  mov     edx, [rax]
0x18001b313  mov     [rbp+0D0h], rcx
0x18001b31a  mov     [rbp+78h], edx
0x18001b31d  mov     eax, [rbp+78h]
0x18001b320  cmp     eax, 0E06D7363h
0x18001b325  jnz     short loc_18001B33E
0x18001b327  mov     rdx, [rbp+0D0h]
0x18001b32e  mov     ecx, [rbp+78h]
0x18001b331  call    _XcptFilter_0
0x18001b336  mov     [rbp+80h], eax
0x18001b33c  jmp     short loc_18001B348
0x18001b33e  mov     dword ptr [rbp+80h], 0
0x18001b348  mov     eax, [rbp+80h]
0x18001b34e  add     rsp, 20h
0x18001b352  pop     rbp
0x18001b353  retn
0x18001b355  push    rbp
0x18001b357  sub     rsp, 20h
0x18001b35b  mov     rbp, rdx
0x18001b35e  mov     rax, [rcx]
0x18001b361  mov     edx, [rax]
0x18001b363  mov     [rbp+0D8h], rcx
0x18001b36a  mov     [rbp+88h], edx
0x18001b370  mov     eax, [rbp+88h]
0x18001b376  cmp     eax, 0E06D7363h
0x18001b37b  jnz     short loc_18001B397
0x18001b37d  mov     rdx, [rbp+0D8h]
0x18001b384  mov     ecx, [rbp+88h]
0x18001b38a  call    _XcptFilter_0
0x18001b38f  mov     [rbp+90h], eax
0x18001b395  jmp     short loc_18001B3A1
0x18001b397  mov     dword ptr [rbp+90h], 0
0x18001b3a1  mov     eax, [rbp+90h]
0x18001b3a7  add     rsp, 20h
0x18001b3ab  pop     rbp
0x18001b3ac  retn
0x18001b3ae  push    rbp
0x18001b3b0  sub     rsp, 20h
0x18001b3b4  mov     rbp, rdx
0x18001b3b7  mov     rax, [rcx]
0x18001b3ba  mov     edx, [rax]
0x18001b3bc  mov     [rbp+0E0h], rcx
0x18001b3c3  mov     [rbp+98h], edx
0x18001b3c9  mov     eax, [rbp+98h]
0x18001b3cf  cmp     eax, 0E06D7363h
0x18001b3d4  jnz     short loc_18001B3F0
0x18001b3d6  mov     rdx, [rbp+0E0h]
0x18001b3dd  mov     ecx, [rbp+98h]
0x18001b3e3  call    _XcptFilter_0
0x18001b3e8  mov     [rbp+0A0h], eax
0x18001b3ee  jmp     short loc_18001B3FA
0x18001b3f0  mov     dword ptr [rbp+0A0h], 0
0x18001b3fa  mov     eax, [rbp+0A0h]
0x18001b400  add     rsp, 20h
0x18001b404  pop     rbp
0x18001b405  retn
0x18001b407  push    rbp
0x18001b409  sub     rsp, 20h
0x18001b40d  mov     rbp, rdx
0x18001b410  cmp     dword ptr [rbp+118h], 1
0x18001b417  ja      short loc_18001B423
0x18001b419  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
