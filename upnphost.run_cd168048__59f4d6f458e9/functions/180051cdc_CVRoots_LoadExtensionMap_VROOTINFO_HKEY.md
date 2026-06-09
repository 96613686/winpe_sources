# CVRoots::LoadExtensionMap(VROOTINFO *,HKEY__ *)

- ea: `0x180051cdc`
- end: `0x180051f17`
- name: `?LoadExtensionMap@CVRoots@@AEAAHPEAUVROOTINFO@@PEAUHKEY__@@@Z`
- size: `571`
- prototype: `int(CVRoots *__hidden this, struct VROOTINFO *, HKEY)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x18002d240`

## callees

- `0x18001b240`
- `0x18002d588`
- `0x18002d5cc`
- `0x18003a42c`
- `0x18003cb60`
- `0x180051cdc`
- `0x180051ff0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180051e63`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180051e63`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180051da0`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180051da0`

## string_xrefs

- `0x180051d13`: `ExtensionMap`

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
0x180051cdc  mov     [rsp-8+arg_0], rbx
0x180051ce1  push    rbp
0x180051ce2  push    rsi
0x180051ce3  push    rdi
0x180051ce4  push    r14
0x180051ce6  push    r15
0x180051ce8  lea     rbp, [rsp-3C0h]
0x180051cf0  sub     rsp, 4C0h
0x180051cf7  mov     rax, cs:__security_cookie
0x180051cfe  xor     rax, rsp
0x180051d01  mov     [rbp+3E0h+var_30], rax
0x180051d08  mov     rax, r8
0x180051d0b  lea     rcx, [rsp+4E0h+hKey]; phkResult
0x180051d10  xor     r15d, r15d
0x180051d13  lea     r8, aExtensionmap; "ExtensionMap"
0x180051d1a  mov     rdi, rdx
0x180051d1d  mov     [rsp+4E0h+hKey], r15
0x180051d22  mov     rdx, rax; hKey
0x180051d25  mov     [rsp+4E0h+dwIndex], r15d
0x180051d2a  mov     [rsp+4E0h+var_468], r15
0x180051d2f  call    ?Open@CReg@@QEAAHPEAUHKEY__@@PEBGK@Z; CReg::Open(HKEY__ *,ushort const *,ulong)
0x180051d34  lea     rcx, [rsp+4E0h+hKey]; this
0x180051d39  cmp     [rsp+4E0h+hKey], r15
0x180051d3e  jz      loc_180051EE5
0x180051d44  mov     r9d, 105h; unsigned int
0x180051d4a  lea     r8, [rbp+3E0h+Data]; unsigned __int16 *
0x180051d4e  call    ?ValueSZ@CReg@@QEAAHPEBGPEAGK@Z; CReg::ValueSZ(ushort const *,ushort *,ulong)
0x180051d53  lea     esi, [r15+1]
0x180051d57  mov     ebx, eax
0x180051d59  test    eax, eax
0x180051d5b  jz      short loc_180051D61
0x180051d5d  mov     ecx, esi
0x180051d5f  jmp     short loc_180051DB0
0x180051d61  mov     rcx, [rsp+4E0h+hKey]; hKey
0x180051d66  lea     rax, [rsp+4E0h+cValues]
0x180051d6b  mov     [rsp+4E0h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180051d70  xor     r9d, r9d; lpReserved
0x180051d73  mov     [rsp+4E0h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x180051d78  xor     r8d, r8d; lpcchClass
0x180051d7b  mov     [rsp+4E0h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x180051d80  xor     edx, edx; lpClass
0x180051d82  mov     [rsp+4E0h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x180051d87  mov     [rsp+4E0h+lpcValues], rax; lpcValues
0x180051d8c  mov     [rsp+4E0h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x180051d91  mov     [rsp+4E0h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x180051d96  mov     [rsp+4E0h+lpcSubKeys], r15; lpcSubKeys
0x180051d9b  mov     [rsp+4E0h+cValues], r15d
0x180051da0  call    cs:__imp_RegQueryInfoKeyW
0x180051da7  nop     dword ptr [rax+rax+00h]
0x180051dac  mov     ecx, [rsp+4E0h+cValues]
0x180051db0  mov     [rdi+2Ch], ecx
0x180051db3  shl     ecx, 4; Size
0x180051db6  call    ?svsutil_AllocZ@@YAPEAXKPEAX@Z; svsutil_AllocZ(ulong,void *)
0x180051dbb  mov     [rdi+30h], rax
0x180051dbf  test    rax, rax
0x180051dc2  jnz     short loc_180051DC9
0x180051dc4  mov     esi, r15d
0x180051dc7  jmp     short loc_180051DF1
0x180051dc9  test    ebx, ebx
0x180051dcb  jz      short loc_180051E02
0x180051dcd  lea     rcx, Src; "*"
0x180051dd4  call    ?MySzDupW@@YAPEAGPEBGH@Z; MySzDupW(ushort const *,int)
0x180051dd9  mov     rcx, [rdi+30h]
0x180051ddd  mov     [rcx], rax
0x180051de0  lea     rcx, [rbp+3E0h+Data]; Src
0x180051de4  call    ?MySzDupW@@YAPEAGPEBGH@Z; MySzDupW(ushort const *,int)
0x180051de9  mov     rcx, [rdi+30h]
0x180051ded  mov     [rcx+8], rax
0x180051df1  lea     rcx, [rsp+4E0h+hKey]; this
0x180051df6  call    ??1CReg@@QEAA@XZ; CReg::~CReg(void)
0x180051dfb  mov     eax, esi
0x180051dfd  jmp     loc_180051EF0
0x180051e02  mov     r14d, r15d
0x180051e05  cmp     [rdi+2Ch], r15d
0x180051e09  jle     short loc_180051DF1
0x180051e0b  mov     rcx, [rsp+4E0h+hKey]; hKey
0x180051e10  mov     [rbp+3E0h+cchValueName], 105h
0x180051e17  mov     [rbp+3E0h+Type], r15d
0x180051e1b  test    rcx, rcx
0x180051e1e  jz      loc_180051ED3
0x180051e24  mov     edx, [rsp+4E0h+dwIndex]; dwIndex
0x180051e28  lea     r9, [rbp+3E0h+cchValueName]; lpcchValueName
0x180051e2c  lea     r8, [rbp+3E0h+ValueName]; lpValueName
0x180051e33  mov     [rsp+4E0h+cValues], 20Ah
0x180051e3b  lea     eax, [rdx+1]
0x180051e3e  mov     [rsp+4E0h+dwIndex], eax
0x180051e42  lea     rax, [rsp+4E0h+cValues]
0x180051e47  mov     [rsp+4E0h+lpcValues], rax; lpcbData
0x180051e4c  lea     rax, [rbp+3E0h+Data]
0x180051e50  mov     [rsp+4E0h+lpcbMaxClassLen], rax; lpData
0x180051e55  lea     rax, [rbp+3E0h+Type]
0x180051e59  mov     [rsp+4E0h+lpcbMaxSubKeyLen], rax; lpType
0x180051e5e  mov     [rsp+4E0h+lpcSubKeys], r15; lpReserved
0x180051e63  call    cs:__imp_RegEnumValueW
0x180051e6a  nop     dword ptr [rax+rax+00h]
0x180051e6f  test    eax, eax
0x180051e71  jnz     short loc_180051ED3
0x180051e73  cmp     [rbp+3E0h+ValueName], r15w
0x180051e7b  jz      short loc_180051EA4
0x180051e7d  cmp     word ptr [rbp+3E0h+Data], r15w
0x180051e82  jz      short loc_180051EA4
0x180051e84  lea     rcx, [rbp+3E0h+ValueName]; Src
0x180051e8b  call    ?MySzDupW@@YAPEAGPEBGH@Z; MySzDupW(ushort const *,int)
0x180051e90  mov     rcx, [rdi+30h]
0x180051e94  movsxd  rbx, r14d
0x180051e97  add     rbx, rbx
0x180051e9a  mov     [rcx+rbx*8], rax
0x180051e9e  lea     rcx, [rbp+3E0h+Data]
0x180051ea2  jmp     short loc_180051EC5
0x180051ea4  lea     rcx, Format; Src
0x180051eab  call    ?MySzDupW@@YAPEAGPEBGH@Z; MySzDupW(ushort const *,int)
0x180051eb0  mov     rcx, [rdi+30h]
0x180051eb4  movsxd  rbx, r14d
0x180051eb7  add     rbx, rbx
0x180051eba  mov     [rcx+rbx*8], rax
0x180051ebe  lea     rcx, Format; Src
0x180051ec5  call    ?MySzDupW@@YAPEAGPEBGH@Z; MySzDupW(ushort const *,int)
0x180051eca  mov     rcx, [rdi+30h]
0x180051ece  mov     [rcx+rbx*8+8], rax
0x180051ed3  add     r14d, esi
0x180051ed6  cmp     r14d, [rdi+2Ch]
0x180051eda  jl      loc_180051E0B
0x180051ee0  jmp     loc_180051DF1
0x180051ee5  mov     [rdi+2Ch], r15d
0x180051ee9  call    ??1CReg@@QEAA@XZ; CReg::~CReg(void)
0x180051eee  xor     eax, eax
0x180051ef0  mov     rcx, [rbp+3E0h+var_30]
0x180051ef7  xor     rcx, rsp; StackCookie
0x180051efa  call    __security_check_cookie
0x180051eff  mov     rbx, [rsp+4E0h+arg_0]
0x180051f07  add     rsp, 4C0h
0x180051f0e  pop     r15
0x180051f10  pop     r14
0x180051f12  pop     rdi
0x180051f13  pop     rsi
0x180051f14  pop     rbp
0x180051f15  retn
```
