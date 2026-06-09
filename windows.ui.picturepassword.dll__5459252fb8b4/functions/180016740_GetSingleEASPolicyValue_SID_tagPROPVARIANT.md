# GetSingleEASPolicyValue(_SID *,tagPROPVARIANT *)

- ea: `0x180016740`
- end: `0x180016850`
- name: `?GetSingleEASPolicyValue@@YAJPEAU_SID@@PEAUtagPROPVARIANT@@@Z`
- size: `272`
- prototype: `__int64 __fastcall(struct _SID *, struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x1800168c4`

## callees

- `0x180016740`
- `0x180016858`
- `0x180019d68`
- `0x180019e3c`
- `0x18001a22c`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x1800167be`
- `ntdll!RtlReleaseResource` at `0x1800167be`
- `ntdll!RtlAcquireResourceExclusive` at `0x180016760`
- `ntdll!RtlAcquireResourceExclusive` at `0x180016760`
- `ntdll!RtlInitializeResource` at `0x180016787`
- `ntdll!RtlInitializeResource` at `0x180016787`

## pseudocode

```c
__int64 __fastcall GetSingleEASPolicyValue(struct _SID *a1, struct tagPROPVARIANT *a2)
{
  void *v3; // rdx
  __int64 v4; // rcx
  int v5; // ebx
  __int64 v6; // r8
  int Policies; // eax
  struct _tagEASPolicy *v8; // rdx
  unsigned int i; // eax
  __int64 v10; // rcx
  struct _SID *v12; // [rsp+40h] [rbp+8h] BYREF
  struct _tagEASPolicy *v13; // [rsp+48h] [rbp+10h] BYREF

  v12 = a1;
  a2->vt = 0;
  RtlAcquireResourceExclusive(&g_lockObject, 1u);
  ++g_dwRefCount;
  if ( !g_bInitialized )
  {
    g_pFnLog = 0;
    RtlInitializeResource(&g_EvalLock);
    gProvData = 1;
    dword_18002D628 = 0;
    qword_18002D630 = 0;
    g_bInitialized = 1;
  }
  RtlReleaseResource(&g_lockObject);
  v5 = ResultFromWin32FromStatus(0);
  if ( v5 >= 0 )
  {
    LODWORD(v12) = 0;
    v13 = 0;
    Policies = EasEngineGetPolicies(v4, v3, v6, (unsigned int *)&v12, &v13);
    v5 = ResultFromWin32FromStatus(Policies);
    if ( v5 >= 0 )
    {
      v8 = v13;
      for ( i = 0; ; ++i )
      {
        v5 = -2147467259;
        if ( i >= (unsigned int)v12 )
          break;
        v10 = 32LL * i;
        if ( *(_DWORD *)((char *)v13 + v10) == 5 )
        {
          v5 = 0;
          a2->iVal = *(_WORD *)((char *)v13 + v10 + 16);
          a2->vt = 11;
          break;
        }
      }
      _FreePolicies((unsigned int)v12, v8);
    }
    EasEngineUninitialize();
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180016740  mov     [rsp+arg_10], rbx
0x180016745  mov     [rsp+arg_0], rcx
0x18001674a  push    rdi
0x18001674b  sub     rsp, 30h
0x18001674f  xor     eax, eax
0x180016751  lea     rcx, ?g_lockObject@@3VLibraryInitLock@@A; Resource
0x180016758  mov     [rdx], ax
0x18001675b  mov     rdi, rdx
0x18001675e  mov     dl, 1; Wait
0x180016760  call    cs:__imp_RtlAcquireResourceExclusive
0x180016766  inc     cs:?g_dwRefCount@@3KA; ulong g_dwRefCount
0x18001676c  cmp     cs:?g_bInitialized@@3HA, 0; int g_bInitialized
0x180016773  jnz     short loc_1800167B7
0x180016775  lea     rcx, ?g_EvalLock@@3U_RTL_RESOURCE@@A; Resource
0x18001677c  mov     cs:?g_pFnLog@@3P6AXKPEAG@ZEA, 0; void (*g_pFnLog)(ulong,ushort *)
0x180016787  call    cs:__imp_RtlInitializeResource
0x18001678d  mov     cs:?gProvData@@3U_PROVIDER_DATA@@A, 1; _PROVIDER_DATA gProvData
0x180016798  mov     cs:dword_18002D628, 0
0x1800167a2  mov     cs:qword_18002D630, 0
0x1800167ad  mov     cs:?g_bInitialized@@3HA, 1; int g_bInitialized
0x1800167b7  lea     rcx, ?g_lockObject@@3VLibraryInitLock@@A; Resource
0x1800167be  call    cs:__imp_RtlReleaseResource
0x1800167c4  xor     ecx, ecx; int
0x1800167c6  call    ?ResultFromWin32FromStatus@@YAJJ@Z; ResultFromWin32FromStatus(long)
0x1800167cb  mov     ebx, eax
0x1800167cd  test    eax, eax
0x1800167cf  js      short loc_180016843
0x1800167d1  lea     rax, [rsp+38h+arg_8]
0x1800167d6  mov     dword ptr [rsp+38h+arg_0], 0
0x1800167de  lea     r9, [rsp+38h+arg_0]; unsigned int *
0x1800167e3  mov     [rsp+38h+var_18], rax; struct _tagEASPolicy **
0x1800167e8  mov     [rsp+38h+arg_8], 0
0x1800167f1  call    ?EasEngineGetPolicies@@YAJHPEAXKPEAKPEAPEAU_tagEASPolicy@@@Z; EasEngineGetPolicies(int,void *,ulong,ulong *,_tagEASPolicy * *)
0x1800167f6  mov     ecx, eax; int
0x1800167f8  call    ?ResultFromWin32FromStatus@@YAJJ@Z; ResultFromWin32FromStatus(long)
0x1800167fd  mov     ebx, eax
0x1800167ff  test    eax, eax
0x180016801  js      short loc_18001683E
0x180016803  mov     rdx, [rsp+38h+arg_8]; struct _tagEASPolicy *
0x180016808  xor     eax, eax
0x18001680a  mov     ebx, 80004005h
0x18001680f  cmp     eax, dword ptr [rsp+38h+arg_0]
0x180016813  jnb     short loc_180016835
0x180016815  mov     ecx, eax
0x180016817  shl     rcx, 5
0x18001681b  cmp     dword ptr [rcx+rdx], 5
0x18001681f  jz      short loc_180016825
0x180016821  inc     eax
0x180016823  jmp     short loc_18001680A
0x180016825  movzx   eax, word ptr [rcx+rdx+10h]
0x18001682a  xor     ebx, ebx
0x18001682c  mov     [rdi+8], ax
0x180016830  mov     word ptr [rdi], 0Bh
0x180016835  mov     ecx, dword ptr [rsp+38h+arg_0]; unsigned int
0x180016839  call    ?_FreePolicies@@YAXKPEAU_tagEASPolicy@@@Z; _FreePolicies(ulong,_tagEASPolicy *)
0x18001683e  call    EasEngineUninitialize
0x180016843  mov     eax, ebx
0x180016845  mov     rbx, [rsp+38h+arg_10]
0x18001684a  add     rsp, 30h
0x18001684e  pop     rdi
0x18001684f  retn
```
