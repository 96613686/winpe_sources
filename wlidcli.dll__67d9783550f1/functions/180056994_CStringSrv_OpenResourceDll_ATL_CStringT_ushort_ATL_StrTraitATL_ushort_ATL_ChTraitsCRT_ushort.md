# CStringSrv::OpenResourceDll(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>)

- ea: `0x180056994`
- end: `0x180056a89`
- name: `?OpenResourceDll@CStringSrv@@CAPEAUHINSTANCE__@@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z`
- size: `245`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180055cd4`

## callees

- `0x180002da0`
- `0x1800039e4`
- `0x18000a914`
- `0x18000b1d8`
- `0x18000ba8c`
- `0x180056994`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056a11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056a11`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800569ec`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800569ec`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180056a2f`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180056a2f`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
HMODULE __fastcall CStringSrv::OpenResourceDll(const WCHAR *a1)
{
  signed int LastError; // eax
  bool v3; // sf
  LPCWSTR v4; // rbx
  HMODULE LibraryW; // rsi
  LPCWSTR lpLibFileName[2]; // [rsp+20h] [rbp-238h] BYREF
  WCHAR Buffer[264]; // [rsp+30h] [rbp-228h] BYREF

  lpLibFileName[1] = a1;
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>((__int64)lpLibFileName);
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
      ATL::CStringData::Release((ATL::CStringData *)(lpLibFileName[0] - 12));
      LibraryW = 0;
      goto LABEL_8;
    }
  }
  v4 = lpLibFileName[0];
  LibraryW = LoadLibraryW(lpLibFileName[0]);
  ATL::CStringData::Release((ATL::CStringData *)(v4 - 12));
LABEL_8:
  ATL::CStringData::Release((ATL::CStringData *)(*(_QWORD *)a1 - 24LL));
  return LibraryW;
}

```

## disassembly

```asm
0x180056994  mov     [rsp+arg_8], rbx
0x180056999  mov     [rsp+arg_10], rsi
0x18005699e  mov     [rsp+arg_0], rcx
0x1800569a3  push    rdi
0x1800569a4  sub     rsp, 250h
0x1800569ab  mov     rax, cs:__security_cookie
0x1800569b2  xor     rax, rsp
0x1800569b5  mov     [rsp+258h+var_18], rax
0x1800569bd  mov     rdi, rcx
0x1800569c0  mov     [rsp+258h+var_230], rcx
0x1800569c5  lea     rcx, [rsp+258h+lpLibFileName]
0x1800569ca  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800569cf  nop
0x1800569d0  xor     edx, edx; Val
0x1800569d2  mov     r8d, 20Ah; Size
0x1800569d8  lea     rcx, [rsp+258h+Buffer]; void *
0x1800569dd  call    memset_0
0x1800569e2  mov     edx, 105h; uSize
0x1800569e7  lea     rcx, [rsp+258h+Buffer]; lpBuffer
0x1800569ec  call    cs:__imp_GetSystemDirectoryW
0x1800569f2  test    eax, eax
0x1800569f4  jz      short loc_180056A11
0x1800569f6  mov     r9, [rdi]
0x1800569f9  lea     r8, [rsp+258h+Buffer]
0x1800569fe  lea     rdx, aSS; "%s\\%s"
0x180056a05  lea     rcx, [rsp+258h+lpLibFileName]
0x180056a0a  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x180056a0f  jmp     short loc_180056A27
0x180056a11  call    cs:__imp_GetLastError
0x180056a17  test    eax, eax
0x180056a19  jle     short loc_180056A25
0x180056a1b  movzx   eax, ax
0x180056a1e  or      eax, 80070000h
0x180056a23  test    eax, eax
0x180056a25  js      short loc_180056A44
0x180056a27  mov     rbx, [rsp+258h+lpLibFileName]
0x180056a2c  mov     rcx, rbx; lpLibFileName
0x180056a2f  call    cs:__imp_LoadLibraryW
0x180056a35  mov     rsi, rax
0x180056a38  lea     rcx, [rbx-18h]; this
0x180056a3c  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180056a41  nop
0x180056a42  jmp     short loc_180056A55
0x180056a44  mov     rcx, [rsp+258h+lpLibFileName]
0x180056a49  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180056a4d  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180056a52  nop
0x180056a53  xor     esi, esi
0x180056a55  mov     rcx, [rdi]
0x180056a58  sub     rcx, 18h; this
0x180056a5c  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180056a61  mov     rax, rsi
0x180056a64  mov     rcx, [rsp+258h+var_18]
0x180056a6c  xor     rcx, rsp; StackCookie
0x180056a6f  call    __security_check_cookie
0x180056a74  lea     r11, [rsp+258h+var_8]
0x180056a7c  mov     rbx, [r11+18h]
0x180056a80  mov     rsi, [r11+20h]
0x180056a84  mov     rsp, r11
0x180056a87  pop     rdi
0x180056a88  retn
```
