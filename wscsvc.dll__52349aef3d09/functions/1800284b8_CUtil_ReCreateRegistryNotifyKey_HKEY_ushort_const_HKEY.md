# CUtil::ReCreateRegistryNotifyKey(HKEY__ *,ushort const *,HKEY__ * *)

- ea: `0x1800284b8`
- end: `0x180028597`
- name: `?ReCreateRegistryNotifyKey@CUtil@@SAJPEAUHKEY__@@PEBGPEAPEAU2@@Z`
- size: `223`
- prototype: `static int(HKEY, const unsigned __int16 *, HKEY *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180002fc0`

## callees

- `0x1800202e8`
- `0x1800284b8`
- `0x18003e7e8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180028532`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180028532`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002850a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002850a`

## pseudocode

```c
__int64 __fastcall CUtil::ReCreateRegistryNotifyKey(HKEY a1, const unsigned __int16 *a2, HKEY *a3)
{
  unsigned int v5; // ebx
  LSTATUS v6; // esi
  int v7; // r8d
  int v8; // r9d

  if ( a3 )
  {
    v5 = 0;
    if ( *a3 )
    {
      RegCloseKey(*a3);
      *a3 = 0;
    }
    v6 = RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\System",
           0,
           0x11u,
           a3);
    if ( v6 )
    {
      if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_qSd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          14,
          v7,
          v8,
          (__int64)L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\System",
          v6);
      }
      *a3 = 0;
      if ( v6 > 0 )
        return (unsigned __int16)v6 | 0x80070000;
      else
        return (unsigned int)v6;
    }
    return v5;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_bc50b57d3a7f3ca15f27abc6215da79e_Traceguids);
    }
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x1800284b8  push    rbx
0x1800284ba  push    rbp
0x1800284bb  push    rsi
0x1800284bc  push    rdi
0x1800284bd  sub     rsp, 38h
0x1800284c1  mov     rdi, r8
0x1800284c4  test    r8, r8
0x1800284c7  jnz     short loc_180028500
0x1800284c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800284d0  lea     rax, WPP_GLOBAL_Control
0x1800284d7  cmp     rcx, rax
0x1800284da  jz      short loc_1800284F6
0x1800284dc  test    byte ptr [rcx+1Ch], 1
0x1800284e0  jz      short loc_1800284F6
0x1800284e2  mov     rcx, [rcx+10h]
0x1800284e6  lea     edx, [r8+0Dh]
0x1800284ea  lea     r8, WPP_bc50b57d3a7f3ca15f27abc6215da79e_Traceguids
0x1800284f1  call    WPP_SF_
0x1800284f6  mov     eax, 80070057h
0x1800284fb  jmp     loc_18002858E
0x180028500  mov     rcx, [r8]; hKey
0x180028503  xor     ebx, ebx
0x180028505  test    rcx, rcx
0x180028508  jz      short loc_180028513
0x18002850a  call    cs:__imp_RegCloseKey
0x180028510  mov     [rdi], rbx
0x180028513  lea     rbp, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18002851a  mov     [rsp+58h+phkResult], rdi; phkResult
0x18002851f  mov     rdx, rbp; lpSubKey
0x180028522  mov     r9d, 11h; samDesired
0x180028528  xor     r8d, r8d; ulOptions
0x18002852b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180028532  call    cs:__imp_RegOpenKeyExW
0x180028538  mov     esi, eax
0x18002853a  test    eax, eax
0x18002853c  jz      short loc_18002858C
0x18002853e  mov     rcx, cs:WPP_GLOBAL_Control
0x180028545  lea     rax, WPP_GLOBAL_Control
0x18002854c  cmp     rcx, rax
0x18002854f  jz      short loc_18002856E
0x180028551  test    byte ptr [rcx+1Ch], 1
0x180028555  jz      short loc_18002856E
0x180028557  mov     rcx, [rcx+10h]
0x18002855b  mov     edx, 0Eh
0x180028560  mov     [rsp+58h+var_30], esi
0x180028564  mov     [rsp+58h+phkResult], rbp
0x180028569  call    WPP_SF_qSd
0x18002856e  mov     [rdi], rbx
0x180028571  test    esi, esi
0x180028573  jg      short loc_180028579
0x180028575  mov     ebx, esi
0x180028577  jmp     short loc_180028582
0x180028579  movzx   ebx, si
0x18002857c  or      ebx, 80070000h
0x180028582  test    ebx, ebx
0x180028584  mov     eax, 80004005h
0x180028589  cmovns  ebx, eax
0x18002858c  mov     eax, ebx
0x18002858e  add     rsp, 38h
0x180028592  pop     rdi
0x180028593  pop     rsi
0x180028594  pop     rbp
0x180028595  pop     rbx
0x180028596  retn
```
