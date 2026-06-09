# CContactStorage::FindRecords(_SBinary *,ulong,_SPropertyRestriction *,ulong *,_SBinary * *)

- ea: `0x18000c260`
- end: `0x18000c770`
- name: `?FindRecords@CContactStorage@@UEAAJPEAU_SBinary@@KPEAU_SPropertyRestriction@@PEAKPEAPEAU2@@Z`
- size: `1296`
- prototype: `__int64 __fastcall(CContactStorage *__hidden this, struct _SBinary *, unsigned int, struct _SPropertyRestriction *, unsigned int *, struct _SBinary **)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x180002818`
- `0x180006f7c`
- `0x180008f74`
- `0x18000c260`
- `0x18000cab4`
- `0x18000ccb4`
- `0x180011890`
- `0x180091eaa`
- `0x180091ef0`
- `0x180093010`

## import_xrefs

- `SHLWAPI!StrCmpIW` at `0x18000c5b0`
- `SHLWAPI!StrCmpIW` at `0x18000c5b0`
- `KERNEL32!LocalAlloc` at `0x18000c65d`
- `KERNEL32!LocalAlloc` at `0x18000c65d`
- `KERNEL32!LocalFree` at `0x18000c338`
- `KERNEL32!LocalFree` at `0x18000c441`
- `KERNEL32!LocalFree` at `0x18000c6df`
- `KERNEL32!LocalFree` at `0x18000c338`
- `KERNEL32!LocalFree` at `0x18000c441`
- `KERNEL32!LocalFree` at `0x18000c6df`
- `KERNEL32!CompareFileTime` at `0x18000c557`
- `KERNEL32!CompareFileTime` at `0x18000c557`
- `iertutil!__imp_DPA_Create` at `0x18000c3b8`
- `iertutil!__imp_DPA_Create` at `0x18000c3b8`
- `iertutil!__imp_DPA_DeletePtr` at `0x18000c6b4`
- `iertutil!__imp_DPA_DeletePtr` at `0x18000c6b4`
- `iertutil!__imp_DPA_Destroy` at `0x18000c6fa`
- `iertutil!__imp_DPA_Destroy` at `0x18000c6fa`
- `iertutil!__imp_DPA_GetPtr` at `0x18000c683`
- `iertutil!__imp_DPA_GetPtr` at `0x18000c6ec`
- `iertutil!__imp_DPA_GetPtr` at `0x18000c683`
- `iertutil!__imp_DPA_GetPtr` at `0x18000c6ec`
- `iertutil!__imp_DPA_InsertPtr` at `0x18000c61f`
- `iertutil!__imp_DPA_InsertPtr` at `0x18000c61f`

## pseudocode

```c
__int64 __fastcall CContactStorage::FindRecords(
        CContactStorage *this,
        struct _SBinary *a2,
        char a3,
        struct _SPropertyRestriction *a4,
        unsigned int *a5,
        struct _SBinary **a6)
{
  struct _DPA *v7; // r14
  unsigned int v8; // r15d
  int MappingFromPropTag; // ebx
  FILETIME v11; // r13
  unsigned int v12; // edi
  INT_PTR i; // rdx
  int v14; // esi
  LPSPropValue lpProp; // rax
  LPSPropValue v16; // rax
  bool v17; // zf
  int ulPropTag; // eax
  __int64 (__fastcall *v19)(__int64, __int128 *, FILETIME); // rax
  int v20; // eax
  int v21; // eax
  const WCHAR *v22; // rcx
  INT_PTR v23; // rbx
  struct _SBinary *v24; // rdi
  int v25; // esi
  BYTE *Ptr; // rdx
  __int64 v27; // rax
  __int64 v28; // rcx
  PVOID v29; // rax
  struct IContact *v31; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v32; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v33; // [rsp+30h] [rbp-D0h] BYREF
  FILETIME FileTime1; // [rsp+38h] [rbp-C8h] BYREF
  HLOCAL hMem[2]; // [rsp+40h] [rbp-C0h] BYREF
  CContactStorage *v36; // [rsp+50h] [rbp-B0h]
  unsigned int v37; // [rsp+58h] [rbp-A8h] BYREF
  PCWSTR psz1[3]; // [rsp+60h] [rbp-A0h] BYREF
  struct _SBinary **v39; // [rsp+78h] [rbp-88h]
  __int128 v40; // [rsp+80h] [rbp-80h] BYREF
  __int64 v41; // [rsp+90h] [rbp-70h]
  unsigned __int16 v42[264]; // [rsp+A0h] [rbp-60h] BYREF

  v36 = this;
  v39 = a6;
  v31 = 0;
  v32 = 0;
  v7 = 0;
  v33 = 0;
  v8 = 0;
  *(_OWORD *)hMem = 0;
  STRW::STRW((STRW *)&v37, v42, 0x104u);
  FileTime1 = 0;
  if ( !a4 || !a5 || !a6 )
  {
    MappingFromPropTag = -2147024809;
    goto LABEL_7;
  }
  *a5 = 0;
  *a6 = 0;
  MappingFromPropTag = CContactStorage::_GetMappingFromPropTag(a4->ulPropTag, (struct CMapping **)&FileTime1);
  if ( MappingFromPropTag < 0 )
    goto LABEL_7;
  v11 = FileTime1;
  if ( !*(_QWORD *)(*(_QWORD *)&FileTime1 + 8LL) )
  {
LABEL_6:
    MappingFromPropTag = 0;
    goto LABEL_7;
  }
  v14 = a3 & 1;
  if ( !v14 && !a4->lpProp || (a4->ulPropTag & 0x1000) != 0 && !v14 )
  {
LABEL_13:
    MappingFromPropTag = -2147467259;
    goto LABEL_7;
  }
  lpProp = a4->lpProp;
  if ( lpProp && lpProp->Value.l == 4 && (a4->relop != 5 || a4->ulPropTag != 268304387) )
  {
    MappingFromPropTag = -2147418113;
    goto LABEL_7;
  }
  if ( a4->relop - 4 > 1 && (v14 || LOWORD(a4->ulPropTag) == 72) )
  {
    MappingFromPropTag = -2147024809;
    goto LABEL_7;
  }
  v7 = DPA_Create(20);
  if ( !v7 )
  {
    MappingFromPropTag = -2147024882;
    goto LABEL_7;
  }
  MappingFromPropTag = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)v36 + 1) + 64LL))(
                         *((_QWORD *)v36 + 1),
                         &v33);
  if ( MappingFromPropTag >= 0 )
  {
    while ( 1 )
    {
      do
      {
        while ( 1 )
        {
          if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v33 + 32LL))(v33) )
          {
            if ( v8 )
            {
              v23 = v8;
              v24 = (struct _SBinary *)LocalAlloc(0x40u, 16LL * v8);
              if ( !v24 )
              {
                MappingFromPropTag = -2147024882;
                goto LABEL_7;
              }
              v25 = v8;
              do
              {
                --v23;
                --v25;
                Ptr = (BYTE *)DPA_GetPtr(v7, v23);
                v27 = -1;
                do
                  ++v27;
                while ( *(_WORD *)&Ptr[2 * v27] );
                v28 = v23;
                v24[v28].lpb = Ptr;
                v24[v28].cb = 2 * v27 + 2;
                DPA_DeletePtr(v7, v25);
              }
              while ( v25 );
              *v39 = v24;
              *a5 = v8;
            }
            MappingFromPropTag = 0;
            goto LABEL_7;
          }
          OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v31);
          MappingFromPropTag = (*(__int64 (__fastcall **)(__int64, struct IContact **))(*(_QWORD *)v33 + 40LL))(
                                 v33,
                                 &v31);
          if ( MappingFromPropTag < 0 )
            goto LABEL_7;
          if ( hMem[1] )
          {
            LocalFree(hMem[1]);
            hMem[1] = 0;
          }
          LODWORD(hMem[0]) = 0;
          MappingFromPropTag = GetEntryIDFromIContact(v31, (struct _SBinary *)hMem);
          if ( MappingFromPropTag < 0 )
            goto LABEL_7;
          if ( a4->ulPropTag == 268304387 )
          {
            v16 = a4->lpProp;
            if ( v16->Value.l == 4 )
            {
              if ( a4->relop == 5 )
                goto LABEL_70;
LABEL_36:
              if ( v16->Value.l != 6 )
                goto LABEL_6;
              v17 = a4->relop == 4;
            }
            else
            {
              if ( v16->Value.l != 8 )
                goto LABEL_36;
              v17 = a4->relop == 5;
            }
            if ( !v17 )
              goto LABEL_6;
            goto LABEL_70;
          }
          OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v32);
          MappingFromPropTag = ((__int64 (__fastcall *)(struct IContact *, GUID *, __int64 *))v31->lpVtbl->QueryInterface)(
                                 v31,
                                 &GUID_70dd27dd_5cbd_46e8_bef0_23b6b346288f,
                                 &v32);
          if ( MappingFromPropTag < 0 )
            goto LABEL_7;
          ulPropTag = (unsigned __int16)a4->ulPropTag;
          if ( ulPropTag != 31 )
            break;
          memset_0((void *)psz1[0], 0, 2LL * v37);
          v37 = 0;
          v20 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))GetContactStringFromMap)(v11, v32, &v37);
          MappingFromPropTag = v20;
          if ( !v20 )
          {
            if ( v14 )
              goto LABEL_70;
            v22 = &Str;
            if ( v37 )
              v22 = psz1[0];
            v21 = StrCmpIW(v22, a4->lpProp->Value.lpszW);
            goto LABEL_54;
          }
LABEL_67:
          if ( v20 != -2147024893 )
            goto LABEL_7;
          if ( v14 && a4->relop == 5 )
          {
LABEL_70:
            if ( DPA_InsertPtr(v7, 0x7FFFFFFF, hMem[1]) == -1 )
              goto LABEL_13;
            LODWORD(hMem[0]) = 0;
            ++v8;
            hMem[1] = 0;
          }
        }
      }
      while ( ulPropTag != 64 );
      FileTime1 = 0;
      v41 = 0;
      v19 = *(__int64 (__fastcall **)(__int64, __int128 *, FILETIME))(*(_QWORD *)&v11 + 8LL);
      v40 = 0;
      if ( !v19 )
        goto LABEL_13;
      LODWORD(v40) = *(_DWORD *)(*(_QWORD *)&v11 + 24LL);
      v20 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))v19)(v32, &v40, v11);
      MappingFromPropTag = v20;
      if ( v20 < 0 )
        goto LABEL_67;
      FileTime1 = (FILETIME)*((_QWORD *)&v40 + 1);
      if ( v14 )
        goto LABEL_70;
      v21 = CompareFileTime(&FileTime1, (const FILETIME *)&a4->lpProp->Value);
LABEL_54:
      if ( a4->relop == 4 && !v21
        || a4->relop == 5 && v21
        || a4->relop == 2 && v21 > 0
        || a4->relop == 3 && v21 >= 0
        || !a4->relop && v21 < 0
        || a4->relop == 1 && v21 <= 0 )
      {
        goto LABEL_70;
      }
    }
  }
LABEL_7:
  if ( hMem[1] )
    LocalFree(hMem[1]);
  if ( v7 )
  {
    v12 = 0;
    for ( i = 0; ; i = v12 )
    {
      v29 = DPA_GetPtr(v7, i);
      if ( !v29 )
        break;
      LocalFree(v29);
      ++v12;
    }
    DPA_Destroy(v7);
  }
  OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v31);
  OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v32);
  OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v33);
  (*(void (__fastcall **)(CContactStorage *, _QWORD, _QWORD))(*(_QWORD *)v36 + 56LL))(v36, v8, 0);
  v37 = 0;
  BUFFER::ReleaseStorage((BUFFER *)psz1);
  return (unsigned int)MappingFromPropTag;
}

```

## disassembly

```asm
0x18000c260  mov     [rsp-8+arg_8], rbx
0x18000c265  push    rbp
0x18000c266  push    rsi
0x18000c267  push    rdi
0x18000c268  push    r12
0x18000c26a  push    r13
0x18000c26c  push    r14
0x18000c26e  push    r15
0x18000c270  lea     rbp, [rsp-1C0h]
0x18000c278  sub     rsp, 2C0h
0x18000c27f  mov     rax, cs:__security_cookie
0x18000c286  xor     rax, rsp
0x18000c289  mov     [rbp+1F0h+var_40], rax
0x18000c290  mov     rbx, [rbp+1F0h+arg_28]
0x18000c297  lea     rdx, [rbp+1F0h+var_250]; unsigned __int16 *
0x18000c29b  mov     r12, [rbp+1F0h+arg_20]
0x18000c2a2  xor     r13d, r13d
0x18000c2a5  mov     esi, r8d
0x18000c2a8  mov     [rsp+2F0h+var_2A0], rcx
0x18000c2ad  xorps   xmm0, xmm0
0x18000c2b0  mov     [rsp+2F0h+var_278], rbx
0x18000c2b5  mov     r8d, 104h; unsigned int
0x18000c2bb  mov     [rsp+2F0h+var_2D0], r13
0x18000c2c0  lea     rcx, [rsp+2F0h+var_298]; this
0x18000c2c5  mov     [rsp+2F0h+var_2C8], r13
0x18000c2ca  mov     r14d, r13d
0x18000c2cd  mov     [rsp+2F0h+var_2C0], r13
0x18000c2d2  mov     r15d, r13d
0x18000c2d5  mov     rdi, r9
0x18000c2d8  movups  xmmword ptr [rsp+2F0h+hMem], xmm0
0x18000c2dd  call    ??0STRW@@QEAA@PEAGK@Z; STRW::STRW(ushort *,ulong)
0x18000c2e2  mov     qword ptr [rsp+2F0h+FileTime1.dwLowDateTime], r13
0x18000c2e7  test    rdi, rdi
0x18000c2ea  jz      loc_18000C6D2
0x18000c2f0  test    r12, r12
0x18000c2f3  jz      loc_18000C6D2
0x18000c2f9  test    rbx, rbx
0x18000c2fc  jz      loc_18000C6D2
0x18000c302  mov     [r12], r13d
0x18000c306  lea     rdx, [rsp+2F0h+FileTime1]; struct CMapping **
0x18000c30b  mov     [rbx], r13
0x18000c30e  mov     ecx, [rdi+4]; unsigned int
0x18000c311  call    ?_GetMappingFromPropTag@CContactStorage@@CAJKPEAPEAVCMapping@@@Z; CContactStorage::_GetMappingFromPropTag(ulong,CMapping * *)
0x18000c316  xor     ecx, ecx
0x18000c318  mov     ebx, eax
0x18000c31a  test    eax, eax
0x18000c31c  js      short loc_18000C32B
0x18000c31e  mov     r13, qword ptr [rsp+2F0h+FileTime1.dwLowDateTime]
0x18000c323  cmp     [r13+8], rcx
0x18000c327  jnz     short loc_18000C351
0x18000c329  mov     ebx, ecx
0x18000c32b  xor     r13d, r13d
0x18000c32e  mov     rcx, [rsp+2F0h+hMem+8]; hMem
0x18000c333  test    rcx, rcx
0x18000c336  jz      short loc_18000C33E
0x18000c338  call    cs:__imp_LocalFree
0x18000c33e  test    r14, r14
0x18000c341  jz      loc_18000C700
0x18000c347  mov     edi, r13d
0x18000c34a  xor     edx, edx
0x18000c34c  jmp     loc_18000C6E9
0x18000c351  and     esi, 1
0x18000c354  jnz     short loc_18000C363
0x18000c356  cmp     [rdi+8], rcx
0x18000c35a  jnz     short loc_18000C363
0x18000c35c  mov     ebx, 80004005h
0x18000c361  jmp     short loc_18000C32B
0x18000c363  test    dword ptr [rdi+4], 1000h
0x18000c36a  jz      short loc_18000C370
0x18000c36c  test    esi, esi
0x18000c36e  jz      short loc_18000C35C
0x18000c370  mov     rax, [rdi+8]
0x18000c374  test    rax, rax
0x18000c377  jz      short loc_18000C394
0x18000c379  cmp     dword ptr [rax+8], 4
0x18000c37d  jnz     short loc_18000C394
0x18000c37f  cmp     dword ptr [rdi], 5
0x18000c382  jnz     short loc_18000C38D
0x18000c384  cmp     dword ptr [rdi+4], 0FFE0003h
0x18000c38b  jz      short loc_18000C394
0x18000c38d  mov     ebx, 8000FFFFh
0x18000c392  jmp     short loc_18000C32B
0x18000c394  mov     eax, [rdi]
0x18000c396  sub     eax, 4
0x18000c399  cmp     eax, 1
0x18000c39c  jbe     short loc_18000C3B3
0x18000c39e  test    esi, esi
0x18000c3a0  jnz     short loc_18000C3A9
0x18000c3a2  cmp     word ptr [rdi+4], 48h ; 'H'
0x18000c3a7  jnz     short loc_18000C3B3
0x18000c3a9  mov     ebx, 80070057h
0x18000c3ae  jmp     loc_18000C32B
0x18000c3b3  mov     ecx, 14h; cItemGrow
0x18000c3b8  call    cs:__imp_DPA_Create
0x18000c3be  mov     r14, rax
0x18000c3c1  test    rax, rax
0x18000c3c4  jnz     short loc_18000C3D0
0x18000c3c6  mov     ebx, 8007000Eh
0x18000c3cb  jmp     loc_18000C32B
0x18000c3d0  mov     rcx, [rsp+2F0h+var_2A0]
0x18000c3d5  lea     rdx, [rsp+2F0h+var_2C0]
0x18000c3da  mov     rcx, [rcx+8]
0x18000c3de  mov     rax, [rcx]
0x18000c3e1  mov     rax, [rax+40h]
0x18000c3e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c3ea  mov     ebx, eax
0x18000c3ec  test    eax, eax
0x18000c3ee  js      loc_18000C32B
0x18000c3f4  mov     rcx, [rsp+2F0h+var_2C0]
0x18000c3f9  mov     rax, [rcx]
0x18000c3fc  mov     rax, [rax+20h]
0x18000c400  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c405  test    eax, eax
0x18000c407  jnz     loc_18000C647
0x18000c40d  lea     rcx, [rsp+2F0h+var_2D0]
0x18000c412  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x18000c417  mov     rcx, [rsp+2F0h+var_2C0]
0x18000c41c  lea     rdx, [rsp+2F0h+var_2D0]
0x18000c421  mov     rax, [rcx]
0x18000c424  mov     rax, [rax+28h]
0x18000c428  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c42d  mov     ebx, eax
0x18000c42f  test    eax, eax
0x18000c431  js      loc_18000C32B
0x18000c437  mov     rcx, [rsp+2F0h+hMem+8]; hMem
0x18000c43c  test    rcx, rcx
0x18000c43f  jz      short loc_18000C450
0x18000c441  call    cs:__imp_LocalFree
0x18000c447  mov     [rsp+2F0h+hMem+8], 0
0x18000c450  mov     rcx, [rsp+2F0h+var_2D0]; struct IContact *
0x18000c455  lea     rdx, [rsp+2F0h+hMem]; struct _SBinary *
0x18000c45a  mov     dword ptr [rsp+2F0h+hMem], 0
0x18000c462  call    ?GetEntryIDFromIContact@@YAJPEAUIContact@@PEAU_SBinary@@@Z; GetEntryIDFromIContact(IContact *,_SBinary *)
0x18000c467  xor     ecx, ecx
0x18000c469  mov     ebx, eax
0x18000c46b  test    eax, eax
0x18000c46d  js      loc_18000C32B
0x18000c473  cmp     dword ptr [rdi+4], 0FFE0003h
0x18000c47a  jnz     short loc_18000C4B2
0x18000c47c  mov     rax, [rdi+8]
0x18000c480  cmp     dword ptr [rax+8], 4
0x18000c484  jnz     short loc_18000C4A7
0x18000c486  cmp     dword ptr [rdi], 5
0x18000c489  jz      loc_18000C612
0x18000c48f  cmp     dword ptr [rax+8], 6
0x18000c493  jnz     loc_18000C329
0x18000c499  cmp     dword ptr [rdi], 4
0x18000c49c  jnz     loc_18000C329
0x18000c4a2  jmp     loc_18000C612
0x18000c4a7  cmp     dword ptr [rax+8], 8
0x18000c4ab  jnz     short loc_18000C48F
0x18000c4ad  cmp     dword ptr [rdi], 5
0x18000c4b0  jmp     short loc_18000C49C
0x18000c4b2  lea     rcx, [rsp+2F0h+var_2C8]
0x18000c4b7  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x18000c4bc  mov     rcx, [rsp+2F0h+var_2D0]
0x18000c4c1  lea     r8, [rsp+2F0h+var_2C8]
0x18000c4c6  lea     rdx, _GUID_70dd27dd_5cbd_46e8_bef0_23b6b346288f
0x18000c4cd  mov     rax, [rcx]
0x18000c4d0  mov     rax, [rax]
0x18000c4d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c4d8  xor     ecx, ecx
0x18000c4da  mov     ebx, eax
0x18000c4dc  test    eax, eax
0x18000c4de  js      loc_18000C32B
0x18000c4e4  mov     eax, [rdi+4]
0x18000c4e7  movzx   eax, ax
0x18000c4ea  cmp     eax, 1Fh
0x18000c4ed  jz      short loc_18000C55F
0x18000c4ef  cmp     eax, 40h ; '@'
0x18000c4f2  jnz     loc_18000C3F4
0x18000c4f8  xor     eax, eax
0x18000c4fa  mov     qword ptr [rsp+2F0h+FileTime1.dwLowDateTime], rcx
0x18000c4ff  mov     [rbp+1F0h+var_260], rax
0x18000c503  xorps   xmm0, xmm0
0x18000c506  mov     rax, [r13+8]
0x18000c50a  movups  [rbp+1F0h+var_270], xmm0
0x18000c50e  test    rax, rax
0x18000c511  jz      loc_18000C35C
0x18000c517  mov     ecx, [r13+18h]
0x18000c51b  lea     rdx, [rbp+1F0h+var_270]
0x18000c51f  mov     dword ptr [rbp+1F0h+var_270], ecx
0x18000c522  mov     r8, r13
0x18000c525  mov     rcx, [rsp+2F0h+var_2C8]
0x18000c52a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c52f  mov     ebx, eax
0x18000c531  test    eax, eax
0x18000c533  js      loc_18000C5F6
0x18000c539  mov     rax, qword ptr [rbp+1F0h+var_270+8]
0x18000c53d  mov     qword ptr [rsp+2F0h+FileTime1.dwLowDateTime], rax
0x18000c542  test    esi, esi
0x18000c544  jnz     loc_18000C612
0x18000c54a  mov     rdx, [rdi+8]
0x18000c54e  lea     rcx, [rsp+2F0h+FileTime1]; lpFileTime1
0x18000c553  add     rdx, 8; lpFileTime2
0x18000c557  call    cs:__imp_CompareFileTime
0x18000c55d  jmp     short loc_18000C5B6
0x18000c55f  mov     r8d, [rsp+2F0h+var_298]
0x18000c564  xor     edx, edx; Val
0x18000c566  mov     rcx, [rsp+2F0h+psz1]; void *
0x18000c56b  add     r8, r8; Size
0x18000c56e  call    memset_0
0x18000c573  mov     rdx, [rsp+2F0h+var_2C8]
0x18000c578  lea     r8, [rsp+2F0h+var_298]
0x18000c57d  mov     rcx, r13
0x18000c580  mov     [rsp+2F0h+var_298], 0
0x18000c588  call    GetContactStringFromMap
0x18000c58d  mov     ebx, eax
0x18000c58f  test    eax, eax
0x18000c591  jnz     short loc_18000C5F6
0x18000c593  test    esi, esi
0x18000c595  jnz     short loc_18000C612
0x18000c597  mov     rax, [rdi+8]
0x18000c59b  lea     rcx, Str
0x18000c5a2  cmp     [rsp+2F0h+var_298], esi
0x18000c5a6  cmovnz  rcx, [rsp+2F0h+psz1]; psz1
0x18000c5ac  mov     rdx, [rax+8]; psz2
0x18000c5b0  call    cs:__imp_StrCmpIW
0x18000c5b6  xor     ecx, ecx
0x18000c5b8  cmp     dword ptr [rdi], 4
0x18000c5bb  jnz     short loc_18000C5C1
0x18000c5bd  test    eax, eax
0x18000c5bf  jz      short loc_18000C612
0x18000c5c1  cmp     dword ptr [rdi], 5
0x18000c5c4  jnz     short loc_18000C5CA
0x18000c5c6  test    eax, eax
0x18000c5c8  jnz     short loc_18000C612
0x18000c5ca  cmp     dword ptr [rdi], 2
0x18000c5cd  jnz     short loc_18000C5D3
0x18000c5cf  test    eax, eax
0x18000c5d1  jg      short loc_18000C612
0x18000c5d3  cmp     dword ptr [rdi], 3
0x18000c5d6  jnz     short loc_18000C5DC
0x18000c5d8  test    eax, eax
0x18000c5da  jns     short loc_18000C612
0x18000c5dc  cmp     [rdi], ecx
0x18000c5de  jnz     short loc_18000C5E4
0x18000c5e0  test    eax, eax
0x18000c5e2  js      short loc_18000C612
0x18000c5e4  cmp     dword ptr [rdi], 1
0x18000c5e7  jnz     loc_18000C3F4
0x18000c5ed  test    eax, eax
0x18000c5ef  jle     short loc_18000C612
0x18000c5f1  jmp     loc_18000C3F4
0x18000c5f6  cmp     eax, 80070003h
0x18000c5fb  jnz     loc_18000C32B
0x18000c601  test    esi, esi
0x18000c603  jz      loc_18000C3F4
0x18000c609  cmp     dword ptr [rdi], 5
0x18000c60c  jnz     loc_18000C3F4
0x18000c612  mov     r8, [rsp+2F0h+hMem+8]; p
0x18000c617  mov     edx, 7FFFFFFFh; i
0x18000c61c  mov     rcx, r14; hdpa
0x18000c61f  call    cs:__imp_DPA_InsertPtr
0x18000c625  cmp     eax, 0FFFFFFFFh
0x18000c628  jz      loc_18000C35C
0x18000c62e  mov     dword ptr [rsp+2F0h+hMem], 0
0x18000c636  inc     r15d
0x18000c639  mov     [rsp+2F0h+hMem+8], 0
0x18000c642  jmp     loc_18000C3F4
0x18000c647  xor     r13d, r13d
0x18000c64a  test    r15d, r15d
0x18000c64d  jz      short loc_18000C6CA
0x18000c64f  mov     edx, r15d
0x18000c652  lea     ecx, [r13+40h]; uFlags
0x18000c656  shl     rdx, 4; uBytes
0x18000c65a  mov     ebx, r15d
0x18000c65d  call    cs:__imp_LocalAlloc
0x18000c663  mov     rdi, rax
0x18000c666  test    rax, rax
0x18000c669  jnz     short loc_18000C675
0x18000c66b  mov     ebx, 8007000Eh
0x18000c670  jmp     loc_18000C32E
0x18000c675  mov     esi, r15d
0x18000c678  dec     rbx
0x18000c67b  mov     rcx, r14; hdpa
0x18000c67e  mov     rdx, rbx; i
0x18000c681  dec     esi
0x18000c683  call    cs:__imp_DPA_GetPtr
0x18000c689  mov     rdx, rax
0x18000c68c  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000c690  inc     rax
0x18000c693  cmp     [rdx+rax*2], r13w
0x18000c698  jnz     short loc_18000C690
0x18000c69a  lea     eax, ds:2[rax*2]
0x18000c6a1  mov     rcx, rbx
0x18000c6a4  add     rcx, rcx
0x18000c6a7  mov     [rdi+rcx*8+8], rdx
0x18000c6ac  mov     edx, esi; i
0x18000c6ae  mov     [rdi+rcx*8], eax
0x18000c6b1  mov     rcx, r14; hdpa
0x18000c6b4  call    cs:__imp_DPA_DeletePtr
0x18000c6ba  test    esi, esi
0x18000c6bc  jnz     short loc_18000C678
0x18000c6be  mov     rax, [rsp+2F0h+var_278]
0x18000c6c3  mov     [rax], rdi
0x18000c6c6  mov     [r12], r15d
0x18000c6ca  mov     ebx, r13d
0x18000c6cd  jmp     loc_18000C32E
0x18000c6d2  mov     ebx, 80070057h
  ... truncated ...
```
