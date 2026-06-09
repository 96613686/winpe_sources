# ConfigMgr::SetReady(void)

- ea: `0x1800a7250`
- end: `0x1800a7732`
- name: `?SetReady@ConfigMgr@@SAJXZ`
- size: `1250`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180058ab0`

## callees

- `0x18000b140`
- `0x18000b46c`
- `0x18002cabc`
- `0x18002cca4`
- `0x18003cfe0`
- `0x180074908`
- `0x1800a68a0`
- `0x1800a6d08`
- `0x1800a7250`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x1800a72c0`
- `wbemcomn!GetMemLogObject` at `0x1800a72fe`
- `wbemcomn!GetMemLogObject` at `0x1800a7371`
- `wbemcomn!GetMemLogObject` at `0x1800a73af`
- `wbemcomn!GetMemLogObject` at `0x1800a741b`
- `wbemcomn!GetMemLogObject` at `0x1800a7459`
- `wbemcomn!GetMemLogObject` at `0x1800a74c7`
- `wbemcomn!GetMemLogObject` at `0x1800a7505`
- `wbemcomn!GetMemLogObject` at `0x1800a7562`
- `wbemcomn!GetMemLogObject` at `0x1800a75a0`
- `wbemcomn!GetMemLogObject` at `0x1800a75f9`
- `wbemcomn!GetMemLogObject` at `0x1800a7637`
- `wbemcomn!GetMemLogObject` at `0x1800a7697`
- `wbemcomn!GetMemLogObject` at `0x1800a76d5`
- `wbemcomn!GetMemLogObject` at `0x1800a72c0`
- `wbemcomn!GetMemLogObject` at `0x1800a72fe`
- `wbemcomn!GetMemLogObject` at `0x1800a7371`
- `wbemcomn!GetMemLogObject` at `0x1800a73af`
- `wbemcomn!GetMemLogObject` at `0x1800a741b`
- `wbemcomn!GetMemLogObject` at `0x1800a7459`
- `wbemcomn!GetMemLogObject` at `0x1800a74c7`
- `wbemcomn!GetMemLogObject` at `0x1800a7505`
- `wbemcomn!GetMemLogObject` at `0x1800a7562`
- `wbemcomn!GetMemLogObject` at `0x1800a75a0`
- `wbemcomn!GetMemLogObject` at `0x1800a75f9`
- `wbemcomn!GetMemLogObject` at `0x1800a7637`
- `wbemcomn!GetMemLogObject` at `0x1800a7697`
- `wbemcomn!GetMemLogObject` at `0x1800a76d5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a72cc`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a7309`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a737d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a73ba`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a7427`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a7464`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a74d3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a7510`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a756e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a75ab`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a7605`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a7642`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a76a3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a76e0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a72cc`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a7309`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a737d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a73ba`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a7427`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a7464`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a74d3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a7510`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a756e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a75ab`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a7605`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a7642`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a76a3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a76e0`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 ConfigMgr::SetReady(void)
{
  unsigned int DefaultSession; // ebx
  CMemoryLog *v1; // rax
  CMemoryLog *v2; // rax
  struct IWmiDbSession *v3; // rbx
  int v4; // edi
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v6; // rax
  CClientCnt *v7; // rcx
  __int64 v8; // rdx
  CMemoryLog *v10; // rax
  CMemoryLog *v11; // rax
  CMemoryLog *v12; // rax
  CMemoryLog *v13; // rax
  CMemoryLog *v14; // rax
  CMemoryLog *v15; // rax
  CMemoryLog *v16; // rax
  CMemoryLog *v17; // rax
  int v18; // ecx
  CMemoryLog *v19; // rax
  CMemoryLog *v20; // rax
  struct IWmiDbHandle *v21; // [rsp+50h] [rbp+30h] BYREF
  struct IWmiDbSession *v22; // [rsp+58h] [rbp+38h] BYREF
  struct IWmiDbHandle *v23; // [rsp+60h] [rbp+40h] BYREF

  v21 = 0;
  v22 = 0;
  if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_38f52a6b533d390cb272ca3924e37b8b_Traceguids);
  }
  DefaultSession = CRepository::GetDefaultSession(&v22);
  if ( (DefaultSession & 0x80000000) == 0 )
  {
    v3 = v22;
    v4 = CRepository::OpenEseNs(v22, L"root", &v21);
    if ( v4 < 0 )
    {
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, -1);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          16,
          WPP_38f52a6b533d390cb272ca3924e37b8b_Traceguids,
          (unsigned int)v4);
      }
      v6 = GetMemLogObject();
      CMemoryLog::Write(v6, v4);
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_24;
      }
      v8 = 17;
      goto LABEL_23;
    }
    v23 = v21;
    v4 = ConfigMgr::SetIdentificationObject(v21, v3);
    if ( v4 >= 0 )
    {
      CReleaseMe::release((CReleaseMe *)&v23);
      v4 = CRepository::OpenEseNs(v3, L"root\\default", &v21);
      if ( v4 < 0 )
      {
        v12 = GetMemLogObject();
        CMemoryLog::Write(v12, -1);
        if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            20,
            WPP_38f52a6b533d390cb272ca3924e37b8b_Traceguids,
            (unsigned int)v4);
        }
        v13 = GetMemLogObject();
        CMemoryLog::Write(v13, v4);
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_24;
        }
        v8 = 21;
LABEL_23:
        WPP_SF_d(*((_QWORD *)v7 + 2), v8, WPP_38f52a6b533d390cb272ca3924e37b8b_Traceguids, (unsigned int)v4);
LABEL_24:
        CReleaseMe::release((CReleaseMe *)&v22);
        return (unsigned int)v4;
      }
      v23 = v21;
      v4 = ConfigMgr::SetIdentificationObject(v21, v3);
      if ( v4 >= 0 )
      {
        DefaultSession = ConfigMgr::SetAdapStatusObject(v21, v3);
        if ( (DefaultSession & 0x80000000) == 0 )
        {
          CReleaseMe::release((CReleaseMe *)&v23);
          DefaultSession = ConfigMgr::PrepareForClients(v18);
          if ( (DefaultSession & 0x80000000) == 0 )
          {
            DefaultSession = 0;
          }
          else
          {
            v19 = GetMemLogObject();
            CMemoryLog::Write(v19, -1);
            if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                26,
                WPP_38f52a6b533d390cb272ca3924e37b8b_Traceguids,
                DefaultSession);
            }
            v20 = GetMemLogObject();
            CMemoryLog::Write(v20, DefaultSession);
            if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                27,
                WPP_38f52a6b533d390cb272ca3924e37b8b_Traceguids,
                DefaultSession);
            }
          }
        }
        else
        {
          v16 = GetMemLogObject();
          CMemoryLog::Write(v16, -1);
          if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              24,
              WPP_38f52a6b533d390cb272ca3924e37b8b_Traceguids,
              DefaultSession);
          }
          v17 = GetMemLogObject();
          CMemoryLog::Write(v17, DefaultSession);
          if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              25,
              WPP_38f52a6b533d390cb272ca3924e37b8b_Traceguids,
              DefaultSession);
          }
          CReleaseMe::release((CReleaseMe *)&v23);
        }
        CReleaseMe::release((CReleaseMe *)&v22);
        return DefaultSession;
      }
      v14 = GetMemLogObject();
      CMemoryLog::Write(v14, -1);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          22,
          WPP_38f52a6b533d390cb272ca3924e37b8b_Traceguids,
          (unsigned int)v4);
      }
      v15 = GetMemLogObject();
      CMemoryLog::Write(v15, v4);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          23,
          WPP_38f52a6b533d390cb272ca3924e37b8b_Traceguids,
          (unsigned int)v4);
      }
    }
    else
    {
      v10 = GetMemLogObject();
      CMemoryLog::Write(v10, -1);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          18,
          WPP_38f52a6b533d390cb272ca3924e37b8b_Traceguids,
          (unsigned int)v4);
      }
      v11 = GetMemLogObject();
      CMemoryLog::Write(v11, v4);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          19,
          WPP_38f52a6b533d390cb272ca3924e37b8b_Traceguids,
          (unsigned int)v4);
      }
    }
    CReleaseMe::release((CReleaseMe *)&v23);
    goto LABEL_24;
  }
  v1 = GetMemLogObject();
  CMemoryLog::Write(v1, -1);
  if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_38f52a6b533d390cb272ca3924e37b8b_Traceguids, DefaultSession);
  }
  v2 = GetMemLogObject();
  CMemoryLog::Write(v2, DefaultSession);
  if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_38f52a6b533d390cb272ca3924e37b8b_Traceguids, DefaultSession);
  }
  return DefaultSession;
}

```

## disassembly

```asm
0x1800a7250  mov     [rsp-28h+arg_18], rbx
0x1800a7255  push    rbp
0x1800a7256  push    rsi
0x1800a7257  push    rdi
0x1800a7258  push    r14
0x1800a725a  push    r15
0x1800a725c  mov     rbp, rsp
0x1800a725f  sub     rsp, 20h
0x1800a7263  mov     [rbp+arg_0], 0
0x1800a726b  mov     [rbp+arg_8], 0
0x1800a7273  lea     r15, WPP_GLOBAL_Control
0x1800a727a  lea     r14, WPP_38f52a6b533d390cb272ca3924e37b8b_Traceguids
0x1800a7281  mov     sil, 1
0x1800a7284  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a728b  cmp     rcx, r15
0x1800a728e  jz      short loc_1800A72AD
0x1800a7290  test    [rcx+1Ch], sil
0x1800a7294  jz      short loc_1800A72AD
0x1800a7296  cmp     byte ptr [rcx+19h], 5
0x1800a729a  jb      short loc_1800A72AD
0x1800a729c  mov     edx, 0Dh
0x1800a72a1  mov     r8, r14
0x1800a72a4  mov     rcx, [rcx+10h]
0x1800a72a8  call    WPP_SF_
0x1800a72ad  lea     rcx, [rbp+arg_8]; struct IWmiDbSession **
0x1800a72b1  call    ?GetDefaultSession@CRepository@@SAJPEAPEAUIWmiDbSession@@@Z; CRepository::GetDefaultSession(IWmiDbSession * *)
0x1800a72b6  mov     ebx, eax
0x1800a72b8  test    eax, eax
0x1800a72ba  jns     loc_1800A734C
0x1800a72c0  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800a72c6  or      edx, 0FFFFFFFFh
0x1800a72c9  mov     rcx, rax
0x1800a72cc  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800a72d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a72d9  cmp     rcx, r15
0x1800a72dc  jz      short loc_1800A72FE
0x1800a72de  test    [rcx+1Ch], sil
0x1800a72e2  jz      short loc_1800A72FE
0x1800a72e4  cmp     byte ptr [rcx+19h], 2
0x1800a72e8  jb      short loc_1800A72FE
0x1800a72ea  mov     edx, 0Eh
0x1800a72ef  mov     r9d, ebx
0x1800a72f2  mov     r8, r14
0x1800a72f5  mov     rcx, [rcx+10h]
0x1800a72f9  call    WPP_SF_d
0x1800a72fe  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800a7304  mov     edx, ebx
0x1800a7306  mov     rcx, rax
0x1800a7309  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800a730f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a7316  cmp     rcx, r15
0x1800a7319  jz      loc_1800A771F
0x1800a731f  test    [rcx+1Ch], sil
0x1800a7323  jz      loc_1800A771F
0x1800a7329  cmp     byte ptr [rcx+19h], 2
0x1800a732d  jb      loc_1800A771F
0x1800a7333  mov     edx, 0Fh
0x1800a7338  mov     r9d, ebx
0x1800a733b  mov     r8, r14
0x1800a733e  mov     rcx, [rcx+10h]
0x1800a7342  call    WPP_SF_d
0x1800a7347  jmp     loc_1800A771F
0x1800a734c  mov     rbx, [rbp+arg_8]
0x1800a7350  mov     [rbp+arg_8], rbx
0x1800a7354  lea     r8, [rbp+arg_0]; struct IWmiDbHandle **
0x1800a7358  lea     rdx, aRoot_0; "root"
0x1800a735f  mov     rcx, rbx; struct IWmiDbSession *
0x1800a7362  call    ?OpenEseNs@CRepository@@SAJPEAUIWmiDbSession@@PEBGPEAPEAUIWmiDbHandle@@@Z; CRepository::OpenEseNs(IWmiDbSession *,ushort const *,IWmiDbHandle * *)
0x1800a7367  mov     edi, eax
0x1800a7369  test    eax, eax
0x1800a736b  jns     loc_1800A73FD
0x1800a7371  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800a7377  or      edx, 0FFFFFFFFh
0x1800a737a  mov     rcx, rax
0x1800a737d  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800a7383  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a738a  cmp     rcx, r15
0x1800a738d  jz      short loc_1800A73AF
0x1800a738f  test    [rcx+1Ch], sil
0x1800a7393  jz      short loc_1800A73AF
0x1800a7395  cmp     byte ptr [rcx+19h], 2
0x1800a7399  jb      short loc_1800A73AF
0x1800a739b  mov     edx, 10h
0x1800a73a0  mov     r9d, edi
0x1800a73a3  mov     r8, r14
0x1800a73a6  mov     rcx, [rcx+10h]
0x1800a73aa  call    WPP_SF_d
0x1800a73af  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800a73b5  mov     edx, edi
0x1800a73b7  mov     rcx, rax
0x1800a73ba  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800a73c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a73c7  cmp     rcx, r15
0x1800a73ca  jz      short loc_1800A73ED
0x1800a73cc  test    [rcx+1Ch], sil
0x1800a73d0  jz      short loc_1800A73ED
0x1800a73d2  cmp     byte ptr [rcx+19h], 2
0x1800a73d6  jb      short loc_1800A73ED
0x1800a73d8  mov     edx, 11h
0x1800a73dd  mov     r9d, edi
0x1800a73e0  mov     r8, r14
0x1800a73e3  mov     rcx, [rcx+10h]
0x1800a73e7  call    WPP_SF_d
0x1800a73ec  nop
0x1800a73ed  lea     rcx, [rbp+arg_8]; this
0x1800a73f1  call    ?release@CReleaseMe@@QEAAXXZ; CReleaseMe::release(void)
0x1800a73f6  mov     eax, edi
0x1800a73f8  jmp     loc_1800A7721
0x1800a73fd  mov     rax, [rbp+arg_0]
0x1800a7401  mov     [rbp+arg_10], rax
0x1800a7405  mov     rdx, rbx; struct IWmiDbSession *
0x1800a7408  mov     rcx, [rbp+arg_0]; struct IWmiDbHandle *
0x1800a740c  call    ?SetIdentificationObject@ConfigMgr@@SAJPEAUIWmiDbHandle@@PEAUIWmiDbSession@@@Z; ConfigMgr::SetIdentificationObject(IWmiDbHandle *,IWmiDbSession *)
0x1800a7411  mov     edi, eax
0x1800a7413  test    eax, eax
0x1800a7415  jns     loc_1800A74A5
0x1800a741b  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800a7421  or      edx, 0FFFFFFFFh
0x1800a7424  mov     rcx, rax
0x1800a7427  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800a742d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a7434  cmp     rcx, r15
0x1800a7437  jz      short loc_1800A7459
0x1800a7439  test    [rcx+1Ch], sil
0x1800a743d  jz      short loc_1800A7459
0x1800a743f  cmp     byte ptr [rcx+19h], 2
0x1800a7443  jb      short loc_1800A7459
0x1800a7445  mov     edx, 12h
0x1800a744a  mov     r9d, edi
0x1800a744d  mov     r8, r14
0x1800a7450  mov     rcx, [rcx+10h]
0x1800a7454  call    WPP_SF_d
0x1800a7459  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800a745f  mov     edx, edi
0x1800a7461  mov     rcx, rax
0x1800a7464  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800a746a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a7471  cmp     rcx, r15
0x1800a7474  jz      short loc_1800A7497
0x1800a7476  test    [rcx+1Ch], sil
0x1800a747a  jz      short loc_1800A7497
0x1800a747c  cmp     byte ptr [rcx+19h], 2
0x1800a7480  jb      short loc_1800A7497
0x1800a7482  mov     edx, 13h
0x1800a7487  mov     r9d, edi
0x1800a748a  mov     r8, r14
0x1800a748d  mov     rcx, [rcx+10h]
0x1800a7491  call    WPP_SF_d
0x1800a7496  nop
0x1800a7497  lea     rcx, [rbp+arg_10]; this
0x1800a749b  call    ?release@CReleaseMe@@QEAAXXZ; CReleaseMe::release(void)
0x1800a74a0  jmp     loc_1800A73ED
0x1800a74a5  lea     rcx, [rbp+arg_10]; this
0x1800a74a9  call    ?release@CReleaseMe@@QEAAXXZ; CReleaseMe::release(void)
0x1800a74ae  lea     r8, [rbp+arg_0]; struct IWmiDbHandle **
0x1800a74b2  lea     rdx, aRootDefault; "root\\default"
0x1800a74b9  mov     rcx, rbx; struct IWmiDbSession *
0x1800a74bc  call    ?OpenEseNs@CRepository@@SAJPEAUIWmiDbSession@@PEBGPEAPEAUIWmiDbHandle@@@Z; CRepository::OpenEseNs(IWmiDbSession *,ushort const *,IWmiDbHandle * *)
0x1800a74c1  mov     edi, eax
0x1800a74c3  test    eax, eax
0x1800a74c5  jns     short loc_1800A7544
0x1800a74c7  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800a74cd  or      edx, 0FFFFFFFFh
0x1800a74d0  mov     rcx, rax
0x1800a74d3  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800a74d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a74e0  cmp     rcx, r15
0x1800a74e3  jz      short loc_1800A7505
0x1800a74e5  test    [rcx+1Ch], sil
0x1800a74e9  jz      short loc_1800A7505
0x1800a74eb  cmp     byte ptr [rcx+19h], 2
0x1800a74ef  jb      short loc_1800A7505
0x1800a74f1  mov     edx, 14h
0x1800a74f6  mov     r9d, edi
0x1800a74f9  mov     r8, r14
0x1800a74fc  mov     rcx, [rcx+10h]
0x1800a7500  call    WPP_SF_d
0x1800a7505  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800a750b  mov     edx, edi
0x1800a750d  mov     rcx, rax
0x1800a7510  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800a7516  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a751d  cmp     rcx, r15
0x1800a7520  jz      loc_1800A73ED
0x1800a7526  test    [rcx+1Ch], sil
0x1800a752a  jz      loc_1800A73ED
0x1800a7530  cmp     byte ptr [rcx+19h], 2
0x1800a7534  jb      loc_1800A73ED
0x1800a753a  mov     edx, 15h
0x1800a753f  jmp     loc_1800A73DD
0x1800a7544  mov     rax, [rbp+arg_0]
0x1800a7548  mov     [rbp+arg_10], rax
0x1800a754c  mov     rdx, rbx; struct IWmiDbSession *
0x1800a754f  mov     rcx, [rbp+arg_0]; struct IWmiDbHandle *
0x1800a7553  call    ?SetIdentificationObject@ConfigMgr@@SAJPEAUIWmiDbHandle@@PEAUIWmiDbSession@@@Z; ConfigMgr::SetIdentificationObject(IWmiDbHandle *,IWmiDbSession *)
0x1800a7558  mov     edi, eax
0x1800a755a  test    eax, eax
0x1800a755c  jns     loc_1800A75E3
0x1800a7562  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800a7568  or      edx, 0FFFFFFFFh
0x1800a756b  mov     rcx, rax
0x1800a756e  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800a7574  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a757b  cmp     rcx, r15
0x1800a757e  jz      short loc_1800A75A0
0x1800a7580  test    [rcx+1Ch], sil
0x1800a7584  jz      short loc_1800A75A0
0x1800a7586  cmp     byte ptr [rcx+19h], 2
0x1800a758a  jb      short loc_1800A75A0
0x1800a758c  mov     edx, 16h
0x1800a7591  mov     r9d, edi
0x1800a7594  mov     r8, r14
0x1800a7597  mov     rcx, [rcx+10h]
0x1800a759b  call    WPP_SF_d
0x1800a75a0  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800a75a6  mov     edx, edi
0x1800a75a8  mov     rcx, rax
0x1800a75ab  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800a75b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a75b8  cmp     rcx, r15
0x1800a75bb  jz      short loc_1800A75DE
0x1800a75bd  test    [rcx+1Ch], sil
0x1800a75c1  jz      short loc_1800A75DE
0x1800a75c3  cmp     byte ptr [rcx+19h], 2
0x1800a75c7  jb      short loc_1800A75DE
0x1800a75c9  mov     edx, 17h
0x1800a75ce  mov     r9d, edi
0x1800a75d1  mov     r8, r14
0x1800a75d4  mov     rcx, [rcx+10h]
0x1800a75d8  call    WPP_SF_d
0x1800a75dd  nop
0x1800a75de  jmp     loc_1800A7497
0x1800a75e3  mov     rdx, rbx; struct IWmiDbSession *
0x1800a75e6  mov     rcx, [rbp+arg_0]; struct IWmiDbHandle *
0x1800a75ea  call    ?SetAdapStatusObject@ConfigMgr@@SAJPEAUIWmiDbHandle@@PEAUIWmiDbSession@@@Z; ConfigMgr::SetAdapStatusObject(IWmiDbHandle *,IWmiDbSession *)
0x1800a75ef  mov     ebx, eax
0x1800a75f1  test    eax, eax
0x1800a75f3  jns     loc_1800A7683
0x1800a75f9  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800a75ff  or      edx, 0FFFFFFFFh
0x1800a7602  mov     rcx, rax
0x1800a7605  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800a760b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a7612  cmp     rcx, r15
0x1800a7615  jz      short loc_1800A7637
0x1800a7617  test    [rcx+1Ch], sil
0x1800a761b  jz      short loc_1800A7637
0x1800a761d  cmp     byte ptr [rcx+19h], 2
0x1800a7621  jb      short loc_1800A7637
0x1800a7623  mov     edx, 18h
0x1800a7628  mov     r9d, ebx
0x1800a762b  mov     r8, r14
0x1800a762e  mov     rcx, [rcx+10h]
0x1800a7632  call    WPP_SF_d
0x1800a7637  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800a763d  mov     edx, ebx
0x1800a763f  mov     rcx, rax
0x1800a7642  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800a7648  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a764f  cmp     rcx, r15
0x1800a7652  jz      short loc_1800A7675
0x1800a7654  test    [rcx+1Ch], sil
0x1800a7658  jz      short loc_1800A7675
0x1800a765a  cmp     byte ptr [rcx+19h], 2
0x1800a765e  jb      short loc_1800A7675
0x1800a7660  mov     edx, 19h
0x1800a7665  mov     r9d, ebx
0x1800a7668  mov     r8, r14
0x1800a766b  mov     rcx, [rcx+10h]
0x1800a766f  call    WPP_SF_d
0x1800a7674  nop
0x1800a7675  lea     rcx, [rbp+arg_10]; this
0x1800a7679  call    ?release@CReleaseMe@@QEAAXXZ; CReleaseMe::release(void)
0x1800a767e  jmp     loc_1800A7716
0x1800a7683  lea     rcx, [rbp+arg_10]; this
0x1800a7687  call    ?release@CReleaseMe@@QEAAXXZ; CReleaseMe::release(void)
0x1800a768c  call    ?PrepareForClients@ConfigMgr@@SAJJ@Z; ConfigMgr::PrepareForClients(long)
0x1800a7691  mov     ebx, eax
0x1800a7693  test    eax, eax
0x1800a7695  jns     short loc_1800A7714
0x1800a7697  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800a769d  or      edx, 0FFFFFFFFh
0x1800a76a0  mov     rcx, rax
0x1800a76a3  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800a76a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a76b0  cmp     rcx, r15
0x1800a76b3  jz      short loc_1800A76D5
0x1800a76b5  test    [rcx+1Ch], sil
0x1800a76b9  jz      short loc_1800A76D5
0x1800a76bb  cmp     byte ptr [rcx+19h], 2
0x1800a76bf  jb      short loc_1800A76D5
0x1800a76c1  mov     edx, 1Ah
0x1800a76c6  mov     r9d, ebx
0x1800a76c9  mov     r8, r14
0x1800a76cc  mov     rcx, [rcx+10h]
0x1800a76d0  call    WPP_SF_d
0x1800a76d5  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800a76db  mov     edx, ebx
0x1800a76dd  mov     rcx, rax
0x1800a76e0  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
  ... truncated ...
```
