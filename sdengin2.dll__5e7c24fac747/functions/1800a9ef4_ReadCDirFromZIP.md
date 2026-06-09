# ReadCDirFromZIP

- ea: `0x1800a9ef4`
- end: `0x1800aa20b`
- name: `ReadCDirFromZIP`
- size: `791`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1800a9748`

## callees

- `0x1800a3608`
- `0x1800a6b74`
- `0x1800a70e8`
- `0x1800a7f5c`
- `0x1800a9ef4`

## import_xrefs

- `KERNEL32!GlobalUnlock` at `0x1800aa189`
- `KERNEL32!GlobalUnlock` at `0x1800aa19e`
- `KERNEL32!GlobalUnlock` at `0x1800aa189`
- `KERNEL32!GlobalUnlock` at `0x1800aa19e`
- `KERNEL32!GlobalLock` at `0x1800aa0c9`
- `KERNEL32!GlobalLock` at `0x1800aa177`
- `KERNEL32!GlobalLock` at `0x1800aa0c9`
- `KERNEL32!GlobalLock` at `0x1800aa177`
- `KERNEL32!GlobalReAlloc` at `0x1800aa0b0`
- `KERNEL32!GlobalReAlloc` at `0x1800aa0b0`
- `KERNEL32!GlobalSize` at `0x1800aa092`
- `KERNEL32!GlobalSize` at `0x1800aa092`
- `KERNEL32!ReadFile` at `0x1800aa019`
- `KERNEL32!ReadFile` at `0x1800aa140`
- `KERNEL32!ReadFile` at `0x1800aa019`
- `KERNEL32!ReadFile` at `0x1800aa140`
- `KERNEL32!SetFilePointer` at `0x1800a9fb5`
- `KERNEL32!SetFilePointer` at `0x1800a9fb5`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800a9f1a`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800a9f1a`

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
0x1800a9ef4  mov     [rsp+arg_0], rbx
0x1800a9ef9  mov     [rsp+arg_10], rbp
0x1800a9efe  push    rsi
0x1800a9eff  push    rdi
0x1800a9f00  push    r13
0x1800a9f02  push    r14
0x1800a9f04  push    r15
0x1800a9f06  sub     rsp, 30h
0x1800a9f0a  mov     edi, ecx
0x1800a9f0c  mov     [rsp+58h+NumberOfBytesRead], 0
0x1800a9f14  mov     ecx, cs:dwUnZIPTlsIndex; dwTlsIndex
0x1800a9f1a  call    cs:__imp_TlsGetValue
0x1800a9f20  mov     rbx, rax
0x1800a9f23  test    rax, rax
0x1800a9f26  jz      loc_1800AA1F4
0x1800a9f2c  mov     rcx, [rax+11D8h]; hFile
0x1800a9f33  xor     esi, esi
0x1800a9f35  lea     r13d, [rsi+1]
0x1800a9f39  test    edi, edi
0x1800a9f3b  jz      short loc_1800A9FAD
0x1800a9f3d  mov     rdx, [rax+154Ch]
0x1800a9f44  xor     r8d, r8d
0x1800a9f47  call    DZSetFilePointer
0x1800a9f4c  xor     edi, edi
0x1800a9f4e  mov     rcx, rbx
0x1800a9f51  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800a9f55  setz    dil
0x1800a9f59  call    DeAllocCDirCache
0x1800a9f5e  test    eax, eax
0x1800a9f60  jz      short loc_1800A9FA0
0x1800a9f62  mov     rcx, rbx
0x1800a9f65  call    AllocCDirCache
0x1800a9f6a  test    eax, eax
0x1800a9f6c  jz      loc_1800AA1F2
0x1800a9f72  mov     [rbx+1176Ah], sil
0x1800a9f79  xorps   xmm0, xmm0
0x1800a9f7c  mov     [rbx+156Ch], esi
0x1800a9f82  movups  xmmword ptr [rbx+1189Eh], xmm0
0x1800a9f89  movups  xmmword ptr [rbx+118AEh], xmm0
0x1800a9f90  movups  xmmword ptr [rbx+118BEh], xmm0
0x1800a9f97  mov     [rbx+11D0h], rsi
0x1800a9f9e  jmp     short loc_1800A9FA3
0x1800a9fa0  mov     edi, r13d
0x1800a9fa3  test    edi, edi
0x1800a9fa5  jnz     loc_1800AA1F2
0x1800a9fab  jmp     short loc_1800A9FC6
0x1800a9fad  xor     r9d, r9d; dwMoveMethod
0x1800a9fb0  xor     r8d, r8d; lpDistanceToMoveHigh
0x1800a9fb3  xor     edx, edx; lDistanceToMove
0x1800a9fb5  call    cs:__imp_SetFilePointer
0x1800a9fbb  cmp     eax, 0FFFFFFFFh
0x1800a9fbe  jz      loc_1800AA1F2
0x1800a9fc4  xor     edi, edi
0x1800a9fc6  cmp     [rbx+15BEh], rsi
0x1800a9fcd  jz      loc_1800AA1F2
0x1800a9fd3  cmp     [rbx+15CEh], rsi
0x1800a9fda  jz      loc_1800AA1F2
0x1800a9fe0  movsxd  rax, dword ptr [rbx+153Ch]
0x1800a9fe7  cmp     [rbx+11D0h], rax
0x1800a9fee  jge     loc_1800AA1F2
0x1800a9ff4  mov     rcx, [rbx+11D8h]; hFile
0x1800a9ffb  lea     r15, [rbx+1570h]
0x1800aa002  mov     rdx, r15; lpBuffer
0x1800aa005  mov     [rsp+58h+lpOverlapped], 0; lpOverlapped
0x1800aa00e  lea     r9, [rsp+58h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800aa013  mov     r8d, 2Eh ; '.'; nNumberOfBytesToRead
0x1800aa019  call    cs:__imp_ReadFile
0x1800aa01f  cmp     eax, r13d
0x1800aa022  jnz     loc_1800AA1F2
0x1800aa028  cmp     [rsp+58h+NumberOfBytesRead], 2Eh ; '.'
0x1800aa02d  jnz     loc_1800AA1F2
0x1800aa033  cmp     dword ptr [r15], 2014B50h
0x1800aa03a  jnz     loc_1800AA1C0
0x1800aa040  movzx   ecx, word ptr [rbx+158Ch]
0x1800aa047  movzx   edx, word ptr [rbx+158Eh]
0x1800aa04e  add     edx, ecx
0x1800aa050  cmp     edx, ecx
0x1800aa052  jb      loc_1800AA1BB
0x1800aa058  movzx   ebp, word ptr [rbx+1590h]
0x1800aa05f  add     ebp, edx
0x1800aa061  cmp     ebp, edx
0x1800aa063  jb      loc_1800AA1BB
0x1800aa069  mov     eax, [rbx+15DEh]
0x1800aa06f  lea     ecx, [rax+rbp]
0x1800aa072  cmp     ecx, eax
0x1800aa074  jb      loc_1800AA1B1
0x1800aa07a  lea     eax, [rcx+2Eh]
0x1800aa07d  cmp     eax, ecx
0x1800aa07f  jb      loc_1800AA1B1
0x1800aa085  mov     [rbx+15DEh], eax
0x1800aa08b  mov     rcx, [rbx+15BEh]; hMem
0x1800aa092  call    cs:__imp_GlobalSize
0x1800aa098  mov     edx, [rbx+15DEh]; dwBytes
0x1800aa09e  mov     rcx, [rbx+15BEh]; hMem
0x1800aa0a5  cmp     rdx, rax
0x1800aa0a8  jbe     short loc_1800AA0B9
0x1800aa0aa  mov     r8d, 2; uFlags
0x1800aa0b0  call    cs:__imp_GlobalReAlloc
0x1800aa0b6  mov     rcx, rax; hMem
0x1800aa0b9  test    rcx, rcx
0x1800aa0bc  jz      loc_1800AA1BB
0x1800aa0c2  mov     [rbx+15BEh], rcx
0x1800aa0c9  call    cs:__imp_GlobalLock
0x1800aa0cf  mov     [rbx+15C6h], rax
0x1800aa0d6  mov     r14, rax
0x1800aa0d9  test    rax, rax
0x1800aa0dc  jz      loc_1800AA1BB
0x1800aa0e2  mov     edx, [rbx+11D0h]
0x1800aa0e8  mov     rcx, [rbx+15CEh]; hMem
0x1800aa0ef  call    GetCDirOffsetFromIndex
0x1800aa0f4  movups  xmm0, xmmword ptr [r15]
0x1800aa0f8  mov     eax, eax
0x1800aa0fa  lea     r9, [rsp+58h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800aa0ff  add     rax, r14
0x1800aa102  mov     [rsp+58h+lpOverlapped], 0; lpOverlapped
0x1800aa10b  mov     [rbx+15C6h], rax
0x1800aa112  mov     r8d, ebp; nNumberOfBytesToRead
0x1800aa115  movups  xmmword ptr [rax], xmm0
0x1800aa118  movups  xmm1, xmmword ptr [r15+10h]
0x1800aa11d  movups  xmmword ptr [rax+10h], xmm1
0x1800aa121  movups  xmm0, xmmword ptr [r15+1Eh]
0x1800aa126  movups  xmmword ptr [rax+1Eh], xmm0
0x1800aa12a  add     qword ptr [rbx+15C6h], 2Eh ; '.'
0x1800aa132  mov     rdx, [rbx+15C6h]; lpBuffer
0x1800aa139  mov     rcx, [rbx+11D8h]; hFile
0x1800aa140  call    cs:__imp_ReadFile
0x1800aa146  test    eax, eax
0x1800aa148  jz      short loc_1800AA191
0x1800aa14a  cmp     [rsp+58h+NumberOfBytesRead], ebp
0x1800aa14e  jnz     short loc_1800AA191
0x1800aa150  add     [rbx+11D0h], r13
0x1800aa157  add     esi, r13d
0x1800aa15a  mov     rbp, [rbx+15CEh]
0x1800aa161  test    rbp, rbp
0x1800aa164  jz      short loc_1800AA197
0x1800aa166  mov     r14d, [rbx+15DEh]
0x1800aa16d  mov     rcx, rbp; hMem
0x1800aa170  movsxd  r15, dword ptr [rbx+11D0h]
0x1800aa177  call    cs:__imp_GlobalLock
0x1800aa17d  test    rax, rax
0x1800aa180  jz      short loc_1800AA197
0x1800aa182  mov     rcx, rbp; hMem
0x1800aa185  mov     [rax+r15*4], r14d
0x1800aa189  call    cs:__imp_GlobalUnlock
0x1800aa18f  jmp     short loc_1800AA197
0x1800aa191  or      esi, 0FFFFFFFFh
0x1800aa194  mov     edi, r13d
0x1800aa197  mov     rcx, [rbx+15BEh]; hMem
0x1800aa19e  call    cs:__imp_GlobalUnlock
0x1800aa1a4  mov     qword ptr [rbx+15C6h], 0
0x1800aa1af  jmp     short loc_1800AA1EA
0x1800aa1b1  mov     dword ptr [rbx+15DEh], 0FFFFFFFFh
0x1800aa1bb  or      esi, 0FFFFFFFFh
0x1800aa1be  jmp     short loc_1800AA1E7
0x1800aa1c0  cmp     dword ptr [r15], 4034B50h
0x1800aa1c7  jnz     short loc_1800AA1E7
0x1800aa1c9  mov     rax, 100000000h
0x1800aa1d3  cmp     [rbx+153Ch], rax
0x1800aa1da  jl      short loc_1800AA1E7
0x1800aa1dc  mov     qword ptr [rbx+153Ch], 0
0x1800aa1e7  mov     edi, r13d
0x1800aa1ea  test    edi, edi
0x1800aa1ec  jz      loc_1800A9FE0
0x1800aa1f2  mov     eax, esi
0x1800aa1f4  mov     rbx, [rsp+58h+arg_0]
0x1800aa1f9  mov     rbp, [rsp+58h+arg_10]
0x1800aa1fe  add     rsp, 30h
0x1800aa202  pop     r15
0x1800aa204  pop     r14
0x1800aa206  pop     r13
0x1800aa208  pop     rdi
0x1800aa209  pop     rsi
0x1800aa20a  retn
```
