# CStringSrv::OpenResourceDll(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>)

- ea: `0x18004fba0`
- end: `0x18004fc85`
- name: `?OpenResourceDll@CStringSrv@@CAPEAUHINSTANCE__@@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z`
- size: `229`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18004f10c`

## callees

- `0x180003990`
- `0x1800039c8`
- `0x180010b80`
- `0x18001a0d0`
- `0x18001ac3c`
- `0x18004fba0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004fc13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004fc13`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18004fbee`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18004fbee`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18004fc2e`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18004fc2e`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
HMODULE __fastcall CStringSrv::OpenResourceDll(WCHAR *a1)
{
  signed int LastError; // eax
  bool v3; // sf
  HMODULE LibraryW; // rdi
  LPCWSTR lpLibFileName[2]; // [rsp+20h] [rbp-238h] BYREF
  WCHAR Buffer[264]; // [rsp+30h] [rbp-228h] BYREF

  lpLibFileName[1] = a1;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(lpLibFileName);
  memset_0(Buffer, 0, 0x20Au);
  if ( GetSystemDirectoryW(Buffer, 0x105u) )
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
      lpLibFileName,
      L"%s\\%s",
      Buffer,
      *(_QWORD *)a1);
  }
  else
  {
    LastError = GetLastError();
    v3 = LastError < 0;
    if ( LastError > 0 )
      v3 = 1;
    if ( v3 )
    {
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(lpLibFileName);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(a1);
      return 0;
    }
  }
  LibraryW = LoadLibraryW(lpLibFileName[0]);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(lpLibFileName);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(a1);
  return LibraryW;
}

```

## disassembly

```asm
0x18004fba0  mov     [rsp+arg_8], rbx
0x18004fba5  push    rdi
0x18004fba6  sub     rsp, 250h
0x18004fbad  mov     rax, cs:__security_cookie
0x18004fbb4  xor     rax, rsp
0x18004fbb7  mov     [rsp+258h+var_18], rax
0x18004fbbf  mov     rbx, rcx
0x18004fbc2  mov     [rsp+258h+var_230], rcx
0x18004fbc7  lea     rcx, [rsp+258h+lpLibFileName]; void *
0x18004fbcc  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18004fbd1  nop
0x18004fbd2  xor     edx, edx; Val
0x18004fbd4  mov     r8d, 20Ah; Size
0x18004fbda  lea     rcx, [rsp+258h+Buffer]; void *
0x18004fbdf  call    memset_0
0x18004fbe4  mov     edx, 105h; uSize
0x18004fbe9  lea     rcx, [rsp+258h+Buffer]; lpBuffer
0x18004fbee  call    cs:__imp_GetSystemDirectoryW
0x18004fbf4  test    eax, eax
0x18004fbf6  jz      short loc_18004FC13
0x18004fbf8  mov     r9, [rbx]
0x18004fbfb  lea     r8, [rsp+258h+Buffer]
0x18004fc00  lea     rdx, aSS; "%s\\%s"
0x18004fc07  lea     rcx, [rsp+258h+lpLibFileName]
0x18004fc0c  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x18004fc11  jmp     short loc_18004FC29
0x18004fc13  call    cs:__imp_GetLastError
0x18004fc19  test    eax, eax
0x18004fc1b  jle     short loc_18004FC27
0x18004fc1d  movzx   eax, ax
0x18004fc20  or      eax, 80070000h
0x18004fc25  test    eax, eax
0x18004fc27  js      short loc_18004FC4C
0x18004fc29  mov     rcx, [rsp+258h+lpLibFileName]; lpLibFileName
0x18004fc2e  call    cs:__imp_LoadLibraryW
0x18004fc34  mov     rdi, rax
0x18004fc37  lea     rcx, [rsp+258h+lpLibFileName]; void *
0x18004fc3c  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18004fc41  nop
0x18004fc42  mov     rcx, rbx; void *
0x18004fc45  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18004fc4a  jmp     short loc_18004FC61
0x18004fc4c  lea     rcx, [rsp+258h+lpLibFileName]; void *
0x18004fc51  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18004fc56  nop
0x18004fc57  mov     rcx, rbx; void *
0x18004fc5a  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18004fc5f  xor     edi, edi
0x18004fc61  mov     rax, rdi
0x18004fc64  mov     rcx, [rsp+258h+var_18]
0x18004fc6c  xor     rcx, rsp; StackCookie
0x18004fc6f  call    __security_check_cookie
0x18004fc74  mov     rbx, [rsp+258h+arg_8]
0x18004fc7c  add     rsp, 250h
0x18004fc83  pop     rdi
0x18004fc84  retn
```
