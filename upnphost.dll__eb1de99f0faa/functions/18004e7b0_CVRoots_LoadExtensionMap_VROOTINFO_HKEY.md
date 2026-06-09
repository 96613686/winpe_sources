# CVRoots::LoadExtensionMap(VROOTINFO *,HKEY__ *)

- ea: `0x18004e7b0`
- end: `0x18004e9de`
- name: `?LoadExtensionMap@CVRoots@@AEAAHPEAUVROOTINFO@@PEAUHKEY__@@@Z`
- size: `558`
- prototype: `int(CVRoots *__hidden this, struct VROOTINFO *, HKEY)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x18002bb38`

## callees

- `0x1800065f0`
- `0x18002be58`
- `0x18002be90`
- `0x180037fdc`
- `0x18003a560`
- `0x18004e7b0`
- `0x18004eaa0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18004e931`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18004e931`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18004e874`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18004e874`

## string_xrefs

- `0x18004e7e7`: `ExtensionMap`

## pseudocode

```c
__int64 __fastcall CVRoots::LoadExtensionMap(CVRoots *this, struct VROOTINFO *a2, HKEY a3)
{
  const unsigned __int16 *v4; // rdx
  unsigned int v5; // esi
  void *v6; // rdx
  int v7; // ebx
  DWORD v8; // ecx
  void *v9; // rax
  int v10; // edx
  int v11; // edx
  int i; // r14d
  DWORD v14; // edx
  int v15; // edx
  __int64 v16; // rbx
  int v17; // edx
  const unsigned __int16 *v18; // rcx
  DWORD cValues; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  DWORD dwIndex; // [rsp+70h] [rbp-90h]
  __int64 v22; // [rsp+78h] [rbp-88h]
  DWORD Type; // [rsp+80h] [rbp-80h] BYREF
  DWORD cchValueName; // [rsp+88h] [rbp-78h] BYREF
  BYTE Data[2]; // [rsp+90h] [rbp-70h] BYREF
  WCHAR ValueName[264]; // [rsp+2A0h] [rbp+1A0h] BYREF

  hKey = 0;
  dwIndex = 0;
  v22 = 0;
  CReg::Open(&hKey, a3, L"ExtensionMap");
  if ( hKey )
  {
    v5 = 1;
    v7 = CReg::ValueSZ((CReg *)&hKey, v4, (unsigned __int16 *)Data, 0x105u);
    if ( v7 )
    {
      v8 = 1;
    }
    else
    {
      cValues = 0;
      RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, &cValues, 0, 0, 0, 0);
      v8 = cValues;
    }
    *((_DWORD *)a2 + 11) = v8;
    v9 = svsutil_AllocZ(16 * v8, v6);
    *((_QWORD *)a2 + 6) = v9;
    if ( v9 )
    {
      if ( v7 )
      {
        **((_QWORD **)a2 + 6) = MySzDupW(L"*", v10);
        *(_QWORD *)(*((_QWORD *)a2 + 6) + 8LL) = MySzDupW((const unsigned __int16 *)Data, v11);
      }
      else
      {
        for ( i = 0; i < *((_DWORD *)a2 + 11); ++i )
        {
          cchValueName = 261;
          Type = 0;
          if ( hKey )
          {
            v14 = dwIndex;
            cValues = 522;
            ++dwIndex;
            if ( !RegEnumValueW(hKey, v14, ValueName, &cchValueName, 0, &Type, Data, &cValues) )
            {
              if ( ValueName[0] && *(_WORD *)Data )
              {
                v16 = 2LL * i;
                *(_QWORD *)(*((_QWORD *)a2 + 6) + 16LL * i) = MySzDupW(ValueName, v15);
                v18 = (const unsigned __int16 *)Data;
              }
              else
              {
                v16 = 2LL * i;
                *(_QWORD *)(*((_QWORD *)a2 + 6) + 16LL * i) = MySzDupW(&Format, v15);
                v18 = &Format;
              }
              *(_QWORD *)(*((_QWORD *)a2 + 6) + 8 * v16 + 8) = MySzDupW(v18, v17);
            }
          }
        }
      }
    }
    else
    {
      v5 = 0;
    }
    CReg::~CReg((CReg *)&hKey);
    return v5;
  }
  else
  {
    *((_DWORD *)a2 + 11) = 0;
    CReg::~CReg((CReg *)&hKey);
    return 0;
  }
}

```

## disassembly

```asm
0x18004e7b0  mov     [rsp-8+arg_0], rbx
0x18004e7b5  push    rbp
0x18004e7b6  push    rsi
0x18004e7b7  push    rdi
0x18004e7b8  push    r14
0x18004e7ba  push    r15
0x18004e7bc  lea     rbp, [rsp-3C0h]
0x18004e7c4  sub     rsp, 4C0h
0x18004e7cb  mov     rax, cs:__security_cookie
0x18004e7d2  xor     rax, rsp
0x18004e7d5  mov     [rbp+3E0h+var_30], rax
0x18004e7dc  mov     rax, r8
0x18004e7df  lea     rcx, [rsp+4E0h+hKey]; phkResult
0x18004e7e4  xor     r15d, r15d
0x18004e7e7  lea     r8, aExtensionmap; "ExtensionMap"
0x18004e7ee  mov     rdi, rdx
0x18004e7f1  mov     [rsp+4E0h+hKey], r15
0x18004e7f6  mov     rdx, rax; hKey
0x18004e7f9  mov     [rsp+4E0h+dwIndex], r15d
0x18004e7fe  mov     [rsp+4E0h+var_468], r15
0x18004e803  call    ?Open@CReg@@QEAAHPEAUHKEY__@@PEBGK@Z; CReg::Open(HKEY__ *,ushort const *,ulong)
0x18004e808  lea     rcx, [rsp+4E0h+hKey]; this
0x18004e80d  cmp     [rsp+4E0h+hKey], r15
0x18004e812  jz      loc_18004E9AD
0x18004e818  mov     r9d, 105h; unsigned int
0x18004e81e  lea     r8, [rbp+3E0h+Data]; unsigned __int16 *
0x18004e822  call    ?ValueSZ@CReg@@QEAAHPEBGPEAGK@Z; CReg::ValueSZ(ushort const *,ushort *,ulong)
0x18004e827  lea     esi, [r15+1]
0x18004e82b  mov     ebx, eax
0x18004e82d  test    eax, eax
0x18004e82f  jz      short loc_18004E835
0x18004e831  mov     ecx, esi
0x18004e833  jmp     short loc_18004E87E
0x18004e835  mov     rcx, [rsp+4E0h+hKey]; hKey
0x18004e83a  lea     rax, [rsp+4E0h+cValues]
0x18004e83f  mov     [rsp+4E0h+lpftLastWriteTime], r15; lpftLastWriteTime
0x18004e844  xor     r9d, r9d; lpReserved
0x18004e847  mov     [rsp+4E0h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x18004e84c  xor     r8d, r8d; lpcchClass
0x18004e84f  mov     [rsp+4E0h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x18004e854  xor     edx, edx; lpClass
0x18004e856  mov     [rsp+4E0h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x18004e85b  mov     [rsp+4E0h+lpcValues], rax; lpcValues
0x18004e860  mov     [rsp+4E0h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x18004e865  mov     [rsp+4E0h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x18004e86a  mov     [rsp+4E0h+lpcSubKeys], r15; lpcSubKeys
0x18004e86f  mov     [rsp+4E0h+cValues], r15d
0x18004e874  call    cs:__imp_RegQueryInfoKeyW
0x18004e87a  mov     ecx, [rsp+4E0h+cValues]
0x18004e87e  mov     [rdi+2Ch], ecx
0x18004e881  shl     ecx, 4; Size
0x18004e884  call    ?svsutil_AllocZ@@YAPEAXKPEAX@Z; svsutil_AllocZ(ulong,void *)
0x18004e889  mov     [rdi+30h], rax
0x18004e88d  test    rax, rax
0x18004e890  jnz     short loc_18004E897
0x18004e892  mov     esi, r15d
0x18004e895  jmp     short loc_18004E8BF
0x18004e897  test    ebx, ebx
0x18004e899  jz      short loc_18004E8D0
0x18004e89b  lea     rcx, Src; "*"
0x18004e8a2  call    ?MySzDupW@@YAPEAGPEBGH@Z; MySzDupW(ushort const *,int)
0x18004e8a7  mov     rcx, [rdi+30h]
0x18004e8ab  mov     [rcx], rax
0x18004e8ae  lea     rcx, [rbp+3E0h+Data]; Src
0x18004e8b2  call    ?MySzDupW@@YAPEAGPEBGH@Z; MySzDupW(ushort const *,int)
0x18004e8b7  mov     rcx, [rdi+30h]
0x18004e8bb  mov     [rcx+8], rax
0x18004e8bf  lea     rcx, [rsp+4E0h+hKey]; this
0x18004e8c4  call    ??1CReg@@QEAA@XZ; CReg::~CReg(void)
0x18004e8c9  mov     eax, esi
0x18004e8cb  jmp     loc_18004E9B8
0x18004e8d0  mov     r14d, r15d
0x18004e8d3  cmp     [rdi+2Ch], r15d
0x18004e8d7  jle     short loc_18004E8BF
0x18004e8d9  mov     rcx, [rsp+4E0h+hKey]; hKey
0x18004e8de  mov     [rbp+3E0h+cchValueName], 105h
0x18004e8e5  mov     [rbp+3E0h+Type], r15d
0x18004e8e9  test    rcx, rcx
0x18004e8ec  jz      loc_18004E99B
0x18004e8f2  mov     edx, [rsp+4E0h+dwIndex]; dwIndex
0x18004e8f6  lea     r9, [rbp+3E0h+cchValueName]; lpcchValueName
0x18004e8fa  lea     r8, [rbp+3E0h+ValueName]; lpValueName
0x18004e901  mov     [rsp+4E0h+cValues], 20Ah
0x18004e909  lea     eax, [rdx+1]
0x18004e90c  mov     [rsp+4E0h+dwIndex], eax
0x18004e910  lea     rax, [rsp+4E0h+cValues]
0x18004e915  mov     [rsp+4E0h+lpcValues], rax; lpcbData
0x18004e91a  lea     rax, [rbp+3E0h+Data]
0x18004e91e  mov     [rsp+4E0h+lpcbMaxClassLen], rax; lpData
0x18004e923  lea     rax, [rbp+3E0h+Type]
0x18004e927  mov     [rsp+4E0h+lpcbMaxSubKeyLen], rax; lpType
0x18004e92c  mov     [rsp+4E0h+lpcSubKeys], r15; lpReserved
0x18004e931  call    cs:__imp_RegEnumValueW
0x18004e937  test    eax, eax
0x18004e939  jnz     short loc_18004E99B
0x18004e93b  cmp     [rbp+3E0h+ValueName], r15w
0x18004e943  jz      short loc_18004E96C
0x18004e945  cmp     word ptr [rbp+3E0h+Data], r15w
0x18004e94a  jz      short loc_18004E96C
0x18004e94c  lea     rcx, [rbp+3E0h+ValueName]; Src
0x18004e953  call    ?MySzDupW@@YAPEAGPEBGH@Z; MySzDupW(ushort const *,int)
0x18004e958  mov     rcx, [rdi+30h]
0x18004e95c  movsxd  rbx, r14d
0x18004e95f  add     rbx, rbx
0x18004e962  mov     [rcx+rbx*8], rax
0x18004e966  lea     rcx, [rbp+3E0h+Data]
0x18004e96a  jmp     short loc_18004E98D
0x18004e96c  lea     rcx, Format; Src
0x18004e973  call    ?MySzDupW@@YAPEAGPEBGH@Z; MySzDupW(ushort const *,int)
0x18004e978  mov     rcx, [rdi+30h]
0x18004e97c  movsxd  rbx, r14d
0x18004e97f  add     rbx, rbx
0x18004e982  mov     [rcx+rbx*8], rax
0x18004e986  lea     rcx, Format; Src
0x18004e98d  call    ?MySzDupW@@YAPEAGPEBGH@Z; MySzDupW(ushort const *,int)
0x18004e992  mov     rcx, [rdi+30h]
0x18004e996  mov     [rcx+rbx*8+8], rax
0x18004e99b  add     r14d, esi
0x18004e99e  cmp     r14d, [rdi+2Ch]
0x18004e9a2  jl      loc_18004E8D9
0x18004e9a8  jmp     loc_18004E8BF
0x18004e9ad  mov     [rdi+2Ch], r15d
0x18004e9b1  call    ??1CReg@@QEAA@XZ; CReg::~CReg(void)
0x18004e9b6  xor     eax, eax
0x18004e9b8  mov     rcx, [rbp+3E0h+var_30]
0x18004e9bf  xor     rcx, rsp; StackCookie
0x18004e9c2  call    __security_check_cookie
0x18004e9c7  mov     rbx, [rsp+4E0h+arg_0]
0x18004e9cf  add     rsp, 4C0h
0x18004e9d6  pop     r15
0x18004e9d8  pop     r14
0x18004e9da  pop     rdi
0x18004e9db  pop     rsi
0x18004e9dc  pop     rbp
0x18004e9dd  retn
```
