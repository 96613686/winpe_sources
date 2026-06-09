# CWinSATResultsInfo::GetDiskStrings(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18001e0c4`
- end: `0x18001e2e0`
- name: `?GetDiskStrings@CWinSATResultsInfo@@AEAAJAEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@0@Z`
- size: `540`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x180005c50`

## callees

- `0x180001584`
- `0x1800019d0`
- `0x180002d48`
- `0x18000305c`
- `0x180003588`
- `0x180005394`
- `0x1800054e0`
- `0x1800071d0`
- `0x18000e864`
- `0x1800111c0`
- `0x18001e0c4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e193`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e193`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceExW` at `0x18001e189`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceExW` at `0x18001e189`
- `SHELL32!SHGetFolderPathW` at `0x18001e133`
- `SHELL32!SHGetFolderPathW` at `0x18001e133`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CWinSATResultsInfo::GetDiskStrings(__int64 a1, __int64 a2, _QWORD *a3)
{
  HRESULT v5; // ebx
  signed int LastError; // eax
  HINSTANCE v8; // r8
  __int64 v9; // rdx
  HINSTANCE v10; // r8
  __int64 v11; // rax
  __int64 *v12; // rax
  __int64 v13; // [rsp+30h] [rbp-A8h] BYREF
  __int64 v14; // [rsp+38h] [rbp-A0h] BYREF
  __int64 v15; // [rsp+40h] [rbp-98h] BYREF
  _ULARGE_INTEGER FreeBytesAvailableToCaller; // [rsp+48h] [rbp-90h] BYREF
  union _ULARGE_INTEGER TotalNumberOfBytes; // [rsp+50h] [rbp-88h] BYREF
  union _ULARGE_INTEGER TotalNumberOfFreeBytes; // [rsp+58h] [rbp-80h] BYREF
  __int64 v19; // [rsp+60h] [rbp-78h]
  _DWORD v20[4]; // [rsp+68h] [rbp-70h] BYREF
  _BYTE v21[40]; // [rsp+78h] [rbp-60h] BYREF
  _BYTE v22[48]; // [rsp+A0h] [rbp-38h] BYREF
  __int64 v23; // [rsp+E0h] [rbp+8h] BYREF
  __int64 v24; // [rsp+F8h] [rbp+20h] BYREF

  v23 = a1;
  v19 = -2;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v24,
    260);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::reserve(
    &v24,
    260);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::clear((__int64)&v24);
  v5 = SHGetFolderPathW(0, 38, 0, 0, *(LPWSTR *)(v24 + 24));
  if ( v5 < 0 )
  {
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::clear((__int64)&v24);
LABEL_7:
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)&v24);
    return (unsigned int)v5;
  }
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::resize(&v24);
  FreeBytesAvailableToCaller.QuadPart = 0;
  TotalNumberOfBytes.QuadPart = 0;
  TotalNumberOfFreeBytes.QuadPart = 0;
  if ( !GetDiskFreeSpaceExW(
          *(LPCWSTR *)(v24 + 24),
          &FreeBytesAvailableToCaller,
          &TotalNumberOfBytes,
          &TotalNumberOfFreeBytes) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v5 = LastError;
    goto LABEL_7;
  }
  ((void (__fastcall *)(_QWORD, _QWORD))ConvertToBestString)(&v15, (_ULARGE_INTEGER)FreeBytesAvailableToCaller.QuadPart);
  ((void (__fastcall *)(_QWORD, _QWORD))ConvertToBestString)(&v14, (union _ULARGE_INTEGER)TotalNumberOfBytes.QuadPart);
  v9 = mlib::MUILoader::MUILoader((mlib::MUILoader *)v21, 0x2710u, v8);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v13,
    v9);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::reserve(
    a2,
    128);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::spf(
    a2,
    *(_QWORD *)(v13 + 24),
    *(_QWORD *)(v15 + 24),
    *(_QWORD *)(v14 + 24));
  try
  {
    v11 = mlib::MUILoader::MUILoader((mlib::MUILoader *)v22, 0x2716u, v10);
    v12 = mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v23,
            v11);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::attach_buf(
      a3,
      *v12);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)&v23);
  }
  catch ( mlib::MSError v20 )
  {
    LODWORD(v23) = v20[0];
    mlib::MSError::~MSError((mlib::MSError *)v20);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)&v13);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)&v14);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)&v15);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)&v24);
    return (unsigned int)v23;
  }
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)&v13);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)&v14);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)&v15);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)&v24);
  return 0;
}

```

## disassembly

```asm
0x18001e0c4  mov     rax, rsp
0x18001e0c7  mov     [rax+8], rcx
0x18001e0cb  push    rdi
0x18001e0cc  sub     rsp, 0D0h
0x18001e0d3  mov     qword ptr [rax-78h], 0FFFFFFFFFFFFFFFEh
0x18001e0db  mov     [rax+10h], rbx
0x18001e0df  mov     [rax+18h], rsi
0x18001e0e3  mov     rdi, r8
0x18001e0e6  mov     rsi, rdx
0x18001e0e9  mov     ebx, 104h
0x18001e0ee  mov     edx, ebx
0x18001e0f0  lea     rcx, [rax+20h]
0x18001e0f4  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@_K@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(unsigned __int64)
0x18001e0f9  nop
0x18001e0fa  mov     edx, ebx
0x18001e0fc  lea     rcx, [rsp+0D8h+arg_18]
0x18001e104  call    ?reserve@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAX_K@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::reserve(unsigned __int64)
0x18001e109  lea     rcx, [rsp+0D8h+arg_18]
0x18001e111  call    ?clear@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::clear(void)
0x18001e116  mov     rax, [rsp+0D8h+arg_18]
0x18001e11e  mov     rcx, [rax+18h]
0x18001e122  mov     [rsp+0D8h+pszPath], rcx; pszPath
0x18001e127  xor     r9d, r9d; dwFlags
0x18001e12a  xor     r8d, r8d; hToken
0x18001e12d  lea     edx, [r9+26h]; csidl
0x18001e131  xor     ecx, ecx; hwnd
0x18001e133  call    cs:__imp_SHGetFolderPathW
0x18001e139  mov     ebx, eax
0x18001e13b  lea     rcx, [rsp+0D8h+arg_18]
0x18001e143  test    eax, eax
0x18001e145  jns     short loc_18001E14E
0x18001e147  call    ?clear@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::clear(void)
0x18001e14c  jmp     short loc_18001E1A7
0x18001e14e  call    ?resize@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::resize(void)
0x18001e153  mov     qword ptr [rsp+0D8h+FreeBytesAvailableToCaller], 0
0x18001e15c  mov     qword ptr [rsp+0D8h+TotalNumberOfBytes], 0
0x18001e165  mov     qword ptr [rsp+0D8h+TotalNumberOfFreeBytes], 0
0x18001e16e  lea     r9, [rsp+0D8h+TotalNumberOfFreeBytes]; lpTotalNumberOfFreeBytes
0x18001e173  lea     r8, [rsp+0D8h+TotalNumberOfBytes]; lpTotalNumberOfBytes
0x18001e178  lea     rdx, [rsp+0D8h+FreeBytesAvailableToCaller]; lpFreeBytesAvailableToCaller
0x18001e17d  mov     rcx, [rsp+0D8h+arg_18]
0x18001e185  mov     rcx, [rcx+18h]; lpDirectoryName
0x18001e189  call    cs:__imp_GetDiskFreeSpaceExW
0x18001e18f  test    eax, eax
0x18001e191  jnz     short loc_18001E1BB
0x18001e193  call    cs:__imp_GetLastError
0x18001e199  test    eax, eax
0x18001e19b  jle     short loc_18001E1A5
0x18001e19d  movzx   eax, ax
0x18001e1a0  or      eax, 80070000h
0x18001e1a5  mov     ebx, eax
0x18001e1a7  lea     rcx, [rsp+0D8h+arg_18]
0x18001e1af  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18001e1b4  mov     eax, ebx
0x18001e1b6  jmp     loc_18001E2CB
0x18001e1bb  mov     rdx, qword ptr [rsp+0D8h+FreeBytesAvailableToCaller]
0x18001e1c0  lea     rcx, [rsp+0D8h+var_98]
0x18001e1c5  call    ?ConvertToBestString@@YA?AV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@_K_N@Z; ConvertToBestString(unsigned __int64,bool)
0x18001e1ca  nop
0x18001e1cb  mov     rdx, qword ptr [rsp+0D8h+TotalNumberOfBytes]
0x18001e1d0  lea     rcx, [rsp+0D8h+var_A0]
0x18001e1d5  call    ?ConvertToBestString@@YA?AV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@_K_N@Z; ConvertToBestString(unsigned __int64,bool)
0x18001e1da  nop
0x18001e1db  mov     edx, 2710h; unsigned __int16
0x18001e1e0  lea     rcx, [rsp+0D8h+var_60]; this
0x18001e1e5  call    ??0MUILoader@mlib@@QEAA@GPEAUHINSTANCE__@@@Z; mlib::MUILoader::MUILoader(ushort,HINSTANCE__ *)
0x18001e1ea  mov     rdx, rax
0x18001e1ed  lea     rcx, [rsp+0D8h+var_A8]
0x18001e1f2  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@AEBVMSInitializer@1@@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(mlib::MSInitializer const &)
0x18001e1f7  nop
0x18001e1f8  mov     edx, 80h
0x18001e1fd  mov     rcx, rsi
0x18001e200  call    ?reserve@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAX_K@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::reserve(unsigned __int64)
0x18001e205  mov     r9, [rsp+0D8h+var_A0]
0x18001e20a  mov     r9, [r9+18h]
0x18001e20e  mov     r8, [rsp+0D8h+var_98]
0x18001e213  mov     r8, [r8+18h]
0x18001e217  mov     rdx, [rsp+0D8h+var_A8]
0x18001e21c  mov     rdx, [rdx+18h]
0x18001e220  mov     rcx, rsi
0x18001e223  call    ?spf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAXPEBGZZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::spf(ushort const *,...)
0x18001e228  nop
0x18001e229  mov     edx, 2716h; unsigned __int16
0x18001e22e  lea     rcx, [rsp+0D8h+var_38]; this
0x18001e236  call    ??0MUILoader@mlib@@QEAA@GPEAUHINSTANCE__@@@Z; mlib::MUILoader::MUILoader(ushort,HINSTANCE__ *)
0x18001e23b  mov     rdx, rax
0x18001e23e  lea     rcx, [rsp+0D8h+arg_0]
0x18001e246  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@AEBVMSInitializer@1@@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(mlib::MSInitializer const &)
0x18001e24b  mov     rdx, [rax]
0x18001e24e  mov     rcx, rdi
0x18001e251  call    ?attach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXPEAV?$mstring_buf@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::attach_buf(mlib::mstring_buf<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x18001e256  lea     rcx, [rsp+0D8h+arg_0]
0x18001e25e  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18001e263  nop
0x18001e264  lea     rcx, [rsp+0D8h+var_A8]
0x18001e269  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18001e26e  nop
0x18001e26f  lea     rcx, [rsp+0D8h+var_A0]
0x18001e274  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18001e279  nop
0x18001e27a  lea     rcx, [rsp+0D8h+var_98]
0x18001e27f  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18001e284  nop
0x18001e285  lea     rcx, [rsp+0D8h+arg_18]
0x18001e28d  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18001e292  xor     eax, eax
0x18001e294  jmp     short loc_18001E2CB
0x18001e296  lea     rcx, [rsp+0D8h+var_A8]
0x18001e29b  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18001e2a0  nop
0x18001e2a1  lea     rcx, [rsp+0D8h+var_A0]
0x18001e2a6  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18001e2ab  nop
0x18001e2ac  lea     rcx, [rsp+0D8h+var_98]
0x18001e2b1  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18001e2b6  nop
0x18001e2b7  lea     rcx, [rsp+0D8h+arg_18]
0x18001e2bf  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18001e2c4  mov     eax, dword ptr [rsp+0D8h+arg_0]
0x18001e2cb  lea     r11, [rsp+0D8h+var_8]
0x18001e2d3  mov     rbx, [r11+18h]
0x18001e2d7  mov     rsi, [r11+20h]
0x18001e2db  mov     rsp, r11
0x18001e2de  pop     rdi
0x18001e2df  retn
```
