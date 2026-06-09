# WriteVersionToPerformanceContextKey(ushort const *,ushort const *)

- ea: `0x180040248`
- end: `0x180040408`
- name: `?WriteVersionToPerformanceContextKey@@YAJPEBG0@Z`
- size: `448`
- prototype: `__int64 __fastcall(const unsigned __int16 *, BYTE *lpData)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x1800382f0`
- `0x1800397d4`
- `0x180039b1c`
- `0x18003ea8c`

## callees

- `0x180007824`
- `0x180040248`
- `0x18004d030`

## import_xrefs

- `KERNEL32!lstrlenW` at `0x180040387`
- `KERNEL32!lstrlenW` at `0x180040387`
- `ADVAPI32!RegCloseKey` at `0x1800403d7`
- `ADVAPI32!RegCloseKey` at `0x1800403d7`
- `ADVAPI32!RegCreateKeyExW` at `0x18004036a`
- `ADVAPI32!RegCreateKeyExW` at `0x18004036a`
- `ADVAPI32!RegSetValueExW` at `0x1800403b2`
- `ADVAPI32!RegSetValueExW` at `0x1800403b2`

## string_xrefs

- `0x180040273`: `SYSTEM\CurrentControlSet\Services\`
- `0x18004031a`: `Linkage`

## pseudocode

```c
__int64 __fastcall WriteVersionToPerformanceContextKey(const unsigned __int16 *a1, const WCHAR *lpData)
{
  __int64 v2; // r9
  WCHAR *v3; // r8
  WCHAR v5; // ax
  WCHAR *v6; // rax
  signed int v7; // ebx
  LSTATUS v8; // eax
  int v9; // eax
  unsigned int v10; // eax
  HKEY hKey; // [rsp+50h] [rbp-238h] BYREF
  WCHAR SubKey[264]; // [rsp+60h] [rbp-228h] BYREF

  hKey = 0;
  v2 = 260;
  v3 = SubKey;
  do
  {
    if ( v2 == -2147483386 )
      break;
    v5 = *(WCHAR *)((char *)v3 + (char *)L"SYSTEM\\CurrentControlSet\\Services\\" - (char *)SubKey);
    if ( !v5 )
      break;
    *v3++ = v5;
    --v2;
  }
  while ( v2 );
  v6 = v3 - 1;
  if ( v2 )
    v6 = v3;
  *v6 = 0;
  v7 = v2 == 0 ? 0x8007007A : 0;
  if ( v2 )
  {
    v7 = StringCchCatW(SubKey, 0x104u, a1);
    if ( !v7 )
    {
      v7 = StringCchCatW(SubKey, 0x104u, L"\\");
      if ( !v7 )
      {
        v7 = StringCchCatW(SubKey, 0x104u, L"Linkage");
        if ( !v7 )
        {
          v8 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0, 0, 0x20006u, 0, &hKey, 0);
          if ( v8 )
          {
            v7 = (unsigned __int16)v8 | 0x80070000;
            if ( v8 <= 0 )
              v7 = v8;
          }
          else
          {
            v9 = lstrlenW(lpData);
            v7 = RegSetValueExW(hKey, L"Export", 0, 7u, (const BYTE *)lpData, 2 * v9 + 2);
            if ( v7 )
            {
              v10 = (unsigned __int16)v7 | 0x80070000;
              if ( v7 <= 0 )
                v10 = v7;
              v7 = v10;
            }
          }
        }
      }
    }
    if ( hKey )
      RegCloseKey(hKey);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180040248  mov     [rsp+arg_0], rbx
0x18004024d  mov     [rsp+arg_10], rbp
0x180040252  mov     [rsp+arg_18], rsi
0x180040257  push    rdi
0x180040258  sub     rsp, 280h
0x18004025f  mov     rax, cs:__security_cookie
0x180040266  xor     rax, rsp
0x180040269  mov     [rsp+288h+var_18], rax
0x180040271  xor     esi, esi
0x180040273  lea     r10, aSystemCurrentc_3; "SYSTEM\\CurrentControlSet\\Services\\"
0x18004027a  mov     ebp, 104h
0x18004027f  mov     [rsp+288h+hKey], rsi
0x180040284  lea     rax, [rsp+288h+SubKey]
0x180040289  mov     r9d, ebp
0x18004028c  sub     r10, rax
0x18004028f  lea     r8, [rsp+288h+SubKey]
0x180040294  mov     rdi, rdx
0x180040297  lea     rax, [r9+7FFFFEFAh]
0x18004029e  test    rax, rax
0x1800402a1  jz      short loc_1800402BB
0x1800402a3  movzx   eax, word ptr [r10+r8]
0x1800402a8  test    ax, ax
0x1800402ab  jz      short loc_1800402BB
0x1800402ad  mov     [r8], ax
0x1800402b1  add     r8, 2
0x1800402b5  sub     r9, 1
0x1800402b9  jnz     short loc_180040297
0x1800402bb  test    r9, r9
0x1800402be  lea     rax, [r8-2]
0x1800402c2  cmovnz  rax, r8
0x1800402c6  mov     [rax], si
0x1800402c9  mov     rax, r9
0x1800402cc  neg     rax
0x1800402cf  sbb     ebx, ebx
0x1800402d1  not     ebx
0x1800402d3  and     ebx, 8007007Ah
0x1800402d9  test    r9, r9
0x1800402dc  jz      loc_1800403DD
0x1800402e2  mov     r8, rcx; unsigned __int16 *
0x1800402e5  mov     rdx, rbp; unsigned __int64
0x1800402e8  lea     rcx, [rsp+288h+SubKey]; unsigned __int16 *
0x1800402ed  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800402f2  mov     ebx, eax
0x1800402f4  test    eax, eax
0x1800402f6  jnz     loc_1800403CD
0x1800402fc  lea     r8, SubBlock; "\\"
0x180040303  mov     rdx, rbp; unsigned __int64
0x180040306  lea     rcx, [rsp+288h+SubKey]; unsigned __int16 *
0x18004030b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180040310  mov     ebx, eax
0x180040312  test    eax, eax
0x180040314  jnz     loc_1800403CD
0x18004031a  lea     r8, aLinkage; "Linkage"
0x180040321  mov     rdx, rbp; unsigned __int64
0x180040324  lea     rcx, [rsp+288h+SubKey]; unsigned __int16 *
0x180040329  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18004032e  mov     ebx, eax
0x180040330  test    eax, eax
0x180040332  jnz     loc_1800403CD
0x180040338  mov     [rsp+288h+lpdwDisposition], rsi; lpdwDisposition
0x18004033d  lea     rax, [rsp+288h+hKey]
0x180040342  mov     [rsp+288h+phkResult], rax; phkResult
0x180040347  lea     rdx, [rsp+288h+SubKey]; lpSubKey
0x18004034c  mov     [rsp+288h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x180040351  xor     r9d, r9d; lpClass
0x180040354  mov     [rsp+288h+samDesired], 20006h; samDesired
0x18004035c  xor     r8d, r8d; Reserved
0x18004035f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180040366  mov     [rsp+288h+dwOptions], esi; dwOptions
0x18004036a  call    cs:__imp_RegCreateKeyExW
0x180040370  test    eax, eax
0x180040372  jz      short loc_180040384
0x180040374  movzx   ebx, ax
0x180040377  or      ebx, 80070000h
0x18004037d  test    eax, eax
0x18004037f  cmovle  ebx, eax
0x180040382  jmp     short loc_1800403CD
0x180040384  mov     rcx, rdi; lpString
0x180040387  call    cs:__imp_lstrlenW
0x18004038d  mov     rcx, [rsp+288h+hKey]; hKey
0x180040392  lea     rdx, aExport; "Export"
0x180040399  mov     r9d, 7; dwType
0x18004039f  xor     r8d, r8d; Reserved
0x1800403a2  lea     eax, ds:2[rax*2]
0x1800403a9  mov     [rsp+288h+samDesired], eax; cbData
0x1800403ad  mov     qword ptr [rsp+288h+dwOptions], rdi; lpData
0x1800403b2  call    cs:__imp_RegSetValueExW
0x1800403b8  mov     ebx, eax
0x1800403ba  test    eax, eax
0x1800403bc  jz      short loc_1800403CD
0x1800403be  movzx   eax, bx
0x1800403c1  or      eax, 80070000h
0x1800403c6  test    ebx, ebx
0x1800403c8  cmovle  eax, ebx
0x1800403cb  mov     ebx, eax
0x1800403cd  mov     rcx, [rsp+288h+hKey]; hKey
0x1800403d2  test    rcx, rcx
0x1800403d5  jz      short loc_1800403DD
0x1800403d7  call    cs:__imp_RegCloseKey
0x1800403dd  mov     eax, ebx
0x1800403df  mov     rcx, [rsp+288h+var_18]
0x1800403e7  xor     rcx, rsp; StackCookie
0x1800403ea  call    __security_check_cookie
0x1800403ef  lea     r11, [rsp+288h+var_8]
0x1800403f7  mov     rbx, [r11+10h]
0x1800403fb  mov     rbp, [r11+20h]
0x1800403ff  mov     rsi, [r11+28h]
0x180040403  mov     rsp, r11
0x180040406  pop     rdi
0x180040407  retn
```
