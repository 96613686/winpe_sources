# tpm12class::TPMW8_COMMAND::Execute(void *)

- ea: `0x1400367d8`
- end: `0x140036a25`
- name: `?Execute@TPMW8_COMMAND@tpm12class@@QEAAJPEAX@Z`
- size: `589`
- prototype: `__int64 __fastcall(tpm12class::TPMW8_COMMAND *__hidden this, void *)`
- caller_count: `6`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x140032eb4`
- `0x140032f58`
- `0x140033154`
- `0x140033368`
- `0x140035f08`
- `0x140038b54`

## callees

- `0x14000cb50`
- `0x140035f08`
- `0x1400367d8`
- `0x140036c34`
- `0x1400372ac`
- `0x140037400`
- `0x140037488`
- `0x140039780`
- `0x140039b40`
- `0x1400454a0`

## pseudocode

```c
__int64 __fastcall tpm12class::TPMW8_COMMAND::Execute(tpm12class::TPMW8_COMMAND *this, void *a2)
{
  size_t v2; // r14
  tpm12class::TPMW8_SESSION *v4; // rcx
  unsigned __int8 *v5; // r15
  unsigned __int8 *v6; // rsi
  signed int v8; // ebx
  tpm12class::TPMW8_SESSION *v9; // rcx
  tpm12class::TPMW8_SESSION *v10; // rcx
  unsigned __int8 *v11; // rax
  unsigned __int8 *v12; // rax
  __int64 v13; // rax
  unsigned __int8 *v14; // rcx
  __int64 v15; // rcx
  unsigned __int8 *v16; // rax
  int v18; // eax
  int v19; // eax
  tpm12class::TPMW8_SESSION *v20; // rcx
  tpm12class::TPMW8_SESSION *v21; // rcx
  tpm12class::TPMW8_SESSION *v22; // rcx
  size_t Size; // [rsp+60h] [rbp+30h] BYREF
  size_t v24; // [rsp+70h] [rbp+40h] BYREF

  LODWORD(v2) = 0;
  LODWORD(v24) = 4096;
  LODWORD(Size) = 0;
  v4 = (tpm12class::TPMW8_SESSION *)*((_QWORD *)this + 21);
  v5 = 0;
  v6 = 0;
  if ( __PAIR128__(*((_QWORD *)this + 22), (unsigned __int64)v4) != 0 || *((_QWORD *)this + 23) )
  {
    *((_WORD *)this + 28) = -32766;
    if ( v4 )
    {
      v8 = tpm12class::TPMW8_SESSION::Create(v4, a2);
      if ( v8 < 0 )
        goto LABEL_16;
      v9 = (tpm12class::TPMW8_SESSION *)*((_QWORD *)this + 22);
      if ( v9 )
      {
        v8 = tpm12class::TPMW8_SESSION::Create(v9, a2);
        if ( v8 < 0 )
          goto LABEL_16;
        v10 = (tpm12class::TPMW8_SESSION *)*((_QWORD *)this + 23);
        if ( v10 )
        {
          v8 = tpm12class::TPMW8_SESSION::Create(v10, a2);
          if ( v8 < 0 )
            goto LABEL_16;
        }
      }
    }
  }
  v8 = tpm12class::TPMW8_COMMAND::Get(this, 0, 0, (unsigned int *)&Size);
  if ( v8 < 0 )
    goto LABEL_15;
  v2 = (unsigned int)Size;
  v11 = (unsigned __int8 *)operator new((unsigned int)Size);
  v5 = v11;
  if ( !v11 )
  {
    v8 = -2147024888;
    goto LABEL_16;
  }
  memset(v11, 0, v2);
  v8 = tpm12class::TPMW8_COMMAND::Get(this, v5, v2, (unsigned int *)&Size);
  if ( v8 < 0 )
    goto LABEL_15;
  v12 = (unsigned __int8 *)operator new((unsigned int)v24);
  v6 = v12;
  if ( !v12 )
  {
    v8 = -2147024888;
LABEL_15:
    LODWORD(v2) = Size;
    goto LABEL_16;
  }
  memset(v12, 0, (unsigned int)v24);
  LODWORD(v2) = Size;
  if ( g_fpW8TpmSubmit )
  {
    v18 = g_fpW8TpmSubmit(a2, v5, Size, v6, (unsigned int *)&v24);
    v8 = v18 & 0xEFFFFFFF;
    if ( v18 < 0 )
      goto LABEL_16;
  }
  v19 = tpm12class::TPMW8_COMMAND::Set(this, v6, v24);
  v8 = v19;
  if ( !v19 )
  {
    v20 = (tpm12class::TPMW8_SESSION *)*((_QWORD *)this + 21);
    if ( v20 )
    {
      tpm12class::TPMW8_SESSION::Refresh(v20);
      v21 = (tpm12class::TPMW8_SESSION *)*((_QWORD *)this + 22);
      if ( v21 )
      {
        tpm12class::TPMW8_SESSION::Refresh(v21);
        v22 = (tpm12class::TPMW8_SESSION *)*((_QWORD *)this + 23);
        if ( v22 )
          tpm12class::TPMW8_SESSION::Refresh(v22);
      }
    }
    goto LABEL_17;
  }
  if ( v19 < 0 )
  {
LABEL_16:
    ReleaseSessionIf(*((_QWORD *)this + 21));
    ReleaseSessionIf(*((_QWORD *)this + 22));
    ReleaseSessionIf(*((_QWORD *)this + 23));
    if ( !v6 )
      goto LABEL_20;
  }
LABEL_17:
  v13 = (unsigned int)v24;
  v14 = v6;
  if ( (_DWORD)v24 )
  {
    do
    {
      *v14++ = 0;
      --v13;
    }
    while ( v13 );
  }
  TpmFree(v6);
LABEL_20:
  LODWORD(v24) = 0;
  if ( v5 )
  {
    v15 = (unsigned int)v2;
    v16 = v5;
    if ( (_DWORD)v2 )
    {
      do
      {
        *v16++ = 0;
        --v15;
      }
      while ( v15 );
    }
    TpmFree(v5);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1400367d8  mov     [rsp-28h+arg_8], rbx
0x1400367dd  mov     [rsp-28h+arg_18], rsi
0x1400367e2  push    rbp
0x1400367e3  push    rdi
0x1400367e4  push    r12
0x1400367e6  push    r14
0x1400367e8  push    r15
0x1400367ea  mov     rbp, rsp
0x1400367ed  sub     rsp, 30h
0x1400367f1  xor     r14d, r14d
0x1400367f4  mov     dword ptr [rbp+arg_10], 1000h
0x1400367fb  mov     rdi, rcx
0x1400367fe  mov     dword ptr [rbp+Size], r14d
0x140036802  mov     rcx, [rcx+0A8h]; this
0x140036809  xor     r15d, r15d
0x14003680c  xor     esi, esi
0x14003680e  mov     r12, rdx
0x140036811  test    rcx, rcx
0x140036814  jnz     short loc_140036828
0x140036816  cmp     [rdi+0B0h], rsi
0x14003681d  jnz     short loc_140036828
0x14003681f  cmp     [rdi+0B8h], rsi
0x140036826  jz      short loc_14003687A
0x140036828  mov     word ptr [rdi+38h], 8002h
0x14003682e  test    rcx, rcx
0x140036831  jz      short loc_14003687A
0x140036833  call    ?Create@TPMW8_SESSION@tpm12class@@QEAAJPEAX@Z; tpm12class::TPMW8_SESSION::Create(void *)
0x140036838  mov     ebx, eax
0x14003683a  test    eax, eax
0x14003683c  js      loc_1400368EE
0x140036842  mov     rcx, [rdi+0B0h]; this
0x140036849  test    rcx, rcx
0x14003684c  jz      short loc_14003687A
0x14003684e  mov     rdx, r12; void *
0x140036851  call    ?Create@TPMW8_SESSION@tpm12class@@QEAAJPEAX@Z; tpm12class::TPMW8_SESSION::Create(void *)
0x140036856  mov     ebx, eax
0x140036858  test    eax, eax
0x14003685a  js      loc_1400368EE
0x140036860  mov     rcx, [rdi+0B8h]; this
0x140036867  test    rcx, rcx
0x14003686a  jz      short loc_14003687A
0x14003686c  mov     rdx, r12; void *
0x14003686f  call    ?Create@TPMW8_SESSION@tpm12class@@QEAAJPEAX@Z; tpm12class::TPMW8_SESSION::Create(void *)
0x140036874  mov     ebx, eax
0x140036876  test    eax, eax
0x140036878  js      short loc_1400368EE
0x14003687a  lea     r9, [rbp+Size]; unsigned int *
0x14003687e  xor     r8d, r8d; unsigned int
0x140036881  xor     edx, edx; unsigned __int8 *
0x140036883  mov     rcx, rdi; this
0x140036886  call    ?Get@TPMW8_COMMAND@tpm12class@@QEAAJPEAEIPEAI@Z; tpm12class::TPMW8_COMMAND::Get(uchar *,uint,uint *)
0x14003688b  mov     ebx, eax
0x14003688d  test    eax, eax
0x14003688f  js      short loc_1400368EA
0x140036891  mov     r14d, dword ptr [rbp+Size]
0x140036895  mov     ecx, r14d; unsigned __int64
0x140036898  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14003689d  mov     r15, rax
0x1400368a0  test    rax, rax
0x1400368a3  jnz     short loc_1400368AC
0x1400368a5  mov     ebx, 80070008h
0x1400368aa  jmp     short loc_1400368EE
0x1400368ac  mov     r8, r14; Size
0x1400368af  xor     edx, edx; Val
0x1400368b1  mov     rcx, r15; void *
0x1400368b4  call    memset
0x1400368b9  lea     r9, [rbp+Size]; unsigned int *
0x1400368bd  mov     r8d, r14d; unsigned int
0x1400368c0  mov     rdx, r15; unsigned __int8 *
0x1400368c3  mov     rcx, rdi; this
0x1400368c6  call    ?Get@TPMW8_COMMAND@tpm12class@@QEAAJPEAEIPEAI@Z; tpm12class::TPMW8_COMMAND::Get(uchar *,uint,uint *)
0x1400368cb  mov     ebx, eax
0x1400368cd  test    eax, eax
0x1400368cf  js      short loc_1400368EA
0x1400368d1  mov     ecx, dword ptr [rbp+arg_10]; unsigned __int64
0x1400368d4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400368d9  mov     rsi, rax
0x1400368dc  test    rax, rax
0x1400368df  jnz     loc_14003697B
0x1400368e5  mov     ebx, 80070008h
0x1400368ea  mov     r14d, dword ptr [rbp+Size]
0x1400368ee  mov     rcx, [rdi+0A8h]
0x1400368f5  call    ReleaseSessionIf
0x1400368fa  mov     rcx, [rdi+0B0h]
0x140036901  call    ReleaseSessionIf
0x140036906  mov     rcx, [rdi+0B8h]
0x14003690d  call    ReleaseSessionIf
0x140036912  test    rsi, rsi
0x140036915  jz      short loc_140036936
0x140036917  mov     eax, dword ptr [rbp+arg_10]
0x14003691a  mov     rcx, rsi
0x14003691d  test    rax, rax
0x140036920  jz      short loc_14003692E
0x140036922  mov     byte ptr [rcx], 0
0x140036925  inc     rcx
0x140036928  sub     rax, 1
0x14003692c  jnz     short loc_140036922
0x14003692e  mov     rcx, rsi; void *
0x140036931  call    ?TpmFree@@YAXPEAX@Z; TpmFree(void *)
0x140036936  mov     dword ptr [rbp+arg_10], 0
0x14003693d  test    r15, r15
0x140036940  jz      short loc_140036961
0x140036942  mov     ecx, r14d
0x140036945  mov     rax, r15
0x140036948  test    r14d, r14d
0x14003694b  jz      short loc_140036959
0x14003694d  mov     byte ptr [rax], 0
0x140036950  inc     rax
0x140036953  sub     rcx, 1
0x140036957  jnz     short loc_14003694D
0x140036959  mov     rcx, r15; void *
0x14003695c  call    ?TpmFree@@YAXPEAX@Z; TpmFree(void *)
0x140036961  mov     rsi, [rsp+30h+arg_18]
0x140036966  mov     eax, ebx
0x140036968  mov     rbx, [rsp+30h+arg_8]
0x14003696d  add     rsp, 30h
0x140036971  pop     r15
0x140036973  pop     r14
0x140036975  pop     r12
0x140036977  pop     rdi
0x140036978  pop     rbp
0x140036979  retn
0x14003697b  mov     r8d, dword ptr [rbp+arg_10]; Size
0x14003697f  xor     edx, edx; Val
0x140036981  mov     rcx, rsi; void *
0x140036984  call    memset
0x140036989  mov     rax, cs:?g_fpW8TpmSubmit@@3P6AIPEAXQEAEIPEAEPEAI@ZEA; uint (*g_fpW8TpmSubmit)(void *,uchar * const,uint,uchar *,uint *)
0x140036990  mov     r14d, dword ptr [rbp+Size]
0x140036994  test    rax, rax
0x140036997  jz      short loc_1400369C1
0x140036999  lea     rcx, [rbp+arg_10]
0x14003699d  mov     r9, rsi
0x1400369a0  mov     [rsp+30h+var_10], rcx
0x1400369a5  mov     r8d, r14d
0x1400369a8  mov     rcx, r12
0x1400369ab  mov     rdx, r15
0x1400369ae  call    _guard_dispatch_icall
0x1400369b3  mov     ebx, eax
0x1400369b5  and     ebx, 0EFFFFFFFh
0x1400369bb  jl      loc_1400368EE
0x1400369c1  mov     r8d, dword ptr [rbp+arg_10]; unsigned int
0x1400369c5  mov     rdx, rsi; unsigned __int8 *
0x1400369c8  mov     rcx, rdi; this
0x1400369cb  call    ?Set@TPMW8_COMMAND@tpm12class@@QEAAJPEBEI@Z; tpm12class::TPMW8_COMMAND::Set(uchar const *,uint)
0x1400369d0  mov     ebx, eax
0x1400369d2  test    eax, eax
0x1400369d4  jnz     short loc_140036A1A
0x1400369d6  mov     rcx, [rdi+0A8h]; this
0x1400369dd  test    rcx, rcx
0x1400369e0  jz      loc_140036917
0x1400369e6  call    ?Refresh@TPMW8_SESSION@tpm12class@@QEAAJXZ; tpm12class::TPMW8_SESSION::Refresh(void)
0x1400369eb  mov     rcx, [rdi+0B0h]; this
0x1400369f2  test    rcx, rcx
0x1400369f5  jz      loc_140036917
0x1400369fb  call    ?Refresh@TPMW8_SESSION@tpm12class@@QEAAJXZ; tpm12class::TPMW8_SESSION::Refresh(void)
0x140036a00  mov     rcx, [rdi+0B8h]; this
0x140036a07  test    rcx, rcx
0x140036a0a  jz      loc_140036917
0x140036a10  call    ?Refresh@TPMW8_SESSION@tpm12class@@QEAAJXZ; tpm12class::TPMW8_SESSION::Refresh(void)
0x140036a15  jmp     loc_140036917
0x140036a1a  jns     loc_140036917
0x140036a20  jmp     loc_1400368EE
```
