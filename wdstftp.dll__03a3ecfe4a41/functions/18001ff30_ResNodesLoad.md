# ResNodesLoad

- ea: `0x18001ff30`
- end: `0x1800204b7`
- name: `ResNodesLoad`
- size: `1415`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, loader_planting`

## callers

- `0x180013690`

## callees

- `0x18001223c`
- `0x1800171e0`
- `0x18001e57c`
- `0x18001f9cc`
- `0x18001ff30`
- `0x180020594`
- `0x1800219c4`
- `0x180060e5a`

## import_xrefs

- `KERNEL32!UnmapViewOfFile` at `0x180020411`
- `KERNEL32!UnmapViewOfFile` at `0x180061bdd`
- `KERNEL32!UnmapViewOfFile` at `0x180020411`
- `KERNEL32!UnmapViewOfFile` at `0x180061bdd`
- `KERNEL32!MapViewOfFile` at `0x180020074`
- `KERNEL32!MapViewOfFile` at `0x180020074`
- `KERNEL32!CreateFileMappingW` at `0x18001ffdd`
- `KERNEL32!CreateFileMappingW` at `0x18001ffdd`
- `KERNEL32!GetSystemInfo` at `0x18002001d`
- `KERNEL32!GetSystemInfo` at `0x18002001d`
- `KERNEL32!GetLastError` at `0x180020337`
- `KERNEL32!GetLastError` at `0x180020356`
- `KERNEL32!GetLastError` at `0x1800203d6`
- `KERNEL32!GetLastError` at `0x18002048d`
- `KERNEL32!GetLastError` at `0x180020337`
- `KERNEL32!GetLastError` at `0x180020356`
- `KERNEL32!GetLastError` at `0x1800203d6`
- `KERNEL32!GetLastError` at `0x18002048d`
- `KERNEL32!CloseHandle` at `0x18002042a`
- `KERNEL32!CloseHandle` at `0x180061bf3`
- `KERNEL32!CloseHandle` at `0x18002042a`
- `KERNEL32!CloseHandle` at `0x180061bf3`
- `KERNEL32!SetLastError` at `0x1800204a4`
- `KERNEL32!SetLastError` at `0x1800204a4`
- `KERNEL32!GetFileSizeEx` at `0x18001ff95`
- `KERNEL32!GetFileSizeEx` at `0x18001ff95`
- `ntdll!RtlNtStatusToDosError` at `0x180020262`
- `ntdll!RtlNtStatusToDosError` at `0x180020286`
- `ntdll!RtlNtStatusToDosError` at `0x180020262`
- `ntdll!RtlNtStatusToDosError` at `0x180020286`

## pseudocode

```c
__int64 __fastcall ResNodesLoad(__int64 a1, void *a2, __int64 a3, __int64 a4)
{
  unsigned int v6; // ebx
  DWORD v7; // r13d
  __int64 v8; // r14
  unsigned int v9; // r15d
  __int64 v11; // rdx
  __int64 v12; // rbx
  char *v13; // rax
  int v14; // ecx
  __int64 v15; // r8
  __int64 v16; // r9
  char v17; // r9
  __int64 inserted; // rax
  char v19; // r9
  __int64 v20; // rcx
  __int64 v21; // rax
  __int64 v22; // r10
  int v23; // eax
  unsigned int v24; // ecx
  int v25; // eax
  bool v26; // cf
  signed int LastError; // ecx
  signed int v28; // eax
  signed int v29; // eax
  __int64 v30; // rdx
  int v31; // edi
  unsigned __int16 v32; // cx
  LPCVOID lpBaseAddress; // [rsp+38h] [rbp-B0h]
  unsigned int v34; // [rsp+40h] [rbp-A8h]
  __int64 v35; // [rsp+48h] [rbp-A0h]
  union _LARGE_INTEGER FileSize; // [rsp+58h] [rbp-90h] BYREF
  HANDLE hFileMappingObject; // [rsp+60h] [rbp-88h]
  __int64 v38; // [rsp+68h] [rbp-80h]
  __int64 v39; // [rsp+70h] [rbp-78h]
  __int64 v40; // [rsp+78h] [rbp-70h]
  struct _SYSTEM_INFO SystemInfo; // [rsp+80h] [rbp-68h] BYREF
  unsigned int Status; // [rsp+108h] [rbp+20h]
  unsigned int Statusa; // [rsp+108h] [rbp+20h]

  v6 = 0;
  v39 = 0;
  if ( a1 )
    v39 = *(_QWORD *)(a1 + 464);
  lpBaseAddress = 0;
  v7 = 0;
  v34 = 0;
  v8 = 0;
  FileSize.QuadPart = 0;
  v9 = a4;
  GetFileSizeEx(a2, &FileSize);
  if ( !a4 )
    return 1;
  hFileMappingObject = CreateFileMappingW(a2, 0, 2u, FileSize.HighPart, FileSize.LowPart, 0);
  if ( hFileMappingObject )
  {
    v12 = a3;
    memset_0(&SystemInfo, 0, sizeof(SystemInfo));
    Status = 0;
    GetSystemInfo(&SystemInfo);
    if ( a3 % SystemInfo.dwAllocationGranularity )
    {
      Status = (unsigned int)a3 % SystemInfo.dwAllocationGranularity;
      v12 = a3 - (unsigned int)a3 % SystemInfo.dwAllocationGranularity;
      v9 = (unsigned int)a3 % SystemInfo.dwAllocationGranularity + a4;
    }
    v13 = (char *)MapViewOfFile(hFileMappingObject, 4u, HIDWORD(v12), v12, v9);
    v14 = (int)v13;
    lpBaseAddress = v13;
    if ( v13 )
    {
      v15 = 1;
      v6 = 1;
      v16 = (__int64)&v13[Status];
      goto LABEL_13;
    }
    v6 = 0;
  }
  else
  {
    v14 = 0;
  }
  v15 = 1;
  v16 = 0;
LABEL_13:
  if ( v6 )
  {
    while ( 1 )
    {
      while ( 1 )
      {
        do
        {
          if ( v8 >= a4 )
            goto LABEL_68;
          v11 = v16;
          v8 += 50;
          v38 = v8;
          v16 += 50;
          v35 = v16;
          v40 = v16;
          if ( (int)v16 - v14 > v9 )
          {
            v6 = 0;
            v7 = 13;
            goto LABEL_68;
          }
        }
        while ( !g_useFileIOCallbacks
             && (*(_BYTE *)(v11 + 7) & 0x10) == 0
             && (*(_QWORD *)(v11 + 8) > a3 || *(_QWORD *)(v11 + 8) + (*(_QWORD *)v11 & 0xFFFFFFFFFFFFFFLL) > a3) );
        v17 = *(_BYTE *)(v11 + 7);
        if ( (v17 & 0xC0) == 0 )
          break;
LABEL_23:
        v16 = v35;
      }
      if ( (v17 & 1) != 0 )
        break;
      v19 = v17 & 0x10;
      v20 = *(_QWORD *)(v11 + 30) - g_bNullHash;
      if ( !v20 )
      {
        v20 = *(_QWORD *)(v11 + 38) - qword_180077908;
        if ( !v20 )
          v20 = *(unsigned int *)(v11 + 46) - (unsigned __int64)(unsigned int)dword_180077910;
      }
      if ( !v20 && !v19 )
      {
        v14 = (int)lpBaseAddress;
        goto LABEL_23;
      }
      v21 = ResDiskNodeAddToEnd(a1);
      v22 = v21;
      v38 = v21;
      if ( !v21 )
        goto LABEL_66;
      if ( (*(_BYTE *)(v21 + 15) & 0x10) == 0 || (v16 = *(unsigned int *)(v21 + 28), (v16 & 1) == 0) )
      {
        if ( (*(_BYTE *)(v21 + 15) & 2) != 0 )
        {
          v24 = v34 + *(_DWORD *)(v21 + 36);
          v25 = -1;
          v26 = v24 < v34;
          if ( v24 >= v34 )
            v25 = v34 + *(_DWORD *)(v22 + 36);
          v34 = v25;
          v11 = v26 ? 0x80070216 : 0;
          Statusa = v26 ? 0x80070216 : 0;
          if ( v26 )
          {
            UtilReportError((__int64)L"ResNodesLoad", v11, 0x32Au, v11);
            v11 = Statusa;
            v22 = v38;
          }
          if ( (int)v11 < 0 )
          {
LABEL_39:
            if ( (v11 & 0x10000000) != 0 )
            {
              if ( RtlNtStatusToDosError(v11) == 317 )
                v7 = Statusa;
              else
                v7 = RtlNtStatusToDosError(Statusa);
            }
            else
            {
              v7 = v11;
              if ( (v11 & 0x1FFF0000) == 0x70000 )
                v7 = (unsigned __int16)v11;
            }
            v6 = 0;
            goto LABEL_68;
          }
          if ( ResMetaListTailAdd(a1, v22) )
          {
LABEL_62:
            v11 = Statusa;
            if ( (Statusa & 0x80000000) != 0 )
              goto LABEL_39;
          }
          else
          {
            LastError = GetLastError();
            v28 = (unsigned __int16)LastError | 0x80070000;
            if ( LastError <= 0 )
              v28 = LastError;
            if ( v28 >= 0 )
            {
              v30 = 2147500037LL;
            }
            else
            {
              v29 = GetLastError();
              v30 = (unsigned __int16)v29 | 0x80070000;
              if ( v29 <= 0 )
                v30 = (unsigned int)v29;
            }
            Statusa = v30;
            if ( (int)v30 < 0 )
            {
              UtilReportError((__int64)L"ResNodesLoad", v30, 0x331u, v30);
              goto LABEL_62;
            }
          }
          v22 = v38;
        }
        inserted = InsertDataIntoHashTableEx(v39, v22 + 40, 20, v22);
LABEL_65:
        if ( !inserted )
        {
LABEL_66:
          v6 = 0;
          goto LABEL_67;
        }
        goto LABEL_26;
      }
      v23 = ParseChunkRegionInternal(a1, *(_QWORD *)(v21 + 16), *(_QWORD *)(v21 + 8) & 0xFFFFFFFFFFFFFFLL);
      v11 = (unsigned int)v23;
      Statusa = v23;
      if ( v23 < 0 )
      {
        UtilReportError((__int64)L"ResNodesLoad", (unsigned int)v23, 0x316u, v23);
        v11 = Statusa;
      }
      if ( (int)v11 < 0 )
        goto LABEL_39;
LABEL_26:
      v15 = 1;
      v14 = (int)lpBaseAddress;
      v16 = v35;
    }
    inserted = ResDiskNodeAddToEnd(a1);
    goto LABEL_65;
  }
LABEL_67:
  v7 = GetLastError();
LABEL_68:
  v31 = 1;
  if ( lpBaseAddress )
    UnmapViewOfFile(lpBaseAddress);
  if ( hFileMappingObject )
    CloseHandle(hFileMappingObject);
  if ( v6 )
  {
    v32 = 0;
    if ( a1 && *(_DWORD *)a1 == -17960959 )
      v32 = *(_WORD *)(a1 + 88);
    if ( v32 <= 1u )
    {
      if ( a1 && *(_DWORD *)a1 == -17960959 )
        v31 = *(_DWORD *)(a1 + 92);
      if ( v34 != v31 )
      {
        v7 = 13;
        v6 = 0;
      }
    }
    if ( v6 )
    {
      v6 = ResMetaAddSingleInstancedImages(a1, v11, v15, v16);
      if ( !v6 )
        v7 = GetLastError();
    }
  }
  if ( v7 )
    SetLastError(v7);
  return v6;
}

```

## disassembly

```asm
0x18001ff30  mov     [rsp+hFile], rdx
0x18001ff35  mov     [rsp+arg_0], rcx
0x18001ff3a  push    rbx
0x18001ff3b  push    rsi
0x18001ff3c  push    rdi
0x18001ff3d  push    r12
0x18001ff3f  push    r13
0x18001ff41  push    r14
0x18001ff43  push    r15
0x18001ff45  sub     rsp, 0B0h
0x18001ff4c  mov     rsi, r9
0x18001ff4f  mov     rdi, r8
0x18001ff52  mov     r8, rdx
0x18001ff55  xor     r12d, r12d
0x18001ff58  mov     ebx, r12d
0x18001ff5b  mov     dword ptr [rsp+0E8h+var_A0], ebx
0x18001ff5f  mov     [rsp+0E8h+var_78], r12
0x18001ff64  test    rcx, rcx
0x18001ff67  jz      short loc_18001FF75
0x18001ff69  mov     rax, [rcx+1D0h]
0x18001ff70  mov     [rsp+0E8h+var_78], rax
0x18001ff75  mov     [rsp+0E8h+lpBaseAddress], r12
0x18001ff7a  mov     r13d, r12d
0x18001ff7d  mov     [rsp+0E8h+var_A8], r12d
0x18001ff82  mov     r14, r12
0x18001ff85  mov     qword ptr [rsp+0E8h+FileSize], r12
0x18001ff8a  mov     r15, rsi
0x18001ff8d  lea     rdx, [rsp+0E8h+FileSize]; lpFileSize
0x18001ff92  mov     rcx, r8; hFile
0x18001ff95  call    cs:__imp_GetFileSizeEx
0x18001ff9c  nop     dword ptr [rax+rax+00h]
0x18001ffa1  test    rsi, rsi
0x18001ffa4  jnz     short loc_18001FFBC
0x18001ffa6  lea     eax, [rsi+1]
0x18001ffa9  add     rsp, 0B0h
0x18001ffb0  pop     r15
0x18001ffb2  pop     r14
0x18001ffb4  pop     r13
0x18001ffb6  pop     r12
0x18001ffb8  pop     rdi
0x18001ffb9  pop     rsi
0x18001ffba  pop     rbx
0x18001ffbb  retn
0x18001ffbc  mov     [rsp+0E8h+lpName], r12; lpName
0x18001ffc1  mov     rax, qword ptr [rsp+0E8h+FileSize]
0x18001ffc6  mov     [rsp+0E8h+dwMaximumSizeLow], eax; dwMaximumSizeLow
0x18001ffca  mov     r9d, dword ptr [rsp+0E8h+FileSize+4]; dwMaximumSizeHigh
0x18001ffcf  xor     edx, edx; lpFileMappingAttributes
0x18001ffd1  lea     r8d, [rdx+2]; flProtect
0x18001ffd5  mov     rcx, [rsp+0E8h+hFile]; hFile
0x18001ffdd  call    cs:__imp_CreateFileMappingW
0x18001ffe4  nop     dword ptr [rax+rax+00h]
0x18001ffe9  mov     [rsp+0E8h+hFileMappingObject], rax
0x18001ffee  test    rax, rax
0x18001fff1  jz      loc_1800200A9
0x18001fff7  mov     rbx, rdi
0x18001fffa  xor     edx, edx; Val
0x18001fffc  lea     r8d, [rdx+30h]; Size
0x180020000  lea     rcx, [rsp+0E8h+SystemInfo]; void *
0x180020008  call    memset_0
0x18002000d  mov     [rsp+0E8h+Status], r12d
0x180020015  lea     rcx, [rsp+0E8h+SystemInfo]; lpSystemInfo
0x18002001d  call    cs:__imp_GetSystemInfo
0x180020024  nop     dword ptr [rax+rax+00h]
0x180020029  mov     ecx, [rsp+0E8h+SystemInfo.dwAllocationGranularity]
0x180020030  mov     rax, rdi
0x180020033  cqo
0x180020035  idiv    rcx
0x180020038  test    rdx, rdx
0x18002003b  jz      short loc_180020058
0x18002003d  xor     edx, edx
0x18002003f  mov     eax, edi
0x180020041  div     [rsp+0E8h+SystemInfo.dwAllocationGranularity]
0x180020048  mov     eax, edx
0x18002004a  mov     [rsp+0E8h+Status], eax
0x180020051  sub     rbx, rax
0x180020054  lea     r15, [rdx+rsi]
0x180020058  mov     eax, r15d
0x18002005b  mov     r8, rbx
0x18002005e  shr     r8, 20h; dwFileOffsetHigh
0x180020062  mov     qword ptr [rsp+0E8h+dwMaximumSizeLow], rax; dwNumberOfBytesToMap
0x180020067  mov     r9d, ebx; dwFileOffsetLow
0x18002006a  mov     edx, 4; dwDesiredAccess
0x18002006f  mov     rcx, [rsp+0E8h+hFileMappingObject]; hFileMappingObject
0x180020074  call    cs:__imp_MapViewOfFile
0x18002007b  nop     dword ptr [rax+rax+00h]
0x180020080  mov     rcx, rax
0x180020083  mov     [rsp+0E8h+lpBaseAddress], rax
0x180020088  test    rax, rax
0x18002008b  jz      short loc_1800200A3
0x18002008d  mov     r8d, 1
0x180020093  mov     ebx, r8d
0x180020096  mov     r9d, [rsp+0E8h+Status]
0x18002009e  add     r9, rax
0x1800200a1  jmp     short loc_1800200B7
0x1800200a3  mov     ebx, dword ptr [rsp+0E8h+var_A0]
0x1800200a7  jmp     short loc_1800200AE
0x1800200a9  mov     rcx, [rsp+0E8h+lpBaseAddress]
0x1800200ae  mov     r8d, 1
0x1800200b4  mov     r9, r12
0x1800200b7  test    ebx, ebx
0x1800200b9  jz      loc_1800203D6
0x1800200bf  mov     r10, 0FFFFFFFFFFFFFFh
0x1800200c9  cmp     r14, rsi
0x1800200cc  jge     loc_1800203E9
0x1800200d2  mov     rdx, r9
0x1800200d5  add     r14, 32h ; '2'
0x1800200d9  mov     [rsp+0E8h+var_80], r14
0x1800200de  add     r9, 32h ; '2'
0x1800200e2  mov     [rsp+0E8h+var_A0], r9
0x1800200e7  mov     [rsp+0E8h+var_70], r9
0x1800200ec  mov     eax, r9d
0x1800200ef  sub     eax, ecx
0x1800200f1  cmp     eax, r15d
0x1800200f4  jbe     short loc_18002010D
0x1800200f6  mov     ebx, r12d
0x1800200f9  mov     [rsp+0E8h+var_B4], ebx
0x1800200fd  mov     r13d, 0Dh
0x180020103  mov     [rsp+0E8h+var_B8], r13d
0x180020108  jmp     loc_1800203E9
0x18002010d  cmp     cs:g_useFileIOCallbacks, r12d
0x180020114  jnz     short loc_180020133
0x180020116  test    byte ptr [rdx+7], 10h
0x18002011a  jnz     short loc_180020133
0x18002011c  cmp     [rdx+8], rdi
0x180020120  jg      short loc_180020131
0x180020122  mov     rax, [rdx]
0x180020125  and     rax, r10
0x180020128  add     rax, [rdx+8]
0x18002012c  cmp     rax, rdi
0x18002012f  jle     short loc_180020133
0x180020131  jmp     short loc_1800200C9
0x180020133  mov     r9b, [rdx+7]
0x180020137  test    r9b, 0C0h
0x18002013b  jz      short loc_180020144
0x18002013d  mov     r9, [rsp+0E8h+var_A0]
0x180020142  jmp     short loc_1800200C9
0x180020144  test    r8b, r9b
0x180020147  jz      short loc_180020170
0x180020149  mov     rcx, [rsp+0E8h+arg_0]
0x180020151  call    ResDiskNodeAddToEnd
0x180020156  jmp     loc_1800203C6
0x18002015b  mov     r8d, 1
0x180020161  mov     rcx, [rsp+0E8h+lpBaseAddress]
0x180020166  mov     r9, [rsp+0E8h+var_A0]
0x18002016b  jmp     loc_1800200BF
0x180020170  and     r9b, 10h
0x180020174  jz      short loc_18002017E
0x180020176  mov     rax, [rdx]
0x180020179  and     rax, r10
0x18002017c  jmp     short loc_180020182
0x18002017e  mov     rax, [rdx+10h]
0x180020182  mov     qword ptr [rsp+0E8h+Status], rax
0x18002018a  mov     rcx, [rdx+1Eh]
0x18002018e  sub     rcx, cs:g_bNullHash
0x180020195  jnz     short loc_1800201B0
0x180020197  mov     rcx, [rdx+26h]
0x18002019b  sub     rcx, cs:qword_180077908
0x1800201a2  jnz     short loc_1800201B0
0x1800201a4  mov     ecx, [rdx+2Eh]
0x1800201a7  mov     eax, cs:dword_180077910
0x1800201ad  sub     rcx, rax
0x1800201b0  mov     eax, r12d
0x1800201b3  test    rcx, rcx
0x1800201b6  cmovz   eax, r8d
0x1800201ba  test    eax, eax
0x1800201bc  jz      short loc_1800201CD
0x1800201be  test    r9b, r9b
0x1800201c1  jnz     short loc_1800201CD
0x1800201c3  mov     rcx, [rsp+0E8h+lpBaseAddress]
0x1800201c8  jmp     loc_18002013D
0x1800201cd  mov     rcx, [rsp+0E8h+arg_0]
0x1800201d5  call    ResDiskNodeAddToEnd
0x1800201da  mov     r10, rax
0x1800201dd  mov     [rsp+0E8h+var_80], rax
0x1800201e2  test    rax, rax
0x1800201e5  jz      loc_1800203CF
0x1800201eb  test    byte ptr [rax+0Fh], 10h
0x1800201ef  jz      loc_1800202BE
0x1800201f5  mov     r9d, [rax+1Ch]
0x1800201f9  mov     eax, 1
0x1800201fe  test    al, r9b
0x180020201  jz      loc_1800202BE
0x180020207  mov     r8, [r10+8]
0x18002020b  mov     rax, 0FFFFFFFFFFFFFFh
0x180020215  and     r8, rax
0x180020218  mov     rdx, [r10+10h]
0x18002021c  mov     rcx, [rsp+0E8h+arg_0]
0x180020224  call    ParseChunkRegionInternal
0x180020229  mov     edx, eax
0x18002022b  mov     [rsp+0E8h+Status], eax
0x180020232  test    eax, eax
0x180020234  jns     short loc_180020252
0x180020236  mov     r9d, eax
0x180020239  mov     r8d, 316h
0x18002023f  lea     rcx, aResnodesload; "ResNodesLoad"
0x180020246  call    UtilReportError
0x18002024b  mov     edx, [rsp+0E8h+Status]
0x180020252  test    edx, edx
0x180020254  jns     loc_18002015B
0x18002025a  mov     ecx, edx; Status
0x18002025c  bt      edx, 1Ch
0x180020260  jnb     short loc_180020297
0x180020262  call    cs:__imp_RtlNtStatusToDosError
0x180020269  nop     dword ptr [rax+rax+00h]
0x18002026e  cmp     eax, 13Dh
0x180020273  jnz     short loc_18002027F
0x180020275  mov     r13d, [rsp+0E8h+Status]
0x18002027d  jmp     short loc_1800202AD
0x18002027f  mov     ecx, [rsp+0E8h+Status]; Status
0x180020286  call    cs:__imp_RtlNtStatusToDosError
0x18002028d  nop     dword ptr [rax+rax+00h]
0x180020292  mov     r13d, eax
0x180020295  jmp     short loc_1800202AD
0x180020297  and     ecx, 1FFF0000h
0x18002029d  movzx   eax, dx
0x1800202a0  mov     r13d, edx
0x1800202a3  cmp     ecx, 70000h
0x1800202a9  cmovz   r13d, eax
0x1800202ad  mov     [rsp+0E8h+var_B8], r13d
0x1800202b2  mov     ebx, r12d
0x1800202b5  mov     [rsp+0E8h+var_B4], ebx
0x1800202b9  jmp     loc_1800203E9
0x1800202be  test    byte ptr [r10+0Fh], 2
0x1800202c3  jz      loc_1800203AF
0x1800202c9  mov     [rsp+0E8h+var_98], r12d
0x1800202ce  mov     ecx, [r10+24h]
0x1800202d2  add     ecx, [rsp+0E8h+var_A8]
0x1800202d6  or      eax, 0FFFFFFFFh
0x1800202d9  cmp     ecx, [rsp+0E8h+var_A8]
0x1800202dd  cmovnb  eax, ecx
0x1800202e0  mov     [rsp+0E8h+var_A8], eax
0x1800202e4  sbb     edx, edx
0x1800202e6  and     edx, 80070216h
0x1800202ec  mov     [rsp+0E8h+Status], edx
0x1800202f3  mov     [rsp+0E8h+var_98], edx
0x1800202f7  jge     short loc_18002031A
0x1800202f9  mov     r9d, edx
0x1800202fc  mov     r8d, 32Ah
0x180020302  lea     rcx, aResnodesload; "ResNodesLoad"
0x180020309  call    UtilReportError
0x18002030e  mov     edx, [rsp+0E8h+Status]
0x180020315  mov     r10, [rsp+0E8h+var_80]
0x18002031a  test    edx, edx
0x18002031c  js      loc_18002025A
0x180020322  mov     rdx, r10
0x180020325  mov     rcx, [rsp+0E8h+arg_0]
0x18002032d  call    ResMetaListTailAdd
0x180020332  test    rax, rax
0x180020335  jnz     short loc_18002039B
0x180020337  call    cs:__imp_GetLastError
0x18002033e  nop     dword ptr [rax+rax+00h]
0x180020343  mov     ecx, eax
0x180020345  movzx   eax, ax
0x180020348  or      eax, 80070000h
0x18002034d  test    ecx, ecx
0x18002034f  cmovle  eax, ecx
0x180020352  test    eax, eax
0x180020354  jns     short loc_180020372
0x180020356  call    cs:__imp_GetLastError
0x18002035d  nop     dword ptr [rax+rax+00h]
0x180020362  movzx   edx, ax
0x180020365  or      edx, 80070000h
0x18002036b  test    eax, eax
0x18002036d  cmovle  edx, eax
0x180020370  jmp     short loc_180020377
0x180020372  mov     edx, 80004005h
0x180020377  mov     [rsp+0E8h+Status], edx
0x18002037e  mov     [rsp+0E8h+var_98], edx
0x180020382  test    edx, edx
0x180020384  jns     short loc_1800203AA
0x180020386  mov     r9d, edx
0x180020389  mov     r8d, 331h
0x18002038f  lea     rcx, aResnodesload; "ResNodesLoad"
0x180020396  call    UtilReportError
0x18002039b  mov     edx, [rsp+0E8h+Status]
0x1800203a2  test    edx, edx
0x1800203a4  js      loc_18002025A
0x1800203aa  mov     r10, [rsp+0E8h+var_80]
0x1800203af  lea     rdx, [r10+28h]
0x1800203b3  mov     r9, r10
0x1800203b6  mov     r8d, 14h
0x1800203bc  mov     rcx, [rsp+0E8h+var_78]
0x1800203c1  call    InsertDataIntoHashTableEx
0x1800203c6  test    rax, rax
0x1800203c9  jnz     loc_18002015B
0x1800203cf  mov     ebx, r12d
0x1800203d2  mov     [rsp+0E8h+var_B4], ebx
0x1800203d6  call    cs:__imp_GetLastError
0x1800203dd  nop     dword ptr [rax+rax+00h]
0x1800203e2  mov     [rsp+0E8h+var_B8], eax
0x1800203e6  mov     r13d, eax
0x1800203e9  mov     edi, 1
0x1800203ee  jmp     short loc_180020407
0x1800203f0  mov     r13d, 0Dh
0x1800203f6  mov     [rsp+0E8h+var_B8], r13d
0x1800203fb  xor     ebx, ebx
0x1800203fd  mov     [rsp+0E8h+var_B4], ebx
0x180020401  xor     r12d, r12d
0x180020404  lea     edi, [rbx+1]
  ... truncated ...
```
