# ClusApi::Facade::NetworkUtilities::GetHostComputerName(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &)

- ea: `0x18008cdb4`
- end: `0x18008ce5d`
- name: `?GetHostComputerName@NetworkUtilities@Facade@ClusApi@@SAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `169`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180036270`

## callees

- `0x18001072c`
- `0x180014630`
- `0x180025888`
- `0x18008cdb4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008cdd8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008cde5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008ce1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008cdd8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008cde5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008ce1e`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18008cdce`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18008ce14`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18008cdce`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18008ce14`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
signed int __fastcall ClusApi::Facade::NetworkUtilities::GetHostComputerName(__int64 a1)
{
  signed int result; // eax
  signed int LastError; // eax
  unsigned int v4; // ebx
  LPWSTR lpBuffer[5]; // [rsp+20h] [rbp-28h] BYREF
  DWORD nSize; // [rsp+58h] [rbp+10h] BYREF

  nSize = 0;
  if ( GetComputerNameExW(ComputerNameNetBIOS, 0, &nSize) )
    return -2147019873;
  if ( GetLastError() == 234 )
  {
    std::vector<wchar_t>::vector<wchar_t>(lpBuffer, nSize);
    if ( GetComputerNameExW(ComputerNameNetBIOS, lpBuffer[0], &nSize) )
    {
      std::wstring::assign(a1);
      v4 = 0;
    }
    else
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
    }
    std::vector<unsigned short>::_Tidy(lpBuffer);
    return v4;
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x18008cdb4  push    rbx
0x18008cdb6  sub     rsp, 40h
0x18008cdba  mov     rbx, rcx
0x18008cdbd  mov     [rsp+48h+nSize], 0
0x18008cdc5  lea     r8, [rsp+48h+nSize]; nSize
0x18008cdca  xor     edx, edx; lpBuffer
0x18008cdcc  xor     ecx, ecx; NameType
0x18008cdce  call    cs:__imp_GetComputerNameExW
0x18008cdd4  test    eax, eax
0x18008cdd6  jnz     short loc_18008CE52
0x18008cdd8  call    cs:__imp_GetLastError
0x18008cdde  cmp     eax, 0EAh
0x18008cde3  jz      short loc_18008CDF9
0x18008cde5  call    cs:__imp_GetLastError
0x18008cdeb  test    eax, eax
0x18008cded  jle     short loc_18008CE57
0x18008cdef  movzx   eax, ax
0x18008cdf2  or      eax, 80070000h
0x18008cdf7  jmp     short loc_18008CE57
0x18008cdf9  mov     edx, [rsp+48h+nSize]
0x18008cdfd  lea     rcx, [rsp+48h+lpBuffer]
0x18008ce02  call    ??0?$vector@_WV?$allocator@_W@std@@@std@@QEAA@_KAEBV?$allocator@_W@1@@Z; std::vector<wchar_t>::vector<wchar_t>(unsigned __int64,std::allocator<wchar_t> const &)
0x18008ce07  nop
0x18008ce08  lea     r8, [rsp+48h+nSize]; nSize
0x18008ce0d  mov     rdx, [rsp+48h+lpBuffer]; lpBuffer
0x18008ce12  xor     ecx, ecx; NameType
0x18008ce14  call    cs:__imp_GetComputerNameExW
0x18008ce1a  test    eax, eax
0x18008ce1c  jnz     short loc_18008CE35
0x18008ce1e  call    cs:__imp_GetLastError
0x18008ce24  mov     ebx, eax
0x18008ce26  test    eax, eax
0x18008ce28  jle     short loc_18008CE44
0x18008ce2a  movzx   ebx, ax
0x18008ce2d  or      ebx, 80070000h
0x18008ce33  jmp     short loc_18008CE44
0x18008ce35  mov     rdx, [rsp+48h+lpBuffer]
0x18008ce3a  mov     rcx, rbx
0x18008ce3d  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x18008ce42  xor     ebx, ebx
0x18008ce44  lea     rcx, [rsp+48h+lpBuffer]
0x18008ce49  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x18008ce4e  mov     eax, ebx
0x18008ce50  jmp     short loc_18008CE57
0x18008ce52  mov     eax, 8007139Fh
0x18008ce57  add     rsp, 40h
0x18008ce5b  pop     rbx
0x18008ce5c  retn
```
