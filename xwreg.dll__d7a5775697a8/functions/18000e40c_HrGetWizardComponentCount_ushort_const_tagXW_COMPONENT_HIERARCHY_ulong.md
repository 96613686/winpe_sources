# HrGetWizardComponentCount(ushort * const,tagXW_COMPONENT_HIERARCHY,ulong *)

- ea: `0x18000e40c`
- end: `0x18000e615`
- name: `?HrGetWizardComponentCount@@YAJQEAGW4tagXW_COMPONENT_HIERARCHY@@PEAK@Z`
- size: `521`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180008b4c`

## callees

- `0x180007820`
- `0x18000a948`
- `0x18000a9d4`
- `0x18000abbc`
- `0x18000e40c`
- `0x180012800`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e4e8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e4e8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e566`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e566`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000e54c`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000e54c`

## string_xrefs

- `0x18000e45b`: `Components`

## pseudocode

```c
__int64 __fastcall HrGetWizardComponentCount(const unsigned __int16 *a1, __int64 a2, DWORD *a3)
{
  LSTATUS v5; // eax
  unsigned int v6; // ebx
  LSTATUS InfoKeyW; // eax
  PVOID *v8; // rcx
  int v9; // edx
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR SubKey[120]; // [rsp+70h] [rbp-90h] BYREF

  *a3 = 0;
  SubKey[0] = 0;
  StringCchCopyW(SubKey, 0x74u, L"Software\\Microsoft\\Windows\\CurrentVersion\\XWizards\\");
  StringCchCatW(SubKey, 0x74u, L"Components");
  if ( a1 )
  {
    StringCchCatW(SubKey, 0x74u, &qword_180017630);
    StringCchCatW(SubKey, 0x74u, a1);
    StringCchCatW(SubKey, 0x74u, &qword_180017630);
    StringCchCatW(SubKey, 0x74u, L"Children");
  }
  hKey = 0;
  v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &hKey);
  v6 = v5;
  if ( !v5 )
  {
    InfoKeyW = RegQueryInfoKeyW(hKey, 0, 0, 0, a3, 0, 0, 0, 0, 0, 0, 0);
    v6 = InfoKeyW;
    if ( InfoKeyW > 0 )
      v6 = (unsigned __int16)InfoKeyW | 0x80070000;
    RegCloseKey(hKey);
    goto LABEL_17;
  }
  if ( v5 == 2 )
  {
    v6 = 0;
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v6;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_18;
    v9 = 68;
LABEL_16:
    WPP_SF_SD(
      (unsigned int)v8[2],
      v9,
      (unsigned int)&WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids,
      (unsigned int)SubKey,
      v6);
LABEL_17:
    v8 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_18;
  }
  if ( v5 > 0 )
    v6 = (unsigned __int16)v5 | 0x80070000;
  v8 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
    {
LABEL_18:
      if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 0x10) != 0 )
        WPP_SF_D(v8[2], 70, &WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids, v6);
      return v6;
    }
    v9 = 69;
    goto LABEL_16;
  }
  return v6;
}

```

## disassembly

```asm
0x18000e40c  mov     [rsp-8+arg_8], rbx
0x18000e411  push    rbp
0x18000e412  push    rdi
0x18000e413  push    r14
0x18000e415  lea     rbp, [rsp-70h]
0x18000e41a  sub     rsp, 170h
0x18000e421  mov     rax, cs:__security_cookie
0x18000e428  xor     rax, rsp
0x18000e42b  mov     [rbp+80h+var_20], rax
0x18000e42f  xor     eax, eax
0x18000e431  mov     dword ptr [r8], 0
0x18000e438  mov     rdi, r8
0x18000e43b  mov     [rsp+180h+SubKey], ax
0x18000e440  mov     rbx, rcx
0x18000e443  lea     r8, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000e44a  lea     rcx, [rsp+180h+SubKey]; unsigned __int16 *
0x18000e44f  lea     r14d, [rax+74h]
0x18000e453  mov     edx, r14d; unsigned __int64
0x18000e456  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000e45b  lea     r8, aComponents_0; "Components"
0x18000e462  mov     edx, r14d; unsigned __int64
0x18000e465  lea     rcx, [rsp+180h+SubKey]; unsigned __int16 *
0x18000e46a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000e46f  test    rbx, rbx
0x18000e472  jz      short loc_18000E4C0
0x18000e474  lea     r8, qword_180017630; unsigned __int16 *
0x18000e47b  mov     edx, r14d; unsigned __int64
0x18000e47e  lea     rcx, [rsp+180h+SubKey]; unsigned __int16 *
0x18000e483  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000e488  mov     r8, rbx; unsigned __int16 *
0x18000e48b  lea     rcx, [rsp+180h+SubKey]; unsigned __int16 *
0x18000e490  mov     edx, r14d; unsigned __int64
0x18000e493  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000e498  lea     r8, qword_180017630; unsigned __int16 *
0x18000e49f  mov     edx, r14d; unsigned __int64
0x18000e4a2  lea     rcx, [rsp+180h+SubKey]; unsigned __int16 *
0x18000e4a7  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000e4ac  lea     r8, aChildren_0; "Children"
0x18000e4b3  mov     edx, r14d; unsigned __int64
0x18000e4b6  lea     rcx, [rsp+180h+SubKey]; unsigned __int16 *
0x18000e4bb  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000e4c0  lea     rax, [rsp+180h+hKey]
0x18000e4c5  mov     [rsp+180h+hKey], 0
0x18000e4ce  mov     r9d, 20019h; samDesired
0x18000e4d4  mov     [rsp+180h+phkResult], rax; phkResult
0x18000e4d9  xor     r8d, r8d; ulOptions
0x18000e4dc  lea     rdx, [rsp+180h+SubKey]; lpSubKey
0x18000e4e1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000e4e8  call    cs:__imp_RegOpenKeyExW
0x18000e4ee  lea     r14, WPP_GLOBAL_Control
0x18000e4f5  mov     ebx, eax
0x18000e4f7  test    eax, eax
0x18000e4f9  jnz     short loc_18000E56E
0x18000e4fb  mov     rcx, [rsp+180h+hKey]; hKey
0x18000e500  xor     r9d, r9d; lpReserved
0x18000e503  mov     [rsp+180h+lpftLastWriteTime], 0; lpftLastWriteTime
0x18000e50c  xor     r8d, r8d; lpcchClass
0x18000e50f  mov     [rsp+180h+lpcbSecurityDescriptor], 0; lpcbSecurityDescriptor
0x18000e518  xor     edx, edx; lpClass
0x18000e51a  mov     [rsp+180h+lpcbMaxValueLen], 0; lpcbMaxValueLen
0x18000e523  mov     [rsp+180h+lpcbMaxValueNameLen], 0; lpcbMaxValueNameLen
0x18000e52c  mov     [rsp+180h+lpcValues], 0; lpcValues
0x18000e535  mov     [rsp+180h+lpcbMaxClassLen], 0; lpcbMaxClassLen
0x18000e53e  mov     [rsp+180h+lpcbMaxSubKeyLen], 0; lpcbMaxSubKeyLen
0x18000e547  mov     [rsp+180h+phkResult], rdi; lpcSubKeys
0x18000e54c  call    cs:__imp_RegQueryInfoKeyW
0x18000e552  mov     ebx, eax
0x18000e554  test    eax, eax
0x18000e556  jle     short loc_18000E561
0x18000e558  movzx   ebx, ax
0x18000e55b  or      ebx, 80070000h
0x18000e561  mov     rcx, [rsp+180h+hKey]; hKey
0x18000e566  call    cs:__imp_RegCloseKey
0x18000e56c  jmp     short loc_18000E5C9
0x18000e56e  cmp     eax, 2
0x18000e571  jnz     short loc_18000E58C
0x18000e573  xor     ebx, ebx
0x18000e575  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e57c  cmp     rcx, r14
0x18000e57f  jz      short loc_18000E5F3
0x18000e581  test    byte ptr [rcx+1Ch], 10h
0x18000e585  jz      short loc_18000E5D0
0x18000e587  lea     edx, [rax+42h]
0x18000e58a  jmp     short loc_18000E5B0
0x18000e58c  test    eax, eax
0x18000e58e  jle     short loc_18000E599
0x18000e590  movzx   ebx, ax
0x18000e593  or      ebx, 80070000h
0x18000e599  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e5a0  cmp     rcx, r14
0x18000e5a3  jz      short loc_18000E5F3
0x18000e5a5  test    byte ptr [rcx+1Ch], 4
0x18000e5a9  jz      short loc_18000E5D0
0x18000e5ab  mov     edx, 45h ; 'E'
0x18000e5b0  mov     rcx, [rcx+10h]
0x18000e5b4  lea     r9, [rsp+180h+SubKey]
0x18000e5b9  lea     r8, WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids
0x18000e5c0  mov     dword ptr [rsp+180h+phkResult], ebx
0x18000e5c4  call    WPP_SF_SD
0x18000e5c9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e5d0  cmp     rcx, r14
0x18000e5d3  jz      short loc_18000E5F3
0x18000e5d5  test    byte ptr [rcx+1Ch], 10h
0x18000e5d9  jz      short loc_18000E5F3
0x18000e5db  mov     rcx, [rcx+10h]
0x18000e5df  lea     r8, WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids
0x18000e5e6  mov     edx, 46h ; 'F'
0x18000e5eb  mov     r9d, ebx
0x18000e5ee  call    WPP_SF_D
0x18000e5f3  mov     eax, ebx
0x18000e5f5  mov     rcx, [rbp+80h+var_20]
0x18000e5f9  xor     rcx, rsp; StackCookie
0x18000e5fc  call    __security_check_cookie
0x18000e601  mov     rbx, [rsp+180h+arg_8]
0x18000e609  add     rsp, 170h
0x18000e610  pop     r14
0x18000e612  pop     rdi
0x18000e613  pop     rbp
0x18000e614  retn
```
