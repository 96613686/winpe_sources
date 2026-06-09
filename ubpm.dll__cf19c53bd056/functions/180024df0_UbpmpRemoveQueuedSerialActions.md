# UbpmpRemoveQueuedSerialActions

- ea: `0x180024df0`
- end: `0x180024ffd`
- name: `UbpmpRemoveQueuedSerialActions`
- size: `525`
- prototype: `__int64 __usercall@<rax>(UUID *Uuid1@<rcx>, UUID *@<rdx>, UUID *@<r8>, __int16)`
- caller_count: `4`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180003050`
- `0x180008030`
- `0x18000ae40`
- `0x180019a30`

## callees

- `0x180019d90`
- `0x18001e9f4`
- `0x180024df0`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x180024e23`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180024e23`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180024e6b`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180024e6b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180024e29`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180024e29`
- `RPCRT4!UuidEqual` at `0x180024f4b`
- `RPCRT4!UuidEqual` at `0x180024f7c`
- `RPCRT4!UuidEqual` at `0x180024f9f`
- `RPCRT4!UuidEqual` at `0x180024f4b`
- `RPCRT4!UuidEqual` at `0x180024f7c`
- `RPCRT4!UuidEqual` at `0x180024f9f`

## string_xrefs

- `0x180024fdc`: `Removed`
- `0x180024fce`: `Not removed`

## pseudocode

```c
__int64 __fastcall UbpmpRemoveQueuedSerialActions(UUID *Uuid1, UUID *a2, UUID *a3, void *a4, __int16 a5)
{
  unsigned __int8 v9; // bl
  DWORD CurrentThreadId; // eax
  _UNKNOWN **v11; // rdi
  __int64 v13; // rax
  _QWORD *v14; // rcx
  _QWORD *v15; // rax
  _UNKNOWN ***v16; // rax
  _QWORD *v17; // rcx
  _UNKNOWN ***v18; // r13
  const wchar_t *v19; // r9
  RPC_STATUS Status[14]; // [rsp+30h] [rbp-38h] BYREF

  Status[0] = 0;
  v9 = 0;
  RtlAcquireSRWLockExclusive(&g_QueuedSerialActionsLock);
  CurrentThreadId = GetCurrentThreadId();
  v11 = (_UNKNOWN **)g_leQueuedSerialActionsListHead;
  dword_18004CEA0 = CurrentThreadId;
  while ( v11 != &g_leQueuedSerialActionsListHead )
  {
    v18 = (_UNKNOWN ***)*v11;
    if ( Uuid1 )
    {
      if ( UuidEqual(Uuid1, (UUID *)v11 + 1, Status) )
      {
        if ( !a5 )
          goto LABEL_6;
        if ( a5 == *((_WORD *)v11 + 28) )
        {
          v16 = (_UNKNOWN ***)*v11;
          if ( *((_UNKNOWN ***)*v11 + 1) != v11 || (v17 = v11[1], (_UNKNOWN **)*v17 != v11) )
LABEL_7:
            __fastfail(3u);
          *v17 = v16;
          v16[1] = (_UNKNOWN **)v17;
          v11[1] = v11;
          *v11 = v11;
          UBPM_MIDL_user_free(v11);
          v9 = 1;
          break;
        }
      }
    }
    else if ( a2 )
    {
      if ( UuidEqual(a2, (UUID *)v11 + 2, Status) && (!a3 || !UuidEqual(a3, (UUID *)v11 + 1, Status)) )
      {
LABEL_6:
        v13 = (__int64)*v11;
        if ( *((_UNKNOWN ***)*v11 + 1) != v11 )
          goto LABEL_7;
        v14 = v11[1];
        if ( (_UNKNOWN **)*v14 != v11 )
          goto LABEL_7;
        *v14 = v13;
        *(_QWORD *)(v13 + 8) = v14;
LABEL_10:
        v11[1] = v11;
        *v11 = v11;
        UBPM_MIDL_user_free(v11);
        v9 = 1;
      }
    }
    else if ( a4 && a4 == v11[6] )
    {
      if ( v18[1] != v11 )
        goto LABEL_7;
      v15 = v11[1];
      if ( (_UNKNOWN **)*v15 != v11 )
        goto LABEL_7;
      *v15 = v18;
      v18[1] = (_UNKNOWN **)v15;
      goto LABEL_10;
    }
    v11 = (_UNKNOWN **)v18;
  }
  dword_18004CEA0 = 0;
  RtlReleaseSRWLockExclusive(&g_QueuedSerialActionsLock);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    v19 = L"Removed";
    if ( !v9 )
      v19 = L"Not removed";
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      95,
      (unsigned int)WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids,
      (_DWORD)v19,
      a5);
  }
  return v9;
}

```

## disassembly

```asm
0x180024df0  mov     [rsp+arg_8], rbx
0x180024df5  mov     [rsp+arg_10], rbp
0x180024dfa  push    rsi
0x180024dfb  push    rdi
0x180024dfc  push    r12
0x180024dfe  push    r14
0x180024e00  push    r15
0x180024e02  sub     rsp, 40h
0x180024e06  mov     r15, rcx
0x180024e09  mov     [rsp+68h+Status], 0
0x180024e11  lea     rcx, g_QueuedSerialActionsLock
0x180024e18  mov     rsi, r9
0x180024e1b  mov     rbp, r8
0x180024e1e  mov     r14, rdx
0x180024e21  xor     bl, bl
0x180024e23  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180024e29  call    cs:__imp_GetCurrentThreadId
0x180024e2f  mov     rdi, cs:g_leQueuedSerialActionsListHead
0x180024e36  movzx   r12d, [rsp+68h+arg_20]
0x180024e3f  mov     cs:dword_18004CEA0, eax
0x180024e45  lea     rax, g_leQueuedSerialActionsListHead
0x180024e4c  mov     [rsp+68h+arg_0], r13
0x180024e51  cmp     rdi, rax
0x180024e54  jnz     loc_180024F37
0x180024e5a  lea     rcx, g_QueuedSerialActionsLock
0x180024e61  mov     cs:dword_18004CEA0, 0
0x180024e6b  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180024e71  mov     rcx, cs:WPP_GLOBAL_Control
0x180024e78  lea     rax, WPP_GLOBAL_Control
0x180024e7f  cmp     rcx, rax
0x180024e82  jz      short loc_180024E8E
0x180024e84  test    byte ptr [rcx+1Ch], 20h
0x180024e88  jnz     loc_180024FCA
0x180024e8e  mov     r13, [rsp+68h+arg_0]
0x180024e93  movzx   eax, bl
0x180024e96  mov     rbx, [rsp+68h+arg_8]
0x180024e9b  mov     rbp, [rsp+68h+arg_10]
0x180024ea3  add     rsp, 40h
0x180024ea7  pop     r15
0x180024ea9  pop     r14
0x180024eab  pop     r12
0x180024ead  pop     rdi
0x180024eae  pop     rsi
0x180024eaf  retn
0x180024eb0  mov     rax, [rdi]
0x180024eb3  cmp     [rax+8], rdi
0x180024eb7  jz      short loc_180024EC0
0x180024eb9  mov     ecx, 3
0x180024ebe  int     29h; Win8: RtlFailFast(ecx)
0x180024ec0  mov     rcx, [rdi+8]
0x180024ec4  cmp     [rcx], rdi
0x180024ec7  jnz     short loc_180024EB9
0x180024ec9  mov     [rcx], rax
0x180024ecc  mov     [rax+8], rcx
0x180024ed0  mov     [rdi+8], rdi
0x180024ed4  mov     rcx, rdi
0x180024ed7  mov     [rdi], rdi
0x180024eda  call    UBPM_MIDL_user_free
0x180024edf  mov     bl, 1
0x180024ee1  lea     rax, g_leQueuedSerialActionsListHead
0x180024ee8  mov     rdi, r13
0x180024eeb  jmp     loc_180024E51
0x180024ef0  cmp     [r13+8], rdi
0x180024ef4  jnz     short loc_180024EB9
0x180024ef6  mov     rax, [rdi+8]
0x180024efa  cmp     [rax], rdi
0x180024efd  jnz     short loc_180024EB9
0x180024eff  mov     [rax], r13
0x180024f02  mov     [r13+8], rax
0x180024f06  jmp     short loc_180024ED0
0x180024f08  mov     rax, [rdi]
0x180024f0b  cmp     [rax+8], rdi
0x180024f0f  jnz     short loc_180024EB9
0x180024f11  mov     rcx, [rdi+8]
0x180024f15  cmp     [rcx], rdi
0x180024f18  jnz     short loc_180024EB9
0x180024f1a  mov     [rcx], rax
0x180024f1d  mov     [rax+8], rcx
0x180024f21  mov     rcx, rdi
0x180024f24  mov     [rdi+8], rdi
0x180024f28  mov     [rdi], rdi
0x180024f2b  call    UBPM_MIDL_user_free
0x180024f30  mov     bl, 1
0x180024f32  jmp     loc_180024E5A
0x180024f37  mov     r13, [rdi]
0x180024f3a  test    r15, r15
0x180024f3d  jz      short loc_180024F6B
0x180024f3f  lea     rdx, [rdi+10h]; Uuid2
0x180024f43  mov     rcx, r15; Uuid1
0x180024f46  lea     r8, [rsp+68h+Status]; Status
0x180024f4b  call    cs:__imp_UuidEqual
0x180024f51  test    eax, eax
0x180024f53  jz      short loc_180024EE1
0x180024f55  test    r12w, r12w
0x180024f59  jz      loc_180024EB0
0x180024f5f  cmp     r12w, [rdi+38h]
0x180024f64  jz      short loc_180024F08
0x180024f66  jmp     loc_180024EE1
0x180024f6b  test    r14, r14
0x180024f6e  jz      short loc_180024FB2
0x180024f70  lea     rdx, [rdi+20h]; Uuid2
0x180024f74  mov     rcx, r14; Uuid1
0x180024f77  lea     r8, [rsp+68h+Status]; Status
0x180024f7c  call    cs:__imp_UuidEqual
0x180024f82  test    eax, eax
0x180024f84  jz      loc_180024EE1
0x180024f8a  test    rbp, rbp
0x180024f8d  jz      loc_180024EB0
0x180024f93  lea     rdx, [rdi+10h]; Uuid2
0x180024f97  mov     rcx, rbp; Uuid1
0x180024f9a  lea     r8, [rsp+68h+Status]; Status
0x180024f9f  call    cs:__imp_UuidEqual
0x180024fa5  test    eax, eax
0x180024fa7  jnz     loc_180024EE1
0x180024fad  jmp     loc_180024EB0
0x180024fb2  test    rsi, rsi
0x180024fb5  jz      loc_180024EE8
0x180024fbb  cmp     rsi, [rdi+30h]
0x180024fbf  jnz     loc_180024EE8
0x180024fc5  jmp     loc_180024EF0
0x180024fca  mov     rcx, [rcx+10h]
0x180024fce  lea     rax, aNotRemoved; "Not removed"
0x180024fd5  test    bl, bl
0x180024fd7  mov     [rsp+68h+var_48], r12d
0x180024fdc  lea     r9, aRemoved; "Removed"
0x180024fe3  mov     edx, 5Fh ; '_'
0x180024fe8  cmovz   r9, rax
0x180024fec  lea     r8, WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids
0x180024ff3  call    WPP_SF_Sd
0x180024ff8  jmp     loc_180024E8E
```
