# PfXpGetLayoutFilePath

- ea: `0x180019650`
- end: `0x1800197bb`
- name: `PfXpGetLayoutFilePath`
- size: `363`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180018ec0`

## callees

- `0x180019650`
- `0x180039f94`
- `0x18006f860`
- `0x1800b64c0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019790`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019790`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001977e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001977e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180019751`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180019751`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800196b0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800196b0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800196c8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800196c8`

## string_xrefs

- `0x180019768`: `LayoutFilePath`

## pseudocode

```c
__int64 __fastcall PfXpGetLayoutFilePath(LPVOID *a1, DWORD *a2)
{
  __int64 v2; // r9
  __int64 v3; // rbx
  DWORD v6; // ebx
  LPVOID v7; // rax
  unsigned int OptimalLayoutRegPath; // ebx
  HKEY hKey; // [rsp+50h] [rbp-248h] BYREF
  WCHAR SubKey[264]; // [rsp+60h] [rbp-238h] BYREF

  v2 = *(_QWORD *)&PfSvcGlobals;
  hKey = 0;
  v3 = -1;
  do
    ++v3;
  while ( *(_WORD *)(*(_QWORD *)&PfSvcGlobals + 2 * v3 + 888) );
  v6 = 2 * v3 + 24;
  if ( *a2 >= v6 )
  {
    v6 = *a2;
  }
  else
  {
    if ( *a1 )
      HeapFree(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, *a1);
    *a2 = 0;
    v7 = HeapAlloc(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, v6);
    *a1 = v7;
    if ( !v7 )
    {
      OptimalLayoutRegPath = 8;
      goto LABEL_13;
    }
    *a2 = v6;
    v2 = *(_QWORD *)&PfSvcGlobals;
  }
  StringCbPrintfW((STRSAFE_LPWSTR)*a1, v6, L"%s\\%s", v2 + 888, L"Layout.ini");
  OptimalLayoutRegPath = PfXpGetOptimalLayoutRegPath(SubKey);
  if ( !OptimalLayoutRegPath )
  {
    OptimalLayoutRegPath = RegCreateKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0, 0, 0xF003Fu, 0, &hKey, 0);
    if ( !OptimalLayoutRegPath )
      OptimalLayoutRegPath = RegSetValueExW(hKey, L"LayoutFilePath", 0, 1u, (const BYTE *)*a1, *a2);
  }
LABEL_13:
  if ( hKey )
    RegCloseKey(hKey);
  return OptimalLayoutRegPath;
}

```

## disassembly

```asm
0x180019650  mov     [rsp+arg_10], rbx
0x180019655  push    rbp
0x180019656  push    rsi
0x180019657  push    rdi
0x180019658  sub     rsp, 280h
0x18001965f  mov     rax, cs:__security_cookie
0x180019666  xor     rax, rsp
0x180019669  mov     [rsp+298h+var_28], rax
0x180019671  mov     r9, cs:PfSvcGlobals
0x180019678  xor     ebp, ebp
0x18001967a  mov     [rsp+298h+hKey], rbp
0x18001967f  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180019683  mov     rdi, rdx
0x180019686  mov     rsi, rcx
0x180019689  inc     rbx
0x18001968c  cmp     [r9+rbx*2+378h], bp
0x180019695  jnz     short loc_180019689
0x180019697  lea     ebx, ds:18h[rbx*2]
0x18001969e  cmp     [rdx], ebx
0x1800196a0  jnb     short loc_1800196E9
0x1800196a2  mov     r8, [rcx]; lpMem
0x1800196a5  test    r8, r8
0x1800196a8  jz      short loc_1800196B6
0x1800196aa  mov     rcx, [r9+58h]; hHeap
0x1800196ae  xor     edx, edx; dwFlags
0x1800196b0  call    cs:__imp_HeapFree
0x1800196b6  mov     [rdi], ebp
0x1800196b8  xor     edx, edx; dwFlags
0x1800196ba  mov     rcx, cs:PfSvcGlobals
0x1800196c1  mov     r8d, ebx; dwBytes
0x1800196c4  mov     rcx, [rcx+58h]; hHeap
0x1800196c8  call    cs:__imp_HeapAlloc
0x1800196ce  mov     [rsi], rax
0x1800196d1  test    rax, rax
0x1800196d4  jnz     short loc_1800196DE
0x1800196d6  lea     ebx, [rax+8]
0x1800196d9  jmp     loc_180019786
0x1800196de  mov     [rdi], ebx
0x1800196e0  mov     r9, cs:PfSvcGlobals
0x1800196e7  jmp     short loc_1800196EB
0x1800196e9  mov     ebx, [rdx]
0x1800196eb  mov     rcx, [rsi]; pszDest
0x1800196ee  lea     rax, aLayoutIni; "Layout.ini"
0x1800196f5  add     r9, 378h
0x1800196fc  mov     edx, ebx; cbDest
0x1800196fe  lea     r8, aSS; "%s\\%s"
0x180019705  mov     qword ptr [rsp+298h+dwOptions], rax
0x18001970a  call    StringCbPrintfW
0x18001970f  lea     rcx, [rsp+298h+SubKey]; pszDest
0x180019714  call    PfXpGetOptimalLayoutRegPath
0x180019719  mov     ebx, eax
0x18001971b  test    eax, eax
0x18001971d  jnz     short loc_180019786
0x18001971f  mov     [rsp+298h+lpdwDisposition], rbp; lpdwDisposition
0x180019724  lea     rax, [rsp+298h+hKey]
0x180019729  mov     [rsp+298h+phkResult], rax; phkResult
0x18001972e  lea     rdx, [rsp+298h+SubKey]; lpSubKey
0x180019733  mov     [rsp+298h+lpSecurityAttributes], rbp; lpSecurityAttributes
0x180019738  xor     r9d, r9d; lpClass
0x18001973b  mov     [rsp+298h+samDesired], 0F003Fh; samDesired
0x180019743  xor     r8d, r8d; Reserved
0x180019746  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001974d  mov     [rsp+298h+dwOptions], ebp; dwOptions
0x180019751  call    cs:__imp_RegCreateKeyExW
0x180019757  mov     ebx, eax
0x180019759  test    eax, eax
0x18001975b  jnz     short loc_180019786
0x18001975d  mov     eax, [rdi]
0x18001975f  lea     r9d, [rbx+1]; dwType
0x180019763  mov     rcx, [rsp+298h+hKey]; hKey
0x180019768  lea     rdx, aLayoutfilepath; "LayoutFilePath"
0x18001976f  mov     [rsp+298h+samDesired], eax; cbData
0x180019773  xor     r8d, r8d; Reserved
0x180019776  mov     rax, [rsi]
0x180019779  mov     qword ptr [rsp+298h+dwOptions], rax; lpData
0x18001977e  call    cs:__imp_RegSetValueExW
0x180019784  mov     ebx, eax
0x180019786  mov     rcx, [rsp+298h+hKey]; hKey
0x18001978b  test    rcx, rcx
0x18001978e  jz      short loc_180019796
0x180019790  call    cs:__imp_RegCloseKey
0x180019796  mov     eax, ebx
0x180019798  mov     rcx, [rsp+298h+var_28]
0x1800197a0  xor     rcx, rsp; StackCookie
0x1800197a3  call    __security_check_cookie
0x1800197a8  mov     rbx, [rsp+298h+arg_10]
0x1800197b0  add     rsp, 280h
0x1800197b7  pop     rdi
0x1800197b8  pop     rsi
0x1800197b9  pop     rbp
0x1800197ba  retn
```
