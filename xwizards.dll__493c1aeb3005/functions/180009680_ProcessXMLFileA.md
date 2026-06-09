# ProcessXMLFileA

- ea: `0x180009680`
- end: `0x18000972a`
- name: `ProcessXMLFileA`
- size: `170`
- prototype: `__int64 __fastcall(HWND hWnd)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180004370`
- `0x180009680`
- `0x180009730`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800096b4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800096b4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009715`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009715`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800096da`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800096da`

## pseudocode

```c
__int64 __fastcall ProcessXMLFileA(HWND hWnd, __int64 a2, const CHAR *a3)
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
      LastErrorHRESULT = ProcessXMLFileW(hWnd, a2, v9);
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
0x180009680  push    rbx
0x180009682  push    rbp
0x180009683  push    rsi
0x180009684  push    rdi
0x180009685  push    r14
0x180009687  push    r15
0x180009689  sub     rsp, 38h
0x18000968d  mov     ebp, r9d
0x180009690  mov     rdi, r8
0x180009693  mov     r14, rdx
0x180009696  mov     r15, rcx
0x180009699  test    r8, r8
0x18000969c  jz      short loc_18000970B
0x18000969e  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800096a2  inc     rax
0x1800096a5  cmp     byte ptr [r8+rax], 0
0x1800096aa  jnz     short loc_1800096A2
0x1800096ac  lea     esi, [rax+1]
0x1800096af  mov     ecx, esi
0x1800096b1  add     rcx, rcx; cb
0x1800096b4  call    cs:__imp_CoTaskMemAlloc
0x1800096ba  mov     rbx, rax
0x1800096bd  test    rax, rax
0x1800096c0  jz      short loc_1800096ED
0x1800096c2  xor     ecx, ecx; CodePage
0x1800096c4  mov     [rsp+68h+cchWideChar], esi; cchWideChar
0x1800096c8  or      r9d, 0FFFFFFFFh; cbMultiByte
0x1800096cc  mov     [rax], cx
0x1800096cf  mov     r8, rdi; lpMultiByteStr
0x1800096d2  mov     [rsp+68h+lpWideCharStr], rax; lpWideCharStr
0x1800096d7  lea     edx, [rcx+1]; dwFlags
0x1800096da  call    cs:__imp_MultiByteToWideChar
0x1800096e0  test    eax, eax
0x1800096e2  jnz     short loc_1800096F6
0x1800096e4  call    ?GetLastErrorHRESULT@@YAJXZ; GetLastErrorHRESULT(void)
0x1800096e9  mov     edi, eax
0x1800096eb  jmp     short loc_1800096F2
0x1800096ed  mov     edi, 8007000Eh
0x1800096f2  test    edi, edi
0x1800096f4  js      short loc_180009712
0x1800096f6  mov     r9d, ebp
0x1800096f9  mov     r8, rbx
0x1800096fc  mov     rdx, r14
0x1800096ff  mov     rcx, r15; hWnd
0x180009702  call    ProcessXMLFileW
0x180009707  mov     edi, eax
0x180009709  jmp     short loc_180009712
0x18000970b  xor     ebx, ebx
0x18000970d  mov     edi, 80070057h
0x180009712  mov     rcx, rbx; pv
0x180009715  call    cs:__imp_CoTaskMemFree
0x18000971b  mov     eax, edi
0x18000971d  add     rsp, 38h
0x180009721  pop     r15
0x180009723  pop     r14
0x180009725  pop     rdi
0x180009726  pop     rsi
0x180009727  pop     rbp
0x180009728  pop     rbx
0x180009729  retn
```
