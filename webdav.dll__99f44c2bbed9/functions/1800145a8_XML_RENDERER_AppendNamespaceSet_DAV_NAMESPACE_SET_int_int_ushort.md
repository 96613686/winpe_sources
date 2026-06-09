# XML_RENDERER::AppendNamespaceSet(DAV_NAMESPACE_SET *,int,int,ushort)

- ea: `0x1800145a8`
- end: `0x180014ae0`
- name: `?AppendNamespaceSet@XML_RENDERER@@AEAAJPEAVDAV_NAMESPACE_SET@@HHG@Z`
- size: `1336`
- prototype: `__int64 __usercall@<rax>(XML_RENDERER *__hidden this@<rcx>, struct DAV_NAMESPACE_SET *@<rdx>, int@<r8d>, int@<r9d>, unsigned __int16)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180015790`
- `0x1800158a8`

## callees

- `0x180014104`
- `0x1800145a8`
- `0x180014b90`
- `0x180014e44`
- `0x180014ef4`
- `0x180022520`
- `0x180023010`

## import_xrefs

- `iisutil!??1STRA@@QEAA@XZ` at `0x180014ab1`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180014ab1`
- `iisutil!??0STRA@@QEAA@XZ` at `0x1800145f1`
- `iisutil!??0STRA@@QEAA@XZ` at `0x1800145f1`

## pseudocode

```c
__int64 __fastcall XML_RENDERER::AppendNamespaceSet(
        XML_RENDERER *this,
        struct DAV_NAMESPACE_SET *a2,
        int a3,
        int a4,
        unsigned __int16 a5)
{
  int appended; // ebx
  __int64 v9; // rdx
  __int64 v10; // r8
  unsigned __int16 *v11; // r15
  __int64 (__fastcall **v12)(char *); // rax
  unsigned __int16 *v13; // rdi
  unsigned __int16 *v14; // r12
  struct DAV_PROPERTY_SET *v15; // r13
  unsigned int i; // ecx
  __int64 v17; // rdx
  int v18; // r15d
  __int64 v19; // rax
  __int64 v20; // rdx
  __int64 v21; // r14
  unsigned __int16 v22; // r8
  const unsigned __int16 *v23; // rdi
  const unsigned __int16 *v24; // rbx
  const unsigned __int16 *v25; // rax
  int v26; // eax
  struct DAV_PROPERTY_SET *NextPropertySet; // rax
  __int64 (__fastcall **v28)(unsigned __int16 *, __int64, __int64); // rax
  int v29; // r12d
  unsigned __int16 *v30; // rax
  __int64 (__fastcall **v31)(char *); // rcx
  unsigned __int16 *v32; // r13
  unsigned __int16 *v33; // r14
  struct DAV_PROPERTY_SET *v34; // r15
  unsigned int j; // ecx
  __int64 v36; // rdx
  __int64 (__fastcall ***v37)(_QWORD); // rdi
  unsigned __int16 *v38; // rax
  __int64 (__fastcall **v39)(_QWORD); // rcx
  unsigned __int16 v40; // di
  unsigned __int16 v41; // r8
  int v43; // [rsp+30h] [rbp-91h]
  unsigned __int16 v44; // [rsp+30h] [rbp-91h]
  unsigned __int16 *v45; // [rsp+38h] [rbp-89h] BYREF
  int v46; // [rsp+40h] [rbp-81h]
  unsigned __int16 *v47; // [rsp+48h] [rbp-79h] BYREF
  int v48; // [rsp+50h] [rbp-71h]
  int v49; // [rsp+54h] [rbp-6Dh]
  DAV_NAMESPACE_SET *v50; // [rsp+58h] [rbp-69h]
  unsigned __int16 *v51; // [rsp+60h] [rbp-61h]
  __int128 v52; // [rsp+68h] [rbp-59h] BYREF
  __int64 v53; // [rsp+78h] [rbp-49h]
  __int128 v54; // [rsp+80h] [rbp-41h] BYREF
  __int64 v55; // [rsp+90h] [rbp-31h]
  _BYTE v56[56]; // [rsp+98h] [rbp-29h] BYREF

  v48 = a4;
  v49 = a3;
  v50 = a2;
  appended = 0;
  STRA::STRA((STRA *)v56);
  v11 = (unsigned __int16 *)((char *)a2 + 1064);
  v55 = 0;
  v53 = 0;
  v51 = (unsigned __int16 *)((char *)a2 + 1064);
  v54 = 0;
  v52 = 0;
  if ( a3 )
  {
    v12 = *(__int64 (__fastcall ***)(char *))v11;
    v43 = 0;
    v46 = 0;
    LODWORD(v55) = 1;
    v13 = (unsigned __int16 *)(*v12)((char *)a2 + 1064);
    v47 = v13;
    v14 = (unsigned __int16 *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v11 + 8LL))((char *)a2 + 1064);
    v45 = v14;
    v10 = 0;
    v15 = (struct DAV_NAMESPACE_SET *)((char *)a2 + 4400);
    while ( v15 )
    {
      *((_QWORD *)&v52 + 1) = 0;
      for ( i = 0; i < 0x83; ++i )
      {
        v17 = *((_QWORD *)v15 + i + 1);
        if ( v17 )
          break;
      }
      v18 = v46;
      v19 = v17 - 8;
      *(_QWORD *)&v52 = v17;
      v20 = -v17;
      DWORD2(v52) = i;
      v21 = v19 & -(__int64)(v20 != 0);
      do
      {
        if ( !v21 )
          break;
        v45 = (unsigned __int16 *)(**(__int64 (__fastcall ***)(__int64, __int64, __int64))v21)(v21, v20, v10);
        if ( (*(unsigned __int16 (__fastcall **)(__int64))(*(_QWORD *)v21 + 32LL))(v21) == 200 )
        {
          if ( !v18 )
          {
            appended = XML_RENDERER::OpenOrCloseXmlTag(this, "propstat", 0);
            if ( appended >= 0 )
            {
              appended = XML_RENDERER::AppendHttpStatus(this, 0xC8u, v22, "OK");
              if ( appended >= 0 )
                appended = XML_RENDERER::OpenOrCloseXmlTag(this, "prop", 0);
            }
            v18 = 1;
          }
          if ( appended >= 0 )
          {
            if ( !v13 || !*v13 )
              v14 = 0;
            if ( v48 )
            {
              appended = XML_RENDERER::AppendProperty((const char **)this, v14, v45, 0, 0, 0);
            }
            else
            {
              v23 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v21 + 24LL))(v21);
              v24 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
              v25 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v21 + 8LL))(v21);
              v26 = XML_RENDERER::AppendProperty((const char **)this, v14, v45, v25, v24, v23);
              v13 = v47;
              appended = v26;
            }
          }
        }
        else
        {
          v43 = 1;
        }
        v21 = (*(__int64 (__fastcall **)(struct DAV_PROPERTY_SET *, __int128 *))(*(_QWORD *)v15 + 56LL))(v15, &v52);
      }
      while ( appended >= 0 );
      v45 = v14;
      v46 = v18;
      NextPropertySet = DAV_NAMESPACE_SET::FindNextPropertySet(
                          v50,
                          (struct DAV_ITERATOR *)&v54,
                          (const unsigned __int16 **)&v47,
                          (const unsigned __int16 **)&v45);
      v11 = v51;
      v10 = 0;
      v15 = NextPropertySet;
      if ( appended < 0 )
        goto LABEL_61;
      v14 = v45;
      v13 = v47;
    }
    if ( v46 )
    {
      appended = XML_RENDERER::OpenOrCloseXmlTag(this, "prop", 1);
      if ( appended < 0 )
        goto LABEL_61;
      appended = XML_RENDERER::OpenOrCloseXmlTag(this, "propstat", 1);
      if ( appended < 0 )
        goto LABEL_61;
    }
    if ( !v43 )
      goto LABEL_61;
  }
  v28 = *(__int64 (__fastcall ***)(unsigned __int16 *, __int64, __int64))v11;
  v44 = 0;
  v29 = 0;
  LODWORD(v55) = 1;
  v30 = (unsigned __int16 *)(*v28)(v11, v9, v10);
  v31 = *(__int64 (__fastcall ***)(char *))v11;
  v32 = v30;
  v47 = v30;
  v33 = (unsigned __int16 *)v31[1]((char *)v11);
  v34 = (DAV_NAMESPACE_SET *)((char *)v50 + 4400);
  v45 = v33;
LABEL_31:
  if ( v34 )
  {
    *((_QWORD *)&v52 + 1) = 0;
    for ( j = 0; j < 0x83; ++j )
    {
      v36 = *((_QWORD *)v34 + j + 1);
      if ( v36 )
        break;
    }
    *(_QWORD *)&v52 = v36;
    DWORD2(v52) = j;
    v37 = (__int64 (__fastcall ***)(_QWORD))((v36 - 8) & -(__int64)(v36 != 0));
    while ( 1 )
    {
      if ( !v37 )
      {
LABEL_56:
        v45 = v33;
        v34 = DAV_NAMESPACE_SET::FindNextPropertySet(
                v50,
                (struct DAV_ITERATOR *)&v54,
                (const unsigned __int16 **)&v47,
                (const unsigned __int16 **)&v45);
        if ( appended < 0 )
          goto LABEL_61;
        v32 = v47;
        v33 = v45;
        goto LABEL_31;
      }
      v38 = (unsigned __int16 *)(**v37)(v37);
      v39 = *v37;
      v51 = v38;
      v40 = v39[4](v37);
      if ( !v40 )
        v40 = a5;
      if ( v40 == 200 )
      {
        if ( v49 )
          goto LABEL_55;
        v40 = 424;
      }
      if ( v40 == v44 )
        goto LABEL_50;
      v44 = v40;
      if ( v29 )
      {
        appended = XML_RENDERER::OpenOrCloseXmlTag(this, "prop", 1);
        if ( appended < 0 )
          goto LABEL_55;
        appended = XML_RENDERER::OpenOrCloseXmlTag(this, "propstat", 1);
        v29 = 0;
      }
      if ( appended >= 0 )
      {
        appended = XML_RENDERER::OpenOrCloseXmlTag(this, "propstat", 0);
        if ( appended >= 0 )
        {
          v29 = 1;
          appended = XML_RENDERER::AppendHttpStatus(this, v40, v41, 0);
          if ( appended >= 0 )
          {
            appended = XML_RENDERER::OpenOrCloseXmlTag(this, "prop", 0);
LABEL_50:
            if ( appended >= 0 )
            {
              if ( !v32 || !*v32 )
                v33 = 0;
              appended = XML_RENDERER::AppendProperty((const char **)this, v33, v51, 0, 0, 0);
            }
          }
        }
      }
LABEL_55:
      v37 = (__int64 (__fastcall ***)(_QWORD))(*(__int64 (__fastcall **)(struct DAV_PROPERTY_SET *, __int128 *))(*(_QWORD *)v34 + 56LL))(
                                                v34,
                                                &v52);
      if ( appended < 0 )
        goto LABEL_56;
    }
  }
  if ( v29 )
  {
    appended = XML_RENDERER::OpenOrCloseXmlTag(this, "prop", 1);
    if ( appended >= 0 )
      appended = XML_RENDERER::OpenOrCloseXmlTag(this, "propstat", 1);
  }
LABEL_61:
  STRA::~STRA((STRA *)v56);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x1800145a8  mov     [rsp-8+arg_10], rbx
0x1800145ad  push    rbp
0x1800145ae  push    rsi
0x1800145af  push    rdi
0x1800145b0  push    r12
0x1800145b2  push    r13
0x1800145b4  push    r14
0x1800145b6  push    r15
0x1800145b8  lea     rbp, [rsp-1Fh]
0x1800145bd  sub     rsp, 0E0h
0x1800145c4  mov     rax, cs:__security_cookie
0x1800145cb  xor     rax, rsp
0x1800145ce  mov     [rbp+4Fh+var_40], rax
0x1800145d2  mov     rsi, rcx
0x1800145d5  mov     [rbp+4Fh+var_C0], r9d
0x1800145d9  xor     r12d, r12d
0x1800145dc  mov     [rbp+4Fh+var_BC], r8d
0x1800145e0  lea     rcx, [rbp+4Fh+var_78]
0x1800145e4  mov     [rbp+4Fh+var_B8], rdx
0x1800145e8  mov     ebx, r12d
0x1800145eb  mov     edi, r8d
0x1800145ee  mov     r14, rdx
0x1800145f1  call    cs:__imp_??0STRA@@QEAA@XZ; STRA::STRA(void)
0x1800145f7  xor     eax, eax
0x1800145f9  lea     r15, [r14+428h]
0x180014600  mov     [rbp+4Fh+var_80], rax
0x180014604  xorps   xmm0, xmm0
0x180014607  mov     [rbp+4Fh+var_98], rax
0x18001460b  xorps   xmm1, xmm1
0x18001460e  mov     [rbp+4Fh+var_B0], r15
0x180014612  movups  [rbp+4Fh+var_90], xmm0
0x180014616  movups  [rbp+4Fh+var_A8], xmm1
0x18001461a  test    edi, edi
0x18001461c  jz      loc_180014886
0x180014622  mov     rax, [r15]
0x180014625  mov     rcx, r15
0x180014628  mov     [rsp+110h+var_E0], r12d
0x18001462d  mov     [rsp+110h+var_D0], r12d
0x180014632  mov     dword ptr [rbp+4Fh+var_80], 1
0x180014639  mov     rax, [rax]
0x18001463c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014641  mov     rdi, rax
0x180014644  mov     [rbp+4Fh+var_C8], rax
0x180014648  mov     rax, [r15]
0x18001464b  mov     rcx, r15
0x18001464e  mov     rax, [rax+8]
0x180014652  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014657  mov     r12, rax
0x18001465a  mov     [rsp+110h+var_D8], rax
0x18001465f  xor     r8d, r8d
0x180014662  lea     r13, [r14+1130h]
0x180014669  test    r13, r13
0x18001466c  jz      loc_180014838
0x180014672  mov     qword ptr [rbp+4Fh+var_A8+8], 0
0x18001467a  mov     ecx, r8d
0x18001467d  mov     eax, ecx
0x18001467f  mov     rdx, [r13+rax*8+8]
0x180014684  test    rdx, rdx
0x180014687  jnz     short loc_180014693
0x180014689  inc     ecx
0x18001468b  cmp     ecx, 83h
0x180014691  jb      short loc_18001467D
0x180014693  mov     r15d, [rsp+110h+var_D0]
0x180014698  lea     rax, [rdx-8]
0x18001469c  mov     qword ptr [rbp+4Fh+var_A8], rdx
0x1800146a0  neg     rdx
0x1800146a3  mov     dword ptr [rbp+4Fh+var_A8+8], ecx
0x1800146a6  sbb     r14, r14
0x1800146a9  and     r14, rax
0x1800146ac  test    r14, r14
0x1800146af  jz      loc_1800147F8
0x1800146b5  mov     rax, [r14]
0x1800146b8  mov     rcx, r14
0x1800146bb  mov     rax, [rax]
0x1800146be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800146c3  mov     [rsp+110h+var_D8], rax
0x1800146c8  mov     rcx, r14
0x1800146cb  mov     rax, [r14]
0x1800146ce  mov     rax, [rax+20h]
0x1800146d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800146d7  mov     ecx, 0C8h
0x1800146dc  cmp     ax, cx
0x1800146df  jnz     loc_1800147D1
0x1800146e5  xor     eax, eax
0x1800146e7  test    r15d, r15d
0x1800146ea  jnz     short loc_18001473E
0x1800146ec  xor     r8d, r8d; int
0x1800146ef  lea     rdx, aPropstat; "propstat"
0x1800146f6  mov     rcx, rsi; this
0x1800146f9  call    ?OpenOrCloseXmlTag@XML_RENDERER@@AEAAJPEBDH@Z; XML_RENDERER::OpenOrCloseXmlTag(char const *,int)
0x1800146fe  mov     ebx, eax
0x180014700  xor     eax, eax
0x180014702  test    ebx, ebx
0x180014704  js      short loc_180014738
0x180014706  mov     edx, 0C8h; unsigned __int16
0x18001470b  lea     r9, aOk; "OK"
0x180014712  mov     rcx, rsi; this
0x180014715  call    ?AppendHttpStatus@XML_RENDERER@@AEAAJGGPEBD@Z; XML_RENDERER::AppendHttpStatus(ushort,ushort,char const *)
0x18001471a  mov     ebx, eax
0x18001471c  xor     eax, eax
0x18001471e  test    ebx, ebx
0x180014720  js      short loc_180014738
0x180014722  xor     r8d, r8d; int
0x180014725  lea     rdx, aProp_0; "prop"
0x18001472c  mov     rcx, rsi; this
0x18001472f  call    ?OpenOrCloseXmlTag@XML_RENDERER@@AEAAJPEBDH@Z; XML_RENDERER::OpenOrCloseXmlTag(char const *,int)
0x180014734  mov     ebx, eax
0x180014736  xor     eax, eax
0x180014738  mov     r15d, 1
0x18001473e  test    ebx, ebx
0x180014740  js      loc_1800147D9
0x180014746  test    rdi, rdi
0x180014749  jz      short loc_180014750
0x18001474b  cmp     [rdi], ax
0x18001474e  jnz     short loc_180014753
0x180014750  mov     r12, rax
0x180014753  cmp     [rbp+4Fh+var_C0], eax
0x180014756  jz      short loc_180014779
0x180014758  mov     r8, [rsp+110h+var_D8]; unsigned __int16 *
0x18001475d  xor     r9d, r9d; unsigned __int16 *
0x180014760  mov     [rsp+110h+var_E8], rax; unsigned __int16 *
0x180014765  mov     rdx, r12; unsigned __int16 *
0x180014768  mov     rcx, rsi; this
0x18001476b  mov     [rsp+110h+var_F0], rax; unsigned __int16 *
0x180014770  call    ?AppendProperty@XML_RENDERER@@AEAAJPEBG0000@Z; XML_RENDERER::AppendProperty(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x180014775  mov     ebx, eax
0x180014777  jmp     short loc_1800147D9
0x180014779  mov     rax, [r14]
0x18001477c  mov     rcx, r14
0x18001477f  mov     rax, [rax+18h]
0x180014783  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014788  mov     rcx, [r14]
0x18001478b  mov     rdi, rax
0x18001478e  mov     rax, [rcx+10h]
0x180014792  mov     rcx, r14
0x180014795  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001479a  mov     rcx, [r14]
0x18001479d  mov     rbx, rax
0x1800147a0  mov     rax, [rcx+8]
0x1800147a4  mov     rcx, r14
0x1800147a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800147ac  mov     r8, [rsp+110h+var_D8]; unsigned __int16 *
0x1800147b1  mov     r9, rax; unsigned __int16 *
0x1800147b4  mov     rdx, r12; unsigned __int16 *
0x1800147b7  mov     [rsp+110h+var_E8], rdi; unsigned __int16 *
0x1800147bc  mov     rcx, rsi; this
0x1800147bf  mov     [rsp+110h+var_F0], rbx; unsigned __int16 *
0x1800147c4  call    ?AppendProperty@XML_RENDERER@@AEAAJPEBG0000@Z; XML_RENDERER::AppendProperty(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x1800147c9  mov     rdi, [rbp+4Fh+var_C8]
0x1800147cd  mov     ebx, eax
0x1800147cf  jmp     short loc_1800147D9
0x1800147d1  mov     [rsp+110h+var_E0], 1
0x1800147d9  mov     rax, [r13+0]
0x1800147dd  lea     rdx, [rbp+4Fh+var_A8]
0x1800147e1  mov     rcx, r13
0x1800147e4  mov     rax, [rax+38h]
0x1800147e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800147ed  mov     r14, rax
0x1800147f0  test    ebx, ebx
0x1800147f2  jns     loc_1800146AC
0x1800147f8  mov     rcx, [rbp+4Fh+var_B8]; this
0x1800147fc  lea     r9, [rsp+110h+var_D8]; unsigned __int16 **
0x180014801  lea     r8, [rbp+4Fh+var_C8]; unsigned __int16 **
0x180014805  mov     [rsp+110h+var_D8], r12
0x18001480a  lea     rdx, [rbp+4Fh+var_90]; struct DAV_ITERATOR *
0x18001480e  mov     [rsp+110h+var_D0], r15d
0x180014813  call    ?FindNextPropertySet@DAV_NAMESPACE_SET@@QEAAPEAVDAV_PROPERTY_SET@@PEAUDAV_ITERATOR@@PEAPEBG1@Z; DAV_NAMESPACE_SET::FindNextPropertySet(DAV_ITERATOR *,ushort const * *,ushort const * *)
0x180014818  mov     r15, [rbp+4Fh+var_B0]
0x18001481c  xor     r8d, r8d
0x18001481f  mov     r13, rax
0x180014822  test    ebx, ebx
0x180014824  js      loc_180014AAD
0x18001482a  mov     r12, [rsp+110h+var_D8]
0x18001482f  mov     rdi, [rbp+4Fh+var_C8]
0x180014833  jmp     loc_180014669
0x180014838  xor     edi, edi
0x18001483a  cmp     [rsp+110h+var_D0], edi
0x18001483e  jz      short loc_18001487A
0x180014840  lea     r8d, [rdi+1]; int
0x180014844  mov     rcx, rsi; this
0x180014847  lea     rdx, aProp_0; "prop"
0x18001484e  call    ?OpenOrCloseXmlTag@XML_RENDERER@@AEAAJPEBDH@Z; XML_RENDERER::OpenOrCloseXmlTag(char const *,int)
0x180014853  mov     ebx, eax
0x180014855  test    eax, eax
0x180014857  js      loc_180014AAD
0x18001485d  lea     r8d, [rdi+1]; int
0x180014861  mov     rcx, rsi; this
0x180014864  lea     rdx, aPropstat; "propstat"
0x18001486b  call    ?OpenOrCloseXmlTag@XML_RENDERER@@AEAAJPEBDH@Z; XML_RENDERER::OpenOrCloseXmlTag(char const *,int)
0x180014870  mov     ebx, eax
0x180014872  test    eax, eax
0x180014874  js      loc_180014AAD
0x18001487a  cmp     [rsp+110h+var_E0], edi
0x18001487e  jz      loc_180014AAD
0x180014884  jmp     short loc_180014888
0x180014886  xor     edi, edi
0x180014888  mov     rax, [r15]
0x18001488b  mov     rcx, r15
0x18001488e  mov     [rsp+110h+var_E0], edi
0x180014892  mov     r12d, edi
0x180014895  mov     dword ptr [rbp+4Fh+var_80], 1
0x18001489c  mov     rax, [rax]
0x18001489f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800148a4  mov     rcx, [r15]
0x1800148a7  mov     r13, rax
0x1800148aa  mov     [rbp+4Fh+var_C8], rax
0x1800148ae  mov     rax, [rcx+8]
0x1800148b2  mov     rcx, r15
0x1800148b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800148ba  mov     r15, [rbp+4Fh+var_B8]
0x1800148be  mov     r14, rax
0x1800148c1  add     r15, 1130h
0x1800148c8  mov     [rsp+110h+var_D8], rax
0x1800148cd  test    r15, r15
0x1800148d0  jz      loc_180014A76
0x1800148d6  mov     qword ptr [rbp+4Fh+var_A8+8], 0
0x1800148de  mov     ecx, edi
0x1800148e0  mov     eax, ecx
0x1800148e2  mov     rdx, [r15+rax*8+8]
0x1800148e7  test    rdx, rdx
0x1800148ea  jnz     short loc_1800148F6
0x1800148ec  inc     ecx
0x1800148ee  cmp     ecx, 83h
0x1800148f4  jb      short loc_1800148E0
0x1800148f6  lea     rax, [rdx-8]
0x1800148fa  mov     qword ptr [rbp+4Fh+var_A8], rdx
0x1800148fe  neg     rdx
0x180014901  mov     dword ptr [rbp+4Fh+var_A8+8], ecx
0x180014904  sbb     rdi, rdi
0x180014907  and     rdi, rax
0x18001490a  test    rdi, rdi
0x18001490d  jz      loc_180014A44
0x180014913  mov     rax, [rdi]
0x180014916  mov     rcx, rdi
0x180014919  mov     rax, [rax]
0x18001491c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014921  mov     rcx, [rdi]
0x180014924  mov     [rbp+4Fh+var_B0], rax
0x180014928  mov     rax, [rcx+20h]
0x18001492c  mov     rcx, rdi
0x18001492f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014934  movzx   edi, ax
0x180014937  mov     ecx, 0C8h
0x18001493c  xor     eax, eax
0x18001493e  test    di, di
0x180014941  cmovz   di, [rbp+4Fh+arg_20]
0x180014946  cmp     di, cx
0x180014949  jnz     short loc_180014959
0x18001494b  cmp     [rbp+4Fh+var_BC], eax
0x18001494e  jnz     loc_180014A26
0x180014954  mov     edi, 1A8h
0x180014959  cmp     di, word ptr [rsp+110h+var_E0]
0x18001495e  jz      loc_1800149F5
0x180014964  mov     word ptr [rsp+110h+var_E0], di
0x180014969  test    r12d, r12d
0x18001496c  jz      short loc_1800149A9
0x18001496e  mov     r8d, 1; int
0x180014974  lea     rdx, aProp_0; "prop"
0x18001497b  mov     rcx, rsi; this
0x18001497e  call    ?OpenOrCloseXmlTag@XML_RENDERER@@AEAAJPEBDH@Z; XML_RENDERER::OpenOrCloseXmlTag(char const *,int)
0x180014983  mov     ebx, eax
0x180014985  test    eax, eax
0x180014987  js      loc_180014A26
0x18001498d  mov     r8d, 1; int
0x180014993  lea     rdx, aPropstat; "propstat"
0x18001499a  mov     rcx, rsi; this
0x18001499d  call    ?OpenOrCloseXmlTag@XML_RENDERER@@AEAAJPEBDH@Z; XML_RENDERER::OpenOrCloseXmlTag(char const *,int)
0x1800149a2  mov     ebx, eax
0x1800149a4  xor     eax, eax
0x1800149a6  mov     r12d, eax
0x1800149a9  test    ebx, ebx
0x1800149ab  js      short loc_180014A26
0x1800149ad  xor     r8d, r8d; int
0x1800149b0  lea     rdx, aPropstat; "propstat"
0x1800149b7  mov     rcx, rsi; this
0x1800149ba  call    ?OpenOrCloseXmlTag@XML_RENDERER@@AEAAJPEBDH@Z; XML_RENDERER::OpenOrCloseXmlTag(char const *,int)
0x1800149bf  mov     ebx, eax
0x1800149c1  test    eax, eax
0x1800149c3  js      short loc_180014A26
0x1800149c5  xor     r9d, r9d; char *
0x1800149c8  movzx   edx, di; unsigned __int16
0x1800149cb  mov     rcx, rsi; this
0x1800149ce  mov     r12d, 1
0x1800149d4  call    ?AppendHttpStatus@XML_RENDERER@@AEAAJGGPEBD@Z; XML_RENDERER::AppendHttpStatus(ushort,ushort,char const *)
0x1800149d9  mov     ebx, eax
0x1800149db  test    eax, eax
0x1800149dd  js      short loc_180014A26
0x1800149df  xor     r8d, r8d; int
0x1800149e2  lea     rdx, aProp_0; "prop"
0x1800149e9  mov     rcx, rsi; this
0x1800149ec  call    ?OpenOrCloseXmlTag@XML_RENDERER@@AEAAJPEBDH@Z; XML_RENDERER::OpenOrCloseXmlTag(char const *,int)
0x1800149f1  mov     ebx, eax
0x1800149f3  xor     eax, eax
0x1800149f5  test    ebx, ebx
0x1800149f7  js      short loc_180014A26
0x1800149f9  test    r13, r13
0x1800149fc  jz      short loc_180014A05
0x1800149fe  cmp     [r13+0], ax
0x180014a03  jnz     short loc_180014A08
0x180014a05  mov     r14, rax
  ... truncated ...
```
