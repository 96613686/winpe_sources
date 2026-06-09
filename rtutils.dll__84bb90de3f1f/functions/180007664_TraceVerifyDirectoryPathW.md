# TraceVerifyDirectoryPathW

- ea: `0x180007664`
- end: `0x180007790`
- name: `TraceVerifyDirectoryPathW`
- size: `300`
- prototype: `HRESULT __fastcall(STRSAFE_PCNZWCH psz)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180006c6c`

## callees

- `0x180003bb0`
- `0x180004a2c`
- `0x180006bf4`
- `0x180006c24`
- `0x180007664`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18000772f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18000774e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18000772f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18000774e`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x1800076b0`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x1800076b0`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800076fd`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800076fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800076ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800076ba`

## pseudocode

```c
HRESULT __fastcall TraceVerifyDirectoryPathW(STRSAFE_PCNZWCH psz)
{
  HRESULT result; // eax
  size_t v3; // rdx
  DWORD FileAttributesW; // eax
  size_t v5; // rdx
  size_t v6; // rbx
  size_t v7; // rbx
  size_t pcchLength; // [rsp+20h] [rbp-E0h] BYREF
  size_t v9; // [rsp+28h] [rbp-D8h] BYREF
  WCHAR Buffer[264]; // [rsp+30h] [rbp-D0h] BYREF

  v9 = 0;
  pcchLength = 0;
  if ( !GetWindowsDirectoryW(Buffer, 0x104u) )
    return GetLastError();
  result = StringCchCatW(Buffer, 0x104u, L"\\Tracing\\");
  if ( result < 0 )
    return (unsigned __int16)result;
  result = StringLengthWorkerW(Buffer, v3, &pcchLength);
  if ( result < 0 )
    return (unsigned __int16)result;
  FileAttributesW = GetFileAttributesW(Buffer);
  if ( FileAttributesW != -1 && (FileAttributesW & 0x400) != 0 )
    return 161;
  result = StringCchLengthW(psz, v5, &v9);
  if ( result < 0 )
    return (unsigned __int16)result;
  v6 = pcchLength;
  if ( (unsigned int)_o__wcsnicmp(psz, Buffer, pcchLength) )
  {
    v7 = v6 - 1;
    if ( v9 == v7 )
      return (unsigned int)_o__wcsnicmp(psz, Buffer, v7) != 0 ? 0xA1 : 0;
    return 161;
  }
  return 0;
}

```

## disassembly

```asm
0x180007664  mov     [rsp-8+arg_8], rbx
0x180007669  mov     [rsp-8+arg_10], rdi
0x18000766e  push    rbp
0x18000766f  lea     rbp, [rsp-150h]
0x180007677  sub     rsp, 250h
0x18000767e  mov     rax, cs:__security_cookie
0x180007685  xor     rax, rsp
0x180007688  mov     [rbp+150h+var_10], rax
0x18000768f  mov     rdi, rcx
0x180007692  mov     [rsp+250h+var_228], 0
0x18000769b  mov     ebx, 104h
0x1800076a0  mov     [rsp+250h+pcchLength], 0
0x1800076a9  mov     edx, ebx; uSize
0x1800076ab  lea     rcx, [rsp+250h+Buffer]; lpBuffer
0x1800076b0  call    cs:__imp_GetWindowsDirectoryW
0x1800076b6  test    eax, eax
0x1800076b8  jnz     short loc_1800076C5
0x1800076ba  call    cs:__imp_GetLastError
0x1800076c0  jmp     loc_18000776C
0x1800076c5  lea     r8, aTracing; "\\Tracing\\"
0x1800076cc  mov     rdx, rbx; cchDest
0x1800076cf  lea     rcx, [rsp+250h+Buffer]; pszDest
0x1800076d4  call    StringCchCatW
0x1800076d9  test    eax, eax
0x1800076db  jns     short loc_1800076E5
0x1800076dd  movzx   eax, ax
0x1800076e0  jmp     loc_18000776C
0x1800076e5  lea     r8, [rsp+250h+pcchLength]; pcchLength
0x1800076ea  lea     rcx, [rsp+250h+Buffer]; psz
0x1800076ef  call    StringLengthWorkerW
0x1800076f4  test    eax, eax
0x1800076f6  js      short loc_1800076DD
0x1800076f8  lea     rcx, [rsp+250h+Buffer]; lpFileName
0x1800076fd  call    cs:__imp_GetFileAttributesW
0x180007703  cmp     eax, 0FFFFFFFFh
0x180007706  jz      short loc_18000770E
0x180007708  bt      eax, 0Ah
0x18000770c  jb      short loc_180007763
0x18000770e  lea     r8, [rsp+250h+var_228]; pcchLength
0x180007713  mov     rcx, rdi; psz
0x180007716  call    StringCchLengthW
0x18000771b  test    eax, eax
0x18000771d  js      short loc_1800076DD
0x18000771f  mov     rbx, [rsp+250h+pcchLength]
0x180007724  lea     rdx, [rsp+250h+Buffer]
0x180007729  mov     r8, rbx
0x18000772c  mov     rcx, rdi
0x18000772f  call    cs:__imp__o__wcsnicmp
0x180007735  test    eax, eax
0x180007737  jz      short loc_18000776A
0x180007739  dec     rbx
0x18000773c  cmp     [rsp+250h+var_228], rbx
0x180007741  jnz     short loc_180007763
0x180007743  mov     r8, rbx
0x180007746  lea     rdx, [rsp+250h+Buffer]
0x18000774b  mov     rcx, rdi
0x18000774e  call    cs:__imp__o__wcsnicmp
0x180007754  xor     ecx, ecx
0x180007756  sub     ecx, eax
0x180007758  neg     ecx
0x18000775a  sbb     eax, eax
0x18000775c  and     eax, 0A1h
0x180007761  jmp     short loc_18000776C
0x180007763  mov     eax, 0A1h
0x180007768  jmp     short loc_18000776C
0x18000776a  xor     eax, eax
0x18000776c  mov     rcx, [rbp+150h+var_10]
0x180007773  xor     rcx, rsp; StackCookie
0x180007776  call    __security_check_cookie
0x18000777b  lea     r11, [rsp+250h+var_s0]
0x180007783  mov     rbx, [r11+18h]
0x180007787  mov     rdi, [r11+20h]
0x18000778b  mov     rsp, r11
0x18000778e  pop     rbp
0x18000778f  retn
```
