# mciSendStringA

- ea: `0x180011e90`
- end: `0x180012054`
- name: `mciSendStringA`
- size: `452`
- prototype: `MCIERROR __stdcall(LPCSTR lpstrCommand, LPSTR lpstrReturnString, UINT uReturnLength, HWND hwndCallback)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x18000a02c`
- `0x18000b1f8`
- `0x18000f99c`
- `0x1800111c8`
- `0x180011e90`
- `0x180012060`
- `0x180015d50`
- `0x180015ddc`
- `0x18001a408`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011ee6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011f1a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012018`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001202a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001203c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011ee6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011f1a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012018`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001202a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001203c`

## pseudocode

```c
MCIERROR __stdcall mciSendStringA(LPCSTR lpstrCommand, LPSTR lpstrReturnString, UINT uReturnLength, HWND hwndCallback)
{
  UINT v7; // r14d
  unsigned int v8; // esi
  WCHAR *v9; // rbx
  WCHAR *v10; // rdi
  WCHAR *v11; // r8
  const WCHAR *v13; // rax
  WCHAR *v14; // rbp
  MCIERROR v15; // r15d
  LPCWSTR v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // r8

  v7 = lpstrReturnString != 0 ? uReturnLength : 0;
  v8 = 2 * v7;
  if ( 2 * v7 )
  {
    v9 = (WCHAR *)winmmAlloc(v8);
    if ( !v9 )
      return 264;
    v10 = (WCHAR *)winmmAlloc(v8);
    if ( !v10 )
    {
      v11 = v9;
LABEL_5:
      HeapFree(hHeap, 0, v11);
      return 264;
    }
  }
  else
  {
    v9 = 0;
    v10 = 0;
  }
  v13 = (const WCHAR *)AllocUnicodeStr((CHAR *)lpstrCommand);
  v14 = (WCHAR *)v13;
  if ( !v13 )
  {
    if ( !v8 )
      return 264;
    HeapFree(hHeap, 0, v9);
    v11 = v10;
    goto LABEL_5;
  }
  v15 = mciSendStringW(v13, v10, v7, hwndCallback);
  v16 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 64, WPP_c925325bbcf0336105c06c8e14f965b6_Traceguids, v15);
    v16 = WPP_GLOBAL_Control;
  }
  if ( v8 )
  {
    if ( v16 != (LPCWSTR)&WPP_GLOBAL_Control && (*((_DWORD *)v16 + 7) & 0x400000) != 0 && *((_BYTE *)v16 + 25) >= 5u )
      WPP_SF_S(*((_QWORD *)v16 + 2), 65, WPP_c925325bbcf0336105c06c8e14f965b6_Traceguids, v10);
    UnicodeStrToAsciiStr((PCHAR)v9);
    if ( StringCbCopyA(lpstrReturnString, v7, (const char *)v9) )
      v15 = 264;
    if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), v17, v18, lpstrReturnString);
    }
    HeapFree(hHeap, 0, v9);
    HeapFree(hHeap, 0, v10);
  }
  HeapFree(hHeap, 0, v14);
  return v15;
}

```

## disassembly

```asm
0x180011e90  push    rbx
0x180011e92  push    rbp
0x180011e93  push    rsi
0x180011e94  push    rdi
0x180011e95  push    r12
0x180011e97  push    r14
0x180011e99  push    r15
0x180011e9b  sub     rsp, 20h
0x180011e9f  mov     rax, rdx
0x180011ea2  mov     r15, r9
0x180011ea5  neg     rax
0x180011ea8  mov     r12, rdx
0x180011eab  mov     rbp, rcx
0x180011eae  sbb     r14d, r14d
0x180011eb1  and     r14d, r8d
0x180011eb4  lea     esi, [r14+r14]
0x180011eb8  test    esi, esi
0x180011eba  jz      short loc_180011EF6
0x180011ebc  mov     ecx, esi; Size
0x180011ebe  call    winmmAlloc
0x180011ec3  mov     rbx, rax
0x180011ec6  test    rax, rax
0x180011ec9  jz      short loc_180011EEC
0x180011ecb  mov     ecx, esi; Size
0x180011ecd  call    winmmAlloc
0x180011ed2  mov     rdi, rax
0x180011ed5  test    rax, rax
0x180011ed8  jnz     short loc_180011EFA
0x180011eda  mov     r8, rbx; lpMem
0x180011edd  mov     rcx, cs:hHeap; hHeap
0x180011ee4  xor     edx, edx; dwFlags
0x180011ee6  call    cs:__imp_HeapFree
0x180011eec  mov     eax, 108h
0x180011ef1  jmp     loc_180012045
0x180011ef6  xor     ebx, ebx
0x180011ef8  xor     edi, edi
0x180011efa  mov     rcx, rbp; MultiByteString
0x180011efd  call    AllocUnicodeStr
0x180011f02  mov     rbp, rax
0x180011f05  test    rax, rax
0x180011f08  jnz     short loc_180011F25
0x180011f0a  test    esi, esi
0x180011f0c  jz      short loc_180011EEC
0x180011f0e  mov     rcx, cs:hHeap; hHeap
0x180011f15  mov     r8, rbx; lpMem
0x180011f18  xor     edx, edx; dwFlags
0x180011f1a  call    cs:__imp_HeapFree
0x180011f20  mov     r8, rdi
0x180011f23  jmp     short loc_180011EDD
0x180011f25  mov     r9, r15; hwndCallback
0x180011f28  mov     r8d, r14d; uReturnLength
0x180011f2b  mov     rdx, rdi; lpstrReturnString
0x180011f2e  mov     rcx, rbp; lpstrCommand
0x180011f31  call    mciSendStringW
0x180011f36  mov     r15d, eax
0x180011f39  mov     rcx, cs:WPP_GLOBAL_Control
0x180011f40  lea     rax, WPP_GLOBAL_Control
0x180011f47  cmp     rcx, rax
0x180011f4a  jz      short loc_180011F81
0x180011f4c  test    dword ptr [rcx+1Ch], 400000h
0x180011f53  jz      short loc_180011F81
0x180011f55  cmp     byte ptr [rcx+19h], 4
0x180011f59  jb      short loc_180011F81
0x180011f5b  mov     rcx, [rcx+10h]
0x180011f5f  lea     r8, WPP_c925325bbcf0336105c06c8e14f965b6_Traceguids
0x180011f66  mov     edx, 40h ; '@'
0x180011f6b  mov     r9d, r15d
0x180011f6e  call    WPP_SF_d
0x180011f73  mov     rcx, cs:WPP_GLOBAL_Control
0x180011f7a  lea     rax, WPP_GLOBAL_Control
0x180011f81  test    esi, esi
0x180011f83  jz      loc_180012030
0x180011f89  cmp     rcx, rax
0x180011f8c  jz      short loc_180011FB5
0x180011f8e  test    dword ptr [rcx+1Ch], 400000h
0x180011f95  jz      short loc_180011FB5
0x180011f97  cmp     byte ptr [rcx+19h], 5
0x180011f9b  jb      short loc_180011FB5
0x180011f9d  mov     rcx, [rcx+10h]
0x180011fa1  lea     r8, WPP_c925325bbcf0336105c06c8e14f965b6_Traceguids
0x180011fa8  mov     edx, 41h ; 'A'
0x180011fad  mov     r9, rdi
0x180011fb0  call    WPP_SF_S
0x180011fb5  mov     edx, esi
0x180011fb7  mov     r8, rdi
0x180011fba  add     rdx, rbx
0x180011fbd  mov     rcx, rbx; MbString
0x180011fc0  call    UnicodeStrToAsciiStr
0x180011fc5  mov     edx, r14d; unsigned __int64
0x180011fc8  mov     r8, rbx; char *
0x180011fcb  mov     rcx, r12; char *
0x180011fce  call    ?StringCbCopyA@@YAJPEAD_KPEBD@Z; StringCbCopyA(char *,unsigned __int64,char const *)
0x180011fd3  test    eax, eax
0x180011fd5  mov     ecx, 108h
0x180011fda  cmovnz  r15d, ecx
0x180011fde  mov     rcx, cs:WPP_GLOBAL_Control
0x180011fe5  lea     rax, WPP_GLOBAL_Control
0x180011fec  cmp     rcx, rax
0x180011fef  jz      short loc_18001200C
0x180011ff1  test    dword ptr [rcx+1Ch], 400000h
0x180011ff8  jz      short loc_18001200C
0x180011ffa  cmp     byte ptr [rcx+19h], 5
0x180011ffe  jb      short loc_18001200C
0x180012000  mov     rcx, [rcx+10h]
0x180012004  mov     r9, r12
0x180012007  call    WPP_SF_s
0x18001200c  mov     rcx, cs:hHeap; hHeap
0x180012013  mov     r8, rbx; lpMem
0x180012016  xor     edx, edx; dwFlags
0x180012018  call    cs:__imp_HeapFree
0x18001201e  mov     rcx, cs:hHeap; hHeap
0x180012025  mov     r8, rdi; lpMem
0x180012028  xor     edx, edx; dwFlags
0x18001202a  call    cs:__imp_HeapFree
0x180012030  mov     rcx, cs:hHeap; hHeap
0x180012037  mov     r8, rbp; lpMem
0x18001203a  xor     edx, edx; dwFlags
0x18001203c  call    cs:__imp_HeapFree
0x180012042  mov     eax, r15d
0x180012045  add     rsp, 20h
0x180012049  pop     r15
0x18001204b  pop     r14
0x18001204d  pop     r12
0x18001204f  pop     rdi
0x180012050  pop     rsi
0x180012051  pop     rbp
0x180012052  pop     rbx
0x180012053  retn
```
