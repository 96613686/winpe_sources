# _CreateSharedHandleACL(int,ulong,void * *)

- ea: `0x1800048f4`
- end: `0x1800049b0`
- name: `?_CreateSharedHandleACL@@YAJHKPEAPEAX@Z`
- size: `188`
- prototype: `int(int, unsigned int, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180004860`

## callees

- `0x1800034dc`
- `0x180004610`
- `0x1800046c8`
- `0x1800048f4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000499c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000499c`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18000493c`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18000493c`

## pseudocode

```c
__int64 __fastcall _CreateSharedHandleACL(int a1, __int64 a2, void **a3)
{
  void **v3; // rdi
  int SharedHandleACLWorker; // ebx
  const unsigned __int16 *v6; // rcx
  __int64 v7; // rdx
  WINBOOL IsMember; // [rsp+38h] [rbp+10h] BYREF
  HLOCAL hMem; // [rsp+40h] [rbp+18h] BYREF

  IsMember = a2;
  *a3 = 0;
  v3 = a3;
  if ( a1 || !NtCurrentPeb()->SessionId )
  {
    v6 = L"AU";
    return (unsigned int)_CreateSharedHandleACLWorker(v6, a2, a3);
  }
  IsMember = 0;
  hMem = 0;
  if ( CheckTokenMembership(0, `_NotRunningAsSystem'::`2'::s_sidSystem, &IsMember) && !IsMember )
  {
    SharedHandleACLWorker = SHGetLogonID((LPWSTR *)&hMem);
    if ( SharedHandleACLWorker >= 0 )
    {
      SharedHandleACLWorker = _CreateSharedHandleACLWorker((const unsigned __int16 *)hMem, v7, v3);
      LocalFree(hMem);
      return (unsigned int)SharedHandleACLWorker;
    }
  }
  else
  {
    SharedHandleACLWorker = -2147467259;
  }
  if ( (unsigned int)_IsSetupRunningAndNotOOBE() )
  {
    a3 = v3;
    v6 = L"SY";
    return (unsigned int)_CreateSharedHandleACLWorker(v6, a2, a3);
  }
  return (unsigned int)SharedHandleACLWorker;
}

```

## disassembly

```asm
0x1800048f4  mov     [rsp+arg_0], rbx
0x1800048f9  mov     [rsp+IsMember], edx
0x1800048fd  push    rdi
0x1800048fe  sub     rsp, 20h
0x180004902  mov     qword ptr [r8], 0
0x180004909  mov     rdi, r8
0x18000490c  test    ecx, ecx
0x18000490e  jnz     short loc_180004968
0x180004910  mov     rax, gs:60h
0x180004919  cmp     [rax+2C0h], ecx
0x18000491f  jz      short loc_180004968
0x180004921  mov     [rsp+28h+IsMember], ecx
0x180004925  lea     r8, [rsp+28h+IsMember]; IsMember
0x18000492a  xor     ecx, ecx; TokenHandle
0x18000492c  mov     [rsp+28h+hMem], 0
0x180004935  lea     rdx, ?s_sidSystem@?1??_NotRunningAsSystem@@YAJXZ@4USINGLE_AUTHORITY_SID@?1??1@YAJXZ@B; SidToCheck
0x18000493c  call    cs:__imp_CheckTokenMembership
0x180004942  test    eax, eax
0x180004944  jz      short loc_18000494D
0x180004946  cmp     [rsp+28h+IsMember], 0
0x18000494b  jz      short loc_180004978
0x18000494d  mov     ebx, 80004005h
0x180004952  call    ?_IsSetupRunningAndNotOOBE@@YAHXZ; _IsSetupRunningAndNotOOBE(void)
0x180004957  test    eax, eax
0x180004959  jnz     short loc_1800049A4
0x18000495b  mov     eax, ebx
0x18000495d  mov     rbx, [rsp+28h+arg_0]
0x180004962  add     rsp, 20h
0x180004966  pop     rdi
0x180004967  retn
0x180004968  lea     rcx, aAu; "AU"
0x18000496f  call    ?_CreateSharedHandleACLWorker@@YAJPEBGKPEAPEAX@Z; _CreateSharedHandleACLWorker(ushort const *,ulong,void * *)
0x180004974  mov     ebx, eax
0x180004976  jmp     short loc_18000495B
0x180004978  lea     rcx, [rsp+28h+hMem]; StringSid
0x18000497d  call    ?SHGetLogonID@@YAJPEAPEAG@Z; SHGetLogonID(ushort * *)
0x180004982  mov     ebx, eax
0x180004984  test    eax, eax
0x180004986  js      short loc_180004952
0x180004988  mov     rcx, [rsp+28h+hMem]; unsigned __int16 *
0x18000498d  mov     r8, rdi; void **
0x180004990  call    ?_CreateSharedHandleACLWorker@@YAJPEBGKPEAPEAX@Z; _CreateSharedHandleACLWorker(ushort const *,ulong,void * *)
0x180004995  mov     rcx, [rsp+28h+hMem]; hMem
0x18000499a  mov     ebx, eax
0x18000499c  call    cs:__imp_LocalFree
0x1800049a2  jmp     short loc_18000495B
0x1800049a4  mov     r8, rdi
0x1800049a7  lea     rcx, aSy; "SY"
0x1800049ae  jmp     short loc_18000496F
```
