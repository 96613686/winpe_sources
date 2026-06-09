# VCardGetBuffer(ushort const *,char *,char * *)

- ea: `0x18007173c`
- end: `0x180071884`
- name: `?VCardGetBuffer@@YAHPEBGPEADPEAPEAD@Z`
- size: `328`
- prototype: `__int64 __fastcall(const unsigned __int16 *, char *, char **)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18004fe0c`
- `0x18006ab14`
- `0x18006af60`

## callees

- `0x180018c48`
- `0x18007173c`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x180071794`
- `KERNEL32!LocalAlloc` at `0x180071826`
- `KERNEL32!LocalAlloc` at `0x180071794`
- `KERNEL32!LocalAlloc` at `0x180071826`
- `KERNEL32!CreateFileW` at `0x1800717f7`
- `KERNEL32!CreateFileW` at `0x1800717f7`
- `KERNEL32!CloseHandle` at `0x180071862`
- `KERNEL32!CloseHandle` at `0x180071862`
- `KERNEL32!GetFileSize` at `0x18007180a`
- `KERNEL32!GetFileSize` at `0x18007180a`
- `KERNEL32!ReadFile` at `0x180071847`
- `KERNEL32!ReadFile` at `0x180071847`

## pseudocode

```c
__int64 __fastcall VCardGetBuffer(const unsigned __int16 *a1, char *a2, char **a3)
{
  unsigned int v5; // r14d
  void *v6; // rdi
  __int64 v7; // rax
  SIZE_T v8; // rbp
  char *v9; // rax
  char *v10; // rbx
  __int64 v11; // rax
  HANDLE FileW; // rax
  DWORD FileSize; // esi
  char *v14; // rax
  DWORD NumberOfBytesRead; // [rsp+70h] [rbp+8h] BYREF

  v5 = 0;
  if ( __PAIR128__((unsigned __int64)a1, (unsigned __int64)a2) == 0 )
    return v5;
  v6 = 0;
  if ( a2 )
  {
    v7 = -1;
    do
      ++v7;
    while ( a2[v7] );
    if ( v7 )
    {
      v8 = (unsigned int)(v7 + 1);
      v9 = (char *)LocalAlloc(0x40u, v8);
      v10 = v9;
      if ( !v9 )
        return v5;
      StringCchCopyA(v9, (unsigned int)v8, a2);
      goto LABEL_16;
    }
  }
  v10 = 0;
  if ( !a1 )
    goto LABEL_16;
  v11 = -1;
  do
    ++v11;
  while ( a1[v11] );
  if ( !v11
    || (FileW = CreateFileW(a1, 0x80000000, 1u, 0, 3u, 0x8000000u, 0), v6 = FileW, FileW != (HANDLE)-1LL)
    && (FileSize = GetFileSize(FileW, 0), NumberOfBytesRead = 0, FileSize - 1 <= 0xFFFFFFFD)
    && (v14 = (char *)LocalAlloc(0x40u, FileSize + 1), (v10 = v14) != 0)
    && ReadFile(v6, v14, FileSize, &NumberOfBytesRead, 0) )
  {
LABEL_16:
    *a3 = v10;
    v5 = 1;
  }
  if ( v6 )
    CloseHandle(v6);
  return v5;
}

```

## disassembly

```asm
0x18007173c  mov     [rsp+arg_8], rbx
0x180071741  mov     [rsp+arg_10], rbp
0x180071746  push    rsi
0x180071747  push    rdi
0x180071748  push    r12
0x18007174a  push    r14
0x18007174c  push    r15
0x18007174e  sub     rsp, 40h
0x180071752  xor     r12d, r12d
0x180071755  mov     r15, r8
0x180071758  mov     rsi, rdx
0x18007175b  mov     r14d, r12d
0x18007175e  test    rcx, rcx
0x180071761  jnz     short loc_18007176C
0x180071763  test    rdx, rdx
0x180071766  jz      loc_180071868
0x18007176c  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180071770  mov     rdi, r12
0x180071773  test    rsi, rsi
0x180071776  jz      short loc_1800717B8
0x180071778  mov     rax, rbp
0x18007177b  inc     rax
0x18007177e  cmp     [rdx+rax], r12b
0x180071782  jnz     short loc_18007177B
0x180071784  test    rax, rax
0x180071787  jz      short loc_1800717B8
0x180071789  inc     eax
0x18007178b  mov     ecx, 40h ; '@'; uFlags
0x180071790  mov     edx, eax; uBytes
0x180071792  mov     ebp, eax
0x180071794  call    cs:__imp_LocalAlloc
0x18007179a  mov     rbx, rax
0x18007179d  test    rax, rax
0x1800717a0  jz      loc_180071868
0x1800717a6  mov     r8, rsi; char *
0x1800717a9  mov     edx, ebp; unsigned __int64
0x1800717ab  mov     rcx, rax; char *
0x1800717ae  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x1800717b3  jmp     loc_180071851
0x1800717b8  mov     rbx, r12
0x1800717bb  test    rcx, rcx
0x1800717be  jz      loc_180071851
0x1800717c4  mov     rax, rbp
0x1800717c7  inc     rax
0x1800717ca  cmp     [rcx+rax*2], r12w
0x1800717cf  jnz     short loc_1800717C7
0x1800717d1  test    rax, rax
0x1800717d4  jz      short loc_180071851
0x1800717d6  xor     r9d, r9d; lpSecurityAttributes
0x1800717d9  mov     [rsp+68h+hTemplateFile], r12; hTemplateFile
0x1800717de  mov     [rsp+68h+dwFlagsAndAttributes], 8000000h; dwFlagsAndAttributes
0x1800717e6  mov     edx, 80000000h; dwDesiredAccess
0x1800717eb  mov     [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x1800717f3  lea     r8d, [r9+1]; dwShareMode
0x1800717f7  call    cs:__imp_CreateFileW
0x1800717fd  mov     rdi, rax
0x180071800  cmp     rax, rbp
0x180071803  jz      short loc_18007185A
0x180071805  xor     edx, edx; lpFileSizeHigh
0x180071807  mov     rcx, rax; hFile
0x18007180a  call    cs:__imp_GetFileSize
0x180071810  mov     esi, eax
0x180071812  mov     [rsp+68h+NumberOfBytesRead], r12d
0x180071817  dec     eax
0x180071819  cmp     eax, 0FFFFFFFDh
0x18007181c  ja      short loc_18007185A
0x18007181e  lea     edx, [rsi+1]; uBytes
0x180071821  mov     ecx, 40h ; '@'; uFlags
0x180071826  call    cs:__imp_LocalAlloc
0x18007182c  mov     rbx, rax
0x18007182f  test    rax, rax
0x180071832  jz      short loc_18007185A
0x180071834  lea     r9, [rsp+68h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180071839  mov     qword ptr [rsp+68h+dwCreationDisposition], r12; lpOverlapped
0x18007183e  mov     r8d, esi; nNumberOfBytesToRead
0x180071841  mov     rdx, rax; lpBuffer
0x180071844  mov     rcx, rdi; hFile
0x180071847  call    cs:__imp_ReadFile
0x18007184d  test    eax, eax
0x18007184f  jz      short loc_18007185A
0x180071851  mov     [r15], rbx
0x180071854  mov     r14d, 1
0x18007185a  test    rdi, rdi
0x18007185d  jz      short loc_180071868
0x18007185f  mov     rcx, rdi; hObject
0x180071862  call    cs:__imp_CloseHandle
0x180071868  lea     r11, [rsp+68h+var_28]
0x18007186d  mov     eax, r14d
0x180071870  mov     rbx, [r11+38h]
0x180071874  mov     rbp, [r11+40h]
0x180071878  mov     rsp, r11
0x18007187b  pop     r15
0x18007187d  pop     r14
0x18007187f  pop     r12
0x180071881  pop     rdi
0x180071882  pop     rsi
0x180071883  retn
```
