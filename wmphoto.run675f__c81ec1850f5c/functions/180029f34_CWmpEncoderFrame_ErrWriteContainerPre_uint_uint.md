# CWmpEncoderFrame::ErrWriteContainerPre(uint,uint)

- ea: `0x180029f34`
- end: `0x18002a749`
- name: `?ErrWriteContainerPre@CWmpEncoderFrame@@IEAAJII@Z`
- size: `2069`
- prototype: `__int64 __fastcall(CWmpEncoderFrame *__hidden this, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180029930`
- `0x18002c260`

## callees

- `0x180029f34`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002a407`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002a407`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a4a9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a4d0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a4a9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a4d0`

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
0x180029f34  mov     [rsp-38h+arg_8], rbx
0x180029f39  push    rbp
0x180029f3a  push    rsi
0x180029f3b  push    rdi
0x180029f3c  push    r12
0x180029f3e  push    r13
0x180029f40  push    r14
0x180029f42  push    r15
0x180029f44  mov     rbp, rsp
0x180029f47  sub     rsp, 80h
0x180029f4e  lea     r13, [rcx+98h]
0x180029f55  xor     edi, edi
0x180029f57  mov     rax, [r13+60h]
0x180029f5b  mov     r14d, edx
0x180029f5e  mov     rbx, rcx
0x180029f61  mov     dword ptr [rbp+cb], edi
0x180029f64  mov     rcx, r13
0x180029f67  mov     [rbp+var_48], rdi
0x180029f6b  lea     rdx, [rbp+var_40]
0x180029f6f  mov     [rbp+var_40], rdi
0x180029f73  mov     r15d, r8d
0x180029f76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029f7b  mov     esi, eax
0x180029f7d  test    eax, eax
0x180029f7f  js      short loc_180029FA0
0x180029f81  mov     rax, [rbp+var_40]
0x180029f85  test    al, 1
0x180029f87  jnz     short loc_180029F9B
0x180029f89  mov     [rbx+103D4h], eax
0x180029f8f  cmp     r14d, [rbx+64h]
0x180029f93  jnz     short loc_180029FD9
0x180029f95  cmp     r15d, [rbx+68h]
0x180029f99  jz      short loc_180029FE5
0x180029f9b  mov     esi, 0FFFFFF96h
0x180029fa0  mov     rcx, [rbp+var_48]
0x180029fa4  test    rcx, rcx
0x180029fa7  jz      short loc_180029FB5
0x180029fa9  mov     rax, [rcx]
0x180029fac  mov     rax, [rax+10h]
0x180029fb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029fb5  mov     rbx, [rsp+80h+arg_8]
0x180029fbd  or      eax, 0FFFFFFFFh
0x180029fc0  test    edi, edi
0x180029fc2  cmovz   eax, esi
0x180029fc5  add     rsp, 80h
0x180029fcc  pop     r15
0x180029fce  pop     r14
0x180029fd0  pop     r13
0x180029fd2  pop     r12
0x180029fd4  pop     rdi
0x180029fd5  pop     rsi
0x180029fd6  pop     rbp
0x180029fd7  retn
0x180029fd9  cmp     r14d, [rbx+68h]
0x180029fdd  jnz     short loc_180029F9B
0x180029fdf  cmp     r15d, [rbx+64h]
0x180029fe3  jnz     short loc_180029F9B
0x180029fe5  mov     rcx, [rbx+103E8h]
0x180029fec  lea     r9, [rbp+var_38]
0x180029ff0  xor     eax, eax
0x180029ff2  lea     r8, [rbp+var_20]
0x180029ff6  mov     [rbp+var_10], rax
0x180029ffa  xor     esi, esi
0x180029ffc  mov     [rbp+var_28], rax
0x18002a000  xorps   xmm0, xmm0
0x18002a003  movups  [rbp+var_20], xmm0
0x18002a007  xor     edx, edx
0x18002a009  lea     eax, [rsi+12h]
0x18002a00c  xorps   xmm1, xmm1
0x18002a00f  mov     word ptr [rbp+var_20], ax
0x18002a013  lea     r12d, [rsi+13h]
0x18002a017  movups  [rbp+var_38], xmm1
0x18002a01b  mov     eax, 0BC80h
0x18002a020  mov     word ptr [rbp+var_38], r12w
0x18002a025  mov     word ptr [rbp+var_20+8], ax
0x18002a029  mov     dword ptr [rbp+var_38+8], r14d
0x18002a02d  mov     rax, [rcx]
0x18002a030  mov     rax, [rax+48h]
0x18002a034  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a039  mov     edi, eax
0x18002a03b  test    eax, eax
0x18002a03d  js      loc_180029FA0
0x18002a043  mov     rcx, [rbx+103E8h]
0x18002a04a  lea     r14d, [rsi+12h]
0x18002a04e  xor     eax, eax
0x18002a050  lea     r9, [rbp+var_38]
0x18002a054  mov     [rbp+var_10], rax
0x18002a058  lea     r8, [rbp+var_20]
0x18002a05c  mov     [rbp+var_28], rax
0x18002a060  xorps   xmm0, xmm0
0x18002a063  movups  [rbp+var_20], xmm0
0x18002a067  mov     word ptr [rbp+var_20], r14w
0x18002a06c  mov     eax, 0BC81h
0x18002a071  mov     word ptr [rbp+var_20+8], ax
0x18002a075  xorps   xmm1, xmm1
0x18002a078  movups  [rbp+var_38], xmm1
0x18002a07c  mov     word ptr [rbp+var_38], r12w
0x18002a081  xor     edx, edx
0x18002a083  mov     dword ptr [rbp+var_38+8], r15d
0x18002a087  mov     rax, [rcx]
0x18002a08a  mov     rax, [rax+48h]
0x18002a08e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a093  mov     edi, eax
0x18002a095  test    eax, eax
0x18002a097  js      loc_180029FA0
0x18002a09d  mov     rcx, [rbx+103E8h]
0x18002a0a4  lea     r15d, [rsi+4]
0x18002a0a8  xor     eax, eax
0x18002a0aa  lea     r9, [rbp+var_38]
0x18002a0ae  xorps   xmm0, xmm0
0x18002a0b1  mov     [rbp+var_10], rax
0x18002a0b5  movups  [rbp+var_20], xmm0
0x18002a0b9  lea     r8, [rbp+var_20]
0x18002a0bd  mov     [rbp+var_28], rax
0x18002a0c1  movsd   xmm0, qword ptr [rbx+70h]
0x18002a0c6  xorps   xmm1, xmm1
0x18002a0c9  movups  [rbp+var_38], xmm1
0x18002a0cd  mov     eax, 0BC82h
0x18002a0d2  mov     word ptr [rbp+var_20], r14w
0x18002a0d7  mov     word ptr [rbp+var_20+8], ax
0x18002a0db  xor     edx, edx
0x18002a0dd  cvtpd2ps xmm0, xmm0
0x18002a0e1  mov     word ptr [rbp+var_38], r15w
0x18002a0e6  movss   dword ptr [rbp+var_38+8], xmm0
0x18002a0eb  mov     rax, [rcx]
0x18002a0ee  mov     rax, [rax+48h]
0x18002a0f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a0f7  mov     edi, eax
0x18002a0f9  test    eax, eax
0x18002a0fb  js      loc_180029FA0
0x18002a101  mov     rcx, [rbx+103E8h]
0x18002a108  lea     r9, [rbp+var_38]
0x18002a10c  xor     eax, eax
0x18002a10e  lea     r8, [rbp+var_20]
0x18002a112  xorps   xmm0, xmm0
0x18002a115  mov     [rbp+var_10], rax
0x18002a119  movups  [rbp+var_20], xmm0
0x18002a11d  mov     [rbp+var_28], rax
0x18002a121  mov     eax, 0BC83h
0x18002a126  movsd   xmm0, qword ptr [rbx+78h]
0x18002a12b  xorps   xmm1, xmm1
0x18002a12e  movups  [rbp+var_38], xmm1
0x18002a132  mov     word ptr [rbp+var_20+8], ax
0x18002a136  xor     edx, edx
0x18002a138  cvtpd2ps xmm0, xmm0
0x18002a13c  mov     word ptr [rbp+var_20], r14w
0x18002a141  mov     word ptr [rbp+var_38], r15w
0x18002a146  movss   dword ptr [rbp+var_38+8], xmm0
0x18002a14b  mov     rax, [rcx]
0x18002a14e  mov     rax, [rax+48h]
0x18002a152  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a157  mov     edi, eax
0x18002a159  test    eax, eax
0x18002a15b  js      loc_180029FA0
0x18002a161  mov     rcx, [rbx+103E8h]
0x18002a168  lea     r9, [rbp+var_38]
0x18002a16c  xor     eax, eax
0x18002a16e  lea     r8, [rbp+var_20]
0x18002a172  mov     [rbp+var_10], rax
0x18002a176  xorps   xmm0, xmm0
0x18002a179  mov     [rbp+var_28], rax
0x18002a17d  xorps   xmm1, xmm1
0x18002a180  movups  [rbp+var_20], xmm0
0x18002a184  mov     eax, 0BCC0h
0x18002a189  mov     word ptr [rbp+var_20], r14w
0x18002a18e  mov     word ptr [rbp+var_20+8], ax
0x18002a192  xor     edx, edx
0x18002a194  mov     eax, [rbx+80h]
0x18002a19a  movups  [rbp+var_38], xmm1
0x18002a19e  mov     dword ptr [rbp+var_38+8], eax
0x18002a1a1  mov     word ptr [rbp+var_38], r12w
0x18002a1a6  mov     rax, [rcx]
0x18002a1a9  mov     rax, [rax+48h]
0x18002a1ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a1b2  mov     edi, eax
0x18002a1b4  test    eax, eax
0x18002a1b6  js      loc_180029FA0
0x18002a1bc  mov     rcx, [rbx+103E8h]
0x18002a1c3  lea     r9, [rbp+var_38]
0x18002a1c7  xor     eax, eax
0x18002a1c9  lea     r8, [rbp+var_20]
0x18002a1cd  mov     [rbp+var_10], rax
0x18002a1d1  xorps   xmm0, xmm0
0x18002a1d4  mov     [rbp+var_28], rax
0x18002a1d8  xorps   xmm1, xmm1
0x18002a1db  movups  [rbp+var_20], xmm0
0x18002a1df  mov     eax, 0BCC1h
0x18002a1e4  mov     word ptr [rbp+var_20], r14w
0x18002a1e9  mov     word ptr [rbp+var_20+8], ax
0x18002a1ed  xor     edx, edx
0x18002a1ef  mov     eax, [rbx+84h]
0x18002a1f5  movups  [rbp+var_38], xmm1
0x18002a1f9  mov     dword ptr [rbp+var_38+8], eax
0x18002a1fc  mov     word ptr [rbp+var_38], r12w
0x18002a201  mov     rax, [rcx]
0x18002a204  mov     rax, [rax+48h]
0x18002a208  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a20d  mov     edi, eax
0x18002a20f  test    eax, eax
0x18002a211  js      loc_180029FA0
0x18002a217  cmp     [rbx+60h], sil
0x18002a21b  jz      loc_18002A2D7
0x18002a221  mov     rcx, [rbx+103E8h]
0x18002a228  lea     r9, [rbp+var_38]
0x18002a22c  xor     eax, eax
0x18002a22e  lea     r8, [rbp+var_20]
0x18002a232  mov     [rbp+var_10], rax
0x18002a236  xorps   xmm0, xmm0
0x18002a239  mov     [rbp+var_28], rax
0x18002a23d  xorps   xmm1, xmm1
0x18002a240  movups  [rbp+var_20], xmm0
0x18002a244  mov     eax, 0BCC2h
0x18002a249  mov     word ptr [rbp+var_20], r14w
0x18002a24e  mov     word ptr [rbp+var_20+8], ax
0x18002a252  xor     edx, edx
0x18002a254  mov     eax, [rbx+88h]
0x18002a25a  movups  [rbp+var_38], xmm1
0x18002a25e  mov     dword ptr [rbp+var_38+8], eax
0x18002a261  mov     word ptr [rbp+var_38], r12w
0x18002a266  mov     rax, [rcx]
0x18002a269  mov     rax, [rax+48h]
0x18002a26d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a272  mov     edi, eax
0x18002a274  test    eax, eax
0x18002a276  js      loc_180029FA0
0x18002a27c  mov     rcx, [rbx+103E8h]
0x18002a283  lea     r9, [rbp+var_38]
0x18002a287  xor     eax, eax
0x18002a289  lea     r8, [rbp+var_20]
0x18002a28d  mov     [rbp+var_10], rax
0x18002a291  xorps   xmm0, xmm0
0x18002a294  mov     [rbp+var_28], rax
0x18002a298  xorps   xmm1, xmm1
0x18002a29b  movups  [rbp+var_20], xmm0
0x18002a29f  mov     eax, 0BCC3h
0x18002a2a4  mov     word ptr [rbp+var_20], r14w
0x18002a2a9  mov     word ptr [rbp+var_20+8], ax
0x18002a2ad  xor     edx, edx
0x18002a2af  mov     eax, [rbx+8Ch]
0x18002a2b5  movups  [rbp+var_38], xmm1
0x18002a2b9  mov     dword ptr [rbp+var_38+8], eax
0x18002a2bc  mov     word ptr [rbp+var_38], r12w
0x18002a2c1  mov     rax, [rcx]
0x18002a2c4  mov     rax, [rax+48h]
0x18002a2c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a2cd  mov     edi, eax
0x18002a2cf  test    eax, eax
0x18002a2d1  js      loc_180029FA0
0x18002a2d7  mov     rax, [rbx+103F8h]
0x18002a2de  sub     rax, [rbx+103F0h]
0x18002a2e5  sar     rax, 3
0x18002a2e9  test    rax, rax
0x18002a2ec  jz      loc_18002A4F1
0x18002a2f2  xor     r12d, r12d
0x18002a2f5  mov     rcx, [rbx+103F0h]
0x18002a2fc  mov     rax, [rbx+103F8h]
0x18002a303  sub     rax, rcx
0x18002a306  mov     r15d, r12d
0x18002a309  sar     rax, 3
0x18002a30d  cmp     r15, rax
0x18002a310  jnb     loc_18002A4EB
0x18002a316  mov     [rbp+arg_18], 0
0x18002a31d  lea     rdx, [rbp+arg_18]
0x18002a321  mov     rcx, [rcx+r12*8]
0x18002a325  mov     rax, [rcx]
0x18002a328  mov     rax, [rax+30h]
0x18002a32c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a331  mov     edi, eax
0x18002a333  test    eax, eax
0x18002a335  js      loc_180029FA0
0x18002a33b  mov     ecx, [rbp+arg_18]
0x18002a33e  mov     [rbp+var_50], 0FFFFFFFFh
0x18002a345  sub     ecx, 1
0x18002a348  jz      loc_18002A3DA
0x18002a34e  cmp     ecx, 1
0x18002a351  jnz     loc_18002A4C3
0x18002a357  mov     rax, [rbx+103F0h]
0x18002a35e  lea     rdx, [rbp+var_50]
0x18002a362  mov     rcx, [rax+r12*8]
0x18002a366  mov     rax, [rcx]
0x18002a369  mov     rax, [rax+40h]
0x18002a36d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a372  mov     edi, eax
0x18002a374  test    eax, eax
0x18002a376  js      loc_180029FA0
0x18002a37c  mov     rcx, [rbx+103E8h]
0x18002a383  lea     r9, [rbp+var_38]
0x18002a387  xor     eax, eax
0x18002a389  lea     r8, [rbp+var_20]
0x18002a38d  mov     [rbp+var_10], rax
0x18002a391  xorps   xmm0, xmm0
0x18002a394  mov     [rbp+var_28], rax
0x18002a398  xorps   xmm1, xmm1
0x18002a39b  movups  [rbp+var_20], xmm0
0x18002a39f  mov     eax, 0A001h
0x18002a3a4  mov     word ptr [rbp+var_20], r14w
0x18002a3a9  mov     word ptr [rbp+var_20+8], ax
0x18002a3ad  xor     edx, edx
0x18002a3af  movzx   eax, word ptr [rbp+var_50]
0x18002a3b3  movups  [rbp+var_38], xmm1
  ... truncated ...
```
