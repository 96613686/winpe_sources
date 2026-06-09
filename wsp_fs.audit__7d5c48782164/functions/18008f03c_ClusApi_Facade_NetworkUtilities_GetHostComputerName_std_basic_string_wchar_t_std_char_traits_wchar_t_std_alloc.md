# ClusApi::Facade::NetworkUtilities::GetHostComputerName(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &)

- ea: `0x18008f03c`
- end: `0x18008f108`
- name: `?GetHostComputerName@NetworkUtilities@Facade@ClusApi@@SAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `204`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180037430`

## callees

- `0x180010b90`
- `0x180014c94`
- `0x180026588`
- `0x18008f03c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008f06a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008f07d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008f0c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008f06a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008f07d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008f0c2`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18008f056`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18008f0b2`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18008f056`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18008f0b2`

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
    std::vector<wchar_t>::vector<wchar_t>(lpBuffer);
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
0x18008f03c  push    rbx
0x18008f03e  sub     rsp, 40h
0x18008f042  mov     rbx, rcx
0x18008f045  mov     [rsp+48h+nSize], 0
0x18008f04d  lea     r8, [rsp+48h+nSize]; nSize
0x18008f052  xor     edx, edx; lpBuffer
0x18008f054  xor     ecx, ecx; NameType
0x18008f056  call    cs:__imp_GetComputerNameExW
0x18008f05d  nop     dword ptr [rax+rax+00h]
0x18008f062  test    eax, eax
0x18008f064  jnz     loc_18008F0FC
0x18008f06a  call    cs:__imp_GetLastError
0x18008f071  nop     dword ptr [rax+rax+00h]
0x18008f076  cmp     eax, 0EAh
0x18008f07b  jz      short loc_18008F097
0x18008f07d  call    cs:__imp_GetLastError
0x18008f084  nop     dword ptr [rax+rax+00h]
0x18008f089  test    eax, eax
0x18008f08b  jle     short loc_18008F101
0x18008f08d  movzx   eax, ax
0x18008f090  or      eax, 80070000h
0x18008f095  jmp     short loc_18008F101
0x18008f097  mov     edx, [rsp+48h+nSize]
0x18008f09b  lea     rcx, [rsp+48h+lpBuffer]
0x18008f0a0  call    ??0?$vector@_WV?$allocator@_W@std@@@std@@QEAA@_KAEBV?$allocator@_W@1@@Z; std::vector<wchar_t>::vector<wchar_t>(unsigned __int64,std::allocator<wchar_t> const &)
0x18008f0a5  nop
0x18008f0a6  lea     r8, [rsp+48h+nSize]; nSize
0x18008f0ab  mov     rdx, [rsp+48h+lpBuffer]; lpBuffer
0x18008f0b0  xor     ecx, ecx; NameType
0x18008f0b2  call    cs:__imp_GetComputerNameExW
0x18008f0b9  nop     dword ptr [rax+rax+00h]
0x18008f0be  test    eax, eax
0x18008f0c0  jnz     short loc_18008F0DF
0x18008f0c2  call    cs:__imp_GetLastError
0x18008f0c9  nop     dword ptr [rax+rax+00h]
0x18008f0ce  mov     ebx, eax
0x18008f0d0  test    eax, eax
0x18008f0d2  jle     short loc_18008F0EE
0x18008f0d4  movzx   ebx, ax
0x18008f0d7  or      ebx, 80070000h
0x18008f0dd  jmp     short loc_18008F0EE
0x18008f0df  mov     rdx, [rsp+48h+lpBuffer]
0x18008f0e4  mov     rcx, rbx
0x18008f0e7  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x18008f0ec  xor     ebx, ebx
0x18008f0ee  lea     rcx, [rsp+48h+lpBuffer]
0x18008f0f3  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x18008f0f8  mov     eax, ebx
0x18008f0fa  jmp     short loc_18008F101
0x18008f0fc  mov     eax, 8007139Fh
0x18008f101  add     rsp, 40h
0x18008f105  pop     rbx
0x18008f106  retn
```
