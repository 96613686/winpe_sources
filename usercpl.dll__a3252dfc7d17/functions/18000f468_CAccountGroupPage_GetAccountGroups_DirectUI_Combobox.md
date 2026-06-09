# CAccountGroupPage::_GetAccountGroups(DirectUI::Combobox *)

- ea: `0x18000f468`
- end: `0x18000f65f`
- name: `?_GetAccountGroups@CAccountGroupPage@@AEAAJPEAVCombobox@DirectUI@@@Z`
- size: `503`
- prototype: `__int64 __fastcall(CAccountGroupPage *__hidden this, struct DirectUI::Combobox *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000f320`

## callees

- `0x18000f468`
- `0x180063b30`

## import_xrefs

- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x18000f560`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x18000f5d3`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x18000f560`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x18000f5d3`
- `SHLWAPI!__imp_StrCmpICW` at `0x18000f521`
- `SHLWAPI!__imp_StrCmpICW` at `0x18000f53e`
- `SHLWAPI!__imp_StrCmpICW` at `0x18000f521`
- `SHLWAPI!__imp_StrCmpICW` at `0x18000f53e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f582`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f582`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f60d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f60d`
- `samcli!NetLocalGroupEnum` at `0x18000f4cb`
- `samcli!NetLocalGroupEnum` at `0x18000f4cb`
- `netutils!NetApiBufferFree` at `0x18000f636`
- `netutils!NetApiBufferFree` at `0x18000f636`
- `DUI70!?AddString@Combobox@DirectUI@@QEAAHPEBG@Z` at `0x18000f577`
- `DUI70!?AddString@Combobox@DirectUI@@QEAAHPEBG@Z` at `0x18000f577`

## pseudocode

```c
__int64 __fastcall CAccountGroupPage::_GetAccountGroups(CAccountGroupPage *this, struct DirectUI::Combobox *a2)
{
  int v2; // ebx
  signed int v5; // eax
  signed int v6; // edi
  DWORD i; // r14d
  signed int LastError; // eax
  LPWSTR v9; // rcx
  LPBYTE bufptr; // [rsp+40h] [rbp-20h] BYREF
  LPWSTR ppwsz; // [rsp+48h] [rbp-18h] BYREF
  LPWSTR v13; // [rsp+50h] [rbp-10h] BYREF
  ULONG_PTR resumehandle; // [rsp+58h] [rbp-8h] BYREF
  DWORD entriesread; // [rsp+A0h] [rbp+40h] BYREF
  DWORD totalentries; // [rsp+A8h] [rbp+48h] BYREF

  v2 = 0;
  bufptr = 0;
  resumehandle = 0;
  entriesread = 0;
  totalentries = 0;
  while ( v2 >= 0 )
  {
    v5 = NetLocalGroupEnum(0, 1u, &bufptr, 0x2000u, &entriesread, &totalentries, &resumehandle);
    v6 = v5;
    if ( !v5 || v5 == 234 )
    {
      v2 = 0;
      for ( i = 0; i < entriesread; ++i )
      {
        if ( v2 < 0 )
          break;
        if ( StrCmpICW((LPCWSTR)this + 1102, *(LPCWSTR *)&bufptr[16 * i]) )
        {
          if ( StrCmpICW((LPCWSTR)this + 845, *(LPCWSTR *)&bufptr[16 * i]) )
          {
            ppwsz = 0;
            v2 = SHStrDupW(*(LPCWSTR *)&bufptr[16 * i], &ppwsz);
            if ( v2 >= 0 )
            {
              if ( DirectUI::Combobox::AddString(a2, ppwsz) == -1 )
              {
                LastError = GetLastError();
                v2 = LastError;
                if ( LastError > 0 )
                  v2 = (unsigned __int16)LastError | 0x80070000;
                if ( v2 >= 0 )
                  v2 = -2147467259;
                continue;
              }
              if ( DPA_InsertPtr(*((HDPA *)this + 209), 0x7FFFFFFF, ppwsz) == -1 )
              {
                v9 = ppwsz;
                goto LABEL_25;
              }
              v13 = 0;
              v2 = SHStrDupW(*(LPCWSTR *)&bufptr[16 * i + 8], &v13);
              if ( v2 >= 0 )
              {
                if ( DPA_InsertPtr(*((HDPA *)this + 210), 0x7FFFFFFF, v13) == -1 )
                {
                  v9 = v13;
LABEL_25:
                  v2 = -2147024882;
                  CoTaskMemFree(v9);
                  continue;
                }
                v2 = 0;
              }
            }
          }
        }
      }
      if ( !*((_BYTE *)this + 1688) )
        *((_BYTE *)this + 1688) = 1;
      NetApiBufferFree(bufptr);
      if ( !v6 )
        return (unsigned int)v2;
    }
    else if ( v5 > 0 )
    {
      v2 = (unsigned __int16)v5 | 0x80070000;
    }
    else
    {
      v2 = v5;
    }
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18000f468  mov     [rsp-28h+arg_0], rbx
0x18000f46d  mov     [rsp-28h+arg_8], rsi
0x18000f472  push    rbp
0x18000f473  push    rdi
0x18000f474  push    r12
0x18000f476  push    r14
0x18000f478  push    r15
0x18000f47a  mov     rbp, rsp
0x18000f47d  sub     rsp, 60h
0x18000f481  xor     ebx, ebx
0x18000f483  mov     r12, rdx
0x18000f486  mov     [rbp+bufptr], rbx
0x18000f48a  mov     r15, rcx
0x18000f48d  mov     [rbp+var_8], rbx
0x18000f491  mov     [rbp+arg_10], ebx
0x18000f494  mov     [rbp+arg_18], ebx
0x18000f497  test    ebx, ebx
0x18000f499  js      loc_18000F644
0x18000f49f  lea     rax, [rbp+var_8]
0x18000f4a3  mov     r9d, 2000h; prefmaxlen
0x18000f4a9  mov     [rsp+60h+resumehandle], rax; resumehandle
0x18000f4ae  lea     r8, [rbp+bufptr]; bufptr
0x18000f4b2  lea     rax, [rbp+arg_18]
0x18000f4b6  mov     edx, 1; level
0x18000f4bb  mov     [rsp+60h+totalentries], rax; totalentries
0x18000f4c0  xor     ecx, ecx; servername
0x18000f4c2  lea     rax, [rbp+arg_10]
0x18000f4c6  mov     [rsp+60h+entriesread], rax; entriesread
0x18000f4cb  call    cs:__imp_NetLocalGroupEnum
0x18000f4d1  mov     edi, eax
0x18000f4d3  test    eax, eax
0x18000f4d5  jz      short loc_18000F4F5
0x18000f4d7  cmp     eax, 0EAh
0x18000f4dc  jz      short loc_18000F4F5
0x18000f4de  test    eax, eax
0x18000f4e0  jg      short loc_18000F4E6
0x18000f4e2  mov     ebx, eax
0x18000f4e4  jmp     short loc_18000F4EF
0x18000f4e6  movzx   ebx, di
0x18000f4e9  or      ebx, 80070000h
0x18000f4ef  test    ebx, ebx
0x18000f4f1  jns     short loc_18000F4F7
0x18000f4f3  jmp     short loc_18000F497
0x18000f4f5  xor     ebx, ebx
0x18000f4f7  xor     r14d, r14d
0x18000f4fa  cmp     [rbp+arg_10], r14d
0x18000f4fe  jbe     loc_18000F620
0x18000f504  test    ebx, ebx
0x18000f506  js      loc_18000F620
0x18000f50c  mov     rdx, [rbp+bufptr]
0x18000f510  lea     rcx, [r15+89Ch]; pszStr1
0x18000f517  mov     esi, r14d
0x18000f51a  add     rsi, rsi
0x18000f51d  mov     rdx, [rdx+rsi*8]; pszStr2
0x18000f521  call    cs:__imp_StrCmpICW
0x18000f527  test    eax, eax
0x18000f529  jz      loc_18000F613
0x18000f52f  mov     rdx, [rbp+bufptr]
0x18000f533  lea     rcx, [r15+69Ah]; pszStr1
0x18000f53a  mov     rdx, [rdx+rsi*8]; pszStr2
0x18000f53e  call    cs:__imp_StrCmpICW
0x18000f544  test    eax, eax
0x18000f546  jz      loc_18000F613
0x18000f54c  mov     rcx, [rbp+bufptr]
0x18000f550  lea     rdx, [rbp+ppwsz]; ppwsz
0x18000f554  mov     [rbp+ppwsz], 0
0x18000f55c  mov     rcx, [rcx+rsi*8]; psz
0x18000f560  call    cs:__imp_SHStrDupW
0x18000f566  mov     ebx, eax
0x18000f568  test    eax, eax
0x18000f56a  js      loc_18000F613
0x18000f570  mov     rdx, [rbp+ppwsz]
0x18000f574  mov     rcx, r12
0x18000f577  call    cs:__imp_?AddString@Combobox@DirectUI@@QEAAHPEBG@Z; DirectUI::Combobox::AddString(ushort const *)
0x18000f57d  cmp     eax, 0FFFFFFFFh
0x18000f580  jnz     short loc_18000F5A3
0x18000f582  call    cs:__imp_GetLastError
0x18000f588  mov     ebx, eax
0x18000f58a  test    eax, eax
0x18000f58c  jle     short loc_18000F597
0x18000f58e  movzx   ebx, ax
0x18000f591  or      ebx, 80070000h
0x18000f597  test    ebx, ebx
0x18000f599  mov     eax, 80004005h
0x18000f59e  cmovns  ebx, eax
0x18000f5a1  jmp     short loc_18000F613
0x18000f5a3  mov     r8, [rbp+ppwsz]; p
0x18000f5a7  mov     edx, 7FFFFFFFh; i
0x18000f5ac  mov     rcx, [r15+688h]; hdpa
0x18000f5b3  call    cs:__imp_DPA_InsertPtr
0x18000f5b9  cmp     eax, 0FFFFFFFFh
0x18000f5bc  jz      short loc_18000F604
0x18000f5be  mov     rcx, [rbp+bufptr]
0x18000f5c2  lea     rdx, [rbp+var_10]; ppwsz
0x18000f5c6  mov     [rbp+var_10], 0
0x18000f5ce  mov     rcx, [rcx+rsi*8+8]; psz
0x18000f5d3  call    cs:__imp_SHStrDupW
0x18000f5d9  mov     ebx, eax
0x18000f5db  test    eax, eax
0x18000f5dd  js      short loc_18000F613
0x18000f5df  mov     r8, [rbp+var_10]; p
0x18000f5e3  mov     edx, 7FFFFFFFh; i
0x18000f5e8  mov     rcx, [r15+690h]; hdpa
0x18000f5ef  call    cs:__imp_DPA_InsertPtr
0x18000f5f5  cmp     eax, 0FFFFFFFFh
0x18000f5f8  jz      short loc_18000F5FE
0x18000f5fa  xor     ebx, ebx
0x18000f5fc  jmp     short loc_18000F613
0x18000f5fe  mov     rcx, [rbp+var_10]
0x18000f602  jmp     short loc_18000F608
0x18000f604  mov     rcx, [rbp+ppwsz]; pv
0x18000f608  mov     ebx, 8007000Eh
0x18000f60d  call    cs:__imp_CoTaskMemFree
0x18000f613  inc     r14d
0x18000f616  cmp     r14d, [rbp+arg_10]
0x18000f61a  jb      loc_18000F504
0x18000f620  cmp     byte ptr [r15+698h], 0
0x18000f628  jnz     short loc_18000F632
0x18000f62a  mov     byte ptr [r15+698h], 1
0x18000f632  mov     rcx, [rbp+bufptr]; Buffer
0x18000f636  call    cs:__imp_NetApiBufferFree
0x18000f63c  test    edi, edi
0x18000f63e  jnz     loc_18000F497
0x18000f644  lea     r11, [rsp+60h+var_s0]
0x18000f649  mov     eax, ebx
0x18000f64b  mov     rbx, [r11+30h]
0x18000f64f  mov     rsi, [r11+38h]
0x18000f653  mov     rsp, r11
0x18000f656  pop     r15
0x18000f658  pop     r14
0x18000f65a  pop     r12
0x18000f65c  pop     rdi
0x18000f65d  pop     rbp
0x18000f65e  retn
```
