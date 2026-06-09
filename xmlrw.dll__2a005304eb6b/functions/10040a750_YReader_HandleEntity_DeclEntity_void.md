# YReader::HandleEntity(DeclEntity *,void *)

- ea: `0x10040a750`
- end: `0x10040a9f1`
- name: `?HandleEntity@YReader@@AEAAPEAVDeclEntity@@PEAV2@PEAX@Z`
- size: `673`
- prototype: `struct DeclEntity *__fastcall(YReader *__hidden this, struct DeclEntity *, void *)`
- caller_count: `5`
- callee_count: `9`
- tags: ``

## callers

- `0x100407620`
- `0x100407ec0`
- `0x10040a020`
- `0x10040a270`
- `0x10040a4c0`

## callees

- `0x100401780`
- `0x10040a750`
- `0x10040ca10`
- `0x10040cc10`
- `0x10040dd40`
- `0x1004171c0`
- `0x100417640`
- `0x100423830`
- `0x100439df0`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x10040a784`
- `OLEAUT32!__imp_VariantInit` at `0x10040a784`
- `OLEAUT32!__imp_VariantClear` at `0x10040a9bf`
- `OLEAUT32!__imp_VariantClear` at `0x10040a9bf`

## pseudocode

```c
struct DeclEntity *__fastcall YReader::HandleEntity(YReader *this, struct DeclEntity *a2, void *a3)
{
  int v6; // edi
  StringPtrInputSource *v7; // rax
  struct InputSource *v8; // r15
  unsigned int v9; // edx
  struct InputSource **v10; // r8
  struct InputSource *v11; // rdx
  __int64 *v12; // r15
  __int64 v13; // rdi
  __int64 v14; // rbx
  _QWORD *v15; // rax
  int v16; // eax
  struct IUnknown *Unknown; // rax
  unsigned int v18; // edx
  struct InputSource **v19; // r8
  struct InputSource *v20; // rbx
  int v22; // [rsp+30h] [rbp-78h]
  VARIANTARG pvarg; // [rsp+50h] [rbp-58h] BYREF
  struct IUnknown *v24; // [rsp+68h] [rbp-40h]
  struct InputSource *v25; // [rsp+C8h] [rbp+20h] BYREF

  v6 = 0;
  v22 = 0;
  v25 = 0;
  VariantInit(&pvarg);
  if ( !a2 )
    return 0;
  if ( *((_QWORD *)a2 + 12) )
  {
    v7 = (StringPtrInputSource *)Base::operator new(0x58u, *((struct IMalloc **)this + 1));
    if ( v7 )
      v8 = StringPtrInputSource::StringPtrInputSource(
             v7,
             *((struct IMalloc **)this + 1),
             (struct DeclEntity *)((char *)a2 + 96));
    else
      v8 = 0;
    v25 = v8;
    v9 = *((_DWORD *)this + 118);
    if ( *((_DWORD *)this + 119) == v9 )
    {
      _stack<void (Scanner::*)(void),8>::grow((__int64)this + 448, 0);
      v9 = *((_DWORD *)this + 118);
    }
    v10 = (struct InputSource **)(*((_QWORD *)this + 58) + 8LL * v9);
    *((_DWORD *)this + 118) = v9 + 1;
    *v10 = v8;
    (*(void (__fastcall **)(struct InputSource *, struct DeclEntity *))(*(_QWORD *)v8 + 48LL))(v8, a2);
    v11 = v8;
    goto LABEL_18;
  }
  v12 = (__int64 *)*((_QWORD *)this + 1032);
  if ( !v12 )
    return 0;
  v13 = *v12;
  v14 = *(_QWORD *)(*(__int64 (__fastcall **)(struct DeclEntity *))(*(_QWORD *)a2 + 40LL))(a2);
  v15 = (_QWORD *)(*(__int64 (__fastcall **)(struct DeclEntity *))(*(_QWORD *)a2 + 24LL))(a2);
  v16 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64, VARIANTARG *))(v13 + 24))(v12, *v15, v14, &pvarg);
  if ( v16 )
    v16 = -2147467259;
  v6 = v16;
  v22 = v16;
  if ( v16 )
    goto LABEL_28;
  Unknown = Variant::getUnknown(&pvarg, 0);
  v24 = Unknown;
  if ( !Unknown )
  {
    v6 = -2147024809;
    v22 = -2147024809;
    goto LABEL_28;
  }
  v6 = CreateStreamInputSource(*((struct IMalloc **)this + 1), Unknown, *((_BYTE *)this + 1791), &v25);
  v22 = v6;
  if ( !v6 )
  {
    v18 = *((_DWORD *)this + 118);
    if ( *((_DWORD *)this + 119) == v18 )
    {
      _stack<void (Scanner::*)(void),8>::grow((__int64)this + 448, 0);
      v18 = *((_DWORD *)this + 118);
    }
    v19 = (struct InputSource **)(*((_QWORD *)this + 58) + 8LL * v18);
    *((_DWORD *)this + 118) = v18 + 1;
    v20 = v25;
    *v19 = v25;
    (*(void (__fastcall **)(struct InputSource *, struct DeclEntity *))(*(_QWORD *)v20 + 48LL))(v20, a2);
    v11 = v20;
LABEL_18:
    Scanner::PushInputSource((YReader *)((char *)this + 40), v11);
    if ( !*((_BYTE *)a2 + 132) )
    {
      if ( *((_QWORD *)a2 + 17) )
      {
        v6 = -1072894395;
        v22 = -1072894395;
        goto LABEL_28;
      }
      *((_QWORD *)a2 + 17) = a3;
    }
    if ( *((_BYTE *)a2 + 128) )
    {
      *((_BYTE *)this + 1794) = 1;
      ++*((_DWORD *)this + 464);
    }
  }
LABEL_28:
  VariantClear(&pvarg);
  if ( v6 < 0 )
  {
    _mm_lfence();
    MXRRaiseException(v22);
    JUMPOUT(0x10040A9F1LL);
  }
  return a2;
}

```

## disassembly

```asm
0x10040a750  mov     rax, rsp
0x10040a753  mov     [rax+18h], rbx
0x10040a757  mov     [rax+10h], rdx
0x10040a75b  mov     [rax+8], rcx
0x10040a75f  push    rsi
0x10040a760  push    rdi
0x10040a761  push    r12
0x10040a763  push    r14
0x10040a765  push    r15
0x10040a767  sub     rsp, 80h
0x10040a76e  mov     r12, r8
0x10040a771  mov     r14, rdx
0x10040a774  mov     rsi, rcx
0x10040a777  xor     edi, edi
0x10040a779  mov     [rax-78h], edi
0x10040a77c  mov     [rax+20h], rdi
0x10040a780  lea     rcx, [rax-58h]; pvarg
0x10040a784  call    cs:__imp_VariantInit
0x10040a78a  nop
0x10040a78b  test    r14, r14
0x10040a78e  jz      loc_10040A96B
0x10040a794  cmp     [r14+60h], rdi
0x10040a798  jz      short loc_10040A815
0x10040a79a  mov     rdx, [rsi+8]; struct IMalloc *
0x10040a79e  lea     ecx, [rdi+58h]; dwBytes
0x10040a7a1  call    ??2Base@@SAPEAX_KPEAUIMalloc@@@Z; Base::operator new(unsigned __int64,IMalloc *)
0x10040a7a6  test    rax, rax
0x10040a7a9  jz      short loc_10040A7C0
0x10040a7ab  lea     r8, [r14+60h]; struct StringPtr *
0x10040a7af  mov     rdx, [rsi+8]; struct IMalloc *
0x10040a7b3  mov     rcx, rax; this
0x10040a7b6  call    ??0StringPtrInputSource@@QEAA@PEAUIMalloc@@PEAUStringPtr@@@Z; StringPtrInputSource::StringPtrInputSource(IMalloc *,StringPtr *)
0x10040a7bb  mov     r15, rax
0x10040a7be  jmp     short loc_10040A7C3
0x10040a7c0  mov     r15, rdi
0x10040a7c3  mov     [rsp+0A8h+arg_18], r15
0x10040a7cb  lea     rbx, [rsi+1C0h]
0x10040a7d2  mov     edx, [rbx+18h]
0x10040a7d5  cmp     [rbx+1Ch], edx
0x10040a7d8  jnz     short loc_10040A7E7
0x10040a7da  xor     edx, edx
0x10040a7dc  mov     rcx, rbx
0x10040a7df  call    ?grow@?$_stack@P8Scanner@@EAAXXZ$07@@AEAAXI@Z; _stack<void (Scanner::*)(void),8>::grow(uint)
0x10040a7e4  mov     edx, [rbx+18h]
0x10040a7e7  mov     ecx, edx
0x10040a7e9  mov     rax, [rbx+10h]
0x10040a7ed  lea     r8, [rax+rcx*8]
0x10040a7f1  lea     eax, [rdx+1]
0x10040a7f4  mov     [rbx+18h], eax
0x10040a7f7  mov     [r8], r15
0x10040a7fa  mov     rax, [r15]
0x10040a7fd  mov     rdx, r14
0x10040a800  mov     rcx, r15
0x10040a803  mov     rax, [rax+30h]
0x10040a807  call    cs:__guard_dispatch_icall_fptr
0x10040a80d  mov     rdx, r15
0x10040a810  jmp     loc_10040A914
0x10040a815  mov     r15, [rsi+2040h]
0x10040a81c  test    r15, r15
0x10040a81f  jz      loc_10040A967
0x10040a825  mov     rdi, [r15]
0x10040a828  mov     rax, [r14]
0x10040a82b  mov     rcx, r14
0x10040a82e  mov     rax, [rax+28h]
0x10040a832  call    cs:__guard_dispatch_icall_fptr
0x10040a838  mov     rbx, [rax]
0x10040a83b  mov     rax, [r14]
0x10040a83e  mov     rcx, r14
0x10040a841  mov     rax, [rax+18h]
0x10040a845  call    cs:__guard_dispatch_icall_fptr
0x10040a84b  lea     r9, [rsp+0A8h+pvarg]
0x10040a850  mov     r8, rbx
0x10040a853  mov     rdx, [rax]
0x10040a856  mov     rcx, r15
0x10040a859  mov     rax, [rdi+18h]
0x10040a85d  call    cs:__guard_dispatch_icall_fptr
0x10040a863  mov     [rsp+0A8h+var_78], eax
0x10040a867  mov     ecx, 80004005h
0x10040a86c  test    eax, eax
0x10040a86e  cmovnz  eax, ecx
0x10040a871  mov     [rsp+0A8h+var_78], eax
0x10040a875  mov     edi, eax
0x10040a877  mov     [rsp+0A8h+var_78], eax
0x10040a87b  test    eax, eax
0x10040a87d  jnz     loc_10040A9BA
0x10040a883  xor     edx, edx; bool
0x10040a885  lea     rcx, [rsp+0A8h+pvarg]; struct tagVARIANT *
0x10040a88a  call    ?getUnknown@Variant@@SAPEAUIUnknown@@PEAUtagVARIANT@@_N@Z; Variant::getUnknown(tagVARIANT *,bool)
0x10040a88f  mov     [rsp+0A8h+var_40], rax
0x10040a894  test    rax, rax
0x10040a897  jz      loc_10040A95C
0x10040a89d  lea     r9, [rsp+0A8h+arg_18]; struct InputSource **
0x10040a8a5  movzx   r8d, byte ptr [rsi+6FFh]; bool
0x10040a8ad  mov     rdx, rax; struct IUnknown *
0x10040a8b0  mov     rcx, [rsi+8]; struct IMalloc *
0x10040a8b4  call    ?CreateStreamInputSource@@YAJPEAUIMalloc@@PEAUIUnknown@@_NPEAPEAVInputSource@@@Z; CreateStreamInputSource(IMalloc *,IUnknown *,bool,InputSource * *)
0x10040a8b9  mov     edi, eax
0x10040a8bb  mov     [rsp+0A8h+var_78], eax
0x10040a8bf  test    eax, eax
0x10040a8c1  jnz     loc_10040A9BA
0x10040a8c7  lea     rbx, [rsi+1C0h]
0x10040a8ce  mov     edx, [rbx+18h]
0x10040a8d1  cmp     [rbx+1Ch], edx
0x10040a8d4  jnz     short loc_10040A8E3
0x10040a8d6  xor     edx, edx
0x10040a8d8  mov     rcx, rbx
0x10040a8db  call    ?grow@?$_stack@P8Scanner@@EAAXXZ$07@@AEAAXI@Z; _stack<void (Scanner::*)(void),8>::grow(uint)
0x10040a8e0  mov     edx, [rbx+18h]
0x10040a8e3  mov     ecx, edx
0x10040a8e5  mov     rax, [rbx+10h]
0x10040a8e9  lea     r8, [rax+rcx*8]
0x10040a8ed  lea     eax, [rdx+1]
0x10040a8f0  mov     [rbx+18h], eax
0x10040a8f3  mov     rbx, [rsp+0A8h+arg_18]
0x10040a8fb  mov     [r8], rbx
0x10040a8fe  mov     rax, [rbx]
0x10040a901  mov     rdx, r14
0x10040a904  mov     rcx, rbx
0x10040a907  mov     rax, [rax+30h]
0x10040a90b  call    cs:__guard_dispatch_icall_fptr
0x10040a911  mov     rdx, rbx; struct InputSource *
0x10040a914  lea     rcx, [rsi+28h]; this
0x10040a918  call    ?PushInputSource@Scanner@@QEAAXPEAVInputSource@@@Z; Scanner::PushInputSource(InputSource *)
0x10040a91d  cmp     byte ptr [r14+84h], 0
0x10040a925  jnz     short loc_10040A943
0x10040a927  cmp     qword ptr [r14+88h], 0
0x10040a92f  jz      short loc_10040A93C
0x10040a931  mov     edi, 0C00CEE45h
0x10040a936  mov     [rsp+0A8h+var_78], edi
0x10040a93a  jmp     short loc_10040A9BA
0x10040a93c  mov     [r14+88h], r12
0x10040a943  cmp     byte ptr [r14+80h], 0
0x10040a94b  jz      short loc_10040A95A
0x10040a94d  mov     byte ptr [rsi+702h], 1
0x10040a954  inc     dword ptr [rsi+740h]
0x10040a95a  jmp     short loc_10040A9BA
0x10040a95c  mov     edi, 80070057h
0x10040a961  mov     [rsp+0A8h+var_78], edi
0x10040a965  jmp     short loc_10040A9BA
0x10040a967  xor     eax, eax
0x10040a969  jmp     short loc_10040A9CC
0x10040a96b  xor     eax, eax
0x10040a96d  jmp     short loc_10040A9CC
0x10040a96f  mov     rcx, [rsp+0A8h+arg_0]
0x10040a977  mov     edx, [rcx+1D8h]
0x10040a97d  dec     edx
0x10040a97f  mov     rax, [rcx+1D0h]
0x10040a986  mov     rcx, [rsp+0A8h+arg_18]
0x10040a98e  cmp     [rax+rdx*8], rcx
0x10040a992  jz      short loc_10040A9AA
0x10040a994  test    rcx, rcx
0x10040a997  jz      short loc_10040A9AA
0x10040a999  mov     rax, [rcx]
0x10040a99c  mov     edx, 1
0x10040a9a1  mov     rax, [rax]
0x10040a9a4  call    cs:__guard_dispatch_icall_fptr
0x10040a9aa  mov     edi, [rsp+0A8h+var_74]
0x10040a9ae  mov     [rsp+0A8h+var_78], edi
0x10040a9b2  mov     r14, [rsp+0A8h+arg_8]
0x10040a9ba  lea     rcx, [rsp+0A8h+pvarg]; pvarg
0x10040a9bf  call    cs:__imp_VariantClear
0x10040a9c5  test    edi, edi
0x10040a9c7  js      short loc_10040A9E4
0x10040a9c9  mov     rax, r14
0x10040a9cc  mov     rbx, [rsp+0A8h+arg_10]
0x10040a9d4  add     rsp, 80h
0x10040a9db  pop     r15
0x10040a9dd  pop     r14
0x10040a9df  pop     r12
0x10040a9e1  pop     rdi
0x10040a9e2  pop     rsi
0x10040a9e3  retn
0x10040a9e4  lfence
0x10040a9e7  mov     ecx, [rsp+0A8h+var_78]; int
0x10040a9eb  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x10040a9f0  nop
0x10043a000  push    rbp
0x10043a002  sub     rsp, 30h
0x10043a006  mov     rbp, rdx
0x10043a009  mov     [rbp+70h], rcx
0x10043a00d  mov     [rbp+48h], rcx
0x10043a011  mov     rax, [rbp+48h]
0x10043a015  mov     rcx, [rax]
0x10043a018  mov     [rbp+40h], rcx
0x10043a01c  mov     rax, [rbp+40h]
0x10043a020  mov     eax, [rax]
0x10043a022  cmp     eax, 0C0000005h
0x10043a027  jz      short loc_10043A059
0x10043a029  add     eax, 1FFFFFFFh
0x10043a02e  cmp     eax, 1
0x10043a031  ja      short loc_10043A049
0x10043a033  mov     rax, [rbp+40h]
0x10043a037  cmp     dword ptr [rax+18h], 1
0x10043a03b  jnz     short loc_10043A049
0x10043a03d  mov     rax, [rbp+40h]
0x10043a041  mov     ecx, [rax+20h]
0x10043a044  mov     [rbp+34h], ecx
0x10043a047  jmp     short loc_10043A050
0x10043a049  mov     dword ptr [rbp+34h], 8000FFFFh
0x10043a050  mov     dword ptr [rbp+38h], 1
0x10043a057  jmp     short loc_10043A060
0x10043a059  mov     dword ptr [rbp+38h], 0
0x10043a060  mov     eax, [rbp+38h]
0x10043a063  add     rsp, 30h
0x10043a067  pop     rbp
0x10043a068  retn
```
