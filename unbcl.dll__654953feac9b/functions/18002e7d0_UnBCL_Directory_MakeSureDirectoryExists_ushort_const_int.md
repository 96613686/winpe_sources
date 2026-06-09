# UnBCL::Directory::MakeSureDirectoryExists(ushort const *,int *)

- ea: `0x18002e7d0`
- end: `0x18002e9e1`
- name: `?MakeSureDirectoryExists@Directory@UnBCL@@SAKPEBGPEAH@Z`
- size: `529`
- prototype: `unsigned int __fastcall(const unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18002d0e0`

## callees

- `0x18002e7d0`
- `0x180068fe6`

## import_xrefs

- `msvcrt!wcschr` at `0x18002e93e`
- `msvcrt!wcschr` at `0x18002e958`
- `msvcrt!wcschr` at `0x18002e93e`
- `msvcrt!wcschr` at `0x18002e958`
- `KERNEL32!GetLastError` at `0x18002e84e`
- `KERNEL32!GetLastError` at `0x18002e84e`
- `KERNEL32!LocalFree` at `0x18002e9bf`
- `KERNEL32!LocalFree` at `0x18002e9bf`
- `KERNEL32!CreateDirectoryW` at `0x18002e97d`
- `KERNEL32!CreateDirectoryW` at `0x18002e97d`
- `KERNEL32!LocalAlloc` at `0x18002e86b`
- `KERNEL32!LocalAlloc` at `0x18002e86b`
- `KERNEL32!GetFileAttributesW` at `0x18002e96d`
- `KERNEL32!GetFileAttributesW` at `0x18002e96d`

## pseudocode

```c
__int64 __fastcall UnBCL::Directory::MakeSureDirectoryExists(const unsigned __int16 *a1, int *a2)
{
  const unsigned __int16 *v3; // r14
  int v4; // r12d
  int i; // esi
  __int64 v6; // r8
  const unsigned __int16 *v7; // rax
  DWORD LastError; // edi
  unsigned int v9; // edx
  __int64 v10; // rbp
  _WORD *v11; // rbx
  _WORD *v12; // rax
  unsigned __int64 v13; // rdx
  __int64 v14; // rax
  _WORD *v15; // r8
  _WORD *v16; // rcx
  const wchar_t *v17; // rcx
  wchar_t *v18; // rax
  wchar_t *v19; // rsi
  wchar_t *v20; // rax
  DWORD FileAttributesW; // eax

  v3 = a1;
  v4 = 0;
  if ( !a1 )
  {
    LOWORD(v9) = 87;
    v11 = 0;
    goto LABEL_38;
  }
  i = 2;
  v6 = 0x7FFFFFFF;
  v7 = a1;
  do
  {
    if ( !*v7 )
      break;
    ++v7;
    --v6;
  }
  while ( v6 );
  LOWORD(LastError) = 87;
  v9 = v6 == 0 ? 0x80070057 : 0;
  v10 = (0x7FFFFFFF - v6) & -(__int64)(v6 != 0);
  if ( !v6 )
  {
    v11 = 0;
LABEL_38:
    LastError = (unsigned __int16)v9;
    goto LABEL_39;
  }
  v12 = LocalAlloc(0x40u, 2 * v10 + 2);
  v11 = v12;
  if ( !v12 )
  {
LABEL_7:
    LastError = GetLastError();
    goto LABEL_39;
  }
  memset_0(v12, 0, 2 * v10 + 2);
  v13 = v10 + 1;
  if ( v10 == -1 )
  {
LABEL_36:
    LastError = (unsigned __int16)LastError;
    goto LABEL_39;
  }
  if ( v13 > 0x7FFFFFFF )
  {
    *v11 = 0;
    goto LABEL_36;
  }
  v14 = 2147483646;
  v15 = v11;
  do
  {
    if ( !v14 )
      break;
    if ( !*v3 )
      break;
    *v15++ = *v3++;
    --v14;
    --v13;
  }
  while ( v13 );
  v16 = v15 - 1;
  LastError = v13 == 0 ? 0x8007007A : 0;
  if ( v13 )
    v16 = v15;
  *v16 = 0;
  if ( !v13 )
    goto LABEL_36;
  LastError = 0;
  v17 = v11;
  if ( *v11 == 92 && v11[1] == 92 )
  {
    if ( v11[2] == 63 )
    {
      for ( i = 3; v11[i] == 92; ++i )
        ;
    }
    v17 = &v11[i];
  }
  v18 = wcschr(v17, 0x5Cu);
  v19 = v18;
  if ( v18 && *v18 )
  {
    while ( 1 )
    {
      v20 = wcschr(v19 + 1, 0x5Cu);
      v19 = v20;
      if ( v20 )
        *v20 = 0;
      FileAttributesW = GetFileAttributesW(v11);
      if ( FileAttributesW == -1 )
      {
        if ( !CreateDirectoryW(v11, 0) )
          goto LABEL_7;
        v4 = 1;
      }
      else if ( (FileAttributesW & 0x10) == 0 )
      {
        LastError = 85;
        break;
      }
      if ( !v19 )
        break;
      *v19 = 92;
    }
  }
LABEL_39:
  LocalFree(v11);
  if ( a2 )
    *a2 = v4;
  return LastError;
}

```

## disassembly

```asm
0x18002e7d0  push    rbx
0x18002e7d2  push    rbp
0x18002e7d3  push    rsi
0x18002e7d4  push    rdi
0x18002e7d5  push    r12
0x18002e7d7  push    r13
0x18002e7d9  push    r14
0x18002e7db  push    r15
0x18002e7dd  sub     rsp, 28h
0x18002e7e1  xor     r15d, r15d
0x18002e7e4  mov     r13, rdx
0x18002e7e7  mov     r14, rcx
0x18002e7ea  mov     r12d, r15d
0x18002e7ed  test    rcx, rcx
0x18002e7f0  jz      loc_18002E9B1
0x18002e7f6  mov     ecx, 7FFFFFFFh
0x18002e7fb  lea     esi, [r15+2]
0x18002e7ff  mov     r8d, ecx
0x18002e802  mov     rax, r14
0x18002e805  cmp     [rax], r15w
0x18002e809  jz      short loc_18002E814
0x18002e80b  add     rax, rsi
0x18002e80e  sub     r8, 1
0x18002e812  jnz     short loc_18002E805
0x18002e814  mov     rax, r8
0x18002e817  mov     edi, 80070057h
0x18002e81c  neg     rax
0x18002e81f  mov     rax, r8
0x18002e822  sbb     edx, edx
0x18002e824  sub     rcx, r8
0x18002e827  not     edx
0x18002e829  and     edx, edi
0x18002e82b  neg     rax
0x18002e82e  sbb     rbp, rbp
0x18002e831  and     rbp, rcx
0x18002e834  test    r8, r8
0x18002e837  jnz     short loc_18002E85B
0x18002e839  mov     eax, edx
0x18002e83b  mov     rbx, r15
0x18002e83e  and     eax, 0FFFF0000h
0x18002e843  cmp     eax, 80070000h
0x18002e848  jz      loc_18002E9B9
0x18002e84e  call    cs:__imp_GetLastError
0x18002e854  mov     edi, eax
0x18002e856  jmp     loc_18002E9BC
0x18002e85b  lea     r15, ds:2[rbp*2]
0x18002e863  mov     ecx, 40h ; '@'; uFlags
0x18002e868  mov     rdx, r15; uBytes
0x18002e86b  call    cs:__imp_LocalAlloc
0x18002e871  mov     rbx, rax
0x18002e874  test    rax, rax
0x18002e877  jz      short loc_18002E84E
0x18002e879  mov     r8, r15; Size
0x18002e87c  xor     edx, edx; Val
0x18002e87e  mov     rcx, rax; void *
0x18002e881  call    memset_0
0x18002e886  lea     rdx, [rbp+1]
0x18002e88a  xor     r15d, r15d
0x18002e88d  test    rdx, rdx
0x18002e890  jz      loc_18002E9AC
0x18002e896  cmp     rdx, 7FFFFFFFh
0x18002e89d  ja      loc_18002E9A8
0x18002e8a3  mov     eax, 7FFFFFFEh
0x18002e8a8  mov     r8, rbx
0x18002e8ab  test    rax, rax
0x18002e8ae  jz      short loc_18002E8CC
0x18002e8b0  movzx   ecx, word ptr [r14]
0x18002e8b4  test    cx, cx
0x18002e8b7  jz      short loc_18002E8CC
0x18002e8b9  mov     [r8], cx
0x18002e8bd  add     r14, rsi
0x18002e8c0  add     r8, rsi
0x18002e8c3  dec     rax
0x18002e8c6  sub     rdx, 1
0x18002e8ca  jnz     short loc_18002E8AB
0x18002e8cc  mov     rax, rdx
0x18002e8cf  lea     rcx, [r8-2]
0x18002e8d3  neg     rax
0x18002e8d6  sbb     edi, edi
0x18002e8d8  not     edi
0x18002e8da  and     edi, 8007007Ah
0x18002e8e0  test    rdx, rdx
0x18002e8e3  cmovnz  rcx, r8
0x18002e8e7  mov     [rcx], r15w
0x18002e8eb  jnz     short loc_18002E904
0x18002e8ed  mov     eax, edi
0x18002e8ef  and     eax, 0FFFF0000h
0x18002e8f4  cmp     eax, 80070000h
0x18002e8f9  jz      loc_18002E9AC
0x18002e8ff  jmp     loc_18002E84E
0x18002e904  mov     ebp, 5Ch ; '\'
0x18002e909  mov     edi, r15d
0x18002e90c  mov     rcx, rbx
0x18002e90f  cmp     [rbx], bp
0x18002e912  jnz     short loc_18002E93C
0x18002e914  cmp     [rbx+2], bp
0x18002e918  jnz     short loc_18002E93C
0x18002e91a  cmp     word ptr [rbx+4], 3Fh ; '?'
0x18002e91f  jnz     short loc_18002E935
0x18002e921  lea     esi, [rbp-59h]
0x18002e924  cmp     [rbx+6], bp
0x18002e928  jnz     short loc_18002E935
0x18002e92a  inc     esi
0x18002e92c  movsxd  rax, esi
0x18002e92f  cmp     [rbx+rax*2], bp
0x18002e933  jz      short loc_18002E92A
0x18002e935  movsxd  rax, esi
0x18002e938  lea     rcx, [rbx+rax*2]; Str
0x18002e93c  mov     edx, ebp; Ch
0x18002e93e  call    cs:__imp_wcschr
0x18002e944  mov     rsi, rax
0x18002e947  test    rax, rax
0x18002e94a  jz      short loc_18002E9BC
0x18002e94c  cmp     [rax], r15w
0x18002e950  jz      short loc_18002E9BC
0x18002e952  mov     edx, ebp; Ch
0x18002e954  lea     rcx, [rsi+2]; Str
0x18002e958  call    cs:__imp_wcschr
0x18002e95e  mov     rsi, rax
0x18002e961  test    rax, rax
0x18002e964  jz      short loc_18002E96A
0x18002e966  mov     [rax], r15w
0x18002e96a  mov     rcx, rbx; lpFileName
0x18002e96d  call    cs:__imp_GetFileAttributesW
0x18002e973  cmp     eax, 0FFFFFFFFh
0x18002e976  jnz     short loc_18002E993
0x18002e978  xor     edx, edx; lpSecurityAttributes
0x18002e97a  mov     rcx, rbx; lpPathName
0x18002e97d  call    cs:__imp_CreateDirectoryW
0x18002e983  test    eax, eax
0x18002e985  jz      loc_18002E84E
0x18002e98b  mov     r12d, 1
0x18002e991  jmp     short loc_18002E997
0x18002e993  test    al, 10h
0x18002e995  jz      short loc_18002E9A1
0x18002e997  test    rsi, rsi
0x18002e99a  jz      short loc_18002E9BC
0x18002e99c  mov     [rsi], bp
0x18002e99f  jmp     short loc_18002E952
0x18002e9a1  mov     edi, 55h ; 'U'
0x18002e9a6  jmp     short loc_18002E9BC
0x18002e9a8  mov     [rbx], r15w
0x18002e9ac  movzx   edi, di
0x18002e9af  jmp     short loc_18002E9BC
0x18002e9b1  mov     edx, 80070057h
0x18002e9b6  mov     rbx, r15
0x18002e9b9  movzx   edi, dx
0x18002e9bc  mov     rcx, rbx; hMem
0x18002e9bf  call    cs:__imp_LocalFree
0x18002e9c5  test    r13, r13
0x18002e9c8  jz      short loc_18002E9CE
0x18002e9ca  mov     [r13+0], r12d
0x18002e9ce  mov     eax, edi
0x18002e9d0  add     rsp, 28h
0x18002e9d4  pop     r15
0x18002e9d6  pop     r14
0x18002e9d8  pop     r13
0x18002e9da  pop     r12
0x18002e9dc  pop     rdi
0x18002e9dd  pop     rsi
0x18002e9de  pop     rbp
0x18002e9df  pop     rbx
0x18002e9e0  retn
```
