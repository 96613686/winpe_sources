# GetSystemDirectoryInMString(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18001cb1c`
- end: `0x18001cb69`
- name: `?GetSystemDirectoryInMString@@YAJAEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@@Z`
- size: `77`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180012af0`
- `0x180020428`

## callees

- `0x180002d48`
- `0x18000305c`
- `0x18001cb1c`

## import_xrefs

- `SHELL32!SHGetFolderPathW` at `0x18001cb41`
- `SHELL32!SHGetFolderPathW` at `0x18001cb41`

## pseudocode

```c
__int64 __fastcall GetSystemDirectoryInMString(__int64 a1)
{
  HRESULT v2; // edi

  v2 = SHGetFolderPathW(0, 37, 0, 0, *(LPWSTR *)(*(_QWORD *)a1 + 24LL));
  if ( v2 >= 0 )
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::resize(a1);
  else
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::clear(a1);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18001cb1c  mov     [rsp+arg_0], rbx
0x18001cb21  push    rdi
0x18001cb22  sub     rsp, 30h
0x18001cb26  mov     rax, [rcx]
0x18001cb29  xor     r9d, r9d; dwFlags
0x18001cb2c  mov     rbx, rcx
0x18001cb2f  xor     r8d, r8d; hToken
0x18001cb32  xor     ecx, ecx; hwnd
0x18001cb34  mov     rdx, [rax+18h]
0x18001cb38  mov     [rsp+38h+pszPath], rdx; pszPath
0x18001cb3d  lea     edx, [r9+25h]; csidl
0x18001cb41  call    cs:__imp_SHGetFolderPathW
0x18001cb47  mov     edi, eax
0x18001cb49  mov     rcx, rbx
0x18001cb4c  test    eax, eax
0x18001cb4e  jns     short loc_18001CB57
0x18001cb50  call    ?clear@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::clear(void)
0x18001cb55  jmp     short loc_18001CB5C
0x18001cb57  call    ?resize@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::resize(void)
0x18001cb5c  mov     rbx, [rsp+38h+arg_0]
0x18001cb61  mov     eax, edi
0x18001cb63  add     rsp, 30h
0x18001cb67  pop     rdi
0x18001cb68  retn
```
