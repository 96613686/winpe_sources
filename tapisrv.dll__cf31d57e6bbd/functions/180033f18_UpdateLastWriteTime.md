# UpdateLastWriteTime

- ea: `0x180033f18`
- end: `0x180034029`
- name: `UpdateLastWriteTime`
- size: `273`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `4`
- callee_count: `4`
- tags: `file_ops, installer_update`

## callers

- `0x18002d6d0`
- `0x1800312ec`
- `0x180032910`
- `0x1800329f0`

## callees

- `0x180001600`
- `0x180001f50`
- `0x18001c740`
- `0x180033f18`

## import_xrefs

- `KERNEL32!GetSystemWindowsDirectoryW` at `0x180033f6a`
- `KERNEL32!GetSystemWindowsDirectoryW` at `0x180033f6a`
- `KERNEL32!GetFileAttributesExW` at `0x180033fc6`
- `KERNEL32!GetFileAttributesExW` at `0x180033fc6`
- `KERNEL32!GetLastError` at `0x180033fd0`
- `KERNEL32!GetLastError` at `0x180033fd0`

## pseudocode

```c
__int64 __fastcall UpdateLastWriteTime(int a1)
{
  unsigned int v2; // ecx
  __int64 *v3; // rbx
  DWORD LastError; // eax
  int v5; // edx
  __int128 FileInformation; // [rsp+20h] [rbp-278h] BYREF
  __int128 v8; // [rsp+30h] [rbp-268h]
  int v9; // [rsp+40h] [rbp-258h]
  WCHAR Buffer[280]; // [rsp+50h] [rbp-248h] BYREF

  memset_0(Buffer, 0, 0x228u);
  FileInformation = 0;
  v9 = 0;
  v8 = 0;
  if ( !GetSystemWindowsDirectoryW(Buffer, 0x104u) )
    return (unsigned int)-2147483576;
  StringCbCatW(Buffer, 0x228u, L"\\");
  StringCbCatW(Buffer, 0x228u, gszFileName);
  v3 = &gftLineLastWrite;
  if ( !a1 )
    v3 = &gftPhoneLastWrite;
  if ( !GetFileAttributesExW(Buffer, GetFileExInfoStandard, &FileInformation) )
  {
    LastError = GetLastError();
    v2 = 1;
    if ( LastError - 2 <= 1 )
    {
      *v3 = 0;
      return v2;
    }
    return (unsigned int)-2147483576;
  }
  v5 = DWORD1(v8);
  if ( DWORD2(v8) > *((_DWORD *)v3 + 1) || (v2 = 0, DWORD1(v8) > *(_DWORD *)v3) )
  {
    *((_DWORD *)v3 + 1) = DWORD2(v8);
    v2 = 1;
    *(_DWORD *)v3 = v5;
  }
  return v2;
}

```

## disassembly

```asm
0x180033f18  mov     [rsp+arg_0], rbx
0x180033f1d  push    rdi
0x180033f1e  sub     rsp, 290h
0x180033f25  mov     rax, cs:__security_cookie
0x180033f2c  xor     rax, rsp
0x180033f2f  mov     [rsp+298h+var_18], rax
0x180033f37  mov     edi, ecx
0x180033f39  mov     ebx, 228h
0x180033f3e  mov     r8d, ebx; Size
0x180033f41  lea     rcx, [rsp+298h+Buffer]; void *
0x180033f46  xor     edx, edx; Val
0x180033f48  call    memset_0
0x180033f4d  xorps   xmm0, xmm0
0x180033f50  lea     rcx, [rsp+298h+Buffer]; lpBuffer
0x180033f55  xor     eax, eax
0x180033f57  mov     edx, 104h; uSize
0x180033f5c  movups  [rsp+298h+FileInformation], xmm0
0x180033f61  mov     [rsp+298h+var_258], eax
0x180033f65  movups  [rsp+298h+var_268], xmm0
0x180033f6a  call    cs:__imp_GetSystemWindowsDirectoryW
0x180033f70  test    eax, eax
0x180033f72  jnz     short loc_180033F7E
0x180033f74  mov     ecx, 80000048h
0x180033f79  jmp     loc_180034006
0x180033f7e  lea     r8, pszSrc; "\\"
0x180033f85  mov     rdx, rbx; cbDest
0x180033f88  lea     rcx, [rsp+298h+Buffer]; pszDest
0x180033f8d  call    StringCbCatW
0x180033f92  lea     r8, gszFileName; "..\\TAPI\\tsec.ini"
0x180033f99  mov     rdx, rbx; cbDest
0x180033f9c  lea     rcx, [rsp+298h+Buffer]; pszDest
0x180033fa1  call    StringCbCatW
0x180033fa6  lea     rax, gftPhoneLastWrite
0x180033fad  test    edi, edi
0x180033faf  lea     rbx, gftLineLastWrite
0x180033fb6  cmovz   rbx, rax
0x180033fba  lea     r8, [rsp+298h+FileInformation]; lpFileInformation
0x180033fbf  xor     edx, edx; fInfoLevelId
0x180033fc1  lea     rcx, [rsp+298h+Buffer]; lpFileName
0x180033fc6  call    cs:__imp_GetFileAttributesExW
0x180033fcc  test    eax, eax
0x180033fce  jnz     short loc_180033FE9
0x180033fd0  call    cs:__imp_GetLastError
0x180033fd6  add     eax, 0FFFFFFFEh
0x180033fd9  mov     ecx, 1
0x180033fde  cmp     eax, ecx
0x180033fe0  ja      short loc_180033F74
0x180033fe2  xor     eax, eax
0x180033fe4  mov     [rbx], rax
0x180033fe7  jmp     short loc_180034006
0x180033fe9  mov     eax, dword ptr [rsp+298h+var_268+8]
0x180033fed  mov     edx, dword ptr [rsp+298h+var_268+4]
0x180033ff1  cmp     eax, [rbx+4]
0x180033ff4  ja      short loc_180033FFC
0x180033ff6  xor     ecx, ecx
0x180033ff8  cmp     edx, [rbx]
0x180033ffa  jbe     short loc_180034006
0x180033ffc  mov     [rbx+4], eax
0x180033fff  mov     ecx, 1
0x180034004  mov     [rbx], edx
0x180034006  mov     eax, ecx
0x180034008  mov     rcx, [rsp+298h+var_18]
0x180034010  xor     rcx, rsp; StackCookie
0x180034013  call    __security_check_cookie
0x180034018  mov     rbx, [rsp+298h+arg_0]
0x180034020  add     rsp, 290h
0x180034027  pop     rdi
0x180034028  retn
```
