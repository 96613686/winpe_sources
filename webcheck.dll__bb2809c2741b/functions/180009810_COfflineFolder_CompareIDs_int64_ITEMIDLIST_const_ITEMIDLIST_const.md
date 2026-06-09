# COfflineFolder::CompareIDs(__int64,_ITEMIDLIST const *,_ITEMIDLIST const *)

- ea: `0x180009810`
- end: `0x180009a19`
- name: `?CompareIDs@COfflineFolder@@UEAAJ_JPEFBU_ITEMIDLIST@@1@Z`
- size: `521`
- prototype: `__int64 __fastcall(COfflineFolder *__hidden this, __int64, const struct _ITEMIDLIST *, const struct _ITEMIDLIST *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180009810`
- `0x180028c6c`
- `0x180028dbc`
- `0x180029280`
- `0x18002a010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180009959`
- `OLEAUT32!__imp_VariantInit` at `0x180009993`
- `OLEAUT32!__imp_VariantInit` at `0x180009959`
- `OLEAUT32!__imp_VariantInit` at `0x180009993`
- `OLEAUT32!__imp_VariantClear` at `0x1800099d5`
- `OLEAUT32!__imp_VariantClear` at `0x1800099df`
- `OLEAUT32!__imp_VariantClear` at `0x1800099d5`
- `OLEAUT32!__imp_VariantClear` at `0x1800099df`
- `PROPSYS!VariantCompare` at `0x1800099a1`
- `PROPSYS!VariantCompare` at `0x1800099a1`
- `SHELL32!__imp_ILFree` at `0x1800099e8`
- `SHELL32!__imp_ILFree` at `0x1800099f1`
- `SHELL32!__imp_ILFree` at `0x1800099e8`
- `SHELL32!__imp_ILFree` at `0x1800099f1`

## pseudocode

```c
__int64 __fastcall COfflineFolder::CompareIDs(
        COfflineFolder *this,
        __int64 a2,
        struct _ITEMIDLIST *a3,
        struct _ITEMIDLIST *a4)
{
  int v7; // ebx
  __int64 cb; // rcx
  ITEMIDLIST *v9; // r14
  _WORD *v10; // rcx
  LPITEMIDLIST v11; // r12
  ITEMIDLIST *v12; // r15
  _WORD *v13; // rcx
  int v14; // eax
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  int v18; // eax
  LPITEMIDLIST pidl; // [rsp+30h] [rbp-49h] BYREF
  __int64 v21; // [rsp+38h] [rbp-41h]
  VARIANTARG var2; // [rsp+40h] [rbp-39h] BYREF
  VARIANTARG pvarg; // [rsp+58h] [rbp-21h] BYREF
  __int128 v24; // [rsp+70h] [rbp-9h] BYREF
  int v25; // [rsp+80h] [rbp+7h]

  v21 = a2;
  v7 = -2147024809;
  if ( a3 && a4 && a3->mkid.cb && a4->mkid.cb )
  {
    if ( a3 == a4 )
    {
      return 0;
    }
    else
    {
      cb = a3->mkid.cb;
      v9 = 0;
      pidl = 0;
      v10 = (USHORT *)((char *)&a3->mkid.cb + cb);
      if ( v10 && *v10 )
      {
        v7 = SHILCloneFirst(a3, &pidl);
        if ( v7 < 0 )
          return (unsigned int)v7;
        v9 = pidl;
        v11 = pidl;
      }
      else
      {
        v11 = a3;
      }
      v12 = 0;
      pidl = 0;
      if ( a4->mkid.cb && (v13 = (USHORT *)((char *)&a4->mkid.cb + a4->mkid.cb)) != 0 && *v13 )
      {
        v14 = SHILCloneFirst(a4, &pidl);
        v12 = pidl;
        v7 = v14;
      }
      else
      {
        pidl = a4;
        v7 = 0;
      }
      if ( v7 >= 0 )
      {
        v25 = 0;
        v15 = *(_QWORD *)this;
        v24 = 0;
        v7 = (*(__int64 (__fastcall **)(COfflineFolder *, _QWORD, __int128 *))(v15 + 152))(
               this,
               (unsigned __int16)v21,
               &v24);
        if ( v7 >= 0 )
        {
          v16 = *(_QWORD *)this;
          memset(&pvarg, 0, sizeof(pvarg));
          if ( (*(int (__fastcall **)(COfflineFolder *, LPITEMIDLIST, __int128 *, VARIANTARG *))(v16 + 136))(
                 this,
                 v11,
                 &v24,
                 &pvarg) < 0 )
            VariantInit(&pvarg);
          v17 = *(_QWORD *)this;
          memset(&var2, 0, sizeof(var2));
          if ( (*(int (__fastcall **)(COfflineFolder *, LPITEMIDLIST, __int128 *, VARIANTARG *))(v17 + 136))(
                 this,
                 pidl,
                 &v24,
                 &var2) < 0 )
            VariantInit(&var2);
          v18 = VariantCompare(&pvarg, &var2);
          if ( v18 )
          {
            if ( v18 >= 0 )
              v7 = v18 > 0;
            else
              v7 = 0xFFFF;
          }
          else
          {
            v7 = ILCompareRelIDs(this, a3, a4, v21);
          }
          VariantClear(&var2);
          VariantClear(&pvarg);
        }
        ILFree(v12);
      }
      ILFree(v9);
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180009810  push    rbp
0x180009812  push    rbx
0x180009813  push    rsi
0x180009814  push    rdi
0x180009815  push    r12
0x180009817  push    r13
0x180009819  push    r14
0x18000981b  push    r15
0x18000981d  lea     rbp, [rsp-1Fh]
0x180009822  sub     rsp, 98h
0x180009829  mov     rax, cs:__security_cookie
0x180009830  xor     rax, rsp
0x180009833  mov     [rbp+57h+var_48], rax
0x180009837  mov     [rbp+57h+var_98], rdx
0x18000983b  mov     rdi, r9
0x18000983e  xor     edx, edx
0x180009840  mov     rsi, r8
0x180009843  mov     r13, rcx
0x180009846  mov     ebx, 80070057h
0x18000984b  test    r8, r8
0x18000984e  jz      loc_1800099F7
0x180009854  test    r9, r9
0x180009857  jz      loc_1800099F7
0x18000985d  cmp     [r8], dx
0x180009861  jz      loc_1800099F7
0x180009867  cmp     [r9], dx
0x18000986b  jz      loc_1800099F7
0x180009871  cmp     r8, r9
0x180009874  jnz     short loc_18000987D
0x180009876  mov     ebx, edx
0x180009878  jmp     loc_1800099F7
0x18000987d  movzx   ecx, word ptr [r8]
0x180009881  mov     r14, rdx
0x180009884  mov     [rbp+57h+pidl], rdx
0x180009888  add     rcx, rsi
0x18000988b  jz      short loc_1800098B3
0x18000988d  cmp     [rcx], dx
0x180009890  jz      short loc_1800098B3
0x180009892  lea     rdx, [rbp+57h+pidl]
0x180009896  mov     rcx, rsi
0x180009899  call    SHILCloneFirst
0x18000989e  xor     edx, edx
0x1800098a0  mov     ebx, eax
0x1800098a2  test    eax, eax
0x1800098a4  js      loc_1800099F7
0x1800098aa  mov     r14, [rbp+57h+pidl]
0x1800098ae  mov     r12, r14
0x1800098b1  jmp     short loc_1800098B6
0x1800098b3  mov     r12, rsi
0x1800098b6  mov     r15, rdx
0x1800098b9  mov     [rbp+57h+pidl], rdx
0x1800098bd  cmp     [rdi], dx
0x1800098c0  jz      short loc_1800098E7
0x1800098c2  movzx   ecx, word ptr [rdi]
0x1800098c5  add     rcx, rdi
0x1800098c8  jz      short loc_1800098E7
0x1800098ca  cmp     [rcx], dx
0x1800098cd  jz      short loc_1800098E7
0x1800098cf  lea     rdx, [rbp+57h+pidl]
0x1800098d3  mov     rcx, rdi
0x1800098d6  call    SHILCloneFirst
0x1800098db  mov     r15, [rbp+57h+pidl]
0x1800098df  mov     ebx, eax
0x1800098e1  mov     [rbp+57h+pidl], r15
0x1800098e5  jmp     short loc_1800098ED
0x1800098e7  mov     [rbp+57h+pidl], rdi
0x1800098eb  mov     ebx, edx
0x1800098ed  test    ebx, ebx
0x1800098ef  js      loc_1800099EE
0x1800098f5  movzx   edx, word ptr [rbp+57h+var_98]
0x1800098f9  lea     r8, [rbp+57h+var_60]
0x1800098fd  xor     eax, eax
0x1800098ff  xorps   xmm0, xmm0
0x180009902  mov     [rbp+57h+var_50], eax
0x180009905  mov     rcx, r13
0x180009908  mov     rax, [r13+0]
0x18000990c  movups  [rbp+57h+var_60], xmm0
0x180009910  mov     rax, [rax+98h]
0x180009917  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000991c  mov     ebx, eax
0x18000991e  test    eax, eax
0x180009920  js      loc_1800099E5
0x180009926  xor     eax, eax
0x180009928  lea     r9, [rbp+57h+pvarg]
0x18000992c  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x180009930  lea     r8, [rbp+57h+var_60]
0x180009934  mov     rax, [r13+0]
0x180009938  xorps   xmm0, xmm0
0x18000993b  mov     rdx, r12
0x18000993e  mov     rcx, r13
0x180009941  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x180009945  mov     rax, [rax+88h]
0x18000994c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009951  test    eax, eax
0x180009953  jns     short loc_18000995F
0x180009955  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180009959  call    cs:__imp_VariantInit
0x18000995f  mov     rdx, [rbp+57h+pidl]
0x180009963  lea     r9, [rbp+57h+var2]
0x180009967  xor     eax, eax
0x180009969  lea     r8, [rbp+57h+var_60]
0x18000996d  mov     qword ptr [rbp+57h+var2+10h], rax
0x180009971  xorps   xmm0, xmm0
0x180009974  mov     rax, [r13+0]
0x180009978  mov     rcx, r13
0x18000997b  movups  xmmword ptr [rbp+57h+var2], xmm0
0x18000997f  mov     rax, [rax+88h]
0x180009986  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000998b  test    eax, eax
0x18000998d  jns     short loc_180009999
0x18000998f  lea     rcx, [rbp+57h+var2]; pvarg
0x180009993  call    cs:__imp_VariantInit
0x180009999  lea     rdx, [rbp+57h+var2]; var2
0x18000999d  lea     rcx, [rbp+57h+pvarg]; var1
0x1800099a1  call    cs:__imp_VariantCompare
0x1800099a7  test    eax, eax
0x1800099a9  jz      short loc_1800099BD
0x1800099ab  jns     short loc_1800099B4
0x1800099ad  mov     ebx, 0FFFFh
0x1800099b2  jmp     short loc_1800099D1
0x1800099b4  xor     ebx, ebx
0x1800099b6  test    eax, eax
0x1800099b8  setnle  bl
0x1800099bb  jmp     short loc_1800099D1
0x1800099bd  mov     r9, [rbp+57h+var_98]
0x1800099c1  mov     r8, rdi
0x1800099c4  mov     rdx, rsi
0x1800099c7  mov     rcx, r13
0x1800099ca  call    ILCompareRelIDs
0x1800099cf  mov     ebx, eax
0x1800099d1  lea     rcx, [rbp+57h+var2]; pvarg
0x1800099d5  call    cs:__imp_VariantClear
0x1800099db  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1800099df  call    cs:__imp_VariantClear
0x1800099e5  mov     rcx, r15; pidl
0x1800099e8  call    cs:__imp_ILFree
0x1800099ee  mov     rcx, r14; pidl
0x1800099f1  call    cs:__imp_ILFree
0x1800099f7  mov     eax, ebx
0x1800099f9  mov     rcx, [rbp+57h+var_48]
0x1800099fd  xor     rcx, rsp; StackCookie
0x180009a00  call    __security_check_cookie
0x180009a05  add     rsp, 98h
0x180009a0c  pop     r15
0x180009a0e  pop     r14
0x180009a10  pop     r13
0x180009a12  pop     r12
0x180009a14  pop     rdi
0x180009a15  pop     rsi
0x180009a16  pop     rbx
0x180009a17  pop     rbp
0x180009a18  retn
```
