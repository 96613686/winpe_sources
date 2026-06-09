# EnablePrivilege(_TOKEN_PRIVILEGES * *,ulong *,long)

- ea: `0x18001d07c`
- end: `0x18001d173`
- name: `?EnablePrivilege@@YAHPEAPEAU_TOKEN_PRIVILEGES@@PEAKJ@Z`
- size: `247`
- prototype: `int(struct _TOKEN_PRIVILEGES **, unsigned int *, int)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18001d200`
- `0x18001d240`

## callees

- `0x18001d07c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001d0c5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001d0fc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001d0c5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001d0fc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d13a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d153`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d13a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d153`
- `ntdll!NtOpenProcessToken` at `0x18001d0a2`
- `ntdll!NtOpenProcessToken` at `0x18001d0a2`
- `ntdll!NtAdjustPrivilegesToken` at `0x18001d127`
- `ntdll!NtAdjustPrivilegesToken` at `0x18001d127`
- `ntdll!NtClose` at `0x18001d161`
- `ntdll!NtClose` at `0x18001d161`

## pseudocode

```c
__int64 __fastcall EnablePrivilege(HLOCAL *a1, unsigned int *a2, int a3)
{
  unsigned int v3; // edi
  __int64 v4; // rbx
  char *v7; // rax
  struct _TOKEN_PRIVILEGES *v8; // rbx
  struct _TOKEN_PRIVILEGES *PreviousState; // rax
  __int64 v11; // [rsp+30h] [rbp-38h]
  HANDLE TokenHandle; // [rsp+88h] [rbp+20h] BYREF

  v3 = 0;
  v4 = a3;
  TokenHandle = 0;
  if ( NtOpenProcessToken((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0x28u, &TokenHandle) >= 0 )
  {
    v11 = v4;
    v7 = (char *)LocalAlloc(0x40u, 0x64u);
    v8 = (struct _TOKEN_PRIVILEGES *)v7;
    if ( v7 )
    {
      v3 = 1;
      *(_DWORD *)v7 = 1;
      *(_QWORD *)(v7 + 4) = v11;
      *((_DWORD *)v7 + 3) = 2;
      PreviousState = (struct _TOKEN_PRIVILEGES *)*a1;
      if ( !*a1 && (PreviousState = (struct _TOKEN_PRIVILEGES *)LocalAlloc(0x40u, 0x64u), (*a1 = PreviousState) == 0)
        || NtAdjustPrivilegesToken(TokenHandle, 0, v8, 0x64u, PreviousState, a2)
        || *a2 > 0x64 )
      {
        LocalFree(*a1);
        *a1 = 0;
        v3 = 0;
        *a2 = 0;
      }
      LocalFree(v8);
    }
    NtClose(TokenHandle);
  }
  return v3;
}

```

## disassembly

```asm
0x18001d07c  mov     rax, rsp
0x18001d07f  push    rbx
0x18001d080  push    rsi
0x18001d081  push    rdi
0x18001d082  push    r14
0x18001d084  sub     rsp, 48h
0x18001d088  xor     edi, edi
0x18001d08a  movsxd  rbx, r8d
0x18001d08d  mov     r14, rdx
0x18001d090  mov     [rax+20h], rdi
0x18001d094  mov     rsi, rcx
0x18001d097  lea     r8, [rax+20h]; TokenHandle
0x18001d09b  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x18001d09f  lea     edx, [rdi+28h]; DesiredAccess
0x18001d0a2  call    cs:__imp_NtOpenProcessToken
0x18001d0a8  test    eax, eax
0x18001d0aa  js      loc_18001D167
0x18001d0b0  mov     rax, rbx
0x18001d0b3  lea     edx, [rdi+64h]; uBytes
0x18001d0b6  mov     dword ptr [rsp+68h+var_38], eax
0x18001d0ba  lea     ecx, [rdi+40h]; uFlags
0x18001d0bd  shr     rax, 20h
0x18001d0c1  mov     dword ptr [rsp+68h+var_38+4], eax
0x18001d0c5  call    cs:__imp_LocalAlloc
0x18001d0cb  mov     rbx, rax
0x18001d0ce  test    rax, rax
0x18001d0d1  jz      loc_18001D159
0x18001d0d7  mov     rdx, [rsp+68h+var_38]
0x18001d0dc  mov     edi, 1
0x18001d0e1  mov     [rax], edi
0x18001d0e3  mov     [rax+4], rdx
0x18001d0e7  mov     dword ptr [rax+0Ch], 2
0x18001d0ee  mov     rax, [rsi]
0x18001d0f1  test    rax, rax
0x18001d0f4  jnz     short loc_18001D10A
0x18001d0f6  lea     edx, [rdi+63h]; uBytes
0x18001d0f9  lea     ecx, [rdi+3Fh]; uFlags
0x18001d0fc  call    cs:__imp_LocalAlloc
0x18001d102  mov     [rsi], rax
0x18001d105  test    rax, rax
0x18001d108  jz      short loc_18001D137
0x18001d10a  mov     rcx, [rsp+68h+TokenHandle]; TokenHandle
0x18001d112  mov     r9d, 64h ; 'd'; BufferLength
0x18001d118  mov     [rsp+68h+ReturnLength], r14; ReturnLength
0x18001d11d  mov     r8, rbx; NewState
0x18001d120  xor     edx, edx; DisableAllPrivileges
0x18001d122  mov     [rsp+68h+PreviousState], rax; PreviousState
0x18001d127  call    cs:__imp_NtAdjustPrivilegesToken
0x18001d12d  test    eax, eax
0x18001d12f  jnz     short loc_18001D137
0x18001d131  cmp     dword ptr [r14], 64h ; 'd'
0x18001d135  jbe     short loc_18001D150
0x18001d137  mov     rcx, [rsi]; hMem
0x18001d13a  call    cs:__imp_LocalFree
0x18001d140  mov     qword ptr [rsi], 0
0x18001d147  xor     edi, edi
0x18001d149  mov     dword ptr [r14], 0
0x18001d150  mov     rcx, rbx; hMem
0x18001d153  call    cs:__imp_LocalFree
0x18001d159  mov     rcx, [rsp+68h+TokenHandle]; Handle
0x18001d161  call    cs:__imp_NtClose
0x18001d167  mov     eax, edi
0x18001d169  add     rsp, 48h
0x18001d16d  pop     r14
0x18001d16f  pop     rdi
0x18001d170  pop     rsi
0x18001d171  pop     rbx
0x18001d172  retn
```
