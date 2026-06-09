# RegistryBasedThrottle::IdentifyCurrentProcessTree(void)

- ea: `0x180066d6c`
- end: `0x180066ebd`
- name: `?IdentifyCurrentProcessTree@RegistryBasedThrottle@@AEAAXXZ`
- size: `337`
- prototype: `void __fastcall(RegistryBasedThrottle *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800546d4`

## callees

- `0x180066d6c`
- `0x180076746`
- `0x1800767a0`

## import_xrefs

- `msvcrt!strcat_s` at `0x180066e4c`
- `msvcrt!strcat_s` at `0x180066e5d`
- `msvcrt!strcat_s` at `0x180066e4c`
- `msvcrt!strcat_s` at `0x180066e5d`
- `KERNEL32!Process32Next` at `0x180066e04`
- `KERNEL32!Process32Next` at `0x180066e04`
- `KERNEL32!CreateToolhelp32Snapshot` at `0x180066dd0`
- `KERNEL32!CreateToolhelp32Snapshot` at `0x180066dd0`
- `KERNEL32!Process32First` at `0x180066dee`
- `KERNEL32!Process32First` at `0x180066dee`
- `KERNEL32!GetCurrentProcessId` at `0x180066d91`
- `KERNEL32!GetCurrentProcessId` at `0x180066d91`
- `KERNEL32!CloseHandle` at `0x180066e6d`
- `KERNEL32!CloseHandle` at `0x180066e85`
- `KERNEL32!CloseHandle` at `0x180066e6d`
- `KERNEL32!CloseHandle` at `0x180066e85`

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
0x180066d6c  push    rbx
0x180066d6e  push    rbp
0x180066d6f  push    rsi
0x180066d70  push    rdi
0x180066d71  push    r13
0x180066d73  push    r14
0x180066d75  sub     rsp, 168h
0x180066d7c  mov     rax, cs:__security_cookie
0x180066d83  xor     rax, rsp
0x180066d86  mov     [rsp+198h+var_48], rax
0x180066d8e  mov     r14, rcx
0x180066d91  call    cs:__imp_GetCurrentProcessId
0x180066d97  xor     edx, edx; Val
0x180066d99  lea     rcx, [rsp+198h+pe.cntUsage]; void *
0x180066d9e  mov     r8d, 12Ch; Size
0x180066da4  mov     esi, eax
0x180066da6  call    memset_0
0x180066dab  mov     [rsp+198h+pe.dwSize], 130h
0x180066db3  lea     rbx, [r14+238h]
0x180066dba  mov     byte ptr [rbx], 0
0x180066dbd  test    esi, esi
0x180066dbf  jz      loc_180066E8B
0x180066dc5  mov     r13d, 104h
0x180066dcb  xor     edx, edx; th32ProcessID
0x180066dcd  lea     ecx, [rdx+2]; dwFlags
0x180066dd0  call    cs:__imp_CreateToolhelp32Snapshot
0x180066dd6  mov     rdi, rax
0x180066dd9  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180066ddd  jz      loc_180066E8B
0x180066de3  xor     bpl, bpl
0x180066de6  lea     rdx, [rsp+198h+pe]; lppe
0x180066deb  mov     rcx, rax; hSnapshot
0x180066dee  call    cs:__imp_Process32First
0x180066df4  jmp     short loc_180066E0A
0x180066df6  cmp     [rsp+198h+pe.th32ProcessID], esi
0x180066dfa  jz      short loc_180066E10
0x180066dfc  lea     rdx, [rsp+198h+pe]; lppe
0x180066e01  mov     rcx, rdi; hSnapshot
0x180066e04  call    cs:__imp_Process32Next
0x180066e0a  test    eax, eax
0x180066e0c  jnz     short loc_180066DF6
0x180066e0e  jmp     short loc_180066E6A
0x180066e10  lea     rax, [rsp+198h+pe.szExeFile]
0x180066e15  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180066e19  inc     rcx
0x180066e1c  cmp     [rax+rcx], bpl
0x180066e20  jnz     short loc_180066E19
0x180066e22  or      rax, 0FFFFFFFFFFFFFFFFh
0x180066e26  inc     rax
0x180066e29  cmp     [rbx+rax], bpl
0x180066e2d  jnz     short loc_180066E26
0x180066e2f  inc     rax
0x180066e32  add     rax, rcx
0x180066e35  cmp     rax, r13
0x180066e38  jnb     short loc_180066E82
0x180066e3a  cmp     [rbx], bpl
0x180066e3d  jz      short loc_180066E52
0x180066e3f  lea     r8, asc_180080FFC; ";"
0x180066e46  mov     rdx, r13; SizeInBytes
0x180066e49  mov     rcx, rbx; Destination
0x180066e4c  call    cs:__imp_strcat_s
0x180066e52  lea     r8, [rsp+198h+pe.szExeFile]; Source
0x180066e57  mov     rdx, r13; SizeInBytes
0x180066e5a  mov     rcx, rbx; Destination
0x180066e5d  call    cs:__imp_strcat_s
0x180066e63  mov     esi, [rsp+198h+pe.th32ParentProcessID]
0x180066e67  mov     bpl, 1
0x180066e6a  mov     rcx, rdi; hObject
0x180066e6d  call    cs:__imp_CloseHandle
0x180066e73  test    bpl, bpl
0x180066e76  jz      short loc_180066E8B
0x180066e78  test    esi, esi
0x180066e7a  jnz     loc_180066DCB
0x180066e80  jmp     short loc_180066E8B
0x180066e82  mov     rcx, rdi; hObject
0x180066e85  call    cs:__imp_CloseHandle
0x180066e8b  mov     [r14+1B48h], rbx
0x180066e92  mov     dword ptr [r14+1B64h], 1
0x180066e9d  mov     rcx, [rsp+198h+var_48]
0x180066ea5  xor     rcx, rsp; StackCookie
0x180066ea8  call    __security_check_cookie
0x180066ead  add     rsp, 168h
0x180066eb4  pop     r14
0x180066eb6  pop     r13
0x180066eb8  pop     rdi
0x180066eb9  pop     rsi
0x180066eba  pop     rbp
0x180066ebb  pop     rbx
0x180066ebc  retn
```
