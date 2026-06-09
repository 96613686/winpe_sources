# ApplySettings::GetVariant(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,tagVARIANT &)

- ea: `0x180043d8c`
- end: `0x180043ee6`
- name: `?GetVariant@ApplySettings@@AEAAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEAUtagVARIANT@@@Z`
- size: `346`
- prototype: ``
- caller_count: `6`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180042d5c`
- `0x1800444d8`
- `0x1800447a0`
- `0x180044b94`
- `0x18004520c`
- `0x180045bd4`

## callees

- `0x18002cca4`
- `0x18002cd00`
- `0x1800388a0`
- `0x180042a80`
- `0x180043d8c`

## import_xrefs

- `msvcrt!wcstol` at `0x180043db7`
- `msvcrt!wcstol` at `0x180043ed2`
- `msvcrt!wcstol` at `0x180043db7`
- `msvcrt!wcstol` at `0x180043ed2`
- `OLEAUT32!__imp_SysAllocString` at `0x180043eb1`
- `OLEAUT32!__imp_SysAllocString` at `0x180043eb1`

## string_xrefs

- `0x180043e51`: `Unexpected data: error in your configuration file`

## pseudocode

```c
__int16 __fastcall ApplySettings::GetVariant(__int64 a1, __int64 a2, const wchar_t *a3, __int64 a4)
{
  const wchar_t *v6; // rax
  int v7; // esi
  PVOID *v8; // rcx
  BSTR v9; // rax

  v6 = (const wchar_t *)a2;
  if ( *(_QWORD *)(a2 + 24) >= 8u )
    v6 = *(const wchar_t **)a2;
  v7 = wcstol(v6, 0, 10);
  v8 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    WppDbgPrint("type = %d");
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      65,
      (unsigned int)&WPP_70cc9e363f77355498ae630336bd681a_Traceguids,
      (unsigned int)"NPSDS",
      v7);
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v7 == 3 )
  {
    *(_WORD *)a4 = 3;
    if ( *((_QWORD *)a3 + 3) >= 8u )
      a3 = *(const wchar_t **)a3;
    LODWORD(v9) = wcstol(a3, 0, 10);
    *(_DWORD *)(a4 + 8) = (_DWORD)v9;
  }
  else if ( v7 == 8 )
  {
    *(_WORD *)a4 = 8;
    if ( *((_QWORD *)a3 + 3) >= 8u )
      a3 = *(const wchar_t **)a3;
    v9 = SysAllocString(a3);
    *(_QWORD *)(a4 + 8) = v9;
  }
  else
  {
    LOWORD(v9) = 11;
    if ( v7 == 11 )
    {
      *(_WORD *)a4 = 11;
      LOWORD(v9) = ((unsigned __int8)std::operator==<unsigned short>(a3, L"-1") ^ 1) - 1;
      *(_WORD *)(a4 + 8) = (_WORD)v9;
    }
    else if ( v8 != &WPP_GLOBAL_Control && *((_BYTE *)v8 + 25) >= 2u && (*((_BYTE *)v8 + 28) & 0x10) != 0 )
    {
      WppDbgPrint("Unexpected data: error in your configuration file");
      LOWORD(v9) = WPP_SF_s(
                     *((_QWORD *)WPP_GLOBAL_Control + 2),
                     66,
                     &WPP_70cc9e363f77355498ae630336bd681a_Traceguids,
                     "NPSDS");
    }
  }
  return (__int16)v9;
}

```

## disassembly

```asm
0x180043d8c  push    rbx
0x180043d8e  push    rbp
0x180043d8f  push    rsi
0x180043d90  push    rdi
0x180043d91  push    r14
0x180043d93  sub     rsp, 30h
0x180043d97  mov     ebp, 8
0x180043d9c  mov     rdi, r9
0x180043d9f  mov     rbx, r8
0x180043da2  mov     rax, rdx
0x180043da5  cmp     [rdx+18h], rbp
0x180043da9  jb      short loc_180043DAE
0x180043dab  mov     rax, [rdx]
0x180043dae  xor     edx, edx; EndPtr
0x180043db0  mov     rcx, rax; String
0x180043db3  lea     r8d, [rdx+0Ah]; Radix
0x180043db7  call    cs:__imp_wcstol
0x180043dbd  mov     esi, eax
0x180043dbf  mov     rcx, cs:WPP_GLOBAL_Control
0x180043dc6  lea     r14, WPP_GLOBAL_Control
0x180043dcd  cmp     rcx, r14
0x180043dd0  jz      short loc_180043E1A
0x180043dd2  cmp     byte ptr [rcx+19h], 4
0x180043dd6  jb      short loc_180043E1A
0x180043dd8  test    byte ptr [rcx+1Ch], 10h
0x180043ddc  jz      short loc_180043E1A
0x180043dde  mov     edx, eax
0x180043de0  lea     rcx, aTypeD; "type = %d"
0x180043de7  call    WppDbgPrint
0x180043dec  mov     rcx, cs:WPP_GLOBAL_Control
0x180043df3  lea     r9, aNpsds; "NPSDS"
0x180043dfa  mov     edx, 41h ; 'A'
0x180043dff  mov     [rsp+58h+var_38], esi
0x180043e03  lea     r8, WPP_70cc9e363f77355498ae630336bd681a_Traceguids
0x180043e0a  mov     rcx, [rcx+10h]
0x180043e0e  call    WPP_SF_sd
0x180043e13  mov     rcx, cs:WPP_GLOBAL_Control
0x180043e1a  mov     eax, 3
0x180043e1f  cmp     esi, eax
0x180043e21  jz      loc_180043EBD
0x180043e27  cmp     esi, ebp
0x180043e29  jz      short loc_180043EA2
0x180043e2b  mov     eax, 0Bh
0x180043e30  cmp     esi, eax
0x180043e32  jz      short loc_180043E82
0x180043e34  cmp     rcx, r14
0x180043e37  jz      loc_180043EDB
0x180043e3d  cmp     byte ptr [rcx+19h], 2
0x180043e41  jb      loc_180043EDB
0x180043e47  test    byte ptr [rcx+1Ch], 10h
0x180043e4b  jz      loc_180043EDB
0x180043e51  lea     rcx, aUnexpectedData; "Unexpected data: error in your configur"...
0x180043e58  call    WppDbgPrint
0x180043e5d  mov     rcx, cs:WPP_GLOBAL_Control
0x180043e64  lea     r9, aNpsds; "NPSDS"
0x180043e6b  mov     edx, 42h ; 'B'
0x180043e70  lea     r8, WPP_70cc9e363f77355498ae630336bd681a_Traceguids
0x180043e77  mov     rcx, [rcx+10h]
0x180043e7b  call    WPP_SF_s
0x180043e80  jmp     short loc_180043EDB
0x180043e82  lea     rdx, a1; "-1"
0x180043e89  mov     [rdi], ax
0x180043e8c  mov     rcx, rbx
0x180043e8f  call    ??$?8GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@PEBG@Z; std::operator==<ushort>(std::wstring const &,ushort const *)
0x180043e94  xor     al, 1
0x180043e96  movzx   eax, al
0x180043e99  dec     ax
0x180043e9c  mov     [rdi+8], ax
0x180043ea0  jmp     short loc_180043EDB
0x180043ea2  mov     [rdi], bp
0x180043ea5  cmp     [rbx+18h], rbp
0x180043ea9  jb      short loc_180043EAE
0x180043eab  mov     rbx, [rbx]
0x180043eae  mov     rcx, rbx; psz
0x180043eb1  call    cs:__imp_SysAllocString
0x180043eb7  mov     [rdi+8], rax
0x180043ebb  jmp     short loc_180043EDB
0x180043ebd  mov     [rdi], ax
0x180043ec0  cmp     [rbx+18h], rbp
0x180043ec4  jb      short loc_180043EC9
0x180043ec6  mov     rbx, [rbx]
0x180043ec9  xor     edx, edx; EndPtr
0x180043ecb  mov     rcx, rbx; String
0x180043ece  lea     r8d, [rdx+0Ah]; Radix
0x180043ed2  call    cs:__imp_wcstol
0x180043ed8  mov     [rdi+8], eax
0x180043edb  add     rsp, 30h
0x180043edf  pop     r14
0x180043ee1  pop     rdi
0x180043ee2  pop     rsi
0x180043ee3  pop     rbp
0x180043ee4  pop     rbx
0x180043ee5  retn
```
