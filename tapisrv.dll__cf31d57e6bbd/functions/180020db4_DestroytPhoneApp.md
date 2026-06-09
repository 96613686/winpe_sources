# DestroytPhoneApp

- ea: `0x180020db4`
- end: `0x180020ff2`
- name: `DestroytPhoneApp`
- size: `574`
- prototype: `__int64 __fastcall(unsigned int, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180024ed0`
- `0x180026730`

## callees

- `0x18001c7c0`
- `0x180020db4`
- `0x180020ff8`
- `0x18002d27c`
- `0x18003dc84`
- `0x18003e15c`
- `0x18003e3b4`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180020f0b`
- `KERNEL32!GetCurrentThreadId` at `0x180020f6b`
- `KERNEL32!GetCurrentThreadId` at `0x180020f0b`
- `KERNEL32!GetCurrentThreadId` at `0x180020f6b`
- `KERNEL32!LeaveCriticalSection` at `0x180020e55`
- `KERNEL32!LeaveCriticalSection` at `0x180020eee`
- `KERNEL32!LeaveCriticalSection` at `0x180020f91`
- `KERNEL32!LeaveCriticalSection` at `0x180020fc1`
- `KERNEL32!LeaveCriticalSection` at `0x180020e55`
- `KERNEL32!LeaveCriticalSection` at `0x180020eee`
- `KERNEL32!LeaveCriticalSection` at `0x180020f91`
- `KERNEL32!LeaveCriticalSection` at `0x180020fc1`
- `KERNEL32!EnterCriticalSection` at `0x180020e0f`
- `KERNEL32!EnterCriticalSection` at `0x180020e7e`
- `KERNEL32!EnterCriticalSection` at `0x180020ea5`
- `KERNEL32!EnterCriticalSection` at `0x180020efb`
- `KERNEL32!EnterCriticalSection` at `0x180020e0f`
- `KERNEL32!EnterCriticalSection` at `0x180020e7e`
- `KERNEL32!EnterCriticalSection` at `0x180020ea5`
- `KERNEL32!EnterCriticalSection` at `0x180020efb`

## pseudocode

```c
__int64 __fastcall DestroytPhoneApp(unsigned int a1, unsigned __int64 a2)
{
  __int64 v4; // rcx
  unsigned __int64 v5; // rax
  unsigned __int64 v6; // rbx
  unsigned __int64 v7; // rdi
  __int64 v8; // rsi
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rax
  size_t v12; // rdx
  __int64 v13; // rcx
  int v14; // r10d
  size_t v15; // rdx
  __int64 v16; // rcx
  __int64 v18; // rcx

  TRACELogPrint(524290, "DestroytPhoneApp: enter, hPhoneApp=x%x", a1);
  v5 = ReferenceObject(v4, a1, 0);
  v6 = v5;
  if ( !v5 )
    return dword_180051928 != 0 ? -1879048185 : -1879048158;
  v7 = v5 >> 4;
  EnterCriticalSection((LPCRITICAL_SECTION)gLockTable + ((v5 >> 4) & (unsigned int)gdwPointerToLockTableIndexBits));
  if ( *(_DWORD *)v6 != 1347436880 || a2 != *(_QWORD *)(v6 + 8) )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)gLockTable + ((unsigned int)v7 & gdwPointerToLockTableIndexBits));
    DereferenceObject(v18, a1, 1);
    return dword_180051928 != 0 ? -1879048185 : -1879048158;
  }
  *(_DWORD *)v6 = 1280724553;
  while ( 1 )
  {
    v8 = *(_QWORD *)(v6 + 24);
    if ( v8 )
      LODWORD(v8) = *(_DWORD *)(v8 + 96);
    LeaveCriticalSection((LPCRITICAL_SECTION)gLockTable + ((unsigned int)v7 & gdwPointerToLockTableIndexBits));
    if ( !(_DWORD)v8 )
      break;
    DestroytPhoneClient((unsigned int)v8);
    EnterCriticalSection((LPCRITICAL_SECTION)gLockTable + ((unsigned int)v7 & gdwPointerToLockTableIndexBits));
  }
  EnterCriticalSection((LPCRITICAL_SECTION)gLockTable + ((a2 >> 4) & (unsigned int)gdwPointerToLockTableIndexBits));
  v9 = *(_QWORD *)(v6 + 40);
  if ( v9 )
    *(_QWORD *)(v9 + 32) = *(_QWORD *)(v6 + 32);
  v10 = *(_QWORD *)(v6 + 32);
  v11 = *(_QWORD *)(v6 + 40);
  if ( v10 )
    *(_QWORD *)(v10 + 40) = v11;
  else
    *(_QWORD *)(a2 + 176) = v11;
  LeaveCriticalSection((LPCRITICAL_SECTION)gLockTable + ((a2 >> 4) & (unsigned int)gdwPointerToLockTableIndexBits));
  EnterCriticalSection(&CriticalSection);
  dword_1800519E0 = 1177;
  dword_1800519E4 = GetCurrentThreadId();
  StringCbCopyA(pszDest, v12, "\\server\\phone.c");
  v14 = --dword_180051928;
  if ( !dword_180051918 && !v14 && (dword_180051900 & 2) == 0 )
  {
    ServerShutdown(v13);
    gbServerInited = 0;
  }
  dword_1800519F8 = 1191;
  dword_1800519FC = GetCurrentThreadId();
  StringCbCopyA(byte_1800519E8, v15, "\\server\\phone.c");
  LeaveCriticalSection(&CriticalSection);
  DereferenceObject(v16, a1, 2);
  return 0;
}

```

## disassembly

```asm
0x180020db4  push    rbx
0x180020db6  push    rbp
0x180020db7  push    rsi
0x180020db8  push    rdi
0x180020db9  push    r14
0x180020dbb  sub     rsp, 20h
0x180020dbf  mov     rbp, rdx
0x180020dc2  mov     r14d, ecx
0x180020dc5  mov     r8d, ecx
0x180020dc8  lea     rdx, aDestroytphonea; "DestroytPhoneApp: enter, hPhoneApp=x%x"
0x180020dcf  mov     ecx, 80002h
0x180020dd4  call    TRACELogPrint
0x180020dd9  xor     r8d, r8d
0x180020ddc  mov     edx, r14d
0x180020ddf  call    ReferenceObject
0x180020de4  mov     rbx, rax
0x180020de7  test    rax, rax
0x180020dea  jz      loc_180020FD5
0x180020df0  mov     rdi, rax
0x180020df3  mov     eax, cs:gdwPointerToLockTableIndexBits
0x180020df9  shr     rdi, 4
0x180020dfd  and     rax, rdi
0x180020e00  lea     rcx, [rax+rax*4]
0x180020e04  mov     rax, cs:gLockTable
0x180020e0b  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x180020e0f  call    cs:__imp_EnterCriticalSection
0x180020e15  cmp     dword ptr [rbx], 50504150h
0x180020e1b  jnz     loc_180020FA9
0x180020e21  cmp     rbp, [rbx+8]
0x180020e25  jnz     loc_180020FA9
0x180020e2b  mov     dword ptr [rbx], 4C564E49h
0x180020e31  mov     rsi, [rbx+18h]
0x180020e35  test    rsi, rsi
0x180020e38  jz      short loc_180020E3D
0x180020e3a  mov     esi, [rsi+60h]
0x180020e3d  mov     eax, cs:gdwPointerToLockTableIndexBits
0x180020e43  and     rax, rdi
0x180020e46  lea     rdx, [rax+rax*4]
0x180020e4a  mov     rax, cs:gLockTable
0x180020e51  lea     rcx, [rax+rdx*8]; lpCriticalSection
0x180020e55  call    cs:__imp_LeaveCriticalSection
0x180020e5b  test    esi, esi
0x180020e5d  jz      short loc_180020E86
0x180020e5f  mov     ecx, esi
0x180020e61  call    DestroytPhoneClient
0x180020e66  mov     eax, cs:gdwPointerToLockTableIndexBits
0x180020e6c  and     rax, rdi
0x180020e6f  lea     rcx, [rax+rax*4]
0x180020e73  mov     rax, cs:gLockTable
0x180020e7a  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x180020e7e  call    cs:__imp_EnterCriticalSection
0x180020e84  jmp     short loc_180020E31
0x180020e86  mov     eax, cs:gdwPointerToLockTableIndexBits
0x180020e8c  mov     rdi, rbp
0x180020e8f  shr     rdi, 4
0x180020e93  and     rax, rdi
0x180020e96  lea     rcx, [rax+rax*4]
0x180020e9a  mov     rax, cs:gLockTable
0x180020ea1  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x180020ea5  call    cs:__imp_EnterCriticalSection
0x180020eab  mov     rcx, [rbx+28h]
0x180020eaf  test    rcx, rcx
0x180020eb2  jz      short loc_180020EBC
0x180020eb4  mov     rax, [rbx+20h]
0x180020eb8  mov     [rcx+20h], rax
0x180020ebc  mov     rcx, [rbx+20h]
0x180020ec0  mov     rax, [rbx+28h]
0x180020ec4  test    rcx, rcx
0x180020ec7  jz      short loc_180020ECF
0x180020ec9  mov     [rcx+28h], rax
0x180020ecd  jmp     short loc_180020ED6
0x180020ecf  mov     [rbp+0B0h], rax
0x180020ed6  mov     eax, cs:gdwPointerToLockTableIndexBits
0x180020edc  and     rax, rdi
0x180020edf  lea     rcx, [rax+rax*4]
0x180020ee3  mov     rax, cs:gLockTable
0x180020eea  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x180020eee  call    cs:__imp_LeaveCriticalSection
0x180020ef4  lea     rcx, CriticalSection; lpCriticalSection
0x180020efb  call    cs:__imp_EnterCriticalSection
0x180020f01  mov     cs:dword_1800519E0, 499h
0x180020f0b  call    cs:__imp_GetCurrentThreadId
0x180020f11  lea     r8, aPrintscanTapiS_2+0Eh; pszSrc
0x180020f18  mov     cs:dword_1800519E4, eax
0x180020f1e  lea     rcx, pszDest; pszDest
0x180020f25  call    StringCbCopyA
0x180020f2a  mov     r10d, cs:dword_180051928
0x180020f31  dec     r10d
0x180020f34  cmp     cs:dword_180051918, 0
0x180020f3b  mov     cs:dword_180051928, r10d
0x180020f42  jnz     short loc_180020F61
0x180020f44  test    r10d, r10d
0x180020f47  jnz     short loc_180020F61
0x180020f49  test    byte ptr cs:dword_180051900, 2
0x180020f50  jnz     short loc_180020F61
0x180020f52  call    ServerShutdown
0x180020f57  mov     cs:gbServerInited, 0
0x180020f61  mov     cs:dword_1800519F8, 4A7h
0x180020f6b  call    cs:__imp_GetCurrentThreadId
0x180020f71  lea     r8, aPrintscanTapiS_2+0Eh; pszSrc
0x180020f78  mov     cs:dword_1800519FC, eax
0x180020f7e  lea     rcx, byte_1800519E8; pszDest
0x180020f85  call    StringCbCopyA
0x180020f8a  lea     rcx, CriticalSection; lpCriticalSection
0x180020f91  call    cs:__imp_LeaveCriticalSection
0x180020f97  mov     r8d, 2
0x180020f9d  mov     edx, r14d
0x180020fa0  call    DereferenceObject
0x180020fa5  xor     eax, eax
0x180020fa7  jmp     short loc_180020FE7
0x180020fa9  mov     eax, cs:gdwPointerToLockTableIndexBits
0x180020faf  and     rax, rdi
0x180020fb2  lea     rcx, [rax+rax*4]
0x180020fb6  mov     rax, cs:gLockTable
0x180020fbd  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x180020fc1  call    cs:__imp_LeaveCriticalSection
0x180020fc7  mov     r8d, 1
0x180020fcd  mov     edx, r14d
0x180020fd0  call    DereferenceObject
0x180020fd5  mov     eax, cs:dword_180051928
0x180020fdb  neg     eax
0x180020fdd  sbb     eax, eax
0x180020fdf  and     eax, 0FFFFFFE5h
0x180020fe2  add     eax, 90000022h
0x180020fe7  add     rsp, 20h
0x180020feb  pop     r14
0x180020fed  pop     rdi
0x180020fee  pop     rsi
0x180020fef  pop     rbp
0x180020ff0  pop     rbx
0x180020ff1  retn
```
