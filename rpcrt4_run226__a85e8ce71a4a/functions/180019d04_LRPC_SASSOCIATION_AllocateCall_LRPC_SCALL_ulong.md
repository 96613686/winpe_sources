# LRPC_SASSOCIATION::AllocateCall(LRPC_SCALL * *,ulong)

- ea: `0x180019d04`
- end: `0x180019ea4`
- name: `?AllocateCall@LRPC_SASSOCIATION@@AEAAJPEAPEAVLRPC_SCALL@@K@Z`
- size: `416`
- prototype: `__int64 __fastcall(LRPC_SASSOCIATION *__hidden this, struct LRPC_SCALL **, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180019720`

## callees

- `0x180016bfc`
- `0x180017ec0`
- `0x180018abc`
- `0x180019d04`
- `0x18001b00c`
- `0x180021e70`
- `0x1800d2010`

## import_xrefs

- `ntdll!EtwEventActivityIdControl` at `0x180019e2e`
- `ntdll!EtwEventActivityIdControl` at `0x180019e2e`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x180019d43`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x180019d43`

## pseudocode

```c
__int64 __fastcall LRPC_SASSOCIATION::AllocateCall(union _SLIST_HEADER *this, struct LRPC_SCALL **a2, unsigned int a3)
{
  signed __int64 Alignment; // rbx
  PSLIST_ENTRY v7; // rax
  bool v8; // zf
  unsigned int v10; // edi
  LRPC_SCALL *v11; // rax
  LRPC_SCALL *v12; // rax
  struct LRPC_SCALL *v13; // rbx
  LRPC_SCALL *v14; // rax
  int v15; // [rsp+40h] [rbp+8h] BYREF

  Alignment = this[25].Alignment;
  if ( !Alignment || Alignment != _InterlockedCompareExchange64((volatile signed __int64 *)&this[25], 0, Alignment) )
  {
    v7 = InterlockedPopEntrySList(this + 26);
    if ( !v7 || (Alignment = (signed __int64)&v7[-37], v7 == (PSLIST_ENTRY)592) )
    {
      v10 = 0;
      v15 = 0;
      if ( gfRPCVerifierEnabled )
      {
        v14 = (LRPC_SCALL *)AllocWrapper(0x290u);
        v13 = v14;
        if ( v14 )
        {
          LRPC_SCALL::LRPC_SCALL(v14, &v15, (struct LRPC_SASSOCIATION *)this, a3);
          v10 = v15;
          *(_QWORD *)v13 = &LRPC_SCALL_AVRF::`vftable';
LABEL_12:
          if ( v10 )
          {
            (*(void (__fastcall **)(struct LRPC_SCALL *, __int64))(*(_QWORD *)v13 + 8LL))(v13, 1);
          }
          else
          {
            *a2 = v13;
            CALL::CreateAndSetActivityId(v13);
          }
          return v10;
        }
        v13 = 0;
      }
      else
      {
        v11 = (LRPC_SCALL *)AllocWrapper(0x290u);
        if ( !v11 )
          return 14;
        v12 = LRPC_SCALL::LRPC_SCALL(v11, &v15, (struct LRPC_SASSOCIATION *)this, a3);
        v10 = v15;
        v13 = v12;
      }
      if ( v13 )
        goto LABEL_12;
      return 14;
    }
  }
  *(_QWORD *)(Alignment + 24) = 0;
  *(_QWORD *)(Alignment + 40) = 0;
  *(_QWORD *)(Alignment + 312) = 0;
  *(_DWORD *)(Alignment + 532) = a3;
  *(_QWORD *)(Alignment + 592) = 0;
  REFERENCED_OBJECT::SingleThreadedAddReference((REFERENCED_OBJECT *)Alignment);
  v8 = dword_1800F9624 == 0;
  *a2 = (struct LRPC_SCALL *)Alignment;
  if ( v8 )
  {
    *(GUID *)(Alignment + 208) = g_NullActivityId;
  }
  else
  {
    if ( UuidCreate((UUID *)(Alignment + 208)) )
      *(GUID *)(Alignment + 208) = g_NullActivityId;
    EtwEventActivityIdControl(2, Alignment + 208);
  }
  return 0;
}

```

## disassembly

```asm
0x180019d04  mov     [rsp+arg_8], rbx
0x180019d09  mov     [rsp+arg_10], rbp
0x180019d0e  push    rsi
0x180019d0f  push    rdi
0x180019d10  push    r14
0x180019d12  sub     rsp, 20h
0x180019d16  mov     rbx, [rcx+190h]
0x180019d1d  mov     ebp, r8d
0x180019d20  mov     r14, rdx
0x180019d23  mov     rsi, rcx
0x180019d26  test    rbx, rbx
0x180019d29  jz      short loc_180019D3C
0x180019d2b  xor     r9d, r9d
0x180019d2e  mov     rax, rbx
0x180019d31  lock cmpxchg [rcx+190h], r9
0x180019d3a  jz      short loc_180019D5A
0x180019d3c  add     rcx, 1A0h; ListHead
0x180019d43  call    cs:__imp_InterlockedPopEntrySList
0x180019d49  test    rax, rax
0x180019d4c  jz      short loc_180019DBF
0x180019d4e  lea     rbx, [rax-250h]
0x180019d55  test    rbx, rbx
0x180019d58  jz      short loc_180019DBF
0x180019d5a  mov     qword ptr [rbx+18h], 0
0x180019d62  mov     rcx, rbx; this
0x180019d65  mov     qword ptr [rbx+28h], 0
0x180019d6d  mov     qword ptr [rbx+138h], 0
0x180019d78  mov     [rbx+214h], ebp
0x180019d7e  mov     qword ptr [rbx+250h], 0
0x180019d89  nop
0x180019d8a  call    ?SingleThreadedAddReference@REFERENCED_OBJECT@@QEAAXXZ; REFERENCED_OBJECT::SingleThreadedAddReference(void)
0x180019d8f  cmp     cs:dword_1800F9624, 0
0x180019d96  mov     [r14], rbx
0x180019d99  jnz     short loc_180019E12
0x180019d9b  movups  xmm0, xmmword ptr cs:?g_NullActivityId@@3U_GUID@@B.Data1; _GUID const g_NullActivityId ...
0x180019da2  movdqu  xmmword ptr [rbx+0D0h], xmm0
0x180019daa  xor     eax, eax
0x180019dac  mov     rbx, [rsp+38h+arg_8]
0x180019db1  mov     rbp, [rsp+38h+arg_10]
0x180019db6  add     rsp, 20h
0x180019dba  pop     r14
0x180019dbc  pop     rdi
0x180019dbd  pop     rsi
0x180019dbe  retn
0x180019dbf  xor     edi, edi
0x180019dc1  mov     ecx, 290h; dwBytes
0x180019dc6  cmp     cs:?gfRPCVerifierEnabled@@3HA, edi; int gfRPCVerifierEnabled
0x180019dcc  mov     [rsp+38h+arg_0], edi
0x180019dd0  jnz     short loc_180019E51
0x180019dd2  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x180019dd7  test    rax, rax
0x180019dda  jz      short loc_180019E39
0x180019ddc  mov     r9d, ebp; unsigned int
0x180019ddf  lea     rdx, [rsp+38h+arg_0]; int *
0x180019de4  mov     r8, rsi; struct LRPC_SASSOCIATION *
0x180019de7  mov     rcx, rax; this
0x180019dea  call    ??0LRPC_SCALL@@QEAA@PEAJPEAVLRPC_SASSOCIATION@@K@Z; LRPC_SCALL::LRPC_SCALL(long *,LRPC_SASSOCIATION *,ulong)
0x180019def  mov     edi, [rsp+38h+arg_0]
0x180019df3  mov     rbx, rax
0x180019df6  test    rbx, rbx
0x180019df9  jz      short loc_180019E39
0x180019dfb  test    edi, edi
0x180019dfd  jnz     loc_180019E84
0x180019e03  mov     rcx, rbx; this
0x180019e06  mov     [r14], rbx
0x180019e09  call    ?CreateAndSetActivityId@CALL@@QEAAXXZ; CALL::CreateAndSetActivityId(void)
0x180019e0e  mov     eax, edi
0x180019e10  jmp     short loc_180019DAC
0x180019e12  lea     rcx, [rbx+0D0h]; Uuid
0x180019e19  call    UuidCreate
0x180019e1e  test    eax, eax
0x180019e20  jnz     short loc_180019E40
0x180019e22  lea     rdx, [rbx+0D0h]
0x180019e29  mov     ecx, 2
0x180019e2e  call    cs:__imp_EtwEventActivityIdControl
0x180019e34  jmp     loc_180019DAA
0x180019e39  mov     edi, 0Eh
0x180019e3e  jmp     short loc_180019E0E
0x180019e40  movups  xmm0, xmmword ptr cs:?g_NullActivityId@@3U_GUID@@B.Data1; _GUID const g_NullActivityId ...
0x180019e47  movdqu  xmmword ptr [rbx+0D0h], xmm0
0x180019e4f  jmp     short loc_180019E22
0x180019e51  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x180019e56  mov     rbx, rax
0x180019e59  test    rax, rax
0x180019e5c  jz      short loc_180019E9D
0x180019e5e  mov     r9d, ebp; unsigned int
0x180019e61  lea     rdx, [rsp+38h+arg_0]; int *
0x180019e66  mov     r8, rsi; struct LRPC_SASSOCIATION *
0x180019e69  mov     rcx, rax; this
0x180019e6c  call    ??0LRPC_SCALL@@QEAA@PEAJPEAVLRPC_SASSOCIATION@@K@Z; LRPC_SCALL::LRPC_SCALL(long *,LRPC_SASSOCIATION *,ulong)
0x180019e71  mov     edi, [rsp+38h+arg_0]
0x180019e75  lea     rax, ??_7LRPC_SCALL_AVRF@@6B@; const LRPC_SCALL_AVRF::`vftable'
0x180019e7c  mov     [rbx], rax
0x180019e7f  jmp     loc_180019DFB
0x180019e84  mov     rcx, [rbx]
0x180019e87  mov     edx, 1
0x180019e8c  mov     rax, [rcx+8]
0x180019e90  mov     rcx, rbx
0x180019e93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019e98  jmp     loc_180019E0E
0x180019e9d  xor     ebx, ebx
0x180019e9f  jmp     loc_180019DF6
```
