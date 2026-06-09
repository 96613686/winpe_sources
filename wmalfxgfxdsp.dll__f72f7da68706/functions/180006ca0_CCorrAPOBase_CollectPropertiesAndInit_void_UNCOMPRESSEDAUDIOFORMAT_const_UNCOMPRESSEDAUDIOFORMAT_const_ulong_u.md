# CCorrAPOBase::CollectPropertiesAndInit(void * *,_UNCOMPRESSEDAUDIOFORMAT const *,_UNCOMPRESSEDAUDIOFORMAT const *,ulong *,ulong *)

- ea: `0x180006ca0`
- end: `0x180007027`
- name: `?CollectPropertiesAndInit@CCorrAPOBase@@IEAAJPEAPEAXPEBU_UNCOMPRESSEDAUDIOFORMAT@@1PEAK2@Z`
- size: `903`
- prototype: `__int64 __usercall@<rax>(CCorrAPOBase *__hidden this@<rcx>, void **@<rdx>, const struct _UNCOMPRESSEDAUDIOFORMAT *@<r8>, const struct _UNCOMPRESSEDAUDIOFORMAT *@<r9>, unsigned int *, unsigned int *)`
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000662c`
- `0x1800066e0`
- `0x180006970`

## callees

- `0x180006ca0`
- `0x180007030`
- `0x180007cf8`
- `0x180007e7c`
- `0x180015190`
- `0x180086010`

## pseudocode

```c
int __fastcall CCorrAPOBase::CollectPropertiesAndInit(
        CCorrAPOBase *this,
        void **a2,
        const struct _UNCOMPRESSEDAUDIOFORMAT *a3,
        const struct _UNCOMPRESSEDAUDIOFORMAT *a4,
        unsigned int *a5,
        unsigned int *a6)
{
  __int64 dwChannelMask; // r8
  int v9; // r13d
  __int64 dwSamplesPerFrame; // rdx
  int v12; // esi
  int result; // eax
  DWORD v14; // r12d
  __int64 v15; // rax
  int v16; // ecx
  __int64 v17; // rax
  float v18; // xmm0_4
  __int64 (__fastcall *v19)(CCorrAPOBase *, _BYTE *, __int64); // rax
  float v20; // xmm0_4
  __int64 (__fastcall *v21)(CCorrAPOBase *, _BYTE *, __int64); // rax
  int v22; // ecx
  __int64 v23; // rax
  bool v24; // zf
  __int64 v25; // rax
  __int64 v26; // rax
  int fFramesPerSecond; // eax
  int v28; // eax
  int v29; // r15d
  DWORD v30; // ebx
  int v31; // esi
  int v32; // edi
  int v33; // ebx
  __int16 *v34; // rax
  _BYTE v35[16]; // [rsp+90h] [rbp-80h] BYREF
  int v36; // [rsp+A0h] [rbp-70h]
  unsigned int *v37; // [rsp+A8h] [rbp-68h]
  __int64 v38; // [rsp+B0h] [rbp-60h]
  unsigned int *v39; // [rsp+B8h] [rbp-58h]
  _BYTE v40[16]; // [rsp+C0h] [rbp-50h] BYREF
  _BYTE v41[16]; // [rsp+D0h] [rbp-40h] BYREF
  _BYTE v42[16]; // [rsp+E0h] [rbp-30h] BYREF
  _DWORD v43[6]; // [rsp+F0h] [rbp-20h] BYREF
  _DWORD v44[6]; // [rsp+108h] [rbp-8h] BYREF
  _DWORD v45[6]; // [rsp+120h] [rbp+10h] BYREF

  dwChannelMask = a3->dwChannelMask;
  v39 = a5;
  v9 = (int)a2;
  dwSamplesPerFrame = a3->dwSamplesPerFrame;
  v37 = a6;
  v12 = CCorrAPOBase::ChannelMaskQuality(
          this,
          dwSamplesPerFrame,
          dwChannelMask,
          a4->dwSamplesPerFrame,
          a4->dwChannelMask);
  result = CCorrAPOBase::CheckFormats(this, a3, a4);
  v14 = 0;
  if ( result >= 0 )
  {
    v15 = (*(__int64 (__fastcall **)(CCorrAPOBase *, _BYTE *, _QWORD))(*(_QWORD *)this + 184LL))(this, v40, 0);
    v16 = *(_DWORD *)v15;
    v38 = *(_QWORD *)(v15 + 8);
    v17 = *(_QWORD *)this;
    v36 = v16;
    v18 = (float)*(int *)(*(__int64 (__fastcall **)(CCorrAPOBase *, _BYTE *, __int64))(v17 + 184))(this, v35, 1);
    v19 = *(__int64 (__fastcall **)(CCorrAPOBase *, _BYTE *, __int64))(*(_QWORD *)this + 184LL);
    *(float *)v43 = v18;
    v20 = (float)(3 * (*(_DWORD *)v19(this, v35, 6) + 1));
    v21 = *(__int64 (__fastcall **)(CCorrAPOBase *, _BYTE *, __int64))(*(_QWORD *)this + 184LL);
    *(float *)&v43[1] = v20;
    v22 = *(_DWORD *)v21(this, v35, 2);
    v23 = *(_QWORD *)this;
    v43[2] = v22;
    v24 = *(_WORD *)(*(__int64 (__fastcall **)(CCorrAPOBase *, _BYTE *, __int64))(v23 + 184))(this, v35, 3) == 0;
    v25 = *(_QWORD *)this;
    v43[3] = !v24;
    v24 = *(_WORD *)(*(__int64 (__fastcall **)(CCorrAPOBase *, _BYTE *, __int64))(v25 + 184))(this, v35, 4) == 0;
    v26 = *(_QWORD *)this;
    v43[4] = !v24;
    v24 = *(_WORD *)(*(__int64 (__fastcall **)(CCorrAPOBase *, _BYTE *, __int64))(v26 + 184))(this, v35, 5) == 0;
    fFramesPerSecond = (int)a3->fFramesPerSecond;
    v45[5] = 1;
    v43[5] = !v24;
    v45[0] = fFramesPerSecond;
    v45[1] = a3->dwSamplesPerFrame;
    v45[2] = a3->dwChannelMask;
    v45[3] = a3->dwValidBitsPerSample;
    v45[4] = a3->dwBytesPerSampleContainer;
    v28 = (int)a4->fFramesPerSecond;
    v44[5] = 1;
    v44[0] = v28;
    v44[1] = a4->dwSamplesPerFrame;
    v44[2] = a4->dwChannelMask;
    v44[3] = a4->dwValidBitsPerSample;
    v44[4] = a4->dwBytesPerSampleContainer;
    if ( *((_DWORD *)this + 36) )
    {
      v29 = 520;
      if ( v12 != 2 )
        v29 = 512;
    }
    else if ( v12 == 2 )
    {
      v29 = *((_DWORD *)this + 69) & 0x33 | 0x340;
    }
    else
    {
      v29 = 832;
    }
    if ( !*((_DWORD *)this + 90) )
      v29 &= *((_DWORD *)this + 69);
    v30 = *(_DWORD *)(*(__int64 (__fastcall **)(CCorrAPOBase *, _BYTE *, __int64))(*(_QWORD *)this + 184LL))(
                       this,
                       v35,
                       10);
    if ( *(_WORD *)(*(__int64 (__fastcall **)(CCorrAPOBase *, _BYTE *, __int64))(*(_QWORD *)this + 184LL))(
                     this,
                     v35,
                     16) )
    {
      v14 = v30;
    }
    else if ( (a4->dwChannelMask & (unsigned __int8)~(_BYTE)v30 & 8) != 0 )
    {
      v14 = a4->dwChannelMask & 0xFFFFFFF7;
    }
    v31 = *((_DWORD *)this + 36);
    v32 = *(_DWORD *)(*(__int64 (__fastcall **)(CCorrAPOBase *, _BYTE *, __int64))(*(_QWORD *)this + 184LL))(
                       this,
                       v35,
                       7);
    v33 = *(_DWORD *)(*(__int64 (__fastcall **)(CCorrAPOBase *, _BYTE *, __int64))(*(_QWORD *)this + 184LL))(
                       this,
                       v41,
                       15);
    v34 = (__int16 *)(*(__int64 (__fastcall **)(CCorrAPOBase *, _BYTE *, __int64))(*(_QWORD *)this + 184LL))(
                       this,
                       v42,
                       8);
    return corr_init(
             v9,
             0,
             v29,
             (_DWORD)v39,
             (__int64)v45,
             (__int64)v44,
             0,
             0,
             v38,
             v36,
             (__int64)v43,
             *v34,
             v33,
             v32,
             (__int64)v37,
             v14,
             v31);
  }
  return result;
}

```

## disassembly

```asm
0x180006ca0  push    rbp
0x180006ca2  push    rbx
0x180006ca3  push    rsi
0x180006ca4  push    rdi
0x180006ca5  push    r12
0x180006ca7  push    r13
0x180006ca9  push    r14
0x180006cab  push    r15
0x180006cad  lea     rbp, [rsp-38h]
0x180006cb2  sub     rsp, 148h
0x180006cb9  mov     rax, cs:__security_cookie
0x180006cc0  xor     rax, rsp
0x180006cc3  mov     [rbp+70h+var_48], rax
0x180006cc7  mov     rax, [rbp+70h+arg_20]
0x180006cce  mov     rbx, r8
0x180006cd1  mov     r8d, [r8+20h]
0x180006cd5  mov     rdi, r9
0x180006cd8  mov     [rbp+70h+var_C8], rax
0x180006cdc  mov     r13, rdx
0x180006cdf  mov     rax, [rbp+70h+arg_28]
0x180006ce6  mov     r14, rcx
0x180006ce9  mov     edx, [rbx+10h]
0x180006cec  mov     [rbp+70h+var_D8], rax
0x180006cf0  mov     eax, [r9+20h]
0x180006cf4  mov     r9d, [r9+10h]
0x180006cf8  mov     dword ptr [rsp+180h+var_160], eax
0x180006cfc  call    ?ChannelMaskQuality@CCorrAPOBase@@IEAA?AW4CHANNELMASKQUALITY@@KKKK@Z; CCorrAPOBase::ChannelMaskQuality(ulong,ulong,ulong,ulong)
0x180006d01  mov     r8, rdi; struct _UNCOMPRESSEDAUDIOFORMAT *
0x180006d04  mov     rdx, rbx; struct _UNCOMPRESSEDAUDIOFORMAT *
0x180006d07  mov     rcx, r14; this
0x180006d0a  mov     esi, eax
0x180006d0c  call    ?CheckFormats@CCorrAPOBase@@IEAAJPEBU_UNCOMPRESSEDAUDIOFORMAT@@0@Z; CCorrAPOBase::CheckFormats(_UNCOMPRESSEDAUDIOFORMAT const *,_UNCOMPRESSEDAUDIOFORMAT const *)
0x180006d11  xor     r12d, r12d
0x180006d14  test    eax, eax
0x180006d16  js      loc_180006FCC
0x180006d1c  mov     rax, [r14]
0x180006d1f  lea     rdx, [rbp+70h+var_C0]
0x180006d23  xor     r8d, r8d
0x180006d26  mov     rcx, r14
0x180006d29  mov     rax, [rax+0B8h]
0x180006d30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d35  lea     r15d, [r12+1]
0x180006d3a  mov     r8d, r15d
0x180006d3d  lea     rdx, [rbp+70h+var_F0]
0x180006d41  mov     ecx, [rax]
0x180006d43  mov     rax, [rax+8]
0x180006d47  mov     [rbp+70h+var_D0], rax
0x180006d4b  mov     rax, [r14]
0x180006d4e  mov     [rbp+70h+var_E0], ecx
0x180006d51  mov     rcx, r14
0x180006d54  mov     rax, [rax+0B8h]
0x180006d5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d60  lea     r8d, [r12+6]
0x180006d65  mov     rcx, r14
0x180006d68  lea     rdx, [rbp+70h+var_F0]
0x180006d6c  movd    xmm0, dword ptr [rax]
0x180006d70  mov     rax, [r14]
0x180006d73  cvtdq2ps xmm0, xmm0
0x180006d76  mov     rax, [rax+0B8h]
0x180006d7d  movss   [rbp+70h+var_90], xmm0
0x180006d82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d87  lea     r8d, [r12+2]
0x180006d8c  lea     rdx, [rbp+70h+var_F0]
0x180006d90  mov     ecx, [rax]
0x180006d92  add     ecx, r15d
0x180006d95  lea     eax, [rcx+rcx*2]
0x180006d98  mov     rcx, r14
0x180006d9b  movd    xmm0, eax
0x180006d9f  mov     rax, [r14]
0x180006da2  cvtdq2ps xmm0, xmm0
0x180006da5  mov     rax, [rax+0B8h]
0x180006dac  movss   [rbp+70h+var_8C], xmm0
0x180006db1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006db6  lea     r8d, [r12+3]
0x180006dbb  lea     rdx, [rbp+70h+var_F0]
0x180006dbf  mov     ecx, [rax]
0x180006dc1  mov     rax, [r14]
0x180006dc4  mov     [rbp+70h+var_88], ecx
0x180006dc7  mov     rcx, r14
0x180006dca  mov     rax, [rax+0B8h]
0x180006dd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006dd6  mov     ecx, r12d
0x180006dd9  lea     r8d, [r12+4]
0x180006dde  lea     rdx, [rbp+70h+var_F0]
0x180006de2  cmp     [rax], r12w
0x180006de6  mov     rax, [r14]
0x180006de9  setnz   cl
0x180006dec  mov     [rbp+70h+var_84], ecx
0x180006def  mov     rcx, r14
0x180006df2  mov     rax, [rax+0B8h]
0x180006df9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006dfe  mov     ecx, r12d
0x180006e01  lea     r8d, [r12+5]
0x180006e06  lea     rdx, [rbp+70h+var_F0]
0x180006e0a  cmp     [rax], r12w
0x180006e0e  mov     rax, [r14]
0x180006e11  setnz   cl
0x180006e14  mov     [rbp+70h+var_80], ecx
0x180006e17  mov     rcx, r14
0x180006e1a  mov     rax, [rax+0B8h]
0x180006e21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e26  mov     ecx, r12d
0x180006e29  cmp     [rax], r12w
0x180006e2d  cvttss2si rax, dword ptr [rbx+1Ch]
0x180006e33  setnz   cl
0x180006e36  mov     [rbp+70h+var_4C], r15d
0x180006e3a  mov     [rbp+70h+var_7C], ecx
0x180006e3d  mov     [rbp+70h+var_60], eax
0x180006e40  mov     eax, [rbx+10h]
0x180006e43  mov     [rbp+70h+var_5C], eax
0x180006e46  mov     eax, [rbx+20h]
0x180006e49  mov     [rbp+70h+var_58], eax
0x180006e4c  mov     eax, [rbx+18h]
0x180006e4f  mov     [rbp+70h+var_54], eax
0x180006e52  mov     eax, [rbx+14h]
0x180006e55  mov     [rbp+70h+var_50], eax
0x180006e58  cvttss2si rax, dword ptr [rdi+1Ch]
0x180006e5e  mov     [rbp+70h+var_64], r15d
0x180006e62  mov     [rbp+70h+var_78], eax
0x180006e65  mov     eax, [rdi+10h]
0x180006e68  mov     [rbp+70h+var_74], eax
0x180006e6b  mov     eax, [rdi+20h]
0x180006e6e  mov     [rbp+70h+var_70], eax
0x180006e71  mov     eax, [rdi+18h]
0x180006e74  mov     [rbp+70h+var_6C], eax
0x180006e77  mov     eax, [rdi+14h]
0x180006e7a  mov     [rbp+70h+var_68], eax
0x180006e7d  cmp     [r14+90h], r12d
0x180006e84  jnz     loc_180006FEC
0x180006e8a  cmp     esi, 2
0x180006e8d  jnz     loc_180007001
0x180006e93  mov     r15d, [r14+114h]
0x180006e9a  and     r15d, 33h
0x180006e9e  or      r15d, 340h
0x180006ea5  cmp     [r14+168h], r12d
0x180006eac  jnz     short loc_180006EB5
0x180006eae  and     r15d, [r14+114h]
0x180006eb5  mov     rax, [r14]
0x180006eb8  lea     rdx, [rbp+70h+var_F0]
0x180006ebc  mov     r8d, 0Ah
0x180006ec2  mov     rcx, r14
0x180006ec5  mov     rax, [rax+0B8h]
0x180006ecc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ed1  mov     r8d, 10h
0x180006ed7  lea     rdx, [rbp+70h+var_F0]
0x180006edb  mov     rcx, r14
0x180006ede  mov     ebx, [rax]
0x180006ee0  mov     rax, [r14]
0x180006ee3  mov     rax, [rax+0B8h]
0x180006eea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006eef  cmp     [rax], r12w
0x180006ef3  jz      loc_18000700C
0x180006ef9  mov     r12d, ebx
0x180006efc  mov     rax, [r14]
0x180006eff  lea     rdx, [rbp+70h+var_F0]
0x180006f03  mov     esi, [r14+90h]
0x180006f0a  mov     r8d, 7
0x180006f10  mov     rcx, r14
0x180006f13  mov     rax, [rax+0B8h]
0x180006f1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f1f  mov     r8d, 0Fh
0x180006f25  lea     rdx, [rbp+70h+var_B0]
0x180006f29  mov     rcx, r14
0x180006f2c  mov     edi, [rax]
0x180006f2e  mov     rax, [r14]
0x180006f31  mov     rax, [rax+0B8h]
0x180006f38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f3d  mov     r8d, 8
0x180006f43  lea     rdx, [rbp+70h+var_A0]
0x180006f47  mov     rcx, r14
0x180006f4a  mov     ebx, [rax]
0x180006f4c  mov     rax, [r14]
0x180006f4f  mov     rax, [rax+0B8h]
0x180006f56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f5b  mov     r9, [rbp+70h+var_C8]
0x180006f5f  mov     r8d, r15d
0x180006f62  mov     [rsp+180h+var_100], esi
0x180006f69  mov     rcx, r13
0x180006f6c  mov     [rsp+180h+var_108], r12d
0x180006f71  movsx   edx, word ptr [rax]
0x180006f74  mov     rax, [rbp+70h+var_D8]
0x180006f78  mov     [rsp+180h+var_110], rax
0x180006f7d  lea     rax, [rbp+70h+var_90]
0x180006f81  mov     [rsp+180h+var_118], edi
0x180006f85  mov     [rsp+180h+var_120], ebx
0x180006f89  mov     [rsp+180h+var_128], edx
0x180006f8d  xor     edx, edx
0x180006f8f  mov     [rsp+180h+var_130], rax
0x180006f94  mov     eax, [rbp+70h+var_E0]
0x180006f97  mov     [rsp+180h+var_138], eax
0x180006f9b  mov     rax, [rbp+70h+var_D0]
0x180006f9f  mov     [rsp+180h+var_140], rax
0x180006fa4  lea     rax, [rbp+70h+var_78]
0x180006fa8  mov     [rsp+180h+var_148], 0
0x180006fb0  mov     [rsp+180h+var_150], 0
0x180006fb9  mov     [rsp+180h+var_158], rax
0x180006fbe  lea     rax, [rbp+70h+var_60]
0x180006fc2  mov     [rsp+180h+var_160], rax
0x180006fc7  call    corr_init
0x180006fcc  mov     rcx, [rbp+70h+var_48]
0x180006fd0  xor     rcx, rsp; StackCookie
0x180006fd3  call    __security_check_cookie
0x180006fd8  add     rsp, 148h
0x180006fdf  pop     r15
0x180006fe1  pop     r14
0x180006fe3  pop     r13
0x180006fe5  pop     r12
0x180006fe7  pop     rdi
0x180006fe8  pop     rsi
0x180006fe9  pop     rbx
0x180006fea  pop     rbp
0x180006feb  retn
0x180006fec  mov     eax, 200h
0x180006ff1  cmp     esi, 2
0x180006ff4  lea     r15d, [rax+8]
0x180006ff8  cmovnz  r15d, eax
0x180006ffc  jmp     loc_180006EA5
0x180007001  mov     r15d, 340h
0x180007007  jmp     loc_180006EA5
0x18000700c  not     ebx
0x18000700e  and     ebx, [rdi+20h]
0x180007011  test    bl, 8
0x180007014  jz      loc_180006EFC
0x18000701a  mov     r12d, [rdi+20h]
0x18000701e  and     r12d, 0FFFFFFF7h
0x180007022  jmp     loc_180006EFC
```
