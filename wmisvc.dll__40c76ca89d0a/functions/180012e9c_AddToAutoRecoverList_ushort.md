# AddToAutoRecoverList(ushort *)

- ea: `0x180012e9c`
- end: `0x180013169`
- name: `?AddToAutoRecoverList@@YAXPEAG@Z`
- size: `717`
- prototype: `void __fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000ba0c`

## callees

- `0x180004120`
- `0x18000b4f4`
- `0x1800101e4`
- `0x180012e9c`
- `0x18001d377`
- `0x18001d3a0`

## import_xrefs

- `msvcrt!_ui64tow_s` at `0x180013112`
- `msvcrt!_ui64tow_s` at `0x180013112`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800130f8`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800130f8`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180012efb`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180012efb`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180012fa6`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180012fa6`
- `wbemcomn!??0Registry@@QEAA@PEBGK@Z` at `0x180012f19`
- `wbemcomn!??0Registry@@QEAA@PEBGK@Z` at `0x180012f19`
- `wbemcomn!??1Registry@@QEAA@XZ` at `0x180013140`
- `wbemcomn!??1Registry@@QEAA@XZ` at `0x180013140`
- `wbemcomn!?SetStr@Registry@@QEAAHPEBG0@Z` at `0x180013129`
- `wbemcomn!?SetStr@Registry@@QEAAHPEBG0@Z` at `0x180013129`
- `wbemcomn!?GetMultiStr@Registry@@QEAAPEAGPEBGAEAK@Z` at `0x180012f31`
- `wbemcomn!?GetMultiStr@Registry@@QEAAPEAGPEBGAEAK@Z` at `0x180012f31`
- `wbemcomn!?SetMultiStr@Registry@@QEAAHPEBGPEAGK@Z` at `0x1800130cf`
- `wbemcomn!?SetMultiStr@Registry@@QEAAHPEBGPEAGK@Z` at `0x1800130cf`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800130d8`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800130d8`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180013003`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180013095`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180013003`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180013095`

## pseudocode

```c
void __fastcall AddToAutoRecoverList(LPCWSTR lpFileName)
{
  unsigned __int16 *MultiStr; // rax
  unsigned __int16 *v3; // rsi
  unsigned int v4; // edx
  const WCHAR *lpString2; // rdi
  __int64 v6; // rbx
  __int64 v7; // rax
  __int64 v8; // rdx
  unsigned int v9; // r15d
  unsigned __int64 v10; // r12
  unsigned __int64 v11; // r14
  unsigned __int16 *v12; // rax
  unsigned __int16 *v13; // rdi
  unsigned __int16 *v14; // rax
  unsigned __int16 *v15; // r10
  __int64 v17; // r10
  __int64 v18; // rax
  unsigned __int64 v19; // rsi
  unsigned __int16 *v20; // rax
  size_t Size; // [rsp+30h] [rbp-D0h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+38h] [rbp-C8h] BYREF
  LPWSTR FilePart; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v24[2]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v25[24]; // [rsp+58h] [rbp-A8h] BYREF
  wchar_t v26[8]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v27[26]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR Buffer[264]; // [rsp+A0h] [rbp-60h] BYREF

  memset_0(Buffer, 0, 0x20Au);
  FilePart = 0;
  LODWORD(Size) = 0;
  if ( GetFullPathNameW(lpFileName, 0x104u, Buffer, &FilePart) )
  {
    Registry::Registry((Registry *)v25, L"Software\\Microsoft\\WBEM\\CIMOM", 3u);
    MultiStr = Registry::GetMultiStr((Registry *)v25, L"Autorecover MOFs", (unsigned int *)&Size);
    v3 = MultiStr;
    v24[0] = MultiStr;
    v24[1] = 0;
    if ( (_DWORD)Size == 1 || !MultiStr )
    {
      v18 = -1;
      do
        ++v18;
      while ( Buffer[v18] );
      v9 = 2 * v18 + 4;
      v19 = (unsigned __int64)v9 >> 1;
      v20 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(saturated_mul(v19, 2u));
      v13 = v20;
      if ( !v20 )
      {
LABEL_28:
        CVectorDeleteMe<unsigned short>::~CVectorDeleteMe<unsigned short>(v24);
        Registry::~Registry((Registry *)v25);
        return;
      }
      StringCchCopyW(v20, v19 - 1, Buffer);
      v13[v19 - 1] = 0;
    }
    else
    {
      v4 = (unsigned int)Size >> 1;
      if ( (unsigned int)Size >> 1 < 2 || MultiStr[v4 - 2] || MultiStr[v4 - 1] )
        goto LABEL_28;
      lpString2 = MultiStr;
      v6 = -1;
      while ( *lpString2 )
      {
        if ( CompareStringW(0x7Fu, 1u, Buffer, -1, lpString2, -1) == 2 )
          goto LABEL_27;
        v7 = -1;
        do
          ++v7;
        while ( lpString2[v7] );
        lpString2 += v7 + 1;
      }
      v8 = -1;
      do
        ++v8;
      while ( Buffer[v8] );
      v9 = Size + 2 * (v8 + 1);
      v10 = (unsigned __int64)(unsigned int)Size >> 1;
      v11 = (unsigned __int64)v9 >> 1;
      v12 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(saturated_mul(v11, 2u));
      v13 = v12;
      if ( !v12 )
        goto LABEL_28;
      memcpy_0(v12, v3, (unsigned int)Size);
      v14 = v13;
      do
      {
        do
          v15 = v14 + 1;
        while ( *v14++ != 0 );
      }
      while ( *v15 );
      StringCchCopyW(v15, v11 - v10, Buffer);
      do
        ++v6;
      while ( Buffer[v6] );
      *(_WORD *)(v17 + 2 * v6 + 2) = 0;
    }
    Registry::SetMultiStr((Registry *)v25, L"Autorecover MOFs", v13, v9);
    CWin32DefaultArena::WbemMemFree(v13);
LABEL_27:
    SystemTimeAsFileTime = 0;
    *(_OWORD *)v26 = 0;
    memset(v27, 0, sizeof(v27));
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    _ui64tow_s(*(_QWORD *)&SystemTimeAsFileTime, v26, 0x15u, 10);
    Registry::SetStr((Registry *)v25, L"Autorecover MOFs timestamp", v26);
    goto LABEL_28;
  }
}

```

## disassembly

```asm
0x180012e9c  push    rbp
0x180012e9e  push    rbx
0x180012e9f  push    rsi
0x180012ea0  push    rdi
0x180012ea1  push    r12
0x180012ea3  push    r13
0x180012ea5  push    r14
0x180012ea7  push    r15
0x180012ea9  lea     rbp, [rsp-1C8h]
0x180012eb1  sub     rsp, 2C8h
0x180012eb8  mov     rax, cs:__security_cookie
0x180012ebf  xor     rax, rsp
0x180012ec2  mov     [rbp+200h+var_50], rax
0x180012ec9  mov     rbx, rcx
0x180012ecc  xor     edx, edx; Val
0x180012ece  mov     r8d, 20Ah; Size
0x180012ed4  lea     rcx, [rbp+200h+Buffer]; void *
0x180012ed8  call    memset_0
0x180012edd  xor     r13d, r13d
0x180012ee0  mov     [rsp+300h+FilePart], r13
0x180012ee5  mov     dword ptr [rsp+300h+Size], r13d
0x180012eea  lea     r9, [rsp+300h+FilePart]; lpFilePart
0x180012eef  lea     r8, [rbp+200h+Buffer]; lpBuffer
0x180012ef3  mov     edx, 104h; nBufferLength
0x180012ef8  mov     rcx, rbx; lpFileName
0x180012efb  call    cs:__imp_GetFullPathNameW
0x180012f01  test    eax, eax
0x180012f03  jz      loc_180013146
0x180012f09  lea     r8d, [r13+3]
0x180012f0d  lea     rdx, SubKey; "Software\\Microsoft\\WBEM\\CIMOM"
0x180012f14  lea     rcx, [rsp+300h+var_2A8]
0x180012f19  call    cs:__imp_??0Registry@@QEAA@PEBGK@Z; Registry::Registry(ushort const *,ulong)
0x180012f1f  nop
0x180012f20  lea     r8, [rsp+300h+Size]
0x180012f25  lea     rdx, aAutorecoverMof_0; "Autorecover MOFs"
0x180012f2c  lea     rcx, [rsp+300h+var_2A8]
0x180012f31  call    cs:__imp_?GetMultiStr@Registry@@QEAAPEAGPEBGAEAK@Z; Registry::GetMultiStr(ushort const *,ulong &)
0x180012f37  mov     rsi, rax
0x180012f3a  mov     [rsp+300h+var_2B8], rax
0x180012f3f  mov     [rsp+300h+var_2B0], r13
0x180012f44  mov     edx, dword ptr [rsp+300h+Size]
0x180012f48  cmp     edx, 1
0x180012f4b  jz      loc_180013063
0x180012f51  test    rax, rax
0x180012f54  jz      loc_180013063
0x180012f5a  shr     edx, 1
0x180012f5c  cmp     edx, 2
0x180012f5f  jb      loc_180013130
0x180012f65  lea     eax, [rdx-2]
0x180012f68  cmp     [rsi+rax*2], r13w
0x180012f6d  jnz     loc_180013130
0x180012f73  lea     eax, [rdx-1]
0x180012f76  cmp     [rsi+rax*2], r13w
0x180012f7b  jnz     loc_180013130
0x180012f81  mov     rdi, rsi
0x180012f84  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180012f88  cmp     [rdi], r13w
0x180012f8c  jz      short loc_180012FCC
0x180012f8e  mov     [rsp+300h+cchCount2], ebx; cchCount2
0x180012f92  mov     [rsp+300h+lpString2], rdi; lpString2
0x180012f97  mov     r9d, ebx; cchCount1
0x180012f9a  lea     r8, [rbp+200h+Buffer]; lpString1
0x180012f9e  mov     edx, 1; dwCmpFlags
0x180012fa3  lea     ecx, [rdx+7Eh]; Locale
0x180012fa6  call    cs:__imp_CompareStringW
0x180012fac  cmp     eax, 2
0x180012faf  jz      loc_1800130DE
0x180012fb5  mov     rax, rbx
0x180012fb8  inc     rax
0x180012fbb  cmp     [rdi+rax*2], r13w
0x180012fc0  jnz     short loc_180012FB8
0x180012fc2  lea     rdi, [rdi+rax*2]
0x180012fc6  add     rdi, 2
0x180012fca  jmp     short loc_180012F88
0x180012fcc  lea     rax, [rbp+200h+Buffer]
0x180012fd0  mov     rdx, rbx
0x180012fd3  inc     rdx
0x180012fd6  cmp     [rax+rdx*2], r13w
0x180012fdb  jnz     short loc_180012FD3
0x180012fdd  mov     ecx, dword ptr [rsp+300h+Size]
0x180012fe1  lea     edx, [rdx+1]
0x180012fe4  lea     r15d, [rcx+rdx*2]
0x180012fe8  mov     r12d, ecx
0x180012feb  shr     r12, 1
0x180012fee  mov     r14d, r15d
0x180012ff1  shr     r14, 1
0x180012ff4  mov     eax, 2
0x180012ff9  mul     r14
0x180012ffc  cmovb   rax, rbx
0x180013000  mov     rcx, rax
0x180013003  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180013009  mov     rdi, rax
0x18001300c  test    rax, rax
0x18001300f  jz      loc_180013130
0x180013015  mov     r8d, dword ptr [rsp+300h+Size]; Size
0x18001301a  mov     rdx, rsi; Src
0x18001301d  mov     rcx, rax; void *
0x180013020  call    memcpy_0
0x180013025  mov     rax, rdi
0x180013028  lea     r10, [rax+2]
0x18001302c  cmp     [rax], r13w
0x180013030  mov     rax, r10
0x180013033  jnz     short loc_180013028
0x180013035  cmp     [r10], r13w
0x180013039  jnz     short loc_180013028
0x18001303b  sub     r14, r12
0x18001303e  lea     r8, [rbp+200h+Buffer]; unsigned __int16 *
0x180013042  mov     rdx, r14; unsigned __int64
0x180013045  mov     rcx, r10; unsigned __int16 *
0x180013048  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001304d  lea     r11, [rbp+200h+Buffer]
0x180013051  inc     rbx
0x180013054  cmp     [r11+rbx*2], r13w
0x180013059  jnz     short loc_180013051
0x18001305b  mov     [r10+rbx*2+2], r13w
0x180013061  jmp     short loc_1800130BD
0x180013063  lea     rcx, [rbp+200h+Buffer]
0x180013067  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001306b  mov     rax, rbx
0x18001306e  inc     rax
0x180013071  cmp     [rcx+rax*2], r13w
0x180013076  jnz     short loc_18001306E
0x180013078  lea     r15d, ds:4[rax*2]
0x180013080  mov     esi, r15d
0x180013083  shr     rsi, 1
0x180013086  mov     eax, 2
0x18001308b  mul     rsi
0x18001308e  cmovb   rax, rbx
0x180013092  mov     rcx, rax
0x180013095  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18001309b  mov     rdi, rax
0x18001309e  test    rax, rax
0x1800130a1  jz      loc_180013130
0x1800130a7  lea     rdx, [rsi-1]; unsigned __int64
0x1800130ab  lea     r8, [rbp+200h+Buffer]; unsigned __int16 *
0x1800130af  mov     rcx, rax; unsigned __int16 *
0x1800130b2  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800130b7  mov     [rdi+rsi*2-2], r13w
0x1800130bd  mov     r9d, r15d
0x1800130c0  mov     r8, rdi
0x1800130c3  lea     rdx, aAutorecoverMof_0; "Autorecover MOFs"
0x1800130ca  lea     rcx, [rsp+300h+var_2A8]
0x1800130cf  call    cs:__imp_?SetMultiStr@Registry@@QEAAHPEBGPEAGK@Z; Registry::SetMultiStr(ushort const *,ushort *,ulong)
0x1800130d5  mov     rcx, rdi
0x1800130d8  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x1800130de  mov     qword ptr [rsp+300h+SystemTimeAsFileTime.dwLowDateTime], r13
0x1800130e3  xorps   xmm0, xmm0
0x1800130e6  movups  xmmword ptr [rsp+300h+var_290], xmm0
0x1800130eb  movups  xmmword ptr [rbp+200h+var_280], xmm0
0x1800130ef  movups  xmmword ptr [rbp+200h+var_280+0Ah], xmm0
0x1800130f3  lea     rcx, [rsp+300h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800130f8  call    cs:__imp_GetSystemTimeAsFileTime
0x1800130fe  mov     r9d, 0Ah; Radix
0x180013104  lea     r8d, [r9+0Bh]; BufferCount
0x180013108  lea     rdx, [rsp+300h+var_290]; Buffer
0x18001310d  mov     rcx, qword ptr [rsp+300h+SystemTimeAsFileTime.dwLowDateTime]; Value
0x180013112  call    cs:__imp__ui64tow_s
0x180013118  lea     r8, [rsp+300h+var_290]
0x18001311d  lea     rdx, aAutorecoverMof; "Autorecover MOFs timestamp"
0x180013124  lea     rcx, [rsp+300h+var_2A8]
0x180013129  call    cs:__imp_?SetStr@Registry@@QEAAHPEBG0@Z; Registry::SetStr(ushort const *,ushort const *)
0x18001312f  nop
0x180013130  lea     rcx, [rsp+300h+var_2B8]
0x180013135  call    ??1?$CVectorDeleteMe@G@@QEAA@XZ; CVectorDeleteMe<ushort>::~CVectorDeleteMe<ushort>(void)
0x18001313a  nop
0x18001313b  lea     rcx, [rsp+300h+var_2A8]
0x180013140  call    cs:__imp_??1Registry@@QEAA@XZ; Registry::~Registry(void)
0x180013146  mov     rcx, [rbp+200h+var_50]
0x18001314d  xor     rcx, rsp; StackCookie
0x180013150  call    __security_check_cookie
0x180013155  add     rsp, 2C8h
0x18001315c  pop     r15
0x18001315e  pop     r14
0x180013160  pop     r13
0x180013162  pop     r12
0x180013164  pop     rdi
0x180013165  pop     rsi
0x180013166  pop     rbx
0x180013167  pop     rbp
0x180013168  retn
```
