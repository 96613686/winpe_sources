# CopyStreams

- ea: `0x180019aec`
- end: `0x180019d21`
- name: `CopyStreams`
- size: `565`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001a1c8`

## callees

- `0x18000214c`
- `0x1800024a6`
- `0x1800197b0`
- `0x180019aec`
- `0x18001b0cc`
- `0x18001dbe0`
- `0x18001dc30`
- `0x180030362`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180019bbb`
- `msvcrt!??3@YAXPEAX@Z` at `0x180019cb3`
- `msvcrt!??3@YAXPEAX@Z` at `0x180019ce6`
- `msvcrt!??3@YAXPEAX@Z` at `0x180019bbb`
- `msvcrt!??3@YAXPEAX@Z` at `0x180019cb3`
- `msvcrt!??3@YAXPEAX@Z` at `0x180019ce6`
- `KERNEL32!CreateFileW` at `0x180019b5f`
- `KERNEL32!CreateFileW` at `0x180019b5f`
- `KERNEL32!GetLastError` at `0x180019b74`
- `KERNEL32!GetLastError` at `0x180019b74`
- `KERNEL32!CloseHandle` at `0x180019cd2`
- `KERNEL32!CloseHandle` at `0x180019cd2`
- `ntdll!NtQueryInformationFile` at `0x180019c14`
- `ntdll!NtQueryInformationFile` at `0x180019c14`

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
0x180019aec  mov     rax, rsp
0x180019aef  mov     [rax+8], rbx
0x180019af3  mov     [rax+10h], rbp
0x180019af7  mov     [rax+18h], rsi
0x180019afb  push    rdi
0x180019afc  push    r12
0x180019afe  push    r13
0x180019b00  push    r14
0x180019b02  push    r15
0x180019b04  sub     rsp, 50h
0x180019b08  xor     ebp, ebp
0x180019b0a  mov     r12, rcx
0x180019b0d  xorps   xmm0, xmm0
0x180019b10  mov     r13, rdx
0x180019b13  movups  xmmword ptr [rax-38h], xmm0
0x180019b17  mov     edi, ebp
0x180019b19  lea     esi, [rbp+1]
0x180019b1c  mov     ecx, esi
0x180019b1e  call    WdsModifyRestorePrivilege
0x180019b23  mov     ebx, eax
0x180019b25  test    eax, eax
0x180019b27  js      loc_180019CF2
0x180019b2d  mov     ecx, esi
0x180019b2f  call    WdsModifySecurityPrivilege
0x180019b34  mov     ebx, eax
0x180019b36  test    eax, eax
0x180019b38  js      loc_180019CF2
0x180019b3e  mov     [rsp+78h+hTemplateFile], rbp; hTemplateFile
0x180019b43  lea     r8d, [rbp+3]; dwShareMode
0x180019b47  mov     [rsp+78h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x180019b4f  xor     r9d, r9d; lpSecurityAttributes
0x180019b52  mov     edx, 80000000h; dwDesiredAccess
0x180019b57  mov     [rsp+78h+dwCreationDisposition], r8d; dwCreationDisposition
0x180019b5c  mov     rcx, r12; lpFileName
0x180019b5f  call    cs:__imp_CreateFileW
0x180019b66  nop     dword ptr [rax+rax+00h]
0x180019b6b  mov     r15, rax
0x180019b6e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180019b72  jnz     short loc_180019BAE
0x180019b74  call    cs:__imp_GetLastError
0x180019b7b  nop     dword ptr [rax+rax+00h]
0x180019b80  mov     ecx, eax
0x180019b82  mov     r9d, 26Bh
0x180019b88  call    ElValidateWin32_8
0x180019b8d  mov     ebx, eax
0x180019b8f  test    eax, eax
0x180019b91  jle     short loc_180019B9C
0x180019b93  movzx   ebx, ax
0x180019b96  or      ebx, 80070000h
0x180019b9c  test    ebx, ebx
0x180019b9e  js      loc_180019CF2
0x180019ba4  mov     ebx, 80004005h
0x180019ba9  jmp     loc_180019CF2
0x180019bae  mov     esi, 450h
0x180019bb3  test    rdi, rdi
0x180019bb6  jz      short loc_180019BCA
0x180019bb8  mov     rcx, rdi
0x180019bbb  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180019bc2  nop     dword ptr [rax+rax+00h]
0x180019bc7  mov     rdi, rbp
0x180019bca  lea     eax, [rsi+rsi]
0x180019bcd  cmp     eax, esi
0x180019bcf  jb      loc_180019CCA
0x180019bd5  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180019bdc  mov     ecx, eax; unsigned __int64
0x180019bde  mov     esi, eax
0x180019be0  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180019be5  mov     rdi, rax
0x180019be8  test    rax, rax
0x180019beb  jz      loc_180019CC1
0x180019bf1  mov     r8d, esi; Size
0x180019bf4  xor     edx, edx; Val
0x180019bf6  mov     rcx, rax; void *
0x180019bf9  call    memset_0
0x180019bfe  mov     r9d, esi; Length
0x180019c01  mov     [rsp+78h+dwCreationDisposition], 16h; FileInformationClass
0x180019c09  mov     r8, rdi; FileInformation
0x180019c0c  lea     rdx, [rsp+78h+IoStatusBlock]; IoStatusBlock
0x180019c11  mov     rcx, r15; FileHandle
0x180019c14  call    cs:__imp_NtQueryInformationFile
0x180019c1b  nop     dword ptr [rax+rax+00h]
0x180019c20  mov     ebp, 0
0x180019c25  cmp     eax, 80000005h
0x180019c2a  jz      short loc_180019BB3
0x180019c2c  test    eax, eax
0x180019c2e  jns     short loc_180019C3B
0x180019c30  mov     ebx, eax
0x180019c32  bts     ebx, 1Ch
0x180019c36  jmp     loc_180019CCF
0x180019c3b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180019c42  mov     ecx, 20Ah; unsigned __int64
0x180019c47  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180019c4c  mov     r14, rax
0x180019c4f  test    rax, rax
0x180019c52  jnz     short loc_180019C5B
0x180019c54  mov     ebx, 8007000Eh
0x180019c59  jmp     short loc_180019CCF
0x180019c5b  mov     rsi, rdi
0x180019c5e  cmp     [rdi+4], ebp
0x180019c61  jz      short loc_180019CB0
0x180019c63  movzx   eax, word ptr [rdi+1Ah]
0x180019c67  cmp     [rdi+18h], ax
0x180019c6b  jnz     short loc_180019C76
0x180019c6d  cmp     [rdi], ebp
0x180019c6f  jz      short loc_180019CB0
0x180019c71  mov     esi, [rdi]
0x180019c73  add     rsi, rdi
0x180019c76  mov     r8d, [rsi+4]; Size
0x180019c7a  lea     rdx, [rsi+18h]; Src
0x180019c7e  mov     rcx, r14; void *
0x180019c81  call    memcpy_0
0x180019c86  mov     eax, [rsi+4]
0x180019c89  mov     r8, r14
0x180019c8c  shr     rax, 1
0x180019c8f  mov     rdx, r13
0x180019c92  mov     rcx, r12
0x180019c95  mov     [r14+rax*2], bp
0x180019c9a  call    CopyStream
0x180019c9f  mov     ebx, eax
0x180019ca1  test    eax, eax
0x180019ca3  js      short loc_180019CB0
0x180019ca5  cmp     [rsi], ebp
0x180019ca7  jz      short loc_180019CB0
0x180019ca9  mov     eax, [rsi]
0x180019cab  add     rsi, rax
0x180019cae  jmp     short loc_180019C76
0x180019cb0  mov     rcx, r14
0x180019cb3  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180019cba  nop     dword ptr [rax+rax+00h]
0x180019cbf  jmp     short loc_180019CCF
0x180019cc1  mov     ebx, 8007000Eh
0x180019cc6  xor     ebp, ebp
0x180019cc8  jmp     short loc_180019CCF
0x180019cca  mov     ebx, 80004005h
0x180019ccf  mov     rcx, r15; hObject
0x180019cd2  call    cs:__imp_CloseHandle
0x180019cd9  nop     dword ptr [rax+rax+00h]
0x180019cde  test    rdi, rdi
0x180019ce1  jz      short loc_180019CF2
0x180019ce3  mov     rcx, rdi
0x180019ce6  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180019ced  nop     dword ptr [rax+rax+00h]
0x180019cf2  xor     ecx, ecx
0x180019cf4  call    WdsModifyRestorePrivilege
0x180019cf9  xor     ecx, ecx
0x180019cfb  call    WdsModifySecurityPrivilege
0x180019d00  lea     r11, [rsp+78h+var_28]
0x180019d05  mov     eax, ebx
0x180019d07  mov     rbx, [r11+30h]
0x180019d0b  mov     rbp, [r11+38h]
0x180019d0f  mov     rsi, [r11+40h]
0x180019d13  mov     rsp, r11
0x180019d16  pop     r15
0x180019d18  pop     r14
0x180019d1a  pop     r13
0x180019d1c  pop     r12
0x180019d1e  pop     rdi
0x180019d1f  retn
```
