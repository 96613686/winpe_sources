# CWmpEncoderFrame::ErrWriteContainerPre(uint,uint)

- ea: `0x180029db8`
- end: `0x18002a5b6`
- name: `?ErrWriteContainerPre@CWmpEncoderFrame@@IEAAJII@Z`
- size: `2046`
- prototype: `__int64 __fastcall(CWmpEncoderFrame *__hidden this, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800297c0`
- `0x18002bfd0`

## callees

- `0x180029db8`
- `0x180044010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002a28a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002a28a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a322`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a343`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a322`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a343`

## pseudocode

```c
__int64 __fastcall CWmpEncoderFrame::ErrWriteContainerPre(CWmpEncoderFrame *this, int a2, int a3)
{
  char *v3; // r13
  int v4; // edi
  __int64 (__fastcall *v5)(char *, __int64 *); // rax
  int v9; // esi
  __int64 result; // rax
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rcx
  double v14; // xmm0_8
  __int64 v15; // rcx
  double v16; // xmm0_8
  __int64 v17; // rcx
  int v18; // eax
  __int64 v19; // rcx
  int v20; // eax
  __int64 v21; // rcx
  int v22; // eax
  __int64 v23; // rcx
  int v24; // eax
  __int64 i; // r12
  __int64 v26; // rcx
  __int64 v27; // rcx
  __int64 v28; // rcx
  __int64 v29; // rcx
  char *v30; // r14
  __int64 v31; // rcx
  __int64 v32; // rcx
  __int64 v33; // rcx
  __int64 v34; // rcx
  int v35; // eax
  char v36; // al
  __int64 v37; // rcx
  char v38; // al
  __int64 v39; // rcx
  __int64 v40; // rcx
  bool v41; // zf
  int v42; // [rsp+30h] [rbp-50h] BYREF
  __int64 v43; // [rsp+38h] [rbp-48h] BYREF
  __int64 v44; // [rsp+40h] [rbp-40h] BYREF
  __int128 v45; // [rsp+48h] [rbp-38h] BYREF
  char *v46; // [rsp+58h] [rbp-28h]
  __int128 v47; // [rsp+60h] [rbp-20h] BYREF
  __int64 v48; // [rsp+70h] [rbp-10h]
  SIZE_T cb; // [rsp+C0h] [rbp+40h] BYREF
  int v50; // [rsp+D8h] [rbp+58h] BYREF

  v3 = (char *)this + 152;
  v4 = 0;
  v5 = (__int64 (__fastcall *)(char *, __int64 *))*((_QWORD *)this + 31);
  LODWORD(cb) = 0;
  v43 = 0;
  v44 = 0;
  v9 = v5((char *)this + 152, &v44);
  if ( v9 >= 0 )
  {
    if ( (v44 & 1) != 0 )
    {
LABEL_5:
      v9 = -106;
      goto LABEL_6;
    }
    *((_DWORD *)this + 16629) = v44;
    if ( a2 == *((_DWORD *)this + 25) )
    {
      if ( a3 != *((_DWORD *)this + 26) )
        goto LABEL_5;
    }
    else if ( a2 != *((_DWORD *)this + 26) || a3 != *((_DWORD *)this + 25) )
    {
      goto LABEL_5;
    }
    v11 = *((_QWORD *)this + 8317);
    v48 = 0;
    v9 = 0;
    v46 = 0;
    v47 = 0;
    LOWORD(v47) = 18;
    v45 = 0;
    LOWORD(v45) = 19;
    WORD4(v47) = -17280;
    DWORD2(v45) = a2;
    v4 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int128 *, __int128 *))(*(_QWORD *)v11 + 72LL))(
           v11,
           0,
           &v47,
           &v45);
    if ( v4 >= 0 )
    {
      v12 = *((_QWORD *)this + 8317);
      v48 = 0;
      v46 = 0;
      v47 = 0;
      LOWORD(v47) = 18;
      WORD4(v47) = -17279;
      v45 = 0;
      LOWORD(v45) = 19;
      DWORD2(v45) = a3;
      v4 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int128 *, __int128 *))(*(_QWORD *)v12 + 72LL))(
             v12,
             0,
             &v47,
             &v45);
      if ( v4 >= 0 )
      {
        v13 = *((_QWORD *)this + 8317);
        v48 = 0;
        v47 = 0;
        v46 = 0;
        v14 = *((double *)this + 14);
        v45 = 0;
        LOWORD(v47) = 18;
        WORD4(v47) = -17278;
        LOWORD(v45) = 4;
        *((float *)&v45 + 2) = v14;
        v4 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int128 *, __int128 *))(*(_QWORD *)v13 + 72LL))(
               v13,
               0,
               &v47,
               &v45);
        if ( v4 >= 0 )
        {
          v15 = *((_QWORD *)this + 8317);
          v48 = 0;
          v47 = 0;
          v46 = 0;
          v16 = *((double *)this + 15);
          v45 = 0;
          WORD4(v47) = -17277;
          LOWORD(v47) = 18;
          LOWORD(v45) = 4;
          *((float *)&v45 + 2) = v16;
          v4 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int128 *, __int128 *))(*(_QWORD *)v15 + 72LL))(
                 v15,
                 0,
                 &v47,
                 &v45);
          if ( v4 >= 0 )
          {
            v17 = *((_QWORD *)this + 8317);
            v48 = 0;
            v46 = 0;
            v47 = 0;
            LOWORD(v47) = 18;
            WORD4(v47) = -17216;
            v18 = *((_DWORD *)this + 32);
            v45 = 0;
            DWORD2(v45) = v18;
            LOWORD(v45) = 19;
            v4 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int128 *, __int128 *))(*(_QWORD *)v17 + 72LL))(
                   v17,
                   0,
                   &v47,
                   &v45);
            if ( v4 >= 0 )
            {
              v19 = *((_QWORD *)this + 8317);
              v48 = 0;
              v46 = 0;
              v47 = 0;
              LOWORD(v47) = 18;
              WORD4(v47) = -17215;
              v20 = *((_DWORD *)this + 33);
              v45 = 0;
              DWORD2(v45) = v20;
              LOWORD(v45) = 19;
              v4 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int128 *, __int128 *))(*(_QWORD *)v19 + 72LL))(
                     v19,
                     0,
                     &v47,
                     &v45);
              if ( v4 >= 0 )
              {
                if ( !*((_BYTE *)this + 96) )
                  goto LABEL_54;
                v21 = *((_QWORD *)this + 8317);
                v48 = 0;
                v46 = 0;
                v47 = 0;
                LOWORD(v47) = 18;
                WORD4(v47) = -17214;
                v22 = *((_DWORD *)this + 34);
                v45 = 0;
                DWORD2(v45) = v22;
                LOWORD(v45) = 19;
                v4 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int128 *, __int128 *))(*(_QWORD *)v21 + 72LL))(
                       v21,
                       0,
                       &v47,
                       &v45);
                if ( v4 >= 0 )
                {
                  v23 = *((_QWORD *)this + 8317);
                  v48 = 0;
                  v46 = 0;
                  v47 = 0;
                  LOWORD(v47) = 18;
                  WORD4(v47) = -17213;
                  v24 = *((_DWORD *)this + 35);
                  v45 = 0;
                  DWORD2(v45) = v24;
                  LOWORD(v45) = 19;
                  v4 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int128 *, __int128 *))(*(_QWORD *)v23 + 72LL))(
                         v23,
                         0,
                         &v47,
                         &v45);
                  if ( v4 >= 0 )
                  {
LABEL_54:
                    if ( (__int64)(*((_QWORD *)this + 8319) - *((_QWORD *)this + 8318)) >> 3 )
                    {
                      for ( i = 0; ; i = (unsigned int)(i + 1) )
                      {
                        v26 = *((_QWORD *)this + 8318);
                        if ( (unsigned int)i >= (unsigned __int64)((*((_QWORD *)this + 8319) - v26) >> 3) )
                          break;
                        v50 = 0;
                        v4 = (*(__int64 (__fastcall **)(_QWORD, int *))(**(_QWORD **)(v26 + 8 * i) + 48LL))(
                               *(_QWORD *)(v26 + 8 * i),
                               &v50);
                        if ( v4 < 0 )
                          goto LABEL_6;
                        v42 = -1;
                        if ( v50 == 1 )
                        {
                          v29 = *(_QWORD *)(*((_QWORD *)this + 8318) + 8 * i);
                          v4 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, SIZE_T *))(*(_QWORD *)v29 + 56LL))(
                                 v29,
                                 0,
                                 0,
                                 &cb);
                          if ( v4 < 0 )
                            goto LABEL_6;
                          v30 = (char *)CoTaskMemAlloc((unsigned int)cb);
                          if ( !v30 )
                          {
                            v4 = -2147024882;
                            goto LABEL_6;
                          }
                          v31 = *(_QWORD *)(*((_QWORD *)this + 8318) + 8 * i);
                          v4 = (*(__int64 (__fastcall **)(__int64, _QWORD, char *, SIZE_T *))(*(_QWORD *)v31 + 56LL))(
                                 v31,
                                 (unsigned int)cb,
                                 v30,
                                 &cb);
                          if ( v4 < 0 )
                            goto LABEL_38;
                          v32 = *((_QWORD *)this + 8317);
                          v46 = v30;
                          v48 = 0;
                          v47 = 0;
                          LOWORD(v47) = 18;
                          WORD4(v47) = -30861;
                          v45 = 0;
                          LOWORD(v45) = 65;
                          DWORD2(v45) = cb;
                          v4 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int128 *, __int128 *))(*(_QWORD *)v32 + 72LL))(
                                 v32,
                                 0,
                                 &v47,
                                 &v45);
                          if ( v4 < 0 )
                          {
LABEL_38:
                            CoTaskMemFree(v30);
                            goto LABEL_6;
                          }
                          CoTaskMemFree(v30);
                        }
                        else
                        {
                          if ( v50 != 2 )
                          {
                            v4 = -2147024809;
                            goto LABEL_6;
                          }
                          v27 = *(_QWORD *)(*((_QWORD *)this + 8318) + 8 * i);
                          v4 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v27 + 64LL))(v27, &v42);
                          if ( v4 < 0 )
                            goto LABEL_6;
                          v28 = *((_QWORD *)this + 8317);
                          v48 = 0;
                          v46 = 0;
                          v47 = 0;
                          LOWORD(v47) = 18;
                          WORD4(v47) = -24575;
                          v45 = 0;
                          DWORD2(v45) = (unsigned __int16)v42;
                          LOWORD(v45) = 18;
                          v4 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int128 *, __int128 *))(*(_QWORD *)v28 + 72LL))(
                                 v28,
                                 0,
                                 &v47,
                                 &v45);
                          if ( v4 < 0 )
                            goto LABEL_6;
                        }
                      }
                    }
                    v33 = *((_QWORD *)this + 8317);
                    v48 = 0;
                    v47 = 0;
                    LOWORD(v47) = 18;
                    WORD4(v47) = -17407;
                    v45 = 0;
                    DWORD2(v45) = 16;
                    LOWORD(v45) = 4113;
                    v46 = (char *)this + 24;
                    v4 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int128 *, __int128 *))(*(_QWORD *)v33 + 72LL))(
                           v33,
                           0,
                           &v47,
                           &v45);
                    if ( v4 >= 0 )
                    {
                      v34 = *((_QWORD *)this + 8317);
                      v48 = 0;
                      v46 = 0;
                      v47 = 0;
                      LOWORD(v47) = 18;
                      WORD4(v47) = -17406;
                      v35 = *((unsigned __int8 *)this + 66464);
                      v45 = 0;
                      DWORD2(v45) = v35;
                      LOWORD(v45) = 19;
                      v4 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int128 *, __int128 *))(*(_QWORD *)v34 + 72LL))(
                             v34,
                             0,
                             &v47,
                             &v45);
                      if ( v4 >= 0 )
                      {
                        if ( !*((_DWORD *)this + 16623) )
                          goto LABEL_55;
                        v36 = *((_BYTE *)this + 66496);
                        if ( !v36 )
                          goto LABEL_56;
                        v48 = 0;
                        v46 = 0;
                        v47 = 0;
                        LOWORD(v47) = 18;
                        WORD4(v47) = -17212;
                        v37 = *((_QWORD *)this + 8317);
                        v45 = 0;
                        BYTE8(v45) = v36;
                        LOWORD(v45) = 17;
                        v4 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int128 *, __int128 *))(*(_QWORD *)v37 + 72LL))(
                               v37,
                               0,
                               &v47,
                               &v45);
                        if ( v4 >= 0 )
                        {
LABEL_56:
                          if ( !*((_BYTE *)this + 96) )
                            goto LABEL_55;
                          v38 = *((_BYTE *)this + 66497);
                          if ( !v38 )
                            goto LABEL_55;
                          v48 = 0;
                          v46 = 0;
                          v47 = 0;
                          LOWORD(v47) = 18;
                          WORD4(v47) = -17211;
                          v39 = *((_QWORD *)this + 8317);
                          v45 = 0;
                          BYTE8(v45) = v38;
                          LOWORD(v45) = 17;
                          v4 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int128 *, __int128 *))(*(_QWORD *)v39 + 72LL))(
                                 v39,
                                 0,
                                 &v47,
                                 &v45);
                          if ( v4 >= 0 )
                          {
LABEL_55:
                            v40 = *((_QWORD *)this + 8317);
                            v48 = 0;
                            v46 = 0;
                            v47 = 0;
                            LOWORD(v47) = 18;
                            WORD4(v47) = -17404;
                            v41 = *((_DWORD *)this + 16647) == 0;
                            v45 = 0;
                            LOWORD(v45) = 19;
                            DWORD2(v45) = !v41;
                            v4 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int128 *, __int128 *))(*(_QWORD *)v40 + 72LL))(
                                   v40,
                                   0,
                                   &v47,
                                   &v45);
                            if ( v4 >= 0 )
                            {
                              v9 = (*((__int64 (__fastcall **)(char *, _QWORD))v3 + 11))(
                                     v3,
                                     *((unsigned int *)this + 16629));
                              if ( v9 >= 0 )
                              {
                                v4 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))this + 8317))(
                                       *((_QWORD *)this + 8317),
                                       &IID_IPersistStream,
                                       &v43);
                                if ( v4 >= 0 )
                                  v4 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v43 + 48LL))(
                                         v43,
                                         *(_QWORD *)v3,
                                         1);
                              }
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_6:
  if ( v43 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
  result = 0xFFFFFFFFLL;
  if ( !v4 )
    return (unsigned int)v9;
  return result;
}

```

## disassembly

```asm
0x180029db8  mov     [rsp-38h+arg_8], rbx
0x180029dbd  push    rbp
0x180029dbe  push    rsi
0x180029dbf  push    rdi
0x180029dc0  push    r12
0x180029dc2  push    r13
0x180029dc4  push    r14
0x180029dc6  push    r15
0x180029dc8  mov     rbp, rsp
0x180029dcb  sub     rsp, 80h
0x180029dd2  lea     r13, [rcx+98h]
0x180029dd9  xor     edi, edi
0x180029ddb  mov     rax, [r13+60h]
0x180029ddf  mov     r14d, edx
0x180029de2  mov     rbx, rcx
0x180029de5  mov     dword ptr [rbp+cb], edi
0x180029de8  mov     rcx, r13
0x180029deb  mov     [rbp+var_48], rdi
0x180029def  lea     rdx, [rbp+var_40]
0x180029df3  mov     [rbp+var_40], rdi
0x180029df7  mov     r15d, r8d
0x180029dfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029dff  mov     esi, eax
0x180029e01  test    eax, eax
0x180029e03  js      short loc_180029E24
0x180029e05  mov     rax, [rbp+var_40]
0x180029e09  test    al, 1
0x180029e0b  jnz     short loc_180029E1F
0x180029e0d  mov     [rbx+103D4h], eax
0x180029e13  cmp     r14d, [rbx+64h]
0x180029e17  jnz     short loc_180029E5C
0x180029e19  cmp     r15d, [rbx+68h]
0x180029e1d  jz      short loc_180029E68
0x180029e1f  mov     esi, 0FFFFFF96h
0x180029e24  mov     rcx, [rbp+var_48]
0x180029e28  test    rcx, rcx
0x180029e2b  jz      short loc_180029E39
0x180029e2d  mov     rax, [rcx]
0x180029e30  mov     rax, [rax+10h]
0x180029e34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029e39  mov     rbx, [rsp+80h+arg_8]
0x180029e41  or      eax, 0FFFFFFFFh
0x180029e44  test    edi, edi
0x180029e46  cmovz   eax, esi
0x180029e49  add     rsp, 80h
0x180029e50  pop     r15
0x180029e52  pop     r14
0x180029e54  pop     r13
0x180029e56  pop     r12
0x180029e58  pop     rdi
0x180029e59  pop     rsi
0x180029e5a  pop     rbp
0x180029e5b  retn
0x180029e5c  cmp     r14d, [rbx+68h]
0x180029e60  jnz     short loc_180029E1F
0x180029e62  cmp     r15d, [rbx+64h]
0x180029e66  jnz     short loc_180029E1F
0x180029e68  mov     rcx, [rbx+103E8h]
0x180029e6f  lea     r9, [rbp+var_38]
0x180029e73  xor     eax, eax
0x180029e75  lea     r8, [rbp+var_20]
0x180029e79  mov     [rbp+var_10], rax
0x180029e7d  xor     esi, esi
0x180029e7f  mov     [rbp+var_28], rax
0x180029e83  xorps   xmm0, xmm0
0x180029e86  movups  [rbp+var_20], xmm0
0x180029e8a  xor     edx, edx
0x180029e8c  lea     eax, [rsi+12h]
0x180029e8f  xorps   xmm1, xmm1
0x180029e92  mov     word ptr [rbp+var_20], ax
0x180029e96  lea     r12d, [rsi+13h]
0x180029e9a  movups  [rbp+var_38], xmm1
0x180029e9e  mov     eax, 0BC80h
0x180029ea3  mov     word ptr [rbp+var_38], r12w
0x180029ea8  mov     word ptr [rbp+var_20+8], ax
0x180029eac  mov     dword ptr [rbp+var_38+8], r14d
0x180029eb0  mov     rax, [rcx]
0x180029eb3  mov     rax, [rax+48h]
0x180029eb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029ebc  mov     edi, eax
0x180029ebe  test    eax, eax
0x180029ec0  js      loc_180029E24
0x180029ec6  mov     rcx, [rbx+103E8h]
0x180029ecd  lea     r14d, [rsi+12h]
0x180029ed1  xor     eax, eax
0x180029ed3  lea     r9, [rbp+var_38]
0x180029ed7  mov     [rbp+var_10], rax
0x180029edb  lea     r8, [rbp+var_20]
0x180029edf  mov     [rbp+var_28], rax
0x180029ee3  xorps   xmm0, xmm0
0x180029ee6  movups  [rbp+var_20], xmm0
0x180029eea  mov     word ptr [rbp+var_20], r14w
0x180029eef  mov     eax, 0BC81h
0x180029ef4  mov     word ptr [rbp+var_20+8], ax
0x180029ef8  xorps   xmm1, xmm1
0x180029efb  movups  [rbp+var_38], xmm1
0x180029eff  mov     word ptr [rbp+var_38], r12w
0x180029f04  xor     edx, edx
0x180029f06  mov     dword ptr [rbp+var_38+8], r15d
0x180029f0a  mov     rax, [rcx]
0x180029f0d  mov     rax, [rax+48h]
0x180029f11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029f16  mov     edi, eax
0x180029f18  test    eax, eax
0x180029f1a  js      loc_180029E24
0x180029f20  mov     rcx, [rbx+103E8h]
0x180029f27  lea     r15d, [rsi+4]
0x180029f2b  xor     eax, eax
0x180029f2d  lea     r9, [rbp+var_38]
0x180029f31  xorps   xmm0, xmm0
0x180029f34  mov     [rbp+var_10], rax
0x180029f38  movups  [rbp+var_20], xmm0
0x180029f3c  lea     r8, [rbp+var_20]
0x180029f40  mov     [rbp+var_28], rax
0x180029f44  movsd   xmm0, qword ptr [rbx+70h]
0x180029f49  xorps   xmm1, xmm1
0x180029f4c  movups  [rbp+var_38], xmm1
0x180029f50  mov     eax, 0BC82h
0x180029f55  mov     word ptr [rbp+var_20], r14w
0x180029f5a  mov     word ptr [rbp+var_20+8], ax
0x180029f5e  xor     edx, edx
0x180029f60  cvtpd2ps xmm0, xmm0
0x180029f64  mov     word ptr [rbp+var_38], r15w
0x180029f69  movss   dword ptr [rbp+var_38+8], xmm0
0x180029f6e  mov     rax, [rcx]
0x180029f71  mov     rax, [rax+48h]
0x180029f75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029f7a  mov     edi, eax
0x180029f7c  test    eax, eax
0x180029f7e  js      loc_180029E24
0x180029f84  mov     rcx, [rbx+103E8h]
0x180029f8b  lea     r9, [rbp+var_38]
0x180029f8f  xor     eax, eax
0x180029f91  lea     r8, [rbp+var_20]
0x180029f95  xorps   xmm0, xmm0
0x180029f98  mov     [rbp+var_10], rax
0x180029f9c  movups  [rbp+var_20], xmm0
0x180029fa0  mov     [rbp+var_28], rax
0x180029fa4  mov     eax, 0BC83h
0x180029fa9  movsd   xmm0, qword ptr [rbx+78h]
0x180029fae  xorps   xmm1, xmm1
0x180029fb1  movups  [rbp+var_38], xmm1
0x180029fb5  mov     word ptr [rbp+var_20+8], ax
0x180029fb9  xor     edx, edx
0x180029fbb  cvtpd2ps xmm0, xmm0
0x180029fbf  mov     word ptr [rbp+var_20], r14w
0x180029fc4  mov     word ptr [rbp+var_38], r15w
0x180029fc9  movss   dword ptr [rbp+var_38+8], xmm0
0x180029fce  mov     rax, [rcx]
0x180029fd1  mov     rax, [rax+48h]
0x180029fd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029fda  mov     edi, eax
0x180029fdc  test    eax, eax
0x180029fde  js      loc_180029E24
0x180029fe4  mov     rcx, [rbx+103E8h]
0x180029feb  lea     r9, [rbp+var_38]
0x180029fef  xor     eax, eax
0x180029ff1  lea     r8, [rbp+var_20]
0x180029ff5  mov     [rbp+var_10], rax
0x180029ff9  xorps   xmm0, xmm0
0x180029ffc  mov     [rbp+var_28], rax
0x18002a000  xorps   xmm1, xmm1
0x18002a003  movups  [rbp+var_20], xmm0
0x18002a007  mov     eax, 0BCC0h
0x18002a00c  mov     word ptr [rbp+var_20], r14w
0x18002a011  mov     word ptr [rbp+var_20+8], ax
0x18002a015  xor     edx, edx
0x18002a017  mov     eax, [rbx+80h]
0x18002a01d  movups  [rbp+var_38], xmm1
0x18002a021  mov     dword ptr [rbp+var_38+8], eax
0x18002a024  mov     word ptr [rbp+var_38], r12w
0x18002a029  mov     rax, [rcx]
0x18002a02c  mov     rax, [rax+48h]
0x18002a030  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a035  mov     edi, eax
0x18002a037  test    eax, eax
0x18002a039  js      loc_180029E24
0x18002a03f  mov     rcx, [rbx+103E8h]
0x18002a046  lea     r9, [rbp+var_38]
0x18002a04a  xor     eax, eax
0x18002a04c  lea     r8, [rbp+var_20]
0x18002a050  mov     [rbp+var_10], rax
0x18002a054  xorps   xmm0, xmm0
0x18002a057  mov     [rbp+var_28], rax
0x18002a05b  xorps   xmm1, xmm1
0x18002a05e  movups  [rbp+var_20], xmm0
0x18002a062  mov     eax, 0BCC1h
0x18002a067  mov     word ptr [rbp+var_20], r14w
0x18002a06c  mov     word ptr [rbp+var_20+8], ax
0x18002a070  xor     edx, edx
0x18002a072  mov     eax, [rbx+84h]
0x18002a078  movups  [rbp+var_38], xmm1
0x18002a07c  mov     dword ptr [rbp+var_38+8], eax
0x18002a07f  mov     word ptr [rbp+var_38], r12w
0x18002a084  mov     rax, [rcx]
0x18002a087  mov     rax, [rax+48h]
0x18002a08b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a090  mov     edi, eax
0x18002a092  test    eax, eax
0x18002a094  js      loc_180029E24
0x18002a09a  cmp     [rbx+60h], sil
0x18002a09e  jz      loc_18002A15A
0x18002a0a4  mov     rcx, [rbx+103E8h]
0x18002a0ab  lea     r9, [rbp+var_38]
0x18002a0af  xor     eax, eax
0x18002a0b1  lea     r8, [rbp+var_20]
0x18002a0b5  mov     [rbp+var_10], rax
0x18002a0b9  xorps   xmm0, xmm0
0x18002a0bc  mov     [rbp+var_28], rax
0x18002a0c0  xorps   xmm1, xmm1
0x18002a0c3  movups  [rbp+var_20], xmm0
0x18002a0c7  mov     eax, 0BCC2h
0x18002a0cc  mov     word ptr [rbp+var_20], r14w
0x18002a0d1  mov     word ptr [rbp+var_20+8], ax
0x18002a0d5  xor     edx, edx
0x18002a0d7  mov     eax, [rbx+88h]
0x18002a0dd  movups  [rbp+var_38], xmm1
0x18002a0e1  mov     dword ptr [rbp+var_38+8], eax
0x18002a0e4  mov     word ptr [rbp+var_38], r12w
0x18002a0e9  mov     rax, [rcx]
0x18002a0ec  mov     rax, [rax+48h]
0x18002a0f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a0f5  mov     edi, eax
0x18002a0f7  test    eax, eax
0x18002a0f9  js      loc_180029E24
0x18002a0ff  mov     rcx, [rbx+103E8h]
0x18002a106  lea     r9, [rbp+var_38]
0x18002a10a  xor     eax, eax
0x18002a10c  lea     r8, [rbp+var_20]
0x18002a110  mov     [rbp+var_10], rax
0x18002a114  xorps   xmm0, xmm0
0x18002a117  mov     [rbp+var_28], rax
0x18002a11b  xorps   xmm1, xmm1
0x18002a11e  movups  [rbp+var_20], xmm0
0x18002a122  mov     eax, 0BCC3h
0x18002a127  mov     word ptr [rbp+var_20], r14w
0x18002a12c  mov     word ptr [rbp+var_20+8], ax
0x18002a130  xor     edx, edx
0x18002a132  mov     eax, [rbx+8Ch]
0x18002a138  movups  [rbp+var_38], xmm1
0x18002a13c  mov     dword ptr [rbp+var_38+8], eax
0x18002a13f  mov     word ptr [rbp+var_38], r12w
0x18002a144  mov     rax, [rcx]
0x18002a147  mov     rax, [rax+48h]
0x18002a14b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a150  mov     edi, eax
0x18002a152  test    eax, eax
0x18002a154  js      loc_180029E24
0x18002a15a  mov     rax, [rbx+103F8h]
0x18002a161  sub     rax, [rbx+103F0h]
0x18002a168  sar     rax, 3
0x18002a16c  test    rax, rax
0x18002a16f  jz      loc_18002A35E
0x18002a175  xor     r12d, r12d
0x18002a178  mov     rcx, [rbx+103F0h]
0x18002a17f  mov     rax, [rbx+103F8h]
0x18002a186  sub     rax, rcx
0x18002a189  mov     r15d, r12d
0x18002a18c  sar     rax, 3
0x18002a190  cmp     r15, rax
0x18002a193  jnb     loc_18002A358
0x18002a199  mov     [rbp+arg_18], 0
0x18002a1a0  lea     rdx, [rbp+arg_18]
0x18002a1a4  mov     rcx, [rcx+r12*8]
0x18002a1a8  mov     rax, [rcx]
0x18002a1ab  mov     rax, [rax+30h]
0x18002a1af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a1b4  mov     edi, eax
0x18002a1b6  test    eax, eax
0x18002a1b8  js      loc_180029E24
0x18002a1be  mov     ecx, [rbp+arg_18]
0x18002a1c1  mov     [rbp+var_50], 0FFFFFFFFh
0x18002a1c8  sub     ecx, 1
0x18002a1cb  jz      loc_18002A25D
0x18002a1d1  cmp     ecx, 1
0x18002a1d4  jnz     loc_18002A336
0x18002a1da  mov     rax, [rbx+103F0h]
0x18002a1e1  lea     rdx, [rbp+var_50]
0x18002a1e5  mov     rcx, [rax+r12*8]
0x18002a1e9  mov     rax, [rcx]
0x18002a1ec  mov     rax, [rax+40h]
0x18002a1f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a1f5  mov     edi, eax
0x18002a1f7  test    eax, eax
0x18002a1f9  js      loc_180029E24
0x18002a1ff  mov     rcx, [rbx+103E8h]
0x18002a206  lea     r9, [rbp+var_38]
0x18002a20a  xor     eax, eax
0x18002a20c  lea     r8, [rbp+var_20]
0x18002a210  mov     [rbp+var_10], rax
0x18002a214  xorps   xmm0, xmm0
0x18002a217  mov     [rbp+var_28], rax
0x18002a21b  xorps   xmm1, xmm1
0x18002a21e  movups  [rbp+var_20], xmm0
0x18002a222  mov     eax, 0A001h
0x18002a227  mov     word ptr [rbp+var_20], r14w
0x18002a22c  mov     word ptr [rbp+var_20+8], ax
0x18002a230  xor     edx, edx
0x18002a232  movzx   eax, word ptr [rbp+var_50]
0x18002a236  movups  [rbp+var_38], xmm1
  ... truncated ...
```
