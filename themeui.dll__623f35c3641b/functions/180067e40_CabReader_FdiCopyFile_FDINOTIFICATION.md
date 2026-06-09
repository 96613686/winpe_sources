# CabReader::FdiCopyFile(FDINOTIFICATION *)

- ea: `0x180067e40`
- end: `0x180067fa8`
- name: `?FdiCopyFile@CabReader@@CA_JPEAUFDINOTIFICATION@@@Z`
- size: `360`
- prototype: `__int64 __fastcall(struct FDINOTIFICATION *)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x18001a3e8`
- `0x1800358c0`
- `0x180067e40`
- `0x1800682e0`
- `0x180068d54`
- `0x180069074`
- `0x18006d010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180067ee2`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180067ee2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180067f77`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180067f77`

## pseudocode

```c
INT_PTR __fastcall CabReader::FdiCopyFile(struct FDINOTIFICATION *a1)
{
  void *pv; // rbx
  char *psz1; // rdx
  char v4; // al
  UINT v5; // r15d
  INT_PTR v6; // rsi
  int v7; // edi
  unsigned int (__fastcall *v8)(_QWORD, LPCWCH, _QWORD, _QWORD); // rax
  LPCWCH lpString1; // [rsp+30h] [rbp-168h] BYREF
  CHAR pszFile[272]; // [rsp+40h] [rbp-158h] BYREF

  if ( !a1 )
    return -1;
  pv = a1->pv;
  if ( !pv )
    return -1;
  psz1 = a1->psz1;
  v4 = a1->attribs & 0x80;
  lpString1 = 0;
  v5 = v4 != 0 ? 0xFDE9 : 0;
  if ( (int)AnsiToUnicodeWithAlloc(v5, psz1, (unsigned __int16 **)&lpString1) < 0 )
    return -1;
  v6 = 0;
  if ( IsValidThemepackItemPath(lpString1) )
  {
    v7 = 0;
    if ( CompareStringOrdinal(lpString1, -1, (LPCWCH)pv + 270, -1, 0) == 2 )
    {
      *((_WORD *)pv + 1050) = 128;
      v7 = UnicodeToAnsi(v5, (const unsigned __int16 *)pv + 790, pszFile, 0x104u);
      if ( v7 >= 0 )
      {
        v6 = CabReader::FdiFileOpen(pszFile, 33057, 0);
        if ( v6 <= 0 )
        {
          v7 = -2147467259;
        }
        else
        {
          v8 = (unsigned int (__fastcall *)(_QWORD, LPCWCH, _QWORD, _QWORD))*((_QWORD *)pv + 266);
          v7 = 0;
          if ( v8 && v8(0, lpString1, a1->cb, *((_QWORD *)pv + 267)) == -1 )
            *((_BYTE *)pv + 2144) = 1;
        }
      }
    }
  }
  else
  {
    v7 = -2147024809;
  }
  CoTaskMemFree((LPVOID)lpString1);
  if ( v7 < 0 )
    return -1;
  return v6;
}

```

## disassembly

```asm
0x180067e40  push    rbx
0x180067e42  push    rbp
0x180067e43  push    rsi
0x180067e44  push    rdi
0x180067e45  push    r13
0x180067e47  push    r15
0x180067e49  sub     rsp, 168h
0x180067e50  mov     rax, cs:__security_cookie
0x180067e57  xor     rax, rsp
0x180067e5a  mov     [rsp+198h+var_48], rax
0x180067e62  mov     rbp, rcx
0x180067e65  test    rcx, rcx
0x180067e68  jz      loc_180067F81
0x180067e6e  mov     rbx, [rcx+20h]
0x180067e72  test    rbx, rbx
0x180067e75  jz      loc_180067F81
0x180067e7b  mov     al, [rcx+34h]
0x180067e7e  lea     r8, [rsp+198h+lpString1]; unsigned __int16 **
0x180067e83  mov     rdx, [rcx+8]; lpMultiByteStr
0x180067e87  mov     r13d, 80h
0x180067e8d  and     al, r13b
0x180067e90  mov     [rsp+198h+lpString1], 0
0x180067e99  neg     al
0x180067e9b  sbb     r15d, r15d
0x180067e9e  and     r15d, 0FDE9h
0x180067ea5  mov     ecx, r15d; CodePage
0x180067ea8  call    ?AnsiToUnicodeWithAlloc@@YAJIPEBDPEAPEAG@Z; AnsiToUnicodeWithAlloc(uint,char const *,ushort * *)
0x180067ead  test    eax, eax
0x180067eaf  js      loc_180067F81
0x180067eb5  mov     rcx, [rsp+198h+lpString1]; lpString2
0x180067eba  xor     esi, esi
0x180067ebc  call    ?IsValidThemepackItemPath@@YA_NPEBG@Z; IsValidThemepackItemPath(ushort const *)
0x180067ec1  test    al, al
0x180067ec3  jz      loc_180067F6D
0x180067ec9  mov     rcx, [rsp+198h+lpString1]; lpString1
0x180067ece  lea     r8, [rbx+21Ch]; lpString2
0x180067ed5  or      r9d, 0FFFFFFFFh; cchCount2
0x180067ed9  mov     [rsp+198h+bIgnoreCase], esi; bIgnoreCase
0x180067edd  or      edx, r9d; cchCount1
0x180067ee0  xor     edi, edi
0x180067ee2  call    cs:__imp_CompareStringOrdinal
0x180067ee8  cmp     eax, 2
0x180067eeb  jnz     loc_180067F72
0x180067ef1  lea     rdx, [rbx+62Ch]; unsigned __int16 *
0x180067ef8  mov     [rbx+834h], r13w
0x180067f00  mov     r9d, 104h; unsigned __int64
0x180067f06  lea     r8, [rsp+198h+pszFile]; char *
0x180067f0b  mov     ecx, r15d; unsigned int
0x180067f0e  call    ?UnicodeToAnsi@@YAJIPEBGPEAD_K@Z; UnicodeToAnsi(uint,ushort const *,char *,unsigned __int64)
0x180067f13  mov     edi, eax
0x180067f15  test    eax, eax
0x180067f17  js      short loc_180067F72
0x180067f19  xor     r8d, r8d; pmode
0x180067f1c  lea     rcx, [rsp+198h+pszFile]; pszFile
0x180067f21  mov     edx, 8121h; oflag
0x180067f26  call    ?FdiFileOpen@CabReader@@CA_JPEADHH@Z; CabReader::FdiFileOpen(char *,int,int)
0x180067f2b  mov     rsi, rax
0x180067f2e  test    rax, rax
0x180067f31  jle     short loc_180067F66
0x180067f33  mov     rax, [rbx+850h]
0x180067f3a  xor     edi, edi
0x180067f3c  test    rax, rax
0x180067f3f  jz      short loc_180067F72
0x180067f41  movsxd  r8, dword ptr [rbp+0]
0x180067f45  xor     ecx, ecx
0x180067f47  mov     r9, [rbx+858h]
0x180067f4e  mov     rdx, [rsp+198h+lpString1]
0x180067f53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067f58  cmp     eax, 0FFFFFFFFh
0x180067f5b  jnz     short loc_180067F72
0x180067f5d  mov     byte ptr [rbx+860h], 1
0x180067f64  jmp     short loc_180067F72
0x180067f66  mov     edi, 80004005h
0x180067f6b  jmp     short loc_180067F72
0x180067f6d  mov     edi, 80070057h
0x180067f72  mov     rcx, [rsp+198h+lpString1]; pv
0x180067f77  call    cs:__imp_CoTaskMemFree
0x180067f7d  test    edi, edi
0x180067f7f  jns     short loc_180067F85
0x180067f81  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180067f85  mov     rax, rsi
0x180067f88  mov     rcx, [rsp+198h+var_48]
0x180067f90  xor     rcx, rsp; StackCookie
0x180067f93  call    __security_check_cookie
0x180067f98  add     rsp, 168h
0x180067f9f  pop     r15
0x180067fa1  pop     r13
0x180067fa3  pop     rdi
0x180067fa4  pop     rsi
0x180067fa5  pop     rbp
0x180067fa6  pop     rbx
0x180067fa7  retn
```
