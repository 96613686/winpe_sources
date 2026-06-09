# CBlbRestoreComponentAsync::ReorderComponentsByApp(ulong,_BLB_COMPONENT *,_BLB_COMPONENT * *)

- ea: `0x14006dd70`
- end: `0x14006e398`
- name: `?ReorderComponentsByApp@CBlbRestoreComponentAsync@@AEAAJKPEAU_BLB_COMPONENT@@PEAPEAU2@@Z`
- size: `1576`
- prototype: `int(CBlbRestoreComponentAsync *__hidden this, unsigned int, struct _BLB_COMPONENT *, struct _BLB_COMPONENT **)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x14006c8b0`

## callees

- `0x140006ca8`
- `0x14000bb24`
- `0x14000bb4c`
- `0x14000cbcc`
- `0x14006dd70`
- `0x1400889f0`
- `0x140088aa0`
- `0x140137010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x14006e1a9`
- `msvcrt!_wcsicmp` at `0x14006e1ca`
- `msvcrt!_wcsicmp` at `0x14006e1a9`
- `msvcrt!_wcsicmp` at `0x14006e1ca`
- `ole32!CoTaskMemFree` at `0x14006e208`
- `ole32!CoTaskMemFree` at `0x14006e2af`
- `ole32!CoTaskMemFree` at `0x14006e2c7`
- `ole32!CoTaskMemFree` at `0x14006e2e3`
- `ole32!CoTaskMemFree` at `0x14006e2f1`
- `ole32!CoTaskMemFree` at `0x14006e300`
- `ole32!CoTaskMemFree` at `0x14006e208`
- `ole32!CoTaskMemFree` at `0x14006e2af`
- `ole32!CoTaskMemFree` at `0x14006e2c7`
- `ole32!CoTaskMemFree` at `0x14006e2e3`
- `ole32!CoTaskMemFree` at `0x14006e2f1`
- `ole32!CoTaskMemFree` at `0x14006e300`
- `ole32!CoCreateInstance` at `0x14006df8d`
- `ole32!CoCreateInstance` at `0x14006df8d`

## string_xrefs

- `0x14006ddde`: `base\stor\blb\engine\service\component.cpp`
- `0x14006ddfb`: `base\stor\blb\engine\service\component.cpp`
- `0x14006e190`: `base\stor\blb\engine\service\component.cpp`
- `0x14006ddd2`: `cComponent != 0`
- `0x14006ddef`: `rgComponent != NULL`
- `0x14006e184`: `(rgComponentNameOrdered[i] != NULL) && (rgComponent[j].m_wszName != NULL)`

## pseudocode

```c
__int64 __fastcall CBlbRestoreComponentAsync::ReorderComponentsByApp(
        CBlbRestoreComponentAsync *this,
        unsigned int a2,
        const unsigned __int16 **a3,
        struct _BLB_COMPONENT **a4)
{
  void *v7; // r13
  unsigned __int16 **v8; // r14
  HRESULT v9; // ebx
  int v10; // eax
  __int64 v11; // r12
  __int128 v12; // xmm0
  __int64 v13; // rsi
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  _QWORD *v16; // rcx
  __int64 v17; // rdx
  int v18; // eax
  __int64 v19; // r12
  unsigned __int16 **v20; // r13
  __int64 v21; // rsi
  unsigned int v22; // eax
  __int64 i; // r13
  __int64 v24; // r12
  __int64 v25; // rsi
  unsigned __int16 **v26; // rcx
  const wchar_t *v27; // rcx
  const unsigned __int16 **v28; // rcx
  signed __int64 v29; // rax
  unsigned __int16 **v30; // rbx
  unsigned __int16 *v31; // rcx
  unsigned int v32; // r12d
  __int64 v33; // rsi
  unsigned __int16 *v34; // rcx
  unsigned __int16 *v35; // rcx
  unsigned __int16 **v37; // [rsp+50h] [rbp-19h] BYREF
  LPVOID ppv; // [rsp+58h] [rbp-11h] BYREF
  unsigned __int16 **v39; // [rsp+60h] [rbp-9h] BYREF
  unsigned __int16 **v40; // [rsp+68h] [rbp-1h] BYREF
  unsigned __int16 **v41; // [rsp+70h] [rbp+7h] BYREF
  void *v42; // [rsp+78h] [rbp+Fh] BYREF
  void *v43; // [rsp+D0h] [rbp+67h] BYREF
  unsigned int v44; // [rsp+D8h] [rbp+6Fh] BYREF
  LPVOID pv; // [rsp+E0h] [rbp+77h] BYREF
  struct _BLB_COMPONENT **v46; // [rsp+E8h] [rbp+7Fh]

  v46 = a4;
  v43 = this;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 120, &WPP_40d550336cac3d55f04e301f30980d6d_Traceguids);
  }
  if ( !a2 )
    BlbAssert("base\\stor\\blb\\engine\\service\\component.cpp", 0xC67u, "cComponent != 0");
  if ( !a3 )
    BlbAssert("base\\stor\\blb\\engine\\service\\component.cpp", 0xC68u, "rgComponent != NULL");
  v7 = 0;
  *a4 = 0;
  v8 = 0;
  v39 = 0;
  v40 = 0;
  v37 = 0;
  v41 = 0;
  v43 = 0;
  pv = 0;
  ppv = 0;
  v42 = 0;
  v9 = BlbutilMemalloc((void **)&v39, a2, 8u);
  if ( v9 < 0 )
    goto LABEL_76;
  v9 = BlbutilMemalloc((void **)&v40, a2, 8u);
  if ( v9 < 0 )
    goto LABEL_76;
  v10 = BlbutilMemalloc(&v43, a2, 0x10u);
  v7 = v43;
  v9 = v10;
  if ( v10 < 0 )
    goto LABEL_76;
  v11 = 0;
  while ( 1 )
  {
    if ( (unsigned int)v11 >= a2 )
    {
      v9 = CoCreateInstance(&CLSID_BlbsrvRecoverySupport, 0, 1u, &IID_IBlbsrvRecoverySupport, &ppv);
      if ( v9 >= 0 )
      {
        v9 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, void *, unsigned __int16 **, unsigned __int16 **, LPVOID *, unsigned __int16 ***, unsigned __int16 ***))(*(_QWORD *)ppv + 24LL))(
               ppv,
               a2,
               v7,
               v39,
               v40,
               &pv,
               &v37,
               &v41);
        if ( v9 >= 0 )
        {
          v18 = BlbutilMemalloc(&v42, a2, 0x48u);
          v8 = (unsigned __int16 **)v42;
          v9 = v18;
          if ( v18 >= 0 )
          {
            v19 = 0;
            while ( (unsigned int)v19 < a2 )
            {
              v20 = &v8[9 * v19];
              v9 = BlbutilDuplicateString(v37[v19], v20 + 1, 0);
              if ( v9 < 0 )
              {
                v14 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  v15 = 125;
                  goto LABEL_25;
                }
                goto LABEL_75;
              }
              v9 = BlbutilDuplicateString(v41[v19], &v8[9 * v19], 0);
              if ( v9 < 0 )
              {
                v14 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  v15 = 126;
                  goto LABEL_25;
                }
                goto LABEL_75;
              }
              v21 = 2LL * (unsigned int)v19;
              v19 = (unsigned int)(v19 + 1);
              *((_OWORD *)v20 + 1) = *(_OWORD *)((char *)pv + 8 * v21);
            }
            v22 = 0;
LABEL_52:
            v44 = v22;
            if ( v22 >= a2 )
            {
              *v46 = (struct _BLB_COMPONENT *)v8;
              v8 = 0;
            }
            else
            {
              for ( i = 0; ; i = (unsigned int)(i + 1) )
              {
                if ( (unsigned int)i >= a2 )
                {
                  ++v22;
                  goto LABEL_52;
                }
                v24 = v22;
                v25 = 9 * i;
                v26 = v37;
                if ( !v37[v22] || !a3[v25 + 1] )
                {
                  BlbAssert(
                    "base\\stor\\blb\\engine\\service\\component.cpp",
                    0xCCCu,
                    "(rgComponentNameOrdered[i] != NULL) && (rgComponent[j].m_wszName != NULL)");
                  v26 = v37;
                }
                if ( !_wcsicmp(v26[v24], a3[v25 + 1]) && ((v27 = v41[v24]) == 0 && !a3[v25] || !_wcsicmp(v27, a3[v25])) )
                {
                  v28 = (const unsigned __int16 **)((char *)pv + 16 * v24);
                  v29 = (char *)*v28 - (char *)a3[v25 + 2];
                  if ( *v28 == a3[v25 + 2] )
                    v29 = (char *)v28[1] - (char *)a3[v25 + 3];
                  if ( !v29 )
                  {
                    v30 = &v8[9 * v24];
                    v31 = v30[6];
                    if ( v31 )
                    {
                      CoTaskMemFree(v31);
                      v30[6] = 0;
                    }
                    v9 = BlbutilDuplicateString(a3[9 * v24 + 6], v30 + 6, 0);
                    if ( v9 < 0 )
                      break;
                  }
                }
                v22 = v44;
              }
              v14 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v15 = 127;
                goto LABEL_25;
              }
            }
            goto LABEL_75;
          }
          goto LABEL_76;
        }
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_75;
        }
        v17 = 124;
      }
      else
      {
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_75;
        }
        v17 = 123;
      }
      WPP_SF_d(v16[2], v17, &WPP_40d550336cac3d55f04e301f30980d6d_Traceguids);
      goto LABEL_76;
    }
    v9 = BlbutilDuplicateString(a3[9 * v11 + 1], &v39[v11], 0);
    if ( v9 < 0 )
      break;
    v9 = BlbutilDuplicateString(a3[9 * v11], &v40[v11], 0);
    if ( v9 < 0 )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v15 = 122;
        goto LABEL_25;
      }
      goto LABEL_75;
    }
    v12 = *(_OWORD *)&a3[9 * v11 + 2];
    v7 = v43;
    v13 = 2LL * (unsigned int)v11;
    v11 = (unsigned int)(v11 + 1);
    *(_OWORD *)((char *)v43 + 8 * v13) = v12;
  }
  v14 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v15 = 121;
LABEL_25:
    WPP_SF_d(v14[2], v15, &WPP_40d550336cac3d55f04e301f30980d6d_Traceguids);
  }
LABEL_75:
  v7 = v43;
LABEL_76:
  if ( ppv )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    ppv = 0;
  }
  if ( v8 )
  {
    v32 = 0;
    if ( a2 )
    {
      v33 = 0;
      do
      {
        v34 = v8[9 * v33 + 1];
        if ( v34 )
        {
          CoTaskMemFree(v34);
          v8[9 * v33 + 1] = 0;
        }
        v35 = v8[9 * v33];
        if ( v35 )
        {
          CoTaskMemFree(v35);
          v8[9 * v33] = 0;
        }
        ++v32;
        ++v33;
      }
      while ( v32 < a2 );
    }
    CoTaskMemFree(v8);
  }
  if ( v7 )
    CoTaskMemFree(v7);
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
  v44 = a2;
  BlbutilFreeStrings(&v39, &v44);
  v44 = a2;
  BlbutilFreeStrings(&v37, &v44);
  v44 = a2;
  BlbutilFreeStrings(&v40, &v44);
  v44 = a2;
  BlbutilFreeStrings(&v41, &v44);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 128, &WPP_40d550336cac3d55f04e301f30980d6d_Traceguids);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x14006dd70  mov     [rsp-8+arg_18], r9
0x14006dd75  mov     [rsp-8+arg_0], rcx
0x14006dd7a  push    rbp
0x14006dd7b  push    rbx
0x14006dd7c  push    rsi
0x14006dd7d  push    rdi
0x14006dd7e  push    r12
0x14006dd80  push    r13
0x14006dd82  push    r14
0x14006dd84  push    r15
0x14006dd86  lea     rbp, [rsp-1Fh]
0x14006dd8b  sub     rsp, 88h
0x14006dd92  mov     rsi, r9
0x14006dd95  mov     r15, r8
0x14006dd98  mov     edi, edx
0x14006dd9a  mov     rcx, cs:WPP_GLOBAL_Control
0x14006dda1  lea     rax, WPP_GLOBAL_Control
0x14006dda8  cmp     rcx, rax
0x14006ddab  jz      short loc_14006DDCE
0x14006ddad  test    byte ptr [rcx+1Ch], 1
0x14006ddb1  jz      short loc_14006DDCE
0x14006ddb3  cmp     byte ptr [rcx+19h], 4
0x14006ddb7  jb      short loc_14006DDCE
0x14006ddb9  mov     rcx, [rcx+10h]
0x14006ddbd  lea     r8, WPP_40d550336cac3d55f04e301f30980d6d_Traceguids
0x14006ddc4  mov     edx, 78h ; 'x'
0x14006ddc9  call    WPP_SF_
0x14006ddce  test    edi, edi
0x14006ddd0  jnz     short loc_14006DDEA
0x14006ddd2  lea     r8, aCcomponent0; "cComponent != 0"
0x14006ddd9  mov     edx, 0C67h; unsigned int
0x14006ddde  lea     rcx, aBaseStorBlbEng_18; "base\\stor\\blb\\engine\\service\\compo"...
0x14006dde5  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x14006ddea  test    r15, r15
0x14006dded  jnz     short loc_14006DE07
0x14006ddef  lea     r8, aRgcomponentNul; "rgComponent != NULL"
0x14006ddf6  mov     edx, 0C68h; unsigned int
0x14006ddfb  lea     rcx, aBaseStorBlbEng_18; "base\\stor\\blb\\engine\\service\\compo"...
0x14006de02  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x14006de07  xor     r13d, r13d
0x14006de0a  mov     qword ptr [rsi], 0
0x14006de11  xor     r14d, r14d
0x14006de14  mov     [rbp+57h+var_60], 0
0x14006de1c  mov     edx, edi; unsigned int
0x14006de1e  mov     [rbp+57h+var_58], 0
0x14006de26  lea     rcx, [rbp+57h+var_60]; void **
0x14006de2a  mov     [rbp+57h+var_70], 0
0x14006de32  lea     esi, [r13+8]
0x14006de36  mov     [rbp+57h+var_50], 0
0x14006de3e  mov     r8d, esi; unsigned int
0x14006de41  mov     [rbp+57h+arg_0], r13
0x14006de45  mov     [rbp+57h+pv], r13
0x14006de49  mov     [rbp+57h+var_68], r13
0x14006de4d  mov     [rbp+57h+var_48], r14
0x14006de51  call    ?BlbutilMemalloc@@YAJPEAPEAXKK@Z; BlbutilMemalloc(void * *,ulong,ulong)
0x14006de56  mov     ebx, eax
0x14006de58  test    eax, eax
0x14006de5a  js      loc_14006E276
0x14006de60  mov     r8d, esi; unsigned int
0x14006de63  lea     rcx, [rbp+57h+var_58]; void **
0x14006de67  mov     edx, edi; unsigned int
0x14006de69  call    ?BlbutilMemalloc@@YAJPEAPEAXKK@Z; BlbutilMemalloc(void * *,ulong,ulong)
0x14006de6e  mov     ebx, eax
0x14006de70  test    eax, eax
0x14006de72  js      loc_14006E276
0x14006de78  lea     r8d, [r13+10h]; unsigned int
0x14006de7c  mov     edx, edi; unsigned int
0x14006de7e  lea     rcx, [rbp+57h+arg_0]; void **
0x14006de82  call    ?BlbutilMemalloc@@YAJPEAPEAXKK@Z; BlbutilMemalloc(void * *,ulong,ulong)
0x14006de87  mov     r13, [rbp+57h+arg_0]
0x14006de8b  mov     ebx, eax
0x14006de8d  test    eax, eax
0x14006de8f  js      loc_14006E276
0x14006de95  xor     r12d, r12d
0x14006de98  cmp     r12d, edi
0x14006de9b  jnb     loc_14006DF70
0x14006dea1  mov     rax, [rbp+57h+var_60]
0x14006dea5  lea     r13, [r12+r12*8]
0x14006dea9  mov     rcx, [r15+r13*8+8]; unsigned __int16 *
0x14006deae  xor     r8d, r8d; unsigned __int64
0x14006deb1  mov     esi, r12d
0x14006deb4  lea     rdx, [rax+r12*8]; unsigned __int16 **
0x14006deb8  call    ?BlbutilDuplicateString@@YAJPEBGPEAPEAG_K@Z; BlbutilDuplicateString(ushort const *,ushort * *,unsigned __int64)
0x14006debd  mov     ebx, eax
0x14006debf  test    eax, eax
0x14006dec1  js      short loc_14006DF28
0x14006dec3  mov     rax, [rbp+57h+var_58]
0x14006dec7  xor     r8d, r8d; unsigned __int64
0x14006deca  mov     rcx, [r15+r13*8]; unsigned __int16 *
0x14006dece  lea     rdx, [rax+r12*8]; unsigned __int16 **
0x14006ded2  call    ?BlbutilDuplicateString@@YAJPEBGPEAPEAG_K@Z; BlbutilDuplicateString(ushort const *,ushort * *,unsigned __int64)
0x14006ded7  mov     ebx, eax
0x14006ded9  test    eax, eax
0x14006dedb  js      short loc_14006DEF6
0x14006dedd  movups  xmm0, xmmword ptr [r15+r13*8+10h]
0x14006dee3  mov     r13, [rbp+57h+arg_0]
0x14006dee7  add     rsi, rsi
0x14006deea  inc     r12d
0x14006deed  movdqu  xmmword ptr [r13+rsi*8+0], xmm0
0x14006def4  jmp     short loc_14006DE98
0x14006def6  mov     rcx, cs:WPP_GLOBAL_Control
0x14006defd  lea     rax, WPP_GLOBAL_Control
0x14006df04  cmp     rcx, rax
0x14006df07  jz      loc_14006E272
0x14006df0d  test    byte ptr [rcx+1Ch], 1
0x14006df11  jz      loc_14006E272
0x14006df17  cmp     byte ptr [rcx+19h], 2
0x14006df1b  jb      loc_14006E272
0x14006df21  mov     edx, 7Ah ; 'z'
0x14006df26  jmp     short loc_14006DF58
0x14006df28  mov     rcx, cs:WPP_GLOBAL_Control
0x14006df2f  lea     rax, WPP_GLOBAL_Control
0x14006df36  cmp     rcx, rax
0x14006df39  jz      loc_14006E272
0x14006df3f  test    byte ptr [rcx+1Ch], 1
0x14006df43  jz      loc_14006E272
0x14006df49  cmp     byte ptr [rcx+19h], 2
0x14006df4d  jb      loc_14006E272
0x14006df53  mov     edx, 79h ; 'y'
0x14006df58  mov     rcx, [rcx+10h]
0x14006df5c  lea     r8, WPP_40d550336cac3d55f04e301f30980d6d_Traceguids
0x14006df63  mov     r9d, ebx
0x14006df66  call    WPP_SF_d
0x14006df6b  jmp     loc_14006E272
0x14006df70  xor     edx, edx; pUnkOuter
0x14006df72  lea     rax, [rbp+57h+var_68]
0x14006df76  lea     r9, IID_IBlbsrvRecoverySupport; riid
0x14006df7d  mov     [rsp+0C0h+ppv], rax; ppv
0x14006df82  lea     rcx, CLSID_BlbsrvRecoverySupport; rclsid
0x14006df89  lea     r8d, [rdx+1]; dwClsContext
0x14006df8d  call    cs:__imp_CoCreateInstance
0x14006df93  mov     ebx, eax
0x14006df95  test    eax, eax
0x14006df97  jns     short loc_14006DFE1
0x14006df99  mov     rcx, cs:WPP_GLOBAL_Control
0x14006dfa0  lea     rax, WPP_GLOBAL_Control
0x14006dfa7  cmp     rcx, rax
0x14006dfaa  jz      loc_14006E272
0x14006dfb0  test    byte ptr [rcx+1Ch], 1
0x14006dfb4  jz      loc_14006E272
0x14006dfba  cmp     byte ptr [rcx+19h], 2
0x14006dfbe  jb      loc_14006E272
0x14006dfc4  mov     edx, 7Bh ; '{'
0x14006dfc9  mov     rcx, [rcx+10h]
0x14006dfcd  lea     r8, WPP_40d550336cac3d55f04e301f30980d6d_Traceguids
0x14006dfd4  mov     r9d, ebx
0x14006dfd7  call    WPP_SF_d
0x14006dfdc  jmp     loc_14006E276
0x14006dfe1  mov     rcx, [rbp+57h+var_68]
0x14006dfe5  lea     rdx, [rbp+57h+var_50]
0x14006dfe9  mov     r9, [rbp+57h+var_60]
0x14006dfed  mov     r8, r13
0x14006dff0  mov     [rsp+0C0h+var_88], rdx
0x14006dff5  lea     rdx, [rbp+57h+var_70]
0x14006dff9  mov     [rsp+0C0h+var_90], rdx
0x14006dffe  lea     rdx, [rbp+57h+pv]
0x14006e002  mov     rax, [rcx]
0x14006e005  mov     [rsp+0C0h+var_98], rdx
0x14006e00a  mov     rdx, [rbp+57h+var_58]
0x14006e00e  mov     [rsp+0C0h+ppv], rdx
0x14006e013  mov     edx, edi
0x14006e015  mov     rax, [rax+18h]
0x14006e019  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006e01e  mov     ebx, eax
0x14006e020  test    eax, eax
0x14006e022  jns     short loc_14006E059
0x14006e024  mov     rcx, cs:WPP_GLOBAL_Control
0x14006e02b  lea     rax, WPP_GLOBAL_Control
0x14006e032  cmp     rcx, rax
0x14006e035  jz      loc_14006E272
0x14006e03b  test    byte ptr [rcx+1Ch], 1
0x14006e03f  jz      loc_14006E272
0x14006e045  cmp     byte ptr [rcx+19h], 2
0x14006e049  jb      loc_14006E272
0x14006e04f  mov     edx, 7Ch ; '|'
0x14006e054  jmp     loc_14006DFC9
0x14006e059  mov     r8d, 48h ; 'H'; unsigned int
0x14006e05f  lea     rcx, [rbp+57h+var_48]; void **
0x14006e063  mov     edx, edi; unsigned int
0x14006e065  call    ?BlbutilMemalloc@@YAJPEAPEAXKK@Z; BlbutilMemalloc(void * *,ulong,ulong)
0x14006e06a  mov     r14, [rbp+57h+var_48]
0x14006e06e  mov     ebx, eax
0x14006e070  test    eax, eax
0x14006e072  js      loc_14006E276
0x14006e078  xor     r12d, r12d
0x14006e07b  cmp     r12d, edi
0x14006e07e  jnb     loc_14006E142
0x14006e084  mov     rcx, [rbp+57h+var_70]
0x14006e088  lea     rax, [r12+r12*8]
0x14006e08c  lea     r13, [r14+rax*8]
0x14006e090  mov     esi, r12d
0x14006e093  lea     rdx, [r13+8]; unsigned __int16 **
0x14006e097  xor     r8d, r8d; unsigned __int64
0x14006e09a  mov     rcx, [rcx+r12*8]; unsigned __int16 *
0x14006e09e  call    ?BlbutilDuplicateString@@YAJPEBGPEAPEAG_K@Z; BlbutilDuplicateString(ushort const *,ushort * *,unsigned __int64)
0x14006e0a3  mov     ebx, eax
0x14006e0a5  test    eax, eax
0x14006e0a7  js      short loc_14006E10D
0x14006e0a9  mov     rcx, [rbp+57h+var_50]
0x14006e0ad  xor     r8d, r8d; unsigned __int64
0x14006e0b0  mov     rdx, r13; unsigned __int16 **
0x14006e0b3  mov     rcx, [rcx+r12*8]; unsigned __int16 *
0x14006e0b7  call    ?BlbutilDuplicateString@@YAJPEBGPEAPEAG_K@Z; BlbutilDuplicateString(ushort const *,ushort * *,unsigned __int64)
0x14006e0bc  mov     ebx, eax
0x14006e0be  test    eax, eax
0x14006e0c0  js      short loc_14006E0D8
0x14006e0c2  mov     rax, [rbp+57h+pv]
0x14006e0c6  add     rsi, rsi
0x14006e0c9  inc     r12d
0x14006e0cc  movups  xmm0, xmmword ptr [rax+rsi*8]
0x14006e0d0  movdqu  xmmword ptr [r13+10h], xmm0
0x14006e0d6  jmp     short loc_14006E07B
0x14006e0d8  mov     rcx, cs:WPP_GLOBAL_Control
0x14006e0df  lea     rax, WPP_GLOBAL_Control
0x14006e0e6  cmp     rcx, rax
0x14006e0e9  jz      loc_14006E272
0x14006e0ef  test    byte ptr [rcx+1Ch], 1
0x14006e0f3  jz      loc_14006E272
0x14006e0f9  cmp     byte ptr [rcx+19h], 2
0x14006e0fd  jb      loc_14006E272
0x14006e103  mov     edx, 7Eh ; '~'
0x14006e108  jmp     loc_14006DF58
0x14006e10d  mov     rcx, cs:WPP_GLOBAL_Control
0x14006e114  lea     rax, WPP_GLOBAL_Control
0x14006e11b  cmp     rcx, rax
0x14006e11e  jz      loc_14006E272
0x14006e124  test    byte ptr [rcx+1Ch], 1
0x14006e128  jz      loc_14006E272
0x14006e12e  cmp     byte ptr [rcx+19h], 2
0x14006e132  jb      loc_14006E272
0x14006e138  mov     edx, 7Dh ; '}'
0x14006e13d  jmp     loc_14006DF58
0x14006e142  xor     eax, eax
0x14006e144  mov     [rbp+57h+arg_8], eax
0x14006e147  cmp     eax, edi
0x14006e149  jnb     loc_14006E268
0x14006e14f  xor     r13d, r13d
0x14006e152  cmp     r13d, edi
0x14006e155  jnb     loc_14006E238
0x14006e15b  lea     rcx, ds:0[r13*8]
0x14006e163  mov     r12d, eax
0x14006e166  add     rcx, r13
0x14006e169  lea     rsi, ds:0[rcx*8]
0x14006e171  mov     rcx, [rbp+57h+var_70]
0x14006e175  cmp     qword ptr [rcx+r12*8], 0
0x14006e17a  jz      short loc_14006E184
0x14006e17c  cmp     qword ptr [r15+rsi+8], 0
0x14006e182  jnz     short loc_14006E1A0
0x14006e184  lea     r8, aRgcomponentnam; "(rgComponentNameOrdered[i] != NULL) && "...
0x14006e18b  mov     edx, 0CCCh; unsigned int
0x14006e190  lea     rcx, aBaseStorBlbEng_18; "base\\stor\\blb\\engine\\service\\compo"...
0x14006e197  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x14006e19c  mov     rcx, [rbp+57h+var_70]
0x14006e1a0  mov     rdx, [rsi+r15+8]; String2
0x14006e1a5  mov     rcx, [rcx+r12*8]; String1
0x14006e1a9  call    cs:__imp__wcsicmp
0x14006e1af  test    eax, eax
0x14006e1b1  jnz     short loc_14006E22D
0x14006e1b3  mov     rax, [rbp+57h+var_50]
0x14006e1b7  mov     rcx, [rax+r12*8]; String1
0x14006e1bb  test    rcx, rcx
0x14006e1be  jnz     short loc_14006E1C6
0x14006e1c0  cmp     [rsi+r15], rcx
0x14006e1c4  jz      short loc_14006E1D4
0x14006e1c6  mov     rdx, [rsi+r15]; String2
0x14006e1ca  call    cs:__imp__wcsicmp
0x14006e1d0  test    eax, eax
0x14006e1d2  jnz     short loc_14006E22D
0x14006e1d4  mov     rcx, r12
0x14006e1d7  shl     rcx, 4
0x14006e1db  add     rcx, [rbp+57h+pv]
0x14006e1df  mov     rax, [rcx]
0x14006e1e2  sub     rax, [rsi+r15+10h]
0x14006e1e7  jnz     short loc_14006E1F2
0x14006e1e9  mov     rax, [rcx+8]
0x14006e1ed  sub     rax, [rsi+r15+18h]
0x14006e1f2  test    rax, rax
0x14006e1f5  jnz     short loc_14006E22D
0x14006e1f7  lea     rsi, [r12+r12*8]
0x14006e1fb  lea     rbx, [r14+rsi*8]
0x14006e1ff  mov     rcx, [rbx+30h]; pv
0x14006e203  test    rcx, rcx
0x14006e206  jz      short loc_14006E216
0x14006e208  call    cs:__imp_CoTaskMemFree
0x14006e20e  mov     qword ptr [rbx+30h], 0
0x14006e216  mov     rcx, [r15+rsi*8+30h]; unsigned __int16 *
0x14006e21b  lea     rdx, [rbx+30h]; unsigned __int16 **
0x14006e21f  xor     r8d, r8d; unsigned __int64
0x14006e222  call    ?BlbutilDuplicateString@@YAJPEBGPEAPEAG_K@Z; BlbutilDuplicateString(ushort const *,ushort * *,unsigned __int64)
0x14006e227  mov     ebx, eax
0x14006e229  test    eax, eax
0x14006e22b  js      short loc_14006E23F
0x14006e22d  mov     eax, [rbp+57h+arg_8]
0x14006e230  inc     r13d
0x14006e233  jmp     loc_14006E152
0x14006e238  inc     eax
0x14006e23a  jmp     loc_14006E144
0x14006e23f  mov     rcx, cs:WPP_GLOBAL_Control
0x14006e246  lea     rax, WPP_GLOBAL_Control
0x14006e24d  cmp     rcx, rax
  ... truncated ...
```
