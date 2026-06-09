# OneSettingsPolicyWrapper::CacheData(ushort const *,ulong,uchar *)

- ea: `0x1800153a0`
- end: `0x180015557`
- name: `?CacheData@OneSettingsPolicyWrapper@@AEAAJPEBGKPEAE@Z`
- size: `439`
- prototype: `int(OneSettingsPolicyWrapper *__hidden this, const unsigned __int16 *, unsigned int, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180022b98`

## callees

- `0x180013ec0`
- `0x1800153a0`
- `0x180026508`
- `0x1800265e0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800153fa`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800153fa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800154b8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001553a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015542`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001554f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800154b8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001553a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015542`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001554f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001544a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001544a`

## pseudocode

```c
__int64 __fastcall OneSettingsPolicyWrapper::CacheData(
        OneSettingsPolicyWrapper *this,
        const unsigned __int16 *a2,
        DWORD a3,
        unsigned __int8 *a4)
{
  const WCHAR *v6; // rdx
  bool v7; // cc
  unsigned int v9; // eax
  __int64 v10; // rax
  DWORD v12; // eax
  unsigned int v13; // eax
  unsigned int v14; // ebx
  unsigned int dwOptions; // [rsp+20h] [rbp-38h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  HKEY hKey; // [rsp+60h] [rbp+8h] BYREF

  v6 = (const WCHAR *)((char *)this + 120);
  v7 = *((_QWORD *)this + 18) <= 7u;
  hKey = 0;
  if ( !v7 )
    v6 = *(const WCHAR **)v6;
  v9 = RegCreateKeyExW(HKEY_CURRENT_USER, v6, 0, 0, 0, 0xF003Fu, 0, &hKey, 0);
  if ( v9 )
  {
    v14 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x1E4,
            (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\onesettings\\src\\onesettingspolicywrapper.cpp",
            (const char *)v9,
            dwOptions);
    if ( hKey )
      RegCloseKey(hKey);
    return v14;
  }
  if ( a3 == 1 )
  {
    v10 = -1;
    while ( *(_WORD *)&a4[2 * v10++ + 2] != 0 )
      ;
    v12 = 2 * v10 + 2;
  }
  else
  {
    if ( a3 != 4 )
    {
      DoTraceMessage(2, "OneSettingsPolicyWrapper: Unexpected data type %u for entry %S", a3, a2);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1F7,
        (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\onesettings\\src\\onesettingspolicywrapper.cpp",
        (const char *)0x8000FFFFLL,
        dwOptions);
      if ( hKey )
        RegCloseKey(hKey);
      return 2147549183LL;
    }
    v12 = 4;
  }
  v13 = RegSetValueExW(hKey, a2, 0, a3, a4, v12);
  if ( v13 )
  {
    v14 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x1FA,
            (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\onesettings\\src\\onesettingspolicywrapper.cpp",
            (const char *)v13,
            dwOptionsa);
    if ( !hKey )
      return v14;
    RegCloseKey(hKey);
    return v14;
  }
  else
  {
    if ( hKey )
      RegCloseKey(hKey);
    return 0;
  }
}

```

## disassembly

```asm
0x1800153a0  mov     [rsp+arg_8], rbx
0x1800153a5  mov     [rsp+arg_10], rsi
0x1800153aa  push    rdi
0x1800153ab  sub     rsp, 50h
0x1800153af  mov     edi, r8d
0x1800153b2  mov     rsi, rdx
0x1800153b5  xor     r8d, r8d; Reserved
0x1800153b8  lea     rdx, [rcx+78h]; lpSubKey
0x1800153bc  cmp     qword ptr [rdx+18h], 7
0x1800153c1  mov     rbx, r9
0x1800153c4  mov     [rsp+58h+hKey], r8
0x1800153c9  ja      loc_180015523
0x1800153cf  mov     [rsp+58h+lpdwDisposition], r8; lpdwDisposition
0x1800153d4  lea     rax, [rsp+58h+hKey]
0x1800153d9  mov     [rsp+58h+phkResult], rax; phkResult
0x1800153de  xor     r9d, r9d; lpClass
0x1800153e1  mov     [rsp+58h+lpSecurityAttributes], r8; lpSecurityAttributes
0x1800153e6  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800153ed  mov     [rsp+58h+samDesired], 0F003Fh; samDesired
0x1800153f5  mov     [rsp+58h+dwOptions], r8d; int
0x1800153fa  call    cs:__imp_RegCreateKeyExW
0x180015400  test    eax, eax
0x180015402  jnz     loc_180015493
0x180015408  mov     eax, edi
0x18001540a  sub     eax, 1
0x18001540d  jnz     loc_18001552B
0x180015413  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18001541a  nop     word ptr [rax+rax+00h]
0x180015420  cmp     word ptr [rbx+rax*2+2], 0
0x180015426  lea     rax, [rax+1]
0x18001542a  jnz     short loc_180015420
0x18001542c  lea     eax, ds:2[rax*2]
0x180015433  mov     rcx, [rsp+58h+hKey]; hKey
0x180015438  mov     r9d, edi; dwType
0x18001543b  mov     [rsp+58h+samDesired], eax; cbData
0x18001543f  xor     r8d, r8d; Reserved
0x180015442  mov     rdx, rsi; lpValueName
0x180015445  mov     qword ptr [rsp+58h+dwOptions], rbx; unsigned int
0x18001544a  call    cs:__imp_RegSetValueExW
0x180015450  test    eax, eax
0x180015452  jz      loc_180015512
0x180015458  mov     rcx, [rsp+58h]; this
0x18001545d  lea     r8, aOnecoreuapEndu_332; "onecoreuap\\enduser\\nui\\onecore\\ones"...
0x180015464  mov     r9d, eax; char *
0x180015467  mov     edx, 1FAh; void *
0x18001546c  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180015471  mov     rcx, [rsp+58h+hKey]; hKey
0x180015476  mov     ebx, eax
0x180015478  test    rcx, rcx
0x18001547b  jnz     loc_180015542
0x180015481  mov     eax, ebx
0x180015483  mov     rbx, [rsp+58h+arg_8]
0x180015488  mov     rsi, [rsp+58h+arg_10]
0x18001548d  add     rsp, 50h
0x180015491  pop     rdi
0x180015492  retn
0x180015493  mov     rcx, [rsp+58h]; this
0x180015498  lea     r8, aOnecoreuapEndu_332; "onecoreuap\\enduser\\nui\\onecore\\ones"...
0x18001549f  mov     r9d, eax; char *
0x1800154a2  mov     edx, 1E4h; void *
0x1800154a7  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800154ac  mov     rcx, [rsp+58h+hKey]; hKey
0x1800154b1  mov     ebx, eax
0x1800154b3  test    rcx, rcx
0x1800154b6  jz      short loc_180015481
0x1800154b8  call    cs:__imp_RegCloseKey
0x1800154be  jmp     short loc_180015481
0x1800154c0  mov     r9, rsi
0x1800154c3  lea     rdx, aOnesettingspol_2; "OneSettingsPolicyWrapper: Unexpected da"...
0x1800154ca  mov     r8d, edi
0x1800154cd  mov     ecx, 2; int
0x1800154d2  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x1800154d7  mov     rcx, [rsp+58h]; this
0x1800154dc  lea     r8, aOnecoreuapEndu_332; "onecoreuap\\enduser\\nui\\onecore\\ones"...
0x1800154e3  mov     r9d, 8000FFFFh; char *
0x1800154e9  mov     edx, 1F7h; void *
0x1800154ee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800154f3  mov     rcx, [rsp+58h+hKey]; hKey
0x1800154f8  test    rcx, rcx
0x1800154fb  jnz     short loc_18001553A
0x1800154fd  mov     rbx, [rsp+58h+arg_8]
0x180015502  mov     eax, 8000FFFFh
0x180015507  mov     rsi, [rsp+58h+arg_10]
0x18001550c  add     rsp, 50h
0x180015510  pop     rdi
0x180015511  retn
0x180015512  mov     rcx, [rsp+58h+hKey]; hKey
0x180015517  test    rcx, rcx
0x18001551a  jnz     short loc_18001554F
0x18001551c  xor     eax, eax
0x18001551e  jmp     loc_180015483
0x180015523  mov     rdx, [rdx]
0x180015526  jmp     loc_1800153CF
0x18001552b  cmp     eax, 3
0x18001552e  jnz     short loc_1800154C0
0x180015530  mov     eax, 4
0x180015535  jmp     loc_180015433
0x18001553a  call    cs:__imp_RegCloseKey
0x180015540  jmp     short loc_1800154FD
0x180015542  call    cs:__imp_RegCloseKey
0x180015548  mov     eax, ebx
0x18001554a  jmp     loc_180015483
0x18001554f  call    cs:__imp_RegCloseKey
0x180015555  jmp     short loc_18001551C
```
