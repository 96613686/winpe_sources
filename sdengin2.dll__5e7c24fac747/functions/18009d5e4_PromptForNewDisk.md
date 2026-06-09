# PromptForNewDisk

- ea: `0x18009d5e4`
- end: `0x18009d986`
- name: `PromptForNewDisk`
- size: `930`
- prototype: `__int64 __fastcall(__int64, HANDLE *, __int64, __int64)`
- caller_count: `4`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x18009fff0`
- `0x1800a03c8`
- `0x1800a08d0`
- `0x1800a0a78`

## callees

- `0x18009d12c`
- `0x18009d4c0`
- `0x18009d5e4`
- `0x18009da0c`
- `0x18009dadc`
- `0x18009de58`
- `0x18009f200`
- `0x1800a3608`
- `0x1800a3660`
- `0x1800ac1bc`

## import_xrefs

- `msvcrt!_getdrive` at `0x18009d845`
- `msvcrt!_getdrive` at `0x18009d845`
- `KERNEL32!CloseHandle` at `0x18009d68a`
- `KERNEL32!CloseHandle` at `0x18009d7cc`
- `KERNEL32!CloseHandle` at `0x18009d68a`
- `KERNEL32!CloseHandle` at `0x18009d7cc`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x18009d712`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x18009d900`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x18009d712`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x18009d900`

## pseudocode

```c
__int64 __fastcall PromptForNewDisk(__int64 a1, HANDLE *a2, __int64 a3, __int64 a4)
{
  __int64 v5; // r15
  unsigned int v8; // ebx
  int v9; // r12d
  int v10; // esi
  __int64 v11; // r15
  __int64 v12; // rbx
  HANDLE v13; // rax
  __int64 v14; // rax
  int v15; // ebx
  unsigned int v16; // eax
  const CHAR *v17; // rcx
  unsigned __int16 v18; // bx
  unsigned int v19; // eax
  int v20; // eax
  HANDLE FileA; // rax
  DWORD dwCreationDisposition; // [rsp+20h] [rbp-88h]
  _OWORD v24[6]; // [rsp+40h] [rbp-68h] BYREF

  v5 = a3;
  v8 = 0;
  memset(v24, 0, 48);
  if ( *(__int16 *)(a4 + 3740) >= 0 || !a2 )
    return v8;
  v9 = 1;
  v10 = 0;
  if ( !*(_DWORD *)(a4 + 3792) )
  {
    while ( 1 )
    {
LABEL_23:
      if ( v5 != -1 )
        goto LABEL_24;
      while ( 1 )
      {
        if ( *a2 != (HANDLE)-1LL )
        {
          CloseHandle(*a2);
          *a2 = (HANDLE)-1LL;
        }
        if ( *(_DWORD *)(a4 + 3744) != 0xFFFF && (unsigned int)stat32(*(_QWORD *)(a4 + 3592), v24) )
        {
LABEL_48:
          *(_DWORD *)(a4 + 208) = 1;
          return 9;
        }
        v15 = 4;
        v10 = 1;
        while ( v15 != 1 )
        {
          v15 = dzMsgCB(*(_QWORD *)(a4 + 3168), 0, 1, *(_DWORD *)(a4 + 3744) + 2, dwCreationDisposition, a4);
          if ( v15 == 1 )
          {
            if ( !(unsigned int)dzDriveFromPath(*(LPCSTR *)(a4 + 3592)) )
              _getdrive();
            v16 = dzDriveFromPath(*(LPCSTR *)(a4 + 3592));
            if ( !(unsigned int)IsMediaWritable(v16, a4) )
            {
              v15 = dzMsgCB(*(_QWORD *)(a4 + 3168), 12, 5, 0, dwCreationDisposition, a4);
              if ( v15 != 4 )
                goto LABEL_48;
              goto LABEL_36;
            }
          }
          else
          {
LABEL_36:
            if ( v15 == 2 )
              goto LABEL_48;
          }
        }
        v17 = *(const CHAR **)(a4 + 3592);
        ++*(_DWORD *)(a4 + 3744);
        v18 = *(_WORD *)(a4 + 3740);
        v19 = dzDriveFromPath(v17);
        v20 = CleanTargetMedia(v19, v18, a4);
        --*(_DWORD *)(a4 + 3744);
        if ( !v20 )
          break;
        if ( (unsigned int)MakeZipFileDir(*(STRSAFE_LPCSTR *)(a4 + 3592)) )
          break;
        FileA = CreateFileA(*(LPCSTR *)(a4 + 3592), 0xC0000000, 0, 0, 2u, 0x80u, 0);
        *a2 = FileA;
        if ( FileA == (HANDLE)-1LL )
          break;
        if ( v5 == -1 )
        {
          v5 = 512;
          goto LABEL_23;
        }
LABEL_24:
        if ( RemainingDiskSpace(*(STRSAFE_LPCSTR *)(a4 + 3592)) >= v5 )
        {
LABEL_21:
          v8 = 0;
LABEL_16:
          if ( v10 && !v8 )
          {
            ++*(_DWORD *)(a4 + 3744);
            *(_QWORD *)(a4 + 3664) = 0;
            *(_QWORD *)(a4 + 3776) = 0;
            if ( *(_DWORD *)(a4 + 3792) )
              v14 = 0x200000;
            else
              v14 = RemainingDiskSpace(*(STRSAFE_LPCSTR *)(a4 + 3592));
            *(_QWORD *)(a4 + 496) = v14;
            if ( a1 && !*(_DWORD *)(a4 + 3792) )
            {
              *(_QWORD *)(a1 + 80) = *(_QWORD *)(a4 + 3664);
              *(_DWORD *)(a1 + 64) = *(_DWORD *)(a4 + 3744);
            }
          }
          return v8;
        }
      }
      v10 = 0;
    }
  }
  v11 = -a3;
  while ( 1 )
  {
    v12 = DZSetFilePointer(*a2, 0, 1);
    DZSetFilePointer(*a2, v11, 2);
    if ( *a2 != (HANDLE)-1LL && v12 <= DZSetFilePointer(*a2, 0, 1) )
    {
      DZSetFilePointer(*a2, v12, 0);
      goto LABEL_21;
    }
    if ( *a2 )
    {
      CloseHandle(*a2);
      *a2 = (HANDLE)-1LL;
    }
    if ( *(_DWORD *)(a4 + 3744) != 0xFFFF && (unsigned int)stat32(*(_QWORD *)(a4 + 3592), v24)
      || (unsigned int)dzMsgCB(*(_QWORD *)(a4 + 3168), 0, 1, *(_DWORD *)(a4 + 3744) + 2, dwCreationDisposition, a4) != 1 )
    {
      break;
    }
    v13 = CreateFileA(*(LPCSTR *)(a4 + 3592), 0xC0000000, 0, 0, 3u, 0x80u, 0);
    *a2 = v13;
    if ( v13 == (HANDLE)-1LL )
    {
      v10 = 0;
      v9 = 0;
      dzerr(13, a4);
    }
    else
    {
      v10 = 1;
    }
    v8 = 19;
    if ( !v9 )
      goto LABEL_16;
  }
  *(_DWORD *)(a4 + 208) = 1;
  return 9;
}

```

## disassembly

```asm
0x18009d5e4  push    rbx
0x18009d5e6  push    rsi
0x18009d5e7  push    rdi
0x18009d5e8  push    r12
0x18009d5ea  push    r13
0x18009d5ec  push    r14
0x18009d5ee  push    r15
0x18009d5f0  sub     rsp, 70h
0x18009d5f4  xorps   xmm0, xmm0
0x18009d5f7  xor     eax, eax
0x18009d5f9  mov     rdi, r9
0x18009d5fc  mov     r15, r8
0x18009d5ff  mov     r14, rdx
0x18009d602  mov     r13, rcx
0x18009d605  mov     ebx, eax
0x18009d607  movups  [rsp+0A8h+var_68], xmm0
0x18009d60c  movups  [rsp+0A8h+var_58], xmm0
0x18009d611  movups  [rsp+0A8h+var_48], xmm0
0x18009d616  cmp     [r9+0E9Ch], ax
0x18009d61e  jge     loc_18009D974
0x18009d624  test    rdx, rdx
0x18009d627  jz      loc_18009D974
0x18009d62d  lea     r12d, [rax+1]
0x18009d631  mov     esi, eax
0x18009d633  cmp     [r9+0ED0h], eax
0x18009d63a  jz      loc_18009D7A9
0x18009d640  neg     r15
0x18009d643  mov     rcx, [r14]
0x18009d646  xor     edx, edx
0x18009d648  lea     r8d, [rdx+1]
0x18009d64c  call    DZSetFilePointer
0x18009d651  mov     rcx, [r14]
0x18009d654  mov     r8d, 2
0x18009d65a  mov     rdx, r15
0x18009d65d  mov     rbx, rax
0x18009d660  call    DZSetFilePointer
0x18009d665  cmp     qword ptr [r14], 0FFFFFFFFFFFFFFFFh
0x18009d669  jz      short loc_18009D682
0x18009d66b  mov     rcx, [r14]
0x18009d66e  xor     edx, edx
0x18009d670  lea     r8d, [rdx+1]
0x18009d674  call    DZSetFilePointer
0x18009d679  cmp     rbx, rax
0x18009d67c  jle     loc_18009D784
0x18009d682  mov     rcx, [r14]; hObject
0x18009d685  test    rcx, rcx
0x18009d688  jz      short loc_18009D697
0x18009d68a  call    cs:__imp_CloseHandle
0x18009d690  mov     qword ptr [r14], 0FFFFFFFFFFFFFFFFh
0x18009d697  cmp     dword ptr [rdi+0EA0h], 0FFFFh
0x18009d6a1  jz      short loc_18009D6BC
0x18009d6a3  mov     rcx, [rdi+0E08h]
0x18009d6aa  lea     rdx, [rsp+0A8h+var_68]
0x18009d6af  call    stat32
0x18009d6b4  test    eax, eax
0x18009d6b6  jnz     loc_18009D79A
0x18009d6bc  mov     r9d, [rdi+0EA0h]
0x18009d6c3  xor     edx, edx
0x18009d6c5  mov     rcx, [rdi+0C60h]
0x18009d6cc  add     r9d, 2
0x18009d6d0  mov     qword ptr [rsp+0A8h+dwFlagsAndAttributes], rdi
0x18009d6d5  lea     r8d, [rdx+1]
0x18009d6d9  call    dzMsgCB
0x18009d6de  cmp     eax, 1
0x18009d6e1  jnz     loc_18009D79A
0x18009d6e7  mov     rcx, [rdi+0E08h]; lpFileName
0x18009d6ee  xor     r9d, r9d; lpSecurityAttributes
0x18009d6f1  mov     [rsp+0A8h+hTemplateFile], 0; hTemplateFile
0x18009d6fa  xor     r8d, r8d; dwShareMode
0x18009d6fd  mov     [rsp+0A8h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18009d705  mov     edx, 0C0000000h; dwDesiredAccess
0x18009d70a  mov     [rsp+0A8h+dwCreationDisposition], 3; dwCreationDisposition
0x18009d712  call    cs:__imp_CreateFileA
0x18009d718  mov     [r14], rax
0x18009d71b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18009d71f  jz      short loc_18009D728
0x18009d721  mov     esi, 1
0x18009d726  jmp     short loc_18009D738
0x18009d728  xor     esi, esi
0x18009d72a  xor     r12d, r12d
0x18009d72d  mov     rdx, rdi
0x18009d730  lea     ecx, [rsi+0Dh]
0x18009d733  call    dzerr
0x18009d738  mov     ebx, 13h
0x18009d73d  test    r12d, r12d
0x18009d740  jnz     loc_18009D643
0x18009d746  xor     r12d, r12d
0x18009d749  test    esi, esi
0x18009d74b  jz      loc_18009D974
0x18009d751  test    ebx, ebx
0x18009d753  jnz     loc_18009D974
0x18009d759  inc     dword ptr [rdi+0EA0h]
0x18009d75f  mov     [rdi+0E50h], r12
0x18009d766  mov     [rdi+0EC0h], r12
0x18009d76d  cmp     [rdi+0ED0h], r12d
0x18009d774  jz      loc_18009D92C
0x18009d77a  mov     eax, 200000h
0x18009d77f  jmp     loc_18009D938
0x18009d784  mov     rcx, [r14]
0x18009d787  xor     r8d, r8d
0x18009d78a  mov     rdx, rbx
0x18009d78d  call    DZSetFilePointer
0x18009d792  xor     r12d, r12d
0x18009d795  mov     ebx, r12d
0x18009d798  jmp     short loc_18009D749
0x18009d79a  mov     dword ptr [rdi+0D0h], 1
0x18009d7a4  jmp     loc_18009D96F
0x18009d7a9  xor     r12d, r12d
0x18009d7ac  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x18009d7b0  jz      short loc_18009D7C3
0x18009d7b2  mov     rcx, [rdi+0E08h]; pszSrc
0x18009d7b9  call    RemainingDiskSpace
0x18009d7be  cmp     rax, r15
0x18009d7c1  jge     short loc_18009D795
0x18009d7c3  cmp     qword ptr [r14], 0FFFFFFFFFFFFFFFFh
0x18009d7c7  jz      short loc_18009D7D9
0x18009d7c9  mov     rcx, [r14]; hObject
0x18009d7cc  call    cs:__imp_CloseHandle
0x18009d7d2  mov     qword ptr [r14], 0FFFFFFFFFFFFFFFFh
0x18009d7d9  cmp     dword ptr [rdi+0EA0h], 0FFFFh
0x18009d7e3  jz      short loc_18009D7FE
0x18009d7e5  mov     rcx, [rdi+0E08h]
0x18009d7ec  lea     rdx, [rsp+0A8h+var_68]
0x18009d7f1  call    stat32
0x18009d7f6  test    eax, eax
0x18009d7f8  jnz     loc_18009D964
0x18009d7fe  mov     ebx, 4
0x18009d803  lea     esi, [rbx-3]
0x18009d806  cmp     ebx, esi
0x18009d808  jz      loc_18009D899
0x18009d80e  mov     r9d, [rdi+0EA0h]
0x18009d815  mov     r8d, esi
0x18009d818  mov     rcx, [rdi+0C60h]
0x18009d81f  add     r9d, 2
0x18009d823  xor     edx, edx
0x18009d825  mov     qword ptr [rsp+0A8h+dwFlagsAndAttributes], rdi
0x18009d82a  call    dzMsgCB
0x18009d82f  mov     ebx, eax
0x18009d831  cmp     eax, esi
0x18009d833  jnz     short loc_18009D88B
0x18009d835  mov     rcx, [rdi+0E08h]; lpszStart
0x18009d83c  call    dzDriveFromPath
0x18009d841  test    eax, eax
0x18009d843  jnz     short loc_18009D84B
0x18009d845  call    cs:__imp__getdrive
0x18009d84b  mov     rcx, [rdi+0E08h]; lpszStart
0x18009d852  call    dzDriveFromPath
0x18009d857  mov     ecx, eax
0x18009d859  mov     rdx, rdi
0x18009d85c  call    IsMediaWritable
0x18009d861  test    eax, eax
0x18009d863  jnz     short loc_18009D806
0x18009d865  mov     rcx, [rdi+0C60h]
0x18009d86c  lea     edx, [rax+0Ch]
0x18009d86f  xor     r9d, r9d
0x18009d872  mov     qword ptr [rsp+0A8h+dwFlagsAndAttributes], rdi
0x18009d877  lea     r8d, [rax+5]
0x18009d87b  call    dzMsgCB
0x18009d880  mov     ebx, eax
0x18009d882  cmp     eax, 4
0x18009d885  jnz     loc_18009D969
0x18009d88b  cmp     ebx, 2
0x18009d88e  jnz     loc_18009D806
0x18009d894  jmp     loc_18009D969
0x18009d899  mov     rcx, [rdi+0E08h]; lpszStart
0x18009d8a0  add     [rdi+0EA0h], esi
0x18009d8a6  movzx   ebx, word ptr [rdi+0E9Ch]
0x18009d8ad  call    dzDriveFromPath
0x18009d8b2  mov     ecx, eax
0x18009d8b4  mov     r8, rdi
0x18009d8b7  movzx   edx, bx
0x18009d8ba  call    CleanTargetMedia
0x18009d8bf  sub     [rdi+0EA0h], esi
0x18009d8c5  test    eax, eax
0x18009d8c7  jz      short loc_18009D924
0x18009d8c9  mov     rcx, [rdi+0E08h]; pszSrc
0x18009d8d0  call    MakeZipFileDir
0x18009d8d5  test    eax, eax
0x18009d8d7  jnz     short loc_18009D924
0x18009d8d9  mov     rcx, [rdi+0E08h]; lpFileName
0x18009d8e0  xor     r9d, r9d; lpSecurityAttributes
0x18009d8e3  mov     [rsp+0A8h+hTemplateFile], r12; hTemplateFile
0x18009d8e8  xor     r8d, r8d; dwShareMode
0x18009d8eb  mov     [rsp+0A8h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18009d8f3  mov     edx, 0C0000000h; dwDesiredAccess
0x18009d8f8  mov     [rsp+0A8h+dwCreationDisposition], 2; dwCreationDisposition
0x18009d900  call    cs:__imp_CreateFileA
0x18009d906  mov     [r14], rax
0x18009d909  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18009d90d  jz      short loc_18009D924
0x18009d90f  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x18009d913  jnz     loc_18009D7B2
0x18009d919  mov     r15d, 200h
0x18009d91f  jmp     loc_18009D7AC
0x18009d924  mov     esi, r12d
0x18009d927  jmp     loc_18009D7AC
0x18009d92c  mov     rcx, [rdi+0E08h]; pszSrc
0x18009d933  call    RemainingDiskSpace
0x18009d938  mov     [rdi+1F0h], rax
0x18009d93f  test    r13, r13
0x18009d942  jz      short loc_18009D974
0x18009d944  cmp     [rdi+0ED0h], r12d
0x18009d94b  jnz     short loc_18009D974
0x18009d94d  mov     rax, [rdi+0E50h]
0x18009d954  mov     [r13+50h], rax
0x18009d958  mov     eax, [rdi+0EA0h]
0x18009d95e  mov     [r13+40h], eax
0x18009d962  jmp     short loc_18009D974
0x18009d964  mov     esi, 1
0x18009d969  mov     [rdi+0D0h], esi
0x18009d96f  mov     ebx, 9
0x18009d974  mov     eax, ebx
0x18009d976  add     rsp, 70h
0x18009d97a  pop     r15
0x18009d97c  pop     r14
0x18009d97e  pop     r13
0x18009d980  pop     r12
0x18009d982  pop     rdi
0x18009d983  pop     rsi
0x18009d984  pop     rbx
0x18009d985  retn
```
