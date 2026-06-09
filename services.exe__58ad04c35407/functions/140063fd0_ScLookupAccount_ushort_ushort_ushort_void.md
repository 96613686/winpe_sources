# ScLookupAccount(ushort *,ushort * *,ushort * *,void * *)

- ea: `0x140063fd0`
- end: `0x1400644ba`
- name: `?ScLookupAccount@@YAKPEAGPEAPEAG1PEAPEAX@Z`
- size: `1258`
- prototype: `unsigned int __fastcall(unsigned __int16 *, unsigned __int16 **, unsigned __int16 **, void **)`
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1400644c0`
- `0x1400647d8`

## callees

- `0x140004c58`
- `0x14000cee0`
- `0x140013b0c`
- `0x1400188fc`
- `0x14001a230`
- `0x14001f99c`
- `0x140036f34`
- `0x14004af50`
- `0x1400575b0`
- `0x140057fb0`
- `0x1400623cc`
- `0x140063fd0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x140064304`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x140064370`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x140064304`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x140064370`
- `ntdll!RtlNtStatusToDosError` at `0x1400643a5`
- `ntdll!RtlNtStatusToDosError` at `0x1400643cc`
- `ntdll!RtlNtStatusToDosError` at `0x1400643a5`
- `ntdll!RtlNtStatusToDosError` at `0x1400643cc`
- `ntdll!RtlCopySid` at `0x14006437e`
- `ntdll!RtlCopySid` at `0x14006437e`
- `ntdll!RtlInitUnicodeString` at `0x1400641fe`
- `ntdll!RtlInitUnicodeString` at `0x1400641fe`
- `ntdll!RtlFreeHeap` at `0x140064447`
- `ntdll!RtlFreeHeap` at `0x140064469`
- `ntdll!RtlFreeHeap` at `0x14006448f`
- `ntdll!RtlFreeHeap` at `0x140064447`
- `ntdll!RtlFreeHeap` at `0x140064469`
- `ntdll!RtlFreeHeap` at `0x14006448f`
- `ntdll!RtlAllocateHeap` at `0x140064045`
- `ntdll!RtlAllocateHeap` at `0x14006418f`
- `ntdll!RtlAllocateHeap` at `0x14006431c`
- `ntdll!RtlAllocateHeap` at `0x140064045`
- `ntdll!RtlAllocateHeap` at `0x14006418f`
- `ntdll!RtlAllocateHeap` at `0x14006431c`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupTranslateNames` at `0x14006426e`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupTranslateNames` at `0x14006426e`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupFreeMemory` at `0x1400642bc`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupFreeMemory` at `0x1400642cb`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupFreeMemory` at `0x1400643dc`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupFreeMemory` at `0x14006442a`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupFreeMemory` at `0x1400642bc`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupFreeMemory` at `0x1400642cb`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupFreeMemory` at `0x1400643dc`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupFreeMemory` at `0x14006442a`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupClose` at `0x1400642d5`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupClose` at `0x1400642e4`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupClose` at `0x1400642d5`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupClose` at `0x1400642e4`

## pseudocode

```c
__int64 __fastcall ScLookupAccount(unsigned __int16 *a1, const wchar_t **a2, unsigned __int16 **a3, void **a4)
{
  unsigned __int16 *v4; // r13
  __int64 v5; // rbx
  __int64 v6; // rax
  SIZE_T v11; // rsi
  unsigned __int16 *Heap; // rax
  wchar_t *v14; // rax
  const unsigned __int16 *v15; // rsi
  ULONG v16; // ebx
  __int64 v17; // rax
  SIZE_T v18; // rbx
  unsigned __int16 *v19; // rax
  const WCHAR *v20; // rdx
  NTSTATUS v21; // ebx
  PLSA_TRANSLATED_SID2 v22; // rcx
  DWORD LengthSid; // eax
  PVOID v24; // rax
  void *v25; // rdi
  PSID Sid; // rbx
  DWORD v27; // eax
  int v28; // edi
  ULONG v29; // eax
  PLSA_TRANSLATED_SID2 Sids; // [rsp+30h] [rbp-39h] BYREF
  LSA_LOOKUP_HANDLE PolicyHandle; // [rsp+38h] [rbp-31h] BYREF
  PLSA_REFERENCED_DOMAIN_LIST ReferencedDomains; // [rsp+40h] [rbp-29h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-21h] BYREF
  unsigned __int16 v34[16]; // [rsp+58h] [rbp-11h] BYREF

  v4 = 0;
  v5 = -1;
  PolicyHandle = 0;
  v6 = -1;
  ReferencedDomains = 0;
  Sids = 0;
  DestinationString = 0;
  do
    ++v6;
  while ( a1[v6] );
  v11 = (unsigned int)(2 * v6 + 2);
  Heap = (unsigned __int16 *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v11);
  *a2 = Heap;
  if ( !Heap )
  {
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->StubInfo, 24, WPP_a9b8e10de094345130a6b8d864a6a1a6_Traceguids);
    return 8;
  }
  StringCbCopyW(Heap, v11, a1);
  v14 = wcschr(*a2, 0x5Cu);
  v15 = v14;
  if ( !v14 )
  {
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->StubInfo, 25, WPP_a9b8e10de094345130a6b8d864a6a1a6_Traceguids);
    ScLogEvent(8u);
LABEL_13:
    v16 = 31;
    goto LABEL_63;
  }
  *a3 = v14 + 1;
  if ( wcsnicmp(*a2, L".", 1u) )
  {
    v20 = *a2;
  }
  else
  {
    if ( !(unsigned int)GetDefaultDomainName(v34) )
    {
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->StubInfo, 26, WPP_a9b8e10de094345130a6b8d864a6a1a6_Traceguids);
      goto LABEL_13;
    }
    v17 = -1;
    do
      ++v17;
    while ( v34[v17] );
    do
      ++v5;
    while ( (*a3)[v5] );
    v18 = (unsigned int)(2 * (v5 + v17) + 4);
    v19 = (unsigned __int16 *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v18);
    v4 = v19;
    if ( !v19 )
    {
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->StubInfo, 27, WPP_a9b8e10de094345130a6b8d864a6a1a6_Traceguids);
      v16 = 8;
      goto LABEL_63;
    }
    StringCbCopyW(v19, v18, v34);
    StringCbCatW(v4, v18, v15);
    v20 = v4;
  }
  RtlInitUnicodeString(&DestinationString, v20);
  if ( ScOpenPolicy(0x801u, &PolicyHandle) )
  {
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->StubInfo, 28, WPP_a9b8e10de094345130a6b8d864a6a1a6_Traceguids);
  }
  else
  {
    v21 = LsaLookupTranslateNames(
            PolicyHandle,
            0,
            1u,
            (PLSA_UNICODE_STRING)&DestinationString,
            &ReferencedDomains,
            &Sids);
    if ( v21 >= 0 )
    {
      LsaLookupClose(PolicyHandle);
      v22 = Sids;
      if ( Sids )
      {
        if ( a4 )
        {
          LengthSid = GetLengthSid(Sids->Sid);
          v24 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, LengthSid);
          *a4 = v24;
          v25 = v24;
          if ( !v24 )
          {
            if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
              && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
            {
              WPP_SF_(WPP_GLOBAL_Control->StubInfo, 30, WPP_a9b8e10de094345130a6b8d864a6a1a6_Traceguids);
            }
            v16 = 8;
            goto LABEL_63;
          }
          Sid = Sids->Sid;
          v27 = GetLengthSid(Sid);
          v28 = RtlCopySid(v27, v25, Sid);
          if ( v28 < 0 )
          {
            if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
              && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
            {
              v29 = RtlNtStatusToDosError(v28);
              WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 31, WPP_a9b8e10de094345130a6b8d864a6a1a6_Traceguids, v29);
            }
            v16 = RtlNtStatusToDosError(v28);
            goto LABEL_63;
          }
          v22 = Sids;
        }
        LsaLookupFreeMemory(v22);
      }
      if ( ReferencedDomains )
      {
        LsaLookupFreeMemory(ReferencedDomains);
        v16 = 0;
        *v15 = 0;
        goto LABEL_63;
      }
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        WPP_SF_S(
          WPP_GLOBAL_Control->StubInfo,
          32,
          WPP_a9b8e10de094345130a6b8d864a6a1a6_Traceguids,
          DestinationString.Buffer);
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 29, WPP_a9b8e10de094345130a6b8d864a6a1a6_Traceguids, (unsigned int)v21);
      if ( v21 == -1073741709 )
      {
        if ( Sids )
          LsaLookupFreeMemory(Sids);
        if ( ReferencedDomains )
          LsaLookupFreeMemory(ReferencedDomains);
      }
      LsaLookupClose(PolicyHandle);
    }
  }
  v16 = 1057;
LABEL_63:
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v4);
  if ( v16 )
  {
    if ( *a2 )
    {
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, (PVOID)*a2);
      *a2 = 0;
    }
    if ( a4 && *a4 )
    {
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, *a4);
      *a4 = 0;
    }
  }
  return v16;
}

```

## disassembly

```asm
0x140063fd0  push    rbp
0x140063fd2  push    rbx
0x140063fd3  push    rsi
0x140063fd4  push    rdi
0x140063fd5  push    r12
0x140063fd7  push    r13
0x140063fd9  push    r14
0x140063fdb  push    r15
0x140063fdd  lea     rbp, [rsp-1Fh]
0x140063fe2  sub     rsp, 88h
0x140063fe9  mov     rax, cs:__security_cookie
0x140063ff0  xor     rax, rsp
0x140063ff3  mov     [rbp+57h+var_48], rax
0x140063ff7  xor     r13d, r13d
0x140063ffa  xorps   xmm0, xmm0
0x140063ffd  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140064001  mov     [rbp+57h+PolicyHandle], r13
0x140064005  mov     rax, rbx
0x140064008  mov     [rbp+57h+var_80], r13
0x14006400c  mov     r15, r9
0x14006400f  mov     [rbp+57h+var_90], r13
0x140064013  mov     r14, r8
0x140064016  mov     r12, rdx
0x140064019  mov     rdi, rcx
0x14006401c  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140064020  inc     rax
0x140064023  cmp     [rcx+rax*2], r13w
0x140064028  jnz     short loc_140064020
0x14006402a  mov     rcx, gs:60h
0x140064033  lea     eax, ds:2[rax*2]
0x14006403a  mov     r8d, eax; Size
0x14006403d  xor     edx, edx; Flags
0x14006403f  mov     esi, eax
0x140064041  mov     rcx, [rcx+30h]; HeapHandle
0x140064045  call    cs:__imp_RtlAllocateHeap
0x14006404b  mov     [r12], rax
0x14006404f  test    rax, rax
0x140064052  jnz     short loc_14006408C
0x140064054  mov     rcx, cs:WPP_GLOBAL_Control
0x14006405b  lea     rax, WPP_GLOBAL_Control
0x140064062  cmp     rcx, rax
0x140064065  jz      short loc_140064082
0x140064067  test    byte ptr [rcx+1Ch], 1
0x14006406b  jz      short loc_140064082
0x14006406d  mov     rcx, [rcx+10h]
0x140064071  lea     r8, WPP_a9b8e10de094345130a6b8d864a6a1a6_Traceguids
0x140064078  mov     edx, 18h
0x14006407d  call    WPP_SF_
0x140064082  mov     eax, 8
0x140064087  jmp     loc_14006449A
0x14006408c  mov     r8, rdi; unsigned __int16 *
0x14006408f  mov     rdx, rsi; unsigned __int64
0x140064092  mov     rcx, rax; unsigned __int16 *
0x140064095  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x14006409a  mov     rcx, [r12]; Str
0x14006409e  mov     edx, 5Ch ; '\'; Ch
0x1400640a3  call    wcschr
0x1400640a8  xor     edi, edi
0x1400640aa  mov     rsi, rax
0x1400640ad  test    rax, rax
0x1400640b0  jnz     short loc_1400640F2
0x1400640b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400640b9  lea     rax, WPP_GLOBAL_Control
0x1400640c0  cmp     rcx, rax
0x1400640c3  jz      short loc_1400640DE
0x1400640c5  test    byte ptr [rcx+1Ch], 1
0x1400640c9  jz      short loc_1400640DE
0x1400640cb  mov     rcx, [rcx+10h]
0x1400640cf  lea     edx, [rsi+19h]
0x1400640d2  lea     r8, WPP_a9b8e10de094345130a6b8d864a6a1a6_Traceguids
0x1400640d9  call    WPP_SF_
0x1400640de  mov     ecx, 8; unsigned int
0x1400640e3  call    ?ScLogEvent@@YAXKZZ; ScLogEvent(ulong,...)
0x1400640e8  mov     ebx, 1Fh
0x1400640ed  jmp     loc_140064435
0x1400640f2  add     rax, 2
0x1400640f6  lea     rdx, asc_1400A65F4; "."
0x1400640fd  mov     [r14], rax
0x140064100  mov     r8d, 1; MaxCount
0x140064106  mov     rcx, [r12]; String1
0x14006410a  call    _wcsnicmp
0x14006410f  test    eax, eax
0x140064111  jnz     loc_1400641F6
0x140064117  lea     rcx, [rbp+57h+var_68]; unsigned __int16 *
0x14006411b  call    ?GetDefaultDomainName@@YAHPEAGK@Z; GetDefaultDomainName(ushort *,ulong)
0x140064120  test    eax, eax
0x140064122  jnz     short loc_140064154
0x140064124  mov     rcx, cs:WPP_GLOBAL_Control
0x14006412b  lea     rax, WPP_GLOBAL_Control
0x140064132  cmp     rcx, rax
0x140064135  jz      short loc_1400640E8
0x140064137  test    byte ptr [rcx+1Ch], 1
0x14006413b  jz      short loc_1400640E8
0x14006413d  mov     rcx, [rcx+10h]
0x140064141  lea     r8, WPP_a9b8e10de094345130a6b8d864a6a1a6_Traceguids
0x140064148  mov     edx, 1Ah
0x14006414d  call    WPP_SF_
0x140064152  jmp     short loc_1400640E8
0x140064154  lea     rcx, [rbp+57h+var_68]
0x140064158  mov     rax, rbx
0x14006415b  inc     rax
0x14006415e  cmp     [rcx+rax*2], di
0x140064162  jnz     short loc_14006415B
0x140064164  mov     rcx, [r14]
0x140064167  inc     rbx
0x14006416a  cmp     [rcx+rbx*2], di
0x14006416e  jnz     short loc_140064167
0x140064170  mov     rcx, gs:60h
0x140064179  add     rax, rbx
0x14006417c  xor     edx, edx; Flags
0x14006417e  mov     rcx, [rcx+30h]; HeapHandle
0x140064182  lea     rax, ds:4[rax*2]
0x14006418a  mov     r8d, eax; Size
0x14006418d  mov     ebx, eax
0x14006418f  call    cs:__imp_RtlAllocateHeap
0x140064195  mov     r13, rax
0x140064198  test    rax, rax
0x14006419b  jnz     short loc_1400641D4
0x14006419d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400641a4  lea     rax, WPP_GLOBAL_Control
0x1400641ab  cmp     rcx, rax
0x1400641ae  jz      short loc_1400641CA
0x1400641b0  test    byte ptr [rcx+1Ch], 1
0x1400641b4  jz      short loc_1400641CA
0x1400641b6  mov     rcx, [rcx+10h]
0x1400641ba  lea     edx, [r13+1Bh]
0x1400641be  lea     r8, WPP_a9b8e10de094345130a6b8d864a6a1a6_Traceguids
0x1400641c5  call    WPP_SF_
0x1400641ca  mov     ebx, 8
0x1400641cf  jmp     loc_140064435
0x1400641d4  lea     r8, [rbp+57h+var_68]; unsigned __int16 *
0x1400641d8  mov     rdx, rbx; unsigned __int64
0x1400641db  mov     rcx, r13; unsigned __int16 *
0x1400641de  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x1400641e3  mov     r8, rsi; unsigned __int16 *
0x1400641e6  mov     rdx, rbx; unsigned __int64
0x1400641e9  mov     rcx, r13; unsigned __int16 *
0x1400641ec  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x1400641f1  mov     rdx, r13
0x1400641f4  jmp     short loc_1400641FA
0x1400641f6  mov     rdx, [r12]; SourceString
0x1400641fa  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1400641fe  call    cs:__imp_RtlInitUnicodeString
0x140064204  lea     rdx, [rbp+57h+PolicyHandle]; PolicyHandle
0x140064208  mov     ecx, 801h; AccessMask
0x14006420d  call    ?ScOpenPolicy@@YAKKPEAPEAX@Z; ScOpenPolicy(ulong,void * *)
0x140064212  test    eax, eax
0x140064214  jz      short loc_14006424E
0x140064216  mov     rcx, cs:WPP_GLOBAL_Control
0x14006421d  lea     rax, WPP_GLOBAL_Control
0x140064224  cmp     rcx, rax
0x140064227  jz      short loc_140064244
0x140064229  test    byte ptr [rcx+1Ch], 1
0x14006422d  jz      short loc_140064244
0x14006422f  mov     rcx, [rcx+10h]
0x140064233  lea     r8, WPP_a9b8e10de094345130a6b8d864a6a1a6_Traceguids
0x14006423a  mov     edx, 1Ch
0x14006423f  call    WPP_SF_
0x140064244  mov     ebx, 421h
0x140064249  jmp     loc_140064435
0x14006424e  mov     rcx, [rbp+57h+PolicyHandle]; PolicyHandle
0x140064252  lea     rax, [rbp+57h+var_90]
0x140064256  mov     [rsp+0C0h+Sids], rax; Sids
0x14006425b  lea     r9, [rbp+57h+DestinationString]; Names
0x14006425f  xor     edx, edx; Flags
0x140064261  lea     rax, [rbp+57h+var_80]
0x140064265  mov     [rsp+0C0h+ReferencedDomains], rax; ReferencedDomains
0x14006426a  lea     r8d, [rdx+1]; Count
0x14006426e  call    cs:__imp_LsaLookupTranslateNames
0x140064274  mov     ebx, eax
0x140064276  test    eax, eax
0x140064278  jns     short loc_1400642E0
0x14006427a  mov     rcx, cs:WPP_GLOBAL_Control
0x140064281  lea     rax, WPP_GLOBAL_Control
0x140064288  cmp     rcx, rax
0x14006428b  jz      short loc_1400642AB
0x14006428d  test    byte ptr [rcx+1Ch], 1
0x140064291  jz      short loc_1400642AB
0x140064293  mov     rcx, [rcx+10h]
0x140064297  lea     r8, WPP_a9b8e10de094345130a6b8d864a6a1a6_Traceguids
0x14006429e  mov     edx, 1Dh
0x1400642a3  mov     r9d, ebx
0x1400642a6  call    WPP_SF_d
0x1400642ab  cmp     ebx, 0C0000073h
0x1400642b1  jnz     short loc_1400642D1
0x1400642b3  mov     rcx, [rbp+57h+var_90]; Buffer
0x1400642b7  test    rcx, rcx
0x1400642ba  jz      short loc_1400642C2
0x1400642bc  call    cs:__imp_LsaLookupFreeMemory
0x1400642c2  mov     rcx, [rbp+57h+var_80]; Buffer
0x1400642c6  test    rcx, rcx
0x1400642c9  jz      short loc_1400642D1
0x1400642cb  call    cs:__imp_LsaLookupFreeMemory
0x1400642d1  mov     rcx, [rbp+57h+PolicyHandle]; ObjectHandle
0x1400642d5  call    cs:__imp_LsaLookupClose
0x1400642db  jmp     loc_140064244
0x1400642e0  mov     rcx, [rbp+57h+PolicyHandle]; ObjectHandle
0x1400642e4  call    cs:__imp_LsaLookupClose
0x1400642ea  mov     rcx, [rbp+57h+var_90]
0x1400642ee  test    rcx, rcx
0x1400642f1  jz      loc_1400643E2
0x1400642f7  test    r15, r15
0x1400642fa  jz      loc_1400643DC
0x140064300  mov     rcx, [rcx+8]; pSid
0x140064304  call    cs:__imp_GetLengthSid
0x14006430a  mov     rcx, gs:60h
0x140064313  xor     edx, edx; Flags
0x140064315  mov     r8d, eax; Size
0x140064318  mov     rcx, [rcx+30h]; HeapHandle
0x14006431c  call    cs:__imp_RtlAllocateHeap
0x140064322  mov     [r15], rax
0x140064325  mov     rdi, rax
0x140064328  test    rax, rax
0x14006432b  jnz     short loc_140064365
0x14006432d  mov     rcx, cs:WPP_GLOBAL_Control
0x140064334  lea     rax, WPP_GLOBAL_Control
0x14006433b  cmp     rcx, rax
0x14006433e  jz      short loc_140064359
0x140064340  test    byte ptr [rcx+1Ch], 1
0x140064344  jz      short loc_140064359
0x140064346  mov     rcx, [rcx+10h]
0x14006434a  lea     edx, [rdi+1Eh]
0x14006434d  lea     r8, WPP_a9b8e10de094345130a6b8d864a6a1a6_Traceguids
0x140064354  call    WPP_SF_
0x140064359  mov     ebx, 8
0x14006435e  xor     edi, edi
0x140064360  jmp     loc_140064435
0x140064365  mov     rax, [rbp+57h+var_90]
0x140064369  mov     rbx, [rax+8]
0x14006436d  mov     rcx, rbx; pSid
0x140064370  call    cs:__imp_GetLengthSid
0x140064376  mov     r8, rbx; SourceSid
0x140064379  mov     rdx, rdi; DestinationSid
0x14006437c  mov     ecx, eax; DestinationSidLength
0x14006437e  call    cs:__imp_RtlCopySid
0x140064384  mov     edi, eax
0x140064386  test    eax, eax
0x140064388  jns     short loc_1400643D6
0x14006438a  mov     rcx, cs:WPP_GLOBAL_Control
0x140064391  lea     rax, WPP_GLOBAL_Control
0x140064398  cmp     rcx, rax
0x14006439b  jz      short loc_1400643CA
0x14006439d  test    byte ptr [rcx+1Ch], 1
0x1400643a1  jz      short loc_1400643CA
0x1400643a3  mov     ecx, edi; Status
0x1400643a5  call    cs:__imp_RtlNtStatusToDosError
0x1400643ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1400643b2  lea     r8, WPP_a9b8e10de094345130a6b8d864a6a1a6_Traceguids
0x1400643b9  mov     edx, 1Fh
0x1400643be  mov     r9d, eax
0x1400643c1  mov     rcx, [rcx+10h]
0x1400643c5  call    WPP_SF_d
0x1400643ca  mov     ecx, edi; Status
0x1400643cc  call    cs:__imp_RtlNtStatusToDosError
0x1400643d2  mov     ebx, eax
0x1400643d4  jmp     short loc_14006435E
0x1400643d6  mov     rcx, [rbp+57h+var_90]; Buffer
0x1400643da  xor     edi, edi
0x1400643dc  call    cs:__imp_LsaLookupFreeMemory
0x1400643e2  mov     rcx, [rbp+57h+var_80]; Buffer
0x1400643e6  test    rcx, rcx
0x1400643e9  jnz     short loc_14006442A
0x1400643eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400643f2  lea     rax, WPP_GLOBAL_Control
0x1400643f9  cmp     rcx, rax
0x1400643fc  jz      loc_140064244
0x140064402  test    byte ptr [rcx+1Ch], 1
0x140064406  jz      loc_140064244
0x14006440c  mov     r9, [rbp+57h+DestinationString.Buffer]
0x140064410  lea     r8, WPP_a9b8e10de094345130a6b8d864a6a1a6_Traceguids
0x140064417  mov     rcx, [rcx+10h]
0x14006441b  mov     edx, 20h ; ' '
0x140064420  call    WPP_SF_S
0x140064425  jmp     loc_140064244
0x14006442a  call    cs:__imp_LsaLookupFreeMemory
0x140064430  mov     ebx, edi
0x140064432  mov     [rsi], di
0x140064435  mov     rcx, gs:60h
0x14006443e  mov     r8, r13; P
0x140064441  xor     edx, edx; Flags
0x140064443  mov     rcx, [rcx+30h]; HeapHandle
0x140064447  call    cs:__imp_RtlFreeHeap
0x14006444d  test    ebx, ebx
0x14006444f  jz      short loc_140064498
0x140064451  mov     r8, [r12]; P
0x140064455  test    r8, r8
0x140064458  jz      short loc_140064473
0x14006445a  mov     rcx, gs:60h
0x140064463  xor     edx, edx; Flags
0x140064465  mov     rcx, [rcx+30h]; HeapHandle
0x140064469  call    cs:__imp_RtlFreeHeap
0x14006446f  mov     [r12], rdi
0x140064473  test    r15, r15
0x140064476  jz      short loc_140064498
0x140064478  mov     r8, [r15]; P
0x14006447b  test    r8, r8
0x14006447e  jz      short loc_140064498
0x140064480  mov     rcx, gs:60h
0x140064489  xor     edx, edx; Flags
0x14006448b  mov     rcx, [rcx+30h]; HeapHandle
  ... truncated ...
```
