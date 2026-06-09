# CContactStorage::FindFuzzyRecordMatches(_SBinary *,ushort *,ulong,ulong *,_SBinary * *)

- ea: `0x18000bd60`
- end: `0x18000c258`
- name: `?FindFuzzyRecordMatches@CContactStorage@@UEAAJPEAU_SBinary@@PEAGKPEAKPEAPEAU2@@Z`
- size: `1272`
- prototype: `int(CContactStorage *__hidden this, struct _SBinary *, unsigned __int16 *, unsigned int, unsigned int *, struct _SBinary **)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x180002818`
- `0x1800045e4`
- `0x1800093c4`
- `0x18000bd60`
- `0x18000ccb4`
- `0x1800112a0`
- `0x1800330b8`
- `0x180063ef4`
- `0x18006a678`
- `0x180093010`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x18000be04`
- `KERNEL32!LocalAlloc` at `0x18000be4e`
- `KERNEL32!LocalAlloc` at `0x18000c12b`
- `KERNEL32!LocalAlloc` at `0x18000be04`
- `KERNEL32!LocalAlloc` at `0x18000be4e`
- `KERNEL32!LocalAlloc` at `0x18000c12b`
- `KERNEL32!LocalFree` at `0x18000c0a3`
- `KERNEL32!LocalFree` at `0x18000c0ac`
- `KERNEL32!LocalFree` at `0x18000c0a3`
- `KERNEL32!LocalFree` at `0x18000c0ac`
- `iertutil!__imp_DPA_Create` at `0x18000beb4`
- `iertutil!__imp_DPA_Create` at `0x18000beb4`
- `iertutil!__imp_DPA_Destroy` at `0x18000c218`
- `iertutil!__imp_DPA_Destroy` at `0x18000c218`
- `iertutil!__imp_DPA_GetPtr` at `0x18000c0e4`
- `iertutil!__imp_DPA_GetPtr` at `0x18000c160`
- `iertutil!__imp_DPA_GetPtr` at `0x18000c206`
- `iertutil!__imp_DPA_GetPtr` at `0x18000c0e4`
- `iertutil!__imp_DPA_GetPtr` at `0x18000c160`
- `iertutil!__imp_DPA_GetPtr` at `0x18000c206`
- `iertutil!__imp_DPA_InsertPtr` at `0x18000c063`
- `iertutil!__imp_DPA_InsertPtr` at `0x18000c109`
- `iertutil!__imp_DPA_InsertPtr` at `0x18000c063`
- `iertutil!__imp_DPA_InsertPtr` at `0x18000c109`

## pseudocode

```c
__int64 __fastcall CContactStorage::FindFuzzyRecordMatches(
        const struct _GUID *this,
        struct _SBinary *a2,
        unsigned __int16 *a3,
        __int16 a4,
        unsigned int *a5,
        struct _SBinary **a6)
{
  struct _DPA *v8; // rsi
  unsigned __int64 v9; // r8
  unsigned int v10; // r14d
  struct _SBinary *v11; // r15
  unsigned int *v12; // rax
  __int64 v13; // rax
  unsigned __int64 v14; // rbx
  unsigned __int16 *v15; // rax
  unsigned __int16 *v16; // rdi
  int EntryIDFromIContact; // ebx
  unsigned int v18; // ebx
  unsigned __int16 *v19; // rcx
  __int64 v20; // rdx
  unsigned __int16 *v21; // rcx
  __int64 v22; // r9
  unsigned __int16 v23; // r10
  unsigned __int16 *v24; // r8
  unsigned int v25; // edi
  CContactStorage *v26; // rcx
  int inserted; // eax
  unsigned int v28; // edi
  const struct _GUID *v29; // rcx
  unsigned int v30; // edi
  INT_PTR i; // rdx
  unsigned __int64 v32; // r8
  void *p; // [rsp+50h] [rbp-29h] BYREF
  unsigned __int16 *v35; // [rsp+58h] [rbp-21h]
  struct _SBinary *v36; // [rsp+60h] [rbp-19h]
  int v37; // [rsp+68h] [rbp-11h] BYREF
  unsigned int v38; // [rsp+6Ch] [rbp-Dh]
  struct IContactProperties *v39; // [rsp+70h] [rbp-9h] BYREF
  __int64 v40; // [rsp+78h] [rbp-1h] BYREF
  HLOCAL hMem; // [rsp+80h] [rbp+7h]
  __int64 v42; // [rsp+88h] [rbp+Fh]
  int v44; // [rsp+E0h] [rbp+67h] BYREF

  p = 0;
  v39 = 0;
  v40 = 0;
  v8 = 0;
  v9 = *((_QWORD *)WPP_GLOBAL_Control + 7);
  v10 = 0;
  v36 = 0;
  v11 = 0;
  if ( v9 )
    ShellPrivateTraceEvent(this, 0x2Bu, v9, 1u);
  if ( a3 )
  {
    v12 = a5;
    if ( a5 )
    {
      if ( a6 )
      {
        *a6 = 0;
        *v12 = 0;
        v13 = -1;
        v42 = -1;
        do
          ++v13;
        while ( a3[v13] );
        v14 = (unsigned int)(v13 + 1);
        v15 = (unsigned __int16 *)LocalAlloc(0x40u, 2 * v14);
        v35 = v15;
        v16 = v15;
        if ( !v15 )
        {
          EntryIDFromIContact = -2147024882;
          goto LABEL_63;
        }
        StringCchCopyW(v15, v14, a3);
        TrimSpaces(v16);
        v18 = nCountSubStrings(v16);
        v38 = v18;
        hMem = LocalAlloc(0x40u, 8LL * v18);
        if ( !hMem )
        {
          EntryIDFromIContact = -2147024882;
LABEL_45:
          LocalFree(v16);
          goto LABEL_63;
        }
        v19 = v16;
        if ( v18 )
        {
          do
          {
            while ( (unsigned int)FIsSpaceA(v19) )
              v19 = v21 + 1;
            v24 = v21;
            while ( *v21 != v23 && !(unsigned int)FIsSpaceA(v21) )
              ++v21;
            *v21 = v23;
            v19 = v21 + 1;
            *(_QWORD *)(v22 + 8 * v20) = v24;
          }
          while ( (_DWORD)v20 );
        }
        v8 = DPA_Create(20);
        if ( !v8 )
        {
          EntryIDFromIContact = -2147024882;
LABEL_44:
          LocalFree(hMem);
          goto LABEL_45;
        }
        EntryIDFromIContact = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)this->Data4 + 64LL))(
                                *(_QWORD *)this->Data4,
                                &v40);
        if ( EntryIDFromIContact < 0 )
          goto LABEL_44;
        EntryIDFromIContact = 0;
        v25 = 0;
        while ( !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v40 + 32LL))(v40) )
        {
          v37 = 0;
          v44 = 0;
          OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&p);
          EntryIDFromIContact = (*(__int64 (__fastcall **)(__int64, void **))(*(_QWORD *)v40 + 40LL))(v40, &p);
          if ( EntryIDFromIContact < 0 )
            goto LABEL_42;
          OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v39);
          EntryIDFromIContact = (**(__int64 (__fastcall ***)(void *, GUID *, struct IContactProperties **))p)(
                                  p,
                                  &GUID_70dd27dd_5cbd_46e8_bef0_23b6b346288f,
                                  &v39);
          if ( EntryIDFromIContact < 0 )
            goto LABEL_42;
          if ( (a4 & 0x10) != 0 )
          {
            EntryIDFromIContact = CContactStorage::_FuzzyStringMatch(
                                    v26,
                                    v39,
                                    0x3001001Fu,
                                    a4 & 0x200,
                                    (unsigned __int16 **)hMem,
                                    v38,
                                    a3,
                                    &v37,
                                    &v44);
            if ( EntryIDFromIContact < 0 )
              goto LABEL_42;
          }
          if ( (a4 & 0x100) != 0 )
          {
            EntryIDFromIContact = CContactStorage::_FuzzyStringMatch(
                                    v26,
                                    v39,
                                    0x3003001Fu,
                                    a4 & 0x200,
                                    (unsigned __int16 **)hMem,
                                    v38,
                                    a3,
                                    &v37,
                                    &v44);
            if ( EntryIDFromIContact < 0 )
              goto LABEL_42;
          }
          if ( (a4 & 0x1000) != 0 )
          {
            EntryIDFromIContact = CContactStorage::_FuzzyStringMatch(
                                    v26,
                                    v39,
                                    0x3A4F001Fu,
                                    a4 & 0x200,
                                    (unsigned __int16 **)hMem,
                                    v38,
                                    a3,
                                    &v37,
                                    &v44);
            if ( EntryIDFromIContact < 0 )
              goto LABEL_42;
          }
          EntryIDFromIContact = 0;
          if ( v37 || v44 )
          {
            inserted = DPA_InsertPtr(v8, 0x7FFFFFFF, p);
            if ( inserted == -1 )
              goto LABEL_46;
            ++v10;
            p = 0;
            if ( v44 )
            {
              LODWORD(v42) = inserted;
              ++v25;
            }
            if ( (a4 & 1) != 0 && v25 > 1 )
              goto LABEL_41;
          }
        }
        if ( (a4 & 1) != 0 && v10 > 1 )
        {
          if ( v25 == 1 )
          {
            v10 = 1;
            OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&p);
            p = DPA_GetPtr(v8, (int)v42);
            (*(void (__fastcall **)(void *))(*(_QWORD *)p + 8LL))(p);
            if ( DPA_InsertPtr(v8, 0, p) != -1 )
            {
              p = 0;
              goto LABEL_53;
            }
LABEL_46:
            EntryIDFromIContact = -2147467259;
          }
          else
          {
LABEL_41:
            EntryIDFromIContact = -2147219712;
          }
LABEL_42:
          v11 = v36;
          goto LABEL_43;
        }
        if ( !v10 )
        {
          v11 = v36;
          goto LABEL_61;
        }
LABEL_53:
        v11 = (struct _SBinary *)LocalAlloc(0x40u, 16LL * v10);
        if ( !v11 )
        {
          EntryIDFromIContact = -2147024882;
LABEL_43:
          v16 = v35;
          goto LABEL_44;
        }
        v28 = v10;
        while ( v28 )
        {
          --v28;
          OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&p);
          p = DPA_GetPtr(v8, v28);
          (*(void (__fastcall **)(void *))(*(_QWORD *)p + 8LL))(p);
          EntryIDFromIContact = GetEntryIDFromIContact((struct IContact *)p, &v11[v28]);
          if ( EntryIDFromIContact < 0 )
            goto LABEL_43;
          EntryIDFromIContact = 0;
        }
LABEL_61:
        *a6 = v11;
        v11 = 0;
        *a5 = v10;
        goto LABEL_43;
      }
    }
  }
  EntryIDFromIContact = -2147024809;
LABEL_63:
  OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&p);
  OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v40);
  OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v39);
  (*(void (__fastcall **)(const struct _GUID *, _QWORD, struct _SBinary *))(*(_QWORD *)&this->Data1 + 56LL))(
    this,
    v10,
    v11);
  if ( v8 )
  {
    v30 = 0;
    for ( i = 0; ; i = v30 )
    {
      p = DPA_GetPtr(v8, i);
      if ( !p )
        break;
      OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&p);
      ++v30;
    }
    DPA_Destroy(v8);
  }
  v32 = *((_QWORD *)WPP_GLOBAL_Control + 7);
  if ( v32 )
    ShellPrivateTraceEvent(v29, 0x2Bu, v32, 2u);
  return (unsigned int)EntryIDFromIContact;
}

```

## disassembly

```asm
0x18000bd60  mov     [rsp-8+arg_8], rbx
0x18000bd65  mov     [rsp-8+arg_0], rcx
0x18000bd6a  push    rbp
0x18000bd6b  push    rsi
0x18000bd6c  push    rdi
0x18000bd6d  push    r12
0x18000bd6f  push    r13
0x18000bd71  push    r14
0x18000bd73  push    r15
0x18000bd75  lea     rbp, [rsp-17h]
0x18000bd7a  sub     rsp, 90h
0x18000bd81  mov     rax, cs:WPP_GLOBAL_Control
0x18000bd88  xor     ebx, ebx
0x18000bd8a  mov     r13, r8
0x18000bd8d  mov     [rbp+47h+p], rbx
0x18000bd91  mov     [rbp+47h+var_50], rbx
0x18000bd95  mov     r12d, r9d
0x18000bd98  mov     [rbp+47h+var_48], rbx
0x18000bd9c  mov     esi, ebx
0x18000bd9e  mov     r8, [rax+38h]; unsigned __int64
0x18000bda2  mov     r14d, ebx
0x18000bda5  mov     [rbp+47h+var_60], rbx
0x18000bda9  mov     r15d, ebx
0x18000bdac  test    r8, r8
0x18000bdaf  jz      short loc_18000BDBC
0x18000bdb1  mov     r9b, 1; unsigned __int8
0x18000bdb4  lea     edx, [rbx+2Bh]; unsigned int
0x18000bdb7  call    ?ShellPrivateTraceEvent@@YAXPEBU_GUID@@K_KE@Z; ShellPrivateTraceEvent(_GUID const *,ulong,unsigned __int64,uchar)
0x18000bdbc  test    r13, r13
0x18000bdbf  jz      loc_18000C1B1
0x18000bdc5  mov     rax, [rbp+47h+arg_20]
0x18000bdc9  test    rax, rax
0x18000bdcc  jz      loc_18000C1B1
0x18000bdd2  mov     rcx, [rbp+47h+arg_28]
0x18000bdd6  test    rcx, rcx
0x18000bdd9  jz      loc_18000C1B1
0x18000bddf  mov     [rcx], rbx
0x18000bde2  mov     [rax], ebx
0x18000bde4  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000bde8  mov     [rbp+47h+var_38], rax
0x18000bdec  inc     rax
0x18000bdef  cmp     [r13+rax*2+0], bx
0x18000bdf5  jnz     short loc_18000BDEC
0x18000bdf7  inc     eax
0x18000bdf9  mov     ecx, 40h ; '@'; uFlags
0x18000bdfe  mov     ebx, eax
0x18000be00  lea     rdx, [rax+rax]; uBytes
0x18000be04  call    cs:__imp_LocalAlloc
0x18000be0a  mov     [rbp+47h+var_68], rax
0x18000be0e  mov     rdi, rax
0x18000be11  test    rax, rax
0x18000be14  jnz     short loc_18000BE20
0x18000be16  mov     ebx, 8007000Eh
0x18000be1b  jmp     loc_18000C1B6
0x18000be20  mov     r8, r13; unsigned __int16 *
0x18000be23  mov     rdx, rbx; unsigned __int64
0x18000be26  mov     rcx, rdi; unsigned __int16 *
0x18000be29  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000be2e  mov     rcx, rdi; unsigned __int16 *
0x18000be31  call    ?TrimSpaces@@YAHPEAG@Z; TrimSpaces(ushort *)
0x18000be36  mov     rcx, rdi; unsigned __int16 *
0x18000be39  call    ?nCountSubStrings@@YAHPEAG@Z; nCountSubStrings(ushort *)
0x18000be3e  mov     edx, eax
0x18000be40  mov     ecx, 40h ; '@'; uFlags
0x18000be45  mov     ebx, eax
0x18000be47  shl     rdx, 3; uBytes
0x18000be4b  mov     [rbp+47h+var_54], ebx
0x18000be4e  call    cs:__imp_LocalAlloc
0x18000be54  xor     r10d, r10d
0x18000be57  mov     [rbp+47h+hMem], rax
0x18000be5b  mov     r9, rax
0x18000be5e  test    rax, rax
0x18000be61  jnz     short loc_18000BE6D
0x18000be63  mov     ebx, 8007000Eh
0x18000be68  jmp     loc_18000C0A9
0x18000be6d  mov     rcx, rdi
0x18000be70  mov     edx, ebx
0x18000be72  test    ebx, ebx
0x18000be74  jz      short loc_18000BEAF
0x18000be76  dec     edx
0x18000be78  jmp     short loc_18000BE7E
0x18000be7a  add     rcx, 2; unsigned __int16 *
0x18000be7e  call    ?FIsSpaceA@@YAHPEAG@Z; FIsSpaceA(ushort *)
0x18000be83  test    eax, eax
0x18000be85  jnz     short loc_18000BE7A
0x18000be87  mov     r8, rcx
0x18000be8a  jmp     short loc_18000BE99
0x18000be8c  call    ?FIsSpaceA@@YAHPEAG@Z; FIsSpaceA(ushort *)
0x18000be91  test    eax, eax
0x18000be93  jnz     short loc_18000BE9F
0x18000be95  add     rcx, 2; unsigned __int16 *
0x18000be99  cmp     [rcx], r10w
0x18000be9d  jnz     short loc_18000BE8C
0x18000be9f  mov     [rcx], r10w
0x18000bea3  add     rcx, 2
0x18000bea7  mov     [r9+rdx*8], r8
0x18000beab  test    edx, edx
0x18000bead  jnz     short loc_18000BE76
0x18000beaf  mov     ecx, 14h; cItemGrow
0x18000beb4  call    cs:__imp_DPA_Create
0x18000beba  mov     rsi, rax
0x18000bebd  test    rax, rax
0x18000bec0  jnz     short loc_18000BECC
0x18000bec2  mov     ebx, 8007000Eh
0x18000bec7  jmp     loc_18000C09F
0x18000becc  mov     rcx, [rbp+47h+arg_0]
0x18000bed0  lea     rdx, [rbp+47h+var_48]
0x18000bed4  mov     rcx, [rcx+8]
0x18000bed8  mov     rax, [rcx]
0x18000bedb  mov     rax, [rax+40h]
0x18000bedf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bee4  mov     ebx, eax
0x18000bee6  test    eax, eax
0x18000bee8  js      loc_18000C09F
0x18000beee  xor     ebx, ebx
0x18000bef0  mov     r15d, r12d
0x18000bef3  mov     edi, ebx
0x18000bef5  and     r15d, 200h
0x18000befc  mov     rcx, [rbp+47h+var_48]
0x18000bf00  mov     rax, [rcx]
0x18000bf03  mov     rax, [rax+20h]
0x18000bf07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf0c  test    eax, eax
0x18000bf0e  jnz     loc_18000C0BE
0x18000bf14  lea     rcx, [rbp+47h+p]
0x18000bf18  mov     [rbp+47h+var_58], ebx
0x18000bf1b  mov     [rbp+47h+arg_10], ebx
0x18000bf1e  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x18000bf23  mov     rcx, [rbp+47h+var_48]
0x18000bf27  lea     rdx, [rbp+47h+p]
0x18000bf2b  mov     rax, [rcx]
0x18000bf2e  mov     rax, [rax+28h]
0x18000bf32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf37  mov     ebx, eax
0x18000bf39  test    eax, eax
0x18000bf3b  js      loc_18000C097
0x18000bf41  lea     rcx, [rbp+47h+var_50]
0x18000bf45  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x18000bf4a  mov     rcx, [rbp+47h+p]
0x18000bf4e  lea     r8, [rbp+47h+var_50]
0x18000bf52  lea     rdx, _GUID_70dd27dd_5cbd_46e8_bef0_23b6b346288f
0x18000bf59  mov     rax, [rcx]
0x18000bf5c  mov     rax, [rax]
0x18000bf5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf64  mov     ebx, eax
0x18000bf66  test    eax, eax
0x18000bf68  js      loc_18000C097
0x18000bf6e  test    r12b, 10h
0x18000bf72  jz      short loc_18000BFB7
0x18000bf74  mov     rdx, [rbp+47h+var_50]; struct IContactProperties *
0x18000bf78  lea     rax, [rbp+47h+arg_10]
0x18000bf7c  mov     [rsp+0C0h+var_80], rax; int *
0x18000bf81  mov     r9d, r15d; int
0x18000bf84  lea     rax, [rbp+47h+var_58]
0x18000bf88  mov     r8d, 3001001Fh; unsigned int
0x18000bf8e  mov     [rsp+0C0h+var_88], rax; int *
0x18000bf93  mov     eax, [rbp+47h+var_54]
0x18000bf96  mov     [rsp+0C0h+var_90], r13; unsigned __int16 *
0x18000bf9b  mov     [rsp+0C0h+var_98], eax; unsigned int
0x18000bf9f  mov     rax, [rbp+47h+hMem]
0x18000bfa3  mov     [rsp+0C0h+var_A0], rax; unsigned __int16 **
0x18000bfa8  call    ?_FuzzyStringMatch@CContactStorage@@AEAAJPEAUIContactProperties@@KHPEAPEAGKPEAGPEAH3@Z; CContactStorage::_FuzzyStringMatch(IContactProperties *,ulong,int,ushort * *,ulong,ushort *,int *,int *)
0x18000bfad  mov     ebx, eax
0x18000bfaf  test    eax, eax
0x18000bfb1  js      loc_18000C097
0x18000bfb7  bt      r12d, 8
0x18000bfbc  jnb     short loc_18000C001
0x18000bfbe  mov     rdx, [rbp+47h+var_50]; struct IContactProperties *
0x18000bfc2  lea     rax, [rbp+47h+arg_10]
0x18000bfc6  mov     [rsp+0C0h+var_80], rax; int *
0x18000bfcb  mov     r9d, r15d; int
0x18000bfce  lea     rax, [rbp+47h+var_58]
0x18000bfd2  mov     r8d, 3003001Fh; unsigned int
0x18000bfd8  mov     [rsp+0C0h+var_88], rax; int *
0x18000bfdd  mov     eax, [rbp+47h+var_54]
0x18000bfe0  mov     [rsp+0C0h+var_90], r13; unsigned __int16 *
0x18000bfe5  mov     [rsp+0C0h+var_98], eax; unsigned int
0x18000bfe9  mov     rax, [rbp+47h+hMem]
0x18000bfed  mov     [rsp+0C0h+var_A0], rax; unsigned __int16 **
0x18000bff2  call    ?_FuzzyStringMatch@CContactStorage@@AEAAJPEAUIContactProperties@@KHPEAPEAGKPEAGPEAH3@Z; CContactStorage::_FuzzyStringMatch(IContactProperties *,ulong,int,ushort * *,ulong,ushort *,int *,int *)
0x18000bff7  mov     ebx, eax
0x18000bff9  test    eax, eax
0x18000bffb  js      loc_18000C097
0x18000c001  bt      r12d, 0Ch
0x18000c006  jnb     short loc_18000C047
0x18000c008  mov     rdx, [rbp+47h+var_50]; struct IContactProperties *
0x18000c00c  lea     rax, [rbp+47h+arg_10]
0x18000c010  mov     [rsp+0C0h+var_80], rax; int *
0x18000c015  mov     r9d, r15d; int
0x18000c018  lea     rax, [rbp+47h+var_58]
0x18000c01c  mov     r8d, 3A4F001Fh; unsigned int
0x18000c022  mov     [rsp+0C0h+var_88], rax; int *
0x18000c027  mov     eax, [rbp+47h+var_54]
0x18000c02a  mov     [rsp+0C0h+var_90], r13; unsigned __int16 *
0x18000c02f  mov     [rsp+0C0h+var_98], eax; unsigned int
0x18000c033  mov     rax, [rbp+47h+hMem]
0x18000c037  mov     [rsp+0C0h+var_A0], rax; unsigned __int16 **
0x18000c03c  call    ?_FuzzyStringMatch@CContactStorage@@AEAAJPEAUIContactProperties@@KHPEAPEAGKPEAGPEAH3@Z; CContactStorage::_FuzzyStringMatch(IContactProperties *,ulong,int,ushort * *,ulong,ushort *,int *,int *)
0x18000c041  mov     ebx, eax
0x18000c043  test    eax, eax
0x18000c045  js      short loc_18000C097
0x18000c047  xor     ebx, ebx
0x18000c049  cmp     [rbp+47h+var_58], ebx
0x18000c04c  jnz     short loc_18000C057
0x18000c04e  cmp     [rbp+47h+arg_10], ebx
0x18000c051  jz      loc_18000BEFC
0x18000c057  mov     r8, [rbp+47h+p]; p
0x18000c05b  mov     edx, 7FFFFFFFh; i
0x18000c060  mov     rcx, rsi; hdpa
0x18000c063  call    cs:__imp_DPA_InsertPtr
0x18000c069  cmp     eax, 0FFFFFFFFh
0x18000c06c  jz      short loc_18000C0B7
0x18000c06e  inc     r14d
0x18000c071  mov     [rbp+47h+p], rbx
0x18000c075  cmp     [rbp+47h+arg_10], ebx
0x18000c078  jz      short loc_18000C07F
0x18000c07a  mov     dword ptr [rbp+47h+var_38], eax
0x18000c07d  inc     edi
0x18000c07f  test    r12b, 1
0x18000c083  jz      loc_18000BEFC
0x18000c089  cmp     edi, 1
0x18000c08c  jbe     loc_18000BEFC
0x18000c092  mov     ebx, 80040700h
0x18000c097  mov     r15, [rbp+47h+var_60]
0x18000c09b  mov     rdi, [rbp+47h+var_68]
0x18000c09f  mov     rcx, [rbp+47h+hMem]; hMem
0x18000c0a3  call    cs:__imp_LocalFree
0x18000c0a9  mov     rcx, rdi; hMem
0x18000c0ac  call    cs:__imp_LocalFree
0x18000c0b2  jmp     loc_18000C1B6
0x18000c0b7  mov     ebx, 80004005h
0x18000c0bc  jmp     short loc_18000C097
0x18000c0be  mov     eax, 1
0x18000c0c3  test    al, r12b
0x18000c0c6  jz      short loc_18000C11A
0x18000c0c8  cmp     r14d, eax
0x18000c0cb  jbe     short loc_18000C11A
0x18000c0cd  cmp     edi, eax
0x18000c0cf  jnz     short loc_18000C092
0x18000c0d1  lea     rcx, [rbp+47h+p]
0x18000c0d5  mov     r14d, eax
0x18000c0d8  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x18000c0dd  movsxd  rdx, dword ptr [rbp+47h+var_38]; i
0x18000c0e1  mov     rcx, rsi; hdpa
0x18000c0e4  call    cs:__imp_DPA_GetPtr
0x18000c0ea  mov     [rbp+47h+p], rax
0x18000c0ee  mov     rdx, rax
0x18000c0f1  mov     rcx, [rax]
0x18000c0f4  mov     rax, [rcx+8]
0x18000c0f8  mov     rcx, rdx
0x18000c0fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c100  mov     r8, [rbp+47h+p]; p
0x18000c104  xor     edx, edx; i
0x18000c106  mov     rcx, rsi; hdpa
0x18000c109  call    cs:__imp_DPA_InsertPtr
0x18000c10f  cmp     eax, 0FFFFFFFFh
0x18000c112  jz      short loc_18000C0B7
0x18000c114  mov     [rbp+47h+p], rbx
0x18000c118  jmp     short loc_18000C11F
0x18000c11a  test    r14d, r14d
0x18000c11d  jz      short loc_18000C197
0x18000c11f  mov     edx, r14d
0x18000c122  mov     ecx, 40h ; '@'; uFlags
0x18000c127  shl     rdx, 4; uBytes
0x18000c12b  call    cs:__imp_LocalAlloc
0x18000c131  mov     r15, rax
0x18000c134  test    rax, rax
0x18000c137  jnz     short loc_18000C143
0x18000c139  mov     ebx, 8007000Eh
0x18000c13e  jmp     loc_18000C09B
0x18000c143  mov     edi, r14d
0x18000c146  jmp     short loc_18000C14A
0x18000c148  xor     ebx, ebx
0x18000c14a  test    edi, edi
0x18000c14c  jz      short loc_18000C19B
0x18000c14e  lea     rcx, [rbp+47h+p]
0x18000c152  dec     edi
0x18000c154  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x18000c159  mov     edx, edi; i
0x18000c15b  mov     rcx, rsi; hdpa
0x18000c15e  mov     ebx, edi
0x18000c160  call    cs:__imp_DPA_GetPtr
0x18000c166  mov     [rbp+47h+p], rax
0x18000c16a  mov     rdx, rax
0x18000c16d  mov     rcx, [rax]
0x18000c170  mov     rax, [rcx+8]
0x18000c174  mov     rcx, rdx
0x18000c177  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c17c  mov     rcx, [rbp+47h+p]; struct IContact *
0x18000c180  add     rbx, rbx
0x18000c183  lea     rdx, [r15+rbx*8]; struct _SBinary *
0x18000c187  call    ?GetEntryIDFromIContact@@YAJPEAUIContact@@PEAU_SBinary@@@Z; GetEntryIDFromIContact(IContact *,_SBinary *)
0x18000c18c  mov     ebx, eax
0x18000c18e  test    eax, eax
0x18000c190  jns     short loc_18000C148
0x18000c192  jmp     loc_18000C09B
0x18000c197  mov     r15, [rbp+47h+var_60]
0x18000c19b  mov     rax, [rbp+47h+arg_28]
0x18000c19f  mov     [rax], r15
0x18000c1a2  mov     r15, rbx
  ... truncated ...
```
