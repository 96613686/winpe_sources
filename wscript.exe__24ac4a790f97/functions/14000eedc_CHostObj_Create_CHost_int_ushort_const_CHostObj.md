# CHostObj::Create(CHost *,int,ushort const * *,CHostObj * *)

- ea: `0x14000eedc`
- end: `0x14000f1a5`
- name: `?Create@CHostObj@@SAJPEAVCHost@@HPEAPEBGPEAPEAV1@@Z`
- size: `713`
- prototype: `static int(struct CHost *, int, const unsigned __int16 **, struct CHostObj **)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x14000757c`

## callees

- `0x140001008`
- `0x14000eedc`
- `0x140012d54`
- `0x1400146ac`
- `0x140016158`
- `0x140017542`
- `0x1400175a0`
- `0x140018010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x14000efc3`
- `OLEAUT32!__imp_SysAllocString` at `0x14000f04d`
- `OLEAUT32!__imp_SysAllocString` at `0x14000efc3`
- `OLEAUT32!__imp_SysAllocString` at `0x14000f04d`
- `OLEAUT32!__imp_LoadTypeLib` at `0x14000f086`
- `OLEAUT32!__imp_LoadTypeLib` at `0x14000f086`

## pseudocode

```c
__int64 __fastcall CHostObj::Create(struct CHost *a1, int a2, const unsigned __int16 **a3, unsigned __int16 ***a4)
{
  struct CArguments *v7; // rsi
  unsigned __int16 **v9; // rax
  __int64 v10; // rdx
  __int64 v11; // r8
  unsigned __int16 **v12; // rdi
  unsigned int v13; // ebx
  const OLECHAR *v14; // r14
  BSTR v15; // rax
  OLECHAR v16; // ax
  const OLECHAR *v17; // rcx
  const OLECHAR *v18; // rdx
  unsigned __int64 v19; // rcx
  __int64 v20; // rbx
  BSTR v21; // rax
  HRESULT v22; // ebx
  int v23; // eax
  struct ITypeLib *v24; // r14
  int v25; // eax
  ITypeLib *pptlib; // [rsp+20h] [rbp-E0h] BYREF
  struct CArguments *v28; // [rsp+28h] [rbp-D8h] BYREF
  OLECHAR psz[264]; // [rsp+30h] [rbp-D0h] BYREF

  pptlib = 0;
  v7 = 0;
  v28 = 0;
  v9 = (unsigned __int16 **)operator new(0x88u);
  v11 = 0;
  v12 = v9;
  if ( !v9 )
  {
    v12 = 0;
    goto LABEL_26;
  }
  v9[2] = (unsigned __int16 *)&CUnknown::`vftable';
  v9[5] = (unsigned __int16 *)&CUnknown::InnerUnknown::`vftable';
  v13 = 1;
  *((_DWORD *)v9 + 12) = 1;
  v9[3] = (unsigned __int16 *)(v9 + 5);
  v9[4] = (unsigned __int16 *)v9;
  _InterlockedAdd(&Global::g_cObjects, 1u);
  *((_BYTE *)v9 + 64) = 0;
  v9[7] = (unsigned __int16 *)&TaUser_DescCHostObj;
  *v9 = (unsigned __int16 *)&CHostObj::`vftable'{for `IHost'};
  v9[1] = (unsigned __int16 *)&CUnnamedArguments::`vftable'{for `IProvideClassInfo'};
  v9[2] = (unsigned __int16 *)&CHostObj::`vftable'{for `CDispatch'};
  v9[10] = 0;
  v9[9] = 0;
  v9[11] = 0;
  v9[12] = 0;
  v9[13] = 0;
  v9[14] = 0;
  v9[15] = 0;
  v9[16] = (unsigned __int16 *)a1;
  v14 = (const OLECHAR *)((char *)a1 + 80);
  v15 = SysAllocString(v14);
  v11 = 0;
  v12[10] = v15;
  if ( !v15 )
  {
LABEL_26:
    v22 = -2147024882;
    goto LABEL_27;
  }
  v16 = *v14;
  v17 = v14;
  v18 = v14;
  while ( v16 )
  {
    if ( v16 == 47 || v16 == 92 )
      v17 = v18;
    v16 = *++v18;
  }
  psz[0] = 0;
  if ( v17 != v14 )
  {
    v19 = (unsigned __int64)((char *)v17 - (char *)v14) >> 1;
    if ( (_DWORD)v19 )
    {
      if ( (unsigned int)(v19 + 1) >= 0x104 )
        goto LABEL_15;
      v13 = v19;
    }
    v20 = v13;
    memcpy_0(psz, v14, v20 * 2);
    psz[v20] = 0;
    goto LABEL_15;
  }
  *(_DWORD *)psz = 46;
LABEL_15:
  v21 = SysAllocString(psz);
  v12[11] = v21;
  if ( !v21 )
    goto LABEL_26;
  LoadStr(v12 + 9, Global::g_lResourceBase + 1);
  v11 = 0;
  if ( !v12[9] )
    goto LABEL_26;
  v22 = LoadTypeLib(v14, &pptlib);
  if ( v22 >= 0 )
  {
    v22 = CDispatch::CacheTypeInfo((CDispatch *)(v12 + 2), pptlib);
    if ( v22 >= 0 )
    {
      v23 = CArguments::Create(a2, a3, &v28);
      v7 = v28;
      v22 = v23;
      if ( v23 >= 0 )
      {
        v24 = pptlib;
        v22 = CDispatch::CacheTypeInfo((CDispatch *)(*((_QWORD *)v28 + 11) + 16LL), pptlib);
        if ( v22 >= 0 )
        {
          v22 = CDispatch::CacheTypeInfo((CDispatch *)(*((_QWORD *)v7 + 12) + 16LL), v24);
          if ( v22 >= 0 )
          {
            v22 = CDispatch::CacheTypeInfo((struct CArguments *)((char *)v7 + 24), v24);
            if ( v22 >= 0 )
            {
              v25 = (**(__int64 (__fastcall ***)(struct CArguments *, GUID *, __int64))v7)(
                      v7,
                      &IID_IArguments2,
                      (__int64)(v12 + 12));
              v11 = 0;
              v22 = v25;
              if ( v25 >= 0 )
              {
                *a4 = v12;
                v22 = 0;
                v12 = 0;
              }
            }
          }
        }
      }
    }
  }
LABEL_27:
  if ( pptlib )
    ((void (__fastcall *)(ITypeLib *, __int64, __int64))pptlib->lpVtbl->Release)(pptlib, v10, v11);
  if ( v7 )
    (*(void (__fastcall **)(struct CArguments *, __int64, __int64))(*(_QWORD *)v7 + 16LL))(v7, v10, v11);
  if ( v12 )
    (*((void (__fastcall **)(unsigned __int16 **, __int64, __int64))*v12 + 2))(v12, v10, v11);
  return (unsigned int)v22;
}

```

## disassembly

```asm
0x14000eedc  push    rbp
0x14000eede  push    rbx
0x14000eedf  push    rsi
0x14000eee0  push    rdi
0x14000eee1  push    r12
0x14000eee3  push    r13
0x14000eee5  push    r14
0x14000eee7  push    r15
0x14000eee9  lea     rbp, [rsp-158h]
0x14000eef1  sub     rsp, 258h
0x14000eef8  mov     rax, cs:__security_cookie
0x14000eeff  xor     rax, rsp
0x14000ef02  mov     [rbp+190h+var_50], rax
0x14000ef09  mov     r14, rcx
0x14000ef0c  mov     r13, r9
0x14000ef0f  xor     ecx, ecx
0x14000ef11  mov     r12, r8
0x14000ef14  mov     [rsp+290h+pptlib], rcx
0x14000ef19  mov     esi, ecx
0x14000ef1b  mov     [rsp+290h+var_268], rcx
0x14000ef20  mov     r15d, edx
0x14000ef23  mov     ecx, 88h; Size
0x14000ef28  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000ef2d  xor     r8d, r8d
0x14000ef30  mov     rdi, rax
0x14000ef33  test    rax, rax
0x14000ef36  jz      loc_14000F13A
0x14000ef3c  lea     rax, ??_7CUnknown@@6B@; const CUnknown::`vftable'
0x14000ef43  mov     [rdi+10h], rax
0x14000ef47  lea     rcx, ??_7InnerUnknown@CUnknown@@6B@; const CUnknown::InnerUnknown::`vftable'
0x14000ef4e  lea     rax, [rdi+28h]
0x14000ef52  mov     [rax], rcx
0x14000ef55  lea     ebx, [rsi+1]
0x14000ef58  mov     [rax+8], ebx
0x14000ef5b  mov     [rdi+18h], rax
0x14000ef5f  mov     [rdi+20h], rdi
0x14000ef63  lock add cs:?g_cObjects@Global@@2JA, ebx; long Global::g_cObjects
0x14000ef6a  mov     [rdi+40h], r8b
0x14000ef6e  lea     rax, ?TaUser_DescCHostObj@@3UTaDescDispatch@@A; TaDescDispatch TaUser_DescCHostObj
0x14000ef75  mov     [rdi+38h], rax
0x14000ef79  lea     rax, ??_7CHostObj@@6BIHost@@@; const CHostObj::`vftable'{for `IHost'}
0x14000ef80  mov     [rdi], rax
0x14000ef83  lea     rax, ??_7CUnnamedArguments@@6BIProvideClassInfo@@@; const CUnnamedArguments::`vftable'{for `IProvideClassInfo'}
0x14000ef8a  mov     [rdi+8], rax
0x14000ef8e  lea     rax, ??_7CHostObj@@6BCDispatch@@@; const CHostObj::`vftable'{for `CDispatch'}
0x14000ef95  mov     [rdi+10h], rax
0x14000ef99  mov     [rdi+50h], r8
0x14000ef9d  mov     [rdi+48h], r8
0x14000efa1  mov     [rdi+58h], r8
0x14000efa5  mov     [rdi+60h], r8
0x14000efa9  mov     [rdi+68h], r8
0x14000efad  mov     [rdi+70h], r8
0x14000efb1  mov     [rdi+78h], r8
0x14000efb5  mov     [rdi+80h], r14
0x14000efbc  add     r14, 50h ; 'P'
0x14000efc0  mov     rcx, r14; psz
0x14000efc3  call    cs:__imp_SysAllocString
0x14000efc9  xor     r8d, r8d
0x14000efcc  mov     [rdi+50h], rax
0x14000efd0  test    rax, rax
0x14000efd3  jz      loc_14000F13D
0x14000efd9  movzx   eax, word ptr [r14]
0x14000efdd  mov     rcx, r14
0x14000efe0  mov     rdx, r14
0x14000efe3  jmp     short loc_14000EFFB
0x14000efe5  cmp     ax, 2Fh ; '/'
0x14000efe9  jz      short loc_14000EFF1
0x14000efeb  cmp     ax, 5Ch ; '\'
0x14000efef  jnz     short loc_14000EFF4
0x14000eff1  mov     rcx, rdx
0x14000eff4  add     rdx, 2
0x14000eff8  movzx   eax, word ptr [rdx]
0x14000effb  test    ax, ax
0x14000effe  jnz     short loc_14000EFE5
0x14000f000  mov     [rsp+290h+psz], r8w
0x14000f006  cmp     rcx, r14
0x14000f009  jnz     short loc_14000F015
0x14000f00b  mov     dword ptr [rsp+290h+psz], 2Eh ; '.'
0x14000f013  jmp     short loc_14000F048
0x14000f015  sub     rcx, r14
0x14000f018  shr     rcx, 1
0x14000f01b  test    ecx, ecx
0x14000f01d  jz      short loc_14000F02B
0x14000f01f  lea     eax, [rcx+1]
0x14000f022  cmp     eax, 104h
0x14000f027  jnb     short loc_14000F048
0x14000f029  mov     ebx, ecx
0x14000f02b  mov     eax, ebx
0x14000f02d  lea     rcx, [rsp+290h+psz]; void *
0x14000f032  mov     rdx, r14; Src
0x14000f035  lea     rbx, [rax+rax]
0x14000f039  mov     r8, rbx; Size
0x14000f03c  call    memcpy_0
0x14000f041  xor     ecx, ecx
0x14000f043  mov     [rsp+rbx+290h+psz], cx
0x14000f048  lea     rcx, [rsp+290h+psz]; psz
0x14000f04d  call    cs:__imp_SysAllocString
0x14000f053  mov     [rdi+58h], rax
0x14000f057  test    rax, rax
0x14000f05a  jz      loc_14000F13D
0x14000f060  mov     edx, cs:?g_lResourceBase@Global@@2JA; long Global::g_lResourceBase
0x14000f066  lea     rcx, [rdi+48h]; unsigned __int16 **
0x14000f06a  inc     edx; unsigned int
0x14000f06c  call    ?LoadStr@@YAHPEAPEAGI@Z; LoadStr(ushort * *,uint)
0x14000f071  xor     r8d, r8d
0x14000f074  cmp     [rdi+48h], r8
0x14000f078  jz      loc_14000F13D
0x14000f07e  lea     rdx, [rsp+290h+pptlib]; pptlib
0x14000f083  mov     rcx, r14; szFile
0x14000f086  call    cs:__imp_LoadTypeLib
0x14000f08c  mov     ebx, eax
0x14000f08e  test    eax, eax
0x14000f090  js      loc_14000F142
0x14000f096  mov     rdx, [rsp+290h+pptlib]; struct ITypeLib *
0x14000f09b  lea     rcx, [rdi+10h]; this
0x14000f09f  call    ?CacheTypeInfo@CDispatch@@QEAAJPEAUITypeLib@@@Z; CDispatch::CacheTypeInfo(ITypeLib *)
0x14000f0a4  mov     ebx, eax
0x14000f0a6  test    eax, eax
0x14000f0a8  js      loc_14000F142
0x14000f0ae  lea     r8, [rsp+290h+var_268]; struct CArguments **
0x14000f0b3  mov     rdx, r12; unsigned __int16 **
0x14000f0b6  mov     ecx, r15d; int
0x14000f0b9  call    ?Create@CArguments@@SAJJPEAPEBGPEAPEAV1@@Z; CArguments::Create(long,ushort const * *,CArguments * *)
0x14000f0be  mov     rsi, [rsp+290h+var_268]
0x14000f0c3  mov     ebx, eax
0x14000f0c5  test    eax, eax
0x14000f0c7  js      short loc_14000F142
0x14000f0c9  mov     r14, [rsp+290h+pptlib]
0x14000f0ce  mov     rcx, [rsi+58h]
0x14000f0d2  mov     rdx, r14; struct ITypeLib *
0x14000f0d5  add     rcx, 10h; this
0x14000f0d9  call    ?CacheTypeInfo@CDispatch@@QEAAJPEAUITypeLib@@@Z; CDispatch::CacheTypeInfo(ITypeLib *)
0x14000f0de  mov     ebx, eax
0x14000f0e0  test    eax, eax
0x14000f0e2  js      short loc_14000F142
0x14000f0e4  mov     rcx, [rsi+60h]
0x14000f0e8  mov     rdx, r14; struct ITypeLib *
0x14000f0eb  add     rcx, 10h; this
0x14000f0ef  call    ?CacheTypeInfo@CDispatch@@QEAAJPEAUITypeLib@@@Z; CDispatch::CacheTypeInfo(ITypeLib *)
0x14000f0f4  mov     ebx, eax
0x14000f0f6  test    eax, eax
0x14000f0f8  js      short loc_14000F142
0x14000f0fa  lea     rcx, [rsi+18h]; this
0x14000f0fe  mov     rdx, r14; struct ITypeLib *
0x14000f101  call    ?CacheTypeInfo@CDispatch@@QEAAJPEAUITypeLib@@@Z; CDispatch::CacheTypeInfo(ITypeLib *)
0x14000f106  mov     ebx, eax
0x14000f108  test    eax, eax
0x14000f10a  js      short loc_14000F142
0x14000f10c  mov     rax, [rsi]
0x14000f10f  lea     r8, [rdi+60h]
0x14000f113  lea     rdx, IID_IArguments2
0x14000f11a  mov     rcx, rsi
0x14000f11d  mov     rax, [rax]
0x14000f120  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f125  xor     r8d, r8d
0x14000f128  mov     ebx, eax
0x14000f12a  test    eax, eax
0x14000f12c  js      short loc_14000F142
0x14000f12e  mov     [r13+0], rdi
0x14000f132  mov     ebx, r8d
0x14000f135  mov     edi, r8d
0x14000f138  jmp     short loc_14000F142
0x14000f13a  mov     rdi, r8
0x14000f13d  mov     ebx, 8007000Eh
0x14000f142  mov     rcx, [rsp+290h+pptlib]
0x14000f147  test    rcx, rcx
0x14000f14a  jz      short loc_14000F158
0x14000f14c  mov     rax, [rcx]
0x14000f14f  mov     rax, [rax+10h]
0x14000f153  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f158  test    rsi, rsi
0x14000f15b  jz      short loc_14000F16C
0x14000f15d  mov     rax, [rsi]
0x14000f160  mov     rcx, rsi
0x14000f163  mov     rax, [rax+10h]
0x14000f167  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f16c  test    rdi, rdi
0x14000f16f  jz      short loc_14000F180
0x14000f171  mov     rax, [rdi]
0x14000f174  mov     rcx, rdi
0x14000f177  mov     rax, [rax+10h]
0x14000f17b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f180  mov     eax, ebx
0x14000f182  mov     rcx, [rbp+190h+var_50]
0x14000f189  xor     rcx, rsp; StackCookie
0x14000f18c  call    __security_check_cookie
0x14000f191  add     rsp, 258h
0x14000f198  pop     r15
0x14000f19a  pop     r14
0x14000f19c  pop     r13
0x14000f19e  pop     r12
0x14000f1a0  pop     rdi
0x14000f1a1  pop     rsi
0x14000f1a2  pop     rbx
0x14000f1a3  pop     rbp
0x14000f1a4  retn
```
