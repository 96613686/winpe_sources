# GetFinalPathFlags

- ea: `0x18000c3b0`
- end: `0x18000c577`
- name: `GetFinalPathFlags`
- size: `455`
- prototype: `__int64 __fastcall(wchar_t *String1, _QWORD *, __int64 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path`

## callers

- `0x18000c580`

## callees

- `0x18000c3b0`
- `0x1800131ae`
- `0x1800131e0`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18000c4b1`
- `msvcrt!_wcsnicmp` at `0x18000c4d4`
- `msvcrt!_wcsnicmp` at `0x18000c4f2`
- `msvcrt!_wcsnicmp` at `0x18000c4b1`
- `msvcrt!_wcsnicmp` at `0x18000c4d4`
- `msvcrt!_wcsnicmp` at `0x18000c4f2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c54c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c54c`

## pseudocode

```c
__int64 __fastcall GetFinalPathFlags(wchar_t *String1, _QWORD *a2, __int64 *a3)
{
  wchar_t v6; // si
  unsigned int v7; // r15d
  __int64 v8; // rbx
  __int64 v9; // rbp
  wchar_t v10; // cx
  wchar_t *v11; // rsi
  wchar_t String2[8]; // [rsp+20h] [rbp-98h] BYREF
  wchar_t v14[8]; // [rsp+30h] [rbp-88h] BYREF
  wchar_t v15[12]; // [rsp+40h] [rbp-78h] BYREF
  wchar_t v16[16]; // [rsp+58h] [rbp-60h] BYREF

  wcscpy(String2, L"\\\\?\\");
  wcscpy(v16, L"\\\\?\\GLBALROOT");
  wcscpy(v15, L"\\\\?\\Volume{");
  wcscpy(v14, L"\\Device");
  if ( !String1 || (v6 = *String1) == 0 )
  {
    SetLastError(0x57u);
    return 4;
  }
  v7 = 0;
  v8 = 0;
  v9 = 0;
  if ( wcsncmp_0(String1, String2, 4u)
    || (v10 = String1[4], (unsigned __int16)(v10 - 97) > 0x19u) && (unsigned __int16)(v10 - 65) > 0x19u
    || String1[5] != 58 )
  {
    if ( (unsigned __int16)(v6 - 97) > 0x19u && (unsigned __int16)(v6 - 65) > 0x19u || String1[1] != 58 )
    {
      v8 = _wcsnicmp(String1, v16, 0xEu) == 0 ? 0xE : 0;
      v11 = &String1[v8];
      if ( !_wcsnicmp(v11, v15, 0xBu) )
      {
        v7 = 1;
        goto LABEL_19;
      }
      if ( !_wcsnicmp(&String1[v8], v14, 7u) )
      {
        v7 = 2;
        goto LABEL_19;
      }
      if ( (unsigned __int16)(*v11 - 97) > 0x19u && (unsigned __int16)(*v11 - 65) > 0x19u || v11[1] != 58 )
      {
        v7 = 4;
        v9 = -1;
        goto LABEL_19;
      }
    }
    v9 = 4;
  }
LABEL_19:
  if ( a2 )
    *a2 = v8;
  if ( a3 )
    *a3 = v9;
  return v7;
}

```

## disassembly

```asm
0x18000c3b0  push    rbx
0x18000c3b2  push    rbp
0x18000c3b3  push    rsi
0x18000c3b4  push    r12
0x18000c3b6  push    r13
0x18000c3b8  push    r14
0x18000c3ba  push    r15
0x18000c3bc  sub     rsp, 80h
0x18000c3c3  mov     rax, cs:__security_cookie
0x18000c3ca  xor     rax, rsp
0x18000c3cd  mov     [rsp+0B8h+var_40], rax
0x18000c3d2  movsd   xmm0, qword ptr cs:pszSrc; "\\\\?\\"
0x18000c3da  mov     r12, r8
0x18000c3dd  movzx   eax, word ptr cs:pszSrc+8; ""
0x18000c3e4  mov     r13, rdx
0x18000c3e7  movsd   qword ptr [rsp+0B8h+String2], xmm0
0x18000c3ed  mov     r14, rcx
0x18000c3f0  mov     [rsp+0B8h+var_90], ax
0x18000c3f5  movups  xmm0, xmmword ptr cs:aGlobalroot; "\\\\?\\GLOBALROOT"
0x18000c3fc  movups  xmm1, xmmword ptr cs:aGlobalroot+0Eh; "BALROOT"
0x18000c403  movups  xmmword ptr [rsp+0B8h+var_60], xmm0
0x18000c408  movups  xmm0, xmmword ptr cs:aVolume_0; "\\\\?\\Volume{"
0x18000c40f  movups  xmmword ptr [rsp+0B8h+var_60+0Eh], xmm1
0x18000c414  movsd   xmm1, qword ptr cs:aVolume_0+10h; "me{"
0x18000c41c  movsd   [rsp+0B8h+var_68], xmm1
0x18000c422  movups  xmmword ptr [rsp+0B8h+var_78], xmm0
0x18000c427  movups  xmm0, xmmword ptr cs:aDevice; "\\Device"
0x18000c42e  movdqu  xmmword ptr [rsp+0B8h+var_88], xmm0
0x18000c434  test    rcx, rcx
0x18000c437  jz      loc_18000C547
0x18000c43d  movzx   esi, word ptr [rcx]
0x18000c440  xor     eax, eax
0x18000c442  cmp     ax, si
0x18000c445  jz      loc_18000C547
0x18000c44b  lea     r8d, [rax+4]; MaxCount
0x18000c44f  xor     r15d, r15d
0x18000c452  lea     rdx, [rsp+0B8h+String2]; String2
0x18000c457  xor     ebx, ebx
0x18000c459  xor     ebp, ebp
0x18000c45b  call    wcsncmp_0
0x18000c460  mov     dx, 19h
0x18000c464  test    eax, eax
0x18000c466  jnz     short loc_18000C48A
0x18000c468  movzx   ecx, word ptr [r14+8]
0x18000c46d  lea     eax, [rcx-61h]
0x18000c470  cmp     ax, dx
0x18000c473  jbe     short loc_18000C47E
0x18000c475  sub     cx, 41h ; 'A'
0x18000c479  cmp     cx, dx
0x18000c47c  ja      short loc_18000C48A
0x18000c47e  cmp     word ptr [r14+0Ah], 3Ah ; ':'
0x18000c484  jz      loc_18000C530
0x18000c48a  lea     eax, [rsi-61h]
0x18000c48d  cmp     ax, dx
0x18000c490  jbe     short loc_18000C49B
0x18000c492  sub     si, 41h ; 'A'
0x18000c496  cmp     si, dx
0x18000c499  ja      short loc_18000C4A3
0x18000c49b  cmp     word ptr [r14+2], 3Ah ; ':'
0x18000c4a1  jz      short loc_18000C51F
0x18000c4a3  mov     r8d, 0Eh; MaxCount
0x18000c4a9  lea     rdx, [rsp+0B8h+var_60]; String2
0x18000c4ae  mov     rcx, r14; String1
0x18000c4b1  call    cs:__imp__wcsnicmp
0x18000c4b7  mov     r8d, 0Bh; MaxCount
0x18000c4bd  lea     rdx, [rsp+0B8h+var_78]; String2
0x18000c4c2  neg     eax
0x18000c4c4  sbb     rbx, rbx
0x18000c4c7  not     rbx
0x18000c4ca  and     ebx, 0Eh
0x18000c4cd  lea     rsi, [r14+rbx*2]
0x18000c4d1  mov     rcx, rsi; String1
0x18000c4d4  call    cs:__imp__wcsnicmp
0x18000c4da  test    eax, eax
0x18000c4dc  jnz     short loc_18000C4E4
0x18000c4de  lea     r15d, [rax+1]
0x18000c4e2  jmp     short loc_18000C530
0x18000c4e4  mov     r8d, 7; MaxCount
0x18000c4ea  lea     rdx, [rsp+0B8h+var_88]; String2
0x18000c4ef  mov     rcx, rsi; String1
0x18000c4f2  call    cs:__imp__wcsnicmp
0x18000c4f8  test    eax, eax
0x18000c4fa  jnz     short loc_18000C502
0x18000c4fc  lea     r15d, [rax+2]
0x18000c500  jmp     short loc_18000C530
0x18000c502  movzx   ecx, word ptr [rsi]
0x18000c505  lea     eax, [rcx-61h]
0x18000c508  cmp     ax, 19h
0x18000c50c  jbe     short loc_18000C518
0x18000c50e  sub     cx, 41h ; 'A'
0x18000c512  cmp     cx, 19h
0x18000c516  ja      short loc_18000C526
0x18000c518  cmp     word ptr [rsi+2], 3Ah ; ':'
0x18000c51d  jnz     short loc_18000C526
0x18000c51f  mov     ebp, 4
0x18000c524  jmp     short loc_18000C530
0x18000c526  mov     r15d, 4
0x18000c52c  or      rbp, 0FFFFFFFFFFFFFFFFh
0x18000c530  test    r13, r13
0x18000c533  jz      short loc_18000C539
0x18000c535  mov     [r13+0], rbx
0x18000c539  test    r12, r12
0x18000c53c  jz      short loc_18000C542
0x18000c53e  mov     [r12], rbp
0x18000c542  mov     eax, r15d
0x18000c545  jmp     short loc_18000C557
0x18000c547  mov     ecx, 57h ; 'W'; dwErrCode
0x18000c54c  call    cs:__imp_SetLastError
0x18000c552  mov     eax, 4
0x18000c557  mov     rcx, [rsp+0B8h+var_40]
0x18000c55c  xor     rcx, rsp; StackCookie
0x18000c55f  call    __security_check_cookie
0x18000c564  add     rsp, 80h
0x18000c56b  pop     r15
0x18000c56d  pop     r14
0x18000c56f  pop     r13
0x18000c571  pop     r12
0x18000c573  pop     rsi
0x18000c574  pop     rbp
0x18000c575  pop     rbx
0x18000c576  retn
```
