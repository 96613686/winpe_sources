# DoCloneSubscriptionItem(ISubscriptionItem *,_GUID *,ISubscriptionItem * *)

- ea: `0x180018d98`
- end: `0x18001907d`
- name: `?DoCloneSubscriptionItem@@YAJPEAUISubscriptionItem@@PEAU_GUID@@PEAPEAU1@@Z`
- size: `741`
- prototype: `__int64 __fastcall(struct ISubscriptionItem *, struct _GUID *, struct ISubscriptionItem **)`
- caller_count: `4`
- callee_count: `8`
- tags: `file_ops, service_task`

## callers

- `0x180004770`
- `0x1800053a4`
- `0x180018c50`
- `0x18001e008`

## callees

- `0x180018d98`
- `0x18001913c`
- `0x180019ae0`
- `0x18001ba08`
- `0x18001ba40`
- `0x18001c728`
- `0x180029280`
- `0x18002a010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180018fbf`
- `ole32!CoTaskMemFree` at `0x180018fbf`
- `OLEAUT32!__imp_VariantClear` at `0x180018fc8`
- `OLEAUT32!__imp_VariantClear` at `0x180018fc8`

## pseudocode

```c
__int64 __fastcall DoCloneSubscriptionItem(
        struct ISubscriptionItem *a1,
        struct _GUID *a2,
        struct ISubscriptionItem **a3)
{
  struct ISubscriptionItem **v3; // r15
  struct ISubscriptionItemVtbl *lpVtbl; // rax
  HRESULT (__stdcall *GetSubscriptionItemInfo)(ISubscriptionItem *, SUBSCRIPTIONITEMINFO *); // rax
  int v8; // edi
  struct ISubscriptionItem *v9; // rbx
  _QWORD *v10; // rsi
  _QWORD *v11; // r12
  _QWORD *v12; // rax
  _QWORD *v13; // r14
  __int64 v14; // rdx
  unsigned int i; // r8d
  __int64 v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // rax
  unsigned int j; // r15d
  void *v20; // rcx
  unsigned int v21; // r8d
  struct ISubscriptionItem *v23; // [rsp+30h] [rbp-39h] BYREF
  __int64 v24; // [rsp+38h] [rbp-31h] BYREF
  struct ISubscriptionItem **v25; // [rsp+40h] [rbp-29h]
  struct _GUID v26; // [rsp+48h] [rbp-21h] BYREF
  _OWORD v27[3]; // [rsp+58h] [rbp-11h] BYREF

  v25 = a3;
  v3 = a3;
  v26 = 0;
  if ( a1 && a3 )
  {
    *a3 = 0;
    lpVtbl = a1->lpVtbl;
    memset(v27, 0, 44);
    v24 = 0;
    GetSubscriptionItemInfo = lpVtbl->GetSubscriptionItemInfo;
    LODWORD(v27[0]) = 44;
    v8 = ((__int64 (__fastcall *)(struct ISubscriptionItem *, _OWORD *))GetSubscriptionItemInfo)(a1, v27);
    if ( v8 < 0 )
      return (unsigned int)v8;
    DWORD1(v27[0]) |= 0x80000000;
    v23 = 0;
    CreateCookie(&v26);
    v8 = SubscriptionItemFromCookie(1, &v26, &v23);
    if ( v8 < 0 )
      return (unsigned int)v8;
    v9 = v23;
    v8 = ((__int64 (__fastcall *)(struct ISubscriptionItem *, _OWORD *))v23->lpVtbl->SetSubscriptionItemInfo)(v23, v27);
    if ( v8 < 0 )
    {
      ((void (__fastcall *)(struct ISubscriptionItem *))v9->lpVtbl->Release)(v9);
      DoDeleteSubscriptionItem(&v26, 0, v21);
      return (unsigned int)v8;
    }
    if ( a2 )
      *a2 = v26;
    v8 = ((__int64 (__fastcall *)(struct ISubscriptionItem *, __int64 *))a1->lpVtbl->EnumProperties)(a1, &v24);
    if ( v8 < 0 )
      goto LABEL_30;
    LODWORD(v23) = 0;
    v8 = (*(__int64 (__fastcall **)(__int64, struct ISubscriptionItem **))(*(_QWORD *)v24 + 56LL))(v24, &v23);
    if ( v8 < 0 )
    {
LABEL_26:
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
      if ( v8 >= 0 )
      {
        *v3 = v9;
        return (unsigned int)v8;
      }
LABEL_30:
      ((void (__fastcall *)(struct ISubscriptionItem *))v9->lpVtbl->Release)(v9);
      return (unsigned int)v8;
    }
    v10 = operator new(saturated_mul((unsigned int)v23, 0x20u));
    v11 = operator new(saturated_mul((unsigned int)v23, 8u));
    v12 = operator new(saturated_mul((unsigned int)v23, 0x18u));
    v13 = v12;
    if ( v10 && v11 && v12 )
    {
      v8 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD *, struct ISubscriptionItem **))(*(_QWORD *)v24 + 24LL))(
             v24,
             (unsigned int)v23,
             v10,
             &v23);
      if ( v8 >= 0 )
      {
        v14 = (unsigned int)v23;
        for ( i = 0; i < (unsigned int)v23; v14 = (unsigned int)v23 )
        {
          v16 = i;
          v17 = i++;
          v17 *= 32;
          v11[v16] = *(_QWORD *)((char *)v10 + v17 + 24);
          v18 = 3 * v16;
          *(_OWORD *)&v13[v18] = *(_OWORD *)((char *)v10 + v17);
          v13[v18 + 2] = *(_QWORD *)((char *)v10 + v17 + 16);
        }
        v8 = ((__int64 (__fastcall *)(struct ISubscriptionItem *, __int64, _QWORD *, _QWORD *))v9->lpVtbl->WriteProperties)(
               v9,
               v14,
               v11,
               v13);
        for ( j = 0; j < (unsigned int)v23; ++j )
        {
          v20 = (void *)v10[4 * j + 3];
          if ( v20 )
            CoTaskMemFree(v20);
          VariantClear((VARIANTARG *)&v10[4 * j]);
        }
        v3 = v25;
      }
    }
    else
    {
      v8 = -2147024882;
      if ( !v10 )
        goto LABEL_22;
    }
    operator delete(v10);
LABEL_22:
    if ( v11 )
      operator delete(v11);
    if ( v13 )
      operator delete(v13);
    goto LABEL_26;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x180018d98  mov     [rsp-8+arg_18], rbx
0x180018d9d  push    rbp
0x180018d9e  push    rsi
0x180018d9f  push    rdi
0x180018da0  push    r12
0x180018da2  push    r13
0x180018da4  push    r14
0x180018da6  push    r15
0x180018da8  lea     rbp, [rsp-27h]
0x180018dad  sub     rsp, 90h
0x180018db4  mov     rax, cs:__security_cookie
0x180018dbb  xor     rax, rsp
0x180018dbe  mov     [rbp+57h+var_38], rax
0x180018dc2  xor     r13d, r13d
0x180018dc5  mov     [rbp+57h+var_80], r8
0x180018dc9  xorps   xmm0, xmm0
0x180018dcc  mov     r15, r8
0x180018dcf  mov     r14, rdx
0x180018dd2  mov     rsi, rcx
0x180018dd5  movups  xmmword ptr [rbp+57h+var_78.Data1], xmm0
0x180018dd9  test    rcx, rcx
0x180018ddc  jz      loc_180019051
0x180018de2  test    r8, r8
0x180018de5  jz      loc_180019051
0x180018deb  mov     [r8], r13
0x180018dee  lea     rdx, [rbp+57h+var_68]
0x180018df2  mov     rax, [rcx]
0x180018df5  movups  [rbp+57h+var_68], xmm0
0x180018df9  mov     [rbp+57h+var_88], r13
0x180018dfd  movups  xmmword ptr [rbp+57h+var_58], xmm0
0x180018e01  mov     rax, [rax+20h]
0x180018e05  movups  xmmword ptr [rbp+57h+var_58+0Ch], xmm0
0x180018e09  mov     dword ptr [rbp+57h+var_68], 2Ch ; ','
0x180018e10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018e15  mov     edi, eax
0x180018e17  test    eax, eax
0x180018e19  js      loc_18001904D
0x180018e1f  bts     dword ptr [rbp+57h+var_68+4], 1Fh
0x180018e24  lea     rcx, [rbp+57h+var_78]
0x180018e28  mov     [rbp+57h+var_90], r13
0x180018e2c  call    CreateCookie
0x180018e31  lea     r8, [rbp+57h+var_90]; struct ISubscriptionItem **
0x180018e35  lea     rdx, [rbp+57h+var_78]; struct _GUID *
0x180018e39  lea     ecx, [r13+1]; int
0x180018e3d  call    ?SubscriptionItemFromCookie@@YAJHPEFBU_GUID@@PEAPEAUISubscriptionItem@@@Z; SubscriptionItemFromCookie(int,_GUID const *,ISubscriptionItem * *)
0x180018e42  mov     edi, eax
0x180018e44  test    eax, eax
0x180018e46  js      loc_18001904D
0x180018e4c  mov     rbx, [rbp+57h+var_90]
0x180018e50  lea     rdx, [rbp+57h+var_68]
0x180018e54  mov     rcx, rbx
0x180018e57  mov     rax, [rbx]
0x180018e5a  mov     rax, [rax+28h]
0x180018e5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018e63  mov     edi, eax
0x180018e65  test    eax, eax
0x180018e67  js      loc_180019033
0x180018e6d  test    r14, r14
0x180018e70  jz      short loc_180018E7B
0x180018e72  movups  xmm0, xmmword ptr [rbp+57h+var_78.Data1]
0x180018e76  movdqu  xmmword ptr [r14], xmm0
0x180018e7b  mov     rax, [rsi]
0x180018e7e  lea     rdx, [rbp+57h+var_88]
0x180018e82  mov     rcx, rsi
0x180018e85  mov     rax, [rax+40h]
0x180018e89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018e8e  mov     edi, eax
0x180018e90  test    eax, eax
0x180018e92  js      loc_180019022
0x180018e98  mov     rcx, [rbp+57h+var_88]
0x180018e9c  lea     rdx, [rbp+57h+var_90]
0x180018ea0  mov     dword ptr [rbp+57h+var_90], r13d
0x180018ea4  mov     rax, [rcx]
0x180018ea7  mov     rax, [rax+38h]
0x180018eab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018eb0  mov     edi, eax
0x180018eb2  test    eax, eax
0x180018eb4  js      loc_180018FFD
0x180018eba  mov     ecx, dword ptr [rbp+57h+var_90]
0x180018ebd  mov     eax, 20h ; ' '
0x180018ec2  mul     rcx
0x180018ec5  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x180018ecc  cmovb   rax, rdi
0x180018ed0  mov     rcx, rax; dwBytes
0x180018ed3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180018ed8  mov     ecx, dword ptr [rbp+57h+var_90]
0x180018edb  mov     rsi, rax
0x180018ede  lea     eax, [rdi+9]
0x180018ee1  mul     rcx
0x180018ee4  cmovb   rax, rdi
0x180018ee8  mov     rcx, rax; dwBytes
0x180018eeb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180018ef0  mov     ecx, dword ptr [rbp+57h+var_90]
0x180018ef3  mov     r12, rax
0x180018ef6  lea     eax, [rdi+19h]
0x180018ef9  mul     rcx
0x180018efc  cmovb   rax, rdi
0x180018f00  mov     rcx, rax; dwBytes
0x180018f03  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180018f08  mov     r14, rax
0x180018f0b  test    rsi, rsi
0x180018f0e  jz      loc_180019016
0x180018f14  test    r12, r12
0x180018f17  jz      loc_180019016
0x180018f1d  test    rax, rax
0x180018f20  jz      loc_180019016
0x180018f26  mov     rcx, [rbp+57h+var_88]
0x180018f2a  lea     r9, [rbp+57h+var_90]
0x180018f2e  mov     r8, rsi
0x180018f31  mov     rdx, [rcx]
0x180018f34  mov     rax, [rdx+18h]
0x180018f38  mov     edx, dword ptr [rbp+57h+var_90]
0x180018f3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018f40  mov     edi, eax
0x180018f42  test    eax, eax
0x180018f44  js      loc_180018FDB
0x180018f4a  mov     edx, dword ptr [rbp+57h+var_90]
0x180018f4d  mov     r8d, r13d
0x180018f50  test    edx, edx
0x180018f52  jz      short loc_180018F8C
0x180018f54  mov     ecx, r8d
0x180018f57  mov     edx, r8d
0x180018f5a  inc     r8d
0x180018f5d  shl     rdx, 5
0x180018f61  mov     rax, [rdx+rsi+18h]
0x180018f66  mov     [r12+rcx*8], rax
0x180018f6a  lea     rax, [rcx+rcx*2]
0x180018f6e  movups  xmm0, xmmword ptr [rdx+rsi]
0x180018f72  movups  xmmword ptr [r14+rax*8], xmm0
0x180018f77  movsd   xmm1, qword ptr [rdx+rsi+10h]
0x180018f7d  movsd   qword ptr [r14+rax*8+10h], xmm1
0x180018f84  mov     edx, dword ptr [rbp+57h+var_90]
0x180018f87  cmp     r8d, edx
0x180018f8a  jb      short loc_180018F54
0x180018f8c  mov     rax, [rbx]
0x180018f8f  mov     r9, r14
0x180018f92  mov     r8, r12
0x180018f95  mov     rcx, rbx
0x180018f98  mov     rax, [rax+38h]
0x180018f9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018fa1  mov     edi, eax
0x180018fa3  mov     r15d, r13d
0x180018fa6  cmp     dword ptr [rbp+57h+var_90], r13d
0x180018faa  jbe     short loc_180018FD7
0x180018fac  mov     r13d, r15d
0x180018faf  shl     r13, 5
0x180018fb3  add     r13, rsi
0x180018fb6  mov     rcx, [r13+18h]; pv
0x180018fba  test    rcx, rcx
0x180018fbd  jz      short loc_180018FC5
0x180018fbf  call    cs:__imp_CoTaskMemFree
0x180018fc5  mov     rcx, r13; pvarg
0x180018fc8  call    cs:__imp_VariantClear
0x180018fce  inc     r15d
0x180018fd1  cmp     r15d, dword ptr [rbp+57h+var_90]
0x180018fd5  jb      short loc_180018FAC
0x180018fd7  mov     r15, [rbp+57h+var_80]
0x180018fdb  mov     rcx, rsi; lpMem
0x180018fde  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180018fe3  test    r12, r12
0x180018fe6  jz      short loc_180018FF0
0x180018fe8  mov     rcx, r12; lpMem
0x180018feb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180018ff0  test    r14, r14
0x180018ff3  jz      short loc_180018FFD
0x180018ff5  mov     rcx, r14; lpMem
0x180018ff8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180018ffd  mov     rcx, [rbp+57h+var_88]
0x180019001  mov     rax, [rcx]
0x180019004  mov     rax, [rax+10h]
0x180019008  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001900d  test    edi, edi
0x18001900f  js      short loc_180019022
0x180019011  mov     [r15], rbx
0x180019014  jmp     short loc_18001904D
0x180019016  mov     edi, 8007000Eh
0x18001901b  test    rsi, rsi
0x18001901e  jz      short loc_180018FE3
0x180019020  jmp     short loc_180018FDB
0x180019022  mov     rax, [rbx]
0x180019025  mov     rcx, rbx
0x180019028  mov     rax, [rax+10h]
0x18001902c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019031  jmp     short loc_18001904D
0x180019033  mov     rax, [rbx]
0x180019036  mov     rcx, rbx
0x180019039  mov     rax, [rax+10h]
0x18001903d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019042  xor     edx, edx; int
0x180019044  lea     rcx, [rbp+57h+var_78]; struct _GUID *
0x180019048  call    ?DoDeleteSubscriptionItem@@YAJPEFBU_GUID@@H@Z; DoDeleteSubscriptionItem(_GUID const *,int)
0x18001904d  mov     eax, edi
0x18001904f  jmp     short loc_180019056
0x180019051  mov     eax, 80070057h
0x180019056  mov     rcx, [rbp+57h+var_38]
0x18001905a  xor     rcx, rsp; StackCookie
0x18001905d  call    __security_check_cookie
0x180019062  mov     rbx, [rsp+0C0h+arg_18]
0x18001906a  add     rsp, 90h
0x180019071  pop     r15
0x180019073  pop     r14
0x180019075  pop     r13
0x180019077  pop     r12
0x180019079  pop     rdi
0x18001907a  pop     rsi
0x18001907b  pop     rbp
0x18001907c  retn
```
