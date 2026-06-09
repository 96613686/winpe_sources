# CServiceRecord::~CServiceRecord(void)

- ea: `0x1400228b0`
- end: `0x1400229c1`
- name: `??1CServiceRecord@@UEAA@XZ`
- size: `273`
- prototype: `void __fastcall(struct _WNF_STATE_NAME *this)`
- caller_count: `4`
- callee_count: `3`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x140043708`
- `0x14006f9d0`
- `0x140072c60`
- `0x140085c20`

## callees

- `0x1400228b0`
- `0x1400229c8`
- `0x140057844`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x1400228e0`
- `ntdll!RtlFreeHeap` at `0x1400228fe`
- `ntdll!RtlFreeHeap` at `0x14002291f`
- `ntdll!RtlFreeHeap` at `0x1400228e0`
- `ntdll!RtlFreeHeap` at `0x1400228fe`
- `ntdll!RtlFreeHeap` at `0x14002291f`
- `ntdll!NtDeleteWnfStateName` at `0x140022948`
- `ntdll!NtDeleteWnfStateName` at `0x14002295e`
- `ntdll!NtDeleteWnfStateName` at `0x140022948`
- `ntdll!NtDeleteWnfStateName` at `0x14002295e`
- `ntdll!RtlDeleteSecurityObject` at `0x140022932`
- `ntdll!RtlDeleteSecurityObject` at `0x140022932`

## pseudocode

```c
void __fastcall CServiceRecord::~CServiceRecord(struct _WNF_STATE_NAME *this)
{
  void *v1; // r8
  void *v3; // r8
  void *v4; // r8
  struct _WNF_STATE_NAME *v5; // rdi
  __int64 *v6; // rcx
  __int64 *v7; // rdx
  __int64 v8; // rax
  void *v9; // rcx

  v1 = (void *)this[8];
  *this = (struct _WNF_STATE_NAME)&CServiceRecord::`vftable';
  if ( v1 != (void *)this[7] )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v1);
  v3 = (void *)this[7];
  if ( v3 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v3);
  v4 = (void *)this[41];
  if ( v4 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v4);
  if ( this[18] )
    RtlDeleteSecurityObject((PSECURITY_DESCRIPTOR *)&this[18]);
  if ( (unsigned int)ScIsStateNameAllocated(this + 25) )
    NtDeleteWnfStateName();
  if ( (unsigned int)ScIsStateNameAllocated(this + 26) )
    NtDeleteWnfStateName();
  v5 = this + 34;
  while ( 1 )
  {
    v6 = (__int64 *)*v5;
    if ( (struct _WNF_STATE_NAME *)*v5 == v5 )
      break;
    v7 = (__int64 *)v6[1];
    v8 = *v6;
    *v7 = *v6;
    *(_QWORD *)(v8 + 8) = v7;
    operator delete(v6, (const struct std::nothrow_t *)std::nothrow);
  }
  v9 = (void *)this[36];
  this[37] = 0;
  if ( v9 )
    operator delete(v9, (const struct std::nothrow_t *)std::nothrow);
  *this = (struct _WNF_STATE_NAME)&SmartPtrRef::`vftable';
}

```

## disassembly

```asm
0x1400228b0  mov     [rsp+arg_0], rbx
0x1400228b5  push    rdi
0x1400228b6  sub     rsp, 20h
0x1400228ba  mov     r8, [rcx+40h]; P
0x1400228be  lea     rax, ??_7CServiceRecord@@6B@; const CServiceRecord::`vftable'
0x1400228c5  mov     rbx, rcx
0x1400228c8  mov     [rcx], rax
0x1400228cb  cmp     r8, [rcx+38h]
0x1400228cf  jz      short loc_1400228E6
0x1400228d1  mov     rcx, gs:60h
0x1400228da  xor     edx, edx; Flags
0x1400228dc  mov     rcx, [rcx+30h]; HeapHandle
0x1400228e0  call    cs:__imp_RtlFreeHeap
0x1400228e6  mov     r8, [rbx+38h]; P
0x1400228ea  test    r8, r8
0x1400228ed  jz      short loc_140022904
0x1400228ef  mov     rcx, gs:60h
0x1400228f8  xor     edx, edx; Flags
0x1400228fa  mov     rcx, [rcx+30h]; HeapHandle
0x1400228fe  call    cs:__imp_RtlFreeHeap
0x140022904  mov     r8, [rbx+148h]; P
0x14002290b  test    r8, r8
0x14002290e  jz      short loc_140022925
0x140022910  mov     rcx, gs:60h
0x140022919  xor     edx, edx; Flags
0x14002291b  mov     rcx, [rcx+30h]; HeapHandle
0x14002291f  call    cs:__imp_RtlFreeHeap
0x140022925  lea     rcx, [rbx+90h]; ObjectDescriptor
0x14002292c  cmp     qword ptr [rcx], 0
0x140022930  jz      short loc_140022938
0x140022932  call    cs:__imp_RtlDeleteSecurityObject
0x140022938  lea     rcx, [rbx+0C8h]; struct _WNF_STATE_NAME *
0x14002293f  call    ?ScIsStateNameAllocated@@YAHAEAU_WNF_STATE_NAME@@@Z; ScIsStateNameAllocated(_WNF_STATE_NAME &)
0x140022944  test    eax, eax
0x140022946  jz      short loc_14002294E
0x140022948  call    cs:__imp_NtDeleteWnfStateName
0x14002294e  lea     rcx, [rbx+0D0h]; struct _WNF_STATE_NAME *
0x140022955  call    ?ScIsStateNameAllocated@@YAHAEAU_WNF_STATE_NAME@@@Z; ScIsStateNameAllocated(_WNF_STATE_NAME &)
0x14002295a  test    eax, eax
0x14002295c  jz      short loc_140022964
0x14002295e  call    cs:__imp_NtDeleteWnfStateName
0x140022964  lea     rdi, [rbx+110h]
0x14002296b  mov     rcx, [rdi]; void *
0x14002296e  cmp     rcx, rdi
0x140022971  jz      short loc_14002298F
0x140022973  mov     rdx, [rcx+8]
0x140022977  mov     rax, [rcx]
0x14002297a  mov     [rdx], rax
0x14002297d  mov     [rax+8], rdx
0x140022981  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140022988  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14002298d  jmp     short loc_14002296B
0x14002298f  mov     rcx, [rdi+10h]; void *
0x140022993  mov     qword ptr [rdi+18h], 0
0x14002299b  test    rcx, rcx
0x14002299e  jz      short loc_1400229AC
0x1400229a0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400229a7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400229ac  lea     rax, ??_7SmartPtrRef@@6B@; const SmartPtrRef::`vftable'
0x1400229b3  mov     [rbx], rax
0x1400229b6  mov     rbx, [rsp+28h+arg_0]
0x1400229bb  add     rsp, 20h
0x1400229bf  pop     rdi
0x1400229c0  retn
```
