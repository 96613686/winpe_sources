# SHRestrictionLookup

- ea: `0x180001d60`
- end: `0x180001f2f`
- name: `SHRestrictionLookup`
- size: `463`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `reparse_path, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180001d60`
- `0x180012550`
- `0x180013066`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180001e1b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180001ef5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180001e1b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180001ef5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180001e38`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180001f14`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180001e38`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180001f14`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathCombineW` at `0x180001e78`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathCombineW` at `0x180001e78`
- `api-ms-win-shcore-registry-l1-1-0!SHGetValueW` at `0x180001eac`
- `api-ms-win-shcore-registry-l1-1-0!SHGetValueW` at `0x180001ee4`
- `api-ms-win-shcore-registry-l1-1-0!SHGetValueW` at `0x180001eac`
- `api-ms-win-shcore-registry-l1-1-0!SHGetValueW` at `0x180001ee4`
- `SHCORE!__imp_SHGlobalCounterGetValue` at `0x180001db1`
- `SHCORE!__imp_SHGlobalCounterGetValue` at `0x180001e26`
- `SHCORE!__imp_SHGlobalCounterGetValue` at `0x180001f00`
- `SHCORE!__imp_SHGlobalCounterGetValue` at `0x180001db1`
- `SHCORE!__imp_SHGlobalCounterGetValue` at `0x180001e26`
- `SHCORE!__imp_SHGlobalCounterGetValue` at `0x180001f00`

## pseudocode

```c
__int64 __fastcall SHRestrictionLookup(int a1, const WCHAR *a2, __int64 a3, unsigned int *a4, unsigned int a5, int *a6)
{
  __int64 i; // rdx
  __int64 v11; // r8
  __int64 result; // rax
  unsigned int *v13; // rbx
  int Value; // eax
  const WCHAR *v15; // rdi
  const WCHAR *v16; // rdx
  const WCHAR *v17; // r8
  unsigned int v18; // edi
  DWORD pcbData; // [rsp+30h] [rbp-268h] BYREF
  _DWORD pvData[3]; // [rsp+34h] [rbp-264h] BYREF
  WCHAR pszDest[264]; // [rsp+40h] [rbp-258h] BYREF

  if ( g_bDllTerminating )
    return 0;
  if ( *a6 != SHGlobalCounterGetValue(GLOBALCOUNTER_RESTRICTIONS) )
  {
    AcquireSRWLockExclusive(&g_csrwlockRestrictions);
    Value = SHGlobalCounterGetValue(GLOBALCOUNTER_RESTRICTIONS);
    if ( *a6 != Value )
    {
      *a6 = Value;
      memset_0(a4, 255, 4LL * a5);
    }
    ReleaseSRWLockExclusive(&g_csrwlockRestrictions);
  }
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    if ( (unsigned int)i >= a5 )
      return 0;
    v11 = a3 + 24 * i;
    if ( a1 == *(_DWORD *)v11 )
      break;
  }
  result = a4[i];
  v13 = &a4[i];
  if ( (_DWORD)result == -1 )
  {
    v15 = *(const WCHAR **)(v11 + 16);
    v16 = L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies";
    v17 = *(const WCHAR **)(v11 + 8);
    pvData[0] = 0;
    if ( a2 )
      v16 = a2;
    PathCombineW(pszDest, v16, v17);
    pcbData = 4;
    if ( SHGetValueW(HKEY_LOCAL_MACHINE, pszDest, v15, 0, pvData, &pcbData) )
    {
      pcbData = 4;
      SHGetValueW(HKEY_CURRENT_USER, pszDest, v15, 0, pvData, &pcbData);
    }
    v18 = pvData[0];
    AcquireSRWLockExclusive(&g_csrwlockRestrictions);
    if ( *a6 == SHGlobalCounterGetValue(GLOBALCOUNTER_RESTRICTIONS) )
      *v13 = v18;
    ReleaseSRWLockExclusive(&g_csrwlockRestrictions);
    return v18;
  }
  return result;
}

```

## disassembly

```asm
0x180001d60  push    rbp
0x180001d62  push    rsi
0x180001d63  push    rdi
0x180001d64  push    r12
0x180001d66  push    r14
0x180001d68  push    r15
0x180001d6a  sub     rsp, 268h
0x180001d71  mov     rax, cs:__security_cookie
0x180001d78  xor     rax, rsp
0x180001d7b  mov     [rsp+298h+var_48], rax
0x180001d83  mov     r15, [rsp+298h+arg_28]
0x180001d8b  xor     ebp, ebp
0x180001d8d  cmp     cs:?g_bDllTerminating@@3HA, ebp; int g_bDllTerminating
0x180001d93  mov     r14, r9
0x180001d96  mov     rsi, r8
0x180001d99  mov     r12, rdx
0x180001d9c  mov     edi, ecx
0x180001d9e  jnz     loc_180001F28
0x180001da4  mov     ecx, 5; id
0x180001da9  mov     [rsp+298h+var_38], rbx
0x180001db1  call    cs:__imp_SHGlobalCounterGetValue
0x180001db7  mov     ebx, [rsp+298h+arg_20]
0x180001dbe  cmp     [r15], eax
0x180001dc1  jnz     short loc_180001E14
0x180001dc3  xor     edx, edx
0x180001dc5  cmp     edx, ebx
0x180001dc7  jnb     loc_180001F21
0x180001dcd  lea     rcx, [rdx+rdx*2]
0x180001dd1  cmp     edi, [rsi+rcx*8]
0x180001dd4  lea     r8, [rsi+rcx*8]
0x180001dd8  jz      short loc_180001DDE
0x180001dda  inc     edx
0x180001ddc  jmp     short loc_180001DC5
0x180001dde  mov     eax, [r14+rdx*4]
0x180001de2  lea     rbx, [r14+rdx*4]
0x180001de6  cmp     eax, 0FFFFFFFFh
0x180001de9  jz      short loc_180001E59
0x180001deb  mov     rbx, [rsp+298h+var_38]
0x180001df3  mov     rcx, [rsp+298h+var_48]
0x180001dfb  xor     rcx, rsp; StackCookie
0x180001dfe  call    __security_check_cookie
0x180001e03  add     rsp, 268h
0x180001e0a  pop     r15
0x180001e0c  pop     r14
0x180001e0e  pop     r12
0x180001e10  pop     rdi
0x180001e11  pop     rsi
0x180001e12  pop     rbp
0x180001e13  retn
0x180001e14  lea     rcx, ?g_csrwlockRestrictions@@3VCSRWLock@@A; SRWLock
0x180001e1b  call    cs:__imp_AcquireSRWLockExclusive
0x180001e21  mov     ecx, 5; id
0x180001e26  call    cs:__imp_SHGlobalCounterGetValue
0x180001e2c  cmp     [r15], eax
0x180001e2f  jnz     short loc_180001E40
0x180001e31  lea     rcx, ?g_csrwlockRestrictions@@3VCSRWLock@@A; SRWLock
0x180001e38  call    cs:__imp_ReleaseSRWLockExclusive
0x180001e3e  jmp     short loc_180001DC3
0x180001e40  mov     r8, rbx
0x180001e43  mov     [r15], eax
0x180001e46  shl     r8, 2; Size
0x180001e4a  mov     edx, 0FFh; Val
0x180001e4f  mov     rcx, r14; void *
0x180001e52  call    memset_0
0x180001e57  jmp     short loc_180001E31
0x180001e59  mov     rdi, [r8+10h]
0x180001e5d  lea     rdx, aSoftwareMicros_10; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180001e64  mov     r8, [r8+8]; pszFile
0x180001e68  lea     rcx, [rsp+298h+pszDest]; pszDest
0x180001e6d  test    r12, r12
0x180001e70  mov     [rsp+298h+var_264], ebp
0x180001e74  cmovnz  rdx, r12; pszDir
0x180001e78  call    cs:__imp_PathCombineW
0x180001e7e  lea     rax, [rsp+298h+var_268]
0x180001e83  mov     [rsp+298h+var_268], 4
0x180001e8b  mov     [rsp+298h+pcbData], rax; pcbData
0x180001e90  lea     rdx, [rsp+298h+pszDest]; pszSubKey
0x180001e95  lea     rax, [rsp+298h+var_264]
0x180001e9a  xor     r9d, r9d; pdwType
0x180001e9d  mov     r8, rdi; pszValue
0x180001ea0  mov     [rsp+298h+pvData], rax; pvData
0x180001ea5  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180001eac  call    cs:__imp_SHGetValueW
0x180001eb2  test    eax, eax
0x180001eb4  jz      short loc_180001EEA
0x180001eb6  lea     rax, [rsp+298h+var_268]
0x180001ebb  mov     [rsp+298h+var_268], 4
0x180001ec3  mov     [rsp+298h+pcbData], rax; pcbData
0x180001ec8  lea     rdx, [rsp+298h+pszDest]; pszSubKey
0x180001ecd  lea     rax, [rsp+298h+var_264]
0x180001ed2  xor     r9d, r9d; pdwType
0x180001ed5  mov     r8, rdi; pszValue
0x180001ed8  mov     [rsp+298h+pvData], rax; pvData
0x180001edd  mov     rcx, 0FFFFFFFF80000001h; hkey
0x180001ee4  call    cs:__imp_SHGetValueW
0x180001eea  mov     edi, [rsp+298h+var_264]
0x180001eee  lea     rcx, ?g_csrwlockRestrictions@@3VCSRWLock@@A; SRWLock
0x180001ef5  call    cs:__imp_AcquireSRWLockExclusive
0x180001efb  mov     ecx, 5; id
0x180001f00  call    cs:__imp_SHGlobalCounterGetValue
0x180001f06  cmp     [r15], eax
0x180001f09  jnz     short loc_180001F0D
0x180001f0b  mov     [rbx], edi
0x180001f0d  lea     rcx, ?g_csrwlockRestrictions@@3VCSRWLock@@A; SRWLock
0x180001f14  call    cs:__imp_ReleaseSRWLockExclusive
0x180001f1a  mov     eax, edi
0x180001f1c  jmp     loc_180001DEB
0x180001f21  mov     eax, ebp
0x180001f23  jmp     loc_180001DEB
0x180001f28  mov     eax, ebp
0x180001f2a  jmp     loc_180001DF3
```
