# ResetRegistrationA

- ea: `0x180009c70`
- end: `0x180009d1a`
- name: `ResetRegistrationA`
- size: `170`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x180004370`
- `0x180009c70`
- `0x180009d20`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009ca4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009ca4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009d05`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009d05`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180009cca`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180009cca`

## pseudocode

```c
__int64 __fastcall ResetRegistrationA(__int64 a1, __int64 a2, const CHAR *a3)
{
  __int64 v6; // rax
  int cchWideChar; // esi
  WCHAR *lpWideCharStr; // rax
  WCHAR *v9; // rbx
  int LastErrorHRESULT; // edi

  if ( !a3 )
  {
    v9 = 0;
    LastErrorHRESULT = -2147024809;
    goto LABEL_11;
  }
  v6 = -1;
  do
    ++v6;
  while ( a3[v6] );
  cchWideChar = v6 + 1;
  lpWideCharStr = (WCHAR *)CoTaskMemAlloc(2LL * (unsigned int)(v6 + 1));
  v9 = lpWideCharStr;
  if ( lpWideCharStr )
  {
    *lpWideCharStr = 0;
    if ( MultiByteToWideChar(0, 1u, a3, -1, lpWideCharStr, cchWideChar) )
    {
LABEL_9:
      LastErrorHRESULT = ResetRegistrationW(a1, a2, v9);
      goto LABEL_11;
    }
    LastErrorHRESULT = GetLastErrorHRESULT();
  }
  else
  {
    LastErrorHRESULT = -2147024882;
  }
  if ( LastErrorHRESULT >= 0 )
    goto LABEL_9;
LABEL_11:
  CoTaskMemFree(v9);
  return (unsigned int)LastErrorHRESULT;
}

```

## disassembly

```asm
0x180009c70  push    rbx
0x180009c72  push    rbp
0x180009c73  push    rsi
0x180009c74  push    rdi
0x180009c75  push    r14
0x180009c77  push    r15
0x180009c79  sub     rsp, 38h
0x180009c7d  mov     ebp, r9d
0x180009c80  mov     rdi, r8
0x180009c83  mov     r14, rdx
0x180009c86  mov     r15, rcx
0x180009c89  test    r8, r8
0x180009c8c  jz      short loc_180009CFB
0x180009c8e  or      rax, 0FFFFFFFFFFFFFFFFh
0x180009c92  inc     rax
0x180009c95  cmp     byte ptr [r8+rax], 0
0x180009c9a  jnz     short loc_180009C92
0x180009c9c  lea     esi, [rax+1]
0x180009c9f  mov     ecx, esi
0x180009ca1  add     rcx, rcx; cb
0x180009ca4  call    cs:__imp_CoTaskMemAlloc
0x180009caa  mov     rbx, rax
0x180009cad  test    rax, rax
0x180009cb0  jz      short loc_180009CDD
0x180009cb2  xor     ecx, ecx; CodePage
0x180009cb4  mov     [rsp+68h+cchWideChar], esi; cchWideChar
0x180009cb8  or      r9d, 0FFFFFFFFh; cbMultiByte
0x180009cbc  mov     [rax], cx
0x180009cbf  mov     r8, rdi; lpMultiByteStr
0x180009cc2  mov     [rsp+68h+lpWideCharStr], rax; lpWideCharStr
0x180009cc7  lea     edx, [rcx+1]; dwFlags
0x180009cca  call    cs:__imp_MultiByteToWideChar
0x180009cd0  test    eax, eax
0x180009cd2  jnz     short loc_180009CE6
0x180009cd4  call    ?GetLastErrorHRESULT@@YAJXZ; GetLastErrorHRESULT(void)
0x180009cd9  mov     edi, eax
0x180009cdb  jmp     short loc_180009CE2
0x180009cdd  mov     edi, 8007000Eh
0x180009ce2  test    edi, edi
0x180009ce4  js      short loc_180009D02
0x180009ce6  mov     r9d, ebp
0x180009ce9  mov     r8, rbx
0x180009cec  mov     rdx, r14
0x180009cef  mov     rcx, r15
0x180009cf2  call    ResetRegistrationW
0x180009cf7  mov     edi, eax
0x180009cf9  jmp     short loc_180009D02
0x180009cfb  xor     ebx, ebx
0x180009cfd  mov     edi, 80070057h
0x180009d02  mov     rcx, rbx; pv
0x180009d05  call    cs:__imp_CoTaskMemFree
0x180009d0b  mov     eax, edi
0x180009d0d  add     rsp, 38h
0x180009d11  pop     r15
0x180009d13  pop     r14
0x180009d15  pop     rdi
0x180009d16  pop     rsi
0x180009d17  pop     rbp
0x180009d18  pop     rbx
0x180009d19  retn
```
