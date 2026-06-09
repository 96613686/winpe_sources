# mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::GetCurrentDirectoryW(void)

- ea: `0x14000d42c`
- end: `0x14000d4b6`
- name: `?GetCurrentDirectoryW@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAKXZ`
- size: `138`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140005e5c`

## callees

- `0x14000d42c`
- `0x140016588`
- `0x1400197b4`
- `0x140019bd8`

## import_xrefs

- `KERNEL32!GetCurrentDirectoryW` at `0x14000d45b`
- `KERNEL32!GetCurrentDirectoryW` at `0x14000d45b`
- `KERNEL32!GetLastError` at `0x14000d491`
- `KERNEL32!GetLastError` at `0x14000d491`
- `KERNEL32!SetLastError` at `0x14000d48b`
- `KERNEL32!SetLastError` at `0x14000d4a3`
- `KERNEL32!SetLastError` at `0x14000d48b`
- `KERNEL32!SetLastError` at `0x14000d4a3`

## pseudocode

```c
__int64 __fastcall mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::GetCurrentDirectoryW(
        unsigned int **a1)
{
  __int64 i; // rdx
  WCHAR *v3; // rdx
  DWORD CurrentDirectoryW; // eax
  DWORD LastError; // ebx

  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::clear((__int64)a1);
  for ( i = 260; ; i = CurrentDirectoryW )
  {
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::resize(
      a1,
      i);
    v3 = (WCHAR *)*((_QWORD *)*a1 + 3);
    if ( !v3 )
    {
      SetLastError(0x57u);
      goto LABEL_8;
    }
    CurrentDirectoryW = GetCurrentDirectoryW(0x104u, v3);
    if ( CurrentDirectoryW <= 0x104 )
      break;
  }
  if ( CurrentDirectoryW )
  {
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::resize(
      a1,
      CurrentDirectoryW);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::strip_lt_ws(a1);
    return **a1;
  }
LABEL_8:
  LastError = GetLastError();
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::clear((__int64)a1);
  SetLastError(LastError);
  return 0;
}

```

## disassembly

```asm
0x14000d42c  mov     [rsp+arg_0], rbx
0x14000d431  push    rdi
0x14000d432  sub     rsp, 20h
0x14000d436  mov     rdi, rcx
0x14000d439  call    ?clear@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::clear(void)
0x14000d43e  mov     ebx, 104h
0x14000d443  mov     edx, ebx
0x14000d445  mov     rcx, rdi
0x14000d448  call    ?resize@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAX_K@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::resize(unsigned __int64)
0x14000d44d  mov     rax, [rdi]
0x14000d450  mov     rdx, [rax+18h]; lpBuffer
0x14000d454  test    rdx, rdx
0x14000d457  jz      short loc_14000D486
0x14000d459  mov     ecx, ebx; nBufferLength
0x14000d45b  call    cs:__imp_GetCurrentDirectoryW
0x14000d461  cmp     eax, ebx
0x14000d463  jbe     short loc_14000D469
0x14000d465  mov     edx, eax
0x14000d467  jmp     short loc_14000D445
0x14000d469  test    eax, eax
0x14000d46b  jz      short loc_14000D491
0x14000d46d  mov     edx, eax
0x14000d46f  mov     rcx, rdi
0x14000d472  call    ?resize@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAX_K@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::resize(unsigned __int64)
0x14000d477  mov     rcx, rdi
0x14000d47a  call    ?strip_lt_ws@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAAEAV12@XZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::strip_lt_ws(void)
0x14000d47f  mov     rax, [rdi]
0x14000d482  mov     eax, [rax]
0x14000d484  jmp     short loc_14000D4AB
0x14000d486  mov     ecx, 57h ; 'W'; dwErrCode
0x14000d48b  call    cs:__imp_SetLastError
0x14000d491  call    cs:__imp_GetLastError
0x14000d497  mov     rcx, rdi
0x14000d49a  mov     ebx, eax
0x14000d49c  call    ?clear@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::clear(void)
0x14000d4a1  mov     ecx, ebx; dwErrCode
0x14000d4a3  call    cs:__imp_SetLastError
0x14000d4a9  xor     eax, eax
0x14000d4ab  mov     rbx, [rsp+28h+arg_0]
0x14000d4b0  add     rsp, 20h
0x14000d4b4  pop     rdi
0x14000d4b5  retn
```
