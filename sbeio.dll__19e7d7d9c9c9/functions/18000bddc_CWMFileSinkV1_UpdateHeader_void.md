# CWMFileSinkV1::UpdateHeader(void)

- ea: `0x18000bddc`
- end: `0x18000c1a8`
- name: `?UpdateHeader@CWMFileSinkV1@@IEAAJXZ`
- size: `972`
- prototype: `__int64 __fastcall(CWMFileSinkV1 *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180009630`

## callees

- `0x1800015f0`
- `0x180001f1c`
- `0x18000bddc`
- `0x180012ff4`
- `0x180013188`
- `0x1800131b4`
- `0x180013b8c`
- `0x18001fbac`
- `0x180024fc0`
- `0x18002a064`
- `0x18002b010`

## pseudocode

```c
__int64 __fastcall CWMFileSinkV1::UpdateHeader(CWMFileSinkV1 *this, __int64 a2, __int64 a3, unsigned int *a4)
{
  __int64 v6; // rsi
  int StreamPropertiesObject; // ebx
  int v8; // r15d
  unsigned __int64 v9; // r14
  __int64 v10; // rax
  __int64 v11; // rcx
  CASFMMStream *v12; // rcx
  int v13; // r14d
  int v14; // r12d
  unsigned int StreamCount; // r13d
  unsigned int v16; // r15d
  CASFMMStream *v17; // rcx
  __int64 v18; // r12
  int v19; // eax
  __int64 v20; // rax
  void *v21; // rcx
  struct CASFLonghandObject *v22; // r15
  __int64 v23; // rax
  BOOL v24; // eax
  unsigned int v25; // eax
  unsigned int v26; // r14d
  unsigned int v27; // eax
  unsigned int v28; // ecx
  unsigned __int64 v29; // rdx
  __int64 v30; // rcx
  unsigned __int64 v31; // rdx
  __int64 j; // r8
  unsigned int *v33; // rdx
  __int64 v34; // rdx
  void *i; // [rsp+20h] [rbp-E0h] BYREF
  struct CASFLonghandObject *v36[2]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v37; // [rsp+40h] [rbp-C0h]
  __int64 v38; // [rsp+48h] [rbp-B8h]
  __int128 Buf2; // [rsp+58h] [rbp-A8h] BYREF
  _DWORD v40[64]; // [rsp+70h] [rbp-90h] BYREF

  if ( !*((_DWORD *)this + 5) )
    return 2147549183LL;
  v6 = *(_QWORD *)(*((_QWORD *)this + 30) + 616LL);
  if ( !v6 )
    return (unsigned int)-2147418113;
  v8 = 0;
  *(_QWORD *)(v6 + 88) = *((_QWORD *)this + 33);
  v9 = 0;
  v10 = *((_QWORD *)this + 32);
  v11 = *(_QWORD *)(v6 + 104);
  *(_QWORD *)(v6 + 104) = v10;
  v38 = v10;
  v37 = v11;
  if ( *((_DWORD *)this + 8) )
    goto LABEL_50;
  v12 = (CASFMMStream *)*((_QWORD *)this + 30);
  StreamPropertiesObject = 0;
  v13 = *(_DWORD *)(v6 + 136);
  v14 = 0;
  LODWORD(i) = 0;
  StreamCount = CASFMMStream::GetStreamCount(v12);
  v16 = 1;
  memset_0(v40, 0, sizeof(v40));
  while ( StreamCount && !v14 )
  {
    v17 = (CASFMMStream *)*((_QWORD *)this + 30);
    v36[0] = 0;
    StreamPropertiesObject = CASFMMStream::GetStreamPropertiesObject(v17, v16, v36);
    if ( StreamPropertiesObject >= 0 )
    {
      v18 = *((unsigned __int16 *)v36[0] + 52);
      if ( (unsigned __int16)(v18 - 1) > 0x3Eu )
        return (unsigned int)-2147467259;
      --StreamCount;
      v19 = (*(__int64 (__fastcall **)(CWMFileSinkV1 *))(*(_QWORD *)this + 296LL))(this);
      v40[v18] = v19;
      v14 = (int)i;
      if ( !v19 )
        v14 = 1;
      LODWORD(i) = v14;
    }
    ++v16;
  }
  if ( StreamPropertiesObject >= 0 )
  {
    v20 = *((_QWORD *)this + 30);
    v36[0] = 0;
    v21 = *(void **)(v20 + 592);
    for ( i = v21; ; v21 = i )
    {
      if ( !v21 || CASFMMStream::GetNextObject((CASFMMStream *)v21, v36, &i) < 0 )
      {
        v25 = v13 & 0xFFFFFFF6;
        v26 = v13 & 0xFFFFFFF4 | 2;
        v27 = v25 & 0xFFFFFFFD;
        if ( v14 )
          v26 = v27;
        *(_DWORD *)(v6 + 136) = v26;
        if ( *((_QWORD *)this + 37) != -1 )
        {
          v28 = *(_DWORD *)(v6 + 148);
          if ( v28 )
          {
            v29 = 10000 * (*((_QWORD *)this + 36) + 8000 * *(_DWORD *)(v6 + 140) / v28);
            goto LABEL_37;
          }
          return (unsigned int)-2147418113;
        }
        v29 = 0;
LABEL_37:
        if ( (int)CASFPropertiesObject::SetSendDuration((CASFPropertiesObject *)v6, v29) < 0 )
          return (unsigned int)-2147418113;
        v30 = *((_QWORD *)this + 37);
        if ( v30 == -1 )
        {
          *(_QWORD *)(v6 + 112) = 0;
        }
        else
        {
          v31 = *(_QWORD *)(v6 + 112) / 0x2710uLL;
          if ( v31 && v37 == v38 )
          {
            v8 = 1;
            v9 = *(_QWORD *)(v6 + 112) / 0x2710uLL;
            *(_QWORD *)(v6 + 112) = 10000 * (v31 - v30);
LABEL_50:
            v34 = *((_QWORD *)this + 30) + 80LL;
            if ( *((_QWORD *)this + 30) == -80 )
            {
              return (unsigned int)-1072887838;
            }
            else
            {
              *(_QWORD *)(*((_QWORD *)this + 30) + 152LL) = *((_QWORD *)this + 32);
              *(_QWORD *)(v34 + 32) = *((_QWORD *)this + 33)
                                    - *((_QWORD *)this + 40)
                                    - *((unsigned int *)this + 56)
                                    + 50LL;
              StreamPropertiesObject = CASFMMStream::StoreHeader(
                                         *((CASFMMStream **)this + 30),
                                         *((unsigned __int8 **)this + 29),
                                         *((_DWORD *)this + 56),
                                         a4);
              if ( StreamPropertiesObject < 0 )
                return (unsigned int)-2147418113;
              if ( v8 )
                *(_QWORD *)(v6 + 112) = v9;
              else
                *(_QWORD *)(v6 + 104) = -1;
            }
            return (unsigned int)StreamPropertiesObject;
          }
          a4 = 0;
          for ( j = 0; j != 64; ++j )
          {
            v33 = (unsigned int *)(*((_QWORD *)this + 6 * j + 45) + *((unsigned int *)this + 12 * j + 92));
            if ( v33 <= a4 )
              v33 = a4;
            a4 = v33;
          }
          *(_QWORD *)(v6 + 112) = 10000LL * (_QWORD)v33;
        }
        v8 = 0;
        v9 = 0;
        goto LABEL_50;
      }
      v22 = v36[0];
      Buf2 = *((_OWORD *)v36[0] + 1);
      if ( memcmp_0(&CLSID_CAsfStreamPropertiesObjectEx, &Buf2, 0x10u) )
        goto LABEL_28;
      if ( (unsigned __int16)(*((_WORD *)v22 + 58) - 1) <= 0x3Eu )
        break;
      StreamPropertiesObject = -2147467259;
LABEL_29:
      CASFLonghandObject::Release(v22);
      if ( StreamPropertiesObject < 0 )
        return (unsigned int)StreamPropertiesObject;
    }
    v23 = *((unsigned __int16 *)v22 + 58);
    v24 = v40[v23] || *((_QWORD *)this + v23 + 921) && *((_DWORD *)this + 83);
    *((_DWORD *)v22 + 26) = v24;
LABEL_28:
    StreamPropertiesObject = 0;
    goto LABEL_29;
  }
  return (unsigned int)StreamPropertiesObject;
}

```

## disassembly

```asm
0x18000bddc  push    rbp
0x18000bdde  push    rbx
0x18000bddf  push    rsi
0x18000bde0  push    rdi
0x18000bde1  push    r12
0x18000bde3  push    r13
0x18000bde5  push    r14
0x18000bde7  push    r15
0x18000bde9  lea     rbp, [rsp-88h]
0x18000bdf1  sub     rsp, 188h
0x18000bdf8  mov     rax, cs:__security_cookie
0x18000bdff  xor     rax, rsp
0x18000be02  mov     [rbp+0C0h+var_50], rax
0x18000be06  xor     r13d, r13d
0x18000be09  mov     rdi, rcx
0x18000be0c  cmp     [rcx+14h], r13d
0x18000be10  jnz     short loc_18000BE1C
0x18000be12  mov     eax, 8000FFFFh
0x18000be17  jmp     loc_18000C188
0x18000be1c  mov     rax, [rcx+0F0h]
0x18000be23  mov     rsi, [rax+268h]
0x18000be2a  test    rsi, rsi
0x18000be2d  jnz     short loc_18000BE39
0x18000be2f  mov     ebx, 8000FFFFh
0x18000be34  jmp     loc_18000C186
0x18000be39  mov     rax, [rcx+108h]
0x18000be40  mov     r15d, r13d
0x18000be43  mov     [rsi+58h], rax
0x18000be47  mov     r14, r13
0x18000be4a  mov     rax, [rcx+100h]
0x18000be51  mov     rcx, [rsi+68h]
0x18000be55  mov     [rsi+68h], rax
0x18000be59  mov     [rsp+1C0h+var_178], rax
0x18000be5e  mov     [rsp+1C0h+var_180], rcx
0x18000be63  cmp     [rdi+20h], r13d
0x18000be67  jnz     loc_18000C111
0x18000be6d  mov     rcx, [rdi+0F0h]; this
0x18000be74  mov     ebx, r13d
0x18000be77  mov     r14d, [rsi+88h]
0x18000be7e  mov     r12d, r13d
0x18000be81  mov     dword ptr [rsp+1C0h+var_1A0], r13d
0x18000be86  call    ?GetStreamCount@CASFMMStream@@QEAAKXZ; CASFMMStream::GetStreamCount(void)
0x18000be8b  xor     edx, edx; Val
0x18000be8d  lea     rcx, [rsp+1C0h+var_150]; void *
0x18000be92  mov     r8d, 100h; Size
0x18000be98  mov     r13d, eax
0x18000be9b  lea     r15d, [rdx+1]
0x18000be9f  call    memset_0
0x18000bea4  test    r13d, r13d
0x18000bea7  jz      loc_18000BF36
0x18000bead  test    r12d, r12d
0x18000beb0  jnz     loc_18000BF36
0x18000beb6  mov     rcx, [rdi+0F0h]; this
0x18000bebd  lea     r8, [rsp+1C0h+var_190]; struct CASFStreamPropertiesObject **
0x18000bec2  mov     edx, r15d; unsigned int
0x18000bec5  mov     [rsp+1C0h+var_190], 0
0x18000bece  call    ?GetStreamPropertiesObject@CASFMMStream@@QEAAJKPEAPEAVCASFStreamPropertiesObject@@@Z; CASFMMStream::GetStreamPropertiesObject(ulong,CASFStreamPropertiesObject * *)
0x18000bed3  mov     ebx, eax
0x18000bed5  test    eax, eax
0x18000bed7  js      short loc_18000BF1F
0x18000bed9  mov     rdx, [rsp+1C0h+var_190]
0x18000bede  movzx   r12d, word ptr [rdx+68h]
0x18000bee3  lea     ecx, [r12-1]
0x18000bee8  cmp     cx, 3Eh ; '>'
0x18000beec  ja      short loc_18000BF2C
0x18000beee  mov     rcx, [rdi]
0x18000bef1  dec     r13d
0x18000bef4  mov     rax, [rcx+128h]
0x18000befb  mov     rcx, rdi
0x18000befe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf03  mov     [rsp+r12*4+1C0h+var_150], eax
0x18000bf08  test    eax, eax
0x18000bf0a  mov     r12d, dword ptr [rsp+1C0h+var_1A0]
0x18000bf0f  mov     eax, 1
0x18000bf14  cmovz   r12d, eax
0x18000bf18  mov     dword ptr [rsp+1C0h+var_1A0], r12d
0x18000bf1d  jmp     short loc_18000BF24
0x18000bf1f  mov     eax, 1
0x18000bf24  add     r15d, eax
0x18000bf27  jmp     loc_18000BEA4
0x18000bf2c  mov     ebx, 80004005h
0x18000bf31  jmp     loc_18000C186
0x18000bf36  xor     r13d, r13d
0x18000bf39  test    ebx, ebx
0x18000bf3b  js      loc_18000C186
0x18000bf41  mov     rax, [rdi+0F0h]
0x18000bf48  mov     ebx, r13d
0x18000bf4b  mov     [rsp+1C0h+var_190], r13
0x18000bf50  mov     rcx, [rax+250h]; this
0x18000bf57  mov     [rsp+1C0h+var_1A0], rcx
0x18000bf5c  test    rcx, rcx
0x18000bf5f  jz      loc_18000C010
0x18000bf65  lea     r8, [rsp+1C0h+var_1A0]; void **
0x18000bf6a  lea     rdx, [rsp+1C0h+var_190]; struct CASFLonghandObject **
0x18000bf6f  call    ?GetNextObject@CASFMMStream@@QEAAJPEAPEAVCASFLonghandObject@@AEAPEAX@Z; CASFMMStream::GetNextObject(CASFLonghandObject * *,void * &)
0x18000bf74  test    eax, eax
0x18000bf76  js      loc_18000C008
0x18000bf7c  mov     r15, [rsp+1C0h+var_190]
0x18000bf81  lea     rdx, [rsp+1C0h+Buf2]; Buf2
0x18000bf86  mov     r8d, 10h; Size
0x18000bf8c  lea     rcx, CLSID_CAsfStreamPropertiesObjectEx; Buf1
0x18000bf93  movups  xmm0, xmmword ptr [r15+10h]
0x18000bf98  movdqu  [rsp+1C0h+Buf2], xmm0
0x18000bf9e  call    memcmp_0
0x18000bfa3  test    eax, eax
0x18000bfa5  jnz     short loc_18000BFE4
0x18000bfa7  movzx   eax, word ptr [r15+74h]
0x18000bfac  mov     ecx, 1
0x18000bfb1  sub     ax, cx
0x18000bfb4  cmp     ax, 3Eh ; '>'
0x18000bfb8  ja      short loc_18000C001
0x18000bfba  movzx   eax, word ptr [r15+74h]
0x18000bfbf  cmp     [rsp+rax*4+1C0h+var_150], r13d
0x18000bfc4  jnz     short loc_18000BFDE
0x18000bfc6  cmp     [rdi+rax*8+1CC8h], r13
0x18000bfce  jz      short loc_18000BFD9
0x18000bfd0  cmp     [rdi+14Ch], r13d
0x18000bfd7  jnz     short loc_18000BFDE
0x18000bfd9  mov     eax, r13d
0x18000bfdc  jmp     short loc_18000BFE0
0x18000bfde  mov     eax, ecx
0x18000bfe0  mov     [r15+68h], eax
0x18000bfe4  mov     ebx, r13d
0x18000bfe7  mov     rcx, r15; this
0x18000bfea  call    ?Release@CASFLonghandObject@@QEAAKXZ; CASFLonghandObject::Release(void)
0x18000bfef  test    ebx, ebx
0x18000bff1  js      loc_18000C186
0x18000bff7  mov     rcx, [rsp+1C0h+var_1A0]
0x18000bffc  jmp     loc_18000BF5C
0x18000c001  mov     ebx, 80004005h
0x18000c006  jmp     short loc_18000BFE7
0x18000c008  test    ebx, ebx
0x18000c00a  js      loc_18000C186
0x18000c010  and     r14d, 0FFFFFFF6h
0x18000c014  mov     eax, r14d
0x18000c017  or      r14d, 2
0x18000c01b  and     eax, 0FFFFFFFDh
0x18000c01e  test    r12d, r12d
0x18000c021  cmovnz  r14d, eax
0x18000c025  mov     [rsi+88h], r14d
0x18000c02c  cmp     qword ptr [rdi+128h], 0FFFFFFFFFFFFFFFFh
0x18000c034  jz      loc_18000C0C6
0x18000c03a  mov     ecx, [rsi+94h]
0x18000c040  test    ecx, ecx
0x18000c042  jz      loc_18000BE2F
0x18000c048  imul    eax, [rsi+8Ch], 1F40h
0x18000c052  xor     edx, edx
0x18000c054  div     ecx
0x18000c056  mov     ecx, eax
0x18000c058  add     rcx, [rdi+120h]
0x18000c05f  imul    rdx, rcx, 2710h; unsigned __int64
0x18000c066  mov     rcx, rsi; this
0x18000c069  call    ?SetSendDuration@CASFPropertiesObject@@QEAAJ_K@Z; CASFPropertiesObject::SetSendDuration(unsigned __int64)
0x18000c06e  test    eax, eax
0x18000c070  js      loc_18000BE2F
0x18000c076  mov     rcx, [rdi+128h]
0x18000c07d  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000c081  jz      loc_18000C107
0x18000c087  mov     rax, 346DC5D63886594Bh
0x18000c091  mul     qword ptr [rsi+70h]
0x18000c095  shr     rdx, 0Bh
0x18000c099  test    rdx, rdx
0x18000c09c  jz      short loc_18000C0CA
0x18000c09e  mov     rax, [rsp+1C0h+var_180]
0x18000c0a3  cmp     rax, [rsp+1C0h+var_178]
0x18000c0a8  jnz     short loc_18000C0CA
0x18000c0aa  mov     rax, rdx
0x18000c0ad  mov     r15d, 1
0x18000c0b3  sub     rax, rcx
0x18000c0b6  mov     r14, rdx
0x18000c0b9  imul    rax, 2710h
0x18000c0c0  mov     [rsi+70h], rax
0x18000c0c4  jmp     short loc_18000C111
0x18000c0c6  xor     edx, edx
0x18000c0c8  jmp     short loc_18000C066
0x18000c0ca  mov     r9, r13
0x18000c0cd  mov     r8, r13
0x18000c0d0  lea     rax, [r8+r8*2]
0x18000c0d4  shl     rax, 4
0x18000c0d8  mov     edx, [rax+rdi+170h]
0x18000c0df  add     rdx, [rax+rdi+168h]
0x18000c0e7  cmp     rdx, r9
0x18000c0ea  cmovbe  rdx, r9
0x18000c0ee  inc     r8
0x18000c0f1  mov     r9, rdx
0x18000c0f4  cmp     r8, 40h ; '@'
0x18000c0f8  jnz     short loc_18000C0D0
0x18000c0fa  imul    rax, r9, 2710h
0x18000c101  mov     [rsi+70h], rax
0x18000c105  jmp     short loc_18000C10B
0x18000c107  mov     [rsi+70h], r13
0x18000c10b  mov     r15d, r13d
0x18000c10e  mov     r14, r13
0x18000c111  mov     rdx, [rdi+0F0h]
0x18000c118  add     rdx, 50h ; 'P'
0x18000c11c  jnz     short loc_18000C125
0x18000c11e  mov     ebx, 0C00D07E2h
0x18000c123  jmp     short loc_18000C186
0x18000c125  mov     rax, [rdi+100h]
0x18000c12c  mov     [rdx+48h], rax
0x18000c130  mov     rcx, [rdi+108h]
0x18000c137  sub     rcx, [rdi+140h]
0x18000c13e  mov     eax, [rdi+0E0h]
0x18000c144  sub     rcx, rax
0x18000c147  add     rcx, 32h ; '2'
0x18000c14b  mov     [rdx+20h], rcx
0x18000c14f  mov     r8d, [rdi+0E0h]; unsigned int
0x18000c156  mov     rdx, [rdi+0E8h]; unsigned __int8 *
0x18000c15d  mov     rcx, [rdi+0F0h]; this
0x18000c164  call    ?StoreHeader@CASFMMStream@@QEAAJPEAEKPEAK@Z; CASFMMStream::StoreHeader(uchar *,ulong,ulong *)
0x18000c169  mov     ebx, eax
0x18000c16b  test    eax, eax
0x18000c16d  js      loc_18000BE2F
0x18000c173  test    r15d, r15d
0x18000c176  jz      short loc_18000C17E
0x18000c178  mov     [rsi+70h], r14
0x18000c17c  jmp     short loc_18000C186
0x18000c17e  mov     qword ptr [rsi+68h], 0FFFFFFFFFFFFFFFFh
0x18000c186  mov     eax, ebx
0x18000c188  mov     rcx, [rbp+0C0h+var_50]
0x18000c18c  xor     rcx, rsp; StackCookie
0x18000c18f  call    __security_check_cookie
0x18000c194  add     rsp, 188h
0x18000c19b  pop     r15
0x18000c19d  pop     r14
0x18000c19f  pop     r13
0x18000c1a1  pop     r12
0x18000c1a3  pop     rdi
0x18000c1a4  pop     rsi
0x18000c1a5  pop     rbx
0x18000c1a6  pop     rbp
0x18000c1a7  retn
```
