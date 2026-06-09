# WTSFreeMemoryExW

- ea: `0x180003920`
- end: `0x180003a43`
- name: `WTSFreeMemoryExW`
- size: `291`
- prototype: `BOOL __stdcall(WTS_TYPE_CLASS WTSTypeClass, PVOID pMemory, ULONG NumberOfEntries)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180002450`
- `0x180002780`
- `0x180007c30`

## callees

- `0x180003920`
- `0x180004720`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003941`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800039a7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003941`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800039a7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800039d1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800039e1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003a05`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003a14`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003a23`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800039d1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800039e1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003a05`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003a14`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003a23`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180003982`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180003982`

## pseudocode

```c
BOOL __stdcall WTSFreeMemoryExW(WTS_TYPE_CLASS WTSTypeClass, PVOID pMemory, ULONG NumberOfEntries)
{
  __int64 v3; // rbx
  __int32 v7; // ecx
  __int32 v8; // ecx
  SIZE_T v9; // rax
  _BYTE *v10; // rcx
  unsigned __int64 v11; // rbp
  void *v12; // rcx
  void *v13; // rcx
  char *v14; // rbp
  void *v15; // rcx
  void *v16; // rcx

  v3 = 0;
  if ( !pMemory )
    goto LABEL_2;
  if ( WTSTypeClass == WTSTypeProcessInfoLevel0 )
  {
    if ( NumberOfEntries )
    {
      do
      {
        v14 = (char *)pMemory + 24 * v3;
        v15 = (void *)*((_QWORD *)v14 + 1);
        if ( v15 )
          LocalFree(v15);
        v16 = (void *)*((_QWORD *)v14 + 2);
        if ( v16 )
          LocalFree(v16);
        v3 = (unsigned int)(v3 + 1);
      }
      while ( (unsigned int)v3 < NumberOfEntries );
    }
    goto LABEL_27;
  }
  v7 = WTSTypeClass - 1;
  if ( !v7 )
  {
    if ( NumberOfEntries )
    {
      do
      {
        v11 = (unsigned __int64)(unsigned int)v3 << 6;
        v12 = *(void **)((char *)pMemory + v11 + 8);
        if ( v12 )
          LocalFree(v12);
        v13 = *(void **)((char *)pMemory + v11 + 16);
        if ( v13 )
          LocalFree(v13);
        LODWORD(v3) = v3 + 1;
      }
      while ( (unsigned int)v3 < NumberOfEntries );
    }
LABEL_27:
    LocalFree(pMemory);
    return 1;
  }
  v8 = v7 - 1;
  if ( v8 )
  {
    if ( (unsigned int)(v8 - 1) > 1 || NumberOfEntries != 1 )
    {
LABEL_2:
      SetLastError(0x57u);
      return 0;
    }
    v9 = LocalSize(pMemory);
    if ( v9 )
    {
      v10 = pMemory;
      do
      {
        *v10++ = 0;
        --v9;
      }
      while ( v9 );
    }
    goto LABEL_27;
  }
  FreeExSessionEnumData(pMemory, NumberOfEntries);
  return 1;
}

```

## disassembly

```asm
0x180003920  mov     [rsp+arg_8], rbx
0x180003925  mov     [rsp+arg_10], rsi
0x18000392a  push    rdi
0x18000392b  sub     rsp, 20h
0x18000392f  xor     ebx, ebx
0x180003931  mov     esi, r8d
0x180003934  mov     rdi, rdx
0x180003937  test    rdx, rdx
0x18000393a  jnz     short loc_180003959
0x18000393c  mov     ecx, 57h ; 'W'; dwErrCode
0x180003941  call    cs:__imp_SetLastError
0x180003947  mov     eax, ebx
0x180003949  mov     rbx, [rsp+28h+arg_8]
0x18000394e  mov     rsi, [rsp+28h+arg_10]
0x180003953  add     rsp, 20h
0x180003957  pop     rdi
0x180003958  retn
0x180003959  mov     [rsp+28h+arg_0], rbp
0x18000395e  test    ecx, ecx
0x180003960  jz      loc_1800039EF
0x180003966  sub     ecx, 1
0x180003969  jz      short loc_1800039BD
0x18000396b  sub     ecx, 1
0x18000396e  jz      short loc_1800039B1
0x180003970  sub     ecx, 1
0x180003973  jz      short loc_18000397A
0x180003975  cmp     ecx, 1
0x180003978  jnz     short loc_1800039A2
0x18000397a  cmp     esi, 1
0x18000397d  jnz     short loc_1800039A2
0x18000397f  mov     rcx, rdi; hMem
0x180003982  call    cs:__imp_LocalSize
0x180003988  test    rax, rax
0x18000398b  jz      loc_180003A20
0x180003991  mov     rcx, rdi
0x180003994  mov     [rcx], bl
0x180003996  lea     rcx, [rcx+1]
0x18000399a  sub     rax, 1
0x18000399e  jnz     short loc_180003994
0x1800039a0  jmp     short loc_180003A20
0x1800039a2  mov     ecx, 57h ; 'W'; dwErrCode
0x1800039a7  call    cs:__imp_SetLastError
0x1800039ad  mov     eax, ebx
0x1800039af  jmp     short loc_180003A2E
0x1800039b1  mov     edx, esi
0x1800039b3  mov     rcx, rdi
0x1800039b6  call    _FreeExSessionEnumData
0x1800039bb  jmp     short loc_180003A29
0x1800039bd  test    esi, esi
0x1800039bf  jz      short loc_180003A20
0x1800039c1  mov     ebp, ebx
0x1800039c3  shl     rbp, 6
0x1800039c7  mov     rcx, [rbp+rdi+8]; hMem
0x1800039cc  test    rcx, rcx
0x1800039cf  jz      short loc_1800039D7
0x1800039d1  call    cs:__imp_LocalFree
0x1800039d7  mov     rcx, [rbp+rdi+10h]; hMem
0x1800039dc  test    rcx, rcx
0x1800039df  jz      short loc_1800039E7
0x1800039e1  call    cs:__imp_LocalFree
0x1800039e7  inc     ebx
0x1800039e9  cmp     ebx, esi
0x1800039eb  jb      short loc_1800039C1
0x1800039ed  jmp     short loc_180003A20
0x1800039ef  test    esi, esi
0x1800039f1  jz      short loc_180003A20
0x1800039f3  lea     rcx, [rbx+rbx*2]
0x1800039f7  lea     rbp, [rdi+rcx*8]
0x1800039fb  mov     rcx, [rdi+rcx*8+8]; hMem
0x180003a00  test    rcx, rcx
0x180003a03  jz      short loc_180003A0B
0x180003a05  call    cs:__imp_LocalFree
0x180003a0b  mov     rcx, [rbp+10h]; hMem
0x180003a0f  test    rcx, rcx
0x180003a12  jz      short loc_180003A1A
0x180003a14  call    cs:__imp_LocalFree
0x180003a1a  inc     ebx
0x180003a1c  cmp     ebx, esi
0x180003a1e  jb      short loc_1800039F3
0x180003a20  mov     rcx, rdi; hMem
0x180003a23  call    cs:__imp_LocalFree
0x180003a29  mov     eax, 1
0x180003a2e  mov     rbp, [rsp+28h+arg_0]
0x180003a33  mov     rbx, [rsp+28h+arg_8]
0x180003a38  mov     rsi, [rsp+28h+arg_10]
0x180003a3d  add     rsp, 20h
0x180003a41  pop     rdi
0x180003a42  retn
```
