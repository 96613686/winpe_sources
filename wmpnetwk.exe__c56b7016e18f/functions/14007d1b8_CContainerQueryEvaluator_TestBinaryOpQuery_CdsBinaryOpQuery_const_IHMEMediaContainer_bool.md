# CContainerQueryEvaluator::TestBinaryOpQuery(CdsBinaryOpQuery const *,IHMEMediaContainer *,bool *)

- ea: `0x14007d1b8`
- end: `0x14007d4e5`
- name: `?TestBinaryOpQuery@CContainerQueryEvaluator@@IEAAJPEBVCdsBinaryOpQuery@@PEAUIHMEMediaContainer@@PEA_N@Z`
- size: `813`
- prototype: `__int64 __fastcall(CContainerQueryEvaluator *__hidden this, const struct CdsBinaryOpQuery *, struct IHMEMediaContainer *, bool *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1400761e0`

## callees

- `0x14000c920`
- `0x140034e14`
- `0x140074980`
- `0x14007d1b8`
- `0x140081dc0`
- `0x14009e010`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x14007d21d`
- `KERNEL32!CompareStringW` at `0x14007d261`
- `KERNEL32!CompareStringW` at `0x14007d21d`
- `KERNEL32!CompareStringW` at `0x14007d261`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CContainerQueryEvaluator::TestBinaryOpQuery(
        CContainerQueryEvaluator *this,
        const struct CdsBinaryOpQuery *a2,
        struct IHMEMediaContainer *a3,
        bool *a4)
{
  unsigned int v7; // esi
  int v8; // eax
  PCNZWCH *v9; // rax
  bool v10; // al
  PCNZWCH *v11; // rax
  CContainerQueryEvaluator **v12; // rcx
  int v13; // ebx
  const unsigned __int16 **v14; // rax
  CContainerQueryEvaluator *v15; // rcx
  int v16; // ebx
  const unsigned __int16 **v17; // rax
  CContainerQueryEvaluator *v18; // rcx
  int v19; // eax
  char v20; // al
  int v21; // eax
  int v22; // ebx
  bool v23; // zf
  __int64 v24; // rax
  CContainerQueryEvaluator *v26; // [rsp+60h] [rbp+30h] BYREF
  char v27; // [rsp+68h] [rbp+38h] BYREF

  v26 = this;
  v7 = 0;
  if ( *((_DWORD *)a2 + 8) != 3 )
  {
    if ( *((_DWORD *)a2 + 8) != 17 )
    {
      if ( *((_DWORD *)a2 + 8) != 1 )
      {
        *a4 = 0;
        return v7;
      }
      if ( *((_DWORD *)a2 + 9) != 1 )
        return (unsigned int)-2147220628;
      v24 = (*(__int64 (__fastcall **)(struct IHMEMediaContainer *))(*(_QWORD *)a3 + 56LL))(a3);
      v20 = ATL::operator==((char *)a2 + 40, v24);
      goto LABEL_20;
    }
    if ( *((_DWORD *)a2 + 9) == 1 )
    {
      LODWORD(v26) = 0;
      if ( !CShellPropertyThunk::GetObjectClassForString(
              *((const unsigned __int16 **)a2 + 5),
              (enum WMPContentProviderObjectClasses *)&v26) )
        return (unsigned int)-2147220628;
      v19 = (*(__int64 (__fastcall **)(struct IHMEMediaContainer *))(*(_QWORD *)a3 + 48LL))(a3);
      v20 = (_DWORD)v26 == v19;
LABEL_20:
      *a4 = v20;
      return v7;
    }
    if ( *((_DWORD *)a2 + 9) == 2 )
    {
      LODWORD(v26) = 0;
      if ( !CShellPropertyThunk::GetObjectClassForString(
              *((const unsigned __int16 **)a2 + 5),
              (enum WMPContentProviderObjectClasses *)&v26) )
        return (unsigned int)-2147220628;
      v21 = (*(__int64 (__fastcall **)(struct IHMEMediaContainer *))(*(_QWORD *)a3 + 48LL))(a3);
      v20 = (_DWORD)v26 != v21;
      goto LABEL_20;
    }
    if ( *((_DWORD *)a2 + 9) != 9 )
      return (unsigned int)-2147220628;
    LODWORD(v26) = 0;
    if ( !CShellPropertyThunk::GetObjectClassForString(
            *((const unsigned __int16 **)a2 + 5),
            (enum WMPContentProviderObjectClasses *)&v26) )
      return (unsigned int)-2147220628;
    v22 = (int)v26;
    if ( (_DWORD)v26 == 11
      || v22 == (*(unsigned int (__fastcall **)(struct IHMEMediaContainer *))(*(_QWORD *)a3 + 48LL))(a3) )
    {
      goto LABEL_24;
    }
    switch ( v22 )
    {
      case 12:
        if ( (*(unsigned int (__fastcall **)(struct IHMEMediaContainer *))(*(_QWORD *)a3 + 48LL))(a3) == 13
          || (*(unsigned int (__fastcall **)(struct IHMEMediaContainer *))(*(_QWORD *)a3 + 48LL))(a3) == 14 )
        {
          goto LABEL_24;
        }
        v23 = (*(unsigned int (__fastcall **)(struct IHMEMediaContainer *))(*(_QWORD *)a3 + 48LL))(a3) == 15;
        break;
      case 16:
        if ( (*(unsigned int (__fastcall **)(struct IHMEMediaContainer *))(*(_QWORD *)a3 + 48LL))(a3) == 17 )
          goto LABEL_24;
        v23 = (*(unsigned int (__fastcall **)(struct IHMEMediaContainer *))(*(_QWORD *)a3 + 48LL))(a3) == 18;
        break;
      case 20:
        if ( (*(unsigned int (__fastcall **)(struct IHMEMediaContainer *))(*(_QWORD *)a3 + 48LL))(a3) == 21 )
        {
LABEL_24:
          *a4 = 1;
          return v7;
        }
        v23 = (*(unsigned int (__fastcall **)(struct IHMEMediaContainer *))(*(_QWORD *)a3 + 48LL))(a3) == 22;
        break;
      default:
        goto LABEL_31;
    }
    if ( !v23 )
    {
LABEL_31:
      *a4 = 0;
      return v7;
    }
    goto LABEL_24;
  }
  v8 = *((_DWORD *)a2 + 9);
  if ( v8 != 1 )
  {
    switch ( v8 )
    {
      case 2:
        v11 = (PCNZWCH *)(*(__int64 (__fastcall **)(struct IHMEMediaContainer *, CContainerQueryEvaluator **))(*(_QWORD *)a3 + 24LL))(
                           a3,
                           &v26);
        v10 = CompareStringW(0x800u, 0x10u, *((PCNZWCH *)a2 + 5), -1, *v11, -1) != 2;
        goto LABEL_6;
      case 7:
        v13 = *(_DWORD *)(*(_QWORD *)(*(__int64 (__fastcall **)(struct IHMEMediaContainer *, char *))(*(_QWORD *)a3 + 24LL))(
                                       a3,
                                       &v27)
                        - 16LL);
        v14 = (const unsigned __int16 **)(*(__int64 (__fastcall **)(struct IHMEMediaContainer *, CContainerQueryEvaluator **))(*(_QWORD *)a3 + 24LL))(
                                           a3,
                                           &v26);
        *a4 = CContainerQueryEvaluator::ContainsIgnoreCase(
                v15,
                *((const unsigned __int16 **)a2 + 5),
                *(_DWORD *)(*((_QWORD *)a2 + 5) - 16LL),
                *v14,
                v13);
        ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v26);
LABEL_11:
        v12 = (CContainerQueryEvaluator **)&v27;
        goto LABEL_12;
      case 8:
        v16 = *(_DWORD *)(*(_QWORD *)(*(__int64 (__fastcall **)(struct IHMEMediaContainer *, char *))(*(_QWORD *)a3 + 24LL))(
                                       a3,
                                       &v27)
                        - 16LL);
        v17 = (const unsigned __int16 **)(*(__int64 (__fastcall **)(struct IHMEMediaContainer *, CContainerQueryEvaluator **))(*(_QWORD *)a3 + 24LL))(
                                           a3,
                                           &v26);
        *a4 = !CContainerQueryEvaluator::ContainsIgnoreCase(
                 v18,
                 *((const unsigned __int16 **)a2 + 5),
                 *(_DWORD *)(*((_QWORD *)a2 + 5) - 16LL),
                 *v17,
                 v16);
        ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v26);
        goto LABEL_11;
    }
    return (unsigned int)-2147220628;
  }
  v9 = (PCNZWCH *)(*(__int64 (__fastcall **)(struct IHMEMediaContainer *, CContainerQueryEvaluator **))(*(_QWORD *)a3 + 24LL))(
                    a3,
                    &v26);
  v10 = CompareStringW(0x800u, 0x10u, *((PCNZWCH *)a2 + 5), -1, *v9, -1) == 2;
LABEL_6:
  *a4 = v10;
  v12 = &v26;
LABEL_12:
  ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(v12);
  return v7;
}

```

## disassembly

```asm
0x14007d1b8  mov     [rsp-28h+arg_10], rbx
0x14007d1bd  mov     [rsp-28h+arg_0], rcx
0x14007d1c2  push    rbp
0x14007d1c3  push    rsi
0x14007d1c4  push    rdi
0x14007d1c5  push    r14
0x14007d1c7  push    r15
0x14007d1c9  mov     rbp, rsp
0x14007d1cc  sub     rsp, 30h
0x14007d1d0  mov     r14, r9
0x14007d1d3  mov     rdi, r8
0x14007d1d6  mov     r15, rdx
0x14007d1d9  xor     esi, esi
0x14007d1db  cmp     dword ptr [rdx+20h], 3
0x14007d1df  jnz     loc_14007D335
0x14007d1e5  mov     eax, [rdx+24h]
0x14007d1e8  cmp     eax, 1
0x14007d1eb  jnz     short loc_14007D22B
0x14007d1ed  mov     rax, [r8]
0x14007d1f0  lea     rdx, [rbp+arg_0]
0x14007d1f4  mov     rcx, r8
0x14007d1f7  mov     rax, [rax+18h]
0x14007d1fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007d200  or      r9d, 0FFFFFFFFh; cchCount1
0x14007d204  mov     [rsp+30h+cchCount2], r9d; cchCount2
0x14007d209  mov     rax, [rax]
0x14007d20c  mov     [rsp+30h+lpString2], rax; lpString2
0x14007d211  mov     r8, [r15+28h]; lpString1
0x14007d215  lea     edx, [rsi+10h]; dwCmpFlags
0x14007d218  mov     ecx, 800h; Locale
0x14007d21d  call    cs:__imp_CompareStringW
0x14007d223  cmp     eax, 2
0x14007d226  setz    al
0x14007d229  jmp     short loc_14007D26D
0x14007d22b  cmp     eax, 2
0x14007d22e  jnz     short loc_14007D279
0x14007d230  mov     rax, [r8]
0x14007d233  lea     rdx, [rbp+arg_0]
0x14007d237  mov     rcx, rdi
0x14007d23a  mov     rax, [rax+18h]
0x14007d23e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007d243  or      r9d, 0FFFFFFFFh; cchCount1
0x14007d247  mov     [rsp+30h+cchCount2], r9d; cchCount2
0x14007d24c  mov     rax, [rax]
0x14007d24f  mov     [rsp+30h+lpString2], rax; lpString2
0x14007d254  mov     r8, [r15+28h]; lpString1
0x14007d258  lea     edx, [r9+11h]; dwCmpFlags
0x14007d25c  mov     ecx, 800h; Locale
0x14007d261  call    cs:__imp_CompareStringW
0x14007d267  cmp     eax, 2
0x14007d26a  setnz   al
0x14007d26d  mov     [r14], al
0x14007d270  lea     rcx, [rbp+arg_0]
0x14007d274  jmp     loc_14007D32B
0x14007d279  cmp     eax, 7
0x14007d27c  jnz     short loc_14007D2CE
0x14007d27e  mov     rax, [r8]
0x14007d281  lea     rdx, [rbp+arg_8]
0x14007d285  mov     rcx, rdi
0x14007d288  mov     rax, [rax+18h]
0x14007d28c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007d291  nop
0x14007d292  mov     rax, [rax]
0x14007d295  mov     ebx, [rax-10h]
0x14007d298  mov     rax, [rdi]
0x14007d29b  lea     rdx, [rbp+arg_0]
0x14007d29f  mov     rcx, rdi
0x14007d2a2  mov     rax, [rax+18h]
0x14007d2a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007d2ab  mov     rdx, [r15+28h]; unsigned __int16 *
0x14007d2af  mov     dword ptr [rsp+30h+lpString2], ebx; int
0x14007d2b3  mov     r9, [rax]; unsigned __int16 *
0x14007d2b6  mov     r8d, [rdx-10h]; int
0x14007d2ba  call    ?ContainsIgnoreCase@CContainerQueryEvaluator@@IEAA_NPEBGH0H@Z; CContainerQueryEvaluator::ContainsIgnoreCase(ushort const *,int,ushort const *,int)
0x14007d2bf  mov     [r14], al
0x14007d2c2  lea     rcx, [rbp+arg_0]
0x14007d2c6  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x14007d2cb  nop
0x14007d2cc  jmp     short loc_14007D327
0x14007d2ce  cmp     eax, 8
0x14007d2d1  jnz     loc_14007D4C8
0x14007d2d7  mov     rax, [r8]
0x14007d2da  lea     rdx, [rbp+arg_8]
0x14007d2de  mov     rcx, rdi
0x14007d2e1  mov     rax, [rax+18h]
0x14007d2e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007d2ea  nop
0x14007d2eb  mov     rax, [rax]
0x14007d2ee  mov     ebx, [rax-10h]
0x14007d2f1  mov     rax, [rdi]
0x14007d2f4  lea     rdx, [rbp+arg_0]
0x14007d2f8  mov     rcx, rdi
0x14007d2fb  mov     rax, [rax+18h]
0x14007d2ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007d304  mov     rdx, [r15+28h]; unsigned __int16 *
0x14007d308  mov     dword ptr [rsp+30h+lpString2], ebx; int
0x14007d30c  mov     r9, [rax]; unsigned __int16 *
0x14007d30f  mov     r8d, [rdx-10h]; int
0x14007d313  call    ?ContainsIgnoreCase@CContainerQueryEvaluator@@IEAA_NPEBGH0H@Z; CContainerQueryEvaluator::ContainsIgnoreCase(ushort const *,int,ushort const *,int)
0x14007d318  xor     al, 1
0x14007d31a  mov     [r14], al
0x14007d31d  lea     rcx, [rbp+arg_0]
0x14007d321  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x14007d326  nop
0x14007d327  lea     rcx, [rbp+arg_8]
0x14007d32b  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x14007d330  jmp     loc_14007D4D2
0x14007d335  cmp     dword ptr [rdx+20h], 11h
0x14007d339  jnz     loc_14007D49C
0x14007d33f  cmp     dword ptr [rdx+24h], 1
0x14007d343  jnz     short loc_14007D374
0x14007d345  mov     dword ptr [rbp+arg_0], esi
0x14007d348  lea     rdx, [rbp+arg_0]; enum WMPContentProviderObjectClasses *
0x14007d34c  mov     rcx, [r15+28h]; unsigned __int16 *
0x14007d350  call    ?GetObjectClassForString@CShellPropertyThunk@@SA_NPEBGPEAW4WMPContentProviderObjectClasses@@@Z; CShellPropertyThunk::GetObjectClassForString(ushort const *,WMPContentProviderObjectClasses *)
0x14007d355  test    al, al
0x14007d357  jz      loc_14007D4C8
0x14007d35d  mov     rax, [rdi]
0x14007d360  mov     rcx, rdi
0x14007d363  mov     rax, [rax+30h]
0x14007d367  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007d36c  cmp     dword ptr [rbp+arg_0], eax
0x14007d36f  setz    al
0x14007d372  jmp     short loc_14007D3A7
0x14007d374  cmp     dword ptr [rdx+24h], 2
0x14007d378  jnz     short loc_14007D3AF
0x14007d37a  mov     dword ptr [rbp+arg_0], esi
0x14007d37d  lea     rdx, [rbp+arg_0]; enum WMPContentProviderObjectClasses *
0x14007d381  mov     rcx, [r15+28h]; unsigned __int16 *
0x14007d385  call    ?GetObjectClassForString@CShellPropertyThunk@@SA_NPEBGPEAW4WMPContentProviderObjectClasses@@@Z; CShellPropertyThunk::GetObjectClassForString(ushort const *,WMPContentProviderObjectClasses *)
0x14007d38a  test    al, al
0x14007d38c  jz      loc_14007D4C8
0x14007d392  mov     rax, [rdi]
0x14007d395  mov     rcx, rdi
0x14007d398  mov     rax, [rax+30h]
0x14007d39c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007d3a1  cmp     dword ptr [rbp+arg_0], eax
0x14007d3a4  setnz   al
0x14007d3a7  mov     [r14], al
0x14007d3aa  jmp     loc_14007D4D2
0x14007d3af  cmp     dword ptr [rdx+24h], 9
0x14007d3b3  jnz     loc_14007D4C8
0x14007d3b9  mov     dword ptr [rbp+arg_0], esi
0x14007d3bc  lea     rdx, [rbp+arg_0]; enum WMPContentProviderObjectClasses *
0x14007d3c0  mov     rcx, [r15+28h]; unsigned __int16 *
0x14007d3c4  call    ?GetObjectClassForString@CShellPropertyThunk@@SA_NPEBGPEAW4WMPContentProviderObjectClasses@@@Z; CShellPropertyThunk::GetObjectClassForString(ushort const *,WMPContentProviderObjectClasses *)
0x14007d3c9  test    al, al
0x14007d3cb  jz      loc_14007D4C8
0x14007d3d1  mov     ebx, dword ptr [rbp+arg_0]
0x14007d3d4  cmp     ebx, 0Bh
0x14007d3d7  jnz     short loc_14007D3E2
0x14007d3d9  mov     byte ptr [r14], 1
0x14007d3dd  jmp     loc_14007D4D2
0x14007d3e2  mov     rax, [rdi]
0x14007d3e5  mov     rcx, rdi
0x14007d3e8  mov     rax, [rax+30h]
0x14007d3ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007d3f1  cmp     ebx, eax
0x14007d3f3  jz      short loc_14007D3D9
0x14007d3f5  cmp     ebx, 0Ch
0x14007d3f8  jnz     short loc_14007D43E
0x14007d3fa  mov     rax, [rdi]
0x14007d3fd  mov     rcx, rdi
0x14007d400  mov     rax, [rax+30h]
0x14007d404  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007d409  cmp     eax, 0Dh
0x14007d40c  jz      short loc_14007D3D9
0x14007d40e  mov     rax, [rdi]
0x14007d411  mov     rcx, rdi
0x14007d414  mov     rax, [rax+30h]
0x14007d418  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007d41d  cmp     eax, 0Eh
0x14007d420  jz      short loc_14007D3D9
0x14007d422  mov     rax, [rdi]
0x14007d425  mov     rcx, rdi
0x14007d428  mov     rax, [rax+30h]
0x14007d42c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007d431  cmp     eax, 0Fh
0x14007d434  jz      short loc_14007D3D9
0x14007d436  mov     [r14], sil
0x14007d439  jmp     loc_14007D4D2
0x14007d43e  cmp     ebx, 10h
0x14007d441  jnz     short loc_14007D46B
0x14007d443  mov     rax, [rdi]
0x14007d446  mov     rcx, rdi
0x14007d449  mov     rax, [rax+30h]
0x14007d44d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007d452  cmp     eax, 11h
0x14007d455  jz      short loc_14007D3D9
0x14007d457  mov     rax, [rdi]
0x14007d45a  mov     rcx, rdi
0x14007d45d  mov     rax, [rax+30h]
0x14007d461  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007d466  cmp     eax, 12h
0x14007d469  jmp     short loc_14007D434
0x14007d46b  cmp     ebx, 14h
0x14007d46e  jnz     short loc_14007D436
0x14007d470  mov     rax, [rdi]
0x14007d473  mov     rcx, rdi
0x14007d476  mov     rax, [rax+30h]
0x14007d47a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007d47f  cmp     eax, 15h
0x14007d482  jz      loc_14007D3D9
0x14007d488  mov     rax, [rdi]
0x14007d48b  mov     rcx, rdi
0x14007d48e  mov     rax, [rax+30h]
0x14007d492  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007d497  cmp     eax, 16h
0x14007d49a  jmp     short loc_14007D434
0x14007d49c  cmp     dword ptr [rdx+20h], 1
0x14007d4a0  jnz     short loc_14007D4CF
0x14007d4a2  cmp     dword ptr [rdx+24h], 1
0x14007d4a6  jnz     short loc_14007D4C8
0x14007d4a8  mov     rax, [r8]
0x14007d4ab  mov     rcx, rdi
0x14007d4ae  mov     rax, [rax+38h]
0x14007d4b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007d4b7  mov     rdx, rax
0x14007d4ba  lea     rcx, [r15+28h]
0x14007d4be  call    ??8ATL@@YA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@0@PEBG@Z; ATL::operator==(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> const &,ushort const *)
0x14007d4c3  jmp     loc_14007D3A7
0x14007d4c8  mov     esi, 8004036Ch
0x14007d4cd  jmp     short loc_14007D4D2
0x14007d4cf  mov     [r9], sil
0x14007d4d2  mov     eax, esi
0x14007d4d4  mov     rbx, [rsp+30h+arg_10]
0x14007d4d9  add     rsp, 30h
0x14007d4dd  pop     r15
0x14007d4df  pop     r14
0x14007d4e1  pop     rdi
0x14007d4e2  pop     rsi
0x14007d4e3  pop     rbp
0x14007d4e4  retn
```
