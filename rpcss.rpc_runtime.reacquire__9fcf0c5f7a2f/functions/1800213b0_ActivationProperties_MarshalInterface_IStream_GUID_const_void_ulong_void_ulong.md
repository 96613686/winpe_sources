# ActivationProperties::MarshalInterface(IStream *,_GUID const &,void *,ulong,void *,ulong)

- ea: `0x1800213b0`
- end: `0x180021a6d`
- name: `?MarshalInterface@ActivationProperties@@UEAAJPEAUIStream@@AEBU_GUID@@PEAXK2K@Z`
- size: `1725`
- prototype: `__int64 __fastcall(ActivationProperties *__hidden this, struct IStream *, const struct _GUID *, void *, unsigned int, void *, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1800213b0`
- `0x180021a74`
- `0x180054ed0`
- `0x180112d84`
- `0x180114010`

## import_xrefs

- `RPCRT4!MesEncodeFixedBufferHandleCreate` at `0x18002176a`
- `RPCRT4!MesEncodeFixedBufferHandleCreate` at `0x180021875`
- `RPCRT4!MesEncodeFixedBufferHandleCreate` at `0x18002176a`
- `RPCRT4!MesEncodeFixedBufferHandleCreate` at `0x180021875`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x18002159c`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x1800216d5`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x18002159c`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x1800216d5`
- `RPCRT4!NdrMesTypeEncode2` at `0x180021529`
- `RPCRT4!NdrMesTypeEncode2` at `0x180021529`
- `RPCRT4!RpcExceptionFilter` at `0x180112eee`
- `RPCRT4!RpcExceptionFilter` at `0x180112eee`
- `RPCRT4!MesHandleFree` at `0x180021566`
- `RPCRT4!MesHandleFree` at `0x1800216a3`
- `RPCRT4!MesHandleFree` at `0x1800219ed`
- `RPCRT4!MesHandleFree` at `0x180021566`
- `RPCRT4!MesHandleFree` at `0x1800216a3`
- `RPCRT4!MesHandleFree` at `0x1800219ed`

## pseudocode

```c
__int64 __fastcall ActivationProperties::MarshalInterface(
        ActivationProperties *this,
        struct IStream *a2,
        const struct _GUID *a3,
        void *a4,
        unsigned int a5)
{
  __int64 result; // rax
  int v8; // r14d
  __int64 v9; // rdx
  int inited; // esi
  __int64 v11; // r8
  unsigned int v12; // edi
  unsigned int v13; // ecx
  RPC_STATUS v14; // eax
  unsigned int v15; // r12d
  unsigned int v16; // edi
  unsigned int v17; // r13d
  unsigned int v18; // r9d
  unsigned __int64 v19; // rsi
  __int64 v20; // rcx
  unsigned int v21; // eax
  unsigned int v22; // esi
  signed int v23; // ecx
  RPC_STATUS v24; // eax
  __int64 v25; // rcx
  __int64 v26; // rcx
  unsigned int v27; // eax
  bool v28; // zf
  __int64 v29; // r10
  __int64 v30; // rax
  __int128 v31; // [rsp+30h] [rbp-B8h] BYREF
  __int64 v32; // [rsp+40h] [rbp-A8h]
  __int64 v33; // [rsp+48h] [rbp-A0h]
  unsigned int pEncodedSize; // [rsp+50h] [rbp-98h] BYREF
  __int64 v35; // [rsp+54h] [rbp-94h]
  handle_t Handle; // [rsp+60h] [rbp-88h] BYREF
  int v37; // [rsp+68h] [rbp-80h]
  int v38; // [rsp+6Ch] [rbp-7Ch]
  __int64 v39; // [rsp+70h] [rbp-78h]
  int v40; // [rsp+78h] [rbp-70h]
  unsigned int v41; // [rsp+7Ch] [rbp-6Ch]
  int v42; // [rsp+80h] [rbp-68h]
  unsigned int v43; // [rsp+90h] [rbp-58h]
  int v44; // [rsp+94h] [rbp-54h]
  void *v45; // [rsp+98h] [rbp-50h] BYREF
  unsigned int v46; // [rsp+A0h] [rbp-48h]
  int v47; // [rsp+A4h] [rbp-44h]
  unsigned __int64 v48; // [rsp+A8h] [rbp-40h]
  __int64 v49; // [rsp+B0h] [rbp-38h] BYREF

  v49 = 0;
  result = (**(__int64 (__fastcall ***)(ActivationProperties *, const struct _GUID *, __int64 *))this)(this, a3, &v49);
  if ( (int)result < 0 )
    return result;
  v8 = 1;
  v44 = 1;
  v35 = 0;
  v33 = 0;
  pEncodedSize = 0;
  v39 = 0;
  v31 = 0;
  v32 = 0;
  Handle = 0;
  v37 = 1;
  v40 = *((_DWORD *)this + 17);
  v41 = a5;
  v42 = *((_DWORD *)this + 46);
  v45 = 0;
  if ( a5 - 3 > 1 )
  {
    v45 = 0;
  }
  else
  {
    v45 = this;
    v8 = 0;
    v44 = 0;
  }
  inited = Serializer::InitStream((Serializer *)&v31, a2, (unsigned int *)this + 14, 2u, &v45);
  v43 = inited;
  if ( inited < 0 )
  {
    if ( v8 )
      (*(void (__fastcall **)(ActivationProperties *))(*(_QWORD *)this + 16LL))(this);
    Serializer::~Serializer((Serializer *)&v31);
    return (unsigned int)inited;
  }
  if ( v45 && !*((_DWORD *)this + 50) )
  {
    v17 = 0;
    v43 = 0;
    goto LABEL_85;
  }
  v48 = 0;
  if ( *((_DWORD *)this + 76) >= 0xCu )
    goto LABEL_68;
  if ( HIDWORD(v35) > (unsigned int)v35 )
    goto LABEL_68;
  if ( (unsigned int)v39 > HIDWORD(v35) )
    goto LABEL_68;
  v48 = (unsigned int)(HIDWORD(v35) - v39);
  if ( v48 < *((unsigned int *)this + 137) )
    goto LABEL_68;
  NdrMesTypeEncode2(Handle, &pPicklingInfo, &pStubDesc, &pFormatString, (char *)this + 56);
  v12 = v39 + *((_DWORD *)this + 137);
  v13 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v32 + 56LL))(v32, (unsigned int)v35, v12);
  if ( v13 )
    goto LABEL_66;
  MesHandleFree(Handle);
  Handle = 0;
  v9 = HIDWORD(v35);
  if ( HIDWORD(v35) < v12 )
    goto LABEL_68;
  if ( v38 == 1 )
  {
    v14 = MesDecodeBufferHandleCreate((char *)(v33 + v12), HIDWORD(v35) - v12, &Handle);
  }
  else
  {
    pEncodedSize = 0;
    if ( HIDWORD(v35) == v12 )
    {
      LODWORD(v39) = v12;
      goto LABEL_68;
    }
    v14 = MesEncodeFixedBufferHandleCreate((char *)(v33 + v12), HIDWORD(v35) - v12, &pEncodedSize, &Handle);
  }
  v13 = v14;
  if ( v14 )
  {
    if ( (v14 & 0x1FFF0000) != 0x10000 )
    {
      v28 = v14 == 0;
      if ( v14 <= 0 )
        goto LABEL_67;
      v13 = (unsigned __int16)v14 | 0x80070000;
    }
LABEL_66:
    v28 = v13 == 0;
LABEL_67:
    if ( v28 )
      goto LABEL_17;
LABEL_68:
    v17 = -2147024809;
    goto LABEL_53;
  }
  if ( !Handle )
    goto LABEL_68;
  LODWORD(v39) = v12;
LABEL_17:
  v15 = *((_DWORD *)this + 31);
  v46 = v15;
  v16 = 0;
  v47 = 0;
  v17 = -2147024809;
  v9 = HIDWORD(v35);
  v18 = v35;
  while ( v16 < *((_DWORD *)this + 76) )
  {
    v19 = *((unsigned int *)this + v16 + 125);
    if ( !(_DWORD)v19 )
      goto LABEL_41;
    if ( (unsigned int)v9 > v18 )
      goto LABEL_53;
    if ( (unsigned int)v39 > (unsigned int)v9 )
      goto LABEL_53;
    v48 = (unsigned int)(v9 - v39);
    v11 = (unsigned int)v19;
    if ( v48 < v19 )
      goto LABEL_53;
    if ( *((_DWORD *)this + 11) && !*((_QWORD *)this + v16 + 26) )
    {
      v26 = *((_QWORD *)this + 69);
      v27 = *(_DWORD *)(v26 + 36);
      if ( v15 >= v27 )
      {
        v23 = -2147024809;
        goto LABEL_36;
      }
      if ( (unsigned int)v19 > v27 - v15 )
      {
        v23 = -2147467259;
        goto LABEL_36;
      }
      if ( (unsigned int)v19 > v18 - (unsigned int)v39 )
      {
        v23 = -2147467259;
        goto LABEL_36;
      }
      memcpy_0((void *)(v33 + (unsigned int)v39), (const void *)(*(_QWORD *)(v26 + 24) + v15), (unsigned int)v19);
    }
    else
    {
      v20 = *((_QWORD *)this + v16 + 26);
      v21 = (*(__int64 (__fastcall **)(__int64, __int128 *, _QWORD))(*(_QWORD *)v20 + 24LL))(
              v20,
              &v31,
              (unsigned int)v19);
      if ( v21 )
      {
        v17 = v21;
        v43 = v21;
        goto LABEL_85;
      }
      LODWORD(v19) = *((_DWORD *)this + v16 + 125);
    }
    v22 = v39 + v19;
    v23 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v32 + 56LL))(v32, (unsigned int)v35, v22);
    if ( !v23 )
    {
      MesHandleFree(Handle);
      Handle = 0;
      v9 = HIDWORD(v35);
      if ( HIDWORD(v35) < v22 )
      {
        v23 = -2147024809;
        goto LABEL_35;
      }
      if ( v38 == 1 )
      {
        v24 = MesDecodeBufferHandleCreate((char *)(v33 + v22), HIDWORD(v35) - v22, &Handle);
      }
      else
      {
        pEncodedSize = 0;
        if ( HIDWORD(v35) == v22 )
        {
          LODWORD(v39) = v22;
          v23 = 1;
          goto LABEL_35;
        }
        v24 = MesEncodeFixedBufferHandleCreate((char *)(v33 + v22), HIDWORD(v35) - v22, &pEncodedSize, &Handle);
      }
      v23 = v24;
      if ( v24 )
      {
        if ( (v24 & 0x1FFF0000) != 0x10000 && v24 > 0 )
          v23 = (unsigned __int16)v24 | 0x80070000;
      }
      else if ( Handle )
      {
        v23 = 0;
        LODWORD(v39) = v22;
      }
      else
      {
        v23 = -2147024882;
      }
    }
    v9 = HIDWORD(v35);
LABEL_35:
    v18 = v35;
LABEL_36:
    if ( v23 < 0 )
    {
      v17 = v23;
      goto LABEL_53;
    }
    if ( v23 == 1 && v16 != *((_DWORD *)this + 76) - 1 )
      goto LABEL_53;
    if ( *((_DWORD *)this + 11) )
    {
      if ( v16 < *((_DWORD *)this + 34) )
      {
        v15 += *(_DWORD *)(*((_QWORD *)this + 21) + 4LL * v16);
        v46 = v15;
      }
    }
LABEL_41:
    v47 = ++v16;
  }
  v25 = *((_QWORD *)&v31 + 1);
  if ( *((_QWORD *)&v31 + 1) && *((_QWORD *)&v31 + 1) != (_QWORD)v31 )
  {
    v29 = v33;
    while ( 1 )
    {
      pEncodedSize = 0;
      v17 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, unsigned int *))(*(_QWORD *)v25 + 32LL))(
              v25,
              v29,
              (unsigned int)v9,
              &pEncodedSize);
      if ( v17 )
        break;
      v9 = HIDWORD(v35) - pEncodedSize;
      HIDWORD(v35) = v9;
      v29 = pEncodedSize + v33;
      v33 = v29;
      if ( !(_DWORD)v9 )
        break;
      v25 = *((_QWORD *)&v31 + 1);
    }
  }
  else
  {
    v17 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v32 + 56LL))(v32, v18, (unsigned int)v9);
  }
LABEL_53:
  v43 = v17;
LABEL_85:
  *((_DWORD *)this + 6) = 3;
  if ( v44 )
    (*(void (__fastcall **)(ActivationProperties *, __int64, __int64))(*(_QWORD *)this + 16LL))(this, v9, v11);
  if ( Handle )
  {
    MesHandleFree(Handle);
    Handle = 0;
  }
  v30 = v31;
  if ( (_QWORD)v31 )
  {
    (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v32 + 16LL))(v32, v9, v11);
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v31 + 16LL))(v31);
    v30 = v31;
  }
  if ( *((_QWORD *)&v31 + 1) && *((_QWORD *)&v31 + 1) != v30 )
    (*(void (__fastcall **)(_QWORD, _QWORD, __int64))(**((_QWORD **)&v31 + 1) + 16LL))(
      *((_QWORD *)&v31 + 1),
      **((_QWORD **)&v31 + 1),
      v11);
  return v17;
}

```

## disassembly

```asm
0x1800213b0  mov     r11, rsp
0x1800213b3  mov     [r11+10h], rbx
0x1800213b7  mov     [r11+18h], rsi
0x1800213bb  mov     [r11+8], rcx
0x1800213bf  push    rdi
0x1800213c0  push    r12
0x1800213c2  push    r13
0x1800213c4  push    r14
0x1800213c6  push    r15
0x1800213c8  sub     rsp, 0C0h
0x1800213cf  mov     r9, r8
0x1800213d2  mov     rsi, rdx
0x1800213d5  mov     rbx, rcx
0x1800213d8  xor     r15d, r15d
0x1800213db  mov     [r11-38h], r15
0x1800213df  mov     rax, [rcx]
0x1800213e2  lea     r8, [r11-38h]
0x1800213e6  mov     rdx, r9
0x1800213e9  mov     rax, [rax]
0x1800213ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800213f1  test    eax, eax
0x1800213f3  js      loc_180021A3C
0x1800213f9  mov     r14d, 1
0x1800213ff  mov     [rsp+0E8h+var_54], r14d
0x180021407  lea     rdi, [rbx+38h]
0x18002140b  mov     [rsp+0E8h+var_94], r15
0x180021410  mov     [rsp+0E8h+var_A0], r15
0x180021415  mov     [rsp+0E8h+pEncodedSize], r15d
0x18002141a  mov     [rsp+0E8h+var_78], r15
0x18002141f  xorps   xmm0, xmm0
0x180021422  movdqa  [rsp+0E8h+var_B8], xmm0
0x180021428  mov     [rsp+0E8h+var_A8], r15
0x18002142d  mov     [rsp+0E8h+Handle], r15
0x180021432  mov     [rsp+0E8h+var_80], r14d
0x180021437  mov     eax, [rdi+0Ch]
0x18002143a  mov     [rsp+0E8h+var_70], eax
0x18002143e  mov     ecx, [rsp+0E8h+arg_20]
0x180021445  mov     [rsp+0E8h+var_6C], ecx
0x180021449  mov     eax, [rbx+0B8h]
0x18002144f  mov     [rsp+0E8h+var_68], eax
0x180021456  mov     [rsp+0E8h+var_50], r15
0x18002145e  lea     eax, [rcx-3]
0x180021461  cmp     eax, r14d
0x180021464  ja      loc_180021941
0x18002146a  mov     [rsp+0E8h+var_50], rbx
0x180021472  mov     r14d, r15d
0x180021475  mov     [rsp+0E8h+var_54], r15d
0x18002147d  lea     rax, [rsp+0E8h+var_50]
0x180021485  mov     [rsp+0E8h+pObject], rax; void **
0x18002148a  mov     r9d, 2; unsigned int
0x180021490  mov     r8, rdi; unsigned int *
0x180021493  mov     rdx, rsi; struct IStream *
0x180021496  lea     rcx, [rsp+0E8h+var_B8]; this
0x18002149b  call    ?InitStream@Serializer@@QEAAJPEAUIStream@@AEAKKAEAPEAX@Z; Serializer::InitStream(IStream *,ulong &,ulong,void * &)
0x1800214a0  mov     esi, eax
0x1800214a2  mov     [rsp+0E8h+var_58], eax
0x1800214a9  test    eax, eax
0x1800214ab  js      loc_1800218BE
0x1800214b1  cmp     [rsp+0E8h+var_50], 0
0x1800214ba  jnz     loc_180021962
0x1800214c0  mov     [rsp+0E8h+var_40], r15
0x1800214c8  cmp     dword ptr [rbx+130h], 0Ch
0x1800214cf  jnb     loc_1800218A9
0x1800214d5  mov     eax, dword ptr [rsp+0E8h+var_94+4]
0x1800214d9  cmp     eax, dword ptr [rsp+0E8h+var_94]
0x1800214dd  ja      loc_1800218A9
0x1800214e3  mov     ecx, dword ptr [rsp+0E8h+var_78]
0x1800214e7  cmp     ecx, eax
0x1800214e9  ja      loc_1800218A9
0x1800214ef  sub     eax, ecx
0x1800214f1  mov     ecx, eax
0x1800214f3  mov     [rsp+0E8h+var_40], rcx
0x1800214fb  mov     eax, [rbx+224h]
0x180021501  cmp     rcx, rax
0x180021504  jb      loc_1800218A9
0x18002150a  mov     [rsp+0E8h+pObject], rdi; pObject
0x18002150f  lea     r9, pFormatString; pFormatString
0x180021516  lea     r8, pStubDesc; pStubDesc
0x18002151d  lea     rdx, pPicklingInfo; pPicklingInfo
0x180021524  mov     rcx, [rsp+0E8h+Handle]; Handle
0x180021529  call    cs:__imp_NdrMesTypeEncode2
0x180021530  nop     dword ptr [rax+rax+00h]
0x180021535  mov     edi, [rbx+224h]
0x18002153b  add     edi, dword ptr [rsp+0E8h+var_78]
0x18002153f  mov     rcx, [rsp+0E8h+var_A8]
0x180021544  mov     rax, [rcx]
0x180021547  mov     r8d, edi
0x18002154a  mov     edx, dword ptr [rsp+0E8h+var_94]
0x18002154e  mov     rax, [rax+38h]
0x180021552  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021557  mov     ecx, eax
0x180021559  test    eax, eax
0x18002155b  jnz     loc_1800218A1
0x180021561  mov     rcx, [rsp+0E8h+Handle]; Handle
0x180021566  call    cs:__imp_MesHandleFree
0x18002156d  nop     dword ptr [rax+rax+00h]
0x180021572  mov     [rsp+0E8h+Handle], r15
0x180021577  mov     edx, dword ptr [rsp+0E8h+var_94+4]
0x18002157b  cmp     edx, edi
0x18002157d  jb      loc_1800218A9
0x180021583  cmp     [rsp+0E8h+var_7C], 1
0x180021588  jnz     loc_180021855
0x18002158e  sub     edx, edi; BufferSize
0x180021590  mov     ecx, edi
0x180021592  add     rcx, [rsp+0E8h+var_A0]; Buffer
0x180021597  lea     r8, [rsp+0E8h+Handle]; pHandle
0x18002159c  call    cs:__imp_MesDecodeBufferHandleCreate
0x1800215a3  nop     dword ptr [rax+rax+00h]
0x1800215a8  mov     ecx, eax
0x1800215aa  test    eax, eax
0x1800215ac  jnz     loc_180021886
0x1800215b2  cmp     [rsp+0E8h+Handle], 0
0x1800215b8  jz      loc_1800218A9
0x1800215be  mov     dword ptr [rsp+0E8h+var_78], edi
0x1800215c2  mov     r12d, [rbx+7Ch]
0x1800215c6  mov     [rsp+0E8h+var_48], r12d
0x1800215ce  mov     edi, r15d
0x1800215d1  mov     [rsp+0E8h+var_44], r15d
0x1800215d9  mov     r13d, 80070057h
0x1800215df  mov     edx, dword ptr [rsp+0E8h+var_94+4]
0x1800215e3  mov     r9d, dword ptr [rsp+0E8h+var_94]
0x1800215e8  nop     dword ptr [rax+rax+00000000h]
0x1800215f0  cmp     edi, [rbx+130h]
0x1800215f6  jnb     loc_1800217B1
0x1800215fc  mov     r14d, edi
0x1800215ff  mov     esi, [rbx+r14*4+1F4h]
0x180021607  test    esi, esi
0x180021609  jz      loc_180021985
0x18002160f  cmp     edx, r9d
0x180021612  ja      loc_1800217E0
0x180021618  mov     ecx, dword ptr [rsp+0E8h+var_78]
0x18002161c  cmp     ecx, edx
0x18002161e  ja      loc_1800217E0
0x180021624  mov     eax, edx
0x180021626  sub     eax, ecx
0x180021628  mov     ecx, eax
0x18002162a  mov     [rsp+0E8h+var_40], rcx
0x180021632  mov     r8d, esi; Size
0x180021635  cmp     rcx, rsi
0x180021638  jb      loc_1800217E0
0x18002163e  cmp     dword ptr [rbx+2Ch], 0
0x180021642  jz      short loc_180021653
0x180021644  cmp     qword ptr [rbx+r14*8+0D0h], 0
0x18002164d  jz      loc_1800217ED
0x180021653  mov     rcx, [rbx+r14*8+0D0h]
0x18002165b  mov     rax, [rcx]
0x18002165e  lea     rdx, [rsp+0E8h+var_B8]
0x180021663  mov     rax, [rax+18h]
0x180021667  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002166c  test    eax, eax
0x18002166e  jnz     loc_18002183E
0x180021674  mov     esi, [rbx+r14*4+1F4h]
0x18002167c  add     esi, dword ptr [rsp+0E8h+var_78]
0x180021680  mov     rcx, [rsp+0E8h+var_A8]
0x180021685  mov     rax, [rcx]
0x180021688  mov     r8d, esi
0x18002168b  mov     edx, dword ptr [rsp+0E8h+var_94]
0x18002168f  mov     rax, [rax+38h]
0x180021693  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021698  mov     ecx, eax
0x18002169a  test    eax, eax
0x18002169c  jnz     short loc_1800216FE
0x18002169e  mov     rcx, [rsp+0E8h+Handle]; Handle
0x1800216a3  call    cs:__imp_MesHandleFree
0x1800216aa  nop     dword ptr [rax+rax+00h]
0x1800216af  mov     [rsp+0E8h+Handle], r15
0x1800216b4  mov     edx, dword ptr [rsp+0E8h+var_94+4]
0x1800216b8  cmp     edx, esi
0x1800216ba  jb      loc_18002184D
0x1800216c0  cmp     [rsp+0E8h+var_7C], 1
0x1800216c5  jnz     short loc_180021743
0x1800216c7  sub     edx, esi; BufferSize
0x1800216c9  mov     ecx, esi
0x1800216cb  add     rcx, [rsp+0E8h+var_A0]; Buffer
0x1800216d0  lea     r8, [rsp+0E8h+Handle]; pHandle
0x1800216d5  call    cs:__imp_MesDecodeBufferHandleCreate
0x1800216dc  nop     dword ptr [rax+rax+00h]
0x1800216e1  mov     ecx, eax
0x1800216e3  test    eax, eax
0x1800216e5  jnz     loc_180021789
0x1800216eb  cmp     [rsp+0E8h+Handle], 0
0x1800216f1  jz      loc_180021834
0x1800216f7  mov     ecx, r15d
0x1800216fa  mov     dword ptr [rsp+0E8h+var_78], esi
0x1800216fe  mov     edx, dword ptr [rsp+0E8h+var_94+4]
0x180021702  mov     r9d, dword ptr [rsp+0E8h+var_94]
0x180021707  test    ecx, ecx
0x180021709  js      loc_180021994
0x18002170f  cmp     ecx, 1
0x180021712  jz      short loc_18002177B
0x180021714  cmp     dword ptr [rbx+2Ch], 0
0x180021718  jz      short loc_180021735
0x18002171a  cmp     edi, [rbx+88h]
0x180021720  jnb     short loc_180021735
0x180021722  mov     rax, [rbx+0A8h]
0x180021729  add     r12d, [rax+r14*4]
0x18002172d  mov     [rsp+0E8h+var_48], r12d
0x180021735  inc     edi
0x180021737  mov     [rsp+0E8h+var_44], edi
0x18002173e  jmp     loc_1800215F0
0x180021743  mov     [rsp+0E8h+pEncodedSize], r15d
0x180021748  cmp     edx, esi
0x18002174a  jnz     short loc_180021757
0x18002174c  mov     dword ptr [rsp+0E8h+var_78], esi
0x180021750  mov     ecx, 1
0x180021755  jmp     short loc_180021702
0x180021757  sub     edx, esi; BufferSize
0x180021759  mov     ecx, esi
0x18002175b  add     rcx, [rsp+0E8h+var_A0]; pBuffer
0x180021760  lea     r9, [rsp+0E8h+Handle]; pHandle
0x180021765  lea     r8, [rsp+0E8h+pEncodedSize]; pEncodedSize
0x18002176a  call    cs:__imp_MesEncodeFixedBufferHandleCreate
0x180021771  nop     dword ptr [rax+rax+00h]
0x180021776  jmp     loc_1800216E1
0x18002177b  mov     eax, [rbx+130h]
0x180021781  dec     eax
0x180021783  cmp     edi, eax
0x180021785  jz      short loc_180021714
0x180021787  jmp     short loc_1800217E0
0x180021789  mov     eax, ecx
0x18002178b  and     eax, 1FFF0000h
0x180021790  cmp     eax, 10000h
0x180021795  jz      loc_1800216FE
0x18002179b  test    ecx, ecx
0x18002179d  jle     loc_1800216FE
0x1800217a3  movzx   ecx, cx
0x1800217a6  or      ecx, 80070000h
0x1800217ac  jmp     loc_1800216FE
0x1800217b1  mov     rcx, qword ptr [rsp+0E8h+var_B8+8]
0x1800217b6  test    rcx, rcx
0x1800217b9  jz      short loc_1800217C6
0x1800217bb  cmp     rcx, qword ptr [rsp+0E8h+var_B8]
0x1800217c0  jnz     loc_1800218E0
0x1800217c6  mov     rcx, [rsp+0E8h+var_A8]
0x1800217cb  mov     rax, [rcx]
0x1800217ce  mov     r8d, edx
0x1800217d1  mov     edx, r9d
0x1800217d4  mov     rax, [rax+38h]
0x1800217d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800217dd  mov     r13d, eax
0x1800217e0  mov     [rsp+0E8h+var_58], r13d
0x1800217e8  jmp     loc_18002199C
0x1800217ed  mov     rcx, [rbx+228h]
0x1800217f4  mov     eax, [rcx+24h]
0x1800217f7  cmp     r12d, eax
0x1800217fa  jnb     loc_1800218D8
0x180021800  sub     eax, r12d
0x180021803  cmp     esi, eax
0x180021805  ja      loc_1800218B4
0x18002180b  mov     eax, r9d
0x18002180e  sub     eax, dword ptr [rsp+0E8h+var_78]
0x180021812  cmp     esi, eax
0x180021814  ja      loc_18002198A
0x18002181a  mov     edx, r12d
0x18002181d  add     rdx, [rcx+18h]; Src
0x180021821  mov     ecx, dword ptr [rsp+0E8h+var_78]
0x180021825  add     rcx, [rsp+0E8h+var_A0]; void *
0x18002182a  call    memcpy_0
0x18002182f  jmp     loc_18002167C
0x180021834  mov     ecx, 8007000Eh
0x180021839  jmp     loc_1800216FE
0x18002183e  mov     r13d, eax
0x180021841  mov     [rsp+0E8h+var_58], eax
0x180021848  jmp     loc_18002199C
0x18002184d  mov     ecx, r13d
0x180021850  jmp     loc_180021702
0x180021855  mov     [rsp+0E8h+pEncodedSize], r15d
0x18002185a  cmp     edx, edi
0x18002185c  jz      loc_18002197C
0x180021862  sub     edx, edi; BufferSize
0x180021864  mov     ecx, edi
0x180021866  add     rcx, [rsp+0E8h+var_A0]; pBuffer
0x18002186b  lea     r9, [rsp+0E8h+Handle]; pHandle
0x180021870  lea     r8, [rsp+0E8h+pEncodedSize]; pEncodedSize
0x180021875  call    cs:__imp_MesEncodeFixedBufferHandleCreate
0x18002187c  nop     dword ptr [rax+rax+00h]
0x180021881  jmp     loc_1800215A8
0x180021886  mov     eax, ecx
0x180021888  and     eax, 1FFF0000h
0x18002188d  cmp     eax, 10000h
0x180021892  jz      short loc_1800218A1
0x180021894  test    ecx, ecx
0x180021896  jle     short loc_1800218A3
0x180021898  movzx   ecx, cx
0x18002189b  or      ecx, 80070000h
0x1800218a1  test    ecx, ecx
0x1800218a3  jz      loc_1800215C2
0x1800218a9  mov     r13d, 80070057h
0x1800218af  jmp     loc_1800217E0
0x1800218b4  mov     ecx, 80004005h
0x1800218b9  jmp     loc_180021707
0x1800218be  test    r14d, r14d
0x1800218c1  jnz     loc_18002194E
0x1800218c7  lea     rcx, [rsp+0E8h+var_B8]; this
0x1800218cc  call    ??1Serializer@@QEAA@XZ; Serializer::~Serializer(void)
0x1800218d1  mov     eax, esi
0x1800218d3  jmp     loc_180021A3C
0x1800218d8  mov     ecx, r13d
0x1800218db  jmp     loc_180021707
0x1800218e0  mov     r10, [rsp+0E8h+var_A0]
  ... truncated ...
```
