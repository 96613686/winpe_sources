# RecordHashCodesAndSizes(_FILE_ID_EXTD_DIR_INFORMATION *,DIRECTORY_SCAN_FUNC_ARGS *,ScanDirectoryObjectFlag,bool)

- ea: `0x18001b160`
- end: `0x18001b41e`
- name: `?RecordHashCodesAndSizes@@YAJPEAU_FILE_ID_EXTD_DIR_INFORMATION@@PEAUDIRECTORY_SCAN_FUNC_ARGS@@W4ScanDirectoryObjectFlag@@_N@Z`
- size: `702`
- prototype: `int __high(struct _FILE_ID_EXTD_DIR_INFORMATION *, struct DIRECTORY_SCAN_FUNC_ARGS *, enum ScanDirectoryObjectFlag, bool)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180005c94`
- `0x180019590`
- `0x18001b160`
- `0x18001e428`
- `0x18001f230`
- `0x180020c30`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001b3fd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001b3fd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001b3eb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001b3eb`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18001b314`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18001b314`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001b2a7`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001b2a7`
- `ntdll!NtClose` at `0x18001b3de`
- `ntdll!NtClose` at `0x18001b3de`
- `bcrypt!BCryptHashData` at `0x18001b32f`
- `bcrypt!BCryptHashData` at `0x18001b32f`
- `bcrypt!BCryptDestroyHash` at `0x18001b3c4`
- `bcrypt!BCryptDestroyHash` at `0x18001b3c4`
- `bcrypt!BCryptCreateHash` at `0x18001b231`
- `bcrypt!BCryptCreateHash` at `0x18001b231`
- `bcrypt!BCryptFinishHash` at `0x18001b366`
- `bcrypt!BCryptFinishHash` at `0x18001b366`

## pseudocode

```c
__int64 __fastcall RecordHashCodesAndSizes(__int64 a1, __int64 a2, int a3, unsigned __int8 a4)
{
  unsigned int v7; // edx
  __int64 FileW; // r13
  unsigned int v9; // r8d
  int LastWin32Error; // esi
  BCRYPT_HASH_HANDLE *v11; // rbx
  NTSTATUS Hash; // eax
  unsigned __int16 v13; // r8
  __int64 i; // r12
  __int64 v15; // rsi
  __int64 v16; // rsi
  NTSTATUS v17; // eax
  NTSTATUS v18; // eax
  __int64 v19; // r9
  HANDLE ProcessHeap; // rax
  struct _UNICODE_STRING v21; // [rsp+40h] [rbp-20h] BYREF
  LPCWSTR lpFileName[2]; // [rsp+50h] [rbp-10h] BYREF
  DWORD NumberOfBytesRead; // [rsp+A0h] [rbp+40h] BYREF
  unsigned __int8 v24; // [rsp+A8h] [rbp+48h]

  v24 = a4;
  *(_OWORD *)lpFileName = 0;
  v21 = 0;
  if ( a3 == 16 )
  {
    WriteInstallersHashBuffer((struct DIRECTORY_SCAN_FUNC_ARGS *)a2);
    return 0;
  }
  else
  {
    v7 = *(unsigned __int16 *)(a2 + 130);
    FileW = -1;
    v9 = *(unsigned __int16 *)(a2 + 16LL * a4 + 40) + *(_DWORD *)(a1 + 60) + 6;
    if ( v9 <= v7 )
    {
      if ( *(_WORD *)(a2 + 120) >= 0x3E8u || v9 + *(unsigned __int16 *)(a2 + 128) > v7 )
        WriteInstallersHashBuffer((struct DIRECTORY_SCAN_FUNC_ARGS *)a2);
      v11 = (BCRYPT_HASH_HANDLE *)(a2 + 168);
      Hash = BCryptCreateHash(*(BCRYPT_ALG_HANDLE *)(a2 + 152), (BCRYPT_HASH_HANDLE *)(a2 + 168), 0, 0, 0, 0, 0x20u);
      LastWin32Error = Hash | 0x10000000;
      if ( Hash >= 0 )
      {
        v21.Buffer = (PWSTR)(a1 + 88);
        v21.Length = *(_WORD *)(a1 + 60);
        v21.MaximumLength = v21.Length + 2;
        LastWin32Error = CombinePathParts(
                           (struct _UNICODE_STRING *)(a2 + 24),
                           &v21,
                           v13,
                           (struct _UNICODE_STRING *)lpFileName);
        if ( LastWin32Error >= 0 )
        {
          FileW = (__int64)CreateFileW(lpFileName[1], 0x80000000, 2u, 0, 3u, 0x8000080u, 0);
          if ( FileW == -1 )
          {
LABEL_11:
            LastWin32Error = GetLastWin32Error();
          }
          else
          {
            for ( i = 0; ; i += NumberOfBytesRead )
            {
              v15 = *(_QWORD *)(a1 + 40);
              if ( i >= v15 )
                break;
              v16 = v15 - i;
              NumberOfBytesRead = 0;
              if ( v16 > 0x8000 )
                LODWORD(v16) = 0x8000;
              memset_0(*(void **)(a2 + 176), 0, 0x8000u);
              if ( !ReadFile((HANDLE)FileW, *(LPVOID *)(a2 + 176), v16, &NumberOfBytesRead, 0) )
                goto LABEL_11;
              v17 = BCryptHashData(*v11, *(PUCHAR *)(a2 + 176), NumberOfBytesRead, 0);
              LastWin32Error = v17 | 0x10000000;
              if ( v17 < 0 )
                goto LABEL_24;
            }
            v18 = BCryptFinishHash(
                    *v11,
                    (PUCHAR)(*(_QWORD *)(a2 + 184)
                           + *(_DWORD *)(a2 + 160) * (unsigned int)*(unsigned __int16 *)(a2 + 120)),
                    *(_DWORD *)(a2 + 160),
                    0);
            LastWin32Error = v18;
            if ( v18 > 0 )
              LastWin32Error = (unsigned __int16)v18 | 0x80070000;
            if ( LastWin32Error >= 0 )
            {
              LOBYTE(v19) = v24;
              LastWin32Error = CopyPath(a1, a2, 0, v19, 0);
              if ( LastWin32Error >= 0 )
                *(_QWORD *)(*(_QWORD *)(a2 + 144) + 8LL * (unsigned __int16)(*(_WORD *)(a2 + 120))++) = *(_QWORD *)(a1 + 40);
            }
          }
        }
      }
    }
    else
    {
      LastWin32Error = 0;
      v11 = (BCRYPT_HASH_HANDLE *)(a2 + 168);
      ++*(_WORD *)(a2 + 80);
    }
LABEL_24:
    if ( (char *)*v11 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      BCryptDestroyHash(*v11);
      *v11 = 0;
    }
    if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      NtClose((HANDLE)FileW);
    if ( lpFileName[1] )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 8u, (LPVOID)lpFileName[1]);
    }
    return (unsigned int)LastWin32Error;
  }
}

```

## disassembly

```asm
0x18001b160  mov     [rsp-28h+arg_0], rbx
0x18001b165  mov     [rsp-28h+arg_8], rsi
0x18001b16a  mov     [rsp-28h+arg_18], r9b
0x18001b16f  push    rbp
0x18001b170  push    rdi
0x18001b171  push    r12
0x18001b173  push    r13
0x18001b175  push    r15
0x18001b177  mov     rbp, rsp
0x18001b17a  sub     rsp, 60h
0x18001b17e  movzx   eax, r9b
0x18001b182  xorps   xmm0, xmm0
0x18001b185  xorps   xmm1, xmm1
0x18001b188  mov     rdi, rdx
0x18001b18b  mov     r15, rcx
0x18001b18e  movups  xmmword ptr [rbp+lpFileName], xmm0
0x18001b192  movups  xmmword ptr [rbp+var_20.Length], xmm1
0x18001b196  cmp     r8d, 10h
0x18001b19a  jnz     short loc_18001B1AB
0x18001b19c  mov     rcx, rdx; struct DIRECTORY_SCAN_FUNC_ARGS *
0x18001b19f  call    ?WriteInstallersHashBuffer@@YAXPEAUDIRECTORY_SCAN_FUNC_ARGS@@@Z; WriteInstallersHashBuffer(DIRECTORY_SCAN_FUNC_ARGS *)
0x18001b1a4  xor     eax, eax
0x18001b1a6  jmp     loc_18001B405
0x18001b1ab  mov     r8d, [r15+3Ch]
0x18001b1af  add     rax, rax
0x18001b1b2  movzx   edx, word ptr [rdx+82h]
0x18001b1b9  add     r8d, 6
0x18001b1bd  or      r13, 0FFFFFFFFFFFFFFFFh
0x18001b1c1  movzx   ecx, word ptr [rdi+rax*8+28h]
0x18001b1c6  add     r8d, ecx
0x18001b1c9  cmp     r8d, edx
0x18001b1cc  jbe     short loc_18001B1E0
0x18001b1ce  xor     esi, esi
0x18001b1d0  lea     rbx, [rdi+0A8h]
0x18001b1d7  inc     word ptr [rdi+50h]
0x18001b1db  jmp     loc_18001B3B7
0x18001b1e0  mov     eax, 3E8h
0x18001b1e5  cmp     [rdi+78h], ax
0x18001b1e9  jnb     short loc_18001B1F9
0x18001b1eb  movzx   eax, word ptr [rdi+80h]
0x18001b1f2  add     eax, r8d
0x18001b1f5  cmp     eax, edx
0x18001b1f7  jbe     short loc_18001B201
0x18001b1f9  mov     rcx, rdi; struct DIRECTORY_SCAN_FUNC_ARGS *
0x18001b1fc  call    ?WriteInstallersHashBuffer@@YAXPEAUDIRECTORY_SCAN_FUNC_ARGS@@@Z; WriteInstallersHashBuffer(DIRECTORY_SCAN_FUNC_ARGS *)
0x18001b201  mov     rcx, [rdi+98h]; hAlgorithm
0x18001b208  lea     rbx, [rdi+0A8h]
0x18001b20f  mov     [rsp+60h+dwFlags], 20h ; ' '; dwFlags
0x18001b217  mov     rdx, rbx; phHash
0x18001b21a  mov     [rsp+60h+cbSecret], 0; cbSecret
0x18001b222  xor     r9d, r9d; cbHashObject
0x18001b225  xor     r8d, r8d; pbHashObject
0x18001b228  mov     [rsp+60h+pbSecret], 0; pbSecret
0x18001b231  call    cs:__imp_BCryptCreateHash
0x18001b237  mov     esi, eax
0x18001b239  or      esi, 10000000h
0x18001b23f  jl      loc_18001B3B7
0x18001b245  lea     rax, [r15+58h]
0x18001b249  mov     r12d, 2
0x18001b24f  mov     [rbp+var_20.Buffer], rax
0x18001b253  lea     rcx, [rdi+18h]; struct _UNICODE_STRING *
0x18001b257  movzx   eax, word ptr [r15+3Ch]
0x18001b25c  lea     r9, [rbp+lpFileName]; struct _UNICODE_STRING *
0x18001b260  mov     [rbp+var_20.Length], ax
0x18001b264  lea     rdx, [rbp+var_20]; struct _UNICODE_STRING *
0x18001b268  add     ax, r12w
0x18001b26c  mov     [rbp+var_20.MaximumLength], ax
0x18001b270  call    ?CombinePathParts@@YAJPEAU_UNICODE_STRING@@0G0@Z; CombinePathParts(_UNICODE_STRING *,_UNICODE_STRING *,ushort,_UNICODE_STRING *)
0x18001b275  mov     esi, eax
0x18001b277  test    eax, eax
0x18001b279  js      loc_18001B3B7
0x18001b27f  mov     rcx, [rbp+lpFileName+8]; lpFileName
0x18001b283  xor     r9d, r9d; lpSecurityAttributes
0x18001b286  mov     qword ptr [rsp+60h+dwFlags], 0; hTemplateFile
0x18001b28f  mov     r8d, r12d; dwShareMode
0x18001b292  mov     [rsp+60h+cbSecret], 8000080h; dwFlagsAndAttributes
0x18001b29a  mov     edx, 80000000h; dwDesiredAccess
0x18001b29f  mov     dword ptr [rsp+60h+pbSecret], 3; dwCreationDisposition
0x18001b2a7  call    cs:__imp_CreateFileW
0x18001b2ad  mov     r13, rax
0x18001b2b0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001b2b4  jnz     short loc_18001B2C2
0x18001b2b6  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x18001b2bb  mov     esi, eax
0x18001b2bd  jmp     loc_18001B3B7
0x18001b2c2  xor     r12d, r12d
0x18001b2c5  mov     rsi, [r15+28h]
0x18001b2c9  cmp     r12, rsi
0x18001b2cc  jge     short loc_18001B34A
0x18001b2ce  sub     rsi, r12
0x18001b2d1  mov     [rbp+NumberOfBytesRead], 0
0x18001b2d8  cmp     rsi, 8000h
0x18001b2df  jle     short loc_18001B2E6
0x18001b2e1  mov     esi, 8000h
0x18001b2e6  mov     rcx, [rdi+0B0h]; void *
0x18001b2ed  xor     edx, edx; Val
0x18001b2ef  mov     r8d, 8000h; Size
0x18001b2f5  call    memset_0
0x18001b2fa  mov     rdx, [rdi+0B0h]; lpBuffer
0x18001b301  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x18001b305  mov     r8d, esi; nNumberOfBytesToRead
0x18001b308  mov     [rsp+60h+pbSecret], 0; lpOverlapped
0x18001b311  mov     rcx, r13; hFile
0x18001b314  call    cs:__imp_ReadFile
0x18001b31a  test    eax, eax
0x18001b31c  jz      short loc_18001B2B6
0x18001b31e  mov     r8d, [rbp+NumberOfBytesRead]; cbInput
0x18001b322  xor     r9d, r9d; dwFlags
0x18001b325  mov     rdx, [rdi+0B0h]; pbInput
0x18001b32c  mov     rcx, [rbx]; hHash
0x18001b32f  call    cs:__imp_BCryptHashData
0x18001b335  mov     esi, eax
0x18001b337  or      esi, 10000000h
0x18001b33d  jl      short loc_18001B3B7
0x18001b33f  mov     eax, [rbp+NumberOfBytesRead]
0x18001b342  add     r12, rax
0x18001b345  jmp     loc_18001B2C5
0x18001b34a  movzx   edx, word ptr [rdi+78h]
0x18001b34e  xor     r9d, r9d; dwFlags
0x18001b351  mov     r8d, [rdi+0A0h]; cbOutput
0x18001b358  mov     rcx, [rbx]; hHash
0x18001b35b  imul    edx, r8d
0x18001b35f  add     rdx, [rdi+0B8h]; pbOutput
0x18001b366  call    cs:__imp_BCryptFinishHash
0x18001b36c  mov     esi, eax
0x18001b36e  test    eax, eax
0x18001b370  jle     short loc_18001B37B
0x18001b372  movzx   esi, ax
0x18001b375  or      esi, 80070000h
0x18001b37b  test    esi, esi
0x18001b37d  js      short loc_18001B3B7
0x18001b37f  mov     r9b, [rbp+arg_18]
0x18001b383  xor     r8d, r8d
0x18001b386  mov     rdx, rdi
0x18001b389  mov     [rsp+60h+pbSecret], 0
0x18001b392  mov     rcx, r15
0x18001b395  call    ?CopyPath@@YAJPEAU_FILE_ID_EXTD_DIR_INFORMATION@@PEAUDIRECTORY_SCAN_FUNC_ARGS@@W4PATH_TYPE@@_NPEBG@Z; CopyPath(_FILE_ID_EXTD_DIR_INFORMATION *,DIRECTORY_SCAN_FUNC_ARGS *,PATH_TYPE,bool,ushort const *)
0x18001b39a  mov     esi, eax
0x18001b39c  test    eax, eax
0x18001b39e  js      short loc_18001B3B7
0x18001b3a0  movzx   edx, word ptr [rdi+78h]
0x18001b3a4  mov     rax, [r15+28h]
0x18001b3a8  mov     rcx, [rdi+90h]
0x18001b3af  mov     [rcx+rdx*8], rax
0x18001b3b3  inc     word ptr [rdi+78h]
0x18001b3b7  mov     rcx, [rbx]; hHash
0x18001b3ba  lea     rax, [rcx-1]
0x18001b3be  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001b3c2  ja      short loc_18001B3D1
0x18001b3c4  call    cs:__imp_BCryptDestroyHash
0x18001b3ca  mov     qword ptr [rbx], 0
0x18001b3d1  lea     rax, [r13-1]
0x18001b3d5  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001b3d9  ja      short loc_18001B3E4
0x18001b3db  mov     rcx, r13; Handle
0x18001b3de  call    cs:__imp_NtClose
0x18001b3e4  cmp     [rbp+lpFileName+8], 0
0x18001b3e9  jz      short loc_18001B403
0x18001b3eb  call    cs:__imp_GetProcessHeap
0x18001b3f1  mov     r8, [rbp+lpFileName+8]; lpMem
0x18001b3f5  mov     edx, 8; dwFlags
0x18001b3fa  mov     rcx, rax; hHeap
0x18001b3fd  call    cs:__imp_HeapFree
0x18001b403  mov     eax, esi
0x18001b405  lea     r11, [rsp+60h+var_s0]
0x18001b40a  mov     rbx, [r11+30h]
0x18001b40e  mov     rsi, [r11+38h]
0x18001b412  mov     rsp, r11
0x18001b415  pop     r15
0x18001b417  pop     r13
0x18001b419  pop     r12
0x18001b41b  pop     rdi
0x18001b41c  pop     rbp
0x18001b41d  retn
```
