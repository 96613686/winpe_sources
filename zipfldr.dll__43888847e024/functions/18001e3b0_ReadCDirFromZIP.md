# ReadCDirFromZIP

- ea: `0x18001e3b0`
- end: `0x18001e721`
- name: `ReadCDirFromZIP`
- size: `881`
- prototype: `_QWORD *__fastcall(int)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180017ba0`

## callees

- `0x180005464`
- `0x18001833c`
- `0x18001e3b0`
- `0x18001e730`
- `0x18001e774`
- `0x180036f50`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001e3d8`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001e3d8`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18001e6b9`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18001e6b9`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18001e4d2`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18001e5fb`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18001e4d2`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18001e5fb`
- `KERNEL32!GlobalReAlloc` at `0x18001e6cd`
- `KERNEL32!GlobalReAlloc` at `0x18001e6cd`
- `KERNEL32!GlobalUnlock` at `0x18001e64e`
- `KERNEL32!GlobalUnlock` at `0x18001e65b`
- `KERNEL32!GlobalUnlock` at `0x18001e70a`
- `KERNEL32!GlobalUnlock` at `0x18001e64e`
- `KERNEL32!GlobalUnlock` at `0x18001e65b`
- `KERNEL32!GlobalUnlock` at `0x18001e70a`
- `KERNEL32!GlobalSize` at `0x18001e555`
- `KERNEL32!GlobalSize` at `0x18001e555`
- `KERNEL32!GlobalLock` at `0x18001e581`
- `KERNEL32!GlobalLock` at `0x18001e639`
- `KERNEL32!GlobalLock` at `0x18001e581`
- `KERNEL32!GlobalLock` at `0x18001e639`

## pseudocode

```c
_QWORD *__fastcall ReadCDirFromZIP(int a1)
{
  _QWORD *result; // rax
  _QWORD *v3; // rdi
  void *v4; // rcx
  unsigned int v5; // ebx
  __int64 v6; // rsi
  BOOL v7; // r15d
  bool v8; // zf
  int v9; // eax
  DWORD v10; // ecx
  DWORD v11; // edx
  DWORD v12; // esi
  unsigned int v13; // eax
  unsigned int v14; // ecx
  SIZE_T v15; // rax
  SIZE_T v16; // rdx
  HGLOBAL v17; // rcx
  char *v18; // rax
  char *v19; // rbp
  int CDirOffsetFromIndex; // eax
  __int128 v21; // xmm0
  char *v22; // rax
  void *v23; // rsi
  __int64 v24; // rbp
  int v25; // r14d
  _DWORD *v26; // rax
  DWORD NumberOfBytesRead; // [rsp+30h] [rbp-28h] BYREF

  NumberOfBytesRead = 0;
  result = TlsGetValue(dwUnZIPTlsIndex);
  v3 = result;
  if ( result )
  {
    v4 = (void *)result[405];
    v5 = 0;
    if ( a1 )
    {
      v6 = DZSetFilePointer(v4, *(_QWORD *)((char *)result + 4374), 0);
      v7 = v6 == -1;
      if ( !(unsigned int)DeAllocCDirCache(v3) || !(unsigned int)AllocCDirCache(v3) )
        return (_QWORD *)v5;
      *((_WORD *)v3 + 35508) = 0;
      *((_DWORD *)v3 + 1102) = 0;
      v8 = v6 == -1;
      *((_OWORD *)v3 + 4474) = 0;
      *((_OWORD *)v3 + 4475) = 0;
      *((_OWORD *)v3 + 4476) = 0;
      v3[404] = 0;
    }
    else
    {
      v7 = 0;
      v8 = SetFilePointer(v4, 0, 0, 0) == -1;
    }
    if ( !v8 && v3[595] && v3[597] )
    {
      while ( v3[404] < *(int *)((char *)v3 + 4358)
           && ReadFile((HANDLE)v3[405], (char *)v3 + 4412, 0x2Eu, &NumberOfBytesRead, 0)
           && NumberOfBytesRead == 46 )
      {
        v9 = *((_DWORD *)v3 + 1103);
        if ( v9 != 33639248 )
        {
          if ( v9 == 67324752 && *(__int64 *)((char *)v3 + 4358) >= 0x100000000LL )
            *(_QWORD *)((char *)v3 + 4358) = 0;
          return (_QWORD *)v5;
        }
        v10 = *((unsigned __int16 *)v3 + 2220);
        v11 = v10 + *((unsigned __int16 *)v3 + 2221);
        if ( v11 < v10 )
          return (_QWORD *)(unsigned int)-1;
        v12 = v11 + *((unsigned __int16 *)v3 + 2222);
        if ( v12 < v11 )
          return (_QWORD *)(unsigned int)-1;
        v13 = *((_DWORD *)v3 + 1198);
        v14 = v13 + v12;
        if ( v13 + v12 < v13 || (*((_DWORD *)v3 + 1198) = v14, v14 + 46 < v14) )
        {
          *((_DWORD *)v3 + 1198) = -1;
          return (_QWORD *)(unsigned int)-1;
        }
        *((_DWORD *)v3 + 1198) = v14 + 46;
        v15 = GlobalSize((HGLOBAL)v3[595]);
        v16 = *((unsigned int *)v3 + 1198);
        v17 = (HGLOBAL)v3[595];
        if ( v16 > v15 )
          v17 = GlobalReAlloc(v17, v16, 2u);
        if ( !v17 )
          return (_QWORD *)(unsigned int)-1;
        v3[595] = v17;
        v18 = (char *)GlobalLock(v17);
        v3[596] = v18;
        v19 = v18;
        if ( !v18 )
          return (_QWORD *)(unsigned int)-1;
        CDirOffsetFromIndex = GetCDirOffsetFromIndex((HGLOBAL)v3[597]);
        v21 = *(_OWORD *)((char *)v3 + 4412);
        v22 = &v19[CDirOffsetFromIndex];
        v3[596] = v22;
        *(_OWORD *)v22 = v21;
        *((_OWORD *)v22 + 1) = *(_OWORD *)((char *)v3 + 4428);
        *(_OWORD *)(v22 + 30) = *(_OWORD *)((char *)v3 + 4442);
        v3[596] += 46LL;
        if ( !ReadFile((HANDLE)v3[405], (LPVOID)v3[596], v12, &NumberOfBytesRead, 0) || NumberOfBytesRead != v12 )
        {
          v5 = -1;
          GlobalUnlock((HGLOBAL)v3[595]);
          v3[596] = 0;
          return (_QWORD *)v5;
        }
        ++v3[404];
        ++v5;
        v23 = (void *)v3[597];
        v24 = v3[404];
        if ( v23 )
        {
          v25 = *((_DWORD *)v3 + 1198);
          v26 = GlobalLock((HGLOBAL)v3[597]);
          if ( v26 )
          {
            v26[(int)v24] = v25;
            GlobalUnlock(v23);
          }
        }
        GlobalUnlock((HGLOBAL)v3[595]);
        v3[596] = 0;
        if ( v7 )
          return (_QWORD *)v5;
      }
    }
    return (_QWORD *)v5;
  }
  return result;
}

```

## disassembly

```asm
0x18001e3b0  push    rsi
0x18001e3b2  push    rdi
0x18001e3b3  push    r12
0x18001e3b5  sub     rsp, 40h
0x18001e3b9  mov     rax, cs:__security_cookie
0x18001e3c0  xor     rax, rsp
0x18001e3c3  mov     [rsp+58h+var_20], rax
0x18001e3c8  mov     esi, ecx
0x18001e3ca  xor     r12d, r12d
0x18001e3cd  mov     ecx, cs:dwUnZIPTlsIndex; dwTlsIndex
0x18001e3d3  mov     [rsp+58h+NumberOfBytesRead], r12d
0x18001e3d8  call    cs:__imp_TlsGetValue
0x18001e3de  mov     rdi, rax
0x18001e3e1  test    rax, rax
0x18001e3e4  jz      loc_18001E71C
0x18001e3ea  mov     rcx, [rax+0CA8h]; hFile
0x18001e3f1  mov     [rsp+58h+arg_0], rbx
0x18001e3f6  mov     ebx, r12d
0x18001e3f9  mov     [rsp+58h+arg_18], r15
0x18001e3fe  test    esi, esi
0x18001e400  jz      loc_18001E6AE
0x18001e406  mov     rdx, [rax+1116h]
0x18001e40d  xor     r8d, r8d
0x18001e410  call    DZSetFilePointer
0x18001e415  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001e419  mov     r15d, r12d
0x18001e41c  mov     rcx, rdi
0x18001e41f  mov     rsi, rax
0x18001e422  setz    r15b
0x18001e426  call    DeAllocCDirCache
0x18001e42b  test    eax, eax
0x18001e42d  jz      loc_18001E68C
0x18001e433  mov     rcx, rdi
0x18001e436  call    AllocCDirCache
0x18001e43b  test    eax, eax
0x18001e43d  jz      loc_18001E68C
0x18001e443  mov     [rdi+11568h], r12w
0x18001e44b  xorps   xmm0, xmm0
0x18001e44e  mov     [rdi+1138h], r12d
0x18001e455  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18001e459  movups  xmmword ptr [rdi+117A0h], xmm0
0x18001e460  movups  xmmword ptr [rdi+117B0h], xmm0
0x18001e467  movups  xmmword ptr [rdi+117C0h], xmm0
0x18001e46e  mov     [rdi+0CA0h], r12
0x18001e475  jz      loc_18001E68C
0x18001e47b  cmp     [rdi+1298h], rbx
0x18001e482  jz      loc_18001E68C
0x18001e488  cmp     [rdi+12A8h], rbx
0x18001e48f  jz      loc_18001E68C
0x18001e495  mov     [rsp+58h+arg_8], rbp
0x18001e49a  mov     [rsp+58h+arg_10], r14
0x18001e49f  nop
0x18001e4a0  movsxd  rax, dword ptr [rdi+1106h]
0x18001e4a7  cmp     [rdi+0CA0h], rax
0x18001e4ae  jge     loc_18001E682
0x18001e4b4  mov     rcx, [rdi+0CA8h]; hFile
0x18001e4bb  lea     r9, [rsp+58h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18001e4c0  mov     r8d, 2Eh ; '.'; nNumberOfBytesToRead
0x18001e4c6  mov     [rsp+58h+lpOverlapped], r12; lpOverlapped
0x18001e4cb  lea     rdx, [rdi+113Ch]; lpBuffer
0x18001e4d2  call    cs:__imp_ReadFile
0x18001e4d8  cmp     eax, 1
0x18001e4db  jnz     loc_18001E682
0x18001e4e1  cmp     [rsp+58h+NumberOfBytesRead], 2Eh ; '.'
0x18001e4e6  jnz     loc_18001E682
0x18001e4ec  mov     eax, [rdi+113Ch]
0x18001e4f2  cmp     eax, 2014B50h
0x18001e4f7  jnz     loc_18001E6DB
0x18001e4fd  movzx   ecx, word ptr [rdi+1158h]
0x18001e504  movzx   edx, word ptr [rdi+115Ah]
0x18001e50b  add     edx, ecx
0x18001e50d  cmp     edx, ecx
0x18001e50f  jb      loc_18001E67D
0x18001e515  movzx   esi, word ptr [rdi+115Ch]
0x18001e51c  add     esi, edx
0x18001e51e  cmp     esi, edx
0x18001e520  jb      loc_18001E67D
0x18001e526  mov     eax, [rdi+12B8h]
0x18001e52c  lea     ecx, [rax+rsi]
0x18001e52f  cmp     ecx, eax
0x18001e531  jb      loc_18001E673
0x18001e537  lea     eax, [rcx+2Eh]
0x18001e53a  mov     [rdi+12B8h], ecx
0x18001e540  cmp     eax, ecx
0x18001e542  jb      loc_18001E673
0x18001e548  mov     [rdi+12B8h], eax
0x18001e54e  mov     rcx, [rdi+1298h]; hMem
0x18001e555  call    cs:__imp_GlobalSize
0x18001e55b  mov     edx, [rdi+12B8h]; dwBytes
0x18001e561  mov     rcx, [rdi+1298h]; hMem
0x18001e568  cmp     rdx, rax
0x18001e56b  ja      loc_18001E6C7
0x18001e571  test    rcx, rcx
0x18001e574  jz      loc_18001E67D
0x18001e57a  mov     [rdi+1298h], rcx
0x18001e581  call    cs:__imp_GlobalLock
0x18001e587  mov     [rdi+12A0h], rax
0x18001e58e  mov     rbp, rax
0x18001e591  test    rax, rax
0x18001e594  jz      loc_18001E67D
0x18001e59a  mov     edx, [rdi+0CA0h]
0x18001e5a0  mov     rcx, [rdi+12A8h]; hMem
0x18001e5a7  call    GetCDirOffsetFromIndex
0x18001e5ac  movups  xmm0, xmmword ptr [rdi+113Ch]
0x18001e5b3  mov     eax, eax
0x18001e5b5  lea     r9, [rsp+58h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18001e5ba  add     rax, rbp
0x18001e5bd  mov     [rsp+58h+lpOverlapped], r12; lpOverlapped
0x18001e5c2  mov     [rdi+12A0h], rax
0x18001e5c9  mov     r8d, esi; nNumberOfBytesToRead
0x18001e5cc  movups  xmmword ptr [rax], xmm0
0x18001e5cf  movups  xmm1, xmmword ptr [rdi+114Ch]
0x18001e5d6  movups  xmmword ptr [rax+10h], xmm1
0x18001e5da  movups  xmm0, xmmword ptr [rdi+115Ah]
0x18001e5e1  movups  xmmword ptr [rax+1Eh], xmm0
0x18001e5e5  add     qword ptr [rdi+12A0h], 2Eh ; '.'
0x18001e5ed  mov     rdx, [rdi+12A0h]; lpBuffer
0x18001e5f4  mov     rcx, [rdi+0CA8h]; hFile
0x18001e5fb  call    cs:__imp_ReadFile
0x18001e601  test    eax, eax
0x18001e603  jz      loc_18001E6FE
0x18001e609  cmp     [rsp+58h+NumberOfBytesRead], esi
0x18001e60d  jnz     loc_18001E6FE
0x18001e613  inc     qword ptr [rdi+0CA0h]
0x18001e61a  inc     ebx
0x18001e61c  mov     rsi, [rdi+12A8h]
0x18001e623  mov     rbp, [rdi+0CA0h]
0x18001e62a  test    rsi, rsi
0x18001e62d  jz      short loc_18001E654
0x18001e62f  mov     r14d, [rdi+12B8h]
0x18001e636  mov     rcx, rsi; hMem
0x18001e639  call    cs:__imp_GlobalLock
0x18001e63f  test    rax, rax
0x18001e642  jz      short loc_18001E654
0x18001e644  movsxd  rdx, ebp
0x18001e647  mov     rcx, rsi; hMem
0x18001e64a  mov     [rax+rdx*4], r14d
0x18001e64e  call    cs:__imp_GlobalUnlock
0x18001e654  mov     rcx, [rdi+1298h]; hMem
0x18001e65b  call    cs:__imp_GlobalUnlock
0x18001e661  mov     [rdi+12A0h], r12
0x18001e668  test    r15d, r15d
0x18001e66b  jz      loc_18001E4A0
0x18001e671  jmp     short loc_18001E682
0x18001e673  mov     dword ptr [rdi+12B8h], 0FFFFFFFFh
0x18001e67d  mov     ebx, 0FFFFFFFFh
0x18001e682  mov     rbp, [rsp+58h+arg_8]
0x18001e687  mov     r14, [rsp+58h+arg_10]
0x18001e68c  mov     r15, [rsp+58h+arg_18]
0x18001e691  mov     eax, ebx
0x18001e693  mov     rbx, [rsp+58h+arg_0]
0x18001e698  mov     rcx, [rsp+58h+var_20]
0x18001e69d  xor     rcx, rsp; StackCookie
0x18001e6a0  call    __security_check_cookie
0x18001e6a5  add     rsp, 40h
0x18001e6a9  pop     r12
0x18001e6ab  pop     rdi
0x18001e6ac  pop     rsi
0x18001e6ad  retn
0x18001e6ae  xor     r9d, r9d; dwMoveMethod
0x18001e6b1  xor     r8d, r8d; lpDistanceToMoveHigh
0x18001e6b4  xor     edx, edx; lDistanceToMove
0x18001e6b6  mov     r15d, r12d
0x18001e6b9  call    cs:__imp_SetFilePointer
0x18001e6bf  cmp     eax, 0FFFFFFFFh
0x18001e6c2  jmp     loc_18001E475
0x18001e6c7  mov     r8d, 2; uFlags
0x18001e6cd  call    cs:__imp_GlobalReAlloc
0x18001e6d3  mov     rcx, rax
0x18001e6d6  jmp     loc_18001E571
0x18001e6db  cmp     eax, 4034B50h
0x18001e6e0  jnz     short loc_18001E682
0x18001e6e2  mov     rax, 100000000h
0x18001e6ec  cmp     [rdi+1106h], rax
0x18001e6f3  jl      short loc_18001E682
0x18001e6f5  mov     [rdi+1106h], r12
0x18001e6fc  jmp     short loc_18001E682
0x18001e6fe  mov     rcx, [rdi+1298h]; hMem
0x18001e705  mov     ebx, 0FFFFFFFFh
0x18001e70a  call    cs:__imp_GlobalUnlock
0x18001e710  mov     [rdi+12A0h], r12
0x18001e717  jmp     loc_18001E682
0x18001e71c  jmp     loc_18001E698
```
