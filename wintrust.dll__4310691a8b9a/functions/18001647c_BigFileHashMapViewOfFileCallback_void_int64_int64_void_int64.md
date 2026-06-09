# BigFileHashMapViewOfFileCallback(void *,__int64,__int64 *,void * *,__int64 *)

- ea: `0x18001647c`
- end: `0x18001663a`
- name: `?BigFileHashMapViewOfFileCallback@@YAJPEAX_JPEA_JPEAPEAX2@Z`
- size: `446`
- prototype: `__int64 __fastcall(void *, __int64, __int64 *, void **, __int64 *)`
- caller_count: `4`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180015bd0`
- `0x180015d18`
- `0x180016400`
- `0x18003d6cc`

## callees

- `0x18001647c`
- `0x1800168c8`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180016532`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180016553`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x1800165a1`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180016532`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180016553`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x1800165a1`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180016584`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180016584`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001661d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001661d`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1800164d9`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1800164d9`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800165c6`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800165c6`

## pseudocode

```c
__int64 __fastcall BigFileHashMapViewOfFileCallback(unsigned int *a1, __int64 a2, __int64 *a3, void **a4, __int64 *a5)
{
  const void *v9; // rcx
  __int64 v10; // rdi
  __int64 v11; // rsi
  __int64 v12; // rdi
  void *v13; // rcx
  DWORD v14; // r8d
  LPVOID v15; // rax
  unsigned int v16; // edi
  DWORD LastError; // eax
  LARGE_INTEGER liDistanceToMove; // [rsp+30h] [rbp-28h]
  union _LARGE_INTEGER NewFilePointer; // [rsp+38h] [rbp-20h] BYREF
  DWORD NumberOfBytesRead; // [rsp+60h] [rbp+8h] BYREF

  NewFilePointer.QuadPart = 0;
  NumberOfBytesRead = 0;
  if ( a1 && *((_QWORD *)a1 + 1) )
  {
    v9 = (const void *)*((_QWORD *)a1 + 5);
    if ( v9 )
    {
      *((_QWORD *)a1 + 5) = 0;
      if ( !UnmapViewOfFile(v9) )
        goto LABEL_23;
    }
    v10 = *((_QWORD *)a1 + 2);
    v11 = a2 - a2 % *a1;
    *((_QWORD *)a1 + 7) = v11;
    if ( v11 < v10 )
    {
      v12 = v10 - v11;
      if ( v12 >= (unsigned int)I_CryptGetMaxHashBytesToMapRegValue() )
        LODWORD(v12) = I_CryptGetMaxHashBytesToMapRegValue();
      v13 = (void *)*((_QWORD *)a1 + 8);
      a1[12] = v12;
      if ( SetFilePointerEx(v13, 0, &NewFilePointer, 1u) )
      {
        liDistanceToMove = *(LARGE_INTEGER *)(a1 + 14);
        if ( SetFilePointerEx(*((HANDLE *)a1 + 8), liDistanceToMove, 0, 0) )
        {
          v14 = a1[20];
          if ( v14 >= a1[12] )
            v14 = a1[12];
          if ( ReadFile(*((HANDLE *)a1 + 8), *((LPVOID *)a1 + 9), v14, &NumberOfBytesRead, 0) )
          {
            if ( SetFilePointerEx(*((HANDLE *)a1 + 8), NewFilePointer, 0, 0) )
            {
              v15 = MapViewOfFile(*((HANDLE *)a1 + 1), 4u, liDistanceToMove.HighPart, liDistanceToMove.LowPart, a1[12]);
              *((_QWORD *)a1 + 5) = v15;
              if ( v15 )
              {
                if ( a3 )
                  *a3 = *((_QWORD *)a1 + 7);
                if ( a4 )
                  *a4 = (void *)*((_QWORD *)a1 + 5);
                if ( a5 )
                  *a5 = a1[12];
                return 0;
              }
            }
          }
        }
      }
LABEL_23:
      v16 = -1073741536;
      LastError = GetLastError();
      a1[1] = LastError;
      if ( !LastError )
        a1[1] = -2147418113;
      return v16;
    }
  }
  return 3221225485LL;
}

```

## disassembly

```asm
0x18001647c  mov     rax, rsp
0x18001647f  mov     [rax+10h], rbx
0x180016483  mov     [rax+18h], rsi
0x180016487  push    rdi
0x180016488  push    r14
0x18001648a  push    r15
0x18001648c  sub     rsp, 40h
0x180016490  mov     qword ptr [rax-20h], 0
0x180016498  mov     r14, r9
0x18001649b  mov     dword ptr [rax+8], 0
0x1800164a2  mov     r15, r8
0x1800164a5  mov     qword ptr [rsp+58h+liDistanceToMove], 0
0x1800164ae  mov     rsi, rdx
0x1800164b1  mov     rbx, rcx
0x1800164b4  test    rcx, rcx
0x1800164b7  jz      loc_180016633
0x1800164bd  cmp     qword ptr [rcx+8], 0
0x1800164c2  jz      loc_180016633
0x1800164c8  mov     rcx, [rcx+28h]; lpBaseAddress
0x1800164cc  test    rcx, rcx
0x1800164cf  jz      short loc_1800164E7
0x1800164d1  mov     qword ptr [rbx+28h], 0
0x1800164d9  call    cs:__imp_UnmapViewOfFile
0x1800164df  test    eax, eax
0x1800164e1  jz      loc_180016618
0x1800164e7  mov     ecx, [rbx]
0x1800164e9  mov     rax, rsi
0x1800164ec  mov     rdi, [rbx+10h]
0x1800164f0  cqo
0x1800164f2  idiv    rcx
0x1800164f5  sub     rsi, rdx
0x1800164f8  mov     [rbx+38h], rsi
0x1800164fc  cmp     rsi, rdi
0x1800164ff  jge     loc_180016633
0x180016505  sub     rdi, rsi
0x180016508  call    I_CryptGetMaxHashBytesToMapRegValue
0x18001650d  mov     eax, eax
0x18001650f  cmp     rdi, rax
0x180016512  jl      short loc_18001651B
0x180016514  call    I_CryptGetMaxHashBytesToMapRegValue
0x180016519  mov     edi, eax
0x18001651b  mov     rdx, qword ptr [rsp+58h+liDistanceToMove]; liDistanceToMove
0x180016520  lea     r8, [rsp+58h+NewFilePointer]; lpNewFilePointer
0x180016525  mov     rcx, [rbx+40h]; hFile
0x180016529  mov     r9d, 1; dwMoveMethod
0x18001652f  mov     [rbx+30h], edi
0x180016532  call    cs:__imp_SetFilePointerEx
0x180016538  test    eax, eax
0x18001653a  jz      loc_180016618
0x180016540  mov     rdx, [rbx+38h]; liDistanceToMove
0x180016544  xor     r9d, r9d; dwMoveMethod
0x180016547  mov     rcx, [rbx+40h]; hFile
0x18001654b  xor     r8d, r8d; lpNewFilePointer
0x18001654e  mov     qword ptr [rsp+58h+liDistanceToMove], rdx
0x180016553  call    cs:__imp_SetFilePointerEx
0x180016559  test    eax, eax
0x18001655b  jz      loc_180016618
0x180016561  mov     r8d, [rbx+50h]
0x180016565  lea     r9, [rsp+58h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18001656a  cmp     r8d, [rbx+30h]
0x18001656e  mov     rdx, [rbx+48h]; lpBuffer
0x180016572  cmovnb  r8d, [rbx+30h]; nNumberOfBytesToRead
0x180016577  mov     rcx, [rbx+40h]; hFile
0x18001657b  mov     [rsp+58h+lpOverlapped], 0; lpOverlapped
0x180016584  call    cs:__imp_ReadFile
0x18001658a  test    eax, eax
0x18001658c  jz      loc_180016618
0x180016592  mov     rdx, qword ptr [rsp+58h+NewFilePointer]; liDistanceToMove
0x180016597  xor     r9d, r9d; dwMoveMethod
0x18001659a  mov     rcx, [rbx+40h]; hFile
0x18001659e  xor     r8d, r8d; lpNewFilePointer
0x1800165a1  call    cs:__imp_SetFilePointerEx
0x1800165a7  test    eax, eax
0x1800165a9  jz      short loc_180016618
0x1800165ab  mov     eax, [rbx+30h]
0x1800165ae  mov     edx, 4; dwDesiredAccess
0x1800165b3  mov     r9d, dword ptr [rsp+58h+liDistanceToMove]; dwFileOffsetLow
0x1800165b8  mov     r8d, dword ptr [rsp+58h+liDistanceToMove+4]; dwFileOffsetHigh
0x1800165bd  mov     rcx, [rbx+8]; hFileMappingObject
0x1800165c1  mov     [rsp+58h+lpOverlapped], rax; dwNumberOfBytesToMap
0x1800165c6  call    cs:__imp_MapViewOfFile
0x1800165cc  mov     [rbx+28h], rax
0x1800165d0  test    rax, rax
0x1800165d3  jz      short loc_180016618
0x1800165d5  test    r15, r15
0x1800165d8  jz      short loc_1800165E1
0x1800165da  mov     rax, [rbx+38h]
0x1800165de  mov     [r15], rax
0x1800165e1  test    r14, r14
0x1800165e4  jz      short loc_1800165ED
0x1800165e6  mov     rax, [rbx+28h]
0x1800165ea  mov     [r14], rax
0x1800165ed  mov     rcx, [rsp+58h+arg_20]
0x1800165f5  test    rcx, rcx
0x1800165f8  jz      short loc_180016600
0x1800165fa  mov     eax, [rbx+30h]
0x1800165fd  mov     [rcx], rax
0x180016600  xor     edi, edi
0x180016602  mov     eax, edi
0x180016604  mov     rbx, [rsp+58h+arg_8]
0x180016609  mov     rsi, [rsp+58h+arg_10]
0x18001660e  add     rsp, 40h
0x180016612  pop     r15
0x180016614  pop     r14
0x180016616  pop     rdi
0x180016617  retn
0x180016618  mov     edi, 0C0000120h
0x18001661d  call    cs:__imp_GetLastError
0x180016623  mov     [rbx+4], eax
0x180016626  test    eax, eax
0x180016628  jnz     short loc_180016602
0x18001662a  mov     dword ptr [rbx+4], 8000FFFFh
0x180016631  jmp     short loc_180016602
0x180016633  mov     eax, 0C000000Dh
0x180016638  jmp     short loc_180016604
```
