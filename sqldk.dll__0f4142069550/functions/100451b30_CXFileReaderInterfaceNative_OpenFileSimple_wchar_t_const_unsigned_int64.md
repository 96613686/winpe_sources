# CXFileReaderInterfaceNative::OpenFileSimple(wchar_t const *,unsigned __int64 *)

- ea: `0x100451b30`
- end: `0x100451c12`
- name: `?OpenFileSimple@CXFileReaderInterfaceNative@@UEAAHPEB_WPEA_K@Z`
- size: `226`
- prototype: `int(CXFileReaderInterfaceNative *__hidden this, const wchar_t *, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x100451b30`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x100451bb7`
- `KERNEL32!CreateFileW` at `0x100451bb7`
- `KERNEL32!GetFileSizeEx` at `0x100451bf3`
- `KERNEL32!GetFileSizeEx` at `0x100451bf3`
- `KERNEL32!GetLastError` at `0x100451bca`
- `KERNEL32!GetLastError` at `0x100451bca`

## pseudocode

```c
__int64 __fastcall CXFileReaderInterfaceNative::OpenFileSimple(
        CXFileReaderInterfaceNative *this,
        const wchar_t *a2,
        union _LARGE_INTEGER *a3)
{
  _WORD *v3; // rax
  signed __int64 v4; // r11
  __int64 v7; // r10
  __int16 v8; // cx
  _WORD *v9; // rcx
  HANDLE FileW; // rax

  v3 = (_WORD *)((char *)this + 40);
  v4 = (char *)a2 - ((char *)this + 40);
  v7 = 260;
  do
  {
    if ( v7 == -2147483386 )
      break;
    v8 = *(_WORD *)((char *)v3 + v4);
    if ( !v8 )
      break;
    *v3++ = v8;
    --v7;
  }
  while ( v7 );
  v9 = v3 - 1;
  if ( v7 )
    v9 = v3;
  *v9 = 0;
  FileW = CreateFileW(a2, 0x80000000, 3u, 0, 3u, 0x40000000u, 0);
  *((_QWORD *)this + 74) = FileW;
  if ( FileW != (HANDLE)-1LL && (!a3 || GetFileSizeEx(FileW, a3)) )
    return 1;
  *((_DWORD *)this + 152) = GetLastError();
  return 0;
}

```

## disassembly

```asm
0x100451b30  mov     [rsp+arg_0], rbx
0x100451b35  mov     [rsp+arg_8], rsi
0x100451b3a  push    rdi
0x100451b3b  sub     rsp, 40h
0x100451b3f  lea     rax, [rcx+28h]
0x100451b43  mov     r11, rdx
0x100451b46  sub     r11, rax
0x100451b49  mov     rdi, r8
0x100451b4c  mov     rsi, rdx
0x100451b4f  mov     rbx, rcx
0x100451b52  mov     r10d, 104h
0x100451b58  nop     dword ptr [rax+rax+00000000h]
0x100451b60  lea     r9, [r10+7FFFFEFAh]
0x100451b67  test    r9, r9
0x100451b6a  jz      short loc_100451B83
0x100451b6c  movzx   ecx, word ptr [r11+rax]
0x100451b71  test    cx, cx
0x100451b74  jz      short loc_100451B83
0x100451b76  mov     [rax], cx
0x100451b79  add     rax, 2
0x100451b7d  sub     r10, 1
0x100451b81  jnz     short loc_100451B60
0x100451b83  lea     rcx, [rax-2]
0x100451b87  test    r10, r10
0x100451b8a  mov     edx, 80000000h; dwDesiredAccess
0x100451b8f  cmovnz  rcx, rax
0x100451b93  xor     eax, eax
0x100451b95  mov     [rsp+48h+hTemplateFile], rax; hTemplateFile
0x100451b9a  xor     r9d, r9d; lpSecurityAttributes
0x100451b9d  mov     [rsp+48h+dwFlagsAndAttributes], 40000000h; dwFlagsAndAttributes
0x100451ba5  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x100451bad  mov     [rcx], ax
0x100451bb0  lea     r8d, [rax+3]; dwShareMode
0x100451bb4  mov     rcx, rsi; lpFileName
0x100451bb7  call    cs:__imp_CreateFileW
0x100451bbd  mov     [rbx+250h], rax
0x100451bc4  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x100451bc8  jnz     short loc_100451BE8
0x100451bca  call    cs:__imp_GetLastError
0x100451bd0  mov     [rbx+260h], eax
0x100451bd6  xor     eax, eax
0x100451bd8  mov     rbx, [rsp+48h+arg_0]
0x100451bdd  mov     rsi, [rsp+48h+arg_8]
0x100451be2  add     rsp, 40h
0x100451be6  pop     rdi
0x100451be7  retn
0x100451be8  test    rdi, rdi
0x100451beb  jz      short loc_100451BFD
0x100451bed  mov     rdx, rdi; lpFileSize
0x100451bf0  mov     rcx, rax; hFile
0x100451bf3  call    cs:__imp_GetFileSizeEx
0x100451bf9  test    eax, eax
0x100451bfb  jz      short loc_100451BCA
0x100451bfd  mov     rbx, [rsp+48h+arg_0]
0x100451c02  mov     eax, 1
0x100451c07  mov     rsi, [rsp+48h+arg_8]
0x100451c0c  add     rsp, 40h
0x100451c10  pop     rdi
0x100451c11  retn
```
