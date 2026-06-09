# CPool<RpcRequest>::GetObjectW(int)

- ea: `0x180004054`
- end: `0x1800040fd`
- name: `?GetObjectW@?$CPool@URpcRequest@@@@QEAAPEAURpcRequest@@H@Z`
- size: `169`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800049b4`

## callees

- `0x18000195c`
- `0x180003d70`
- `0x180004054`

## import_xrefs

- `KERNEL32!InterlockedPopEntrySList` at `0x180004063`
- `KERNEL32!InterlockedPopEntrySList` at `0x180004063`

## pseudocode

```c
PSLIST_ENTRY __fastcall CPool<RpcRequest>::GetObjectW(__int64 a1)
{
  PSLIST_ENTRY v2; // rbx
  PSLIST_ENTRY v3; // rax
  struct _SLIST_ENTRY *v4; // rax

  v2 = 0;
  v3 = InterlockedPopEntrySList((PSLIST_HEADER)a1);
  if ( v3 )
  {
    _InterlockedDecrement((volatile signed __int32 *)(a1 + 16));
    v2 = v3 - 143;
  }
  if ( !v2 )
  {
    v4 = (struct _SLIST_ENTRY *)operator new(0x900u, (const struct std::nothrow_t *)&std::nothrow);
    v2 = v4;
    if ( !v4 )
      return 0;
    *((_QWORD *)&v4[138].Next + 1) = 0;
    v4[139].Next = 0;
    *((_DWORD *)&v4[139].Next + 3) = 0;
    *((_QWORD *)&v4[141].Next + 1) = 0;
    v4[142].Next = 0;
    v4[138].Next = 0;
    RpcRequest::Cleanup((RpcRequest *)v4);
  }
  _InterlockedExchange((volatile __int32 *)&v2[140].Next + 2, 2);
  v2[141].Next = (struct _SLIST_ENTRY *)a1;
  _InterlockedIncrement((volatile signed __int32 *)(a1 + 32));
  return v2;
}

```

## disassembly

```asm
0x180004054  mov     [rsp+arg_0], rbx
0x180004059  push    rdi
0x18000405a  sub     rsp, 20h
0x18000405e  mov     rdi, rcx
0x180004061  xor     ebx, ebx
0x180004063  call    cs:__imp_InterlockedPopEntrySList
0x18000406a  nop     dword ptr [rax+rax+00h]
0x18000406f  test    rax, rax
0x180004072  jz      short loc_18000407F
0x180004074  lock dec dword ptr [rdi+10h]
0x180004078  lea     rbx, [rax-8F0h]
0x18000407f  test    rbx, rbx
0x180004082  jnz     short loc_1800040D4
0x180004084  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000408b  mov     ecx, 900h; unsigned __int64
0x180004090  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180004095  mov     rbx, rax
0x180004098  test    rax, rax
0x18000409b  jz      short loc_1800040F9
0x18000409d  and     qword ptr [rax+8A8h], 0
0x1800040a5  mov     rcx, rax; this
0x1800040a8  and     qword ptr [rax+8B0h], 0
0x1800040b0  and     dword ptr [rax+8BCh], 0
0x1800040b7  and     qword ptr [rax+8D8h], 0
0x1800040bf  and     qword ptr [rax+8E0h], 0
0x1800040c7  and     qword ptr [rax+8A0h], 0
0x1800040cf  call    ?Cleanup@RpcRequest@@QEAAXXZ; RpcRequest::Cleanup(void)
0x1800040d4  mov     ecx, 2
0x1800040d9  xchg    ecx, [rbx+8C8h]
0x1800040df  mov     [rbx+8D0h], rdi
0x1800040e6  lock inc dword ptr [rdi+20h]
0x1800040ea  mov     rax, rbx
0x1800040ed  mov     rbx, [rsp+28h+arg_0]
0x1800040f2  add     rsp, 20h
0x1800040f6  pop     rdi
0x1800040f7  retn
0x1800040f9  xor     ebx, ebx
0x1800040fb  jmp     short loc_1800040EA
```
