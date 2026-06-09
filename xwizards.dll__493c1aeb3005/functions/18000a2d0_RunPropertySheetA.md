# RunPropertySheetA

- ea: `0x18000a2d0`
- end: `0x18000a37a`
- name: `RunPropertySheetA`
- size: `170`
- prototype: `__int64 __fastcall(HWND hWnd)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x180004370`
- `0x18000a2d0`
- `0x18000a380`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a304`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a304`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a365`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a365`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000a32a`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000a32a`

## pseudocode

```c
__int64 __fastcall RunPropertySheetA(va_list hWnd, __int64 a2, const CHAR *a3)
{
  __int64 v6; // rax
  int cchWideChar; // esi
  WCHAR *lpWideCharStr; // rax
  unsigned __int16 *v9; // rbx
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
      LastErrorHRESULT = RunPropertySheetW(hWnd, a2, v9);
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
0x18000a2d0  push    rbx
0x18000a2d2  push    rbp
0x18000a2d3  push    rsi
0x18000a2d4  push    rdi
0x18000a2d5  push    r14
0x18000a2d7  push    r15
0x18000a2d9  sub     rsp, 38h
0x18000a2dd  mov     ebp, r9d
0x18000a2e0  mov     rdi, r8
0x18000a2e3  mov     r14, rdx
0x18000a2e6  mov     r15, rcx
0x18000a2e9  test    r8, r8
0x18000a2ec  jz      short loc_18000A35B
0x18000a2ee  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000a2f2  inc     rax
0x18000a2f5  cmp     byte ptr [r8+rax], 0
0x18000a2fa  jnz     short loc_18000A2F2
0x18000a2fc  lea     esi, [rax+1]
0x18000a2ff  mov     ecx, esi
0x18000a301  add     rcx, rcx; cb
0x18000a304  call    cs:__imp_CoTaskMemAlloc
0x18000a30a  mov     rbx, rax
0x18000a30d  test    rax, rax
0x18000a310  jz      short loc_18000A33D
0x18000a312  xor     ecx, ecx; CodePage
0x18000a314  mov     [rsp+68h+cchWideChar], esi; cchWideChar
0x18000a318  or      r9d, 0FFFFFFFFh; cbMultiByte
0x18000a31c  mov     [rax], cx
0x18000a31f  mov     r8, rdi; lpMultiByteStr
0x18000a322  mov     [rsp+68h+lpWideCharStr], rax; lpWideCharStr
0x18000a327  lea     edx, [rcx+1]; dwFlags
0x18000a32a  call    cs:__imp_MultiByteToWideChar
0x18000a330  test    eax, eax
0x18000a332  jnz     short loc_18000A346
0x18000a334  call    ?GetLastErrorHRESULT@@YAJXZ; GetLastErrorHRESULT(void)
0x18000a339  mov     edi, eax
0x18000a33b  jmp     short loc_18000A342
0x18000a33d  mov     edi, 8007000Eh
0x18000a342  test    edi, edi
0x18000a344  js      short loc_18000A362
0x18000a346  mov     r9d, ebp
0x18000a349  mov     r8, rbx
0x18000a34c  mov     rdx, r14
0x18000a34f  mov     rcx, r15; hWnd
0x18000a352  call    RunPropertySheetW
0x18000a357  mov     edi, eax
0x18000a359  jmp     short loc_18000A362
0x18000a35b  xor     ebx, ebx
0x18000a35d  mov     edi, 80070057h
0x18000a362  mov     rcx, rbx; pv
0x18000a365  call    cs:__imp_CoTaskMemFree
0x18000a36b  mov     eax, edi
0x18000a36d  add     rsp, 38h
0x18000a371  pop     r15
0x18000a373  pop     r14
0x18000a375  pop     rdi
0x18000a376  pop     rsi
0x18000a377  pop     rbp
0x18000a378  pop     rbx
0x18000a379  retn
```
