# GetPolicyEnabledProviderListp(TimeProvider * *,TimeProvider * *)

- ea: `0x180008520`
- end: `0x180008856`
- name: `?GetPolicyEnabledProviderListp@@YAJPEAPEAUTimeProvider@@0@Z`
- size: `822`
- prototype: `__int64 __fastcall(struct TimeProvider **, struct TimeProvider **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800073f0`

## callees

- `0x180008520`
- `0x180009238`
- `0x18000bde0`
- `0x180018138`
- `0x18001d9a0`
- `0x18003d270`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000879b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800087aa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000879b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800087aa`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800086e0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008719`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800086e0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008719`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800085a0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008645`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800085a0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008645`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008774`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800087ed`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008803`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008774`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800087ed`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008803`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800085ea`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800085ea`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180008695`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180008695`

## string_xrefs

- `0x18000861c`: `ReadConfig (policy): Found provider '%s':\n`
- `0x1800086cc`: `ReadConfig (policy):   '%s'=0x%08X\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=9 #try_helpers=1
__int64 __fastcall GetPolicyEnabledProviderListp(struct TimeProvider **a1, struct TimeProvider **a2)
{
  struct TimeProvider *v4; // r14
  struct TimeProvider *v5; // rsi
  DWORD i; // r15d
  LSTATUS v7; // eax
  signed int v8; // ebx
  bool v9; // cc
  _QWORD *v10; // rdi
  __int64 v11; // rax
  unsigned __int64 v12; // rbx
  unsigned __int16 *v13; // rax
  int v14; // r10d
  struct TimeProvider *v15; // rax
  void *v16; // rcx
  unsigned int pvData; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cchName; // [rsp+44h] [rbp-BCh] BYREF
  DWORD pcbData; // [rsp+48h] [rbp-B8h] BYREF
  DWORD pdwType; // [rsp+4Ch] [rbp-B4h] BYREF
  HKEY hkey; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Name[264]; // [rsp+70h] [rbp-90h] BYREF

  *a1 = 0;
  cchName = 0;
  ftLastWriteTime = 0;
  pdwType = 0;
  pvData = 0;
  pcbData = 0;
  hKey = 0;
  v4 = 0;
  hkey = 0;
  v5 = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Policies\\Microsoft\\W32Time\\TimeProviders", 0, 0x20019u, &hKey) )
  {
    for ( i = 0; ; ++i )
    {
      cchName = 260;
      v7 = RegEnumKeyExW(hKey, i, Name, &cchName, 0, 0, 0, &ftLastWriteTime);
      v8 = v7;
      if ( v7 == 259 )
        break;
      v9 = v7 <= 0;
      if ( v7 )
        goto LABEL_28;
      if ( (unsigned __int8)FileLogAllowEntry(112) )
        FileLogAdd(L"ReadConfig (policy): Found provider '%s':\n", Name);
      v7 = RegOpenKeyExW(hKey, Name, 0, 0x20019u, &hkey);
      v8 = v7;
      v9 = v7 <= 0;
      if ( v7 )
      {
LABEL_28:
        if ( !v9 )
          v8 = (unsigned __int16)v7 | 0x80070000;
        goto LABEL_31;
      }
      pcbData = 4;
      if ( !RegGetValueW(hkey, 0, L"Enabled", 0xFFFFu, &pdwType, &pvData, &pcbData) )
      {
        if ( pdwType != 4 )
        {
          v8 = -2147418113;
          goto LABEL_31;
        }
        if ( (unsigned __int8)FileLogAllowEntry((unsigned int)(v8 + 112)) )
          FileLogAdd(L"ReadConfig (policy):   '%s'=0x%08X\n", L"Enabled", pvData);
        v10 = LocalAlloc(0x40u, 0x78u);
        if ( !v10 )
        {
          v8 = -2147024882;
          goto LABEL_31;
        }
        v11 = -1;
        do
          ++v11;
        while ( Name[v11] );
        v12 = v11 + 1;
        v13 = (unsigned __int16 *)LocalAlloc(0x40u, 2 * (v11 + 1));
        v10[1] = v13;
        if ( !v13 )
        {
          v8 = -2147024882;
LABEL_23:
          v16 = (void *)v10[1];
          if ( v16 )
            LocalFree(v16);
          LocalFree(v10);
          goto LABEL_31;
        }
        v8 = StringCchCopyW(v13, v12, Name);
        if ( v8 < 0 )
          goto LABEL_23;
        *((_DWORD *)v10 + 20) = v14 + 3;
        *((_DWORD *)v10 + 23) = v14 + 3;
        *((_DWORD *)v10 + 24) = v14 + 3;
        if ( pvData == v14 )
        {
          v15 = v5;
          v5 = (struct TimeProvider *)v10;
        }
        else
        {
          v15 = v4;
          v4 = (struct TimeProvider *)v10;
        }
        v10[3] = v15;
      }
      RegCloseKey(hkey);
      hkey = 0;
    }
  }
  *a1 = v4;
  v8 = 0;
  *a2 = v5;
  v4 = 0;
  v5 = 0;
LABEL_31:
  if ( hkey )
    RegCloseKey(hkey);
  if ( hKey )
    RegCloseKey(hKey);
  if ( v4 )
    FreeTimeProviderList(v4);
  if ( v5 )
    FreeTimeProviderList(v5);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180008520  mov     [rsp-8+arg_10], rbx
0x180008525  push    rbp
0x180008526  push    rsi
0x180008527  push    rdi
0x180008528  push    r12
0x18000852a  push    r13
0x18000852c  push    r14
0x18000852e  push    r15
0x180008530  lea     rbp, [rsp-190h]
0x180008538  sub     rsp, 290h
0x18000853f  mov     rax, cs:__security_cookie
0x180008546  xor     rax, rsp
0x180008549  mov     [rbp+1C0h+var_40], rax
0x180008550  xor     edi, edi
0x180008552  lea     rax, [rsp+2C0h+hKey]
0x180008557  mov     [rcx], rdi
0x18000855a  mov     r13, rdx
0x18000855d  mov     r12, rcx
0x180008560  mov     [rsp+2C0h+cchName], edi
0x180008564  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000856b  mov     qword ptr [rsp+2C0h+ftLastWriteTime.dwLowDateTime], rdi
0x180008570  mov     r9d, 20019h; samDesired
0x180008576  mov     [rsp+2C0h+pdwType], edi
0x18000857a  xor     r8d, r8d; ulOptions
0x18000857d  mov     [rsp+2C0h+pvData], edi
0x180008581  lea     rdx, aSoftwarePolici_3; "Software\\Policies\\Microsoft\\W32Time"...
0x180008588  mov     [rsp+2C0h+pcbData], edi
0x18000858c  mov     [rsp+2C0h+hKey], rdi
0x180008591  mov     r14d, edi
0x180008594  mov     [rsp+2C0h+hkey], rdi
0x180008599  mov     esi, edi
0x18000859b  mov     [rsp+2C0h+phkResult], rax; phkResult
0x1800085a0  call    cs:__imp_RegOpenKeyExW
0x1800085a7  nop     dword ptr [rax+rax+00h]
0x1800085ac  test    eax, eax
0x1800085ae  jnz     loc_1800087D3
0x1800085b4  mov     r15d, edi
0x1800085b7  mov     rcx, [rsp+2C0h+hKey]; hKey
0x1800085bc  lea     rax, [rsp+2C0h+ftLastWriteTime]
0x1800085c1  mov     [rsp+2C0h+lpftLastWriteTime], rax; lpftLastWriteTime
0x1800085c6  lea     r9, [rsp+2C0h+cchName]; lpcchName
0x1800085cb  mov     [rsp+2C0h+lpcchClass], rdi; lpcchClass
0x1800085d0  lea     r8, [rsp+2C0h+Name]; lpName
0x1800085d5  mov     [rsp+2C0h+lpClass], rdi; lpClass
0x1800085da  mov     edx, r15d; dwIndex
0x1800085dd  mov     [rsp+2C0h+phkResult], rdi; lpReserved
0x1800085e2  mov     [rsp+2C0h+cchName], 104h
0x1800085ea  call    cs:__imp_RegEnumKeyExW
0x1800085f1  nop     dword ptr [rax+rax+00h]
0x1800085f6  mov     ebx, eax
0x1800085f8  cmp     eax, 103h
0x1800085fd  jz      loc_1800087D3
0x180008603  test    eax, eax
0x180008605  jnz     loc_1800087C6
0x18000860b  lea     ecx, [rax+70h]
0x18000860e  call    FileLogAllowEntry
0x180008613  test    al, al
0x180008615  jz      short loc_180008628
0x180008617  lea     rdx, [rsp+2C0h+Name]
0x18000861c  lea     rcx, aReadconfigPoli; "ReadConfig (policy): Found provider '%s"...
0x180008623  call    FileLogAdd
0x180008628  mov     rcx, [rsp+2C0h+hKey]; hKey
0x18000862d  lea     rax, [rsp+2C0h+hkey]
0x180008632  mov     r9d, 20019h; samDesired
0x180008638  mov     [rsp+2C0h+phkResult], rax; phkResult
0x18000863d  xor     r8d, r8d; ulOptions
0x180008640  lea     rdx, [rsp+2C0h+Name]; lpSubKey
0x180008645  call    cs:__imp_RegOpenKeyExW
0x18000864c  nop     dword ptr [rax+rax+00h]
0x180008651  mov     ebx, eax
0x180008653  test    eax, eax
0x180008655  jnz     loc_1800087C6
0x18000865b  mov     rcx, [rsp+2C0h+hkey]; hkey
0x180008660  lea     rax, [rsp+2C0h+pcbData]
0x180008665  mov     [rsp+2C0h+lpcchClass], rax; pcbData
0x18000866a  lea     r8, aEnabled; "Enabled"
0x180008671  lea     rax, [rsp+2C0h+pvData]
0x180008676  mov     [rsp+2C0h+pcbData], 4
0x18000867e  mov     [rsp+2C0h+lpClass], rax; pvData
0x180008683  mov     r9d, 0FFFFh; dwFlags
0x180008689  lea     rax, [rsp+2C0h+pdwType]
0x18000868e  xor     edx, edx; lpSubKey
0x180008690  mov     [rsp+2C0h+phkResult], rax; pdwType
0x180008695  call    cs:__imp_RegGetValueW
0x18000869c  nop     dword ptr [rax+rax+00h]
0x1800086a1  test    eax, eax
0x1800086a3  jnz     loc_18000876F
0x1800086a9  cmp     [rsp+2C0h+pdwType], 4
0x1800086ae  jnz     loc_1800087BF
0x1800086b4  lea     ecx, [rbx+70h]
0x1800086b7  call    FileLogAllowEntry
0x1800086bc  test    al, al
0x1800086be  jz      short loc_1800086D8
0x1800086c0  mov     r8d, [rsp+2C0h+pvData]
0x1800086c5  lea     rdx, aEnabled; "Enabled"
0x1800086cc  lea     rcx, aReadconfigPoli_0; "ReadConfig (policy):   '%s'=0x%08X\n"
0x1800086d3  call    FileLogAdd
0x1800086d8  mov     edx, 78h ; 'x'; uBytes
0x1800086dd  lea     ecx, [rdx-38h]; uFlags
0x1800086e0  call    cs:__imp_LocalAlloc
0x1800086e7  nop     dword ptr [rax+rax+00h]
0x1800086ec  xor     ecx, ecx
0x1800086ee  mov     rdi, rax
0x1800086f1  test    rax, rax
0x1800086f4  jz      loc_1800087B8
0x1800086fa  lea     rdx, [rsp+2C0h+Name]
0x1800086ff  or      rax, 0FFFFFFFFFFFFFFFFh
0x180008703  inc     rax
0x180008706  cmp     [rdx+rax*2], cx
0x18000870a  jnz     short loc_180008703
0x18000870c  lea     rbx, [rax+1]
0x180008710  mov     ecx, 40h ; '@'; uFlags
0x180008715  lea     rdx, [rbx+rbx]; uBytes
0x180008719  call    cs:__imp_LocalAlloc
0x180008720  nop     dword ptr [rax+rax+00h]
0x180008725  xor     r10d, r10d
0x180008728  mov     [rdi+8], rax
0x18000872c  test    rax, rax
0x18000872f  jz      short loc_18000878D
0x180008731  lea     r8, [rsp+2C0h+Name]; unsigned __int16 *
0x180008736  mov     rdx, rbx; unsigned __int64
0x180008739  mov     rcx, rax; unsigned __int16 *
0x18000873c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180008741  mov     ebx, eax
0x180008743  test    eax, eax
0x180008745  js      short loc_180008792
0x180008747  lea     eax, [r10+3]
0x18000874b  mov     [rdi+50h], eax
0x18000874e  mov     [rdi+5Ch], eax
0x180008751  mov     [rdi+60h], eax
0x180008754  cmp     [rsp+2C0h+pvData], r10d
0x180008759  jz      short loc_180008763
0x18000875b  mov     rax, r14
0x18000875e  mov     r14, rdi
0x180008761  jmp     short loc_180008769
0x180008763  mov     rax, rsi
0x180008766  mov     rsi, rdi
0x180008769  mov     [rdi+18h], rax
0x18000876d  xor     edi, edi
0x18000876f  mov     rcx, [rsp+2C0h+hkey]; hKey
0x180008774  call    cs:__imp_RegCloseKey
0x18000877b  nop     dword ptr [rax+rax+00h]
0x180008780  inc     r15d
0x180008783  mov     [rsp+2C0h+hkey], rdi
0x180008788  jmp     loc_1800085B7
0x18000878d  mov     ebx, 8007000Eh
0x180008792  mov     rcx, [rdi+8]; hMem
0x180008796  test    rcx, rcx
0x180008799  jz      short loc_1800087A7
0x18000879b  call    cs:__imp_LocalFree
0x1800087a2  nop     dword ptr [rax+rax+00h]
0x1800087a7  mov     rcx, rdi; hMem
0x1800087aa  call    cs:__imp_LocalFree
0x1800087b1  nop     dword ptr [rax+rax+00h]
0x1800087b6  jmp     short loc_1800087E3
0x1800087b8  mov     ebx, 8007000Eh
0x1800087bd  jmp     short loc_1800087E3
0x1800087bf  mov     ebx, 8000FFFFh
0x1800087c4  jmp     short loc_1800087E3
0x1800087c6  jle     short loc_1800087E3
0x1800087c8  movzx   ebx, ax
0x1800087cb  or      ebx, 80070000h
0x1800087d1  jmp     short loc_1800087E3
0x1800087d3  mov     [r12], r14
0x1800087d7  mov     ebx, edi
0x1800087d9  mov     [r13+0], rsi
0x1800087dd  mov     r14, rdi
0x1800087e0  mov     rsi, rdi
0x1800087e3  mov     rcx, [rsp+2C0h+hkey]; hKey
0x1800087e8  test    rcx, rcx
0x1800087eb  jz      short loc_1800087F9
0x1800087ed  call    cs:__imp_RegCloseKey
0x1800087f4  nop     dword ptr [rax+rax+00h]
0x1800087f9  mov     rcx, [rsp+2C0h+hKey]; hKey
0x1800087fe  test    rcx, rcx
0x180008801  jz      short loc_18000880F
0x180008803  call    cs:__imp_RegCloseKey
0x18000880a  nop     dword ptr [rax+rax+00h]
0x18000880f  test    r14, r14
0x180008812  jz      short loc_18000881C
0x180008814  mov     rcx, r14; hMem
0x180008817  call    ?FreeTimeProviderList@@YAXPEAUTimeProvider@@@Z; FreeTimeProviderList(TimeProvider *)
0x18000881c  test    rsi, rsi
0x18000881f  jz      short loc_180008829
0x180008821  mov     rcx, rsi; hMem
0x180008824  call    ?FreeTimeProviderList@@YAXPEAUTimeProvider@@@Z; FreeTimeProviderList(TimeProvider *)
0x180008829  mov     eax, ebx
0x18000882b  mov     rcx, [rbp+1C0h+var_40]
0x180008832  xor     rcx, rsp; StackCookie
0x180008835  call    __security_check_cookie
0x18000883a  mov     rbx, [rsp+2C0h+arg_10]
0x180008842  add     rsp, 290h
0x180008849  pop     r15
0x18000884b  pop     r14
0x18000884d  pop     r13
0x18000884f  pop     r12
0x180008851  pop     rdi
0x180008852  pop     rsi
0x180008853  pop     rbp
0x180008854  retn
```
