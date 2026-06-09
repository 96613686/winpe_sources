# CRepository::RecursiveDeleteClassesFromNamespace(IWmiDbSession *,ushort const *,CWStringArray &,bool)

- ea: `0x18008ce28`
- end: `0x18008d3be`
- name: `?RecursiveDeleteClassesFromNamespace@CRepository@@CAJPEAUIWmiDbSession@@PEBGAEAVCWStringArray@@_N@Z`
- size: `1430`
- prototype: `__int64 __fastcall(struct IWmiDbSession *, const unsigned __int16 *, struct CWStringArray *, bool)`
- caller_count: `2`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180070c74`
- `0x18008ce28`

## callees

- `0x18000aed8`
- `0x18000b140`
- `0x180019020`
- `0x18001cce0`
- `0x18001d390`
- `0x18002cca4`
- `0x18003cfe0`
- `0x18004d2f8`
- `0x180087094`
- `0x180089ccc`
- `0x18008ce28`
- `0x1800da010`

## import_xrefs

- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18008cf91`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18008d114`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18008cf91`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18008d114`
- `wbemcomn!??ACWStringArray@@QEBAPEAGH@Z` at `0x18008ced0`
- `wbemcomn!??ACWStringArray@@QEBAPEAGH@Z` at `0x18008d0eb`
- `wbemcomn!??ACWStringArray@@QEBAPEAGH@Z` at `0x18008d1f6`
- `wbemcomn!??ACWStringArray@@QEBAPEAGH@Z` at `0x18008ced0`
- `wbemcomn!??ACWStringArray@@QEBAPEAGH@Z` at `0x18008d0eb`
- `wbemcomn!??ACWStringArray@@QEBAPEAGH@Z` at `0x18008d1f6`
- `wbemcomn!?Size@CWStringArray@@QEBAHXZ` at `0x18008cec1`
- `wbemcomn!?Size@CWStringArray@@QEBAHXZ` at `0x18008cf06`
- `wbemcomn!?Size@CWStringArray@@QEBAHXZ` at `0x18008d0ca`
- `wbemcomn!?Size@CWStringArray@@QEBAHXZ` at `0x18008cec1`
- `wbemcomn!?Size@CWStringArray@@QEBAHXZ` at `0x18008cf06`
- `wbemcomn!?Size@CWStringArray@@QEBAHXZ` at `0x18008d0ca`
- `wbemcomn!??0CWStringArray@@QEAA@HH@Z` at `0x18008cf85`
- `wbemcomn!??0CWStringArray@@QEAA@HH@Z` at `0x18008cf85`
- `wbemcomn!??1CWStringArray@@QEAA@XZ` at `0x18008d325`
- `wbemcomn!??1CWStringArray@@QEAA@XZ` at `0x18008d325`
- `wbemcomn!GetMemLogObject` at `0x18008cf35`
- `wbemcomn!GetMemLogObject` at `0x18008cfd1`
- `wbemcomn!GetMemLogObject` at `0x18008d066`
- `wbemcomn!GetMemLogObject` at `0x18008d148`
- `wbemcomn!GetMemLogObject` at `0x18008d1a8`
- `wbemcomn!GetMemLogObject` at `0x18008d213`
- `wbemcomn!GetMemLogObject` at `0x18008d282`
- `wbemcomn!GetMemLogObject` at `0x18008d2bc`
- `wbemcomn!GetMemLogObject` at `0x18008d356`
- `wbemcomn!GetMemLogObject` at `0x18008cf35`
- `wbemcomn!GetMemLogObject` at `0x18008cfd1`
- `wbemcomn!GetMemLogObject` at `0x18008d066`
- `wbemcomn!GetMemLogObject` at `0x18008d148`
- `wbemcomn!GetMemLogObject` at `0x18008d1a8`
- `wbemcomn!GetMemLogObject` at `0x18008d213`
- `wbemcomn!GetMemLogObject` at `0x18008d282`
- `wbemcomn!GetMemLogObject` at `0x18008d2bc`
- `wbemcomn!GetMemLogObject` at `0x18008d356`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008cf40`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008cfe1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008d071`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008d153`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008d1b3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008d21e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008d28d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008d2cc`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008d361`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008cf40`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008cfe1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008d071`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008d153`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008d1b3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008d21e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008d28d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008d2cc`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008d361`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CRepository::RecursiveDeleteClassesFromNamespace(
        struct IWmiDbSession *a1,
        const unsigned __int16 *a2,
        struct CWStringArray *a3,
        char a4)
{
  int v8; // ebx
  unsigned int v9; // edi
  const unsigned __int16 *v10; // rax
  int v11; // eax
  CMemoryLog *v12; // rax
  CClientCnt *v13; // rcx
  __int64 v14; // rdx
  struct IWbemObjectSink *v15; // rax
  struct IWbemObjectSink *v16; // rbx
  CMemoryLog *v17; // rax
  CMemoryLog *v18; // rax
  CClientCnt *v19; // rcx
  __int64 v20; // rdx
  unsigned int i; // esi
  __int64 v22; // rbx
  __int64 v23; // rax
  __int64 v24; // rcx
  unsigned __int64 v25; // r14
  void *v26; // rax
  unsigned __int16 *v27; // rbx
  int v28; // edi
  CMemoryLog *v29; // rax
  int v30; // edi
  CMemoryLog *v31; // rax
  const unsigned __int16 *v32; // rax
  int v33; // edi
  CMemoryLog *v34; // rax
  CMemoryLog *v35; // rax
  CClientCnt *v36; // rcx
  __int64 v37; // rdx
  __int64 v38; // r9
  CMemoryLog *v39; // rax
  CMemoryLog *MemLogObject; // rax
  struct IWmiDbHandle *v42; // [rsp+30h] [rbp-69h] BYREF
  unsigned __int16 *v43; // [rsp+38h] [rbp-61h] BYREF
  struct IWbemObjectSink *v44; // [rsp+40h] [rbp-59h] BYREF
  struct IWmiDbHandle *v45; // [rsp+48h] [rbp-51h] BYREF
  _BYTE v46[160]; // [rsp+50h] [rbp-49h] BYREF

  if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_qS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      140,
      (unsigned int)WPP_3195b2018fcf36e0cdc4b4f2f02aaf3d_Traceguids,
      (_DWORD)a1,
      (__int64)a2);
  }
  v42 = 0;
  v8 = CRepository::OpenEseNs(a1, a2, &v42);
  v45 = v42;
  if ( v8 < 0 )
    goto LABEL_72;
  if ( a4 )
  {
    v9 = 0;
    if ( CWStringArray::Size(a3) )
    {
      while ( 1 )
      {
        v10 = (const unsigned __int16 *)CWStringArray::operator[](a3, v9);
        v8 = CRepository::DeleteByPath(a1, v42, v10, 0);
        if ( (int)(v8 + 0x80000000) >= 0 && v8 != -2147217406 )
          break;
        if ( ++v9 == CWStringArray::Size(a3) )
          goto LABEL_11;
      }
LABEL_72:
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, v8);
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v14 = 141;
        goto LABEL_76;
      }
      goto LABEL_77;
    }
  }
LABEL_11:
  v11 = CRepository::DeleteByPath(a1, v42, L"__classes", 0);
  v8 = 0;
  if ( v11 != -2147217406 )
    v8 = v11;
  if ( v8 >= 0 )
  {
    CWStringArray::CWStringArray((CWStringArray *)v46, 0, 100);
    v15 = (struct IWbemObjectSink *)CWin32DefaultArena::WbemMemAlloc(0x20u);
    v16 = v15;
    v43 = (unsigned __int16 *)v15;
    if ( v15 )
    {
      v15->lpVtbl = (struct IWbemObjectSinkVtbl *)&CUnkBase<IWbemObjectSink,&_GUID const IID_IWbemObjectSink>::`vftable';
      LODWORD(v15[1].lpVtbl) = 0;
      v15[2].lpVtbl = 0;
      v15->lpVtbl = (struct IWbemObjectSinkVtbl *)&CNamespaceListSink::`vftable';
      v15[3].lpVtbl = (struct IWbemObjectSinkVtbl *)v46;
    }
    else
    {
      v16 = 0;
    }
    if ( !v16 )
    {
      v17 = GetMemLogObject();
      v8 = -2147217402;
      CMemoryLog::Write(v17, -2147217402);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          143,
          WPP_3195b2018fcf36e0cdc4b4f2f02aaf3d_Traceguids,
          2147749894LL);
      }
      goto LABEL_67;
    }
    ((void (__fastcall *)(struct IWbemObjectSink *))v16->lpVtbl->AddRef)(v16);
    v44 = v16;
    v8 = CRepository::ExecQuery(a1, v42, L"select * from __namespace", v16, 0);
    if ( v8 >= 0 )
    {
      for ( i = 0; i != CWStringArray::Size((CWStringArray *)v46); ++i )
      {
        v22 = -1;
        do
          ++v22;
        while ( a2[v22] );
        v23 = CWStringArray::operator[](v46, i);
        v24 = -1;
        do
          ++v24;
        while ( *(_WORD *)(v23 + 2 * v24) );
        v25 = v22 + v24 + 2;
        v26 = CWin32DefaultArena::WbemMemAlloc(saturated_mul(v25, 2u));
        std::unique_ptr<IWbemClassObject * [0]>::unique_ptr<IWbemClassObject * [0]>(&v43, (__int64)v26);
        v27 = v43;
        if ( !v43 )
        {
          v39 = GetMemLogObject();
          v8 = -2147217402;
          CMemoryLog::Write(v39, -2147217402);
          v36 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v37 = 145;
            v38 = 2147749894LL;
LABEL_64:
            WPP_SF_d(*((_QWORD *)v36 + 2), v37, WPP_3195b2018fcf36e0cdc4b4f2f02aaf3d_Traceguids, v38);
          }
LABEL_65:
          std::unique_ptr<IUnknown * [0]>::~unique_ptr<IUnknown * [0]>((void **)&v43);
          goto LABEL_66;
        }
        v28 = StringCchCopyW(v43, v25, a2);
        if ( v28 < 0 )
        {
          v29 = GetMemLogObject();
          CMemoryLog::Write(v29, v28);
          if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              146,
              WPP_3195b2018fcf36e0cdc4b4f2f02aaf3d_Traceguids,
              (unsigned int)v28);
          }
        }
        v30 = StringCchCatW(v27, v25, L"\\");
        if ( v30 < 0 )
        {
          v31 = GetMemLogObject();
          CMemoryLog::Write(v31, v30);
          if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              147,
              WPP_3195b2018fcf36e0cdc4b4f2f02aaf3d_Traceguids,
              (unsigned int)v30);
          }
        }
        v32 = (const unsigned __int16 *)CWStringArray::operator[](v46, i);
        v33 = StringCchCatW(v27, v25, v32);
        if ( v33 < 0 )
        {
          v34 = GetMemLogObject();
          CMemoryLog::Write(v34, v33);
          if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              148,
              WPP_3195b2018fcf36e0cdc4b4f2f02aaf3d_Traceguids,
              (unsigned int)v33);
          }
        }
        v8 = CRepository::RecursiveDeleteClassesFromNamespace(a1, v27, a3, 1);
        if ( v8 < 0 )
        {
          v35 = GetMemLogObject();
          CMemoryLog::Write(v35, v8);
          v36 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v37 = 149;
            v38 = (unsigned int)v8;
            goto LABEL_64;
          }
          goto LABEL_65;
        }
        std::unique_ptr<IUnknown * [0]>::~unique_ptr<IUnknown * [0]>((void **)&v43);
      }
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_66;
      }
      v20 = 150;
    }
    else
    {
      v18 = GetMemLogObject();
      CMemoryLog::Write(v18, v8);
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_66;
      }
      v20 = 144;
    }
    WPP_SF_d(*((_QWORD *)v19 + 2), v20, WPP_3195b2018fcf36e0cdc4b4f2f02aaf3d_Traceguids, (unsigned int)v8);
LABEL_66:
    CReleaseMe::release((CReleaseMe *)&v44);
LABEL_67:
    CWStringArray::~CWStringArray((CWStringArray *)v46);
    goto LABEL_77;
  }
  v12 = GetMemLogObject();
  CMemoryLog::Write(v12, v8);
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v14 = 142;
LABEL_76:
    WPP_SF_d(*((_QWORD *)v13 + 2), v14, WPP_3195b2018fcf36e0cdc4b4f2f02aaf3d_Traceguids, (unsigned int)v8);
  }
LABEL_77:
  CReleaseMe::release((CReleaseMe *)&v45);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18008ce28  push    rbp
0x18008ce2a  push    rbx
0x18008ce2b  push    rsi
0x18008ce2c  push    rdi
0x18008ce2d  push    r12
0x18008ce2f  push    r13
0x18008ce31  push    r14
0x18008ce33  push    r15
0x18008ce35  lea     rbp, [rsp-1Fh]
0x18008ce3a  sub     rsp, 0B8h
0x18008ce41  mov     dil, r9b
0x18008ce44  mov     r13, r8
0x18008ce47  mov     r12, rdx
0x18008ce4a  mov     r15, rcx
0x18008ce4d  lea     rax, WPP_GLOBAL_Control
0x18008ce54  mov     esi, 1
0x18008ce59  mov     rcx, cs:WPP_GLOBAL_Control
0x18008ce60  cmp     rcx, rax
0x18008ce63  jz      short loc_18008CE8E
0x18008ce65  test    [rcx+1Ch], sil
0x18008ce69  jz      short loc_18008CE8E
0x18008ce6b  cmp     byte ptr [rcx+19h], 5
0x18008ce6f  jb      short loc_18008CE8E
0x18008ce71  mov     edx, 8Ch
0x18008ce76  mov     qword ptr [rsp+0F0h+var_D0], r12
0x18008ce7b  mov     r9, r15
0x18008ce7e  lea     r8, WPP_3195b2018fcf36e0cdc4b4f2f02aaf3d_Traceguids
0x18008ce85  mov     rcx, [rcx+10h]
0x18008ce89  call    WPP_SF_qS
0x18008ce8e  xor     r14d, r14d
0x18008ce91  mov     [rbp+57h+var_C0], r14
0x18008ce95  lea     r8, [rbp+57h+var_C0]; struct IWmiDbHandle **
0x18008ce99  mov     rdx, r12; unsigned __int16 *
0x18008ce9c  mov     rcx, r15; struct IWmiDbSession *
0x18008ce9f  call    ?OpenEseNs@CRepository@@SAJPEAUIWmiDbSession@@PEBGPEAPEAUIWmiDbHandle@@@Z; CRepository::OpenEseNs(IWmiDbSession *,ushort const *,IWmiDbHandle * *)
0x18008cea4  mov     ebx, eax
0x18008cea6  mov     rcx, [rbp+57h+var_C0]
0x18008ceaa  mov     [rbp+57h+var_A8], rcx
0x18008ceae  test    eax, eax
0x18008ceb0  js      loc_18008D356
0x18008ceb6  test    dil, dil
0x18008ceb9  jz      short loc_18008CF10
0x18008cebb  mov     edi, r14d
0x18008cebe  mov     rcx, r13
0x18008cec1  call    cs:__imp_?Size@CWStringArray@@QEBAHXZ; CWStringArray::Size(void)
0x18008cec7  test    eax, eax
0x18008cec9  jz      short loc_18008CF10
0x18008cecb  mov     edx, edi
0x18008cecd  mov     rcx, r13
0x18008ced0  call    cs:__imp_??ACWStringArray@@QEBAPEAGH@Z; CWStringArray::operator[](int)
0x18008ced6  xor     r9d, r9d; unsigned int
0x18008ced9  mov     r8, rax; unsigned __int16 *
0x18008cedc  mov     rdx, [rbp+57h+var_C0]; struct IWmiDbHandle *
0x18008cee0  mov     rcx, r15; struct IWmiDbSession *
0x18008cee3  call    ?DeleteByPath@CRepository@@SAJPEAUIWmiDbSession@@PEAUIWmiDbHandle@@PEBGK@Z; CRepository::DeleteByPath(IWmiDbSession *,IWmiDbHandle *,ushort const *,ulong)
0x18008cee8  mov     ebx, eax
0x18008ceea  mov     ecx, 80000000h
0x18008ceef  add     eax, ecx
0x18008cef1  test    ecx, eax
0x18008cef3  jnz     short loc_18008CF01
0x18008cef5  cmp     ebx, 80041002h
0x18008cefb  jnz     loc_18008D356
0x18008cf01  add     edi, esi
0x18008cf03  mov     rcx, r13
0x18008cf06  call    cs:__imp_?Size@CWStringArray@@QEBAHXZ; CWStringArray::Size(void)
0x18008cf0c  cmp     edi, eax
0x18008cf0e  jnz     short loc_18008CECB
0x18008cf10  xor     r9d, r9d; unsigned int
0x18008cf13  lea     r8, aClasses; "__classes"
0x18008cf1a  mov     rdx, [rbp+57h+var_C0]; struct IWmiDbHandle *
0x18008cf1e  mov     rcx, r15; struct IWmiDbSession *
0x18008cf21  call    ?DeleteByPath@CRepository@@SAJPEAUIWmiDbSession@@PEAUIWmiDbHandle@@PEBGK@Z; CRepository::DeleteByPath(IWmiDbSession *,IWmiDbHandle *,ushort const *,ulong)
0x18008cf26  mov     ebx, r14d
0x18008cf29  cmp     eax, 80041002h
0x18008cf2e  cmovnz  ebx, eax
0x18008cf31  test    ebx, ebx
0x18008cf33  jns     short loc_18008CF7B
0x18008cf35  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18008cf3b  mov     edx, ebx
0x18008cf3d  mov     rcx, rax
0x18008cf40  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18008cf46  mov     rcx, cs:WPP_GLOBAL_Control
0x18008cf4d  lea     rax, WPP_GLOBAL_Control
0x18008cf54  cmp     rcx, rax
0x18008cf57  jz      loc_18008D39F
0x18008cf5d  test    [rcx+1Ch], sil
0x18008cf61  jz      loc_18008D39F
0x18008cf67  cmp     byte ptr [rcx+19h], 2
0x18008cf6b  jb      loc_18008D39F
0x18008cf71  mov     edx, 8Eh
0x18008cf76  jmp     loc_18008D38B
0x18008cf7b  xor     edx, edx
0x18008cf7d  lea     r8d, [rdx+64h]
0x18008cf81  lea     rcx, [rbp+57h+var_A0]
0x18008cf85  call    cs:__imp_??0CWStringArray@@QEAA@HH@Z; CWStringArray::CWStringArray(int,int)
0x18008cf8b  nop
0x18008cf8c  mov     ecx, 20h ; ' '
0x18008cf91  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18008cf97  mov     rbx, rax
0x18008cf9a  mov     [rbp+57h+var_B8], rax
0x18008cf9e  test    rax, rax
0x18008cfa1  jz      short loc_18008CFC9
0x18008cfa3  lea     rax, ??_7?$CUnkBase@UIWbemObjectSink@@$1?IID_IWbemObjectSink@@3U_GUID@@B@@6B@; const CUnkBase<IWbemObjectSink,&_GUID const IID_IWbemObjectSink>::`vftable'
0x18008cfaa  mov     [rbx], rax
0x18008cfad  mov     [rbx+8], r14d
0x18008cfb1  mov     [rbx+10h], r14
0x18008cfb5  lea     rax, ??_7CNamespaceListSink@@6B@; const CNamespaceListSink::`vftable'
0x18008cfbc  mov     [rbx], rax
0x18008cfbf  lea     rax, [rbp+57h+var_A0]
0x18008cfc3  mov     [rbx+18h], rax
0x18008cfc7  jmp     short loc_18008CFCC
0x18008cfc9  mov     rbx, r14
0x18008cfcc  test    rbx, rbx
0x18008cfcf  jnz     short loc_18008D032
0x18008cfd1  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18008cfd7  mov     ebx, 80041006h
0x18008cfdc  mov     edx, ebx
0x18008cfde  mov     rcx, rax
0x18008cfe1  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18008cfe7  mov     rcx, cs:WPP_GLOBAL_Control
0x18008cfee  lea     rax, WPP_GLOBAL_Control
0x18008cff5  cmp     rcx, rax
0x18008cff8  jz      loc_18008D321
0x18008cffe  test    [rcx+1Ch], sil
0x18008d002  jz      loc_18008D321
0x18008d008  cmp     byte ptr [rcx+19h], 2
0x18008d00c  jb      loc_18008D321
0x18008d012  mov     edx, 8Fh
0x18008d017  mov     r9d, 80041006h
0x18008d01d  lea     r8, WPP_3195b2018fcf36e0cdc4b4f2f02aaf3d_Traceguids
0x18008d024  mov     rcx, [rcx+10h]
0x18008d028  call    WPP_SF_d
0x18008d02d  jmp     loc_18008D321
0x18008d032  mov     rax, [rbx]
0x18008d035  mov     rcx, rbx
0x18008d038  mov     rax, [rax+8]
0x18008d03c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008d041  mov     [rbp+57h+var_B0], rbx
0x18008d045  mov     [rsp+0F0h+var_D0], r14d; int
0x18008d04a  mov     r9, rbx; struct IWbemObjectSink *
0x18008d04d  lea     r8, aSelectFromName; "select * from __namespace"
0x18008d054  mov     rdx, [rbp+57h+var_C0]; struct IWmiDbHandle *
0x18008d058  mov     rcx, r15; struct IWmiDbSession *
0x18008d05b  call    ?ExecQuery@CRepository@@SAJPEAUIWmiDbSession@@PEAUIWmiDbHandle@@PEBGPEAUIWbemObjectSink@@J@Z; CRepository::ExecQuery(IWmiDbSession *,IWmiDbHandle *,ushort const *,IWbemObjectSink *,long)
0x18008d060  mov     ebx, eax
0x18008d062  test    eax, eax
0x18008d064  jns     short loc_18008D0BF
0x18008d066  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18008d06c  mov     edx, ebx
0x18008d06e  mov     rcx, rax
0x18008d071  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18008d077  mov     rcx, cs:WPP_GLOBAL_Control
0x18008d07e  lea     rax, WPP_GLOBAL_Control
0x18008d085  cmp     rcx, rax
0x18008d088  jz      loc_18008D317
0x18008d08e  test    [rcx+1Ch], sil
0x18008d092  jz      loc_18008D317
0x18008d098  cmp     byte ptr [rcx+19h], 2
0x18008d09c  jb      loc_18008D317
0x18008d0a2  mov     edx, 90h
0x18008d0a7  mov     r9d, ebx
0x18008d0aa  lea     r8, WPP_3195b2018fcf36e0cdc4b4f2f02aaf3d_Traceguids
0x18008d0b1  mov     rcx, [rcx+10h]
0x18008d0b5  call    WPP_SF_d
0x18008d0ba  jmp     loc_18008D317
0x18008d0bf  mov     esi, r14d
0x18008d0c2  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18008d0c6  lea     rcx, [rbp+57h+var_A0]
0x18008d0ca  call    cs:__imp_?Size@CWStringArray@@QEBAHXZ; CWStringArray::Size(void)
0x18008d0d0  cmp     esi, eax
0x18008d0d2  jz      loc_18008D32D
0x18008d0d8  mov     rbx, rdi
0x18008d0db  inc     rbx
0x18008d0de  cmp     [r12+rbx*2], r14w
0x18008d0e3  jnz     short loc_18008D0DB
0x18008d0e5  mov     edx, esi
0x18008d0e7  lea     rcx, [rbp+57h+var_A0]
0x18008d0eb  call    cs:__imp_??ACWStringArray@@QEBAPEAGH@Z; CWStringArray::operator[](int)
0x18008d0f1  mov     rcx, rdi
0x18008d0f4  inc     rcx
0x18008d0f7  cmp     [rax+rcx*2], r14w
0x18008d0fc  jnz     short loc_18008D0F4
0x18008d0fe  lea     r14, [rcx+2]
0x18008d102  add     r14, rbx
0x18008d105  mov     eax, 2
0x18008d10a  mul     r14
0x18008d10d  cmovb   rax, rdi
0x18008d111  mov     rcx, rax
0x18008d114  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18008d11a  mov     rdx, rax
0x18008d11d  lea     rcx, [rbp+57h+var_B8]
0x18008d121  call    ??0?$unique_ptr@$$BY0A@PEAUIWbemClassObject@@U?$default_delete@$$BY0A@PEAUIWbemClassObject@@@std@@@std@@QEAA@PEAPEAUIWbemClassObject@@@Z; std::unique_ptr<IWbemClassObject * [0]>::unique_ptr<IWbemClassObject * [0]>(IWbemClassObject * *)
0x18008d126  nop
0x18008d127  mov     rbx, [rbp+57h+var_B8]
0x18008d12b  test    rbx, rbx
0x18008d12e  jz      loc_18008D2BC
0x18008d134  mov     r8, r12; unsigned __int16 *
0x18008d137  mov     rdx, r14; unsigned __int64
0x18008d13a  mov     rcx, rbx; unsigned __int16 *
0x18008d13d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18008d142  mov     edi, eax
0x18008d144  test    eax, eax
0x18008d146  jns     short loc_18008D190
0x18008d148  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18008d14e  mov     edx, edi
0x18008d150  mov     rcx, rax
0x18008d153  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18008d159  mov     rcx, cs:WPP_GLOBAL_Control
0x18008d160  lea     rax, WPP_GLOBAL_Control
0x18008d167  cmp     rcx, rax
0x18008d16a  jz      short loc_18008D190
0x18008d16c  test    byte ptr [rcx+1Ch], 1
0x18008d170  jz      short loc_18008D190
0x18008d172  cmp     byte ptr [rcx+19h], 2
0x18008d176  jb      short loc_18008D190
0x18008d178  mov     edx, 92h
0x18008d17d  mov     r9d, edi
0x18008d180  lea     r8, WPP_3195b2018fcf36e0cdc4b4f2f02aaf3d_Traceguids
0x18008d187  mov     rcx, [rcx+10h]
0x18008d18b  call    WPP_SF_d
0x18008d190  lea     r8, Delimiter; "\\"
0x18008d197  mov     rdx, r14; unsigned __int64
0x18008d19a  mov     rcx, rbx; unsigned __int16 *
0x18008d19d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18008d1a2  mov     edi, eax
0x18008d1a4  test    eax, eax
0x18008d1a6  jns     short loc_18008D1F0
0x18008d1a8  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18008d1ae  mov     edx, edi
0x18008d1b0  mov     rcx, rax
0x18008d1b3  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18008d1b9  mov     rcx, cs:WPP_GLOBAL_Control
0x18008d1c0  lea     rax, WPP_GLOBAL_Control
0x18008d1c7  cmp     rcx, rax
0x18008d1ca  jz      short loc_18008D1F0
0x18008d1cc  test    byte ptr [rcx+1Ch], 1
0x18008d1d0  jz      short loc_18008D1F0
0x18008d1d2  cmp     byte ptr [rcx+19h], 2
0x18008d1d6  jb      short loc_18008D1F0
0x18008d1d8  mov     edx, 93h
0x18008d1dd  mov     r9d, edi
0x18008d1e0  lea     r8, WPP_3195b2018fcf36e0cdc4b4f2f02aaf3d_Traceguids
0x18008d1e7  mov     rcx, [rcx+10h]
0x18008d1eb  call    WPP_SF_d
0x18008d1f0  mov     edx, esi
0x18008d1f2  lea     rcx, [rbp+57h+var_A0]
0x18008d1f6  call    cs:__imp_??ACWStringArray@@QEBAPEAGH@Z; CWStringArray::operator[](int)
0x18008d1fc  mov     r8, rax; unsigned __int16 *
0x18008d1ff  mov     rdx, r14; unsigned __int64
0x18008d202  mov     rcx, rbx; unsigned __int16 *
0x18008d205  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18008d20a  mov     edi, eax
0x18008d20c  xor     r14d, r14d
0x18008d20f  test    eax, eax
0x18008d211  jns     short loc_18008D25B
0x18008d213  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18008d219  mov     edx, edi
0x18008d21b  mov     rcx, rax
0x18008d21e  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18008d224  mov     rcx, cs:WPP_GLOBAL_Control
0x18008d22b  lea     rax, WPP_GLOBAL_Control
0x18008d232  cmp     rcx, rax
0x18008d235  jz      short loc_18008D25B
0x18008d237  test    byte ptr [rcx+1Ch], 1
0x18008d23b  jz      short loc_18008D25B
0x18008d23d  cmp     byte ptr [rcx+19h], 2
0x18008d241  jb      short loc_18008D25B
0x18008d243  mov     edx, 94h
0x18008d248  mov     r9d, edi
0x18008d24b  lea     r8, WPP_3195b2018fcf36e0cdc4b4f2f02aaf3d_Traceguids
0x18008d252  mov     rcx, [rcx+10h]
0x18008d256  call    WPP_SF_d
0x18008d25b  mov     r9b, 1; bool
0x18008d25e  mov     r8, r13; struct CWStringArray *
0x18008d261  mov     rdx, rbx; unsigned __int16 *
0x18008d264  mov     rcx, r15; struct IWmiDbSession *
0x18008d267  call    ?RecursiveDeleteClassesFromNamespace@CRepository@@CAJPEAUIWmiDbSession@@PEBGAEAVCWStringArray@@_N@Z; CRepository::RecursiveDeleteClassesFromNamespace(IWmiDbSession *,ushort const *,CWStringArray &,bool)
0x18008d26c  mov     ebx, eax
0x18008d26e  test    eax, eax
0x18008d270  js      short loc_18008D282
0x18008d272  lea     rcx, [rbp+57h+var_B8]
0x18008d276  call    ??1?$unique_ptr@$$BY0A@PEAUIUnknown@@U?$default_delete@$$BY0A@PEAUIUnknown@@@std@@@std@@QEAA@XZ; std::unique_ptr<IUnknown * [0]>::~unique_ptr<IUnknown * [0]>(void)
0x18008d27b  inc     esi
0x18008d27d  jmp     loc_18008D0C2
0x18008d282  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18008d288  mov     edx, ebx
0x18008d28a  mov     rcx, rax
0x18008d28d  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18008d293  mov     rcx, cs:WPP_GLOBAL_Control
0x18008d29a  lea     rax, WPP_GLOBAL_Control
0x18008d2a1  cmp     rcx, rax
0x18008d2a4  jz      short loc_18008D30D
0x18008d2a6  test    byte ptr [rcx+1Ch], 1
0x18008d2aa  jz      short loc_18008D30D
0x18008d2ac  cmp     byte ptr [rcx+19h], 2
0x18008d2b0  jb      short loc_18008D30D
0x18008d2b2  mov     edx, 95h
0x18008d2b7  mov     r9d, ebx
0x18008d2ba  jmp     short loc_18008D2FC
0x18008d2bc  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
  ... truncated ...
```
