# SampRepairBug19471073ForOneAlias(ulong,ulong,void *,ulong,void *)

- ea: `0x1800985f0`
- end: `0x1800989ca`
- name: `?SampRepairBug19471073ForOneAlias@@YAJKKPEAXK0@Z`
- size: `986`
- prototype: `__int64 __fastcall(unsigned int, unsigned int, void *, unsigned int, PSID SourceSid)`
- caller_count: `1`
- callee_count: `17`
- tags: `reparse_path, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800982a4`

## callees

- `0x180003760`
- `0x180003860`
- `0x1800066f0`
- `0x180011810`
- `0x180011fe0`
- `0x1800213d0`
- `0x180022440`
- `0x180022530`
- `0x1800270e0`
- `0x180027e24`
- `0x18002d720`
- `0x180037284`
- `0x1800372ac`
- `0x180065b60`
- `0x1800985f0`
- `0x1800aeafc`
- `0x1800bb788`

## import_xrefs

- `ntdll!RtlAddActionToRXact` at `0x1800989ac`
- `ntdll!RtlAddActionToRXact` at `0x1800989ac`
- `ntdll!NtClose` at `0x180098770`
- `ntdll!NtClose` at `0x180098770`
- `ntdll!RtlpNtQueryValueKey` at `0x1800988d1`
- `ntdll!RtlpNtQueryValueKey` at `0x18009891f`
- `ntdll!RtlpNtQueryValueKey` at `0x1800988d1`
- `ntdll!RtlpNtQueryValueKey` at `0x18009891f`
- `ntdll!RtlpNtOpenKey` at `0x18009889f`
- `ntdll!RtlpNtOpenKey` at `0x18009889f`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18009872a`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18009872a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800988e5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180098963`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800988e5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180098963`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180098779`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180098782`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009879e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800987a8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180098779`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180098782`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009879e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800987a8`

## pseudocode

```c
__int64 __fastcall SampRepairBug19471073ForOneAlias(__int64 a1, unsigned int a2, void *a3, ULONG a4, PSID SourceSid)
{
  void *v5; // r14
  void *v6; // r15
  int AccountContext; // ebx
  __int64 v10; // r8
  __int64 v11; // r9
  __int64 v12; // rdi
  PUNICODE_STRING v13; // rcx
  NTSTATUS v15; // eax
  HLOCAL v16; // rax
  __int64 v17; // rcx
  ULONG v18; // eax
  ULONG v19; // ebx
  _DWORD *v20; // rax
  __int64 v21; // rcx
  __int64 Unused; // [rsp+28h] [rbp-61h]
  HANDLE Handle; // [rsp+38h] [rbp-51h] BYREF
  PSID pSid1; // [rsp+40h] [rbp-49h] BYREF
  PVOID HandleId; // [rsp+48h] [rbp-41h] BYREF
  HLOCAL hMem[2]; // [rsp+50h] [rbp-39h] BYREF
  struct _UNICODE_STRING KeyName; // [rsp+60h] [rbp-29h] BYREF
  struct _UNICODE_STRING v28; // [rsp+70h] [rbp-19h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp-9h] BYREF
  ULONG DataLength; // [rsp+E8h] [rbp+5Fh] BYREF
  ULONG Type; // [rsp+F8h] [rbp+6Fh] BYREF
  int v32; // [rsp+FCh] [rbp+73h]

  v32 = HIDWORD(a3);
  pSid1 = 0;
  v5 = 0;
  DataLength = 0;
  HandleId = 0;
  v6 = 0;
  Type = 0;
  v28 = 0;
  KeyName = 0;
  Handle = 0;
  *(_OWORD *)hMem = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 1) != 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 4u )
    WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 32, WPP_e294cfc5e5043c283e392179ed50e6b7_Traceguids, a2);
  AccountContext = SampCreateFullSid(SourceSid, a4, &pSid1);
  if ( AccountContext >= 0 )
  {
    SampAcquireReadLock();
    SampSetTransactionDomain(0);
    AccountContext = SampCreateAccountContext(3, a2, v10, v11, Unused, (__int64)&HandleId);
    if ( AccountContext >= 0 )
    {
      AccountContext = SampRetrieveAliasMembers(
                         (struct _SAMP_OBJECT *)HandleId,
                         (unsigned int *)hMem,
                         (void ***)&hMem[1]);
      SampDeleteContext(HandleId);
    }
    SampReleaseReadLock();
    if ( AccountContext < 0 )
    {
      if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 1) != 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
        WPP_SF_d(
          WPP_GLOBAL_Control[3].Buffer,
          33,
          WPP_e294cfc5e5043c283e392179ed50e6b7_Traceguids,
          (unsigned int)AccountContext);
      goto LABEL_17;
    }
    v12 = 0;
    if ( LODWORD(hMem[0]) )
    {
      while ( !EqualSid(pSid1, *((PSID *)hMem[1] + v12)) )
      {
        v12 = (unsigned int)(v12 + 1);
        if ( (unsigned int)v12 >= LODWORD(hMem[0]) )
          goto LABEL_14;
      }
      AccountContext = SampAcquireWriteLock(*((_QWORD *)SampDefinedDomains + 170));
      if ( AccountContext >= 0 )
      {
        SampSetTransactionDomain(0);
        AccountContext = SampBuildAliasMembersKeyName(pSid1, &v28, &KeyName);
        if ( AccountContext < 0 )
          goto LABEL_27;
        ObjectAttributes.RootDirectory = SampKey;
        ObjectAttributes.Length = 48;
        ObjectAttributes.ObjectName = &KeyName;
        ObjectAttributes.Attributes = 64;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        v15 = RtlpNtOpenKey(&Handle, 0x20019u, &ObjectAttributes, 0);
        AccountContext = v15;
        if ( v15 != -1073741766 && v15 != -1073741772 )
        {
          if ( v15 < 0 )
            goto LABEL_27;
          DataLength = 0;
          AccountContext = RtlpNtQueryValueKey(Handle, &Type, 0, &DataLength, 0);
          if ( AccountContext == -2147483643 )
          {
            v16 = LocalAlloc(0x40u, DataLength);
            v5 = v16;
            if ( !v16 )
              goto LABEL_33;
            memset_0(v16, 0, DataLength);
            AccountContext = RtlpNtQueryValueKey(Handle, &Type, v5, &DataLength, 0);
          }
        }
        if ( AccountContext < 0 )
          goto LABEL_27;
        v17 = 0;
        v18 = DataLength >> 2;
        if ( Type == DataLength >> 2 )
        {
          AccountContext = 0;
          goto LABEL_27;
        }
        while ( (unsigned int)v17 < v18 )
        {
          if ( a2 == *((_DWORD *)v5 + v17) )
          {
            AccountContext = 0;
            goto LABEL_27;
          }
          v17 = (unsigned int)(v17 + 1);
        }
        v19 = v18 + 1;
        v20 = LocalAlloc(0x40u, 4LL * (v18 + 1));
        v6 = v20;
        if ( v20 )
        {
          *v20 = a2;
          if ( DataLength )
            memcpy_0(v20 + 1, v5, DataLength);
          AccountContext = RtlAddActionToRXact(SampRXactContext, 2u, &KeyName, v19, v6, 4 * v19);
          if ( AccountContext >= 0 )
          {
            LOBYTE(v21) = 1;
            AccountContext = SampReleaseWriteLock(v21);
            goto LABEL_17;
          }
LABEL_27:
          SampReleaseWriteLock(0);
          goto LABEL_17;
        }
LABEL_33:
        AccountContext = -1073741670;
        goto LABEL_27;
      }
    }
    else
    {
LABEL_14:
      if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 1) != 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 4u )
        WPP_SF_(WPP_GLOBAL_Control[3].Buffer, 34, WPP_e294cfc5e5043c283e392179ed50e6b7_Traceguids);
    }
  }
LABEL_17:
  if ( Handle )
    NtClose(Handle);
  LocalFree(v6);
  LocalFree(v5);
  SampFreeUnicodeString(&KeyName);
  SampFreeUnicodeString(&v28);
  LocalFree(hMem[1]);
  LocalFree(pSid1);
  v13 = WPP_GLOBAL_Control;
  if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 1) != 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 4u )
  {
    WPP_SF_d(
      WPP_GLOBAL_Control[3].Buffer,
      35,
      WPP_e294cfc5e5043c283e392179ed50e6b7_Traceguids,
      (unsigned int)AccountContext);
    v13 = WPP_GLOBAL_Control;
  }
  if ( (*(_DWORD *)(&v13[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(
      v13[3].Buffer,
      36,
      WPP_e294cfc5e5043c283e392179ed50e6b7_Traceguids,
      (unsigned int)AccountContext,
      AccountContext);
  return (unsigned int)AccountContext;
}

```

## disassembly

```asm
0x1800985f0  mov     rax, rsp
0x1800985f3  mov     [rax+10h], rbx
0x1800985f7  mov     [rax+18h], r8
0x1800985fb  mov     [rax+8], ecx
0x1800985fe  push    rbp
0x1800985ff  push    rsi
0x180098600  push    rdi
0x180098601  push    r14
0x180098603  push    r15
0x180098605  lea     rbp, [rax-57h]
0x180098609  sub     rsp, 0B0h
0x180098610  xorps   xmm1, xmm1
0x180098613  mov     [rbp+4Fh+pSid1], 0
0x18009861b  xor     r14d, r14d
0x18009861e  mov     [rbp+4Fh+DataLength], 0
0x180098625  xorps   xmm0, xmm0
0x180098628  mov     [rbp+4Fh+HandleId], r14
0x18009862c  xor     r15d, r15d
0x18009862f  mov     [rbp+4Fh+Type], 0
0x180098636  movups  xmmword ptr [rbp+4Fh+var_68.Length], xmm0
0x18009863a  mov     ebx, r9d
0x18009863d  mov     esi, edx
0x18009863f  movups  xmmword ptr [rbp+4Fh+KeyName.Length], xmm1
0x180098643  mov     [rbp+4Fh+Handle], 0
0x18009864b  movups  xmmword ptr [rbp+4Fh+hMem], xmm0
0x18009864f  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.Length], xmm1
0x180098653  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.ObjectName], xmm1
0x180098657  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm1
0x18009865b  mov     rcx, cs:WPP_GLOBAL_Control
0x180098662  test    byte ptr [rcx+44h], 1
0x180098666  jz      short loc_180098685
0x180098668  cmp     byte ptr [rcx+41h], 4
0x18009866c  jb      short loc_180098685
0x18009866e  mov     rcx, [rcx+38h]
0x180098672  lea     edx, [r14+20h]
0x180098676  mov     r9d, esi
0x180098679  lea     r8, WPP_e294cfc5e5043c283e392179ed50e6b7_Traceguids
0x180098680  call    WPP_SF_d
0x180098685  mov     rcx, [rbp+4Fh+SourceSid]; SourceSid
0x180098689  lea     r8, [rbp+4Fh+pSid1]
0x18009868d  mov     edx, ebx
0x18009868f  call    SampCreateFullSid
0x180098694  mov     ebx, eax
0x180098696  test    eax, eax
0x180098698  js      loc_180098767
0x18009869e  call    SampAcquireReadLock
0x1800986a3  xor     ecx, ecx
0x1800986a5  call    SampSetTransactionDomain
0x1800986aa  lea     rax, [rbp+4Fh+HandleId]
0x1800986ae  mov     edx, esi
0x1800986b0  mov     ecx, 3
0x1800986b5  mov     [rsp+28h], rax
0x1800986ba  call    ?SampCreateAccountContext@@YAJW4_SAMP_OBJECT_TYPE@@KEEEPEAPEAU_SAMP_OBJECT@@@Z; SampCreateAccountContext(_SAMP_OBJECT_TYPE,ulong,uchar,uchar,uchar,_SAMP_OBJECT * *)
0x1800986bf  mov     ebx, eax
0x1800986c1  test    eax, eax
0x1800986c3  js      short loc_1800986E1
0x1800986c5  mov     rcx, [rbp+4Fh+HandleId]; struct _SAMP_OBJECT *
0x1800986c9  lea     r8, [rbp+4Fh+hMem+8]; void ***
0x1800986cd  lea     rdx, [rbp+4Fh+hMem]; unsigned int *
0x1800986d1  call    ?SampRetrieveAliasMembers@@YAJPEAU_SAMP_OBJECT@@PEAKPEAPEAPEAX@Z; SampRetrieveAliasMembers(_SAMP_OBJECT *,ulong *,void * * *)
0x1800986d6  mov     rcx, [rbp+4Fh+HandleId]; HandleId
0x1800986da  mov     ebx, eax
0x1800986dc  call    SampDeleteContext
0x1800986e1  call    SampReleaseReadLock
0x1800986e6  test    ebx, ebx
0x1800986e8  jns     short loc_180098717
0x1800986ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800986f1  test    byte ptr [rcx+44h], 1
0x1800986f5  jz      short loc_180098767
0x1800986f7  cmp     byte ptr [rcx+41h], 2
0x1800986fb  jb      short loc_180098767
0x1800986fd  mov     rcx, [rcx+38h]
0x180098701  lea     r8, WPP_e294cfc5e5043c283e392179ed50e6b7_Traceguids
0x180098708  mov     edx, 21h ; '!'
0x18009870d  mov     r9d, ebx
0x180098710  call    WPP_SF_d
0x180098715  jmp     short loc_180098767
0x180098717  xor     edi, edi
0x180098719  cmp     dword ptr [rbp+4Fh+hMem], edi
0x18009871c  jbe     short loc_18009873F
0x18009871e  mov     rdx, [rbp+4Fh+hMem+8]
0x180098722  mov     rcx, [rbp+4Fh+pSid1]; pSid1
0x180098726  mov     rdx, [rdx+rdi*8]; pSid2
0x18009872a  call    cs:__imp_EqualSid
0x180098730  test    eax, eax
0x180098732  jnz     loc_18009881E
0x180098738  inc     edi
0x18009873a  cmp     edi, dword ptr [rbp+4Fh+hMem]
0x18009873d  jb      short loc_18009871E
0x18009873f  mov     rcx, cs:WPP_GLOBAL_Control
0x180098746  test    byte ptr [rcx+44h], 1
0x18009874a  jz      short loc_180098767
0x18009874c  cmp     byte ptr [rcx+41h], 4
0x180098750  jb      short loc_180098767
0x180098752  mov     rcx, [rcx+38h]
0x180098756  lea     r8, WPP_e294cfc5e5043c283e392179ed50e6b7_Traceguids
0x18009875d  mov     edx, 22h ; '"'
0x180098762  call    WPP_SF_
0x180098767  mov     rcx, [rbp+4Fh+Handle]; Handle
0x18009876b  test    rcx, rcx
0x18009876e  jz      short loc_180098776
0x180098770  call    cs:__imp_NtClose
0x180098776  mov     rcx, r15; hMem
0x180098779  call    cs:__imp_LocalFree
0x18009877f  mov     rcx, r14; hMem
0x180098782  call    cs:__imp_LocalFree
0x180098788  lea     rcx, [rbp+4Fh+KeyName]
0x18009878c  call    SampFreeUnicodeString
0x180098791  lea     rcx, [rbp+4Fh+var_68]
0x180098795  call    SampFreeUnicodeString
0x18009879a  mov     rcx, [rbp+4Fh+hMem+8]; hMem
0x18009879e  call    cs:__imp_LocalFree
0x1800987a4  mov     rcx, [rbp+4Fh+pSid1]; hMem
0x1800987a8  call    cs:__imp_LocalFree
0x1800987ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800987b5  test    byte ptr [rcx+44h], 1
0x1800987b9  jz      short loc_1800987E0
0x1800987bb  cmp     byte ptr [rcx+41h], 4
0x1800987bf  jb      short loc_1800987E0
0x1800987c1  mov     rcx, [rcx+38h]
0x1800987c5  lea     r8, WPP_e294cfc5e5043c283e392179ed50e6b7_Traceguids
0x1800987cc  mov     edx, 23h ; '#'
0x1800987d1  mov     r9d, ebx
0x1800987d4  call    WPP_SF_d
0x1800987d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800987e0  test    dword ptr [rcx+44h], 20000h
0x1800987e7  jz      short loc_180098805
0x1800987e9  mov     rcx, [rcx+38h]
0x1800987ed  lea     r8, WPP_e294cfc5e5043c283e392179ed50e6b7_Traceguids
0x1800987f4  mov     edx, 24h ; '$'
0x1800987f9  mov     [rsp+0D0h+Unused], ebx
0x1800987fd  mov     r9d, ebx
0x180098800  call    WPP_SF_Dd
0x180098805  mov     eax, ebx
0x180098807  mov     rbx, [rsp+0D0h+arg_8]
0x18009880f  add     rsp, 0B0h
0x180098816  pop     r15
0x180098818  pop     r14
0x18009881a  pop     rdi
0x18009881b  pop     rsi
0x18009881c  pop     rbp
0x18009881d  retn
0x18009881e  mov     rcx, cs:?SampDefinedDomains@@3PEAU_PSAMP_DEFINED_DOMAINS@@EA; _PSAMP_DEFINED_DOMAINS * SampDefinedDomains
0x180098825  mov     rcx, [rcx+550h]
0x18009882c  call    SampAcquireWriteLock
0x180098831  mov     ebx, eax
0x180098833  test    eax, eax
0x180098835  js      loc_180098767
0x18009883b  xor     ecx, ecx
0x18009883d  call    SampSetTransactionDomain
0x180098842  mov     rcx, [rbp+4Fh+pSid1]; Sid
0x180098846  lea     r8, [rbp+4Fh+KeyName]; struct _UNICODE_STRING *
0x18009884a  lea     rdx, [rbp+4Fh+var_68]; struct _UNICODE_STRING *
0x18009884e  call    SampBuildAliasMembersKeyName
0x180098853  mov     ebx, eax
0x180098855  test    eax, eax
0x180098857  jns     short loc_180098865
0x180098859  xor     ecx, ecx
0x18009885b  call    SampReleaseWriteLock
0x180098860  jmp     loc_180098767
0x180098865  mov     rax, cs:SampKey
0x18009886c  lea     r8, [rbp+4Fh+ObjectAttributes]; ObjectAttributes
0x180098870  mov     [rbp+4Fh+ObjectAttributes.RootDirectory], rax
0x180098874  lea     rcx, [rbp+4Fh+Handle]; KeyHandle
0x180098878  lea     rax, [rbp+4Fh+KeyName]
0x18009887c  mov     [rbp+4Fh+ObjectAttributes.Length], 30h ; '0'
0x180098883  xorps   xmm0, xmm0
0x180098886  mov     [rbp+4Fh+ObjectAttributes.ObjectName], rax
0x18009888a  mov     edi, 40h ; '@'
0x18009888f  xor     r9d, r9d; Unused
0x180098892  mov     edx, 20019h; DesiredAccess
0x180098897  mov     [rbp+4Fh+ObjectAttributes.Attributes], edi
0x18009889a  movdqu  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x18009889f  call    cs:__imp_RtlpNtOpenKey
0x1800988a5  mov     ebx, eax
0x1800988a7  cmp     eax, 0C000003Ah
0x1800988ac  jz      short loc_180098927
0x1800988ae  cmp     eax, 0C0000034h
0x1800988b3  jz      short loc_180098927
0x1800988b5  test    eax, eax
0x1800988b7  js      short loc_180098859
0x1800988b9  mov     rcx, [rbp+4Fh+Handle]; KeyHandle
0x1800988bd  lea     r9, [rbp+4Fh+DataLength]; DataLength
0x1800988c1  xor     r8d, r8d; Data
0x1800988c4  mov     [rbp+4Fh+DataLength], r14d
0x1800988c8  lea     rdx, [rbp+4Fh+Type]; Type
0x1800988cc  mov     qword ptr [rsp+0D0h+Unused], r14; Unused
0x1800988d1  call    cs:__imp_RtlpNtQueryValueKey
0x1800988d7  mov     ebx, eax
0x1800988d9  cmp     eax, 80000005h
0x1800988de  jnz     short loc_180098927
0x1800988e0  mov     edx, [rbp+4Fh+DataLength]; uBytes
0x1800988e3  mov     ecx, edi; uFlags
0x1800988e5  call    cs:__imp_LocalAlloc
0x1800988eb  mov     r14, rax
0x1800988ee  test    rax, rax
0x1800988f1  jnz     short loc_1800988FD
0x1800988f3  mov     ebx, 0C000009Ah
0x1800988f8  jmp     loc_180098859
0x1800988fd  mov     r8d, [rbp+4Fh+DataLength]; Size
0x180098901  xor     edx, edx; Val
0x180098903  mov     rcx, r14; void *
0x180098906  call    memset_0
0x18009890b  mov     rcx, [rbp+4Fh+Handle]; KeyHandle
0x18009890f  lea     r9, [rbp+4Fh+DataLength]; DataLength
0x180098913  mov     r8, r14; Data
0x180098916  mov     qword ptr [rsp+0D0h+Unused], r15; Unused
0x18009891b  lea     rdx, [rbp+4Fh+Type]; Type
0x18009891f  call    cs:__imp_RtlpNtQueryValueKey
0x180098925  mov     ebx, eax
0x180098927  test    ebx, ebx
0x180098929  js      loc_180098859
0x18009892f  mov     eax, [rbp+4Fh+DataLength]
0x180098932  xor     ecx, ecx
0x180098934  shr     eax, 2
0x180098937  cmp     [rbp+4Fh+Type], eax
0x18009893a  jnz     short loc_180098943
0x18009893c  xor     ebx, ebx
0x18009893e  jmp     loc_18009885B
0x180098943  cmp     ecx, eax
0x180098945  jnb     short loc_180098958
0x180098947  cmp     esi, [r14+rcx*4]
0x18009894b  jz      short loc_180098951
0x18009894d  inc     ecx
0x18009894f  jmp     short loc_180098943
0x180098951  xor     ebx, ebx
0x180098953  jmp     loc_180098859
0x180098958  lea     ebx, [rax+1]
0x18009895b  mov     ecx, edi; uFlags
0x18009895d  mov     edx, ebx
0x18009895f  shl     rdx, 2; uBytes
0x180098963  call    cs:__imp_LocalAlloc
0x180098969  mov     r15, rax
0x18009896c  test    rax, rax
0x18009896f  jz      short loc_1800988F3
0x180098971  mov     [rax], esi
0x180098973  mov     eax, [rbp+4Fh+DataLength]
0x180098976  test    eax, eax
0x180098978  jz      short loc_180098989
0x18009897a  mov     r8d, eax; Size
0x18009897d  lea     rcx, [r15+4]; void *
0x180098981  mov     rdx, r14; Src
0x180098984  call    memcpy_0
0x180098989  mov     rcx, cs:?SampRXactContext@@3PEAU_RTL_RXACT_CONTEXT@@EA; Context
0x180098990  lea     eax, ds:0[rbx*4]
0x180098997  mov     [rsp+28h], eax; ValueDataSize
0x18009899b  lea     r8, [rbp+4Fh+KeyName]; KeyName
0x18009899f  mov     r9d, ebx; ValueType
0x1800989a2  mov     qword ptr [rsp+0D0h+Unused], r15; ValueData
0x1800989a7  mov     edx, 2; ActionType
0x1800989ac  call    cs:__imp_RtlAddActionToRXact
0x1800989b2  mov     ebx, eax
0x1800989b4  test    eax, eax
0x1800989b6  js      loc_180098859
0x1800989bc  mov     cl, 1
0x1800989be  call    SampReleaseWriteLock
0x1800989c3  mov     ebx, eax
0x1800989c5  jmp     loc_180098767
```
