# WinSAT::StorageDevice::pOpen(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,ulong,ulong)

- ea: `0x140062a38`
- end: `0x140062ac6`
- name: `?pOpen@StorageDevice@WinSAT@@AEAA_NAEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@KK@Z`
- size: `142`
- prototype: `char __fastcall(__int64, _QWORD *, DWORD, int)`
- caller_count: `5`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x14006099c`
- `0x140061378`
- `0x140061494`
- `0x140061600`
- `0x140061ab4`

## callees

- `0x140016480`
- `0x140060888`
- `0x140062a38`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x140062a97`
- `KERNEL32!CreateFileW` at `0x140062a97`
- `KERNEL32!SetLastError` at `0x140062a59`
- `KERNEL32!SetLastError` at `0x140062a59`

## pseudocode

```c
char __fastcall WinSAT::StorageDevice::pOpen(__int64 a1, _QWORD *a2, DWORD a3, int a4)
{
  char result; // al
  HANDLE FileW; // rax

  if ( !*(_QWORD *)(a1 + 80) )
  {
    SetLastError(6u);
    return 0;
  }
  if ( *(_QWORD *)(a1 + 72) != -1 )
    WinSAT::StorageDevice::Close((WinSAT::StorageDevice *)a1);
  FileW = CreateFileW(*(LPCWSTR *)(*a2 + 24LL), a3, 3u, 0, 3u, a4 | 0x80u, 0);
  *(_QWORD *)(a1 + 72) = FileW;
  if ( FileW == (HANDLE)-1LL )
    return 0;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::attach_buf(
    a1 + 32,
    *a2);
  result = 1;
  *(_BYTE *)(a1 + 93) = 1;
  *(_BYTE *)(a1 + 112) = 0;
  return result;
}

```

## disassembly

```asm
0x140062a38  push    rbx
0x140062a3a  push    rbp
0x140062a3b  push    rsi
0x140062a3c  push    rdi
0x140062a3d  sub     rsp, 48h
0x140062a41  cmp     qword ptr [rcx+50h], 0
0x140062a46  mov     esi, r9d
0x140062a49  mov     ebp, r8d
0x140062a4c  mov     rdi, rdx
0x140062a4f  mov     rbx, rcx
0x140062a52  jnz     short loc_140062A63
0x140062a54  mov     ecx, 6; dwErrCode
0x140062a59  call    cs:__imp_SetLastError
0x140062a5f  xor     al, al
0x140062a61  jmp     short loc_140062ABD
0x140062a63  cmp     qword ptr [rcx+48h], 0FFFFFFFFFFFFFFFFh
0x140062a68  jz      short loc_140062A6F
0x140062a6a  call    ?Close@StorageDevice@WinSAT@@QEAAXXZ; WinSAT::StorageDevice::Close(void)
0x140062a6f  mov     rcx, [rdi]
0x140062a72  mov     r8d, 3; dwShareMode
0x140062a78  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x140062a81  bts     esi, 7
0x140062a85  mov     [rsp+68h+dwFlagsAndAttributes], esi; dwFlagsAndAttributes
0x140062a89  xor     r9d, r9d; lpSecurityAttributes
0x140062a8c  mov     edx, ebp; dwDesiredAccess
0x140062a8e  mov     [rsp+68h+dwCreationDisposition], r8d; dwCreationDisposition
0x140062a93  mov     rcx, [rcx+18h]; lpFileName
0x140062a97  call    cs:__imp_CreateFileW
0x140062a9d  mov     [rbx+48h], rax
0x140062aa1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140062aa5  jz      short loc_140062A5F
0x140062aa7  mov     rdx, [rdi]
0x140062aaa  lea     rcx, [rbx+20h]
0x140062aae  call    ?attach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXPEAV?$mstring_buf@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::attach_buf(mlib::mstring_buf<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x140062ab3  mov     al, 1
0x140062ab5  mov     byte ptr [rbx+5Dh], 1
0x140062ab9  mov     byte ptr [rbx+70h], 0
0x140062abd  add     rsp, 48h
0x140062ac1  pop     rdi
0x140062ac2  pop     rsi
0x140062ac3  pop     rbp
0x140062ac4  pop     rbx
0x140062ac5  retn
```
