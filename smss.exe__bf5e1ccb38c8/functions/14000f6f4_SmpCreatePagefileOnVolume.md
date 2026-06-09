# SmpCreatePagefileOnVolume

- ea: `0x14000f6f4`
- end: `0x14000f9c2`
- name: `SmpCreatePagefileOnVolume`
- size: `718`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14000ea5c`

## callees

- `0x14000d4c0`
- `0x14000f280`
- `0x14000f6f4`
- `0x14000f9c8`
- `0x1400107e8`
- `0x140010bb8`
- `0x1400112c8`

## import_xrefs

- `ntdll!NtOpenFile` at `0x14000f780`
- `ntdll!NtOpenFile` at `0x14000f780`
- `ntdll!NtClose` at `0x14000f7c2`
- `ntdll!NtClose` at `0x14000f7c2`

## string_xrefs

- `0x14000f9a2`: `SmpCreatePagefileOnVolume`

## pseudocode

```c
__int64 __fastcall SmpCreatePagefileOnVolume(__int64 a1, __int64 a2, int a3)
{
  __int64 v3; // rsi
  bool v4; // r14
  bool v5; // zf
  int PagingFileSize; // eax
  unsigned __int64 v10; // rsi
  unsigned __int64 v11; // rdx
  unsigned __int64 v12; // r9
  unsigned __int64 v13; // r10
  unsigned __int64 v14; // r8
  unsigned __int64 v15; // rcx
  unsigned __int64 v16; // rdx
  __int64 v17; // rdx
  __int64 v18; // rax
  unsigned __int64 v19; // rcx
  unsigned __int64 v20; // rax
  unsigned __int64 v21; // rax
  __int64 result; // rax
  unsigned __int64 v23; // rdx
  __int64 v24; // rcx
  unsigned __int64 v25; // rdx
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+30h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  int v28; // [rsp+B0h] [rbp+40h] BYREF
  void *FileHandle; // [rsp+B8h] [rbp+48h] BYREF
  __int64 v30; // [rsp+C8h] [rbp+58h] BYREF

  v3 = 0;
  v4 = 0;
  *(&ObjectAttributes.Length + 1) = 0;
  v5 = (*(_BYTE *)(a1 + 92) & 4) == 0;
  *(&ObjectAttributes.Attributes + 1) = 0;
  FileHandle = 0;
  v28 = 0;
  IoStatusBlock = 0;
  v30 = 0;
  if ( !v5 )
    *(_WORD *)(*(_QWORD *)(a1 + 24) + 8LL) = *(_WORD *)(a2 + 28);
  ObjectAttributes.ObjectName = (PUNICODE_STRING)(a1 + 16);
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( NtOpenFile(&FileHandle, 0xC0100000, &ObjectAttributes, &IoStatusBlock, 3u, 0x28u) >= 0 )
  {
    PagingFileSize = SmpGetPagingFileSize(FileHandle, a1 + 16, &v30);
    v3 = v30;
    if ( PagingFileSize >= 0 )
      v4 = v30 != 0;
    SmpTrimPagingFileExtents(FileHandle, a1 + 16);
    NtClose(FileHandle);
  }
  v10 = *(_QWORD *)(a2 + 32) + v3;
  v11 = *(_QWORD *)(a2 + 40);
  if ( v10 <= v11 )
    v11 = v10;
  else
    v10 = *(_QWORD *)(a2 + 40);
  v5 = (*(_BYTE *)(a1 + 92) & 2) == 0;
  v12 = *(_QWORD *)(a1 + 56);
  v13 = *(_QWORD *)(a1 + 64);
  *(_QWORD *)(a1 + 72) = v12;
  *(_QWORD *)(a1 + 80) = v13;
  if ( v5 )
  {
    if ( v12 > v11 )
    {
      if ( !a3 )
        return 3221225599LL;
      *(_QWORD *)(a1 + 72) = v10;
    }
    v21 = *(_QWORD *)(a2 + 40);
    if ( v13 > v21 )
      *(_QWORD *)(a1 + 80) = v21;
  }
  else
  {
    v14 = *(_QWORD *)(a2 + 40) >> 3;
    v15 = v11 >> 2;
    if ( SmpMemorySize >= v11 >> 2 )
      v15 = SmpMemorySize;
    v16 = v11 >> 1;
    if ( v15 <= v16 )
      v16 = v15;
    if ( v16 > v14 )
      v16 = *(_QWORD *)(a2 + 40) >> 3;
    if ( v12 > v16 )
    {
      if ( !a3 )
      {
        v17 = 2184;
LABEL_63:
        SmpLogFailure("SmpCreatePagefileOnVolume", v17, 3221225599LL);
        return 3221225599LL;
      }
      if ( (*(_BYTE *)(a1 + 92) & 8) == 0 )
        goto LABEL_28;
      v18 = v10 >> 5;
      if ( v10 >> 5 > 0x40000000 )
        v18 = 0x40000000;
      v19 = v10 - v18;
      if ( v12 > v10 - v18 && v12 != *(_QWORD *)(a1 + 48) )
        goto LABEL_28;
      v16 = v10 - v18;
      if ( v14 < v19 )
        v14 = v10 - v18;
      if ( v12 > v19 )
      {
LABEL_28:
        v20 = *(_QWORD *)(a1 + 48);
        if ( v12 <= v20 || (*(_QWORD *)(a1 + 72) = v20, v20 > v16) )
          *(_QWORD *)(a1 + 72) = v16;
      }
    }
    if ( v13 > v14 )
      *(_QWORD *)(a1 + 80) = v14;
  }
  *(_DWORD *)(a1 + 88) = 0;
  if ( (*(_BYTE *)(a2 + 16) & 4) != 0 )
    *(_DWORD *)(a1 + 88) = 0x40000000;
  if ( (*(_BYTE *)(a2 + 16) & 8) != 0
    && (int)SmpCheckHybridPriority(*(unsigned int *)(a2 + 20), &v28, 0) >= 0
    && (v28 & 0xFFFFFFF0) == 0 )
  {
    *(_DWORD *)(a1 + 88) |= (v28 | 0x10) << 26;
  }
  if ( (*(_BYTE *)(a2 + 16) & 0x40) != 0 )
    *(_DWORD *)(a1 + 88) |= 0x1000000u;
  while ( 1 )
  {
    result = SmpCreatePagingFile(
               (UNICODE_STRING *)(a1 + 16),
               *(union _LARGE_INTEGER *)(a1 + 72),
               *(union _LARGE_INTEGER *)(a1 + 80),
               *(_DWORD *)(a1 + 88));
    if ( (int)result >= 0 )
      break;
    if ( !a3 )
      goto LABEL_58;
    v23 = *(_QWORD *)(a1 + 72);
    if ( v23 <= 0x1000000 )
      goto LABEL_58;
    v24 = 0x1000000;
    if ( v23 >> 4 > 0x1000000 )
      v24 = v23 >> 4;
    v25 = v23 - v24;
    *(_QWORD *)(a1 + 72) = v25;
    if ( v25 < 0x1000000 )
      *(_QWORD *)(a1 + 72) = 0x1000000;
  }
  *(_DWORD *)(a1 + 92) |= 1u;
  *(_DWORD *)(a2 + 16) |= 0x10u;
  if ( (*(_DWORD *)(a1 + 88) & 0x40000000) != 0 )
    *(_DWORD *)(a2 + 16) |= 0x20u;
  if ( (*(_BYTE *)(a1 + 92) & 2) != 0 )
    ++SmpNumberOfManagedPagefilesCreated;
  ++SmpNumberOfPagefilesCreated;
LABEL_58:
  if ( (*(_BYTE *)(a1 + 92) & 1) == 0 )
  {
    if ( v4 && (int)SmpDeletePagingFile((struct _UNICODE_STRING *)(a1 + 16)) >= 0 )
      *(_QWORD *)(a2 + 32) = v10;
    v17 = 2387;
    goto LABEL_63;
  }
  return result;
}

```

## disassembly

```asm
0x14000f6f4  push    rbp
0x14000f6f6  push    rbx
0x14000f6f7  push    rsi
0x14000f6f8  push    rdi
0x14000f6f9  push    r12
0x14000f6fb  push    r14
0x14000f6fd  push    r15
0x14000f6ff  mov     rbp, rsp
0x14000f702  sub     rsp, 70h
0x14000f706  xor     eax, eax
0x14000f708  xor     esi, esi
0x14000f70a  xor     r14b, r14b
0x14000f70d  mov     dword ptr [rbp+ObjectAttributes+4], eax
0x14000f710  test    byte ptr [rcx+5Ch], 4
0x14000f714  xorps   xmm0, xmm0
0x14000f717  mov     r12d, r8d
0x14000f71a  mov     dword ptr [rbp+ObjectAttributes+1Ch], eax
0x14000f71d  mov     rdi, rdx
0x14000f720  mov     [rbp+FileHandle], rax
0x14000f724  mov     rbx, rcx
0x14000f727  mov     [rbp+arg_0], eax
0x14000f72a  movups  xmmword ptr [rbp+IoStatusBlock], xmm0
0x14000f72e  mov     [rbp+arg_18], rsi
0x14000f732  jz      short loc_14000F740
0x14000f734  mov     rcx, [rcx+18h]
0x14000f738  movzx   eax, word ptr [rdx+1Ch]
0x14000f73c  mov     [rcx+8], ax
0x14000f740  lea     r15, [rbx+10h]
0x14000f744  mov     [rsp+70h+OpenOptions], 28h ; '('; OpenOptions
0x14000f74c  lea     r9, [rbp+IoStatusBlock]; IoStatusBlock
0x14000f750  mov     [rbp+ObjectAttributes.ObjectName], r15
0x14000f754  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14000f758  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x14000f75f  mov     edx, 0C0100000h; DesiredAccess
0x14000f764  mov     [rbp+ObjectAttributes.RootDirectory], rsi
0x14000f768  lea     rcx, [rbp+FileHandle]; FileHandle
0x14000f76c  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x14000f773  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14000f778  mov     [rsp+70h+ShareAccess], 3; ShareAccess
0x14000f780  call    cs:__imp_NtOpenFile
0x14000f786  test    eax, eax
0x14000f788  js      short loc_14000F7C8
0x14000f78a  mov     rcx, [rbp+FileHandle]
0x14000f78e  lea     r8, [rbp+arg_18]
0x14000f792  mov     rdx, r15
0x14000f795  call    SmpGetPagingFileSize
0x14000f79a  mov     rsi, [rbp+arg_18]
0x14000f79e  test    eax, eax
0x14000f7a0  js      short loc_14000F7B2
0x14000f7a2  test    rsi, rsi
0x14000f7a5  movzx   r14d, r14b
0x14000f7a9  mov     eax, 1
0x14000f7ae  cmovnz  r14d, eax
0x14000f7b2  mov     rcx, [rbp+FileHandle]
0x14000f7b6  mov     rdx, r15
0x14000f7b9  call    SmpTrimPagingFileExtents
0x14000f7be  mov     rcx, [rbp+FileHandle]; Handle
0x14000f7c2  call    cs:__imp_NtClose
0x14000f7c8  add     rsi, [rdi+20h]
0x14000f7cc  mov     rdx, [rdi+28h]
0x14000f7d0  cmp     rsi, rdx
0x14000f7d3  jbe     short loc_14000F7DA
0x14000f7d5  mov     rsi, rdx
0x14000f7d8  jmp     short loc_14000F7DD
0x14000f7da  mov     rdx, rsi
0x14000f7dd  test    byte ptr [rbx+5Ch], 2
0x14000f7e1  mov     r11d, 40000000h
0x14000f7e7  mov     r9, [rbx+38h]
0x14000f7eb  mov     r10, [rbx+40h]
0x14000f7ef  mov     [rbx+48h], r9
0x14000f7f3  mov     [rbx+50h], r10
0x14000f7f7  jz      loc_14000F895
0x14000f7fd  mov     r8, [rdi+28h]
0x14000f801  mov     rcx, rdx
0x14000f804  shr     r8, 3
0x14000f808  shr     rcx, 2
0x14000f80c  cmp     cs:SmpMemorySize, rcx
0x14000f813  cmovnb  rcx, cs:SmpMemorySize
0x14000f81b  shr     rdx, 1
0x14000f81e  cmp     rcx, rdx
0x14000f821  cmovbe  rdx, rcx
0x14000f825  cmp     rdx, r8
0x14000f828  cmova   rdx, r8
0x14000f82c  cmp     r9, rdx
0x14000f82f  jbe     short loc_14000F88A
0x14000f831  test    r12d, r12d
0x14000f834  jnz     short loc_14000F840
0x14000f836  mov     edx, 888h
0x14000f83b  jmp     loc_14000F99C
0x14000f840  test    byte ptr [rbx+5Ch], 8
0x14000f844  jz      short loc_14000F874
0x14000f846  mov     rax, rsi
0x14000f849  mov     rcx, rsi
0x14000f84c  shr     rax, 5
0x14000f850  cmp     rax, r11
0x14000f853  cmova   rax, r11
0x14000f857  sub     rcx, rax
0x14000f85a  cmp     r9, rcx
0x14000f85d  jbe     short loc_14000F865
0x14000f85f  cmp     r9, [rbx+30h]
0x14000f863  jnz     short loc_14000F874
0x14000f865  cmp     r8, rcx
0x14000f868  mov     rdx, rcx
0x14000f86b  cmovb   r8, rcx
0x14000f86f  cmp     r9, rcx
0x14000f872  jbe     short loc_14000F88A
0x14000f874  mov     rax, [rbx+30h]
0x14000f878  cmp     r9, rax
0x14000f87b  jbe     short loc_14000F886
0x14000f87d  mov     [rbx+48h], rax
0x14000f881  cmp     rax, rdx
0x14000f884  jbe     short loc_14000F88A
0x14000f886  mov     [rbx+48h], rdx
0x14000f88a  cmp     r10, r8
0x14000f88d  jbe     short loc_14000F8B4
0x14000f88f  mov     [rbx+50h], r8
0x14000f893  jmp     short loc_14000F8B4
0x14000f895  cmp     r9, rdx
0x14000f898  jbe     short loc_14000F8A7
0x14000f89a  test    r12d, r12d
0x14000f89d  jz      loc_14000F9AE
0x14000f8a3  mov     [rbx+48h], rsi
0x14000f8a7  mov     rax, [rdi+28h]
0x14000f8ab  cmp     r10, rax
0x14000f8ae  jbe     short loc_14000F8B4
0x14000f8b0  mov     [rbx+50h], rax
0x14000f8b4  mov     dword ptr [rbx+58h], 0
0x14000f8bb  test    byte ptr [rdi+10h], 4
0x14000f8bf  jz      short loc_14000F8C5
0x14000f8c1  mov     [rbx+58h], r11d
0x14000f8c5  test    byte ptr [rdi+10h], 8
0x14000f8c9  jz      short loc_14000F8F1
0x14000f8cb  mov     ecx, [rdi+14h]
0x14000f8ce  lea     rdx, [rbp+arg_0]
0x14000f8d2  xor     r8d, r8d
0x14000f8d5  call    SmpCheckHybridPriority
0x14000f8da  test    eax, eax
0x14000f8dc  js      short loc_14000F8F1
0x14000f8de  mov     eax, [rbp+arg_0]
0x14000f8e1  test    eax, 0FFFFFFF0h
0x14000f8e6  jnz     short loc_14000F8F1
0x14000f8e8  or      eax, 10h
0x14000f8eb  shl     eax, 1Ah
0x14000f8ee  or      [rbx+58h], eax
0x14000f8f1  test    byte ptr [rdi+10h], 40h
0x14000f8f5  jz      short loc_14000F8FC
0x14000f8f7  bts     dword ptr [rbx+58h], 18h
0x14000f8fc  mov     r9d, [rbx+58h]
0x14000f900  mov     rcx, r15; String2
0x14000f903  mov     r8, [rbx+50h]
0x14000f907  mov     rdx, [rbx+48h]
0x14000f90b  call    SmpCreatePagingFile
0x14000f910  test    eax, eax
0x14000f912  jns     short loc_14000F94B
0x14000f914  test    r12d, r12d
0x14000f917  jz      short loc_14000F978
0x14000f919  mov     rdx, [rbx+48h]
0x14000f91d  mov     r8d, 1000000h
0x14000f923  cmp     rdx, r8
0x14000f926  jbe     short loc_14000F978
0x14000f928  mov     rax, rdx
0x14000f92b  mov     ecx, r8d
0x14000f92e  shr     rax, 4
0x14000f932  cmp     rax, r8
0x14000f935  cmova   rcx, rax
0x14000f939  sub     rdx, rcx
0x14000f93c  mov     [rbx+48h], rdx
0x14000f940  cmp     rdx, r8
0x14000f943  jnb     short loc_14000F8FC
0x14000f945  mov     [rbx+48h], r8
0x14000f949  jmp     short loc_14000F8FC
0x14000f94b  mov     edx, 1
0x14000f950  or      [rbx+5Ch], edx
0x14000f953  or      dword ptr [rdi+10h], 10h
0x14000f957  test    dword ptr [rbx+58h], 40000000h
0x14000f95e  jz      short loc_14000F964
0x14000f960  or      dword ptr [rdi+10h], 20h
0x14000f964  test    byte ptr [rbx+5Ch], 2
0x14000f968  jz      short loc_14000F970
0x14000f96a  add     cs:SmpNumberOfManagedPagefilesCreated, edx
0x14000f970  add     cs:SmpNumberOfPagefilesCreated, edx
0x14000f976  jmp     short loc_14000F97D
0x14000f978  mov     edx, 1
0x14000f97d  test    [rbx+5Ch], dl
0x14000f980  jnz     short loc_14000F9B3
0x14000f982  test    r14b, r14b
0x14000f985  jz      short loc_14000F997
0x14000f987  mov     rcx, r15
0x14000f98a  call    SmpDeletePagingFile
0x14000f98f  test    eax, eax
0x14000f991  js      short loc_14000F997
0x14000f993  mov     [rdi+20h], rsi
0x14000f997  mov     edx, 953h
0x14000f99c  mov     r8d, 0C000007Fh
0x14000f9a2  lea     rcx, aSmpcreatepagef; "SmpCreatePagefileOnVolume"
0x14000f9a9  call    SmpLogFailure
0x14000f9ae  mov     eax, 0C000007Fh
0x14000f9b3  add     rsp, 70h
0x14000f9b7  pop     r15
0x14000f9b9  pop     r14
0x14000f9bb  pop     r12
0x14000f9bd  pop     rdi
0x14000f9be  pop     rsi
0x14000f9bf  pop     rbx
0x14000f9c0  pop     rbp
0x14000f9c1  retn
```
