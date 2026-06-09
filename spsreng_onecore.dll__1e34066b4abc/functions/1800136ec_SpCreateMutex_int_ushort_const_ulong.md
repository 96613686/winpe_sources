# SpCreateMutex(int,ushort const *,ulong)

- ea: `0x1800136ec`
- end: `0x1800137d7`
- name: `?SpCreateMutex@@YAPEAXHPEBGK@Z`
- size: `235`
- prototype: `void *(int, const unsigned __int16 *, unsigned int)`
- caller_count: `3`
- callee_count: `5`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x18000a5f8`
- `0x1800999d8`
- `0x1800a5aa8`

## callees

- `0x1800034b0`
- `0x1800067d4`
- `0x1800117c0`
- `0x1800136ec`
- `0x1800c774c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800137a2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800137a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001378e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001378e`
- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x18001375b`
- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x18001375b`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180013780`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180013780`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800137ad`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800137ad`

## pseudocode

```c
HANDLE __fastcall SpCreateMutex(__int64 a1, const unsigned __int16 *a2)
{
  const unsigned __int16 *v3; // rdx
  int v4; // eax
  HANDLE MutexW; // rbx
  int i; // edi
  _BYTE v8[8]; // [rsp+20h] [rbp-258h] BYREF
  HLOCAL hMem; // [rsp+28h] [rbp-250h]
  _WORD v10[272]; // [rsp+40h] [rbp-238h] BYREF

  CSpSecurityAttribute::CSpSecurityAttribute((CSpSecurityAttribute *)v8, 0x100001u, 1048577);
  v4 = PrefixedObjectName::Initialize((PrefixedObjectName *)v10, v3, a2);
  MutexW = 0;
  if ( !SetLastErrorIfFailed(v4) )
  {
    for ( i = 0; i < 100; ++i )
    {
      MutexW = OpenMutexW(0x100000u, 0, (LPCWSTR)((unsigned __int64)v10 & -(__int64)(v10[0] != 0)));
      if ( MutexW )
      {
        SetLastError(0xB7u);
        break;
      }
      MutexW = CreateMutexW(0, 0, (LPCWSTR)((unsigned __int64)v10 & -(__int64)(v10[0] != 0)));
      if ( MutexW || GetLastError() != 5 )
        break;
    }
  }
  LocalFree(hMem);
  return MutexW;
}

```

## disassembly

```asm
0x1800136ec  mov     [rsp+arg_0], rbx
0x1800136f1  push    rdi
0x1800136f2  sub     rsp, 270h
0x1800136f9  mov     rax, cs:__security_cookie
0x180013700  xor     rax, rsp
0x180013703  mov     [rsp+278h+var_18], rax
0x18001370b  mov     rbx, rdx
0x18001370e  lea     rcx, [rsp+278h+var_258]; this
0x180013713  mov     edx, 100001h; unsigned int
0x180013718  mov     r8d, edx; unsigned int
0x18001371b  call    ??0CSpSecurityAttribute@@QEAA@KK@Z; CSpSecurityAttribute::CSpSecurityAttribute(ulong,ulong)
0x180013720  mov     r8, rbx; unsigned __int16 *
0x180013723  lea     rcx, [rsp+278h+var_238]; this
0x180013728  call    ?Initialize@PrefixedObjectName@@AEAAJPEBG0@Z; PrefixedObjectName::Initialize(ushort const *,ushort const *)
0x18001372d  mov     ecx, eax; int
0x18001372f  call    ?SetLastErrorIfFailed@@YA_NJ@Z; SetLastErrorIfFailed(long)
0x180013734  xor     ebx, ebx
0x180013736  test    al, al
0x180013738  jnz     short loc_1800137A8
0x18001373a  xor     edi, edi
0x18001373c  cmp     edi, 64h ; 'd'
0x18001373f  jge     short loc_1800137A8
0x180013741  movzx   eax, [rsp+278h+var_238]
0x180013746  mov     ecx, 100000h; dwDesiredAccess
0x18001374b  neg     ax
0x18001374e  lea     rax, [rsp+278h+var_238]
0x180013753  sbb     r8, r8
0x180013756  xor     edx, edx; bInheritHandle
0x180013758  and     r8, rax; lpName
0x18001375b  call    cs:__imp_OpenMutexW
0x180013761  mov     rbx, rax
0x180013764  test    rax, rax
0x180013767  jnz     short loc_18001379D
0x180013769  movzx   eax, [rsp+278h+var_238]
0x18001376e  neg     ax
0x180013771  lea     rax, [rsp+278h+var_238]
0x180013776  sbb     r8, r8
0x180013779  xor     edx, edx; bInitialOwner
0x18001377b  and     r8, rax; lpName
0x18001377e  xor     ecx, ecx; lpMutexAttributes
0x180013780  call    cs:__imp_CreateMutexW
0x180013786  mov     rbx, rax
0x180013789  test    rax, rax
0x18001378c  jnz     short loc_1800137A8
0x18001378e  call    cs:__imp_GetLastError
0x180013794  cmp     eax, 5
0x180013797  jnz     short loc_1800137A8
0x180013799  inc     edi
0x18001379b  jmp     short loc_18001373C
0x18001379d  mov     ecx, 0B7h; dwErrCode
0x1800137a2  call    cs:__imp_SetLastError
0x1800137a8  mov     rcx, [rsp+278h+hMem]; hMem
0x1800137ad  call    cs:__imp_LocalFree
0x1800137b3  mov     rax, rbx
0x1800137b6  mov     rcx, [rsp+278h+var_18]
0x1800137be  xor     rcx, rsp; StackCookie
0x1800137c1  call    __security_check_cookie
0x1800137c6  mov     rbx, [rsp+278h+arg_0]
0x1800137ce  add     rsp, 270h
0x1800137d5  pop     rdi
0x1800137d6  retn
```
