# Pca::MergeSdb::Utils::MergeSdbpUtilIsTheSameFile(ushort const *,ushort const *)

- ea: `0x14002cd38`
- end: `0x14002ce60`
- name: `?MergeSdbpUtilIsTheSameFile@Utils@MergeSdb@Pca@@YA_NPEBG0@Z`
- size: `296`
- prototype: `char __fastcall(LPCWSTR lpFileName, LPCWSTR, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x14002ce68`

## callees

- `0x14002cc74`
- `0x14002cd38`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x14002cdfa`
- `KERNEL32!CloseHandle` at `0x14002ce0e`
- `KERNEL32!CloseHandle` at `0x14002ce41`
- `KERNEL32!CloseHandle` at `0x14002ce55`
- `KERNEL32!CloseHandle` at `0x14002cdfa`
- `KERNEL32!CloseHandle` at `0x14002ce0e`
- `KERNEL32!CloseHandle` at `0x14002ce41`
- `KERNEL32!CloseHandle` at `0x14002ce55`
- `KERNEL32!CreateFileW` at `0x14002cda8`
- `KERNEL32!CreateFileW` at `0x14002cde5`
- `KERNEL32!CreateFileW` at `0x14002cda8`
- `KERNEL32!CreateFileW` at `0x14002cde5`
- `msvcrt!_wcsicmp` at `0x14002cd73`
- `msvcrt!_wcsicmp` at `0x14002cd73`

## pseudocode

```c
char __fastcall Pca::MergeSdb::Utils::MergeSdbpUtilIsTheSameFile(
        LPCWSTR lpFileName,
        LPCWSTR a2,
        const unsigned __int16 *a3)
{
  char *FileW; // rbx
  char *v7; // rdi
  void *v8; // r8
  bool IsTheSameFile; // si

  if ( !lpFileName || !*lpFileName || !a2 || !*a2 )
    return 0;
  if ( !_wcsicmp(lpFileName, a2) )
    return 1;
  FileW = (char *)CreateFileW(lpFileName, 0x80000000, 4u, 0, 3u, 0x80u, 0);
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    goto LABEL_10;
  v7 = (char *)CreateFileW(a2, 0x80000000, 4u, 0, 3u, 0x80u, 0);
  if ( (unsigned __int64)(v7 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    CloseHandle(v7);
    if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
      return 0;
LABEL_10:
    CloseHandle(FileW);
    return 0;
  }
  IsTheSameFile = Pca::MergeSdb::Utils::MergeSdbpUtilIsTheSameFile((Pca::MergeSdb::Utils *)FileW, v7, v8);
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(FileW);
  return IsTheSameFile;
}

```

## disassembly

```asm
0x14002cd38  mov     [rsp+arg_8], rbx
0x14002cd3d  mov     [rsp+arg_10], rsi
0x14002cd42  push    rdi
0x14002cd43  sub     rsp, 40h
0x14002cd47  mov     rdi, rdx
0x14002cd4a  mov     rbx, rcx
0x14002cd4d  xor     esi, esi
0x14002cd4f  test    rcx, rcx
0x14002cd52  jz      loc_14002CE14
0x14002cd58  cmp     [rcx], si
0x14002cd5b  jz      loc_14002CE14
0x14002cd61  test    rdx, rdx
0x14002cd64  jz      loc_14002CE14
0x14002cd6a  cmp     [rdx], si
0x14002cd6d  jz      loc_14002CE14
0x14002cd73  call    cs:__imp__wcsicmp
0x14002cd79  test    eax, eax
0x14002cd7b  jnz     short loc_14002CD84
0x14002cd7d  mov     al, 1
0x14002cd7f  jmp     loc_14002CE16
0x14002cd84  mov     [rsp+48h+hTemplateFile], rsi; hTemplateFile
0x14002cd89  mov     [rsp+48h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x14002cd91  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x14002cd99  xor     r9d, r9d; lpSecurityAttributes
0x14002cd9c  mov     edx, 80000000h; dwDesiredAccess
0x14002cda1  lea     r8d, [r9+4]; dwShareMode
0x14002cda5  mov     rcx, rbx; lpFileName
0x14002cda8  call    cs:__imp_CreateFileW
0x14002cdae  mov     rbx, rax
0x14002cdb1  mov     [rsp+48h+arg_0], rax
0x14002cdb6  dec     rax
0x14002cdb9  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14002cdbd  ja      short loc_14002CDC1
0x14002cdbf  jmp     short loc_14002CE0B
0x14002cdc1  mov     [rsp+48h+hTemplateFile], rsi; hTemplateFile
0x14002cdc6  mov     [rsp+48h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x14002cdce  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x14002cdd6  xor     r9d, r9d; lpSecurityAttributes
0x14002cdd9  mov     edx, 80000000h; dwDesiredAccess
0x14002cdde  lea     r8d, [r9+4]; dwShareMode
0x14002cde2  mov     rcx, rdi; lpFileName
0x14002cde5  call    cs:__imp_CreateFileW
0x14002cdeb  mov     rdi, rax
0x14002cdee  dec     rax
0x14002cdf1  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14002cdf5  ja      short loc_14002CE26
0x14002cdf7  mov     rcx, rdi; hObject
0x14002cdfa  call    cs:__imp_CloseHandle
0x14002ce00  nop
0x14002ce01  lea     rax, [rbx-1]
0x14002ce05  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14002ce09  ja      short loc_14002CE14
0x14002ce0b  mov     rcx, rbx; hObject
0x14002ce0e  call    cs:__imp_CloseHandle
0x14002ce14  xor     al, al
0x14002ce16  mov     rbx, [rsp+48h+arg_8]
0x14002ce1b  mov     rsi, [rsp+48h+arg_10]
0x14002ce20  add     rsp, 40h
0x14002ce24  pop     rdi
0x14002ce25  retn
0x14002ce26  mov     rdx, rdi; void *
0x14002ce29  mov     rcx, rbx; this
0x14002ce2c  call    ?MergeSdbpUtilIsTheSameFile@Utils@MergeSdb@Pca@@YA_NPEAX0@Z; Pca::MergeSdb::Utils::MergeSdbpUtilIsTheSameFile(void *,void *)
0x14002ce31  mov     sil, al
0x14002ce34  lea     rcx, [rdi-1]
0x14002ce38  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x14002ce3c  ja      short loc_14002CE48
0x14002ce3e  mov     rcx, rdi; hObject
0x14002ce41  call    cs:__imp_CloseHandle
0x14002ce47  nop
0x14002ce48  lea     rcx, [rbx-1]
0x14002ce4c  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x14002ce50  ja      short loc_14002CE5B
0x14002ce52  mov     rcx, rbx; hObject
0x14002ce55  call    cs:__imp_CloseHandle
0x14002ce5b  mov     al, sil
0x14002ce5e  jmp     short loc_14002CE16
```
