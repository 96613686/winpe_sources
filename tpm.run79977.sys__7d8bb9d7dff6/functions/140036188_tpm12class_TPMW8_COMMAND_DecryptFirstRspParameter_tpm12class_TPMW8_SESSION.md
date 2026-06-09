# tpm12class::TPMW8_COMMAND::DecryptFirstRspParameter(tpm12class::TPMW8_SESSION *)

- ea: `0x140036188`
- end: `0x1400364a2`
- name: `?DecryptFirstRspParameter@TPMW8_COMMAND@tpm12class@@IEAAJPEAVTPMW8_SESSION@2@@Z`
- size: `794`
- prototype: `__int64 __fastcall(tpm12class::TPMW8_COMMAND *__hidden this, struct tpm12class::TPMW8_SESSION *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x140036cb4`

## callees

- `0x14000da40`
- `0x140031008`
- `0x1400320d4`
- `0x140032114`
- `0x140032214`
- `0x140035ac4`
- `0x140036188`
- `0x140039780`

## pseudocode

```c
__int64 __fastcall tpm12class::TPMW8_COMMAND::DecryptFirstRspParameter(
        tpm12class::TPMW8_COMMAND *this,
        struct tpm12class::TPMW8_SESSION *a2)
{
  unsigned int v4; // edx
  int v5; // ebx
  unsigned int v6; // edx
  unsigned int v8; // r14d
  unsigned __int64 v9; // rsi
  int v10; // eax
  int v11; // ebx
  bool v12; // sf
  _QWORD v13[3]; // [rsp+40h] [rbp-C0h] BYREF
  int v14; // [rsp+58h] [rbp-A8h]
  __int64 v15; // [rsp+60h] [rbp-A0h]
  __int64 v16; // [rsp+68h] [rbp-98h]
  char v17; // [rsp+70h] [rbp-90h]
  unsigned __int16 v18; // [rsp+78h] [rbp-88h]
  unsigned __int8 *v19; // [rsp+80h] [rbp-80h]
  _QWORD v20[3]; // [rsp+90h] [rbp-70h] BYREF
  int v21; // [rsp+A8h] [rbp-58h]
  __int64 v22; // [rsp+B0h] [rbp-50h]
  __int64 v23; // [rsp+B8h] [rbp-48h]
  char v24; // [rsp+C0h] [rbp-40h]
  unsigned __int16 v25; // [rsp+C8h] [rbp-38h]
  unsigned __int8 *v26; // [rsp+D0h] [rbp-30h]
  _QWORD v27[3]; // [rsp+E0h] [rbp-20h] BYREF
  int v28; // [rsp+F8h] [rbp-8h]
  __int64 v29; // [rsp+100h] [rbp+0h]
  __int64 v30; // [rsp+108h] [rbp+8h]
  char v31; // [rsp+110h] [rbp+10h]
  unsigned __int16 v32; // [rsp+118h] [rbp+18h]
  unsigned __int8 *v33; // [rsp+120h] [rbp+20h]
  _QWORD v34[3]; // [rsp+130h] [rbp+30h] BYREF
  int v35; // [rsp+148h] [rbp+48h]
  __int64 v36; // [rsp+150h] [rbp+50h]
  __int64 v37; // [rsp+158h] [rbp+58h]
  char v38; // [rsp+160h] [rbp+60h]
  unsigned __int16 v39; // [rsp+168h] [rbp+68h]
  unsigned __int8 *v40; // [rsp+170h] [rbp+70h]
  unsigned __int16 v41; // [rsp+1C8h] [rbp+C8h] BYREF

  v20[0] = &tpm12class::TPMW82B_BUFFER::`vftable';
  v34[0] = &tpm12class::TPMW82B_BUFFER::`vftable';
  v27[0] = &tpm12class::TPMW82B_BUFFER::`vftable';
  v13[0] = &tpm12class::TPMW82B_BUFFER::`vftable';
  v20[1] = 0;
  v20[2] = 0;
  v21 = 0;
  v22 = 0;
  v23 = 0;
  v24 = 0;
  v25 = 0;
  v26 = 0;
  v34[1] = 0;
  v34[2] = 0;
  v35 = 0;
  v36 = 0;
  v37 = 0;
  v38 = 0;
  v39 = 0;
  v40 = 0;
  v27[1] = 0;
  v27[2] = 0;
  v28 = 0;
  v29 = 0;
  v30 = 0;
  v31 = 0;
  v32 = 0;
  v33 = 0;
  v13[1] = 0;
  v13[2] = 0;
  v14 = 0;
  v15 = 0;
  v16 = 0;
  v17 = 0;
  v18 = 0;
  v19 = 0;
  if ( !*((_BYTE *)a2 + 760) )
  {
    v4 = *((_DWORD *)this + 19) + *((_DWORD *)this + 18);
    v41 = 0;
    v5 = tpm12class::TpmDataObject::PeekDataAtOffset(this, v4, &v41);
    if ( v5 < 0 )
    {
LABEL_12:
      tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER((tpm12class::TPMW82B_BUFFER *)v13);
      tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER((tpm12class::TPMW82B_BUFFER *)v27);
      tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER((tpm12class::TPMW82B_BUFFER *)v34);
      tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER((tpm12class::TPMW82B_BUFFER *)v20);
      return (unsigned int)v5;
    }
    if ( v41 && (unsigned int)v41 <= *((_DWORD *)this + 4) )
    {
      v5 = tpm12class::TPMW82B_BUFFER::Allocate((tpm12class::TPMW82B_BUFFER *)v20, v41);
      if ( v5 < 0 )
        goto LABEL_12;
      v5 = tpm12class::TpmDataObject::PeekDataAtOffset(
             this,
             *((_DWORD *)this + 18) + 2 + *((_DWORD *)this + 19),
             v26,
             v25);
      if ( v5 < 0 )
        goto LABEL_12;
      if ( *((_BYTE *)a2 + 760) )
      {
        v5 = -2147023537;
        goto LABEL_12;
      }
      v5 = tpm12class::TPMW8_AUTH_PROVIDER::CalcParamEncryptionKey(
             *((tpm12class::TPMW8_AUTH_PROVIDER **)a2 + 97),
             (struct tpm12class::TPMW82B_BUFFER *)v20,
             (struct tpm12class::TPMW8_SESSION *)((char *)a2 + 24),
             (struct tpm12class::TPMW82B_BUFFER *)v34,
             (struct tpm12class::TPMW82B_BUFFER *)v27);
      if ( v5 < 0 )
        goto LABEL_12;
      v6 = *((_DWORD *)this + 18);
      v41 = 0;
      v5 = tpm12class::TpmDataObject::PeekDataAtOffset(this, v6, &v41);
      if ( v5 < 0 || !v41 )
        goto LABEL_12;
      v8 = v41;
      if ( (unsigned int)v41 <= *((_DWORD *)this + 4) )
      {
        v9 = v41;
        v5 = tpm12class::TPMW82B_BUFFER::Allocate((tpm12class::TPMW8_COMMAND *)((char *)this + 88), v41);
        if ( v5 < 0 )
          goto LABEL_12;
        v5 = tpm12class::TPMW82B_BUFFER::Allocate((tpm12class::TPMW82B_BUFFER *)v13, v9);
        if ( v5 < 0 )
          goto LABEL_12;
        v5 = tpm12class::TpmDataObject::PeekDataAtOffset(
               this,
               *((_DWORD *)this + 18) + 2,
               *((unsigned __int8 **)this + 19),
               *((unsigned __int16 *)this + 72));
        if ( v5 < 0 )
          goto LABEL_12;
        if ( g_fpAesCfbDecrypt )
        {
          v10 = g_fpAesCfbDecrypt(*((unsigned __int8 **)this + 19), v8, v40, v39, v33, v32, v19);
          v11 = v10;
          if ( !v10 )
            goto LABEL_28;
          if ( (v10 & 0xFFFF000) == 0x290000 )
          {
            v5 = v10 & 0xFFF | 0x80280000;
            goto LABEL_26;
          }
          if ( (v10 & 0xFFF0000) == 0x70000 )
          {
            v5 = (unsigned __int16)v10;
            v12 = 0;
            if ( !(_WORD)v10 )
              goto LABEL_27;
            v5 = (unsigned __int16)v10 | 0x80070000;
LABEL_26:
            v12 = v5 < 0;
LABEL_27:
            if ( v12 )
              goto LABEL_12;
LABEL_28:
            v5 = tpm12class::TpmDataObject::SetData(this, v19, v18, *((_DWORD *)this + 18) + 2);
            goto LABEL_12;
          }
        }
        else
        {
          v11 = -1073741822;
        }
        v5 = v11 | 0x10000000;
        goto LABEL_26;
      }
    }
  }
  tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER((tpm12class::TPMW82B_BUFFER *)v13);
  tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER((tpm12class::TPMW82B_BUFFER *)v27);
  tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER((tpm12class::TPMW82B_BUFFER *)v34);
  tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER((tpm12class::TPMW82B_BUFFER *)v20);
  return 2147943759LL;
}

```

## disassembly

```asm
0x140036188  push    rbp
0x14003618a  push    rbx
0x14003618b  push    rsi
0x14003618c  push    rdi
0x14003618d  push    r14
0x14003618f  push    r15
0x140036191  lea     rbp, [rsp-88h]
0x140036199  sub     rsp, 188h
0x1400361a0  xor     r15d, r15d
0x1400361a3  mov     rdi, rcx
0x1400361a6  lea     rcx, ??_7TPMW82B_BUFFER@tpm12class@@6B@; const tpm12class::TPMW82B_BUFFER::`vftable'
0x1400361ad  mov     rsi, rdx
0x1400361b0  mov     [rbp+0B0h+var_120], rcx
0x1400361b4  mov     [rbp+0B0h+var_80], rcx
0x1400361b8  mov     [rbp+0B0h+var_D0], rcx
0x1400361bc  mov     [rsp+1B0h+var_170], rcx
0x1400361c1  mov     [rbp+0B0h+var_118], r15
0x1400361c5  mov     [rbp+0B0h+var_110], r15
0x1400361c9  mov     [rbp+0B0h+var_108], r15d
0x1400361cd  mov     [rbp+0B0h+var_100], r15
0x1400361d1  mov     [rbp+0B0h+var_F8], r15
0x1400361d5  mov     [rbp+0B0h+var_F0], r15b
0x1400361d9  mov     [rbp+0B0h+var_E8], r15w
0x1400361de  mov     [rbp+0B0h+var_E0], r15
0x1400361e2  mov     [rbp+0B0h+var_78], r15
0x1400361e6  mov     [rbp+0B0h+var_70], r15
0x1400361ea  mov     [rbp+0B0h+var_68], r15d
0x1400361ee  mov     [rbp+0B0h+var_60], r15
0x1400361f2  mov     [rbp+0B0h+var_58], r15
0x1400361f6  mov     [rbp+0B0h+var_50], r15b
0x1400361fa  mov     [rbp+0B0h+var_48], r15w
0x1400361ff  mov     [rbp+0B0h+var_40], r15
0x140036203  mov     [rbp+0B0h+var_C8], r15
0x140036207  mov     [rbp+0B0h+var_C0], r15
0x14003620b  mov     [rbp+0B0h+var_B8], r15d
0x14003620f  mov     [rbp+0B0h+var_B0], r15
0x140036213  mov     [rbp+0B0h+var_A8], r15
0x140036217  mov     [rbp+0B0h+var_A0], r15b
0x14003621b  mov     [rbp+0B0h+var_98], r15w
0x140036220  mov     [rbp+0B0h+var_90], r15
0x140036224  mov     [rsp+1B0h+var_168], r15
0x140036229  mov     [rsp+1B0h+var_160], r15
0x14003622e  mov     [rsp+1B0h+var_158], r15d
0x140036233  mov     [rsp+1B0h+var_150], r15
0x140036238  mov     [rsp+1B0h+var_148], r15
0x14003623d  mov     [rsp+1B0h+var_140], r15b
0x140036242  mov     [rsp+1B0h+var_138], r15w
0x140036248  mov     [rbp+0B0h+var_130], r15
0x14003624c  cmp     [rdx+2F8h], r15b
0x140036253  jnz     loc_140036467
0x140036259  mov     edx, [rdi+48h]
0x14003625c  lea     r8, [rbp+0B0h+arg_8]; unsigned __int16 *
0x140036263  add     edx, [rdi+4Ch]; unsigned int
0x140036266  mov     rcx, rdi; this
0x140036269  mov     [rbp+0B0h+arg_8], r15w
0x140036271  call    ?PeekDataAtOffset@TpmDataObject@tpm12class@@QEAAJIPEAG@Z; tpm12class::TpmDataObject::PeekDataAtOffset(uint,ushort *)
0x140036276  mov     ebx, eax
0x140036278  test    eax, eax
0x14003627a  js      loc_140036333
0x140036280  movzx   ecx, [rbp+0B0h+arg_8]
0x140036287  test    cx, cx
0x14003628a  jz      loc_140036467
0x140036290  cmp     ecx, [rdi+10h]
0x140036293  ja      loc_140036467
0x140036299  mov     edx, ecx; unsigned __int64
0x14003629b  lea     rcx, [rbp+0B0h+var_120]; this
0x14003629f  call    ?Allocate@TPMW82B_BUFFER@tpm12class@@QEAAJ_K@Z; tpm12class::TPMW82B_BUFFER::Allocate(unsigned __int64)
0x1400362a4  mov     ebx, eax
0x1400362a6  test    eax, eax
0x1400362a8  js      loc_140036333
0x1400362ae  mov     ecx, [rdi+48h]
0x1400362b1  mov     edx, [rdi+4Ch]
0x1400362b4  add     ecx, 2
0x1400362b7  movzx   r9d, [rbp+0B0h+var_E8]; unsigned int
0x1400362bc  add     edx, ecx; unsigned int
0x1400362be  mov     r8, [rbp+0B0h+var_E0]; unsigned __int8 *
0x1400362c2  mov     rcx, rdi; this
0x1400362c5  call    ?PeekDataAtOffset@TpmDataObject@tpm12class@@QEAAJIPEAEI@Z; tpm12class::TpmDataObject::PeekDataAtOffset(uint,uchar *,uint)
0x1400362ca  mov     ebx, eax
0x1400362cc  test    eax, eax
0x1400362ce  js      short loc_140036333
0x1400362d0  cmp     [rsi+2F8h], r15b
0x1400362d7  jz      short loc_1400362E0
0x1400362d9  mov     ebx, 8007054Fh
0x1400362de  jmp     short loc_140036333
0x1400362e0  mov     rcx, [rsi+308h]; this
0x1400362e7  lea     rax, [rbp+0B0h+var_D0]
0x1400362eb  lea     r8, [rsi+18h]; struct tpm12class::TPMW82B_BUFFER *
0x1400362ef  mov     [rsp+1B0h+var_190], rax; struct tpm12class::TPMW82B_BUFFER *
0x1400362f4  lea     r9, [rbp+0B0h+var_80]; struct tpm12class::TPMW82B_BUFFER *
0x1400362f8  lea     rdx, [rbp+0B0h+var_120]; struct tpm12class::TPMW82B_BUFFER *
0x1400362fc  call    ?CalcParamEncryptionKey@TPMW8_AUTH_PROVIDER@tpm12class@@AEAAJPEAVTPMW82B_BUFFER@2@000@Z; tpm12class::TPMW8_AUTH_PROVIDER::CalcParamEncryptionKey(tpm12class::TPMW82B_BUFFER *,tpm12class::TPMW82B_BUFFER *,tpm12class::TPMW82B_BUFFER *,tpm12class::TPMW82B_BUFFER *)
0x140036301  mov     ebx, eax
0x140036303  test    eax, eax
0x140036305  js      short loc_140036333
0x140036307  mov     edx, [rdi+48h]; unsigned int
0x14003630a  lea     r8, [rbp+0B0h+arg_8]; unsigned __int16 *
0x140036311  mov     rcx, rdi; this
0x140036314  mov     [rbp+0B0h+arg_8], r15w
0x14003631c  call    ?PeekDataAtOffset@TpmDataObject@tpm12class@@QEAAJIPEAG@Z; tpm12class::TpmDataObject::PeekDataAtOffset(uint,ushort *)
0x140036321  mov     ebx, eax
0x140036323  test    eax, eax
0x140036325  js      short loc_140036333
0x140036327  movzx   eax, [rbp+0B0h+arg_8]
0x14003632e  test    ax, ax
0x140036331  jnz     short loc_14003635F
0x140036333  lea     rcx, [rsp+1B0h+var_170]; this
0x140036338  call    ??1TPMW82B_BUFFER@tpm12class@@UEAA@XZ; tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER(void)
0x14003633d  lea     rcx, [rbp+0B0h+var_D0]; this
0x140036341  call    ??1TPMW82B_BUFFER@tpm12class@@UEAA@XZ; tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER(void)
0x140036346  lea     rcx, [rbp+0B0h+var_80]; this
0x14003634a  call    ??1TPMW82B_BUFFER@tpm12class@@UEAA@XZ; tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER(void)
0x14003634f  lea     rcx, [rbp+0B0h+var_120]; this
0x140036353  call    ??1TPMW82B_BUFFER@tpm12class@@UEAA@XZ; tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER(void)
0x140036358  mov     eax, ebx
0x14003635a  jmp     loc_140036491
0x14003635f  mov     r14d, eax
0x140036362  cmp     eax, [rdi+10h]
0x140036365  ja      loc_140036467
0x14003636b  lea     rcx, [rdi+58h]; this
0x14003636f  mov     rdx, rax; unsigned __int64
0x140036372  mov     rsi, rax
0x140036375  call    ?Allocate@TPMW82B_BUFFER@tpm12class@@QEAAJ_K@Z; tpm12class::TPMW82B_BUFFER::Allocate(unsigned __int64)
0x14003637a  mov     ebx, eax
0x14003637c  test    eax, eax
0x14003637e  js      short loc_140036333
0x140036380  mov     rdx, rsi; unsigned __int64
0x140036383  lea     rcx, [rsp+1B0h+var_170]; this
0x140036388  call    ?Allocate@TPMW82B_BUFFER@tpm12class@@QEAAJ_K@Z; tpm12class::TPMW82B_BUFFER::Allocate(unsigned __int64)
0x14003638d  mov     ebx, eax
0x14003638f  test    eax, eax
0x140036391  js      short loc_140036333
0x140036393  mov     edx, [rdi+48h]
0x140036396  mov     rcx, rdi; this
0x140036399  movzx   r9d, word ptr [rdi+90h]; unsigned int
0x1400363a1  add     edx, 2; unsigned int
0x1400363a4  mov     r8, [rdi+98h]; unsigned __int8 *
0x1400363ab  call    ?PeekDataAtOffset@TpmDataObject@tpm12class@@QEAAJIPEAEI@Z; tpm12class::TpmDataObject::PeekDataAtOffset(uint,uchar *,uint)
0x1400363b0  mov     ebx, eax
0x1400363b2  test    eax, eax
0x1400363b4  js      loc_140036333
0x1400363ba  mov     rax, cs:?g_fpAesCfbDecrypt@@3P6AJPEAEI0I0I0@ZEA; long (*g_fpAesCfbDecrypt)(uchar *,uint,uchar *,uint,uchar *,uint,uchar *)
0x1400363c1  test    rax, rax
0x1400363c4  jz      short loc_140036435
0x1400363c6  movzx   ecx, [rbp+0B0h+var_98]
0x1400363ca  mov     edx, r14d
0x1400363cd  mov     r10, [rbp+0B0h+var_130]
0x1400363d1  mov     r11, [rbp+0B0h+var_90]
0x1400363d5  movzx   r9d, [rbp+0B0h+var_48]
0x1400363da  mov     r8, [rbp+0B0h+var_40]
0x1400363de  mov     [rsp+1B0h+var_180], r10
0x1400363e3  mov     [rsp+1B0h+var_188], ecx
0x1400363e7  mov     rcx, [rdi+98h]
0x1400363ee  mov     [rsp+1B0h+var_190], r11
0x1400363f3  call    _guard_dispatch_icall
0x1400363f8  mov     ebx, eax
0x1400363fa  test    eax, eax
0x1400363fc  jz      short loc_140036446
0x1400363fe  and     eax, 0FFFF000h
0x140036403  cmp     eax, 290000h
0x140036408  jnz     short loc_140036418
0x14003640a  and     ebx, 0FFFh
0x140036410  or      ebx, 80280000h
0x140036416  jmp     short loc_14003643E
0x140036418  mov     eax, ebx
0x14003641a  and     eax, 0FFF0000h
0x14003641f  cmp     eax, 70000h
0x140036424  jnz     short loc_14003643A
0x140036426  movzx   ebx, bx
0x140036429  test    ebx, ebx
0x14003642b  jz      short loc_140036440
0x14003642d  or      ebx, 80070000h
0x140036433  jmp     short loc_14003643E
0x140036435  mov     ebx, 0C0000002h
0x14003643a  bts     ebx, 1Ch
0x14003643e  test    ebx, ebx
0x140036440  js      loc_140036333
0x140036446  mov     r9d, [rdi+48h]
0x14003644a  mov     rcx, rdi; this
0x14003644d  movzx   r8d, [rsp+1B0h+var_138]; unsigned int
0x140036453  add     r9d, 2; unsigned int
0x140036457  mov     rdx, [rbp+0B0h+var_130]; unsigned __int8 *
0x14003645b  call    ?SetData@TpmDataObject@tpm12class@@QEAAJPEAEII@Z; tpm12class::TpmDataObject::SetData(uchar *,uint,uint)
0x140036460  mov     ebx, eax
0x140036462  jmp     loc_140036333
0x140036467  lea     rcx, [rsp+1B0h+var_170]; this
0x14003646c  call    ??1TPMW82B_BUFFER@tpm12class@@UEAA@XZ; tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER(void)
0x140036471  lea     rcx, [rbp+0B0h+var_D0]; this
0x140036475  call    ??1TPMW82B_BUFFER@tpm12class@@UEAA@XZ; tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER(void)
0x14003647a  lea     rcx, [rbp+0B0h+var_80]; this
0x14003647e  call    ??1TPMW82B_BUFFER@tpm12class@@UEAA@XZ; tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER(void)
0x140036483  lea     rcx, [rbp+0B0h+var_120]; this
0x140036487  call    ??1TPMW82B_BUFFER@tpm12class@@UEAA@XZ; tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER(void)
0x14003648c  mov     eax, 8007054Fh
0x140036491  add     rsp, 188h
0x140036498  pop     r15
0x14003649a  pop     r14
0x14003649c  pop     rdi
0x14003649d  pop     rsi
0x14003649e  pop     rbx
0x14003649f  pop     rbp
0x1400364a0  retn
```
