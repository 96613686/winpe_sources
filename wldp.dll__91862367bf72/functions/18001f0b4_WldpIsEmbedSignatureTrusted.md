# WldpIsEmbedSignatureTrusted

- ea: `0x18001f0b4`
- end: `0x18001f3f3`
- name: `WldpIsEmbedSignatureTrusted`
- size: `831`
- prototype: `__int64 __fastcall(__int64, __int64, char, _DWORD *, _BYTE *, GUID *, HANDLE *, __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180018518`
- `0x18001e6b8`

## callees

- `0x18001bb98`
- `0x18001f0b4`
- `0x180021ec0`
- `0x180022a10`

## import_xrefs

- `WINTRUST!WinVerifyTrust` at `0x18001f217`
- `WINTRUST!WinVerifyTrust` at `0x18001f217`
- `WINTRUST!WTHelperProvDataFromStateData` at `0x18001f237`
- `WINTRUST!WTHelperProvDataFromStateData` at `0x18001f237`
- `WINTRUST!WTConfigCiFreePrivateData` at `0x18001f389`
- `WINTRUST!WTConfigCiFreePrivateData` at `0x18001f389`

## pseudocode

```c
__int64 __fastcall WldpIsEmbedSignatureTrusted(
        __int64 a1,
        __int64 a2,
        char a3,
        _DWORD *a4,
        _BYTE *a5,
        GUID *a6,
        HANDLE *a7,
        __int64 a8)
{
  GUID *v12; // rdx
  unsigned int v13; // ebx
  CRYPT_PROVIDER_DATA *v14; // rax
  GUID gSubject; // xmm0
  __int128 v16; // xmm6
  __int128 v17; // xmm7
  __int128 v18; // xmm8
  __int128 v19; // xmm9
  __int128 v20; // xmm10
  __int128 v21; // xmm11
  __int128 v22; // xmm12
  __int128 v23; // xmm13
  __int128 v24; // xmm14
  __int128 v25; // xmm15
  __int64 v26; // rbx
  __int128 v28; // [rsp+30h] [rbp-D8h]
  _QWORD v29[5]; // [rsp+40h] [rbp-C8h] BYREF
  _QWORD pWVTData[3]; // [rsp+68h] [rbp-A0h] BYREF
  int v31; // [rsp+80h] [rbp-88h]
  int v32; // [rsp+84h] [rbp-84h]
  int v33; // [rsp+88h] [rbp-80h]
  _QWORD *v34; // [rsp+90h] [rbp-78h]
  int v35; // [rsp+98h] [rbp-70h]
  HANDLE hStateData; // [rsp+A0h] [rbp-68h]
  int v37; // [rsp+B0h] [rbp-58h]
  __int128 v38; // [rsp+C8h] [rbp-40h]
  __int128 v39; // [rsp+D8h] [rbp-30h]
  __int128 v40; // [rsp+E8h] [rbp-20h]
  __int64 v41; // [rsp+F8h] [rbp-10h] BYREF
  __int128 v42; // [rsp+100h] [rbp-8h]
  __int128 v43; // [rsp+110h] [rbp+8h]
  _OWORD *v44; // [rsp+120h] [rbp+18h]
  _OWORD v45[14]; // [rsp+128h] [rbp+20h] BYREF
  __int64 v46; // [rsp+208h] [rbp+100h]

  memset_0(v45, 0, 0xE8u);
  LODWORD(v45[0]) = 232;
  memset_0(pWVTData, 0, 0x58u);
  v29[0] = 32;
  v29[3] = 0;
  v41 = 48;
  v42 = 0;
  v43 = 0;
  v12 = (GUID *)&stru_180047D90;
  if ( !a3 )
    v12 = (GUID *)&pgActionID;
  v44 = v45;
  v29[2] = a1;
  v29[1] = a2;
  LODWORD(pWVTData[0]) = 88;
  v31 = 2;
  v33 = 1;
  v34 = v29;
  v35 = 1;
  v32 = 1;
  v37 = 4224;
  pWVTData[1] = (unsigned __int64)&v41 & -(__int64)(a3 != 0);
  v13 = WinVerifyTrust(HWND_MESSAGE|0x2LL, v12, pWVTData);
  if ( (unsigned __int8)IsWvtErrorRecoverable((char *)v13) )
  {
    v14 = WTHelperProvDataFromStateData(hStateData);
    if ( v14 )
      gSubject = v14->pPDSip->gSubject;
    else
      gSubject = 0;
    *a6 = gSubject;
    if ( a3 )
    {
      *a4 = HIDWORD(v42);
      *a5 = BYTE4(v43);
    }
    else
    {
      *a4 = 0;
      *a5 = 0;
    }
    *a7 = hStateData;
    hStateData = 0;
    if ( a8 )
    {
      v16 = v45[0];
      v17 = v45[1];
      v18 = v45[2];
      v19 = v45[3];
      v20 = v45[4];
      v21 = v45[5];
      v22 = v45[6];
      v23 = v45[7];
      v24 = v45[8];
      v25 = v45[9];
      v28 = v45[10];
      v38 = v45[11];
      v39 = v45[12];
      v40 = v45[13];
      v26 = v46;
      memset_0(v45, 0, 0xE8u);
      LODWORD(v45[0]) = 232;
      *(_OWORD *)a8 = v16;
      *(_OWORD *)(a8 + 16) = v17;
      *(_OWORD *)(a8 + 32) = v18;
      *(_OWORD *)(a8 + 48) = v19;
      *(_OWORD *)(a8 + 64) = v20;
      *(_OWORD *)(a8 + 80) = v21;
      *(_OWORD *)(a8 + 96) = v22;
      *(_OWORD *)(a8 + 112) = v23;
      *(_OWORD *)(a8 + 128) = v24;
      *(_OWORD *)(a8 + 144) = v25;
      *(_OWORD *)(a8 + 160) = v28;
      *(_OWORD *)(a8 + 176) = v38;
      *(_OWORD *)(a8 + 192) = v39;
      *(_OWORD *)(a8 + 208) = v40;
      *(_QWORD *)(a8 + 224) = v26;
    }
    v13 = 0;
  }
  WTConfigCiFreePrivateData(v45);
  return v13;
}

```

## disassembly

```asm
0x18001f0b4  mov     rax, rsp
0x18001f0b7  mov     [rax+18h], rbx
0x18001f0bb  push    rbp
0x18001f0bc  push    rsi
0x18001f0bd  push    rdi
0x18001f0be  push    r12
0x18001f0c0  push    r13
0x18001f0c2  push    r14
0x18001f0c4  push    r15
0x18001f0c6  lea     rbp, [rax-1F8h]
0x18001f0cd  sub     rsp, 2C0h
0x18001f0d4  movaps  xmmword ptr [rax-48h], xmm6
0x18001f0d8  movaps  xmmword ptr [rax-58h], xmm7
0x18001f0dc  movaps  xmmword ptr [rax-68h], xmm8
0x18001f0e1  movaps  xmmword ptr [rax-78h], xmm9
0x18001f0e6  movaps  xmmword ptr [rax-88h], xmm10
0x18001f0ee  movaps  xmmword ptr [rax-98h], xmm11
0x18001f0f6  movaps  xmmword ptr [rax-0A8h], xmm12
0x18001f0fe  movaps  xmmword ptr [rax-0B8h], xmm13
0x18001f106  movaps  xmmword ptr [rax-0C8h], xmm14
0x18001f10e  movaps  xmmword ptr [rax-0D8h], xmm15
0x18001f116  mov     rax, cs:__security_cookie
0x18001f11d  xor     rax, rsp
0x18001f120  mov     [rbp+1F0h+var_E0], rax
0x18001f127  mov     r14, r9
0x18001f12a  mov     r13b, r8b
0x18001f12d  mov     rdi, rdx
0x18001f130  mov     rbx, rcx
0x18001f133  mov     r15, [rbp+1F0h+arg_20]
0x18001f13a  mov     r12, [rbp+1F0h+arg_28]
0x18001f141  mov     rax, [rbp+1F0h+arg_30]
0x18001f148  mov     qword ptr [rsp+2F0h+var_2D0+8], rax
0x18001f14d  mov     rsi, [rbp+1F0h+arg_38]
0x18001f154  mov     byte ptr [rsp+2F0h+var_2D0], 0
0x18001f159  xor     edx, edx; Val
0x18001f15b  mov     r8d, 0E8h; Size
0x18001f161  lea     rcx, [rbp+1F0h+var_1D0]; void *
0x18001f165  call    memset_0
0x18001f16a  mov     dword ptr [rbp+1F0h+var_1D0], 0E8h
0x18001f171  xor     edx, edx; Val
0x18001f173  lea     r8d, [rdx+58h]; Size
0x18001f177  lea     rcx, [rsp+2F0h+pWVTData]; void *
0x18001f17c  call    memset_0
0x18001f181  xor     ecx, ecx
0x18001f183  mov     [rsp+2F0h+var_2B8], 20h ; ' '
0x18001f18c  mov     [rsp+2F0h+var_2A0], rcx
0x18001f191  mov     [rbp+1F0h+var_200], 30h ; '0'
0x18001f199  xorps   xmm0, xmm0
0x18001f19c  movups  [rbp+1F0h+var_1F8], xmm0
0x18001f1a0  movups  [rbp+1F0h+var_1E8], xmm0
0x18001f1a4  lea     rax, pgActionID
0x18001f1ab  lea     rdx, stru_180047D90
0x18001f1b2  test    r13b, r13b
0x18001f1b5  cmovz   rdx, rax; pgActionID
0x18001f1b9  lea     rax, [rbp+1F0h+var_1D0]
0x18001f1bd  mov     [rbp+1F0h+var_1D8], rax
0x18001f1c1  mov     [rsp+2F0h+var_2A8], rbx
0x18001f1c6  mov     [rsp+2F0h+var_2B0], rdi
0x18001f1cb  mov     dword ptr [rsp+2F0h+pWVTData], 58h ; 'X'
0x18001f1d3  mov     [rsp+2F0h+var_278], 2
0x18001f1db  mov     ecx, 1
0x18001f1e0  mov     [rbp+1F0h+var_270], ecx
0x18001f1e3  lea     rax, [rsp+2F0h+var_2B8]
0x18001f1e8  mov     [rbp+1F0h+var_268], rax
0x18001f1ec  mov     [rbp+1F0h+var_260], ecx
0x18001f1ef  mov     [rsp+2F0h+var_274], ecx
0x18001f1f3  mov     [rbp+1F0h+var_248], 1080h
0x18001f1fa  mov     al, r13b
0x18001f1fd  neg     al
0x18001f1ff  sbb     rcx, rcx
0x18001f202  lea     rax, [rbp+1F0h+var_200]
0x18001f206  and     rcx, rax
0x18001f209  mov     [rsp+2F0h+var_288], rcx
0x18001f20e  lea     r8, [rsp+2F0h+pWVTData]; pWVTData
0x18001f213  or      rcx, 0FFFFFFFFFFFFFFFFh; hwnd
0x18001f217  call    cs:__imp_WinVerifyTrust
0x18001f21d  mov     ebx, eax
0x18001f21f  lea     rdx, [rsp+2F0h+var_2D0]
0x18001f224  mov     ecx, eax
0x18001f226  call    IsWvtErrorRecoverable
0x18001f22b  test    al, al
0x18001f22d  jz      loc_18001F385
0x18001f233  mov     rcx, [rbp+1F0h+hStateData]; hStateData
0x18001f237  call    cs:__imp_WTHelperProvDataFromStateData
0x18001f23d  test    rax, rax
0x18001f240  jz      short loc_18001F24F
0x18001f242  mov     rax, [rax+0A0h]
0x18001f249  movups  xmm0, xmmword ptr [rax+4]
0x18001f24d  jmp     short loc_18001F252
0x18001f24f  xorps   xmm0, xmm0
0x18001f252  movdqu  xmmword ptr [r12], xmm0
0x18001f258  test    r13b, r13b
0x18001f25b  jz      short loc_18001F26B
0x18001f25d  mov     eax, dword ptr [rbp+1F0h+var_1F8+0Ch]
0x18001f260  mov     [r14], eax
0x18001f263  mov     al, byte ptr [rbp+1F0h+var_1E8+4]
0x18001f266  mov     [r15], al
0x18001f269  jmp     short loc_18001F277
0x18001f26b  movzx   eax, byte ptr [rsp+2F0h+var_2D0]
0x18001f270  mov     [r14], eax
0x18001f273  mov     byte ptr [r15], 0
0x18001f277  mov     rax, [rbp+1F0h+hStateData]
0x18001f27b  mov     rcx, qword ptr [rsp+2F0h+var_2D0+8]
0x18001f280  mov     [rcx], rax
0x18001f283  mov     [rbp+1F0h+hStateData], 0
0x18001f28b  test    rsi, rsi
0x18001f28e  jz      loc_18001F383
0x18001f294  movups  xmm6, [rbp+1F0h+var_1D0]
0x18001f298  movups  xmm7, [rbp+1F0h+var_1C0]
0x18001f29c  movups  xmm8, [rbp+1F0h+var_1B0]
0x18001f2a1  movups  xmm9, [rbp+1F0h+var_1A0]
0x18001f2a6  movups  xmm10, [rbp+1F0h+var_190]
0x18001f2ab  movups  xmm11, [rbp+1F0h+var_180]
0x18001f2b0  movups  xmm12, [rbp+1F0h+var_170]
0x18001f2b8  movups  xmm13, [rbp+1F0h+var_160]
0x18001f2c0  movups  xmm14, [rbp+1F0h+var_150]
0x18001f2c8  movups  xmm15, [rbp+1F0h+var_140]
0x18001f2d0  movups  xmm0, [rbp+1F0h+var_130]
0x18001f2d7  movups  [rsp+2F0h+var_2D0+8], xmm0
0x18001f2dc  movups  xmm0, [rbp+1F0h+var_120]
0x18001f2e3  movups  [rbp+1F0h+var_230], xmm0
0x18001f2e7  movups  xmm0, [rbp+1F0h+var_110]
0x18001f2ee  movups  [rbp+1F0h+var_220], xmm0
0x18001f2f2  movups  xmm0, [rbp+1F0h+var_100]
0x18001f2f9  movups  [rbp+1F0h+var_210], xmm0
0x18001f2fd  mov     rbx, [rbp+1F0h+var_F0]
0x18001f304  mov     edi, 0E8h
0x18001f309  mov     r8d, edi; Size
0x18001f30c  xor     edx, edx; Val
0x18001f30e  lea     rcx, [rbp+1F0h+var_1D0]; void *
0x18001f312  call    memset_0
0x18001f317  mov     dword ptr [rbp+1F0h+var_1D0], edi
0x18001f31a  movups  xmmword ptr [rsi], xmm6
0x18001f31d  movups  xmmword ptr [rsi+10h], xmm7
0x18001f321  movups  xmmword ptr [rsi+20h], xmm8
0x18001f326  movups  xmmword ptr [rsi+30h], xmm9
0x18001f32b  movups  xmmword ptr [rsi+40h], xmm10
0x18001f330  movups  xmmword ptr [rsi+50h], xmm11
0x18001f335  movups  xmmword ptr [rsi+60h], xmm12
0x18001f33a  movups  xmmword ptr [rsi+70h], xmm13
0x18001f33f  movups  xmmword ptr [rsi+80h], xmm14
0x18001f347  movups  xmmword ptr [rsi+90h], xmm15
0x18001f34f  movups  xmm0, [rsp+2F0h+var_2D0+8]
0x18001f354  movups  xmmword ptr [rsi+0A0h], xmm0
0x18001f35b  movups  xmm1, [rbp+1F0h+var_230]
0x18001f35f  movups  xmmword ptr [rsi+0B0h], xmm1
0x18001f366  movups  xmm0, [rbp+1F0h+var_220]
0x18001f36a  movups  xmmword ptr [rsi+0C0h], xmm0
0x18001f371  movups  xmm1, [rbp+1F0h+var_210]
0x18001f375  movups  xmmword ptr [rsi+0D0h], xmm1
0x18001f37c  mov     [rsi+0E0h], rbx
0x18001f383  xor     ebx, ebx
0x18001f385  lea     rcx, [rbp+1F0h+var_1D0]
0x18001f389  call    cs:__imp_WTConfigCiFreePrivateData
0x18001f38f  mov     eax, ebx
0x18001f391  mov     rcx, [rbp+1F0h+var_E0]
0x18001f398  xor     rcx, rsp; StackCookie
0x18001f39b  call    __security_check_cookie
0x18001f3a0  lea     r11, [rsp+2F0h+var_30]
0x18001f3a8  mov     rbx, [r11+50h]
0x18001f3ac  movaps  xmm6, xmmword ptr [r11-10h]
0x18001f3b1  movaps  xmm7, xmmword ptr [r11-20h]
0x18001f3b6  movaps  xmm8, xmmword ptr [r11-30h]
0x18001f3bb  movaps  xmm9, xmmword ptr [r11-40h]
0x18001f3c0  movaps  xmm10, xmmword ptr [r11-50h]
0x18001f3c5  movaps  xmm11, xmmword ptr [r11-60h]
0x18001f3ca  movaps  xmm12, xmmword ptr [r11-70h]
0x18001f3cf  movaps  xmm13, xmmword ptr [r11-80h]
0x18001f3d4  movaps  xmm14, xmmword ptr [r11-90h]
0x18001f3dc  movaps  xmm15, xmmword ptr [r11-0A0h]
0x18001f3e4  mov     rsp, r11
0x18001f3e7  pop     r15
0x18001f3e9  pop     r14
0x18001f3eb  pop     r13
0x18001f3ed  pop     r12
0x18001f3ef  pop     rdi
0x18001f3f0  pop     rsi
0x18001f3f1  pop     rbp
0x18001f3f2  retn
```
