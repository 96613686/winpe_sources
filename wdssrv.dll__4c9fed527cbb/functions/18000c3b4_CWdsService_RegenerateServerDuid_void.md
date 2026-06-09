# CWdsService::RegenerateServerDuid(void)

- ea: `0x18000c3b4`
- end: `0x18000c487`
- name: `?RegenerateServerDuid@CWdsService@@AEAAKXZ`
- size: `211`
- prototype: `unsigned int __fastcall(CWdsService *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180009da4`
- `0x18000cc30`

## callees

- `0x180008c58`
- `0x18000c3b4`
- `0x18000e988`
- `0x18000f0dc`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18000c46b`
- `KERNEL32!LeaveCriticalSection` at `0x18000c46b`
- `KERNEL32!EnterCriticalSection` at `0x18000c3cd`
- `KERNEL32!EnterCriticalSection` at `0x18000c3cd`
- `WdsServerCommonLib!?WdsPrivateHpFree@@YAKPEAX@Z` at `0x18000c412`
- `WdsServerCommonLib!?WdsPrivateHpFree@@YAKPEAX@Z` at `0x18000c45c`
- `WdsServerCommonLib!?WdsPrivateHpFree@@YAKPEAX@Z` at `0x18000c412`
- `WdsServerCommonLib!?WdsPrivateHpFree@@YAKPEAX@Z` at `0x18000c45c`

## pseudocode

```c
__int64 __fastcall CWdsService::RegenerateServerDuid(struct _RTL_CRITICAL_SECTION *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rbp
  CWdsService *v3; // rcx
  unsigned int v4; // esi
  __int64 v5; // rdx
  __int64 v6; // r8
  void *v7; // rcx
  unsigned __int8 *v8; // rbx
  __int64 v9; // rdx
  __int64 v10; // r8
  unsigned int v12; // [rsp+40h] [rbp+8h] BYREF
  unsigned __int8 *v13; // [rsp+48h] [rbp+10h] BYREF

  v1 = this + 1683;
  EnterCriticalSection(this + 1683);
  v13 = 0;
  v12 = 0;
  v4 = CWdsService::GenerateServerDuid(v3, (u_short **)&v13, &v12);
  if ( (unsigned int)ElValidateWin32_0(v4, v5, v6, 0x5CCu) )
  {
    v8 = v13;
  }
  else
  {
    v7 = *(void **)&this[1684].LockCount;
    if ( v7 )
      WdsPrivateHpFree(v7);
    *(_QWORD *)&this[1684].LockCount = v13;
    v8 = 0;
    LODWORD(this[1684].DebugInfo) = v12;
    v4 = CWdsService::WriteServerDuid((CWdsService *)this);
    ElValidateWin32_0(v4, v9, v10, 0x5D4u);
  }
  if ( v8 )
    WdsPrivateHpFree(v8);
  LeaveCriticalSection(v1);
  return v4;
}

```

## disassembly

```asm
0x18000c3b4  mov     [rsp+arg_10], rbx
0x18000c3b9  push    rbp
0x18000c3ba  push    rsi
0x18000c3bb  push    rdi
0x18000c3bc  sub     rsp, 20h
0x18000c3c0  lea     rbp, [rcx+106F8h]
0x18000c3c7  mov     rdi, rcx
0x18000c3ca  mov     rcx, rbp; lpCriticalSection
0x18000c3cd  call    cs:__imp_EnterCriticalSection
0x18000c3d4  nop     dword ptr [rax+rax+00h]
0x18000c3d9  and     [rsp+38h+arg_8], 0
0x18000c3df  lea     r8, [rsp+38h+arg_0]; unsigned int *
0x18000c3e4  and     [rsp+38h+arg_0], 0
0x18000c3e9  lea     rdx, [rsp+38h+arg_8]; unsigned __int8 **
0x18000c3ee  call    ?GenerateServerDuid@CWdsService@@AEAAKPEAPEAEPEAK@Z; CWdsService::GenerateServerDuid(uchar * *,ulong *)
0x18000c3f3  mov     r9d, 5CCh
0x18000c3f9  mov     ecx, eax
0x18000c3fb  mov     esi, eax
0x18000c3fd  call    ElValidateWin32_0
0x18000c402  test    eax, eax
0x18000c404  jnz     short loc_18000C44F
0x18000c406  mov     rcx, [rdi+10728h]
0x18000c40d  test    rcx, rcx
0x18000c410  jz      short loc_18000C41E
0x18000c412  call    cs:__imp_?WdsPrivateHpFree@@YAKPEAX@Z; WdsPrivateHpFree(void *)
0x18000c419  nop     dword ptr [rax+rax+00h]
0x18000c41e  mov     rax, [rsp+38h+arg_8]
0x18000c423  mov     rcx, rdi; this
0x18000c426  mov     [rdi+10728h], rax
0x18000c42d  xor     ebx, ebx
0x18000c42f  mov     eax, [rsp+38h+arg_0]
0x18000c433  mov     [rdi+10720h], eax
0x18000c439  call    ?WriteServerDuid@CWdsService@@AEAAKXZ; CWdsService::WriteServerDuid(void)
0x18000c43e  mov     r9d, 5D4h
0x18000c444  mov     ecx, eax
0x18000c446  mov     esi, eax
0x18000c448  call    ElValidateWin32_0
0x18000c44d  jmp     short loc_18000C454
0x18000c44f  mov     rbx, [rsp+38h+arg_8]
0x18000c454  test    rbx, rbx
0x18000c457  jz      short loc_18000C468
0x18000c459  mov     rcx, rbx
0x18000c45c  call    cs:__imp_?WdsPrivateHpFree@@YAKPEAX@Z; WdsPrivateHpFree(void *)
0x18000c463  nop     dword ptr [rax+rax+00h]
0x18000c468  mov     rcx, rbp; lpCriticalSection
0x18000c46b  call    cs:__imp_LeaveCriticalSection
0x18000c472  nop     dword ptr [rax+rax+00h]
0x18000c477  mov     rbx, [rsp+38h+arg_10]
0x18000c47c  mov     eax, esi
0x18000c47e  add     rsp, 20h
0x18000c482  pop     rdi
0x18000c483  pop     rsi
0x18000c484  pop     rbp
0x18000c485  retn
```
