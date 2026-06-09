# IsSafeMode(int *)

- ea: `0x180021f9c`
- end: `0x18002206f`
- name: `?IsSafeMode@@YAJPEAH@Z`
- size: `211`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180022388`
- `0x180022720`

## callees

- `0x180004288`
- `0x180021f9c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180022027`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180022027`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180022056`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180022056`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180021fec`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180021fec`

## pseudocode

```c
__int64 __fastcall IsSafeMode(int *a1)
{
  BOOL v2; // ebx
  DWORD cbData; // [rsp+60h] [rbp+28h] BYREF
  DWORD Type; // [rsp+68h] [rbp+30h] BYREF
  int Data; // [rsp+70h] [rbp+38h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+40h] BYREF

  hKey = 0;
  cbData = 0;
  v2 = 0;
  Data = 0;
  Type = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\SafeBoot\\Option", 0, 1u, &hKey) )
  {
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"OptionValue", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 )
      v2 = Data != 0;
  }
  *a1 = v2;
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x180021f9c  push    rbp
0x180021f9e  push    rbx
0x180021f9f  push    rdi
0x180021fa0  push    r14
0x180021fa2  mov     rbp, rsp
0x180021fa5  sub     rsp, 38h
0x180021fa9  mov     rdi, rcx
0x180021fac  mov     [rbp+hKey], 0
0x180021fb4  lea     rax, [rbp+hKey]
0x180021fb8  mov     [rbp+cbData], 0
0x180021fbf  xor     ebx, ebx
0x180021fc1  mov     [rbp+Data], 0
0x180021fc8  xor     r8d, r8d; ulOptions
0x180021fcb  mov     [rbp+Type], 0
0x180021fd2  lea     rdx, SubKey; "System\\CurrentControlSet\\Control\\Saf"...
0x180021fd9  mov     [rsp+38h+phkResult], rax; phkResult
0x180021fde  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180021fe5  lea     r14d, [rbx+1]
0x180021fe9  mov     r9d, r14d; samDesired
0x180021fec  call    cs:__imp_RegOpenKeyExW
0x180021ff3  nop     dword ptr [rax+rax+00h]
0x180021ff8  test    eax, eax
0x180021ffa  jnz     short loc_180022044
0x180021ffc  mov     rcx, [rbp+hKey]; hKey
0x180022000  lea     rax, [rbp+cbData]
0x180022004  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180022009  lea     r9, [rbp+Type]; lpType
0x18002200d  lea     rax, [rbp+Data]
0x180022011  mov     [rbp+cbData], 4
0x180022018  xor     r8d, r8d; lpReserved
0x18002201b  mov     [rsp+38h+phkResult], rax; lpData
0x180022020  lea     rdx, ValueName; "OptionValue"
0x180022027  call    cs:__imp_RegQueryValueExW
0x18002202e  nop     dword ptr [rax+rax+00h]
0x180022033  test    eax, eax
0x180022035  jnz     short loc_180022044
0x180022037  cmp     [rbp+Type], 4
0x18002203b  jnz     short loc_180022044
0x18002203d  cmp     [rbp+Data], ebx
0x180022040  cmovnz  ebx, r14d
0x180022044  mov     [rdi], ebx
0x180022046  xor     ecx, ecx
0x180022048  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002204d  mov     rcx, [rbp+hKey]; hKey
0x180022051  test    rcx, rcx
0x180022054  jz      short loc_180022062
0x180022056  call    cs:__imp_RegCloseKey
0x18002205d  nop     dword ptr [rax+rax+00h]
0x180022062  xor     eax, eax
0x180022064  add     rsp, 38h
0x180022068  pop     r14
0x18002206a  pop     rdi
0x18002206b  pop     rbx
0x18002206c  pop     rbp
0x18002206d  retn
```
