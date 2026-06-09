# GetConnectivityCapability(_CONNECTIVITY_CAPABILITY *,_CONNECTIVITY_CAPABILITY *,ulong *,ulong *)

- ea: `0x180004fcc`
- end: `0x1800054d4`
- name: `?GetConnectivityCapability@@YAKPEAW4_CONNECTIVITY_CAPABILITY@@0PEAK1@Z`
- size: `1288`
- prototype: `unsigned int __fastcall(enum _CONNECTIVITY_CAPABILITY *, enum _CONNECTIVITY_CAPABILITY *, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180004ef8`

## callees

- `0x180004fcc`
- `0x18000d7e0`
- `0x180012d6e`
- `0x180012db0`
- `0x180014010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180005286`
- `OLEAUT32!__imp_VariantInit` at `0x1800052f4`
- `OLEAUT32!__imp_VariantInit` at `0x180005286`
- `OLEAUT32!__imp_VariantInit` at `0x1800052f4`
- `OLEAUT32!__imp_VariantClear` at `0x1800052de`
- `OLEAUT32!__imp_VariantClear` at `0x18000534c`
- `OLEAUT32!__imp_VariantClear` at `0x1800052de`
- `OLEAUT32!__imp_VariantClear` at `0x18000534c`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800050db`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000542f`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800054a4`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800050db`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000542f`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800054a4`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180005018`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180005018`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800050a0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800050a0`

## pseudocode

```c
__int64 __fastcall GetConnectivityCapability(
        enum _CONNECTIVITY_CAPABILITY *a1,
        enum _CONNECTIVITY_CAPABILITY *a2,
        unsigned int *a3,
        unsigned int *a4)
{
  HRESULT v9; // ebx
  BOOL v10; // ebx
  HRESULT v11; // eax
  unsigned int v12; // edi
  int v13; // eax
  int v14; // eax
  unsigned int v15; // r14d
  __int64 *v16; // rbx
  __int64 *v17; // r14
  __int64 (__fastcall ***v18)(__int64, GUID *, __int64 **); // rdi
  int v19; // eax
  unsigned int v20; // r8d
  char v21; // al
  __int64 (__fastcall **v22)(__int64, GUID *, __int64 **); // rax
  int v23; // eax
  unsigned int v24; // r8d
  int v25; // eax
  unsigned int v26; // r8d
  int v27; // eax
  unsigned int v28; // r8d
  _QWORD *v29; // rdi
  _QWORD *v30; // rdi
  _QWORD *v31; // rdi
  int ppv; // [rsp+20h] [rbp-E0h]
  LPVOID v33; // [rsp+30h] [rbp-D0h] BYREF
  __int64 *v34; // [rsp+38h] [rbp-C8h] BYREF
  int v35; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v36; // [rsp+48h] [rbp-B8h] BYREF
  int v37; // [rsp+50h] [rbp-B0h] BYREF
  BOOL v38; // [rsp+58h] [rbp-A8h]
  int v39; // [rsp+5Ch] [rbp-A4h]
  VARIANTARG pvarg; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v41[20]; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v42[10]; // [rsp+120h] [rbp+20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+78h]

  if ( __PAIR128__((unsigned __int64)a1, (unsigned __int64)a2) == 0 )
    return 13;
  v9 = CoInitializeEx(0, 0);
  if ( (int)(v9 + 0x80000000) >= 0 && v9 != -2147417850 )
  {
    if ( (v9 & 0x1FFF0000) == 0x70000 )
      return (unsigned __int16)v9;
    return (unsigned int)v9;
  }
  v10 = v9 >= 0;
  v38 = v10;
  if ( a1 )
    *(_DWORD *)a1 = 0;
  if ( a2 )
    *(_DWORD *)a2 = 0;
  if ( a3 )
    *a3 = 0;
  if ( a4 )
    *a4 = 0;
  v33 = 0;
  v11 = CoCreateInstance(
          &GUID_a47979d2_c419_11d9_a5b4_001185ad2b89,
          0,
          4u,
          &GUID_d0074ffd_570f_4a9b_8d69_199fdba5723b,
          &v33);
  v12 = v11;
  if ( v11 < 0 )
  {
    if ( (v11 & 0x1FFF0000) == 0x70000 )
      v12 = (unsigned __int16)v11;
LABEL_19:
    if ( v33 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v33 + 16LL))(v33);
    if ( v10 )
      CoUninitialize();
    return v12;
  }
  v36 = 0;
  v13 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64 *))(*(_QWORD *)v33 + 232LL))(v33, 1, &v36);
  v12 = v13;
  if ( v13 < 0 )
  {
    if ( (v13 & 0x1FFF0000) == 0x70000 )
      v12 = (unsigned __int16)v13;
    if ( v36 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
    goto LABEL_19;
  }
  while ( 1 )
  {
    memset_0(v41, 0, sizeof(v41));
    v35 = 0;
    v14 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD *, int *))(*(_QWORD *)v36 + 24LL))(v36, 20, v41, &v35);
    v39 = v14;
    v15 = v14;
    if ( v14 < 0 )
      break;
    if ( !v35 )
    {
      v30 = v41;
      do
      {
        if ( *v30 )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v30 + 16LL))(*v30);
        ++v30;
      }
      while ( v30 != v42 );
      goto LABEL_80;
    }
    v34 = v41;
    if ( v41 != &v41[v35] )
    {
      v16 = v34;
      v17 = &v41[v35];
      do
      {
        v18 = (__int64 (__fastcall ***)(__int64, GUID *, __int64 **))*v16;
        v37 = 0;
        v19 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(__int64, GUID *, __int64 **), int *))(*v18)[7])(
                v18,
                &v37);
        if ( v19 >= 0 )
        {
          v21 = v37;
          if ( a1 )
          {
            if ( (v37 & 8) != 0 )
            {
              *(_DWORD *)a1 = 2;
            }
            else if ( *(_DWORD *)a1 != 2 && (v37 & 4) != 0 )
            {
              *(_DWORD *)a1 = 1;
            }
          }
          if ( a2 )
          {
            if ( (v21 & 0x20) != 0 )
            {
              *(_DWORD *)a2 = 2;
            }
            else if ( *(_DWORD *)a2 != 2 && (v21 & 0x10) != 0 )
            {
              *(_DWORD *)a2 = 1;
            }
          }
        }
        else
        {
          wil::details::in1diag3::_Log_Hr(retaddr, (void *)0x58, v20, (const char *)(unsigned int)v19, ppv);
        }
        if ( a3 || a4 )
        {
          v22 = *v18;
          v34 = 0;
          v23 = (*v22)((__int64)v18, &GUID_55272a00_42cb_11ce_8135_00aa004bb851, &v34);
          if ( v23 >= 0 )
          {
            if ( a3 )
            {
              VariantInit(&pvarg);
              v25 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, VARIANTARG *, _QWORD))(*v34 + 24))(
                      v34,
                      L"NA_InternetConnectivityV4",
                      &pvarg,
                      0);
              if ( v25 >= 0 )
              {
                if ( pvarg.vt == 19 )
                  *a3 |= pvarg.cyVal.Lo;
              }
              else
              {
                wil::details::in1diag3::_Log_Hr(retaddr, (void *)0x7B, v26, (const char *)(unsigned int)v25, ppv);
              }
              VariantClear(&pvarg);
            }
            if ( a4 )
            {
              VariantInit(&pvarg);
              v27 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, VARIANTARG *, _QWORD))(*v34 + 24))(
                      v34,
                      L"NA_InternetConnectivityV6",
                      &pvarg,
                      0);
              if ( v27 >= 0 )
              {
                if ( pvarg.vt == 19 )
                  *a4 |= pvarg.cyVal.Lo;
              }
              else
              {
                wil::details::in1diag3::_Log_Hr(retaddr, (void *)0x85, v28, (const char *)(unsigned int)v27, ppv);
              }
              VariantClear(&pvarg);
            }
          }
          else
          {
            wil::details::in1diag3::_Log_Hr(retaddr, (void *)0x76, v24, (const char *)(unsigned int)v23, ppv);
          }
          if ( v34 )
            (*(void (__fastcall **)(__int64 *))(*v34 + 16))(v34);
        }
        ++v16;
      }
      while ( v16 != v17 );
      LOBYTE(v10) = v38;
      v15 = v39;
    }
    v29 = v41;
    if ( v15 == 1 )
    {
      do
      {
        if ( *v29 )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v29 + 16LL))(*v29);
        ++v29;
      }
      while ( v29 != v42 );
LABEL_80:
      if ( v36 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
      if ( v33 )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v33 + 16LL))(v33);
      if ( v10 )
        CoUninitialize();
      return 0;
    }
    do
    {
      if ( *v29 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v29 + 16LL))(*v29);
      ++v29;
    }
    while ( v29 != v42 );
  }
  if ( (v14 & 0x1FFF0000) == 0x70000 )
    v15 = (unsigned __int16)v14;
  v31 = v41;
  do
  {
    if ( *v31 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v31 + 16LL))(*v31);
    ++v31;
  }
  while ( v31 != v42 );
  if ( v36 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
  if ( v33 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v33 + 16LL))(v33);
  if ( v10 )
    CoUninitialize();
  return v15;
}

```

## disassembly

```asm
0x180004fcc  push    rbp
0x180004fce  push    rbx
0x180004fcf  push    rsi
0x180004fd0  push    rdi
0x180004fd1  push    r12
0x180004fd3  push    r13
0x180004fd5  push    r14
0x180004fd7  push    r15
0x180004fd9  lea     rbp, [rsp-38h]
0x180004fde  sub     rsp, 138h
0x180004fe5  mov     rax, cs:__security_cookie
0x180004fec  xor     rax, rsp
0x180004fef  mov     [rbp+70h+var_50], rax
0x180004ff3  xor     r14d, r14d
0x180004ff6  mov     r13, r9
0x180004ff9  mov     r12, r8
0x180004ffc  mov     rsi, rdx
0x180004fff  mov     r15, rcx
0x180005002  test    rcx, rcx
0x180005005  jnz     short loc_180005014
0x180005007  test    rdx, rdx
0x18000500a  jnz     short loc_180005014
0x18000500c  lea     eax, [rdx+0Dh]
0x18000500f  jmp     loc_1800054B3
0x180005014  xor     edx, edx; dwCoInit
0x180005016  xor     ecx, ecx; pvReserved
0x180005018  call    cs:__imp_CoInitializeEx
0x18000501f  nop     dword ptr [rax+rax+00h]
0x180005024  mov     ecx, 80000000h
0x180005029  mov     ebx, eax
0x18000502b  add     eax, ecx
0x18000502d  test    ecx, eax
0x18000502f  jnz     short loc_180005051
0x180005031  cmp     ebx, 80010106h
0x180005037  jz      short loc_180005051
0x180005039  mov     eax, ebx
0x18000503b  and     eax, 1FFF0000h
0x180005040  cmp     eax, 70000h
0x180005045  jnz     short loc_18000504A
0x180005047  movzx   ebx, bx
0x18000504a  mov     eax, ebx
0x18000504c  jmp     loc_1800054B3
0x180005051  shr     ebx, 1Fh
0x180005054  xor     bl, 1
0x180005057  mov     [rsp+170h+var_118], ebx
0x18000505b  test    r15, r15
0x18000505e  jz      short loc_180005063
0x180005060  mov     [r15], r14d
0x180005063  test    rsi, rsi
0x180005066  jz      short loc_18000506B
0x180005068  mov     [rsi], r14d
0x18000506b  test    r12, r12
0x18000506e  jz      short loc_180005074
0x180005070  mov     [r12], r14d
0x180005074  test    r13, r13
0x180005077  jz      short loc_18000507D
0x180005079  mov     [r13+0], r14d
0x18000507d  xor     edx, edx; pUnkOuter
0x18000507f  mov     [rsp+170h+var_140], r14
0x180005084  lea     rax, [rsp+170h+var_140]
0x180005089  lea     r9, _GUID_d0074ffd_570f_4a9b_8d69_199fdba5723b; riid
0x180005090  mov     qword ptr [rsp+170h+ppv], rax; int
0x180005095  lea     rcx, _GUID_a47979d2_c419_11d9_a5b4_001185ad2b89; rclsid
0x18000509c  lea     r8d, [rdx+4]; dwClsContext
0x1800050a0  call    cs:__imp_CoCreateInstance
0x1800050a7  nop     dword ptr [rax+rax+00h]
0x1800050ac  mov     edi, eax
0x1800050ae  test    eax, eax
0x1800050b0  jns     short loc_1800050EE
0x1800050b2  and     eax, 1FFF0000h
0x1800050b7  cmp     eax, 70000h
0x1800050bc  jnz     short loc_1800050C1
0x1800050be  movzx   edi, di
0x1800050c1  mov     rcx, [rsp+170h+var_140]
0x1800050c6  test    rcx, rcx
0x1800050c9  jz      short loc_1800050D7
0x1800050cb  mov     rdx, [rcx]
0x1800050ce  mov     rax, [rdx+10h]
0x1800050d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800050d7  test    bl, bl
0x1800050d9  jz      short loc_1800050E7
0x1800050db  call    cs:__imp_CoUninitialize
0x1800050e2  nop     dword ptr [rax+rax+00h]
0x1800050e7  mov     eax, edi
0x1800050e9  jmp     loc_1800054B3
0x1800050ee  mov     rcx, [rsp+170h+var_140]
0x1800050f3  lea     r8, [rsp+170h+var_128]
0x1800050f8  mov     [rsp+170h+var_128], r14
0x1800050fd  mov     edx, 1
0x180005102  mov     rax, [rcx]
0x180005105  mov     rax, [rax+0E8h]
0x18000510c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005111  mov     edi, eax
0x180005113  test    eax, eax
0x180005115  jns     short loc_18000513E
0x180005117  and     eax, 1FFF0000h
0x18000511c  cmp     eax, 70000h
0x180005121  jnz     short loc_180005126
0x180005123  movzx   edi, di
0x180005126  mov     rcx, [rsp+170h+var_128]
0x18000512b  test    rcx, rcx
0x18000512e  jz      short loc_1800050C1
0x180005130  mov     rax, [rcx]
0x180005133  mov     rax, [rax+10h]
0x180005137  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000513c  jmp     short loc_1800050C1
0x18000513e  xor     edx, edx; Val
0x180005140  lea     rcx, [rbp+70h+var_F0]; void *
0x180005144  mov     r8d, 0A0h; Size
0x18000514a  call    memset_0
0x18000514f  mov     rcx, [rsp+170h+var_128]
0x180005154  lea     r9, [rsp+170h+var_130]
0x180005159  mov     [rsp+170h+var_130], r14d
0x18000515e  lea     r8, [rbp+70h+var_F0]
0x180005162  mov     edx, 14h
0x180005167  mov     rax, [rcx]
0x18000516a  mov     rax, [rax+18h]
0x18000516e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005173  mov     [rsp+170h+var_114], eax
0x180005177  mov     r14d, eax
0x18000517a  test    eax, eax
0x18000517c  js      loc_18000543F
0x180005182  mov     eax, [rsp+170h+var_130]
0x180005186  test    eax, eax
0x180005188  jz      loc_1800053DA
0x18000518e  lea     rcx, [rbp+70h+var_F0]
0x180005192  mov     [rsp+170h+var_138], rcx
0x180005197  lea     rcx, [rbp+70h+var_F0]
0x18000519b  lea     rax, [rcx+rax*8]
0x18000519f  lea     rcx, [rbp+70h+var_F0]
0x1800051a3  cmp     rcx, rax
0x1800051a6  jz      loc_180005384
0x1800051ac  mov     rbx, [rsp+170h+var_138]
0x1800051b1  mov     r14, rax
0x1800051b4  mov     rdi, [rbx]
0x1800051b7  lea     rdx, [rsp+170h+var_120]
0x1800051bc  mov     rcx, rdi
0x1800051bf  mov     [rsp+170h+var_120], 0
0x1800051c7  mov     rax, [rdi]
0x1800051ca  mov     rax, [rax+38h]
0x1800051ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800051d3  test    eax, eax
0x1800051d5  jns     short loc_1800051EA
0x1800051d7  mov     rcx, [rbp+78h]; this
0x1800051db  mov     r9d, eax; char *
0x1800051de  mov     edx, 58h ; 'X'; void *
0x1800051e3  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800051e8  jmp     short loc_180005231
0x1800051ea  mov     eax, [rsp+170h+var_120]
0x1800051ee  test    r15, r15
0x1800051f1  jz      short loc_180005211
0x1800051f3  test    al, 8
0x1800051f5  jz      short loc_180005200
0x1800051f7  mov     dword ptr [r15], 2
0x1800051fe  jmp     short loc_180005211
0x180005200  cmp     dword ptr [r15], 2
0x180005204  jz      short loc_180005211
0x180005206  test    al, 4
0x180005208  jz      short loc_180005211
0x18000520a  mov     dword ptr [r15], 1
0x180005211  test    rsi, rsi
0x180005214  jz      short loc_180005231
0x180005216  test    al, 20h
0x180005218  jz      short loc_180005222
0x18000521a  mov     dword ptr [rsi], 2
0x180005220  jmp     short loc_180005231
0x180005222  cmp     dword ptr [rsi], 2
0x180005225  jz      short loc_180005231
0x180005227  test    al, 10h
0x180005229  jz      short loc_180005231
0x18000522b  mov     dword ptr [rsi], 1
0x180005231  test    r12, r12
0x180005234  jnz     short loc_18000523F
0x180005236  test    r13, r13
0x180005239  jz      loc_18000536E
0x18000523f  mov     rax, [rdi]
0x180005242  lea     r8, [rsp+170h+var_138]
0x180005247  lea     rdx, _GUID_55272a00_42cb_11ce_8135_00aa004bb851
0x18000524e  mov     [rsp+170h+var_138], 0
0x180005257  mov     rcx, rdi
0x18000525a  mov     rax, [rax]
0x18000525d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005262  test    eax, eax
0x180005264  jns     short loc_18000527C
0x180005266  mov     rcx, [rbp+78h]; this
0x18000526a  mov     r9d, eax; char *
0x18000526d  mov     edx, 76h ; 'v'; void *
0x180005272  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180005277  jmp     loc_180005358
0x18000527c  test    r12, r12
0x18000527f  jz      short loc_1800052EA
0x180005281  lea     rcx, [rsp+170h+pvarg]; pvarg
0x180005286  call    cs:__imp_VariantInit
0x18000528d  nop     dword ptr [rax+rax+00h]
0x180005292  mov     rcx, [rsp+170h+var_138]
0x180005297  lea     r8, [rsp+170h+pvarg]
0x18000529c  xor     r9d, r9d
0x18000529f  lea     rdx, aNaInternetconn_0; "NA_InternetConnectivityV4"
0x1800052a6  mov     rax, [rcx]
0x1800052a9  mov     rax, [rax+18h]
0x1800052ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800052b2  test    eax, eax
0x1800052b4  jns     short loc_1800052C9
0x1800052b6  mov     rcx, [rbp+78h]; this
0x1800052ba  mov     r9d, eax; char *
0x1800052bd  mov     edx, 7Bh ; '{'; void *
0x1800052c2  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800052c7  jmp     short loc_1800052D9
0x1800052c9  cmp     word ptr [rsp+170h+pvarg], 13h
0x1800052cf  jnz     short loc_1800052D9
0x1800052d1  mov     eax, dword ptr [rsp+170h+pvarg+8]
0x1800052d5  or      [r12], eax
0x1800052d9  lea     rcx, [rsp+170h+pvarg]; pvarg
0x1800052de  call    cs:__imp_VariantClear
0x1800052e5  nop     dword ptr [rax+rax+00h]
0x1800052ea  test    r13, r13
0x1800052ed  jz      short loc_180005358
0x1800052ef  lea     rcx, [rsp+170h+pvarg]; pvarg
0x1800052f4  call    cs:__imp_VariantInit
0x1800052fb  nop     dword ptr [rax+rax+00h]
0x180005300  mov     rcx, [rsp+170h+var_138]
0x180005305  lea     r8, [rsp+170h+pvarg]
0x18000530a  xor     r9d, r9d
0x18000530d  lea     rdx, aNaInternetconn; "NA_InternetConnectivityV6"
0x180005314  mov     rax, [rcx]
0x180005317  mov     rax, [rax+18h]
0x18000531b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005320  test    eax, eax
0x180005322  jns     short loc_180005337
0x180005324  mov     rcx, [rbp+78h]; this
0x180005328  mov     r9d, eax; char *
0x18000532b  mov     edx, 85h; void *
0x180005330  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180005335  jmp     short loc_180005347
0x180005337  cmp     word ptr [rsp+170h+pvarg], 13h
0x18000533d  jnz     short loc_180005347
0x18000533f  mov     eax, dword ptr [rsp+170h+pvarg+8]
0x180005343  or      [r13+0], eax
0x180005347  lea     rcx, [rsp+170h+pvarg]; pvarg
0x18000534c  call    cs:__imp_VariantClear
0x180005353  nop     dword ptr [rax+rax+00h]
0x180005358  mov     rcx, [rsp+170h+var_138]
0x18000535d  test    rcx, rcx
0x180005360  jz      short loc_18000536E
0x180005362  mov     rax, [rcx]
0x180005365  mov     rax, [rax+10h]
0x180005369  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000536e  add     rbx, 8
0x180005372  cmp     rbx, r14
0x180005375  jnz     loc_1800051B4
0x18000537b  mov     ebx, [rsp+170h+var_118]
0x18000537f  mov     r14d, [rsp+170h+var_114]
0x180005384  lea     rdi, [rbp+70h+var_F0]
0x180005388  cmp     r14d, 1
0x18000538c  jz      short loc_1800053B7
0x18000538e  xor     r14d, r14d
0x180005391  mov     rcx, [rdi]
0x180005394  test    rcx, rcx
0x180005397  jz      short loc_1800053A5
0x180005399  mov     rax, [rcx]
0x18000539c  mov     rax, [rax+10h]
0x1800053a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800053a5  add     rdi, 8
0x1800053a9  lea     rax, [rbp+70h+var_50]
0x1800053ad  cmp     rdi, rax
0x1800053b0  jnz     short loc_180005391
0x1800053b2  jmp     loc_18000513E
0x1800053b7  mov     rcx, [rdi]
0x1800053ba  test    rcx, rcx
0x1800053bd  jz      short loc_1800053CB
0x1800053bf  mov     rax, [rcx]
0x1800053c2  mov     rax, [rax+10h]
0x1800053c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800053cb  add     rdi, 8
0x1800053cf  lea     rax, [rbp+70h+var_50]
0x1800053d3  cmp     rdi, rax
0x1800053d6  jnz     short loc_1800053B7
0x1800053d8  jmp     short loc_1800053FF
0x1800053da  lea     rdi, [rbp+70h+var_F0]
0x1800053de  mov     rcx, [rdi]
0x1800053e1  test    rcx, rcx
0x1800053e4  jz      short loc_1800053F2
0x1800053e6  mov     rax, [rcx]
0x1800053e9  mov     rax, [rax+10h]
0x1800053ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800053f2  add     rdi, 8
0x1800053f6  lea     rax, [rbp+70h+var_50]
0x1800053fa  cmp     rdi, rax
0x1800053fd  jnz     short loc_1800053DE
0x1800053ff  mov     rcx, [rsp+170h+var_128]
0x180005404  test    rcx, rcx
0x180005407  jz      short loc_180005415
0x180005409  mov     rax, [rcx]
0x18000540c  mov     rax, [rax+10h]
0x180005410  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005415  mov     rcx, [rsp+170h+var_140]
0x18000541a  test    rcx, rcx
0x18000541d  jz      short loc_18000542B
0x18000541f  mov     rax, [rcx]
0x180005422  mov     rax, [rax+10h]
  ... truncated ...
```
