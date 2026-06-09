# CASFContentDescriptionObjectBase::AddDescriptor(ushort,uchar,ushort const *,ushort const *,ushort const *)

- ea: `0x18002c700`
- end: `0x18002c93a`
- name: `?AddDescriptor@CASFContentDescriptionObjectBase@@UEAAJGEPEBG00@Z`
- size: `570`
- prototype: `__int64 __fastcall(CASFContentDescriptionObjectBase *__hidden this, unsigned __int16, unsigned __int8, const unsigned __int16 *, const unsigned __int16 *Src, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x1800011c0`
- `0x1800011cc`
- `0x1800015d0`
- `0x1800021dc`
- `0x18000220c`
- `0x18001a31c`
- `0x18002c700`
- `0x1800310c0`
- `0x18003f2a0`
- `0x180040010`

## pseudocode

```c
__int64 __fastcall CASFContentDescriptionObjectBase::AddDescriptor(
        CASFContentDescriptionObjectBase *this,
        __int16 a2,
        unsigned __int8 a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *Src,
        unsigned __int16 *a6)
{
  unsigned __int16 *v6; // rbx
  struct IWMSCriticalSection *v8; // rdx
  __int64 v12; // rcx
  int v13; // ebx
  __int16 v14; // ax
  __int64 v15; // rax
  unsigned __int16 v16; // ax
  __int64 v17; // rcx
  __int64 v18; // rdi
  unsigned __int64 v19; // r12
  void *v20; // rbx
  __int64 v21; // r14
  void *v22; // rsi
  void *v23; // rcx
  char *v24; // rcx
  __int128 v26; // [rsp+20h] [rbp-58h] BYREF
  void *v27; // [rsp+30h] [rbp-48h]
  void *v28; // [rsp+40h] [rbp-38h]
  CASFContentDescriptionObjectBase *v29; // [rsp+48h] [rbp-30h]
  _BYTE v30[8]; // [rsp+50h] [rbp-28h] BYREF
  __int64 v31; // [rsp+58h] [rbp-20h] BYREF
  __int16 v32; // [rsp+60h] [rbp-18h] BYREF

  v6 = a6;
  v8 = (struct IWMSCriticalSection *)*((_QWORD *)this + 4);
  v29 = this;
  v28 = a6;
  CAutoCritSec::CAutoCritSec((CAutoCritSec *)v30, v8);
  v12 = *((_QWORD *)this + 5);
  if ( !v12 )
  {
    v13 = -1072887818;
    goto LABEL_36;
  }
  if ( !Src && a3 >= 0x64u || !a6 )
  {
    v13 = -2147024809;
    goto LABEL_36;
  }
  v14 = 0;
  v32 = 0;
  if ( !a4 )
  {
LABEL_13:
    v26 = 0;
    WORD2(v26) = a2;
    LOBYTE(v26) = a3;
    WORD1(v26) = v14;
    v27 = 0;
    if ( Src )
    {
      v15 = -1;
      do
        ++v15;
      while ( Src[v15] );
      v16 = v15 + 1;
    }
    else
    {
      v16 = 0;
    }
    v17 = -1;
    do
      ++v17;
    while ( v6[v17] );
    v18 = v16;
    v19 = (unsigned __int16)(v17 + 1);
    if ( v16 )
    {
      *((_QWORD *)&v26 + 1) = operator new[](saturated_mul(v16, 2u));
      v20 = (void *)*((_QWORD *)&v26 + 1);
      if ( !*((_QWORD *)&v26 + 1) )
        goto LABEL_28;
      v21 = (unsigned int)v18;
    }
    else
    {
      v20 = 0;
      v21 = 0;
      *((_QWORD *)&v26 + 1) = 0;
    }
    v22 = operator new[](saturated_mul(v19, 2u));
    if ( v22 )
    {
      if ( v20 )
      {
        memcpy_0(v20, Src, 2 * v21 - 2);
        *((_WORD *)v20 + v18 - 1) = 0;
      }
      memcpy_0(v22, v28, 2 * v19 - 2);
      v27 = v22;
      v24 = (char *)v29 + 80;
      *((_WORD *)v22 + v19 - 1) = 0;
      if ( (unsigned int)CTDynArray<CASFContentDescriptionObjectBase::CONTENT_DESCRIPTION_REC,20>::Add(v24, &v26) )
      {
        v13 = 0;
        goto LABEL_36;
      }
      if ( v20 )
        operator delete(v20);
      v23 = v22;
      goto LABEL_27;
    }
    if ( v20 )
    {
      v23 = v20;
LABEL_27:
      operator delete(v23);
    }
LABEL_28:
    v13 = -2147024882;
    goto LABEL_36;
  }
  v31 = 0;
  v13 = ASFGetHeaderObject(v12, &CLSID_ASFLanguageListObject, &IID_IASFLanguageListObject, &v31);
  if ( v13 >= 0 )
  {
    v13 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, __int16 *))(*(_QWORD *)v31 + 112LL))(
            v31,
            a4,
            &v32);
    if ( v31 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
      v31 = 0;
    }
    if ( v13 >= 0 )
    {
      v14 = v32;
      v6 = (unsigned __int16 *)v28;
      goto LABEL_13;
    }
  }
LABEL_36:
  CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v30);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18002c700  push    rbp
0x18002c702  push    rbx
0x18002c703  push    rsi
0x18002c704  push    rdi
0x18002c705  push    r12
0x18002c707  push    r13
0x18002c709  push    r14
0x18002c70b  push    r15
0x18002c70d  mov     rbp, rsp
0x18002c710  sub     rsp, 78h
0x18002c714  mov     rax, cs:__security_cookie
0x18002c71b  xor     rax, rsp
0x18002c71e  mov     [rbp+var_10], rax
0x18002c722  mov     rbx, [rbp+arg_28]
0x18002c726  movzx   r14d, dx
0x18002c72a  mov     rdx, [rcx+20h]; struct IWMSCriticalSection *
0x18002c72e  mov     r13, rcx
0x18002c731  mov     r15, [rbp+Src]
0x18002c735  mov     rsi, r9
0x18002c738  mov     [rbp+var_30], rcx
0x18002c73c  mov     dil, r8b
0x18002c73f  lea     rcx, [rbp+var_28]; this
0x18002c743  mov     [rbp+var_38], rbx
0x18002c747  call    ??0CAutoCritSec@@QEAA@PEAUIWMSCriticalSection@@@Z; CAutoCritSec::CAutoCritSec(IWMSCriticalSection *)
0x18002c74c  mov     rcx, [r13+28h]
0x18002c750  xor     r13d, r13d
0x18002c753  test    rcx, rcx
0x18002c756  jnz     short loc_18002C762
0x18002c758  mov     ebx, 0C00D07F6h
0x18002c75d  jmp     loc_18002C912
0x18002c762  test    r15, r15
0x18002c765  jnz     short loc_18002C76D
0x18002c767  cmp     dil, 64h ; 'd'
0x18002c76b  jnb     short loc_18002C772
0x18002c76d  test    rbx, rbx
0x18002c770  jnz     short loc_18002C77C
0x18002c772  mov     ebx, 80070057h
0x18002c777  jmp     loc_18002C912
0x18002c77c  mov     eax, r13d
0x18002c77f  mov     [rbp+var_18], ax
0x18002c783  test    rsi, rsi
0x18002c786  jz      short loc_18002C7EF
0x18002c788  lea     r9, [rbp+var_20]
0x18002c78c  mov     [rbp+var_20], r13
0x18002c790  lea     r8, IID_IASFLanguageListObject
0x18002c797  lea     rdx, CLSID_ASFLanguageListObject
0x18002c79e  call    ASFGetHeaderObject
0x18002c7a3  mov     ebx, eax
0x18002c7a5  test    eax, eax
0x18002c7a7  js      loc_18002C912
0x18002c7ad  mov     rcx, [rbp+var_20]
0x18002c7b1  lea     r8, [rbp+var_18]
0x18002c7b5  mov     rdx, rsi
0x18002c7b8  mov     rax, [rcx]
0x18002c7bb  mov     rax, [rax+70h]
0x18002c7bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c7c4  mov     rcx, [rbp+var_20]
0x18002c7c8  mov     ebx, eax
0x18002c7ca  test    rcx, rcx
0x18002c7cd  jz      short loc_18002C7DF
0x18002c7cf  mov     rax, [rcx]
0x18002c7d2  mov     rax, [rax+10h]
0x18002c7d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c7db  mov     [rbp+var_20], r13
0x18002c7df  test    ebx, ebx
0x18002c7e1  js      loc_18002C912
0x18002c7e7  movzx   eax, [rbp+var_18]
0x18002c7eb  mov     rbx, [rbp+var_38]
0x18002c7ef  xor     ecx, ecx
0x18002c7f1  xorps   xmm0, xmm0
0x18002c7f4  movups  [rbp+var_58], xmm0
0x18002c7f8  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18002c7fc  mov     word ptr [rbp+var_58+4], r14w
0x18002c801  mov     byte ptr [rbp+var_58], dil
0x18002c805  mov     word ptr [rbp+var_58+2], ax
0x18002c809  mov     [rbp+var_48], rcx
0x18002c80d  test    r15, r15
0x18002c810  jz      short loc_18002C824
0x18002c812  mov     rax, rsi
0x18002c815  inc     rax
0x18002c818  cmp     [r15+rax*2], r13w
0x18002c81d  jnz     short loc_18002C815
0x18002c81f  inc     ax
0x18002c822  jmp     short loc_18002C827
0x18002c824  mov     eax, r13d
0x18002c827  mov     rcx, rsi
0x18002c82a  inc     rcx
0x18002c82d  cmp     [rbx+rcx*2], r13w
0x18002c832  jnz     short loc_18002C82A
0x18002c834  inc     cx
0x18002c837  movzx   edi, ax
0x18002c83a  movzx   r12d, cx
0x18002c83e  test    ax, ax
0x18002c841  jz      short loc_18002C868
0x18002c843  mov     eax, 2
0x18002c848  mul     rdi
0x18002c84b  cmovb   rax, rsi
0x18002c84f  mov     rcx, rax; unsigned __int64
0x18002c852  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18002c857  mov     qword ptr [rbp+var_58+8], rax
0x18002c85b  mov     rbx, rax
0x18002c85e  test    rax, rax
0x18002c861  jz      short loc_18002C89B
0x18002c863  mov     r14d, edi
0x18002c866  jmp     short loc_18002C872
0x18002c868  mov     rbx, r13
0x18002c86b  mov     r14, r13
0x18002c86e  mov     qword ptr [rbp+var_58+8], rbx
0x18002c872  mov     eax, 2
0x18002c877  mul     r12
0x18002c87a  cmovb   rax, rsi
0x18002c87e  mov     rcx, rax; unsigned __int64
0x18002c881  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18002c886  mov     rsi, rax
0x18002c889  test    rax, rax
0x18002c88c  jnz     short loc_18002C8A2
0x18002c88e  test    rbx, rbx
0x18002c891  jz      short loc_18002C89B
0x18002c893  mov     rcx, rbx; Block
0x18002c896  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002c89b  mov     ebx, 8007000Eh
0x18002c8a0  jmp     short loc_18002C912
0x18002c8a2  test    rbx, rbx
0x18002c8a5  jz      short loc_18002C8C1
0x18002c8a7  lea     r8, ds:0FFFFFFFFFFFFFFFEh[r14*2]; Size
0x18002c8af  mov     rdx, r15; Src
0x18002c8b2  mov     rcx, rbx; void *
0x18002c8b5  call    memcpy_0
0x18002c8ba  xor     eax, eax
0x18002c8bc  mov     [rbx+rdi*2-2], ax
0x18002c8c1  mov     rdx, [rbp+var_38]; Src
0x18002c8c5  lea     r8, ds:0FFFFFFFFFFFFFFFEh[r12*2]; Size
0x18002c8cd  mov     rcx, rsi; void *
0x18002c8d0  call    memcpy_0
0x18002c8d5  movups  xmm0, [rbp+var_58]
0x18002c8d9  mov     rcx, [rbp+var_30]
0x18002c8dd  lea     rdx, [rbp+var_58]
0x18002c8e1  xor     eax, eax
0x18002c8e3  mov     [rbp+var_48], rsi
0x18002c8e7  add     rcx, 50h ; 'P'
0x18002c8eb  movaps  [rbp+var_58], xmm0
0x18002c8ef  mov     [rsi+r12*2-2], ax
0x18002c8f5  call    ?Add@?$CTDynArray@UCONTENT_DESCRIPTION_REC@CASFContentDescriptionObjectBase@@$0BE@@@QEAAHUCONTENT_DESCRIPTION_REC@CASFContentDescriptionObjectBase@@PEAK@Z; CTDynArray<CASFContentDescriptionObjectBase::CONTENT_DESCRIPTION_REC,20>::Add(CASFContentDescriptionObjectBase::CONTENT_DESCRIPTION_REC,ulong *)
0x18002c8fa  test    eax, eax
0x18002c8fc  jnz     short loc_18002C910
0x18002c8fe  test    rbx, rbx
0x18002c901  jz      short loc_18002C90B
0x18002c903  mov     rcx, rbx; Block
0x18002c906  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002c90b  mov     rcx, rsi
0x18002c90e  jmp     short loc_18002C896
0x18002c910  xor     ebx, ebx
0x18002c912  lea     rcx, [rbp+var_28]; this
0x18002c916  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x18002c91b  mov     eax, ebx
0x18002c91d  mov     rcx, [rbp+var_10]
0x18002c921  xor     rcx, rsp; StackCookie
0x18002c924  call    __security_check_cookie
0x18002c929  add     rsp, 78h
0x18002c92d  pop     r15
0x18002c92f  pop     r14
0x18002c931  pop     r13
0x18002c933  pop     r12
0x18002c935  pop     rdi
0x18002c936  pop     rsi
0x18002c937  pop     rbx
0x18002c938  pop     rbp
0x18002c939  retn
```
