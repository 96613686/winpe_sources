# SecpLoadSaslProfiles(void)

- ea: `0x180006eac`
- end: `0x1800070c8`
- name: `?SecpLoadSaslProfiles@@YAJXZ`
- size: `540`
- prototype: `__int64(void)`
- caller_count: `7`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180003ee0`
- `0x1800049c0`
- `0x180005400`
- `0x180005860`
- `0x1800061a0`
- `0x180007200`
- `0x180009c90`

## callees

- `0x180006eac`
- `0x18001d478`
- `0x180022047`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x1800070a5`
- `ntdll!RtlFreeHeap` at `0x1800070a5`
- `ntdll!RtlInitUnicodeString` at `0x180006f97`
- `ntdll!RtlInitUnicodeString` at `0x180006f97`
- `ntdll!RtlAllocateHeap` at `0x180006f1d`
- `ntdll!RtlAllocateHeap` at `0x180006f1d`
- `ntdll!RtlEqualUnicodeString` at `0x180006fdc`
- `ntdll!RtlEqualUnicodeString` at `0x180006fdc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800070af`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800070af`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180006f78`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180006f78`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006efa`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006efa`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000701c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000701c`

## string_xrefs

- `0x180006edf`: `System\CurrentControlSet\Control\SecurityProviders\SaslProfiles`

## pseudocode

```c
__int64 SecpLoadSaslProfiles(void)
{
  char *Heap; // rax
  WCHAR *v1; // rsi
  BYTE *lpData; // r15
  DWORD i; // r14d
  __int64 v4; // r8
  const UNICODE_STRING *j; // rbx
  __int64 v6; // rax
  _QWORD *v7; // rax
  _QWORD *v8; // rdi
  _QWORD *v9; // rax
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-18h] BYREF
  DWORD cbData; // [rsp+A0h] [rbp+48h] BYREF
  DWORD cchValueName; // [rsp+A8h] [rbp+50h] BYREF
  DWORD Type; // [rsp+B0h] [rbp+58h] BYREF
  HKEY hKey; // [rsp+B8h] [rbp+60h] BYREF

  hKey = 0;
  Type = 0;
  cbData = 0;
  cchValueName = 0;
  DestinationString = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"System\\CurrentControlSet\\Control\\SecurityProviders\\SaslProfiles",
          0,
          0x20019u,
          &hKey) )
  {
    Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x410u);
    v1 = (WCHAR *)Heap;
    if ( Heap )
    {
      lpData = (BYTE *)(Heap + 520);
      for ( i = 0; ; ++i )
      {
        cchValueName = 260;
        cbData = 520;
        if ( RegEnumValueW(hKey, i, v1, &cchValueName, 0, &Type, lpData, &cbData) )
          break;
        if ( Type == 1 )
        {
          RtlInitUnicodeString(&DestinationString, (PCWSTR)lpData);
          for ( j = (const UNICODE_STRING *)SecPackageControlList;
                j != (const UNICODE_STRING *)&SecPackageControlList;
                j = *(const UNICODE_STRING **)&j->Length )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
              WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, v4, j[6].Buffer);
            if ( RtlEqualUnicodeString(j + 6, &DestinationString, 1u) )
            {
              if ( j )
              {
                v6 = -1;
                do
                  ++v6;
                while ( v1[v6] );
                cbData = 2 * v6 + 2;
                v7 = LocalAlloc(0, cbData + 40LL);
                v8 = v7;
                if ( v7 )
                {
                  v7[2] = j;
                  v7[4] = v7 + 5;
                  *((_WORD *)v7 + 13) = cbData;
                  *((_WORD *)v7 + 12) = cbData - 2;
                  memcpy_0(v7 + 5, v1, cbData);
                  v9 = (_QWORD *)qword_18003FEC0;
                  if ( *(HLOCAL **)qword_18003FEC0 != &SecSaslProfileList )
                    __fastfail(3u);
                  *v8 = &SecSaslProfileList;
                  v8[1] = v9;
                  *v9 = v8;
                  qword_18003FEC0 = (__int64)v8;
                  *(_DWORD *)(&j[2].MaximumLength + 1) |= 8u;
                  ++SecSaslProfileCount;
                }
              }
              break;
            }
          }
        }
      }
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v1);
    }
    RegCloseKey(hKey);
  }
  return 0;
}

```

## disassembly

```asm
0x180006eac  push    rbp
0x180006eae  push    rbx
0x180006eaf  push    rsi
0x180006eb0  push    rdi
0x180006eb1  push    r12
0x180006eb3  push    r13
0x180006eb5  push    r14
0x180006eb7  push    r15
0x180006eb9  mov     rbp, rsp
0x180006ebc  sub     rsp, 58h
0x180006ec0  xor     r12d, r12d
0x180006ec3  lea     rax, [rbp+hKey]
0x180006ec7  xorps   xmm0, xmm0
0x180006eca  mov     [rbp+hKey], r12
0x180006ece  mov     r9d, 20019h; samDesired
0x180006ed4  mov     [rbp+Type], r12d
0x180006ed8  xor     r8d, r8d; ulOptions
0x180006edb  mov     [rbp+cbData], r12d
0x180006edf  lea     rdx, SubKey; "System\\CurrentControlSet\\Control\\Sec"...
0x180006ee6  mov     [rbp+cchValueName], r12d
0x180006eea  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180006ef1  mov     [rsp+58h+phkResult], rax; phkResult
0x180006ef6  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180006efa  call    cs:__imp_RegOpenKeyExW
0x180006f00  test    eax, eax
0x180006f02  jnz     loc_1800070B5
0x180006f08  mov     rcx, gs:60h
0x180006f11  xor     edx, edx; Flags
0x180006f13  mov     r8d, 410h; Size
0x180006f19  mov     rcx, [rcx+30h]; HeapHandle
0x180006f1d  call    cs:__imp_RtlAllocateHeap
0x180006f23  mov     rsi, rax
0x180006f26  test    rax, rax
0x180006f29  jz      loc_1800070AB
0x180006f2f  lea     r15, [rax+208h]
0x180006f36  mov     r14d, r12d
0x180006f39  lea     r13, ?SecPackageControlList@@3U_LIST_ENTRY@@A; _LIST_ENTRY SecPackageControlList
0x180006f40  mov     rcx, [rbp+hKey]; hKey
0x180006f44  lea     rax, [rbp+cbData]
0x180006f48  mov     [rsp+58h+lpcbData], rax; lpcbData
0x180006f4d  lea     r9, [rbp+cchValueName]; lpcchValueName
0x180006f51  lea     rax, [rbp+Type]
0x180006f55  mov     [rsp+58h+lpData], r15; lpData
0x180006f5a  mov     [rsp+58h+lpType], rax; lpType
0x180006f5f  mov     r8, rsi; lpValueName
0x180006f62  mov     edx, r14d; dwIndex
0x180006f65  mov     [rsp+58h+phkResult], r12; lpReserved
0x180006f6a  mov     [rbp+cchValueName], 104h
0x180006f71  mov     [rbp+cbData], 208h
0x180006f78  call    cs:__imp_RegEnumValueW
0x180006f7e  test    eax, eax
0x180006f80  jnz     loc_180007093
0x180006f86  cmp     [rbp+Type], 1
0x180006f8a  jnz     loc_180007084
0x180006f90  mov     rdx, r15; SourceString
0x180006f93  lea     rcx, [rbp+DestinationString]; DestinationString
0x180006f97  call    cs:__imp_RtlInitUnicodeString
0x180006f9d  mov     rbx, cs:?SecPackageControlList@@3U_LIST_ENTRY@@A; _LIST_ENTRY SecPackageControlList
0x180006fa4  jmp     short loc_180006FE9
0x180006fa6  mov     rcx, cs:WPP_GLOBAL_Control
0x180006fad  lea     rax, WPP_GLOBAL_Control
0x180006fb4  cmp     rcx, rax
0x180006fb7  jz      short loc_180006FD1
0x180006fb9  test    byte ptr [rcx+1Ch], 4
0x180006fbd  jz      short loc_180006FD1
0x180006fbf  mov     r9, [rbx+68h]
0x180006fc3  mov     edx, 0Bh
0x180006fc8  mov     rcx, [rcx+10h]
0x180006fcc  call    WPP_SF_S
0x180006fd1  lea     rcx, [rbx+60h]; String1
0x180006fd5  mov     r8b, 1; CaseInsensitive
0x180006fd8  lea     rdx, [rbp+DestinationString]; String2
0x180006fdc  call    cs:__imp_RtlEqualUnicodeString
0x180006fe2  test    al, al
0x180006fe4  jnz     short loc_180006FF3
0x180006fe6  mov     rbx, [rbx]
0x180006fe9  cmp     rbx, r13
0x180006fec  jnz     short loc_180006FA6
0x180006fee  jmp     loc_180007084
0x180006ff3  test    rbx, rbx
0x180006ff6  jz      loc_180007084
0x180006ffc  or      rax, 0FFFFFFFFFFFFFFFFh
0x180007000  inc     rax
0x180007003  cmp     [rsi+rax*2], r12w
0x180007008  jnz     short loc_180007000
0x18000700a  lea     eax, ds:2[rax*2]
0x180007011  xor     ecx, ecx; uFlags
0x180007013  mov     edx, eax
0x180007015  add     rdx, 28h ; '('; uBytes
0x180007019  mov     [rbp+cbData], eax
0x18000701c  call    cs:__imp_LocalAlloc
0x180007022  mov     rdi, rax
0x180007025  test    rax, rax
0x180007028  jz      short loc_180007084
0x18000702a  mov     [rax+10h], rbx
0x18000702e  lea     rcx, [rax+28h]; void *
0x180007032  mov     [rax+20h], rcx
0x180007036  movzx   edx, word ptr [rbp+cbData]
0x18000703a  mov     [rax+1Ah], dx
0x18000703e  movzx   edx, word ptr [rbp+cbData]
0x180007042  sub     dx, 2
0x180007046  mov     [rax+18h], dx
0x18000704a  mov     rdx, rsi; Src
0x18000704d  mov     r8d, [rbp+cbData]; Size
0x180007051  call    memcpy_0
0x180007056  mov     rax, cs:qword_18003FEC0
0x18000705d  lea     rcx, ?SecSaslProfileList@@3U_LIST_ENTRY@@A; _LIST_ENTRY SecSaslProfileList
0x180007064  cmp     [rax], rcx
0x180007067  jnz     short loc_18000708C
0x180007069  mov     [rdi], rcx
0x18000706c  mov     [rdi+8], rax
0x180007070  mov     [rax], rdi
0x180007073  mov     cs:qword_18003FEC0, rdi
0x18000707a  or      dword ptr [rbx+24h], 8
0x18000707e  inc     cs:?SecSaslProfileCount@@3KA; ulong SecSaslProfileCount
0x180007084  inc     r14d
0x180007087  jmp     loc_180006F40
0x18000708c  mov     ecx, 3
0x180007091  int     29h; Win8: RtlFailFast(ecx)
0x180007093  mov     rcx, gs:60h
0x18000709c  mov     r8, rsi; P
0x18000709f  xor     edx, edx; Flags
0x1800070a1  mov     rcx, [rcx+30h]; HeapHandle
0x1800070a5  call    cs:__imp_RtlFreeHeap
0x1800070ab  mov     rcx, [rbp+hKey]; hKey
0x1800070af  call    cs:__imp_RegCloseKey
0x1800070b5  xor     eax, eax
0x1800070b7  add     rsp, 58h
0x1800070bb  pop     r15
0x1800070bd  pop     r14
0x1800070bf  pop     r13
0x1800070c1  pop     r12
0x1800070c3  pop     rdi
0x1800070c4  pop     rsi
0x1800070c5  pop     rbx
0x1800070c6  pop     rbp
0x1800070c7  retn
```
