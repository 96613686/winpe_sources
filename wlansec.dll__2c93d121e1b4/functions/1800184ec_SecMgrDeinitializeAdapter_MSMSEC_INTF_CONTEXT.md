# SecMgrDeinitializeAdapter(MSMSEC_INTF_CONTEXT *)

- ea: `0x1800184ec`
- end: `0x18001876c`
- name: `?SecMgrDeinitializeAdapter@@YAXPEAUMSMSEC_INTF_CONTEXT@@@Z`
- size: `640`
- prototype: `void __fastcall(struct MSMSEC_INTF_CONTEXT *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x180038368`

## callees

- `0x180004518`
- `0x180005418`
- `0x18000892c`
- `0x180008998`
- `0x1800169c0`
- `0x1800184ec`
- `0x1800319ec`
- `0x180035e00`
- `0x1800361cc`
- `0x180043e00`
- `0x1800832d8`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x1800185b6`
- `MobileNetworking!ReleaseWriteLock` at `0x1800185b6`
- `MobileNetworking!AcquireWriteLock` at `0x18001853d`
- `MobileNetworking!AcquireWriteLock` at `0x18001853d`

## pseudocode

```c
void __fastcall SecMgrDeinitializeAdapter(struct MSMSEC_INTF_CONTEXT *a1)
{
  PVOID *v2; // rdi
  __int64 v3; // rdi
  struct _RTL_CRITICAL_SECTION *v4; // rcx
  const char *v5; // r8
  const char *v6; // r10
  const char *v7; // rax

  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 59, &WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids);
      v2 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 68) & 2) != 0 )
      WPP_SF_qDDDDDD(
        v2[7],
        60,
        *((unsigned __int8 *)a1 + 2363),
        a1,
        *((unsigned __int8 *)a1 + 2360),
        *((unsigned __int8 *)a1 + 2361),
        *((unsigned __int8 *)a1 + 2362),
        *((unsigned __int8 *)a1 + 2363),
        *((unsigned __int8 *)a1 + 2364),
        *((unsigned __int8 *)a1 + 2365));
  }
  TraceAdapterId(*((_DWORD *)a1 + 624), ">>> Locking >>>");
  AcquireWriteLock(a1, (char *)a1 + 2512, "SecMgrDeinitializeAdapter", 842);
  v3 = *((_QWORD *)a1 + 418);
  if ( v3 )
  {
    SaeAuthContextManager::~SaeAuthContextManager((SaeAuthContextManager *)(v3 + 16));
    operator delete((void *)v3, (const struct std::nothrow_t *)0x600);
  }
  if ( *((_DWORD *)a1 + 680) )
    FreeAPPeerKeyList((struct _LIST_ENTRY *)a1 + 169, (unsigned int *)a1 + 680);
  v4 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)a1 + 417);
  if ( v4 )
  {
    IpAllocationMgrDestroy(v4);
    *((_QWORD *)a1 + 417) = 0;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0 )
  {
    v5 = "Empty";
    v6 = "nullptr";
    if ( *((_QWORD *)a1 + 333) )
      v6 = "Non-nullptr";
    v7 = "Empty";
    if ( *((struct MSMSEC_INTF_CONTEXT **)a1 + 338) != (struct MSMSEC_INTF_CONTEXT *)((char *)a1 + 2704) )
      v5 = "Non-empty";
    if ( *((struct MSMSEC_INTF_CONTEXT **)a1 + 336) != (struct MSMSEC_INTF_CONTEXT *)((char *)a1 + 2688) )
      v7 = "Non-empty";
    WPP_SF_ssss(*((_QWORD *)WPP_GLOBAL_Control + 7), (__int64)v7, (__int64)v5, (__int64)v6);
  }
  TraceAdapterId(*((_DWORD *)a1 + 624), "<<< Unlocking <<<");
  ReleaseWriteLock(a1, (char *)a1 + 2512, "SecMgrDeinitializeAdapter", 877);
  SecMgrDeinitializeAdapterHelper(a1, 1, 1, 1, 1);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 62, &WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids, 0);
}

```

## disassembly

```asm
0x1800184ec  push    rbx
0x1800184ee  push    rbp
0x1800184ef  push    rsi
0x1800184f0  push    rdi
0x1800184f1  push    r14
0x1800184f3  sub     rsp, 50h
0x1800184f7  mov     rbx, rcx
0x1800184fa  mov     rdi, cs:WPP_GLOBAL_Control
0x180018501  lea     r14, WPP_GLOBAL_Control
0x180018508  cmp     rdi, r14
0x18001850b  jnz     loc_1800185F5
0x180018511  mov     ecx, [rbx+9C0h]; unsigned int
0x180018517  lea     rdx, aLocking; ">>> Locking >>>"
0x18001851e  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x180018523  lea     rsi, [rbx+9D0h]
0x18001852a  mov     r9d, 34Ah
0x180018530  mov     rdx, rsi
0x180018533  lea     r8, aSecmgrdeinitia; "SecMgrDeinitializeAdapter"
0x18001853a  mov     rcx, rbx
0x18001853d  call    cs:__imp_AcquireWriteLock
0x180018544  nop     dword ptr [rax+rax+00h]
0x180018549  mov     rdi, [rbx+0D10h]
0x180018550  xor     ebp, ebp
0x180018552  test    rdi, rdi
0x180018555  jnz     loc_180018692
0x18001855b  lea     rdx, [rbx+0AA0h]; unsigned int *
0x180018562  lea     rdi, [rbx+0A90h]
0x180018569  cmp     [rdx], ebp
0x18001856b  jnz     loc_1800186AD
0x180018571  mov     rcx, [rbx+0D08h]; lpCriticalSection
0x180018578  test    rcx, rcx
0x18001857b  jnz     loc_1800186BA
0x180018581  mov     rcx, cs:WPP_GLOBAL_Control
0x180018588  cmp     rcx, r14
0x18001858b  jnz     loc_1800186CB
0x180018591  mov     ecx, [rbx+9C0h]; unsigned int
0x180018597  lea     rdx, aUnlocking; "<<< Unlocking <<<"
0x18001859e  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x1800185a3  mov     r9d, 36Dh
0x1800185a9  lea     r8, aSecmgrdeinitia; "SecMgrDeinitializeAdapter"
0x1800185b0  mov     rdx, rsi
0x1800185b3  mov     rcx, rbx
0x1800185b6  call    cs:__imp_ReleaseWriteLock
0x1800185bd  nop     dword ptr [rax+rax+00h]
0x1800185c2  mov     edx, 1; int
0x1800185c7  mov     rcx, rbx; struct MSMSEC_INTF_CONTEXT *
0x1800185ca  mov     r9d, edx; int
0x1800185cd  mov     dword ptr [rsp+78h+var_58], edx; int
0x1800185d1  mov     r8d, edx; int
0x1800185d4  call    ?SecMgrDeinitializeAdapterHelper@@YAXPEAUMSMSEC_INTF_CONTEXT@@HHHH@Z; SecMgrDeinitializeAdapterHelper(MSMSEC_INTF_CONTEXT *,int,int,int,int)
0x1800185d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800185e0  cmp     rcx, r14
0x1800185e3  jnz     loc_180018742
0x1800185e9  add     rsp, 50h
0x1800185ed  pop     r14
0x1800185ef  pop     rdi
0x1800185f0  pop     rsi
0x1800185f1  pop     rbp
0x1800185f2  pop     rbx
0x1800185f3  retn
0x1800185f5  test    dword ptr [rdi+44h], 100h
0x1800185fc  jnz     short loc_180018671
0x1800185fe  cmp     rdi, r14
0x180018601  jz      loc_180018511
0x180018607  test    byte ptr [rdi+44h], 2
0x18001860b  jz      loc_180018511
0x180018611  movzx   ecx, byte ptr [rbx+93Ch]
0x180018618  mov     edx, 3Ch ; '<'
0x18001861d  movzx   r9d, byte ptr [rbx+93Ah]
0x180018625  movzx   eax, byte ptr [rbx+93Dh]
0x18001862c  movzx   r8d, byte ptr [rbx+93Bh]
0x180018634  movzx   r10d, byte ptr [rbx+939h]
0x18001863c  movzx   r11d, byte ptr [rbx+938h]
0x180018644  mov     [rsp+78h+var_30], eax
0x180018648  mov     [rsp+78h+var_38], ecx
0x18001864c  mov     rcx, [rdi+38h]
0x180018650  mov     [rsp+78h+var_40], r8d
0x180018655  mov     dword ptr [rsp+78h+var_48], r9d
0x18001865a  mov     r9, rbx
0x18001865d  mov     dword ptr [rsp+78h+var_50], r10d
0x180018662  mov     dword ptr [rsp+78h+var_58], r11d
0x180018667  call    WPP_SF_qDDDDDD
0x18001866c  jmp     loc_180018511
0x180018671  mov     rcx, [rdi+38h]
0x180018675  lea     r8, WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids
0x18001867c  mov     edx, 3Bh ; ';'
0x180018681  call    WPP_SF_
0x180018686  mov     rdi, cs:WPP_GLOBAL_Control
0x18001868d  jmp     loc_1800185FE
0x180018692  lea     rcx, [rdi+10h]; this
0x180018696  call    ??1SaeAuthContextManager@@QEAA@XZ; SaeAuthContextManager::~SaeAuthContextManager(void)
0x18001869b  mov     edx, 600h; struct std::nothrow_t *
0x1800186a0  mov     rcx, rdi; void *
0x1800186a3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800186a8  jmp     loc_18001855B
0x1800186ad  mov     rcx, rdi; struct _LIST_ENTRY *
0x1800186b0  call    ?FreeAPPeerKeyList@@YAXPEAU_LIST_ENTRY@@PEAK@Z; FreeAPPeerKeyList(_LIST_ENTRY *,ulong *)
0x1800186b5  jmp     loc_180018571
0x1800186ba  call    ?IpAllocationMgrDestroy@@YAKPEAU_IP_ALLOCATION_MGR@@@Z; IpAllocationMgrDestroy(_IP_ALLOCATION_MGR *)
0x1800186bf  mov     [rbx+0D08h], rbp
0x1800186c6  jmp     loc_180018581
0x1800186cb  test    byte ptr [rcx+44h], 2
0x1800186cf  jz      loc_180018591
0x1800186d5  cmp     [rbx+0A68h], rbp
0x1800186dc  lea     r9, aEmpty; "Empty"
0x1800186e3  mov     rcx, [rcx+38h]; LoggerHandle
0x1800186e7  lea     rbp, aNonEmpty; "Non-empty"
0x1800186ee  mov     r8, r9
0x1800186f1  lea     rax, aNonNullptr; "Non-nullptr"
0x1800186f8  lea     rdx, [rbx+0A80h]
0x1800186ff  lea     r11, [rbx+0A70h]
0x180018706  lea     r10, aNullptr; "nullptr"
0x18001870d  cmovnz  r10, rax
0x180018711  cmp     [rdi], rdi
0x180018714  mov     rax, r9
0x180018717  mov     [rsp+78h+var_48], r10; __int64
0x18001871c  cmovnz  r8, rbp
0x180018720  cmp     [rdx], rdx
0x180018723  mov     [rsp+78h+var_50], r8; __int64
0x180018728  cmovnz  rax, rbp
0x18001872c  cmp     [r11], r11
0x18001872f  mov     [rsp+78h+var_58], rax; __int64
0x180018734  cmovnz  r9, rbp
0x180018738  call    WPP_SF_ssss
0x18001873d  jmp     loc_180018591
0x180018742  test    dword ptr [rcx+44h], 100h
0x180018749  jz      loc_1800185E9
0x18001874f  mov     rcx, [rcx+38h]
0x180018753  lea     r8, WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids
0x18001875a  mov     edx, 3Eh ; '>'
0x18001875f  xor     r9d, r9d
0x180018762  call    WPP_SF_d
0x180018767  jmp     loc_1800185E9
```
