# NonceCreate

- ea: `0x180024328`
- end: `0x1800245c9`
- name: `NonceCreate`
- size: `673`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18001e4b0`

## callees

- `0x18000c6f0`
- `0x18000c850`
- `0x180011fec`
- `0x180012880`
- `0x1800185b8`
- `0x180024000`
- `0x180024328`
- `0x1800245d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800244c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800244c9`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGenRandom` at `0x1800244ad`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGenRandom` at `0x1800244ad`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002435f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002435f`

## pseudocode

```c
__int64 __fastcall NonceCreate(__int64 a1)
{
  PVOID *v2; // rcx
  unsigned int v3; // edi
  int v4; // eax
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  DWORD LastError; // eax
  __int64 v9; // r8
  __int64 v10; // r9
  __int16 v11; // ax
  int v12; // [rsp+28h] [rbp-90h]
  int v13; // [rsp+30h] [rbp-88h]
  int v14; // [rsp+38h] [rbp-80h]
  struct _FILETIME v15; // [rsp+50h] [rbp-68h] BYREF
  BYTE pbBuffer[16]; // [rsp+58h] [rbp-60h] BYREF
  BYTE v17[16]; // [rsp+68h] [rbp-50h] BYREF
  __int128 v18; // [rsp+78h] [rbp-40h]

  v15 = 0;
  GetSystemTimeAsFileTime(&v15);
  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_44f4a821d5a93d79ff0a58e212c9bb48_Traceguids);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !*(_QWORD *)(a1 + 8) )
  {
    if ( (int)StringAllocate(a1, 124) < 0 )
    {
      v3 = -2146893056;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_44f4a821d5a93d79ff0a58e212c9bb48_Traceguids, 2148074240LL);
      goto LABEL_29;
    }
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( *(_WORD *)(a1 + 2) < 0x7Du )
  {
    if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 1) != 0 )
      WPP_SF_(v2[2], 18, WPP_44f4a821d5a93d79ff0a58e212c9bb48_Traceguids);
    v3 = -1073741789;
    goto LABEL_29;
  }
  qmemcpy(*(void **)(a1 + 8), "+Upgraded+v1", 12);
  v4 = NonceHashTargetInfo(&g_ustrWorkstationName, (BYTE *)hMem, *(_QWORD *)(a1 + 8) + 12LL);
  v3 = v4;
  if ( v4 < 0 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_29;
    v6 = 19;
    goto LABEL_28;
  }
  BinToHex(&v15, 8, *(_QWORD *)(a1 + 8) + 44LL);
  if ( CryptGenRandom(g_hCryptProv, 0x10u, pbBuffer) )
  {
    BinToHex(pbBuffer, 16, v17);
    v9 = *(_QWORD *)(a1 + 8);
    *(_OWORD *)(v9 + 60) = *(_OWORD *)v17;
    *(_OWORD *)(v9 + 76) = v18;
    v4 = NonceHash(
           *(BYTE **)(a1 + 8),
           0x2Cu,
           (BYTE *)(*(_QWORD *)(a1 + 8) + 44LL),
           v10,
           v17,
           v12,
           v13,
           v14,
           *(_QWORD *)(a1 + 8) + 92LL);
    v3 = v4;
    if ( v4 >= 0 )
    {
      v11 = 124;
      goto LABEL_31;
    }
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
LABEL_29:
      v11 = 0;
LABEL_31:
      *(_WORD *)a1 = v11;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_44f4a821d5a93d79ff0a58e212c9bb48_Traceguids);
      return v3;
    }
    v6 = 21;
LABEL_28:
    WPP_SF_d(v5[2], v6, WPP_44f4a821d5a93d79ff0a58e212c9bb48_Traceguids, (unsigned int)v4);
    goto LABEL_29;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    LastError = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_44f4a821d5a93d79ff0a58e212c9bb48_Traceguids, LastError);
  }
  return 3221225701LL;
}

```

## disassembly

```asm
0x180024328  mov     r11, rsp
0x18002432b  mov     [r11+10h], rbx
0x18002432f  mov     [r11+18h], rbp
0x180024333  push    rsi
0x180024334  push    rdi
0x180024335  push    r14
0x180024337  sub     rsp, 0A0h
0x18002433e  mov     rax, cs:__security_cookie
0x180024345  xor     rax, rsp
0x180024348  mov     [rsp+0B8h+var_28], rax
0x180024350  mov     rbx, rcx
0x180024353  mov     qword ptr [r11-68h], 0
0x18002435b  lea     rcx, [r11-68h]; lpSystemTimeAsFileTime
0x18002435f  call    cs:__imp_GetSystemTimeAsFileTime
0x180024365  mov     rcx, cs:WPP_GLOBAL_Control
0x18002436c  lea     rsi, WPP_GLOBAL_Control
0x180024373  lea     rbp, WPP_44f4a821d5a93d79ff0a58e212c9bb48_Traceguids
0x18002437a  cmp     rcx, rsi
0x18002437d  jz      short loc_18002439D
0x18002437f  test    byte ptr [rcx+1Ch], 80h
0x180024383  jz      short loc_18002439D
0x180024385  mov     rcx, [rcx+10h]
0x180024389  mov     edx, 10h
0x18002438e  mov     r8, rbp
0x180024391  call    WPP_SF_
0x180024396  mov     rcx, cs:WPP_GLOBAL_Control
0x18002439d  cmp     qword ptr [rbx+8], 0
0x1800243a2  mov     r14d, 7Ch ; '|'
0x1800243a8  jnz     short loc_1800243FA
0x1800243aa  mov     edx, r14d
0x1800243ad  mov     rcx, rbx
0x1800243b0  call    StringAllocate
0x1800243b5  test    eax, eax
0x1800243b7  jns     short loc_1800243F3
0x1800243b9  mov     edi, 80090300h
0x1800243be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800243c5  cmp     rcx, rsi
0x1800243c8  jz      loc_180024571
0x1800243ce  test    byte ptr [rcx+1Ch], 1
0x1800243d2  jz      loc_180024571
0x1800243d8  mov     rcx, [rcx+10h]
0x1800243dc  lea     edx, [r14-6Bh]
0x1800243e0  mov     r9d, 80090300h
0x1800243e6  mov     r8, rbp
0x1800243e9  call    WPP_SF_d
0x1800243ee  jmp     loc_180024571
0x1800243f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800243fa  cmp     word ptr [rbx+2], 7Dh ; '}'
0x1800243ff  jnb     short loc_180024427
0x180024401  cmp     rcx, rsi
0x180024404  jz      short loc_18002441D
0x180024406  test    byte ptr [rcx+1Ch], 1
0x18002440a  jz      short loc_18002441D
0x18002440c  mov     rcx, [rcx+10h]
0x180024410  mov     edx, 12h
0x180024415  mov     r8, rbp
0x180024418  call    WPP_SF_
0x18002441d  mov     edi, 0C0000023h
0x180024422  jmp     loc_180024571
0x180024427  mov     rcx, [rbx+8]
0x18002442b  movsd   xmm0, qword ptr cs:aUpgradedV1; "+Upgraded+v1"
0x180024433  movsd   qword ptr [rcx], xmm0
0x180024437  mov     eax, dword ptr cs:aUpgradedV1+8; "d+v1"
0x18002443d  mov     [rcx+8], eax
0x180024440  lea     rcx, g_ustrWorkstationName; SourceString
0x180024447  mov     r8, [rbx+8]
0x18002444b  mov     rdx, cs:hMem; pbData
0x180024452  add     r8, 0Ch
0x180024456  call    NonceHashTargetInfo
0x18002445b  mov     edi, eax
0x18002445d  test    eax, eax
0x18002445f  jns     short loc_180024485
0x180024461  mov     rcx, cs:WPP_GLOBAL_Control
0x180024468  cmp     rcx, rsi
0x18002446b  jz      loc_180024571
0x180024471  test    byte ptr [rcx+1Ch], 1
0x180024475  jz      loc_180024571
0x18002447b  mov     edx, 13h
0x180024480  jmp     loc_180024562
0x180024485  mov     r8, [rbx+8]
0x180024489  lea     rcx, [rsp+0B8h+var_68]
0x18002448e  add     r8, 2Ch ; ','
0x180024492  mov     edx, 8
0x180024497  call    BinToHex
0x18002449c  mov     rcx, cs:g_hCryptProv; hProv
0x1800244a3  lea     r8, [rsp+0B8h+pbBuffer]; pbBuffer
0x1800244a8  mov     edx, 10h; dwLen
0x1800244ad  call    cs:__imp_CryptGenRandom
0x1800244b3  test    eax, eax
0x1800244b5  jnz     short loc_1800244F4
0x1800244b7  mov     rax, cs:WPP_GLOBAL_Control
0x1800244be  cmp     rax, rsi
0x1800244c1  jz      short loc_1800244EA
0x1800244c3  test    byte ptr [rax+1Ch], 4
0x1800244c7  jz      short loc_1800244EA
0x1800244c9  call    cs:__imp_GetLastError
0x1800244cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800244d6  mov     edx, 14h
0x1800244db  mov     r9d, eax
0x1800244de  mov     r8, rbp
0x1800244e1  mov     rcx, [rcx+10h]
0x1800244e5  call    WPP_SF_d
0x1800244ea  mov     eax, 0C00000E5h
0x1800244ef  jmp     loc_1800245A1
0x1800244f4  lea     r8, [rsp+0B8h+var_50]
0x1800244f9  mov     edx, 10h
0x1800244fe  lea     rcx, [rsp+0B8h+pbBuffer]
0x180024503  call    BinToHex
0x180024508  mov     r8, [rbx+8]
0x18002450c  mov     edx, 2Ch ; ','; dwDataLen
0x180024511  movups  xmm0, xmmword ptr [rsp+0B8h+var_50]
0x180024516  movups  xmmword ptr [r8+3Ch], xmm0
0x18002451b  movups  xmm1, [rsp+0B8h+var_40]
0x180024520  movups  xmmword ptr [r8+4Ch], xmm1
0x180024525  mov     rcx, [rbx+8]; pbData
0x180024529  lea     r8, [rcx+2Ch]; BYTE *
0x18002452d  lea     rax, [r8+30h]
0x180024531  mov     [rsp+0B8h+var_78], rax; __int64
0x180024536  lea     rax, [rsp+0B8h+var_50]
0x18002453b  mov     [rsp+0B8h+var_98], rax; BYTE *
0x180024540  call    NonceHash
0x180024545  mov     edi, eax
0x180024547  test    eax, eax
0x180024549  jns     short loc_180024575
0x18002454b  mov     rcx, cs:WPP_GLOBAL_Control
0x180024552  cmp     rcx, rsi
0x180024555  jz      short loc_180024571
0x180024557  test    byte ptr [rcx+1Ch], 1
0x18002455b  jz      short loc_180024571
0x18002455d  mov     edx, 15h
0x180024562  mov     rcx, [rcx+10h]
0x180024566  mov     r9d, eax
0x180024569  mov     r8, rbp
0x18002456c  call    WPP_SF_d
0x180024571  xor     eax, eax
0x180024573  jmp     short loc_180024579
0x180024575  movzx   eax, r14w
0x180024579  mov     [rbx], ax
0x18002457c  mov     rcx, cs:WPP_GLOBAL_Control
0x180024583  cmp     rcx, rsi
0x180024586  jz      short loc_18002459F
0x180024588  test    byte ptr [rcx+1Ch], 80h
0x18002458c  jz      short loc_18002459F
0x18002458e  mov     rcx, [rcx+10h]
0x180024592  mov     edx, 16h
0x180024597  mov     r8, rbp
0x18002459a  call    WPP_SF_
0x18002459f  mov     eax, edi
0x1800245a1  mov     rcx, [rsp+0B8h+var_28]
0x1800245a9  xor     rcx, rsp; StackCookie
0x1800245ac  call    __security_check_cookie
0x1800245b1  lea     r11, [rsp+0B8h+var_18]
0x1800245b9  mov     rbx, [r11+28h]
0x1800245bd  mov     rbp, [r11+30h]
0x1800245c1  mov     rsp, r11
0x1800245c4  pop     r14
0x1800245c6  pop     rdi
0x1800245c7  pop     rsi
0x1800245c8  retn
```
