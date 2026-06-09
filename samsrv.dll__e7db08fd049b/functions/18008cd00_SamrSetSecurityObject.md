# SamrSetSecurityObject

- ea: `0x18008cd00`
- end: `0x18008d248`
- name: `SamrSetSecurityObject`
- size: `1352`
- prototype: `__int64 __fastcall(struct _SAMP_OBJECT *, SECURITY_INFORMATION, __int64)`
- caller_count: `1`
- callee_count: `24`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18006da20`

## callees

- `0x180008590`
- `0x18000ae10`
- `0x180012a28`
- `0x180016a80`
- `0x18001cfa0`
- `0x18001d0d0`
- `0x180022678`
- `0x180022b30`
- `0x1800270e0`
- `0x180027e24`
- `0x180037284`
- `0x1800372ac`
- `0x180037394`
- `0x18003cd20`
- `0x1800655e4`
- `0x180065b60`
- `0x180076bbc`
- `0x180077dc4`
- `0x18008a720`
- `0x18008cd00`
- `0x1800ac198`
- `0x1800acb78`
- `0x1800b14a0`
- `0x1800bb788`

## import_xrefs

- `ntdll!NtOpenProcessToken` at `0x18008d0af`
- `ntdll!NtOpenProcessToken` at `0x18008d0af`
- `ntdll!NtOpenThreadToken` at `0x18008d090`
- `ntdll!NtOpenThreadToken` at `0x18008d090`
- `ntdll!RtlSetSecurityObject` at `0x18008d145`
- `ntdll!RtlSetSecurityObject` at `0x18008d145`
- `ntdll!RtlLengthSecurityDescriptor` at `0x18008d1ac`
- `ntdll!RtlLengthSecurityDescriptor` at `0x18008d1ac`
- `ntdll!RtlFreeHeap` at `0x18008d1ed`
- `ntdll!RtlFreeHeap` at `0x18008d1ed`
- `ntdll!RtlAllocateHeap` at `0x18008d032`
- `ntdll!RtlAllocateHeap` at `0x18008d032`
- `ntdll!NtClose` at `0x18008d156`
- `ntdll!NtClose` at `0x18008d156`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008cf2b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008d165`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008d1ce`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008cf2b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008d165`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008d1ce`
- `ext-ms-win-ntdsaapi-l1-1-0!NtdsaExtPropagateSelectedSdChanges` at `0x18008d10a`
- `ext-ms-win-ntdsaapi-l1-1-0!NtdsaExtPropagateSelectedSdChanges` at `0x18008d10a`

## pseudocode

```c
__int64 __fastcall SamrSetSecurityObject(struct _SAMP_OBJECT *a1, SECURITY_INFORMATION a2, __int64 a3)
{
  char v4; // r13
  NTSTATUS ObjectSD; // ebx
  int v7; // r15d
  int v8; // edx
  unsigned int v9; // esi
  _DWORD *v10; // r14
  int v11; // r12d
  int v12; // eax
  unsigned int v13; // r13d
  int IsLapsAutoManagedAccount; // eax
  NTSTATUS v15; // eax
  PUNICODE_STRING v16; // rcx
  __int64 v18; // rdx
  PVOID Heap; // rax
  bool v20; // zf
  unsigned int v21; // esi
  NTSTATUS v22; // eax
  int v23; // eax
  ULONG v24; // eax
  int v25; // eax
  unsigned int v26; // [rsp+30h] [rbp-40h]
  SIZE_T Size; // [rsp+34h] [rbp-3Ch] BYREF
  PSECURITY_DESCRIPTOR ObjectsSecurityDescriptor; // [rsp+40h] [rbp-30h] BYREF
  HLOCAL v29; // [rsp+48h] [rbp-28h] BYREF
  int v30; // [rsp+50h] [rbp-20h] BYREF
  void *TokenHandle; // [rsp+58h] [rbp-18h] BYREF
  void *Src; // [rsp+60h] [rbp-10h]
  HLOCAL hMem; // [rsp+68h] [rbp-8h] BYREF
  char v35; // [rsp+C8h] [rbp+58h]

  v4 = a2;
  Src = 0;
  ObjectsSecurityDescriptor = 0;
  HIDWORD(Size) = 0;
  TokenHandle = 0;
  LODWORD(v29) = 0;
  v30 = 0;
  hMem = 0;
  if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 8) != 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 4u )
    WPP_SF_qD(WPP_GLOBAL_Control[3].Buffer, 38, WPP_18fb10c206133c98d7a2b000be93359d_Traceguids, a1, a2);
  SampTraceEvent(1);
  if ( !SampValidateSD((struct _SAMPR_SR_SECURITY_DESCRIPTOR *)a3) )
    goto LABEL_5;
  v7 = v4 & 8;
  v8 = (v7 != 0 ? 0x1000000 : 0) | 0x80000;
  if ( (v4 & 3) == 0 )
    v8 = (v4 & 8) != 0 ? 0x1000000 : 0;
  v9 = v8 | 0x40000;
  if ( (v4 & 4) == 0 )
    v9 = v8;
  if ( !v9 )
  {
    ObjectSD = -1073741811;
    goto LABEL_49;
  }
  if ( (v10 = *(_DWORD **)(a3 + 8), v11 = v4 & 1, (v4 & 1) != 0) && !v10[1] || (v4 & 2) != 0 && !v10[2] )
  {
LABEL_5:
    ObjectSD = -1073741593;
    goto LABEL_49;
  }
  ObjectSD = SampAcquireWriteLock(a1);
  if ( ObjectSD < 0 )
    goto LABEL_49;
  v35 = 1;
  v12 = SampLookupContext(a1, v9, 5, (char *)&Size + 4);
  ObjectSD = v12;
  switch ( HIDWORD(Size) )
  {
    case 0:
      v26 = 0;
      v35 = 0;
      goto LABEL_30;
    case 1:
      v26 = 1;
LABEL_30:
      v13 = 0;
      goto LABEL_31;
    case 2:
      v26 = 3;
      break;
    case 3:
      v26 = 4;
      break;
    case 4:
      v26 = 2;
      break;
    default:
      if ( v12 >= 0 )
        ObjectSD = -1073741595;
      goto LABEL_47;
  }
  v13 = *((_DWORD *)a1 + 62);
LABEL_31:
  if ( v12 < 0 )
    goto LABEL_47;
  if ( (*((_BYTE *)a1 + 192) & 2) != 0 )
  {
    if ( (*((_BYTE *)a1 + 20) & 0x20) != 0 )
      goto LABEL_56;
    if ( v7 )
    {
      SampDeReferenceContext(a1, 0);
      ObjectSD = -1073741811;
      goto LABEL_47;
    }
  }
  if ( (*((_BYTE *)a1 + 20) & 0x20) == 0 )
  {
    IsLapsAutoManagedAccount = SampIsLapsAutoManagedAccount(a1, &v30);
    ObjectSD = IsLapsAutoManagedAccount;
    if ( IsLapsAutoManagedAccount < 0 )
    {
      if ( IsLapsAutoManagedAccount != -1073741724 )
        goto LABEL_46;
    }
    else
    {
      if ( v30 )
      {
        if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 1) != 0
          && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
        {
          WPP_SF_(WPP_GLOBAL_Control[3].Buffer, 39, WPP_18fb10c206133c98d7a2b000be93359d_Traceguids);
        }
        if ( (int)SampCreateAccountSid(a1, &hMem) >= 0 )
        {
          SamLAPSNotifyBlockedOperation(hMem, 3u);
          LocalFree(hMem);
        }
        ObjectSD = -1073700725;
      }
      if ( ObjectSD < 0 )
        goto LABEL_46;
    }
  }
LABEL_56:
  Src = 0;
  ObjectsSecurityDescriptor = 0;
  ObjectSD = SampGetObjectSD(a1);
  if ( ObjectSD >= 0 )
  {
    ObjectSD = SampCheckForDescriptorRestrictions(a1, HIDWORD(Size), v13, v10);
    if ( ObjectSD < 0 )
      goto LABEL_87;
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0);
    ObjectsSecurityDescriptor = Heap;
    if ( !Heap )
    {
      ObjectSD = -1073741670;
      goto LABEL_87;
    }
    memcpy_0(Heap, Src, 0);
    TokenHandle = 0;
    if ( v11 )
    {
      if ( (*((_BYTE *)a1 + 20) & 0x20) != 0 )
      {
        ObjectSD = NtOpenProcessToken((HANDLE)0xFFFFFFFFFFFFFFFFLL, 8u, &TokenHandle);
      }
      else
      {
        ObjectSD = SampImpersonateClient(&v29);
        if ( ObjectSD < 0 )
          goto LABEL_87;
        ObjectSD = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 8u, 1u, &TokenHandle);
        SampRevertToSelf((unsigned int)v29);
      }
      if ( ObjectSD < 0 )
      {
LABEL_87:
        if ( Src )
          LocalFree(Src);
        if ( ObjectsSecurityDescriptor )
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, ObjectsSecurityDescriptor);
        if ( ObjectSD >= 0 )
        {
          LOBYTE(v18) = 1;
          ObjectSD = SampDeReferenceContext(a1, v18);
          if ( ObjectSD >= 0 )
          {
            v25 = SampCommitAndRetainWriteLock();
            ObjectSD = v25;
            if ( v35 )
            {
              if ( v25 >= 0 )
                SampNotifyNetlogonOfDelta(7, v26, v13, 0, 0, 0);
            }
          }
          goto LABEL_47;
        }
        goto LABEL_46;
      }
    }
    v20 = (*((_BYTE *)a1 + 192) & 2) == 0;
    v29 = 0;
    if ( v20 )
    {
LABEL_76:
      ObjectSD = RtlSetSecurityObject(
                   a2,
                   v10,
                   &ObjectsSecurityDescriptor,
                   (PGENERIC_MAPPING)(&SampObjectInformation + 11 * SHIDWORD(Size)),
                   TokenHandle);
      if ( TokenHandle )
        NtClose(TokenHandle);
      if ( v29 )
        LocalFree(v29);
      if ( ObjectSD >= 0 )
      {
        if ( *((__int16 *)ObjectsSecurityDescriptor + 1) < 0 )
        {
          v24 = RtlLengthSecurityDescriptor(ObjectsSecurityDescriptor);
          ObjectSD = SampSetAccessAttribute(a1, 0, (unsigned __int8 *)ObjectsSecurityDescriptor, v24);
        }
        else
        {
          if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20) != 0
            && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
          {
            WPP_SF_(WPP_GLOBAL_Control[3].Buffer, 40, WPP_18fb10c206133c98d7a2b000be93359d_Traceguids);
          }
          ObjectSD = -1073741811;
        }
      }
      goto LABEL_87;
    }
    v21 = *((_DWORD *)a1 + 4);
    if ( (*((_BYTE *)a1 + 20) & 0x20) != 0 )
    {
      v22 = SampExtConvertNt4SdToNt5SdDs(v10, v21, a1, &v29);
LABEL_73:
      ObjectSD = v22;
      goto LABEL_74;
    }
    v23 = SampShouldCallNtdsaApiSet();
    ObjectSD = v23;
    if ( v23 == -1073741637 )
    {
      ObjectSD = 0;
    }
    else if ( v23 >= 0 )
    {
      v22 = NtdsaExtPropagateSelectedSdChanges(v10, v21, a1, &v29);
      goto LABEL_73;
    }
LABEL_74:
    if ( ObjectSD < 0 )
      goto LABEL_87;
    v10 = v29;
    goto LABEL_76;
  }
LABEL_46:
  SampDeReferenceContext(a1, 0);
LABEL_47:
  v15 = SampReleaseWriteLock(0);
  if ( ObjectSD >= 0 )
    ObjectSD = v15;
LABEL_49:
  SampTraceEvent(2);
  v16 = WPP_GLOBAL_Control;
  if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 8) != 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 4u )
  {
    WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 41, WPP_18fb10c206133c98d7a2b000be93359d_Traceguids, (unsigned int)ObjectSD);
    v16 = WPP_GLOBAL_Control;
  }
  if ( (*(_DWORD *)(&v16[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(v16[3].Buffer, 42, WPP_18fb10c206133c98d7a2b000be93359d_Traceguids, (unsigned int)ObjectSD, ObjectSD);
  return (unsigned int)ObjectSD;
}

```

## disassembly

```asm
0x18008cd00  mov     [rsp-38h+arg_0], rbx
0x18008cd05  mov     [rsp-38h+SecurityInformation], edx
0x18008cd09  push    rbp
0x18008cd0a  push    rsi
0x18008cd0b  push    rdi
0x18008cd0c  push    r12
0x18008cd0e  push    r13
0x18008cd10  push    r14
0x18008cd12  push    r15
0x18008cd14  mov     rbp, rsp
0x18008cd17  sub     rsp, 70h
0x18008cd1b  xor     r14d, r14d
0x18008cd1e  mov     rbx, r8
0x18008cd21  mov     dword ptr [rbp+Size+4], r14d
0x18008cd25  mov     r13d, edx
0x18008cd28  mov     [rbp+Src], r14
0x18008cd2c  mov     rdi, rcx
0x18008cd2f  mov     [rbp+ObjectsSecurityDescriptor], r14
0x18008cd33  mov     dword ptr [rbp+Size], r14d
0x18008cd37  mov     [rbp+TokenHandle], r14
0x18008cd3b  mov     dword ptr [rbp+var_28], r14d
0x18008cd3f  mov     [rbp+var_20], r14d
0x18008cd43  mov     [rbp+hMem], r14
0x18008cd47  mov     rcx, cs:WPP_GLOBAL_Control
0x18008cd4e  test    byte ptr [rcx+44h], 8
0x18008cd52  jz      short loc_18008CD76
0x18008cd54  cmp     byte ptr [rcx+41h], 4
0x18008cd58  jb      short loc_18008CD76
0x18008cd5a  mov     rcx, [rcx+38h]
0x18008cd5e  lea     edx, [r14+26h]
0x18008cd62  mov     r9, rdi
0x18008cd65  mov     dword ptr [rsp+70h+Token], r13d
0x18008cd6a  lea     r8, WPP_18fb10c206133c98d7a2b000be93359d_Traceguids
0x18008cd71  call    WPP_SF_qD
0x18008cd76  xor     r8d, r8d
0x18008cd79  lea     edx, [r8+2]
0x18008cd7d  lea     ecx, [rdx-1]
0x18008cd80  call    SampTraceEvent
0x18008cd85  mov     rcx, rbx; struct _SAMPR_SR_SECURITY_DESCRIPTOR *
0x18008cd88  call    ?SampValidateSD@@YAEPEAU_SAMPR_SR_SECURITY_DESCRIPTOR@@@Z; SampValidateSD(_SAMPR_SR_SECURITY_DESCRIPTOR *)
0x18008cd8d  test    al, al
0x18008cd8f  jnz     short loc_18008CD9B
0x18008cd91  mov     ebx, 0C00000E7h
0x18008cd96  jmp     loc_18008CF54
0x18008cd9b  mov     r15d, r13d
0x18008cd9e  and     r15d, 8
0x18008cda2  mov     eax, r15d
0x18008cda5  neg     eax
0x18008cda7  sbb     ecx, ecx
0x18008cda9  and     ecx, 1000000h
0x18008cdaf  mov     edx, ecx
0x18008cdb1  bts     edx, 13h
0x18008cdb5  test    r13b, 3
0x18008cdb9  cmovz   edx, ecx
0x18008cdbc  mov     esi, edx
0x18008cdbe  bts     esi, 12h
0x18008cdc2  test    r13b, 4
0x18008cdc6  cmovz   esi, edx
0x18008cdc9  test    esi, esi
0x18008cdcb  jnz     short loc_18008CDD7
0x18008cdcd  mov     ebx, 0C000000Dh
0x18008cdd2  jmp     loc_18008CF54
0x18008cdd7  mov     r14, [rbx+8]
0x18008cddb  mov     r12d, r13d
0x18008cdde  and     r12d, 1
0x18008cde2  jz      short loc_18008CDEB
0x18008cde4  cmp     dword ptr [r14+4], 0
0x18008cde9  jz      short loc_18008CD91
0x18008cdeb  test    r13b, 2
0x18008cdef  jz      short loc_18008CDF8
0x18008cdf1  cmp     dword ptr [r14+8], 0
0x18008cdf6  jz      short loc_18008CD91
0x18008cdf8  mov     rcx, rdi
0x18008cdfb  call    SampAcquireWriteLock
0x18008ce00  mov     ebx, eax
0x18008ce02  test    eax, eax
0x18008ce04  js      loc_18008CF54
0x18008ce0a  lea     r9, [rbp+Size+4]
0x18008ce0e  mov     [rbp+arg_18], 1
0x18008ce12  mov     r8d, 5
0x18008ce18  mov     edx, esi
0x18008ce1a  mov     rcx, rdi
0x18008ce1d  call    SampLookupContext
0x18008ce22  mov     ecx, dword ptr [rbp+Size+4]
0x18008ce25  xor     esi, esi
0x18008ce27  mov     ebx, eax
0x18008ce29  test    ecx, ecx
0x18008ce2b  jz      short loc_18008CE7E
0x18008ce2d  sub     ecx, 1
0x18008ce30  jz      short loc_18008CE75
0x18008ce32  sub     ecx, 1
0x18008ce35  jz      short loc_18008CE6C
0x18008ce37  sub     ecx, 1
0x18008ce3a  jz      short loc_18008CE63
0x18008ce3c  cmp     ecx, 1
0x18008ce3f  jz      short loc_18008CE53
0x18008ce41  test    eax, eax
0x18008ce43  js      loc_18008CF48
0x18008ce49  mov     ebx, 0C00000E5h
0x18008ce4e  jmp     loc_18008CF48
0x18008ce53  mov     [rbp+var_40], 2
0x18008ce5a  mov     r13d, [rdi+0F8h]
0x18008ce61  jmp     short loc_18008CE88
0x18008ce63  mov     [rbp+var_40], 4
0x18008ce6a  jmp     short loc_18008CE5A
0x18008ce6c  mov     [rbp+var_40], 3
0x18008ce73  jmp     short loc_18008CE5A
0x18008ce75  mov     [rbp+var_40], 1
0x18008ce7c  jmp     short loc_18008CE85
0x18008ce7e  mov     [rbp+var_40], esi
0x18008ce81  mov     [rbp+arg_18], sil
0x18008ce85  mov     r13d, esi
0x18008ce88  test    eax, eax
0x18008ce8a  js      loc_18008CF48
0x18008ce90  test    byte ptr [rdi+0C0h], 2
0x18008ce97  jz      short loc_18008CEBC
0x18008ce99  test    byte ptr [rdi+14h], 20h
0x18008ce9d  jnz     loc_18008CFDF
0x18008cea3  test    r15d, r15d
0x18008cea6  jz      short loc_18008CEBC
0x18008cea8  xor     edx, edx
0x18008ceaa  mov     rcx, rdi
0x18008cead  call    SampDeReferenceContext
0x18008ceb2  mov     ebx, 0C000000Dh
0x18008ceb7  jmp     loc_18008CF48
0x18008cebc  test    byte ptr [rdi+14h], 20h
0x18008cec0  jnz     loc_18008CFDF
0x18008cec6  lea     rdx, [rbp+var_20]; int *
0x18008ceca  mov     rcx, rdi; struct _SAMP_OBJECT *
0x18008cecd  call    ?SampIsLapsAutoManagedAccount@@YAJPEAU_SAMP_OBJECT@@PEAH@Z; SampIsLapsAutoManagedAccount(_SAMP_OBJECT *,int *)
0x18008ced2  mov     ebx, eax
0x18008ced4  test    eax, eax
0x18008ced6  js      loc_18008CFD4
0x18008cedc  cmp     [rbp+var_20], esi
0x18008cedf  jz      short loc_18008CF36
0x18008cee1  mov     rcx, cs:WPP_GLOBAL_Control
0x18008cee8  test    byte ptr [rcx+44h], 1
0x18008ceec  jz      short loc_18008CF09
0x18008ceee  cmp     byte ptr [rcx+41h], 2
0x18008cef2  jb      short loc_18008CF09
0x18008cef4  mov     rcx, [rcx+38h]
0x18008cef8  lea     r8, WPP_18fb10c206133c98d7a2b000be93359d_Traceguids
0x18008ceff  mov     edx, 27h ; '''
0x18008cf04  call    WPP_SF_
0x18008cf09  lea     rdx, [rbp+hMem]; void **
0x18008cf0d  mov     rcx, rdi; struct _SAMP_OBJECT *
0x18008cf10  call    ?SampCreateAccountSid@@YAJPEAU_SAMP_OBJECT@@PEAPEAX@Z; SampCreateAccountSid(_SAMP_OBJECT *,void * *)
0x18008cf15  test    eax, eax
0x18008cf17  js      short loc_18008CF31
0x18008cf19  mov     rcx, [rbp+hMem]; void *
0x18008cf1d  mov     edx, 3; unsigned int
0x18008cf22  call    ?SamLAPSNotifyBlockedOperation@@YAXPEAXK@Z; SamLAPSNotifyBlockedOperation(void *,ulong)
0x18008cf27  mov     rcx, [rbp+hMem]; hMem
0x18008cf2b  call    cs:__imp_LocalFree
0x18008cf31  mov     ebx, 0C000A08Bh
0x18008cf36  test    ebx, ebx
0x18008cf38  jns     loc_18008CFDF
0x18008cf3e  xor     edx, edx
0x18008cf40  mov     rcx, rdi
0x18008cf43  call    SampDeReferenceContext
0x18008cf48  xor     ecx, ecx
0x18008cf4a  call    SampReleaseWriteLock
0x18008cf4f  test    ebx, ebx
0x18008cf51  cmovns  ebx, eax
0x18008cf54  mov     edi, 2
0x18008cf59  mov     r8d, ebx
0x18008cf5c  mov     edx, edi
0x18008cf5e  mov     ecx, edi
0x18008cf60  call    SampTraceEvent
0x18008cf65  mov     rcx, cs:WPP_GLOBAL_Control
0x18008cf6c  test    byte ptr [rcx+44h], 8
0x18008cf70  jz      short loc_18008CF95
0x18008cf72  cmp     byte ptr [rcx+41h], 4
0x18008cf76  jb      short loc_18008CF95
0x18008cf78  mov     rcx, [rcx+38h]
0x18008cf7c  lea     edx, [rdi+27h]
0x18008cf7f  mov     r9d, ebx
0x18008cf82  lea     r8, WPP_18fb10c206133c98d7a2b000be93359d_Traceguids
0x18008cf89  call    WPP_SF_d
0x18008cf8e  mov     rcx, cs:WPP_GLOBAL_Control
0x18008cf95  test    dword ptr [rcx+44h], 20000h
0x18008cf9c  jz      short loc_18008CFBA
0x18008cf9e  mov     rcx, [rcx+38h]
0x18008cfa2  lea     r8, WPP_18fb10c206133c98d7a2b000be93359d_Traceguids
0x18008cfa9  mov     edx, 2Ah ; '*'
0x18008cfae  mov     dword ptr [rsp+70h+Token], ebx
0x18008cfb2  mov     r9d, ebx
0x18008cfb5  call    WPP_SF_Dd
0x18008cfba  mov     eax, ebx
0x18008cfbc  mov     rbx, [rsp+70h+arg_0]
0x18008cfc4  add     rsp, 70h
0x18008cfc8  pop     r15
0x18008cfca  pop     r14
0x18008cfcc  pop     r13
0x18008cfce  pop     r12
0x18008cfd0  pop     rdi
0x18008cfd1  pop     rsi
0x18008cfd2  pop     rbp
0x18008cfd3  retn
0x18008cfd4  cmp     eax, 0C0000064h
0x18008cfd9  jnz     loc_18008CF3E
0x18008cfdf  lea     r8, [rbp+Src]
0x18008cfe3  mov     [rbp+Src], rsi
0x18008cfe7  lea     rdx, [rbp+Size]
0x18008cfeb  mov     dword ptr [rbp+Size], esi
0x18008cfee  mov     rcx, rdi; struct _SAMP_OBJECT *
0x18008cff1  mov     [rbp+ObjectsSecurityDescriptor], rsi
0x18008cff5  call    SampGetObjectSD
0x18008cffa  mov     ebx, eax
0x18008cffc  test    eax, eax
0x18008cffe  js      loc_18008CF3E
0x18008d004  mov     edx, dword ptr [rbp+Size+4]
0x18008d007  mov     r9, r14
0x18008d00a  mov     r8d, r13d
0x18008d00d  mov     rcx, rdi
0x18008d010  call    ?SampCheckForDescriptorRestrictions@@YAJPEAU_SAMP_OBJECT@@W4_SAMP_OBJECT_TYPE@@KPEAU_SECURITY_DESCRIPTOR_RELATIVE@@@Z; SampCheckForDescriptorRestrictions(_SAMP_OBJECT *,_SAMP_OBJECT_TYPE,ulong,_SECURITY_DESCRIPTOR_RELATIVE *)
0x18008d015  mov     ebx, eax
0x18008d017  test    eax, eax
0x18008d019  js      loc_18008D1C5
0x18008d01f  mov     rcx, gs:60h
0x18008d028  xor     edx, edx; Flags
0x18008d02a  mov     r8d, dword ptr [rbp+Size]; Size
0x18008d02e  mov     rcx, [rcx+30h]; HeapHandle
0x18008d032  call    cs:__imp_RtlAllocateHeap
0x18008d038  mov     [rbp+ObjectsSecurityDescriptor], rax
0x18008d03c  test    rax, rax
0x18008d03f  jnz     short loc_18008D04B
0x18008d041  mov     ebx, 0C000009Ah
0x18008d046  jmp     loc_18008D1C5
0x18008d04b  mov     r8d, dword ptr [rbp+Size]; Size
0x18008d04f  mov     rcx, rax; void *
0x18008d052  mov     rdx, [rbp+Src]; Src
0x18008d056  call    memcpy_0
0x18008d05b  mov     [rbp+TokenHandle], rsi
0x18008d05f  test    r12d, r12d
0x18008d062  jz      short loc_18008D0BF
0x18008d064  test    byte ptr [rdi+14h], 20h
0x18008d068  jnz     short loc_18008D0A2
0x18008d06a  lea     rcx, [rbp+var_28]
0x18008d06e  call    SampImpersonateClient
0x18008d073  mov     ebx, eax
0x18008d075  test    eax, eax
0x18008d077  js      loc_18008D1C5
0x18008d07d  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18008d081  mov     r8b, 1; OpenAsSelf
0x18008d084  mov     edx, 8; DesiredAccess
0x18008d089  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18008d090  call    cs:__imp_NtOpenThreadToken
0x18008d096  mov     ecx, dword ptr [rbp+var_28]
0x18008d099  mov     ebx, eax
0x18008d09b  call    SampRevertToSelf
0x18008d0a0  jmp     short loc_18008D0B7
0x18008d0a2  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18008d0a6  mov     edx, 8; DesiredAccess
0x18008d0ab  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x18008d0af  call    cs:__imp_NtOpenProcessToken
0x18008d0b5  mov     ebx, eax
0x18008d0b7  test    ebx, ebx
0x18008d0b9  js      loc_18008D1C5
0x18008d0bf  test    byte ptr [rdi+0C0h], 2
0x18008d0c6  mov     [rbp+var_28], rsi
0x18008d0ca  jz      short loc_18008D120
0x18008d0cc  test    byte ptr [rdi+14h], 20h
0x18008d0d0  mov     esi, [rdi+10h]
0x18008d0d3  jz      short loc_18008D0E8
0x18008d0d5  lea     r9, [rbp+var_28]
0x18008d0d9  mov     r8, rdi
0x18008d0dc  mov     edx, esi
0x18008d0de  mov     rcx, r14
0x18008d0e1  call    ?SampExtConvertNt4SdToNt5SdDs@@YAJPEAXW4_SAMP_OBJECT_TYPE@@PEAU_SAMP_OBJECT@@PEAPEAX@Z; SampExtConvertNt4SdToNt5SdDs(void *,_SAMP_OBJECT_TYPE,_SAMP_OBJECT *,void * *)
0x18008d0e6  jmp     short loc_18008D110
0x18008d0e8  call    ?SampShouldCallNtdsaApiSet@@YAJXZ; SampShouldCallNtdsaApiSet(void)
0x18008d0ed  mov     ebx, eax
0x18008d0ef  cmp     eax, 0C00000BBh
0x18008d0f4  jnz     short loc_18008D0FA
0x18008d0f6  xor     ebx, ebx
0x18008d0f8  jmp     short loc_18008D112
0x18008d0fa  test    eax, eax
0x18008d0fc  js      short loc_18008D112
0x18008d0fe  lea     r9, [rbp+var_28]
0x18008d102  mov     r8, rdi
0x18008d105  mov     edx, esi
0x18008d107  mov     rcx, r14
0x18008d10a  call    cs:__imp_NtdsaExtPropagateSelectedSdChanges
0x18008d110  mov     ebx, eax
0x18008d112  xor     esi, esi
0x18008d114  test    ebx, ebx
0x18008d116  js      loc_18008D1C5
0x18008d11c  mov     r14, [rbp+var_28]
0x18008d120  movsxd  rax, dword ptr [rbp+Size+4]
0x18008d124  lea     r8, [rbp+ObjectsSecurityDescriptor]; ObjectsSecurityDescriptor
0x18008d128  mov     ecx, [rbp+SecurityInformation]; SecurityInformation
0x18008d12b  mov     rdx, r14; ModificationDescriptor
0x18008d12e  imul    r9, rax, 58h ; 'X'
0x18008d132  lea     rax, ?SampObjectInformation@@3PAU_SAMP_OBJECT_INFORMATION@@A; _SAMP_OBJECT_INFORMATION near * SampObjectInformation
0x18008d139  add     r9, rax; GenericMapping
0x18008d13c  mov     rax, [rbp+TokenHandle]
0x18008d140  mov     [rsp+70h+Token], rax; Token
0x18008d145  call    cs:__imp_RtlSetSecurityObject
0x18008d14b  mov     rcx, [rbp+TokenHandle]; Handle
  ... truncated ...
```
