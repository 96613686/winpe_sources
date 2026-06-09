# ActivationProperties::MarshalInterface(IStream *,_GUID const &,void *,ulong,void *,ulong)

- ea: `0x18002bcd0`
- end: `0x18002c3b6`
- name: `?MarshalInterface@ActivationProperties@@UEAAJPEAUIStream@@AEBU_GUID@@PEAXK2K@Z`
- size: `1766`
- prototype: `__int64 __fastcall(ActivationProperties *this, struct IStream *, const struct _GUID *, void *, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18002bcd0`
- `0x18002c3bc`
- `0x18010a084`
- `0x18010b010`

## import_xrefs

- `RPCRT4!MesEncodeFixedBufferHandleCreate` at `0x18002c06e`
- `RPCRT4!MesEncodeFixedBufferHandleCreate` at `0x18002c173`
- `RPCRT4!MesEncodeFixedBufferHandleCreate` at `0x18002c06e`
- `RPCRT4!MesEncodeFixedBufferHandleCreate` at `0x18002c173`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x18002beb0`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x18002bfdf`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x18002beb0`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x18002bfdf`
- `RPCRT4!NdrMesTypeEncode2` at `0x18002be49`
- `RPCRT4!NdrMesTypeEncode2` at `0x18002be49`
- `RPCRT4!RpcExceptionFilter` at `0x18010a27e`
- `RPCRT4!RpcExceptionFilter` at `0x18010a27e`
- `RPCRT4!MesHandleFree` at `0x18002be80`
- `RPCRT4!MesHandleFree` at `0x18002bfb3`
- `RPCRT4!MesHandleFree` at `0x18002c1c9`
- `RPCRT4!MesHandleFree` at `0x18002c33d`
- `RPCRT4!MesHandleFree` at `0x18002be80`
- `RPCRT4!MesHandleFree` at `0x18002bfb3`
- `RPCRT4!MesHandleFree` at `0x18002c1c9`
- `RPCRT4!MesHandleFree` at `0x18002c33d`

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
  __int64 v29; // rax
  __int64 v30; // r10
  __int64 v31; // rax
  __int128 v32; // [rsp+30h] [rbp-B8h] BYREF
  __int64 v33; // [rsp+40h] [rbp-A8h]
  __int64 v34; // [rsp+48h] [rbp-A0h]
  unsigned int pEncodedSize; // [rsp+50h] [rbp-98h] BYREF
  __int64 v36; // [rsp+54h] [rbp-94h]
  handle_t Handle; // [rsp+60h] [rbp-88h] BYREF
  int v38; // [rsp+68h] [rbp-80h]
  int v39; // [rsp+6Ch] [rbp-7Ch]
  __int64 v40; // [rsp+70h] [rbp-78h]
  int v41; // [rsp+78h] [rbp-70h]
  unsigned int v42; // [rsp+7Ch] [rbp-6Ch]
  int v43; // [rsp+80h] [rbp-68h]
  unsigned int v44; // [rsp+90h] [rbp-58h]
  int v45; // [rsp+94h] [rbp-54h]
  void *v46; // [rsp+98h] [rbp-50h] BYREF
  unsigned int v47; // [rsp+A0h] [rbp-48h]
  int v48; // [rsp+A4h] [rbp-44h]
  unsigned __int64 v49; // [rsp+A8h] [rbp-40h]
  __int64 v50; // [rsp+B0h] [rbp-38h] BYREF

  v50 = 0;
  result = (**(__int64 (__fastcall ***)(ActivationProperties *, const struct _GUID *, __int64 *))this)(this, a3, &v50);
  if ( (int)result < 0 )
    return result;
  v8 = 1;
  v45 = 1;
  v36 = 0;
  v34 = 0;
  pEncodedSize = 0;
  v40 = 0;
  v32 = 0;
  v33 = 0;
  Handle = 0;
  v38 = 1;
  v41 = *((_DWORD *)this + 17);
  v42 = a5;
  v43 = *((_DWORD *)this + 46);
  v46 = 0;
  if ( a5 - 3 > 1 )
  {
    v46 = 0;
  }
  else
  {
    v46 = this;
    v8 = 0;
    v45 = 0;
  }
  inited = Serializer::InitStream((Serializer *)&v32, a2, (unsigned int *)this + 14, 2u, &v46);
  v44 = inited;
  if ( inited < 0 )
  {
    if ( v8 )
      (*(void (__fastcall **)(ActivationProperties *))(*(_QWORD *)this + 16LL))(this);
    if ( Handle )
    {
      MesHandleFree(Handle);
      Handle = 0;
    }
    v29 = v32;
    if ( (_QWORD)v32 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v32 + 16LL))(v32);
      v29 = v32;
    }
    if ( *((_QWORD *)&v32 + 1) && *((_QWORD *)&v32 + 1) != v29 )
      (*(void (**)(void))(**((_QWORD **)&v32 + 1) + 16LL))();
    return (unsigned int)inited;
  }
  if ( v46 && !*((_DWORD *)this + 50) )
  {
    v17 = 0;
    v44 = 0;
    goto LABEL_92;
  }
  v49 = 0;
  if ( *((_DWORD *)this + 76) >= 0xCu )
    goto LABEL_68;
  if ( HIDWORD(v36) > (unsigned int)v36 )
    goto LABEL_68;
  if ( (unsigned int)v40 > HIDWORD(v36) )
    goto LABEL_68;
  v49 = (unsigned int)(HIDWORD(v36) - v40);
  if ( v49 < *((unsigned int *)this + 137) )
    goto LABEL_68;
  NdrMesTypeEncode2(Handle, &pPicklingInfo, &pStubDesc, &pFormatString, (char *)this + 56);
  v12 = v40 + *((_DWORD *)this + 137);
  v13 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v33 + 56LL))(v33, (unsigned int)v36, v12);
  if ( v13 )
    goto LABEL_66;
  MesHandleFree(Handle);
  Handle = 0;
  v9 = HIDWORD(v36);
  if ( HIDWORD(v36) < v12 )
    goto LABEL_68;
  if ( v39 == 1 )
  {
    v14 = MesDecodeBufferHandleCreate((char *)(v34 + v12), HIDWORD(v36) - v12, &Handle);
  }
  else
  {
    pEncodedSize = 0;
    if ( HIDWORD(v36) == v12 )
    {
      LODWORD(v40) = v12;
      goto LABEL_68;
    }
    v14 = MesEncodeFixedBufferHandleCreate((char *)(v34 + v12), HIDWORD(v36) - v12, &pEncodedSize, &Handle);
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
  LODWORD(v40) = v12;
LABEL_17:
  v15 = *((_DWORD *)this + 31);
  v47 = v15;
  v16 = 0;
  v48 = 0;
  v17 = -2147024809;
  v9 = HIDWORD(v36);
  v18 = v36;
  while ( v16 < *((_DWORD *)this + 76) )
  {
    v19 = *((unsigned int *)this + v16 + 125);
    if ( !(_DWORD)v19 )
      goto LABEL_41;
    if ( (unsigned int)v9 > v18 )
      goto LABEL_53;
    if ( (unsigned int)v40 > (unsigned int)v9 )
      goto LABEL_53;
    v49 = (unsigned int)(v9 - v40);
    v11 = (unsigned int)v19;
    if ( v49 < v19 )
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
      if ( (unsigned int)v19 > v18 - (unsigned int)v40 )
      {
        v23 = -2147467259;
        goto LABEL_36;
      }
      memcpy_0((void *)(v34 + (unsigned int)v40), (const void *)(*(_QWORD *)(v26 + 24) + v15), (unsigned int)v19);
    }
    else
    {
      v20 = *((_QWORD *)this + v16 + 26);
      v21 = (*(__int64 (__fastcall **)(__int64, __int128 *, _QWORD))(*(_QWORD *)v20 + 24LL))(
              v20,
              &v32,
              (unsigned int)v19);
      if ( v21 )
      {
        v17 = v21;
        v44 = v21;
        goto LABEL_92;
      }
      LODWORD(v19) = *((_DWORD *)this + v16 + 125);
    }
    v22 = v40 + v19;
    v23 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v33 + 56LL))(v33, (unsigned int)v36, v22);
    if ( !v23 )
    {
      MesHandleFree(Handle);
      Handle = 0;
      v9 = HIDWORD(v36);
      if ( HIDWORD(v36) < v22 )
      {
        v23 = -2147024809;
        goto LABEL_35;
      }
      if ( v39 == 1 )
      {
        v24 = MesDecodeBufferHandleCreate((char *)(v34 + v22), HIDWORD(v36) - v22, &Handle);
      }
      else
      {
        pEncodedSize = 0;
        if ( HIDWORD(v36) == v22 )
        {
          LODWORD(v40) = v22;
          v23 = 1;
          goto LABEL_35;
        }
        v24 = MesEncodeFixedBufferHandleCreate((char *)(v34 + v22), HIDWORD(v36) - v22, &pEncodedSize, &Handle);
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
        LODWORD(v40) = v22;
      }
      else
      {
        v23 = -2147024882;
      }
    }
    v9 = HIDWORD(v36);
LABEL_35:
    v18 = v36;
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
        v47 = v15;
      }
    }
LABEL_41:
    v48 = ++v16;
  }
  v25 = *((_QWORD *)&v32 + 1);
  if ( *((_QWORD *)&v32 + 1) && *((_QWORD *)&v32 + 1) != (_QWORD)v32 )
  {
    v30 = v34;
    while ( 1 )
    {
      pEncodedSize = 0;
      v17 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, unsigned int *))(*(_QWORD *)v25 + 32LL))(
              v25,
              v30,
              (unsigned int)v9,
              &pEncodedSize);
      if ( v17 )
        break;
      v9 = HIDWORD(v36) - pEncodedSize;
      HIDWORD(v36) = v9;
      v30 = pEncodedSize + v34;
      v34 = v30;
      if ( !(_DWORD)v9 )
        break;
      v25 = *((_QWORD *)&v32 + 1);
    }
  }
  else
  {
    v17 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v33 + 56LL))(v33, v18, (unsigned int)v9);
  }
LABEL_53:
  v44 = v17;
LABEL_92:
  *((_DWORD *)this + 6) = 3;
  if ( v45 )
    (*(void (__fastcall **)(ActivationProperties *, __int64, __int64))(*(_QWORD *)this + 16LL))(this, v9, v11);
  if ( Handle )
  {
    MesHandleFree(Handle);
    Handle = 0;
  }
  v31 = v32;
  if ( (_QWORD)v32 )
  {
    (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v33 + 16LL))(v33, v9, v11);
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v32 + 16LL))(v32);
    v31 = v32;
  }
  if ( *((_QWORD *)&v32 + 1) && *((_QWORD *)&v32 + 1) != v31 )
    (*(void (__fastcall **)(_QWORD, _QWORD, __int64))(**((_QWORD **)&v32 + 1) + 16LL))(
      *((_QWORD *)&v32 + 1),
      **((_QWORD **)&v32 + 1),
      v11);
  return v17;
}

```

## disassembly

```asm
0x18002bcd0  mov     r11, rsp
0x18002bcd3  mov     [r11+10h], rbx
0x18002bcd7  mov     [r11+18h], rsi
0x18002bcdb  mov     [r11+8], rcx
0x18002bcdf  push    rdi
0x18002bce0  push    r12
0x18002bce2  push    r13
0x18002bce4  push    r14
0x18002bce6  push    r15
0x18002bce8  sub     rsp, 0C0h
0x18002bcef  mov     r9, r8
0x18002bcf2  mov     rsi, rdx
0x18002bcf5  mov     rbx, rcx
0x18002bcf8  xor     r15d, r15d
0x18002bcfb  mov     [r11-38h], r15
0x18002bcff  mov     rax, [rcx]
0x18002bd02  lea     r8, [r11-38h]
0x18002bd06  mov     rdx, r9
0x18002bd09  mov     rax, [rax]
0x18002bd0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bd11  test    eax, eax
0x18002bd13  js      loc_18002C386
0x18002bd19  mov     r14d, 1
0x18002bd1f  mov     [rsp+0E8h+var_54], r14d
0x18002bd27  lea     rdi, [rbx+38h]
0x18002bd2b  mov     [rsp+0E8h+var_94], r15
0x18002bd30  mov     [rsp+0E8h+var_A0], r15
0x18002bd35  mov     [rsp+0E8h+pEncodedSize], r15d
0x18002bd3a  mov     [rsp+0E8h+var_78], r15
0x18002bd3f  xorps   xmm0, xmm0
0x18002bd42  movdqa  [rsp+0E8h+var_B8], xmm0
0x18002bd48  mov     [rsp+0E8h+var_A8], r15
0x18002bd4d  mov     [rsp+0E8h+Handle], r15
0x18002bd52  mov     [rsp+0E8h+var_80], r14d
0x18002bd57  mov     eax, [rdi+0Ch]
0x18002bd5a  mov     [rsp+0E8h+var_70], eax
0x18002bd5e  mov     ecx, [rsp+0E8h+arg_20]
0x18002bd65  mov     [rsp+0E8h+var_6C], ecx
0x18002bd69  mov     eax, [rbx+0B8h]
0x18002bd6f  mov     [rsp+0E8h+var_68], eax
0x18002bd76  mov     [rsp+0E8h+var_50], r15
0x18002bd7e  lea     eax, [rcx-3]
0x18002bd81  cmp     eax, r14d
0x18002bd84  ja      loc_18002C291
0x18002bd8a  mov     [rsp+0E8h+var_50], rbx
0x18002bd92  mov     r14d, r15d
0x18002bd95  mov     [rsp+0E8h+var_54], r15d
0x18002bd9d  lea     rax, [rsp+0E8h+var_50]
0x18002bda5  mov     [rsp+0E8h+pObject], rax; void **
0x18002bdaa  mov     r9d, 2; unsigned int
0x18002bdb0  mov     r8, rdi; unsigned int *
0x18002bdb3  mov     rdx, rsi; struct IStream *
0x18002bdb6  lea     rcx, [rsp+0E8h+var_B8]; this
0x18002bdbb  call    ?InitStream@Serializer@@QEAAJPEAUIStream@@AEAKKAEAPEAX@Z; Serializer::InitStream(IStream *,ulong &,ulong,void * &)
0x18002bdc0  mov     esi, eax
0x18002bdc2  mov     [rsp+0E8h+var_58], eax
0x18002bdc9  test    eax, eax
0x18002bdcb  js      loc_18002C1B6
0x18002bdd1  cmp     [rsp+0E8h+var_50], 0
0x18002bdda  jnz     loc_18002C2B2
0x18002bde0  mov     [rsp+0E8h+var_40], r15
0x18002bde8  cmp     dword ptr [rbx+130h], 0Ch
0x18002bdef  jnb     loc_18002C1A1
0x18002bdf5  mov     eax, dword ptr [rsp+0E8h+var_94+4]
0x18002bdf9  cmp     eax, dword ptr [rsp+0E8h+var_94]
0x18002bdfd  ja      loc_18002C1A1
0x18002be03  mov     ecx, dword ptr [rsp+0E8h+var_78]
0x18002be07  cmp     ecx, eax
0x18002be09  ja      loc_18002C1A1
0x18002be0f  sub     eax, ecx
0x18002be11  mov     ecx, eax
0x18002be13  mov     [rsp+0E8h+var_40], rcx
0x18002be1b  mov     eax, [rbx+224h]
0x18002be21  cmp     rcx, rax
0x18002be24  jb      loc_18002C1A1
0x18002be2a  mov     [rsp+0E8h+pObject], rdi; pObject
0x18002be2f  lea     r9, pFormatString; pFormatString
0x18002be36  lea     r8, pStubDesc; pStubDesc
0x18002be3d  lea     rdx, pPicklingInfo; pPicklingInfo
0x18002be44  mov     rcx, [rsp+0E8h+Handle]; Handle
0x18002be49  call    cs:__imp_NdrMesTypeEncode2
0x18002be4f  mov     edi, [rbx+224h]
0x18002be55  add     edi, dword ptr [rsp+0E8h+var_78]
0x18002be59  mov     rcx, [rsp+0E8h+var_A8]
0x18002be5e  mov     rax, [rcx]
0x18002be61  mov     r8d, edi
0x18002be64  mov     edx, dword ptr [rsp+0E8h+var_94]
0x18002be68  mov     rax, [rax+38h]
0x18002be6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002be71  mov     ecx, eax
0x18002be73  test    eax, eax
0x18002be75  jnz     loc_18002C199
0x18002be7b  mov     rcx, [rsp+0E8h+Handle]; Handle
0x18002be80  call    cs:__imp_MesHandleFree
0x18002be86  mov     [rsp+0E8h+Handle], r15
0x18002be8b  mov     edx, dword ptr [rsp+0E8h+var_94+4]
0x18002be8f  cmp     edx, edi
0x18002be91  jb      loc_18002C1A1
0x18002be97  cmp     [rsp+0E8h+var_7C], 1
0x18002be9c  jnz     loc_18002C153
0x18002bea2  sub     edx, edi; BufferSize
0x18002bea4  mov     ecx, edi
0x18002bea6  add     rcx, [rsp+0E8h+var_A0]; Buffer
0x18002beab  lea     r8, [rsp+0E8h+Handle]; pHandle
0x18002beb0  call    cs:__imp_MesDecodeBufferHandleCreate
0x18002beb6  mov     ecx, eax
0x18002beb8  test    eax, eax
0x18002beba  jnz     loc_18002C17E
0x18002bec0  cmp     [rsp+0E8h+Handle], 0
0x18002bec6  jz      loc_18002C1A1
0x18002becc  mov     dword ptr [rsp+0E8h+var_78], edi
0x18002bed0  mov     r12d, [rbx+7Ch]
0x18002bed4  mov     [rsp+0E8h+var_48], r12d
0x18002bedc  mov     edi, r15d
0x18002bedf  mov     [rsp+0E8h+var_44], r15d
0x18002bee7  mov     r13d, 80070057h
0x18002beed  mov     edx, dword ptr [rsp+0E8h+var_94+4]
0x18002bef1  mov     r9d, dword ptr [rsp+0E8h+var_94]
0x18002bef6  nop     word ptr [rax+rax+00000000h]
0x18002bf00  cmp     edi, [rbx+130h]
0x18002bf06  jnb     loc_18002C0AF
0x18002bf0c  mov     r14d, edi
0x18002bf0f  mov     esi, [rbx+r14*4+1F4h]
0x18002bf17  test    esi, esi
0x18002bf19  jz      loc_18002C2D5
0x18002bf1f  cmp     edx, r9d
0x18002bf22  ja      loc_18002C0DE
0x18002bf28  mov     ecx, dword ptr [rsp+0E8h+var_78]
0x18002bf2c  cmp     ecx, edx
0x18002bf2e  ja      loc_18002C0DE
0x18002bf34  mov     eax, edx
0x18002bf36  sub     eax, ecx
0x18002bf38  mov     ecx, eax
0x18002bf3a  mov     [rsp+0E8h+var_40], rcx
0x18002bf42  mov     r8d, esi; Size
0x18002bf45  cmp     rcx, rsi
0x18002bf48  jb      loc_18002C0DE
0x18002bf4e  cmp     dword ptr [rbx+2Ch], 0
0x18002bf52  jz      short loc_18002BF63
0x18002bf54  cmp     qword ptr [rbx+r14*8+0D0h], 0
0x18002bf5d  jz      loc_18002C0EB
0x18002bf63  mov     rcx, [rbx+r14*8+0D0h]
0x18002bf6b  mov     rax, [rcx]
0x18002bf6e  lea     rdx, [rsp+0E8h+var_B8]
0x18002bf73  mov     rax, [rax+18h]
0x18002bf77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bf7c  test    eax, eax
0x18002bf7e  jnz     loc_18002C13C
0x18002bf84  mov     esi, [rbx+r14*4+1F4h]
0x18002bf8c  add     esi, dword ptr [rsp+0E8h+var_78]
0x18002bf90  mov     rcx, [rsp+0E8h+var_A8]
0x18002bf95  mov     rax, [rcx]
0x18002bf98  mov     r8d, esi
0x18002bf9b  mov     edx, dword ptr [rsp+0E8h+var_94]
0x18002bf9f  mov     rax, [rax+38h]
0x18002bfa3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bfa8  mov     ecx, eax
0x18002bfaa  test    eax, eax
0x18002bfac  jnz     short loc_18002C002
0x18002bfae  mov     rcx, [rsp+0E8h+Handle]; Handle
0x18002bfb3  call    cs:__imp_MesHandleFree
0x18002bfb9  mov     [rsp+0E8h+Handle], r15
0x18002bfbe  mov     edx, dword ptr [rsp+0E8h+var_94+4]
0x18002bfc2  cmp     edx, esi
0x18002bfc4  jb      loc_18002C14B
0x18002bfca  cmp     [rsp+0E8h+var_7C], 1
0x18002bfcf  jnz     short loc_18002C047
0x18002bfd1  sub     edx, esi; BufferSize
0x18002bfd3  mov     ecx, esi
0x18002bfd5  add     rcx, [rsp+0E8h+var_A0]; Buffer
0x18002bfda  lea     r8, [rsp+0E8h+Handle]; pHandle
0x18002bfdf  call    cs:__imp_MesDecodeBufferHandleCreate
0x18002bfe5  mov     ecx, eax
0x18002bfe7  test    eax, eax
0x18002bfe9  jnz     loc_18002C087
0x18002bfef  cmp     [rsp+0E8h+Handle], 0
0x18002bff5  jz      loc_18002C132
0x18002bffb  mov     ecx, r15d
0x18002bffe  mov     dword ptr [rsp+0E8h+var_78], esi
0x18002c002  mov     edx, dword ptr [rsp+0E8h+var_94+4]
0x18002c006  mov     r9d, dword ptr [rsp+0E8h+var_94]
0x18002c00b  test    ecx, ecx
0x18002c00d  js      loc_18002C2E4
0x18002c013  cmp     ecx, 1
0x18002c016  jz      short loc_18002C079
0x18002c018  cmp     dword ptr [rbx+2Ch], 0
0x18002c01c  jz      short loc_18002C039
0x18002c01e  cmp     edi, [rbx+88h]
0x18002c024  jnb     short loc_18002C039
0x18002c026  mov     rax, [rbx+0A8h]
0x18002c02d  add     r12d, [rax+r14*4]
0x18002c031  mov     [rsp+0E8h+var_48], r12d
0x18002c039  inc     edi
0x18002c03b  mov     [rsp+0E8h+var_44], edi
0x18002c042  jmp     loc_18002BF00
0x18002c047  mov     [rsp+0E8h+pEncodedSize], r15d
0x18002c04c  cmp     edx, esi
0x18002c04e  jnz     short loc_18002C05B
0x18002c050  mov     dword ptr [rsp+0E8h+var_78], esi
0x18002c054  mov     ecx, 1
0x18002c059  jmp     short loc_18002C006
0x18002c05b  sub     edx, esi; BufferSize
0x18002c05d  mov     ecx, esi
0x18002c05f  add     rcx, [rsp+0E8h+var_A0]; pBuffer
0x18002c064  lea     r9, [rsp+0E8h+Handle]; pHandle
0x18002c069  lea     r8, [rsp+0E8h+pEncodedSize]; pEncodedSize
0x18002c06e  call    cs:__imp_MesEncodeFixedBufferHandleCreate
0x18002c074  jmp     loc_18002BFE5
0x18002c079  mov     eax, [rbx+130h]
0x18002c07f  dec     eax
0x18002c081  cmp     edi, eax
0x18002c083  jz      short loc_18002C018
0x18002c085  jmp     short loc_18002C0DE
0x18002c087  mov     eax, ecx
0x18002c089  and     eax, 1FFF0000h
0x18002c08e  cmp     eax, 10000h
0x18002c093  jz      loc_18002C002
0x18002c099  test    ecx, ecx
0x18002c09b  jle     loc_18002C002
0x18002c0a1  movzx   ecx, cx
0x18002c0a4  or      ecx, 80070000h
0x18002c0aa  jmp     loc_18002C002
0x18002c0af  mov     rcx, qword ptr [rsp+0E8h+var_B8+8]
0x18002c0b4  test    rcx, rcx
0x18002c0b7  jz      short loc_18002C0C4
0x18002c0b9  cmp     rcx, qword ptr [rsp+0E8h+var_B8]
0x18002c0be  jnz     loc_18002C231
0x18002c0c4  mov     rcx, [rsp+0E8h+var_A8]
0x18002c0c9  mov     rax, [rcx]
0x18002c0cc  mov     r8d, edx
0x18002c0cf  mov     edx, r9d
0x18002c0d2  mov     rax, [rax+38h]
0x18002c0d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c0db  mov     r13d, eax
0x18002c0de  mov     [rsp+0E8h+var_58], r13d
0x18002c0e6  jmp     loc_18002C2EC
0x18002c0eb  mov     rcx, [rbx+228h]
0x18002c0f2  mov     eax, [rcx+24h]
0x18002c0f5  cmp     r12d, eax
0x18002c0f8  jnb     loc_18002C229
0x18002c0fe  sub     eax, r12d
0x18002c101  cmp     esi, eax
0x18002c103  ja      loc_18002C1AC
0x18002c109  mov     eax, r9d
0x18002c10c  sub     eax, dword ptr [rsp+0E8h+var_78]
0x18002c110  cmp     esi, eax
0x18002c112  ja      loc_18002C2DA
0x18002c118  mov     edx, r12d
0x18002c11b  add     rdx, [rcx+18h]; Src
0x18002c11f  mov     ecx, dword ptr [rsp+0E8h+var_78]
0x18002c123  add     rcx, [rsp+0E8h+var_A0]; void *
0x18002c128  call    memcpy_0
0x18002c12d  jmp     loc_18002BF8C
0x18002c132  mov     ecx, 8007000Eh
0x18002c137  jmp     loc_18002C002
0x18002c13c  mov     r13d, eax
0x18002c13f  mov     [rsp+0E8h+var_58], eax
0x18002c146  jmp     loc_18002C2EC
0x18002c14b  mov     ecx, r13d
0x18002c14e  jmp     loc_18002C006
0x18002c153  mov     [rsp+0E8h+pEncodedSize], r15d
0x18002c158  cmp     edx, edi
0x18002c15a  jz      loc_18002C2CC
0x18002c160  sub     edx, edi; BufferSize
0x18002c162  mov     ecx, edi
0x18002c164  add     rcx, [rsp+0E8h+var_A0]; pBuffer
0x18002c169  lea     r9, [rsp+0E8h+Handle]; pHandle
0x18002c16e  lea     r8, [rsp+0E8h+pEncodedSize]; pEncodedSize
0x18002c173  call    cs:__imp_MesEncodeFixedBufferHandleCreate
0x18002c179  jmp     loc_18002BEB6
0x18002c17e  mov     eax, ecx
0x18002c180  and     eax, 1FFF0000h
0x18002c185  cmp     eax, 10000h
0x18002c18a  jz      short loc_18002C199
0x18002c18c  test    ecx, ecx
0x18002c18e  jle     short loc_18002C19B
0x18002c190  movzx   ecx, cx
0x18002c193  or      ecx, 80070000h
0x18002c199  test    ecx, ecx
0x18002c19b  jz      loc_18002BED0
0x18002c1a1  mov     r13d, 80070057h
0x18002c1a7  jmp     loc_18002C0DE
0x18002c1ac  mov     ecx, 80004005h
0x18002c1b1  jmp     loc_18002C00B
0x18002c1b6  test    r14d, r14d
0x18002c1b9  jnz     loc_18002C29E
0x18002c1bf  mov     rcx, [rsp+0E8h+Handle]; Handle
0x18002c1c4  test    rcx, rcx
0x18002c1c7  jz      short loc_18002C1D4
0x18002c1c9  call    cs:__imp_MesHandleFree
0x18002c1cf  mov     [rsp+0E8h+Handle], r15
0x18002c1d4  mov     rax, qword ptr [rsp+0E8h+var_B8]
0x18002c1d9  test    rax, rax
0x18002c1dc  jz      short loc_18002C205
0x18002c1de  mov     rcx, [rsp+0E8h+var_A8]
0x18002c1e3  mov     rax, [rcx]
0x18002c1e6  mov     rax, [rax+10h]
0x18002c1ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c1ef  mov     rcx, qword ptr [rsp+0E8h+var_B8]
0x18002c1f4  mov     rax, [rcx]
  ... truncated ...
```
