# SXWriter::put_output(tagVARIANT)

- ea: `0x1004082d0`
- end: `0x100408447`
- name: `?put_output@SXWriter@@UEAAJUtagVARIANT@@@Z`
- size: `375`
- prototype: `int(SXWriter *__hidden this, struct tagVARIANT *__struct_ptr)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x100401350`
- `0x1004082d0`
- `0x1004087e0`
- `0x100413940`
- `0x100414140`
- `0x100424580`

## pseudocode

```c
__int64 __fastcall SXWriter::put_output(SXWriter *this, struct tagVARIANT *a2)
{
  unsigned int v4; // ebx
  VARTYPE vt; // si
  struct tagVARIANT *pvarVal; // rcx
  struct tagVARIANT *BaseVariant; // r15
  unsigned __int16 v8; // si
  BSTR bstrVal; // rax
  int (__fastcall ***llVal)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v11; // rsi
  __int64 *v12; // r14
  __int64 v13; // rax
  __int64 *v14; // rcx
  __int64 v16; // [rsp+78h] [rbp+10h] BYREF
  int (__fastcall ***v17)(_QWORD, _QWORD, _QWORD); // [rsp+80h] [rbp+18h]

  v4 = 0;
  vt = a2->vt;
  if ( a2->vt == 16396 && (pvarVal = a2->pvarVal) != 0 )
  {
    BaseVariant = Variant::getBaseVariant(pvarVal);
    vt = BaseVariant->vt;
  }
  else
  {
    BaseVariant = a2;
  }
  v8 = vt & 0xBFFF;
  v16 = 0;
  SXWriter::commitStream((SXWriter *)((char *)this - 16));
  if ( ((v8 - 9) & 0xFFFB) != 0 )
  {
    if ( v8 >= 2u && (v8 != 8 || (bstrVal = BaseVariant->bstrVal) != 0 && *bstrVal) )
    {
      MXRRaiseException(-2147024809);
      __debugbreak();
      JUMPOUT(0x100408447LL);
    }
    goto LABEL_18;
  }
  llVal = (int (__fastcall ***)(_QWORD, _QWORD, _QWORD))Variant::getBaseVariant(a2)->llVal;
  v17 = llVal;
  if ( !llVal )
  {
LABEL_18:
    v14 = (__int64 *)*((_QWORD *)this + 13);
    *((_QWORD *)this + 13) = 0;
    if ( !v14 )
      goto LABEL_21;
    v13 = *v14;
    goto LABEL_20;
  }
  if ( (**llVal)(llVal, &IID_IStream, &v16) < 0 )
  {
    v4 = -2147024809;
    goto LABEL_21;
  }
  v11 = v16;
  v12 = (__int64 *)*((_QWORD *)this + 13);
  if ( v16 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 8LL))(v16);
  *((_QWORD *)this + 13) = v11;
  if ( v12 )
  {
    v13 = *v12;
    v14 = v12;
LABEL_20:
    (*(void (__fastcall **)(__int64 *))(v13 + 16))(v14);
  }
LABEL_21:
  *((_BYTE *)this + 235) = 0;
  *((_QWORD *)this + 36) = (char *)this + 337;
  if ( v16 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  return v4;
}

```

## disassembly

```asm
0x1004082d0  mov     [rsp+arg_0], rbx
0x1004082d5  mov     [rsp+arg_18], rsi
0x1004082da  push    rdi
0x1004082db  push    r14
0x1004082dd  push    r15
0x1004082df  sub     rsp, 50h
0x1004082e3  mov     r14, rdx
0x1004082e6  mov     rdi, rcx
0x1004082e9  xor     ebx, ebx
0x1004082eb  mov     [rsp+68h+var_40], ebx
0x1004082ef  movzx   esi, word ptr [rdx]
0x1004082f2  mov     eax, 400Ch
0x1004082f7  cmp     si, ax
0x1004082fa  jnz     short loc_100408312
0x1004082fc  mov     rcx, [rdx+8]; struct tagVARIANT *
0x100408300  test    rcx, rcx
0x100408303  jz      short loc_100408312
0x100408305  call    ?getBaseVariant@Variant@@SAPEAUtagVARIANT@@PEAU2@@Z; Variant::getBaseVariant(tagVARIANT *)
0x10040830a  mov     r15, rax
0x10040830d  movzx   esi, word ptr [rax]
0x100408310  jmp     short loc_100408315
0x100408312  mov     r15, r14
0x100408315  mov     eax, 0BFFFh
0x10040831a  and     si, ax
0x10040831d  mov     [rsp+68h+arg_8], rbx
0x100408322  lea     rcx, [rdi-10h]; this
0x100408326  call    ?commitStream@SXWriter@@IEAAXXZ; SXWriter::commitStream(void)
0x10040832b  lea     eax, [rsi-9]
0x10040832e  mov     ecx, 0FFFBh
0x100408333  test    cx, ax
0x100408336  jz      short loc_100408360
0x100408338  cmp     si, 2
0x10040833c  jb      loc_1004083CF
0x100408342  cmp     si, 8
0x100408346  jnz     loc_10040843B
0x10040834c  mov     rax, [r15+8]
0x100408350  test    rax, rax
0x100408353  jz      short loc_1004083CF
0x100408355  cmp     bx, [rax]
0x100408358  jnz     loc_10040843B
0x10040835e  jmp     short loc_1004083CF
0x100408360  mov     rcx, r14; struct tagVARIANT *
0x100408363  call    ?getBaseVariant@Variant@@SAPEAUtagVARIANT@@PEAU2@@Z; Variant::getBaseVariant(tagVARIANT *)
0x100408368  mov     rcx, [rax+8]
0x10040836c  mov     [rsp+68h+arg_10], rcx
0x100408374  test    rcx, rcx
0x100408377  jz      short loc_1004083CF
0x100408379  mov     rax, [rcx]
0x10040837c  lea     r8, [rsp+68h+arg_8]
0x100408381  lea     rdx, IID_IStream
0x100408388  mov     rax, [rax]
0x10040838b  call    cs:__guard_dispatch_icall_fptr
0x100408391  test    eax, eax
0x100408393  js      short loc_1004083C4
0x100408395  mov     rsi, [rsp+68h+arg_8]
0x10040839a  mov     r14, [rdi+68h]
0x10040839e  test    rsi, rsi
0x1004083a1  jz      short loc_1004083B3
0x1004083a3  mov     rax, [rsi]
0x1004083a6  mov     rcx, rsi
0x1004083a9  mov     rax, [rax+8]
0x1004083ad  call    cs:__guard_dispatch_icall_fptr
0x1004083b3  mov     [rdi+68h], rsi
0x1004083b7  test    r14, r14
0x1004083ba  jz      short loc_1004083E9
0x1004083bc  mov     rax, [r14]
0x1004083bf  mov     rcx, r14
0x1004083c2  jmp     short loc_1004083DF
0x1004083c4  mov     ebx, 80070057h
0x1004083c9  mov     [rsp+68h+var_40], ebx
0x1004083cd  jmp     short loc_1004083E9
0x1004083cf  mov     rcx, [rdi+68h]
0x1004083d3  test    rcx, rcx
0x1004083d6  mov     [rdi+68h], rbx
0x1004083da  jz      short loc_1004083E9
0x1004083dc  mov     rax, [rcx]
0x1004083df  mov     rax, [rax+10h]
0x1004083e3  call    cs:__guard_dispatch_icall_fptr
0x1004083e9  mov     byte ptr [rdi+0EBh], 0
0x1004083f0  lea     rax, [rdi+151h]
0x1004083f7  mov     [rdi+120h], rax
0x1004083fe  jmp     short loc_100408408
0x100408400  mov     ebx, [rsp+68h+var_48]
0x100408404  mov     [rsp+68h+var_40], ebx
0x100408408  mov     rsi, [rsp+68h+arg_8]
0x10040840d  test    rsi, rsi
0x100408410  jz      short loc_100408422
0x100408412  mov     rcx, [rsi]
0x100408415  mov     rax, [rcx+10h]
0x100408419  mov     rcx, rsi
0x10040841c  call    cs:__guard_dispatch_icall_fptr
0x100408422  mov     eax, ebx
0x100408424  mov     rbx, [rsp+68h+arg_0]
0x100408429  mov     rsi, [rsp+68h+arg_18]
0x100408431  add     rsp, 50h
0x100408435  pop     r15
0x100408437  pop     r14
0x100408439  pop     rdi
0x10040843a  retn
0x10040843b  mov     ecx, 80070057h; int
0x100408440  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x100408445  nop
0x100408446  int     3; Trap to Debugger
0x1004245b0  push    rbp
0x1004245b2  sub     rsp, 20h
0x1004245b6  mov     rbp, rdx
0x1004245b9  mov     [rbp+40h], rcx
0x1004245bd  mov     [rbp+38h], rcx
0x1004245c1  mov     rax, [rbp+38h]
0x1004245c5  mov     rcx, [rax]
0x1004245c8  mov     [rbp+30h], rcx
0x1004245cc  mov     rax, [rbp+30h]
0x1004245d0  mov     eax, [rax]
0x1004245d2  cmp     eax, 0C0000005h
0x1004245d7  jz      short loc_100424609
0x1004245d9  add     eax, 1FFFFFFFh
0x1004245de  cmp     eax, 1
0x1004245e1  ja      short loc_1004245F9
0x1004245e3  mov     rax, [rbp+30h]
0x1004245e7  cmp     dword ptr [rax+18h], 1
0x1004245eb  jnz     short loc_1004245F9
0x1004245ed  mov     rax, [rbp+30h]
0x1004245f1  mov     ecx, [rax+20h]
0x1004245f4  mov     [rbp+20h], ecx
0x1004245f7  jmp     short loc_100424600
0x1004245f9  mov     dword ptr [rbp+20h], 8000FFFFh
0x100424600  mov     dword ptr [rbp+24h], 1
0x100424607  jmp     short loc_100424610
0x100424609  mov     dword ptr [rbp+24h], 0
0x100424610  mov     eax, [rbp+24h]
0x100424613  add     rsp, 20h
0x100424617  pop     rbp
0x100424618  retn
```
