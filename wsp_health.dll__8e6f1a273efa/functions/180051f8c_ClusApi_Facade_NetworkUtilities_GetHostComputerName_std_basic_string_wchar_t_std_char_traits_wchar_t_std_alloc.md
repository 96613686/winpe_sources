# ClusApi::Facade::NetworkUtilities::GetHostComputerName(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &)

- ea: `0x180051f8c`
- end: `0x180052058`
- name: `?GetHostComputerName@NetworkUtilities@Facade@ClusApi@@SAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `204`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800335f0`

## callees

- `0x18000f89c`
- `0x180013864`
- `0x18002274c`
- `0x180051f8c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051fba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051fcd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052012`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051fba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051fcd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052012`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180051fa6`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180052002`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180051fa6`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180052002`

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
      std::wstring::assign(a1, lpBuffer[0]);
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
0x180051f8c  push    rbx
0x180051f8e  sub     rsp, 40h
0x180051f92  mov     rbx, rcx
0x180051f95  mov     [rsp+48h+nSize], 0
0x180051f9d  lea     r8, [rsp+48h+nSize]; nSize
0x180051fa2  xor     edx, edx; lpBuffer
0x180051fa4  xor     ecx, ecx; NameType
0x180051fa6  call    cs:__imp_GetComputerNameExW
0x180051fad  nop     dword ptr [rax+rax+00h]
0x180051fb2  test    eax, eax
0x180051fb4  jnz     loc_18005204C
0x180051fba  call    cs:__imp_GetLastError
0x180051fc1  nop     dword ptr [rax+rax+00h]
0x180051fc6  cmp     eax, 0EAh
0x180051fcb  jz      short loc_180051FE7
0x180051fcd  call    cs:__imp_GetLastError
0x180051fd4  nop     dword ptr [rax+rax+00h]
0x180051fd9  test    eax, eax
0x180051fdb  jle     short loc_180052051
0x180051fdd  movzx   eax, ax
0x180051fe0  or      eax, 80070000h
0x180051fe5  jmp     short loc_180052051
0x180051fe7  mov     edx, [rsp+48h+nSize]
0x180051feb  lea     rcx, [rsp+48h+lpBuffer]
0x180051ff0  call    ??0?$vector@_WV?$allocator@_W@std@@@std@@QEAA@_KAEBV?$allocator@_W@1@@Z; std::vector<wchar_t>::vector<wchar_t>(unsigned __int64,std::allocator<wchar_t> const &)
0x180051ff5  nop
0x180051ff6  lea     r8, [rsp+48h+nSize]; nSize
0x180051ffb  mov     rdx, [rsp+48h+lpBuffer]; lpBuffer
0x180052000  xor     ecx, ecx; NameType
0x180052002  call    cs:__imp_GetComputerNameExW
0x180052009  nop     dword ptr [rax+rax+00h]
0x18005200e  test    eax, eax
0x180052010  jnz     short loc_18005202F
0x180052012  call    cs:__imp_GetLastError
0x180052019  nop     dword ptr [rax+rax+00h]
0x18005201e  mov     ebx, eax
0x180052020  test    eax, eax
0x180052022  jle     short loc_18005203E
0x180052024  movzx   ebx, ax
0x180052027  or      ebx, 80070000h
0x18005202d  jmp     short loc_18005203E
0x18005202f  mov     rdx, [rsp+48h+lpBuffer]
0x180052034  mov     rcx, rbx
0x180052037  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x18005203c  xor     ebx, ebx
0x18005203e  lea     rcx, [rsp+48h+lpBuffer]
0x180052043  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x180052048  mov     eax, ebx
0x18005204a  jmp     short loc_180052051
0x18005204c  mov     eax, 8007139Fh
0x180052051  add     rsp, 40h
0x180052055  pop     rbx
0x180052056  retn
```
