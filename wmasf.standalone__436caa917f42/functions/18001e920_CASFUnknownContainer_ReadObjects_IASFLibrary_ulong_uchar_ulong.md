# CASFUnknownContainer::ReadObjects(IASFLibrary *,ulong,uchar *,ulong *)

- ea: `0x18001e920`
- end: `0x18001ef64`
- name: `?ReadObjects@CASFUnknownContainer@@UEAAJPEAUIASFLibrary@@KPEAEPEAK@Z`
- size: `1604`
- prototype: `__int64 __fastcall(CASFUnknownContainer *__hidden this, struct IASFLibrary *, unsigned int, unsigned __int8 *, unsigned int *)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x1800011c0`
- `0x1800011cc`
- `0x1800015d0`
- `0x18001decc`
- `0x18001e920`
- `0x18003f11c`
- `0x18003f294`
- `0x180040010`

## pseudocode

```c
__int64 __fastcall CASFUnknownContainer::ReadObjects(
        CASFUnknownContainer *this,
        struct IASFLibrary *a2,
        unsigned int a3,
        unsigned __int8 *a4,
        unsigned int *a5)
{
  struct IASFLibrary *v5; // r10
  unsigned __int64 v6; // r12
  int v8; // ebx
  unsigned int v9; // edi
  __int64 v10; // r8
  _DWORD *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rax
  __int64 v14; // rcx
  int v15; // esi
  unsigned __int8 *v16; // r13
  unsigned __int8 *v17; // r14
  unsigned __int64 v18; // r15
  __int64 v19; // rax
  int v20; // eax
  _QWORD *v21; // rcx
  _QWORD *v22; // rax
  __int64 v23; // r8
  int v24; // eax
  __int64 v25; // rdx
  void *v26; // rax
  void *v27; // r14
  __int64 v28; // rax
  unsigned __int64 v29; // rcx
  unsigned __int8 *v32; // [rsp+40h] [rbp-C0h]
  int v33; // [rsp+48h] [rbp-B8h]
  int v34; // [rsp+58h] [rbp-A8h] BYREF
  void *v35; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v36; // [rsp+68h] [rbp-98h] BYREF
  __int64 v37; // [rsp+70h] [rbp-90h] BYREF
  __int64 v38; // [rsp+78h] [rbp-88h] BYREF
  __int64 v39; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int64 v40; // [rsp+88h] [rbp-78h] BYREF
  __int128 Buf2; // [rsp+90h] [rbp-70h] BYREF
  __int64 v42; // [rsp+A0h] [rbp-60h] BYREF
  _DWORD *v43; // [rsp+A8h] [rbp-58h]
  int v44; // [rsp+B0h] [rbp-50h]
  _DWORD v45[101]; // [rsp+B4h] [rbp-4Ch] BYREF
  _QWORD *v46; // [rsp+248h] [rbp+148h]
  __int64 v47; // [rsp+250h] [rbp+150h]
  int v48; // [rsp+258h] [rbp+158h]

  v5 = a2;
  v33 = (int)a4;
  v6 = a3;
  if ( a5 && a2 )
  {
    if ( !a3 )
    {
      *a5 = 0;
      return 0;
    }
    if ( a4 )
    {
      if ( a3 < 0x18 )
      {
        *a5 = 24;
        return 3222079441LL;
      }
      v8 = 0;
      v9 = 0;
      v48 = 0;
      v10 = 0;
      v47 = 0;
      v11 = v45;
      v46 = 0;
      *(_QWORD *)&v45[99] = 0;
      v12 = 0;
      v43 = v45;
      *(_QWORD *)v45 = 0;
      v44 = 8;
      while ( 1 )
      {
        v13 = 3 * v12++;
        v14 = (__int64)&v11[2 * v13 + 2];
        *(_QWORD *)(v14 + 8) = v10;
        v10 = v14;
        v42 = v14;
        if ( v12 == 16 )
          break;
        v11 = v43;
      }
      v15 = 0;
      v16 = a4;
      v17 = 0;
      v32 = 0;
      while ( 1 )
      {
        if ( v9 + 24 > (unsigned int)v6 )
        {
LABEL_74:
          *a5 = v9;
          CVPtrList::~CVPtrList((CVPtrList *)&v42);
          return (unsigned int)v8;
        }
        Buf2 = 0;
        Buf2 = *(_OWORD *)v16;
        v18 = *((_QWORD *)v16 + 2);
        if ( v18 )
        {
          if ( v18 >= 0x100000000LL )
            LODWORD(v18) = -1;
        }
        else
        {
          LODWORD(v18) = v6 - v9;
        }
        v19 = *(_QWORD *)v5;
        v34 = 0;
        v35 = 0;
        v20 = (*(__int64 (__fastcall **)(struct IASFLibrary *, __int128 *, void **))(v19 + 56))(v5, &Buf2, &v35);
        if ( v20 != -2147221164 && v20 != -1072887824
          || (v8 = (*(__int64 (__fastcall **)(struct IASFLibrary *, GUID *, void **))(*(_QWORD *)a2 + 56LL))(
                     a2,
                     &CLSID_ASFGenericObject,
                     &v35),
              v8 >= 0) )
        {
          v8 = (*(__int64 (__fastcall **)(CASFUnknownContainer *, GUID *, void *, __int64))(*(_QWORD *)this + 40LL))(
                 this,
                 &GUID_NULL,
                 v35,
                 0xFFFFFFFFLL);
          if ( v8 >= 0 )
          {
            v8 = (*(__int64 (__fastcall **)(void *, _QWORD, unsigned __int8 *, int *))(*(_QWORD *)v35 + 64LL))(
                   v35,
                   (unsigned int)v6 - v9,
                   v16,
                   &v34);
            if ( v8 >= 0 )
            {
              if ( memcmp_0(&CLSID_ASFDataObjectv1, &Buf2, 0x10u) && v34 != (_DWORD)v18 )
              {
                v8 = -1072887838;
                goto LABEL_62;
              }
              if ( !memcmp_0(&CLSID_ASFDigitalSignatureObject, &Buf2, 0x10u) )
              {
                if ( !v15 || !v17 )
                {
LABEL_67:
                  v8 = -2147418113;
                  goto LABEL_62;
                }
                *((_DWORD *)this + 60) = (_DWORD)v17 - v33 + 30;
                *((_DWORD *)this + 61) = (_DWORD)v16 - (_DWORD)v17;
                while ( 1 )
                {
                  v21 = v46;
                  if ( !v46 )
                    break;
                  v22 = (_QWORD *)v46[1];
                  v23 = *v46;
                  v46 = v22;
                  if ( v22 )
                    v22[2] = 0;
                  else
                    v47 = 0;
                  v21[1] = v42;
                  --v48;
                  v42 = (__int64)v21;
                  if ( !v23 )
                    break;
                  (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v23 + 40LL))(v23, 1);
                }
                v15 = 0;
              }
              else if ( v15 && !CVPtrList::AddTail((CVPtrList *)&v42, v35) )
              {
                v8 = -2147024882;
                goto LABEL_62;
              }
              if ( !memcmp_0(&CLSID_ASFPropertiesObjectv1, &Buf2, 0x10u) )
              {
                if ( v15 )
                  goto LABEL_67;
                v15 = 1;
                v32 = &v16[v34];
              }
              if ( memcmp_0(&CLSID_ASFStreamPropertiesObjectExv1, &Buf2, 0x10u) )
                goto LABEL_79;
              v36 = 0;
              v24 = (**(__int64 (__fastcall ***)(void *, GUID *, __int64 *))v35)(
                      v35,
                      &IID_IASFStreamPropertiesObjectExv1,
                      &v36);
              v38 = 0;
              if ( v24 >= 0 )
              {
                (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v36 + 184LL))(v36, &v38);
                if ( v38 )
                {
                  v37 = 0;
                  if ( (**(int (__fastcall ***)(__int64, GUID *, __int64 *))v38)(
                         v38,
                         &IID_IASFStreamPropertiesObject,
                         &v37) >= 0 )
                  {
                    LODWORD(v40) = 0;
                    if ( (*(int (__fastcall **)(__int64, unsigned __int64 *))(*(_QWORD *)v37 + 240LL))(v37, &v40) >= 0 )
                    {
                      v25 = (unsigned int)v40;
                      LODWORD(v25) = v40 | 0x80000000;
                      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v37 + 248LL))(v37, v25);
                    }
                    if ( v37 )
                    {
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
                      v37 = 0;
                    }
                  }
                  v39 = 0;
                  v8 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v38)(v38, &IID_IASFUnknown, &v39);
                  if ( v8 >= 0 )
                  {
                    v8 = (*(__int64 (__fastcall **)(CASFUnknownContainer *, GUID *, __int64, __int64))(*(_QWORD *)this + 40LL))(
                           this,
                           &GUID_NULL,
                           v39,
                           0xFFFFFFFFLL);
                    if ( v39 )
                    {
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
                      v39 = 0;
                    }
                  }
                  if ( v38 )
                  {
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
                    v38 = 0;
                  }
                }
              }
              if ( v36 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
              if ( v8 >= 0 )
              {
LABEL_79:
                if ( !memcmp_0(&CLSID_ASFClockObjectv1, &Buf2, 0x10u) )
                {
                  v40 = 0;
                  v36 = 0;
                  if ( (**(int (__fastcall ***)(void *, GUID *, __int64 *))v35)(v35, &IID_IASFClockObjectv1, &v36) >= 0 )
                  {
                    (*(void (__fastcall **)(__int64, _QWORD, _QWORD, unsigned __int64 *))(*(_QWORD *)v36 + 96LL))(
                      v36,
                      0,
                      0,
                      &v40);
                    v26 = operator new[]((unsigned int)v40);
                    v27 = v26;
                    if ( v26 )
                    {
                      if ( (*(int (__fastcall **)(__int64, _QWORD, void *, char *))(*(_QWORD *)v36 + 96LL))(
                             v36,
                             (unsigned int)v40,
                             v26,
                             (char *)&v40 + 4) >= 0 )
                      {
                        v28 = *(_QWORD *)this;
                        LODWORD(v37) = 0;
                        v8 = (*(__int64 (__fastcall **)(CASFUnknownContainer *, struct IASFLibrary *, _QWORD, void *, __int64 *))(v28 + 80))(
                               this,
                               a2,
                               HIDWORD(v40),
                               v27,
                               &v37);
                      }
                      operator delete(v27);
                    }
                  }
                  if ( v36 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
                }
              }
            }
          }
        }
LABEL_62:
        if ( v35 )
        {
          (*(void (__fastcall **)(void *))(*(_QWORD *)v35 + 16LL))(v35);
          v35 = 0;
        }
        if ( v8 < 0 )
          goto LABEL_74;
        v29 = (unsigned int)v18 + (unsigned __int64)v9;
        if ( v29 + 24 > v6 )
        {
          if ( v29 > v6 )
            v9 += v34;
          else
            v9 += v18;
          goto LABEL_74;
        }
        v17 = v32;
        v9 += v18;
        v5 = a2;
        v16 += (unsigned int)v18;
      }
    }
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x18001e920  push    rbp
0x18001e922  push    rbx
0x18001e923  push    rsi
0x18001e924  push    rdi
0x18001e925  push    r12
0x18001e927  push    r13
0x18001e929  push    r14
0x18001e92b  push    r15
0x18001e92d  lea     rbp, [rsp-178h]
0x18001e935  sub     rsp, 278h
0x18001e93c  mov     rax, cs:__security_cookie
0x18001e943  xor     rax, rsp
0x18001e946  mov     [rbp+1B0h+var_50], rax
0x18001e94d  mov     rax, [rbp+1B0h+arg_20]
0x18001e954  mov     r10, rdx
0x18001e957  mov     [rsp+2B0h+var_268], r9
0x18001e95c  mov     r12d, r8d
0x18001e95f  mov     [rsp+2B0h+var_278], rdx
0x18001e964  mov     [rsp+2B0h+var_280], rcx
0x18001e969  mov     [rsp+2B0h+var_260], rax
0x18001e96e  test    rax, rax
0x18001e971  jz      loc_18001EF3C
0x18001e977  test    rdx, rdx
0x18001e97a  jz      loc_18001EF3C
0x18001e980  test    r8d, r8d
0x18001e983  jz      loc_18001EF32
0x18001e989  test    r9, r9
0x18001e98c  jz      loc_18001EF3C
0x18001e992  cmp     r12d, 18h
0x18001e996  jnb     short loc_18001E9A8
0x18001e998  mov     dword ptr [rax], 18h
0x18001e99e  mov     eax, 0C00D07D1h
0x18001e9a3  jmp     loc_18001EF41
0x18001e9a8  xor     ebx, ebx
0x18001e9aa  mov     [rsp+2B0h+var_270], r9
0x18001e9af  xor     edi, edi
0x18001e9b1  mov     [rbp+1B0h+var_58], ebx
0x18001e9b7  xor     r8d, r8d
0x18001e9ba  mov     [rbp+1B0h+var_60], rbx
0x18001e9c1  lea     rcx, [rbp+1B0h+var_1FC]
0x18001e9c5  mov     [rbp+1B0h+var_68], rbx
0x18001e9cc  mov     [rbp+1B0h+var_70], rbx
0x18001e9d3  xor     edx, edx
0x18001e9d5  mov     [rbp+1B0h+var_208], rcx
0x18001e9d9  mov     [rbp+1B0h+var_1FC], rbx
0x18001e9dd  mov     [rbp+1B0h+var_200], 8
0x18001e9e4  lea     rax, [rdx+rdx*2]
0x18001e9e8  inc     rdx
0x18001e9eb  lea     rcx, [rcx+rax*8]
0x18001e9ef  add     rcx, 8
0x18001e9f3  mov     [rcx+8], r8
0x18001e9f7  mov     r8, rcx
0x18001e9fa  mov     [rbp+1B0h+var_210], rcx
0x18001e9fe  cmp     rdx, 10h
0x18001ea02  jz      short loc_18001EA0A
0x18001ea04  mov     rcx, [rbp+1B0h+var_208]
0x18001ea08  jmp     short loc_18001E9E4
0x18001ea0a  xor     esi, esi
0x18001ea0c  mov     r13, r9
0x18001ea0f  xor     r14d, r14d
0x18001ea12  mov     [rsp+2B0h+var_270], r14
0x18001ea17  lea     eax, [rdi+18h]
0x18001ea1a  cmp     eax, r12d
0x18001ea1d  ja      loc_18001EF1E
0x18001ea23  xorps   xmm0, xmm0
0x18001ea26  movups  [rbp+1B0h+Buf2], xmm0
0x18001ea2a  movups  xmm1, xmmword ptr [r13+0]
0x18001ea2f  movdqu  [rbp+1B0h+Buf2], xmm1
0x18001ea34  mov     r15, [r13+10h]
0x18001ea38  test    r15, r15
0x18001ea3b  jnz     short loc_18001EA45
0x18001ea3d  mov     r15d, r12d
0x18001ea40  sub     r15d, edi
0x18001ea43  jmp     short loc_18001EA58
0x18001ea45  mov     rax, 100000000h
0x18001ea4f  cmp     r15, rax
0x18001ea52  jb      short loc_18001EA58
0x18001ea54  or      r15d, 0FFFFFFFFh
0x18001ea58  mov     rax, [r10]
0x18001ea5b  lea     r8, [rsp+2B0h+var_250]
0x18001ea60  lea     rdx, [rbp+1B0h+Buf2]
0x18001ea64  mov     [rsp+2B0h+var_258], 0
0x18001ea6c  mov     rcx, r10
0x18001ea6f  mov     [rsp+2B0h+var_250], 0
0x18001ea78  mov     rax, [rax+38h]
0x18001ea7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ea81  cmp     eax, 80040154h
0x18001ea86  jz      short loc_18001EA8F
0x18001ea88  cmp     eax, 0C00D07F0h
0x18001ea8d  jnz     short loc_18001EAB6
0x18001ea8f  mov     rcx, [rsp+2B0h+var_278]
0x18001ea94  lea     r8, [rsp+2B0h+var_250]
0x18001ea99  lea     rdx, CLSID_ASFGenericObject
0x18001eaa0  mov     rax, [rcx]
0x18001eaa3  mov     rax, [rax+38h]
0x18001eaa7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eaac  mov     ebx, eax
0x18001eaae  test    eax, eax
0x18001eab0  js      loc_18001EE9A
0x18001eab6  mov     rcx, [rsp+2B0h+var_280]
0x18001eabb  lea     rdx, GUID_NULL
0x18001eac2  mov     r8, [rsp+2B0h+var_250]
0x18001eac7  or      r9d, 0FFFFFFFFh
0x18001eacb  mov     rax, [rcx]
0x18001eace  mov     rax, [rax+28h]
0x18001ead2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ead7  mov     ebx, eax
0x18001ead9  test    eax, eax
0x18001eadb  js      loc_18001EE9A
0x18001eae1  mov     rcx, [rsp+2B0h+var_250]
0x18001eae6  lea     r9, [rsp+2B0h+var_258]
0x18001eaeb  mov     edx, r12d
0x18001eaee  mov     r8, r13
0x18001eaf1  sub     edx, edi
0x18001eaf3  mov     rax, [rcx]
0x18001eaf6  mov     rax, [rax+40h]
0x18001eafa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eaff  mov     ebx, eax
0x18001eb01  test    eax, eax
0x18001eb03  js      loc_18001EE9A
0x18001eb09  mov     r8d, 10h; Size
0x18001eb0f  lea     rdx, [rbp+1B0h+Buf2]; Buf2
0x18001eb13  lea     rcx, CLSID_ASFDataObjectv1; Buf1
0x18001eb1a  call    memcmp_0
0x18001eb1f  test    eax, eax
0x18001eb21  jz      short loc_18001EB34
0x18001eb23  cmp     [rsp+2B0h+var_258], r15d
0x18001eb28  jz      short loc_18001EB34
0x18001eb2a  mov     ebx, 0C00D07E2h
0x18001eb2f  jmp     loc_18001EE9A
0x18001eb34  mov     r8d, 10h; Size
0x18001eb3a  lea     rdx, [rbp+1B0h+Buf2]; Buf2
0x18001eb3e  lea     rcx, CLSID_ASFDigitalSignatureObject; Buf1
0x18001eb45  call    memcmp_0
0x18001eb4a  test    eax, eax
0x18001eb4c  jnz     loc_18001EEEA
0x18001eb52  test    esi, esi
0x18001eb54  jz      loc_18001EEE3
0x18001eb5a  test    r14, r14
0x18001eb5d  jz      loc_18001EEE3
0x18001eb63  mov     rcx, [rsp+2B0h+var_280]
0x18001eb68  mov     eax, r14d
0x18001eb6b  sub     eax, dword ptr [rsp+2B0h+var_268]
0x18001eb6f  add     eax, 1Eh
0x18001eb72  mov     [rcx+0F0h], eax
0x18001eb78  mov     eax, r13d
0x18001eb7b  sub     eax, r14d
0x18001eb7e  mov     [rcx+0F4h], eax
0x18001eb84  mov     rcx, [rbp+1B0h+var_68]
0x18001eb8b  test    rcx, rcx
0x18001eb8e  jz      short loc_18001EBE5
0x18001eb90  mov     rax, [rcx+8]
0x18001eb94  mov     r8, [rcx]
0x18001eb97  mov     [rbp+1B0h+var_68], rax
0x18001eb9e  test    rax, rax
0x18001eba1  jz      short loc_18001EBAD
0x18001eba3  mov     qword ptr [rax+10h], 0
0x18001ebab  jmp     short loc_18001EBB8
0x18001ebad  mov     [rbp+1B0h+var_60], 0
0x18001ebb8  mov     rax, [rbp+1B0h+var_210]
0x18001ebbc  mov     [rcx+8], rax
0x18001ebc0  dec     [rbp+1B0h+var_58]
0x18001ebc6  mov     [rbp+1B0h+var_210], rcx
0x18001ebca  test    r8, r8
0x18001ebcd  jz      short loc_18001EBE5
0x18001ebcf  mov     rax, [r8]
0x18001ebd2  mov     edx, 1
0x18001ebd7  mov     rcx, r8
0x18001ebda  mov     rax, [rax+28h]
0x18001ebde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ebe3  jmp     short loc_18001EB84
0x18001ebe5  xor     esi, esi
0x18001ebe7  mov     r14d, 10h
0x18001ebed  lea     rdx, [rbp+1B0h+Buf2]; Buf2
0x18001ebf1  mov     r8d, r14d; Size
0x18001ebf4  lea     rcx, CLSID_ASFPropertiesObjectv1; Buf1
0x18001ebfb  call    memcmp_0
0x18001ec00  test    eax, eax
0x18001ec02  jnz     short loc_18001EC20
0x18001ec04  test    esi, esi
0x18001ec06  jnz     loc_18001EEE3
0x18001ec0c  mov     r14d, [rsp+2B0h+var_258]
0x18001ec11  lea     esi, [rax+1]
0x18001ec14  add     r14, r13
0x18001ec17  mov     [rsp+2B0h+var_270], r14
0x18001ec1c  lea     r14d, [rax+10h]
0x18001ec20  mov     r8, r14; Size
0x18001ec23  lea     rdx, [rbp+1B0h+Buf2]; Buf2
0x18001ec27  lea     rcx, CLSID_ASFStreamPropertiesObjectExv1; Buf1
0x18001ec2e  call    memcmp_0
0x18001ec33  test    eax, eax
0x18001ec35  jnz     loc_18001EDB4
0x18001ec3b  mov     rcx, [rsp+2B0h+var_250]
0x18001ec40  lea     r8, [rsp+2B0h+var_248]
0x18001ec45  mov     [rsp+2B0h+var_248], 0
0x18001ec4e  lea     rdx, IID_IASFStreamPropertiesObjectExv1
0x18001ec55  mov     rax, [rcx]
0x18001ec58  mov     rax, [rax]
0x18001ec5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ec60  mov     [rsp+2B0h+var_238], 0
0x18001ec69  test    eax, eax
0x18001ec6b  js      loc_18001ED96
0x18001ec71  mov     rcx, [rsp+2B0h+var_248]
0x18001ec76  lea     rdx, [rsp+2B0h+var_238]
0x18001ec7b  mov     rax, [rcx]
0x18001ec7e  mov     rax, [rax+0B8h]
0x18001ec85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ec8a  mov     rcx, [rsp+2B0h+var_238]
0x18001ec8f  test    rcx, rcx
0x18001ec92  jz      loc_18001ED96
0x18001ec98  mov     [rsp+2B0h+var_240], 0
0x18001eca1  lea     r8, [rsp+2B0h+var_240]
0x18001eca6  mov     rax, [rcx]
0x18001eca9  lea     rdx, IID_IASFStreamPropertiesObject
0x18001ecb0  mov     rax, [rax]
0x18001ecb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ecb8  xor     ebx, ebx
0x18001ecba  test    eax, eax
0x18001ecbc  js      short loc_18001ED13
0x18001ecbe  mov     rcx, [rsp+2B0h+var_240]
0x18001ecc3  lea     rdx, [rbp+1B0h+var_228]
0x18001ecc7  mov     dword ptr [rbp+1B0h+var_228], ebx
0x18001ecca  mov     rax, [rcx]
0x18001eccd  mov     rax, [rax+0F0h]
0x18001ecd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ecd9  test    eax, eax
0x18001ecdb  js      short loc_18001ECF8
0x18001ecdd  mov     rcx, [rsp+2B0h+var_240]
0x18001ece2  mov     edx, dword ptr [rbp+1B0h+var_228]
0x18001ece5  bts     edx, 1Fh
0x18001ece9  mov     rax, [rcx]
0x18001ecec  mov     rax, [rax+0F8h]
0x18001ecf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ecf8  mov     rcx, [rsp+2B0h+var_240]
0x18001ecfd  test    rcx, rcx
0x18001ed00  jz      short loc_18001ED13
0x18001ed02  mov     rax, [rcx]
0x18001ed05  mov     rax, [rax+10h]
0x18001ed09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ed0e  mov     [rsp+2B0h+var_240], rbx
0x18001ed13  mov     rcx, [rsp+2B0h+var_238]
0x18001ed18  lea     r8, [rbp+1B0h+var_230]
0x18001ed1c  mov     [rbp+1B0h+var_230], rbx
0x18001ed20  lea     rdx, IID_IASFUnknown
0x18001ed27  mov     rax, [rcx]
0x18001ed2a  mov     rax, [rax]
0x18001ed2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ed32  mov     ebx, eax
0x18001ed34  test    eax, eax
0x18001ed36  js      short loc_18001ED77
0x18001ed38  mov     rcx, [rsp+2B0h+var_280]
0x18001ed3d  lea     rdx, GUID_NULL
0x18001ed44  mov     r8, [rbp+1B0h+var_230]
0x18001ed48  or      r9d, 0FFFFFFFFh
0x18001ed4c  mov     rax, [rcx]
0x18001ed4f  mov     rax, [rax+28h]
0x18001ed53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ed58  mov     rcx, [rbp+1B0h+var_230]
0x18001ed5c  mov     ebx, eax
0x18001ed5e  test    rcx, rcx
0x18001ed61  jz      short loc_18001ED77
0x18001ed63  mov     rax, [rcx]
0x18001ed66  mov     rax, [rax+10h]
0x18001ed6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ed6f  mov     [rbp+1B0h+var_230], 0
0x18001ed77  mov     rcx, [rsp+2B0h+var_238]
0x18001ed7c  test    rcx, rcx
0x18001ed7f  jz      short loc_18001ED96
0x18001ed81  mov     rax, [rcx]
0x18001ed84  mov     rax, [rax+10h]
0x18001ed88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ed8d  mov     [rsp+2B0h+var_238], 0
0x18001ed96  mov     rcx, [rsp+2B0h+var_248]
0x18001ed9b  test    rcx, rcx
0x18001ed9e  jz      short loc_18001EDAC
0x18001eda0  mov     rax, [rcx]
0x18001eda3  mov     rax, [rax+10h]
0x18001eda7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001edac  test    ebx, ebx
0x18001edae  js      loc_18001EE9A
0x18001edb4  mov     r8, r14; Size
0x18001edb7  lea     rdx, [rbp+1B0h+Buf2]; Buf2
0x18001edbb  lea     rcx, CLSID_ASFClockObjectv1; Buf1
0x18001edc2  call    memcmp_0
0x18001edc7  test    eax, eax
0x18001edc9  jnz     loc_18001EE9A
0x18001edcf  mov     rcx, [rsp+2B0h+var_250]
0x18001edd4  lea     r8, [rsp+2B0h+var_248]
0x18001edd9  mov     dword ptr [rbp+1B0h+var_228], eax
0x18001eddc  lea     rdx, IID_IASFClockObjectv1
0x18001ede3  mov     dword ptr [rbp+1B0h+var_228+4], eax
0x18001ede6  mov     [rsp+2B0h+var_248], 0
0x18001edef  mov     rax, [rcx]
0x18001edf2  mov     rax, [rax]
0x18001edf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001edfa  test    eax, eax
0x18001edfc  js      loc_18001EE84
0x18001ee02  mov     rcx, [rsp+2B0h+var_248]
0x18001ee07  lea     r9, [rbp+1B0h+var_228]
0x18001ee0b  xor     r8d, r8d
  ... truncated ...
```
