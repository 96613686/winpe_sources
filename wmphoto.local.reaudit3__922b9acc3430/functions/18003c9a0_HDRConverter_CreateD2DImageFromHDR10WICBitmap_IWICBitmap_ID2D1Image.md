# HDRConverter::CreateD2DImageFromHDR10WICBitmap(IWICBitmap *,ID2D1Image * *)

- ea: `0x18003c9a0`
- end: `0x18003cc55`
- name: `?CreateD2DImageFromHDR10WICBitmap@HDRConverter@@AEAAJPEAUIWICBitmap@@PEAPEAUID2D1Image@@@Z`
- size: `693`
- prototype: `__int64 __fastcall(HDRConverter *__hidden this, struct IWICBitmap *, struct ID2D1Image **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18003c640`

## callees

- `0x180036420`
- `0x18003c9a0`
- `0x180045010`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
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
0x18003c9a0  mov     [rsp-8+arg_18], rbx
0x18003c9a5  push    rbp
0x18003c9a6  push    rsi
0x18003c9a7  push    rdi
0x18003c9a8  push    r14
0x18003c9aa  push    r15
0x18003c9ac  lea     rbp, [rsp-37h]
0x18003c9b1  sub     rsp, 0D0h
0x18003c9b8  mov     rax, cs:__security_cookie
0x18003c9bf  xor     rax, rsp
0x18003c9c2  mov     [rbp+57h+var_30], rax
0x18003c9c6  mov     r14, r8
0x18003c9c9  mov     rdi, rdx
0x18003c9cc  mov     rsi, rcx
0x18003c9cf  xor     r15d, r15d
0x18003c9d2  mov     [rbp+57h+var_90], r15
0x18003c9d6  mov     [rbp+57h+var_98], r15d
0x18003c9da  mov     [rbp+57h+var_88], r15d
0x18003c9de  mov     [rbp+57h+var_80], r15
0x18003c9e2  xorps   xmm0, xmm0
0x18003c9e5  movups  [rbp+57h+var_70], xmm0
0x18003c9e9  xorps   xmm1, xmm1
0x18003c9ec  movups  [rbp+57h+var_60], xmm1
0x18003c9f0  movups  [rbp+57h+var_50], xmm1
0x18003c9f4  movups  [rbp+57h+var_50+0Ch], xmm1
0x18003c9f8  mov     [rbp+57h+var_A0], r15
0x18003c9fc  mov     [rbp+57h+var_A8], r15
0x18003ca00  mov     [rbp+57h+var_B0], r15
0x18003ca04  mov     [r8], r15
0x18003ca07  mov     rax, [rdx]
0x18003ca0a  lea     r9, [rbp+57h+var_90]
0x18003ca0e  xor     edx, edx
0x18003ca10  mov     r8d, 1
0x18003ca16  mov     rcx, rdi
0x18003ca19  mov     rax, [rax+40h]
0x18003ca1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ca22  mov     ebx, eax
0x18003ca24  test    eax, eax
0x18003ca26  js      loc_18003CBC7
0x18003ca2c  mov     rcx, [rbp+57h+var_90]
0x18003ca30  mov     rax, [rcx]
0x18003ca33  lea     rdx, [rbp+57h+var_98]
0x18003ca37  mov     rax, [rax+20h]
0x18003ca3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ca40  mov     ebx, eax
0x18003ca42  test    eax, eax
0x18003ca44  js      loc_18003CBC7
0x18003ca4a  mov     rcx, [rbp+57h+var_90]
0x18003ca4e  mov     rax, [rcx]
0x18003ca51  lea     r8, [rbp+57h+var_80]
0x18003ca55  lea     rdx, [rbp+57h+var_88]
0x18003ca59  mov     rax, [rax+28h]
0x18003ca5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ca62  mov     ebx, eax
0x18003ca64  test    eax, eax
0x18003ca66  js      loc_18003CBC7
0x18003ca6c  mov     rax, [rbp+57h+var_80]
0x18003ca70  mov     qword ptr [rbp+57h+var_70], rax
0x18003ca74  mov     eax, [rbp+57h+var_98]
0x18003ca77  mov     dword ptr [rbp+57h+var_70+8], eax
0x18003ca7a  mov     rax, [rdi]
0x18003ca7d  lea     r8, [rbp+57h+var_60+4]
0x18003ca81  lea     rdx, [rbp+57h+var_60]
0x18003ca85  mov     rcx, rdi
0x18003ca88  mov     rax, [rax+18h]
0x18003ca8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ca91  mov     ebx, eax
0x18003ca93  test    eax, eax
0x18003ca95  js      loc_18003CBC7
0x18003ca9b  mov     dword ptr [rbp+57h+var_60+8], 1
0x18003caa2  mov     dword ptr [rbp+57h+var_60+0Ch], 1
0x18003caa9  mov     dword ptr [rbp+57h+var_50], 0Bh
0x18003cab0  mov     dword ptr [rbp+57h+var_50+4], 1
0x18003cab7  mov     dword ptr [rbp+57h+var_50+0Ch], 1
0x18003cabe  mov     [rbp+57h+var_40], 8
0x18003cac6  mov     [rbp+57h+var_38], r15d
0x18003caca  mov     rbx, [rsi+20h]
0x18003cace  mov     rax, [rbx]
0x18003cad1  mov     rdi, [rax+28h]
0x18003cad5  mov     rcx, [rbp+57h+var_A0]
0x18003cad9  test    rcx, rcx
0x18003cadc  jz      short loc_18003CAEF
0x18003cade  mov     [rbp+57h+var_A0], r15
0x18003cae2  mov     rdx, [rcx]
0x18003cae5  mov     rax, [rdx+10h]
0x18003cae9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003caee  nop
0x18003caef  lea     r9, [rbp+57h+var_A0]
0x18003caf3  lea     r8, [rbp+57h+var_70]
0x18003caf7  lea     rdx, [rbp+57h+var_60]
0x18003cafb  mov     rcx, rbx
0x18003cafe  mov     rax, rdi
0x18003cb01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cb06  mov     ebx, eax
0x18003cb08  test    eax, eax
0x18003cb0a  js      loc_18003CBC7
0x18003cb10  mov     rbx, [rbp+57h+var_A0]
0x18003cb14  mov     rax, [rbx]
0x18003cb17  mov     rdi, [rax]
0x18003cb1a  mov     rcx, [rbp+57h+var_A8]
0x18003cb1e  test    rcx, rcx
0x18003cb21  jz      short loc_18003CB34
0x18003cb23  mov     [rbp+57h+var_A8], r15
0x18003cb27  mov     rdx, [rcx]
0x18003cb2a  mov     rax, [rdx+10h]
0x18003cb2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cb33  nop
0x18003cb34  lea     r8, [rbp+57h+var_A8]
0x18003cb38  lea     rdx, _GUID_cafcb56c_6ac3_4889_bf47_9e23bbd260ec
0x18003cb3f  mov     rcx, rbx
0x18003cb42  mov     rax, rdi
0x18003cb45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cb4a  mov     ebx, eax
0x18003cb4c  test    eax, eax
0x18003cb4e  js      short loc_18003CBC7
0x18003cb50  mov     rax, [rbp+57h+var_A8]
0x18003cb54  mov     [rbp+57h+var_78], rax
0x18003cb58  mov     rbx, [rsi+28h]
0x18003cb5c  mov     rax, [rbx]
0x18003cb5f  mov     rdi, [rax+320h]
0x18003cb66  mov     rcx, [rbp+57h+var_B0]
0x18003cb6a  test    rcx, rcx
0x18003cb6d  jz      short loc_18003CB80
0x18003cb6f  mov     [rbp+57h+var_B0], r15
0x18003cb73  mov     rax, [rcx]
0x18003cb76  mov     rax, [rax+10h]
0x18003cb7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cb7f  nop
0x18003cb80  lea     rax, [rbp+57h+var_B0]
0x18003cb84  mov     [rsp+0F0h+var_C8], rax
0x18003cb89  mov     [rsp+0F0h+var_D0], r15d
0x18003cb8e  xor     r9d, r9d
0x18003cb91  mov     r8d, 1
0x18003cb97  lea     rdx, [rbp+57h+var_78]
0x18003cb9b  mov     rcx, rbx
0x18003cb9e  mov     rax, rdi
0x18003cba1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cba6  mov     ebx, eax
0x18003cba8  test    eax, eax
0x18003cbaa  js      short loc_18003CBC7
0x18003cbac  mov     rcx, [rbp+57h+var_B0]
0x18003cbb0  mov     rax, [rcx]
0x18003cbb3  mov     r8, r14
0x18003cbb6  lea     rdx, _GUID_65019f75_8da2_497c_b32c_dfa34e48ede6
0x18003cbbd  mov     rax, [rax]
0x18003cbc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cbc5  mov     ebx, eax
0x18003cbc7  mov     rcx, [rbp+57h+var_B0]
0x18003cbcb  test    rcx, rcx
0x18003cbce  jz      short loc_18003CBE1
0x18003cbd0  mov     [rbp+57h+var_B0], r15
0x18003cbd4  mov     rax, [rcx]
0x18003cbd7  mov     rax, [rax+10h]
0x18003cbdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cbe0  nop
0x18003cbe1  mov     rcx, [rbp+57h+var_A8]
0x18003cbe5  test    rcx, rcx
0x18003cbe8  jz      short loc_18003CBFB
0x18003cbea  mov     [rbp+57h+var_A8], r15
0x18003cbee  mov     rax, [rcx]
0x18003cbf1  mov     rax, [rax+10h]
0x18003cbf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cbfa  nop
0x18003cbfb  mov     rcx, [rbp+57h+var_A0]
0x18003cbff  test    rcx, rcx
0x18003cc02  jz      short loc_18003CC15
0x18003cc04  mov     [rbp+57h+var_A0], r15
0x18003cc08  mov     rax, [rcx]
0x18003cc0b  mov     rax, [rax+10h]
0x18003cc0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cc14  nop
0x18003cc15  mov     rcx, [rbp+57h+var_90]
0x18003cc19  test    rcx, rcx
0x18003cc1c  jz      short loc_18003CC2F
0x18003cc1e  mov     [rbp+57h+var_90], r15
0x18003cc22  mov     rax, [rcx]
0x18003cc25  mov     rax, [rax+10h]
0x18003cc29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cc2e  nop
0x18003cc2f  mov     eax, ebx
0x18003cc31  mov     rcx, [rbp+57h+var_30]
0x18003cc35  xor     rcx, rsp; StackCookie
0x18003cc38  call    __security_check_cookie
0x18003cc3d  mov     rbx, [rsp+0F0h+arg_18]
0x18003cc45  add     rsp, 0D0h
0x18003cc4c  pop     r15
0x18003cc4e  pop     r14
0x18003cc50  pop     rdi
0x18003cc51  pop     rsi
0x18003cc52  pop     rbp
0x18003cc53  retn
```
