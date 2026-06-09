# TpmVCardManagerImpl::VCardCreate(ushort const *,uchar,uchar,uchar const *,ulong,uchar const *,ulong,uchar const *,ulong,uchar const *,ulong,uchar const *,ulong,TPMVSC_ATTESTATION_TYPE)

- ea: `0x180026c70`
- end: `0x180026e09`
- name: `?VCardCreate@TpmVCardManagerImpl@@UEAAJPEBGEEPEBEK1K1K1K1KW4TPMVSC_ATTESTATION_TYPE@@@Z`
- size: `409`
- prototype: `__int64(int, __int64, char, char, __int64, ...)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180001ec0`
- `0x180025758`
- `0x180025778`
- `0x1800258d8`
- `0x180025f10`
- `0x180026c70`

## string_xrefs

- `0x180026c9d`: `TpmVCardManagerImpl::VCardCreate`

## pseudocode

```c
__int64 TpmVCardManagerImpl::VCardCreate(int a1, __int64 a2, char a3, char a4, __int64 a5, ...)
{
  __int64 v6; // rax
  int v7; // eax
  unsigned int v8; // ebx
  _BYTE v10[8]; // [rsp+80h] [rbp-80h] BYREF
  char v11; // [rsp+88h] [rbp-78h] BYREF
  int v12; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v13; // [rsp+94h] [rbp-6Ch] BYREF
  __int64 v14; // [rsp+98h] [rbp-68h] BYREF
  __int64 v15; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v16; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v17; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v18; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v19; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD *v20; // [rsp+C8h] [rbp-38h] BYREF
  _QWORD v21[3]; // [rsp+D0h] [rbp-30h] BYREF
  char v22; // [rsp+E8h] [rbp-18h] BYREF
  char v23[40]; // [rsp+160h] [rbp+60h] BYREF
  __int64 v24; // [rsp+1D8h] [rbp+D8h] BYREF
  va_list va; // [rsp+1D8h] [rbp+D8h]
  __int64 v26; // [rsp+1E0h] [rbp+E0h]
  __int64 v27; // [rsp+1E8h] [rbp+E8h] BYREF
  va_list va1; // [rsp+1E8h] [rbp+E8h]
  __int64 v29; // [rsp+1F0h] [rbp+F0h]
  __int64 v30; // [rsp+1F8h] [rbp+F8h] BYREF
  va_list va2; // [rsp+1F8h] [rbp+F8h]
  __int64 v32; // [rsp+200h] [rbp+100h]
  __int64 v33; // [rsp+208h] [rbp+108h] BYREF
  va_list va3; // [rsp+208h] [rbp+108h]
  __int64 v35; // [rsp+210h] [rbp+110h]
  __int64 v36; // [rsp+218h] [rbp+118h] BYREF
  va_list va4; // [rsp+218h] [rbp+118h]
  va_list va5; // [rsp+220h] [rbp+120h] BYREF

  va_start(va5, a5);
  va_start(va4, a5);
  va_start(va3, a5);
  va_start(va2, a5);
  va_start(va1, a5);
  va_start(va, a5);
  v24 = va_arg(va1, _QWORD);
  v26 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v27 = va_arg(va2, _QWORD);
  v29 = va_arg(va2, _QWORD);
  va_copy(va3, va2);
  v30 = va_arg(va3, _QWORD);
  v32 = va_arg(va3, _QWORD);
  va_copy(va4, va3);
  v33 = va_arg(va4, _QWORD);
  v35 = va_arg(va4, _QWORD);
  va_copy(va5, va4);
  v36 = va_arg(va5, _QWORD);
  v18 = a5;
  v17 = v26;
  v16 = v29;
  v15 = v32;
  v14 = v35;
  v21[0] = v23;
  v21[1] = &v12;
  v21[2] = &v13;
  v19 = a2;
  v11 = a3;
  v10[0] = a4;
  v13 = 0;
  v12 = 0;
  strcpy(v23, "TpmVCardManagerImpl::VCardCreate");
  lambda_f4b35da9302f823b1ca21f65a71b1469_::operator()(v21);
  v12 = 1;
  v20 = v21;
  v6 = lambda_e5725e412e5b80066c0ddc6c4f046f9d_::_lambda_e5725e412e5b80066c0ddc6c4f046f9d_(
         (unsigned int)&v22,
         a1,
         (unsigned int)&v19,
         (unsigned int)&v11,
         (__int64)v10,
         (__int64)&v18,
         (__int64)va,
         (__int64)&v17,
         (__int64)va1,
         (__int64)&v16,
         (__int64)va2,
         (__int64)&v15,
         (__int64)va3,
         (__int64)&v14,
         (__int64)va4,
         (__int64)va5);
  v7 = VCardErrorContract__lambda_e5725e412e5b80066c0ddc6c4f046f9d_(v6);
  v8 = v7;
  if ( v7 > 0 )
    v8 = (unsigned __int16)v7 | 0x80070000;
  v13 = v8;
  WppTraceUnwinder__lambda_f4b35da9302f823b1ca21f65a71b1469____::_WppTraceUnwinder__lambda_f4b35da9302f823b1ca21f65a71b1469____(&v20);
  return v8;
}

```

## disassembly

```asm
0x180026c70  push    rbp
0x180026c72  push    rbx
0x180026c73  lea     rbp, [rsp-98h]
0x180026c7b  sub     rsp, 198h
0x180026c82  mov     rax, cs:__security_cookie
0x180026c89  xor     rax, rsp
0x180026c8c  mov     [rbp+0A0h+var_18], rax
0x180026c93  mov     rax, [rbp+0A0h+arg_20]
0x180026c9a  mov     rbx, rcx
0x180026c9d  movups  xmm0, xmmword ptr cs:aTpmvcardmanage; "TpmVCardManagerImpl::VCardCreate"
0x180026ca4  mov     [rbp+0A0h+var_E8], rax
0x180026ca8  lea     rcx, [rbp+0A0h+var_D0]
0x180026cac  mov     rax, [rbp+0A0h+arg_30]
0x180026cb3  movups  xmm1, xmmword ptr cs:aTpmvcardmanage+10h; "mpl::VCardCreate"
0x180026cba  mov     [rbp+0A0h+var_F0], rax
0x180026cbe  mov     rax, [rbp+0A0h+arg_40]
0x180026cc5  mov     [rbp+0A0h+var_F8], rax
0x180026cc9  mov     rax, [rbp+0A0h+arg_50]
0x180026cd0  mov     [rbp+0A0h+var_100], rax
0x180026cd4  mov     rax, [rbp+0A0h+arg_60]
0x180026cdb  mov     [rbp+0A0h+var_108], rax
0x180026cdf  mov     al, byte ptr cs:aTpmvcardmanage+20h; ""
0x180026ce5  mov     [rbp+0A0h+var_40+20h], al
0x180026ceb  lea     rax, [rbp+0A0h+var_40]
0x180026cef  mov     [rbp+0A0h+var_D0], rax
0x180026cf3  lea     rax, [rbp+0A0h+var_110]
0x180026cf7  mov     [rbp+0A0h+var_C8], rax
0x180026cfb  lea     rax, [rbp+0A0h+var_10C]
0x180026cff  mov     [rbp+0A0h+var_C0], rax
0x180026d03  mov     [rbp+0A0h+var_E0], rdx
0x180026d07  mov     [rbp+0A0h+var_118], r8b
0x180026d0b  mov     [rbp+0A0h+var_120], r9b
0x180026d0f  mov     [rbp+0A0h+var_10C], 0
0x180026d16  mov     [rbp+0A0h+var_110], 0
0x180026d1d  movups  xmmword ptr [rbp+0A0h+var_40], xmm0
0x180026d21  movups  xmmword ptr [rbp+0A0h+var_40+10h], xmm1
0x180026d25  call    _lambda_f4b35da9302f823b1ca21f65a71b1469___operator__
0x180026d2a  lea     rax, [rbp+0A0h+var_D0]
0x180026d2e  mov     [rbp+0A0h+var_110], 1
0x180026d35  mov     [rbp+0A0h+var_D8], rax
0x180026d39  lea     r9, [rbp+0A0h+var_118]
0x180026d3d  lea     rax, [rbp+0A0h+arg_70]
0x180026d44  mov     rdx, rbx
0x180026d47  mov     [rsp+1A0h+var_128], rax
0x180026d4c  lea     r8, [rbp+0A0h+var_E0]
0x180026d50  lea     rax, [rbp+0A0h+arg_68]
0x180026d57  mov     [rsp+1A0h+var_130], rax
0x180026d5c  lea     rcx, [rbp+0A0h+var_B8]
0x180026d60  lea     rax, [rbp+0A0h+var_108]
0x180026d64  mov     [rsp+1A0h+var_138], rax
0x180026d69  lea     rax, [rbp+0A0h+arg_58]
0x180026d70  mov     [rsp+1A0h+var_140], rax
0x180026d75  lea     rax, [rbp+0A0h+var_100]
0x180026d79  mov     [rsp+1A0h+var_148], rax
0x180026d7e  lea     rax, [rbp+0A0h+arg_48]
0x180026d85  mov     [rsp+1A0h+var_150], rax
0x180026d8a  lea     rax, [rbp+0A0h+var_F8]
0x180026d8e  mov     [rsp+1A0h+var_158], rax
0x180026d93  lea     rax, [rbp+0A0h+arg_38]
0x180026d9a  mov     [rsp+1A0h+var_160], rax
0x180026d9f  lea     rax, [rbp+0A0h+var_F0]
0x180026da3  mov     [rsp+1A0h+var_168], rax
0x180026da8  lea     rax, [rbp+0A0h+arg_28]
0x180026daf  mov     [rsp+1A0h+var_170], rax
0x180026db4  lea     rax, [rbp+0A0h+var_E8]
0x180026db8  mov     [rsp+1A0h+var_178], rax
0x180026dbd  lea     rax, [rbp+0A0h+var_120]
0x180026dc1  mov     [rsp+1A0h+var_180], rax
0x180026dc6  call    _lambda_e5725e412e5b80066c0ddc6c4f046f9d____lambda_e5725e412e5b80066c0ddc6c4f046f9d_
0x180026dcb  mov     rcx, rax
0x180026dce  call    VCardErrorContract__lambda_e5725e412e5b80066c0ddc6c4f046f9d___; VCardErrorContract__lambda_e5725e412e5b80066c0ddc6c4f046f9d_
0x180026dd3  mov     ebx, eax
0x180026dd5  test    eax, eax
0x180026dd7  jle     short loc_180026DE2
0x180026dd9  movzx   ebx, ax
0x180026ddc  or      ebx, 80070000h
0x180026de2  lea     rcx, [rbp+0A0h+var_D8]
0x180026de6  mov     [rbp+0A0h+var_10C], ebx
0x180026de9  call    WppTraceUnwinder__lambda_f4b35da9302f823b1ca21f65a71b1469_______WppTraceUnwinder__lambda_f4b35da9302f823b1ca21f65a71b1469____
0x180026dee  mov     eax, ebx
0x180026df0  mov     rcx, [rbp+0A0h+var_18]
0x180026df7  xor     rcx, rsp; StackCookie
0x180026dfa  call    __security_check_cookie
0x180026dff  add     rsp, 198h
0x180026e06  pop     rbx
0x180026e07  pop     rbp
0x180026e08  retn
```
