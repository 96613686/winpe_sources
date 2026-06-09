# BlbSetDiffAreaSpace(ushort *,__int64,uchar)

- ea: `0x140118f04`
- end: `0x1401193e2`
- name: `?BlbSetDiffAreaSpace@@YAJPEAG_JE@Z`
- size: `1246`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, unsigned __int8)`
- caller_count: `3`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1400346f8`
- `0x140036db4`
- `0x140117d50`

## callees

- `0x140006ca8`
- `0x14000bb24`
- `0x14000bb4c`
- `0x140014260`
- `0x1400142d8`
- `0x14003c69c`
- `0x14003cdfc`
- `0x1400889f0`
- `0x140118f04`
- `0x140137010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x140119151`
- `ole32!CoTaskMemFree` at `0x1401191e0`
- `ole32!CoTaskMemFree` at `0x1401191ea`
- `ole32!CoTaskMemFree` at `0x14011923d`
- `ole32!CoTaskMemFree` at `0x140119247`
- `ole32!CoTaskMemFree` at `0x1401192f5`
- `ole32!CoTaskMemFree` at `0x140119151`
- `ole32!CoTaskMemFree` at `0x1401191e0`
- `ole32!CoTaskMemFree` at `0x1401191ea`
- `ole32!CoTaskMemFree` at `0x14011923d`
- `ole32!CoTaskMemFree` at `0x140119247`
- `ole32!CoTaskMemFree` at `0x1401192f5`
- `ole32!CoCreateInstance` at `0x140118fae`
- `ole32!CoCreateInstance` at `0x140118fae`

## pseudocode

```c
__int64 __fastcall BlbSetDiffAreaSpace(char *a1, __int64 a2, char a3)
{
  unsigned __int16 *v6; // rdi
  HRESULT v7; // ebx
  PVOID *v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // rax
  int v11; // eax
  int v12; // eax
  void *v13; // rax
  unsigned __int16 *v14; // rcx
  int v15; // r8d
  int v16; // edx
  int v17; // eax
  unsigned __int16 *v19; // [rsp+30h] [rbp-29h] BYREF
  __int64 v20; // [rsp+38h] [rbp-21h] BYREF
  __int64 v21; // [rsp+40h] [rbp-19h] BYREF
  LPVOID ppv; // [rsp+48h] [rbp-11h] BYREF
  __int128 v23; // [rsp+50h] [rbp-9h] BYREF
  LPVOID v24[2]; // [rsp+60h] [rbp+7h] BYREF
  LPVOID pv[2]; // [rsp+70h] [rbp+17h]
  __int128 v26; // [rsp+80h] [rbp+27h]
  int v27; // [rsp+D8h] [rbp+7Fh] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_3d0416bbb01f34b24d372dad5da93638_Traceguids);
  }
  ppv = 0;
  v6 = 0;
  v20 = 0;
  v21 = 0;
  v19 = 0;
  *(_OWORD *)v24 = 0;
  *(_OWORD *)pv = 0;
  v26 = 0;
  v7 = CoCreateInstance(&CLSID_VssSnapshotMgmt, 0, 4u, &IID_IVssSnapshotMgmt, &ppv);
  if ( v7 >= 0 )
  {
    v10 = *(_QWORD *)ppv;
    v23 = xmmword_14014D548;
    v7 = (*(__int64 (__fastcall **)(LPVOID, __int128 *, GUID *, __int64 *))(v10 + 24))(
           ppv,
           &v23,
           &IID_IVssDifferentialSoftwareSnapshotMgmt,
           &v20);
    if ( v7 >= 0 )
    {
      v11 = (*(__int64 (__fastcall **)(__int64, char *, __int64 *))(*(_QWORD *)v20 + 48LL))(v20, a1, &v21);
      v7 = v11;
      if ( v11 >= 0 )
      {
        while ( 1 )
        {
          v27 = 0;
          v12 = (*(__int64 (__fastcall **)(__int64, __int64, LPVOID *, int *))(*(_QWORD *)v21 + 24LL))(
                  v21,
                  1,
                  v24,
                  &v27);
          v7 = v12;
          if ( v12 == 1 )
          {
            v7 = -2139619280;
            goto LABEL_56;
          }
          if ( v12 < 0 )
            goto LABEL_56;
          if ( LODWORD(v24[0]) != 3 )
            BlbAssert(
              "base\\stor\\blb\\engine\\blbengutils\\blbdiffareautils.cpp",
              0x262u,
              "prop.Type == VSS_MGMT_OBJECT_DIFF_AREA");
          if ( v27 != 1 )
            BlbAssert("base\\stor\\blb\\engine\\blbengutils\\blbdiffareautils.cpp", 0x263u, "ulFetched == 1");
          if ( v6 )
          {
            CoTaskMemFree(v6);
            v19 = 0;
          }
          v7 = BlbutilDuplicateString((const unsigned __int16 *)pv[0], &v19, 0);
          if ( v7 < 0 )
          {
            v6 = v19;
            goto LABEL_56;
          }
          v13 = pv[0];
          if ( !a3 )
            break;
          v14 = (unsigned __int16 *)pv[0];
          do
          {
            v15 = *(unsigned __int16 *)((char *)v14 + a1 - (char *)pv[0]);
            v16 = *v14 - v15;
            if ( v16 )
              break;
            ++v14;
          }
          while ( v15 );
          if ( !v16 )
            break;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_3d0416bbb01f34b24d372dad5da93638_Traceguids);
            v13 = pv[0];
          }
          CoTaskMemFree(v13);
          CoTaskMemFree(v24[1]);
          v6 = v19;
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_SS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            37,
            (unsigned int)&WPP_3d0416bbb01f34b24d372dad5da93638_Traceguids,
            v24[1],
            (__int64)pv[0]);
          v13 = pv[0];
        }
        CoTaskMemFree(v13);
        CoTaskMemFree(v24[1]);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, &WPP_3d0416bbb01f34b24d372dad5da93638_Traceguids, a2);
        }
        v6 = v19;
        v17 = (*(__int64 (__fastcall **)(__int64, char *, unsigned __int16 *, __int64))(*(_QWORD *)v20 + 32LL))(
                v20,
                a1,
                v19,
                a2);
        v7 = v17;
        if ( v17 >= 0 )
          goto LABEL_56;
        v8 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_SiD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            39,
            (unsigned int)&WPP_3d0416bbb01f34b24d372dad5da93638_Traceguids,
            (_DWORD)a1,
            a2,
            v17);
LABEL_56:
          v8 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v6 )
        {
          CoTaskMemFree(v6);
          v8 = (PVOID *)WPP_GLOBAL_Control;
        }
      }
      else
      {
        v8 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            35,
            (unsigned int)&WPP_3d0416bbb01f34b24d372dad5da93638_Traceguids,
            (_DWORD)a1,
            v11);
          goto LABEL_11;
        }
      }
    }
    else
    {
      v8 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v9 = 34;
        goto LABEL_10;
      }
    }
  }
  else
  {
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v9 = 33;
LABEL_10:
      WPP_SF_d(v8[2], v9, &WPP_3d0416bbb01f34b24d372dad5da93638_Traceguids);
LABEL_11:
      v8 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  if ( v21 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v20 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( ppv )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v7 < 0 )
  {
    if ( v8 == &WPP_GLOBAL_Control )
      return (unsigned int)v7;
    if ( (*((_BYTE *)v8 + 28) & 1) != 0 && *((_BYTE *)v8 + 25) >= 2u )
    {
      WPP_SF_Sd((unsigned int)v8[2], 40, (unsigned int)&WPP_3d0416bbb01f34b24d372dad5da93638_Traceguids, (_DWORD)a1, v7);
      v8 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 1) != 0 && *((_BYTE *)v8 + 25) >= 4u )
    WPP_SF_(v8[2], 41, &WPP_3d0416bbb01f34b24d372dad5da93638_Traceguids);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140118f04  mov     [rsp-8+arg_0], rbx
0x140118f09  mov     [rsp-8+arg_8], rsi
0x140118f0e  push    rbp
0x140118f0f  push    rdi
0x140118f10  push    r13
0x140118f12  push    r14
0x140118f14  push    r15
0x140118f16  lea     rbp, [rsp-37h]
0x140118f1b  sub     rsp, 90h
0x140118f22  mov     r15b, r8b
0x140118f25  mov     r14, rdx
0x140118f28  mov     rsi, rcx
0x140118f2b  mov     rcx, cs:WPP_GLOBAL_Control
0x140118f32  lea     rax, WPP_GLOBAL_Control
0x140118f39  mov     r13d, 1
0x140118f3f  cmp     rcx, rax
0x140118f42  jz      short loc_140118F64
0x140118f44  test    [rcx+1Ch], r13b
0x140118f48  jz      short loc_140118F64
0x140118f4a  cmp     byte ptr [rcx+19h], 4
0x140118f4e  jb      short loc_140118F64
0x140118f50  mov     rcx, [rcx+10h]
0x140118f54  lea     edx, [r13+1Fh]
0x140118f58  lea     r8, WPP_3d0416bbb01f34b24d372dad5da93638_Traceguids
0x140118f5f  call    WPP_SF_
0x140118f64  xorps   xmm0, xmm0
0x140118f67  mov     [rbp+57h+var_68], 0
0x140118f6f  xor     edi, edi
0x140118f71  mov     [rbp+57h+var_78], 0
0x140118f79  lea     rax, [rbp+57h+var_68]
0x140118f7d  mov     [rbp+57h+var_70], 0
0x140118f85  lea     r9, IID_IVssSnapshotMgmt; riid
0x140118f8c  mov     [rbp+57h+var_80], rdi
0x140118f90  xor     edx, edx; pUnkOuter
0x140118f92  mov     [rsp+0B0h+ppv], rax; ppv
0x140118f97  lea     r8d, [rdi+4]; dwClsContext
0x140118f9b  lea     rcx, CLSID_VssSnapshotMgmt; rclsid
0x140118fa2  movups  xmmword ptr [rbp+57h+var_50], xmm0
0x140118fa6  movups  xmmword ptr [rbp+57h+pv], xmm0
0x140118faa  movups  [rbp+57h+var_30], xmm0
0x140118fae  call    cs:__imp_CoCreateInstance
0x140118fb4  mov     ebx, eax
0x140118fb6  test    eax, eax
0x140118fb8  jns     short loc_140119009
0x140118fba  mov     rcx, cs:WPP_GLOBAL_Control
0x140118fc1  lea     rdi, WPP_GLOBAL_Control
0x140118fc8  cmp     rcx, rdi
0x140118fcb  jz      loc_140119309
0x140118fd1  test    [rcx+1Ch], r13b
0x140118fd5  jz      loc_140119309
0x140118fdb  cmp     byte ptr [rcx+19h], 2
0x140118fdf  jb      loc_140119309
0x140118fe5  mov     edx, 21h ; '!'
0x140118fea  mov     rcx, [rcx+10h]
0x140118fee  lea     r8, WPP_3d0416bbb01f34b24d372dad5da93638_Traceguids
0x140118ff5  mov     r9d, eax
0x140118ff8  call    WPP_SF_d
0x140118ffd  mov     rcx, cs:WPP_GLOBAL_Control
0x140119004  jmp     loc_140119309
0x140119009  mov     rcx, [rbp+57h+var_68]
0x14011900d  lea     r9, [rbp+57h+var_78]
0x140119011  movups  xmm0, cs:xmmword_14014D548
0x140119018  lea     r8, IID_IVssDifferentialSoftwareSnapshotMgmt
0x14011901f  lea     rdx, [rbp+57h+var_60]
0x140119023  mov     rax, [rcx]
0x140119026  movdqu  [rbp+57h+var_60], xmm0
0x14011902b  mov     rax, [rax+18h]
0x14011902f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140119034  mov     ebx, eax
0x140119036  test    eax, eax
0x140119038  jns     short loc_14011906F
0x14011903a  mov     rcx, cs:WPP_GLOBAL_Control
0x140119041  lea     rdi, WPP_GLOBAL_Control
0x140119048  cmp     rcx, rdi
0x14011904b  jz      loc_140119309
0x140119051  test    [rcx+1Ch], r13b
0x140119055  jz      loc_140119309
0x14011905b  cmp     byte ptr [rcx+19h], 2
0x14011905f  jb      loc_140119309
0x140119065  mov     edx, 22h ; '"'
0x14011906a  jmp     loc_140118FEA
0x14011906f  mov     rcx, [rbp+57h+var_78]
0x140119073  lea     r8, [rbp+57h+var_70]
0x140119077  mov     rdx, rsi
0x14011907a  mov     rax, [rcx]
0x14011907d  mov     rax, [rax+30h]
0x140119081  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140119086  mov     ebx, eax
0x140119088  test    eax, eax
0x14011908a  jns     short loc_1401190D8
0x14011908c  mov     rcx, cs:WPP_GLOBAL_Control
0x140119093  lea     rdi, WPP_GLOBAL_Control
0x14011909a  cmp     rcx, rdi
0x14011909d  jz      loc_140119309
0x1401190a3  test    [rcx+1Ch], r13b
0x1401190a7  jz      loc_140119309
0x1401190ad  cmp     byte ptr [rcx+19h], 2
0x1401190b1  jb      loc_140119309
0x1401190b7  mov     rcx, [rcx+10h]
0x1401190bb  lea     r8, WPP_3d0416bbb01f34b24d372dad5da93638_Traceguids
0x1401190c2  mov     edx, 23h ; '#'
0x1401190c7  mov     dword ptr [rsp+0B0h+ppv], eax
0x1401190cb  mov     r9, rsi
0x1401190ce  call    WPP_SF_Sd
0x1401190d3  jmp     loc_140118FFD
0x1401190d8  mov     rcx, [rbp+57h+var_70]
0x1401190dc  lea     r9, [rbp+57h+arg_18]
0x1401190e0  mov     [rbp+57h+arg_18], 0
0x1401190e7  lea     r8, [rbp+57h+var_50]
0x1401190eb  mov     edx, r13d
0x1401190ee  mov     rax, [rcx]
0x1401190f1  mov     rax, [rax+18h]
0x1401190f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401190fa  mov     ebx, eax
0x1401190fc  cmp     eax, r13d
0x1401190ff  jz      loc_1401192E1
0x140119105  test    eax, eax
0x140119107  js      loc_1401192E6
0x14011910d  cmp     dword ptr [rbp+57h+var_50], 3
0x140119111  jz      short loc_14011912B
0x140119113  lea     r8, aPropTypeVssMgm; "prop.Type == VSS_MGMT_OBJECT_DIFF_AREA"
0x14011911a  mov     edx, 262h; unsigned int
0x14011911f  lea     rcx, aBaseStorBlbEng_6; "base\\stor\\blb\\engine\\blbengutils\\b"...
0x140119126  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x14011912b  cmp     [rbp+57h+arg_18], r13d
0x14011912f  jz      short loc_140119149
0x140119131  lea     r8, aUlfetched1; "ulFetched == 1"
0x140119138  mov     edx, 263h; unsigned int
0x14011913d  lea     rcx, aBaseStorBlbEng_6; "base\\stor\\blb\\engine\\blbengutils\\b"...
0x140119144  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x140119149  test    rdi, rdi
0x14011914c  jz      short loc_14011915F
0x14011914e  mov     rcx, rdi; pv
0x140119151  call    cs:__imp_CoTaskMemFree
0x140119157  mov     [rbp+57h+var_80], 0
0x14011915f  mov     rcx, [rbp+57h+pv]; unsigned __int16 *
0x140119163  lea     rdx, [rbp+57h+var_80]; unsigned __int16 **
0x140119167  xor     r8d, r8d; unsigned __int64
0x14011916a  call    ?BlbutilDuplicateString@@YAJPEBGPEAPEAG_K@Z; BlbutilDuplicateString(ushort const *,ushort * *,unsigned __int64)
0x14011916f  mov     ebx, eax
0x140119171  test    eax, eax
0x140119173  js      loc_1401192DB
0x140119179  mov     rax, [rbp+57h+pv]
0x14011917d  test    r15b, r15b
0x140119180  jz      short loc_1401191F9
0x140119182  mov     r9, rsi
0x140119185  mov     rcx, rax
0x140119188  sub     r9, rax
0x14011918b  movzx   edx, word ptr [rcx]
0x14011918e  movzx   r8d, word ptr [rcx+r9]
0x140119193  sub     edx, r8d
0x140119196  jnz     short loc_1401191A1
0x140119198  add     rcx, 2
0x14011919c  test    r8d, r8d
0x14011919f  jnz     short loc_14011918B
0x1401191a1  test    edx, edx
0x1401191a3  jz      short loc_1401191F9
0x1401191a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1401191ac  lea     rdx, WPP_GLOBAL_Control
0x1401191b3  cmp     rcx, rdx
0x1401191b6  jz      short loc_1401191DD
0x1401191b8  test    [rcx+1Ch], r13b
0x1401191bc  jz      short loc_1401191DD
0x1401191be  cmp     byte ptr [rcx+19h], 2
0x1401191c2  jb      short loc_1401191DD
0x1401191c4  mov     rcx, [rcx+10h]
0x1401191c8  lea     r8, WPP_3d0416bbb01f34b24d372dad5da93638_Traceguids
0x1401191cf  mov     edx, 24h ; '$'
0x1401191d4  call    WPP_SF_
0x1401191d9  mov     rax, [rbp+57h+pv]
0x1401191dd  mov     rcx, rax; pv
0x1401191e0  call    cs:__imp_CoTaskMemFree
0x1401191e6  mov     rcx, [rbp+57h+var_50+8]; pv
0x1401191ea  call    cs:__imp_CoTaskMemFree
0x1401191f0  mov     rdi, [rbp+57h+var_80]
0x1401191f4  jmp     loc_1401190D8
0x1401191f9  mov     rcx, cs:WPP_GLOBAL_Control
0x140119200  lea     r15, WPP_GLOBAL_Control
0x140119207  cmp     rcx, r15
0x14011920a  jz      short loc_14011923A
0x14011920c  test    [rcx+1Ch], r13b
0x140119210  jz      short loc_14011923A
0x140119212  cmp     byte ptr [rcx+19h], 4
0x140119216  jb      short loc_14011923A
0x140119218  mov     r9, [rbp+57h+var_50+8]
0x14011921c  lea     r8, WPP_3d0416bbb01f34b24d372dad5da93638_Traceguids
0x140119223  mov     rcx, [rcx+10h]
0x140119227  mov     edx, 25h ; '%'
0x14011922c  mov     [rsp+0B0h+ppv], rax
0x140119231  call    WPP_SF_SS
0x140119236  mov     rax, [rbp+57h+pv]
0x14011923a  mov     rcx, rax; pv
0x14011923d  call    cs:__imp_CoTaskMemFree
0x140119243  mov     rcx, [rbp+57h+var_50+8]; pv
0x140119247  call    cs:__imp_CoTaskMemFree
0x14011924d  mov     rcx, cs:WPP_GLOBAL_Control
0x140119254  cmp     rcx, r15
0x140119257  jz      short loc_14011927D
0x140119259  test    [rcx+1Ch], r13b
0x14011925d  jz      short loc_14011927D
0x14011925f  cmp     byte ptr [rcx+19h], 5
0x140119263  jb      short loc_14011927D
0x140119265  mov     rcx, [rcx+10h]
0x140119269  lea     r8, WPP_3d0416bbb01f34b24d372dad5da93638_Traceguids
0x140119270  mov     edx, 26h ; '&'
0x140119275  mov     r9, r14
0x140119278  call    WPP_SF_q
0x14011927d  mov     rcx, [rbp+57h+var_78]
0x140119281  mov     r9, r14
0x140119284  mov     rdi, [rbp+57h+var_80]
0x140119288  mov     rdx, rsi
0x14011928b  mov     r8, rdi
0x14011928e  mov     rax, [rcx]
0x140119291  mov     rax, [rax+20h]
0x140119295  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14011929a  mov     ebx, eax
0x14011929c  test    eax, eax
0x14011929e  jns     short loc_1401192E6
0x1401192a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1401192a7  cmp     rcx, r15
0x1401192aa  jz      short loc_1401192ED
0x1401192ac  test    [rcx+1Ch], r13b
0x1401192b0  jz      short loc_1401192ED
0x1401192b2  cmp     byte ptr [rcx+19h], 2
0x1401192b6  jb      short loc_1401192ED
0x1401192b8  mov     rcx, [rcx+10h]
0x1401192bc  lea     r8, WPP_3d0416bbb01f34b24d372dad5da93638_Traceguids
0x1401192c3  mov     [rsp+0B0h+var_88], eax
0x1401192c7  mov     edx, 27h ; '''
0x1401192cc  mov     r9, rsi
0x1401192cf  mov     [rsp+0B0h+ppv], r14
0x1401192d4  call    WPP_SF_SiD
0x1401192d9  jmp     short loc_1401192E6
0x1401192db  mov     rdi, [rbp+57h+var_80]
0x1401192df  jmp     short loc_1401192E6
0x1401192e1  mov     ebx, 80780030h
0x1401192e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1401192ed  test    rdi, rdi
0x1401192f0  jz      short loc_140119302
0x1401192f2  mov     rcx, rdi; pv
0x1401192f5  call    cs:__imp_CoTaskMemFree
0x1401192fb  mov     rcx, cs:WPP_GLOBAL_Control
0x140119302  lea     rdi, WPP_GLOBAL_Control
0x140119309  mov     rdx, [rbp+57h+var_70]
0x14011930d  test    rdx, rdx
0x140119310  jz      short loc_140119328
0x140119312  mov     rax, [rdx]
0x140119315  mov     rcx, rdx
0x140119318  mov     rax, [rax+10h]
0x14011931c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140119321  mov     rcx, cs:WPP_GLOBAL_Control
0x140119328  mov     rdx, [rbp+57h+var_78]
0x14011932c  test    rdx, rdx
0x14011932f  jz      short loc_140119347
0x140119331  mov     rax, [rdx]
0x140119334  mov     rcx, rdx
0x140119337  mov     rax, [rax+10h]
0x14011933b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140119340  mov     rcx, cs:WPP_GLOBAL_Control
0x140119347  mov     rdx, [rbp+57h+var_68]
0x14011934b  test    rdx, rdx
0x14011934e  jz      short loc_140119366
0x140119350  mov     rax, [rdx]
0x140119353  mov     rcx, rdx
0x140119356  mov     rax, [rax+10h]
0x14011935a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14011935f  mov     rcx, cs:WPP_GLOBAL_Control
0x140119366  test    ebx, ebx
0x140119368  jns     short loc_14011939E
0x14011936a  cmp     rcx, rdi
0x14011936d  jz      short loc_1401193C4
0x14011936f  test    [rcx+1Ch], r13b
0x140119373  jz      short loc_14011939E
0x140119375  cmp     byte ptr [rcx+19h], 2
0x140119379  jb      short loc_14011939E
0x14011937b  mov     rcx, [rcx+10h]
0x14011937f  lea     r8, WPP_3d0416bbb01f34b24d372dad5da93638_Traceguids
0x140119386  mov     edx, 28h ; '('
0x14011938b  mov     dword ptr [rsp+0B0h+ppv], ebx
0x14011938f  mov     r9, rsi
0x140119392  call    WPP_SF_Sd
0x140119397  mov     rcx, cs:WPP_GLOBAL_Control
0x14011939e  cmp     rcx, rdi
0x1401193a1  jz      short loc_1401193C4
0x1401193a3  test    [rcx+1Ch], r13b
0x1401193a7  jz      short loc_1401193C4
0x1401193a9  cmp     byte ptr [rcx+19h], 4
0x1401193ad  jb      short loc_1401193C4
0x1401193af  mov     rcx, [rcx+10h]
0x1401193b3  lea     r8, WPP_3d0416bbb01f34b24d372dad5da93638_Traceguids
0x1401193ba  mov     edx, 29h ; ')'
0x1401193bf  call    WPP_SF_
0x1401193c4  lea     r11, [rsp+0B0h+var_20]
0x1401193cc  mov     eax, ebx
0x1401193ce  mov     rbx, [r11+30h]
0x1401193d2  mov     rsi, [r11+38h]
0x1401193d6  mov     rsp, r11
0x1401193d9  pop     r15
0x1401193db  pop     r14
0x1401193dd  pop     r13
  ... truncated ...
```
