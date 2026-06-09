# HTTP2CurrentUserTable::ReferenceUser(void *)

- ea: `0x180016bc4`
- end: `0x180016cd2`
- name: `?ReferenceUser@HTTP2CurrentUserTable@@QEAAHPEAX@Z`
- size: `270`
- prototype: `int(HTTP2CurrentUserTable *__hidden this, void *)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180002770`
- `0x180002874`

## callees

- `0x1800033d8`
- `0x18000ce68`
- `0x180016bc4`
- `0x18001ea20`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x180016cb6`
- `ntdll!RtlLeaveCriticalSection` at `0x180016cb6`
- `ntdll!RtlEnterCriticalSection` at `0x180016c04`
- `ntdll!RtlEnterCriticalSection` at `0x180016c04`
- `ADVAPI32!EqualSid` at `0x180016c26`
- `ADVAPI32!EqualSid` at `0x180016c26`
- `ADVAPI32!CopySid` at `0x180016c73`
- `ADVAPI32!CopySid` at `0x180016c73`
- `ADVAPI32!GetLengthSid` at `0x180016c53`
- `ADVAPI32!GetLengthSid` at `0x180016c53`
- `RPCRT4!I_RpcFree` at `0x180016c80`
- `RPCRT4!I_RpcFree` at `0x180016c80`
- `RPCRT4!I_RpcAllocate` at `0x180016c3b`
- `RPCRT4!I_RpcAllocate` at `0x180016c5d`
- `RPCRT4!I_RpcAllocate` at `0x180016c3b`
- `RPCRT4!I_RpcAllocate` at `0x180016c5d`

## pseudocode

```c
__int64 __fastcall HTTP2CurrentUserTable::ReferenceUser(HTTP2CurrentUserTable *this, void *a2)
{
  struct HTTP2CurrentUserTable *v2; // rdi
  __int64 v4; // rbx
  unsigned int v5; // eax
  unsigned int v6; // r15d
  __int64 v7; // r14
  __int64 v8; // rsi
  __int64 v9; // rbx
  void **v10; // rax
  void **v11; // rbx
  DWORD LengthSid; // esi
  void *v13; // rax
  unsigned int v14; // edx

  v2 = g_HTTP2CurrentUserTable;
  v4 = *(_QWORD *)g_HTTP2CurrentUserTable;
  v5 = HTTP2CurrentUserTable::HashSid(this, a2);
  if ( !*(_QWORD *)v2 )
    return 0;
  v6 = 0;
  v7 = v4 + 88LL * (v5 % *((_DWORD *)v2 + 2));
  RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)(v7 + 48));
  v8 = 0;
  while ( (unsigned int)v8 < *(_DWORD *)(v7 + 8) )
  {
    v9 = *(_QWORD *)(*(_QWORD *)v7 + 8 * v8);
    v8 = (unsigned int)(v8 + 1);
    if ( v9 && EqualSid(*(PSID *)v9, a2) )
    {
      _InterlockedIncrement((volatile signed __int32 *)(v9 + 8));
      goto LABEL_15;
    }
  }
  v10 = (void **)I_RpcAllocate(0x10u);
  v11 = v10;
  if ( v10 )
  {
    *((_DWORD *)v10 + 2) = 1;
    LengthSid = GetLengthSid(a2);
    v13 = I_RpcAllocate(LengthSid);
    *v11 = v13;
    if ( v13 && !CopySid(LengthSid, v13, a2) )
    {
      I_RpcFree(*v11);
      *v11 = 0;
    }
    if ( !*v11 || SIMPLE_DICT::Insert((SIMPLE_DICT *)v7, v11) == -1 )
    {
      HTTP2CurrentUserEntry::`scalar deleting destructor'((HTTP2CurrentUserEntry *)v11, v14);
    }
    else
    {
      _InterlockedIncrement((volatile signed __int32 *)v2 + 3);
      v6 = 1;
    }
  }
LABEL_15:
  RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)(v7 + 48));
  return v6;
}

```

## disassembly

```asm
0x180016bc4  push    rbx
0x180016bc6  push    rbp
0x180016bc7  push    rsi
0x180016bc8  push    rdi
0x180016bc9  push    r12
0x180016bcb  push    r14
0x180016bcd  push    r15
0x180016bcf  sub     rsp, 20h
0x180016bd3  mov     rdi, cs:?g_HTTP2CurrentUserTable@@3PEAVHTTP2CurrentUserTable@@EA; HTTP2CurrentUserTable * g_HTTP2CurrentUserTable
0x180016bda  mov     rbp, rdx
0x180016bdd  mov     rbx, [rdi]
0x180016be0  call    ?HashSid@HTTP2CurrentUserTable@@IEAAKPEAX@Z; HTTP2CurrentUserTable::HashSid(void *)
0x180016be5  cmp     qword ptr [rdi], 0
0x180016be9  jz      loc_180016CC1
0x180016bef  xor     edx, edx
0x180016bf1  xor     r15d, r15d
0x180016bf4  div     dword ptr [rdi+8]
0x180016bf7  mov     ecx, edx
0x180016bf9  imul    r14, rcx, 58h ; 'X'
0x180016bfd  add     r14, rbx
0x180016c00  lea     rcx, [r14+30h]; CriticalSection
0x180016c04  call    cs:__imp_RtlEnterCriticalSection
0x180016c0a  xor     esi, esi
0x180016c0c  cmp     esi, [r14+8]
0x180016c10  jnb     short loc_180016C36
0x180016c12  mov     rax, [r14]
0x180016c15  mov     rbx, [rax+rsi*8]
0x180016c19  inc     esi
0x180016c1b  test    rbx, rbx
0x180016c1e  jz      short loc_180016C0C
0x180016c20  mov     rcx, [rbx]; pSid1
0x180016c23  mov     rdx, rbp; pSid2
0x180016c26  call    cs:__imp_EqualSid
0x180016c2c  test    eax, eax
0x180016c2e  jz      short loc_180016C0C
0x180016c30  lock inc dword ptr [rbx+8]
0x180016c34  jmp     short loc_180016CB2
0x180016c36  mov     ecx, 10h; Size
0x180016c3b  call    cs:__imp_I_RpcAllocate
0x180016c41  mov     rbx, rax
0x180016c44  test    rax, rax
0x180016c47  jz      short loc_180016CB2
0x180016c49  mov     rcx, rbp; pSid
0x180016c4c  mov     dword ptr [rax+8], 1
0x180016c53  call    cs:__imp_GetLengthSid
0x180016c59  mov     ecx, eax; Size
0x180016c5b  mov     esi, eax
0x180016c5d  call    cs:__imp_I_RpcAllocate
0x180016c63  mov     [rbx], rax
0x180016c66  test    rax, rax
0x180016c69  jz      short loc_180016C89
0x180016c6b  mov     r8, rbp; pSourceSid
0x180016c6e  mov     rdx, rax; pDestinationSid
0x180016c71  mov     ecx, esi; nDestinationSidLength
0x180016c73  call    cs:__imp_CopySid
0x180016c79  test    eax, eax
0x180016c7b  jnz     short loc_180016C89
0x180016c7d  mov     rcx, [rbx]; Object
0x180016c80  call    cs:__imp_I_RpcFree
0x180016c86  mov     [rbx], r15
0x180016c89  cmp     [rbx], r15
0x180016c8c  jz      short loc_180016CAA
0x180016c8e  mov     rdx, rbx; void *
0x180016c91  mov     rcx, r14; this
0x180016c94  call    ?Insert@SIMPLE_DICT@@QEAAIPEAX@Z; SIMPLE_DICT::Insert(void *)
0x180016c99  cmp     eax, 0FFFFFFFFh
0x180016c9c  jz      short loc_180016CAA
0x180016c9e  lock inc dword ptr [rdi+0Ch]
0x180016ca2  mov     r15d, 1
0x180016ca8  jmp     short loc_180016CB2
0x180016caa  mov     rcx, rbx; this
0x180016cad  call    ??_GHTTP2CurrentUserEntry@@QEAAPEAXI@Z; HTTP2CurrentUserEntry::`scalar deleting destructor'(uint)
0x180016cb2  lea     rcx, [r14+30h]; CriticalSection
0x180016cb6  call    cs:__imp_RtlLeaveCriticalSection
0x180016cbc  mov     eax, r15d
0x180016cbf  jmp     short loc_180016CC3
0x180016cc1  xor     eax, eax
0x180016cc3  add     rsp, 20h
0x180016cc7  pop     r15
0x180016cc9  pop     r14
0x180016ccb  pop     r12
0x180016ccd  pop     rdi
0x180016cce  pop     rsi
0x180016ccf  pop     rbp
0x180016cd0  pop     rbx
0x180016cd1  retn
```
