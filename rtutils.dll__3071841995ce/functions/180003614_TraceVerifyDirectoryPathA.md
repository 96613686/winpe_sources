# TraceVerifyDirectoryPathA

- ea: `0x180003614`
- end: `0x180003737`
- name: `TraceVerifyDirectoryPathA`
- size: `291`
- prototype: `__int64 __fastcall(char *String1)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180005f70`

## callees

- `0x180002830`
- `0x180003614`
- `0x180003740`
- `0x180003774`
- `0x180003bb0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__strnicmp` at `0x1800036d9`
- `api-ms-win-crt-private-l1-1-0!_o__strnicmp` at `0x1800036f8`
- `api-ms-win-crt-private-l1-1-0!_o__strnicmp` at `0x1800036d9`
- `api-ms-win-crt-private-l1-1-0!_o__strnicmp` at `0x1800036f8`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryA` at `0x18000365a`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryA` at `0x18000365a`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesA` at `0x1800036a7`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesA` at `0x1800036a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003664`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003664`

## pseudocode

```c
HRESULT __fastcall TraceVerifyDirectoryPathA(char *String1)
{
  HRESULT result; // eax
  size_t v3; // rdx
  DWORD FileAttributesA; // eax
  size_t v5; // rdx
  size_t v6; // rbx
  size_t v7; // rbx
  size_t pcchLength; // [rsp+20h] [rbp-E0h] BYREF
  size_t v9; // [rsp+28h] [rbp-D8h] BYREF
  CHAR Buffer[272]; // [rsp+30h] [rbp-D0h] BYREF

  v9 = 0;
  pcchLength = 0;
  if ( !GetWindowsDirectoryA(Buffer, 0x104u) )
    return GetLastError();
  result = StringCchCatA(Buffer, 0x104u, "\\Tracing\\");
  if ( result < 0 )
    return (unsigned __int16)result;
  result = StringLengthWorkerA(Buffer, v3, &pcchLength);
  if ( result < 0 )
    return (unsigned __int16)result;
  FileAttributesA = GetFileAttributesA(Buffer);
  if ( FileAttributesA != -1 && (FileAttributesA & 0x400) != 0 )
    return 161;
  result = StringCchLengthA(String1, v5, &v9);
  if ( result < 0 )
    return (unsigned __int16)result;
  v6 = pcchLength;
  if ( _strnicmp(String1, Buffer, pcchLength) )
  {
    v7 = v6 - 1;
    if ( v9 == v7 )
      return _strnicmp(String1, Buffer, v7) != 0 ? 0xA1 : 0;
    return 161;
  }
  return 0;
}

```

## disassembly

```asm
0x180003614  mov     [rsp-8+arg_8], rbx
0x180003619  mov     [rsp-8+arg_10], rdi
0x18000361e  push    rbp
0x18000361f  lea     rbp, [rsp-50h]
0x180003624  sub     rsp, 150h
0x18000362b  mov     rax, cs:__security_cookie
0x180003632  xor     rax, rsp
0x180003635  mov     [rbp+50h+var_10], rax
0x180003639  mov     rdi, rcx
0x18000363c  mov     [rsp+150h+var_128], 0
0x180003645  mov     ebx, 104h
0x18000364a  mov     [rsp+150h+pcchLength], 0
0x180003653  mov     edx, ebx; uSize
0x180003655  lea     rcx, [rsp+150h+Buffer]; lpBuffer
0x18000365a  call    cs:__imp_GetWindowsDirectoryA
0x180003660  test    eax, eax
0x180003662  jnz     short loc_18000366F
0x180003664  call    cs:__imp_GetLastError
0x18000366a  jmp     loc_180003716
0x18000366f  lea     r8, aTracing_0; "\\Tracing\\"
0x180003676  mov     rdx, rbx; cchDest
0x180003679  lea     rcx, [rsp+150h+Buffer]; pszDest
0x18000367e  call    StringCchCatA
0x180003683  test    eax, eax
0x180003685  jns     short loc_18000368F
0x180003687  movzx   eax, ax
0x18000368a  jmp     loc_180003716
0x18000368f  lea     r8, [rsp+150h+pcchLength]; pcchLength
0x180003694  lea     rcx, [rsp+150h+Buffer]; psz
0x180003699  call    StringLengthWorkerA
0x18000369e  test    eax, eax
0x1800036a0  js      short loc_180003687
0x1800036a2  lea     rcx, [rsp+150h+Buffer]; lpFileName
0x1800036a7  call    cs:__imp_GetFileAttributesA
0x1800036ad  cmp     eax, 0FFFFFFFFh
0x1800036b0  jz      short loc_1800036B8
0x1800036b2  bt      eax, 0Ah
0x1800036b6  jb      short loc_18000370D
0x1800036b8  lea     r8, [rsp+150h+var_128]; pcchLength
0x1800036bd  mov     rcx, rdi; psz
0x1800036c0  call    StringCchLengthA
0x1800036c5  test    eax, eax
0x1800036c7  js      short loc_180003687
0x1800036c9  mov     rbx, [rsp+150h+pcchLength]
0x1800036ce  lea     rdx, [rsp+150h+Buffer]; String2
0x1800036d3  mov     r8, rbx; MaxCount
0x1800036d6  mov     rcx, rdi; String1
0x1800036d9  call    cs:__imp__strnicmp
0x1800036df  test    eax, eax
0x1800036e1  jz      short loc_180003714
0x1800036e3  dec     rbx
0x1800036e6  cmp     [rsp+150h+var_128], rbx
0x1800036eb  jnz     short loc_18000370D
0x1800036ed  mov     r8, rbx; MaxCount
0x1800036f0  lea     rdx, [rsp+150h+Buffer]; String2
0x1800036f5  mov     rcx, rdi; String1
0x1800036f8  call    cs:__imp__strnicmp
0x1800036fe  xor     ecx, ecx
0x180003700  sub     ecx, eax
0x180003702  neg     ecx
0x180003704  sbb     eax, eax
0x180003706  and     eax, 0A1h
0x18000370b  jmp     short loc_180003716
0x18000370d  mov     eax, 0A1h
0x180003712  jmp     short loc_180003716
0x180003714  xor     eax, eax
0x180003716  mov     rcx, [rbp+50h+var_10]
0x18000371a  xor     rcx, rsp; StackCookie
0x18000371d  call    __security_check_cookie
0x180003722  lea     r11, [rsp+150h+var_s0]
0x18000372a  mov     rbx, [r11+18h]
0x18000372e  mov     rdi, [r11+20h]
0x180003732  mov     rsp, r11
0x180003735  pop     rbp
0x180003736  retn
```
