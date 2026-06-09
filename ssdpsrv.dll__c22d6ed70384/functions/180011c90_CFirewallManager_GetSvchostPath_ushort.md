# CFirewallManager::GetSvchostPath(ushort * *)

- ea: `0x180011c90`
- end: `0x180011f3c`
- name: `?GetSvchostPath@CFirewallManager@@AEAAKPEAPEAG@Z`
- size: `684`
- prototype: `__int64 __fastcall(CFirewallManager *this, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180010ce0`

## callees

- `0x18000936c`
- `0x180011c90`
- `0x18001c724`
- `0x1800255a8`
- `0x180032110`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180011d22`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180011d22`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180011cb4`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180011d64`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180011cb4`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180011d64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011cbe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011d6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011cbe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011d6e`

## string_xrefs

- `0x180011e90`: `system32\svchost.exe`

## pseudocode

```c
__int64 __fastcall CFirewallManager::GetSvchostPath(CFirewallManager *this, unsigned __int16 **a2)
{
  UINT SystemWindowsDirectoryW; // eax
  DWORD LastError; // eax
  unsigned int v6; // ebx
  LPCSTR v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // r9
  UINT v10; // ebx
  unsigned __int64 v11; // rdi
  WCHAR *v12; // rax
  WCHAR *v13; // rsi
  UINT v14; // eax
  DWORD v15; // eax
  LPCSTR v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // r9
  unsigned int v19; // ebx
  LPCSTR v20; // rcx
  __int64 v21; // rdx
  __int64 v22; // r8
  unsigned __int64 v23; // rcx
  WCHAR *v24; // rax
  unsigned __int64 v25; // rdx
  unsigned __int64 v26; // rdi
  const wchar_t *v27; // rax
  WCHAR *i; // rdx
  WCHAR *v29; // rcx

  if ( !a2 )
    return 87;
  *a2 = 0;
  SystemWindowsDirectoryW = GetSystemWindowsDirectoryW(0, 0);
  if ( !SystemWindowsDirectoryW )
  {
    LastError = GetLastError();
    v6 = LastError;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCSTR)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
      return v6;
    v8 = 14;
    v9 = LastError;
    goto LABEL_7;
  }
  v10 = SystemWindowsDirectoryW + 23;
  v11 = SystemWindowsDirectoryW + 23;
  v12 = (WCHAR *)malloc(saturated_mul(v11, 2u));
  v13 = v12;
  if ( v12 )
  {
    v14 = GetSystemWindowsDirectoryW(v12, v10);
    if ( !v14 )
    {
      v15 = GetLastError();
      v6 = v15;
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCSTR)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
        goto LABEL_48;
      v17 = 16;
      v18 = v15;
      goto LABEL_16;
    }
    if ( v14 >= v10 )
    {
      v6 = 122;
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCSTR)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
        goto LABEL_48;
      v17 = 17;
      v18 = 122;
LABEL_16:
      WPP_SF_d(*((_QWORD *)v16 + 2), v17, WPP_db283a32a0f73fa63383008e81c323d4_Traceguids, v18);
LABEL_48:
      operator delete(v13);
      return v6;
    }
    if ( v13[v14 - 1] == 92 || (v19 = StringCchCatW(v13, v11, L"\\")) == 0 )
    {
      v22 = 2147483646;
      if ( v11 - 1 > 0x7FFFFFFE )
      {
        v19 = -2147024809;
      }
      else
      {
        v23 = v11;
        v24 = v13;
        do
        {
          if ( !*v24 )
            break;
          ++v24;
          --v23;
        }
        while ( v23 );
        v19 = v23 == 0 ? 0x80070057 : 0;
        if ( v23 )
          v25 = v11 - v23;
        else
          v25 = 0;
        if ( v23 )
        {
          v26 = v11 - v25;
          v27 = L"system32\\svchost.exe";
          for ( i = &v13[v25]; v26; --v26 )
          {
            if ( !v22 )
              break;
            if ( !*v27 )
              break;
            *i++ = *v27++;
            --v22;
          }
          v29 = i - 1;
          v19 = v26 == 0 ? 0x8007007A : 0;
          if ( v26 )
            v29 = i;
          *v29 = 0;
          if ( v26 )
          {
            v6 = 0;
            *a2 = v13;
            return v6;
          }
        }
      }
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCSTR)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
        goto LABEL_47;
      v21 = 19;
    }
    else
    {
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCSTR)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
        goto LABEL_47;
      v21 = 18;
    }
    WPP_SF_d(*((_QWORD *)v20 + 2), v21, WPP_db283a32a0f73fa63383008e81c323d4_Traceguids, v19);
LABEL_47:
    v6 = DwWin32ErrorFromHr(v19);
    goto LABEL_48;
  }
  v6 = 8;
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (LPCSTR)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
    return v6;
  v8 = 15;
  v9 = 8;
LABEL_7:
  WPP_SF_d(*((_QWORD *)v7 + 2), v8, WPP_db283a32a0f73fa63383008e81c323d4_Traceguids, v9);
  return v6;
}

```

## disassembly

```asm
0x180011c90  push    rbx
0x180011c92  push    rbp
0x180011c93  push    rsi
0x180011c94  push    rdi
0x180011c95  push    r14
0x180011c97  sub     rsp, 20h
0x180011c9b  xor     ebp, ebp
0x180011c9d  mov     r14, rdx
0x180011ca0  test    rdx, rdx
0x180011ca3  jnz     short loc_180011CAD
0x180011ca5  lea     eax, [rdx+57h]
0x180011ca8  jmp     loc_180011F31
0x180011cad  mov     [rdx], rbp
0x180011cb0  xor     ecx, ecx; lpBuffer
0x180011cb2  xor     edx, edx; uSize
0x180011cb4  call    cs:__imp_GetSystemWindowsDirectoryW
0x180011cba  test    eax, eax
0x180011cbc  jnz     short loc_180011D07
0x180011cbe  call    cs:__imp_GetLastError
0x180011cc4  mov     ebx, eax
0x180011cc6  mov     rcx, cs:WPP_GLOBAL_Control
0x180011ccd  lea     rdx, WPP_GLOBAL_Control
0x180011cd4  cmp     rcx, rdx
0x180011cd7  jz      loc_180011F2F
0x180011cdd  test    dword ptr [rcx+1Ch], 200h
0x180011ce4  jz      loc_180011F2F
0x180011cea  mov     edx, 0Eh
0x180011cef  mov     r9d, eax
0x180011cf2  mov     rcx, [rcx+10h]
0x180011cf6  lea     r8, WPP_db283a32a0f73fa63383008e81c323d4_Traceguids
0x180011cfd  call    WPP_SF_d
0x180011d02  jmp     loc_180011F2F
0x180011d07  lea     ebx, [rax+17h]
0x180011d0a  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180011d11  mov     edi, ebx
0x180011d13  mov     eax, 2
0x180011d18  mul     rdi
0x180011d1b  cmovb   rax, rcx
0x180011d1f  mov     rcx, rax; Size
0x180011d22  call    cs:__imp_malloc
0x180011d28  mov     rsi, rax
0x180011d2b  test    rax, rax
0x180011d2e  jnz     short loc_180011D5F
0x180011d30  lea     ebx, [rax+8]
0x180011d33  mov     rcx, cs:WPP_GLOBAL_Control
0x180011d3a  lea     rdx, WPP_GLOBAL_Control
0x180011d41  cmp     rcx, rdx
0x180011d44  jz      loc_180011F2F
0x180011d4a  test    dword ptr [rcx+1Ch], 200h
0x180011d51  jz      loc_180011F2F
0x180011d57  lea     edx, [rax+0Fh]
0x180011d5a  mov     r9d, ebx
0x180011d5d  jmp     short loc_180011CF2
0x180011d5f  mov     edx, ebx; uSize
0x180011d61  mov     rcx, rsi; lpBuffer
0x180011d64  call    cs:__imp_GetSystemWindowsDirectoryW
0x180011d6a  test    eax, eax
0x180011d6c  jnz     short loc_180011DB7
0x180011d6e  call    cs:__imp_GetLastError
0x180011d74  mov     ebx, eax
0x180011d76  mov     rcx, cs:WPP_GLOBAL_Control
0x180011d7d  lea     rdx, WPP_GLOBAL_Control
0x180011d84  cmp     rcx, rdx
0x180011d87  jz      loc_180011F27
0x180011d8d  test    dword ptr [rcx+1Ch], 200h
0x180011d94  jz      loc_180011F27
0x180011d9a  mov     edx, 10h
0x180011d9f  mov     r9d, eax
0x180011da2  mov     rcx, [rcx+10h]
0x180011da6  lea     r8, WPP_db283a32a0f73fa63383008e81c323d4_Traceguids
0x180011dad  call    WPP_SF_d
0x180011db2  jmp     loc_180011F27
0x180011db7  cmp     eax, ebx
0x180011db9  jb      short loc_180011DEC
0x180011dbb  mov     ebx, 7Ah ; 'z'
0x180011dc0  mov     rcx, cs:WPP_GLOBAL_Control
0x180011dc7  lea     rdx, WPP_GLOBAL_Control
0x180011dce  cmp     rcx, rdx
0x180011dd1  jz      loc_180011F27
0x180011dd7  test    dword ptr [rcx+1Ch], 200h
0x180011dde  jz      loc_180011F27
0x180011de4  lea     edx, [rbx-69h]
0x180011de7  mov     r9d, ebx
0x180011dea  jmp     short loc_180011DA2
0x180011dec  lea     ecx, [rax-1]
0x180011def  mov     eax, 5Ch ; '\'
0x180011df4  cmp     ax, [rsi+rcx*2]
0x180011df8  jz      short loc_180011E40
0x180011dfa  lea     r8, asc_1800394F0; "\\"
0x180011e01  mov     rdx, rdi; unsigned __int64
0x180011e04  mov     rcx, rsi; unsigned __int16 *
0x180011e07  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180011e0c  mov     ebx, eax
0x180011e0e  test    eax, eax
0x180011e10  jz      short loc_180011E40
0x180011e12  mov     rcx, cs:WPP_GLOBAL_Control
0x180011e19  lea     rdx, WPP_GLOBAL_Control
0x180011e20  cmp     rcx, rdx
0x180011e23  jz      loc_180011F1E
0x180011e29  test    dword ptr [rcx+1Ch], 200h
0x180011e30  jz      loc_180011F1E
0x180011e36  mov     edx, 12h
0x180011e3b  jmp     loc_180011F0B
0x180011e40  lea     rax, [rdi-1]
0x180011e44  mov     r8d, 7FFFFFFEh
0x180011e4a  cmp     rax, r8
0x180011e4d  ja      loc_180011EE5
0x180011e53  mov     rcx, rdi
0x180011e56  mov     rax, rsi
0x180011e59  mov     rdx, rdi
0x180011e5c  cmp     [rax], bp
0x180011e5f  jz      short loc_180011E6B
0x180011e61  add     rax, 2
0x180011e65  sub     rcx, 1
0x180011e69  jnz     short loc_180011E5C
0x180011e6b  mov     rax, rcx
0x180011e6e  neg     rax
0x180011e71  sbb     ebx, ebx
0x180011e73  not     ebx
0x180011e75  and     ebx, 80070057h
0x180011e7b  test    rcx, rcx
0x180011e7e  jz      short loc_180011E85
0x180011e80  sub     rdx, rcx
0x180011e83  jmp     short loc_180011E88
0x180011e85  mov     rdx, rbp
0x180011e88  test    rcx, rcx
0x180011e8b  jz      short loc_180011EEA
0x180011e8d  sub     rdi, rdx
0x180011e90  lea     rax, aSystem32Svchos; "system32\\svchost.exe"
0x180011e97  lea     rdx, [rsi+rdx*2]
0x180011e9b  jz      short loc_180011EBE
0x180011e9d  test    r8, r8
0x180011ea0  jz      short loc_180011EBE
0x180011ea2  movzx   ecx, word ptr [rax]
0x180011ea5  test    cx, cx
0x180011ea8  jz      short loc_180011EBE
0x180011eaa  mov     [rdx], cx
0x180011ead  add     rax, 2
0x180011eb1  add     rdx, 2
0x180011eb5  dec     r8
0x180011eb8  sub     rdi, 1
0x180011ebc  jnz     short loc_180011E9D
0x180011ebe  mov     rax, rdi
0x180011ec1  lea     rcx, [rdx-2]
0x180011ec5  neg     rax
0x180011ec8  sbb     ebx, ebx
0x180011eca  not     ebx
0x180011ecc  and     ebx, 8007007Ah
0x180011ed2  test    rdi, rdi
0x180011ed5  cmovnz  rcx, rdx
0x180011ed9  mov     [rcx], bp
0x180011edc  jz      short loc_180011EEA
0x180011ede  mov     ebx, ebp
0x180011ee0  mov     [r14], rsi
0x180011ee3  jmp     short loc_180011F2F
0x180011ee5  mov     ebx, 80070057h
0x180011eea  mov     rcx, cs:WPP_GLOBAL_Control
0x180011ef1  lea     rdx, WPP_GLOBAL_Control
0x180011ef8  cmp     rcx, rdx
0x180011efb  jz      short loc_180011F1E
0x180011efd  test    dword ptr [rcx+1Ch], 200h
0x180011f04  jz      short loc_180011F1E
0x180011f06  mov     edx, 13h
0x180011f0b  mov     rcx, [rcx+10h]
0x180011f0f  lea     r8, WPP_db283a32a0f73fa63383008e81c323d4_Traceguids
0x180011f16  mov     r9d, ebx
0x180011f19  call    WPP_SF_d
0x180011f1e  mov     ecx, ebx; int
0x180011f20  call    ?DwWin32ErrorFromHr@@YAKJ@Z; DwWin32ErrorFromHr(long)
0x180011f25  mov     ebx, eax
0x180011f27  mov     rcx, rsi; void *
0x180011f2a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180011f2f  mov     eax, ebx
0x180011f31  add     rsp, 20h
0x180011f35  pop     r14
0x180011f37  pop     rdi
0x180011f38  pop     rsi
0x180011f39  pop     rbp
0x180011f3a  pop     rbx
0x180011f3b  retn
```
