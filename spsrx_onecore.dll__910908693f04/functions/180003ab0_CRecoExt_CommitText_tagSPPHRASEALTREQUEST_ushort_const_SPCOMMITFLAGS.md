# CRecoExt::CommitText(tagSPPHRASEALTREQUEST *,ushort const *,SPCOMMITFLAGS)

- ea: `0x180003ab0`
- end: `0x180003c94`
- name: `?CommitText@CRecoExt@@UEAAJPEAUtagSPPHRASEALTREQUEST@@PEBGW4SPCOMMITFLAGS@@@Z`
- size: `484`
- prototype: `__int64 __fastcall(CRecoExt *this, struct tagSPPHRASEALTREQUEST *, unsigned __int16 *, enum SPCOMMITFLAGS)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x180002570`
- `0x1800031c8`
- `0x18000382c`
- `0x180003ab0`
- `0x18000f0dc`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003b99`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003b99`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003c4f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003c5a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003c4f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003c5a`

## pseudocode

```c
__int64 __fastcall CRecoExt::CommitText(
        CRecoExt *this,
        struct tagSPPHRASEALTREQUEST *a2,
        unsigned __int16 *a3,
        enum SPCOMMITFLAGS a4)
{
  char *v8; // rsi
  int v9; // ebx
  __int64 *v10; // rdx
  unsigned int v11; // r14d
  ULONG v12; // r12d
  char *v13; // rax
  char *v14; // rbx
  void *Src; // [rsp+30h] [rbp-D0h] BYREF
  void **v17; // [rsp+40h] [rbp-C0h] BYREF
  void *v18; // [rsp+48h] [rbp-B8h]
  unsigned int v19; // [rsp+50h] [rbp-B0h]
  __int16 v20; // [rsp+58h] [rbp-A8h] BYREF

  v19 = 0x80000000;
  v18 = &v20;
  v20 = 0;
  v17 = &CQuickStringW<100>::`vftable';
  Src = 0;
  v8 = 0;
  if ( *((_QWORD *)this + 15) && a2 )
  {
    v9 = ((__int64 (__fastcall *)(ISpPhrase *, void **))a2->pPhrase->lpVtbl->GetSerializedPhrase)(a2->pPhrase, &Src);
    if ( v9 >= 0 )
    {
      v10 = &qword_180012480;
      if ( a3 )
        v10 = (__int64 *)a3;
      CQuickStringW<100>::Append(&v17, v10);
      v11 = (v19 & 0x7FFFFFFF) + 1;
      v12 = ((a2->cbResultExtra + 7) & 0xFFFFFFF8) + ((2 * v11 + 3) & 0xFFFFFFFC) + *(_DWORD *)Src + 24;
      v13 = (char *)CoTaskMemAlloc(v12);
      v8 = v13;
      if ( v13 )
      {
        *(_DWORD *)v13 = 40;
        *((_DWORD *)v13 + 1) = a2->ulStartElement;
        *((_DWORD *)v13 + 2) = a2->cElements;
        *((_DWORD *)v13 + 3) = a2->ulRequestAltCount;
        *((_DWORD *)v13 + 4) = a2->cbResultExtra;
        *((_DWORD *)v13 + 5) = a4;
        memcpy_0(v13 + 24, a2->pvResultExtra, a2->cbResultExtra);
        v14 = &v8[((a2->cbResultExtra + 7) & 0xFFFFFFF8) + 24];
        memcpy_0(v14, Src, *(unsigned int *)Src);
        memcpy_0(&v14[*(unsigned int *)Src], v18, 2LL * v11);
        v9 = (*(__int64 (__fastcall **)(_QWORD, char *, _QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 15) + 32LL))(
               *((_QWORD *)this + 15),
               v8,
               v12,
               0,
               0);
      }
      else
      {
        v9 = -2147024882;
      }
    }
  }
  else
  {
    v9 = -2147467259;
  }
  CoTaskMemFree(v8);
  CoTaskMemFree(Src);
  CQuickStringTBase::~CQuickStringTBase((CQuickStringTBase *)&v17);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180003ab0  mov     [rsp-8+arg_18], rbx
0x180003ab5  push    rbp
0x180003ab6  push    rsi
0x180003ab7  push    rdi
0x180003ab8  push    r12
0x180003aba  push    r13
0x180003abc  push    r14
0x180003abe  push    r15
0x180003ac0  lea     rbp, [rsp-40h]
0x180003ac5  sub     rsp, 140h
0x180003acc  mov     rax, cs:__security_cookie
0x180003ad3  xor     rax, rsp
0x180003ad6  mov     [rbp+70h+var_40], rax
0x180003ada  mov     r13d, r9d
0x180003add  mov     r14, r8
0x180003ae0  mov     rdi, rdx
0x180003ae3  mov     r15, rcx
0x180003ae6  mov     [rsp+170h+var_120], 80000000h
0x180003aee  lea     rax, [rsp+170h+var_118]
0x180003af3  mov     [rsp+170h+var_128], rax
0x180003af8  xor     eax, eax
0x180003afa  mov     [rsp+170h+var_118], ax
0x180003aff  lea     rax, ??_7?$CQuickStringW@$0GE@@@6B@; const CQuickStringW<100>::`vftable'
0x180003b06  mov     [rsp+170h+var_130], rax
0x180003b0b  mov     [rsp+170h+Src], 0
0x180003b14  xor     esi, esi
0x180003b16  cmp     [rcx+78h], rsi
0x180003b1a  jz      loc_180003C47
0x180003b20  test    rdx, rdx
0x180003b23  jz      loc_180003C47
0x180003b29  mov     rcx, [rdx+20h]
0x180003b2d  mov     rax, [rcx]
0x180003b30  lea     rdx, [rsp+170h+Src]
0x180003b35  mov     rax, [rax+20h]
0x180003b39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b3e  mov     ebx, eax
0x180003b40  test    eax, eax
0x180003b42  js      loc_180003C4C
0x180003b48  lea     rdx, qword_180012480
0x180003b4f  test    r14, r14
0x180003b52  cmovnz  rdx, r14
0x180003b56  lea     rcx, [rsp+170h+var_130]
0x180003b5b  call    ?Append@?$CQuickStringW@$0GE@@@QEAAJQEBG@Z; CQuickStringW<100>::Append(ushort const * const)
0x180003b60  mov     r14d, [rsp+170h+var_120]
0x180003b65  btr     r14d, 1Fh
0x180003b6a  inc     r14d
0x180003b6d  lea     edx, ds:3[r14*2]
0x180003b75  and     edx, 0FFFFFFFCh
0x180003b78  mov     eax, [rdi+18h]
0x180003b7b  add     eax, 7
0x180003b7e  mov     ecx, 0FFFFFFF8h
0x180003b83  and     eax, ecx
0x180003b85  add     edx, eax
0x180003b87  mov     rax, [rsp+170h+Src]
0x180003b8c  mov     r12d, [rax]
0x180003b8f  add     r12d, 18h
0x180003b93  add     r12d, edx
0x180003b96  mov     ecx, r12d; cb
0x180003b99  call    cs:__imp_CoTaskMemAlloc
0x180003b9f  mov     rsi, rax
0x180003ba2  test    rax, rax
0x180003ba5  jnz     short loc_180003BB1
0x180003ba7  mov     ebx, 8007000Eh
0x180003bac  jmp     loc_180003C4C
0x180003bb1  mov     dword ptr [rax], 28h ; '('
0x180003bb7  mov     eax, [rdi]
0x180003bb9  mov     [rsi+4], eax
0x180003bbc  mov     eax, [rdi+4]
0x180003bbf  mov     [rsi+8], eax
0x180003bc2  mov     eax, [rdi+8]
0x180003bc5  mov     [rsi+0Ch], eax
0x180003bc8  mov     eax, [rdi+18h]
0x180003bcb  mov     [rsi+10h], eax
0x180003bce  mov     [rsi+14h], r13d
0x180003bd2  lea     rbx, [rsi+18h]
0x180003bd6  mov     r8d, [rdi+18h]; Size
0x180003bda  mov     rdx, [rdi+10h]; Src
0x180003bde  mov     rcx, rbx; void *
0x180003be1  call    memcpy_0
0x180003be6  mov     eax, [rdi+18h]
0x180003be9  add     eax, 7
0x180003bec  mov     ecx, 0FFFFFFF8h
0x180003bf1  and     rax, rcx
0x180003bf4  add     rbx, rax
0x180003bf7  mov     rdx, [rsp+170h+Src]; Src
0x180003bfc  mov     r8d, [rdx]; Size
0x180003bff  mov     rcx, rbx; void *
0x180003c02  call    memcpy_0
0x180003c07  mov     r8d, r14d
0x180003c0a  add     r8, r8; Size
0x180003c0d  mov     rax, [rsp+170h+Src]
0x180003c12  mov     ecx, [rax]
0x180003c14  add     rcx, rbx; void *
0x180003c17  mov     rdx, [rsp+170h+var_128]; Src
0x180003c1c  call    memcpy_0
0x180003c21  mov     rcx, [r15+78h]
0x180003c25  mov     rax, [rcx]
0x180003c28  mov     [rsp+170h+var_150], 0
0x180003c31  xor     r9d, r9d
0x180003c34  mov     r8d, r12d
0x180003c37  mov     rdx, rsi
0x180003c3a  mov     rax, [rax+20h]
0x180003c3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c43  mov     ebx, eax
0x180003c45  jmp     short loc_180003C4C
0x180003c47  mov     ebx, 80004005h
0x180003c4c  mov     rcx, rsi; pv
0x180003c4f  call    cs:__imp_CoTaskMemFree
0x180003c55  mov     rcx, [rsp+170h+Src]; pv
0x180003c5a  call    cs:__imp_CoTaskMemFree
0x180003c60  nop
0x180003c61  lea     rcx, [rsp+170h+var_130]; this
0x180003c66  call    ??1CQuickStringTBase@@MEAA@XZ; CQuickStringTBase::~CQuickStringTBase(void)
0x180003c6b  mov     eax, ebx
0x180003c6d  mov     rcx, [rbp+70h+var_40]
0x180003c71  xor     rcx, rsp; StackCookie
0x180003c74  call    __security_check_cookie
0x180003c79  mov     rbx, [rsp+170h+arg_18]
0x180003c81  add     rsp, 140h
0x180003c88  pop     r15
0x180003c8a  pop     r14
0x180003c8c  pop     r13
0x180003c8e  pop     r12
0x180003c90  pop     rdi
0x180003c91  pop     rsi
0x180003c92  pop     rbp
0x180003c93  retn
```
