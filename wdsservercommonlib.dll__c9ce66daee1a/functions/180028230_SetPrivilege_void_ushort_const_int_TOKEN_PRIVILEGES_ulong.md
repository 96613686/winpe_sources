# SetPrivilege(void *,ushort const *,int,_TOKEN_PRIVILEGES *,ulong *)

- ea: `0x180028230`
- end: `0x180028322`
- name: `?SetPrivilege@@YAKPEAXPEBGHPEAU_TOKEN_PRIVILEGES@@PEAK@Z`
- size: `242`
- prototype: `unsigned int __usercall@<eax>(HANDLE TokenHandle@<rcx>, const unsigned __int16 *@<rdx>, int@<r8d>, struct _TOKEN_PRIVILEGES *@<r9>, unsigned int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation`

## callees

- `0x180028230`
- `0x1800288c0`
- `0x18002f3e0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180028279`
- `KERNEL32!GetLastError` at `0x1800282e2`
- `KERNEL32!GetLastError` at `0x180028279`
- `KERNEL32!GetLastError` at `0x1800282e2`
- `ADVAPI32!AdjustTokenPrivileges` at `0x1800282d2`
- `ADVAPI32!AdjustTokenPrivileges` at `0x1800282d2`
- `ADVAPI32!LookupPrivilegeValueW` at `0x180028269`
- `ADVAPI32!LookupPrivilegeValueW` at `0x180028269`

## pseudocode

```c
__int64 __fastcall SetPrivilege(
        HANDLE TokenHandle,
        const unsigned __int16 *a2,
        int a3,
        struct _TOKEN_PRIVILEGES *a4,
        unsigned int *ReturnLength)
{
  unsigned int v7; // ebx
  DWORD v9; // eax
  __int64 v10; // rdx
  __int64 v11; // r8
  DWORD LastError; // eax
  __int64 v13; // rdx
  __int64 v14; // r8
  unsigned int v15; // eax
  struct _LUID Luid; // [rsp+30h] [rbp-48h] BYREF
  struct _TOKEN_PRIVILEGES NewState; // [rsp+38h] [rbp-40h] BYREF

  v7 = 0;
  Luid = 0;
  if ( LookupPrivilegeValueW(0, a2, &Luid) )
  {
    NewState.Privileges[0].Luid = Luid;
    NewState.PrivilegeCount = 1;
    NewState.Privileges[0].Attributes = a3 != 0 ? 2 : 0;
    if ( !AdjustTokenPrivileges(TokenHandle, 0, &NewState, 0x10u, a4, ReturnLength) )
    {
      LastError = GetLastError();
      v15 = ElValidateWin32_19(LastError, v13, v14, 88);
      if ( !v15 )
        return 31;
      return v15;
    }
  }
  else
  {
    v9 = GetLastError();
    v7 = ElValidateWin32_19(v9, v10, v11, 70);
    if ( !v7 )
      return 31;
  }
  return v7;
}

```

## disassembly

```asm
0x180028230  push    rbx
0x180028232  push    rbp
0x180028233  push    rsi
0x180028234  push    rdi
0x180028235  push    r14
0x180028237  sub     rsp, 50h
0x18002823b  mov     rax, cs:__security_cookie
0x180028242  xor     rax, rsp
0x180028245  mov     [rsp+78h+var_30], rax
0x18002824a  mov     r14, [rsp+78h+arg_20]
0x180028252  mov     edi, r8d
0x180028255  mov     rsi, rcx
0x180028258  lea     r8, [rsp+78h+Luid]; lpLuid
0x18002825d  xor     ebx, ebx
0x18002825f  xor     ecx, ecx; lpSystemName
0x180028261  and     qword ptr [rsp+78h+Luid.LowPart], rbx
0x180028266  mov     rbp, r9
0x180028269  call    cs:__imp_LookupPrivilegeValueW
0x180028270  nop     dword ptr [rax+rax+00h]
0x180028275  test    eax, eax
0x180028277  jnz     short loc_18002829B
0x180028279  call    cs:__imp_GetLastError
0x180028280  nop     dword ptr [rax+rax+00h]
0x180028285  mov     ecx, eax
0x180028287  lea     r9d, [rbx+46h]
0x18002828b  call    ElValidateWin32_19
0x180028290  mov     ebx, eax
0x180028292  test    eax, eax
0x180028294  jnz     short loc_180028307
0x180028296  lea     ebx, [rax+1Fh]
0x180028299  jmp     short loc_180028307
0x18002829b  mov     rax, qword ptr [rsp+78h+Luid.LowPart]
0x1800282a0  lea     r8, [rsp+78h+NewState]; NewState
0x1800282a5  mov     qword ptr [rsp+78h+NewState.Privileges.Luid.LowPart], rax
0x1800282aa  neg     edi
0x1800282ac  mov     [rsp+78h+ReturnLength], r14; ReturnLength
0x1800282b1  mov     r9d, 10h; BufferLength
0x1800282b7  sbb     eax, eax
0x1800282b9  mov     [rsp+78h+NewState.PrivilegeCount], 1
0x1800282c1  and     eax, 2
0x1800282c4  mov     [rsp+78h+PreviousState], rbp; PreviousState
0x1800282c9  xor     edx, edx; DisableAllPrivileges
0x1800282cb  mov     [rsp+78h+NewState.Privileges.Attributes], eax
0x1800282cf  mov     rcx, rsi; TokenHandle
0x1800282d2  call    cs:__imp_AdjustTokenPrivileges
0x1800282d9  nop     dword ptr [rax+rax+00h]
0x1800282de  test    eax, eax
0x1800282e0  jnz     short loc_180028307
0x1800282e2  call    cs:__imp_GetLastError
0x1800282e9  nop     dword ptr [rax+rax+00h]
0x1800282ee  mov     ecx, eax
0x1800282f0  mov     r9d, 58h ; 'X'
0x1800282f6  call    ElValidateWin32_19
0x1800282fb  mov     ebx, 1Fh
0x180028300  test    eax, eax
0x180028302  cmovz   eax, ebx
0x180028305  mov     ebx, eax
0x180028307  mov     eax, ebx
0x180028309  mov     rcx, [rsp+78h+var_30]
0x18002830e  xor     rcx, rsp; StackCookie
0x180028311  call    __security_check_cookie
0x180028316  add     rsp, 50h
0x18002831a  pop     r14
0x18002831c  pop     rdi
0x18002831d  pop     rsi
0x18002831e  pop     rbp
0x18002831f  pop     rbx
0x180028320  retn
```
