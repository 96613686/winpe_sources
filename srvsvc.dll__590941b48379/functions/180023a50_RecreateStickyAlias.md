# RecreateStickyAlias

- ea: `0x180023a50`
- end: `0x180023bf4`
- name: `RecreateStickyAlias`
- size: `420`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000a460`
- `0x18000b940`
- `0x1800214a4`
- `0x180023400`
- `0x180023a50`
- `0x180024410`
- `0x180026a6c`
- `0x180044010`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x180023b5d`
- `ntdll!RtlFreeUnicodeString` at `0x180023b6d`
- `ntdll!RtlFreeUnicodeString` at `0x180023b5d`
- `ntdll!RtlFreeUnicodeString` at `0x180023b6d`

## pseudocode

```c
__int64 __fastcall RecreateStickyAlias(__int64 a1, __int64 a2, __int64 a3)
{
  int v4; // edx
  size_t *v5; // r8
  _QWORD *v6; // rcx
  const wchar_t *v7; // r9
  int v8; // eax
  _BYTE v10[8]; // [rsp+30h] [rbp-40h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+38h] [rbp-38h] BYREF
  STRSAFE_PCNZWCH psz[2]; // [rsp+48h] [rbp-28h] BYREF
  STRSAFE_PCNZWCH v13[2]; // [rsp+58h] [rbp-18h] BYREF
  __int64 v14; // [rsp+68h] [rbp-8h]

  v14 = 0;
  v10[0] = 0;
  *(_OWORD *)v13 = 0;
  UnicodeString = 0;
  *(_OWORD *)psz = 0;
  if ( !(unsigned __int8)GetStickyAliasInfo(a1, a2, a3, &UnicodeString, psz, v10) )
    return 0;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 89, WPP_6c51fa01af1134468f88fcdefbc326dc_Traceguids, a1);
    v6 = WPP_GLOBAL_Control;
  }
  v7 = 0;
  if ( LOWORD(psz[0]) )
    v7 = psz[1];
  v13[1] = UnicodeString.Buffer;
  v13[0] = v7;
  LOBYTE(v14) = v10[0];
  HIDWORD(v14) = 1;
  if ( !v7 )
    goto LABEL_11;
  if ( StringCchLengthW(v7, 0x100u, 0) || !v13[1] || StringCchLengthW(v13[1], 0x100u, v5) )
  {
    v6 = WPP_GLOBAL_Control;
LABEL_11:
    LOBYTE(v8) = 87;
LABEL_12:
    if ( v6 != &WPP_GLOBAL_Control && (*((_DWORD *)v6 + 7) & 0x100) != 0 && *((_BYTE *)v6 + 25) )
      WPP_SF_SZl(v6[2], v4, (_DWORD)v5, a1, (__int64)&UnicodeString, v8);
    goto LABEL_16;
  }
  if ( dword_18005CE2C && (unsigned int)SsCheckAccess((__int64)&SsConfigInfoSecurityObject, L"SRV Alias Add", 0x10u) )
  {
    LOBYTE(v8) = 5;
LABEL_26:
    v6 = WPP_GLOBAL_Control;
    goto LABEL_12;
  }
  v8 = ((__int64 (__fastcall *)(_QWORD, STRSAFE_PCNZWCH *, __int64))qword_18005E510)(0, v13, 24);
  if ( v8 )
    goto LABEL_26;
  SsAddAliasToRegistry((__int64)v13);
LABEL_16:
  if ( UnicodeString.Buffer )
    RtlFreeUnicodeString(&UnicodeString);
  if ( psz[1] )
    RtlFreeUnicodeString((PUNICODE_STRING)psz);
  return 0;
}

```

## disassembly

```asm
0x180023a50  push    rbp
0x180023a52  push    rbx
0x180023a53  push    rsi
0x180023a54  push    rdi
0x180023a55  push    r14
0x180023a57  mov     rbp, rsp
0x180023a5a  sub     rsp, 70h
0x180023a5e  xor     eax, eax
0x180023a60  lea     r9, [rbp+UnicodeString]
0x180023a64  mov     [rbp+var_8], rax
0x180023a68  xorps   xmm0, xmm0
0x180023a6b  lea     rax, [rbp+var_40]
0x180023a6f  xorps   xmm1, xmm1
0x180023a72  mov     [rsp+70h+var_48], rax
0x180023a77  xor     edi, edi
0x180023a79  lea     rax, [rbp+psz]
0x180023a7d  mov     [rbp+var_40], dil
0x180023a81  mov     [rsp+70h+var_50], rax
0x180023a86  mov     rbx, rcx
0x180023a89  movups  xmmword ptr [rbp+var_18], xmm0
0x180023a8d  movups  xmmword ptr [rbp+UnicodeString.Length], xmm0
0x180023a91  movups  xmmword ptr [rbp+psz], xmm1
0x180023a95  call    GetStickyAliasInfo
0x180023a9a  test    al, al
0x180023a9c  jz      loc_180023B73
0x180023aa2  mov     rcx, cs:WPP_GLOBAL_Control
0x180023aa9  lea     r14, WPP_GLOBAL_Control
0x180023ab0  mov     esi, 100h
0x180023ab5  cmp     rcx, r14
0x180023ab8  jz      short loc_180023AE2
0x180023aba  test    [rcx+1Ch], esi
0x180023abd  jz      short loc_180023AE2
0x180023abf  cmp     byte ptr [rcx+19h], 2
0x180023ac3  jb      short loc_180023AE2
0x180023ac5  mov     rcx, [rcx+10h]
0x180023ac9  lea     edx, [rdi+59h]
0x180023acc  mov     r9, rbx
0x180023acf  lea     r8, WPP_6c51fa01af1134468f88fcdefbc326dc_Traceguids
0x180023ad6  call    WPP_SF_S
0x180023adb  mov     rcx, cs:WPP_GLOBAL_Control
0x180023ae2  cmp     word ptr [rbp+psz], di
0x180023ae6  mov     r9, rdi
0x180023ae9  mov     rax, [rbp+UnicodeString.Buffer]
0x180023aed  cmova   r9, [rbp+psz+8]
0x180023af2  mov     [rbp+var_18+8], rax
0x180023af6  mov     al, [rbp+var_40]
0x180023af9  mov     [rbp+var_18], r9
0x180023afd  mov     byte ptr [rbp+var_8], al
0x180023b00  mov     dword ptr [rbp+var_8+4], 1
0x180023b07  test    r9, r9
0x180023b0a  jz      short loc_180023B25
0x180023b0c  xor     r8d, r8d; pcchLength
0x180023b0f  mov     rdx, rsi; cchMax
0x180023b12  mov     rcx, r9; psz
0x180023b15  call    StringCchLengthW
0x180023b1a  test    eax, eax
0x180023b1c  jz      short loc_180023B80
0x180023b1e  mov     rcx, cs:WPP_GLOBAL_Control
0x180023b25  mov     eax, 57h ; 'W'
0x180023b2a  cmp     rcx, r14
0x180023b2d  jz      short loc_180023B53
0x180023b2f  test    [rcx+1Ch], esi
0x180023b32  jz      short loc_180023B53
0x180023b34  cmp     byte ptr [rcx+19h], 1
0x180023b38  jb      short loc_180023B53
0x180023b3a  mov     rcx, [rcx+10h]
0x180023b3e  mov     r9, rbx
0x180023b41  mov     dword ptr [rsp+70h+var_48], eax
0x180023b45  lea     rax, [rbp+UnicodeString]
0x180023b49  mov     [rsp+70h+var_50], rax
0x180023b4e  call    WPP_SF_SZl
0x180023b53  cmp     [rbp+UnicodeString.Buffer], rdi
0x180023b57  jz      short loc_180023B63
0x180023b59  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x180023b5d  call    cs:__imp_RtlFreeUnicodeString
0x180023b63  cmp     [rbp+psz+8], rdi
0x180023b67  jz      short loc_180023B73
0x180023b69  lea     rcx, [rbp+psz]; UnicodeString
0x180023b6d  call    cs:__imp_RtlFreeUnicodeString
0x180023b73  xor     eax, eax
0x180023b75  add     rsp, 70h
0x180023b79  pop     r14
0x180023b7b  pop     rdi
0x180023b7c  pop     rsi
0x180023b7d  pop     rbx
0x180023b7e  pop     rbp
0x180023b7f  retn
0x180023b80  mov     rcx, [rbp+var_18+8]; psz
0x180023b84  test    rcx, rcx
0x180023b87  jz      short loc_180023B1E
0x180023b89  mov     rdx, rsi; cchMax
0x180023b8c  call    StringCchLengthW
0x180023b91  test    eax, eax
0x180023b93  jnz     short loc_180023B1E
0x180023b95  cmp     cs:dword_18005CE2C, edi
0x180023b9b  jz      short loc_180023BC9
0x180023b9d  lea     r8d, [rax+10h]
0x180023ba1  lea     rdx, aSrvAliasAdd; "SRV Alias Add"
0x180023ba8  lea     rcx, SsConfigInfoSecurityObject
0x180023baf  call    SsCheckAccess
0x180023bb4  test    eax, eax
0x180023bb6  jz      short loc_180023BC9
0x180023bb8  mov     eax, 5
0x180023bbd  mov     rcx, cs:WPP_GLOBAL_Control
0x180023bc4  jmp     loc_180023B2A
0x180023bc9  mov     rax, cs:qword_18005E510
0x180023bd0  lea     rdx, [rbp+var_18]
0x180023bd4  xor     r9d, r9d
0x180023bd7  xor     ecx, ecx
0x180023bd9  lea     r8d, [r9+18h]
0x180023bdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023be2  test    eax, eax
0x180023be4  jnz     short loc_180023BBD
0x180023be6  lea     rcx, [rbp+var_18]
0x180023bea  call    SsAddAliasToRegistry
0x180023bef  jmp     loc_180023B53
```
