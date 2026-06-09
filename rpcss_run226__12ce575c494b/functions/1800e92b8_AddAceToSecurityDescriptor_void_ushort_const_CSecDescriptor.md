# AddAceToSecurityDescriptor(void *,ushort const *,CSecDescriptor * *)

- ea: `0x1800e92b8`
- end: `0x1800e9554`
- name: `?AddAceToSecurityDescriptor@@YAJPEAXPEBGPEAPEAVCSecDescriptor@@@Z`
- size: `668`
- prototype: `__int64 __fastcall(void *, const unsigned __int16 *, struct CSecDescriptor **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18009709c`

## callees

- `0x180034540`
- `0x1800672dc`
- `0x18007e3d4`
- `0x1800e92b8`
- `0x18010a084`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e92fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e93ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e940b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e92fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e93ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e940b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800e94d1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800e952b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800e94d1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800e952b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800e93a0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800e946a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800e9499`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800e93a0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800e946a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800e9499`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x1800e9456`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x1800e94b1`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x1800e9456`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x1800e94b1`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800e9401`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800e9401`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x1800e92ee`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x1800e92ee`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1800e9514`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1800e953b`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1800e9514`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1800e953b`

## string_xrefs

- `0x1800e9356`: `onecore\com\combase\rpcss\olescm\registry.cxx`
- `0x1800e934f`: `AddAceToSecurityDescriptor`

## pseudocode

```c
__int64 __fastcall AddAceToSecurityDescriptor(void *a1, const unsigned __int16 *a2, struct CSecDescriptor **a3)
{
  WCHAR *v5; // rbp
  signed int v6; // eax
  signed int v7; // ebx
  int v8; // r8d
  __int64 v9; // rax
  __int64 v10; // rcx
  SIZE_T v11; // rdi
  unsigned __int16 *v12; // rax
  signed int v13; // eax
  signed int LastError; // eax
  DWORD SecurityDescriptorLength; // edi
  void *v16; // rax
  void *v17; // rsi
  struct CSecDescriptor *v18; // rax
  struct CSecDescriptor *v19; // rdi
  HANDLE v20; // rcx
  HLOCAL hMem; // [rsp+70h] [rbp+18h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+78h] [rbp+20h] BYREF

  *a3 = 0;
  hMem = 0;
  SecurityDescriptor = 0;
  if ( ConvertSecurityDescriptorToStringSecurityDescriptorW(a1, 1u, 0x7Fu, (LPWSTR *)&hMem, 0) )
  {
    v9 = -1;
    v10 = -1;
    do
      ++v10;
    while ( a2[v10] );
    do
      ++v9;
    while ( *((_WORD *)hMem + v9) );
    v11 = (unsigned int)(2 * (v10 + v9) + 2);
    v12 = (unsigned __int16 *)HeapAlloc(g_hHeap, 0, v11);
    v5 = v12;
    if ( v12 )
    {
      v7 = StringCbPrintfW(v12, v11, L"%s%s", hMem, a2);
      if ( v7 >= 0 )
      {
        if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(v5, 1u, &SecurityDescriptor, 0) )
        {
          SecurityDescriptorLength = GetSecurityDescriptorLength(SecurityDescriptor);
          v16 = HeapAlloc(g_hHeap, 0, SecurityDescriptorLength);
          v17 = v16;
          if ( v16 )
          {
            memcpy_0(v16, SecurityDescriptor, SecurityDescriptorLength);
            v18 = (struct CSecDescriptor *)HeapAlloc(g_hHeap, 0, 0x10u);
            v19 = v18;
            if ( v18 )
            {
              *((_DWORD *)v18 + 3) = 1;
              *((_DWORD *)v18 + 2) = GetSecurityDescriptorLength(v17);
              *(_QWORD *)v19 = v17;
              *a3 = v19;
            }
            else
            {
              v20 = g_hHeap;
              *a3 = 0;
              HeapFree(v20, 0, v17);
              v7 = -2147024882;
              if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
              {
                v8 = 144;
                goto LABEL_8;
              }
            }
          }
          else
          {
            v7 = -2147024882;
          }
        }
        else
        {
          LastError = GetLastError();
          v7 = LastError;
          if ( LastError > 0 )
            v7 = (unsigned __int16)LastError | 0x80070000;
          if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
          {
            v8 = 117;
            goto LABEL_8;
          }
        }
      }
    }
    else
    {
      v13 = GetLastError();
      v7 = v13;
      if ( v13 > 0 )
        v7 = (unsigned __int16)v13 | 0x80070000;
    }
  }
  else
  {
    v5 = 0;
    v6 = GetLastError();
    v7 = v6;
    if ( v6 > 0 )
      v7 = (unsigned __int16)v6 | 0x80070000;
    if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
    {
      v8 = 86;
LABEL_8:
      ComTraceMessageT<long>(
        (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\registry.cxx",
        (unsigned int)"AddAceToSecurityDescriptor",
        v8,
        0,
        (__int64)L"%!HRESULT!",
        v7);
    }
  }
  if ( hMem )
    LocalFree(hMem);
  if ( v5 )
    HeapFree(g_hHeap, 0, v5);
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800e92b8  mov     rax, rsp
0x1800e92bb  mov     [rax+8], rbx
0x1800e92bf  push    rbp
0x1800e92c0  push    rsi
0x1800e92c1  push    rdi
0x1800e92c2  push    r14
0x1800e92c4  push    r15
0x1800e92c6  sub     rsp, 30h
0x1800e92ca  xor     r15d, r15d
0x1800e92cd  lea     r9, [rax+18h]; StringSecurityDescriptor
0x1800e92d1  mov     r14, r8
0x1800e92d4  mov     [r8], r15
0x1800e92d7  mov     rbx, rdx
0x1800e92da  mov     [rax+18h], r15
0x1800e92de  mov     [rax+20h], r15
0x1800e92e2  lea     edx, [r15+1]; RequestedStringSDRevision
0x1800e92e6  mov     [rax-38h], r15
0x1800e92ea  lea     r8d, [r15+7Fh]; SecurityInformation
0x1800e92ee  call    cs:__imp_ConvertSecurityDescriptorToStringSecurityDescriptorW
0x1800e92f4  test    eax, eax
0x1800e92f6  jnz     short loc_1800E9367
0x1800e92f8  mov     ebp, r15d
0x1800e92fb  call    cs:__imp_GetLastError
0x1800e9301  mov     ebx, eax
0x1800e9303  test    eax, eax
0x1800e9305  jle     short loc_1800E9310
0x1800e9307  movzx   ebx, ax
0x1800e930a  or      ebx, 80070000h
0x1800e9310  mov     eax, cs:dword_18014E4B8
0x1800e9316  test    eax, eax
0x1800e9318  jnz     short loc_1800E9336
0x1800e931a  cmp     cs:?gfEnableTracing@@3HA, r15d; int gfEnableTracing
0x1800e9321  jz      loc_1800E950A
0x1800e9327  xor     ecx, ecx
0x1800e9329  call    IsWppLevelEnabled
0x1800e932e  test    al, al
0x1800e9330  jz      loc_1800E950A
0x1800e9336  mov     r8d, 56h ; 'V'
0x1800e933c  lea     rax, aHresult; "%!HRESULT!"
0x1800e9343  mov     [rsp+58h+var_30], ebx
0x1800e9347  xor     r9d, r9d
0x1800e934a  mov     [rsp+58h+var_38], rax
0x1800e934f  lea     rdx, aAddacetosecuri; "AddAceToSecurityDescriptor"
0x1800e9356  lea     rcx, aOnecoreComComb_114; "onecore\\com\\combase\\rpcss\\olescm\\r"...
0x1800e935d  call    ??$ComTraceMessageT@J@@YAXPEBD0HW4TraceLevel@@PEBGJ@Z; ComTraceMessageT<long>(char const *,char const *,int,TraceLevel,ushort const *,long)
0x1800e9362  jmp     loc_1800E950A
0x1800e9367  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800e936b  mov     rcx, rax
0x1800e936e  inc     rcx
0x1800e9371  cmp     [rbx+rcx*2], r15w
0x1800e9376  jnz     short loc_1800E936E
0x1800e9378  mov     rdx, [rsp+58h+hMem]
0x1800e937d  inc     rax
0x1800e9380  cmp     [rdx+rax*2], r15w
0x1800e9385  jnz     short loc_1800E937D
0x1800e9387  add     rax, rcx
0x1800e938a  xor     edx, edx; dwFlags
0x1800e938c  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800e9393  lea     rax, ds:2[rax*2]
0x1800e939b  mov     r8d, eax; dwBytes
0x1800e939e  mov     edi, eax
0x1800e93a0  call    cs:__imp_HeapAlloc
0x1800e93a6  mov     rbp, rax
0x1800e93a9  test    rax, rax
0x1800e93ac  jnz     short loc_1800E93CC
0x1800e93ae  call    cs:__imp_GetLastError
0x1800e93b4  mov     ebx, eax
0x1800e93b6  test    eax, eax
0x1800e93b8  jle     loc_1800E950A
0x1800e93be  movzx   ebx, ax
0x1800e93c1  or      ebx, 80070000h
0x1800e93c7  jmp     loc_1800E950A
0x1800e93cc  mov     r9, [rsp+58h+hMem]
0x1800e93d1  lea     r8, aSS_0; "%s%s"
0x1800e93d8  mov     rdx, rdi; unsigned __int64
0x1800e93db  mov     [rsp+58h+var_38], rbx
0x1800e93e0  mov     rcx, rbp; unsigned __int16 *
0x1800e93e3  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800e93e8  mov     ebx, eax
0x1800e93ea  test    eax, eax
0x1800e93ec  js      loc_1800E950A
0x1800e93f2  xor     r9d, r9d; SecurityDescriptorSize
0x1800e93f5  lea     r8, [rsp+58h+SecurityDescriptor]; SecurityDescriptor
0x1800e93fa  mov     rcx, rbp; StringSecurityDescriptor
0x1800e93fd  lea     edx, [r9+1]; StringSDRevision
0x1800e9401  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800e9407  test    eax, eax
0x1800e9409  jnz     short loc_1800E9451
0x1800e940b  call    cs:__imp_GetLastError
0x1800e9411  mov     ebx, eax
0x1800e9413  test    eax, eax
0x1800e9415  jle     short loc_1800E9420
0x1800e9417  movzx   ebx, ax
0x1800e941a  or      ebx, 80070000h
0x1800e9420  mov     eax, cs:dword_18014E4B8
0x1800e9426  test    eax, eax
0x1800e9428  jnz     short loc_1800E9446
0x1800e942a  cmp     cs:?gfEnableTracing@@3HA, r15d; int gfEnableTracing
0x1800e9431  jz      loc_1800E950A
0x1800e9437  xor     ecx, ecx
0x1800e9439  call    IsWppLevelEnabled
0x1800e943e  test    al, al
0x1800e9440  jz      loc_1800E950A
0x1800e9446  mov     r8d, 75h ; 'u'
0x1800e944c  jmp     loc_1800E933C
0x1800e9451  mov     rcx, [rsp+58h+SecurityDescriptor]; pSecurityDescriptor
0x1800e9456  call    cs:__imp_GetSecurityDescriptorLength
0x1800e945c  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800e9463  xor     edx, edx; dwFlags
0x1800e9465  mov     r8d, eax; dwBytes
0x1800e9468  mov     edi, eax
0x1800e946a  call    cs:__imp_HeapAlloc
0x1800e9470  mov     rsi, rax
0x1800e9473  test    rax, rax
0x1800e9476  jz      loc_1800E9505
0x1800e947c  mov     rdx, [rsp+58h+SecurityDescriptor]; Src
0x1800e9481  mov     r8d, edi; Size
0x1800e9484  mov     rcx, rax; void *
0x1800e9487  call    memcpy_0
0x1800e948c  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800e9493  xor     edx, edx; dwFlags
0x1800e9495  lea     r8d, [rdx+10h]; dwBytes
0x1800e9499  call    cs:__imp_HeapAlloc
0x1800e949f  mov     rdi, rax
0x1800e94a2  test    rax, rax
0x1800e94a5  jz      short loc_1800E94C2
0x1800e94a7  mov     rcx, rsi; pSecurityDescriptor
0x1800e94aa  mov     dword ptr [rax+0Ch], 1
0x1800e94b1  call    cs:__imp_GetSecurityDescriptorLength
0x1800e94b7  mov     [rdi+8], eax
0x1800e94ba  mov     [rdi], rsi
0x1800e94bd  mov     [r14], rdi
0x1800e94c0  jmp     short loc_1800E950A
0x1800e94c2  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800e94c9  mov     r8, rsi; lpMem
0x1800e94cc  xor     edx, edx; dwFlags
0x1800e94ce  mov     [r14], r15
0x1800e94d1  call    cs:__imp_HeapFree
0x1800e94d7  mov     eax, cs:dword_18014E4B8
0x1800e94dd  mov     ebx, 8007000Eh
0x1800e94e2  test    eax, eax
0x1800e94e4  jnz     short loc_1800E94FA
0x1800e94e6  cmp     cs:?gfEnableTracing@@3HA, r15d; int gfEnableTracing
0x1800e94ed  jz      short loc_1800E950A
0x1800e94ef  xor     ecx, ecx
0x1800e94f1  call    IsWppLevelEnabled
0x1800e94f6  test    al, al
0x1800e94f8  jz      short loc_1800E950A
0x1800e94fa  mov     r8d, 90h
0x1800e9500  jmp     loc_1800E933C
0x1800e9505  mov     ebx, 8007000Eh
0x1800e950a  mov     rcx, [rsp+58h+hMem]; hMem
0x1800e950f  test    rcx, rcx
0x1800e9512  jz      short loc_1800E951A
0x1800e9514  call    cs:__imp_LocalFree
0x1800e951a  test    rbp, rbp
0x1800e951d  jz      short loc_1800E9531
0x1800e951f  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800e9526  mov     r8, rbp; lpMem
0x1800e9529  xor     edx, edx; dwFlags
0x1800e952b  call    cs:__imp_HeapFree
0x1800e9531  mov     rcx, [rsp+58h+SecurityDescriptor]; hMem
0x1800e9536  test    rcx, rcx
0x1800e9539  jz      short loc_1800E9541
0x1800e953b  call    cs:__imp_LocalFree
0x1800e9541  mov     eax, ebx
0x1800e9543  mov     rbx, [rsp+58h+arg_0]
0x1800e9548  add     rsp, 30h
0x1800e954c  pop     r15
0x1800e954e  pop     r14
0x1800e9550  pop     rdi
0x1800e9551  pop     rsi
0x1800e9552  pop     rbp
0x1800e9553  retn
```
