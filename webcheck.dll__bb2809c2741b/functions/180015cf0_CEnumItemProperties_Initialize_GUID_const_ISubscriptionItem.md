# CEnumItemProperties::Initialize(_GUID const *,ISubscriptionItem *)

- ea: `0x180015cf0`
- end: `0x180015f50`
- name: `?Initialize@CEnumItemProperties@@QEAAJPEBU_GUID@@PEAUISubscriptionItem@@@Z`
- size: `608`
- prototype: `int(CEnumItemProperties *__hidden this, const struct _GUID *, struct ISubscriptionItem *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, service_task`

## callers

- `0x180015bc0`

## callees

- `0x180003950`
- `0x180015cf0`
- `0x180016570`
- `0x180019948`
- `0x18001ba08`
- `0x18001ba40`

## import_xrefs

- `SHLWAPI!SHEnumValueW` at `0x180015e43`
- `SHLWAPI!SHEnumValueW` at `0x180015e43`
- `SHLWAPI!StrCmpW` at `0x180015e65`
- `SHLWAPI!StrCmpW` at `0x180015e65`
- `ADVAPI32!RegCloseKey` at `0x180015f2d`
- `ADVAPI32!RegCloseKey` at `0x180015f2d`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180015d89`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180015d89`
- `ole32!CoTaskMemAlloc` at `0x180015eb3`
- `ole32!CoTaskMemAlloc` at `0x180015eb3`

## pseudocode

```c
__int64 __fastcall CEnumItemProperties::Initialize(
        CEnumItemProperties *this,
        const struct _GUID *a2,
        struct ISubscriptionItem *a3)
{
  int v4; // ebx
  SIZE_T v5; // rax
  WCHAR *v6; // rdi
  void *v7; // rax
  void *v8; // r14
  DWORD i; // r15d
  __int64 v10; // rax
  SIZE_T v11; // r12
  unsigned __int16 *v12; // rcx
  DWORD cbMaxValueLen; // [rsp+60h] [rbp-20h] BYREF
  DWORD pdwType; // [rsp+64h] [rbp-1Ch] BYREF
  DWORD pcbData; // [rsp+68h] [rbp-18h] BYREF
  DWORD pcchValueName; // [rsp+6Ch] [rbp-14h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-10h] BYREF
  struct ISubscriptionItem *cbMaxValueNameLen; // [rsp+D0h] [rbp+50h] BYREF
  DWORD cValues; // [rsp+D8h] [rbp+58h] BYREF

  cbMaxValueNameLen = a3;
  hKey = 0;
  v4 = -2147467259;
  if ( OpenItemKey(a2, 0, 0x20019u, &hKey) )
  {
    LODWORD(cbMaxValueNameLen) = 0;
    cbMaxValueLen = 0;
    cValues = 0;
    if ( RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, &cValues, (LPDWORD)&cbMaxValueNameLen, &cbMaxValueLen, 0, 0) )
    {
LABEL_26:
      RegCloseKey(hKey);
      return (unsigned int)v4;
    }
    v5 = 32LL * (cValues + 1);
    if ( !is_mul_ok(cValues + 1, 0x20u) )
      v5 = -1;
    *((_QWORD *)this + 3) = operator new(v5);
    LODWORD(cbMaxValueNameLen) = (_DWORD)cbMaxValueNameLen + 1;
    v6 = (WCHAR *)operator new(saturated_mul((unsigned int)cbMaxValueNameLen, 2u));
    v7 = operator new(cbMaxValueLen);
    v8 = v7;
    if ( *((_QWORD *)this + 3) && v7 && v6 )
    {
      v4 = 0;
      for ( i = 0; i < cValues; ++i )
      {
        pcbData = cbMaxValueLen;
        pcchValueName = (unsigned int)cbMaxValueNameLen;
        pdwType = 0;
        if ( SHEnumValueW(hKey, i, v6, &pcchValueName, &pdwType, v8, &pcbData) )
          goto LABEL_21;
        if ( *v6 && StrCmpW(v6, L"~SubsInfo") )
        {
          if ( pdwType != 3 )
          {
LABEL_21:
            v4 = -2147418113;
            break;
          }
          v4 = SignatureBlobToVariant(
                 (unsigned __int8 *)v8,
                 pcbData,
                 (struct tagVARIANT *)(*((_QWORD *)this + 3) + 32LL * *((unsigned int *)this + 4)));
          if ( v4 < 0 )
            break;
          v10 = -1;
          do
            ++v10;
          while ( v6[v10] );
          v11 = (unsigned int)(2 * v10 + 2);
          *(_QWORD *)(32LL * *((unsigned int *)this + 4) + *((_QWORD *)this + 3) + 24) = CoTaskMemAlloc(v11);
          v12 = *(unsigned __int16 **)(32LL * *((unsigned int *)this + 4) + *((_QWORD *)this + 3) + 24);
          if ( !v12 )
          {
            v4 = -2147024882;
            break;
          }
          StringCchCopyW(v12, v11 >> 1, v6);
          ++*((_DWORD *)this + 4);
        }
      }
    }
    else
    {
      v4 = -2147024882;
      if ( !v6 )
        goto LABEL_24;
    }
    operator delete(v6);
LABEL_24:
    if ( v8 )
      operator delete(v8);
    goto LABEL_26;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180015cf0  mov     [rsp-38h+arg_0], rbx
0x180015cf5  mov     [rsp-38h+cbMaxValueNameLen], r8
0x180015cfa  push    rbp
0x180015cfb  push    rsi
0x180015cfc  push    rdi
0x180015cfd  push    r12
0x180015cff  push    r13
0x180015d01  push    r14
0x180015d03  push    r15
0x180015d05  mov     rbp, rsp
0x180015d08  sub     rsp, 80h
0x180015d0f  mov     rax, rdx
0x180015d12  lea     r9, [rbp+hKey]; HKEY *
0x180015d16  mov     rsi, rcx
0x180015d19  xor     r13d, r13d
0x180015d1c  mov     rcx, rax; struct _GUID *
0x180015d1f  mov     [rbp+hKey], r13
0x180015d23  xor     edx, edx; int
0x180015d25  mov     r8d, 20019h; unsigned int
0x180015d2b  mov     ebx, 80004005h
0x180015d30  call    ?OpenItemKey@@YAHPEBU_GUID@@HKPEAPEAUHKEY__@@@Z; OpenItemKey(_GUID const *,int,ulong,HKEY__ * *)
0x180015d35  test    eax, eax
0x180015d37  jz      loc_180015F33
0x180015d3d  mov     rcx, [rbp+hKey]; hKey
0x180015d41  lea     rax, [rbp+cbMaxValueLen]
0x180015d45  mov     [rsp+80h+lpftLastWriteTime], r13; lpftLastWriteTime
0x180015d4a  xor     r9d, r9d; lpReserved
0x180015d4d  mov     [rsp+80h+lpcbSecurityDescriptor], r13; lpcbSecurityDescriptor
0x180015d52  xor     r8d, r8d; lpcchClass
0x180015d55  mov     [rsp+80h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x180015d5a  xor     edx, edx; lpClass
0x180015d5c  lea     rax, [rbp+cbMaxValueNameLen]
0x180015d60  mov     dword ptr [rbp+cbMaxValueNameLen], r13d
0x180015d64  mov     [rsp+80h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x180015d69  lea     rax, [rbp+cValues]
0x180015d6d  mov     [rsp+80h+lpcValues], rax; lpcValues
0x180015d72  mov     [rsp+80h+lpcbMaxClassLen], r13; lpcbMaxClassLen
0x180015d77  mov     [rsp+80h+lpcbMaxSubKeyLen], r13; lpcbMaxSubKeyLen
0x180015d7c  mov     [rsp+80h+lpcSubKeys], r13; lpcSubKeys
0x180015d81  mov     [rbp+cbMaxValueLen], r13d
0x180015d85  mov     [rbp+cValues], r13d
0x180015d89  call    cs:__imp_RegQueryInfoKeyW
0x180015d8f  test    eax, eax
0x180015d91  jnz     loc_180015F29
0x180015d97  mov     ecx, [rbp+cValues]
0x180015d9a  lea     eax, [r13+20h]
0x180015d9e  inc     ecx
0x180015da0  lea     r12, [r13-1]
0x180015da4  mul     rcx
0x180015da7  cmovb   rax, r12
0x180015dab  mov     rcx, rax; dwBytes
0x180015dae  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180015db3  mov     [rsi+18h], rax
0x180015db7  mov     eax, dword ptr [rbp+cbMaxValueNameLen]
0x180015dba  inc     eax
0x180015dbc  mov     ecx, eax
0x180015dbe  mov     dword ptr [rbp+cbMaxValueNameLen], eax
0x180015dc1  lea     eax, [r13+2]
0x180015dc5  mul     rcx
0x180015dc8  cmovb   rax, r12
0x180015dcc  mov     rcx, rax; dwBytes
0x180015dcf  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180015dd4  mov     ecx, [rbp+cbMaxValueLen]; dwBytes
0x180015dd7  mov     rdi, rax
0x180015dda  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180015ddf  mov     r14, rax
0x180015de2  cmp     [rsi+18h], r13
0x180015de6  jz      loc_180015F0A
0x180015dec  test    rax, rax
0x180015def  jz      loc_180015F0A
0x180015df5  test    rdi, rdi
0x180015df8  jz      loc_180015F0A
0x180015dfe  mov     ebx, r13d
0x180015e01  mov     r15d, r13d
0x180015e04  cmp     r15d, [rbp+cValues]
0x180015e08  jnb     loc_180015F14
0x180015e0e  mov     eax, [rbp+cbMaxValueLen]
0x180015e11  lea     r9, [rbp+pcchValueName]; pcchValueName
0x180015e15  mov     rcx, [rbp+hKey]; hkey
0x180015e19  mov     r8, rdi; pszValueName
0x180015e1c  mov     [rbp+pcbData], eax
0x180015e1f  mov     edx, r15d; dwIndex
0x180015e22  mov     eax, dword ptr [rbp+cbMaxValueNameLen]
0x180015e25  mov     [rbp+pcchValueName], eax
0x180015e28  lea     rax, [rbp+pcbData]
0x180015e2c  mov     [rsp+80h+lpcbMaxClassLen], rax; pcbData
0x180015e31  lea     rax, [rbp+pdwType]
0x180015e35  mov     [rsp+80h+lpcbMaxSubKeyLen], r14; pvData
0x180015e3a  mov     [rsp+80h+lpcSubKeys], rax; pdwType
0x180015e3f  mov     [rbp+pdwType], r13d
0x180015e43  call    cs:__imp_SHEnumValueW
0x180015e49  test    eax, eax
0x180015e4b  jnz     loc_180015F03
0x180015e51  cmp     r13w, [rdi]
0x180015e55  jz      loc_180015EF4
0x180015e5b  lea     rdx, ValueName; "~SubsInfo"
0x180015e62  mov     rcx, rdi; psz1
0x180015e65  call    cs:__imp_StrCmpW
0x180015e6b  test    eax, eax
0x180015e6d  jz      loc_180015EF4
0x180015e73  cmp     [rbp+pdwType], 3
0x180015e77  jnz     loc_180015F03
0x180015e7d  mov     r8d, [rsi+10h]
0x180015e81  mov     rcx, r14; unsigned __int8 *
0x180015e84  mov     edx, [rbp+pcbData]; unsigned int
0x180015e87  shl     r8, 5
0x180015e8b  add     r8, [rsi+18h]; struct tagVARIANT *
0x180015e8f  call    ?SignatureBlobToVariant@@YAJPEAEKPEAUtagVARIANT@@@Z; SignatureBlobToVariant(uchar *,ulong,tagVARIANT *)
0x180015e94  mov     ebx, eax
0x180015e96  test    eax, eax
0x180015e98  js      short loc_180015F14
0x180015e9a  mov     rax, r12
0x180015e9d  inc     rax
0x180015ea0  cmp     [rdi+rax*2], r13w
0x180015ea5  jnz     short loc_180015E9D
0x180015ea7  lea     eax, ds:2[rax*2]
0x180015eae  mov     ecx, eax; cb
0x180015eb0  mov     r12d, eax
0x180015eb3  call    cs:__imp_CoTaskMemAlloc
0x180015eb9  mov     r8d, [rsi+10h]
0x180015ebd  mov     rcx, [rsi+18h]
0x180015ec1  shl     r8, 5
0x180015ec5  mov     [r8+rcx+18h], rax
0x180015eca  mov     ecx, [rsi+10h]
0x180015ecd  mov     rax, [rsi+18h]
0x180015ed1  shl     rcx, 5
0x180015ed5  mov     rcx, [rcx+rax+18h]; unsigned __int16 *
0x180015eda  test    rcx, rcx
0x180015edd  jz      short loc_180015EFC
0x180015edf  shr     r12, 1
0x180015ee2  mov     r8, rdi; unsigned __int16 *
0x180015ee5  mov     rdx, r12; unsigned __int64
0x180015ee8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180015eed  inc     dword ptr [rsi+10h]
0x180015ef0  or      r12, 0FFFFFFFFFFFFFFFFh
0x180015ef4  inc     r15d
0x180015ef7  jmp     loc_180015E04
0x180015efc  mov     ebx, 8007000Eh
0x180015f01  jmp     short loc_180015F14
0x180015f03  mov     ebx, 8000FFFFh
0x180015f08  jmp     short loc_180015F14
0x180015f0a  mov     ebx, 8007000Eh
0x180015f0f  test    rdi, rdi
0x180015f12  jz      short loc_180015F1C
0x180015f14  mov     rcx, rdi; lpMem
0x180015f17  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180015f1c  test    r14, r14
0x180015f1f  jz      short loc_180015F29
0x180015f21  mov     rcx, r14; lpMem
0x180015f24  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180015f29  mov     rcx, [rbp+hKey]; hKey
0x180015f2d  call    cs:__imp_RegCloseKey
0x180015f33  mov     eax, ebx
0x180015f35  mov     rbx, [rsp+80h+arg_0]
0x180015f3d  add     rsp, 80h
0x180015f44  pop     r15
0x180015f46  pop     r14
0x180015f48  pop     r13
0x180015f4a  pop     r12
0x180015f4c  pop     rdi
0x180015f4d  pop     rsi
0x180015f4e  pop     rbp
0x180015f4f  retn
```
