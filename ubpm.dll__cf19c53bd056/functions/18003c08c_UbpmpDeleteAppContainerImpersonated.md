# UbpmpDeleteAppContainerImpersonated

- ea: `0x18003c08c`
- end: `0x18003c11a`
- name: `UbpmpDeleteAppContainerImpersonated`
- size: `142`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180022054`
- `0x18003bfac`

## callees

- `0x18000a6e0`
- `0x180019d90`
- `0x18003c08c`

## import_xrefs

- `ntdll!RtlReleaseSRWLockExclusive` at `0x18003c0fb`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18003c0fb`
- `USERENV!DeleteAppContainerProfile` at `0x18003c0bc`
- `USERENV!DeleteAppContainerProfile` at `0x18003c0bc`

## pseudocode

```c
__int64 __fastcall UbpmpDeleteAppContainerImpersonated(__int64 a1)
{
  _QWORD *v1; // rbx
  __int64 result; // rax
  __int64 v4; // rdx
  _QWORD *v5; // rax

  v1 = *(_QWORD **)a1;
  result = _InterlockedExchangeAdd64((volatile signed __int64 *)(*(_QWORD *)a1 + 16LL), 0xFFFFFFFFFFFFFFFFuLL);
  if ( result == 1 )
  {
    UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE((struct _UBPM_SRWLOCK *)&g_ContainerProfilesListLock);
    DeleteAppContainerProfile(v1 + 4);
    v4 = *v1;
    if ( *(_QWORD **)(*v1 + 8LL) != v1 || (v5 = (_QWORD *)v1[1], (_QWORD *)*v5 != v1) )
      __fastfail(3u);
    *v5 = v4;
    *(_QWORD *)(v4 + 8) = v5;
    v1[1] = v1;
    *v1 = v1;
    UBPM_MIDL_user_free(v1);
    dword_18004CFA8 = 0;
    result = RtlReleaseSRWLockExclusive(&g_ContainerProfilesListLock);
    *(_QWORD *)a1 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x18003c08c  mov     [rsp+arg_0], rbx
0x18003c091  push    rdi
0x18003c092  sub     rsp, 20h
0x18003c096  mov     rbx, [rcx]
0x18003c099  mov     rdi, rcx
0x18003c09c  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003c0a0  lock xadd [rbx+10h], rax
0x18003c0a6  cmp     rax, 1
0x18003c0aa  jnz     short loc_18003C108
0x18003c0ac  lea     rcx, ?g_ContainerProfilesListLock@@3U_UBPM_SRWLOCK@@A; struct _UBPM_SRWLOCK *
0x18003c0b3  call    ?UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE@@YAXAEAU_UBPM_SRWLOCK@@@Z; UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE(_UBPM_SRWLOCK &)
0x18003c0b8  lea     rcx, [rbx+20h]
0x18003c0bc  call    cs:__imp_DeleteAppContainerProfile
0x18003c0c2  mov     rdx, [rbx]
0x18003c0c5  cmp     [rdx+8], rbx
0x18003c0c9  jnz     short loc_18003C113
0x18003c0cb  mov     rax, [rbx+8]
0x18003c0cf  cmp     [rax], rbx
0x18003c0d2  jnz     short loc_18003C113
0x18003c0d4  mov     [rax], rdx
0x18003c0d7  mov     rcx, rbx
0x18003c0da  mov     [rdx+8], rax
0x18003c0de  mov     [rbx+8], rbx
0x18003c0e2  mov     [rbx], rbx
0x18003c0e5  call    UBPM_MIDL_user_free
0x18003c0ea  lea     rcx, ?g_ContainerProfilesListLock@@3U_UBPM_SRWLOCK@@A; _UBPM_SRWLOCK g_ContainerProfilesListLock
0x18003c0f1  mov     cs:dword_18004CFA8, 0
0x18003c0fb  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18003c101  mov     qword ptr [rdi], 0
0x18003c108  mov     rbx, [rsp+28h+arg_0]
0x18003c10d  add     rsp, 20h
0x18003c111  pop     rdi
0x18003c112  retn
0x18003c113  mov     ecx, 3
0x18003c118  int     29h; Win8: RtlFailFast(ecx)
```
