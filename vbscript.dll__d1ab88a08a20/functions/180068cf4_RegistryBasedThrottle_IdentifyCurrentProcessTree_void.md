# RegistryBasedThrottle::IdentifyCurrentProcessTree(void)

- ea: `0x180068cf4`
- end: `0x180068e76`
- name: `?IdentifyCurrentProcessTree@RegistryBasedThrottle@@AEAAXXZ`
- size: `386`
- prototype: `void __fastcall(RegistryBasedThrottle *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180055fe4`

## callees

- `0x180068cf4`
- `0x180079436`
- `0x180079490`

## import_xrefs

- `msvcrt!strcat_s` at `0x180068dec`
- `msvcrt!strcat_s` at `0x180068e03`
- `msvcrt!strcat_s` at `0x180068dec`
- `msvcrt!strcat_s` at `0x180068e03`
- `KERNEL32!Process32Next` at `0x180068d9e`
- `KERNEL32!Process32Next` at `0x180068d9e`
- `KERNEL32!CreateToolhelp32Snapshot` at `0x180068d5e`
- `KERNEL32!CreateToolhelp32Snapshot` at `0x180068d5e`
- `KERNEL32!Process32First` at `0x180068d82`
- `KERNEL32!Process32First` at `0x180068d82`
- `KERNEL32!GetCurrentProcessId` at `0x180068d19`
- `KERNEL32!GetCurrentProcessId` at `0x180068d19`
- `KERNEL32!CloseHandle` at `0x180068e19`
- `KERNEL32!CloseHandle` at `0x180068e37`
- `KERNEL32!CloseHandle` at `0x180068e19`
- `KERNEL32!CloseHandle` at `0x180068e37`

## pseudocode

```c
void __fastcall RegistryBasedThrottle::IdentifyCurrentProcessTree(RegistryBasedThrottle *this)
{
  DWORD CurrentProcessId; // esi
  _BYTE *v3; // rbx
  HANDLE Toolhelp32Snapshot; // rax
  void *v5; // rdi
  char v6; // bp
  BOOL i; // eax
  __int64 v8; // rcx
  __int64 v9; // rax
  PROCESSENTRY32 pe; // [rsp+20h] [rbp-178h] BYREF

  CurrentProcessId = GetCurrentProcessId();
  memset_0(&pe.cntUsage, 0, 0x12Cu);
  pe.dwSize = 304;
  v3 = (char *)this + 568;
  *((_BYTE *)this + 568) = 0;
  while ( CurrentProcessId )
  {
    Toolhelp32Snapshot = CreateToolhelp32Snapshot(2u, 0);
    v5 = Toolhelp32Snapshot;
    if ( Toolhelp32Snapshot == (HANDLE)-1LL )
      break;
    v6 = 0;
    for ( i = Process32First(Toolhelp32Snapshot, &pe); i; i = Process32Next(v5, &pe) )
    {
      if ( pe.th32ProcessID == CurrentProcessId )
      {
        v8 = -1;
        do
          ++v8;
        while ( pe.szExeFile[v8] );
        v9 = -1;
        do
          ++v9;
        while ( v3[v9] );
        if ( (unsigned __int64)(v8 + v9 + 1) >= 0x104 )
        {
          CloseHandle(v5);
          goto LABEL_20;
        }
        if ( *v3 )
          strcat_s((char *)this + 568, 0x104u, ";");
        strcat_s((char *)this + 568, 0x104u, pe.szExeFile);
        CurrentProcessId = pe.th32ParentProcessID;
        v6 = 1;
        break;
      }
    }
    CloseHandle(v5);
    if ( !v6 )
      break;
  }
LABEL_20:
  *((_QWORD *)this + 873) = v3;
  *((_DWORD *)this + 1753) = 1;
}

```

## disassembly

```asm
0x180068cf4  push    rbx
0x180068cf6  push    rbp
0x180068cf7  push    rsi
0x180068cf8  push    rdi
0x180068cf9  push    r13
0x180068cfb  push    r14
0x180068cfd  sub     rsp, 168h
0x180068d04  mov     rax, cs:__security_cookie
0x180068d0b  xor     rax, rsp
0x180068d0e  mov     [rsp+198h+var_48], rax
0x180068d16  mov     r14, rcx
0x180068d19  call    cs:__imp_GetCurrentProcessId
0x180068d20  nop     dword ptr [rax+rax+00h]
0x180068d25  xor     edx, edx; Val
0x180068d27  lea     rcx, [rsp+198h+pe.cntUsage]; void *
0x180068d2c  mov     r8d, 12Ch; Size
0x180068d32  mov     esi, eax
0x180068d34  call    memset_0
0x180068d39  mov     [rsp+198h+pe.dwSize], 130h
0x180068d41  lea     rbx, [r14+238h]
0x180068d48  mov     byte ptr [rbx], 0
0x180068d4b  test    esi, esi
0x180068d4d  jz      loc_180068E43
0x180068d53  mov     r13d, 104h
0x180068d59  xor     edx, edx; th32ProcessID
0x180068d5b  lea     ecx, [rdx+2]; dwFlags
0x180068d5e  call    cs:__imp_CreateToolhelp32Snapshot
0x180068d65  nop     dword ptr [rax+rax+00h]
0x180068d6a  mov     rdi, rax
0x180068d6d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180068d71  jz      loc_180068E43
0x180068d77  xor     bpl, bpl
0x180068d7a  lea     rdx, [rsp+198h+pe]; lppe
0x180068d7f  mov     rcx, rax; hSnapshot
0x180068d82  call    cs:__imp_Process32First
0x180068d89  nop     dword ptr [rax+rax+00h]
0x180068d8e  jmp     short loc_180068DAA
0x180068d90  cmp     [rsp+198h+pe.th32ProcessID], esi
0x180068d94  jz      short loc_180068DB0
0x180068d96  lea     rdx, [rsp+198h+pe]; lppe
0x180068d9b  mov     rcx, rdi; hSnapshot
0x180068d9e  call    cs:__imp_Process32Next
0x180068da5  nop     dword ptr [rax+rax+00h]
0x180068daa  test    eax, eax
0x180068dac  jnz     short loc_180068D90
0x180068dae  jmp     short loc_180068E16
0x180068db0  lea     rax, [rsp+198h+pe.szExeFile]
0x180068db5  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180068db9  inc     rcx
0x180068dbc  cmp     [rax+rcx], bpl
0x180068dc0  jnz     short loc_180068DB9
0x180068dc2  or      rax, 0FFFFFFFFFFFFFFFFh
0x180068dc6  inc     rax
0x180068dc9  cmp     [rbx+rax], bpl
0x180068dcd  jnz     short loc_180068DC6
0x180068dcf  inc     rax
0x180068dd2  add     rax, rcx
0x180068dd5  cmp     rax, r13
0x180068dd8  jnb     short loc_180068E34
0x180068dda  cmp     [rbx], bpl
0x180068ddd  jz      short loc_180068DF8
0x180068ddf  lea     r8, asc_180084074; ";"
0x180068de6  mov     rdx, r13; SizeInBytes
0x180068de9  mov     rcx, rbx; Destination
0x180068dec  call    cs:__imp_strcat_s
0x180068df3  nop     dword ptr [rax+rax+00h]
0x180068df8  lea     r8, [rsp+198h+pe.szExeFile]; Source
0x180068dfd  mov     rdx, r13; SizeInBytes
0x180068e00  mov     rcx, rbx; Destination
0x180068e03  call    cs:__imp_strcat_s
0x180068e0a  nop     dword ptr [rax+rax+00h]
0x180068e0f  mov     esi, [rsp+198h+pe.th32ParentProcessID]
0x180068e13  mov     bpl, 1
0x180068e16  mov     rcx, rdi; hObject
0x180068e19  call    cs:__imp_CloseHandle
0x180068e20  nop     dword ptr [rax+rax+00h]
0x180068e25  test    bpl, bpl
0x180068e28  jz      short loc_180068E43
0x180068e2a  test    esi, esi
0x180068e2c  jnz     loc_180068D59
0x180068e32  jmp     short loc_180068E43
0x180068e34  mov     rcx, rdi; hObject
0x180068e37  call    cs:__imp_CloseHandle
0x180068e3e  nop     dword ptr [rax+rax+00h]
0x180068e43  mov     [r14+1B48h], rbx
0x180068e4a  mov     dword ptr [r14+1B64h], 1
0x180068e55  mov     rcx, [rsp+198h+var_48]
0x180068e5d  xor     rcx, rsp; StackCookie
0x180068e60  call    __security_check_cookie
0x180068e65  add     rsp, 168h
0x180068e6c  pop     r14
0x180068e6e  pop     r13
0x180068e70  pop     rdi
0x180068e71  pop     rsi
0x180068e72  pop     rbp
0x180068e73  pop     rbx
0x180068e74  retn
```
