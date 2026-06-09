# WldpIsDetachedSignatureTrusted

- ea: `0x18002d228`
- end: `0x18002d4e2`
- name: `WldpIsDetachedSignatureTrusted`
- size: `698`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18002d4e8`

## callees

- `0x18001bb98`
- `0x180021ec0`
- `0x180022a10`
- `0x18002d228`

## import_xrefs

- `WINTRUST!WinVerifyTrust` at `0x18002d358`
- `WINTRUST!WinVerifyTrust` at `0x18002d358`
- `WINTRUST!WTConfigCiFreePrivateData` at `0x18002d47c`
- `WINTRUST!WTConfigCiFreePrivateData` at `0x18002d47c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WldpIsDetachedSignatureTrusted(__int64 a1, __int64 a2, _DWORD *a3, _QWORD *a4, __int64 a5)
{
  unsigned int v9; // ebx
  unsigned int v10; // r8d
  __int128 v11; // xmm6
  __int128 v12; // xmm7
  __int128 v13; // xmm8
  __int128 v14; // xmm9
  __int128 v15; // xmm10
  __int128 v16; // xmm11
  __int128 v17; // xmm12
  __int128 v18; // xmm13
  __int128 v19; // xmm14
  __int128 v20; // xmm15
  __int64 v21; // rbx
  int v23; // [rsp+28h] [rbp-E0h] BYREF
  _QWORD v24[2]; // [rsp+30h] [rbp-D8h] BYREF
  _QWORD v25[3]; // [rsp+40h] [rbp-C8h] BYREF
  _QWORD pWVTData[3]; // [rsp+58h] [rbp-B0h] BYREF
  int v27; // [rsp+70h] [rbp-98h]
  int v28; // [rsp+74h] [rbp-94h]
  __int64 v29; // [rsp+78h] [rbp-90h]
  _QWORD *v30; // [rsp+80h] [rbp-88h]
  int v31; // [rsp+88h] [rbp-80h]
  __int64 v32; // [rsp+90h] [rbp-78h]
  int v33; // [rsp+A0h] [rbp-68h]
  __int128 v34; // [rsp+B8h] [rbp-50h]
  __int128 v35; // [rsp+C8h] [rbp-40h]
  __int128 v36; // [rsp+D8h] [rbp-30h]
  __int128 v37; // [rsp+E8h] [rbp-20h]
  __int64 v38; // [rsp+F8h] [rbp-10h] BYREF
  __int128 v39; // [rsp+100h] [rbp-8h]
  __int128 v40; // [rsp+110h] [rbp+8h]
  _OWORD *v41; // [rsp+120h] [rbp+18h]
  _OWORD v42[14]; // [rsp+128h] [rbp+20h] BYREF
  __int64 v43; // [rsp+208h] [rbp+100h]

  memset_0(v42, 0, 0xE8u);
  LODWORD(v42[0]) = 232;
  memset_0(pWVTData, 0, 0x58u);
  v24[0] = 0x100000000LL;
  v38 = 48;
  v39 = 0;
  v40 = 0;
  v25[1] = a2;
  v25[0] = a1;
  v24[1] = v25;
  v41 = v42;
  LODWORD(pWVTData[0]) = 88;
  v27 = 2;
  LODWORD(v29) = 6;
  v30 = v24;
  v31 = 1;
  v28 = 1;
  v33 = 4224;
  pWVTData[1] = &v38;
  v9 = WinVerifyTrust(HWND_MESSAGE|0x2LL, (GUID *)&stru_180047D90, pWVTData);
  if ( IsWvtErrorRecoverable((char *)v9, &v23, v10) )
  {
    *a3 = HIDWORD(v39);
    *a4 = v32;
    v32 = 0;
    v11 = v42[0];
    v12 = v42[1];
    v13 = v42[2];
    v14 = v42[3];
    v15 = v42[4];
    v16 = v42[5];
    v17 = v42[6];
    v18 = v42[7];
    v19 = v42[8];
    v20 = v42[9];
    v34 = v42[10];
    v35 = v42[11];
    v36 = v42[12];
    v37 = v42[13];
    v21 = v43;
    memset_0(v42, 0, 0xE8u);
    LODWORD(v42[0]) = 232;
    *(_OWORD *)a5 = v11;
    *(_OWORD *)(a5 + 16) = v12;
    *(_OWORD *)(a5 + 32) = v13;
    *(_OWORD *)(a5 + 48) = v14;
    *(_OWORD *)(a5 + 64) = v15;
    *(_OWORD *)(a5 + 80) = v16;
    *(_OWORD *)(a5 + 96) = v17;
    *(_OWORD *)(a5 + 112) = v18;
    *(_OWORD *)(a5 + 128) = v19;
    *(_OWORD *)(a5 + 144) = v20;
    *(_OWORD *)(a5 + 160) = v34;
    *(_OWORD *)(a5 + 176) = v35;
    *(_OWORD *)(a5 + 192) = v36;
    *(_OWORD *)(a5 + 208) = v37;
    *(_QWORD *)(a5 + 224) = v21;
    v9 = 0;
  }
  WTConfigCiFreePrivateData(v42);
  return v9;
}

```

## disassembly

```asm
0x18002d228  mov     rax, rsp
0x18002d22b  push    rbp
0x18002d22c  push    rbx
0x18002d22d  push    rsi
0x18002d22e  push    rdi
0x18002d22f  push    r14
0x18002d231  push    r15
0x18002d233  lea     rbp, [rax-1F8h]
0x18002d23a  sub     rsp, 2C8h
0x18002d241  movaps  xmmword ptr [rax-48h], xmm6
0x18002d245  movaps  xmmword ptr [rax-58h], xmm7
0x18002d249  movaps  xmmword ptr [rax-68h], xmm8
0x18002d24e  movaps  xmmword ptr [rax-78h], xmm9
0x18002d253  movaps  xmmword ptr [rax-88h], xmm10
0x18002d25b  movaps  xmmword ptr [rax-98h], xmm11
0x18002d263  movaps  xmmword ptr [rax-0A8h], xmm12
0x18002d26b  movaps  xmmword ptr [rax-0B8h], xmm13
0x18002d273  movaps  xmmword ptr [rax-0C8h], xmm14
0x18002d27b  movaps  xmmword ptr [rax-0D8h], xmm15
0x18002d283  mov     rax, cs:__security_cookie
0x18002d28a  xor     rax, rsp
0x18002d28d  mov     [rbp+1F0h+var_E0], rax
0x18002d294  mov     r15, r9
0x18002d297  mov     r14, r8
0x18002d29a  mov     rdi, rdx
0x18002d29d  mov     rbx, rcx
0x18002d2a0  mov     rsi, [rbp+1F0h+arg_20]
0x18002d2a7  xor     edx, edx; Val
0x18002d2a9  mov     r8d, 0E8h; Size
0x18002d2af  lea     rcx, [rbp+1F0h+var_1D0]; void *
0x18002d2b3  call    memset_0
0x18002d2b8  mov     dword ptr [rbp+1F0h+var_1D0], 0E8h
0x18002d2bf  xor     edx, edx; Val
0x18002d2c1  lea     r8d, [rdx+58h]; Size
0x18002d2c5  lea     rcx, [rsp+2F0h+pWVTData]; void *
0x18002d2ca  call    memset_0
0x18002d2cf  mov     dword ptr [rsp+2F0h+var_2C8], 0
0x18002d2d7  mov     [rbp+1F0h+var_200], 30h ; '0'
0x18002d2df  xorps   xmm0, xmm0
0x18002d2e2  movups  [rbp+1F0h+var_1F8], xmm0
0x18002d2e6  movups  [rbp+1F0h+var_1E8], xmm0
0x18002d2ea  mov     ecx, 1
0x18002d2ef  mov     dword ptr [rsp+2F0h+var_2C8+4], ecx
0x18002d2f3  mov     [rsp+2F0h+var_2B0], rdi
0x18002d2f8  mov     [rsp+2F0h+var_2B8], rbx
0x18002d2fd  lea     rax, [rsp+2F0h+var_2B8]
0x18002d302  mov     [rsp+2F0h+var_2C0], rax
0x18002d307  lea     rax, [rbp+1F0h+var_1D0]
0x18002d30b  mov     [rbp+1F0h+var_1D8], rax
0x18002d30f  mov     dword ptr [rsp+2F0h+pWVTData], 58h ; 'X'
0x18002d317  mov     [rsp+2F0h+var_288], 2
0x18002d31f  mov     dword ptr [rsp+2F0h+var_280], 6
0x18002d327  lea     rax, [rsp+2F0h+var_2C8]
0x18002d32c  mov     [rsp+2F0h+var_278], rax
0x18002d331  mov     [rbp+1F0h+var_270], ecx
0x18002d334  mov     [rsp+2F0h+var_284], ecx
0x18002d338  mov     [rbp+1F0h+var_258], 1080h
0x18002d33f  lea     rax, [rbp+1F0h+var_200]
0x18002d343  mov     [rsp+2F0h+var_298], rax
0x18002d348  lea     r8, [rsp+2F0h+pWVTData]; pWVTData
0x18002d34d  lea     rdx, stru_180047D90; pgActionID
0x18002d354  or      rcx, 0FFFFFFFFFFFFFFFFh; hwnd
0x18002d358  call    cs:__imp_WinVerifyTrust
0x18002d35e  mov     ebx, eax
0x18002d360  lea     rdx, [rsp+2F0h+var_2D0]
0x18002d365  mov     ecx, eax
0x18002d367  call    IsWvtErrorRecoverable
0x18002d36c  test    al, al
0x18002d36e  jz      loc_18002D478
0x18002d374  mov     eax, dword ptr [rbp+1F0h+var_1F8+0Ch]
0x18002d377  mov     [r14], eax
0x18002d37a  mov     rax, [rbp+1F0h+var_268]
0x18002d37e  mov     [r15], rax
0x18002d381  mov     [rbp+1F0h+var_268], 0
0x18002d389  movups  xmm6, [rbp+1F0h+var_1D0]
0x18002d38d  movups  xmm7, [rbp+1F0h+var_1C0]
0x18002d391  movups  xmm8, [rbp+1F0h+var_1B0]
0x18002d396  movups  xmm9, [rbp+1F0h+var_1A0]
0x18002d39b  movups  xmm10, [rbp+1F0h+var_190]
0x18002d3a0  movups  xmm11, [rbp+1F0h+var_180]
0x18002d3a5  movups  xmm12, [rbp+1F0h+var_170]
0x18002d3ad  movups  xmm13, [rbp+1F0h+var_160]
0x18002d3b5  movups  xmm14, [rbp+1F0h+var_150]
0x18002d3bd  movups  xmm15, [rbp+1F0h+var_140]
0x18002d3c5  movups  xmm0, [rbp+1F0h+var_130]
0x18002d3cc  movups  [rbp+1F0h+var_240], xmm0
0x18002d3d0  movups  xmm0, [rbp+1F0h+var_120]
0x18002d3d7  movups  [rbp+1F0h+var_230], xmm0
0x18002d3db  movups  xmm0, [rbp+1F0h+var_110]
0x18002d3e2  movups  [rbp+1F0h+var_220], xmm0
0x18002d3e6  movups  xmm0, [rbp+1F0h+var_100]
0x18002d3ed  movups  [rbp+1F0h+var_210], xmm0
0x18002d3f1  mov     rbx, [rbp+1F0h+var_F0]
0x18002d3f8  mov     edi, 0E8h
0x18002d3fd  mov     r8d, edi; Size
0x18002d400  xor     edx, edx; Val
0x18002d402  lea     rcx, [rbp+1F0h+var_1D0]; void *
0x18002d406  call    memset_0
0x18002d40b  mov     dword ptr [rbp+1F0h+var_1D0], edi
0x18002d40e  movups  xmmword ptr [rsi], xmm6
0x18002d411  movups  xmmword ptr [rsi+10h], xmm7
0x18002d415  movups  xmmword ptr [rsi+20h], xmm8
0x18002d41a  movups  xmmword ptr [rsi+30h], xmm9
0x18002d41f  movups  xmmword ptr [rsi+40h], xmm10
0x18002d424  movups  xmmword ptr [rsi+50h], xmm11
0x18002d429  movups  xmmword ptr [rsi+60h], xmm12
0x18002d42e  movups  xmmword ptr [rsi+70h], xmm13
0x18002d433  movups  xmmword ptr [rsi+80h], xmm14
0x18002d43b  movups  xmmword ptr [rsi+90h], xmm15
0x18002d443  movups  xmm0, [rbp+1F0h+var_240]
0x18002d447  movups  xmmword ptr [rsi+0A0h], xmm0
0x18002d44e  movups  xmm1, [rbp+1F0h+var_230]
0x18002d452  movups  xmmword ptr [rsi+0B0h], xmm1
0x18002d459  movups  xmm0, [rbp+1F0h+var_220]
0x18002d45d  movups  xmmword ptr [rsi+0C0h], xmm0
0x18002d464  movups  xmm1, [rbp+1F0h+var_210]
0x18002d468  movups  xmmword ptr [rsi+0D0h], xmm1
0x18002d46f  mov     [rsi+0E0h], rbx
0x18002d476  xor     ebx, ebx
0x18002d478  lea     rcx, [rbp+1F0h+var_1D0]
0x18002d47c  call    cs:__imp_WTConfigCiFreePrivateData
0x18002d482  mov     eax, ebx
0x18002d484  mov     rcx, [rbp+1F0h+var_E0]
0x18002d48b  xor     rcx, rsp; StackCookie
0x18002d48e  call    __security_check_cookie
0x18002d493  lea     r11, [rsp+2F0h+var_28]
0x18002d49b  movaps  xmm6, xmmword ptr [r11-18h]
0x18002d4a0  movaps  xmm7, xmmword ptr [r11-28h]
0x18002d4a5  movaps  xmm8, xmmword ptr [r11-38h]
0x18002d4aa  movaps  xmm9, xmmword ptr [r11-48h]
0x18002d4af  movaps  xmm10, xmmword ptr [r11-58h]
0x18002d4b4  movaps  xmm11, xmmword ptr [r11-68h]
0x18002d4b9  movaps  xmm12, xmmword ptr [r11-78h]
0x18002d4be  movaps  xmm13, xmmword ptr [r11-88h]
0x18002d4c6  movaps  xmm14, xmmword ptr [r11-98h]
0x18002d4ce  movaps  xmm15, xmmword ptr [r11-0A8h]
0x18002d4d6  mov     rsp, r11
0x18002d4d9  pop     r15
0x18002d4db  pop     r14
0x18002d4dd  pop     rdi
0x18002d4de  pop     rsi
0x18002d4df  pop     rbx
0x18002d4e0  pop     rbp
0x18002d4e1  retn
```
