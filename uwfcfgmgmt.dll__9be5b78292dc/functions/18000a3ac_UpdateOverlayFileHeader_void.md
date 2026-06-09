# UpdateOverlayFileHeader(void *)

- ea: `0x18000a3ac`
- end: `0x18000a5e5`
- name: `?UpdateOverlayFileHeader@@YAJPEAX@Z`
- size: `569`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, installer_update`

## callers

- `0x180006bb0`
- `0x1800098d0`

## callees

- `0x180007e38`
- `0x18000a3ac`
- `0x18001afe2`
- `0x18001b020`
- `0x18001b0e0`

## import_xrefs

- `msvcrt!free` at `0x18000a5b6`
- `msvcrt!free` at `0x18000a5b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a489`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a4c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a489`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a4c9`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18000a4bf`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18000a53b`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18000a584`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18000a4bf`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18000a53b`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18000a584`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x18000a5a9`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x18000a5a9`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18000a47e`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18000a47e`
- `RPCRT4!UuidCreate` at `0x18000a466`
- `RPCRT4!UuidCreate` at `0x18000a466`

## pseudocode

```c
__int64 __fastcall UpdateOverlayFileHeader(void *a1)
{
  unsigned int v3; // esi
  signed int LastError; // eax
  unsigned int v5; // ebx
  signed int v6; // eax
  unsigned int v7; // ebx
  __int64 *v8; // r10
  unsigned int v9; // [rsp+30h] [rbp-D0h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+34h] [rbp-CCh] BYREF
  void *Block; // [rsp+38h] [rbp-C8h] BYREF
  int Buffer; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v13; // [rsp+44h] [rbp-BCh]
  int v14; // [rsp+4Ch] [rbp-B4h]
  __int128 v15; // [rsp+50h] [rbp-B0h]
  struct _GUID v16; // [rsp+60h] [rbp-A0h]
  UUID Uuid; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v18; // [rsp+90h] [rbp-70h]
  struct _GUID v19; // [rsp+1040h] [rbp+F40h] BYREF
  _BYTE v20[4096]; // [rsp+1050h] [rbp+F50h] BYREF

  Block = 0;
  v9 = 0;
  v19 = 0;
  if ( GetRetrievalPointers(a1, (struct _UWFVOL_SWAPFILE_EXTENT **)&Block, &v9, &v19) < 0 )
    return 2147500037LL;
  memset_0(&Uuid, 0, 0xFD0u);
  Buffer = 1397118805;
  v13 = 0;
  v15 = UWF_SWAPFILE_SIGNATURE_GUID;
  v14 = 0;
  v16 = v19;
  UuidCreate(&Uuid);
  v3 = v9;
  v18 = v9;
  if ( SetFilePointer(a1, 0, 0, 0) == -1 )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
  }
  else
  {
    if ( !WriteFile(a1, &Buffer, 0x58u, 0, 0) )
      goto LABEL_7;
    v7 = 0;
    if ( v3 )
    {
      while ( 1 )
      {
        v8 = (__int64 *)((char *)Block + 16 * v7);
        if ( ((((v8[1] >> 63) & 0xFFF) + v8[1]) & 0xFFF) != ((v8[1] >> 63) & 0xFFF)
          || ((((*v8 >> 63) & 0xFFF) + *v8) & 0xFFF) != ((*v8 >> 63) & 0xFFF) )
        {
          break;
        }
        if ( !WriteFile(a1, (char *)Block + 16 * v7, 0x10u, 0, 0) )
          goto LABEL_7;
        if ( ++v7 >= v3 )
          goto LABEL_15;
      }
      v5 = -2147467259;
      goto LABEL_20;
    }
LABEL_15:
    memset_0(v20, 0, sizeof(v20));
    NumberOfBytesWritten = 0;
    if ( WriteFile(a1, v20, 0x1000u, &NumberOfBytesWritten, 0) )
    {
      if ( NumberOfBytesWritten == 4096 )
      {
        FlushFileBuffers(a1);
        v5 = 0;
      }
      else
      {
        v5 = -2147418113;
      }
    }
    else
    {
LABEL_7:
      v6 = GetLastError();
      if ( v6 > 0 )
        v6 = (unsigned __int16)v6 | 0x80070000;
      v5 = v6;
    }
  }
LABEL_20:
  free(Block);
  return v5;
}

```

## disassembly

```asm
0x18000a3ac  mov     [rsp-8+arg_8], rbx
0x18000a3b1  mov     [rsp-8+arg_10], rsi
0x18000a3b6  push    rbp
0x18000a3b7  push    rdi
0x18000a3b8  push    r15
0x18000a3ba  lea     rbp, [rsp-1F60h]
0x18000a3c2  mov     eax, 2060h
0x18000a3c7  call    _alloca_probe
0x18000a3cc  sub     rsp, rax
0x18000a3cf  mov     rax, cs:__security_cookie
0x18000a3d6  xor     rax, rsp
0x18000a3d9  mov     [rbp+1F70h+var_20], rax
0x18000a3e0  xorps   xmm0, xmm0
0x18000a3e3  mov     [rsp+2070h+Block], 0
0x18000a3ec  lea     r9, [rbp+1F70h+var_1030]; struct _GUID *
0x18000a3f3  mov     [rsp+2070h+var_2040], 0
0x18000a3fb  lea     r8, [rsp+2070h+var_2040]; unsigned int *
0x18000a400  mov     rdi, rcx
0x18000a403  lea     rdx, [rsp+2070h+Block]; struct _UWFVOL_SWAPFILE_EXTENT **
0x18000a408  movups  xmmword ptr [rbp+1F70h+var_1030.Data1], xmm0
0x18000a40f  call    ?GetRetrievalPointers@@YAJPEAXPEAPEAU_UWFVOL_SWAPFILE_EXTENT@@PEAKPEAU_GUID@@@Z; GetRetrievalPointers(void *,_UWFVOL_SWAPFILE_EXTENT * *,ulong *,_GUID *)
0x18000a414  test    eax, eax
0x18000a416  jns     short loc_18000A422
0x18000a418  mov     eax, 80004005h
0x18000a41d  jmp     loc_18000A5BE
0x18000a422  xor     edx, edx; Val
0x18000a424  lea     rcx, [rsp+2070h+Uuid]; void *
0x18000a429  mov     r8d, 0FD0h; Size
0x18000a42f  call    memset_0
0x18000a434  movups  xmm0, cs:UWF_SWAPFILE_SIGNATURE_GUID
0x18000a43b  xor     eax, eax
0x18000a43d  mov     [rsp+2070h+Buffer], 53465755h
0x18000a445  lea     rcx, [rsp+2070h+Uuid]; Uuid
0x18000a44a  mov     [rsp+2070h+var_202C], rax
0x18000a44f  movdqu  [rsp+2070h+var_2020], xmm0
0x18000a455  mov     [rsp+2070h+var_2024], eax
0x18000a459  movups  xmm0, xmmword ptr [rbp+1F70h+var_1030.Data1]
0x18000a460  movdqu  [rsp+2070h+var_2010], xmm0
0x18000a466  call    cs:__imp_UuidCreate
0x18000a46c  mov     esi, [rsp+2070h+var_2040]
0x18000a470  xor     r9d, r9d; dwMoveMethod
0x18000a473  xor     r8d, r8d; lpDistanceToMoveHigh
0x18000a476  mov     [rbp+1F70h+var_1FE0], esi
0x18000a479  xor     edx, edx; lDistanceToMove
0x18000a47b  mov     rcx, rdi; hFile
0x18000a47e  call    cs:__imp_SetFilePointer
0x18000a484  cmp     eax, 0FFFFFFFFh
0x18000a487  jnz     short loc_18000A4A7
0x18000a489  call    cs:__imp_GetLastError
0x18000a48f  mov     ebx, eax
0x18000a491  test    eax, eax
0x18000a493  jle     loc_18000A5B1
0x18000a499  movzx   ebx, ax
0x18000a49c  or      ebx, 80070000h
0x18000a4a2  jmp     loc_18000A5B1
0x18000a4a7  xor     r9d, r9d; lpNumberOfBytesWritten
0x18000a4aa  mov     [rsp+2070h+lpOverlapped], 0; lpOverlapped
0x18000a4b3  lea     rdx, [rsp+2070h+Buffer]; lpBuffer
0x18000a4b8  mov     rcx, rdi; hFile
0x18000a4bb  lea     r8d, [r9+58h]; nNumberOfBytesToWrite
0x18000a4bf  call    cs:__imp_WriteFile
0x18000a4c5  test    eax, eax
0x18000a4c7  jnz     short loc_18000A4E2
0x18000a4c9  call    cs:__imp_GetLastError
0x18000a4cf  test    eax, eax
0x18000a4d1  jle     short loc_18000A4DB
0x18000a4d3  movzx   eax, ax
0x18000a4d6  or      eax, 80070000h
0x18000a4db  mov     ebx, eax
0x18000a4dd  jmp     loc_18000A5B1
0x18000a4e2  xor     ebx, ebx
0x18000a4e4  test    esi, esi
0x18000a4e6  jz      short loc_18000A54B
0x18000a4e8  mov     r15d, 0FFFh
0x18000a4ee  mov     r10d, ebx
0x18000a4f1  shl     r10, 4
0x18000a4f5  add     r10, [rsp+2070h+Block]
0x18000a4fa  mov     rax, [r10+8]
0x18000a4fe  cqo
0x18000a500  and     rdx, r15
0x18000a503  add     rax, rdx
0x18000a506  and     rax, r15
0x18000a509  cmp     rax, rdx
0x18000a50c  jnz     loc_18000A59F
0x18000a512  mov     rax, [r10]
0x18000a515  cqo
0x18000a517  and     rdx, r15
0x18000a51a  add     rax, rdx
0x18000a51d  and     rax, r15
0x18000a520  cmp     rax, rdx
0x18000a523  jnz     short loc_18000A59F
0x18000a525  xor     r9d, r9d; lpNumberOfBytesWritten
0x18000a528  mov     [rsp+2070h+lpOverlapped], 0; lpOverlapped
0x18000a531  mov     rdx, r10; lpBuffer
0x18000a534  mov     rcx, rdi; hFile
0x18000a537  lea     r8d, [r9+10h]; nNumberOfBytesToWrite
0x18000a53b  call    cs:__imp_WriteFile
0x18000a541  test    eax, eax
0x18000a543  jz      short loc_18000A4C9
0x18000a545  inc     ebx
0x18000a547  cmp     ebx, esi
0x18000a549  jb      short loc_18000A4EE
0x18000a54b  mov     ebx, 1000h
0x18000a550  lea     rcx, [rbp+1F70h+var_1020]; void *
0x18000a557  mov     r8d, ebx; Size
0x18000a55a  xor     edx, edx; Val
0x18000a55c  call    memset_0
0x18000a561  lea     r9, [rsp+2070h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18000a566  mov     [rsp+2070h+NumberOfBytesWritten], 0
0x18000a56e  mov     r8d, ebx; nNumberOfBytesToWrite
0x18000a571  mov     [rsp+2070h+lpOverlapped], 0; lpOverlapped
0x18000a57a  lea     rdx, [rbp+1F70h+var_1020]; lpBuffer
0x18000a581  mov     rcx, rdi; hFile
0x18000a584  call    cs:__imp_WriteFile
0x18000a58a  test    eax, eax
0x18000a58c  jz      loc_18000A4C9
0x18000a592  cmp     [rsp+2070h+NumberOfBytesWritten], ebx
0x18000a596  jz      short loc_18000A5A6
0x18000a598  mov     ebx, 8000FFFFh
0x18000a59d  jmp     short loc_18000A5B1
0x18000a59f  mov     ebx, 80004005h
0x18000a5a4  jmp     short loc_18000A5B1
0x18000a5a6  mov     rcx, rdi; hFile
0x18000a5a9  call    cs:__imp_FlushFileBuffers
0x18000a5af  xor     ebx, ebx
0x18000a5b1  mov     rcx, [rsp+2070h+Block]; Block
0x18000a5b6  call    cs:__imp_free
0x18000a5bc  mov     eax, ebx
0x18000a5be  mov     rcx, [rbp+1F70h+var_20]
0x18000a5c5  xor     rcx, rsp; StackCookie
0x18000a5c8  call    __security_check_cookie
0x18000a5cd  lea     r11, [rsp+2070h+var_10]
0x18000a5d5  mov     rbx, [r11+28h]
0x18000a5d9  mov     rsi, [r11+30h]
0x18000a5dd  mov     rsp, r11
0x18000a5e0  pop     r15
0x18000a5e2  pop     rdi
0x18000a5e3  pop     rbp
0x18000a5e4  retn
```
