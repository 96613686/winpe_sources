# CabReader::FdiFileWrite(__int64,void *,uint)

- ea: `0x180068520`
- end: `0x180068737`
- name: `?FdiFileWrite@CabReader@@CAI_JPEAXI@Z`
- size: `535`
- prototype: `UINT __cdecl(INT_PTR hf, void *pv, UINT cb)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180030f64`
- `0x1800358c0`
- `0x180036300`
- `0x180068520`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180068682`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180068682`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006866f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006866f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800685f9`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800685f9`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x1800685ba`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x1800685ba`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180068630`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180068707`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180068630`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180068707`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180068652`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180068652`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x180068588`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x180068588`

## pseudocode

```c
__int64 __fastcall CabReader::FdiFileWrite(INT_PTR hf, void *pv, UINT cb)
{
  unsigned int v3; // edi
  DWORD v4; // ebp
  int v7; // ecx
  unsigned int TempPath2W; // eax
  HANDLE FileW; // rax
  DWORD v10; // r8d
  const void *v11; // rdx
  void *v12; // rcx
  LONG v13; // ebx
  int Error; // ebx
  int v15; // eax
  unsigned int v16; // ecx
  void *v17; // rcx
  BOOL v18; // eax
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-468h] BYREF
  WCHAR PathName[264]; // [rsp+50h] [rbp-458h] BYREF
  WCHAR TempFileName[264]; // [rsp+260h] [rbp-248h] BYREF

  v3 = 0;
  v4 = cb;
  if ( (*(_BYTE *)hf & 1) == 0 )
    goto LABEL_21;
  v7 = *(_DWORD *)(hf + 16);
  if ( v7 + cb < cb )
    return v3;
  if ( v7 + cb <= *(_DWORD *)(hf + 24) )
  {
LABEL_21:
    if ( (*(_BYTE *)hf & 1) == 0 )
    {
      v17 = *(void **)(hf + 32);
      NumberOfBytesWritten = 0;
      v18 = WriteFile(v17, pv, v4, &NumberOfBytesWritten, 0);
      return v18 ? NumberOfBytesWritten : 0;
    }
    if ( memcpy_s_1(
           (void *const)(*(_QWORD *)(hf + 8) + *(int *)(hf + 16)),
           *(_DWORD *)(hf + 24) - *(_DWORD *)(hf + 16),
           pv,
           v4) )
    {
      v15 = -2147467259;
    }
    else
    {
      v16 = v4 + *(_DWORD *)(hf + 16);
      if ( v16 >= v4 )
      {
        if ( v16 <= 0x7FFFFFFF )
        {
          *(_DWORD *)(hf + 16) = v16;
          v15 = 0;
          if ( *(_DWORD *)(hf + 20) < (signed int)v16 )
            *(_DWORD *)(hf + 20) = v16;
          goto LABEL_30;
        }
        *(_DWORD *)(hf + 16) = -1;
      }
      v15 = -2147024362;
    }
LABEL_30:
    if ( v15 >= 0 )
      return v4;
    return v3;
  }
  if ( (*(_BYTE *)hf & 2) == 0 )
  {
    v4 = *(_DWORD *)(hf + 24) - v7;
    goto LABEL_21;
  }
  TempPath2W = GetTempPath2W(260, PathName);
  if ( (TempPath2W && TempPath2W < 0x104 || (int)ResultFromKnownLastError() >= 0)
    && (GetTempFileNameW(PathName, L"SD_", 0, TempFileName) || (int)ResultFromKnownLastError() >= 0) )
  {
    FileW = CreateFileW(TempFileName, 0xC0000000, 0, 0, 2u, 0x4000100u, 0);
    *(_QWORD *)(hf + 32) = FileW;
    if ( FileW != (HANDLE)-1LL || (int)ResultFromKnownLastError() >= 0 )
    {
      v10 = *(_DWORD *)(hf + 20);
      v11 = *(const void **)(hf + 8);
      v12 = *(void **)(hf + 32);
      NumberOfBytesWritten = 0;
      if ( WriteFile(v12, v11, v10, &NumberOfBytesWritten, 0)
        && NumberOfBytesWritten == *(_DWORD *)(hf + 20)
        && (v13 = *(_DWORD *)(hf + 16), SetFilePointer(*(HANDLE *)(hf + 32), v13, 0, 0) == v13) )
      {
        Error = 0;
      }
      else
      {
        Error = ResultFromKnownLastError();
        if ( Error < 0 )
        {
          CloseHandle(*(HANDLE *)(hf + 32));
LABEL_20:
          if ( Error < 0 )
            return v3;
          goto LABEL_21;
        }
      }
      CoTaskMemFree(*(LPVOID *)(hf + 8));
      *(_DWORD *)hf &= ~1u;
      *(_QWORD *)(hf + 8) = 0;
      goto LABEL_20;
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180068520  push    rbx
0x180068522  push    rbp
0x180068523  push    rsi
0x180068524  push    rdi
0x180068525  push    r14
0x180068527  sub     rsp, 480h
0x18006852e  mov     rax, cs:__security_cookie
0x180068535  xor     rax, rsp
0x180068538  mov     [rsp+4A8h+var_38], rax
0x180068540  xor     edi, edi
0x180068542  mov     ebp, r8d
0x180068545  test    byte ptr [rcx], 1
0x180068548  mov     r14, rdx
0x18006854b  mov     rsi, rcx
0x18006854e  jz      loc_180068690
0x180068554  mov     ecx, [rcx+10h]
0x180068557  lea     eax, [rcx+r8]
0x18006855b  cmp     eax, r8d
0x18006855e  jb      loc_180068717
0x180068564  cmp     eax, [rsi+18h]
0x180068567  jbe     loc_180068690
0x18006856d  test    byte ptr [rsi], 2
0x180068570  jnz     short loc_18006857C
0x180068572  mov     ebp, [rsi+18h]
0x180068575  sub     ebp, ecx
0x180068577  jmp     loc_180068690
0x18006857c  mov     ebx, 104h
0x180068581  lea     rdx, [rsp+4A8h+PathName]
0x180068586  mov     ecx, ebx
0x180068588  call    cs:__imp_GetTempPath2W
0x18006858e  test    eax, eax
0x180068590  jz      short loc_180068596
0x180068592  cmp     eax, ebx
0x180068594  jb      short loc_1800685A3
0x180068596  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18006859b  test    eax, eax
0x18006859d  js      loc_180068717
0x1800685a3  lea     r9, [rsp+4A8h+TempFileName]; lpTempFileName
0x1800685ab  xor     r8d, r8d; uUnique
0x1800685ae  lea     rdx, PrefixString; "SD_"
0x1800685b5  lea     rcx, [rsp+4A8h+PathName]; lpPathName
0x1800685ba  call    cs:__imp_GetTempFileNameW
0x1800685c0  test    eax, eax
0x1800685c2  jnz     short loc_1800685D1
0x1800685c4  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800685c9  test    eax, eax
0x1800685cb  js      loc_180068717
0x1800685d1  mov     [rsp+4A8h+hTemplateFile], rdi; hTemplateFile
0x1800685d6  lea     rcx, [rsp+4A8h+TempFileName]; lpFileName
0x1800685de  mov     [rsp+4A8h+dwFlagsAndAttributes], 4000100h; dwFlagsAndAttributes
0x1800685e6  xor     r9d, r9d; lpSecurityAttributes
0x1800685e9  xor     r8d, r8d; dwShareMode
0x1800685ec  mov     [rsp+4A8h+dwCreationDisposition], 2; dwCreationDisposition
0x1800685f4  mov     edx, 0C0000000h; dwDesiredAccess
0x1800685f9  call    cs:__imp_CreateFileW
0x1800685ff  mov     [rsi+20h], rax
0x180068603  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180068607  jnz     short loc_180068616
0x180068609  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18006860e  test    eax, eax
0x180068610  js      loc_180068717
0x180068616  mov     r8d, [rsi+14h]; nNumberOfBytesToWrite
0x18006861a  lea     r9, [rsp+4A8h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18006861f  mov     rdx, [rsi+8]; lpBuffer
0x180068623  mov     rcx, [rsi+20h]; hFile
0x180068627  mov     [rsp+4A8h+NumberOfBytesWritten], edi
0x18006862b  mov     qword ptr [rsp+4A8h+dwCreationDisposition], rdi; lpOverlapped
0x180068630  call    cs:__imp_WriteFile
0x180068636  test    eax, eax
0x180068638  jz      short loc_180068660
0x18006863a  mov     eax, [rsi+14h]
0x18006863d  cmp     [rsp+4A8h+NumberOfBytesWritten], eax
0x180068641  jnz     short loc_180068660
0x180068643  mov     ebx, [rsi+10h]
0x180068646  xor     r9d, r9d; dwMoveMethod
0x180068649  mov     rcx, [rsi+20h]; hFile
0x18006864d  mov     edx, ebx; lDistanceToMove
0x18006864f  xor     r8d, r8d; lpDistanceToMoveHigh
0x180068652  call    cs:__imp_SetFilePointer
0x180068658  cmp     eax, ebx
0x18006865a  jnz     short loc_180068660
0x18006865c  mov     ebx, edi
0x18006865e  jmp     short loc_18006866B
0x180068660  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180068665  mov     ebx, eax
0x180068667  test    eax, eax
0x180068669  js      short loc_18006867E
0x18006866b  mov     rcx, [rsi+8]; pv
0x18006866f  call    cs:__imp_CoTaskMemFree
0x180068675  and     dword ptr [rsi], 0FFFFFFFEh
0x180068678  mov     [rsi+8], rdi
0x18006867c  jmp     short loc_180068688
0x18006867e  mov     rcx, [rsi+20h]; hObject
0x180068682  call    cs:__imp_CloseHandle
0x180068688  test    ebx, ebx
0x18006868a  js      loc_180068717
0x180068690  test    byte ptr [rsi], 1
0x180068693  jz      short loc_1800686EF
0x180068695  mov     eax, [rsi+18h]
0x180068698  mov     r8, r14; Source
0x18006869b  sub     eax, [rsi+10h]
0x18006869e  movsxd  rcx, dword ptr [rsi+10h]
0x1800686a2  add     rcx, [rsi+8]; Destination
0x1800686a6  movsxd  rdx, eax; DestinationSize
0x1800686a9  mov     r9d, ebp; SourceSize
0x1800686ac  call    memcpy_s_1
0x1800686b1  test    eax, eax
0x1800686b3  jz      short loc_1800686BC
0x1800686b5  mov     eax, 80004005h
0x1800686ba  jmp     short loc_1800686E8
0x1800686bc  mov     ecx, [rsi+10h]
0x1800686bf  add     ecx, ebp
0x1800686c1  cmp     ecx, ebp
0x1800686c3  jb      short loc_1800686E3
0x1800686c5  cmp     ecx, 7FFFFFFFh
0x1800686cb  ja      short loc_1800686DC
0x1800686cd  mov     [rsi+10h], ecx
0x1800686d0  mov     eax, edi
0x1800686d2  cmp     [rsi+14h], ecx
0x1800686d5  jge     short loc_1800686E8
0x1800686d7  mov     [rsi+14h], ecx
0x1800686da  jmp     short loc_1800686E8
0x1800686dc  mov     dword ptr [rsi+10h], 0FFFFFFFFh
0x1800686e3  mov     eax, 80070216h
0x1800686e8  test    eax, eax
0x1800686ea  cmovns  edi, ebp
0x1800686ed  jmp     short loc_180068717
0x1800686ef  mov     rcx, [rsi+20h]; hFile
0x1800686f3  lea     r9, [rsp+4A8h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800686f8  mov     r8d, ebp; nNumberOfBytesToWrite
0x1800686fb  mov     [rsp+4A8h+NumberOfBytesWritten], edi
0x1800686ff  mov     rdx, r14; lpBuffer
0x180068702  mov     qword ptr [rsp+4A8h+dwCreationDisposition], rdi; lpOverlapped
0x180068707  call    cs:__imp_WriteFile
0x18006870d  neg     eax
0x18006870f  sbb     ecx, ecx
0x180068711  and     ecx, [rsp+4A8h+NumberOfBytesWritten]
0x180068715  mov     edi, ecx
0x180068717  mov     eax, edi
0x180068719  mov     rcx, [rsp+4A8h+var_38]
0x180068721  xor     rcx, rsp; StackCookie
0x180068724  call    __security_check_cookie
0x180068729  add     rsp, 480h
0x180068730  pop     r14
0x180068732  pop     rdi
0x180068733  pop     rsi
0x180068734  pop     rbp
0x180068735  pop     rbx
0x180068736  retn
```
