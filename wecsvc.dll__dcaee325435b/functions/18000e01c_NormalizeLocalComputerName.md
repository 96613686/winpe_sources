# NormalizeLocalComputerName

- ea: `0x18000e01c`
- end: `0x18000e12c`
- name: `NormalizeLocalComputerName`
- size: `272`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x180007844`

## callees

- `0x180006334`
- `0x18000669c`
- `0x18000e01c`
- `0x1800112e8`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000e041`
- `msvcrt!_wcsicmp` at `0x18000e041`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e0a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e0a1`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18000e092`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18000e0c7`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18000e092`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18000e0c7`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x18000e0fd`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x18000e0fd`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall NormalizeLocalComputerName(const wchar_t *a1, __int64 a2)
{
  LPWSTR v4; // rdi
  const wchar_t *v5; // rdx
  LPWSTR v6; // rdi
  BOOL ComputerNameW; // eax
  LPWSTR lpBuffer[2]; // [rsp+20h] [rbp-28h] BYREF
  __int64 v9; // [rsp+30h] [rbp-18h]
  DWORD nSize; // [rsp+70h] [rbp+28h] BYREF

  if ( a1 && *a1 && _wcsicmp(a1, L"localhost") )
  {
    std::wstring::assign(a2, (__int64)a1);
  }
  else
  {
    *(_OWORD *)lpBuffer = 0;
    v9 = 0;
    std::vector<unsigned short>::resize(lpBuffer, 0x100u);
    v4 = lpBuffer[0];
    nSize = lpBuffer[1] - lpBuffer[0];
    if ( GetComputerNameExW(ComputerNameDnsFullyQualified, lpBuffer[0], &nSize) )
    {
      v5 = v4;
    }
    else if ( GetLastError() == 234
           && (std::vector<unsigned short>::resize(lpBuffer, nSize),
               GetComputerNameExW(ComputerNameDnsFullyQualified, lpBuffer[0], &nSize)) )
    {
      v5 = lpBuffer[0];
    }
    else
    {
      std::vector<unsigned short>::resize(lpBuffer, 0x10u);
      v6 = lpBuffer[0];
      nSize = lpBuffer[1] - lpBuffer[0];
      ComputerNameW = GetComputerNameW(lpBuffer[0], &nSize);
      v5 = v6;
      if ( !ComputerNameW )
        v5 = L"localhost";
    }
    std::wstring::assign(a2, (__int64)v5);
    std::vector<_WSMAN_OPTION>::~vector<_WSMAN_OPTION>((__int64)lpBuffer);
  }
}

```

## disassembly

```asm
0x18000e01c  push    rbp
0x18000e01e  push    rbx
0x18000e01f  push    rsi
0x18000e020  push    rdi
0x18000e021  mov     rbp, rsp
0x18000e024  sub     rsp, 48h
0x18000e028  mov     rbx, rdx
0x18000e02b  mov     rdi, rcx
0x18000e02e  xor     esi, esi
0x18000e030  test    rcx, rcx
0x18000e033  jz      short loc_18000E05B
0x18000e035  cmp     [rcx], si
0x18000e038  jz      short loc_18000E05B
0x18000e03a  lea     rdx, aLocalhost; "localhost"
0x18000e041  call    cs:__imp__wcsicmp
0x18000e047  test    eax, eax
0x18000e049  jz      short loc_18000E05B
0x18000e04b  mov     rdx, rdi
0x18000e04e  mov     rcx, rbx
0x18000e051  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18000e056  jmp     loc_18000E123
0x18000e05b  xorps   xmm0, xmm0
0x18000e05e  movdqu  xmmword ptr [rbp+lpBuffer], xmm0
0x18000e063  mov     [rbp+var_18], rsi
0x18000e067  mov     edx, 100h
0x18000e06c  lea     rcx, [rbp+lpBuffer]
0x18000e070  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18000e075  mov     rax, [rbp+lpBuffer+8]
0x18000e079  mov     rdi, [rbp+lpBuffer]
0x18000e07d  sub     rax, rdi
0x18000e080  sar     rax, 1
0x18000e083  mov     [rbp+nSize], eax
0x18000e086  lea     r8, [rbp+nSize]; nSize
0x18000e08a  mov     rdx, rdi; lpBuffer
0x18000e08d  mov     ecx, 3; NameType
0x18000e092  call    cs:__imp_GetComputerNameExW
0x18000e098  test    eax, eax
0x18000e09a  jz      short loc_18000E0A1
0x18000e09c  mov     rdx, rdi
0x18000e09f  jmp     short loc_18000E111
0x18000e0a1  call    cs:__imp_GetLastError
0x18000e0a7  cmp     eax, 0EAh
0x18000e0ac  jnz     short loc_18000E0D7
0x18000e0ae  mov     edx, [rbp+nSize]
0x18000e0b1  lea     rcx, [rbp+lpBuffer]
0x18000e0b5  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18000e0ba  lea     r8, [rbp+nSize]; nSize
0x18000e0be  mov     rdx, [rbp+lpBuffer]; lpBuffer
0x18000e0c2  mov     ecx, 3; NameType
0x18000e0c7  call    cs:__imp_GetComputerNameExW
0x18000e0cd  test    eax, eax
0x18000e0cf  jz      short loc_18000E0D7
0x18000e0d1  mov     rdx, [rbp+lpBuffer]
0x18000e0d5  jmp     short loc_18000E111
0x18000e0d7  mov     edx, 10h
0x18000e0dc  lea     rcx, [rbp+lpBuffer]
0x18000e0e0  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18000e0e5  mov     rax, [rbp+lpBuffer+8]
0x18000e0e9  mov     rdi, [rbp+lpBuffer]
0x18000e0ed  sub     rax, rdi
0x18000e0f0  sar     rax, 1
0x18000e0f3  mov     [rbp+nSize], eax
0x18000e0f6  lea     rdx, [rbp+nSize]; nSize
0x18000e0fa  mov     rcx, rdi; lpBuffer
0x18000e0fd  call    cs:__imp_GetComputerNameW
0x18000e103  test    eax, eax
0x18000e105  mov     rdx, rdi
0x18000e108  jnz     short loc_18000E111
0x18000e10a  lea     rdx, aLocalhost; "localhost"
0x18000e111  mov     rcx, rbx
0x18000e114  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18000e119  nop
0x18000e11a  lea     rcx, [rbp+lpBuffer]
0x18000e11e  call    ??1?$vector@U_WSMAN_OPTION@@V?$allocator@U_WSMAN_OPTION@@@std@@@std@@QEAA@XZ; std::vector<_WSMAN_OPTION>::~vector<_WSMAN_OPTION>(void)
0x18000e123  add     rsp, 48h
0x18000e127  pop     rdi
0x18000e128  pop     rsi
0x18000e129  pop     rbx
0x18000e12a  pop     rbp
0x18000e12b  retn
```
