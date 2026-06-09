# tpm12class::TPMW8_COMMAND::EncryptFirstParameter(tpm12class::TPMW8_SESSION *)

- ea: `0x140036534`
- end: `0x1400367d1`
- name: `?EncryptFirstParameter@TPMW8_COMMAND@tpm12class@@IEAAJPEAVTPMW8_SESSION@2@@Z`
- size: `669`
- prototype: `__int64 __fastcall(tpm12class::TPMW8_COMMAND *this, tpm12class::TPMW8_AUTH_PROVIDER **)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x140036a30`

## callees

- `0x14000da40`
- `0x140031008`
- `0x140031c14`
- `0x1400320d4`
- `0x140032114`
- `0x140032214`
- `0x140032300`
- `0x140032340`
- `0x140035ac4`
- `0x140036534`

## pseudocode

```c
__int64 __fastcall tpm12class::TPMW8_COMMAND::EncryptFirstParameter(
        tpm12class::TPMW8_COMMAND *this,
        tpm12class::TPMW8_AUTH_PROVIDER **a2)
{
  int v3; // ebx
  unsigned int v4; // edx
  unsigned int v5; // r10d
  __int64 v6; // r10
  int v8; // eax
  bool v9; // sf
  _QWORD v10[3]; // [rsp+40h] [rbp-C0h] BYREF
  int v11; // [rsp+58h] [rbp-A8h]
  __int64 v12; // [rsp+60h] [rbp-A0h]
  __int64 v13; // [rsp+68h] [rbp-98h]
  char v14; // [rsp+70h] [rbp-90h]
  unsigned __int16 v15; // [rsp+78h] [rbp-88h]
  unsigned __int8 *v16; // [rsp+80h] [rbp-80h]
  _QWORD v17[3]; // [rsp+90h] [rbp-70h] BYREF
  int v18; // [rsp+A8h] [rbp-58h]
  __int64 v19; // [rsp+B0h] [rbp-50h]
  __int64 v20; // [rsp+B8h] [rbp-48h]
  char v21; // [rsp+C0h] [rbp-40h]
  unsigned __int16 v22; // [rsp+C8h] [rbp-38h]
  unsigned __int8 *v23; // [rsp+D0h] [rbp-30h]
  _QWORD v24[3]; // [rsp+E0h] [rbp-20h] BYREF
  int v25; // [rsp+F8h] [rbp-8h]
  __int64 v26; // [rsp+100h] [rbp+0h]
  __int64 v27; // [rsp+108h] [rbp+8h]
  char v28; // [rsp+110h] [rbp+10h]
  unsigned __int16 v29; // [rsp+118h] [rbp+18h]
  unsigned __int8 *v30; // [rsp+120h] [rbp+20h]
  unsigned __int16 v31; // [rsp+168h] [rbp+68h] BYREF

  v24[0] = &tpm12class::TPMW82B_BUFFER::`vftable';
  v17[0] = &tpm12class::TPMW82B_BUFFER::`vftable';
  v10[0] = &tpm12class::TPMW82B_BUFFER::`vftable';
  v24[1] = 0;
  v24[2] = 0;
  v25 = 0;
  v26 = 0;
  v27 = 0;
  v28 = 0;
  v29 = 0;
  v30 = 0;
  v17[1] = 0;
  v17[2] = 0;
  v18 = 0;
  v19 = 0;
  v20 = 0;
  v21 = 0;
  v22 = 0;
  v23 = 0;
  v10[1] = 0;
  v10[2] = 0;
  v11 = 0;
  v12 = 0;
  v13 = 0;
  v14 = 0;
  v15 = 0;
  v16 = 0;
  if ( !*((_BYTE *)a2 + 760) )
  {
    v3 = tpm12class::TPMW8_AUTH_PROVIDER::CalcParamEncryptionKey(
           a2[97],
           (struct tpm12class::TPMW82B_BUFFER *)(a2 + 3),
           (struct tpm12class::TPMW82B_BUFFER *)(a2 + 12),
           (struct tpm12class::TPMW82B_BUFFER *)v24,
           (struct tpm12class::TPMW82B_BUFFER *)v17);
    if ( v3 < 0 )
      goto LABEL_24;
    v4 = *((_DWORD *)this + 18);
    if ( v4 && *((_DWORD *)this + 20) )
    {
      v31 = 0;
      v3 = tpm12class::TpmDataObject::PeekDataAtOffset(this, v4, &v31);
      if ( v3 < 0 )
        goto LABEL_24;
      if ( (int)anonymous_namespace_::CheckBufferReadSize_unsigned___int64_unsigned_int_(
                  *((unsigned int *)this + 10),
                  v5,
                  2) < 0 )
      {
        v3 = -2147024774;
        goto LABEL_24;
      }
      if ( v31 == ((unsigned __int16)(*(_WORD *)(*((_QWORD *)this + 4) + v6) << 8)
                 | *(unsigned __int8 *)(*((_QWORD *)this + 4) + v6 + 1)) )
      {
        if ( !v31 )
        {
          tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER((tpm12class::TPMW82B_BUFFER *)v10);
          tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER((tpm12class::TPMW82B_BUFFER *)v17);
          tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER((tpm12class::TPMW82B_BUFFER *)v24);
          return 0;
        }
        v3 = tpm12class::TPMW82B_BUFFER::Allocate((tpm12class::TPMW82B_BUFFER *)v10, v31);
        if ( v3 < 0 )
          goto LABEL_24;
        v3 = tpm12class::TpmDataObject::PeekDataAtOffset(this, *((_DWORD *)this + 18) + 2, v16, v15);
        if ( v3 < 0 )
          goto LABEL_24;
        v8 = PlatformAesCfbEncrypt(v16, v31, v30, v29, v23, v22, v16);
        if ( !v8 )
          goto LABEL_21;
        if ( (v8 & 0xFFFF000) == 0x290000 )
        {
          v3 = v8 & 0xFFF | 0x80280000;
        }
        else if ( (v8 & 0xFFF0000) == 0x70000 )
        {
          v3 = (unsigned __int16)v8;
          v9 = 0;
          if ( !(_WORD)v8 )
            goto LABEL_20;
          v3 = (unsigned __int16)v8 | 0x80070000;
        }
        else
        {
          v3 = v8 | 0x10000000;
        }
        v9 = v3 < 0;
LABEL_20:
        if ( !v9 )
        {
LABEL_21:
          v3 = tpm12class::TpmDataObject::SetData(this, v16, v15, *((_DWORD *)this + 18) + 2);
          if ( v3 >= 0 )
            v3 = tpm12class::TpmDataObject::SetHashData(this, v16, v15, *((_DWORD *)this + 20) + 2);
        }
LABEL_24:
        tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER((tpm12class::TPMW82B_BUFFER *)v10);
        tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER((tpm12class::TPMW82B_BUFFER *)v17);
        tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER((tpm12class::TPMW82B_BUFFER *)v24);
        return (unsigned int)v3;
      }
    }
  }
  tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER((tpm12class::TPMW82B_BUFFER *)v10);
  tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER((tpm12class::TPMW82B_BUFFER *)v17);
  tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER((tpm12class::TPMW82B_BUFFER *)v24);
  return 2147943759LL;
}

```

## disassembly

```asm
0x140036534  push    rbp
0x140036536  push    rbx
0x140036537  push    rdi
0x140036538  push    r14
0x14003653a  lea     rbp, [rsp-38h]
0x14003653f  sub     rsp, 138h
0x140036546  xor     r14d, r14d
0x140036549  mov     rdi, rcx
0x14003654c  lea     rcx, ??_7TPMW82B_BUFFER@tpm12class@@6B@; const tpm12class::TPMW82B_BUFFER::`vftable'
0x140036553  mov     r10, rdx
0x140036556  mov     [rbp+50h+var_70], rcx
0x14003655a  mov     [rbp+50h+var_C0], rcx
0x14003655e  mov     [rsp+150h+var_110], rcx
0x140036563  mov     [rbp+50h+var_68], r14
0x140036567  mov     [rbp+50h+var_60], r14
0x14003656b  mov     [rbp+50h+var_58], r14d
0x14003656f  mov     [rbp+50h+var_50], r14
0x140036573  mov     [rbp+50h+var_48], r14
0x140036577  mov     [rbp+50h+var_40], r14b
0x14003657b  mov     [rbp+50h+var_38], r14w
0x140036580  mov     [rbp+50h+var_30], r14
0x140036584  mov     [rbp+50h+var_B8], r14
0x140036588  mov     [rbp+50h+var_B0], r14
0x14003658c  mov     [rbp+50h+var_A8], r14d
0x140036590  mov     [rbp+50h+var_A0], r14
0x140036594  mov     [rbp+50h+var_98], r14
0x140036598  mov     [rbp+50h+var_90], r14b
0x14003659c  mov     [rbp+50h+var_88], r14w
0x1400365a1  mov     [rbp+50h+var_80], r14
0x1400365a5  mov     [rsp+150h+var_108], r14
0x1400365aa  mov     [rsp+150h+var_100], r14
0x1400365af  mov     [rsp+150h+var_F8], r14d
0x1400365b4  mov     [rsp+150h+var_F0], r14
0x1400365b9  mov     [rsp+150h+var_E8], r14
0x1400365be  mov     [rsp+150h+var_E0], r14b
0x1400365c3  mov     [rsp+150h+var_D8], r14w
0x1400365c9  mov     [rbp+50h+var_D0], r14
0x1400365cd  cmp     [rdx+2F8h], r14b
0x1400365d4  jnz     loc_1400367A2
0x1400365da  mov     rcx, [r10+308h]; this
0x1400365e1  lea     r8, [rdx+60h]; struct tpm12class::TPMW82B_BUFFER *
0x1400365e5  lea     rax, [rbp+50h+var_C0]
0x1400365e9  add     rdx, 18h; struct tpm12class::TPMW82B_BUFFER *
0x1400365ed  lea     r9, [rbp+50h+var_70]; struct tpm12class::TPMW82B_BUFFER *
0x1400365f1  mov     [rsp+150h+var_130], rax; struct tpm12class::TPMW82B_BUFFER *
0x1400365f6  call    ?CalcParamEncryptionKey@TPMW8_AUTH_PROVIDER@tpm12class@@AEAAJPEAVTPMW82B_BUFFER@2@000@Z; tpm12class::TPMW8_AUTH_PROVIDER::CalcParamEncryptionKey(tpm12class::TPMW82B_BUFFER *,tpm12class::TPMW82B_BUFFER *,tpm12class::TPMW82B_BUFFER *,tpm12class::TPMW82B_BUFFER *)
0x1400365fb  mov     ebx, eax
0x1400365fd  test    eax, eax
0x1400365ff  js      loc_140036782
0x140036605  mov     edx, [rdi+48h]; unsigned int
0x140036608  test    edx, edx
0x14003660a  jz      loc_1400367A2
0x140036610  mov     r10d, [rdi+50h]
0x140036614  test    r10d, r10d
0x140036617  jz      loc_1400367A2
0x14003661d  lea     r8, [rbp+50h+arg_8]; unsigned __int16 *
0x140036621  mov     [rbp+50h+arg_8], r14w
0x140036626  mov     rcx, rdi; this
0x140036629  call    ?PeekDataAtOffset@TpmDataObject@tpm12class@@QEAAJIPEAG@Z; tpm12class::TpmDataObject::PeekDataAtOffset(uint,ushort *)
0x14003662e  mov     ebx, eax
0x140036630  test    eax, eax
0x140036632  js      loc_140036782
0x140036638  mov     ecx, [rdi+28h]
0x14003663b  lea     r8d, [r14+2]
0x14003663f  mov     edx, r10d
0x140036642  call    _anonymous_namespace___CheckBufferReadSize_unsigned___int64_unsigned_int_
0x140036647  test    eax, eax
0x140036649  js      loc_14003677D
0x14003664f  mov     rax, [rdi+20h]
0x140036653  movzx   edx, byte ptr [rax+r10+1]
0x140036659  movzx   eax, word ptr [rax+r10]
0x14003665e  shl     ax, 8
0x140036662  or      dx, ax
0x140036665  cmp     [rbp+50h+arg_8], dx
0x140036669  jnz     loc_1400367A2
0x14003666f  lea     rcx, [rsp+150h+var_110]; this
0x140036674  cmp     [rbp+50h+arg_8], r14w
0x140036679  jnz     short loc_140036699
0x14003667b  call    ??1TPMW82B_BUFFER@tpm12class@@UEAA@XZ; tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER(void)
0x140036680  lea     rcx, [rbp+50h+var_C0]; this
0x140036684  call    ??1TPMW82B_BUFFER@tpm12class@@UEAA@XZ; tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER(void)
0x140036689  lea     rcx, [rbp+50h+var_70]; this
0x14003668d  call    ??1TPMW82B_BUFFER@tpm12class@@UEAA@XZ; tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER(void)
0x140036692  xor     eax, eax
0x140036694  jmp     loc_1400367C3
0x140036699  movzx   edx, [rbp+50h+arg_8]; unsigned __int64
0x14003669d  call    ?Allocate@TPMW82B_BUFFER@tpm12class@@QEAAJ_K@Z; tpm12class::TPMW82B_BUFFER::Allocate(unsigned __int64)
0x1400366a2  mov     ebx, eax
0x1400366a4  test    eax, eax
0x1400366a6  js      loc_140036782
0x1400366ac  mov     edx, [rdi+48h]
0x1400366af  mov     rcx, rdi; this
0x1400366b2  movzx   r9d, [rsp+150h+var_D8]; unsigned int
0x1400366b8  add     edx, 2; unsigned int
0x1400366bb  mov     r8, [rbp+50h+var_D0]; unsigned __int8 *
0x1400366bf  call    ?PeekDataAtOffset@TpmDataObject@tpm12class@@QEAAJIPEAEI@Z; tpm12class::TpmDataObject::PeekDataAtOffset(uint,uchar *,uint)
0x1400366c4  mov     ebx, eax
0x1400366c6  test    eax, eax
0x1400366c8  js      loc_140036782
0x1400366ce  movzx   eax, [rbp+50h+var_88]
0x1400366d2  mov     rcx, [rbp+50h+var_D0]; unsigned __int8 *
0x1400366d6  movzx   r9d, [rbp+50h+var_38]; unsigned int
0x1400366db  movzx   edx, [rbp+50h+arg_8]; unsigned int
0x1400366df  mov     r8, [rbp+50h+var_30]; unsigned __int8 *
0x1400366e3  mov     [rsp+150h+var_120], rcx; unsigned __int8 *
0x1400366e8  mov     [rsp+150h+var_128], eax; unsigned int
0x1400366ec  mov     rax, [rbp+50h+var_80]
0x1400366f0  mov     [rsp+150h+var_130], rax; unsigned __int8 *
0x1400366f5  call    ?PlatformAesCfbEncrypt@@YAJPEAEI0I0I0@Z; PlatformAesCfbEncrypt(uchar *,uint,uchar *,uint,uchar *,uint,uchar *)
0x1400366fa  mov     ebx, eax
0x1400366fc  test    eax, eax
0x1400366fe  jz      short loc_14003673F
0x140036700  and     eax, 0FFFF000h
0x140036705  cmp     eax, 290000h
0x14003670a  jnz     short loc_14003671A
0x14003670c  and     ebx, 0FFFh
0x140036712  or      ebx, 80280000h
0x140036718  jmp     short loc_14003673B
0x14003671a  mov     eax, ebx
0x14003671c  and     eax, 0FFF0000h
0x140036721  cmp     eax, 70000h
0x140036726  jnz     short loc_140036737
0x140036728  movzx   ebx, bx
0x14003672b  test    ebx, ebx
0x14003672d  jz      short loc_14003673D
0x14003672f  or      ebx, 80070000h
0x140036735  jmp     short loc_14003673B
0x140036737  bts     ebx, 1Ch
0x14003673b  test    ebx, ebx
0x14003673d  js      short loc_140036782
0x14003673f  mov     r9d, [rdi+48h]
0x140036743  mov     rcx, rdi; this
0x140036746  movzx   r8d, [rsp+150h+var_D8]; unsigned int
0x14003674c  add     r9d, 2; unsigned int
0x140036750  mov     rdx, [rbp+50h+var_D0]; unsigned __int8 *
0x140036754  call    ?SetData@TpmDataObject@tpm12class@@QEAAJPEAEII@Z; tpm12class::TpmDataObject::SetData(uchar *,uint,uint)
0x140036759  mov     ebx, eax
0x14003675b  test    eax, eax
0x14003675d  js      short loc_140036782
0x14003675f  mov     r9d, [rdi+50h]
0x140036763  mov     rcx, rdi; this
0x140036766  movzx   r8d, [rsp+150h+var_D8]; unsigned int
0x14003676c  add     r9d, 2; unsigned int
0x140036770  mov     rdx, [rbp+50h+var_D0]; unsigned __int8 *
0x140036774  call    ?SetHashData@TpmDataObject@tpm12class@@QEAAJPEAEII@Z; tpm12class::TpmDataObject::SetHashData(uchar *,uint,uint)
0x140036779  mov     ebx, eax
0x14003677b  jmp     short loc_140036782
0x14003677d  mov     ebx, 8007007Ah
0x140036782  lea     rcx, [rsp+150h+var_110]; this
0x140036787  call    ??1TPMW82B_BUFFER@tpm12class@@UEAA@XZ; tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER(void)
0x14003678c  lea     rcx, [rbp+50h+var_C0]; this
0x140036790  call    ??1TPMW82B_BUFFER@tpm12class@@UEAA@XZ; tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER(void)
0x140036795  lea     rcx, [rbp+50h+var_70]; this
0x140036799  call    ??1TPMW82B_BUFFER@tpm12class@@UEAA@XZ; tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER(void)
0x14003679e  mov     eax, ebx
0x1400367a0  jmp     short loc_1400367C3
0x1400367a2  lea     rcx, [rsp+150h+var_110]; this
0x1400367a7  call    ??1TPMW82B_BUFFER@tpm12class@@UEAA@XZ; tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER(void)
0x1400367ac  lea     rcx, [rbp+50h+var_C0]; this
0x1400367b0  call    ??1TPMW82B_BUFFER@tpm12class@@UEAA@XZ; tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER(void)
0x1400367b5  lea     rcx, [rbp+50h+var_70]; this
0x1400367b9  call    ??1TPMW82B_BUFFER@tpm12class@@UEAA@XZ; tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER(void)
0x1400367be  mov     eax, 8007054Fh
0x1400367c3  add     rsp, 138h
0x1400367ca  pop     r14
0x1400367cc  pop     rdi
0x1400367cd  pop     rbx
0x1400367ce  pop     rbp
0x1400367cf  retn
```
