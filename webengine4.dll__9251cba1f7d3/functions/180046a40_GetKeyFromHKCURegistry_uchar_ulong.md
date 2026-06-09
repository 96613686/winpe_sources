# GetKeyFromHKCURegistry(uchar *,ulong)

- ea: `0x180046a40`
- end: `0x180046c3e`
- name: `?GetKeyFromHKCURegistry@@YAJPEAEK@Z`
- size: `510`
- prototype: `__int64 __fastcall(unsigned __int8 *, size_t Size)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180045e38`

## callees

- `0x180007824`
- `0x18000d56c`
- `0x180046270`
- `0x180046a40`
- `0x180046c40`
- `0x18004d030`
- `0x18004d350`
- `0x1800653c0`

## import_xrefs

- `KERNEL32!lstrlenW` at `0x180046b8e`
- `KERNEL32!lstrlenW` at `0x180046b8e`
- `ADVAPI32!RegCloseKey` at `0x180046ac8`
- `ADVAPI32!RegCloseKey` at `0x180046bf9`
- `ADVAPI32!RegCloseKey` at `0x180046c09`
- `ADVAPI32!RegCloseKey` at `0x180046ac8`
- `ADVAPI32!RegCloseKey` at `0x180046bf9`
- `ADVAPI32!RegCloseKey` at `0x180046c09`
- `ADVAPI32!RegOpenKeyExW` at `0x180046bcd`
- `ADVAPI32!RegOpenKeyExW` at `0x180046bcd`

## pseudocode

```c
__int64 __fastcall GetKeyFromHKCURegistry(unsigned __int8 *a1, size_t Size)
{
  unsigned int v2; // edi
  unsigned int KeyFromHKCURegistryUsingKey; // ebx
  __int64 v5; // rdx
  WCHAR *v6; // rcx
  WCHAR v7; // ax
  WCHAR *v8; // rax
  int v9; // eax
  unsigned int LastWin32Error; // eax
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  HKEY v13; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR String[1024]; // [rsp+40h] [rbp-C0h] BYREF

  v2 = Size;
  if ( !a1 || !(_DWORD)Size )
    return 2147942487LL;
  hKey = 0;
  v13 = 0;
  if ( (unsigned int)CRegInfo::OpenCurrentVersionKey(&hKey, 0x2001Fu, 0, 1) )
    goto LABEL_6;
  KeyFromHKCURegistryUsingKey = GetKeyFromHKCURegistryUsingKey(a1, v2, hKey);
  if ( KeyFromHKCURegistryUsingKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
LABEL_6:
    KeyFromHKCURegistryUsingKey = CRegInfo::OpenCurrentVersionKey(&v13, 0x20019u, 1, 1);
    if ( !KeyFromHKCURegistryUsingKey )
    {
      memset_0(String, 0, sizeof(String));
      v5 = 1024;
      v6 = String;
      do
      {
        if ( v5 == -2147482622 )
          break;
        v7 = *(WCHAR *)((char *)v6 + (char *)L"AutoGenKeys" - (char *)String);
        if ( !v7 )
          break;
        *v6++ = v7;
        --v5;
      }
      while ( v5 );
      v8 = v6 - 1;
      if ( v5 )
        v8 = v6;
      *v8 = 0;
      KeyFromHKCURegistryUsingKey = v5 == 0 ? 0x8007007A : 0;
      if ( v5 )
      {
        KeyFromHKCURegistryUsingKey = StringCchCatW(String, 0x400u, L"\\");
        if ( !KeyFromHKCURegistryUsingKey )
        {
          v9 = lstrlenW(String);
          KeyFromHKCURegistryUsingKey = GetCurrentSidString(&String[v9], 1024 - v9);
          if ( !KeyFromHKCURegistryUsingKey )
          {
            if ( RegOpenKeyExW(v13, String, 0, 0x2001Fu, &hKey) )
              LastWin32Error = GetLastWin32Error();
            else
              LastWin32Error = GetKeyFromHKCURegistryUsingKey(a1, v2, hKey);
            KeyFromHKCURegistryUsingKey = LastWin32Error;
          }
        }
      }
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( v13 )
    RegCloseKey(v13);
  return KeyFromHKCURegistryUsingKey;
}

```

## disassembly

```asm
0x180046a40  mov     [rsp-8+arg_10], rbx
0x180046a45  push    rbp
0x180046a46  push    rsi
0x180046a47  push    rdi
0x180046a48  push    r14
0x180046a4a  push    r15
0x180046a4c  lea     rbp, [rsp-750h]
0x180046a54  sub     rsp, 850h
0x180046a5b  mov     rax, cs:__security_cookie
0x180046a62  xor     rax, rsp
0x180046a65  mov     [rbp+770h+var_30], rax
0x180046a6c  xor     r15d, r15d
0x180046a6f  mov     edi, edx
0x180046a71  mov     rsi, rcx
0x180046a74  test    rcx, rcx
0x180046a77  jz      loc_180046C13
0x180046a7d  cmp     edx, 1
0x180046a80  jb      loc_180046C13
0x180046a86  lea     r9d, [r15+1]; int
0x180046a8a  mov     [rsp+870h+hKey], r15
0x180046a8f  xor     r8d, r8d; int
0x180046a92  mov     [rsp+870h+var_838], r15
0x180046a97  mov     edx, 2001Fh; samDesired
0x180046a9c  lea     rcx, [rsp+870h+hKey]; dwOptions
0x180046aa1  call    ?OpenCurrentVersionKey@CRegInfo@@SAJPEAPEAUHKEY__@@KHH@Z; CRegInfo::OpenCurrentVersionKey(HKEY__ * *,ulong,int,int)
0x180046aa6  test    eax, eax
0x180046aa8  jnz     short loc_180046AD3
0x180046aaa  mov     r8, [rsp+870h+hKey]; hKey
0x180046aaf  mov     edx, edi; Size
0x180046ab1  mov     rcx, rsi; unsigned __int8 *
0x180046ab4  call    ?GetKeyFromHKCURegistryUsingKey@@YAJPEAEKPEAUHKEY__@@@Z; GetKeyFromHKCURegistryUsingKey(uchar *,ulong,HKEY__ *)
0x180046ab9  mov     ebx, eax
0x180046abb  test    eax, eax
0x180046abd  jz      loc_180046BEF
0x180046ac3  mov     rcx, [rsp+870h+hKey]; hKey
0x180046ac8  call    cs:__imp_RegCloseKey
0x180046ace  mov     [rsp+870h+hKey], r15
0x180046ad3  mov     r9d, 1; int
0x180046ad9  lea     rcx, [rsp+870h+var_838]; dwOptions
0x180046ade  mov     r8d, r9d; int
0x180046ae1  mov     edx, 20019h; samDesired
0x180046ae6  call    ?OpenCurrentVersionKey@CRegInfo@@SAJPEAPEAUHKEY__@@KHH@Z; CRegInfo::OpenCurrentVersionKey(HKEY__ * *,ulong,int,int)
0x180046aeb  mov     ebx, eax
0x180046aed  test    eax, eax
0x180046aef  jnz     loc_180046BEF
0x180046af5  xor     edx, edx; Val
0x180046af7  lea     rcx, [rsp+870h+String]; void *
0x180046afc  mov     r8d, 800h; Size
0x180046b02  call    memset_0
0x180046b07  lea     r8, aAutogenkeys_0; "AutoGenKeys"
0x180046b0e  mov     r14d, 400h
0x180046b14  lea     rax, [rsp+870h+String]
0x180046b19  mov     edx, r14d
0x180046b1c  sub     r8, rax
0x180046b1f  lea     rcx, [rsp+870h+String]
0x180046b24  lea     rax, [rdx+7FFFFBFEh]
0x180046b2b  test    rax, rax
0x180046b2e  jz      short loc_180046B47
0x180046b30  movzx   eax, word ptr [r8+rcx]
0x180046b35  test    ax, ax
0x180046b38  jz      short loc_180046B47
0x180046b3a  mov     [rcx], ax
0x180046b3d  add     rcx, 2
0x180046b41  sub     rdx, 1
0x180046b45  jnz     short loc_180046B24
0x180046b47  test    rdx, rdx
0x180046b4a  lea     rax, [rcx-2]
0x180046b4e  cmovnz  rax, rcx
0x180046b52  mov     [rax], r15w
0x180046b56  mov     rax, rdx
0x180046b59  neg     rax
0x180046b5c  sbb     ebx, ebx
0x180046b5e  not     ebx
0x180046b60  and     ebx, 8007007Ah
0x180046b66  test    rdx, rdx
0x180046b69  jz      loc_180046BEF
0x180046b6f  lea     r8, SubBlock; "\\"
0x180046b76  mov     rdx, r14; unsigned __int64
0x180046b79  lea     rcx, [rsp+870h+String]; unsigned __int16 *
0x180046b7e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180046b83  mov     ebx, eax
0x180046b85  test    eax, eax
0x180046b87  jnz     short loc_180046BEF
0x180046b89  lea     rcx, [rsp+870h+String]; lpString
0x180046b8e  call    cs:__imp_lstrlenW
0x180046b94  sub     r14d, eax
0x180046b97  lea     rcx, [rsp+870h+String]
0x180046b9c  cdqe
0x180046b9e  mov     edx, r14d; unsigned int
0x180046ba1  lea     rcx, [rcx+rax*2]; unsigned __int16 *
0x180046ba5  call    ?GetCurrentSidString@@YAJPEAGK@Z; GetCurrentSidString(ushort *,ulong)
0x180046baa  mov     ebx, eax
0x180046bac  test    eax, eax
0x180046bae  jnz     short loc_180046BEF
0x180046bb0  mov     rcx, [rsp+870h+var_838]; hKey
0x180046bb5  lea     rax, [rsp+870h+hKey]
0x180046bba  mov     r9d, 2001Fh; samDesired
0x180046bc0  mov     [rsp+870h+phkResult], rax; phkResult
0x180046bc5  xor     r8d, r8d; ulOptions
0x180046bc8  lea     rdx, [rsp+870h+String]; lpSubKey
0x180046bcd  call    cs:__imp_RegOpenKeyExW
0x180046bd3  test    eax, eax
0x180046bd5  jz      short loc_180046BDE
0x180046bd7  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x180046bdc  jmp     short loc_180046BED
0x180046bde  mov     r8, [rsp+870h+hKey]; hKey
0x180046be3  mov     edx, edi; Size
0x180046be5  mov     rcx, rsi; unsigned __int8 *
0x180046be8  call    ?GetKeyFromHKCURegistryUsingKey@@YAJPEAEKPEAUHKEY__@@@Z; GetKeyFromHKCURegistryUsingKey(uchar *,ulong,HKEY__ *)
0x180046bed  mov     ebx, eax
0x180046bef  mov     rcx, [rsp+870h+hKey]; hKey
0x180046bf4  test    rcx, rcx
0x180046bf7  jz      short loc_180046BFF
0x180046bf9  call    cs:__imp_RegCloseKey
0x180046bff  mov     rcx, [rsp+870h+var_838]; hKey
0x180046c04  test    rcx, rcx
0x180046c07  jz      short loc_180046C0F
0x180046c09  call    cs:__imp_RegCloseKey
0x180046c0f  mov     eax, ebx
0x180046c11  jmp     short loc_180046C18
0x180046c13  mov     eax, 80070057h
0x180046c18  mov     rcx, [rbp+770h+var_30]
0x180046c1f  xor     rcx, rsp; StackCookie
0x180046c22  call    __security_check_cookie
0x180046c27  mov     rbx, [rsp+870h+arg_10]
0x180046c2f  add     rsp, 850h
0x180046c36  pop     r15
0x180046c38  pop     r14
0x180046c3a  pop     rdi
0x180046c3b  pop     rsi
0x180046c3c  pop     rbp
0x180046c3d  retn
```
