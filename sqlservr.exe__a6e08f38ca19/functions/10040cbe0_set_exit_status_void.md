# set_exit_status(void)

- ea: `0x10040cbe0`
- end: `0x10040cd82`
- name: `?set_exit_status@@YAXXZ`
- size: `418`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x10040c8d0`

## callees

- `0x100401580`
- `0x100401aa0`
- `0x10040cbe0`
- `0x10041eac0`
- `0x10044aad0`

## import_xrefs

- `KERNEL32!OpenFileMappingW` at `0x10040cd2e`
- `KERNEL32!OpenFileMappingW` at `0x10040cd2e`
- `KERNEL32!MapViewOfFile` at `0x10040cd52`
- `KERNEL32!MapViewOfFile` at `0x10040cd52`
- `KERNEL32!CloseHandle` at `0x10040cd63`
- `KERNEL32!CloseHandle` at `0x10040cd63`
- `sqlmin!?SetWin32ExitCode@@YAXK@Z` at `0x10040ccd5`
- `sqlmin!?SetWin32ExitCode@@YAXK@Z` at `0x10040ccd5`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x10040cc0b`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x10040cc84`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x10040cc9a`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x10040ccdb`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x10040cc9a`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x10040ccdb`
- `instapi160!IsDefaultInstanceName` at `0x10040cc21`
- `instapi160!IsDefaultInstanceName` at `0x10040cc21`

## pseudocode

```c
void set_exit_status(void)
{
  __int64 v0; // rax
  __int64 v1; // rdx
  WCHAR *v2; // rax
  WCHAR v3; // cx
  WCHAR *v4; // rcx
  signed int v5; // ebx
  __int64 v6; // rbx
  struct __crt_locale_pointers *DefaultLocale; // rax
  struct __crt_locale_pointers *v8; // rax
  int v9; // eax
  char *v10; // rcx
  HANDLE v11; // rax
  void *v12; // rbx
  _BYTE *v13; // rax
  __int64 v14; // [rsp+28h] [rbp-430h]
  WCHAR Name[264]; // [rsp+30h] [rbp-428h] BYREF
  char Buffer[512]; // [rsp+240h] [rbp-218h] BYREF

  if ( *((_DWORD *)qword_10049F360 + 3636)
    || (v0 = (*(__int64 (__fastcall **)(struct IServerConfiguration *))(*(_QWORD *)s_pServerConf + 224LL))(s_pServerConf),
        !(unsigned int)IsDefaultInstanceName(v0)) )
  {
    v6 = (*(__int64 (__fastcall **)(struct IServerConfiguration *))(*(_QWORD *)s_pServerConf + 224LL))(s_pServerConf);
    DefaultLocale = GetDefaultLocale();
    v5 = StringCchPrintf_lW(Name, 0x105u, L"%ls$%ls", DefaultLocale, L"SQL60_SHUTDOWN", v6);
  }
  else
  {
    v1 = 261;
    v2 = Name;
    do
    {
      if ( v1 == -2147483385 )
        break;
      v3 = *(WCHAR *)((char *)v2 + (char *)L"SQL60_SHUTDOWN" - (char *)Name);
      if ( !v3 )
        break;
      *v2++ = v3;
      --v1;
    }
    while ( v1 );
    v4 = v2 - 1;
    v5 = -2147024774;
    if ( v1 )
    {
      v4 = v2;
      v5 = 0;
    }
    *v4 = 0;
  }
  if ( v5 < 0 )
  {
    _mm_lfence();
    SetWin32ExitCode(v5);
    v8 = GetDefaultLocale();
    LODWORD(v14) = v5;
    v9 = StringCchPrintf_lA(
           Buffer,
           0x200u,
           "%hs (HRESULT 0x%x)",
           v8,
           "String operation failure (exit status block)",
           v14);
    v10 = "String operation failure (exit status block)";
    if ( v9 >= 0 )
      v10 = Buffer;
    FailAndExit(v10);
  }
  v11 = OpenFileMappingW(6u, 1, Name);
  v12 = v11;
  if ( v11 )
  {
    v13 = MapViewOfFile(v11, 6u, 0, 0, 4u);
    if ( v13 )
      *v13 = 1;
    CloseHandle(v12);
  }
}

```

## disassembly

```asm
0x10040cbe0  push    rbx
0x10040cbe2  sub     rsp, 450h
0x10040cbe9  mov     rax, cs:__security_cookie
0x10040cbf0  xor     rax, rsp
0x10040cbf3  mov     [rsp+458h+var_18], rax
0x10040cbfb  mov     rax, cs:qword_10049F360
0x10040cc02  cmp     dword ptr [rax+38D0h], 0
0x10040cc09  jnz     short loc_10040CC84
0x10040cc0b  mov     rax, cs:__imp_?s_pServerConf@@3PEAVIServerConfiguration@@EA; IServerConfiguration * s_pServerConf
0x10040cc12  mov     rcx, [rax]
0x10040cc15  mov     rax, [rcx]
0x10040cc18  call    qword ptr [rax+0E0h]
0x10040cc1e  mov     rcx, rax
0x10040cc21  call    cs:__imp_IsDefaultInstanceName
0x10040cc27  test    eax, eax
0x10040cc29  jz      short loc_10040CC84
0x10040cc2b  lea     r8, aSql60Shutdown; "SQL60_SHUTDOWN"
0x10040cc32  mov     edx, 105h
0x10040cc37  lea     rcx, [rsp+458h+Name]
0x10040cc3c  sub     r8, rcx
0x10040cc3f  lea     rax, [rsp+458h+Name]
0x10040cc44  lea     rcx, [rdx+7FFFFEF9h]
0x10040cc4b  test    rcx, rcx
0x10040cc4e  jz      short loc_10040CC67
0x10040cc50  movzx   ecx, word ptr [r8+rax]
0x10040cc55  test    cx, cx
0x10040cc58  jz      short loc_10040CC67
0x10040cc5a  mov     [rax], cx
0x10040cc5d  add     rax, 2
0x10040cc61  sub     rdx, 1
0x10040cc65  jnz     short loc_10040CC44
0x10040cc67  test    rdx, rdx
0x10040cc6a  lea     rcx, [rax-2]
0x10040cc6e  mov     ebx, 8007007Ah
0x10040cc73  cmovnz  rcx, rax
0x10040cc77  xor     eax, eax
0x10040cc79  test    rdx, rdx
0x10040cc7c  cmovnz  ebx, eax
0x10040cc7f  mov     [rcx], ax
0x10040cc82  jmp     short loc_10040CCCC
0x10040cc84  mov     rax, cs:__imp_?s_pServerConf@@3PEAVIServerConfiguration@@EA; IServerConfiguration * s_pServerConf
0x10040cc8b  mov     rcx, [rax]
0x10040cc8e  mov     rax, [rcx]
0x10040cc91  call    qword ptr [rax+0E0h]
0x10040cc97  mov     rbx, rax
0x10040cc9a  call    cs:__imp_?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ; GetDefaultLocale(void)
0x10040cca0  lea     r8, aSql60Shutdown; "SQL60_SHUTDOWN"
0x10040cca7  mov     [rsp+458h+var_430], rbx
0x10040ccac  mov     [rsp+458h+dwNumberOfBytesToMap], r8
0x10040ccb1  lea     rcx, [rsp+458h+Name]; Buffer
0x10040ccb6  lea     r8, aLsLs; "%ls$%ls"
0x10040ccbd  mov     r9, rax; struct __crt_locale_pointers *
0x10040ccc0  mov     edx, 105h; unsigned __int64
0x10040ccc5  call    ?StringCchPrintf_lW@@YAJPEA_W_KPEB_WPEAU__crt_locale_pointers@@ZZ; StringCchPrintf_lW(wchar_t *,unsigned __int64,wchar_t const *,__crt_locale_pointers *,...)
0x10040ccca  mov     ebx, eax
0x10040cccc  test    ebx, ebx
0x10040ccce  jns     short loc_10040CD21
0x10040ccd0  lfence
0x10040ccd3  mov     ecx, ebx
0x10040ccd5  call    cs:__imp_?SetWin32ExitCode@@YAXK@Z; SetWin32ExitCode(ulong)
0x10040ccdb  call    cs:__imp_?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ; GetDefaultLocale(void)
0x10040cce1  mov     dword ptr [rsp+458h+var_430], ebx
0x10040cce5  lea     r8, aHsHresult0xX; "%hs (HRESULT 0x%x)"
0x10040ccec  lea     rbx, aStringOperatio_0; "String operation failure (exit status b"...
0x10040ccf3  mov     r9, rax; struct __crt_locale_pointers *
0x10040ccf6  mov     edx, 200h; unsigned __int64
0x10040ccfb  mov     [rsp+458h+dwNumberOfBytesToMap], rbx
0x10040cd00  lea     rcx, [rsp+458h+Buffer]; Buffer
0x10040cd08  call    ?StringCchPrintf_lA@@YAJPEAD_KPEBDPEAU__crt_locale_pointers@@ZZ; StringCchPrintf_lA(char *,unsigned __int64,char const *,__crt_locale_pointers *,...)
0x10040cd0d  mov     rcx, rbx
0x10040cd10  test    eax, eax
0x10040cd12  js      short loc_10040CD1C
0x10040cd14  lea     rcx, [rsp+458h+Buffer]; char *
0x10040cd1c  call    ?FailAndExit@@YAXPEBD@Z; FailAndExit(char const *)
0x10040cd21  mov     edx, 1; bInheritHandle
0x10040cd26  lea     r8, [rsp+458h+Name]; lpName
0x10040cd2b  lea     ecx, [rdx+5]; dwDesiredAccess
0x10040cd2e  call    cs:__imp_OpenFileMappingW
0x10040cd34  mov     rbx, rax
0x10040cd37  test    rax, rax
0x10040cd3a  jz      short loc_10040CD69
0x10040cd3c  xor     r9d, r9d; dwFileOffsetLow
0x10040cd3f  mov     [rsp+458h+dwNumberOfBytesToMap], 4; dwNumberOfBytesToMap
0x10040cd48  xor     r8d, r8d; dwFileOffsetHigh
0x10040cd4b  mov     rcx, rax; hFileMappingObject
0x10040cd4e  lea     edx, [r9+6]; dwDesiredAccess
0x10040cd52  call    cs:__imp_MapViewOfFile
0x10040cd58  test    rax, rax
0x10040cd5b  jz      short loc_10040CD60
0x10040cd5d  mov     byte ptr [rax], 1
0x10040cd60  mov     rcx, rbx; hObject
0x10040cd63  call    cs:__imp_CloseHandle
0x10040cd69  mov     rcx, [rsp+458h+var_18]
0x10040cd71  xor     rcx, rsp; StackCookie
0x10040cd74  call    __security_check_cookie
0x10040cd79  add     rsp, 450h
0x10040cd80  pop     rbx
0x10040cd81  retn
```
