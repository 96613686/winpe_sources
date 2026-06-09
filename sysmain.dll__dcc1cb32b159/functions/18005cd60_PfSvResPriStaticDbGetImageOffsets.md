# PfSvResPriStaticDbGetImageOffsets

- ea: `0x18005cd60`
- end: `0x18005cf98`
- name: `PfSvResPriStaticDbGetImageOffsets`
- size: `568`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, loader_planting, service_task`

## callers

- `0x180082dc8`

## callees

- `0x18005cd60`
- `0x18005cfa0`
- `0x180067634`

## import_xrefs

- `ntdll!RtlImageNtHeader` at `0x18005ce1e`
- `ntdll!RtlImageNtHeader` at `0x18005ce1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005cdb8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005cdee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005cdb8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005cdee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005cf5c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005cf6a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005cf5c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005cf6a`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18005cf78`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18005cf78`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18005ce0d`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18005ce0d`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18005cddd`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18005cddd`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18005cda9`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18005cda9`

## pseudocode

```c
__int64 __fastcall PfSvResPriStaticDbGetImageOffsets(__int64 a1, __int64 a2, LPCWSTR lpFileName, char *a4)
{
  unsigned int v4; // r14d
  __int64 v5; // rbx
  HANDLE FileW; // rax
  void *v8; // r13
  DWORD POGODebugDirectory; // ebx
  HANDLE FileMappingW; // rax
  void *v11; // rbp
  char *v12; // rdi
  char *v13; // rax
  PIMAGE_NT_HEADERS v14; // rcx
  unsigned int SizeOfHeapReserve_high; // edx
  __int64 v16; // rax
  unsigned int v17; // edx
  __int64 v18; // r15
  unsigned int SizeOfImage; // r8d
  char *v20; // rsi
  unsigned __int128 v21; // rax
  unsigned __int64 v22; // r15
  __int64 v23; // r9
  __int64 v24; // r9
  int v25; // ecx
  int v26; // edx
  unsigned int v28; // [rsp+40h] [rbp-58h]
  int v29[2]; // [rsp+48h] [rbp-50h] BYREF
  __int64 v30; // [rsp+50h] [rbp-48h]

  v4 = 0;
  v5 = a2;
  FileW = CreateFileW(lpFileName, 0x80000000, 1u, 0, 3u, 0, 0);
  v8 = FileW;
  if ( FileW == (HANDLE)-1LL )
    return GetLastError();
  FileMappingW = CreateFileMappingW(FileW, 0, 0x1000002u, 0, 0, 0);
  v11 = FileMappingW;
  if ( FileMappingW )
  {
    v13 = (char *)MapViewOfFile(FileMappingW, 4u, 0, 0, 0);
    v12 = v13;
    if ( !v13 )
      goto LABEL_5;
    v14 = RtlImageNtHeader(v13);
    if ( !v14 )
      goto LABEL_5;
    if ( v14->OptionalHeader.Magic == 267 )
    {
      SizeOfHeapReserve_high = HIDWORD(v14->OptionalHeader.SizeOfHeapReserve);
      v16 = 168;
    }
    else
    {
      if ( v14->OptionalHeader.Magic != 523 )
      {
LABEL_26:
        POGODebugDirectory = 11;
        goto LABEL_27;
      }
      SizeOfHeapReserve_high = v14->OptionalHeader.NumberOfRvaAndSizes;
      v16 = 184;
    }
    if ( SizeOfHeapReserve_high > 6 )
    {
      if ( *(DWORD *)((char *)&v14->Signature + v16) )
      {
        v17 = *(_DWORD *)((char *)&v14->FileHeader.Machine + v16);
        if ( v17 )
        {
          v18 = v17;
          SizeOfImage = v14->OptionalHeader.SizeOfImage;
          v20 = &v12[*(unsigned int *)((char *)&v14->Signature + v16)];
          v21 = *(unsigned int *)((char *)&v14->FileHeader.Machine + v16) * (unsigned __int128)0x2492492492492493uLL;
          v28 = SizeOfImage;
          v22 = (*((_QWORD *)&v21 + 1) + ((unsigned __int64)(v18 - *((_QWORD *)&v21 + 1)) >> 1)) >> 4;
          v23 = v14->FileHeader.NumberOfSections - 1LL;
          *(_QWORD *)v29 = (char *)&v14->OptionalHeader + v14->FileHeader.SizeOfOptionalHeader;
          v24 = *(_QWORD *)v29 + 40 * v23;
          v30 = v24;
          while ( v4 < (unsigned int)v22 )
          {
            if ( *((_DWORD *)v20 + 3) == 13 )
            {
              v25 = *((_DWORD *)v20 + 5);
              if ( v25 )
              {
                v26 = *((_DWORD *)v20 + 4);
                if ( v26 + v25 < SizeOfImage )
                {
                  POGODebugDirectory = PfSvResPriStaticDbReadPOGODebugDirectory(
                                         (int)v12 + v25,
                                         v26,
                                         (int)v29,
                                         v24,
                                         a4,
                                         a1,
                                         v5);
                  if ( POGODebugDirectory )
                    goto LABEL_27;
                  v5 = a2;
                  SizeOfImage = v28;
                  LODWORD(v24) = v30;
                }
              }
            }
            ++v4;
            v20 += 28;
          }
          if ( !*(_DWORD *)(a1 + 32)
            || (POGODebugDirectory = PfSvResPriStaticDbInsertImageOffsetIntoBtDb(a1, v5, 0, 1)) == 0 )
          {
            POGODebugDirectory = 0;
          }
          goto LABEL_27;
        }
      }
    }
    goto LABEL_26;
  }
  v12 = 0;
LABEL_5:
  POGODebugDirectory = GetLastError();
LABEL_27:
  CloseHandle(v8);
  if ( v11 )
    CloseHandle(v11);
  if ( v12 )
    UnmapViewOfFile(v12);
  return POGODebugDirectory;
}

```

## disassembly

```asm
0x18005cd60  mov     r11, rsp
0x18005cd63  mov     [r11+8], rbx
0x18005cd67  mov     [r11+20h], r9
0x18005cd6b  mov     [r11+10h], rdx
0x18005cd6f  push    rbp
0x18005cd70  push    rsi
0x18005cd71  push    rdi
0x18005cd72  push    r12
0x18005cd74  push    r13
0x18005cd76  push    r14
0x18005cd78  push    r15
0x18005cd7a  sub     rsp, 60h
0x18005cd7e  xor     r14d, r14d
0x18005cd81  mov     rax, r8
0x18005cd84  mov     [r11-68h], r14
0x18005cd88  mov     rbx, rdx
0x18005cd8b  mov     r12, rcx
0x18005cd8e  mov     [r11-70h], r14d
0x18005cd92  xor     r9d, r9d; lpSecurityAttributes
0x18005cd95  mov     [rsp+98h+dwCreationDisposition], 3; dwCreationDisposition
0x18005cd9d  lea     r8d, [r14+1]; dwShareMode
0x18005cda1  mov     edx, 80000000h; dwDesiredAccess
0x18005cda6  mov     rcx, rax; lpFileName
0x18005cda9  call    cs:__imp_CreateFileW
0x18005cdaf  mov     r13, rax
0x18005cdb2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18005cdb6  jnz     short loc_18005CDC5
0x18005cdb8  call    cs:__imp_GetLastError
0x18005cdbe  mov     ebx, eax
0x18005cdc0  jmp     loc_18005CF7E
0x18005cdc5  mov     [rsp+98h+lpName], r14; lpName
0x18005cdca  xor     r9d, r9d; dwMaximumSizeHigh
0x18005cdcd  xor     edx, edx; lpFileMappingAttributes
0x18005cdcf  mov     [rsp+98h+dwCreationDisposition], r14d; dwMaximumSizeLow
0x18005cdd4  mov     r8d, 1000002h; flProtect
0x18005cdda  mov     rcx, r13; hFile
0x18005cddd  call    cs:__imp_CreateFileMappingW
0x18005cde3  mov     rbp, rax
0x18005cde6  test    rax, rax
0x18005cde9  jnz     short loc_18005CDFB
0x18005cdeb  mov     rdi, r14
0x18005cdee  call    cs:__imp_GetLastError
0x18005cdf4  mov     ebx, eax
0x18005cdf6  jmp     loc_18005CF59
0x18005cdfb  xor     r9d, r9d; dwFileOffsetLow
0x18005cdfe  mov     qword ptr [rsp+98h+dwCreationDisposition], r14; dwNumberOfBytesToMap
0x18005ce03  xor     r8d, r8d; dwFileOffsetHigh
0x18005ce06  mov     rcx, rbp; hFileMappingObject
0x18005ce09  lea     edx, [r9+4]; dwDesiredAccess
0x18005ce0d  call    cs:__imp_MapViewOfFile
0x18005ce13  mov     rdi, rax
0x18005ce16  test    rax, rax
0x18005ce19  jz      short loc_18005CDEE
0x18005ce1b  mov     rcx, rax; BaseAddress
0x18005ce1e  call    cs:__imp_RtlImageNtHeader
0x18005ce24  mov     rcx, rax
0x18005ce27  test    rax, rax
0x18005ce2a  jz      short loc_18005CDEE
0x18005ce2c  mov     eax, 10Bh
0x18005ce31  cmp     [rcx+18h], ax
0x18005ce35  jnz     short loc_18005CE41
0x18005ce37  mov     edx, [rcx+74h]
0x18005ce3a  mov     eax, 0A8h
0x18005ce3f  jmp     short loc_18005CE5B
0x18005ce41  mov     eax, 20Bh
0x18005ce46  cmp     [rcx+18h], ax
0x18005ce4a  jnz     loc_18005CF54
0x18005ce50  mov     edx, [rcx+84h]
0x18005ce56  mov     eax, 0B8h
0x18005ce5b  cmp     edx, 6
0x18005ce5e  jbe     loc_18005CF54
0x18005ce64  cmp     [rax+rcx], r14d
0x18005ce68  jz      loc_18005CF54
0x18005ce6e  mov     edx, [rax+rcx+4]
0x18005ce72  test    edx, edx
0x18005ce74  jz      loc_18005CF54
0x18005ce7a  mov     esi, [rax+rcx]
0x18005ce7d  mov     r15d, edx
0x18005ce80  mov     r8d, [rcx+50h]
0x18005ce84  mov     rax, 2492492492492493h
0x18005ce8e  movzx   r9d, word ptr [rcx+6]
0x18005ce93  add     rsi, rdi
0x18005ce96  mul     rdx
0x18005ce99  mov     [rsp+98h+var_58], r8d
0x18005ce9e  sub     r15, rdx
0x18005cea1  shr     r15, 1
0x18005cea4  add     r15, rdx
0x18005cea7  movzx   edx, word ptr [rcx+14h]
0x18005ceab  add     rdx, 18h
0x18005ceaf  shr     r15, 4
0x18005ceb3  add     rdx, rcx
0x18005ceb6  dec     r9
0x18005ceb9  mov     qword ptr [rsp+98h+var_50], rdx
0x18005cebe  lea     r9, [r9+r9*4]
0x18005cec2  lea     r9, [rdx+r9*8]; int
0x18005cec6  mov     [rsp+98h+var_48], r9
0x18005cecb  cmp     r14d, r15d
0x18005cece  jnb     short loc_18005CF2D
0x18005ced0  cmp     dword ptr [rsi+0Ch], 0Dh
0x18005ced4  jnz     short loc_18005CF24
0x18005ced6  mov     ecx, [rsi+14h]
0x18005ced9  test    ecx, ecx
0x18005cedb  jz      short loc_18005CF24
0x18005cedd  mov     edx, [rsi+10h]; int
0x18005cee0  lea     eax, [rdx+rcx]
0x18005cee3  cmp     eax, r8d
0x18005cee6  jnb     short loc_18005CF24
0x18005cee8  mov     rax, [rsp+98h+Str]
0x18005cef0  lea     r8, [rsp+98h+var_50]; int
0x18005cef5  mov     [rsp+98h+var_68], rbx; __int64
0x18005cefa  add     rcx, rdi; int
0x18005cefd  mov     [rsp+98h+lpName], r12; __int64
0x18005cf02  mov     qword ptr [rsp+98h+dwCreationDisposition], rax; Str
0x18005cf07  call    PfSvResPriStaticDbReadPOGODebugDirectory
0x18005cf0c  mov     ebx, eax
0x18005cf0e  test    eax, eax
0x18005cf10  jnz     short loc_18005CF59
0x18005cf12  mov     rbx, [rsp+98h+arg_8]
0x18005cf1a  mov     r8d, [rsp+98h+var_58]
0x18005cf1f  mov     r9, [rsp+98h+var_48]
0x18005cf24  inc     r14d
0x18005cf27  add     rsi, 1Ch
0x18005cf2b  jmp     short loc_18005CECB
0x18005cf2d  xor     r14d, r14d
0x18005cf30  cmp     [r12+20h], r14d
0x18005cf35  jz      short loc_18005CF4F
0x18005cf37  lea     r9d, [r14+1]
0x18005cf3b  xor     r8d, r8d
0x18005cf3e  mov     rdx, rbx
0x18005cf41  mov     rcx, r12
0x18005cf44  call    PfSvResPriStaticDbInsertImageOffsetIntoBtDb
0x18005cf49  mov     ebx, eax
0x18005cf4b  test    eax, eax
0x18005cf4d  jnz     short loc_18005CF59
0x18005cf4f  mov     ebx, r14d
0x18005cf52  jmp     short loc_18005CF59
0x18005cf54  mov     ebx, 0Bh
0x18005cf59  mov     rcx, r13; hObject
0x18005cf5c  call    cs:__imp_CloseHandle
0x18005cf62  test    rbp, rbp
0x18005cf65  jz      short loc_18005CF70
0x18005cf67  mov     rcx, rbp; hObject
0x18005cf6a  call    cs:__imp_CloseHandle
0x18005cf70  test    rdi, rdi
0x18005cf73  jz      short loc_18005CF7E
0x18005cf75  mov     rcx, rdi; lpBaseAddress
0x18005cf78  call    cs:__imp_UnmapViewOfFile
0x18005cf7e  mov     eax, ebx
0x18005cf80  mov     rbx, [rsp+98h+arg_0]
0x18005cf88  add     rsp, 60h
0x18005cf8c  pop     r15
0x18005cf8e  pop     r14
0x18005cf90  pop     r13
0x18005cf92  pop     r12
0x18005cf94  pop     rdi
0x18005cf95  pop     rsi
0x18005cf96  pop     rbp
0x18005cf97  retn
```
