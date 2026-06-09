# TpmW8ApiOwnerReadNV(HTPMCONTEXT__ *,uint,_TPM_API_HASH_DATA const *,uint *,uchar *)

- ea: `0x140033154`
- end: `0x14003335f`
- name: `?TpmW8ApiOwnerReadNV@@YAJPEAUHTPMCONTEXT__@@IPEBU_TPM_API_HASH_DATA@@PEAIPEAE@Z`
- size: `523`
- prototype: `int(struct HTPMCONTEXT__ *, unsigned int, const struct _TPM_API_HASH_DATA *, unsigned int *, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x14002a410`

## callees

- `0x14000da40`
- `0x140031234`
- `0x140031284`
- `0x140033154`
- `0x1400367d8`
- `0x1400374f8`
- `0x140037ddc`
- `0x140037e54`
- `0x140038c38`
- `0x140038d2c`
- `0x140039840`

## pseudocode

```c
__int64 __fastcall TpmW8ApiOwnerReadNV(
        struct HTPMCONTEXT__ *a1,
        int a2,
        const struct _TPM_API_HASH_DATA *a3,
        unsigned int *a4,
        unsigned __int8 *a5)
{
  int v8; // ebx
  unsigned int v9; // ecx
  unsigned __int16 v10; // r8
  unsigned int i; // esi
  unsigned int v12; // edi
  unsigned int v13; // edi
  int v14; // r14d
  _QWORD v16[3]; // [rsp+20h] [rbp-E0h] BYREF
  int v17; // [rsp+38h] [rbp-C8h]
  __int64 v18; // [rsp+40h] [rbp-C0h]
  __int64 v19; // [rsp+48h] [rbp-B8h]
  char v20; // [rsp+50h] [rbp-B0h]
  __int16 v21; // [rsp+58h] [rbp-A8h]
  __int64 v22; // [rsp+60h] [rbp-A0h]
  _BYTE v23[168]; // [rsp+70h] [rbp-90h] BYREF
  tpm12class::TPMW8_SESSION *v24; // [rsp+118h] [rbp+18h]
  int v25; // [rsp+130h] [rbp+30h]
  int v26; // [rsp+180h] [rbp+80h]
  _BYTE v27[72]; // [rsp+188h] [rbp+88h] BYREF
  __int16 v28; // [rsp+1D0h] [rbp+D0h]
  __int16 v29; // [rsp+1D2h] [rbp+D2h]
  unsigned __int16 v30; // [rsp+210h] [rbp+110h]
  void *Src; // [rsp+218h] [rbp+118h]
  _BYTE v32[196]; // [rsp+220h] [rbp+120h] BYREF
  int v33; // [rsp+2E4h] [rbp+1E4h]
  __int64 v34; // [rsp+2E8h] [rbp+1E8h]
  _BYTE v35[128]; // [rsp+2F0h] [rbp+1F0h] BYREF
  struct HTPMCONTEXT__ *v36; // [rsp+380h] [rbp+280h] BYREF

  v36 = a1;
  v16[1] = 0;
  v16[2] = 0;
  v17 = 0;
  v18 = 0;
  v19 = 0;
  v20 = 0;
  v16[0] = &tpm12class::TPMW82B_BUFFER::`vftable';
  v21 = 0;
  v22 = 0;
  tpm12class::TPMW8_NV_ReadPublic::TPMW8_NV_ReadPublic((tpm12class::TPMW8_NV_ReadPublic *)v32);
  tpm12class::TPMW8_NV_Read::TPMW8_NV_Read((tpm12class::TPMW8_NV_Read *)v23);
  v33 = a2;
  v8 = tpm12class::TPMW8_COMMAND::Execute((tpm12class::TPMW8_COMMAND *)v32, &v36);
  if ( v8 >= 0 && v34 )
  {
    v9 = *(unsigned __int16 *)(v34 + 144);
    if ( (_WORD)v9 )
    {
      if ( a5 && v9 <= *a4 )
      {
        v8 = tpm12class::TPMW82B_BUFFER::CopyFrom((tpm12class::TPMW82B_BUFFER *)v16, (const unsigned __int8 *)a3, 0x14u);
        if ( v8 >= 0 )
        {
          v25 = 1073741825;
          v26 = a2;
          tpm12class::TPMW82B_BUFFER::CopyFrom(
            (tpm12class::TPMW82B_BUFFER *)v27,
            (const struct tpm12class::TPMW82B_BUFFER *)v35);
          *((_BYTE *)v24 + 760) = 1;
          v8 = tpm12class::TPMW8_SESSION::SetAuthProvider(v24, (const struct tpm12class::TPMW82B_BUFFER *)v16, v10);
          if ( v8 >= 0 )
          {
            for ( i = 0; ; i += v14 )
            {
              v12 = *(unsigned __int16 *)(v34 + 144);
              if ( i >= v12 )
                break;
              v13 = v12 - i;
              if ( v13 <= 0x300 )
              {
                *((_BYTE *)v24 + 764) &= ~1u;
              }
              else
              {
                *((_BYTE *)v24 + 764) |= 1u;
                v13 = 768;
              }
              v28 = v13;
              v29 = i;
              v8 = tpm12class::TPMW8_COMMAND::Execute((tpm12class::TPMW8_COMMAND *)v23, &v36);
              if ( v8 || (v14 = v30, v30 > v13) )
              {
                v8 = -2144796404;
                break;
              }
              memmove(&a5[i], Src, v30);
            }
          }
        }
      }
      else
      {
        *a4 = v9;
        v8 = -2144796410;
      }
    }
    else
    {
      *a4 = 0;
    }
  }
  else
  {
    v8 = -2144796412;
  }
  tpm12class::TPMW8_NV_Read::~TPMW8_NV_Read((tpm12class::TPMW8_NV_Read *)v23);
  tpm12class::TPMW8_NV_ReadPublic::~TPMW8_NV_ReadPublic((tpm12class::TPMW8_NV_ReadPublic *)v32);
  tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER((tpm12class::TPMW82B_BUFFER *)v16);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140033154  mov     [rsp-8+arg_0], rcx
0x140033159  push    rbp
0x14003315a  push    rbx
0x14003315b  push    rsi
0x14003315c  push    rdi
0x14003315d  push    r12
0x14003315f  push    r14
0x140033161  lea     rbp, [rsp-248h]
0x140033169  sub     rsp, 348h
0x140033170  xor     r12d, r12d
0x140033173  lea     rax, ??_7TPMW82B_BUFFER@tpm12class@@6B@; const tpm12class::TPMW82B_BUFFER::`vftable'
0x14003317a  lea     rcx, [rbp+270h+var_150]; this
0x140033181  mov     [rsp+370h+var_348], r12
0x140033186  mov     [rsp+370h+var_340], r12
0x14003318b  mov     rdi, r9
0x14003318e  mov     [rsp+370h+var_338], r12d
0x140033193  mov     r14, r8
0x140033196  mov     [rsp+370h+var_330], r12
0x14003319b  mov     esi, edx
0x14003319d  mov     [rsp+370h+var_328], r12
0x1400331a2  mov     [rsp+370h+var_320], r12b
0x1400331a7  mov     [rsp+370h+var_350], rax
0x1400331ac  mov     [rsp+370h+var_318], r12w
0x1400331b2  mov     [rsp+370h+var_310], r12
0x1400331b7  call    ??0TPMW8_NV_ReadPublic@tpm12class@@QEAA@XZ; tpm12class::TPMW8_NV_ReadPublic::TPMW8_NV_ReadPublic(void)
0x1400331bc  lea     rcx, [rsp+370h+var_300]; this
0x1400331c1  call    ??0TPMW8_NV_Read@tpm12class@@QEAA@XZ; tpm12class::TPMW8_NV_Read::TPMW8_NV_Read(void)
0x1400331c6  lea     rdx, [rbp+270h+arg_0]; void *
0x1400331cd  mov     [rbp+270h+var_8C], esi
0x1400331d3  lea     rcx, [rbp+270h+var_150]; this
0x1400331da  call    ?Execute@TPMW8_COMMAND@tpm12class@@QEAAJPEAX@Z; tpm12class::TPMW8_COMMAND::Execute(void *)
0x1400331df  mov     ebx, eax
0x1400331e1  test    eax, eax
0x1400331e3  js      loc_140033327
0x1400331e9  mov     rax, [rbp+270h+var_88]
0x1400331f0  test    rax, rax
0x1400331f3  jz      loc_140033327
0x1400331f9  movzx   ecx, word ptr [rax+90h]
0x140033200  test    cx, cx
0x140033203  jnz     short loc_14003320D
0x140033205  mov     [rdi], r12d
0x140033208  jmp     loc_14003332C
0x14003320d  mov     eax, ecx
0x14003320f  cmp     [rbp+270h+arg_20], r12
0x140033216  jz      loc_14003331E
0x14003321c  cmp     eax, [rdi]
0x14003321e  ja      loc_14003331E
0x140033224  mov     r8d, 14h; unsigned __int64
0x14003322a  lea     rcx, [rsp+370h+var_350]; this
0x14003322f  mov     rdx, r14; unsigned __int8 *
0x140033232  call    ?CopyFrom@TPMW82B_BUFFER@tpm12class@@QEAAJPEBE_K@Z; tpm12class::TPMW82B_BUFFER::CopyFrom(uchar const *,unsigned __int64)
0x140033237  mov     ebx, eax
0x140033239  test    eax, eax
0x14003323b  js      loc_14003332C
0x140033241  lea     rdx, [rbp+270h+var_80]; struct tpm12class::TPMW82B_BUFFER *
0x140033248  mov     [rbp+270h+var_240], 40000001h
0x14003324f  lea     rcx, [rbp+270h+var_1E8]; this
0x140033256  mov     [rbp+270h+var_1F0], esi
0x14003325c  call    ?CopyFrom@TPMW82B_BUFFER@tpm12class@@QEAAJPEBV12@@Z; tpm12class::TPMW82B_BUFFER::CopyFrom(tpm12class::TPMW82B_BUFFER const *)
0x140033261  mov     rax, [rbp+270h+var_258]
0x140033265  lea     rdx, [rsp+370h+var_350]; struct tpm12class::TPMW82B_BUFFER *
0x14003326a  mov     byte ptr [rax+2F8h], 1
0x140033271  mov     rcx, [rbp+270h+var_258]; this
0x140033275  call    ?SetAuthProvider@TPMW8_SESSION@tpm12class@@QEAAJAEBVTPMW82B_BUFFER@2@G@Z; tpm12class::TPMW8_SESSION::SetAuthProvider(tpm12class::TPMW82B_BUFFER const &,ushort)
0x14003327a  mov     ebx, eax
0x14003327c  test    eax, eax
0x14003327e  js      loc_14003332C
0x140033284  mov     esi, r12d
0x140033287  mov     rax, [rbp+270h+var_88]
0x14003328e  movzx   edi, word ptr [rax+90h]
0x140033295  cmp     esi, edi
0x140033297  jnb     loc_14003332C
0x14003329d  mov     rax, [rbp+270h+var_258]
0x1400332a1  sub     edi, esi
0x1400332a3  cmp     edi, 300h
0x1400332a9  jbe     short loc_1400332B9
0x1400332ab  or      byte ptr [rax+2FCh], 1
0x1400332b2  mov     edi, 300h
0x1400332b7  jmp     short loc_1400332C0
0x1400332b9  and     byte ptr [rax+2FCh], 0FEh
0x1400332c0  lea     rdx, [rbp+270h+arg_0]; void *
0x1400332c7  mov     [rbp+270h+var_1A0], di
0x1400332ce  lea     rcx, [rsp+370h+var_300]; this
0x1400332d3  mov     [rbp+270h+var_19E], si
0x1400332da  call    ?Execute@TPMW8_COMMAND@tpm12class@@QEAAJPEAX@Z; tpm12class::TPMW8_COMMAND::Execute(void *)
0x1400332df  mov     ebx, eax
0x1400332e1  test    eax, eax
0x1400332e3  jnz     short loc_140033317
0x1400332e5  movzx   r14d, [rbp+270h+var_160]
0x1400332ed  cmp     r14d, edi
0x1400332f0  ja      short loc_140033317
0x1400332f2  movzx   r8d, [rbp+270h+var_160]; Size
0x1400332fa  mov     rdx, [rbp+270h+Src]; Src
0x140033301  mov     ecx, esi
0x140033303  add     rcx, [rbp+270h+arg_20]; void *
0x14003330a  call    memmove
0x14003330f  add     esi, r14d
0x140033312  jmp     loc_140033287
0x140033317  mov     ebx, 8029010Ch
0x14003331c  jmp     short loc_14003332C
0x14003331e  mov     [rdi], eax
0x140033320  mov     ebx, 80290106h
0x140033325  jmp     short loc_14003332C
0x140033327  mov     ebx, 80290104h
0x14003332c  lea     rcx, [rsp+370h+var_300]; this
0x140033331  call    ??1TPMW8_NV_Read@tpm12class@@UEAA@XZ; tpm12class::TPMW8_NV_Read::~TPMW8_NV_Read(void)
0x140033336  lea     rcx, [rbp+270h+var_150]; this
0x14003333d  call    ??1TPMW8_NV_ReadPublic@tpm12class@@UEAA@XZ; tpm12class::TPMW8_NV_ReadPublic::~TPMW8_NV_ReadPublic(void)
0x140033342  lea     rcx, [rsp+370h+var_350]; this
0x140033347  call    ??1TPMW82B_BUFFER@tpm12class@@UEAA@XZ; tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER(void)
0x14003334c  mov     eax, ebx
0x14003334e  add     rsp, 348h
0x140033355  pop     r14
0x140033357  pop     r12
0x140033359  pop     rdi
0x14003335a  pop     rsi
0x14003335b  pop     rbx
0x14003335c  pop     rbp
0x14003335d  retn
```
