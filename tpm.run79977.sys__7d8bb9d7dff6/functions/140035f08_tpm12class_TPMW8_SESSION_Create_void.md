# tpm12class::TPMW8_SESSION::Create(void *)

- ea: `0x140035f08`
- end: `0x14003617f`
- name: `?Create@TPMW8_SESSION@tpm12class@@QEAAJPEAX@Z`
- size: `631`
- prototype: `__int64 __fastcall(tpm12class::TPMW8_SESSION *__hidden this, void *)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x1400367d8`

## callees

- `0x14000cb50`
- `0x140031284`
- `0x140031554`
- `0x140032390`
- `0x14003535c`
- `0x140035c24`
- `0x140035f08`
- `0x1400367d8`
- `0x140036d58`
- `0x1400382b0`
- `0x1400383e8`
- `0x140039b40`
- `0x1400454a0`

## pseudocode

```c
__int64 __fastcall tpm12class::TPMW8_SESSION::Create(tpm12class::TPMW8_SESSION *this, void *a2)
{
  __int64 v4; // rcx
  int inited; // ebx
  _WORD *v6; // rsi
  int Random; // eax
  void *v8; // rcx
  void *v9; // rax
  _BYTE v11[192]; // [rsp+20h] [rbp-E0h] BYREF
  int v12; // [rsp+E0h] [rbp-20h]
  int v13; // [rsp+E4h] [rbp-1Ch]
  _BYTE v14[80]; // [rsp+E8h] [rbp-18h] BYREF
  _BYTE v15[72]; // [rsp+138h] [rbp+38h] BYREF
  _BYTE v16[72]; // [rsp+180h] [rbp+80h] BYREF
  __int16 v17; // [rsp+1C8h] [rbp+C8h]
  int v18; // [rsp+1CCh] [rbp+CCh]
  _BYTE v19[128]; // [rsp+1D0h] [rbp+D0h] BYREF

  tpm12class::TPMW8_StartAuthSession::TPMW8_StartAuthSession((tpm12class::TPMW8_StartAuthSession *)v11);
  v4 = *((_QWORD *)this + 97);
  if ( !v4 )
  {
    inited = -2147024883;
    goto LABEL_35;
  }
  *((_QWORD *)this + 94) = a2;
  if ( *((_BYTE *)this + 760) )
  {
    *((_DWORD *)this + 4) = 1073741833;
    tpm12class::TPMW82B_BUFFER::Empty((tpm12class::TPMW8_SESSION *)((char *)this + 24));
    *((_BYTE *)this + 764) = 0;
LABEL_5:
    inited = 0;
    goto LABEL_35;
  }
  *(_WORD *)(v4 + 370) = *((_WORD *)this + 381);
  if ( *((_DWORD *)this + 4) )
    goto LABEL_5;
  if ( (*((_BYTE *)this + 764) & 0x60) != 0 )
  {
    *((_DWORD *)this + 184) = 8388614;
    *((_WORD *)this + 370) = 67;
  }
  if ( *((_WORD *)this + 40) || (inited = tpm12class::TPMW8_SESSION::InitNonceCaller(this), inited >= 0) )
  {
    v12 = *((_DWORD *)this + 151);
    v13 = *((_DWORD *)this + 192);
    inited = tpm12class::TPMW82B_BUFFER::CopyFrom(
               (tpm12class::TPMW82B_BUFFER *)v14,
               (tpm12class::TPMW8_SESSION *)((char *)this + 24));
    if ( inited >= 0 )
    {
      v14[72] = *((_BYTE *)this + 761);
      inited = tpm12class::TPMW82B_BUFFER::CopyFrom(
                 (tpm12class::TPMW82B_BUFFER *)v15,
                 (tpm12class::TPMW8_SESSION *)((char *)this + 608));
      if ( inited >= 0 )
      {
        tpm12class::TPMW8T_SYM_DEF::operator=(v16, (char *)this + 680);
        v17 = *((_WORD *)this + 381);
        inited = tpm12class::TPMW8_COMMAND::Execute((tpm12class::TPMW8_COMMAND *)v11, a2);
        if ( inited >= 0 )
        {
          *((_DWORD *)this + 4) = v18;
          tpm12class::TPMW82B_BUFFER::CopyFrom(
            (tpm12class::TPMW8_SESSION *)((char *)this + 96),
            (const struct tpm12class::TPMW82B_BUFFER *)v19);
          if ( *((_DWORD *)this + 192) != 1073741831 || *((_DWORD *)this + 151) != 1073741831 )
          {
            if ( *((_BYTE *)this + 784) )
            {
              inited = -2147024809;
              goto LABEL_35;
            }
            inited = tpm12class::TPMW8_AUTH_PROVIDER::CalcSessionKey(
                       *((tpm12class::TPMW8_AUTH_PROVIDER **)this + 97),
                       (tpm12class::TPMW8_SESSION *)((char *)this + 96),
                       (tpm12class::TPMW8_SESSION *)((char *)this + 24));
            if ( inited < 0 )
              goto LABEL_35;
          }
          if ( *((_BYTE *)this + 784) )
            goto LABEL_35;
          v6 = (_WORD *)((char *)this + 80);
          Random = PlatformGetRandom(*((unsigned __int8 **)this + 11), *((unsigned __int16 *)this + 40));
          if ( !Random )
          {
            inited = 0;
LABEL_30:
            v8 = (void *)*((_QWORD *)this + 65);
            *((_WORD *)this + 256) = *v6;
            if ( v8 )
            {
              TpmFree(v8);
              *((_QWORD *)this + 65) = 0;
            }
            v9 = operator new(*((unsigned __int16 *)this + 256));
            *((_QWORD *)this + 65) = v9;
            if ( v9 )
              memset(v9, 0, *((unsigned __int16 *)this + 256));
            else
              inited = -2147024888;
            goto LABEL_35;
          }
          if ( (Random & 0xFFFF000) == 0x290000 )
          {
            inited = Random & 0xFFF | 0x80280000;
          }
          else if ( (Random & 0xFFF0000) == 0x70000 )
          {
            inited = (unsigned __int16)Random;
            if ( (_WORD)Random )
              inited = (unsigned __int16)Random | 0x80070000;
            v6 = (_WORD *)((char *)this + 80);
          }
          else
          {
            inited = Random | 0x10000000;
          }
          if ( inited >= 0 )
            goto LABEL_30;
        }
      }
    }
  }
LABEL_35:
  tpm12class::TPMW8_StartAuthSession::~TPMW8_StartAuthSession((tpm12class::TPMW8_StartAuthSession *)v11);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x140035f08  push    rbp
0x140035f0a  push    rbx
0x140035f0b  push    rsi
0x140035f0c  push    rdi
0x140035f0d  push    r14
0x140035f0f  push    r15
0x140035f11  lea     rbp, [rsp-128h]
0x140035f19  sub     rsp, 228h
0x140035f20  mov     rdi, rcx
0x140035f23  mov     r14, rdx
0x140035f26  lea     rcx, [rsp+250h+var_230]; this
0x140035f2b  call    ??0TPMW8_StartAuthSession@tpm12class@@QEAA@XZ; tpm12class::TPMW8_StartAuthSession::TPMW8_StartAuthSession(void)
0x140035f30  mov     rcx, [rdi+308h]
0x140035f37  xor     r15d, r15d
0x140035f3a  test    rcx, rcx
0x140035f3d  jnz     short loc_140035F49
0x140035f3f  mov     ebx, 8007000Dh
0x140035f44  jmp     loc_140036162
0x140035f49  mov     [rdi+2F0h], r14
0x140035f50  cmp     [rdi+2F8h], r15b
0x140035f57  jz      short loc_140035F78
0x140035f59  lea     rcx, [rdi+18h]; this
0x140035f5d  mov     dword ptr [rdi+10h], 40000009h
0x140035f64  call    ?Empty@TPMW82B_BUFFER@tpm12class@@QEAAJXZ; tpm12class::TPMW82B_BUFFER::Empty(void)
0x140035f69  mov     [rdi+2FCh], r15b
0x140035f70  mov     ebx, r15d
0x140035f73  jmp     loc_140036162
0x140035f78  movzx   eax, word ptr [rdi+2FAh]
0x140035f7f  mov     [rcx+172h], ax
0x140035f86  cmp     [rdi+10h], r15d
0x140035f8a  jnz     short loc_140035F70
0x140035f8c  test    byte ptr [rdi+2FCh], 60h
0x140035f93  jz      short loc_140035FA8
0x140035f95  mov     dword ptr [rdi+2E0h], 800006h
0x140035f9f  mov     word ptr [rdi+2E4h], 43h ; 'C'
0x140035fa8  cmp     [rdi+50h], r15w
0x140035fad  jnz     short loc_140035FC1
0x140035faf  mov     rcx, rdi; this
0x140035fb2  call    ?InitNonceCaller@TPMW8_SESSION@tpm12class@@IEAAJXZ; tpm12class::TPMW8_SESSION::InitNonceCaller(void)
0x140035fb7  mov     ebx, eax
0x140035fb9  test    eax, eax
0x140035fbb  js      loc_140036162
0x140035fc1  mov     eax, [rdi+25Ch]
0x140035fc7  lea     rdx, [rdi+18h]; struct tpm12class::TPMW82B_BUFFER *
0x140035fcb  mov     [rbp+150h+var_170], eax
0x140035fce  lea     rcx, [rbp+150h+var_168]; this
0x140035fd2  mov     eax, [rdi+300h]
0x140035fd8  mov     [rbp+150h+var_16C], eax
0x140035fdb  call    ?CopyFrom@TPMW82B_BUFFER@tpm12class@@QEAAJPEBV12@@Z; tpm12class::TPMW82B_BUFFER::CopyFrom(tpm12class::TPMW82B_BUFFER const *)
0x140035fe0  mov     ebx, eax
0x140035fe2  test    eax, eax
0x140035fe4  js      loc_140036162
0x140035fea  mov     al, [rdi+2F9h]
0x140035ff0  lea     rdx, [rdi+260h]; struct tpm12class::TPMW82B_BUFFER *
0x140035ff7  lea     rcx, [rbp+150h+var_118]; this
0x140035ffb  mov     [rbp+150h+var_120], al
0x140035ffe  call    ?CopyFrom@TPMW82B_BUFFER@tpm12class@@QEAAJPEBV12@@Z; tpm12class::TPMW82B_BUFFER::CopyFrom(tpm12class::TPMW82B_BUFFER const *)
0x140036003  mov     ebx, eax
0x140036005  test    eax, eax
0x140036007  js      loc_140036162
0x14003600d  lea     rdx, [rdi+2A8h]
0x140036014  lea     rcx, [rbp+150h+var_D0]
0x14003601b  call    ??4TPMW8T_SYM_DEF@tpm12class@@QEAAAEAV01@AEBV01@@Z; tpm12class::TPMW8T_SYM_DEF::operator=(tpm12class::TPMW8T_SYM_DEF const &)
0x140036020  movzx   ecx, word ptr [rdi+2FAh]
0x140036027  mov     rdx, r14; void *
0x14003602a  mov     [rbp+150h+var_88], cx
0x140036031  lea     rcx, [rsp+250h+var_230]; this
0x140036036  call    ?Execute@TPMW8_COMMAND@tpm12class@@QEAAJPEAX@Z; tpm12class::TPMW8_COMMAND::Execute(void *)
0x14003603b  mov     ebx, eax
0x14003603d  test    eax, eax
0x14003603f  js      loc_140036162
0x140036045  mov     eax, [rbp+150h+var_84]
0x14003604b  lea     rdx, [rbp+150h+var_80]; struct tpm12class::TPMW82B_BUFFER *
0x140036052  lea     rcx, [rdi+60h]; this
0x140036056  mov     [rdi+10h], eax
0x140036059  call    ?CopyFrom@TPMW82B_BUFFER@tpm12class@@QEAAJPEBV12@@Z; tpm12class::TPMW82B_BUFFER::CopyFrom(tpm12class::TPMW82B_BUFFER const *)
0x14003605e  mov     eax, 40000007h
0x140036063  cmp     [rdi+300h], eax
0x140036069  jnz     short loc_140036073
0x14003606b  cmp     [rdi+25Ch], eax
0x140036071  jz      short loc_1400360A4
0x140036073  cmp     [rdi+310h], r15b
0x14003607a  jz      short loc_140036086
0x14003607c  mov     ebx, 80070057h
0x140036081  jmp     loc_140036162
0x140036086  mov     rcx, [rdi+308h]; this
0x14003608d  lea     r8, [rdi+18h]; struct tpm12class::TPMW82B_BUFFER *
0x140036091  lea     rdx, [rdi+60h]; struct tpm12class::TPMW82B_BUFFER *
0x140036095  call    ?CalcSessionKey@TPMW8_AUTH_PROVIDER@tpm12class@@AEAAJPEAVTPMW82B_BUFFER@2@0@Z; tpm12class::TPMW8_AUTH_PROVIDER::CalcSessionKey(tpm12class::TPMW82B_BUFFER *,tpm12class::TPMW82B_BUFFER *)
0x14003609a  mov     ebx, eax
0x14003609c  test    eax, eax
0x14003609e  js      loc_140036162
0x1400360a4  cmp     [rdi+310h], r15b
0x1400360ab  jnz     loc_140036162
0x1400360b1  mov     rcx, [rdi+58h]; unsigned __int8 *
0x1400360b5  lea     rsi, [rdi+50h]
0x1400360b9  movzx   edx, word ptr [rsi]; unsigned int
0x1400360bc  call    ?PlatformGetRandom@@YAJPEAEI@Z; PlatformGetRandom(uchar *,uint)
0x1400360c1  mov     ebx, eax
0x1400360c3  test    eax, eax
0x1400360c5  jnz     short loc_1400360CC
0x1400360c7  mov     ebx, r15d
0x1400360ca  jmp     short loc_14003610F
0x1400360cc  and     eax, 0FFFF000h
0x1400360d1  cmp     eax, 290000h
0x1400360d6  jnz     short loc_1400360E6
0x1400360d8  and     ebx, 0FFFh
0x1400360de  or      ebx, 80280000h
0x1400360e4  jmp     short loc_14003610B
0x1400360e6  mov     eax, ebx
0x1400360e8  and     eax, 0FFF0000h
0x1400360ed  cmp     eax, 70000h
0x1400360f2  jnz     short loc_140036107
0x1400360f4  movzx   ebx, bx
0x1400360f7  test    ebx, ebx
0x1400360f9  jz      short loc_140036101
0x1400360fb  or      ebx, 80070000h
0x140036101  lea     rsi, [rdi+50h]
0x140036105  jmp     short loc_14003610B
0x140036107  bts     ebx, 1Ch
0x14003610b  test    ebx, ebx
0x14003610d  js      short loc_140036162
0x14003610f  mov     rcx, [rdi+208h]; void *
0x140036116  movzx   eax, word ptr [rsi]
0x140036119  mov     [rdi+200h], ax
0x140036120  test    rcx, rcx
0x140036123  jz      short loc_140036131
0x140036125  call    ?TpmFree@@YAXPEAX@Z; TpmFree(void *)
0x14003612a  mov     [rdi+208h], r15
0x140036131  movzx   ecx, word ptr [rdi+200h]; unsigned __int64
0x140036138  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14003613d  mov     [rdi+208h], rax
0x140036144  test    rax, rax
0x140036147  jnz     short loc_140036150
0x140036149  mov     ebx, 80070008h
0x14003614e  jmp     short loc_140036162
0x140036150  movzx   r8d, word ptr [rdi+200h]; Size
0x140036158  xor     edx, edx; Val
0x14003615a  mov     rcx, rax; void *
0x14003615d  call    memset
0x140036162  lea     rcx, [rsp+250h+var_230]; this
0x140036167  call    ??1TPMW8_StartAuthSession@tpm12class@@UEAA@XZ; tpm12class::TPMW8_StartAuthSession::~TPMW8_StartAuthSession(void)
0x14003616c  mov     eax, ebx
0x14003616e  add     rsp, 228h
0x140036175  pop     r15
0x140036177  pop     r14
0x140036179  pop     rdi
0x14003617a  pop     rsi
0x14003617b  pop     rbx
0x14003617c  pop     rbp
0x14003617d  retn
```
