# DeleteKeyAndSubKeys(HKEY__ *,char const *)

- ea: `0x18000a848`
- end: `0x18000a9d5`
- name: `?DeleteKeyAndSubKeys@@YAJPEAUHKEY__@@PEBD@Z`
- size: `397`
- prototype: `__int64 __fastcall(HKEY, const char *)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, registry_config`

## callers

- `0x18000a848`
- `0x18000ac08`

## callees

- `0x1800031f4`
- `0x180003200`
- `0x18000a848`
- `0x18000d1c0`

## import_xrefs

- `msvcrt!strcpy_s` at `0x18000a938`
- `msvcrt!strcpy_s` at `0x18000a938`
- `ADVAPI32!RegEnumKeyExA` at `0x18000a8e4`
- `ADVAPI32!RegEnumKeyExA` at `0x18000a8e4`
- `ADVAPI32!RegDeleteKeyA` at `0x18000a99e`
- `ADVAPI32!RegDeleteKeyA` at `0x18000a99e`
- `ADVAPI32!RegOpenKeyExA` at `0x18000a891`
- `ADVAPI32!RegOpenKeyExA` at `0x18000a891`
- `ADVAPI32!RegCloseKey` at `0x18000a951`
- `ADVAPI32!RegCloseKey` at `0x18000a98e`
- `ADVAPI32!RegCloseKey` at `0x18000a951`
- `ADVAPI32!RegCloseKey` at `0x18000a98e`

## pseudocode

```c
__int64 __fastcall DeleteKeyAndSubKeys(HKEY a1, const char *a2)
{
  LSTATUS v4; // eax
  LSTATUS v5; // eax
  const char **v6; // rbx
  DWORD i; // esi
  LSTATUS v8; // eax
  const char ***v9; // rax
  const char **v10; // rdi
  __int64 v11; // rax
  size_t v12; // rbx
  char *v13; // rax
  __int64 result; // rax
  const char *v15; // rdi
  HKEY hKey; // [rsp+40h] [rbp-148h] BYREF
  DWORD cchName; // [rsp+48h] [rbp-140h] BYREF
  CHAR Name[272]; // [rsp+50h] [rbp-138h] BYREF

  hKey = 0;
  v4 = RegOpenKeyExA(a1, a2, 0, 0xF003Fu, &hKey);
  if ( v4 )
  {
    v5 = v4 - 2;
  }
  else
  {
    v6 = 0;
    for ( i = 0; ; ++i )
    {
      cchName = 261;
      v8 = RegEnumKeyExA(hKey, i, Name, &cchName, 0, 0, 0, 0);
      if ( v8 == 259 )
        break;
      if ( v8 )
      {
        RegCloseKey(hKey);
        return 2147549183LL;
      }
      v9 = (const char ***)operator new(0x10u);
      v10 = (const char **)v9;
      if ( v9 )
      {
        *v9 = v6;
        v11 = -1;
        do
          ++v11;
        while ( Name[v11] );
        v12 = (unsigned int)(v11 + 1);
        v13 = (char *)operator new(v12);
        v10[1] = v13;
        if ( v13 )
          strcpy_s(v13, (unsigned int)v12, Name);
        v6 = v10;
      }
      else
      {
        v6 = 0;
      }
    }
    while ( v6 )
    {
      v15 = *v6;
      result = DeleteKeyAndSubKeys(hKey, v6[1]);
      if ( (int)result < 0 )
        return result;
      operator delete((void *)v6[1]);
      operator delete(v6);
      v6 = (const char **)v15;
    }
    v5 = RegCloseKey(hKey);
    if ( !v5 )
      v5 = RegDeleteKeyA(a1, a2);
  }
  return v5 != 0 ? 0x8000FFFF : 0;
}

```

## disassembly

```asm
0x18000a848  mov     [rsp+arg_10], rbx
0x18000a84d  mov     [rsp+arg_18], rbp
0x18000a852  push    rsi
0x18000a853  push    rdi
0x18000a854  push    r14
0x18000a856  sub     rsp, 170h
0x18000a85d  mov     rax, cs:__security_cookie
0x18000a864  xor     rax, rsp
0x18000a867  mov     [rsp+188h+var_28], rax
0x18000a86f  lea     rax, [rsp+188h+hKey]
0x18000a874  mov     [rsp+188h+hKey], 0
0x18000a87d  mov     r9d, 0F003Fh; samDesired
0x18000a883  mov     [rsp+188h+phkResult], rax; phkResult
0x18000a888  xor     r8d, r8d; ulOptions
0x18000a88b  mov     r14, rdx
0x18000a88e  mov     rbp, rcx
0x18000a891  call    cs:__imp_RegOpenKeyExA
0x18000a897  test    eax, eax
0x18000a899  jz      short loc_18000A8A3
0x18000a89b  sub     eax, 2
0x18000a89e  jmp     loc_18000A9A4
0x18000a8a3  xor     ebx, ebx
0x18000a8a5  xor     esi, esi
0x18000a8a7  mov     rcx, [rsp+188h+hKey]; hKey
0x18000a8ac  lea     r9, [rsp+188h+cchName]; lpcchName
0x18000a8b1  mov     [rsp+188h+lpftLastWriteTime], 0; lpftLastWriteTime
0x18000a8ba  lea     r8, [rsp+188h+Name]; lpName
0x18000a8bf  mov     [rsp+188h+lpcchClass], 0; lpcchClass
0x18000a8c8  mov     edx, esi; dwIndex
0x18000a8ca  mov     [rsp+188h+lpClass], 0; lpClass
0x18000a8d3  mov     [rsp+188h+phkResult], 0; lpReserved
0x18000a8dc  mov     [rsp+188h+cchName], 105h
0x18000a8e4  call    cs:__imp_RegEnumKeyExA
0x18000a8ea  cmp     eax, 103h
0x18000a8ef  jz      short loc_18000A95E
0x18000a8f1  test    eax, eax
0x18000a8f3  jnz     short loc_18000A94C
0x18000a8f5  lea     ecx, [rax+10h]; Size
0x18000a8f8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a8fd  mov     rdi, rax
0x18000a900  test    rax, rax
0x18000a903  jz      short loc_18000A943
0x18000a905  mov     [rax], rbx
0x18000a908  lea     rcx, [rsp+188h+Name]
0x18000a90d  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000a911  inc     rax
0x18000a914  cmp     byte ptr [rcx+rax], 0
0x18000a918  jnz     short loc_18000A911
0x18000a91a  inc     eax
0x18000a91c  mov     ecx, eax; Size
0x18000a91e  mov     ebx, eax
0x18000a920  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a925  mov     [rdi+8], rax
0x18000a929  test    rax, rax
0x18000a92c  jz      short loc_18000A93E
0x18000a92e  lea     r8, [rsp+188h+Name]; Source
0x18000a933  mov     edx, ebx; SizeInBytes
0x18000a935  mov     rcx, rax; Destination
0x18000a938  call    cs:__imp_strcpy_s
0x18000a93e  mov     rbx, rdi
0x18000a941  jmp     short loc_18000A945
0x18000a943  xor     ebx, ebx
0x18000a945  inc     esi
0x18000a947  jmp     loc_18000A8A7
0x18000a94c  mov     rcx, [rsp+188h+hKey]; hKey
0x18000a951  call    cs:__imp_RegCloseKey
0x18000a957  mov     eax, 8000FFFFh
0x18000a95c  jmp     short loc_18000A9AD
0x18000a95e  mov     rcx, [rsp+188h+hKey]; HKEY
0x18000a963  test    rbx, rbx
0x18000a966  jz      short loc_18000A98E
0x18000a968  mov     rdx, [rbx+8]; char *
0x18000a96c  mov     rdi, [rbx]
0x18000a96f  call    ?DeleteKeyAndSubKeys@@YAJPEAUHKEY__@@PEBD@Z; DeleteKeyAndSubKeys(HKEY__ *,char const *)
0x18000a974  test    eax, eax
0x18000a976  js      short loc_18000A9AD
0x18000a978  mov     rcx, [rbx+8]; Block
0x18000a97c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a981  mov     rcx, rbx; Block
0x18000a984  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a989  mov     rbx, rdi
0x18000a98c  jmp     short loc_18000A95E
0x18000a98e  call    cs:__imp_RegCloseKey
0x18000a994  test    eax, eax
0x18000a996  jnz     short loc_18000A9A4
0x18000a998  mov     rdx, r14; lpSubKey
0x18000a99b  mov     rcx, rbp; hKey
0x18000a99e  call    cs:__imp_RegDeleteKeyA
0x18000a9a4  neg     eax
0x18000a9a6  sbb     eax, eax
0x18000a9a8  and     eax, 8000FFFFh
0x18000a9ad  mov     rcx, [rsp+188h+var_28]
0x18000a9b5  xor     rcx, rsp; StackCookie
0x18000a9b8  call    __security_check_cookie
0x18000a9bd  lea     r11, [rsp+188h+var_18]
0x18000a9c5  mov     rbx, [r11+30h]
0x18000a9c9  mov     rbp, [r11+38h]
0x18000a9cd  mov     rsp, r11
0x18000a9d0  pop     r14
0x18000a9d2  pop     rdi
0x18000a9d3  pop     rsi
0x18000a9d4  retn
```
