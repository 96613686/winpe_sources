# ClusApi::Facade::NetworkUtilities::GetHostComputerName(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &)

- ea: `0x180050534`
- end: `0x1800505dd`
- name: `?GetHostComputerName@NetworkUtilities@Facade@ClusApi@@SAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `169`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180032540`

## callees

- `0x18000f3e8`
- `0x1800131a0`
- `0x180021b50`
- `0x180050534`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050558`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050565`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005059e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050558`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050565`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005059e`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18005054e`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180050594`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18005054e`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180050594`

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
0x180050534  push    rbx
0x180050536  sub     rsp, 40h
0x18005053a  mov     rbx, rcx
0x18005053d  mov     [rsp+48h+nSize], 0
0x180050545  lea     r8, [rsp+48h+nSize]; nSize
0x18005054a  xor     edx, edx; lpBuffer
0x18005054c  xor     ecx, ecx; NameType
0x18005054e  call    cs:__imp_GetComputerNameExW
0x180050554  test    eax, eax
0x180050556  jnz     short loc_1800505D2
0x180050558  call    cs:__imp_GetLastError
0x18005055e  cmp     eax, 0EAh
0x180050563  jz      short loc_180050579
0x180050565  call    cs:__imp_GetLastError
0x18005056b  test    eax, eax
0x18005056d  jle     short loc_1800505D7
0x18005056f  movzx   eax, ax
0x180050572  or      eax, 80070000h
0x180050577  jmp     short loc_1800505D7
0x180050579  mov     edx, [rsp+48h+nSize]
0x18005057d  lea     rcx, [rsp+48h+lpBuffer]
0x180050582  call    ??0?$vector@_WV?$allocator@_W@std@@@std@@QEAA@_KAEBV?$allocator@_W@1@@Z; std::vector<wchar_t>::vector<wchar_t>(unsigned __int64,std::allocator<wchar_t> const &)
0x180050587  nop
0x180050588  lea     r8, [rsp+48h+nSize]; nSize
0x18005058d  mov     rdx, [rsp+48h+lpBuffer]; lpBuffer
0x180050592  xor     ecx, ecx; NameType
0x180050594  call    cs:__imp_GetComputerNameExW
0x18005059a  test    eax, eax
0x18005059c  jnz     short loc_1800505B5
0x18005059e  call    cs:__imp_GetLastError
0x1800505a4  mov     ebx, eax
0x1800505a6  test    eax, eax
0x1800505a8  jle     short loc_1800505C4
0x1800505aa  movzx   ebx, ax
0x1800505ad  or      ebx, 80070000h
0x1800505b3  jmp     short loc_1800505C4
0x1800505b5  mov     rdx, [rsp+48h+lpBuffer]
0x1800505ba  mov     rcx, rbx
0x1800505bd  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x1800505c2  xor     ebx, ebx
0x1800505c4  lea     rcx, [rsp+48h+lpBuffer]
0x1800505c9  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x1800505ce  mov     eax, ebx
0x1800505d0  jmp     short loc_1800505D7
0x1800505d2  mov     eax, 8007139Fh
0x1800505d7  add     rsp, 40h
0x1800505db  pop     rbx
0x1800505dc  retn
```
