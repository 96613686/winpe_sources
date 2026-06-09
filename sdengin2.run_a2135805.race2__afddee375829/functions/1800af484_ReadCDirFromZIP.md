# ReadCDirFromZIP

- ea: `0x1800af484`
- end: `0x1800af7d8`
- name: `ReadCDirFromZIP`
- size: `852`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1800aecb8`

## callees

- `0x1800a8544`
- `0x1800abd30`
- `0x1800ac310`
- `0x1800ad368`
- `0x1800af484`

## import_xrefs

- `KERNEL32!GlobalUnlock` at `0x1800af749`
- `KERNEL32!GlobalUnlock` at `0x1800af764`
- `KERNEL32!GlobalUnlock` at `0x1800af749`
- `KERNEL32!GlobalUnlock` at `0x1800af764`
- `KERNEL32!GlobalLock` at `0x1800af677`
- `KERNEL32!GlobalLock` at `0x1800af731`
- `KERNEL32!GlobalLock` at `0x1800af677`
- `KERNEL32!GlobalLock` at `0x1800af731`
- `KERNEL32!GlobalReAlloc` at `0x1800af658`
- `KERNEL32!GlobalReAlloc` at `0x1800af658`
- `KERNEL32!GlobalSize` at `0x1800af634`
- `KERNEL32!GlobalSize` at `0x1800af634`
- `KERNEL32!ReadFile` at `0x1800af5b5`
- `KERNEL32!ReadFile` at `0x1800af6f4`
- `KERNEL32!ReadFile` at `0x1800af5b5`
- `KERNEL32!ReadFile` at `0x1800af6f4`
- `KERNEL32!SetFilePointer` at `0x1800af54b`
- `KERNEL32!SetFilePointer` at `0x1800af54b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800af4aa`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800af4aa`

## pseudocode

```c
_QWORD *__fastcall ReadCDirFromZIP(int a1)
{
  _QWORD *result; // rax
  _QWORD *v3; // rbx
  void *v4; // rcx
  unsigned int v5; // esi
  BOOL v6; // edi
  __int128 *v7; // r15
  DWORD v8; // ecx
  DWORD v9; // edx
  DWORD v10; // ebp
  unsigned int v11; // eax
  unsigned int v12; // ecx
  SIZE_T v13; // rax
  SIZE_T v14; // rdx
  HGLOBAL v15; // rcx
  char *v16; // rax
  char *v17; // r14
  int CDirOffsetFromIndex; // eax
  __int128 v19; // xmm0
  char *v20; // rax
  void *v21; // rbp
  int v22; // r14d
  __int64 v23; // r15
  _DWORD *v24; // rax
  DWORD NumberOfBytesRead; // [rsp+68h] [rbp+10h] BYREF

  NumberOfBytesRead = 0;
  result = TlsGetValue(dwUnZIPTlsIndex);
  v3 = result;
  if ( result )
  {
    v4 = (void *)result[571];
    v5 = 0;
    if ( a1 )
    {
      v6 = DZSetFilePointer(v4, *(_QWORD *)((char *)result + 5452), 0) == -1;
      if ( (unsigned int)DeAllocCDirCache(v3) )
      {
        if ( !(unsigned int)AllocCDirCache(v3) )
          return (_QWORD *)v5;
        *((_BYTE *)v3 + 71530) = 0;
        *((_DWORD *)v3 + 1371) = 0;
        *(_OWORD *)((char *)v3 + 71838) = 0;
        *(_OWORD *)((char *)v3 + 71854) = 0;
        *(_OWORD *)((char *)v3 + 71870) = 0;
        v3[570] = 0;
      }
      else
      {
        v6 = 1;
      }
      if ( !v6 )
        goto LABEL_11;
    }
    else if ( SetFilePointer(v4, 0, 0, 0) != -1 )
    {
      v6 = 0;
LABEL_11:
      if ( *(_QWORD *)((char *)v3 + 5566) && *(_QWORD *)((char *)v3 + 5582) )
      {
        do
        {
          if ( v3[570] >= *((int *)v3 + 1359) )
            return (_QWORD *)v5;
          v7 = (__int128 *)(v3 + 686);
          if ( !ReadFile((HANDLE)v3[571], v3 + 686, 0x2Eu, &NumberOfBytesRead, 0) || NumberOfBytesRead != 46 )
            return (_QWORD *)v5;
          if ( *(_DWORD *)v7 == 33639248 )
          {
            v8 = *((unsigned __int16 *)v3 + 2758);
            v9 = v8 + *((unsigned __int16 *)v3 + 2759);
            if ( v9 >= v8 )
            {
              v10 = v9 + *((unsigned __int16 *)v3 + 2760);
              if ( v10 >= v9 )
              {
                v11 = *(_DWORD *)((char *)v3 + 5598);
                v12 = v11 + v10;
                if ( v11 + v10 < v11 || v12 + 46 < v12 )
                {
                  *(_DWORD *)((char *)v3 + 5598) = -1;
                }
                else
                {
                  *(_DWORD *)((char *)v3 + 5598) = v12 + 46;
                  v13 = GlobalSize(*(HGLOBAL *)((char *)v3 + 5566));
                  v14 = *(unsigned int *)((char *)v3 + 5598);
                  v15 = *(HGLOBAL *)((char *)v3 + 5566);
                  if ( v14 > v13 )
                    v15 = GlobalReAlloc(v15, v14, 2u);
                  if ( v15 )
                  {
                    *(_QWORD *)((char *)v3 + 5566) = v15;
                    v16 = (char *)GlobalLock(v15);
                    *(_QWORD *)((char *)v3 + 5574) = v16;
                    v17 = v16;
                    if ( v16 )
                    {
                      CDirOffsetFromIndex = GetCDirOffsetFromIndex(*(HGLOBAL *)((char *)v3 + 5582));
                      v19 = *v7;
                      v20 = &v17[CDirOffsetFromIndex];
                      *(_QWORD *)((char *)v3 + 5574) = v20;
                      *(_OWORD *)v20 = v19;
                      *((_OWORD *)v20 + 1) = *((_OWORD *)v3 + 344);
                      *(_OWORD *)(v20 + 30) = *(_OWORD *)((char *)v3 + 5518);
                      *(_QWORD *)((char *)v3 + 5574) += 46LL;
                      if ( ReadFile((HANDLE)v3[571], *(LPVOID *)((char *)v3 + 5574), v10, &NumberOfBytesRead, 0)
                        && NumberOfBytesRead == v10 )
                      {
                        ++v3[570];
                        ++v5;
                        v21 = *(void **)((char *)v3 + 5582);
                        if ( v21 )
                        {
                          v22 = *(_DWORD *)((char *)v3 + 5598);
                          v23 = *((int *)v3 + 1140);
                          v24 = GlobalLock(*(HGLOBAL *)((char *)v3 + 5582));
                          if ( v24 )
                          {
                            v24[v23] = v22;
                            GlobalUnlock(v21);
                          }
                        }
                      }
                      else
                      {
                        v5 = -1;
                        v6 = 1;
                      }
                      GlobalUnlock(*(HGLOBAL *)((char *)v3 + 5566));
                      *(_QWORD *)((char *)v3 + 5574) = 0;
                      continue;
                    }
                  }
                }
              }
            }
            v5 = -1;
          }
          else if ( *(_DWORD *)v7 == 67324752 && *(__int64 *)((char *)v3 + 5436) >= 0x100000000LL )
          {
            *(_QWORD *)((char *)v3 + 5436) = 0;
          }
          v6 = 1;
        }
        while ( !v6 );
      }
    }
    return (_QWORD *)v5;
  }
  return result;
}

```

## disassembly

```asm
0x1800af484  mov     [rsp+arg_0], rbx
0x1800af489  mov     [rsp+arg_10], rbp
0x1800af48e  push    rsi
0x1800af48f  push    rdi
0x1800af490  push    r13
0x1800af492  push    r14
0x1800af494  push    r15
0x1800af496  sub     rsp, 30h
0x1800af49a  mov     edi, ecx
0x1800af49c  mov     [rsp+58h+NumberOfBytesRead], 0
0x1800af4a4  mov     ecx, cs:dwUnZIPTlsIndex; dwTlsIndex
0x1800af4aa  call    cs:__imp_TlsGetValue
0x1800af4b1  nop     dword ptr [rax+rax+00h]
0x1800af4b6  mov     rbx, rax
0x1800af4b9  test    rax, rax
0x1800af4bc  jz      loc_1800AF7C0
0x1800af4c2  mov     rcx, [rax+11D8h]; hFile
0x1800af4c9  xor     esi, esi
0x1800af4cb  lea     r13d, [rsi+1]
0x1800af4cf  test    edi, edi
0x1800af4d1  jz      short loc_1800AF543
0x1800af4d3  mov     rdx, [rax+154Ch]
0x1800af4da  xor     r8d, r8d
0x1800af4dd  call    DZSetFilePointer
0x1800af4e2  xor     edi, edi
0x1800af4e4  mov     rcx, rbx
0x1800af4e7  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800af4eb  setz    dil
0x1800af4ef  call    DeAllocCDirCache
0x1800af4f4  test    eax, eax
0x1800af4f6  jz      short loc_1800AF536
0x1800af4f8  mov     rcx, rbx
0x1800af4fb  call    AllocCDirCache
0x1800af500  test    eax, eax
0x1800af502  jz      loc_1800AF7BE
0x1800af508  mov     [rbx+1176Ah], sil
0x1800af50f  xorps   xmm0, xmm0
0x1800af512  mov     [rbx+156Ch], esi
0x1800af518  movups  xmmword ptr [rbx+1189Eh], xmm0
0x1800af51f  movups  xmmword ptr [rbx+118AEh], xmm0
0x1800af526  movups  xmmword ptr [rbx+118BEh], xmm0
0x1800af52d  mov     [rbx+11D0h], rsi
0x1800af534  jmp     short loc_1800AF539
0x1800af536  mov     edi, r13d
0x1800af539  test    edi, edi
0x1800af53b  jnz     loc_1800AF7BE
0x1800af541  jmp     short loc_1800AF562
0x1800af543  xor     r9d, r9d; dwMoveMethod
0x1800af546  xor     r8d, r8d; lpDistanceToMoveHigh
0x1800af549  xor     edx, edx; lDistanceToMove
0x1800af54b  call    cs:__imp_SetFilePointer
0x1800af552  nop     dword ptr [rax+rax+00h]
0x1800af557  cmp     eax, 0FFFFFFFFh
0x1800af55a  jz      loc_1800AF7BE
0x1800af560  xor     edi, edi
0x1800af562  cmp     [rbx+15BEh], rsi
0x1800af569  jz      loc_1800AF7BE
0x1800af56f  cmp     [rbx+15CEh], rsi
0x1800af576  jz      loc_1800AF7BE
0x1800af57c  movsxd  rax, dword ptr [rbx+153Ch]
0x1800af583  cmp     [rbx+11D0h], rax
0x1800af58a  jge     loc_1800AF7BE
0x1800af590  mov     rcx, [rbx+11D8h]; hFile
0x1800af597  lea     r15, [rbx+1570h]
0x1800af59e  mov     rdx, r15; lpBuffer
0x1800af5a1  mov     [rsp+58h+lpOverlapped], 0; lpOverlapped
0x1800af5aa  lea     r9, [rsp+58h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800af5af  mov     r8d, 2Eh ; '.'; nNumberOfBytesToRead
0x1800af5b5  call    cs:__imp_ReadFile
0x1800af5bc  nop     dword ptr [rax+rax+00h]
0x1800af5c1  cmp     eax, r13d
0x1800af5c4  jnz     loc_1800AF7BE
0x1800af5ca  cmp     [rsp+58h+NumberOfBytesRead], 2Eh ; '.'
0x1800af5cf  jnz     loc_1800AF7BE
0x1800af5d5  cmp     dword ptr [r15], 2014B50h
0x1800af5dc  jnz     loc_1800AF78C
0x1800af5e2  movzx   ecx, word ptr [rbx+158Ch]
0x1800af5e9  movzx   edx, word ptr [rbx+158Eh]
0x1800af5f0  add     edx, ecx
0x1800af5f2  cmp     edx, ecx
0x1800af5f4  jb      loc_1800AF787
0x1800af5fa  movzx   ebp, word ptr [rbx+1590h]
0x1800af601  add     ebp, edx
0x1800af603  cmp     ebp, edx
0x1800af605  jb      loc_1800AF787
0x1800af60b  mov     eax, [rbx+15DEh]
0x1800af611  lea     ecx, [rax+rbp]
0x1800af614  cmp     ecx, eax
0x1800af616  jb      loc_1800AF77D
0x1800af61c  lea     eax, [rcx+2Eh]
0x1800af61f  cmp     eax, ecx
0x1800af621  jb      loc_1800AF77D
0x1800af627  mov     [rbx+15DEh], eax
0x1800af62d  mov     rcx, [rbx+15BEh]; hMem
0x1800af634  call    cs:__imp_GlobalSize
0x1800af63b  nop     dword ptr [rax+rax+00h]
0x1800af640  mov     edx, [rbx+15DEh]; dwBytes
0x1800af646  mov     rcx, [rbx+15BEh]; hMem
0x1800af64d  cmp     rdx, rax
0x1800af650  jbe     short loc_1800AF667
0x1800af652  mov     r8d, 2; uFlags
0x1800af658  call    cs:__imp_GlobalReAlloc
0x1800af65f  nop     dword ptr [rax+rax+00h]
0x1800af664  mov     rcx, rax; hMem
0x1800af667  test    rcx, rcx
0x1800af66a  jz      loc_1800AF787
0x1800af670  mov     [rbx+15BEh], rcx
0x1800af677  call    cs:__imp_GlobalLock
0x1800af67e  nop     dword ptr [rax+rax+00h]
0x1800af683  mov     [rbx+15C6h], rax
0x1800af68a  mov     r14, rax
0x1800af68d  test    rax, rax
0x1800af690  jz      loc_1800AF787
0x1800af696  mov     edx, [rbx+11D0h]
0x1800af69c  mov     rcx, [rbx+15CEh]; hMem
0x1800af6a3  call    GetCDirOffsetFromIndex
0x1800af6a8  movups  xmm0, xmmword ptr [r15]
0x1800af6ac  mov     eax, eax
0x1800af6ae  lea     r9, [rsp+58h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800af6b3  add     rax, r14
0x1800af6b6  mov     [rsp+58h+lpOverlapped], 0; lpOverlapped
0x1800af6bf  mov     [rbx+15C6h], rax
0x1800af6c6  mov     r8d, ebp; nNumberOfBytesToRead
0x1800af6c9  movups  xmmword ptr [rax], xmm0
0x1800af6cc  movups  xmm1, xmmword ptr [r15+10h]
0x1800af6d1  movups  xmmword ptr [rax+10h], xmm1
0x1800af6d5  movups  xmm0, xmmword ptr [r15+1Eh]
0x1800af6da  movups  xmmword ptr [rax+1Eh], xmm0
0x1800af6de  add     qword ptr [rbx+15C6h], 2Eh ; '.'
0x1800af6e6  mov     rdx, [rbx+15C6h]; lpBuffer
0x1800af6ed  mov     rcx, [rbx+11D8h]; hFile
0x1800af6f4  call    cs:__imp_ReadFile
0x1800af6fb  nop     dword ptr [rax+rax+00h]
0x1800af700  test    eax, eax
0x1800af702  jz      short loc_1800AF757
0x1800af704  cmp     [rsp+58h+NumberOfBytesRead], ebp
0x1800af708  jnz     short loc_1800AF757
0x1800af70a  add     [rbx+11D0h], r13
0x1800af711  add     esi, r13d
0x1800af714  mov     rbp, [rbx+15CEh]
0x1800af71b  test    rbp, rbp
0x1800af71e  jz      short loc_1800AF75D
0x1800af720  mov     r14d, [rbx+15DEh]
0x1800af727  mov     rcx, rbp; hMem
0x1800af72a  movsxd  r15, dword ptr [rbx+11D0h]
0x1800af731  call    cs:__imp_GlobalLock
0x1800af738  nop     dword ptr [rax+rax+00h]
0x1800af73d  test    rax, rax
0x1800af740  jz      short loc_1800AF75D
0x1800af742  mov     rcx, rbp; hMem
0x1800af745  mov     [rax+r15*4], r14d
0x1800af749  call    cs:__imp_GlobalUnlock
0x1800af750  nop     dword ptr [rax+rax+00h]
0x1800af755  jmp     short loc_1800AF75D
0x1800af757  or      esi, 0FFFFFFFFh
0x1800af75a  mov     edi, r13d
0x1800af75d  mov     rcx, [rbx+15BEh]; hMem
0x1800af764  call    cs:__imp_GlobalUnlock
0x1800af76b  nop     dword ptr [rax+rax+00h]
0x1800af770  mov     qword ptr [rbx+15C6h], 0
0x1800af77b  jmp     short loc_1800AF7B6
0x1800af77d  mov     dword ptr [rbx+15DEh], 0FFFFFFFFh
0x1800af787  or      esi, 0FFFFFFFFh
0x1800af78a  jmp     short loc_1800AF7B3
0x1800af78c  cmp     dword ptr [r15], 4034B50h
0x1800af793  jnz     short loc_1800AF7B3
0x1800af795  mov     rax, 100000000h
0x1800af79f  cmp     [rbx+153Ch], rax
0x1800af7a6  jl      short loc_1800AF7B3
0x1800af7a8  mov     qword ptr [rbx+153Ch], 0
0x1800af7b3  mov     edi, r13d
0x1800af7b6  test    edi, edi
0x1800af7b8  jz      loc_1800AF57C
0x1800af7be  mov     eax, esi
0x1800af7c0  mov     rbx, [rsp+58h+arg_0]
0x1800af7c5  mov     rbp, [rsp+58h+arg_10]
0x1800af7ca  add     rsp, 30h
0x1800af7ce  pop     r15
0x1800af7d0  pop     r14
0x1800af7d2  pop     r13
0x1800af7d4  pop     rdi
0x1800af7d5  pop     rsi
0x1800af7d6  retn
```
