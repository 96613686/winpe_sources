# HDRConverter::CreateD2DImageFromHDR10WICBitmap(IWICBitmap *,ID2D1Image * *)

- ea: `0x18003c190`
- end: `0x18003c444`
- name: `?CreateD2DImageFromHDR10WICBitmap@HDRConverter@@AEAAJPEAUIWICBitmap@@PEAPEAUID2D1Image@@@Z`
- size: `692`
- prototype: `__int64 __fastcall(HDRConverter *__hidden this, struct IWICBitmap *, struct ID2D1Image **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18003be30`

## callees

- `0x180035e50`
- `0x18003c190`
- `0x180044010`

## pseudocode

```c
__int64 __fastcall HDRConverter::CreateD2DImageFromHDR10WICBitmap(
        HDRConverter *this,
        struct IWICBitmap *a2,
        struct ID2D1Image **a3)
{
  int v6; // ebx
  __int64 v7; // rbx
  __int64 (__fastcall *v8)(__int64, _OWORD *, __int128 *, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)); // rdi
  __int64 (__fastcall ***v9)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 (__fastcall ***v10)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v11)(_QWORD, GUID *, __int64 *); // rdi
  __int64 v12; // rcx
  __int64 v13; // rbx
  __int64 (__fastcall *v14)(__int64, __int64 *, __int64, _QWORD, _DWORD, __int64 (__fastcall ****)(_QWORD, GUID *, struct ID2D1Image **)); // rdi
  __int64 (__fastcall ***v15)(_QWORD, GUID *, struct ID2D1Image **); // rcx
  __int64 (__fastcall ***v16)(_QWORD, GUID *, struct ID2D1Image **); // rcx
  __int64 v17; // rcx
  __int64 (__fastcall ***v18)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v19; // rcx
  __int64 (__fastcall ***v21)(_QWORD, GUID *, struct ID2D1Image **); // [rsp+40h] [rbp-59h] BYREF
  __int64 v22; // [rsp+48h] [rbp-51h] BYREF
  __int64 (__fastcall ***v23)(_QWORD, GUID *, __int64 *); // [rsp+50h] [rbp-49h] BYREF
  int v24; // [rsp+58h] [rbp-41h] BYREF
  __int64 v25; // [rsp+60h] [rbp-39h] BYREF
  int v26; // [rsp+68h] [rbp-31h] BYREF
  __int64 v27; // [rsp+70h] [rbp-29h] BYREF
  __int64 v28; // [rsp+78h] [rbp-21h] BYREF
  __int128 v29; // [rsp+80h] [rbp-19h] BYREF
  _OWORD v30[3]; // [rsp+90h] [rbp-9h] BYREF

  v25 = 0;
  v24 = 0;
  v26 = 0;
  v27 = 0;
  v29 = 0;
  memset(v30, 0, 44);
  v23 = 0;
  v22 = 0;
  v21 = 0;
  *a3 = 0;
  v6 = ((__int64 (__fastcall *)(struct IWICBitmap *, _QWORD, __int64, __int64 *))a2->lpVtbl->Lock)(a2, 0, 1, &v25);
  if ( v6 >= 0 )
  {
    v6 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v25 + 32LL))(v25, &v24);
    if ( v6 >= 0 )
    {
      v6 = (*(__int64 (__fastcall **)(__int64, int *, __int64 *))(*(_QWORD *)v25 + 40LL))(v25, &v26, &v27);
      if ( v6 >= 0 )
      {
        *(_QWORD *)&v29 = v27;
        DWORD2(v29) = v24;
        v6 = ((__int64 (__fastcall *)(struct IWICBitmap *, _OWORD *, char *))a2->lpVtbl->GetSize)(
               a2,
               v30,
               (char *)v30 + 4);
        if ( v6 >= 0 )
        {
          *((_QWORD *)&v30[0] + 1) = 0x100000001LL;
          *(_QWORD *)&v30[1] = 0x10000000BLL;
          HIDWORD(v30[1]) = 1;
          *(_QWORD *)&v30[2] = 8;
          DWORD2(v30[2]) = 0;
          v7 = *((_QWORD *)this + 4);
          v8 = *(__int64 (__fastcall **)(__int64, _OWORD *, __int128 *, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)v7 + 40LL);
          v9 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v23;
          if ( v23 )
          {
            v23 = 0;
            ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v9)[2])(v9);
          }
          v6 = v8(v7, v30, &v29, &v23);
          if ( v6 >= 0 )
          {
            v10 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v23;
            v11 = **v23;
            v12 = v22;
            if ( v22 )
            {
              v22 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
            }
            v6 = v11(v10, &GUID_cafcb56c_6ac3_4889_bf47_9e23bbd260ec, &v22);
            if ( v6 >= 0 )
            {
              v28 = v22;
              v13 = *((_QWORD *)this + 5);
              v14 = *(__int64 (__fastcall **)(__int64, __int64 *, __int64, _QWORD, _DWORD, __int64 (__fastcall ****)(_QWORD, GUID *, struct ID2D1Image **)))(*(_QWORD *)v13 + 800LL);
              v15 = v21;
              if ( v21 )
              {
                v21 = 0;
                ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, struct ID2D1Image **)))(*v15)[2])(v15);
              }
              v6 = v14(v13, &v28, 1, 0, 0, &v21);
              if ( v6 >= 0 )
                v6 = (**v21)(v21, &GUID_65019f75_8da2_497c_b32c_dfa34e48ede6, a3);
            }
          }
        }
      }
    }
  }
  v16 = v21;
  if ( v21 )
  {
    v21 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, struct ID2D1Image **)))(*v16)[2])(v16);
  }
  v17 = v22;
  if ( v22 )
  {
    v22 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  }
  v18 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v23;
  if ( v23 )
  {
    v23 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v18)[2])(v18);
  }
  v19 = v25;
  if ( v25 )
  {
    v25 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18003c190  mov     [rsp-8+arg_18], rbx
0x18003c195  push    rbp
0x18003c196  push    rsi
0x18003c197  push    rdi
0x18003c198  push    r14
0x18003c19a  push    r15
0x18003c19c  lea     rbp, [rsp-37h]
0x18003c1a1  sub     rsp, 0D0h
0x18003c1a8  mov     rax, cs:__security_cookie
0x18003c1af  xor     rax, rsp
0x18003c1b2  mov     [rbp+57h+var_30], rax
0x18003c1b6  mov     r14, r8
0x18003c1b9  mov     rdi, rdx
0x18003c1bc  mov     rsi, rcx
0x18003c1bf  xor     r15d, r15d
0x18003c1c2  mov     [rbp+57h+var_90], r15
0x18003c1c6  mov     [rbp+57h+var_98], r15d
0x18003c1ca  mov     [rbp+57h+var_88], r15d
0x18003c1ce  mov     [rbp+57h+var_80], r15
0x18003c1d2  xorps   xmm0, xmm0
0x18003c1d5  movups  [rbp+57h+var_70], xmm0
0x18003c1d9  xorps   xmm1, xmm1
0x18003c1dc  movups  [rbp+57h+var_60], xmm1
0x18003c1e0  movups  [rbp+57h+var_50], xmm1
0x18003c1e4  movups  [rbp+57h+var_50+0Ch], xmm1
0x18003c1e8  mov     [rbp+57h+var_A0], r15
0x18003c1ec  mov     [rbp+57h+var_A8], r15
0x18003c1f0  mov     [rbp+57h+var_B0], r15
0x18003c1f4  mov     [r8], r15
0x18003c1f7  mov     rax, [rdx]
0x18003c1fa  lea     r9, [rbp+57h+var_90]
0x18003c1fe  xor     edx, edx
0x18003c200  mov     r8d, 1
0x18003c206  mov     rcx, rdi
0x18003c209  mov     rax, [rax+40h]
0x18003c20d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c212  mov     ebx, eax
0x18003c214  test    eax, eax
0x18003c216  js      loc_18003C3B7
0x18003c21c  mov     rcx, [rbp+57h+var_90]
0x18003c220  mov     rax, [rcx]
0x18003c223  lea     rdx, [rbp+57h+var_98]
0x18003c227  mov     rax, [rax+20h]
0x18003c22b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c230  mov     ebx, eax
0x18003c232  test    eax, eax
0x18003c234  js      loc_18003C3B7
0x18003c23a  mov     rcx, [rbp+57h+var_90]
0x18003c23e  mov     rax, [rcx]
0x18003c241  lea     r8, [rbp+57h+var_80]
0x18003c245  lea     rdx, [rbp+57h+var_88]
0x18003c249  mov     rax, [rax+28h]
0x18003c24d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c252  mov     ebx, eax
0x18003c254  test    eax, eax
0x18003c256  js      loc_18003C3B7
0x18003c25c  mov     rax, [rbp+57h+var_80]
0x18003c260  mov     qword ptr [rbp+57h+var_70], rax
0x18003c264  mov     eax, [rbp+57h+var_98]
0x18003c267  mov     dword ptr [rbp+57h+var_70+8], eax
0x18003c26a  mov     rax, [rdi]
0x18003c26d  lea     r8, [rbp+57h+var_60+4]
0x18003c271  lea     rdx, [rbp+57h+var_60]
0x18003c275  mov     rcx, rdi
0x18003c278  mov     rax, [rax+18h]
0x18003c27c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c281  mov     ebx, eax
0x18003c283  test    eax, eax
0x18003c285  js      loc_18003C3B7
0x18003c28b  mov     dword ptr [rbp+57h+var_60+8], 1
0x18003c292  mov     dword ptr [rbp+57h+var_60+0Ch], 1
0x18003c299  mov     dword ptr [rbp+57h+var_50], 0Bh
0x18003c2a0  mov     dword ptr [rbp+57h+var_50+4], 1
0x18003c2a7  mov     dword ptr [rbp+57h+var_50+0Ch], 1
0x18003c2ae  mov     [rbp+57h+var_40], 8
0x18003c2b6  mov     [rbp+57h+var_38], r15d
0x18003c2ba  mov     rbx, [rsi+20h]
0x18003c2be  mov     rax, [rbx]
0x18003c2c1  mov     rdi, [rax+28h]
0x18003c2c5  mov     rcx, [rbp+57h+var_A0]
0x18003c2c9  test    rcx, rcx
0x18003c2cc  jz      short loc_18003C2DF
0x18003c2ce  mov     [rbp+57h+var_A0], r15
0x18003c2d2  mov     rdx, [rcx]
0x18003c2d5  mov     rax, [rdx+10h]
0x18003c2d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c2de  nop
0x18003c2df  lea     r9, [rbp+57h+var_A0]
0x18003c2e3  lea     r8, [rbp+57h+var_70]
0x18003c2e7  lea     rdx, [rbp+57h+var_60]
0x18003c2eb  mov     rcx, rbx
0x18003c2ee  mov     rax, rdi
0x18003c2f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c2f6  mov     ebx, eax
0x18003c2f8  test    eax, eax
0x18003c2fa  js      loc_18003C3B7
0x18003c300  mov     rbx, [rbp+57h+var_A0]
0x18003c304  mov     rax, [rbx]
0x18003c307  mov     rdi, [rax]
0x18003c30a  mov     rcx, [rbp+57h+var_A8]
0x18003c30e  test    rcx, rcx
0x18003c311  jz      short loc_18003C324
0x18003c313  mov     [rbp+57h+var_A8], r15
0x18003c317  mov     rdx, [rcx]
0x18003c31a  mov     rax, [rdx+10h]
0x18003c31e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c323  nop
0x18003c324  lea     r8, [rbp+57h+var_A8]
0x18003c328  lea     rdx, _GUID_cafcb56c_6ac3_4889_bf47_9e23bbd260ec
0x18003c32f  mov     rcx, rbx
0x18003c332  mov     rax, rdi
0x18003c335  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c33a  mov     ebx, eax
0x18003c33c  test    eax, eax
0x18003c33e  js      short loc_18003C3B7
0x18003c340  mov     rax, [rbp+57h+var_A8]
0x18003c344  mov     [rbp+57h+var_78], rax
0x18003c348  mov     rbx, [rsi+28h]
0x18003c34c  mov     rax, [rbx]
0x18003c34f  mov     rdi, [rax+320h]
0x18003c356  mov     rcx, [rbp+57h+var_B0]
0x18003c35a  test    rcx, rcx
0x18003c35d  jz      short loc_18003C370
0x18003c35f  mov     [rbp+57h+var_B0], r15
0x18003c363  mov     rax, [rcx]
0x18003c366  mov     rax, [rax+10h]
0x18003c36a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c36f  nop
0x18003c370  lea     rax, [rbp+57h+var_B0]
0x18003c374  mov     [rsp+0F0h+var_C8], rax
0x18003c379  mov     [rsp+0F0h+var_D0], r15d
0x18003c37e  xor     r9d, r9d
0x18003c381  mov     r8d, 1
0x18003c387  lea     rdx, [rbp+57h+var_78]
0x18003c38b  mov     rcx, rbx
0x18003c38e  mov     rax, rdi
0x18003c391  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c396  mov     ebx, eax
0x18003c398  test    eax, eax
0x18003c39a  js      short loc_18003C3B7
0x18003c39c  mov     rcx, [rbp+57h+var_B0]
0x18003c3a0  mov     rax, [rcx]
0x18003c3a3  mov     r8, r14
0x18003c3a6  lea     rdx, _GUID_65019f75_8da2_497c_b32c_dfa34e48ede6
0x18003c3ad  mov     rax, [rax]
0x18003c3b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c3b5  mov     ebx, eax
0x18003c3b7  mov     rcx, [rbp+57h+var_B0]
0x18003c3bb  test    rcx, rcx
0x18003c3be  jz      short loc_18003C3D1
0x18003c3c0  mov     [rbp+57h+var_B0], r15
0x18003c3c4  mov     rax, [rcx]
0x18003c3c7  mov     rax, [rax+10h]
0x18003c3cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c3d0  nop
0x18003c3d1  mov     rcx, [rbp+57h+var_A8]
0x18003c3d5  test    rcx, rcx
0x18003c3d8  jz      short loc_18003C3EB
0x18003c3da  mov     [rbp+57h+var_A8], r15
0x18003c3de  mov     rax, [rcx]
0x18003c3e1  mov     rax, [rax+10h]
0x18003c3e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c3ea  nop
0x18003c3eb  mov     rcx, [rbp+57h+var_A0]
0x18003c3ef  test    rcx, rcx
0x18003c3f2  jz      short loc_18003C405
0x18003c3f4  mov     [rbp+57h+var_A0], r15
0x18003c3f8  mov     rax, [rcx]
0x18003c3fb  mov     rax, [rax+10h]
0x18003c3ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c404  nop
0x18003c405  mov     rcx, [rbp+57h+var_90]
0x18003c409  test    rcx, rcx
0x18003c40c  jz      short loc_18003C41F
0x18003c40e  mov     [rbp+57h+var_90], r15
0x18003c412  mov     rax, [rcx]
0x18003c415  mov     rax, [rax+10h]
0x18003c419  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c41e  nop
0x18003c41f  mov     eax, ebx
0x18003c421  mov     rcx, [rbp+57h+var_30]
0x18003c425  xor     rcx, rsp; StackCookie
0x18003c428  call    __security_check_cookie
0x18003c42d  mov     rbx, [rsp+0F0h+arg_18]
0x18003c435  add     rsp, 0D0h
0x18003c43c  pop     r15
0x18003c43e  pop     r14
0x18003c440  pop     rdi
0x18003c441  pop     rsi
0x18003c442  pop     rbp
0x18003c443  retn
```
