# CommonUtil::UtilRegOpenKey(HKEY__ * *,HKEY__ *,ushort const *,ulong)

- ea: `0x18003f704`
- end: `0x18003f81f`
- name: `?UtilRegOpenKey@CommonUtil@@YAJPEAPEAUHKEY__@@PEAU2@PEBGK@Z`
- size: `283`
- prototype: `__int64 __fastcall(CommonUtil *__hidden this, HKEY *, HKEY, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003a040`

## callees

- `0x180029158`
- `0x180032c38`
- `0x18003f704`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003f745`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003f745`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003f78f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003f7f4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003f78f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003f7f4`

## pseudocode

```c
__int64 __fastcall CommonUtil::UtilRegOpenKey(CommonUtil *this, HKEY *a2, HKEY a3, const unsigned __int16 *a4)
{
  int v5; // ebx
  bool v7; // sf
  HKEY hKey; // [rsp+50h] [rbp+18h] BYREF

  *(_QWORD *)this = 0;
  hKey = 0;
  v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Windows Defender", 0, 0x20019u, &hKey);
  if ( v5 == 2 )
  {
    if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        WPP_206b02167db13a360b8041c753392543_Traceguids,
        L"Software\\Microsoft\\Windows Defender");
    }
    if ( hKey )
      RegCloseKey(hKey);
    return 2147942402LL;
  }
  else
  {
    if ( !v5 )
      goto LABEL_18;
    if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_SD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        (unsigned int)WPP_206b02167db13a360b8041c753392543_Traceguids,
        (unsigned int)L"Software\\Microsoft\\Windows Defender",
        v5);
    }
    v7 = v5 < 0;
    if ( v5 > 0 )
    {
      v5 = (unsigned __int16)v5 | 0x80070000;
      v7 = v5 < 0;
    }
    if ( v7 )
    {
      if ( hKey )
        RegCloseKey(hKey);
      return (unsigned int)v5;
    }
    else
    {
LABEL_18:
      if ( hKey )
      {
        *(_QWORD *)this = hKey;
        return 0;
      }
      else
      {
        return 2147549183LL;
      }
    }
  }
}

```

## disassembly

```asm
0x18003f704  mov     r11, rsp
0x18003f707  mov     [r11+8], rbx
0x18003f70b  mov     [r11+18h], r8
0x18003f70f  push    rdi
0x18003f710  sub     rsp, 30h
0x18003f714  mov     rdi, rcx
0x18003f717  mov     qword ptr [rcx], 0
0x18003f71e  lea     rax, [r11+18h]
0x18003f722  mov     qword ptr [r11+18h], 0
0x18003f72a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003f731  mov     [r11-18h], rax
0x18003f735  mov     r9d, 20019h; samDesired
0x18003f73b  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows Defender"
0x18003f742  xor     r8d, r8d; ulOptions
0x18003f745  call    cs:__imp_RegOpenKeyExW
0x18003f74b  mov     ebx, eax
0x18003f74d  cmp     eax, 2
0x18003f750  jnz     short loc_18003F79C
0x18003f752  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f759  lea     rax, WPP_GLOBAL_Control
0x18003f760  cmp     rcx, rax
0x18003f763  jz      short loc_18003F785
0x18003f765  test    byte ptr [rcx+1Ch], 10h
0x18003f769  jz      short loc_18003F785
0x18003f76b  mov     rcx, [rcx+10h]
0x18003f76f  lea     edx, [rbx+8]
0x18003f772  lea     r9, aSoftwareMicros_2; "Software\\Microsoft\\Windows Defender"
0x18003f779  lea     r8, WPP_206b02167db13a360b8041c753392543_Traceguids
0x18003f780  call    WPP_SF_S
0x18003f785  mov     rcx, [rsp+38h+hKey]; hKey
0x18003f78a  test    rcx, rcx
0x18003f78d  jz      short loc_18003F795
0x18003f78f  call    cs:__imp_RegCloseKey
0x18003f795  mov     eax, 80070002h
0x18003f79a  jmp     short loc_18003F814
0x18003f79c  test    ebx, ebx
0x18003f79e  jz      short loc_18003F7FE
0x18003f7a0  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f7a7  lea     rax, WPP_GLOBAL_Control
0x18003f7ae  cmp     rcx, rax
0x18003f7b1  jz      short loc_18003F7D9
0x18003f7b3  test    byte ptr [rcx+1Ch], 1
0x18003f7b7  jz      short loc_18003F7D9
0x18003f7b9  mov     rcx, [rcx+10h]
0x18003f7bd  lea     r9, aSoftwareMicros_2; "Software\\Microsoft\\Windows Defender"
0x18003f7c4  mov     edx, 0Bh
0x18003f7c9  mov     [rsp+38h+var_18], ebx
0x18003f7cd  lea     r8, WPP_206b02167db13a360b8041c753392543_Traceguids
0x18003f7d4  call    WPP_SF_SD
0x18003f7d9  test    ebx, ebx
0x18003f7db  jle     short loc_18003F7E8
0x18003f7dd  movzx   ebx, bx
0x18003f7e0  or      ebx, 80070000h
0x18003f7e6  test    ebx, ebx
0x18003f7e8  jns     short loc_18003F7FE
0x18003f7ea  mov     rcx, [rsp+38h+hKey]; hKey
0x18003f7ef  test    rcx, rcx
0x18003f7f2  jz      short loc_18003F7FA
0x18003f7f4  call    cs:__imp_RegCloseKey
0x18003f7fa  mov     eax, ebx
0x18003f7fc  jmp     short loc_18003F814
0x18003f7fe  mov     rax, [rsp+38h+hKey]
0x18003f803  test    rax, rax
0x18003f806  jnz     short loc_18003F80F
0x18003f808  mov     eax, 8000FFFFh
0x18003f80d  jmp     short loc_18003F814
0x18003f80f  mov     [rdi], rax
0x18003f812  xor     eax, eax
0x18003f814  mov     rbx, [rsp+38h+arg_0]
0x18003f819  add     rsp, 30h
0x18003f81d  pop     rdi
0x18003f81e  retn
```
