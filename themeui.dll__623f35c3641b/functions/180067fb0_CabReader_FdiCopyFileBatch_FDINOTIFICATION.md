# CabReader::FdiCopyFileBatch(FDINOTIFICATION *)

- ea: `0x180067fb0`
- end: `0x180068197`
- name: `?FdiCopyFileBatch@CabReader@@CA_JPEAUFDINOTIFICATION@@@Z`
- size: `487`
- prototype: `__int64 __fastcall(struct FDINOTIFICATION *)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, reparse_path, service_task, broker_com_uri`

## callees

- `0x1800179e0`
- `0x18001a3e8`
- `0x1800358c0`
- `0x180067fb0`
- `0x1800682e0`
- `0x180068d54`
- `0x180069074`
- `0x18006d010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180068091`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180068091`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006815a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006815a`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1800680ba`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1800680ba`

## pseudocode

```c
INT_PTR __fastcall CabReader::FdiCopyFileBatch(struct FDINOTIFICATION *a1)
{
  unsigned int *pv; // rdi
  char *psz1; // rdx
  bool v4; // cf
  UINT v5; // r12d
  INT_PTR v6; // rbp
  HRESULT v7; // ebx
  const WCHAR *Ptr; // rax
  const WCHAR *v9; // rsi
  unsigned int (__fastcall *v10)(_QWORD, LPCWCH, _QWORD, _QWORD); // rax
  LPCWCH lpString1; // [rsp+30h] [rbp-158h] BYREF
  CHAR pszFile[272]; // [rsp+40h] [rbp-148h] BYREF

  pv = (unsigned int *)a1->pv;
  if ( !pv )
    return -1;
  psz1 = a1->psz1;
  v4 = SLOBYTE(a1->attribs) < 0;
  lpString1 = 0;
  v5 = v4 ? 0xFDE9 : 0;
  if ( (int)AnsiToUnicodeWithAlloc(v5, psz1, (unsigned __int16 **)&lpString1) < 0 )
    return -1;
  v6 = 0;
  if ( !IsValidThemepackItemPath(lpString1) )
  {
    v7 = -2147024809;
    goto LABEL_18;
  }
  Ptr = (const WCHAR *)g_pfn_DPA_GetPtr(*((HDPA *)pv + 264), pv[530]);
  v9 = Ptr;
  if ( Ptr )
  {
    v7 = 0;
    if ( *((_BYTE *)pv + 2144) || !*((_DWORD *)Ptr + 133) || *((_DWORD *)Ptr + 134) )
      goto LABEL_17;
    if ( CompareStringOrdinal(lpString1, -1, Ptr + 2, -1, 0) == 2 )
    {
      v7 = PathCchCombine((PWSTR)pv + 790, 0x104u, (PCWSTR)pv + 530, v9 + 2);
      if ( v7 < 0 )
        goto LABEL_17;
      *((_WORD *)pv + 1050) = v9[264];
      v7 = UnicodeToAnsi(v5, (const unsigned __int16 *)pv + 790, pszFile, 0x104u);
      if ( v7 < 0 )
        goto LABEL_17;
      v6 = CabReader::FdiFileOpen(pszFile, 33057, 0);
      if ( v6 > 0 )
      {
        *((_DWORD *)v9 + 134) = 1;
        v7 = 0;
        v10 = (unsigned int (__fastcall *)(_QWORD, LPCWCH, _QWORD, _QWORD))*((_QWORD *)pv + 266);
        if ( v10 && v10(0, lpString1, a1->cb, *((_QWORD *)pv + 267)) == -1 )
          *((_BYTE *)pv + 2144) = 1;
        goto LABEL_17;
      }
    }
  }
  v7 = -2147467259;
LABEL_17:
  ++pv[530];
LABEL_18:
  CoTaskMemFree((LPVOID)lpString1);
  if ( v7 < 0 )
    return -1;
  return v6;
}

```

## disassembly

```asm
0x180067fb0  mov     [rsp+arg_8], rbx
0x180067fb5  mov     [rsp+arg_10], rbp
0x180067fba  push    rsi
0x180067fbb  push    rdi
0x180067fbc  push    r12
0x180067fbe  push    r13
0x180067fc0  push    r14
0x180067fc2  sub     rsp, 160h
0x180067fc9  mov     rax, cs:__security_cookie
0x180067fd0  xor     rax, rsp
0x180067fd3  mov     [rsp+188h+var_38], rax
0x180067fdb  mov     rdi, [rcx+20h]
0x180067fdf  mov     r14, rcx
0x180067fe2  test    rdi, rdi
0x180067fe5  jz      loc_180068164
0x180067feb  mov     al, [rcx+34h]
0x180067fee  lea     r8, [rsp+188h+lpString1]; unsigned __int16 **
0x180067ff3  mov     rdx, [rcx+8]; lpMultiByteStr
0x180067ff7  and     al, 80h
0x180067ff9  neg     al
0x180067ffb  mov     [rsp+188h+lpString1], 0
0x180068004  sbb     r12d, r12d
0x180068007  and     r12d, 0FDE9h
0x18006800e  mov     ecx, r12d; CodePage
0x180068011  call    ?AnsiToUnicodeWithAlloc@@YAJIPEBDPEAPEAG@Z; AnsiToUnicodeWithAlloc(uint,char const *,ushort * *)
0x180068016  test    eax, eax
0x180068018  js      loc_180068164
0x18006801e  mov     rcx, [rsp+188h+lpString1]; lpString2
0x180068023  xor     ebp, ebp
0x180068025  call    ?IsValidThemepackItemPath@@YA_NPEBG@Z; IsValidThemepackItemPath(ushort const *)
0x18006802a  test    al, al
0x18006802c  jnz     short loc_180068038
0x18006802e  mov     ebx, 80070057h
0x180068033  jmp     loc_180068155
0x180068038  mov     edx, [rdi+848h]; i
0x18006803e  mov     rcx, [rdi+840h]; hdpa
0x180068045  call    cs:g_pfn_DPA_GetPtr
0x18006804b  mov     rsi, rax
0x18006804e  test    rax, rax
0x180068051  jz      loc_18006814A
0x180068057  xor     ebx, ebx
0x180068059  cmp     [rdi+860h], bl
0x18006805f  jnz     loc_18006814F
0x180068065  cmp     [rax+214h], ebx
0x18006806b  jz      loc_18006814F
0x180068071  cmp     [rax+218h], ebx
0x180068077  jnz     loc_18006814F
0x18006807d  mov     rcx, [rsp+188h+lpString1]; lpString1
0x180068082  lea     r8, [rax+4]; lpString2
0x180068086  or      r9d, 0FFFFFFFFh; cchCount2
0x18006808a  mov     [rsp+188h+bIgnoreCase], ebx; bIgnoreCase
0x18006808e  or      edx, r9d; cchCount1
0x180068091  call    cs:__imp_CompareStringOrdinal
0x180068097  cmp     eax, 2
0x18006809a  jnz     loc_18006814A
0x1800680a0  lea     r13, [rdi+62Ch]
0x1800680a7  mov     edx, 104h; cchPathOut
0x1800680ac  mov     rcx, r13; pszPathOut
0x1800680af  lea     r8, [rdi+424h]; pszPathIn
0x1800680b6  lea     r9, [rsi+4]; pszMore
0x1800680ba  call    cs:__imp_PathCchCombine
0x1800680c0  mov     ebx, eax
0x1800680c2  test    eax, eax
0x1800680c4  js      loc_18006814F
0x1800680ca  movzx   eax, word ptr [rsi+210h]
0x1800680d1  lea     r8, [rsp+188h+pszFile]; char *
0x1800680d6  mov     r9d, 104h; unsigned __int64
0x1800680dc  mov     [rdi+834h], ax
0x1800680e3  mov     rdx, r13; unsigned __int16 *
0x1800680e6  mov     ecx, r12d; unsigned int
0x1800680e9  call    ?UnicodeToAnsi@@YAJIPEBGPEAD_K@Z; UnicodeToAnsi(uint,ushort const *,char *,unsigned __int64)
0x1800680ee  mov     ebx, eax
0x1800680f0  test    eax, eax
0x1800680f2  js      short loc_18006814F
0x1800680f4  xor     r8d, r8d; pmode
0x1800680f7  lea     rcx, [rsp+188h+pszFile]; pszFile
0x1800680fc  mov     edx, 8121h; oflag
0x180068101  call    ?FdiFileOpen@CabReader@@CA_JPEADHH@Z; CabReader::FdiFileOpen(char *,int,int)
0x180068106  mov     rbp, rax
0x180068109  test    rax, rax
0x18006810c  jle     short loc_18006814A
0x18006810e  mov     dword ptr [rsi+218h], 1
0x180068118  xor     ebx, ebx
0x18006811a  mov     rax, [rdi+850h]
0x180068121  test    rax, rax
0x180068124  jz      short loc_18006814F
0x180068126  movsxd  r8, dword ptr [r14]
0x180068129  xor     ecx, ecx
0x18006812b  mov     r9, [rdi+858h]
0x180068132  mov     rdx, [rsp+188h+lpString1]
0x180068137  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006813c  cmp     eax, 0FFFFFFFFh
0x18006813f  jnz     short loc_18006814F
0x180068141  mov     byte ptr [rdi+860h], 1
0x180068148  jmp     short loc_18006814F
0x18006814a  mov     ebx, 80004005h
0x18006814f  inc     dword ptr [rdi+848h]
0x180068155  mov     rcx, [rsp+188h+lpString1]; pv
0x18006815a  call    cs:__imp_CoTaskMemFree
0x180068160  test    ebx, ebx
0x180068162  jns     short loc_180068168
0x180068164  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180068168  mov     rax, rbp
0x18006816b  mov     rcx, [rsp+188h+var_38]
0x180068173  xor     rcx, rsp; StackCookie
0x180068176  call    __security_check_cookie
0x18006817b  lea     r11, [rsp+188h+var_28]
0x180068183  mov     rbx, [r11+38h]
0x180068187  mov     rbp, [r11+40h]
0x18006818b  mov     rsp, r11
0x18006818e  pop     r14
0x180068190  pop     r13
0x180068192  pop     r12
0x180068194  pop     rdi
0x180068195  pop     rsi
0x180068196  retn
```
