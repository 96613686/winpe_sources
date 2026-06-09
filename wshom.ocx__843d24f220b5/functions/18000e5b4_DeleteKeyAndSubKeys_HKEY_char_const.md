# DeleteKeyAndSubKeys(HKEY__ *,char const *)

- ea: `0x18000e5b4`
- end: `0x18000e741`
- name: `?DeleteKeyAndSubKeys@@YAJPEAUHKEY__@@PEBD@Z`
- size: `397`
- prototype: `__int64 __fastcall(HKEY, const char *)`
- caller_count: `4`
- callee_count: `4`
- tags: `file_ops, registry_config`

## callers

- `0x18000e5b4`
- `0x18000ecec`
- `0x18000edd0`
- `0x18000ee4c`

## callees

- `0x1800060e4`
- `0x180006124`
- `0x18000e5b4`
- `0x180010250`

## import_xrefs

- `msvcrt!strcpy_s` at `0x18000e6a4`
- `msvcrt!strcpy_s` at `0x18000e6a4`
- `ADVAPI32!RegDeleteKeyA` at `0x18000e70a`
- `ADVAPI32!RegDeleteKeyA` at `0x18000e70a`
- `ADVAPI32!RegOpenKeyExA` at `0x18000e5fd`
- `ADVAPI32!RegOpenKeyExA` at `0x18000e5fd`
- `ADVAPI32!RegCloseKey` at `0x18000e6bd`
- `ADVAPI32!RegCloseKey` at `0x18000e6fa`
- `ADVAPI32!RegCloseKey` at `0x18000e6bd`
- `ADVAPI32!RegCloseKey` at `0x18000e6fa`
- `ADVAPI32!RegEnumKeyExA` at `0x18000e650`
- `ADVAPI32!RegEnumKeyExA` at `0x18000e650`

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
0x18000e5b4  mov     [rsp+arg_10], rbx
0x18000e5b9  mov     [rsp+arg_18], rbp
0x18000e5be  push    rsi
0x18000e5bf  push    rdi
0x18000e5c0  push    r14
0x18000e5c2  sub     rsp, 170h
0x18000e5c9  mov     rax, cs:__security_cookie
0x18000e5d0  xor     rax, rsp
0x18000e5d3  mov     [rsp+188h+var_28], rax
0x18000e5db  lea     rax, [rsp+188h+hKey]
0x18000e5e0  mov     [rsp+188h+hKey], 0
0x18000e5e9  mov     r9d, 0F003Fh; samDesired
0x18000e5ef  mov     [rsp+188h+phkResult], rax; phkResult
0x18000e5f4  xor     r8d, r8d; ulOptions
0x18000e5f7  mov     r14, rdx
0x18000e5fa  mov     rbp, rcx
0x18000e5fd  call    cs:__imp_RegOpenKeyExA
0x18000e603  test    eax, eax
0x18000e605  jz      short loc_18000E60F
0x18000e607  sub     eax, 2
0x18000e60a  jmp     loc_18000E710
0x18000e60f  xor     ebx, ebx
0x18000e611  xor     esi, esi
0x18000e613  mov     rcx, [rsp+188h+hKey]; hKey
0x18000e618  lea     r9, [rsp+188h+cchName]; lpcchName
0x18000e61d  mov     [rsp+188h+lpftLastWriteTime], 0; lpftLastWriteTime
0x18000e626  lea     r8, [rsp+188h+Name]; lpName
0x18000e62b  mov     [rsp+188h+lpcchClass], 0; lpcchClass
0x18000e634  mov     edx, esi; dwIndex
0x18000e636  mov     [rsp+188h+lpClass], 0; lpClass
0x18000e63f  mov     [rsp+188h+phkResult], 0; lpReserved
0x18000e648  mov     [rsp+188h+cchName], 105h
0x18000e650  call    cs:__imp_RegEnumKeyExA
0x18000e656  cmp     eax, 103h
0x18000e65b  jz      short loc_18000E6CA
0x18000e65d  test    eax, eax
0x18000e65f  jnz     short loc_18000E6B8
0x18000e661  lea     ecx, [rax+10h]; Size
0x18000e664  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000e669  mov     rdi, rax
0x18000e66c  test    rax, rax
0x18000e66f  jz      short loc_18000E6AF
0x18000e671  mov     [rax], rbx
0x18000e674  lea     rcx, [rsp+188h+Name]
0x18000e679  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000e67d  inc     rax
0x18000e680  cmp     byte ptr [rcx+rax], 0
0x18000e684  jnz     short loc_18000E67D
0x18000e686  inc     eax
0x18000e688  mov     ecx, eax; Size
0x18000e68a  mov     ebx, eax
0x18000e68c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000e691  mov     [rdi+8], rax
0x18000e695  test    rax, rax
0x18000e698  jz      short loc_18000E6AA
0x18000e69a  lea     r8, [rsp+188h+Name]; Source
0x18000e69f  mov     edx, ebx; SizeInBytes
0x18000e6a1  mov     rcx, rax; Destination
0x18000e6a4  call    cs:__imp_strcpy_s
0x18000e6aa  mov     rbx, rdi
0x18000e6ad  jmp     short loc_18000E6B1
0x18000e6af  xor     ebx, ebx
0x18000e6b1  inc     esi
0x18000e6b3  jmp     loc_18000E613
0x18000e6b8  mov     rcx, [rsp+188h+hKey]; hKey
0x18000e6bd  call    cs:__imp_RegCloseKey
0x18000e6c3  mov     eax, 8000FFFFh
0x18000e6c8  jmp     short loc_18000E719
0x18000e6ca  mov     rcx, [rsp+188h+hKey]; HKEY
0x18000e6cf  test    rbx, rbx
0x18000e6d2  jz      short loc_18000E6FA
0x18000e6d4  mov     rdx, [rbx+8]; char *
0x18000e6d8  mov     rdi, [rbx]
0x18000e6db  call    ?DeleteKeyAndSubKeys@@YAJPEAUHKEY__@@PEBD@Z; DeleteKeyAndSubKeys(HKEY__ *,char const *)
0x18000e6e0  test    eax, eax
0x18000e6e2  js      short loc_18000E719
0x18000e6e4  mov     rcx, [rbx+8]; Block
0x18000e6e8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000e6ed  mov     rcx, rbx; Block
0x18000e6f0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000e6f5  mov     rbx, rdi
0x18000e6f8  jmp     short loc_18000E6CA
0x18000e6fa  call    cs:__imp_RegCloseKey
0x18000e700  test    eax, eax
0x18000e702  jnz     short loc_18000E710
0x18000e704  mov     rdx, r14; lpSubKey
0x18000e707  mov     rcx, rbp; hKey
0x18000e70a  call    cs:__imp_RegDeleteKeyA
0x18000e710  neg     eax
0x18000e712  sbb     eax, eax
0x18000e714  and     eax, 8000FFFFh
0x18000e719  mov     rcx, [rsp+188h+var_28]
0x18000e721  xor     rcx, rsp; StackCookie
0x18000e724  call    __security_check_cookie
0x18000e729  lea     r11, [rsp+188h+var_18]
0x18000e731  mov     rbx, [r11+30h]
0x18000e735  mov     rbp, [r11+38h]
0x18000e739  mov     rsp, r11
0x18000e73c  pop     r14
0x18000e73e  pop     rdi
0x18000e73f  pop     rsi
0x18000e740  retn
```
