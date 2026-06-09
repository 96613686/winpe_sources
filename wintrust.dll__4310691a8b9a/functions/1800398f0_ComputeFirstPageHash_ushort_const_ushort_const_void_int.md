# ComputeFirstPageHash(ushort const *,ushort const *,void *,int)

- ea: `0x1800398f0`
- end: `0x180039b3d`
- name: `?ComputeFirstPageHash@@YAHPEBG0PEAXH@Z`
- size: `589`
- prototype: `__int64 __fastcall(wchar_t *String1, const unsigned __int16 *, void *, int)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800398a4`
- `0x1800398f0`
- `0x180039bc8`
- `0x180039bf4`
- `0x180048894`
- `0x18004de52`
- `0x18004de82`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180039a20`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180039a20`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180039a48`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180039a48`
- `ntdll!RtlFreeHeap` at `0x180039aea`
- `ntdll!RtlFreeHeap` at `0x180039b17`
- `ntdll!RtlFreeHeap` at `0x180039aea`
- `ntdll!RtlFreeHeap` at `0x180039b17`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180039a00`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180039a00`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180039a9f`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180039ad1`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180039b23`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180039a9f`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180039ad1`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180039b23`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ComputeFirstPageHash(wchar_t *String1, const unsigned __int16 *a2, void *a3, int a4)
{
  const WCHAR *v8; // rdi
  int v9; // ebx
  unsigned int v10; // esi
  int v11; // ebx
  int v12; // ebx
  int v13; // ebx
  int v14; // ebx
  SIZE_T dwNumberOfBytesToMap; // rax
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+40h] [rbp-29h] BYREF
  PVOID P; // [rsp+48h] [rbp-21h]
  SIZE_T v19; // [rsp+50h] [rbp-19h] BYREF
  HANDLE hFileMappingObject; // [rsp+58h] [rbp-11h]
  __int64 v21; // [rsp+60h] [rbp-9h]
  LPCVOID lpBaseAddress[2]; // [rsp+68h] [rbp-1h]
  unsigned int v23[18]; // [rsp+78h] [rbp+Fh]

  if ( !a2 || !String1 )
    return 0;
  v8 = L"SHA256";
  if ( wcscmp_0(String1, L"SHA1") )
  {
    if ( !wcscmp_0(String1, L"SHA256") )
    {
      v9 = 32780;
      v10 = 32;
      goto LABEL_7;
    }
    return 0;
  }
  v9 = 32772;
  v10 = 20;
LABEL_7:
  if ( a3 && a4 == v10 )
  {
    P = 0;
    phAlgorithm = 0;
    LODWORD(v19) = 0;
    hFileMappingObject = 0;
    v21 = 0;
    *(_OWORD *)lpBaseAddress = 0;
    *(_QWORD *)v23 = 0;
    if ( ViewInfo::initialize((ViewInfo *)&v19, a2) )
    {
      v11 = v9 - 32771;
      if ( v11 )
      {
        v12 = v11 - 1;
        if ( v12 )
        {
          v13 = v12 - 8;
          if ( v13 )
          {
            v14 = v13 - 1;
            if ( v14 )
            {
              if ( v14 == 1 )
                v8 = L"SHA512";
              else
                v8 = 0;
            }
            else
            {
              v8 = L"SHA384";
            }
          }
        }
        else
        {
          v8 = L"SHA1";
        }
      }
      else
      {
        v8 = L"MD5";
      }
      if ( !BCryptOpenAlgorithmProvider(&phAlgorithm, v8, 0, 0) )
      {
        ViewInfo::Unmap((ViewInfo *)&v19);
        if ( lpBaseAddress[1] )
          UnmapViewOfFile(lpBaseAddress[1]);
        dwNumberOfBytesToMap = 10485760;
        if ( (unsigned int)v19 < 0xA00000 )
          dwNumberOfBytesToMap = (unsigned int)v19;
        v23[0] = dwNumberOfBytesToMap;
        lpBaseAddress[1] = MapViewOfFile(hFileMappingObject, 4u, 0, 0, dwNumberOfBytesToMap);
        HIDWORD(v21) = v19;
        LODWORD(v21) = 0;
        if ( (unsigned int)HashGeneratePageHashesEx(phAlgorithm, lpBaseAddress[1]) )
        {
          BCryptCloseAlgorithmProvider(phAlgorithm, 0);
        }
        else
        {
          BCryptCloseAlgorithmProvider(phAlgorithm, 0);
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
        }
      }
    }
    ViewInfo::~ViewInfo((ViewInfo *)&v19);
    return 0;
  }
  return v10;
}

```

## disassembly

```asm
0x1800398f0  push    rbp
0x1800398f2  push    rbx
0x1800398f3  push    rsi
0x1800398f4  push    rdi
0x1800398f5  push    r12
0x1800398f7  push    r13
0x1800398f9  push    r14
0x1800398fb  push    r15
0x1800398fd  lea     rbp, [rsp-1Fh]
0x180039902  sub     rsp, 88h
0x180039909  movsxd  r15, r9d
0x18003990c  mov     r12, r8
0x18003990f  mov     r14, rdx
0x180039912  mov     rbx, rcx
0x180039915  xor     r13d, r13d
0x180039918  test    rdx, rdx
0x18003991b  jz      loc_180039AAF
0x180039921  test    rcx, rcx
0x180039924  jz      loc_180039AAF
0x18003992a  lea     rdx, aSha1; "SHA1"
0x180039931  call    wcscmp_0
0x180039936  lea     rdi, aSha256; "SHA256"
0x18003993d  test    eax, eax
0x18003993f  jnz     short loc_18003994B
0x180039941  mov     ebx, 8004h
0x180039946  lea     esi, [rax+14h]
0x180039949  jmp     short loc_180039966
0x18003994b  mov     rdx, rdi; String2
0x18003994e  mov     rcx, rbx; String1
0x180039951  call    wcscmp_0
0x180039956  test    eax, eax
0x180039958  jnz     loc_180039AAF
0x18003995e  mov     ebx, 800Ch
0x180039963  lea     esi, [rax+20h]
0x180039966  test    r12, r12
0x180039969  jz      loc_180039B36
0x18003996f  cmp     r15d, esi
0x180039972  jnz     loc_180039B36
0x180039978  mov     [rbp+57h+arg_8], r13d
0x18003997c  mov     [rbp+57h+P], r13
0x180039980  mov     [rbp+57h+phAlgorithm], r13
0x180039984  mov     dword ptr [rbp+57h+var_70], r13d
0x180039988  mov     [rbp+57h+hFileMappingObject], r13
0x18003998c  mov     [rbp+57h+var_60], r13
0x180039990  xorps   xmm0, xmm0
0x180039993  movdqu  xmmword ptr [rbp+57h+lpBaseAddress], xmm0
0x180039998  mov     qword ptr [rbp+57h+var_48], r13
0x18003999c  mov     rdx, r14; unsigned __int16 *
0x18003999f  lea     rcx, [rbp+57h+var_70]; this
0x1800399a3  call    ?initialize@ViewInfo@@QEAA_NPEBG@Z; ViewInfo::initialize(ushort const *)
0x1800399a8  test    al, al
0x1800399aa  jz      loc_180039AA6
0x1800399b0  sub     ebx, 8003h
0x1800399b6  jz      short loc_1800399EC
0x1800399b8  sub     ebx, 1
0x1800399bb  jz      short loc_1800399E3
0x1800399bd  sub     ebx, 8
0x1800399c0  jz      short loc_1800399F3
0x1800399c2  sub     ebx, 1
0x1800399c5  jz      short loc_1800399DA
0x1800399c7  cmp     ebx, 1
0x1800399ca  jz      short loc_1800399D1
0x1800399cc  mov     rdi, r13
0x1800399cf  jmp     short loc_1800399F3
0x1800399d1  lea     rdi, aSha512; "SHA512"
0x1800399d8  jmp     short loc_1800399F3
0x1800399da  lea     rdi, aSha384; "SHA384"
0x1800399e1  jmp     short loc_1800399F3
0x1800399e3  lea     rdi, aSha1; "SHA1"
0x1800399ea  jmp     short loc_1800399F3
0x1800399ec  lea     rdi, aMd5; "MD5"
0x1800399f3  xor     r9d, r9d; dwFlags
0x1800399f6  xor     r8d, r8d; pszImplementation
0x1800399f9  mov     rdx, rdi; pszAlgId
0x1800399fc  lea     rcx, [rbp+57h+phAlgorithm]; phAlgorithm
0x180039a00  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180039a06  test    eax, eax
0x180039a08  jnz     loc_180039AA6
0x180039a0e  lea     rcx, [rbp+57h+var_70]; this
0x180039a12  call    ?Unmap@ViewInfo@@QEAAXXZ; ViewInfo::Unmap(void)
0x180039a17  mov     rcx, [rbp+57h+lpBaseAddress+8]; lpBaseAddress
0x180039a1b  test    rcx, rcx
0x180039a1e  jz      short loc_180039A26
0x180039a20  call    cs:__imp_UnmapViewOfFile
0x180039a26  mov     eax, 0A00000h
0x180039a2b  cmp     dword ptr [rbp+57h+var_70], eax
0x180039a2e  cmovb   eax, dword ptr [rbp+57h+var_70]
0x180039a32  mov     [rbp+57h+var_48], eax
0x180039a35  mov     [rsp+0C0h+dwNumberOfBytesToMap], rax; dwNumberOfBytesToMap
0x180039a3a  xor     r9d, r9d; dwFileOffsetLow
0x180039a3d  xor     r8d, r8d; dwFileOffsetHigh
0x180039a40  lea     edx, [r9+4]; dwDesiredAccess
0x180039a44  mov     rcx, [rbp+57h+hFileMappingObject]; hFileMappingObject
0x180039a48  call    cs:__imp_MapViewOfFile
0x180039a4e  mov     [rbp+57h+lpBaseAddress+8], rax
0x180039a52  mov     r8d, dword ptr [rbp+57h+var_70]; unsigned int
0x180039a56  mov     dword ptr [rbp+57h+var_60+4], r8d
0x180039a5a  mov     dword ptr [rbp+57h+var_60], r13d
0x180039a5e  lea     rcx, [rbp+57h+P]
0x180039a62  mov     [rsp+0C0h+var_88], rcx; struct PAGE_HASH_V2 **
0x180039a67  lea     rcx, [rbp+57h+arg_8]
0x180039a6b  mov     [rsp+0C0h+var_90], rcx; unsigned int *
0x180039a70  lea     rcx, [rbp+57h+var_70]
0x180039a74  mov     [rsp+0C0h+var_98], rcx; void *
0x180039a79  lea     rcx, ?HashMapViewOfFile@ViewInfo@@SAJPEAXKPEAKPEAPEAX1@Z; ViewInfo::HashMapViewOfFile(void *,ulong,ulong *,void * *,ulong *)
0x180039a80  mov     [rsp+0C0h+dwNumberOfBytesToMap], rcx; int (*)(void *, unsigned int, unsigned int *, void **, unsigned int *)
0x180039a85  mov     r9d, [rbp+57h+var_48]; unsigned int
0x180039a89  mov     rdx, rax; void *
0x180039a8c  mov     rcx, [rbp+57h+phAlgorithm]; void *
0x180039a90  call    ?HashGeneratePageHashesEx@@YAJPEAXPEBXKKP6AJ0KPEAKPEAPEAX2@Z02PEAPEAUPAGE_HASH_V2@@@Z; HashGeneratePageHashesEx(void *,void const *,ulong,ulong,long (*)(void *,ulong,ulong *,void * *,ulong *),void *,ulong *,PAGE_HASH_V2 * *)
0x180039a95  test    eax, eax
0x180039a97  jz      short loc_180039AC5
0x180039a99  xor     edx, edx; dwFlags
0x180039a9b  mov     rcx, [rbp+57h+phAlgorithm]; hAlgorithm
0x180039a9f  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180039aa5  nop
0x180039aa6  lea     rcx, [rbp+57h+var_70]; this
0x180039aaa  call    ??1ViewInfo@@QEAA@XZ; ViewInfo::~ViewInfo(void)
0x180039aaf  xor     eax, eax
0x180039ab1  add     rsp, 88h
0x180039ab8  pop     r15
0x180039aba  pop     r14
0x180039abc  pop     r13
0x180039abe  pop     r12
0x180039ac0  pop     rdi
0x180039ac1  pop     rsi
0x180039ac2  pop     rbx
0x180039ac3  pop     rbp
0x180039ac4  retn
0x180039ac5  cmp     [rbp+57h+arg_8], r13d
0x180039ac9  jnz     short loc_180039AF2
0x180039acb  xor     edx, edx; dwFlags
0x180039acd  mov     rcx, [rbp+57h+phAlgorithm]; hAlgorithm
0x180039ad1  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180039ad7  mov     rcx, gs:60h
0x180039ae0  mov     r8, [rbp+57h+P]; P
0x180039ae4  xor     edx, edx; Flags
0x180039ae6  mov     rcx, [rcx+30h]; HeapHandle
0x180039aea  call    cs:__imp_RtlFreeHeap
0x180039af0  jmp     short loc_180039AA6
0x180039af2  mov     r8, r15; Size
0x180039af5  mov     rbx, [rbp+57h+P]
0x180039af9  lea     rdx, [rbx+4]; Src
0x180039afd  mov     rcx, r12; void *
0x180039b00  call    memcpy_0
0x180039b05  mov     rcx, gs:60h
0x180039b0e  mov     r8, rbx; P
0x180039b11  xor     edx, edx; Flags
0x180039b13  mov     rcx, [rcx+30h]; HeapHandle
0x180039b17  call    cs:__imp_RtlFreeHeap
0x180039b1d  xor     edx, edx; dwFlags
0x180039b1f  mov     rcx, [rbp+57h+phAlgorithm]; hAlgorithm
0x180039b23  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180039b29  mov     [rbp+57h+phAlgorithm], r13
0x180039b2d  lea     rcx, [rbp+57h+var_70]; this
0x180039b31  call    ??1ViewInfo@@QEAA@XZ; ViewInfo::~ViewInfo(void)
0x180039b36  mov     eax, esi
0x180039b38  jmp     loc_180039AB1
```
