# IERegQueryInfoKey(ushort const *,int,ulong *,ulong *)

- ea: `0x18000c570`
- end: `0x18000c7c5`
- name: `?IERegQueryInfoKey@@YAJPEBGHPEAK1@Z`
- size: `597`
- prototype: `__int64 __fastcall(PCNZWCH lpString1, int, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800368ec`

## callees

- `0x18000c570`
- `0x18001018c`
- `0x180013d00`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c74f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c74f`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000c706`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000c706`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c6a4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c6a4`

## pseudocode

```c
__int64 __fastcall IERegQueryInfoKey(PCNZWCH lpString1, int a2, unsigned int *a3, unsigned int *a4)
{
  PCNZWCH v7; // rax
  __int64 v8; // r10
  struct IERegCacheEntry *v9; // rsi
  unsigned int v10; // r15d
  int v11; // ebp
  unsigned int v12; // edi
  const WCHAR *v13; // rdx
  bool v14; // cf
  LSTATUS v15; // eax
  unsigned int v16; // edx
  HKEY phkResult; // [rsp+A0h] [rbp+8h] BYREF
  int v19; // [rsp+A8h] [rbp+10h]

  v19 = a2;
  phkResult = 0;
  IERegInit();
  if ( !lpString1 )
    return 2147942487LL;
  v7 = lpString1;
  v8 = 260;
  do
  {
    if ( !*v7 )
      break;
    ++v7;
    --v8;
  }
  while ( v8 );
  v9 = (struct IERegCacheEntry *)((260 - v8) & -(__int64)(v8 != 0));
  if ( !v8 )
    return 2147942487LL;
  v10 = 0;
  v11 = 0;
  v12 = 0;
  while ( !v11 )
  {
    if ( v19 == *((_DWORD *)&g_IERegPolicyKeyCache + 10 * v12)
      && v9 >= *(&g_IERegPolicyKeyCache + 5 * v12 + 2)
      && CompareStringW_0(
           0x7Fu,
           1u,
           lpString1,
           *((_DWORD *)&g_IERegPolicyKeyCache + 10 * v12 + 4),
           (PCNZWCH)*(&g_IERegPolicyKeyCache + 5 * v12 + 1),
           *((_DWORD *)&g_IERegPolicyKeyCache + 10 * v12 + 4)) == 2 )
    {
      if ( *((_DWORD *)&g_IERegPolicyKeyCache + 10 * v12 + 6) )
      {
        if ( v9 == *(&g_IERegPolicyKeyCache + 5 * v12 + 2) || !*((_DWORD *)&g_IERegPolicyKeyCache + 10 * v12 + 7) )
        {
          v10 = v12;
          v11 = 1;
        }
      }
      else
      {
        v13 = (const WCHAR *)*(&g_IERegPolicyKeyCache + 5 * v12 + 1);
        v14 = *((_DWORD *)&g_IERegPolicyKeyCache + 10 * v12) != 0;
        phkResult = 0;
        v15 = RegOpenKeyExW((HKEY)(-(__int64)v14 - 2147483646), v13, 0, 1u, &phkResult);
        if ( v15 == 2
          || !v15
          && !RegQueryInfoKeyW(
                phkResult,
                0,
                0,
                0,
                (LPDWORD)&g_IERegPolicyKeyCache + 10 * v12 + 7,
                0,
                0,
                (LPDWORD)&qword_1800591F0[5 * v12 + 2],
                0,
                0,
                0,
                0) )
        {
          *((_DWORD *)&g_IERegPolicyKeyCache + 10 * v12 + 6) = 1;
          if ( v9 == *(&g_IERegPolicyKeyCache + 5 * v12 + 2) || !*((_DWORD *)&g_IERegPolicyKeyCache + 10 * v12 + 7) )
          {
            v10 = v12;
            v11 = 1;
          }
        }
        if ( phkResult )
          RegCloseKey(phkResult);
      }
    }
    if ( ++v12 >= 0xA )
    {
      v16 = -2147467259;
      if ( !v11 )
        return v16;
      break;
    }
  }
  v16 = 0;
  if ( a3 )
    *a3 = *((_DWORD *)&g_IERegPolicyKeyCache + 10 * v10 + 7);
  if ( a4 )
  {
    if ( v9 == *(&g_IERegPolicyKeyCache + 5 * v10 + 2) )
      *a4 = *((_DWORD *)&g_IERegPolicyKeyCache + 10 * v10 + 8);
    else
      *a4 = 0;
  }
  return v16;
}

```

## disassembly

```asm
0x18000c570  mov     rax, rsp
0x18000c573  mov     [rax+18h], rbx
0x18000c577  mov     [rax+10h], edx
0x18000c57a  push    rbp
0x18000c57b  push    rsi
0x18000c57c  push    rdi
0x18000c57d  push    r12
0x18000c57f  push    r13
0x18000c581  push    r14
0x18000c583  push    r15
0x18000c585  sub     rsp, 60h
0x18000c589  mov     r14, r9
0x18000c58c  mov     qword ptr [rax+8], 0
0x18000c594  mov     r13, r8
0x18000c597  mov     r12, rcx
0x18000c59a  call    IERegInit
0x18000c59f  xor     r8d, r8d
0x18000c5a2  test    r12, r12
0x18000c5a5  jz      loc_18000C7A8
0x18000c5ab  mov     r11d, 104h
0x18000c5b1  mov     rax, r12
0x18000c5b4  mov     r10d, r11d
0x18000c5b7  cmp     [rax], r8w
0x18000c5bb  jz      short loc_18000C5C7
0x18000c5bd  add     rax, 2
0x18000c5c1  sub     r10, 1
0x18000c5c5  jnz     short loc_18000C5B7
0x18000c5c7  sub     r11, r10
0x18000c5ca  mov     rax, r10
0x18000c5cd  neg     rax
0x18000c5d0  sbb     rsi, rsi
0x18000c5d3  and     rsi, r11
0x18000c5d6  test    r10, r10
0x18000c5d9  jz      loc_18000C7A8
0x18000c5df  mov     r15d, r8d
0x18000c5e2  lea     r10, ?g_IERegPolicyKeyCache@@3PAUIERegCacheEntry@@A; IERegCacheEntry near * g_IERegPolicyKeyCache
0x18000c5e9  mov     ebp, r8d
0x18000c5ec  mov     edi, r8d
0x18000c5ef  test    ebp, ebp
0x18000c5f1  jnz     loc_18000C773
0x18000c5f7  mov     eax, edi
0x18000c5f9  lea     rbx, [rax+rax*4]
0x18000c5fd  mov     eax, [rsp+98h+arg_8]
0x18000c604  cmp     eax, [r10+rbx*8]
0x18000c608  jnz     loc_18000C75F
0x18000c60e  cmp     rsi, [r10+rbx*8+10h]
0x18000c613  jb      loc_18000C75F
0x18000c619  mov     r9d, [r10+rbx*8+10h]; cchCount1
0x18000c61e  lea     edx, [rbp+1]; dwCmpFlags
0x18000c621  mov     rax, [r10+rbx*8+8]
0x18000c626  lea     ecx, [rbp+7Fh]; Locale
0x18000c629  mov     [rsp+98h+cchCount2], r9d; cchCount2
0x18000c62e  mov     r8, r12; lpString1
0x18000c631  mov     [rsp+98h+lpString2], rax; lpString2
0x18000c636  call    CompareStringW_0
0x18000c63b  xor     r8d, r8d; ulOptions
0x18000c63e  lea     r10, ?g_IERegPolicyKeyCache@@3PAUIERegCacheEntry@@A; IERegCacheEntry near * g_IERegPolicyKeyCache
0x18000c645  cmp     eax, 2
0x18000c648  jnz     loc_18000C75F
0x18000c64e  cmp     [r10+rbx*8+18h], r8d
0x18000c653  jz      short loc_18000C674
0x18000c655  cmp     rsi, [r10+rbx*8+10h]
0x18000c65a  jz      short loc_18000C667
0x18000c65c  cmp     [r10+rbx*8+1Ch], r8d
0x18000c661  jnz     loc_18000C75F
0x18000c667  mov     r15d, edi
0x18000c66a  mov     ebp, 1
0x18000c66f  jmp     loc_18000C75F
0x18000c674  mov     eax, [r10+rbx*8]
0x18000c678  mov     r9d, 1; samDesired
0x18000c67e  mov     rdx, [r10+rbx*8+8]; lpSubKey
0x18000c683  neg     eax
0x18000c685  lea     rax, [rsp+98h+phkResult]
0x18000c68d  mov     [rsp+98h+phkResult], r8
0x18000c695  sbb     rcx, rcx
0x18000c698  mov     [rsp+98h+lpString2], rax; phkResult
0x18000c69d  add     rcx, 0FFFFFFFF80000002h; hKey
0x18000c6a4  call    cs:__imp_RegOpenKeyExW
0x18000c6aa  xor     r8d, r8d; lpcchClass
0x18000c6ad  cmp     eax, 2
0x18000c6b0  jz      short loc_18000C713
0x18000c6b2  test    eax, eax
0x18000c6b4  jnz     loc_18000C73B
0x18000c6ba  mov     [rsp+98h+lpftLastWriteTime], r8; lpftLastWriteTime
0x18000c6bf  lea     rcx, ?g_IERegPolicyKeyCache@@3PAUIERegCacheEntry@@A; IERegCacheEntry near * g_IERegPolicyKeyCache
0x18000c6c6  mov     [rsp+98h+lpcbSecurityDescriptor], r8; lpcbSecurityDescriptor
0x18000c6cb  lea     rax, [rcx+20h]
0x18000c6cf  mov     [rsp+98h+lpcbMaxValueLen], r8; lpcbMaxValueLen
0x18000c6d4  lea     rcx, [rcx+rbx*8]
0x18000c6d8  mov     [rsp+98h+lpcbMaxValueNameLen], r8; lpcbMaxValueNameLen
0x18000c6dd  lea     rax, [rax+rbx*8]
0x18000c6e1  mov     [rsp+98h+lpcValues], rax; lpcValues
0x18000c6e6  add     rcx, 1Ch
0x18000c6ea  mov     [rsp+98h+lpcbMaxClassLen], r8; lpcbMaxClassLen
0x18000c6ef  xor     r9d, r9d; lpReserved
0x18000c6f2  mov     qword ptr [rsp+98h+cchCount2], r8; lpcbMaxSubKeyLen
0x18000c6f7  xor     edx, edx; lpClass
0x18000c6f9  mov     [rsp+98h+lpString2], rcx; lpcSubKeys
0x18000c6fe  mov     rcx, [rsp+98h+phkResult]; hKey
0x18000c706  call    cs:__imp_RegQueryInfoKeyW
0x18000c70c  xor     r8d, r8d
0x18000c70f  test    eax, eax
0x18000c711  jnz     short loc_18000C73B
0x18000c713  lea     r10, ?g_IERegPolicyKeyCache@@3PAUIERegCacheEntry@@A; IERegCacheEntry near * g_IERegPolicyKeyCache
0x18000c71a  mov     dword ptr [r10+rbx*8+18h], 1
0x18000c723  cmp     rsi, [r10+rbx*8+10h]
0x18000c728  jz      short loc_18000C731
0x18000c72a  cmp     [r10+rbx*8+1Ch], r8d
0x18000c72f  jnz     short loc_18000C742
0x18000c731  mov     r15d, edi
0x18000c734  mov     ebp, 1
0x18000c739  jmp     short loc_18000C742
0x18000c73b  lea     r10, ?g_IERegPolicyKeyCache@@3PAUIERegCacheEntry@@A; IERegCacheEntry near * g_IERegPolicyKeyCache
0x18000c742  mov     rcx, [rsp+98h+phkResult]; hKey
0x18000c74a  test    rcx, rcx
0x18000c74d  jz      short loc_18000C75F
0x18000c74f  call    cs:__imp_RegCloseKey
0x18000c755  xor     r8d, r8d
0x18000c758  lea     r10, ?g_IERegPolicyKeyCache@@3PAUIERegCacheEntry@@A; IERegCacheEntry near * g_IERegPolicyKeyCache
0x18000c75f  inc     edi
0x18000c761  cmp     edi, 0Ah
0x18000c764  jb      loc_18000C5EF
0x18000c76a  mov     edx, 80004005h
0x18000c76f  test    ebp, ebp
0x18000c771  jz      short loc_18000C7A4
0x18000c773  mov     eax, r15d
0x18000c776  mov     edx, r8d
0x18000c779  lea     rcx, [rax+rax*4]
0x18000c77d  test    r13, r13
0x18000c780  jz      short loc_18000C78B
0x18000c782  mov     eax, [r10+rcx*8+1Ch]
0x18000c787  mov     [r13+0], eax
0x18000c78b  test    r14, r14
0x18000c78e  jz      short loc_18000C7A4
0x18000c790  cmp     rsi, [r10+rcx*8+10h]
0x18000c795  jnz     short loc_18000C7A1
0x18000c797  mov     eax, [r10+rcx*8+20h]
0x18000c79c  mov     [r14], eax
0x18000c79f  jmp     short loc_18000C7A4
0x18000c7a1  mov     [r14], r8d
0x18000c7a4  mov     eax, edx
0x18000c7a6  jmp     short loc_18000C7AD
0x18000c7a8  mov     eax, 80070057h
0x18000c7ad  mov     rbx, [rsp+98h+arg_10]
0x18000c7b5  add     rsp, 60h
0x18000c7b9  pop     r15
0x18000c7bb  pop     r14
0x18000c7bd  pop     r13
0x18000c7bf  pop     r12
0x18000c7c1  pop     rdi
0x18000c7c2  pop     rsi
0x18000c7c3  pop     rbp
0x18000c7c4  retn
```
