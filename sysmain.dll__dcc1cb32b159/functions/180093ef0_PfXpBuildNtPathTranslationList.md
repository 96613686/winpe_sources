# PfXpBuildNtPathTranslationList

- ea: `0x180093ef0`
- end: `0x180094340`
- name: `PfXpBuildNtPathTranslationList`
- size: `1104`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path`

## callers

- `0x1800197c4`

## callees

- `0x180078746`
- `0x180093ef0`
- `0x180094378`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180094200`
- `msvcrt!_wcsicmp` at `0x180094200`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180093fa6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180093fec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800942b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800942c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180093fa6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180093fec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800942b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800942c3`
- `api-ms-win-core-file-l1-1-0!FindVolumeClose` at `0x18009426a`
- `api-ms-win-core-file-l1-1-0!FindVolumeClose` at `0x18009426a`
- `api-ms-win-core-file-l1-1-0!FindNextVolumeW` at `0x180094242`
- `api-ms-win-core-file-l1-1-0!FindNextVolumeW` at `0x180094242`
- `api-ms-win-core-file-l1-1-0!QueryDosDeviceW` at `0x180094106`
- `api-ms-win-core-file-l1-1-0!QueryDosDeviceW` at `0x180094106`
- `api-ms-win-core-file-l1-1-0!FindFirstVolumeW` at `0x180093f95`
- `api-ms-win-core-file-l1-1-0!FindFirstVolumeW` at `0x180093f95`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180094014`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180094285`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800942fd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180094318`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180094014`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180094285`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800942fd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180094318`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180093f26`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180093f3f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180093f70`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180094032`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180094172`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180093f26`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180093f3f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180093f70`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180094032`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180094172`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x180093fe2`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x180093fe2`

## pseudocode

```c
__int64 __fastcall PfXpBuildNtPathTranslationList(_QWORD *a1)
{
  _QWORD *v1; // rdi
  char v2; // r15
  LPVOID v3; // r14
  WCHAR *v4; // rax
  WCHAR *v5; // r12
  _QWORD *v6; // rax
  _QWORD *v7; // rsi
  DWORD LastError; // ebx
  DWORD v9; // eax
  _WORD *v10; // rbp
  __int64 v11; // r13
  int v12; // edi
  unsigned int v13; // edi
  _WORD *v14; // rdx
  _WORD *v15; // r8
  __int64 v16; // rcx
  _WORD *v17; // rax
  unsigned int v18; // eax
  __int64 v19; // rcx
  __int64 v20; // rax
  DWORD DosDeviceW; // eax
  __int64 v22; // rbx
  __int64 v23; // rcx
  _DWORD *v24; // rax
  _DWORD *v25; // r15
  char *v26; // rdi
  __int64 v27; // rbx
  unsigned int v28; // eax
  char *v29; // rdi
  size_t v30; // rbx
  _QWORD *v31; // rbx
  _QWORD *v32; // rdi
  __int64 v33; // rax
  HANDLE hFindVolume; // [rsp+20h] [rbp-68h]
  void *Src; // [rsp+28h] [rbp-60h]
  WCHAR *v37; // [rsp+30h] [rbp-58h]
  DWORD cchReturnLength; // [rsp+98h] [rbp+10h] BYREF
  unsigned int v40; // [rsp+A0h] [rbp+18h]
  DWORD v41; // [rsp+A8h] [rbp+20h]

  v1 = a1;
  v2 = 0;
  cchReturnLength = 0;
  v3 = HeapAlloc(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, 0x20Au);
  v4 = (WCHAR *)HeapAlloc(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, 0x20Au);
  v37 = v4;
  v5 = v4;
  if ( !v3 || !v4 )
  {
    LastError = 8;
    if ( !v3 )
      goto LABEL_64;
    goto LABEL_63;
  }
  v6 = HeapAlloc(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, 0x10u);
  v7 = v6;
  if ( v6 )
  {
    v6[1] = v6;
    *v6 = v6;
    hFindVolume = FindFirstVolumeW((LPWSTR)v3, 0x105u);
    if ( hFindVolume == (HANDLE)-1LL )
    {
      LastError = GetLastError();
    }
    else
    {
      v9 = 0;
      v10 = 0;
      v41 = 0;
      while ( 2 )
      {
        v11 = -1;
        do
          ++v11;
        while ( *((_WORD *)v3 + v11) );
        v12 = 0;
        while ( !GetVolumePathNamesForVolumeNameW((LPCWSTR)v3, v10, v9, &cchReturnLength) )
        {
          LastError = GetLastError();
          if ( LastError != 234 )
            goto LABEL_50;
          if ( v10 )
            HeapFree(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, v10);
          v10 = HeapAlloc(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, 2LL * cchReturnLength);
          if ( !v10 )
          {
            LastError = 8;
            goto LABEL_50;
          }
          if ( (unsigned int)++v12 > 0x3E8 )
          {
            LastError = 1;
LABEL_50:
            v1 = a1;
            goto LABEL_51;
          }
          v9 = cchReturnLength;
          v41 = cchReturnLength;
        }
        v13 = -1;
        v14 = v10;
        v15 = 0;
        if ( *v10 )
        {
          do
          {
            v16 = -1;
            do
              ++v16;
            while ( v14[v16] );
            v17 = v14;
            if ( (unsigned int)v16 >= v13 )
              v17 = v15;
            v15 = v17;
            v18 = v16;
            if ( (unsigned int)v16 >= v13 )
              v18 = v13;
            v13 = v18;
            v14 += (unsigned int)(v16 + 1);
          }
          while ( *v14 );
          Src = v15;
          v40 = v18;
          if ( v15 )
          {
            v19 = v18 - 1;
            if ( v15[v19] == 92 )
            {
              v15[v19] = 0;
              v13 = v18 - 1;
              v40 = v18 - 1;
            }
            if ( (unsigned int)v11 <= 4 )
            {
              LastError = 11;
              goto LABEL_50;
            }
            v20 = (unsigned int)(v11 - 1);
            if ( *((_WORD *)v3 + v20) == 92 )
            {
              *((_WORD *)v3 + v20) = 0;
              v2 = 1;
            }
            DosDeviceW = QueryDosDeviceW((LPCWSTR)v3 + 4, v5, 0x105u);
            if ( v2 )
              *((_WORD *)v3 + (unsigned int)(v11 - 1)) = 92;
            v2 = 0;
            if ( !DosDeviceW )
            {
              LastError = GetLastError();
              goto LABEL_50;
            }
            v5[260] = 0;
            v22 = -1;
            do
              ++v22;
            while ( v5[v22] );
            if ( (_DWORD)v22 )
            {
              v23 = (unsigned int)(v22 - 1);
              if ( v5[v23] == 92 )
              {
                v5[v23] = 0;
                LODWORD(v22) = v22 - 1;
              }
              v24 = HeapAlloc(
                      *(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL),
                      0,
                      2 * ((unsigned int)v11 + v13 + (_DWORD)v22) + 70);
              v25 = v24;
              if ( !v24 )
              {
                LastError = 8;
                goto LABEL_50;
              }
              v24[6] = v22;
              v26 = (char *)(v24 + 16);
              v27 = (unsigned int)(2 * v22 + 2);
              *((_QWORD *)v24 + 2) = v24 + 16;
              memcpy_0(v24 + 16, v5, (unsigned int)v27);
              v28 = v40;
              v29 = &v26[v27];
              v25[10] = v40;
              *((_QWORD *)v25 + 4) = v29;
              v30 = 2 * v28 + 2;
              memcpy_0(v29, Src, v30);
              v25[14] = v11;
              *((_QWORD *)v25 + 6) = &v29[v30];
              memcpy_0(&v29[v30], v3, (unsigned int)(2 * v11 + 2));
              v31 = (_QWORD *)*v7;
              v32 = v7;
              if ( (_QWORD *)*v7 != v7 )
              {
                do
                {
                  if ( _wcsicmp(*((const wchar_t **)v25 + 2), (const wchar_t *)v31[2]) <= 0 )
                    break;
                  v32 = v31;
                  v31 = (_QWORD *)*v31;
                }
                while ( v31 != v7 );
                v5 = v37;
              }
              v33 = *v32;
              if ( *(_QWORD **)(*v32 + 8LL) != v32 )
                __fastfail(3u);
              *(_QWORD *)v25 = v33;
              *((_QWORD *)v25 + 1) = v32;
              *(_QWORD *)(v33 + 8) = v25;
              *v32 = v25;
              v2 = 0;
            }
          }
        }
        if ( FindNextVolumeW(hFindVolume, (LPWSTR)v3, 0x105u) )
        {
          v9 = v41;
          continue;
        }
        break;
      }
      LastError = GetLastError();
      if ( LastError != 18 )
        goto LABEL_50;
      v1 = a1;
      LastError = 0;
      *a1 = v7;
      v7 = 0;
LABEL_51:
      FindVolumeClose(hFindVolume);
      if ( v10 )
        HeapFree(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, v10);
      if ( !v7 )
        goto LABEL_63;
    }
    PfXpFreeNtPathTranslationList(v7);
  }
  else
  {
    LastError = 8;
  }
LABEL_63:
  HeapFree(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, v3);
LABEL_64:
  if ( v5 )
    HeapFree(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, v5);
  if ( !LastError && !*v1 )
    return 1359;
  return LastError;
}

```

## disassembly

```asm
0x180093ef0  mov     rax, rsp
0x180093ef3  mov     [rax+8], rcx
0x180093ef7  push    rbx
0x180093ef8  push    rbp
0x180093ef9  push    rsi
0x180093efa  push    rdi
0x180093efb  push    r12
0x180093efd  push    r13
0x180093eff  push    r14
0x180093f01  push    r15
0x180093f03  sub     rsp, 48h
0x180093f07  mov     rdi, rcx
0x180093f0a  mov     ebx, 20Ah
0x180093f0f  mov     rcx, cs:PfSvcGlobals
0x180093f16  xor     r15d, r15d
0x180093f19  mov     r8d, ebx; dwBytes
0x180093f1c  mov     [rax+10h], r15d
0x180093f20  xor     edx, edx; dwFlags
0x180093f22  mov     rcx, [rcx+58h]; hHeap
0x180093f26  call    cs:__imp_HeapAlloc
0x180093f2c  mov     rcx, cs:PfSvcGlobals
0x180093f33  mov     r8d, ebx; dwBytes
0x180093f36  xor     edx, edx; dwFlags
0x180093f38  mov     r14, rax
0x180093f3b  mov     rcx, [rcx+58h]; hHeap
0x180093f3f  call    cs:__imp_HeapAlloc
0x180093f45  mov     [rsp+88h+var_58], rax
0x180093f4a  mov     r12, rax
0x180093f4d  test    r14, r14
0x180093f50  jz      loc_1800942E3
0x180093f56  test    rax, rax
0x180093f59  jz      loc_1800942E3
0x180093f5f  mov     rcx, cs:PfSvcGlobals
0x180093f66  lea     r8d, [r15+10h]; dwBytes
0x180093f6a  xor     edx, edx; dwFlags
0x180093f6c  mov     rcx, [rcx+58h]; hHeap
0x180093f70  call    cs:__imp_HeapAlloc
0x180093f76  mov     rsi, rax
0x180093f79  test    rax, rax
0x180093f7c  jnz     short loc_180093F86
0x180093f7e  lea     ebx, [rax+8]
0x180093f81  jmp     loc_1800942ED
0x180093f86  mov     edx, 105h; cchBufferLength
0x180093f8b  mov     [rax+8], rsi
0x180093f8f  mov     rcx, r14; lpszVolumeName
0x180093f92  mov     [rax], rsi
0x180093f95  call    cs:__imp_FindFirstVolumeW
0x180093f9b  mov     [rsp+88h+hFindVolume], rax
0x180093fa0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180093fa4  jnz     short loc_180093FB3
0x180093fa6  call    cs:__imp_GetLastError
0x180093fac  mov     ebx, eax
0x180093fae  jmp     loc_180094290
0x180093fb3  mov     eax, r15d
0x180093fb6  mov     rbp, r15
0x180093fb9  mov     [rsp+88h+arg_18], eax
0x180093fc0  or      r13, 0FFFFFFFFFFFFFFFFh
0x180093fc4  inc     r13
0x180093fc7  cmp     [r14+r13*2], r15w
0x180093fcc  jnz     short loc_180093FC4
0x180093fce  mov     edi, r15d
0x180093fd1  lea     r9, [rsp+88h+cchReturnLength]; lpcchReturnLength
0x180093fd9  mov     r8d, eax; cchBufferLength
0x180093fdc  mov     rdx, rbp; lpszVolumePathNames
0x180093fdf  mov     rcx, r14; lpszVolumeName
0x180093fe2  call    cs:__imp_GetVolumePathNamesForVolumeNameW
0x180093fe8  test    eax, eax
0x180093fea  jnz     short loc_180094065
0x180093fec  call    cs:__imp_GetLastError
0x180093ff2  mov     ebx, eax
0x180093ff4  cmp     eax, 0EAh
0x180093ff9  jnz     loc_18009425D
0x180093fff  test    rbp, rbp
0x180094002  jz      short loc_18009401A
0x180094004  mov     rcx, cs:PfSvcGlobals
0x18009400b  mov     r8, rbp; lpMem
0x18009400e  xor     edx, edx; dwFlags
0x180094010  mov     rcx, [rcx+58h]; hHeap
0x180094014  call    cs:__imp_HeapFree
0x18009401a  mov     rcx, cs:PfSvcGlobals
0x180094021  xor     edx, edx; dwFlags
0x180094023  mov     r8d, [rsp+88h+cchReturnLength]
0x18009402b  add     r8, r8; dwBytes
0x18009402e  mov     rcx, [rcx+58h]; hHeap
0x180094032  call    cs:__imp_HeapAlloc
0x180094038  mov     rbp, rax
0x18009403b  test    rax, rax
0x18009403e  jz      loc_18009429A
0x180094044  inc     edi
0x180094046  cmp     edi, 3E8h
0x18009404c  ja      loc_180094258
0x180094052  mov     eax, [rsp+88h+cchReturnLength]
0x180094059  mov     [rsp+88h+arg_18], eax
0x180094060  jmp     loc_180093FD1
0x180094065  or      edi, 0FFFFFFFFh
0x180094068  mov     rdx, rbp
0x18009406b  mov     r8, r15
0x18009406e  cmp     [rbp+0], r15w
0x180094073  jz      loc_180094234
0x180094079  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18009407d  inc     rcx
0x180094080  cmp     [rdx+rcx*2], r15w
0x180094085  jnz     short loc_18009407D
0x180094087  cmp     ecx, edi
0x180094089  mov     rax, rdx
0x18009408c  cmovnb  rax, r8
0x180094090  mov     r8, rax
0x180094093  mov     eax, ecx
0x180094095  cmovnb  eax, edi
0x180094098  mov     edi, eax
0x18009409a  lea     eax, [rcx+1]
0x18009409d  lea     rdx, [rdx+rax*2]
0x1800940a1  cmp     [rdx], r15w
0x1800940a5  jnz     short loc_180094079
0x1800940a7  mov     [rsp+88h+Src], r8
0x1800940ac  mov     [rsp+88h+arg_10], edi
0x1800940b3  test    r8, r8
0x1800940b6  jz      loc_180094234
0x1800940bc  lea     ecx, [rdi-1]
0x1800940bf  mov     r9d, 5Ch ; '\'
0x1800940c5  cmp     [r8+rcx*2], r9w
0x1800940ca  jnz     short loc_1800940DA
0x1800940cc  mov     [r8+rcx*2], r15w
0x1800940d1  mov     edi, ecx
0x1800940d3  mov     [rsp+88h+arg_10], ecx
0x1800940da  cmp     r13d, 4
0x1800940de  jbe     loc_1800942BC
0x1800940e4  lea     eax, [r13-1]
0x1800940e8  mov     ebx, eax
0x1800940ea  cmp     [r14+rax*2], r9w
0x1800940ef  jnz     short loc_1800940F9
0x1800940f1  mov     [r14+rax*2], r15w
0x1800940f6  mov     r15b, 1
0x1800940f9  lea     rcx, [r14+8]; lpDeviceName
0x1800940fd  mov     r8d, 105h; ucchMax
0x180094103  mov     rdx, r12; lpTargetPath
0x180094106  call    cs:__imp_QueryDosDeviceW
0x18009410c  mov     r8d, 5Ch ; '\'
0x180094112  test    r15b, r15b
0x180094115  jz      short loc_18009411C
0x180094117  mov     [r14+rbx*2], r8w
0x18009411c  xor     r15d, r15d
0x18009411f  test    eax, eax
0x180094121  jz      loc_1800942B2
0x180094127  mov     [r12+208h], r15w
0x180094130  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180094134  inc     rbx
0x180094137  cmp     [r12+rbx*2], r15w
0x18009413c  jnz     short loc_180094134
0x18009413e  test    ebx, ebx
0x180094140  jz      loc_180094234
0x180094146  lea     ecx, [rbx-1]
0x180094149  cmp     [r12+rcx*2], r8w
0x18009414e  jnz     short loc_180094157
0x180094150  mov     [r12+rcx*2], r15w
0x180094155  mov     ebx, ecx
0x180094157  mov     rcx, cs:PfSvcGlobals
0x18009415e  lea     eax, [rdi+rbx]
0x180094161  add     eax, r13d
0x180094164  xor     edx, edx; dwFlags
0x180094166  mov     rcx, [rcx+58h]; hHeap
0x18009416a  lea     r8d, ds:46h[rax*2]; dwBytes
0x180094172  call    cs:__imp_HeapAlloc
0x180094178  mov     r15, rax
0x18009417b  test    rax, rax
0x18009417e  jz      loc_1800942A8
0x180094184  lea     ecx, ds:2[rbx*2]
0x18009418b  mov     [rax+18h], ebx
0x18009418e  lea     rdi, [rax+40h]
0x180094192  mov     ebx, ecx
0x180094194  mov     r8d, ecx; Size
0x180094197  mov     rdx, r12; Src
0x18009419a  mov     rcx, rdi; void *
0x18009419d  mov     [rax+10h], rdi
0x1800941a1  call    memcpy_0
0x1800941a6  mov     eax, [rsp+88h+arg_10]
0x1800941ad  add     rdi, rbx
0x1800941b0  mov     rdx, [rsp+88h+Src]; Src
0x1800941b5  mov     rcx, rdi; void *
0x1800941b8  mov     [r15+28h], eax
0x1800941bc  mov     [r15+20h], rdi
0x1800941c0  lea     eax, ds:2[rax*2]
0x1800941c7  mov     r8d, eax; Size
0x1800941ca  mov     ebx, eax
0x1800941cc  call    memcpy_0
0x1800941d1  lea     rcx, [rdi+rbx]; void *
0x1800941d5  mov     [r15+38h], r13d
0x1800941d9  lea     r8d, ds:2[r13*2]; Size
0x1800941e1  mov     [r15+30h], rcx
0x1800941e5  mov     rdx, r14; Src
0x1800941e8  call    memcpy_0
0x1800941ed  mov     rbx, [rsi]
0x1800941f0  mov     rdi, rsi
0x1800941f3  cmp     rbx, rsi
0x1800941f6  jz      short loc_18009421A
0x1800941f8  mov     rdx, [rbx+10h]; String2
0x1800941fc  mov     rcx, [r15+10h]; String1
0x180094200  call    cs:__imp__wcsicmp
0x180094206  test    eax, eax
0x180094208  jle     short loc_180094215
0x18009420a  mov     rdi, rbx
0x18009420d  mov     rbx, [rbx]
0x180094210  cmp     rbx, rsi
0x180094213  jnz     short loc_1800941F8
0x180094215  mov     r12, [rsp+88h+var_58]
0x18009421a  mov     rax, [rdi]
0x18009421d  cmp     [rax+8], rdi
0x180094221  jnz     short loc_1800942A1
0x180094223  mov     [r15], rax
0x180094226  mov     [r15+8], rdi
0x18009422a  mov     [rax+8], r15
0x18009422e  mov     [rdi], r15
0x180094231  xor     r15d, r15d
0x180094234  mov     rcx, [rsp+88h+hFindVolume]; hFindVolume
0x180094239  mov     r8d, 105h; cchBufferLength
0x18009423f  mov     rdx, r14; lpszVolumeName
0x180094242  call    cs:__imp_FindNextVolumeW
0x180094248  test    eax, eax
0x18009424a  jz      short loc_1800942C3
0x18009424c  mov     eax, [rsp+88h+arg_18]
0x180094253  jmp     loc_180093FC0
0x180094258  mov     ebx, 1
0x18009425d  mov     rdi, [rsp+88h+arg_0]
0x180094265  mov     rcx, [rsp+88h+hFindVolume]; hFindVolume
0x18009426a  call    cs:__imp_FindVolumeClose
0x180094270  test    rbp, rbp
0x180094273  jz      short loc_18009428B
0x180094275  mov     rcx, cs:PfSvcGlobals
0x18009427c  mov     r8, rbp; lpMem
0x18009427f  xor     edx, edx; dwFlags
0x180094281  mov     rcx, [rcx+58h]; hHeap
0x180094285  call    cs:__imp_HeapFree
0x18009428b  test    rsi, rsi
0x18009428e  jz      short loc_1800942ED
0x180094290  mov     rcx, rsi
0x180094293  call    PfXpFreeNtPathTranslationList
0x180094298  jmp     short loc_1800942ED
0x18009429a  mov     ebx, 8
0x18009429f  jmp     short loc_18009425D
0x1800942a1  mov     ecx, 3
0x1800942a6  int     29h; Win8: RtlFailFast(ecx)
0x1800942a8  mov     ebx, 8
0x1800942ad  xor     r15d, r15d
0x1800942b0  jmp     short loc_18009425D
0x1800942b2  call    cs:__imp_GetLastError
0x1800942b8  mov     ebx, eax
0x1800942ba  jmp     short loc_18009425D
0x1800942bc  mov     ebx, 0Bh
0x1800942c1  jmp     short loc_18009425D
0x1800942c3  call    cs:__imp_GetLastError
0x1800942c9  mov     ebx, eax
0x1800942cb  cmp     eax, 12h
0x1800942ce  jnz     short loc_18009425D
0x1800942d0  mov     rdi, [rsp+88h+arg_0]
0x1800942d8  mov     ebx, r15d
0x1800942db  mov     [rdi], rsi
0x1800942de  mov     rsi, r15
0x1800942e1  jmp     short loc_180094265
0x1800942e3  mov     ebx, 8
0x1800942e8  test    r14, r14
0x1800942eb  jz      short loc_180094303
0x1800942ed  mov     rcx, cs:PfSvcGlobals
0x1800942f4  mov     r8, r14; lpMem
0x1800942f7  xor     edx, edx; dwFlags
0x1800942f9  mov     rcx, [rcx+58h]; hHeap
0x1800942fd  call    cs:__imp_HeapFree
0x180094303  test    r12, r12
0x180094306  jz      short loc_18009431E
0x180094308  mov     rcx, cs:PfSvcGlobals
0x18009430f  mov     r8, r12; lpMem
0x180094312  xor     edx, edx; dwFlags
0x180094314  mov     rcx, [rcx+58h]; hHeap
0x180094318  call    cs:__imp_HeapFree
0x18009431e  test    ebx, ebx
0x180094320  jnz     short loc_18009432D
0x180094322  cmp     [rdi], r15
0x180094325  mov     eax, 54Fh
0x18009432a  cmovz   ebx, eax
0x18009432d  mov     eax, ebx
0x18009432f  add     rsp, 48h
0x180094333  pop     r15
0x180094335  pop     r14
0x180094337  pop     r13
0x180094339  pop     r12
0x18009433b  pop     rdi
0x18009433c  pop     rsi
0x18009433d  pop     rbp
0x18009433e  pop     rbx
0x18009433f  retn
```
