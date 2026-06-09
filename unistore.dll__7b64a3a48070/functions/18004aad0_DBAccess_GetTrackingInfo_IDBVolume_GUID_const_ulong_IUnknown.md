# DBAccess::GetTrackingInfo(IDBVolume *,_GUID const &,ulong,IUnknown * *)

- ea: `0x18004aad0`
- end: `0x18004ad14`
- name: `?GetTrackingInfo@DBAccess@@UEAAJPEAVIDBVolume@@AEBU_GUID@@KPEAPEAUIUnknown@@@Z`
- size: `580`
- prototype: `int(DBAccess *__hidden this, struct IDBVolume *, const struct _GUID *, unsigned int, struct IUnknown **)`
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180004440`
- `0x180035d40`
- `0x18003d100`
- `0x18003d668`
- `0x18004aad0`
- `0x180058490`
- `0x18006c458`
- `0x180071c5c`
- `0x1800736c4`
- `0x180079030`
- `0x1800c6010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004aafd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004aafd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004abc9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004abc9`
- `ntdll!RtlIsCriticalSectionLockedByThread` at `0x18004ab0a`
- `ntdll!RtlIsCriticalSectionLockedByThread` at `0x18004ab0a`

## pseudocode

```c
__int64 __fastcall DBAccess::GetTrackingInfo(
        DBAccess *this,
        struct IDBVolume *a2,
        const struct _GUID *a3,
        unsigned int a4,
        struct IUnknown **a5)
{
  struct _RTL_CRITICAL_SECTION *v5; // r15
  __int64 v6; // rsi
  __int64 v9; // rdx
  __int64 v10; // rcx
  char *v11; // rdi
  __int64 v12; // rdx
  unsigned __int64 v13; // r8
  char v14; // cl
  char *v15; // rbx
  char *v16; // rcx
  int v17; // eax
  __int64 v18; // r8
  unsigned int v19; // ebx
  struct IDBVolume *v21; // rcx
  int PartnerTickCount; // eax
  __int64 v23; // r8
  __int64 v24; // r9
  __int64 v25; // rdx
  __int64 v26; // rcx
  __int64 v27; // r8
  _DWORD *v28; // rax
  _DWORD *v29; // rbx
  struct ISyncSchema *v30; // rdx
  __int64 v31; // rdx
  __int64 v32; // rcx
  char *v33; // [rsp+30h] [rbp-40h] BYREF
  char v34; // [rsp+38h] [rbp-38h]
  char *v35; // [rsp+40h] [rbp-30h] BYREF
  int v36; // [rsp+50h] [rbp-20h]
  int v37; // [rsp+54h] [rbp-1Ch]
  struct ISyncSchema *v38; // [rsp+58h] [rbp-18h] BYREF
  unsigned __int64 v39; // [rsp+60h] [rbp-10h] BYREF
  __int64 v40; // [rsp+A0h] [rbp+30h] BYREF

  v5 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 16);
  v6 = a4;
  v33 = (char *)this + 16;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  v34 = 1;
  if ( !RtlIsCriticalSectionLockedByThread(v5) )
    Log_AssertionEvent_2(v10, v9, 632);
  v11 = (char *)this + 64;
  v12 = *((_QWORD *)this + 10);
  if ( v12 )
  {
    v13 = (0xC4CEB9FE1A85EC53uLL * ((0xFF51AFD7ED558CCDuLL * v6) ^ ((0xFF51AFD7ED558CCDuLL * v6) >> 33)))
        ^ ((0xC4CEB9FE1A85EC53uLL * ((0xFF51AFD7ED558CCDuLL * v6) ^ ((0xFF51AFD7ED558CCDuLL * v6) >> 33))) >> 33);
    v14 = *((_BYTE *)this + 96);
    v15 = *(char **)(v12 + 16 * (v13 & ((8LL << v14) - 1)));
    if ( v15 )
    {
      v16 = **(char ***)(v12 + 16 * (v13 & ((8LL << v14) - 1)) + 8);
      while ( v15 != v16 )
      {
        if ( *((_QWORD *)v15 + 2) >= v13 )
        {
          if ( *((_QWORD *)v15 + 2) > v13 )
            break;
          if ( (_DWORD)v6 == *((_DWORD *)v15 + 6) )
          {
            if ( v15 == v11 )
              break;
            goto LABEL_12;
          }
        }
        v15 = *(char **)v15;
      }
    }
  }
  v21 = (struct IDBVolume *)*((_QWORD *)this + 14);
  v36 = v6;
  v37 = 0;
  v38 = 0;
  v39 = 0;
  v40 = 0;
  PartnerTickCount = CSyncPartner::LoadPartnerSchema(v21, 0, v6, &v38);
  v19 = PartnerTickCount;
  if ( PartnerTickCount < 0 )
  {
    v24 = 646;
LABEL_18:
    v25 = 1;
    v26 = (unsigned int)PartnerTickCount;
LABEL_19:
    Log_UnistoreHREvent_13(v26, v25, v23, v24);
    ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v38);
    Log_UnistoreHREvent_13(v19, 1, v27, 693);
    goto LABEL_14;
  }
  PartnerTickCount = CSyncPartner::GetPartnerTickCount(*((struct IDBVolume **)this + 14), 0, v23, v6, &v39);
  v19 = PartnerTickCount;
  if ( PartnerTickCount < 0 )
  {
    v24 = 653;
    goto LABEL_18;
  }
  v28 = operator new(0x38u, (const struct std::nothrow_t *)&std::nothrow);
  v29 = v28;
  if ( v28 )
  {
    v30 = v38;
    v28[6] = v6;
    v28[8] = v36;
    ATL::CComPtrBase<IDBVolume>::CComPtrBase<IDBVolume>(v28 + 10, v30);
    *((_QWORD *)v29 + 6) = v39;
  }
  utl::_HashTable<unsigned long,utl::pair<unsigned long const,StoreInfo>,utl::hash<unsigned long>,utl::equal_to<unsigned long>,utl::allocator<utl::pair<unsigned long const,StoreInfo>>,0>::_EmplaceImpl(
    (char *)this + 64,
    &v35,
    v29);
  v15 = v35;
  if ( !v35 )
  {
    v19 = -2147024882;
    v25 = 0;
    v26 = 2147942414LL;
    v24 = 656;
    goto LABEL_19;
  }
  if ( v35 == v11 )
    Log_AssertionEvent_2(v32, v31, 659);
  ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v40);
  ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v38);
LABEL_12:
  v17 = (***((__int64 (__fastcall ****)(_QWORD, const struct _GUID *, struct IUnknown **))v15 + 5))(
          *((_QWORD *)v15 + 5),
          a3,
          a5);
  v19 = v17;
  if ( v17 < 0 )
  {
    Log_UnistoreHREvent_13((unsigned int)v17, 1, v18, 695);
    ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(&v33);
    return v19;
  }
  v19 = 0;
LABEL_14:
  LeaveCriticalSection(v5);
  return v19;
}

```

## disassembly

```asm
0x18004aad0  mov     [rsp-28h+arg_8], rbx
0x18004aad5  mov     [rsp-28h+arg_10], rsi
0x18004aada  push    rbp
0x18004aadb  push    rdi
0x18004aadc  push    r12
0x18004aade  push    r14
0x18004aae0  push    r15
0x18004aae2  mov     rbp, rsp
0x18004aae5  sub     rsp, 70h
0x18004aae9  lea     r15, [rcx+10h]
0x18004aaed  mov     esi, r9d
0x18004aaf0  mov     r14, rcx
0x18004aaf3  mov     [rbp+var_40], r15
0x18004aaf7  mov     rcx, r15; lpCriticalSection
0x18004aafa  mov     r12, r8
0x18004aafd  call    cs:__imp_EnterCriticalSection
0x18004ab03  mov     rcx, r15; CriticalSection
0x18004ab06  mov     [rbp+var_38], 1
0x18004ab0a  call    cs:__imp_RtlIsCriticalSectionLockedByThread
0x18004ab10  test    eax, eax
0x18004ab12  jnz     short loc_18004AB1F
0x18004ab14  mov     r8d, 278h
0x18004ab1a  call    Log_AssertionEvent_2
0x18004ab1f  lea     rdi, [r14+40h]
0x18004ab23  mov     rdx, [rdi+10h]
0x18004ab27  test    rdx, rdx
0x18004ab2a  jz      loc_18004ABEA
0x18004ab30  mov     rcx, 0FF51AFD7ED558CCDh
0x18004ab3a  mov     rax, rsi
0x18004ab3d  imul    rax, rcx
0x18004ab41  mov     rcx, rax
0x18004ab44  shr     rcx, 21h
0x18004ab48  xor     rcx, rax
0x18004ab4b  mov     rax, 0C4CEB9FE1A85EC53h
0x18004ab55  imul    rcx, rax
0x18004ab59  mov     eax, 8
0x18004ab5e  mov     r8, rcx
0x18004ab61  shr     r8, 21h
0x18004ab65  xor     r8, rcx
0x18004ab68  mov     cl, [rdi+20h]
0x18004ab6b  shl     rax, cl
0x18004ab6e  dec     rax
0x18004ab71  and     rax, r8
0x18004ab74  add     rax, rax
0x18004ab77  mov     rbx, [rdx+rax*8]
0x18004ab7b  test    rbx, rbx
0x18004ab7e  jz      short loc_18004ABEA
0x18004ab80  mov     rax, [rdx+rax*8+8]
0x18004ab85  mov     rcx, [rax]
0x18004ab88  cmp     rbx, rcx
0x18004ab8b  jz      short loc_18004ABEA
0x18004ab8d  cmp     [rbx+10h], r8
0x18004ab91  jb      short loc_18004AB9A
0x18004ab93  ja      short loc_18004ABEA
0x18004ab95  cmp     esi, [rbx+18h]
0x18004ab98  jz      short loc_18004AB9F
0x18004ab9a  mov     rbx, [rbx]
0x18004ab9d  jmp     short loc_18004AB88
0x18004ab9f  cmp     rbx, rdi
0x18004aba2  jz      short loc_18004ABEA
0x18004aba4  mov     rcx, [rbx+28h]
0x18004aba8  mov     rdx, r12
0x18004abab  mov     r8, [rbp+arg_20]
0x18004abaf  mov     rax, [rcx]
0x18004abb2  mov     rax, [rax]
0x18004abb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004abba  mov     ebx, eax
0x18004abbc  test    eax, eax
0x18004abbe  js      loc_18004ACF4
0x18004abc4  xor     ebx, ebx
0x18004abc6  mov     rcx, r15; lpCriticalSection
0x18004abc9  call    cs:__imp_LeaveCriticalSection
0x18004abcf  lea     r11, [rsp+70h+var_s0]
0x18004abd4  mov     eax, ebx
0x18004abd6  mov     rbx, [r11+38h]
0x18004abda  mov     rsi, [r11+40h]
0x18004abde  mov     rsp, r11
0x18004abe1  pop     r15
0x18004abe3  pop     r14
0x18004abe5  pop     r12
0x18004abe7  pop     rdi
0x18004abe8  pop     rbp
0x18004abe9  retn
0x18004abea  mov     rcx, [r14+70h]; struct IDBVolume *
0x18004abee  lea     r9, [rbp+var_18]; struct ISyncSchema **
0x18004abf2  xor     eax, eax
0x18004abf4  mov     [rbp+var_20], esi
0x18004abf7  mov     r8d, esi; unsigned int
0x18004abfa  mov     [rbp+var_1C], eax
0x18004abfd  xor     edx, edx; unsigned int
0x18004abff  mov     [rbp+var_18], rax
0x18004ac03  mov     [rbp+var_10], rax
0x18004ac07  mov     [rbp+arg_0], rax
0x18004ac0b  call    ?LoadPartnerSchema@CSyncPartner@@SAJPEAVIDBVolume@@KKPEAPEAUISyncSchema@@@Z; CSyncPartner::LoadPartnerSchema(IDBVolume *,ulong,ulong,ISyncSchema * *)
0x18004ac10  mov     ebx, eax
0x18004ac12  test    eax, eax
0x18004ac14  jns     short loc_18004AC45
0x18004ac16  mov     r9d, 286h
0x18004ac1c  mov     edx, 1
0x18004ac21  mov     ecx, eax
0x18004ac23  call    Log_UnistoreHREvent_13
0x18004ac28  lea     rcx, [rbp+var_18]; void *
0x18004ac2c  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x18004ac31  mov     edx, 1
0x18004ac36  mov     r9d, 2B5h
0x18004ac3c  mov     ecx, ebx
0x18004ac3e  call    Log_UnistoreHREvent_13
0x18004ac43  jmp     short loc_18004ABC6
0x18004ac45  mov     rcx, [r14+70h]; struct IDBVolume *
0x18004ac49  lea     rax, [rbp+var_10]
0x18004ac4d  mov     r9d, esi; unsigned int
0x18004ac50  mov     [rsp+70h+var_50], rax; unsigned __int64 *
0x18004ac55  xor     edx, edx; int
0x18004ac57  call    ?GetPartnerTickCount@CSyncPartner@@SAJPEAVIDBVolume@@HKKPEA_K@Z; CSyncPartner::GetPartnerTickCount(IDBVolume *,int,ulong,ulong,unsigned __int64 *)
0x18004ac5c  mov     ebx, eax
0x18004ac5e  test    eax, eax
0x18004ac60  jns     short loc_18004AC6A
0x18004ac62  mov     r9d, 28Dh
0x18004ac68  jmp     short loc_18004AC1C
0x18004ac6a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18004ac71  mov     ecx, 38h ; '8'; unsigned __int64
0x18004ac76  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18004ac7b  mov     rbx, rax
0x18004ac7e  test    rax, rax
0x18004ac81  jz      short loc_18004ACA1
0x18004ac83  mov     rdx, [rbp+var_18]
0x18004ac87  lea     rcx, [rbx+28h]
0x18004ac8b  mov     [rax+18h], esi
0x18004ac8e  mov     eax, [rbp+var_20]
0x18004ac91  mov     [rbx+20h], eax
0x18004ac94  call    ??0?$CComPtrBase@VIDBVolume@@@ATL@@IEAA@PEAVIDBVolume@@@Z; ATL::CComPtrBase<IDBVolume>::CComPtrBase<IDBVolume>(IDBVolume *)
0x18004ac99  mov     rax, [rbp+var_10]
0x18004ac9d  mov     [rbx+30h], rax
0x18004aca1  mov     r8, rbx
0x18004aca4  lea     rdx, [rbp+var_30]
0x18004aca8  mov     rcx, rdi
0x18004acab  call    ?_EmplaceImpl@?$_HashTable@KU?$pair@$$CBKUStoreInfo@@@utl@@U?$hash@K@2@U?$equal_to@K@2@V?$allocator@U?$pair@$$CBKUStoreInfo@@@utl@@@2@$0A@@utl@@AEAA?AU?$pair@V?$_DlistIt@U?$_HashNode@U?$pair@$$CBKUStoreInfo@@@utl@@@utl@@U?$pair@$$CBKUStoreInfo@@@2@@utl@@_N@2@PEAU?$_HashNode@U?$pair@$$CBKUStoreInfo@@@utl@@@2@@Z; utl::_HashTable<ulong,utl::pair<ulong const,StoreInfo>,utl::hash<ulong>,utl::equal_to<ulong>,utl::allocator<utl::pair<ulong const,StoreInfo>>,0>::_EmplaceImpl(utl::_HashNode<utl::pair<ulong const,StoreInfo>> *)
0x18004acb0  mov     rbx, [rbp+var_30]
0x18004acb4  test    rbx, rbx
0x18004acb7  jnz     short loc_18004ACCD
0x18004acb9  mov     ebx, 8007000Eh
0x18004acbe  xor     edx, edx
0x18004acc0  mov     ecx, ebx
0x18004acc2  mov     r9d, 290h
0x18004acc8  jmp     loc_18004AC23
0x18004accd  cmp     rbx, rdi
0x18004acd0  jnz     short loc_18004ACDD
0x18004acd2  mov     r8d, 293h
0x18004acd8  call    Log_AssertionEvent_2
0x18004acdd  lea     rcx, [rbp+arg_0]; void *
0x18004ace1  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x18004ace6  lea     rcx, [rbp+var_18]; void *
0x18004acea  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x18004acef  jmp     loc_18004ABA4
0x18004acf4  mov     edx, 1
0x18004acf9  mov     r9d, 2B7h
0x18004acff  mov     ecx, ebx
0x18004ad01  call    Log_UnistoreHREvent_13
0x18004ad06  lea     rcx, [rbp+var_40]
0x18004ad0a  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x18004ad0f  jmp     loc_18004ABCF
```
