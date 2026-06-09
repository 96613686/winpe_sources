# LsaLookupClientUpdateCacheUsingNames

- ea: `0x180020adc`
- end: `0x180020d37`
- name: `LsaLookupClientUpdateCacheUsingNames`
- size: `603`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, installer_update`

## callers

- `0x18000ce20`

## callees

- `0x18000d710`
- `0x180013ea8`
- `0x1800194cc`
- `0x18001fdb4`
- `0x18001fea0`
- `0x180020624`
- `0x1800208c0`
- `0x180020adc`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180020beb`
- `ntdll!RtlInitUnicodeString` at `0x180020ca3`
- `ntdll!RtlInitUnicodeString` at `0x180020beb`
- `ntdll!RtlInitUnicodeString` at `0x180020ca3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020b61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020b61`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180020c8b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180020c8b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180020c75`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180020c75`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180020c3a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180020c3a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180020c58`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180020c58`

## pseudocode

```c
__int64 __fastcall LsaLookupClientUpdateCacheUsingNames(ULONG a1, int a2, int a3, __int64 a4, __int64 a5)
{
  WCHAR *v6; // rdi
  __int64 v8; // rcx
  int inserted; // ebx
  WCHAR *v11; // r14
  WCHAR *v12; // rax
  int v13; // edx
  __int64 v14; // rdi
  __int64 v15; // rsi
  int v16; // ecx
  char v17; // r12
  __int64 v19; // [rsp+40h] [rbp-51h] BYREF
  struct _UNICODE_STRING v20; // [rsp+48h] [rbp-49h] BYREF
  WCHAR *v21; // [rsp+58h] [rbp-39h] BYREF
  __int64 Memory; // [rsp+60h] [rbp-31h] BYREF
  UNICODE_STRING v23; // [rsp+68h] [rbp-29h] BYREF
  UNICODE_STRING String2; // [rsp+78h] [rbp-19h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+88h] [rbp-9h] BYREF
  ULONG v26; // [rsp+F0h] [rbp+5Fh] BYREF

  v26 = a1;
  *(_DWORD *)&v20.Length = 0;
  v6 = 0;
  v21 = 0;
  v8 = *(_QWORD *)(a4 + 8);
  LODWORD(v19) = 0;
  v26 = 0;
  inserted = -1073741709;
  DestinationString = 0;
  v23 = 0;
  String2 = 0;
  if ( !(unsigned int)LookupAccountSidInternal(v8, 0, (unsigned int *)&v19, 0, &v26, &v20, a2) )
  {
    inserted = -1073741823;
    if ( GetLastError() == 122 )
    {
      inserted = -1073741801;
      Memory = LsaLookupClientAllocateMemory((unsigned int)(2 * v19));
      v11 = (WCHAR *)Memory;
      if ( Memory )
      {
        v12 = (WCHAR *)LsaLookupClientAllocateMemory(2 * v26);
        v21 = v12;
        v6 = v12;
        if ( v12 )
        {
          if ( (unsigned int)LookupAccountSidInternal(
                               *(_QWORD *)(a4 + 8),
                               v11,
                               (unsigned int *)&v19,
                               v12,
                               &v26,
                               &v20,
                               a2) )
          {
            inserted = 0;
            RtlInitUnicodeString(&DestinationString, L"\\");
            LsaLookupClientRtlSplitNames(
              a3,
              v13,
              (unsigned int)&DestinationString,
              (unsigned int)&v23,
              (__int64)&String2);
            v14 = a5;
            v15 = 0;
            do
            {
              v16 = *(_DWORD *)(a4 + 24 * v15);
              v19 = 3 * v15;
              if ( (unsigned int)(v16 - 7) <= 1 || (v17 = 1, v16 == 6) )
                v17 = 0;
              AcquireSRWLockShared(&LsaLookupClientSidCacheLock);
              *(_QWORD *)&v20.Length = LsaLookupClientFindCacheEntryByName(&v23, &String2);
              ReleaseSRWLockShared(&LsaLookupClientSidCacheLock);
              if ( *(_QWORD *)&v20.Length )
              {
                if ( !v17 )
                {
                  AcquireSRWLockExclusive(&LsaLookupClientSidCacheLock);
                  LsaLookupClientInvalidateNamesByEntry(*(_QWORD *)&v20.Length);
                  ReleaseSRWLockExclusive(&LsaLookupClientSidCacheLock);
                  inserted = 0;
                }
              }
              else
              {
                v20 = 0;
                RtlInitUnicodeString(&v20, v11);
                inserted = LsaLookupClientInsertCacheEntry(
                             *(PSID *)(a4 + 8 * v19 + 8),
                             *(PSID *)(*(_QWORD *)(v14 + 16LL * (unsigned int)v15 + 8)
                                     + 24LL * *(int *)(a4 + 8 * v19 + 16)
                                     + 16),
                             &String2,
                             &v23,
                             (__int64)&v20,
                             *(_QWORD *)(v14 + 8),
                             *(_DWORD *)(a4 + 8 * v19));
                if ( inserted < 0 )
                  break;
              }
              v15 = (unsigned int)(v15 + 1);
            }
            while ( !(_DWORD)v15 );
            v6 = v21;
          }
          else
          {
            inserted = -1073741823;
          }
        }
      }
      if ( v11 )
        LsaLookupClientFreeMemory(&Memory);
      if ( v6 )
        LsaLookupClientFreeMemory(&v21);
    }
  }
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x180020adc  mov     [rsp-8+arg_0], ecx
0x180020ae0  push    rbp
0x180020ae1  push    rbx
0x180020ae2  push    rsi
0x180020ae3  push    rdi
0x180020ae4  push    r12
0x180020ae6  push    r13
0x180020ae8  push    r14
0x180020aea  push    r15
0x180020aec  lea     rbp, [rsp-17h]
0x180020af1  sub     rsp, 0A8h
0x180020af8  mov     [rsp+0E0h+var_B0], edx
0x180020afc  lea     rax, [rbp+4Fh+var_98]
0x180020b00  mov     r13, r9
0x180020b03  mov     [rsp+0E0h+var_B8], rax
0x180020b08  xorps   xmm0, xmm0
0x180020b0b  mov     dword ptr [rbp+4Fh+var_98.Length], 0
0x180020b12  xor     edi, edi
0x180020b14  lea     rax, [rbp+4Fh+arg_0]
0x180020b18  mov     r15, r8
0x180020b1b  mov     [rbp+4Fh+var_88], rdi
0x180020b1f  mov     rcx, [r13+8]
0x180020b23  lea     r8, [rbp+4Fh+var_A0]
0x180020b27  mov     esi, edx
0x180020b29  mov     dword ptr [rbp+4Fh+var_A0], edi
0x180020b2c  xorps   xmm1, xmm1
0x180020b2f  mov     [rbp+4Fh+arg_0], edi
0x180020b32  xor     r9d, r9d
0x180020b35  mov     [rsp+0E0h+var_C0], rax
0x180020b3a  xor     edx, edx
0x180020b3c  mov     ebx, 0C0000073h
0x180020b41  movups  xmmword ptr [rbp+4Fh+DestinationString.Length], xmm0
0x180020b45  movups  xmmword ptr [rbp+4Fh+var_78.Length], xmm1
0x180020b49  movups  xmmword ptr [rbp+4Fh+String2.Length], xmm0
0x180020b4d  call    LookupAccountSidInternal
0x180020b52  test    eax, eax
0x180020b54  jnz     loc_180020D21
0x180020b5a  lea     r12d, [rbx-72h]
0x180020b5e  mov     ebx, r12d
0x180020b61  call    cs:__imp_GetLastError
0x180020b67  cmp     eax, 7Ah ; 'z'
0x180020b6a  jnz     loc_180020D21
0x180020b70  mov     ecx, dword ptr [rbp+4Fh+var_A0]
0x180020b73  lea     ebx, [r12+16h]
0x180020b78  add     ecx, ecx
0x180020b7a  call    LsaLookupClientAllocateMemory
0x180020b7f  mov     [rbp+4Fh+var_80], rax
0x180020b83  mov     r14, rax
0x180020b86  test    rax, rax
0x180020b89  jz      loc_180020D05
0x180020b8f  mov     ecx, [rbp+4Fh+arg_0]
0x180020b92  add     ecx, ecx
0x180020b94  call    LsaLookupClientAllocateMemory
0x180020b99  mov     [rbp+4Fh+var_88], rax
0x180020b9d  mov     rdi, rax
0x180020ba0  test    rax, rax
0x180020ba3  jz      loc_180020D05
0x180020ba9  mov     rcx, [r13+8]
0x180020bad  lea     rax, [rbp+4Fh+var_98]
0x180020bb1  mov     [rsp+0E0h+var_B0], esi
0x180020bb5  lea     r8, [rbp+4Fh+var_A0]
0x180020bb9  mov     [rsp+0E0h+var_B8], rax
0x180020bbe  mov     r9, rdi
0x180020bc1  lea     rax, [rbp+4Fh+arg_0]
0x180020bc5  mov     rdx, r14
0x180020bc8  mov     [rsp+0E0h+var_C0], rax
0x180020bcd  call    LookupAccountSidInternal
0x180020bd2  test    eax, eax
0x180020bd4  jnz     short loc_180020BDE
0x180020bd6  mov     ebx, r12d
0x180020bd9  jmp     loc_180020D05
0x180020bde  lea     rdx, SourceString; "\\"
0x180020be5  xor     ebx, ebx
0x180020be7  lea     rcx, [rbp+4Fh+DestinationString]; DestinationString
0x180020beb  call    cs:__imp_RtlInitUnicodeString
0x180020bf1  lea     rax, [rbp+4Fh+String2]
0x180020bf5  mov     rcx, r15
0x180020bf8  lea     r9, [rbp+4Fh+var_78]
0x180020bfc  mov     [rsp+0E0h+var_C0], rax
0x180020c01  lea     r8, [rbp+4Fh+DestinationString]
0x180020c05  call    LsaLookupClientRtlSplitNames
0x180020c0a  mov     rdi, [rbp+4Fh+arg_20]
0x180020c0e  xor     esi, esi
0x180020c10  lea     rax, [rsi+rsi*2]
0x180020c14  mov     r15d, esi
0x180020c17  mov     ecx, [r13+rax*8+0]
0x180020c1c  mov     [rbp+4Fh+var_A0], rax
0x180020c20  lea     eax, [rcx-7]
0x180020c23  cmp     eax, 1
0x180020c26  jbe     short loc_180020C30
0x180020c28  mov     r12b, 1
0x180020c2b  cmp     ecx, 6
0x180020c2e  jnz     short loc_180020C33
0x180020c30  xor     r12b, r12b
0x180020c33  lea     rcx, LsaLookupClientSidCacheLock; SRWLock
0x180020c3a  call    cs:__imp_AcquireSRWLockShared
0x180020c40  lea     rdx, [rbp+4Fh+String2]
0x180020c44  lea     rcx, [rbp+4Fh+var_78]
0x180020c48  call    LsaLookupClientFindCacheEntryByName
0x180020c4d  lea     rcx, LsaLookupClientSidCacheLock; SRWLock
0x180020c54  mov     qword ptr [rbp+4Fh+var_98.Length], rax
0x180020c58  call    cs:__imp_ReleaseSRWLockShared
0x180020c5e  cmp     qword ptr [rbp+4Fh+var_98.Length], 0
0x180020c63  jz      short loc_180020C95
0x180020c65  test    r12b, r12b
0x180020c68  jnz     loc_180020CF6
0x180020c6e  lea     rcx, LsaLookupClientSidCacheLock; SRWLock
0x180020c75  call    cs:__imp_AcquireSRWLockExclusive
0x180020c7b  mov     rcx, qword ptr [rbp+4Fh+var_98.Length]
0x180020c7f  call    LsaLookupClientInvalidateNamesByEntry
0x180020c84  lea     rcx, LsaLookupClientSidCacheLock; SRWLock
0x180020c8b  call    cs:__imp_ReleaseSRWLockExclusive
0x180020c91  xor     ebx, ebx
0x180020c93  jmp     short loc_180020CF6
0x180020c95  xorps   xmm0, xmm0
0x180020c98  lea     rcx, [rbp+4Fh+var_98]; DestinationString
0x180020c9c  mov     rdx, r14; SourceString
0x180020c9f  movups  xmmword ptr [rbp+4Fh+var_98.Length], xmm0
0x180020ca3  call    cs:__imp_RtlInitUnicodeString
0x180020ca9  mov     r10, [rbp+4Fh+var_A0]
0x180020cad  lea     r9, [rbp+4Fh+var_78]; PCUNICODE_STRING
0x180020cb1  add     r15, r15
0x180020cb4  lea     r8, [rbp+4Fh+String2]; String2
0x180020cb8  movsxd  rax, dword ptr [r13+r10*8+10h]
0x180020cbd  mov     rdx, [rdi+r15*8+8]
0x180020cc2  lea     rcx, [rax+rax*2]
0x180020cc6  mov     eax, [r13+r10*8+0]
0x180020ccb  mov     rdx, [rdx+rcx*8+10h]; PSID
0x180020cd0  mov     rcx, [r13+r10*8+8]; SourceSid
0x180020cd5  mov     [rsp+0E0h+var_B0], eax; int
0x180020cd9  mov     rax, [rdi+8]
0x180020cdd  mov     [rsp+0E0h+var_B8], rax; __int64
0x180020ce2  lea     rax, [rbp+4Fh+var_98]
0x180020ce6  mov     [rsp+0E0h+var_C0], rax; __int64
0x180020ceb  call    LsaLookupClientInsertCacheEntry
0x180020cf0  mov     ebx, eax
0x180020cf2  test    eax, eax
0x180020cf4  js      short loc_180020D01
0x180020cf6  inc     esi
0x180020cf8  cmp     esi, 1
0x180020cfb  jb      loc_180020C10
0x180020d01  mov     rdi, [rbp+4Fh+var_88]
0x180020d05  test    r14, r14
0x180020d08  jz      short loc_180020D13
0x180020d0a  lea     rcx, [rbp+4Fh+var_80]
0x180020d0e  call    LsaLookupClientFreeMemory
0x180020d13  test    rdi, rdi
0x180020d16  jz      short loc_180020D21
0x180020d18  lea     rcx, [rbp+4Fh+var_88]
0x180020d1c  call    LsaLookupClientFreeMemory
0x180020d21  mov     eax, ebx
0x180020d23  add     rsp, 0A8h
0x180020d2a  pop     r15
0x180020d2c  pop     r14
0x180020d2e  pop     r13
0x180020d30  pop     r12
0x180020d32  pop     rdi
0x180020d33  pop     rsi
0x180020d34  pop     rbx
0x180020d35  pop     rbp
0x180020d36  retn
```
