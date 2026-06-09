# CSREngine::SetRecoProfile(ISpObjectToken *)

- ea: `0x1800128e0`
- end: `0x180012be3`
- name: `?SetRecoProfile@CSREngine@@UEAAJPEAUISpObjectToken@@@Z`
- size: `771`
- prototype: `__int64 __fastcall(CSREngine *this, struct IUnknown *)`
- caller_count: `0`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callees

- `0x180004810`
- `0x1800055f8`
- `0x1800062a0`
- `0x180006c7c`
- `0x1800073b4`
- `0x18000ba90`
- `0x18000bb5c`
- `0x18000f628`
- `0x180011e44`
- `0x1800128e0`
- `0x180102010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800129a5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800129af`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800129a5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800129af`

## pseudocode

```c
__int64 __fastcall CSREngine::SetRecoProfile(CSREngine *this, struct IUnknown *a2)
{
  struct ISpObjectTokenVtbl *lpVtbl; // rax
  char v6; // si
  void *v7; // rcx
  unsigned __int16 *v8; // rax
  int v9; // r8d
  int v10; // r9d
  int inited; // edi
  unsigned int v12; // edi
  unsigned int v13; // esi
  unsigned int v14; // edx
  CAcousticModel *v15; // rcx
  CAcousticModel *v16; // rax
  CAcousticModel *v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  unsigned int v20; // [rsp+68h] [rbp+38h] BYREF
  LPVOID pv; // [rsp+70h] [rbp+40h] BYREF
  LPVOID v22; // [rsp+78h] [rbp+48h] BYREF

  v20 = 0;
  if ( !a2 )
    return 2147942487LL;
  if ( !*((_DWORD *)this + 199) && *((_QWORD *)this + 31) )
  {
    lpVtbl = (struct ISpObjectTokenVtbl *)a2->lpVtbl;
    pv = 0;
    v22 = 0;
    v6 = 0;
    if ( ((int (__fastcall *)(struct IUnknown *, LPVOID *))lpVtbl->GetId)(a2, &v22) < 0
      || (*(int (__fastcall **)(_QWORD, LPVOID *))(**((_QWORD **)this + 31) + 128LL))(*((_QWORD *)this + 31), &pv) < 0 )
    {
      v7 = pv;
    }
    else
    {
      v7 = pv;
      v8 = (unsigned __int16 *)v22;
      do
      {
        v9 = *(unsigned __int16 *)((char *)v8 + (_BYTE *)pv - (_BYTE *)v22);
        v10 = *v8 - v9;
        if ( v10 )
          break;
        ++v8;
      }
      while ( v9 );
      if ( !v10 )
        v6 = 1;
    }
    CoTaskMemFree(v7);
    CoTaskMemFree(v22);
    if ( v6 )
      return 0;
  }
  if ( *((_DWORD *)this + 46) || *((_DWORD *)this + 222) )
    return 2147766292LL;
  if ( *((struct IUnknown **)this + 31) != a2 )
    ATL::AtlComPtrAssign((struct IUnknown **)this + 31, a2);
  if ( *((int *)this + 225) > 0 )
  {
    inited = CSREngine::ReloadSLMs(this);
    if ( inited < 0 )
      goto LABEL_38;
  }
  *((_DWORD *)this + 216) = 1;
  *((_DWORD *)this + 217) = 1;
  *((_DWORD *)this + 221) = -1;
  CSREngine::GetProfileParameter(this, 96, &v20);
  v12 = v20;
  CSREngine::GetProfileParameter(this, 97, &v20);
  v13 = v20;
  CSREngine::GetProfileParameter(this, 7, &v20);
  *((_DWORD *)this + 218) = v20;
  CSREngine::GetProfileParameter(this, 3, &v20);
  *((_BYTE *)this + 786) = v20 != 0;
  CSREngine::GetProfileParameter(this, 98, &v20);
  *((_BYTE *)this + 424) = v20 != 0;
  CSREngine::GetProfileParameter(this, 8, &v20);
  if ( *((_DWORD *)this + 218) == 1 && v12 && v13 )
  {
    if ( !*((_DWORD *)this + 219) )
      CSREngine::SetProfileParameter(this, 7, 2u);
    *((_DWORD *)this + 218) = 2;
  }
  v15 = (CAcousticModel *)*((_QWORD *)this + 87);
  if ( v15 )
    CAcousticModel::`scalar deleting destructor'(v15, v14);
  v16 = (CAcousticModel *)CAllocOnSpecificHeapBase::operator_new(0x1C8u, *((struct CHeap **)this + 16), 0);
  if ( !v16 )
  {
    *((_QWORD *)this + 87) = 0;
    goto LABEL_37;
  }
  v17 = CAcousticModel::CAcousticModel(v16, this);
  *((_QWORD *)this + 87) = v17;
  if ( !v17 )
  {
LABEL_37:
    inited = -2147024882;
    goto LABEL_38;
  }
  inited = CAcousticModel::InitAM(v17, v13, v12, *((unsigned int *)this + 218));
  if ( inited >= 0 )
  {
    if ( *((_DWORD *)this + 219) != 1 )
      *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 17) + 64LL) + 52LL) = CSREngine::GetProfileRegValue(
                                                                         this,
                                                                         L"Adapted Accuracy",
                                                                         *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 17)
                                                                                               + 64LL)
                                                                                   + 52LL),
                                                                         0);
    *((_DWORD *)this + 199) = 0;
    goto LABEL_39;
  }
LABEL_38:
  *((_DWORD *)this + 199) = 1;
  *((_DWORD *)this + 222) = 0;
LABEL_39:
  v18 = *((_QWORD *)this + 17);
  *((_BYTE *)this + 800) = 0;
  if ( v18 )
  {
    v19 = *(_QWORD *)(v18 + 64);
    if ( v19 )
      *(_BYTE *)(v19 + 2595) = 0;
  }
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x1800128e0  mov     [rsp-28h+arg_0], rbx
0x1800128e5  push    rbp
0x1800128e6  push    rsi
0x1800128e7  push    rdi
0x1800128e8  push    r14
0x1800128ea  push    r15
0x1800128ec  mov     rbp, rsp
0x1800128ef  sub     rsp, 30h
0x1800128f3  xor     r14d, r14d
0x1800128f6  mov     rdi, rdx
0x1800128f9  mov     [rbp+arg_8], r14d
0x1800128fd  mov     rbx, rcx
0x180012900  test    rdx, rdx
0x180012903  jnz     short loc_18001290F
0x180012905  mov     eax, 80070057h
0x18001290a  jmp     loc_180012BD2
0x18001290f  mov     r15d, 1
0x180012915  cmp     [rcx+31Ch], r14d
0x18001291c  jnz     loc_1800129C1
0x180012922  cmp     [rcx+0F8h], r14
0x180012929  jz      loc_1800129C1
0x18001292f  mov     rax, [rdx]
0x180012932  mov     rcx, rdi
0x180012935  lea     rdx, [rbp+arg_18]
0x180012939  mov     [rbp+pv], r14
0x18001293d  mov     [rbp+arg_18], r14
0x180012941  movzx   esi, r14b
0x180012945  mov     rax, [rax+80h]
0x18001294c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012951  test    eax, eax
0x180012953  js      short loc_1800129A1
0x180012955  mov     rcx, [rbx+0F8h]
0x18001295c  lea     rdx, [rbp+pv]
0x180012960  mov     rax, [rcx]
0x180012963  mov     rax, [rax+80h]
0x18001296a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001296f  test    eax, eax
0x180012971  js      short loc_1800129A1
0x180012973  mov     rcx, [rbp+pv]
0x180012977  mov     rax, [rbp+arg_18]
0x18001297b  mov     rdx, rcx
0x18001297e  sub     rdx, rax
0x180012981  movzx   r9d, word ptr [rax]
0x180012985  movzx   r8d, word ptr [rax+rdx]
0x18001298a  sub     r9d, r8d
0x18001298d  jnz     short loc_180012998
0x18001298f  add     rax, 2
0x180012993  test    r8d, r8d
0x180012996  jnz     short loc_180012981
0x180012998  test    r9d, r9d
0x18001299b  cmovz   esi, r15d
0x18001299f  jmp     short loc_1800129A5
0x1800129a1  mov     rcx, [rbp+pv]; pv
0x1800129a5  call    cs:__imp_CoTaskMemFree
0x1800129ab  mov     rcx, [rbp+arg_18]; pv
0x1800129af  call    cs:__imp_CoTaskMemFree
0x1800129b5  test    sil, sil
0x1800129b8  jz      short loc_1800129C1
0x1800129ba  xor     eax, eax
0x1800129bc  jmp     loc_180012BD2
0x1800129c1  cmp     [rbx+0B8h], r14d
0x1800129c8  jnz     loc_180012BCD
0x1800129ce  cmp     [rbx+378h], r14d
0x1800129d5  jnz     loc_180012BCD
0x1800129db  lea     rcx, [rbx+0F8h]; struct IUnknown **
0x1800129e2  cmp     [rcx], rdi
0x1800129e5  jz      short loc_1800129EF
0x1800129e7  mov     rdx, rdi; struct IUnknown *
0x1800129ea  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x1800129ef  cmp     [rbx+384h], r14d
0x1800129f6  jle     short loc_180012A0A
0x1800129f8  mov     rcx, rbx; this
0x1800129fb  call    ?ReloadSLMs@CSREngine@@QEAAJXZ; CSREngine::ReloadSLMs(void)
0x180012a00  mov     edi, eax
0x180012a02  test    eax, eax
0x180012a04  js      loc_180012B98
0x180012a0a  lea     r8, [rbp+arg_8]; unsigned int *
0x180012a0e  mov     [rbx+360h], r15d
0x180012a15  mov     edx, 60h ; '`'; int
0x180012a1a  mov     [rbx+364h], r15d
0x180012a21  mov     rcx, rbx; this
0x180012a24  mov     dword ptr [rbx+374h], 0FFFFFFFFh
0x180012a2e  call    ?GetProfileParameter@CSREngine@@AEAAJHPEAK@Z; CSREngine::GetProfileParameter(int,ulong *)
0x180012a33  mov     edi, [rbp+arg_8]
0x180012a36  lea     r8, [rbp+arg_8]; unsigned int *
0x180012a3a  mov     edx, 61h ; 'a'; int
0x180012a3f  mov     rcx, rbx; this
0x180012a42  call    ?GetProfileParameter@CSREngine@@AEAAJHPEAK@Z; CSREngine::GetProfileParameter(int,ulong *)
0x180012a47  mov     esi, [rbp+arg_8]
0x180012a4a  lea     r8, [rbp+arg_8]; unsigned int *
0x180012a4e  mov     edx, 7; int
0x180012a53  mov     rcx, rbx; this
0x180012a56  call    ?GetProfileParameter@CSREngine@@AEAAJHPEAK@Z; CSREngine::GetProfileParameter(int,ulong *)
0x180012a5b  mov     eax, [rbp+arg_8]
0x180012a5e  lea     r8, [rbp+arg_8]; unsigned int *
0x180012a62  mov     edx, 3; int
0x180012a67  mov     [rbx+368h], eax
0x180012a6d  mov     rcx, rbx; this
0x180012a70  call    ?GetProfileParameter@CSREngine@@AEAAJHPEAK@Z; CSREngine::GetProfileParameter(int,ulong *)
0x180012a75  cmp     [rbp+arg_8], r14d
0x180012a79  lea     r8, [rbp+arg_8]; unsigned int *
0x180012a7d  mov     edx, 62h ; 'b'; int
0x180012a82  mov     rcx, rbx; this
0x180012a85  setnz   al
0x180012a88  mov     [rbx+312h], al
0x180012a8e  call    ?GetProfileParameter@CSREngine@@AEAAJHPEAK@Z; CSREngine::GetProfileParameter(int,ulong *)
0x180012a93  cmp     [rbp+arg_8], r14d
0x180012a97  lea     r8, [rbp+arg_8]; unsigned int *
0x180012a9b  mov     edx, 8; int
0x180012aa0  mov     rcx, rbx; this
0x180012aa3  setnz   al
0x180012aa6  mov     [rbx+1A8h], al
0x180012aac  call    ?GetProfileParameter@CSREngine@@AEAAJHPEAK@Z; CSREngine::GetProfileParameter(int,ulong *)
0x180012ab1  cmp     [rbx+368h], r15d
0x180012ab8  jnz     short loc_180012AE6
0x180012aba  test    edi, edi
0x180012abc  jz      short loc_180012AE6
0x180012abe  test    esi, esi
0x180012ac0  jz      short loc_180012AE6
0x180012ac2  cmp     [rbx+36Ch], r14d
0x180012ac9  jnz     short loc_180012ADC
0x180012acb  mov     edx, 7; int
0x180012ad0  mov     rcx, rbx; this
0x180012ad3  lea     r8d, [rdx-5]; unsigned int
0x180012ad7  call    ?SetProfileParameter@CSREngine@@AEAAJHK@Z; CSREngine::SetProfileParameter(int,ulong)
0x180012adc  mov     dword ptr [rbx+368h], 2
0x180012ae6  mov     rcx, [rbx+2B8h]; this
0x180012aed  test    rcx, rcx
0x180012af0  jz      short loc_180012AF7
0x180012af2  call    ??_GCAcousticModel@@QEAAPEAXI@Z; CAcousticModel::`scalar deleting destructor'(uint)
0x180012af7  mov     rdx, [rbx+80h]; struct CHeap *
0x180012afe  xor     r8d, r8d; bool
0x180012b01  mov     ecx, 1C8h; unsigned __int64
0x180012b06  call    ?operator_new@CAllocOnSpecificHeapBase@@SAPEAX_KPEAVCHeap@@_N@Z; CAllocOnSpecificHeapBase::operator_new(unsigned __int64,CHeap *,bool)
0x180012b0b  test    rax, rax
0x180012b0e  jz      short loc_180012B8C
0x180012b10  mov     rdx, rbx; struct CSREngine *
0x180012b13  mov     rcx, rax; this
0x180012b16  call    ??0CAcousticModel@@QEAA@PEAVCSREngine@@@Z; CAcousticModel::CAcousticModel(CSREngine *)
0x180012b1b  mov     [rbx+2B8h], rax
0x180012b22  test    rax, rax
0x180012b25  jz      short loc_180012B93
0x180012b27  mov     ecx, [rbx+2C0h]
0x180012b2d  mov     r8d, edi
0x180012b30  mov     r9d, [rbx+368h]
0x180012b37  mov     edx, esi
0x180012b39  mov     [rsp+30h+var_8], ecx
0x180012b3d  mov     rcx, rax
0x180012b40  call    ?InitAM@CAcousticModel@@QEAAJW4MSAM_AGE@@W4MSAM_GENDER@@W4MSAM_AUTOD@@W4MSAM_USAGE@@K@Z; CAcousticModel::InitAM(MSAM_AGE,MSAM_GENDER,MSAM_AUTOD,MSAM_USAGE,ulong)
0x180012b45  mov     edi, eax
0x180012b47  test    eax, eax
0x180012b49  js      short loc_180012B98
0x180012b4b  cmp     [rbx+36Ch], r15d
0x180012b52  jz      short loc_180012B83
0x180012b54  mov     rax, [rbx+88h]
0x180012b5b  lea     rdx, aAdaptedAccurac; "Adapted Accuracy"
0x180012b62  xor     r9d, r9d; bool
0x180012b65  mov     rcx, rbx; this
0x180012b68  mov     r8, [rax+40h]
0x180012b6c  mov     r8d, [r8+34h]; unsigned int
0x180012b70  call    ?GetProfileRegValue@CSREngine@@AEAAKPEBGK_N@Z; CSREngine::GetProfileRegValue(ushort const *,ulong,bool)
0x180012b75  mov     rcx, [rbx+88h]
0x180012b7c  mov     rdx, [rcx+40h]
0x180012b80  mov     [rdx+34h], eax
0x180012b83  mov     [rbx+31Ch], r14d
0x180012b8a  jmp     short loc_180012BA6
0x180012b8c  mov     [rbx+2B8h], r14
0x180012b93  mov     edi, 8007000Eh
0x180012b98  mov     [rbx+31Ch], r15d
0x180012b9f  mov     [rbx+378h], r14d
0x180012ba6  mov     rax, [rbx+88h]
0x180012bad  mov     [rbx+320h], r14b
0x180012bb4  test    rax, rax
0x180012bb7  jz      short loc_180012BC9
0x180012bb9  mov     rax, [rax+40h]
0x180012bbd  test    rax, rax
0x180012bc0  jz      short loc_180012BC9
0x180012bc2  mov     [rax+0A23h], r14b
0x180012bc9  mov     eax, edi
0x180012bcb  jmp     short loc_180012BD2
0x180012bcd  mov     eax, 80045014h
0x180012bd2  mov     rbx, [rsp+30h+arg_0]
0x180012bd7  add     rsp, 30h
0x180012bdb  pop     r15
0x180012bdd  pop     r14
0x180012bdf  pop     rdi
0x180012be0  pop     rsi
0x180012be1  pop     rbp
0x180012be2  retn
```
