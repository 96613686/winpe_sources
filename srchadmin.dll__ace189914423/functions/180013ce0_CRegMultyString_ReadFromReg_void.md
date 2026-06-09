# CRegMultyString::ReadFromReg(void)

- ea: `0x180013ce0`
- end: `0x180013f71`
- name: `?ReadFromReg@CRegMultyString@@QEAAJXZ`
- size: `657`
- prototype: `__int64 __fastcall(CRegMultyString *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180014738`

## callees

- `0x1800057a0`
- `0x1800061c0`
- `0x180013ce0`
- `0x18001a7fc`

## import_xrefs

- `SHLWAPI!SHStrDupW` at `0x180013ede`
- `SHLWAPI!SHStrDupW` at `0x180013f0b`
- `SHLWAPI!SHStrDupW` at `0x180013ede`
- `SHLWAPI!SHStrDupW` at `0x180013f0b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013f2f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013f38`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013f2f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013f38`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180013dc7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180013de2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180013dc7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180013de2`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180013d85`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180013d85`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180013d18`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180013d18`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180013eae`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180013eae`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CRegMultyString::ReadFromReg(CRegMultyString *this)
{
  LSTATUS v2; // eax
  int v3; // ebx
  DWORD *v4; // r13
  LSTATUS v5; // eax
  WCHAR *v6; // rdi
  BYTE *v7; // rsi
  unsigned __int64 v8; // rax
  SIZE_T v9; // rcx
  unsigned __int64 v10; // r15
  __int64 v11; // rax
  bool v12; // cf
  unsigned __int64 v13; // rax
  unsigned __int64 *v14; // rax
  _QWORD *v15; // rbx
  DWORD v16; // r15d
  LSTATUS v17; // eax
  __int64 v18; // r12
  unsigned __int64 v19; // rcx
  DWORD cchValueName[2]; // [rsp+60h] [rbp-18h] BYREF
  HKEY hKey[2]; // [rsp+68h] [rbp-10h] BYREF
  DWORD cbMaxValueNameLen; // [rsp+C0h] [rbp+48h] BYREF
  DWORD cbMaxValueLen; // [rsp+C8h] [rbp+50h] BYREF
  DWORD Type; // [rsp+D0h] [rbp+58h] BYREF
  unsigned __int64 cbData; // [rsp+D8h] [rbp+60h] BYREF

  hKey[0] = 0;
  v2 = RegOpenKeyExW(*((HKEY *)this + 4), *((LPCWSTR *)this + 1), 0, 0x20019u, hKey);
  v3 = v2;
  if ( v2 > 0 )
    v3 = (unsigned __int16)v2 | 0x80070000;
  if ( v3 >= 0 )
  {
    *(_DWORD *)this = 1;
    cbMaxValueNameLen = 0;
    cbMaxValueLen = 0;
    v4 = (DWORD *)((char *)this + 24);
    v5 = RegQueryInfoKeyW(hKey[0], 0, 0, 0, 0, 0, 0, (LPDWORD)this + 6, &cbMaxValueNameLen, &cbMaxValueLen, 0, 0);
    v3 = v5;
    if ( v5 > 0 )
      v3 = (unsigned __int16)v5 | 0x80070000;
    Type = 0;
    v6 = 0;
    v7 = 0;
    if ( v3 >= 0 )
    {
      v8 = 2LL * cbMaxValueNameLen;
      if ( v8 > 0xFFFFFFFF || (v9 = (unsigned int)(v8 + 2), (unsigned int)v9 < (unsigned int)v8) )
      {
        v3 = -2147024362;
      }
      else
      {
        v6 = (WCHAR *)CoTaskMemAlloc(v9);
        if ( v6 && (v7 = (BYTE *)CoTaskMemAlloc(cbMaxValueLen)) != 0 )
        {
          v10 = *v4;
          cbData = v10;
          v11 = 16 * v10;
          if ( !is_mul_ok(v10, 0x10u) )
            v11 = -1;
          v12 = __CFADD__(v11, 8);
          v13 = v11 + 8;
          if ( v12 )
            v13 = -1;
          v14 = (unsigned __int64 *)operator new(v13);
          *(_QWORD *)cchValueName = v14;
          if ( v14 )
          {
            *v14 = v10;
            v15 = v14 + 1;
            `eh vector constructor iterator'(
              v14 + 1,
              0x10u,
              (unsigned int)v10,
              (void (*)(void *))CRegMultyString::CStrRegValue::CStrRegValue,
              (void (*)(void *))CRegMultyString::CStrRegValue::~CStrRegValue);
          }
          else
          {
            v15 = 0;
          }
          *((_QWORD *)this + 2) = v15;
          if ( v15 )
          {
            v16 = 0;
            v3 = 0;
            do
            {
              if ( v16 >= *v4 )
                break;
              cchValueName[0] = cbMaxValueNameLen + 1;
              LODWORD(cbData) = cbMaxValueLen;
              v17 = RegEnumValueW(hKey[0], v16, v6, cchValueName, 0, &Type, v7, (LPDWORD)&cbData);
              v3 = v17;
              if ( v17 > 0 )
                v3 = (unsigned __int16)v17 | 0x80070000;
              if ( v3 >= 0 && Type == 1 )
              {
                v18 = 16LL * v16;
                v3 = SHStrDupW(v6, (LPWSTR *)(v18 + *((_QWORD *)this + 2)));
                if ( v3 >= 0 )
                {
                  v19 = (unsigned __int64)(unsigned int)cbData >> 1;
                  if ( *(_WORD *)&v7[2 * v19 - 2] )
                    *(_WORD *)&v7[2 * v19] = 0;
                  v3 = SHStrDupW((LPCWSTR)v7, (LPWSTR *)(v18 + *((_QWORD *)this + 2) + 8LL));
                }
              }
              ++v16;
            }
            while ( v3 >= 0 );
            goto LABEL_35;
          }
          v3 = -2147024888;
        }
        else
        {
          v3 = -2147024882;
        }
      }
    }
    *v4 = 0;
LABEL_35:
    CoTaskMemFree(v6);
    CoTaskMemFree(v7);
  }
  if ( ((v3 + 2147024894) & 0xFFFFFEFE) == 0 && v3 != -2147024638 )
    v3 = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(hKey);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180013ce0  push    rbp
0x180013ce2  push    rbx
0x180013ce3  push    rsi
0x180013ce4  push    rdi
0x180013ce5  push    r12
0x180013ce7  push    r13
0x180013ce9  push    r14
0x180013ceb  push    r15
0x180013ced  mov     rbp, rsp
0x180013cf0  sub     rsp, 78h
0x180013cf4  mov     r14, rcx
0x180013cf7  xor     r12d, r12d
0x180013cfa  mov     [rbp+hKey], r12
0x180013cfe  lea     rax, [rbp+hKey]
0x180013d02  mov     [rsp+78h+phkResult], rax; phkResult
0x180013d07  mov     r9d, 20019h; samDesired
0x180013d0d  xor     r8d, r8d; ulOptions
0x180013d10  mov     rdx, [rcx+8]; lpSubKey
0x180013d14  mov     rcx, [rcx+20h]; hKey
0x180013d18  call    cs:__imp_RegOpenKeyExW
0x180013d1e  mov     ebx, eax
0x180013d20  mov     edi, 80070000h
0x180013d25  test    eax, eax
0x180013d27  jle     short loc_180013D2E
0x180013d29  movzx   ebx, ax
0x180013d2c  or      ebx, edi
0x180013d2e  test    ebx, ebx
0x180013d30  js      loc_180013F3E
0x180013d36  mov     dword ptr [r14], 1
0x180013d3d  mov     [rbp+cbMaxValueNameLen], r12d
0x180013d41  mov     [rbp+cbMaxValueLen], r12d
0x180013d45  lea     r13, [r14+18h]
0x180013d49  mov     [rsp+78h+lpftLastWriteTime], r12; lpftLastWriteTime
0x180013d4e  mov     [rsp+78h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x180013d53  lea     rax, [rbp+cbMaxValueLen]
0x180013d57  mov     [rsp+78h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x180013d5c  lea     rax, [rbp+cbMaxValueNameLen]
0x180013d60  mov     [rsp+78h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x180013d65  mov     [rsp+78h+lpcValues], r13; lpcValues
0x180013d6a  mov     [rsp+78h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x180013d6f  mov     [rsp+78h+lpcbMaxSubKeyLen], r12; lpcbMaxSubKeyLen
0x180013d74  mov     [rsp+78h+phkResult], r12; lpcSubKeys
0x180013d79  xor     r9d, r9d; lpReserved
0x180013d7c  xor     r8d, r8d; lpcchClass
0x180013d7f  xor     edx, edx; lpClass
0x180013d81  mov     rcx, [rbp+hKey]; hKey
0x180013d85  call    cs:__imp_RegQueryInfoKeyW
0x180013d8b  mov     ebx, eax
0x180013d8d  test    eax, eax
0x180013d8f  jle     short loc_180013D96
0x180013d91  movzx   ebx, ax
0x180013d94  or      ebx, edi
0x180013d96  mov     [rbp+Type], r12d
0x180013d9a  mov     rdi, r12
0x180013d9d  mov     rsi, r12
0x180013da0  test    ebx, ebx
0x180013da2  js      loc_180013F28
0x180013da8  mov     eax, [rbp+cbMaxValueNameLen]
0x180013dab  add     rax, rax
0x180013dae  mov     ecx, 0FFFFFFFFh
0x180013db3  cmp     rax, rcx
0x180013db6  ja      loc_180013F23
0x180013dbc  lea     ecx, [rax+2]; cb
0x180013dbf  cmp     ecx, eax
0x180013dc1  jb      loc_180013F23
0x180013dc7  call    cs:__imp_CoTaskMemAlloc
0x180013dcd  mov     rdi, rax
0x180013dd0  test    rax, rax
0x180013dd3  jnz     short loc_180013DDF
0x180013dd5  mov     ebx, 8007000Eh
0x180013dda  jmp     loc_180013F28
0x180013ddf  mov     ecx, [rbp+cbMaxValueLen]; cb
0x180013de2  call    cs:__imp_CoTaskMemAlloc
0x180013de8  mov     rsi, rax
0x180013deb  test    rax, rax
0x180013dee  jz      short loc_180013DD5
0x180013df0  mov     r15d, [r13+0]
0x180013df4  mov     [rbp+cbData], r15
0x180013df8  mov     eax, 10h
0x180013dfd  mul     r15
0x180013e00  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180013e07  cmovb   rax, rcx
0x180013e0b  add     rax, 8
0x180013e0f  cmovb   rax, rcx
0x180013e13  mov     rcx, rax; unsigned __int64
0x180013e16  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180013e1b  mov     qword ptr [rbp+cchValueName], rax
0x180013e1f  test    rax, rax
0x180013e22  jz      short loc_180013E50
0x180013e24  mov     [rax], r15
0x180013e27  lea     rbx, [rax+8]
0x180013e2b  lea     rax, ??1CStrRegValue@CRegMultyString@@QEAA@XZ; CRegMultyString::CStrRegValue::~CStrRegValue(void)
0x180013e32  mov     [rsp+78h+phkResult], rax; void (*)(void *)
0x180013e37  lea     r9, ??0CStrRegValue@CRegMultyString@@QEAA@XZ; void (*)(void *)
0x180013e3e  mov     r8d, r15d; unsigned __int64
0x180013e41  mov     edx, 10h; unsigned __int64
0x180013e46  mov     rcx, rbx; void *
0x180013e49  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x180013e4e  jmp     short loc_180013E53
0x180013e50  mov     rbx, r12
0x180013e53  mov     [r14+10h], rbx
0x180013e57  test    rbx, rbx
0x180013e5a  jnz     short loc_180013E66
0x180013e5c  mov     ebx, 80070008h
0x180013e61  jmp     loc_180013F28
0x180013e66  mov     r15d, r12d
0x180013e69  mov     ebx, r12d
0x180013e6c  cmp     r15d, [r13+0]
0x180013e70  jnb     loc_180013F2C
0x180013e76  mov     eax, [rbp+cbMaxValueNameLen]
0x180013e79  inc     eax
0x180013e7b  mov     [rbp+cchValueName], eax
0x180013e7e  mov     eax, [rbp+cbMaxValueLen]
0x180013e81  mov     dword ptr [rbp+cbData], eax
0x180013e84  lea     rax, [rbp+cbData]
0x180013e88  mov     [rsp+78h+lpcValues], rax; lpcbData
0x180013e8d  mov     [rsp+78h+lpcbMaxClassLen], rsi; lpData
0x180013e92  lea     rax, [rbp+Type]
0x180013e96  mov     [rsp+78h+lpcbMaxSubKeyLen], rax; lpType
0x180013e9b  mov     [rsp+78h+phkResult], r12; lpReserved
0x180013ea0  lea     r9, [rbp+cchValueName]; lpcchValueName
0x180013ea4  mov     r8, rdi; lpValueName
0x180013ea7  mov     edx, r15d; dwIndex
0x180013eaa  mov     rcx, [rbp+hKey]; hKey
0x180013eae  call    cs:__imp_RegEnumValueW
0x180013eb4  mov     ebx, eax
0x180013eb6  test    eax, eax
0x180013eb8  jle     short loc_180013EC3
0x180013eba  movzx   ebx, ax
0x180013ebd  or      ebx, 80070000h
0x180013ec3  test    ebx, ebx
0x180013ec5  js      short loc_180013F16
0x180013ec7  cmp     [rbp+Type], 1
0x180013ecb  jnz     short loc_180013F16
0x180013ecd  mov     r12d, r15d
0x180013ed0  shl     r12, 4
0x180013ed4  mov     rdx, [r14+10h]
0x180013ed8  add     rdx, r12; ppwsz
0x180013edb  mov     rcx, rdi; psz
0x180013ede  call    cs:__imp_SHStrDupW
0x180013ee4  mov     ebx, eax
0x180013ee6  test    eax, eax
0x180013ee8  js      short loc_180013F13
0x180013eea  mov     ecx, dword ptr [rbp+cbData]
0x180013eed  shr     rcx, 1
0x180013ef0  xor     eax, eax
0x180013ef2  cmp     ax, [rsi+rcx*2-2]
0x180013ef7  jz      short loc_180013EFD
0x180013ef9  mov     [rsi+rcx*2], ax
0x180013efd  mov     rdx, [r14+10h]
0x180013f01  add     rdx, 8
0x180013f05  add     rdx, r12; ppwsz
0x180013f08  mov     rcx, rsi; psz
0x180013f0b  call    cs:__imp_SHStrDupW
0x180013f11  mov     ebx, eax
0x180013f13  xor     r12d, r12d
0x180013f16  inc     r15d
0x180013f19  test    ebx, ebx
0x180013f1b  jns     loc_180013E6C
0x180013f21  jmp     short loc_180013F2C
0x180013f23  mov     ebx, 80070216h
0x180013f28  mov     [r13+0], r12d
0x180013f2c  mov     rcx, rdi; pv
0x180013f2f  call    cs:__imp_CoTaskMemFree
0x180013f35  mov     rcx, rsi; pv
0x180013f38  call    cs:__imp_CoTaskMemFree
0x180013f3e  lea     eax, [rbx+7FF8FFFEh]
0x180013f44  test    eax, 0FFFFFEFEh
0x180013f49  jnz     short loc_180013F55
0x180013f4b  cmp     ebx, 80070102h
0x180013f51  cmovnz  ebx, r12d
0x180013f55  lea     rcx, [rbp+hKey]
0x180013f59  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180013f5e  mov     eax, ebx
0x180013f60  add     rsp, 78h
0x180013f64  pop     r15
0x180013f66  pop     r14
0x180013f68  pop     r13
0x180013f6a  pop     r12
0x180013f6c  pop     rdi
0x180013f6d  pop     rsi
0x180013f6e  pop     rbx
0x180013f6f  pop     rbp
0x180013f70  retn
```
