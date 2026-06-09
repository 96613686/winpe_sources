# CWbemNamespace::Initialize(ushort *,ushort *,ulong,ulong,int,int,ushort const *,ulong,int,IWmiDbSession *,ulong)

- ea: `0x18002ab80`
- end: `0x18002baef`
- name: `?Initialize@CWbemNamespace@@QEAAJPEAG0KKHHPEBGKHPEAUIWmiDbSession@@K@Z`
- size: `3951`
- prototype: `__int64 __usercall@<rax>(CWbemNamespace *__hidden this@<rcx>, unsigned __int16 *@<rdx>, unsigned __int16 *Src@<r8>, unsigned int@<r9d>, unsigned int, int, int, const unsigned __int16 *, unsigned int, int, struct IWmiDbSession *, unsigned int)`
- caller_count: `7`
- callee_count: `14`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x18001933c`
- `0x180026a00`
- `0x18002a998`
- `0x18002da30`
- `0x18005d9a8`
- `0x1800827d0`
- `0x1800be2d0`

## callees

- `0x18000abbc`
- `0x18000b140`
- `0x180021520`
- `0x18002ab80`
- `0x18002baf8`
- `0x18002bf10`
- `0x18002bf9c`
- `0x18002c010`
- `0x18002cabc`
- `0x18003cfe0`
- `0x1800614d0`
- `0x180088486`
- `0x1800ce510`
- `0x1800da010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18002ac80`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18002ac80`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18002acaa`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18002acaa`
- `wbemcomn!?GetStatus@CNtSid@@QEAAKXZ` at `0x18002acb5`
- `wbemcomn!?GetStatus@CNtSid@@QEAAKXZ` at `0x18002b511`
- `wbemcomn!?GetStatus@CNtSid@@QEAAKXZ` at `0x18002acb5`
- `wbemcomn!?GetStatus@CNtSid@@QEAAKXZ` at `0x18002b511`
- `wbemcomn!?GetStatus@CNtAce@@UEAAKXZ` at `0x18002ad2d`
- `wbemcomn!?GetStatus@CNtAce@@UEAAKXZ` at `0x18002ad2d`
- `wbemcomn!??0CNtAce@@QEAA@KKKAEAVCNtSid@@@Z` at `0x18002ad0a`
- `wbemcomn!??0CNtAce@@QEAA@KKKAEAVCNtSid@@@Z` at `0x18002ad0a`
- `wbemcomn!??0CNtSid@@QEAA@PEAX@Z` at `0x18002ac9b`
- `wbemcomn!??0CNtSid@@QEAA@PEAX@Z` at `0x18002ac9b`
- `wbemcomn!??1CNtSid@@QEAA@XZ` at `0x18002b143`
- `wbemcomn!??1CNtSid@@QEAA@XZ` at `0x18002b292`
- `wbemcomn!??1CNtSid@@QEAA@XZ` at `0x18002b302`
- `wbemcomn!??1CNtSid@@QEAA@XZ` at `0x18002b387`
- `wbemcomn!??1CNtSid@@QEAA@XZ` at `0x18002b3ed`
- `wbemcomn!??1CNtSid@@QEAA@XZ` at `0x18002b4b5`
- `wbemcomn!??1CNtSid@@QEAA@XZ` at `0x18002b4ff`
- `wbemcomn!??1CNtSid@@QEAA@XZ` at `0x18002b60d`
- `wbemcomn!??1CNtSid@@QEAA@XZ` at `0x18002b68c`
- `wbemcomn!??1CNtSid@@QEAA@XZ` at `0x18002b6f0`
- `wbemcomn!??1CNtSid@@QEAA@XZ` at `0x18002b754`
- `wbemcomn!??1CNtSid@@QEAA@XZ` at `0x18002b7b8`
- `wbemcomn!??1CNtSid@@QEAA@XZ` at `0x18002b86e`
- `wbemcomn!??1CNtSid@@QEAA@XZ` at `0x18002b94c`
- `wbemcomn!??1CNtSid@@QEAA@XZ` at `0x18002bad5`
- `wbemcomn!??1CNtSid@@QEAA@XZ` at `0x18002b143`
- `wbemcomn!??1CNtSid@@QEAA@XZ` at `0x18002b292`
- `wbemcomn!??1CNtSid@@QEAA@XZ` at `0x18002b302`
- `wbemcomn!??1CNtSid@@QEAA@XZ` at `0x18002b387`
- `wbemcomn!??1CNtSid@@QEAA@XZ` at `0x18002b3ed`
- `wbemcomn!??1CNtSid@@QEAA@XZ` at `0x18002b4b5`
- `wbemcomn!??1CNtSid@@QEAA@XZ` at `0x18002b4ff`
- `wbemcomn!??1CNtSid@@QEAA@XZ` at `0x18002b60d`
- `wbemcomn!??1CNtSid@@QEAA@XZ` at `0x18002b68c`
- `wbemcomn!??1CNtSid@@QEAA@XZ` at `0x18002b6f0`
- `wbemcomn!??1CNtSid@@QEAA@XZ` at `0x18002b754`
- `wbemcomn!??1CNtSid@@QEAA@XZ` at `0x18002b7b8`
- `wbemcomn!??1CNtSid@@QEAA@XZ` at `0x18002b86e`
- `wbemcomn!??1CNtSid@@QEAA@XZ` at `0x18002b94c`
- `wbemcomn!??1CNtSid@@QEAA@XZ` at `0x18002bad5`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18002acd8`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18002ad6b`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18002ae5c`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18002af72`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18002acd8`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18002ad6b`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18002ae5c`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18002af72`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18002af4d`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18002b7c8`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18002af4d`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18002b7c8`
- `wbemcomn!?IsOffline@CWbemInstallObject@@SA_NXZ` at `0x18002b18f`
- `wbemcomn!?IsOffline@CWbemInstallObject@@SA_NXZ` at `0x18002b18f`
- `wbemcomn!?CoCreateInstance@CWbemInstallObject@@SAJAEBU_GUID@@PEAUIUnknown@@K0PEAPEAX@Z` at `0x18002b0d3`
- `wbemcomn!?CoCreateInstance@CWbemInstallObject@@SAJAEBU_GUID@@PEAUIUnknown@@K0PEAPEAX@Z` at `0x18002b0d3`
- `wbemcomn!GetMemLogObject` at `0x18002b249`
- `wbemcomn!GetMemLogObject` at `0x18002b2d5`
- `wbemcomn!GetMemLogObject` at `0x18002b341`
- `wbemcomn!GetMemLogObject` at `0x18002b39c`
- `wbemcomn!GetMemLogObject` at `0x18002b3fb`
- `wbemcomn!GetMemLogObject` at `0x18002b452`
- `wbemcomn!GetMemLogObject` at `0x18002b55a`
- `wbemcomn!GetMemLogObject` at `0x18002b5bf`
- `wbemcomn!GetMemLogObject` at `0x18002b638`
- `wbemcomn!GetMemLogObject` at `0x18002b69c`
- `wbemcomn!GetMemLogObject` at `0x18002b700`
- `wbemcomn!GetMemLogObject` at `0x18002b764`
- `wbemcomn!GetMemLogObject` at `0x18002b7d3`
- `wbemcomn!GetMemLogObject` at `0x18002b821`
- `wbemcomn!GetMemLogObject` at `0x18002b8ed`
- `wbemcomn!GetMemLogObject` at `0x18002ba04`
- `wbemcomn!GetMemLogObject` at `0x18002ba76`
- `wbemcomn!GetMemLogObject` at `0x18002b249`
- `wbemcomn!GetMemLogObject` at `0x18002b2d5`
- `wbemcomn!GetMemLogObject` at `0x18002b341`
- `wbemcomn!GetMemLogObject` at `0x18002b39c`
- `wbemcomn!GetMemLogObject` at `0x18002b3fb`
- `wbemcomn!GetMemLogObject` at `0x18002b452`
- `wbemcomn!GetMemLogObject` at `0x18002b55a`
- `wbemcomn!GetMemLogObject` at `0x18002b5bf`
- `wbemcomn!GetMemLogObject` at `0x18002b638`
- `wbemcomn!GetMemLogObject` at `0x18002b69c`
- `wbemcomn!GetMemLogObject` at `0x18002b700`
- `wbemcomn!GetMemLogObject` at `0x18002b764`
- `wbemcomn!GetMemLogObject` at `0x18002b7d3`
- `wbemcomn!GetMemLogObject` at `0x18002b821`
- `wbemcomn!GetMemLogObject` at `0x18002b8ed`
- `wbemcomn!GetMemLogObject` at `0x18002ba04`
- `wbemcomn!GetMemLogObject` at `0x18002ba76`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002b257`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002b2e0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002b34c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002b3a8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002b409`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002b45e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002b568`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002b5ca`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002b646`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002b6aa`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002b70e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002b772`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002b7e1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002b82f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002b8fb`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002ba0f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002ba84`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002b257`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002b2e0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002b34c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002b3a8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002b409`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002b45e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002b568`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002b5ca`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002b646`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002b6aa`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002b70e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002b772`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002b7e1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002b82f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002b8fb`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002ba0f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002ba84`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CWbemNamespace::Initialize(
        CWbemNamespace *this,
        unsigned __int16 *a2,
        unsigned __int16 *Src,
        int a4,
        unsigned int a5,
        int a6,
        int a7,
        const unsigned __int16 *a8,
        unsigned int a9,
        int a10,
        struct IWmiDbSession *a11,
        unsigned int a12)
{
  const unsigned __int16 *v16; // rsi
  struct IWmiDbSession *v17; // rbx
  char v18; // al
  CNtAce *v19; // rcx
  struct IWmiDbSession *v20; // r14
  unsigned __int16 *v21; // rax
  CClientCnt *v22; // rcx
  void *v23; // r14
  const unsigned __int16 *v24; // r12
  void *v25; // rcx
  unsigned __int16 *v26; // rax
  _WORD *v27; // rax
  __int64 v28; // rcx
  void *v29; // rax
  void *v30; // r14
  __int64 v31; // r8
  __int64 *v32; // rdi
  __int64 *v33; // r14
  int v34; // r12d
  __int64 v35; // rcx
  __int64 v36; // rdi
  unsigned __int64 v37; // rdi
  unsigned __int16 *v38; // rdx
  int v39; // eax
  __int64 v40; // rcx
  __int64 v41; // r8
  unsigned __int16 v42; // ax
  int v43; // ecx
  int v44; // edi
  int v45; // edi
  __int64 v46; // rcx
  void *v47; // rax
  __int64 result; // rax
  struct IWmiDbSession *v49; // rdi
  int v50; // r14d
  CMemoryLog *v51; // rax
  signed int DefaultSession; // ebx
  CMemoryLog *v53; // rax
  CMemoryLog *v54; // rax
  CMemoryLog *v55; // rax
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v57; // rax
  int Status; // eax
  CMemoryLog *v59; // rax
  CMemoryLog *v60; // rax
  CMemoryLog *v61; // rax
  CMemoryLog *v62; // rax
  CMemoryLog *v63; // rax
  CMemoryLog *v64; // rax
  CMemoryLog *v65; // rax
  CMemoryLog *v66; // rax
  CMemoryLog *v67; // rax
  CMemoryLog *v68; // rax
  CMemoryLog *v69; // rax
  CMemoryLog *v70; // rax
  _BYTE v71[16]; // [rsp+60h] [rbp-B8h] BYREF
  void *v72; // [rsp+70h] [rbp-A8h] BYREF
  struct IWmiDbSession *v73; // [rsp+78h] [rbp-A0h] BYREF
  struct IWmiDbSession *v74; // [rsp+80h] [rbp-98h] BYREF
  int v75; // [rsp+88h] [rbp-90h]
  PSID pSid; // [rsp+90h] [rbp-88h] BYREF
  struct IWmiDbSession *v77; // [rsp+98h] [rbp-80h] BYREF
  unsigned __int16 *v78; // [rsp+A0h] [rbp-78h]
  __int64 i; // [rsp+A8h] [rbp-70h]
  _WORD *v80; // [rsp+B0h] [rbp-68h]
  const unsigned __int16 *v81; // [rsp+B8h] [rbp-60h]
  unsigned __int64 v82; // [rsp+C0h] [rbp-58h]
  __int64 v83; // [rsp+C8h] [rbp-50h]
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+D0h] [rbp-48h] BYREF

  v16 = a8;
  v17 = a11;
  v18 = a9;
  if ( a9 == -1 && a12 )
  {
    v18 = g_dwHostProcessId;
    a9 = g_dwHostProcessId;
  }
  if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_SSqd(*((_QWORD *)WPP_GLOBAL_Control + 2), (_DWORD)a2, (_DWORD)Src, (_DWORD)a2, (__int64)Src, (char)a11, v18);
  }
  try
  {
    *((_DWORD *)this + 27) = a4;
    *((_DWORD *)this + 26) = a5;
    if ( g_bDontAllowNewConnections )
    {
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, -2147217357);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, 2147749939LL);
      }
      return 2147749939LL;
    }
    pSid = 0;
    pIdentifierAuthority.Value[0] = 0;
    pIdentifierAuthority.Value[1] = 0;
    pIdentifierAuthority.Value[2] = 0;
    pIdentifierAuthority.Value[3] = 0;
    pIdentifierAuthority.Value[4] = 0;
    pIdentifierAuthority.Value[5] = 5;
    if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &pSid) )
    {
      v59 = GetMemLogObject();
      CMemoryLog::Write(v59, -2147217402);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, 2147749894LL);
      }
      return 2147749894LL;
    }
    CNtSid::CNtSid((CNtSid *)v71, pSid);
    FreeSid(pSid);
    if ( !CNtSid::GetStatus((CNtSid *)v71) )
    {
      v19 = (CNtAce *)*((_QWORD *)this + 29);
      if ( v19 )
      {
        CNtAce::`scalar deleting destructor'(v19, 1u);
        *((_QWORD *)this + 29) = 0;
      }
      v20 = (struct IWmiDbSession *)CWin32DefaultArena::WbemMemAlloc(0x18u);
      v74 = v20;
      if ( v20 )
      {
        CNtAce::CNtAce(v20, 1u, 0, 0, (struct CNtSid *)v71);
        *(_QWORD *)v20 = &CNtAce::`local vftable';
      }
      else
      {
        v20 = 0;
      }
      *((_QWORD *)this + 29) = v20;
      if ( v20 )
      {
        if ( CNtAce::GetStatus(v20) )
        {
          v62 = GetMemLogObject();
          CMemoryLog::Write(v62, -2147217402);
          if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              28,
              WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
              2147749894LL);
          }
        }
        else
        {
          *((_DWORD *)this + 32) = a6;
          v21 = StripServer(a2);
          *((_QWORD *)this + 11) = v21;
          if ( v21 )
          {
            *((_QWORD *)this + 12) = v21 + 4;
            v23 = CWin32DefaultArena::WbemMemAlloc(0x28u);
            v74 = (struct IWmiDbSession *)v23;
            if ( v23 )
            {
              *(_QWORD *)v23 = &CCoreServices::`vftable';
              *((_DWORD *)v23 + 2) = 0;
              *((_QWORD *)v23 + 4) = 0;
              CClientCnt::AddClientPtr(v22, (struct _LIST_ENTRY *)v23 + 1);
            }
            else
            {
              v23 = 0;
            }
            if ( v23 )
              _InterlockedIncrement((volatile signed __int32 *)v23 + 2);
            *((_QWORD *)this + 32) = v23;
            if ( v23 )
            {
              v24 = (const unsigned __int16 *)*((_QWORD *)this + 12);
              v25 = (void *)*((_QWORD *)v23 + 4);
              if ( v25 )
                CWin32DefaultArena::WbemMemFree(v25);
              v26 = Macro_CloneLPWSTR(v24);
              *((_QWORD *)v23 + 4) = v26;
              if ( v26 )
              {
                *((_QWORD *)this + 31) = 0;
                *((_DWORD *)this + 66) = a7;
                v27 = (_WORD *)*((_QWORD *)this + 12);
                v80 = v27;
                while ( *v27 )
                {
                  if ( *v27 == 47 )
                    *v27 = 92;
                  v80 = ++v27;
                }
                if ( Src )
                {
                  v28 = -1;
                  do
                    ++v28;
                  while ( Src[v28] );
                  v29 = CWin32DefaultArena::WbemMemAlloc(saturated_mul(v28 + 1, 2u));
                  v30 = v29;
                  if ( v29 )
                  {
                    v31 = -1;
                    do
                      ++v31;
                    while ( Src[v31] );
                    memcpy_0(v29, Src, 2 * v31 + 2);
                  }
                  else
                  {
                    v30 = 0;
                  }
                }
                else
                {
                  v30 = 0;
                }
                *((_QWORD *)this + 14) = v30;
                v32 = (__int64 *)((char *)this + 56);
                *((_QWORD *)this + 7) = 0;
                v74 = a11;
                if ( a11 )
                {
                  (*(void (__fastcall **)(struct IWmiDbSession *))(*(_QWORD *)a11 + 8LL))(a11);
                  goto LABEL_36;
                }
                DefaultSession = CRepository::GetDefaultSession(&v74);
                if ( DefaultSession >= 0 )
                {
                  v17 = v74;
LABEL_36:
                  v73 = v17;
                  v33 = (__int64 *)((char *)this + 64);
                  v34 = CRepository::OpenScope(
                          v17,
                          *((unsigned __int16 **)this + 12),
                          0,
                          (struct IWmiDbController **)this + 6,
                          (struct IWmiDbSession **)this + 5,
                          (struct IWmiDbHandle **)this + 8,
                          (struct IWmiDbHandle **)this + 7);
                  if ( v34 < 0 )
                  {
                    *((_DWORD *)this + 8) = -2147217394;
                    v55 = GetMemLogObject();
                    CMemoryLog::Write(v55, v34);
                    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                    {
                      WPP_SF_d(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        33,
                        WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
                        (unsigned int)v34);
                    }
                    if ( v17 )
                      (*(void (__fastcall **)(struct IWmiDbSession *))(*(_QWORD *)v17 + 16LL))(v17);
                    v73 = 0;
                    CNtSid::~CNtSid((CNtSid *)v71);
                    return (unsigned int)v34;
                  }
                  else if ( *v33 )
                  {
                    *((_DWORD *)this + 20) = 1;
                    v69 = GetMemLogObject();
                    CMemoryLog::Write(v69, -2147217394);
                    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                    {
                      WPP_SF_d(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        35,
                        WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
                        2147749902LL);
                    }
                    CReleaseMe::release((CReleaseMe *)&v73);
                    CNtSid::~CNtSid((CNtSid *)v71);
                    return 2147749902LL;
                  }
                  else
                  {
                    *((_DWORD *)this + 20) = 0;
                    v35 = *v32;
                    *v33 = *v32;
                    if ( v35 )
                    {
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 8LL))(v35);
                      *((_QWORD *)this + 31) = 0;
                      if ( a7 || (unsigned __int8)CWbemInstallObject::IsOffline() )
                      {
LABEL_40:
                        if ( !a8 )
                          goto LABEL_56;
                        CWin32DefaultArena::WbemMemFree(*((void **)this + 35));
                        v36 = -1;
                        do
                          ++v36;
                        while ( a8[v36] );
                        v37 = v36 + 1;
                        v38 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(saturated_mul(v37, 2u));
                        *((_QWORD *)this + 35) = v38;
                        if ( v38 )
                        {
                          v75 = 0;
                          if ( !v37 || (v39 = 0, v37 > 0x7FFFFFFF) )
                            v39 = -2147024809;
                          v75 = v39;
                          if ( v39 < 0 )
                          {
                            if ( v37 )
                              *v38 = 0;
                          }
                          else
                          {
                            v40 = 2147483646;
                            v83 = 2147483646;
                            v81 = a8;
                            v82 = v37;
                            v78 = v38;
                            v41 = 0;
                            for ( i = 0; v37; i = v41 )
                            {
                              if ( !v40 )
                                break;
                              v42 = *v16;
                              if ( !*v16 )
                                break;
                              v81 = ++v16;
                              *v38++ = v42;
                              v78 = v38;
                              v82 = --v37;
                              v83 = --v40;
                              ++v41;
                            }
                            v43 = 0;
                            if ( !v37 )
                            {
                              v78 = --v38;
                              i = v41 - 1;
                              v43 = -2147024774;
                            }
                            *v38 = 0;
                            v75 = v43;
                          }
                        }
                        if ( !*((_QWORD *)this + 35) )
                        {
                          v51 = GetMemLogObject();
                          CMemoryLog::Write(v51, -2147217402);
                          if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
                            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                          {
                            WPP_SF_d(
                              *((_QWORD *)WPP_GLOBAL_Control + 2),
                              37,
                              WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
                              2147749894LL);
                          }
                          if ( v17 )
                            (*(void (__fastcall **)(struct IWmiDbSession *))(*(_QWORD *)v17 + 16LL))(v17);
                          v73 = 0;
                          CNtSid::~CNtSid((CNtSid *)v71);
                          return 2147749894LL;
                        }
                        else
                        {
LABEL_56:
                          *((_DWORD *)this + 76) = a9;
                          *((_DWORD *)this + 8) = 0;
                          if ( a10 || (v44 = CWbemNamespace::InitializeSD(this, v17), v44 >= 0) )
                          {
                            (*(void (__fastcall **)(_QWORD, __int64, __int64))(**((_QWORD **)this + 32) + 96LL))(
                              *((_QWORD *)this + 32),
                              1,
                              1);
                            v72 = 0;
                            v74 = (struct IWmiDbSession *)&v72;
                            v45 = CWbemInstallObject::CoCreateInstance(
                                    &CLSID_WbemContext,
                                    0,
                                    1u,
                                    &IID_IWbemContext,
                                    &v72);
                            if ( v45 < 0 )
                            {
                              v68 = GetMemLogObject();
                              CMemoryLog::Write(v68, v45);
                              if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
                                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                              {
                                WPP_SF_d(
                                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                                  39,
                                  WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
                                  (unsigned int)v45);
                              }
                              if ( v72 )
                                (*(void (__fastcall **)(void *))(*(_QWORD *)v72 + 16LL))(v72);
                              v72 = 0;
                              CReleaseMe::release((CReleaseMe *)&v73);
                              CNtSid::~CNtSid((CNtSid *)v71);
                              return (unsigned int)v45;
                            }
                            else
                            {
                              v46 = *((_QWORD *)this + 48);
                              if ( v46 )
                                (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
                              v47 = v72;
                              v72 = 0;
                              *((_QWORD *)this + 48) = v47;
                              *((_DWORD *)this + 95) = a12;
                              if ( v72 )
                                (*(void (__fastcall **)(void *))(*(_QWORD *)v72 + 16LL))(v72);
                              v72 = 0;
                              if ( v17 )
                                (*(void (__fastcall **)(struct IWmiDbSession *))(*(_QWORD *)v17 + 16LL))(v17);
                              v73 = 0;
                              CNtSid::~CNtSid((CNtSid *)v71);
                              return 0;
                            }
                          }
                          else
                          {
                            v54 = GetMemLogObject();
                            CMemoryLog::Write(v54, v44);
                            if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
                              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                            {
                              WPP_SF_d(
                                *((_QWORD *)WPP_GLOBAL_Control + 2),
                                38,
                                WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
                                (unsigned int)v44);
                            }
                            if ( v17 )
                              (*(void (__fastcall **)(struct IWmiDbSession *))(*(_QWORD *)v17 + 16LL))(v17);
                            v73 = 0;
                            CNtSid::~CNtSid((CNtSid *)v71);
                            return (unsigned int)v44;
                          }
                        }
                      }
                      v77 = 0;
                      (*(void (__fastcall **)(_QWORD, _QWORD, struct IWmiDbSession **))(**((_QWORD **)this + 32) + 56LL))(
                        *((_QWORD *)this + 32),
                        0,
                        &v77);
                      v49 = v77;
                      v74 = v77;
                      if ( !v77
                        || (v50 = (*(__int64 (__fastcall **)(struct IWmiDbSession *, CWbemNamespace *, _QWORD, _QWORD, _QWORD, GUID *, char *))(*(_QWORD *)v77 + 32LL))(
                                    v77,
                                    this,
                                    0,
                                    0,
                                    *((_QWORD *)this + 12),
                                    &IID__IWmiProviderFactory,
                                    (char *)this + 248),
                            v50 >= 0) )
                      {
                        if ( v49 )
                          (*(void (__fastcall **)(struct IWmiDbSession *))(*(_QWORD *)v49 + 16LL))(v49);
                        v74 = 0;
                        goto LABEL_40;
                      }
                      v57 = GetMemLogObject();
                      CMemoryLog::Write(v57, v50);
                      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
                        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                      {
                        WPP_SF_d(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          36,
                          WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
                          (unsigned int)v50);
                      }
                      if ( v49 )
                        (*(void (__fastcall **)(struct IWmiDbSession *))(*(_QWORD *)v49 + 16LL))(v49);
                      v74 = 0;
                      if ( v17 )
                        (*(void (__fastcall **)(struct IWmiDbSession *))(*(_QWORD *)v17 + 16LL))(v17);
                      v73 = 0;
                      CNtSid::~CNtSid((CNtSid *)v71);
                      return (unsigned int)v50;
                    }
                    else
                    {
                      v67 = GetMemLogObject();
                      CMemoryLog::Write(v67, -2147217398);
                      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
                        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                      {
                        WPP_SF_d(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          34,
                          WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
                          2147749898LL);
                      }
                      CReleaseMe::release((CReleaseMe *)&v73);
                      CNtSid::~CNtSid((CNtSid *)v71);
                      return 2147749898LL;
                    }
                  }
                }
                v53 = GetMemLogObject();
                CMemoryLog::Write(v53, DefaultSession);
                if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    32,
                    WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
                    (unsigned int)DefaultSession);
                }
LABEL_82:
                CNtSid::~CNtSid((CNtSid *)v71);
                return (unsigned int)DefaultSession;
              }
              v65 = GetMemLogObject();
              CMemoryLog::Write(v65, -2147217402);
              if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  12,
                  WPP_28a6391408553a99477eaaaeeaa95c37_Traceguids,
                  2147749894LL);
              }
              v66 = GetMemLogObject();
              CMemoryLog::Write(v66, -2147217402);
              if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  31,
                  WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
                  2147749894LL);
              }
            }
            else
            {
              v64 = GetMemLogObject();
              CMemoryLog::Write(v64, -2147217402);
              if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  30,
                  WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
                  2147749894LL);
              }
            }
          }
          else
          {
            v63 = GetMemLogObject();
            CMemoryLog::Write(v63, -2147217402);
            if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                29,
                WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
                2147749894LL);
            }
          }
        }
      }
      else
      {
        v61 = GetMemLogObject();
        CMemoryLog::Write(v61, -2147217402);
        if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            27,
            WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
            2147749894LL);
        }
      }
      CNtSid::~CNtSid((CNtSid *)v71);
      return 2147749894LL;
    }
    Status = CNtSid::GetStatus((CNtSid *)v71);
    DefaultSession = Status;
    if ( Status > 0 )
      DefaultSession = (unsigned __int16)Status | 0x80070000;
    if ( DefaultSession < 0 )
    {
      v60 = GetMemLogObject();
      CMemoryLog::Write(v60, DefaultSession);
    }
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        26,
        WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
        (unsigned int)DefaultSession);
    }
    goto LABEL_82;
  }
  catch ( CX_MemoryException )
  {
    _InterlockedIncrement(&ExceptionCounter::s_Count);
    v70 = GetMemLogObject();
    CMemoryLog::Write(v70, -2147217402);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, 2147749894LL);
    }
    return 2147749894LL;
  }
  return result;
}

```

## disassembly

```asm
0x18002ab80  push    rbx
0x18002ab82  push    rsi
0x18002ab83  push    rdi
0x18002ab84  push    r12
0x18002ab86  push    r13
0x18002ab88  push    r14
0x18002ab8a  push    r15
0x18002ab8c  sub     rsp, 0E0h
0x18002ab93  mov     rax, cs:__security_cookie
0x18002ab9a  xor     rax, rsp
0x18002ab9d  mov     [rsp+118h+var_40], rax
0x18002aba5  mov     r14d, r9d
0x18002aba8  mov     rdi, r8
0x18002abab  mov     r12, rdx
0x18002abae  mov     r15, rcx
0x18002abb1  mov     rsi, [rsp+118h+arg_38]
0x18002abb9  mov     rbx, [rsp+118h+arg_50]
0x18002abc1  mov     eax, [rsp+118h+arg_40]
0x18002abc8  cmp     eax, 0FFFFFFFFh
0x18002abcb  jz      loc_18002B2A2
0x18002abd1  lea     r13, WPP_GLOBAL_Control
0x18002abd8  mov     rcx, cs:WPP_GLOBAL_Control
0x18002abdf  cmp     rcx, r13
0x18002abe2  jnz     loc_18002B23A
0x18002abe8  mov     [r15+6Ch], r14d
0x18002abec  mov     eax, [rsp+118h+arg_20]
0x18002abf3  mov     [r15+68h], eax
0x18002abf7  cmp     cs:?g_bDontAllowNewConnections@@3HA, 0; int g_bDontAllowNewConnections
0x18002abfe  jnz     loc_18002B3FB
0x18002ac04  xor     r13d, r13d
0x18002ac07  mov     [rsp+118h+var_88], r13
0x18002ac0f  mov     [rsp+118h+pIdentifierAuthority.Value], r13b
0x18002ac17  mov     [rsp+118h+pIdentifierAuthority.Value+1], r13b
0x18002ac1f  mov     [rsp+118h+pIdentifierAuthority.Value+2], r13b
0x18002ac27  mov     [rsp+118h+pIdentifierAuthority.Value+3], r13b
0x18002ac2f  mov     [rsp+118h+pIdentifierAuthority.Value+4], r13b
0x18002ac37  mov     [rsp+118h+pIdentifierAuthority.Value+5], 5
0x18002ac3f  lea     rax, [rsp+118h+var_88]
0x18002ac47  mov     [rsp+118h+pSid], rax; pSid
0x18002ac4c  mov     [rsp+118h+nSubAuthority7], r13d; nSubAuthority7
0x18002ac51  mov     [rsp+118h+nSubAuthority6], r13d; nSubAuthority6
0x18002ac56  mov     [rsp+118h+nSubAuthority5], r13d; nSubAuthority5
0x18002ac5b  mov     [rsp+118h+nSubAuthority4], r13d; nSubAuthority4
0x18002ac60  mov     [rsp+118h+nSubAuthority3], r13d; nSubAuthority3
0x18002ac65  mov     [rsp+118h+nSubAuthority2], r13d; nSubAuthority2
0x18002ac6a  mov     r9d, 220h; nSubAuthority1
0x18002ac70  mov     r8d, 20h ; ' '; nSubAuthority0
0x18002ac76  mov     dl, 2; nSubAuthorityCount
0x18002ac78  lea     rcx, [rsp+118h+pIdentifierAuthority]; pIdentifierAuthority
0x18002ac80  call    cs:__imp_AllocateAndInitializeSid
0x18002ac86  test    eax, eax
0x18002ac88  jz      loc_18002B55A
0x18002ac8e  mov     rdx, [rsp+118h+var_88]
0x18002ac96  lea     rcx, [rsp+118h+var_B8]
0x18002ac9b  call    cs:__imp_??0CNtSid@@QEAA@PEAX@Z; CNtSid::CNtSid(void *)
0x18002aca1  nop
0x18002aca2  mov     rcx, [rsp+118h+var_88]; pSid
0x18002acaa  call    cs:__imp_FreeSid
0x18002acb0  lea     rcx, [rsp+118h+var_B8]
0x18002acb5  call    cs:__imp_?GetStatus@CNtSid@@QEAAKXZ; CNtSid::GetStatus(void)
0x18002acbb  test    eax, eax
0x18002acbd  jnz     loc_18002B50C
0x18002acc3  mov     rcx, [r15+0E8h]; this
0x18002acca  test    rcx, rcx
0x18002accd  jnz     loc_18002B61A
0x18002acd3  mov     ecx, 18h
0x18002acd8  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18002acde  mov     r14, rax
0x18002ace1  mov     [rsp+118h+var_98], rax
0x18002ace9  test    rax, rax
0x18002acec  jz      loc_18002B630
0x18002acf2  lea     rax, [rsp+118h+var_B8]
0x18002acf7  mov     qword ptr [rsp+118h+nSubAuthority2], rax
0x18002acfc  xor     r9d, r9d
0x18002acff  xor     r8d, r8d
0x18002ad02  mov     edx, 1
0x18002ad07  mov     rcx, r14
0x18002ad0a  call    cs:__imp_??0CNtAce@@QEAA@KKKAEAVCNtSid@@@Z; CNtAce::CNtAce(ulong,ulong,ulong,CNtSid &)
0x18002ad10  lea     rax, ??_SCNtAce@@6B@; const CNtAce::`local vftable'
0x18002ad17  mov     [r14], rax
0x18002ad1a  mov     [r15+0E8h], r14
0x18002ad21  test    r14, r14
0x18002ad24  jz      loc_18002B638
0x18002ad2a  mov     rcx, r14
0x18002ad2d  call    cs:__imp_?GetStatus@CNtAce@@UEAAKXZ; CNtAce::GetStatus(void)
0x18002ad33  test    eax, eax
0x18002ad35  jnz     loc_18002B69C
0x18002ad3b  mov     eax, [rsp+118h+arg_28]
0x18002ad42  mov     [r15+80h], eax
0x18002ad49  mov     rcx, r12; unsigned __int16 *
0x18002ad4c  call    ?StripServer@@YAPEAGPEAG@Z; StripServer(ushort *)
0x18002ad51  mov     [r15+58h], rax
0x18002ad55  test    rax, rax
0x18002ad58  jz      loc_18002B700
0x18002ad5e  add     rax, 8
0x18002ad62  mov     [r15+60h], rax
0x18002ad66  mov     ecx, 28h ; '('
0x18002ad6b  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18002ad71  mov     r14, rax
0x18002ad74  mov     [rsp+118h+var_98], rax
0x18002ad7c  test    rax, rax
0x18002ad7f  jz      loc_18002B324
0x18002ad85  lea     rax, ??_7CCoreServices@@6B@; const CCoreServices::`vftable'
0x18002ad8c  mov     [r14], rax
0x18002ad8f  mov     [r14+8], r13d
0x18002ad93  mov     [r14+20h], r13
0x18002ad97  lea     rdx, [r14+10h]; struct _LIST_ENTRY *
0x18002ad9b  call    ?AddClientPtr@CClientCnt@@QEAA_NPEAU_LIST_ENTRY@@@Z; CClientCnt::AddClientPtr(_LIST_ENTRY *)
0x18002ada0  nop
0x18002ada1  test    r14, r14
0x18002ada4  jz      short loc_18002ADAB
0x18002ada6  lock inc dword ptr [r14+8]
0x18002adab  mov     [r15+100h], r14
0x18002adb2  test    r14, r14
0x18002adb5  jz      loc_18002B764
0x18002adbb  mov     r12, [r15+60h]
0x18002adbf  mov     rcx, [r14+20h]
0x18002adc3  test    rcx, rcx
0x18002adc6  jnz     loc_18002B7C8
0x18002adcc  mov     rcx, r12; Src
0x18002adcf  call    ?Macro_CloneLPWSTR@@YAPEAGPEBG@Z; Macro_CloneLPWSTR(ushort const *)
0x18002add4  mov     [r14+20h], rax
0x18002add8  test    rax, rax
0x18002addb  jz      loc_18002B7D3
0x18002ade1  mov     [r15+0F8h], r13
0x18002ade8  mov     eax, [rsp+118h+arg_30]
0x18002adef  mov     [r15+108h], eax
0x18002adf6  mov     rax, [r15+60h]
0x18002adfa  mov     [rsp+118h+var_68], rax
0x18002ae02  mov     edx, 5Ch ; '\'
0x18002ae07  movzx   ecx, word ptr [rax]
0x18002ae0a  test    cx, cx
0x18002ae0d  jz      short loc_18002AE27
0x18002ae0f  cmp     cx, 2Fh ; '/'
0x18002ae13  jz      loc_18002B31C
0x18002ae19  add     rax, 2
0x18002ae1d  mov     [rsp+118h+var_68], rax
0x18002ae25  jmp     short loc_18002AE07
0x18002ae27  test    rdi, rdi
0x18002ae2a  jz      loc_18002B886
0x18002ae30  mov     r13, 0FFFFFFFFFFFFFFFFh
0x18002ae37  mov     rcx, r13
0x18002ae3a  nop     word ptr [rax+rax+00h]
0x18002ae40  inc     rcx
0x18002ae43  cmp     word ptr [rdi+rcx*2], 0
0x18002ae48  jnz     short loc_18002AE40
0x18002ae4a  inc     rcx
0x18002ae4d  mov     eax, 2
0x18002ae52  mul     rcx
0x18002ae55  cmovb   rax, r13
0x18002ae59  mov     rcx, rax
0x18002ae5c  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18002ae62  mov     r14, rax
0x18002ae65  test    rax, rax
0x18002ae68  jz      loc_18002B87E
0x18002ae6e  mov     r8, r13
0x18002ae71  lea     r8, [r8+1]
0x18002ae75  cmp     word ptr [rdi+r8*2], 0
0x18002ae7b  jnz     short loc_18002AE71
0x18002ae7d  lea     r8, ds:2[r8*2]; Size
0x18002ae85  mov     rdx, rdi; Src
0x18002ae88  mov     rcx, rax; void *
0x18002ae8b  call    memcpy_0
0x18002ae90  mov     [r15+70h], r14
0x18002ae94  lea     rdi, [r15+38h]
0x18002ae98  mov     qword ptr [rdi], 0
0x18002ae9f  mov     [rsp+118h+var_98], rbx
0x18002aea7  test    rbx, rbx
0x18002aeaa  jz      loc_18002B2C2
0x18002aeb0  mov     rax, [rbx]
0x18002aeb3  mov     rcx, rbx
0x18002aeb6  mov     rax, [rax+8]
0x18002aeba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002aebf  mov     [rsp+118h+var_A0], rbx
0x18002aec4  lea     r14, [r15+40h]
0x18002aec8  lea     rax, [r15+28h]
0x18002aecc  lea     r9, [r15+30h]; struct IWmiDbController **
0x18002aed0  mov     qword ptr [rsp+118h+nSubAuthority4], rdi; struct IWmiDbHandle **
0x18002aed5  mov     qword ptr [rsp+118h+nSubAuthority3], r14; struct IWmiDbHandle **
0x18002aeda  mov     qword ptr [rsp+118h+nSubAuthority2], rax; struct IWmiDbSession **
0x18002aedf  xor     r8d, r8d; struct _GUID *
0x18002aee2  mov     rdx, [r15+60h]; unsigned __int16 *
0x18002aee6  mov     rcx, rbx; struct IWmiDbSession *
0x18002aee9  call    ?OpenScope@CRepository@@SAJPEAUIWmiDbSession@@PEAGPEAU_GUID@@PEAPEAUIWmiDbController@@PEAPEAU2@PEAPEAUIWmiDbHandle@@5@Z; CRepository::OpenScope(IWmiDbSession *,ushort *,_GUID *,IWmiDbController * *,IWmiDbSession * *,IWmiDbHandle * *,IWmiDbHandle * *)
0x18002aeee  mov     r12d, eax
0x18002aef1  test    eax, eax
0x18002aef3  js      loc_18002B394
0x18002aef9  cmp     qword ptr [r14], 0
0x18002aefd  jnz     loc_18002BA6E
0x18002af03  xor     r12d, r12d
0x18002af06  mov     [r15+50h], r12d
0x18002af0a  mov     rcx, [rdi]
0x18002af0d  mov     [r14], rcx
0x18002af10  test    rcx, rcx
0x18002af13  jz      loc_18002B8ED
0x18002af19  mov     rax, [rcx]
0x18002af1c  mov     rax, [rax+8]
0x18002af20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002af25  lea     r14, [r15+0F8h]
0x18002af2c  mov     [r14], r12
0x18002af2f  cmp     [rsp+118h+arg_30], r12d
0x18002af37  jz      loc_18002B18F
0x18002af3d  test    rsi, rsi
0x18002af40  jz      loc_18002B055
0x18002af46  mov     rcx, [r15+118h]
0x18002af4d  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18002af53  mov     rdi, r13
0x18002af56  inc     rdi
0x18002af59  cmp     word ptr [rsi+rdi*2], 0
0x18002af5e  jnz     short loc_18002AF56
0x18002af60  inc     rdi
0x18002af63  mov     eax, 2
0x18002af68  mul     rdi
0x18002af6b  cmovb   rax, r13
0x18002af6f  mov     rcx, rax
0x18002af72  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18002af78  mov     rdx, rax
0x18002af7b  mov     [r15+118h], rax
0x18002af82  test    rax, rax
0x18002af85  jz      loc_18002B047
0x18002af8b  mov     [rsp+118h+var_90], r12d
0x18002af93  test    rdi, rdi
0x18002af96  jnz     loc_18002B32C
0x18002af9c  mov     eax, 80070057h
0x18002afa1  mov     [rsp+118h+var_90], eax
0x18002afa8  test    eax, eax
0x18002afaa  js      loc_18002B98D
0x18002afb0  mov     ecx, 7FFFFFFEh
0x18002afb5  mov     [rsp+118h+var_50], rcx
0x18002afbd  mov     [rsp+118h+var_60], rsi
0x18002afc5  mov     [rsp+118h+var_58], rdi
0x18002afcd  mov     [rsp+118h+var_78], rdx
0x18002afd5  mov     r8, r12
0x18002afd8  mov     [rsp+118h+var_70], r12
0x18002afe0  test    rdi, rdi
0x18002afe3  jz      short loc_18002B030
0x18002afe5  test    rcx, rcx
0x18002afe8  jz      short loc_18002B030
0x18002afea  movzx   eax, word ptr [rsi]
0x18002afed  test    ax, ax
0x18002aff0  jz      short loc_18002B030
0x18002aff2  add     rsi, 2
0x18002aff6  mov     [rsp+118h+var_60], rsi
0x18002affe  mov     [rdx], ax
0x18002b001  add     rdx, 2
0x18002b005  mov     [rsp+118h+var_78], rdx
0x18002b00d  dec     rdi
0x18002b010  mov     [rsp+118h+var_58], rdi
0x18002b018  dec     rcx
0x18002b01b  mov     [rsp+118h+var_50], rcx
0x18002b023  inc     r8
0x18002b026  mov     [rsp+118h+var_70], r8
0x18002b02e  jmp     short loc_18002AFE0
0x18002b030  mov     ecx, r12d
0x18002b033  test    rdi, rdi
0x18002b036  jz      loc_18002B16E
0x18002b03c  mov     [rdx], r12w
0x18002b040  mov     [rsp+118h+var_90], ecx
0x18002b047  cmp     qword ptr [r15+118h], 0
0x18002b04f  jz      loc_18002B249
0x18002b055  mov     eax, [rsp+118h+arg_40]
0x18002b05c  mov     [r15+130h], eax
0x18002b063  mov     [r15+20h], r12d
0x18002b067  cmp     [rsp+118h+arg_48], 0
0x18002b06f  jnz     short loc_18002B086
0x18002b071  mov     rdx, rbx; struct IWmiDbSession *
0x18002b074  mov     rcx, r15; this
0x18002b077  call    ?InitializeSD@CWbemNamespace@@QEAAJPEAUIWmiDbSession@@@Z; CWbemNamespace::InitializeSD(IWmiDbSession *)
0x18002b07c  mov     edi, eax
0x18002b07e  test    eax, eax
0x18002b080  js      loc_18002B341
0x18002b086  mov     rcx, [r15+100h]
0x18002b08d  mov     rax, [rcx]
0x18002b090  mov     edx, 1
0x18002b095  mov     r8d, edx
0x18002b098  mov     rax, [rax+60h]
0x18002b09c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b0a1  mov     [rsp+118h+var_A8], r12
0x18002b0a6  lea     rax, [rsp+118h+var_A8]
0x18002b0ab  mov     [rsp+118h+var_98], rax
0x18002b0b3  lea     rax, [rsp+118h+var_A8]
0x18002b0b8  mov     qword ptr [rsp+118h+nSubAuthority2], rax
0x18002b0bd  lea     r9, IID_IWbemContext
0x18002b0c4  xor     edx, edx
0x18002b0c6  mov     r8d, 1
0x18002b0cc  lea     rcx, CLSID_WbemContext
0x18002b0d3  call    cs:__imp_?CoCreateInstance@CWbemInstallObject@@SAJAEBU_GUID@@PEAUIUnknown@@K0PEAPEAX@Z; CWbemInstallObject::CoCreateInstance(_GUID const &,IUnknown *,ulong,_GUID const &,void * *)
0x18002b0d9  mov     edi, eax
0x18002b0db  test    eax, eax
0x18002b0dd  js      loc_18002BA04
0x18002b0e3  mov     rcx, [r15+180h]
0x18002b0ea  test    rcx, rcx
0x18002b0ed  jnz     loc_18002BA5D
0x18002b0f3  mov     rax, [rsp+118h+var_A8]
0x18002b0f8  mov     [rsp+118h+var_A8], r12
0x18002b0fd  mov     [r15+180h], rax
0x18002b104  mov     eax, [rsp+118h+arg_58]
0x18002b10b  mov     [r15+17Ch], eax
0x18002b112  mov     rcx, [rsp+118h+var_A8]
0x18002b117  test    rcx, rcx
  ... truncated ...
```
