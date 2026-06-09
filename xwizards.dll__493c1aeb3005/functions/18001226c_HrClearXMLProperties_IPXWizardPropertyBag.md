# HrClearXMLProperties(IPXWizardPropertyBag *)

- ea: `0x18001226c`
- end: `0x1800124b7`
- name: `?HrClearXMLProperties@@YAJPEAUIPXWizardPropertyBag@@@Z`
- size: `587`
- prototype: `__int64 __fastcall(struct IPXWizardPropertyBag *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180014c80`

## callees

- `0x18000ae04`
- `0x18000e0f0`
- `0x18001226c`
- `0x180032a02`
- `0x180032a30`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012442`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001245d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012442`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001245d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012432`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012432`
- `OLEAUT32!__imp_SysFreeString` at `0x180012452`
- `OLEAUT32!__imp_SysFreeString` at `0x180012452`
- `OLEAUT32!__imp_VariantClear` at `0x1800123e1`
- `OLEAUT32!__imp_VariantClear` at `0x1800123e1`

## pseudocode

```c
__int64 __fastcall HrClearXMLProperties(struct IPXWizardPropertyBag *a1)
{
  int v3; // eax
  unsigned int v4; // esi
  int v5; // esi
  __int64 v6; // rax
  __int64 (__fastcall *v7)(struct IPXWizardPropertyBag *, __int64, int *, LPVOID *, _QWORD, _QWORD, int *); // rax
  unsigned __int8 v8; // al
  int v9; // eax
  int v10; // eax
  unsigned int v11; // ebx
  int v12; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v14; // [rsp+50h] [rbp-B0h] BYREF
  int v15; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v16[12]; // [rsp+64h] [rbp-9Ch] BYREF
  __int128 v17; // [rsp+70h] [rbp-90h]
  __int128 v18; // [rsp+80h] [rbp-80h]
  __int128 v19; // [rsp+90h] [rbp-70h]
  __int128 v20; // [rsp+A0h] [rbp-60h]
  __int128 v21; // [rsp+B0h] [rbp-50h]
  _OWORD v22[2]; // [rsp+C0h] [rbp-40h]
  _OWORD v23[5]; // [rsp+E0h] [rbp-20h] BYREF
  _OWORD v24[2]; // [rsp+130h] [rbp+30h]

  v14 = 0;
  v15 = 0;
  memset_0(v16, 0, 0x74u);
  if ( !a1 )
    return 0;
  v3 = (*(__int64 (__fastcall **)(struct IPXWizardPropertyBag *, __int64 *))(*(_QWORD *)a1 + 72LL))(a1, &v14);
  v4 = v3;
  if ( v3 >= 0 )
  {
    do
    {
      v5 = (*(__int64 (__fastcall **)(struct IPXWizardPropertyBag *, __int64, _QWORD, int *))(*(_QWORD *)a1 + 32LL))(
             a1,
             v14,
             0,
             &v15);
      if ( v5 )
        break;
      v23[0] = v17;
      v12 = 0;
      v6 = *(_QWORD *)a1;
      v23[1] = v18;
      v23[2] = v19;
      v7 = *(__int64 (__fastcall **)(struct IPXWizardPropertyBag *, __int64, int *, LPVOID *, _QWORD, _QWORD, int *))(v6 + 56);
      v23[3] = v20;
      v23[4] = v21;
      v24[0] = v22[0];
      *(_QWORD *)((char *)v24 + 14) = *(_QWORD *)((char *)v22 + 14);
      pv = 0;
      v5 = v7(a1, v14, &v15, &pv, 0, 0, &v12);
      if ( v5 >= 0 && *(_QWORD *)pv )
      {
        v8 = v12;
        if ( (v12 & 0x100) != 0 )
        {
          VariantClear(*(VARIANTARG **)pv);
          v8 = v12;
        }
        v9 = v8 - 1;
        if ( v9 )
        {
          v10 = v9 - 1;
          if ( v10 )
          {
            if ( v10 == 2 )
            {
              LocalFree(*(HLOCAL *)pv);
            }
            else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            {
              WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, &WPP_92b4ede73d0c3990e751819403b3312f_Traceguids, v23);
            }
          }
          else
          {
            CoTaskMemFree(*(LPVOID *)pv);
          }
        }
        else
        {
          SysFreeString(*(BSTR *)pv);
        }
        CoTaskMemFree(pv);
      }
    }
    while ( !v5 );
    v11 = 0;
    if ( v5 != 1 )
      v11 = v5;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, &WPP_92b4ede73d0c3990e751819403b3312f_Traceguids, v11);
    return v11;
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        56,
        &WPP_92b4ede73d0c3990e751819403b3312f_Traceguids,
        (unsigned int)v3);
    return v4;
  }
}

```

## disassembly

```asm
0x18001226c  push    rbp
0x18001226e  push    rbx
0x18001226f  push    rsi
0x180012270  push    rdi
0x180012271  lea     rbp, [rsp-68h]
0x180012276  sub     rsp, 168h
0x18001227d  mov     rax, cs:__security_cookie
0x180012284  xor     rax, rsp
0x180012287  mov     [rbp+80h+var_30], rax
0x18001228b  xor     edx, edx; Val
0x18001228d  mov     [rsp+180h+var_130], 0
0x180012296  mov     rbx, rcx
0x180012299  mov     [rsp+180h+var_120], 0
0x1800122a1  lea     rcx, [rsp+180h+var_11C]; void *
0x1800122a6  lea     r8d, [rdx+74h]; Size
0x1800122aa  call    memset_0
0x1800122af  test    rbx, rbx
0x1800122b2  jnz     short loc_1800122BB
0x1800122b4  xor     eax, eax
0x1800122b6  jmp     loc_18001249F
0x1800122bb  mov     rax, [rbx]
0x1800122be  lea     rdx, [rsp+180h+var_130]
0x1800122c3  mov     rcx, rbx
0x1800122c6  mov     rax, [rax+48h]
0x1800122ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800122cf  mov     esi, eax
0x1800122d1  test    eax, eax
0x1800122d3  jns     short loc_18001230D
0x1800122d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800122dc  lea     rdi, WPP_GLOBAL_Control
0x1800122e3  cmp     rcx, rdi
0x1800122e6  jz      short loc_180012306
0x1800122e8  test    byte ptr [rcx+1Ch], 4
0x1800122ec  jz      short loc_180012306
0x1800122ee  mov     rcx, [rcx+10h]
0x1800122f2  lea     r8, WPP_92b4ede73d0c3990e751819403b3312f_Traceguids
0x1800122f9  mov     edx, 38h ; '8'
0x1800122fe  mov     r9d, eax
0x180012301  call    WPP_SF_d
0x180012306  mov     eax, esi
0x180012308  jmp     loc_18001249F
0x18001230d  lea     rdi, WPP_GLOBAL_Control
0x180012314  mov     rax, [rbx]
0x180012317  lea     r9, [rsp+180h+var_120]
0x18001231c  mov     rdx, [rsp+180h+var_130]
0x180012321  xor     r8d, r8d
0x180012324  mov     rcx, rbx
0x180012327  mov     rax, [rax+20h]
0x18001232b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012330  mov     esi, eax
0x180012332  test    eax, eax
0x180012334  jnz     loc_18001246B
0x18001233a  movaps  xmm0, [rsp+180h+var_110]
0x18001233f  lea     rcx, [rsp+180h+var_140]
0x180012344  movaps  xmm1, [rbp+80h+var_100]
0x180012348  lea     r9, [rsp+180h+pv]
0x18001234d  mov     rdx, [rsp+180h+var_130]
0x180012352  lea     r8, [rsp+180h+var_120]
0x180012357  movaps  [rbp+80h+var_A0], xmm0
0x18001235b  movaps  xmm0, [rbp+80h+var_F0]
0x18001235f  mov     [rsp+180h+var_150], rcx
0x180012364  mov     rcx, rbx
0x180012367  mov     [rsp+180h+var_140], eax
0x18001236b  mov     rax, [rbx]
0x18001236e  movaps  [rbp+80h+var_90], xmm1
0x180012372  movaps  xmm1, [rbp+80h+var_E0]
0x180012376  movaps  [rbp+80h+var_80], xmm0
0x18001237a  movaps  xmm0, [rbp+80h+var_D0]
0x18001237e  mov     rax, [rax+38h]
0x180012382  movaps  [rbp+80h+var_70], xmm1
0x180012386  movaps  xmm1, xmmword ptr [rbp+80h+var_C0]
0x18001238a  movaps  [rbp+80h+var_60], xmm0
0x18001238e  movsd   xmm0, qword ptr [rbp+80h+var_C0+0Eh]
0x180012393  movaps  xmmword ptr [rbp+80h+var_50], xmm1
0x180012397  mov     [rsp+180h+var_158], 0
0x1800123a0  movsd   qword ptr [rbp+80h+var_50+0Eh], xmm0
0x1800123a5  mov     [rsp+180h+pv], 0
0x1800123ae  mov     [rsp+180h+var_160], 0
0x1800123b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800123bc  mov     esi, eax
0x1800123be  test    eax, eax
0x1800123c0  js      loc_180012463
0x1800123c6  mov     rax, [rsp+180h+pv]
0x1800123cb  mov     rcx, [rax]; pvarg
0x1800123ce  test    rcx, rcx
0x1800123d1  jz      loc_180012463
0x1800123d7  mov     eax, [rsp+180h+var_140]
0x1800123db  bt      eax, 8
0x1800123df  jnb     short loc_1800123EB
0x1800123e1  call    cs:__imp_VariantClear
0x1800123e7  mov     eax, [rsp+180h+var_140]
0x1800123eb  movzx   eax, al
0x1800123ee  sub     eax, 1
0x1800123f1  jz      short loc_18001244A
0x1800123f3  sub     eax, 1
0x1800123f6  jz      short loc_18001243A
0x1800123f8  cmp     eax, 2
0x1800123fb  jz      short loc_18001242A
0x1800123fd  mov     rcx, cs:WPP_GLOBAL_Control
0x180012404  cmp     rcx, rdi
0x180012407  jz      short loc_180012458
0x180012409  test    byte ptr [rcx+1Ch], 8
0x18001240d  jz      short loc_180012458
0x18001240f  mov     rcx, [rcx+10h]
0x180012413  lea     r9, [rbp+80h+var_A0]
0x180012417  mov     edx, 39h ; '9'
0x18001241c  lea     r8, WPP_92b4ede73d0c3990e751819403b3312f_Traceguids
0x180012423  call    WPP_SF_S
0x180012428  jmp     short loc_180012458
0x18001242a  mov     rcx, [rsp+180h+pv]
0x18001242f  mov     rcx, [rcx]; hMem
0x180012432  call    cs:__imp_LocalFree
0x180012438  jmp     short loc_180012458
0x18001243a  mov     rcx, [rsp+180h+pv]
0x18001243f  mov     rcx, [rcx]; pv
0x180012442  call    cs:__imp_CoTaskMemFree
0x180012448  jmp     short loc_180012458
0x18001244a  mov     rcx, [rsp+180h+pv]
0x18001244f  mov     rcx, [rcx]; bstrString
0x180012452  call    cs:__imp_SysFreeString
0x180012458  mov     rcx, [rsp+180h+pv]; pv
0x18001245d  call    cs:__imp_CoTaskMemFree
0x180012463  test    esi, esi
0x180012465  jz      loc_180012314
0x18001246b  mov     rcx, cs:WPP_GLOBAL_Control
0x180012472  xor     ebx, ebx
0x180012474  cmp     esi, 1
0x180012477  cmovnz  ebx, esi
0x18001247a  cmp     rcx, rdi
0x18001247d  jz      short loc_18001249D
0x18001247f  test    byte ptr [rcx+1Ch], 10h
0x180012483  jz      short loc_18001249D
0x180012485  mov     rcx, [rcx+10h]
0x180012489  lea     r8, WPP_92b4ede73d0c3990e751819403b3312f_Traceguids
0x180012490  mov     edx, 3Ah ; ':'
0x180012495  mov     r9d, ebx
0x180012498  call    WPP_SF_d
0x18001249d  mov     eax, ebx
0x18001249f  mov     rcx, [rbp+80h+var_30]
0x1800124a3  xor     rcx, rsp; StackCookie
0x1800124a6  call    __security_check_cookie
0x1800124ab  add     rsp, 168h
0x1800124b2  pop     rdi
0x1800124b3  pop     rsi
0x1800124b4  pop     rbx
0x1800124b5  pop     rbp
0x1800124b6  retn
```
