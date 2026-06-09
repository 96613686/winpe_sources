# CWmpEncoderFrame::WriteSource(IWICBitmapSource *,WICRect *)

- ea: `0x180028fb0`
- end: `0x180029581`
- name: `?WriteSource@CWmpEncoderFrame@@UEAAJPEAUIWICBitmapSource@@PEAUWICRect@@@Z`
- size: `1489`
- prototype: `__int64 __fastcall(CWmpEncoderFrame *__hidden this, struct IWICBitmapSource *, struct WICRect *)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180028980`
- `0x180028e94`
- `0x180028fb0`
- `0x180029590`
- `0x1800297c0`
- `0x18002aec8`
- `0x180030150`
- `0x180034420`
- `0x180035e50`
- `0x180044010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180029449`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180029449`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180028ffb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180028ffb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002939e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002939e`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800294f0`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800294f0`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18002938f`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18002938f`

## pseudocode

```c
__int64 __fastcall CWmpEncoderFrame::WriteSource(
        CWmpEncoderFrame *this,
        struct IWICBitmapSource *a2,
        struct WICRect *a3)
{
  char *v3; // r15
  struct _RTL_CRITICAL_SECTION *v4; // r12
  bool v8; // zf
  struct IWICBitmapSourceVtbl *lpVtbl; // rax
  int v10; // eax
  int v11; // ecx
  int FrameBuffer; // ebx
  struct IWICBitmapSourceVtbl *v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  struct IWICBitmapSourceVtbl *v16; // rax
  _QWORD *v17; // r15
  __int64 v18; // rax
  __int64 v19; // rax
  struct IWICBitmapSourceVtbl *v20; // rax
  struct IWICBitmapSource *v21; // rcx
  struct IWICComponentFactory *WICFactory; // rax
  __int64 v23; // rdx
  void *v24; // rcx
  unsigned __int64 Height; // r15
  INT Y; // r12d
  unsigned __int64 i; // r14
  __int64 v29; // rcx
  INT v30; // edx
  DWORD v31; // r8d
  const void *v32; // rdx
  void *v33; // rcx
  __int64 v34; // rax
  char *v35; // [rsp+40h] [rbp-69h]
  LONG DistanceToMoveHigh[2]; // [rsp+48h] [rbp-61h] BYREF
  DWORD NumberOfBytesWritten[2]; // [rsp+50h] [rbp-59h] BYREF
  __int64 v38; // [rsp+58h] [rbp-51h] BYREF
  int v39; // [rsp+60h] [rbp-49h]
  struct IWICBitmapSource *v40; // [rsp+68h] [rbp-41h] BYREF
  __int64 v41; // [rsp+70h] [rbp-39h] BYREF
  _QWORD v42[6]; // [rsp+78h] [rbp-31h] BYREF
  __int64 v43; // [rsp+A8h] [rbp-1h] BYREF
  DWORD v44; // [rsp+B0h] [rbp+7h]
  LONG v45; // [rsp+B4h] [rbp+Bh]
  struct _GUID v46; // [rsp+B8h] [rbp+Fh] BYREF

  v3 = (char *)this - 56;
  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this - 48);
  v35 = (char *)this - 56;
  if ( *((_BYTE *)this - 8) )
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this - 48));
  v40 = 0;
  v38 = 0;
  v44 = *((_DWORD *)this - 16569);
  v45 = *((_DWORD *)this - 16568);
  v41 = 0;
  memset(v42, 0, sizeof(v42));
  v43 = 0;
  if ( !a2 )
  {
    FrameBuffer = -2147024809;
    goto LABEL_65;
  }
  if ( *((int *)this - 16590) < 2 )
  {
    FrameBuffer = -2003292412;
    goto LABEL_65;
  }
  v8 = -1.0 == *((double *)this - 8283);
  v39 = 0;
  if ( v8 && -1.0 == *((double *)this - 8282) )
  {
    lpVtbl = a2->lpVtbl;
    *(double *)NumberOfBytesWritten = DOUBLE_N1_0;
    *(double *)DistanceToMoveHigh = DOUBLE_N1_0;
    if ( ((int (__fastcall *)(struct IWICBitmapSource *, DWORD *, LONG *))lpVtbl->GetResolution)(
           a2,
           NumberOfBytesWritten,
           DistanceToMoveHigh) < 0
      || (int)CWmpEncoderFrame::SetResolution(this, *(double *)NumberOfBytesWritten, *(double *)DistanceToMoveHigh) < 0 )
    {
      *((_QWORD *)this - 8282) = 0x4058000000000000LL;
      *((_QWORD *)this - 8283) = 0x4058000000000000LL;
    }
  }
  v10 = *((_DWORD *)this - 16569);
  if ( v10 && (v11 = *((_DWORD *)this - 16568)) != 0 )
  {
    if ( a3 )
    {
      if ( a3->Width != v10 || a3->Height != v11 )
      {
LABEL_16:
        FrameBuffer = -2003292343;
        goto LABEL_53;
      }
    }
    else
    {
      a3 = (struct WICRect *)&v43;
    }
  }
  else
  {
    if ( !a3 )
    {
      v13 = a2->lpVtbl;
      NumberOfBytesWritten[0] = 0;
      DistanceToMoveHigh[0] = 0;
      FrameBuffer = ((__int64 (__fastcall *)(struct IWICBitmapSource *, DWORD *, LONG *))v13->GetSize)(
                      a2,
                      NumberOfBytesWritten,
                      DistanceToMoveHigh);
      if ( FrameBuffer < 0 )
        goto LABEL_53;
      a3 = (struct WICRect *)&v43;
      v44 = NumberOfBytesWritten[0];
      v45 = DistanceToMoveHigh[0];
      v43 = 0;
    }
    FrameBuffer = CWmpEncoderFrame::SetSize(this, a3->Width, a3->Height);
    if ( FrameBuffer < 0 )
      goto LABEL_53;
  }
  if ( *((_DWORD *)this + 29)
    && ((__int64 (__fastcall *)(struct IWICBitmapSource *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
         a2,
         &IID_IWMPhotoElementaryStream,
         &v41) >= 0
    && (*(int (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v41 + 24LL))(v41, v42) >= 0 )
  {
    v14 = *((_QWORD *)this - 8294);
    v39 = 1;
    v15 = v14 - v42[0];
    if ( !v15 )
      v15 = *((_QWORD *)this - 8293) - v42[1];
    if ( !v15 )
    {
      if ( *((_DWORD *)this - 16590) != 2 )
      {
        FrameBuffer = -2003292412;
        goto LABEL_53;
      }
      if ( a3->Height == *((_DWORD *)this - 16568) )
      {
        DistanceToMoveHigh[0] = *((unsigned __int8 *)this + 88);
        FrameBuffer = TransformConsolidate(LODWORD(v42[5]), a3, &v42[4], (char *)&v42[4] + 4, DistanceToMoveHigh);
        if ( FrameBuffer >= 0 )
        {
          *((_BYTE *)this + 88) = DistanceToMoveHigh[0];
          FrameBuffer = CWmpEncoderFrame::HrEncodeStream((char *)this - 66376, v42, a3, 0);
          if ( FrameBuffer >= 0 )
            *((_DWORD *)this - 16590) = 4;
        }
        goto LABEL_53;
      }
      goto LABEL_16;
    }
  }
  if ( (unsigned int)(a3->Height + *((_DWORD *)this + 4)) > *((_DWORD *)this - 16568) )
  {
    FrameBuffer = -2003292346;
    goto LABEL_53;
  }
  v16 = a2->lpVtbl;
  v46 = 0;
  FrameBuffer = ((__int64 (__fastcall *)(struct IWICBitmapSource *, struct _GUID *))v16->GetPixelFormat)(a2, &v46);
  if ( FrameBuffer >= 0 )
  {
    v17 = (_QWORD *)((char *)this - 66352);
    v18 = *(_QWORD *)&GUID_WICPixelFormatDontCare.Data1 - *((_QWORD *)this - 8294);
    if ( *(_QWORD *)&GUID_WICPixelFormatDontCare.Data1 == *((_QWORD *)this - 8294) )
      v18 = *(_QWORD *)GUID_WICPixelFormatDontCare.Data4 - v17[1];
    if ( !v18 )
    {
      FrameBuffer = CWmpEncoderFrame::SetPixelFormat(this, &v46);
      if ( FrameBuffer < 0 )
        goto LABEL_52;
    }
    v19 = *v17 - *(_QWORD *)&v46.Data1;
    if ( *v17 == *(_QWORD *)&v46.Data1 )
      v19 = v17[1] - *(_QWORD *)v46.Data4;
    if ( v19 )
    {
      WICFactory = GetWICFactory();
      FrameBuffer = ((__int64 (__fastcall *)(struct IWICComponentFactory *, struct IWICBitmapSource **))WICFactory->lpVtbl->CreateFormatConverter)(
                      WICFactory,
                      &v40);
      if ( FrameBuffer < 0 )
        goto LABEL_52;
      FrameBuffer = ((__int64 (__fastcall *)(struct IWICBitmapSource *, struct IWICBitmapSource *, char *, _QWORD, _QWORD, _QWORD, _DWORD))v40->lpVtbl[1].QueryInterface)(
                      v40,
                      a2,
                      (char *)this - 66352,
                      0,
                      0,
                      0,
                      0);
      if ( FrameBuffer < 0 )
        goto LABEL_52;
      v21 = v40;
      v20 = v40->lpVtbl;
    }
    else
    {
      v20 = a2->lpVtbl;
      v21 = a2;
    }
    FrameBuffer = ((__int64 (__fastcall *)(struct IWICBitmapSource *, GUID *, __int64 *))v20->QueryInterface)(
                    v21,
                    &IID_IWICBitmapSource,
                    &v38);
    if ( FrameBuffer >= 0 )
    {
      FrameBuffer = CWmpEncoderFrame::HrAllocateFrameBuffer((CWmpEncoderFrame *)((char *)this - 66376));
      if ( FrameBuffer >= 0 )
      {
        v23 = *((_QWORD *)this - 8) * *((unsigned int *)this + 4);
        v24 = (void *)*((_QWORD *)this + 24);
        if ( v24 == (void *)-1LL )
        {
          FrameBuffer = (*(__int64 (__fastcall **)(__int64, struct WICRect *, _QWORD, _QWORD, __int64))(*(_QWORD *)v38 + 56LL))(
                          v38,
                          a3,
                          *((unsigned int *)this - 16),
                          (unsigned int)(a3->Height * *((_DWORD *)this - 16)),
                          *((_QWORD *)this - 9) + v23);
          if ( FrameBuffer < 0 )
            goto LABEL_52;
        }
        else
        {
          Height = a3->Height;
          Y = a3->Y;
          DistanceToMoveHigh[0] = (*((_QWORD *)this - 8) * (unsigned __int64)*((unsigned int *)this + 4)) >> 32;
          if ( SetFilePointer(v24, v23, DistanceToMoveHigh, 0) == -1 && GetLastError() )
          {
            FrameBuffer = -1;
            goto LABEL_52;
          }
          for ( i = Height; i; i -= v34 )
          {
            v29 = v38;
            v30 = i;
            if ( i > 0x10 )
              v30 = 16;
            a3->Height = v30;
            FrameBuffer = (*(__int64 (__fastcall **)(__int64, struct WICRect *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v29 + 56LL))(
                            v29,
                            a3,
                            *((unsigned int *)this - 16),
                            (unsigned int)(v30 * *((_DWORD *)this - 16)),
                            *((_QWORD *)this - 9));
            if ( FrameBuffer < 0 )
              goto LABEL_52;
            v31 = a3->Height * *((_DWORD *)this - 16);
            v32 = (const void *)*((_QWORD *)this - 9);
            v33 = (void *)*((_QWORD *)this + 24);
            NumberOfBytesWritten[0] = 0;
            if ( !WriteFile(v33, v32, v31, NumberOfBytesWritten, 0) )
            {
              FrameBuffer = -2003292303;
              goto LABEL_52;
            }
            v34 = a3->Height;
            a3->Y += v34;
          }
          a3->Height = Height;
          a3->Y = Y;
        }
        *((_DWORD *)this + 4) += a3->Height;
        *((_DWORD *)this - 16590) = 3;
      }
    }
LABEL_52:
    v3 = v35;
  }
LABEL_53:
  if ( v40 )
  {
    ((void (__fastcall *)(struct IWICBitmapSource *))v40->lpVtbl->Release)(v40);
    v40 = 0;
  }
  if ( v38 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
    v38 = 0;
  }
  if ( v39 )
  {
    if ( v42[2] )
    {
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v42[2] + 16LL))(v42[2]);
      v42[2] = 0;
    }
    if ( v42[3] )
    {
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v42[3] + 16LL))(v42[3]);
      v42[3] = 0;
    }
  }
  if ( v41 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
    v41 = 0;
  }
  v4 = (struct _RTL_CRITICAL_SECTION *)(v3 + 8);
LABEL_65:
  if ( v3 && v3[48] )
    LeaveCriticalSection(v4);
  return (unsigned int)FrameBuffer;
}

```

## disassembly

```asm
0x180028fb0  mov     [rsp-8+arg_18], rbx
0x180028fb5  push    rbp
0x180028fb6  push    rsi
0x180028fb7  push    rdi
0x180028fb8  push    r12
0x180028fba  push    r13
0x180028fbc  push    r14
0x180028fbe  push    r15
0x180028fc0  lea     rbp, [rsp-27h]
0x180028fc5  sub     rsp, 0D0h
0x180028fcc  mov     rax, cs:__security_cookie
0x180028fd3  xor     rax, rsp
0x180028fd6  mov     [rbp+57h+var_38], rax
0x180028fda  lea     r15, [rcx-38h]
0x180028fde  xor     ebx, ebx
0x180028fe0  lea     r12, [r15+8]
0x180028fe4  mov     [rbp+57h+var_C0], r15
0x180028fe8  mov     rsi, r8
0x180028feb  mov     r14, rdx
0x180028fee  mov     rdi, rcx
0x180028ff1  cmp     [r12+28h], bl
0x180028ff6  jz      short loc_180029001
0x180028ff8  mov     rcx, r12; lpCriticalSection
0x180028ffb  call    cs:__imp_EnterCriticalSection
0x180029001  mov     [rbp+57h+var_98], rbx
0x180029005  xorps   xmm0, xmm0
0x180029008  mov     [rbp+57h+var_A8], rbx
0x18002900c  lea     r13, [rdi-10348h]
0x180029013  mov     eax, [r13+64h]
0x180029017  mov     [rbp+57h+var_50], eax
0x18002901a  mov     eax, [rdi-102E0h]
0x180029020  mov     [rbp+57h+var_4C], eax
0x180029023  mov     [rbp+57h+var_90], rbx
0x180029027  mov     dword ptr [rbp+57h+var_88], ebx
0x18002902a  mov     [rbp+57h+var_58], rbx
0x18002902e  movups  [rbp+57h+var_74], xmm0
0x180029032  movups  xmmword ptr [rbp+57h+var_88+4], xmm0
0x180029036  movups  [rbp+57h+var_74+0Ch], xmm0
0x18002903a  test    r14, r14
0x18002903d  jz      loc_18002957A
0x180029043  cmp     dword ptr [rdi-10338h], 2
0x18002904a  jl      loc_18002956E
0x180029050  movsd   xmm0, cs:__real@bff0000000000000
0x180029058  xor     r12d, r12d
0x18002905b  ucomisd xmm0, qword ptr [rdi-102D8h]
0x180029063  mov     [rbp+57h+var_A0], r12d
0x180029067  jp      short loc_1800290CA
0x180029069  jnz     short loc_1800290CA
0x18002906b  ucomisd xmm0, qword ptr [rdi-102D0h]
0x180029073  jp      short loc_1800290CA
0x180029075  jnz     short loc_1800290CA
0x180029077  mov     rax, [r14]
0x18002907a  lea     r8, [rbp+57h+DistanceToMoveHigh]
0x18002907e  lea     rdx, [rbp+57h+NumberOfBytesWritten]
0x180029082  movsd   qword ptr [rbp+57h+NumberOfBytesWritten], xmm0
0x180029087  mov     rcx, r14
0x18002908a  movsd   qword ptr [rbp+57h+DistanceToMoveHigh], xmm0
0x18002908f  mov     rax, [rax+28h]
0x180029093  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029098  test    eax, eax
0x18002909a  js      short loc_1800290B2
0x18002909c  movsd   xmm2, qword ptr [rbp+57h+DistanceToMoveHigh]; double
0x1800290a1  mov     rcx, rdi; this
0x1800290a4  movsd   xmm1, qword ptr [rbp+57h+NumberOfBytesWritten]; double
0x1800290a9  call    ?SetResolution@CWmpEncoderFrame@@UEAAJNN@Z; CWmpEncoderFrame::SetResolution(double,double)
0x1800290ae  test    eax, eax
0x1800290b0  jns     short loc_1800290CA
0x1800290b2  mov     rax, 4058000000000000h
0x1800290bc  mov     [rdi-102D0h], rax
0x1800290c3  mov     [rdi-102D8h], rax
0x1800290ca  mov     eax, [rdi-102E4h]
0x1800290d0  test    eax, eax
0x1800290d2  jz      short loc_1800290FD
0x1800290d4  mov     ecx, [rdi-102E0h]
0x1800290da  test    ecx, ecx
0x1800290dc  jz      short loc_1800290FD
0x1800290de  test    rsi, rsi
0x1800290e1  jnz     short loc_1800290E9
0x1800290e3  lea     rsi, [rbp+57h+var_58]
0x1800290e7  jmp     short loc_180029158
0x1800290e9  cmp     [rsi+8], eax
0x1800290ec  jnz     short loc_1800290F3
0x1800290ee  cmp     [rsi+0Ch], ecx
0x1800290f1  jz      short loc_180029158
0x1800290f3  mov     ebx, 88982F49h
0x1800290f8  jmp     loc_1800293B3
0x1800290fd  test    rsi, rsi
0x180029100  jnz     short loc_18002913F
0x180029102  mov     rax, [r14]
0x180029105  lea     r8, [rbp+57h+DistanceToMoveHigh]
0x180029109  lea     rdx, [rbp+57h+NumberOfBytesWritten]
0x18002910d  mov     [rbp+57h+NumberOfBytesWritten], r12d
0x180029111  mov     rcx, r14
0x180029114  mov     [rbp+57h+DistanceToMoveHigh], r12d
0x180029118  mov     rax, [rax+18h]
0x18002911c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029121  mov     ebx, eax
0x180029123  test    eax, eax
0x180029125  js      loc_1800293B3
0x18002912b  mov     eax, [rbp+57h+NumberOfBytesWritten]
0x18002912e  lea     rsi, [rbp+57h+var_58]
0x180029132  mov     [rbp+57h+var_50], eax
0x180029135  mov     eax, [rbp+57h+DistanceToMoveHigh]
0x180029138  mov     [rbp+57h+var_4C], eax
0x18002913b  mov     [rbp+57h+var_58], r12
0x18002913f  mov     r8d, [rsi+0Ch]; unsigned int
0x180029143  mov     rcx, rdi; this
0x180029146  mov     edx, [rsi+8]; unsigned int
0x180029149  call    ?SetSize@CWmpEncoderFrame@@UEAAJII@Z; CWmpEncoderFrame::SetSize(uint,uint)
0x18002914e  mov     ebx, eax
0x180029150  test    eax, eax
0x180029152  js      loc_1800293B3
0x180029158  cmp     [rdi+74h], r12d
0x18002915c  jz      loc_180029247
0x180029162  mov     rax, [r14]
0x180029165  lea     r8, [rbp+57h+var_90]
0x180029169  lea     rdx, IID_IWMPhotoElementaryStream
0x180029170  mov     rcx, r14
0x180029173  mov     rax, [rax]
0x180029176  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002917b  test    eax, eax
0x18002917d  js      loc_180029247
0x180029183  mov     rcx, [rbp+57h+var_90]
0x180029187  lea     rdx, [rbp+57h+var_88]
0x18002918b  mov     rax, [rcx]
0x18002918e  mov     rax, [rax+18h]
0x180029192  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029197  test    eax, eax
0x180029199  js      loc_180029247
0x18002919f  mov     rax, [rdi-10330h]
0x1800291a6  mov     [rbp+57h+var_A0], 1
0x1800291ad  sub     rax, [rbp+57h+var_88]
0x1800291b1  jnz     short loc_1800291BE
0x1800291b3  mov     rax, [rdi-10328h]
0x1800291ba  sub     rax, [rbp+57h+var_80]
0x1800291be  test    rax, rax
0x1800291c1  jnz     loc_180029247
0x1800291c7  cmp     dword ptr [rdi-10338h], 2
0x1800291ce  jnz     short loc_18002923D
0x1800291d0  mov     eax, [rdi-102E0h]
0x1800291d6  cmp     [rsi+0Ch], eax
0x1800291d9  jnz     loc_1800290F3
0x1800291df  movzx   eax, byte ptr [rdi+58h]
0x1800291e3  lea     r9, [rbp+57h+var_64]
0x1800291e7  mov     ecx, [rbp+57h+var_60]
0x1800291ea  lea     r8, [rbp+57h+var_74+0Ch]
0x1800291ee  mov     [rbp+57h+DistanceToMoveHigh], eax
0x1800291f1  mov     rdx, rsi
0x1800291f4  lea     rax, [rbp+57h+DistanceToMoveHigh]
0x1800291f8  mov     [rsp+100h+lpOverlapped], rax
0x1800291fd  call    ?TransformConsolidate@@YAJW4ORIENTATION@@PEAUWICRect@@PEAI2PEAW41@@Z; TransformConsolidate(ORIENTATION,WICRect *,uint *,uint *,ORIENTATION *)
0x180029202  mov     ebx, eax
0x180029204  test    eax, eax
0x180029206  js      loc_1800293B3
0x18002920c  mov     al, byte ptr [rbp+57h+DistanceToMoveHigh]
0x18002920f  lea     rdx, [rbp+57h+var_88]
0x180029213  xor     r9d, r9d
0x180029216  mov     [rdi+58h], al
0x180029219  mov     r8, rsi
0x18002921c  mov     rcx, r13
0x18002921f  call    ?HrEncodeStream@CWmpEncoderFrame@@MEAAJPEAUtagWMPhotoElementaryStreamInfo@@PEAUWICRect@@W4ORIENTATION@@@Z; CWmpEncoderFrame::HrEncodeStream(tagWMPhotoElementaryStreamInfo *,WICRect *,ORIENTATION)
0x180029224  mov     ebx, eax
0x180029226  test    eax, eax
0x180029228  js      loc_1800293B3
0x18002922e  mov     dword ptr [rdi-10338h], 4
0x180029238  jmp     loc_1800293B3
0x18002923d  mov     ebx, 88982F04h
0x180029242  jmp     loc_1800293B3
0x180029247  mov     eax, [rdi+10h]
0x18002924a  add     eax, [rsi+0Ch]
0x18002924d  cmp     eax, [rdi-102E0h]
0x180029253  ja      loc_180029564
0x180029259  mov     rax, [r14]
0x18002925c  lea     rdx, [rbp+57h+var_48]
0x180029260  xorps   xmm0, xmm0
0x180029263  mov     rcx, r14
0x180029266  movups  xmmword ptr [rbp+57h+var_48.Data1], xmm0
0x18002926a  mov     rax, [rax+20h]
0x18002926e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029273  mov     ebx, eax
0x180029275  test    eax, eax
0x180029277  js      loc_1800293B3
0x18002927d  mov     rax, qword ptr cs:GUID_WICPixelFormatDontCare.Data1
0x180029284  lea     r15, [rdi-10330h]
0x18002928b  sub     rax, [r15]
0x18002928e  jnz     short loc_18002929B
0x180029290  mov     rax, qword ptr cs:GUID_WICPixelFormatDontCare.Data4
0x180029297  sub     rax, [r15+8]
0x18002929b  test    rax, rax
0x18002929e  jnz     short loc_1800292B6
0x1800292a0  lea     rdx, [rbp+57h+var_48]; struct _GUID *
0x1800292a4  mov     rcx, rdi; this
0x1800292a7  call    ?SetPixelFormat@CWmpEncoderFrame@@UEAAJPEAU_GUID@@@Z; CWmpEncoderFrame::SetPixelFormat(_GUID *)
0x1800292ac  mov     ebx, eax
0x1800292ae  test    eax, eax
0x1800292b0  js      loc_1800293AF
0x1800292b6  mov     rax, [r15]
0x1800292b9  sub     rax, qword ptr [rbp+57h+var_48.Data1]
0x1800292bd  jnz     short loc_1800292C7
0x1800292bf  mov     rax, [r15+8]
0x1800292c3  sub     rax, qword ptr [rbp+57h+var_48.Data4]
0x1800292c7  test    rax, rax
0x1800292ca  jnz     short loc_1800292D4
0x1800292cc  mov     rax, [r14]
0x1800292cf  mov     rcx, r14
0x1800292d2  jmp     short loc_180029336
0x1800292d4  call    ?GetWICFactory@@YAPEAUIWICComponentFactory@@XZ; GetWICFactory(void)
0x1800292d9  mov     r8, rax
0x1800292dc  lea     rdx, [rbp+57h+var_98]
0x1800292e0  mov     rcx, [rax]
0x1800292e3  mov     rax, [rcx+50h]
0x1800292e7  mov     rcx, r8
0x1800292ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800292ef  mov     ebx, eax
0x1800292f1  test    eax, eax
0x1800292f3  js      loc_1800293AF
0x1800292f9  mov     rcx, [rbp+57h+var_98]
0x1800292fd  xorps   xmm0, xmm0
0x180029300  mov     [rsp+100h+var_D0], r12d
0x180029305  xor     r9d, r9d
0x180029308  movsd   [rsp+100h+var_D8], xmm0
0x18002930e  mov     r8, r15
0x180029311  mov     rdx, r14
0x180029314  mov     [rsp+100h+lpOverlapped], r12
0x180029319  mov     rax, [rcx]
0x18002931c  mov     rax, [rax+40h]
0x180029320  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029325  mov     ebx, eax
0x180029327  test    eax, eax
0x180029329  js      loc_1800293AF
0x18002932f  mov     rcx, [rbp+57h+var_98]
0x180029333  mov     rax, [rcx]
0x180029336  mov     rax, [rax]
0x180029339  lea     r8, [rbp+57h+var_A8]
0x18002933d  lea     rdx, IID_IWICBitmapSource
0x180029344  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029349  mov     ebx, eax
0x18002934b  test    eax, eax
0x18002934d  js      short loc_1800293AF
0x18002934f  mov     rcx, r13; this
0x180029352  call    ?HrAllocateFrameBuffer@CWmpEncoderFrame@@MEAAJXZ; CWmpEncoderFrame::HrAllocateFrameBuffer(void)
0x180029357  mov     ebx, eax
0x180029359  test    eax, eax
0x18002935b  js      short loc_1800293AF
0x18002935d  mov     edx, [rdi+10h]
0x180029360  imul    rdx, [rdi-40h]; lDistanceToMove
0x180029365  mov     rcx, [rdi+0C0h]; hFile
0x18002936c  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180029370  jz      loc_18002951D
0x180029376  movsxd  r15, dword ptr [rsi+0Ch]
0x18002937a  lea     r8, [rbp+57h+DistanceToMoveHigh]; lpDistanceToMoveHigh
0x18002937e  mov     r12d, [rsi+4]
0x180029382  mov     rax, rdx
0x180029385  sar     rax, 20h
0x180029389  xor     r9d, r9d; dwMoveMethod
0x18002938c  mov     [rbp+57h+DistanceToMoveHigh], eax
0x18002938f  call    cs:__imp_SetFilePointer
0x180029395  cmp     eax, 0FFFFFFFFh
0x180029398  jnz     loc_180029478
0x18002939e  call    cs:__imp_GetLastError
0x1800293a4  test    eax, eax
0x1800293a6  jz      loc_180029478
0x1800293ac  or      ebx, 0FFFFFFFFh
0x1800293af  mov     r15, [rbp+57h+var_C0]
0x1800293b3  mov     rcx, [rbp+57h+var_98]
0x1800293b7  xor     edi, edi
0x1800293b9  test    rcx, rcx
0x1800293bc  jz      short loc_1800293CE
0x1800293be  mov     rax, [rcx]
0x1800293c1  mov     rax, [rax+10h]
0x1800293c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800293ca  mov     [rbp+57h+var_98], rdi
0x1800293ce  mov     rcx, [rbp+57h+var_A8]
0x1800293d2  test    rcx, rcx
0x1800293d5  jz      short loc_1800293E7
0x1800293d7  mov     rax, [rcx]
0x1800293da  mov     rax, [rax+10h]
0x1800293de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800293e3  mov     [rbp+57h+var_A8], rdi
0x1800293e7  cmp     [rbp+57h+var_A0], edi
0x1800293ea  jz      short loc_18002941E
0x1800293ec  mov     rcx, [rbp-21h]
0x1800293f0  test    rcx, rcx
0x1800293f3  jz      short loc_180029405
0x1800293f5  mov     rax, [rcx]
0x1800293f8  mov     rax, [rax+10h]
0x1800293fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029401  mov     [rbp-21h], rdi
0x180029405  mov     rcx, qword ptr [rbp+57h+var_74+4]
0x180029409  test    rcx, rcx
0x18002940c  jz      short loc_18002941E
0x18002940e  mov     rax, [rcx]
0x180029411  mov     rax, [rax+10h]
0x180029415  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002941a  mov     qword ptr [rbp+57h+var_74+4], rdi
0x18002941e  mov     rcx, [rbp+57h+var_90]
0x180029422  test    rcx, rcx
0x180029425  jz      short loc_180029437
0x180029427  mov     rax, [rcx]
0x18002942a  mov     rax, [rax+10h]
  ... truncated ...
```
