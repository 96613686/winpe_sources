# SecpReadPackageList(ulong *,ushort * * *,void * *,_FILETIME *)

- ea: `0x18000eeb0`
- end: `0x18000f0fe`
- name: `?SecpReadPackageList@@YAJPEAKPEAPEAPEAGPEAPEAXPEAU_FILETIME@@@Z`
- size: `590`
- prototype: `int(unsigned int *, unsigned __int16 ***, void **, struct _FILETIME *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800070d0`
- `0x18001caa0`

## callees

- `0x18000eeb0`
- `0x18000f104`
- `0x180022047`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000f0d1`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000f0d1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000efac`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f05c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f06d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f0e0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000efac`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f05c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f06d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f0e0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000ef3f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000efa0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000ef3f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000efa0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ef08`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ef08`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000efd0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f077`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000efd0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f077`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000ef6a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000eff9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000ef6a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000eff9`

## string_xrefs

- `0x18000ef38`: `SecurityProviders`
- `0x18000ef91`: `SecurityProviders`
- `0x18000eee5`: `System\CurrentControlSet\Control\SecurityProviders`

## pseudocode

```c
__int64 __fastcall SecpReadPackageList(unsigned int *a1, unsigned __int16 ***a2, BYTE **a3, struct _FILETIME *a4)
{
  unsigned int v4; // esi
  LSTATUS v9; // ebx
  BYTE *v10; // rdi
  __int64 v11; // r14
  LSTATUS v12; // ebx
  DWORD i; // ecx
  unsigned __int16 *v15; // rcx
  unsigned __int16 *v16; // rdx
  unsigned __int16 *v17; // rdx
  unsigned __int16 **v18; // rbx
  unsigned __int16 *v19; // rax
  unsigned __int16 *v20; // rdx
  __int64 v21; // r14
  unsigned int v22; // ebx
  unsigned __int16 *v23; // rcx
  HKEY hKey; // [rsp+60h] [rbp-10h] BYREF
  unsigned __int16 *v25; // [rsp+68h] [rbp-8h] BYREF
  DWORD cbData; // [rsp+B0h] [rbp+40h] BYREF
  DWORD Type; // [rsp+B8h] [rbp+48h] BYREF

  v4 = 0;
  *a1 = 0;
  *a2 = 0;
  hKey = 0;
  Type = 0;
  cbData = 0;
  v25 = 0;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\SecurityProviders", 0, 0x20019u, &hKey) )
    return 0;
  if ( a4 )
    RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, a4);
  v9 = RegQueryValueExW(hKey, L"SecurityProviders", 0, &Type, 0, &cbData);
  if ( v9 )
  {
    RegCloseKey(hKey);
    return v9 != 2 ? 0x80090307 : 0;
  }
  if ( Type != 1 )
  {
    RegCloseKey(hKey);
    return 0;
  }
  if ( cbData <= 2 )
  {
    v22 = 0;
    goto LABEL_24;
  }
  v10 = (BYTE *)LocalAlloc(0, 2 * cbData);
  if ( !v10 )
  {
    v22 = -2146893056;
LABEL_24:
    RegCloseKey(hKey);
    return v22;
  }
  v11 = cbData;
  v12 = RegQueryValueExW(hKey, L"SecurityProviders", 0, &Type, v10, &cbData);
  RegCloseKey(hKey);
  if ( !v12 )
  {
    for ( i = 0; i < cbData >> 1; ++i )
    {
      if ( !*(_WORD *)&v10[2 * i] )
      {
        memcpy_0(&v10[v11], v10, cbData);
        v15 = (unsigned __int16 *)&v10[v11];
        while ( LocalWcsTok(v15, v16, &v25) )
        {
          v15 = v25;
          ++v4;
        }
        v18 = (unsigned __int16 **)LocalAlloc(0, 8LL * v4);
        if ( !v18 )
        {
          LocalFree(v10);
          return 2148074240LL;
        }
        v19 = LocalWcsTok((unsigned __int16 *)v10, v17, &v25);
        v21 = 0;
        while ( v19 )
        {
          v23 = v25;
          v18[v21] = v19;
          v21 = (unsigned int)(v21 + 1);
          v19 = LocalWcsTok(v23, v20, &v25);
        }
        *a1 = v4;
        *a2 = v18;
        *a3 = v10;
        return 0;
      }
    }
  }
  LocalFree(v10);
  return 2148074247LL;
}

```

## disassembly

```asm
0x18000eeb0  mov     [rsp-38h+arg_10], rbx
0x18000eeb5  push    rbp
0x18000eeb6  push    rsi
0x18000eeb7  push    rdi
0x18000eeb8  push    r12
0x18000eeba  push    r13
0x18000eebc  push    r14
0x18000eebe  push    r15
0x18000eec0  mov     rbp, rsp
0x18000eec3  sub     rsp, 70h
0x18000eec7  xor     esi, esi
0x18000eec9  lea     rax, [rbp+hKey]
0x18000eecd  mov     [rcx], esi
0x18000eecf  mov     rbx, r9
0x18000eed2  mov     [rdx], rsi
0x18000eed5  mov     r13, r8
0x18000eed8  mov     r15, rdx
0x18000eedb  mov     [rbp+hKey], rsi
0x18000eedf  mov     r12, rcx
0x18000eee2  mov     [rbp+Type], esi
0x18000eee5  lea     rdx, aSystemCurrentc_3; "System\\CurrentControlSet\\Control\\Sec"...
0x18000eeec  mov     [rbp+cbData], esi
0x18000eeef  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000eef6  mov     [rbp+var_8], rsi
0x18000eefa  mov     r9d, 20019h; samDesired
0x18000ef00  mov     [rsp+70h+phkResult], rax; phkResult
0x18000ef05  xor     r8d, r8d; ulOptions
0x18000ef08  call    cs:__imp_RegOpenKeyExW
0x18000ef0e  test    eax, eax
0x18000ef10  jnz     loc_18000F026
0x18000ef16  test    rbx, rbx
0x18000ef19  jnz     loc_18000F09D
0x18000ef1f  mov     rcx, [rbp+hKey]; hKey
0x18000ef23  lea     rax, [rbp+cbData]
0x18000ef27  mov     [rsp+70h+lpcbData], rax; lpcbData
0x18000ef2c  lea     r9, [rbp+Type]; lpType
0x18000ef30  xor     r8d, r8d; lpReserved
0x18000ef33  mov     [rsp+70h+phkResult], rsi; lpData
0x18000ef38  lea     rdx, aSecurityprovid; "SecurityProviders"
0x18000ef3f  call    cs:__imp_RegQueryValueExW
0x18000ef45  mov     ebx, eax
0x18000ef47  test    eax, eax
0x18000ef49  jnz     loc_18000F0DC
0x18000ef4f  cmp     [rbp+Type], 1
0x18000ef53  jnz     loc_18000F058
0x18000ef59  mov     eax, [rbp+cbData]
0x18000ef5c  cmp     eax, 2
0x18000ef5f  jbe     loc_18000F0F7
0x18000ef65  lea     edx, [rax+rax]; uBytes
0x18000ef68  xor     ecx, ecx; uFlags
0x18000ef6a  call    cs:__imp_LocalAlloc
0x18000ef70  mov     rdi, rax
0x18000ef73  test    rax, rax
0x18000ef76  jz      loc_18000F064
0x18000ef7c  mov     rcx, [rbp+hKey]; hKey
0x18000ef80  lea     rax, [rbp+cbData]
0x18000ef84  mov     r14d, [rbp+cbData]
0x18000ef88  lea     r9, [rbp+Type]; lpType
0x18000ef8c  mov     [rsp+70h+lpcbData], rax; lpcbData
0x18000ef91  lea     rdx, aSecurityprovid; "SecurityProviders"
0x18000ef98  xor     r8d, r8d; lpReserved
0x18000ef9b  mov     [rsp+70h+phkResult], rdi; lpData
0x18000efa0  call    cs:__imp_RegQueryValueExW
0x18000efa6  mov     rcx, [rbp+hKey]; hKey
0x18000efaa  mov     ebx, eax
0x18000efac  call    cs:__imp_RegCloseKey
0x18000efb2  test    ebx, ebx
0x18000efb4  jnz     short loc_18000EFCD
0x18000efb6  mov     ecx, esi
0x18000efb8  mov     eax, [rbp+cbData]
0x18000efbb  shr     eax, 1
0x18000efbd  cmp     ecx, eax
0x18000efbf  jnb     short loc_18000EFCD
0x18000efc1  mov     eax, ecx
0x18000efc3  cmp     [rdi+rax*2], si
0x18000efc7  jz      short loc_18000F040
0x18000efc9  inc     ecx
0x18000efcb  jmp     short loc_18000EFB8
0x18000efcd  mov     rcx, rdi; hMem
0x18000efd0  call    cs:__imp_LocalFree
0x18000efd6  mov     eax, 80090307h
0x18000efdb  jmp     short loc_18000F028
0x18000efdd  mov     rcx, [rbp+var_8]; unsigned __int16 *
0x18000efe1  inc     esi
0x18000efe3  lea     r8, [rbp+var_8]; unsigned __int16 **
0x18000efe7  call    ?LocalWcsTok@@YAPEAGPEAG0PEAPEAG@Z; LocalWcsTok(ushort *,ushort *,ushort * *)
0x18000efec  test    rax, rax
0x18000efef  jnz     short loc_18000EFDD
0x18000eff1  mov     edx, esi
0x18000eff3  xor     ecx, ecx; uFlags
0x18000eff5  shl     rdx, 3; uBytes
0x18000eff9  call    cs:__imp_LocalAlloc
0x18000efff  mov     rbx, rax
0x18000f002  mov     rcx, rdi; unsigned __int16 *
0x18000f005  test    rax, rax
0x18000f008  jz      short loc_18000F077
0x18000f00a  lea     r8, [rbp+var_8]; unsigned __int16 **
0x18000f00e  call    ?LocalWcsTok@@YAPEAGPEAG0PEAPEAG@Z; LocalWcsTok(ushort *,ushort *,ushort * *)
0x18000f013  xor     r14d, r14d
0x18000f016  test    rax, rax
0x18000f019  jnz     short loc_18000F084
0x18000f01b  mov     [r12], esi
0x18000f01f  mov     [r15], rbx
0x18000f022  mov     [r13+0], rdi
0x18000f026  xor     eax, eax
0x18000f028  mov     rbx, [rsp+70h+arg_10]
0x18000f030  add     rsp, 70h
0x18000f034  pop     r15
0x18000f036  pop     r14
0x18000f038  pop     r13
0x18000f03a  pop     r12
0x18000f03c  pop     rdi
0x18000f03d  pop     rsi
0x18000f03e  pop     rbp
0x18000f03f  retn
0x18000f040  mov     r8d, [rbp+cbData]; Size
0x18000f044  lea     rbx, [r14+rdi]
0x18000f048  mov     rcx, rbx; void *
0x18000f04b  mov     rdx, rdi; Src
0x18000f04e  call    memcpy_0
0x18000f053  mov     rcx, rbx
0x18000f056  jmp     short loc_18000EFE3
0x18000f058  mov     rcx, [rbp+hKey]; hKey
0x18000f05c  call    cs:__imp_RegCloseKey
0x18000f062  jmp     short loc_18000F026
0x18000f064  mov     ebx, 80090300h
0x18000f069  mov     rcx, [rbp+hKey]; hKey
0x18000f06d  call    cs:__imp_RegCloseKey
0x18000f073  mov     eax, ebx
0x18000f075  jmp     short loc_18000F028
0x18000f077  call    cs:__imp_LocalFree
0x18000f07d  mov     eax, 80090300h
0x18000f082  jmp     short loc_18000F028
0x18000f084  mov     rcx, [rbp+var_8]; unsigned __int16 *
0x18000f088  lea     r8, [rbp+var_8]; unsigned __int16 **
0x18000f08c  mov     [rbx+r14*8], rax
0x18000f090  inc     r14d
0x18000f093  call    ?LocalWcsTok@@YAPEAGPEAG0PEAPEAG@Z; LocalWcsTok(ushort *,ushort *,ushort * *)
0x18000f098  jmp     loc_18000F016
0x18000f09d  mov     rcx, [rbp+hKey]; hKey
0x18000f0a1  xor     r9d, r9d; lpReserved
0x18000f0a4  mov     [rsp+70h+lpftLastWriteTime], rbx; lpftLastWriteTime
0x18000f0a9  xor     r8d, r8d; lpcchClass
0x18000f0ac  mov     [rsp+70h+lpcbSecurityDescriptor], rsi; lpcbSecurityDescriptor
0x18000f0b1  xor     edx, edx; lpClass
0x18000f0b3  mov     [rsp+70h+lpcbMaxValueLen], rsi; lpcbMaxValueLen
0x18000f0b8  mov     [rsp+70h+lpcbMaxValueNameLen], rsi; lpcbMaxValueNameLen
0x18000f0bd  mov     [rsp+70h+lpcValues], rsi; lpcValues
0x18000f0c2  mov     [rsp+70h+lpcbMaxClassLen], rsi; lpcbMaxClassLen
0x18000f0c7  mov     [rsp+70h+lpcbData], rsi; lpcbMaxSubKeyLen
0x18000f0cc  mov     [rsp+70h+phkResult], rsi; lpcSubKeys
0x18000f0d1  call    cs:__imp_RegQueryInfoKeyW
0x18000f0d7  jmp     loc_18000EF1F
0x18000f0dc  mov     rcx, [rbp+hKey]; hKey
0x18000f0e0  call    cs:__imp_RegCloseKey
0x18000f0e6  sub     ebx, 2
0x18000f0e9  neg     ebx
0x18000f0eb  sbb     eax, eax
0x18000f0ed  and     eax, 80090307h
0x18000f0f2  jmp     loc_18000F028
0x18000f0f7  mov     ebx, esi
0x18000f0f9  jmp     loc_18000F069
```
