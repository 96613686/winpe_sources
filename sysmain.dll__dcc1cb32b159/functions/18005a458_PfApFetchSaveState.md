# PfApFetchSaveState

- ea: `0x18005a458`
- end: `0x18005a695`
- name: `PfApFetchSaveState`
- size: `573`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003b118`
- `0x18005c994`

## callees

- `0x180023698`
- `0x18003875c`
- `0x180039f94`
- `0x18004ebf4`
- `0x18005a458`
- `0x18006d124`
- `0x180073e28`
- `0x1800b645a`
- `0x1800b64c0`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x18005a66d`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x18005a66d`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18005a60b`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18005a60b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005a657`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005a657`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005a4bc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005a4bc`

## pseudocode

```c
__int64 __fastcall PfApFetchSaveState(__int64 a1)
{
  void *v1; // rbx
  bool v3; // cc
  unsigned int v4; // edi
  int v5; // r12d
  void *v6; // rcx
  unsigned int v7; // r12d
  _DWORD *v8; // rax
  _DWORD *v9; // r15
  _DWORD *v10; // r13
  _QWORD *v11; // rsi
  _QWORD *v12; // rbx
  unsigned int v13; // eax
  DWORD LengthSid; // eax
  unsigned int SidHash; // eax
  unsigned int v17; // [rsp+30h] [rbp-99h] BYREF
  _QWORD *v18; // [rsp+38h] [rbp-91h] BYREF
  void *v19; // [rsp+40h] [rbp-89h] BYREF
  wchar_t pszDest[64]; // [rsp+50h] [rbp-79h] BYREF

  v1 = 0;
  v3 = *(_DWORD *)a1 <= 0x6EB3E4u;
  v19 = 0;
  if ( v3 )
  {
    v5 = 296 * *(_DWORD *)a1;
    v6 = *(void **)(*(_QWORD *)&PfSvcGlobals + 88LL);
    v7 = v5 + 8;
    v17 = v7;
    v8 = HeapAlloc(v6, 0, v7);
    v9 = v8;
    if ( v8 )
    {
      memset_0(v8, 0, v7);
      *v9 = 2;
      v10 = v9 + 2;
      v9[1] = *(_DWORD *)a1;
      v11 = *(_QWORD **)(a1 + 8);
      v12 = v11;
      while ( 1 )
      {
        v18 = v12;
        if ( !v12 )
          break;
        if ( (*v12 & 0x8000000000000002uLL) == 0x8000000000000002uLL )
        {
          PfsHashTableCorruptionCallback(a1, 30, &v18);
          v12 = v18;
        }
        if ( !v12 )
          break;
        v12 = (_QWORD *)*v12;
        if ( ((unsigned __int8)v12 & 1) != 0 )
          break;
LABEL_16:
        if ( !v12 )
          goto LABEL_18;
        *((_QWORD *)v10 + 33) = v12[10];
        *((_QWORD *)v10 + 34) = v12[11];
        *((_WORD *)v10 + 144) = *((_WORD *)v12 + 50);
        v10[70] = *((_DWORD *)v12 + 24);
        *((_BYTE *)v10 + 290) = *((_BYTE *)v12 + 102);
        v10[71] = *((_DWORD *)v12 + 2);
        StringCchCopyW((STRSAFE_LPWSTR)v10, 0x80u, (STRSAFE_LPCWSTR)v12[9]);
        *((_QWORD *)v10 + 32) = v12[5];
        v10 += 74;
      }
      for ( ++v11;
            (unsigned __int64)v11 < *(_QWORD *)(a1 + 8) + 8 * ((unsigned __int64)*(unsigned int *)(a1 + 4) >> 5);
            ++v11 )
      {
        v12 = (_QWORD *)*v11;
        if ( (*v11 & 1) == 0 )
        {
          v18 = (_QWORD *)*v11;
          goto LABEL_16;
        }
      }
LABEL_18:
      v13 = PfsCompressBuffer((_DWORD)v9, v17, (unsigned int)&v19, (unsigned int)&v17, 0x10000);
      v1 = v19;
      v4 = v13;
      if ( !v13 )
      {
        LengthSid = GetLengthSid(*(PSID *)(a1 + 72));
        SidHash = PfsGetSidHash(*(_QWORD *)(a1 + 72), LengthSid);
        StringCbPrintfW(pszDest, 0x80u, L"ApFetch_%08lx", SidHash);
        v4 = PfApRegValueSet(pszDest, v1, v17);
      }
      HeapFree(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, v9);
    }
    else
    {
      v4 = 8;
    }
    if ( v1 )
      VirtualFree(v1, 0, 0x8000u);
  }
  else
  {
    return 111;
  }
  return v4;
}

```

## disassembly

```asm
0x18005a458  push    rbp
0x18005a45a  push    rbx
0x18005a45b  push    rsi
0x18005a45c  push    rdi
0x18005a45d  push    r12
0x18005a45f  push    r13
0x18005a461  push    r14
0x18005a463  push    r15
0x18005a465  lea     rbp, [rsp-1Fh]
0x18005a46a  sub     rsp, 0E8h
0x18005a471  mov     rax, cs:__security_cookie
0x18005a478  xor     rax, rsp
0x18005a47b  mov     [rbp+57h+var_50], rax
0x18005a47f  xor     ebx, ebx
0x18005a481  mov     r14, rcx
0x18005a484  cmp     dword ptr [rcx], 6EB3E4h
0x18005a48a  mov     [rsp+120h+var_E0], rbx
0x18005a48f  jbe     short loc_18005A499
0x18005a491  lea     edi, [rbx+6Fh]
0x18005a494  jmp     loc_18005A673
0x18005a499  imul    r12d, [rcx], 128h
0x18005a4a0  xor     edx, edx; dwFlags
0x18005a4a2  mov     rcx, cs:PfSvcGlobals
0x18005a4a9  mov     rcx, [rcx+58h]; hHeap
0x18005a4ad  add     r12d, 8
0x18005a4b1  mov     r8d, r12d; dwBytes
0x18005a4b4  mov     [rsp+120h+var_F0], r12d
0x18005a4b9  mov     edi, r12d
0x18005a4bc  call    cs:__imp_HeapAlloc
0x18005a4c2  mov     r15, rax
0x18005a4c5  test    rax, rax
0x18005a4c8  jnz     short loc_18005A4D2
0x18005a4ca  lea     edi, [rax+8]
0x18005a4cd  jmp     loc_18005A65D
0x18005a4d2  mov     r8, rdi; Size
0x18005a4d5  xor     edx, edx; Val
0x18005a4d7  mov     rcx, r15; void *
0x18005a4da  call    memset_0
0x18005a4df  mov     dword ptr [r15], 2
0x18005a4e6  lea     r13, [r15+8]
0x18005a4ea  mov     eax, [r14]
0x18005a4ed  mov     edi, 8
0x18005a4f2  mov     [r15+4], eax
0x18005a4f6  mov     r12, 8000000000000002h
0x18005a500  mov     rsi, [r14+8]
0x18005a504  mov     rbx, rsi
0x18005a507  mov     [rsp+120h+var_E8], rbx
0x18005a50c  test    rbx, rbx
0x18005a50f  jz      short loc_18005A540
0x18005a511  mov     rax, [rbx]
0x18005a514  and     rax, r12
0x18005a517  cmp     rax, r12
0x18005a51a  jnz     short loc_18005A533
0x18005a51c  lea     r8, [rsp+120h+var_E8]
0x18005a521  mov     edx, 1Eh
0x18005a526  mov     rcx, r14
0x18005a529  call    PfsHashTableCorruptionCallback
0x18005a52e  mov     rbx, [rsp+120h+var_E8]
0x18005a533  test    rbx, rbx
0x18005a536  jz      short loc_18005A540
0x18005a538  mov     rbx, [rbx]
0x18005a53b  test    bl, 1
0x18005a53e  jz      short loc_18005A56E
0x18005a540  mov     ecx, [r14+4]
0x18005a544  add     rsi, rdi
0x18005a547  mov     rax, [r14+8]
0x18005a54b  shr     rcx, 5
0x18005a54f  lea     rdx, [rax+rcx*8]
0x18005a553  cmp     rsi, rdx
0x18005a556  jnb     loc_18005A5DE
0x18005a55c  mov     rbx, [rsi]
0x18005a55f  test    bl, 1
0x18005a562  jz      short loc_18005A569
0x18005a564  add     rsi, rdi
0x18005a567  jmp     short loc_18005A553
0x18005a569  mov     [rsp+120h+var_E8], rbx
0x18005a56e  mov     rax, rbx
0x18005a571  test    rax, rax
0x18005a574  jz      short loc_18005A5DE
0x18005a576  mov     rax, [rbx+50h]
0x18005a57a  mov     edx, 80h; cchDest
0x18005a57f  mov     [r13+108h], rax
0x18005a586  mov     rcx, r13; pszDest
0x18005a589  mov     rax, [rbx+58h]
0x18005a58d  mov     [r13+110h], rax
0x18005a594  movzx   eax, word ptr [rbx+64h]
0x18005a598  mov     [r13+120h], ax
0x18005a5a0  mov     eax, [rbx+60h]
0x18005a5a3  mov     [r13+118h], eax
0x18005a5aa  mov     al, [rbx+66h]
0x18005a5ad  mov     [r13+122h], al
0x18005a5b4  mov     eax, [rbx+8]
0x18005a5b7  mov     [r13+11Ch], eax
0x18005a5be  mov     r8, [rbx+48h]; pszSrc
0x18005a5c2  call    StringCchCopyW
0x18005a5c7  mov     r11, [rbx+28h]
0x18005a5cb  mov     [r13+100h], r11
0x18005a5d2  add     r13, 128h
0x18005a5d9  jmp     loc_18005A507
0x18005a5de  mov     edx, [rsp+120h+var_F0]
0x18005a5e2  lea     r9, [rsp+120h+var_F0]
0x18005a5e7  lea     r8, [rsp+120h+var_E0]
0x18005a5ec  mov     [rsp+120h+var_100], 10000h
0x18005a5f4  mov     rcx, r15
0x18005a5f7  call    PfsCompressBuffer
0x18005a5fc  mov     rbx, [rsp+120h+var_E0]
0x18005a601  mov     edi, eax
0x18005a603  test    eax, eax
0x18005a605  jnz     short loc_18005A647
0x18005a607  mov     rcx, [r14+48h]; pSid
0x18005a60b  call    cs:__imp_GetLengthSid
0x18005a611  mov     rcx, [r14+48h]
0x18005a615  mov     edx, eax
0x18005a617  call    PfsGetSidHash
0x18005a61c  mov     r9d, eax
0x18005a61f  lea     r8, aApfetch08lx; "ApFetch_%08lx"
0x18005a626  mov     edx, 80h; cbDest
0x18005a62b  lea     rcx, [rbp+57h+pszDest]; pszDest
0x18005a62f  call    StringCbPrintfW
0x18005a634  mov     r8d, [rsp+120h+var_F0]
0x18005a639  lea     rcx, [rbp+57h+pszDest]
0x18005a63d  mov     rdx, rbx
0x18005a640  call    PfApRegValueSet
0x18005a645  mov     edi, eax
0x18005a647  mov     rcx, cs:PfSvcGlobals
0x18005a64e  mov     r8, r15; lpMem
0x18005a651  xor     edx, edx; dwFlags
0x18005a653  mov     rcx, [rcx+58h]; hHeap
0x18005a657  call    cs:__imp_HeapFree
0x18005a65d  test    rbx, rbx
0x18005a660  jz      short loc_18005A673
0x18005a662  xor     edx, edx; dwSize
0x18005a664  mov     r8d, 8000h; dwFreeType
0x18005a66a  mov     rcx, rbx; lpAddress
0x18005a66d  call    cs:__imp_VirtualFree
0x18005a673  mov     eax, edi
0x18005a675  mov     rcx, [rbp+57h+var_50]
0x18005a679  xor     rcx, rsp; StackCookie
0x18005a67c  call    __security_check_cookie
0x18005a681  add     rsp, 0E8h
0x18005a688  pop     r15
0x18005a68a  pop     r14
0x18005a68c  pop     r13
0x18005a68e  pop     r12
0x18005a690  pop     rdi
0x18005a691  pop     rsi
0x18005a692  pop     rbx
0x18005a693  pop     rbp
0x18005a694  retn
```
