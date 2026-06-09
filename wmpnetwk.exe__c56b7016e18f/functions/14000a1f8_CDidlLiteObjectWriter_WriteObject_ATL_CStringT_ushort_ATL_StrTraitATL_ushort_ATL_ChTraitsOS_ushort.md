# CDidlLiteObjectWriter::WriteObject(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> &)

- ea: `0x14000a1f8`
- end: `0x14000aa93`
- name: `?WriteObject@CDidlLiteObjectWriter@@QEAAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@@Z`
- size: `2203`
- prototype: ``
- caller_count: `1`
- callee_count: `26`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140015390`

## callees

- `0x1400065e0`
- `0x140007020`
- `0x14000a1f8`
- `0x14000b3f0`
- `0x14000c780`
- `0x14000c9cc`
- `0x14000e5e8`
- `0x1400105a0`
- `0x140015100`
- `0x140015230`
- `0x14001b620`
- `0x140023eb0`
- `0x14003325c`
- `0x1400396dc`
- `0x14003e5f4`
- `0x140045f20`
- `0x140046c32`
- `0x140047798`
- `0x14004a500`
- `0x140054490`
- `0x140054534`
- `0x14005ea04`
- `0x14009a294`
- `0x14009ad10`
- `0x14009ad1c`
- `0x14009e010`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x14000a24a`
- `KERNEL32!GetTickCount` at `0x14000a42f`
- `KERNEL32!GetTickCount` at `0x14000a460`
- `KERNEL32!GetTickCount` at `0x14000a6b3`
- `KERNEL32!GetTickCount` at `0x14000a9f3`
- `KERNEL32!GetTickCount` at `0x14000a24a`
- `KERNEL32!GetTickCount` at `0x14000a42f`
- `KERNEL32!GetTickCount` at `0x14000a460`
- `KERNEL32!GetTickCount` at `0x14000a6b3`
- `KERNEL32!GetTickCount` at `0x14000a9f3`
- `KERNEL32!CompareStringW` at `0x14000a59b`
- `KERNEL32!CompareStringW` at `0x14000a5c1`
- `KERNEL32!CompareStringW` at `0x14000a5f7`
- `KERNEL32!CompareStringW` at `0x14000a59b`
- `KERNEL32!CompareStringW` at `0x14000a5c1`
- `KERNEL32!CompareStringW` at `0x14000a5f7`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000a3ae`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000a3ae`
- `OLEAUT32!__imp_VariantClear` at `0x14000a4a1`
- `OLEAUT32!__imp_VariantClear` at `0x14000a4a1`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CDidlLiteObjectWriter::WriteObject(_QWORD **a1, __int64 *a2)
{
  _QWORD **v3; // r12
  unsigned int v4; // esi
  WCHAR *v5; // rdi
  WCHAR *v6; // rdx
  int v7; // ebx
  __int64 v8; // r8
  __int64 v9; // rbx
  unsigned __int64 v10; // r13
  __int64 v11; // r15
  int v12; // eax
  __int64 v13; // rcx
  __int64 v14; // r12
  unsigned __int64 v15; // r15
  WCHAR *v16; // r8
  __int64 v17; // r8
  PVOID *v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // r8
  PVOID *v21; // rcx
  _QWORD *v22; // rax
  _QWORD *v23; // rax
  bool v24; // bl
  int v25; // eax
  __int64 *i; // rax
  __int64 v27; // r13
  int v28; // r15d
  __int64 v29; // rdx
  __int64 v30; // [rsp+30h] [rbp-D0h] BYREF
  PCNZWCH lpString1; // [rsp+38h] [rbp-C8h] BYREF
  VARIANTARG pvarg; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Src[264]; // [rsp+60h] [rbp-A0h] BYREF

  v3 = a1;
  v30 = (__int64)a1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_478ffc6658c23ee89d991dcff0807d2d_Traceguids);
  GetTickCount();
  v4 = *(_DWORD *)(*a2 - 16);
  v5 = (WCHAR *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  lpString1 = v5;
  pvarg.vt = 19;
  pvarg.lVal = 4;
  v7 = (*(__int64 (__fastcall **)(_QWORD *, VARIANTARG *, _QWORD, __int64, WCHAR *))(*v3[1] + 8LL))(
         v3[1],
         &pvarg,
         0,
         256,
         Src);
  if ( v7 < 0 )
    Src[0] = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    v6 = (WCHAR *)(((v7 >> 31) & 0xFFFFFFFD) + 5);
    if ( *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= (unsigned int)v6 )
      WPP_SF_dS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        29,
        (unsigned int)&WPP_478ffc6658c23ee89d991dcff0807d2d_Traceguids,
        v7,
        (__int64)Src);
  }
  if ( v7 < 0 )
    goto LABEL_31;
  v9 = -1;
  do
    ++v9;
  while ( Src[v9] );
  if ( (_DWORD)v9 )
  {
    v10 = *((unsigned int *)v5 - 4);
    v11 = (char *)Src - (char *)v5;
    v12 = *((_DWORD *)v5 - 3) - v9;
    v13 = v12 | (unsigned int)(1 - *((_DWORD *)v5 - 2));
    if ( (v12 | (1 - *((_DWORD *)v5 - 2))) < 0 )
    {
      ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(&lpString1, (unsigned int)v9);
      v5 = (WCHAR *)lpString1;
    }
    v14 = (int)v9;
    if ( !(v14 * 2) )
      goto LABEL_20;
    v15 = v11 >> 1;
    if ( v15 <= v10 )
    {
      if ( v5 )
      {
        v6 = &v5[v15];
        if ( v6 )
        {
          memmove_0(v5, v6, 2LL * (int)v9);
LABEL_20:
          if ( (int)v9 < 0 || (int)v9 > *((_DWORD *)v5 - 3) )
            ATL::AtlThrowImpl(-2147024809);
          *((_DWORD *)v5 - 4) = v9;
          v5[v14] = 0;
          v3 = (_QWORD **)v30;
          goto LABEL_23;
        }
      }
    }
    else if ( v5 )
    {
      memcpy_0(v5, Src, 2LL * (int)v9);
      goto LABEL_20;
    }
    *(_DWORD *)_o__errno(v13, v6, v8) = 22;
    invalid_parameter_noinfo();
    goto LABEL_20;
  }
  ATL::CSimpleStringT<unsigned short,0>::Empty(&lpString1);
  v5 = (WCHAR *)lpString1;
LABEL_23:
  if ( *((int *)v5 - 4) > 0 )
  {
    v16 = v5;
    if ( v5 )
    {
      while ( *v16 )
      {
        if ( *v16 == 46 )
        {
          if ( !v16 )
            break;
          v17 = v16 - v5;
          if ( (_DWORD)v17 == -1 )
            break;
          v22 = (_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::Mid(
                            &lpString1,
                            &v30,
                            (unsigned int)(v17 + 1));
          ATL::CSimpleStringT<unsigned short,0>::operator=(&lpString1, v22);
          ATL::CStringData::Release((ATL::CStringData *)(v30 - 24));
          v23 = (_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::SpanExcluding(
                            &lpString1,
                            &v30,
                            L".");
          ATL::CSimpleStringT<unsigned short,0>::operator=(&lpString1, v23);
          ATL::CStringData::Release((ATL::CStringData *)(v30 - 24));
          v5 = (WCHAR *)lpString1;
          v18 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            WPP_SF_S(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              31,
              &WPP_478ffc6658c23ee89d991dcff0807d2d_Traceguids,
              lpString1);
            v18 = (PVOID *)WPP_GLOBAL_Control;
          }
          if ( !*((_DWORD *)v5 - 4) )
          {
            v7 = -2147418113;
            if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 0x20) != 0 && *((_BYTE *)v18 + 25) >= 4u )
            {
              v29 = 32;
              goto LABEL_72;
            }
            goto LABEL_31;
          }
          CompareStringW(0x7Fu, 1u, v5, -1, L"item", -1);
          v24 = CompareStringW(0x7Fu, 1u, v5, -1, L"container", -1) == 2;
          if ( CompareStringW(0x7Fu, 1u, Src, -1, L"object.container.storageFolder", -1) == 2 )
            (*(void (__fastcall **)(_QWORD *, __int64))(*v3[3] + 32LL))(v3[3], 45);
          v30 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
          ATL::CSimpleStringT<unsigned short,0>::SetString(&v30, Src);
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::MakeUpper(&v30);
          if ( v24
            || !*((_BYTE *)v3 + 20)
            && ((unsigned int)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::Find(
                                &v30,
                                L"MUSIC",
                                0) != -1
             || (unsigned int)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::Find(
                                &v30,
                                L"AUDIO",
                                0) != -1) )
          {
            (*(void (__fastcall **)(_QWORD *, __int64))(*v3[3] + 24LL))(v3[3], 71);
            (*(void (__fastcall **)(_QWORD *, __int64))(*v3[3] + 24LL))(v3[3], 72);
          }
          ATL::CStringData::Release((ATL::CStringData *)(v30 - 24));
          ATL::CSimpleStringT<unsigned short,0>::Append(a2, "<");
          ATL::CSimpleStringT<unsigned short,0>::Append(a2, (const void **)&lpString1);
          v25 = ((__int64 (__fastcall *)(_QWORD **, __int64 *, __int64 *))(*v3)[10])(v3, a2, qword_1400C1160);
          v7 = v25;
          if ( v25 < 0 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
            {
              WPP_SF_qD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                33,
                &WPP_478ffc6658c23ee89d991dcff0807d2d_Traceguids,
                qword_1400C1160,
                v25);
            }
            goto LABEL_31;
          }
          ATL::CSimpleStringT<unsigned short,0>::Append(a2, L">");
          GetTickCount();
          for ( i = (__int64 *)qword_1400C1190; i; i = (__int64 *)v30 )
          {
            v30 = *i;
            v27 = i[2];
            v28 = ((__int64 (__fastcall *)(_QWORD **, __int64 *, __int64))(*v3)[4])(v3, a2, v27);
            if ( v28 < 0 )
            {
              if ( (*(unsigned __int8 (__fastcall **)(_QWORD *, _QWORD))(*v3[3] + 16LL))(
                     v3[3],
                     *(unsigned int *)(v27 + 8)) )
              {
                v7 = v28;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
                {
                  WPP_SF_qD(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    34,
                    &WPP_478ffc6658c23ee89d991dcff0807d2d_Traceguids,
                    v27,
                    v28);
                  goto LABEL_35;
                }
                break;
              }
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
              {
                WPP_SF_qD(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  35,
                  &WPP_478ffc6658c23ee89d991dcff0807d2d_Traceguids,
                  v27,
                  v28);
              }
            }
          }
          if ( v7 >= 0 )
          {
            ATL::CSimpleStringT<unsigned short,0>::Append(a2, L"</");
            ATL::CSimpleStringT<unsigned short,0>::Append(a2, (const void **)&lpString1);
            ATL::CSimpleStringT<unsigned short,0>::Append(a2, L">");
          }
          goto LABEL_35;
        }
        ++v16;
      }
    }
  }
  v7 = -2147418113;
  v18 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    v29 = 30;
LABEL_72:
    WPP_SF_S(v18[2], v29, &WPP_478ffc6658c23ee89d991dcff0807d2d_Traceguids, Src);
  }
LABEL_31:
  GetTickCount();
LABEL_35:
  GetTickCount();
  v21 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_qdd(*((_QWORD *)WPP_GLOBAL_Control + 2), v19, v20, *a2, v4, v7);
    v21 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v7 < 0 && *(_DWORD *)(*a2 - 16) > v4 )
  {
    ATL::CSimpleStringT<unsigned short,0>::SetLength(a2, v4);
    v21 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_42;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_DDd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        38,
        &WPP_478ffc6658c23ee89d991dcff0807d2d_Traceguids,
        *(unsigned int *)(*a2 - 16),
        v4,
        v7);
      v21 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  if ( v21 != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)v21 + 28) & 2) != 0 )
    {
      WPP_SF_(v21[2], 39, &WPP_478ffc6658c23ee89d991dcff0807d2d_Traceguids);
      v21 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v21 != &WPP_GLOBAL_Control && (*((_BYTE *)v21 + 28) & 2) != 0 && *((_BYTE *)v21 + 25) >= 5u )
      WPP_SF_SS((TRACEHANDLE)v21[2], *a2);
  }
LABEL_42:
  VariantClear(&pvarg);
  ATL::CStringData::Release((ATL::CStringData *)(v5 - 12));
}

```

## disassembly

```asm
0x14000a1f8  mov     [rsp-8+arg_10], rbx
0x14000a1fd  push    rbp
0x14000a1fe  push    rsi
0x14000a1ff  push    rdi
0x14000a200  push    r12
0x14000a202  push    r13
0x14000a204  push    r14
0x14000a206  push    r15
0x14000a208  lea     rbp, [rsp-180h]
0x14000a210  sub     rsp, 280h
0x14000a217  mov     rax, cs:__security_cookie
0x14000a21e  xor     rax, rsp
0x14000a221  mov     [rbp+1B0h+var_40], rax
0x14000a228  mov     r14, rdx
0x14000a22b  mov     r12, rcx
0x14000a22e  mov     [rsp+2B0h+var_280], rcx
0x14000a233  lea     r15, WPP_GLOBAL_Control
0x14000a23a  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a241  cmp     rcx, r15
0x14000a244  jnz     loc_14000A840
0x14000a24a  call    cs:__imp_GetTickCount
0x14000a250  mov     rax, [r14]
0x14000a253  mov     esi, [rax-10h]
0x14000a256  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000a25d  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000a264  mov     rax, [rax+18h]
0x14000a268  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a26d  lea     rdi, [rax+18h]
0x14000a271  mov     [rsp+2B0h+lpString1], rdi
0x14000a276  mov     eax, 13h
0x14000a27b  mov     word ptr [rsp+2B0h+pvarg], ax
0x14000a280  mov     dword ptr [rsp+2B0h+pvarg+8], 4
0x14000a288  mov     rcx, [r12+8]
0x14000a28d  mov     rax, [rcx]
0x14000a290  lea     rdx, [rsp+2B0h+Src]
0x14000a295  mov     [rsp+2B0h+lpString2], rdx
0x14000a29a  mov     r9d, 100h
0x14000a2a0  xor     r8d, r8d
0x14000a2a3  lea     rdx, [rsp+2B0h+pvarg]
0x14000a2a8  mov     rax, [rax+8]
0x14000a2ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a2b1  mov     ebx, eax
0x14000a2b3  xor     r13d, r13d
0x14000a2b6  test    eax, eax
0x14000a2b8  js      loc_14000A864
0x14000a2be  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a2c5  cmp     rcx, r15
0x14000a2c8  jnz     loc_14000A355
0x14000a2ce  test    ebx, ebx
0x14000a2d0  js      loc_14000A568
0x14000a2d6  lea     rax, [rsp+2B0h+Src]
0x14000a2db  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14000a2df  inc     rbx
0x14000a2e2  cmp     [rax+rbx*2], r13w
0x14000a2e7  jnz     short loc_14000A2DF
0x14000a2e9  test    ebx, ebx
0x14000a2eb  jz      loc_14000A39D
0x14000a2f1  mov     r13d, [rdi-10h]
0x14000a2f5  lea     r15, [rsp+2B0h+Src]
0x14000a2fa  sub     r15, rdi
0x14000a2fd  mov     ecx, 1
0x14000a302  sub     ecx, [rdi-8]
0x14000a305  mov     eax, [rdi-0Ch]
0x14000a308  sub     eax, ebx
0x14000a30a  or      ecx, eax
0x14000a30c  jge     short loc_14000A31F
0x14000a30e  mov     edx, ebx
0x14000a310  lea     rcx, [rsp+2B0h+lpString1]
0x14000a315  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x14000a31a  mov     rdi, [rsp+2B0h+lpString1]
0x14000a31f  movsxd  rax, ebx
0x14000a322  lea     r12, [rax+rax]
0x14000a326  test    r12, r12
0x14000a329  jz      loc_14000A86F
0x14000a32f  sar     r15, 1
0x14000a332  cmp     r15, r13
0x14000a335  jbe     loc_14000A7EE
0x14000a33b  xor     r13d, r13d
0x14000a33e  test    rdi, rdi
0x14000a341  jz      short loc_14000A3AE
0x14000a343  mov     r8, r12; Size
0x14000a346  lea     rdx, [rsp+2B0h+Src]; Src
0x14000a34b  mov     rcx, rdi; void *
0x14000a34e  call    memcpy_0
0x14000a353  jmp     short loc_14000A3BF
0x14000a355  test    byte ptr [rcx+1Ch], 20h
0x14000a359  jz      loc_14000A2CE
0x14000a35f  mov     edx, ebx
0x14000a361  sar     edx, 1Fh
0x14000a364  and     edx, 0FFFFFFFDh
0x14000a367  add     edx, 5
0x14000a36a  movzx   eax, byte ptr [rcx+19h]
0x14000a36e  cmp     eax, edx
0x14000a370  jb      loc_14000A2CE
0x14000a376  mov     edx, 1Dh
0x14000a37b  lea     rax, [rsp+2B0h+Src]
0x14000a380  mov     [rsp+2B0h+lpString2], rax
0x14000a385  mov     r9d, ebx
0x14000a388  lea     r8, WPP_478ffc6658c23ee89d991dcff0807d2d_Traceguids
0x14000a38f  mov     rcx, [rcx+10h]
0x14000a393  call    WPP_SF_dS
0x14000a398  jmp     loc_14000A2CE
0x14000a39d  lea     rcx, [rsp+2B0h+lpString1]
0x14000a3a2  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x14000a3a7  mov     rdi, [rsp+2B0h+lpString1]
0x14000a3ac  jmp     short loc_14000A3E4
0x14000a3ae  call    cs:__imp__o__errno
0x14000a3b4  mov     dword ptr [rax], 16h
0x14000a3ba  call    _invalid_parameter_noinfo
0x14000a3bf  test    ebx, ebx
0x14000a3c1  js      loc_14000A8E0
0x14000a3c7  cmp     ebx, [rdi-0Ch]
0x14000a3ca  jg      loc_14000A8E0
0x14000a3d0  mov     [rdi-10h], ebx
0x14000a3d3  mov     [r12+rdi], r13w
0x14000a3d8  mov     r12, [rsp+2B0h+var_280]
0x14000a3dd  lea     r15, WPP_GLOBAL_Control
0x14000a3e4  cmp     [rdi-10h], r13d
0x14000a3e8  jle     short loc_14000A41A
0x14000a3ea  mov     r8, rdi
0x14000a3ed  test    rdi, rdi
0x14000a3f0  jz      short loc_14000A41A
0x14000a3f2  cmp     [r8], r13w
0x14000a3f6  jz      short loc_14000A41A
0x14000a3f8  cmp     word ptr [r8], 2Eh ; '.'
0x14000a3fd  jz      short loc_14000A405
0x14000a3ff  add     r8, 2
0x14000a403  jmp     short loc_14000A3F2
0x14000a405  test    r8, r8
0x14000a408  jz      short loc_14000A41A
0x14000a40a  sub     r8, rdi
0x14000a40d  sar     r8, 1
0x14000a410  cmp     r8d, 0FFFFFFFFh
0x14000a414  jnz     loc_14000A4DC
0x14000a41a  mov     ebx, 8000FFFFh
0x14000a41f  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a426  cmp     rcx, r15
0x14000a429  jnz     loc_14000A8D1
0x14000a42f  call    cs:__imp_GetTickCount
0x14000a435  jmp     short loc_14000A460
0x14000a437  mov     ebx, r15d
0x14000a43a  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a441  lea     rax, WPP_GLOBAL_Control
0x14000a448  cmp     rcx, rax
0x14000a44b  jnz     loc_14000A9BD
0x14000a451  test    ebx, ebx
0x14000a453  jns     loc_14000A754
0x14000a459  lea     r15, WPP_GLOBAL_Control
0x14000a460  call    cs:__imp_GetTickCount
0x14000a466  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a46d  cmp     rcx, r15
0x14000a470  jz      short loc_14000A47C
0x14000a472  test    byte ptr [rcx+1Ch], 2
0x14000a476  jnz     loc_14000A9FE
0x14000a47c  test    ebx, ebx
0x14000a47e  js      loc_14000A784
0x14000a484  cmp     rcx, r15
0x14000a487  jz      short loc_14000A49C
0x14000a489  test    byte ptr [rcx+1Ch], 2
0x14000a48d  jnz     loc_14000AA28
0x14000a493  cmp     rcx, r15
0x14000a496  jnz     loc_14000AA49
0x14000a49c  lea     rcx, [rsp+2B0h+pvarg]; pvarg
0x14000a4a1  call    cs:__imp_VariantClear
0x14000a4a7  nop
0x14000a4a8  lea     rcx, [rdi-18h]; this
0x14000a4ac  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x14000a4b1  nop
0x14000a4b2  mov     rcx, [rbp+1B0h+var_40]
0x14000a4b9  xor     rcx, rsp; StackCookie
0x14000a4bc  call    __security_check_cookie
0x14000a4c1  mov     rbx, [rsp+2B0h+arg_10]
0x14000a4c9  add     rsp, 280h
0x14000a4d0  pop     r15
0x14000a4d2  pop     r14
0x14000a4d4  pop     r13
0x14000a4d6  pop     r12
0x14000a4d8  pop     rdi
0x14000a4d9  pop     rsi
0x14000a4da  pop     rbp
0x14000a4db  retn
0x14000a4dc  inc     r8d
0x14000a4df  lea     rdx, [rsp+2B0h+var_280]
0x14000a4e4  lea     rcx, [rsp+2B0h+lpString1]
0x14000a4e9  call    ?Mid@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEBA?AV12@H@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::Mid(int)
0x14000a4ee  mov     rdx, rax
0x14000a4f1  lea     rcx, [rsp+2B0h+lpString1]
0x14000a4f6  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x14000a4fb  nop
0x14000a4fc  mov     rcx, [rsp+2B0h+var_280]
0x14000a501  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x14000a505  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x14000a50a  nop
0x14000a50b  lea     r8, asc_1400A2B94; "."
0x14000a512  lea     rdx, [rsp+2B0h+var_280]
0x14000a517  lea     rcx, [rsp+2B0h+lpString1]
0x14000a51c  call    ?SpanExcluding@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEBA?AV12@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::SpanExcluding(ushort const *)
0x14000a521  mov     rdx, rax
0x14000a524  lea     rcx, [rsp+2B0h+lpString1]
0x14000a529  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x14000a52e  nop
0x14000a52f  mov     rcx, [rsp+2B0h+var_280]
0x14000a534  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x14000a538  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x14000a53d  nop
0x14000a53e  mov     rdi, [rsp+2B0h+lpString1]
0x14000a543  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a54a  cmp     rcx, r15
0x14000a54d  jz      short loc_14000A559
0x14000a54f  test    byte ptr [rcx+1Ch], 20h
0x14000a553  jnz     loc_14000A877
0x14000a559  cmp     [rdi-10h], r13d
0x14000a55d  jz      loc_14000A8A5
0x14000a563  mov     r15b, r13b
0x14000a566  jmp     short loc_14000A573
0x14000a568  mov     r15b, r13b
0x14000a56b  test    ebx, ebx
0x14000a56d  js      loc_14000A9F3
0x14000a573  mov     [rsp+2B0h+cchCount2], 0FFFFFFFFh; cchCount2
0x14000a57b  lea     rax, aItem; "item"
0x14000a582  mov     [rsp+2B0h+lpString2], rax; lpString2
0x14000a587  or      r9d, 0FFFFFFFFh; cchCount1
0x14000a58b  mov     r8, rdi; lpString1
0x14000a58e  lea     ebx, [r9+2]
0x14000a592  mov     edx, ebx; dwCmpFlags
0x14000a594  lea     r13d, [rbx+7Eh]
0x14000a598  mov     ecx, r13d; Locale
0x14000a59b  call    cs:__imp_CompareStringW
0x14000a5a1  mov     [rsp+2B0h+cchCount2], 0FFFFFFFFh; cchCount2
0x14000a5a9  lea     rax, aContainer; "container"
0x14000a5b0  mov     [rsp+2B0h+lpString2], rax; lpString2
0x14000a5b5  or      r9d, 0FFFFFFFFh; cchCount1
0x14000a5b9  mov     r8, rdi; lpString1
0x14000a5bc  mov     edx, ebx; dwCmpFlags
0x14000a5be  mov     ecx, r13d; Locale
0x14000a5c1  call    cs:__imp_CompareStringW
0x14000a5c7  movzx   ebx, r15b
0x14000a5cb  cmp     eax, 2
0x14000a5ce  lea     ecx, [r13-7Eh]
0x14000a5d2  cmovz   ebx, ecx
0x14000a5d5  mov     [rsp+2B0h+cchCount2], 0FFFFFFFFh; cchCount2
0x14000a5dd  lea     rax, aObjectContaine_1; "object.container.storageFolder"
0x14000a5e4  mov     [rsp+2B0h+lpString2], rax; lpString2
0x14000a5e9  or      r9d, 0FFFFFFFFh; cchCount1
0x14000a5ed  lea     r8, [rsp+2B0h+Src]; lpString1
0x14000a5f2  mov     edx, ecx; dwCmpFlags
0x14000a5f4  mov     ecx, r13d; Locale
0x14000a5f7  call    cs:__imp_CompareStringW
0x14000a5fd  cmp     eax, 2
0x14000a600  jz      loc_14000A8EB
0x14000a606  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000a60d  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000a614  mov     rax, [rax+18h]
0x14000a618  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a61d  add     rax, 18h
0x14000a621  mov     [rsp+2B0h+var_280], rax
0x14000a626  lea     rdx, [rsp+2B0h+Src]
0x14000a62b  lea     rcx, [rsp+2B0h+var_280]
0x14000a630  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x14000a635  lea     rcx, [rsp+2B0h+var_280]
0x14000a63a  call    ?MakeUpper@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAAAEAV12@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::MakeUpper(void)
0x14000a63f  xor     r13d, r13d
0x14000a642  test    bl, bl
0x14000a644  jnz     loc_14000A93C
0x14000a64a  cmp     [r12+14h], r13b
0x14000a64f  jz      loc_14000A906
0x14000a655  mov     rcx, [rsp+2B0h+var_280]
0x14000a65a  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x14000a65e  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x14000a663  nop
0x14000a664  lea     rdx, ?s_chBase64EncodingTable@?1??Base64Encode@ATL@@YAHPEBEHPEADPEAHK@Z@4QBDB+40h; "<"
0x14000a66b  mov     rcx, r14
0x14000a66e  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *)
0x14000a673  lea     rdx, [rsp+2B0h+lpString1]
0x14000a678  mov     rcx, r14
0x14000a67b  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXAEBV12@@Z; ATL::CSimpleStringT<ushort,0>::Append(ATL::CSimpleStringT<ushort,0> const &)
0x14000a680  mov     rax, [r12]
0x14000a684  lea     r8, qword_1400C1160
0x14000a68b  mov     rdx, r14
0x14000a68e  mov     rcx, r12
0x14000a691  mov     rax, [rax+50h]
0x14000a695  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a69a  mov     ebx, eax
0x14000a69c  test    eax, eax
0x14000a69e  js      loc_14000A96D
0x14000a6a4  lea     rdx, asc_1400A3CBC; ">"
0x14000a6ab  mov     rcx, r14
0x14000a6ae  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *)
0x14000a6b3  call    cs:__imp_GetTickCount
0x14000a6b9  mov     rax, cs:qword_1400C1190
0x14000a6c0  test    rax, rax
0x14000a6c3  jz      loc_14000A451
0x14000a6c9  mov     rcx, [rax]
0x14000a6cc  mov     [rsp+2B0h+var_280], rcx
0x14000a6d1  mov     r13, [rax+10h]
0x14000a6d5  mov     rax, [r12]
0x14000a6d9  mov     r8, r13
0x14000a6dc  mov     rdx, r14
0x14000a6df  mov     rcx, r12
0x14000a6e2  mov     rax, [rax+20h]
  ... truncated ...
```
