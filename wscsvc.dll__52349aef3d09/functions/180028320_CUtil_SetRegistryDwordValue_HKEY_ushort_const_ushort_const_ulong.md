# CUtil::SetRegistryDwordValue(HKEY__ *,ushort const *,ushort const *,ulong)

- ea: `0x180028320`
- end: `0x1800284af`
- name: `?SetRegistryDwordValue@CUtil@@SAJPEAUHKEY__@@PEBG1K@Z`
- size: `399`
- prototype: `static int(HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180034b30`

## callees

- `0x1800202e8`
- `0x180028320`
- `0x18003e6e8`
- `0x18003e7e8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002838b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002838b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800283c9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800283c9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800283bc`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800283bc`

## pseudocode

```c
__int64 __fastcall CUtil::SetRegistryDwordValue(
        HKEY a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        int a4)
{
  unsigned int v6; // eax
  int v7; // r8d
  int v8; // r9d
  HKEY v9; // rbx
  LSTATUS v10; // edi
  int v11; // edx
  int v12; // r8d
  int v13; // r9d
  bool v14; // sf
  HKEY hKey; // [rsp+70h] [rbp+8h] BYREF
  int Data; // [rsp+88h] [rbp+20h] BYREF

  Data = a4;
  hKey = a1;
  if ( a2 && a3 )
  {
    hKey = 0;
    v6 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, a2, 0, 0, 0, 0x20006u, 0, &hKey, 0);
    v9 = (HKEY)v6;
    if ( v6 )
    {
      if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_qSd(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, v7, v8, (__int64)a2, v6);
      }
      v14 = (int)v9 < 0;
      if ( (int)v9 <= 0 )
        goto LABEL_18;
      LODWORD(v9) = (unsigned __int16)v9;
    }
    else
    {
      v10 = RegSetValueExW(hKey, a3, 0, 4u, (const BYTE *)&Data, 4u);
      RegCloseKey(hKey);
      hKey = v9;
      if ( !v10 )
        return (unsigned int)v9;
      if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_qSSdd(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, v12, v13, (__int64)a2, (__int64)a3, Data, v10);
      }
      if ( v10 <= 0 )
      {
        LODWORD(v9) = v10;
LABEL_17:
        v14 = (int)v9 < 0;
LABEL_18:
        if ( !v14 )
          LODWORD(v9) = -2147467259;
        return (unsigned int)v9;
      }
      LODWORD(v9) = (unsigned __int16)v10;
    }
    LODWORD(v9) = (unsigned int)v9 | 0x80070000;
    goto LABEL_17;
  }
  if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_bc50b57d3a7f3ca15f27abc6215da79e_Traceguids);
  return 2147942487LL;
}

```

## disassembly

```asm
0x180028320  mov     r11, rsp
0x180028323  mov     [r11+10h], rbx
0x180028327  mov     [r11+20h], r9d
0x18002832b  mov     [r11+8], rcx
0x18002832f  push    rbp
0x180028330  push    rsi
0x180028331  push    rdi
0x180028332  sub     rsp, 50h
0x180028336  mov     rbp, r8
0x180028339  mov     rsi, rdx
0x18002833c  test    rdx, rdx
0x18002833f  jz      loc_18002846F
0x180028345  test    r8, r8
0x180028348  jz      loc_18002846F
0x18002834e  mov     qword ptr [r11-28h], 0
0x180028356  lea     rax, [r11+8]
0x18002835a  mov     [r11-30h], rax
0x18002835e  xor     r9d, r9d; lpClass
0x180028361  mov     qword ptr [r11-38h], 0
0x180028369  xor     r8d, r8d; Reserved
0x18002836c  mov     [rsp+68h+samDesired], 20006h; samDesired
0x180028374  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002837b  mov     [rsp+68h+dwOptions], 0; dwOptions
0x180028383  mov     qword ptr [r11+8], 0
0x18002838b  call    cs:__imp_RegCreateKeyExW
0x180028391  mov     ebx, eax
0x180028393  test    eax, eax
0x180028395  jnz     loc_180028424
0x18002839b  mov     rcx, [rsp+68h+hKey]; hKey
0x1800283a0  lea     r9d, [rax+4]; dwType
0x1800283a4  lea     rax, [rsp+68h+Data]
0x1800283ac  mov     [rsp+68h+samDesired], r9d; cbData
0x1800283b1  xor     r8d, r8d; Reserved
0x1800283b4  mov     qword ptr [rsp+68h+dwOptions], rax; lpData
0x1800283b9  mov     rdx, rbp; lpValueName
0x1800283bc  call    cs:__imp_RegSetValueExW
0x1800283c2  mov     rcx, [rsp+68h+hKey]; hKey
0x1800283c7  mov     edi, eax
0x1800283c9  call    cs:__imp_RegCloseKey
0x1800283cf  mov     [rsp+68h+hKey], rbx
0x1800283d4  test    edi, edi
0x1800283d6  jz      loc_18002846B
0x1800283dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800283e3  lea     rax, WPP_GLOBAL_Control
0x1800283ea  cmp     rcx, rax
0x1800283ed  jz      short loc_180028417
0x1800283ef  test    byte ptr [rcx+1Ch], 1
0x1800283f3  jz      short loc_180028417
0x1800283f5  mov     eax, [rsp+68h+Data]
0x1800283fc  mov     rcx, [rcx+10h]
0x180028400  mov     [rsp+68h+var_30], edi
0x180028404  mov     [rsp+68h+var_38], eax
0x180028408  mov     qword ptr [rsp+68h+samDesired], rbp
0x18002840d  mov     qword ptr [rsp+68h+dwOptions], rsi
0x180028412  call    WPP_SF_qSSdd
0x180028417  test    edi, edi
0x180028419  jg      short loc_18002841F
0x18002841b  mov     ebx, edi
0x18002841d  jmp     short loc_180028461
0x18002841f  movzx   ebx, di
0x180028422  jmp     short loc_18002845B
0x180028424  mov     rcx, cs:WPP_GLOBAL_Control
0x18002842b  lea     rax, WPP_GLOBAL_Control
0x180028432  cmp     rcx, rax
0x180028435  jz      short loc_180028454
0x180028437  test    byte ptr [rcx+1Ch], 1
0x18002843b  jz      short loc_180028454
0x18002843d  mov     rcx, [rcx+10h]
0x180028441  mov     edx, 18h
0x180028446  mov     [rsp+68h+samDesired], ebx
0x18002844a  mov     qword ptr [rsp+68h+dwOptions], rsi
0x18002844f  call    WPP_SF_qSd
0x180028454  test    ebx, ebx
0x180028456  jle     short loc_180028463
0x180028458  movzx   ebx, bx
0x18002845b  or      ebx, 80070000h
0x180028461  test    ebx, ebx
0x180028463  mov     eax, 80004005h
0x180028468  cmovns  ebx, eax
0x18002846b  mov     eax, ebx
0x18002846d  jmp     short loc_1800284A2
0x18002846f  mov     rcx, cs:WPP_GLOBAL_Control
0x180028476  lea     rax, WPP_GLOBAL_Control
0x18002847d  cmp     rcx, rax
0x180028480  jz      short loc_18002849D
0x180028482  test    byte ptr [rcx+1Ch], 1
0x180028486  jz      short loc_18002849D
0x180028488  mov     rcx, [rcx+10h]
0x18002848c  lea     r8, WPP_bc50b57d3a7f3ca15f27abc6215da79e_Traceguids
0x180028493  mov     edx, 16h
0x180028498  call    WPP_SF_
0x18002849d  mov     eax, 80070057h
0x1800284a2  mov     rbx, [rsp+68h+arg_8]
0x1800284a7  add     rsp, 50h
0x1800284ab  pop     rdi
0x1800284ac  pop     rsi
0x1800284ad  pop     rbp
0x1800284ae  retn
```
