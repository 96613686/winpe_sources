# CWmpEncoderFrame::WriteSource(IWICBitmapSource *,WICRect *)

- ea: `0x180029040`
- end: `0x180029630`
- name: `?WriteSource@CWmpEncoderFrame@@UEAAJPEAUIWICBitmapSource@@PEAUWICRect@@@Z`
- size: `1520`
- prototype: `__int64 __fastcall(CWmpEncoderFrame *__hidden this, struct IWICBitmapSource *, struct WICRect *)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180028940`
- `0x180028f18`
- `0x180029040`
- `0x180029640`
- `0x180029930`
- `0x18002b078`
- `0x1800305a0`
- `0x180034980`
- `0x180036420`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800294eb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800294eb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002908b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002908b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002943a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002943a`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180029599`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180029599`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180029425`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180029425`

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
0x180029040  mov     [rsp-8+arg_18], rbx
0x180029045  push    rbp
0x180029046  push    rsi
0x180029047  push    rdi
0x180029048  push    r12
0x18002904a  push    r13
0x18002904c  push    r14
0x18002904e  push    r15
0x180029050  lea     rbp, [rsp-27h]
0x180029055  sub     rsp, 0D0h
0x18002905c  mov     rax, cs:__security_cookie
0x180029063  xor     rax, rsp
0x180029066  mov     [rbp+57h+var_38], rax
0x18002906a  lea     r15, [rcx-38h]
0x18002906e  xor     ebx, ebx
0x180029070  lea     r12, [r15+8]
0x180029074  mov     [rbp+57h+var_C0], r15
0x180029078  mov     rsi, r8
0x18002907b  mov     r14, rdx
0x18002907e  mov     rdi, rcx
0x180029081  cmp     [r12+28h], bl
0x180029086  jz      short loc_180029097
0x180029088  mov     rcx, r12; lpCriticalSection
0x18002908b  call    cs:__imp_EnterCriticalSection
0x180029092  nop     dword ptr [rax+rax+00h]
0x180029097  mov     [rbp+57h+var_98], rbx
0x18002909b  xorps   xmm0, xmm0
0x18002909e  mov     [rbp+57h+var_A8], rbx
0x1800290a2  lea     r13, [rdi-10348h]
0x1800290a9  mov     eax, [r13+64h]
0x1800290ad  mov     [rbp+57h+var_50], eax
0x1800290b0  mov     eax, [rdi-102E0h]
0x1800290b6  mov     [rbp+57h+var_4C], eax
0x1800290b9  mov     [rbp+57h+var_90], rbx
0x1800290bd  mov     dword ptr [rbp+57h+var_88], ebx
0x1800290c0  mov     [rbp+57h+var_58], rbx
0x1800290c4  movups  [rbp+57h+var_74], xmm0
0x1800290c8  movups  xmmword ptr [rbp+57h+var_88+4], xmm0
0x1800290cc  movups  [rbp+57h+var_74+0Ch], xmm0
0x1800290d0  test    r14, r14
0x1800290d3  jz      loc_180029629
0x1800290d9  cmp     dword ptr [rdi-10338h], 2
0x1800290e0  jl      loc_18002961D
0x1800290e6  movsd   xmm0, cs:__real@bff0000000000000
0x1800290ee  xor     r12d, r12d
0x1800290f1  ucomisd xmm0, qword ptr [rdi-102D8h]
0x1800290f9  mov     [rbp+57h+var_A0], r12d
0x1800290fd  jp      short loc_180029160
0x1800290ff  jnz     short loc_180029160
0x180029101  ucomisd xmm0, qword ptr [rdi-102D0h]
0x180029109  jp      short loc_180029160
0x18002910b  jnz     short loc_180029160
0x18002910d  mov     rax, [r14]
0x180029110  lea     r8, [rbp+57h+DistanceToMoveHigh]
0x180029114  lea     rdx, [rbp+57h+NumberOfBytesWritten]
0x180029118  movsd   qword ptr [rbp+57h+NumberOfBytesWritten], xmm0
0x18002911d  mov     rcx, r14
0x180029120  movsd   qword ptr [rbp+57h+DistanceToMoveHigh], xmm0
0x180029125  mov     rax, [rax+28h]
0x180029129  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002912e  test    eax, eax
0x180029130  js      short loc_180029148
0x180029132  movsd   xmm2, qword ptr [rbp+57h+DistanceToMoveHigh]; double
0x180029137  mov     rcx, rdi; this
0x18002913a  movsd   xmm1, qword ptr [rbp+57h+NumberOfBytesWritten]; double
0x18002913f  call    ?SetResolution@CWmpEncoderFrame@@UEAAJNN@Z; CWmpEncoderFrame::SetResolution(double,double)
0x180029144  test    eax, eax
0x180029146  jns     short loc_180029160
0x180029148  mov     rax, 4058000000000000h
0x180029152  mov     [rdi-102D0h], rax
0x180029159  mov     [rdi-102D8h], rax
0x180029160  mov     eax, [rdi-102E4h]
0x180029166  test    eax, eax
0x180029168  jz      short loc_180029193
0x18002916a  mov     ecx, [rdi-102E0h]
0x180029170  test    ecx, ecx
0x180029172  jz      short loc_180029193
0x180029174  test    rsi, rsi
0x180029177  jnz     short loc_18002917F
0x180029179  lea     rsi, [rbp+57h+var_58]
0x18002917d  jmp     short loc_1800291EE
0x18002917f  cmp     [rsi+8], eax
0x180029182  jnz     short loc_180029189
0x180029184  cmp     [rsi+0Ch], ecx
0x180029187  jz      short loc_1800291EE
0x180029189  mov     ebx, 88982F49h
0x18002918e  jmp     loc_180029455
0x180029193  test    rsi, rsi
0x180029196  jnz     short loc_1800291D5
0x180029198  mov     rax, [r14]
0x18002919b  lea     r8, [rbp+57h+DistanceToMoveHigh]
0x18002919f  lea     rdx, [rbp+57h+NumberOfBytesWritten]
0x1800291a3  mov     [rbp+57h+NumberOfBytesWritten], r12d
0x1800291a7  mov     rcx, r14
0x1800291aa  mov     [rbp+57h+DistanceToMoveHigh], r12d
0x1800291ae  mov     rax, [rax+18h]
0x1800291b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800291b7  mov     ebx, eax
0x1800291b9  test    eax, eax
0x1800291bb  js      loc_180029455
0x1800291c1  mov     eax, [rbp+57h+NumberOfBytesWritten]
0x1800291c4  lea     rsi, [rbp+57h+var_58]
0x1800291c8  mov     [rbp+57h+var_50], eax
0x1800291cb  mov     eax, [rbp+57h+DistanceToMoveHigh]
0x1800291ce  mov     [rbp+57h+var_4C], eax
0x1800291d1  mov     [rbp+57h+var_58], r12
0x1800291d5  mov     r8d, [rsi+0Ch]; unsigned int
0x1800291d9  mov     rcx, rdi; this
0x1800291dc  mov     edx, [rsi+8]; unsigned int
0x1800291df  call    ?SetSize@CWmpEncoderFrame@@UEAAJII@Z; CWmpEncoderFrame::SetSize(uint,uint)
0x1800291e4  mov     ebx, eax
0x1800291e6  test    eax, eax
0x1800291e8  js      loc_180029455
0x1800291ee  cmp     [rdi+74h], r12d
0x1800291f2  jz      loc_1800292DD
0x1800291f8  mov     rax, [r14]
0x1800291fb  lea     r8, [rbp+57h+var_90]
0x1800291ff  lea     rdx, IID_IWMPhotoElementaryStream
0x180029206  mov     rcx, r14
0x180029209  mov     rax, [rax]
0x18002920c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029211  test    eax, eax
0x180029213  js      loc_1800292DD
0x180029219  mov     rcx, [rbp+57h+var_90]
0x18002921d  lea     rdx, [rbp+57h+var_88]
0x180029221  mov     rax, [rcx]
0x180029224  mov     rax, [rax+18h]
0x180029228  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002922d  test    eax, eax
0x18002922f  js      loc_1800292DD
0x180029235  mov     rax, [rdi-10330h]
0x18002923c  mov     [rbp+57h+var_A0], 1
0x180029243  sub     rax, [rbp+57h+var_88]
0x180029247  jnz     short loc_180029254
0x180029249  mov     rax, [rdi-10328h]
0x180029250  sub     rax, [rbp+57h+var_80]
0x180029254  test    rax, rax
0x180029257  jnz     loc_1800292DD
0x18002925d  cmp     dword ptr [rdi-10338h], 2
0x180029264  jnz     short loc_1800292D3
0x180029266  mov     eax, [rdi-102E0h]
0x18002926c  cmp     [rsi+0Ch], eax
0x18002926f  jnz     loc_180029189
0x180029275  movzx   eax, byte ptr [rdi+58h]
0x180029279  lea     r9, [rbp+57h+var_64]
0x18002927d  mov     ecx, [rbp+57h+var_60]
0x180029280  lea     r8, [rbp+57h+var_74+0Ch]
0x180029284  mov     [rbp+57h+DistanceToMoveHigh], eax
0x180029287  mov     rdx, rsi
0x18002928a  lea     rax, [rbp+57h+DistanceToMoveHigh]
0x18002928e  mov     [rsp+100h+lpOverlapped], rax
0x180029293  call    ?TransformConsolidate@@YAJW4ORIENTATION@@PEAUWICRect@@PEAI2PEAW41@@Z; TransformConsolidate(ORIENTATION,WICRect *,uint *,uint *,ORIENTATION *)
0x180029298  mov     ebx, eax
0x18002929a  test    eax, eax
0x18002929c  js      loc_180029455
0x1800292a2  mov     al, byte ptr [rbp+57h+DistanceToMoveHigh]
0x1800292a5  lea     rdx, [rbp+57h+var_88]
0x1800292a9  xor     r9d, r9d
0x1800292ac  mov     [rdi+58h], al
0x1800292af  mov     r8, rsi
0x1800292b2  mov     rcx, r13
0x1800292b5  call    ?HrEncodeStream@CWmpEncoderFrame@@MEAAJPEAUtagWMPhotoElementaryStreamInfo@@PEAUWICRect@@W4ORIENTATION@@@Z; CWmpEncoderFrame::HrEncodeStream(tagWMPhotoElementaryStreamInfo *,WICRect *,ORIENTATION)
0x1800292ba  mov     ebx, eax
0x1800292bc  test    eax, eax
0x1800292be  js      loc_180029455
0x1800292c4  mov     dword ptr [rdi-10338h], 4
0x1800292ce  jmp     loc_180029455
0x1800292d3  mov     ebx, 88982F04h
0x1800292d8  jmp     loc_180029455
0x1800292dd  mov     eax, [rdi+10h]
0x1800292e0  add     eax, [rsi+0Ch]
0x1800292e3  cmp     eax, [rdi-102E0h]
0x1800292e9  ja      loc_180029613
0x1800292ef  mov     rax, [r14]
0x1800292f2  lea     rdx, [rbp+57h+var_48]
0x1800292f6  xorps   xmm0, xmm0
0x1800292f9  mov     rcx, r14
0x1800292fc  movups  xmmword ptr [rbp+57h+var_48.Data1], xmm0
0x180029300  mov     rax, [rax+20h]
0x180029304  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029309  mov     ebx, eax
0x18002930b  test    eax, eax
0x18002930d  js      loc_180029455
0x180029313  mov     rax, qword ptr cs:GUID_WICPixelFormatDontCare.Data1
0x18002931a  lea     r15, [rdi-10330h]
0x180029321  sub     rax, [r15]
0x180029324  jnz     short loc_180029331
0x180029326  mov     rax, qword ptr cs:GUID_WICPixelFormatDontCare.Data4
0x18002932d  sub     rax, [r15+8]
0x180029331  test    rax, rax
0x180029334  jnz     short loc_18002934C
0x180029336  lea     rdx, [rbp+57h+var_48]; struct _GUID *
0x18002933a  mov     rcx, rdi; this
0x18002933d  call    ?SetPixelFormat@CWmpEncoderFrame@@UEAAJPEAU_GUID@@@Z; CWmpEncoderFrame::SetPixelFormat(_GUID *)
0x180029342  mov     ebx, eax
0x180029344  test    eax, eax
0x180029346  js      loc_180029451
0x18002934c  mov     rax, [r15]
0x18002934f  sub     rax, qword ptr [rbp+57h+var_48.Data1]
0x180029353  jnz     short loc_18002935D
0x180029355  mov     rax, [r15+8]
0x180029359  sub     rax, qword ptr [rbp+57h+var_48.Data4]
0x18002935d  test    rax, rax
0x180029360  jnz     short loc_18002936A
0x180029362  mov     rax, [r14]
0x180029365  mov     rcx, r14
0x180029368  jmp     short loc_1800293CC
0x18002936a  call    ?GetWICFactory@@YAPEAUIWICComponentFactory@@XZ; GetWICFactory(void)
0x18002936f  mov     r8, rax
0x180029372  lea     rdx, [rbp+57h+var_98]
0x180029376  mov     rcx, [rax]
0x180029379  mov     rax, [rcx+50h]
0x18002937d  mov     rcx, r8
0x180029380  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029385  mov     ebx, eax
0x180029387  test    eax, eax
0x180029389  js      loc_180029451
0x18002938f  mov     rcx, [rbp+57h+var_98]
0x180029393  xorps   xmm0, xmm0
0x180029396  mov     [rsp+100h+var_D0], r12d
0x18002939b  xor     r9d, r9d
0x18002939e  movsd   [rsp+100h+var_D8], xmm0
0x1800293a4  mov     r8, r15
0x1800293a7  mov     rdx, r14
0x1800293aa  mov     [rsp+100h+lpOverlapped], r12
0x1800293af  mov     rax, [rcx]
0x1800293b2  mov     rax, [rax+40h]
0x1800293b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800293bb  mov     ebx, eax
0x1800293bd  test    eax, eax
0x1800293bf  js      loc_180029451
0x1800293c5  mov     rcx, [rbp+57h+var_98]
0x1800293c9  mov     rax, [rcx]
0x1800293cc  mov     rax, [rax]
0x1800293cf  lea     r8, [rbp+57h+var_A8]
0x1800293d3  lea     rdx, IID_IWICBitmapSource
0x1800293da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800293df  mov     ebx, eax
0x1800293e1  test    eax, eax
0x1800293e3  js      short loc_180029451
0x1800293e5  mov     rcx, r13; this
0x1800293e8  call    ?HrAllocateFrameBuffer@CWmpEncoderFrame@@MEAAJXZ; CWmpEncoderFrame::HrAllocateFrameBuffer(void)
0x1800293ed  mov     ebx, eax
0x1800293ef  test    eax, eax
0x1800293f1  js      short loc_180029451
0x1800293f3  mov     edx, [rdi+10h]
0x1800293f6  imul    rdx, [rdi-40h]; lDistanceToMove
0x1800293fb  mov     rcx, [rdi+0C0h]; hFile
0x180029402  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180029406  jz      loc_1800295CC
0x18002940c  movsxd  r15, dword ptr [rsi+0Ch]
0x180029410  lea     r8, [rbp+57h+DistanceToMoveHigh]; lpDistanceToMoveHigh
0x180029414  mov     r12d, [rsi+4]
0x180029418  mov     rax, rdx
0x18002941b  sar     rax, 20h
0x18002941f  xor     r9d, r9d; dwMoveMethod
0x180029422  mov     [rbp+57h+DistanceToMoveHigh], eax
0x180029425  call    cs:__imp_SetFilePointer
0x18002942c  nop     dword ptr [rax+rax+00h]
0x180029431  cmp     eax, 0FFFFFFFFh
0x180029434  jnz     loc_180029521
0x18002943a  call    cs:__imp_GetLastError
0x180029441  nop     dword ptr [rax+rax+00h]
0x180029446  test    eax, eax
0x180029448  jz      loc_180029521
0x18002944e  or      ebx, 0FFFFFFFFh
0x180029451  mov     r15, [rbp+57h+var_C0]
0x180029455  mov     rcx, [rbp+57h+var_98]
0x180029459  xor     edi, edi
0x18002945b  test    rcx, rcx
0x18002945e  jz      short loc_180029470
0x180029460  mov     rax, [rcx]
0x180029463  mov     rax, [rax+10h]
0x180029467  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002946c  mov     [rbp+57h+var_98], rdi
0x180029470  mov     rcx, [rbp+57h+var_A8]
0x180029474  test    rcx, rcx
0x180029477  jz      short loc_180029489
0x180029479  mov     rax, [rcx]
0x18002947c  mov     rax, [rax+10h]
0x180029480  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029485  mov     [rbp+57h+var_A8], rdi
0x180029489  cmp     [rbp+57h+var_A0], edi
0x18002948c  jz      short loc_1800294C0
0x18002948e  mov     rcx, [rbp-21h]
0x180029492  test    rcx, rcx
0x180029495  jz      short loc_1800294A7
0x180029497  mov     rax, [rcx]
0x18002949a  mov     rax, [rax+10h]
0x18002949e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800294a3  mov     [rbp-21h], rdi
0x1800294a7  mov     rcx, qword ptr [rbp+57h+var_74+4]
0x1800294ab  test    rcx, rcx
0x1800294ae  jz      short loc_1800294C0
0x1800294b0  mov     rax, [rcx]
0x1800294b3  mov     rax, [rax+10h]
0x1800294b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800294bc  mov     qword ptr [rbp+57h+var_74+4], rdi
0x1800294c0  mov     rcx, [rbp+57h+var_90]
0x1800294c4  test    rcx, rcx
  ... truncated ...
```
