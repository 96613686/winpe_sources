# InitializeExternalAuthorizationEngine(void)

- ea: `0x1004161b0`
- end: `0x1004162ca`
- name: `?InitializeExternalAuthorizationEngine@@YAXXZ`
- size: `282`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config`

## callers

- `0x100416770`

## callees

- `0x1004161b0`
- `0x1004403d0`

## import_xrefs

- `sqlmin!?Init@CGlobalBabylonPolicyProvider@@SAXPEAVIMemObj@@@Z` at `0x100416261`
- `sqlmin!?Init@CGlobalBabylonPolicyProvider@@SAXPEAVIMemObj@@@Z` at `0x100416261`
- `sqllang!?Init@CArcResourceInfo@@SAXPEAVIMemObj@@@Z` at `0x10041626a`
- `sqllang!?Init@CArcResourceInfo@@SAXPEAVIMemObj@@@Z` at `0x10041626a`
- `sqllang!?Init@CExtGovDatabasesPermCache@@SAXPEAVIMemObj@@@Z` at `0x100416258`
- `sqllang!?Init@CExtGovDatabasesPermCache@@SAXPEAVIMemObj@@@Z` at `0x100416258`
- `sqllang!?Init@CPurviewAadGroupsInfo@@SAXPEAVIMemObj@@@Z` at `0x10041624f`
- `sqllang!?Init@CPurviewAadGroupsInfo@@SAXPEAVIMemObj@@@Z` at `0x10041624f`
- `sqllang!?Init@CPurviewSessionsAuditCache@@SAXPEAVIMemObj@@@Z` at `0x100416246`
- `sqllang!?Init@CPurviewSessionsAuditCache@@SAXPEAVIMemObj@@@Z` at `0x100416246`
- `sqllang!?Init@CBabylonPdp@@SAXPEAVIMemObj@@@Z` at `0x10041623d`
- `sqllang!?Init@CBabylonPdp@@SAXPEAVIMemObj@@@Z` at `0x10041623d`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10041629c`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10041629c`
- `sqldk!SystemThread_TlsOffset` at `0x100416283`
- `sqldk!SystemThread_TlsIndex` at `0x10041627a`
- `sqldk!?CreateMemObject@MemoryObjectFactory@@SAPEAVIMemObj@@W4SOSHOST_MEMOBJ_ID@@KPEAVPageAllocator@@FF@Z` at `0x100416211`
- `sqldk!?CreateMemObject@MemoryObjectFactory@@SAPEAVIMemObj@@W4SOSHOST_MEMOBJ_ID@@KPEAVPageAllocator@@FF@Z` at `0x100416211`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x1004162b7`
- `sqldk!?CreateMemoryClerk@SOS_Node@@SAPEAVMemoryClerk@@PEB_WW4SOSHOST_MEMORYCLERK_TYPE@@W4SOS_CallerType@@@Z` at `0x1004161cf`
- `sqldk!?CreateMemoryClerk@SOS_Node@@SAPEAVMemoryClerk@@PEB_WW4SOSHOST_MEMORYCLERK_TYPE@@W4SOS_CallerType@@@Z` at `0x1004161cf`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void InitializeExternalAuthorizationEngine(void)
{
  struct MemoryClerk *MemoryClerk; // rax
  const wchar_t *v1; // rdx
  struct IMemObj *MemObject; // rax
  struct IMemObj *v3; // rbx
  __int64 v4; // rbx
  __int64 v5; // rcx
  _BYTE v6[16]; // [rsp+38h] [rbp-30h] BYREF
  _BYTE v7[32]; // [rsp+48h] [rbp-20h] BYREF
  struct IMemObj *v8; // [rsp+70h] [rbp+8h]

  MemoryClerk = (struct MemoryClerk *)SOS_Node::CreateMemoryClerk(
                                        L"MemoryClerk EXTERNAL GOVERNANCE AUTHORIZATION ENGINE",
                                        92,
                                        1);
  s_memoryClerkRBAC = MemoryClerk;
  if ( !MemoryClerk )
  {
    v1 = L"External Governance Authorization Engine SSO";
LABEL_3:
    scierrlog(0x42F2u, v1);
    return;
  }
  MemObject = (struct IMemObj *)MemoryObjectFactory::CreateMemObject(423, 2, (char *)MemoryClerk + 64, 8, 128);
  v3 = MemObject;
  v8 = MemObject;
  if ( !MemObject )
  {
    v1 = L"External Governance Authorization Engine PMO";
    goto LABEL_3;
  }
  try
  {
    CBabylonPdp::Init(MemObject);
    CPurviewSessionsAuditCache::Init(v3);
    CPurviewAadGroupsInfo::Init(v3);
    CExtGovDatabasesPermCache::Init(v3);
    CGlobalBabylonPolicyProvider::Init(v3);
    CArcResourceInfo::Init(v3);
  }
  catch ( SQLError v7 )
  {
    try
    {
      ExceptionBackout::ExceptionBackout((ExceptionBackout *)v6, (const struct SQLError *)v7);
      (*(void (__fastcall **)(struct IMemObj *))(*(_QWORD *)v8 + 16LL))(v8);
      ExceptionBackout::~ExceptionBackout((ExceptionBackout *)v6);
    }
    catch ( ShortStackException )
    {
    }
  }
  v4 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v5 = *(_QWORD *)(v4 + 256);
  if ( !v5 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v5 = *(_QWORD *)(v4 + 256);
  }
  if ( *(_DWORD *)(v5 + 556) )
    ExceptionPostCatchActions((struct Worker *)v5);
}

```

## disassembly

```asm
0x1004161b0  push    rbx
0x1004161b2  sub     rsp, 60h
0x1004161b6  mov     [rsp+68h+var_38], 0FFFFFFFFFFFFFFFEh
0x1004161bf  mov     edx, 5Ch ; '\'
0x1004161c4  lea     r8d, [rdx-5Bh]
0x1004161c8  lea     rcx, aMemoryclerkExt_3; "MemoryClerk EXTERNAL GOVERNANCE AUTHORI"...
0x1004161cf  call    cs:__imp_?CreateMemoryClerk@SOS_Node@@SAPEAVMemoryClerk@@PEB_WW4SOSHOST_MEMORYCLERK_TYPE@@W4SOS_CallerType@@@Z; SOS_Node::CreateMemoryClerk(wchar_t const *,SOSHOST_MEMORYCLERK_TYPE,SOS_CallerType)
0x1004161d5  mov     cs:?s_memoryClerkRBAC@@3PEAVMemoryClerk@@EA, rax; MemoryClerk * s_memoryClerkRBAC
0x1004161dc  test    rax, rax
0x1004161df  jnz     short loc_1004161F7
0x1004161e1  lea     rdx, aExternalGovern; "External Governance Authorization Engin"...
0x1004161e8  mov     ecx, 42F2h; unsigned int
0x1004161ed  add     rsp, 60h
0x1004161f1  pop     rbx
0x1004161f2  jmp     ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x1004161f7  lea     r8, [rax+40h]
0x1004161fb  mov     eax, 80h
0x100416200  lea     r9d, [rax-78h]
0x100416204  mov     [rsp+68h+var_48], ax
0x100416209  lea     edx, [rax-7Eh]
0x10041620c  mov     ecx, 1A7h
0x100416211  call    cs:__imp_?CreateMemObject@MemoryObjectFactory@@SAPEAVIMemObj@@W4SOSHOST_MEMOBJ_ID@@KPEAVPageAllocator@@FF@Z; MemoryObjectFactory::CreateMemObject(SOSHOST_MEMOBJ_ID,ulong,PageAllocator *,short,short)
0x100416217  mov     rbx, rax
0x10041621a  mov     [rsp+68h+arg_0], rax
0x10041621f  test    rax, rax
0x100416222  jnz     short loc_10041623A
0x100416224  lea     rdx, aExternalGovern_0; "External Governance Authorization Engin"...
0x10041622b  mov     ecx, 42F2h; unsigned int
0x100416230  add     rsp, 60h
0x100416234  pop     rbx
0x100416235  jmp     ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x10041623a  mov     rcx, rbx
0x10041623d  call    cs:__imp_?Init@CBabylonPdp@@SAXPEAVIMemObj@@@Z; CBabylonPdp::Init(IMemObj *)
0x100416243  mov     rcx, rbx
0x100416246  call    cs:__imp_?Init@CPurviewSessionsAuditCache@@SAXPEAVIMemObj@@@Z; CPurviewSessionsAuditCache::Init(IMemObj *)
0x10041624c  mov     rcx, rbx
0x10041624f  call    cs:__imp_?Init@CPurviewAadGroupsInfo@@SAXPEAVIMemObj@@@Z; CPurviewAadGroupsInfo::Init(IMemObj *)
0x100416255  mov     rcx, rbx
0x100416258  call    cs:__imp_?Init@CExtGovDatabasesPermCache@@SAXPEAVIMemObj@@@Z; CExtGovDatabasesPermCache::Init(IMemObj *)
0x10041625e  mov     rcx, rbx
0x100416261  call    cs:__imp_?Init@CGlobalBabylonPolicyProvider@@SAXPEAVIMemObj@@@Z; CGlobalBabylonPolicyProvider::Init(IMemObj *)
0x100416267  mov     rcx, rbx
0x10041626a  call    cs:__imp_?Init@CArcResourceInfo@@SAXPEAVIMemObj@@@Z; CArcResourceInfo::Init(IMemObj *)
0x100416270  nop
0x100416271  mov     rdx, gs:58h
0x10041627a  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100416281  mov     ecx, [rax]
0x100416283  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10041628a  mov     ebx, [rax]
0x10041628c  add     rbx, [rdx+rcx*8]
0x100416290  mov     rcx, [rbx+100h]
0x100416297  test    rcx, rcx
0x10041629a  jnz     short loc_1004162A9
0x10041629c  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1004162a2  mov     rcx, [rbx+100h]
0x1004162a9  cmp     dword ptr [rcx+22Ch], 0
0x1004162b0  jz      short loc_1004162C4
0x1004162b2  add     rsp, 60h
0x1004162b6  pop     rbx
0x1004162b7  jmp     cs:__imp_?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z; ExceptionPostCatchActions(Worker *)
0x1004162c4  add     rsp, 60h
0x1004162c8  pop     rbx
0x1004162c9  retn
```
