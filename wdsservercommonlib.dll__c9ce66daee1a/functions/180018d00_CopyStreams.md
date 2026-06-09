# CopyStreams

- ea: `0x180018d00`
- end: `0x180018f20`
- name: `CopyStreams`
- size: `544`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800193b8`

## callees

- `0x18000179c`
- `0x1800189d0`
- `0x180018d00`
- `0x18001a28c`
- `0x18001cc80`
- `0x18001ccd0`
- `0x18002e468`
- `0x18002f3a2`
- `0x18002f3ba`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180018d88`
- `KERNEL32!GetLastError` at `0x180018d88`
- `KERNEL32!CloseHandle` at `0x180018ed8`
- `KERNEL32!CloseHandle` at `0x180018ed8`
- `KERNEL32!CreateFileW` at `0x180018d73`
- `KERNEL32!CreateFileW` at `0x180018d73`
- `ntdll!NtQueryInformationFile` at `0x180018e21`
- `ntdll!NtQueryInformationFile` at `0x180018e21`

## pseudocode

```c
__int64 __fastcall CopyStreams(LPCWSTR lpFileName, __int64 a2)
{
  _DWORD *v4; // rdi
  int v5; // ebx
  HANDLE FileW; // r15
  DWORD LastError; // eax
  __int64 v8; // rdx
  __int64 v9; // r8
  int v10; // eax
  ULONG v11; // esi
  unsigned int v12; // eax
  _DWORD *v13; // rax
  NTSTATUS v14; // eax
  void *v15; // r14
  unsigned int *v16; // rsi
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+40h] [rbp-38h] BYREF

  IoStatusBlock = 0;
  v4 = 0;
  v5 = WdsModifyRestorePrivilege(1);
  if ( v5 >= 0 )
  {
    v5 = WdsModifySecurityPrivilege(1);
    if ( v5 >= 0 )
    {
      FileW = CreateFileW(lpFileName, 0x80000000, 3u, 0, 3u, 0x2000000u, 0);
      if ( FileW == (HANDLE)-1LL )
      {
        LastError = GetLastError();
        v10 = ElValidateWin32_8(LastError, v8, v9, 619);
        v5 = v10;
        if ( v10 > 0 )
          v5 = (unsigned __int16)v10 | 0x80070000;
        if ( v5 >= 0 )
          v5 = -2147467259;
      }
      else
      {
        v11 = 1104;
        while ( 1 )
        {
          if ( v4 )
          {
            operator delete(v4);
            v4 = 0;
          }
          v12 = 2 * v11;
          if ( 2 * v11 < v11 )
            break;
          v11 *= 2;
          v13 = operator new[](v12, (const struct std::nothrow_t *)&std::nothrow);
          v4 = v13;
          if ( !v13 )
          {
            v5 = -2147024882;
            goto LABEL_28;
          }
          memset_0(v13, 0, v11);
          v14 = NtQueryInformationFile(FileW, &IoStatusBlock, v4, v11, FileStreamInformation);
          if ( v14 != -2147483643 )
          {
            if ( v14 < 0 )
            {
              v5 = v14 | 0x10000000;
              goto LABEL_28;
            }
            v15 = operator new[](0x20Au, (const struct std::nothrow_t *)&std::nothrow);
            if ( !v15 )
            {
              v5 = -2147024882;
              goto LABEL_28;
            }
            v16 = v4;
            if ( v4[1] )
            {
              if ( *((_WORD *)v4 + 12) != *((_WORD *)v4 + 13) )
                goto LABEL_22;
              if ( *v4 )
              {
                v16 = (_DWORD *)((char *)v4 + (unsigned int)*v4);
LABEL_22:
                while ( 1 )
                {
                  memcpy_0(v15, v16 + 6, v16[1]);
                  *((_WORD *)v15 + ((unsigned __int64)v16[1] >> 1)) = 0;
                  v5 = CopyStream((__int64)lpFileName, a2, (__int64)v15);
                  if ( v5 < 0 || !*v16 )
                    break;
                  v16 = (unsigned int *)((char *)v16 + *v16);
                }
              }
            }
            operator delete(v15);
            goto LABEL_28;
          }
        }
        v5 = -2147467259;
LABEL_28:
        CloseHandle(FileW);
        if ( v4 )
          operator delete(v4);
      }
    }
  }
  WdsModifyRestorePrivilege(0);
  WdsModifySecurityPrivilege(0);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180018d00  mov     rax, rsp
0x180018d03  mov     [rax+8], rbx
0x180018d07  mov     [rax+10h], rbp
0x180018d0b  mov     [rax+18h], rsi
0x180018d0f  push    rdi
0x180018d10  push    r12
0x180018d12  push    r13
0x180018d14  push    r14
0x180018d16  push    r15
0x180018d18  sub     rsp, 50h
0x180018d1c  xor     ebp, ebp
0x180018d1e  mov     r12, rcx
0x180018d21  xorps   xmm0, xmm0
0x180018d24  mov     r13, rdx
0x180018d27  movups  xmmword ptr [rax-38h], xmm0
0x180018d2b  mov     edi, ebp
0x180018d2d  lea     esi, [rbp+1]
0x180018d30  mov     ecx, esi
0x180018d32  call    WdsModifyRestorePrivilege
0x180018d37  mov     ebx, eax
0x180018d39  test    eax, eax
0x180018d3b  js      loc_180018EF1
0x180018d41  mov     ecx, esi
0x180018d43  call    WdsModifySecurityPrivilege
0x180018d48  mov     ebx, eax
0x180018d4a  test    eax, eax
0x180018d4c  js      loc_180018EF1
0x180018d52  mov     [rsp+78h+hTemplateFile], rbp; hTemplateFile
0x180018d57  lea     r8d, [rbp+3]; dwShareMode
0x180018d5b  mov     [rsp+78h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x180018d63  xor     r9d, r9d; lpSecurityAttributes
0x180018d66  mov     edx, 80000000h; dwDesiredAccess
0x180018d6b  mov     [rsp+78h+dwCreationDisposition], r8d; dwCreationDisposition
0x180018d70  mov     rcx, r12; lpFileName
0x180018d73  call    cs:__imp_CreateFileW
0x180018d7a  nop     dword ptr [rax+rax+00h]
0x180018d7f  mov     r15, rax
0x180018d82  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180018d86  jnz     short loc_180018DC2
0x180018d88  call    cs:__imp_GetLastError
0x180018d8f  nop     dword ptr [rax+rax+00h]
0x180018d94  mov     ecx, eax
0x180018d96  mov     r9d, 26Bh
0x180018d9c  call    ElValidateWin32_8
0x180018da1  mov     ebx, eax
0x180018da3  test    eax, eax
0x180018da5  jle     short loc_180018DB0
0x180018da7  movzx   ebx, ax
0x180018daa  or      ebx, 80070000h
0x180018db0  test    ebx, ebx
0x180018db2  js      loc_180018EF1
0x180018db8  mov     ebx, 80004005h
0x180018dbd  jmp     loc_180018EF1
0x180018dc2  mov     esi, 450h
0x180018dc7  test    rdi, rdi
0x180018dca  jz      short loc_180018DD7
0x180018dcc  mov     rcx, rdi; lpMem
0x180018dcf  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180018dd4  mov     rdi, rbp
0x180018dd7  lea     eax, [rsi+rsi]
0x180018dda  cmp     eax, esi
0x180018ddc  jb      loc_180018ED0
0x180018de2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180018de9  mov     ecx, eax; unsigned __int64
0x180018deb  mov     esi, eax
0x180018ded  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180018df2  mov     rdi, rax
0x180018df5  test    rax, rax
0x180018df8  jz      loc_180018EC7
0x180018dfe  mov     r8d, esi; Size
0x180018e01  xor     edx, edx; Val
0x180018e03  mov     rcx, rax; void *
0x180018e06  call    memset_0
0x180018e0b  mov     r9d, esi; Length
0x180018e0e  mov     [rsp+78h+dwCreationDisposition], 16h; FileInformationClass
0x180018e16  mov     r8, rdi; FileInformation
0x180018e19  lea     rdx, [rsp+78h+IoStatusBlock]; IoStatusBlock
0x180018e1e  mov     rcx, r15; FileHandle
0x180018e21  call    cs:__imp_NtQueryInformationFile
0x180018e28  nop     dword ptr [rax+rax+00h]
0x180018e2d  mov     ebp, 0
0x180018e32  cmp     eax, 80000005h
0x180018e37  jz      short loc_180018DC7
0x180018e39  test    eax, eax
0x180018e3b  jns     short loc_180018E48
0x180018e3d  mov     ebx, eax
0x180018e3f  bts     ebx, 1Ch
0x180018e43  jmp     loc_180018ED5
0x180018e48  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180018e4f  mov     ecx, 20Ah; unsigned __int64
0x180018e54  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180018e59  mov     r14, rax
0x180018e5c  test    rax, rax
0x180018e5f  jnz     short loc_180018E68
0x180018e61  mov     ebx, 8007000Eh
0x180018e66  jmp     short loc_180018ED5
0x180018e68  mov     rsi, rdi
0x180018e6b  cmp     [rdi+4], ebp
0x180018e6e  jz      short loc_180018EBD
0x180018e70  movzx   eax, word ptr [rdi+1Ah]
0x180018e74  cmp     [rdi+18h], ax
0x180018e78  jnz     short loc_180018E83
0x180018e7a  cmp     [rdi], ebp
0x180018e7c  jz      short loc_180018EBD
0x180018e7e  mov     esi, [rdi]
0x180018e80  add     rsi, rdi
0x180018e83  mov     r8d, [rsi+4]; Size
0x180018e87  lea     rdx, [rsi+18h]; Src
0x180018e8b  mov     rcx, r14; void *
0x180018e8e  call    memcpy_0
0x180018e93  mov     eax, [rsi+4]
0x180018e96  mov     r8, r14
0x180018e99  shr     rax, 1
0x180018e9c  mov     rdx, r13
0x180018e9f  mov     rcx, r12
0x180018ea2  mov     [r14+rax*2], bp
0x180018ea7  call    CopyStream
0x180018eac  mov     ebx, eax
0x180018eae  test    eax, eax
0x180018eb0  js      short loc_180018EBD
0x180018eb2  cmp     [rsi], ebp
0x180018eb4  jz      short loc_180018EBD
0x180018eb6  mov     eax, [rsi]
0x180018eb8  add     rsi, rax
0x180018ebb  jmp     short loc_180018E83
0x180018ebd  mov     rcx, r14; lpMem
0x180018ec0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180018ec5  jmp     short loc_180018ED5
0x180018ec7  mov     ebx, 8007000Eh
0x180018ecc  xor     ebp, ebp
0x180018ece  jmp     short loc_180018ED5
0x180018ed0  mov     ebx, 80004005h
0x180018ed5  mov     rcx, r15; hObject
0x180018ed8  call    cs:__imp_CloseHandle
0x180018edf  nop     dword ptr [rax+rax+00h]
0x180018ee4  test    rdi, rdi
0x180018ee7  jz      short loc_180018EF1
0x180018ee9  mov     rcx, rdi; lpMem
0x180018eec  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180018ef1  xor     ecx, ecx
0x180018ef3  call    WdsModifyRestorePrivilege
0x180018ef8  xor     ecx, ecx
0x180018efa  call    WdsModifySecurityPrivilege
0x180018eff  lea     r11, [rsp+78h+var_28]
0x180018f04  mov     eax, ebx
0x180018f06  mov     rbx, [r11+30h]
0x180018f0a  mov     rbp, [r11+38h]
0x180018f0e  mov     rsi, [r11+40h]
0x180018f12  mov     rsp, r11
0x180018f15  pop     r15
0x180018f17  pop     r14
0x180018f19  pop     r13
0x180018f1b  pop     r12
0x180018f1d  pop     rdi
0x180018f1e  retn
```
