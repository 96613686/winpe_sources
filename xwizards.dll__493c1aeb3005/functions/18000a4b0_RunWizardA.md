# RunWizardA

- ea: `0x18000a4b0`
- end: `0x18000a55a`
- name: `RunWizardA`
- size: `170`
- prototype: `__int64 __fastcall(HWND hWnd)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x180004370`
- `0x18000a4b0`
- `0x18000a560`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a4e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a4e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a545`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a545`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000a50a`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000a50a`

## pseudocode

```c
__int64 __fastcall RunWizardA(va_list hWnd, __int64 a2, const CHAR *a3)
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
      LastErrorHRESULT = RunWizardW(hWnd, a2, v9);
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
0x18000a4b0  push    rbx
0x18000a4b2  push    rbp
0x18000a4b3  push    rsi
0x18000a4b4  push    rdi
0x18000a4b5  push    r14
0x18000a4b7  push    r15
0x18000a4b9  sub     rsp, 38h
0x18000a4bd  mov     ebp, r9d
0x18000a4c0  mov     rdi, r8
0x18000a4c3  mov     r14, rdx
0x18000a4c6  mov     r15, rcx
0x18000a4c9  test    r8, r8
0x18000a4cc  jz      short loc_18000A53B
0x18000a4ce  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000a4d2  inc     rax
0x18000a4d5  cmp     byte ptr [r8+rax], 0
0x18000a4da  jnz     short loc_18000A4D2
0x18000a4dc  lea     esi, [rax+1]
0x18000a4df  mov     ecx, esi
0x18000a4e1  add     rcx, rcx; cb
0x18000a4e4  call    cs:__imp_CoTaskMemAlloc
0x18000a4ea  mov     rbx, rax
0x18000a4ed  test    rax, rax
0x18000a4f0  jz      short loc_18000A51D
0x18000a4f2  xor     ecx, ecx; CodePage
0x18000a4f4  mov     [rsp+68h+cchWideChar], esi; cchWideChar
0x18000a4f8  or      r9d, 0FFFFFFFFh; cbMultiByte
0x18000a4fc  mov     [rax], cx
0x18000a4ff  mov     r8, rdi; lpMultiByteStr
0x18000a502  mov     [rsp+68h+lpWideCharStr], rax; lpWideCharStr
0x18000a507  lea     edx, [rcx+1]; dwFlags
0x18000a50a  call    cs:__imp_MultiByteToWideChar
0x18000a510  test    eax, eax
0x18000a512  jnz     short loc_18000A526
0x18000a514  call    ?GetLastErrorHRESULT@@YAJXZ; GetLastErrorHRESULT(void)
0x18000a519  mov     edi, eax
0x18000a51b  jmp     short loc_18000A522
0x18000a51d  mov     edi, 8007000Eh
0x18000a522  test    edi, edi
0x18000a524  js      short loc_18000A542
0x18000a526  mov     r9d, ebp
0x18000a529  mov     r8, rbx
0x18000a52c  mov     rdx, r14
0x18000a52f  mov     rcx, r15; hWnd
0x18000a532  call    RunWizardW
0x18000a537  mov     edi, eax
0x18000a539  jmp     short loc_18000A542
0x18000a53b  xor     ebx, ebx
0x18000a53d  mov     edi, 80070057h
0x18000a542  mov     rcx, rbx; pv
0x18000a545  call    cs:__imp_CoTaskMemFree
0x18000a54b  mov     eax, edi
0x18000a54d  add     rsp, 38h
0x18000a551  pop     r15
0x18000a553  pop     r14
0x18000a555  pop     rdi
0x18000a556  pop     rsi
0x18000a557  pop     rbp
0x18000a558  pop     rbx
0x18000a559  retn
```
