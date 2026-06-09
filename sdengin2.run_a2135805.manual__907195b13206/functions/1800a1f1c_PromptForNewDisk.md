# PromptForNewDisk

- ea: `0x1800a1f1c`
- end: `0x1800a22dd`
- name: `PromptForNewDisk`
- size: `961`
- prototype: ``
- caller_count: `4`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x1800a4c0c`
- `0x1800a500c`
- `0x1800a5548`
- `0x1800a5704`

## callees

- `0x1800a1a1c`
- `0x1800a1dd0`
- `0x1800a1f1c`
- `0x1800a236c`
- `0x1800a2458`
- `0x1800a2834`
- `0x1800a3d14`
- `0x1800a8544`
- `0x1800a85ac`
- `0x1800b18d8`

## import_xrefs

- `msvcrt!_getdrive` at `0x1800a218f`
- `msvcrt!_getdrive` at `0x1800a218f`
- `KERNEL32!CloseHandle` at `0x1800a1fc2`
- `KERNEL32!CloseHandle` at `0x1800a2110`
- `KERNEL32!CloseHandle` at `0x1800a1fc2`
- `KERNEL32!CloseHandle` at `0x1800a2110`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x1800a2050`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x1800a2250`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x1800a2050`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x1800a2250`

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
  _OWORD v23[6]; // [rsp+40h] [rbp-68h] BYREF

  v5 = a3;
  v8 = 0;
  memset(v23, 0, 48);
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
        if ( *(_DWORD *)(a4 + 3744) != 0xFFFF && (unsigned int)stat32(*(_QWORD *)(a4 + 3592), v23) )
        {
LABEL_48:
          *(_DWORD *)(a4 + 208) = 1;
          return 9;
        }
        v15 = 4;
        v10 = 1;
        while ( v15 != 1 )
        {
          v15 = dzMsgCB(*(_QWORD *)(a4 + 3168), 0, 1, *(_DWORD *)(a4 + 3744) + 2);
          if ( v15 == 1 )
          {
            if ( !(unsigned int)dzDriveFromPath(*(LPCSTR *)(a4 + 3592)) )
              _getdrive();
            v16 = dzDriveFromPath(*(LPCSTR *)(a4 + 3592));
            if ( !(unsigned int)IsMediaWritable(v16, a4) )
            {
              v15 = dzMsgCB(*(_QWORD *)(a4 + 3168), 12, 5, 0);
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
    if ( *(_DWORD *)(a4 + 3744) != 0xFFFF && (unsigned int)stat32(*(_QWORD *)(a4 + 3592), v23)
      || (unsigned int)dzMsgCB(*(_QWORD *)(a4 + 3168), 0, 1, *(_DWORD *)(a4 + 3744) + 2) != 1 )
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
0x1800a1f1c  push    rbx
0x1800a1f1e  push    rsi
0x1800a1f1f  push    rdi
0x1800a1f20  push    r12
0x1800a1f22  push    r13
0x1800a1f24  push    r14
0x1800a1f26  push    r15
0x1800a1f28  sub     rsp, 70h
0x1800a1f2c  xorps   xmm0, xmm0
0x1800a1f2f  xor     eax, eax
0x1800a1f31  mov     rdi, r9
0x1800a1f34  mov     r15, r8
0x1800a1f37  mov     r14, rdx
0x1800a1f3a  mov     r13, rcx
0x1800a1f3d  mov     ebx, eax
0x1800a1f3f  movups  [rsp+0A8h+var_68], xmm0
0x1800a1f44  movups  [rsp+0A8h+var_58], xmm0
0x1800a1f49  movups  [rsp+0A8h+var_48], xmm0
0x1800a1f4e  cmp     [r9+0E9Ch], ax
0x1800a1f56  jge     loc_1800A22CA
0x1800a1f5c  test    rdx, rdx
0x1800a1f5f  jz      loc_1800A22CA
0x1800a1f65  lea     r12d, [rax+1]
0x1800a1f69  mov     esi, eax
0x1800a1f6b  cmp     [r9+0ED0h], eax
0x1800a1f72  jz      loc_1800A20ED
0x1800a1f78  neg     r15
0x1800a1f7b  mov     rcx, [r14]
0x1800a1f7e  xor     edx, edx
0x1800a1f80  lea     r8d, [rdx+1]
0x1800a1f84  call    DZSetFilePointer
0x1800a1f89  mov     rcx, [r14]
0x1800a1f8c  mov     r8d, 2
0x1800a1f92  mov     rdx, r15
0x1800a1f95  mov     rbx, rax
0x1800a1f98  call    DZSetFilePointer
0x1800a1f9d  cmp     qword ptr [r14], 0FFFFFFFFFFFFFFFFh
0x1800a1fa1  jz      short loc_1800A1FBA
0x1800a1fa3  mov     rcx, [r14]
0x1800a1fa6  xor     edx, edx
0x1800a1fa8  lea     r8d, [rdx+1]
0x1800a1fac  call    DZSetFilePointer
0x1800a1fb1  cmp     rbx, rax
0x1800a1fb4  jle     loc_1800A20C8
0x1800a1fba  mov     rcx, [r14]; hObject
0x1800a1fbd  test    rcx, rcx
0x1800a1fc0  jz      short loc_1800A1FD5
0x1800a1fc2  call    cs:__imp_CloseHandle
0x1800a1fc9  nop     dword ptr [rax+rax+00h]
0x1800a1fce  mov     qword ptr [r14], 0FFFFFFFFFFFFFFFFh
0x1800a1fd5  cmp     dword ptr [rdi+0EA0h], 0FFFFh
0x1800a1fdf  jz      short loc_1800A1FFA
0x1800a1fe1  mov     rcx, [rdi+0E08h]
0x1800a1fe8  lea     rdx, [rsp+0A8h+var_68]
0x1800a1fed  call    stat32
0x1800a1ff2  test    eax, eax
0x1800a1ff4  jnz     loc_1800A20DE
0x1800a1ffa  mov     r9d, [rdi+0EA0h]
0x1800a2001  xor     edx, edx
0x1800a2003  mov     rcx, [rdi+0C60h]
0x1800a200a  add     r9d, 2
0x1800a200e  mov     qword ptr [rsp+0A8h+dwFlagsAndAttributes], rdi
0x1800a2013  lea     r8d, [rdx+1]
0x1800a2017  call    dzMsgCB
0x1800a201c  cmp     eax, 1
0x1800a201f  jnz     loc_1800A20DE
0x1800a2025  mov     rcx, [rdi+0E08h]; lpFileName
0x1800a202c  xor     r9d, r9d; lpSecurityAttributes
0x1800a202f  mov     [rsp+0A8h+hTemplateFile], 0; hTemplateFile
0x1800a2038  xor     r8d, r8d; dwShareMode
0x1800a203b  mov     [rsp+0A8h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800a2043  mov     edx, 0C0000000h; dwDesiredAccess
0x1800a2048  mov     [rsp+0A8h+dwCreationDisposition], 3; dwCreationDisposition
0x1800a2050  call    cs:__imp_CreateFileA
0x1800a2057  nop     dword ptr [rax+rax+00h]
0x1800a205c  mov     [r14], rax
0x1800a205f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800a2063  jz      short loc_1800A206C
0x1800a2065  mov     esi, 1
0x1800a206a  jmp     short loc_1800A207C
0x1800a206c  xor     esi, esi
0x1800a206e  xor     r12d, r12d
0x1800a2071  mov     rdx, rdi
0x1800a2074  lea     ecx, [rsi+0Dh]
0x1800a2077  call    dzerr
0x1800a207c  mov     ebx, 13h
0x1800a2081  test    r12d, r12d
0x1800a2084  jnz     loc_1800A1F7B
0x1800a208a  xor     r12d, r12d
0x1800a208d  test    esi, esi
0x1800a208f  jz      loc_1800A22CA
0x1800a2095  test    ebx, ebx
0x1800a2097  jnz     loc_1800A22CA
0x1800a209d  inc     dword ptr [rdi+0EA0h]
0x1800a20a3  mov     [rdi+0E50h], r12
0x1800a20aa  mov     [rdi+0EC0h], r12
0x1800a20b1  cmp     [rdi+0ED0h], r12d
0x1800a20b8  jz      loc_1800A2282
0x1800a20be  mov     eax, 200000h
0x1800a20c3  jmp     loc_1800A228E
0x1800a20c8  mov     rcx, [r14]
0x1800a20cb  xor     r8d, r8d
0x1800a20ce  mov     rdx, rbx
0x1800a20d1  call    DZSetFilePointer
0x1800a20d6  xor     r12d, r12d
0x1800a20d9  mov     ebx, r12d
0x1800a20dc  jmp     short loc_1800A208D
0x1800a20de  mov     dword ptr [rdi+0D0h], 1
0x1800a20e8  jmp     loc_1800A22C5
0x1800a20ed  xor     r12d, r12d
0x1800a20f0  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x1800a20f4  jz      short loc_1800A2107
0x1800a20f6  mov     rcx, [rdi+0E08h]; pszSrc
0x1800a20fd  call    RemainingDiskSpace
0x1800a2102  cmp     rax, r15
0x1800a2105  jge     short loc_1800A20D9
0x1800a2107  cmp     qword ptr [r14], 0FFFFFFFFFFFFFFFFh
0x1800a210b  jz      short loc_1800A2123
0x1800a210d  mov     rcx, [r14]; hObject
0x1800a2110  call    cs:__imp_CloseHandle
0x1800a2117  nop     dword ptr [rax+rax+00h]
0x1800a211c  mov     qword ptr [r14], 0FFFFFFFFFFFFFFFFh
0x1800a2123  cmp     dword ptr [rdi+0EA0h], 0FFFFh
0x1800a212d  jz      short loc_1800A2148
0x1800a212f  mov     rcx, [rdi+0E08h]
0x1800a2136  lea     rdx, [rsp+0A8h+var_68]
0x1800a213b  call    stat32
0x1800a2140  test    eax, eax
0x1800a2142  jnz     loc_1800A22BA
0x1800a2148  mov     ebx, 4
0x1800a214d  lea     esi, [rbx-3]
0x1800a2150  cmp     ebx, esi
0x1800a2152  jz      loc_1800A21E9
0x1800a2158  mov     r9d, [rdi+0EA0h]
0x1800a215f  mov     r8d, esi
0x1800a2162  mov     rcx, [rdi+0C60h]
0x1800a2169  add     r9d, 2
0x1800a216d  xor     edx, edx
0x1800a216f  mov     qword ptr [rsp+0A8h+dwFlagsAndAttributes], rdi
0x1800a2174  call    dzMsgCB
0x1800a2179  mov     ebx, eax
0x1800a217b  cmp     eax, esi
0x1800a217d  jnz     short loc_1800A21DB
0x1800a217f  mov     rcx, [rdi+0E08h]; lpszStart
0x1800a2186  call    dzDriveFromPath
0x1800a218b  test    eax, eax
0x1800a218d  jnz     short loc_1800A219B
0x1800a218f  call    cs:__imp__getdrive
0x1800a2196  nop     dword ptr [rax+rax+00h]
0x1800a219b  mov     rcx, [rdi+0E08h]; lpszStart
0x1800a21a2  call    dzDriveFromPath
0x1800a21a7  mov     ecx, eax
0x1800a21a9  mov     rdx, rdi
0x1800a21ac  call    IsMediaWritable
0x1800a21b1  test    eax, eax
0x1800a21b3  jnz     short loc_1800A2150
0x1800a21b5  mov     rcx, [rdi+0C60h]
0x1800a21bc  lea     edx, [rax+0Ch]
0x1800a21bf  xor     r9d, r9d
0x1800a21c2  mov     qword ptr [rsp+0A8h+dwFlagsAndAttributes], rdi
0x1800a21c7  lea     r8d, [rax+5]
0x1800a21cb  call    dzMsgCB
0x1800a21d0  mov     ebx, eax
0x1800a21d2  cmp     eax, 4
0x1800a21d5  jnz     loc_1800A22BF
0x1800a21db  cmp     ebx, 2
0x1800a21de  jnz     loc_1800A2150
0x1800a21e4  jmp     loc_1800A22BF
0x1800a21e9  mov     rcx, [rdi+0E08h]; lpszStart
0x1800a21f0  add     [rdi+0EA0h], esi
0x1800a21f6  movzx   ebx, word ptr [rdi+0E9Ch]
0x1800a21fd  call    dzDriveFromPath
0x1800a2202  mov     ecx, eax
0x1800a2204  mov     r8, rdi
0x1800a2207  movzx   edx, bx
0x1800a220a  call    CleanTargetMedia
0x1800a220f  sub     [rdi+0EA0h], esi
0x1800a2215  test    eax, eax
0x1800a2217  jz      short loc_1800A227A
0x1800a2219  mov     rcx, [rdi+0E08h]; pszSrc
0x1800a2220  call    MakeZipFileDir
0x1800a2225  test    eax, eax
0x1800a2227  jnz     short loc_1800A227A
0x1800a2229  mov     rcx, [rdi+0E08h]; lpFileName
0x1800a2230  xor     r9d, r9d; lpSecurityAttributes
0x1800a2233  mov     [rsp+0A8h+hTemplateFile], r12; hTemplateFile
0x1800a2238  xor     r8d, r8d; dwShareMode
0x1800a223b  mov     [rsp+0A8h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800a2243  mov     edx, 0C0000000h; dwDesiredAccess
0x1800a2248  mov     [rsp+0A8h+dwCreationDisposition], 2; dwCreationDisposition
0x1800a2250  call    cs:__imp_CreateFileA
0x1800a2257  nop     dword ptr [rax+rax+00h]
0x1800a225c  mov     [r14], rax
0x1800a225f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800a2263  jz      short loc_1800A227A
0x1800a2265  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x1800a2269  jnz     loc_1800A20F6
0x1800a226f  mov     r15d, 200h
0x1800a2275  jmp     loc_1800A20F0
0x1800a227a  mov     esi, r12d
0x1800a227d  jmp     loc_1800A20F0
0x1800a2282  mov     rcx, [rdi+0E08h]; pszSrc
0x1800a2289  call    RemainingDiskSpace
0x1800a228e  mov     [rdi+1F0h], rax
0x1800a2295  test    r13, r13
0x1800a2298  jz      short loc_1800A22CA
0x1800a229a  cmp     [rdi+0ED0h], r12d
0x1800a22a1  jnz     short loc_1800A22CA
0x1800a22a3  mov     rax, [rdi+0E50h]
0x1800a22aa  mov     [r13+50h], rax
0x1800a22ae  mov     eax, [rdi+0EA0h]
0x1800a22b4  mov     [r13+40h], eax
0x1800a22b8  jmp     short loc_1800A22CA
0x1800a22ba  mov     esi, 1
0x1800a22bf  mov     [rdi+0D0h], esi
0x1800a22c5  mov     ebx, 9
0x1800a22ca  mov     eax, ebx
0x1800a22cc  add     rsp, 70h
0x1800a22d0  pop     r15
0x1800a22d2  pop     r14
0x1800a22d4  pop     r13
0x1800a22d6  pop     r12
0x1800a22d8  pop     rdi
0x1800a22d9  pop     rsi
0x1800a22da  pop     rbx
0x1800a22db  retn
```
