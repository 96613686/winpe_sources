# SsipVerifyAndLoad

- ea: `0x18002b2b8`
- end: `0x18002b7d2`
- name: `SsipVerifyAndLoad`
- size: `1306`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting`

## callers

- `0x18002a6f8`

## callees

- `0x180003520`
- `0x1800061a0`
- `0x180009770`
- `0x180011fec`
- `0x180012880`
- `0x1800185b8`
- `0x18001874c`
- `0x18002ac54`
- `0x18002af40`
- `0x18002b2b8`
- `0x18002b7d8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncat_s` at `0x18002b402`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncat_s` at `0x18002b43e`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncat_s` at `0x18002b402`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncat_s` at `0x18002b43e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002b579`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002b579`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002b736`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002b736`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002b476`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002b476`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b496`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b752`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b496`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b752`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x18002b3e4`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x18002b3e4`
- `ntdll!RtlLeaveCriticalSection` at `0x18002b643`
- `ntdll!RtlLeaveCriticalSection` at `0x18002b643`
- `ntdll!RtlEnterCriticalSection` at `0x18002b5fb`
- `ntdll!RtlEnterCriticalSection` at `0x18002b5fb`

## string_xrefs

- `0x18002b2d7`: `\System32\`

## pseudocode

```c
__int64 __fastcall SsipVerifyAndLoad(unsigned __int16 *a1, __int64 *a2)
{
  HMODULE Library; // rsi
  __int64 v5; // rdi
  int DllName; // eax
  unsigned int v7; // ebx
  PVOID *v8; // rcx
  WCHAR *Memory; // rax
  WCHAR *v10; // r14
  DWORD EnvironmentVariableW; // eax
  __int64 v12; // rbx
  __int64 v13; // r8
  DWORD LastError; // eax
  __int64 v15; // rax
  int v16; // eax
  _QWORD *v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // r9
  FARPROC ProcAddress; // rax
  bool v21; // zf
  struct _LIST_ENTRY *Flink; // rax
  DWORD v23; // eax
  DWORD v25; // [rsp+20h] [rbp-58h] BYREF
  HLOCAL hMem; // [rsp+28h] [rbp-50h] BYREF
  _BYTE v27[22]; // [rsp+30h] [rbp-48h] BYREF

  Library = 0;
  *(_OWORD *)v27 = *(_OWORD *)L"\\System32\\";
  v5 = 0;
  hMem = 0;
  *(_QWORD *)&v27[14] = *(_QWORD *)L"32\\";
  v25 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    WPP_SF_Z(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, &WPP_57c72a8c831a31d68b40d535909494f1_Traceguids, a1);
  *a2 = 0;
  DllName = SsipGetDllName(a1, &v25, (BYTE **)&hMem);
  v7 = DllName;
  if ( DllName >= 0 )
  {
    Memory = (WCHAR *)DigestAllocateMemory(0x20Au);
    v10 = Memory;
    if ( !Memory )
    {
      v8 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, &WPP_57c72a8c831a31d68b40d535909494f1_Traceguids);
        v8 = (PVOID *)WPP_GLOBAL_Control;
      }
      v7 = -2146893056;
      goto LABEL_54;
    }
    EnvironmentVariableW = GetEnvironmentVariableW(L"SystemRoot", Memory, 0x104u);
    v12 = EnvironmentVariableW;
    _o_wcsncat_s(v10, 261, v27, 259 - EnvironmentVariableW);
    if ( !v25 || v12 + (((unsigned __int64)v25 + 22) >> 1) > 0x104 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, &WPP_57c72a8c831a31d68b40d535909494f1_Traceguids);
      v7 = -1073741634;
      goto LABEL_52;
    }
    _o_wcsncat_s(v10, 261, hMem, (unsigned __int64)v25 >> 1);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, v13, v10);
    Library = LoadLibraryExW(v10, 0, 0);
    if ( !Library )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        LastError = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, &WPP_57c72a8c831a31d68b40d535909494f1_Traceguids, LastError);
      }
      v7 = -1073741515;
      goto LABEL_52;
    }
    v15 = DigestAllocateMemory(0x38u);
    v5 = v15;
    if ( !v15 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, &WPP_57c72a8c831a31d68b40d535909494f1_Traceguids);
      v7 = -2146893056;
      goto LABEL_52;
    }
    *(_OWORD *)v15 = 0;
    *(_OWORD *)(v15 + 16) = 0;
    *(_OWORD *)(v15 + 32) = 0;
    *(_QWORD *)(v15 + 48) = 0;
    *(_DWORD *)(v15 + 20) = 1;
    v16 = UnicodeStringDuplicate(v15 + 24, a1);
    v7 = v16;
    if ( v16 >= 0 )
    {
      ProcAddress = GetProcAddress(Library, "SsiInitialize");
      *(_QWORD *)(v5 + 48) = ProcAddress;
      if ( ProcAddress )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, &WPP_57c72a8c831a31d68b40d535909494f1_Traceguids);
        v21 = l_bSsiInitialized == 0;
        *(_QWORD *)(v5 + 40) = Library;
        if ( v21 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              55,
              &WPP_57c72a8c831a31d68b40d535909494f1_Traceguids,
              3221225701LL);
          Library = 0;
          v7 = -1073741595;
        }
        else
        {
          RtlEnterCriticalSection(&l_SsiCritSect);
          Flink = l_SsiProviderList.Flink;
          if ( l_SsiProviderList.Flink->Blink != &l_SsiProviderList )
            __fastfail(3u);
          *(_QWORD *)(v5 + 8) = &l_SsiProviderList;
          *(_QWORD *)v5 = Flink;
          Flink->Blink = (struct _LIST_ENTRY *)v5;
          l_SsiProviderList.Flink = (struct _LIST_ENTRY *)v5;
          *(_DWORD *)(v5 + 16) = 1;
          *(_DWORD *)(v5 + 20) = 0;
          RtlLeaveCriticalSection(&l_SsiCritSect);
          *a2 = v5;
          Library = 0;
          v5 = 0;
          v7 = 0;
        }
        goto LABEL_52;
      }
      v7 = -1073741515;
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
LABEL_52:
        DigestFreeMemory(v10);
        goto LABEL_53;
      }
      v18 = 53;
      v19 = 3221225781LL;
    }
    else
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_52;
      v18 = 52;
      v19 = (unsigned int)v16;
    }
    WPP_SF_d(v17[2], v18, &WPP_57c72a8c831a31d68b40d535909494f1_Traceguids, v19);
    goto LABEL_52;
  }
  v8 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      45,
      &WPP_57c72a8c831a31d68b40d535909494f1_Traceguids,
      (unsigned int)DllName);
LABEL_53:
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_54:
  if ( hMem )
  {
    DigestFreeMemory(hMem);
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v5 )
  {
    if ( (int)SsipProviderFree((HLOCAL)v5) >= 0 )
    {
LABEL_61:
      v8 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_62;
    }
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, &WPP_57c72a8c831a31d68b40d535909494f1_Traceguids, v7);
      goto LABEL_61;
    }
  }
LABEL_62:
  if ( Library )
  {
    if ( FreeLibrary(Library) )
    {
      v8 = (PVOID *)WPP_GLOBAL_Control;
    }
    else
    {
      v8 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v23 = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, &WPP_57c72a8c831a31d68b40d535909494f1_Traceguids, v23);
        v8 = (PVOID *)WPP_GLOBAL_Control;
      }
      v7 = -1073741595;
    }
  }
  if ( v8 != &WPP_GLOBAL_Control && *((char *)v8 + 28) < 0 )
    WPP_SF_d(v8[2], 58, &WPP_57c72a8c831a31d68b40d535909494f1_Traceguids, v7);
  return v7;
}

```

## disassembly

```asm
0x18002b2b8  mov     [rsp+arg_10], rbx
0x18002b2bd  push    rbp
0x18002b2be  push    rsi
0x18002b2bf  push    rdi
0x18002b2c0  push    r14
0x18002b2c2  push    r15
0x18002b2c4  sub     rsp, 50h
0x18002b2c8  mov     rax, cs:__security_cookie
0x18002b2cf  xor     rax, rsp
0x18002b2d2  mov     [rsp+78h+var_30], rax
0x18002b2d7  movups  xmm0, xmmword ptr cs:aSystem32; "\\System32\\"
0x18002b2de  xor     esi, esi
0x18002b2e0  mov     r15, rdx
0x18002b2e3  movsd   xmm1, qword ptr cs:aSystem32+0Eh; "32\\"
0x18002b2eb  mov     rbp, rcx
0x18002b2ee  movups  xmmword ptr [rsp+78h+var_48], xmm0
0x18002b2f3  xor     edi, edi
0x18002b2f5  mov     [rsp+78h+hMem], rsi
0x18002b2fa  movsd   qword ptr [rsp+78h+var_48+0Eh], xmm1
0x18002b300  mov     [rsp+78h+var_58], esi
0x18002b304  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b30b  lea     r14, WPP_GLOBAL_Control
0x18002b312  cmp     rcx, r14
0x18002b315  jz      short loc_18002B333
0x18002b317  test    byte ptr [rcx+1Ch], 80h
0x18002b31b  jz      short loc_18002B333
0x18002b31d  mov     rcx, [rcx+10h]
0x18002b321  lea     edx, [rsi+2Ch]
0x18002b324  mov     r9, rbp
0x18002b327  lea     r8, WPP_57c72a8c831a31d68b40d535909494f1_Traceguids
0x18002b32e  call    WPP_SF_Z
0x18002b333  lea     r8, [rsp+78h+hMem]
0x18002b338  mov     [r15], rsi
0x18002b33b  lea     rdx, [rsp+78h+var_58]
0x18002b340  mov     rcx, rbp
0x18002b343  call    SsipGetDllName
0x18002b348  mov     ebx, eax
0x18002b34a  test    eax, eax
0x18002b34c  jns     short loc_18002B385
0x18002b34e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b355  cmp     rcx, r14
0x18002b358  jz      loc_18002B6D3
0x18002b35e  test    byte ptr [rcx+1Ch], 1
0x18002b362  jz      loc_18002B6D3
0x18002b368  mov     rcx, [rcx+10h]
0x18002b36c  lea     r8, WPP_57c72a8c831a31d68b40d535909494f1_Traceguids
0x18002b373  mov     edx, 2Dh ; '-'
0x18002b378  mov     r9d, eax
0x18002b37b  call    WPP_SF_d
0x18002b380  jmp     loc_18002B6CC
0x18002b385  mov     ecx, 20Ah; Size
0x18002b38a  call    DigestAllocateMemory
0x18002b38f  mov     r14, rax
0x18002b392  test    rax, rax
0x18002b395  jnz     short loc_18002B3D4
0x18002b397  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b39e  lea     r14, WPP_GLOBAL_Control
0x18002b3a5  cmp     rcx, r14
0x18002b3a8  jz      short loc_18002B3CA
0x18002b3aa  test    byte ptr [rcx+1Ch], 1
0x18002b3ae  jz      short loc_18002B3CA
0x18002b3b0  mov     rcx, [rcx+10h]
0x18002b3b4  lea     edx, [rax+2Eh]
0x18002b3b7  lea     r8, WPP_57c72a8c831a31d68b40d535909494f1_Traceguids
0x18002b3be  call    WPP_SF_
0x18002b3c3  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b3ca  mov     ebx, 80090300h
0x18002b3cf  jmp     loc_18002B6D3
0x18002b3d4  mov     r8d, 104h; nSize
0x18002b3da  lea     rcx, Name; "SystemRoot"
0x18002b3e1  mov     rdx, r14; lpBuffer
0x18002b3e4  call    cs:__imp_GetEnvironmentVariableW
0x18002b3ea  mov     r9d, 103h
0x18002b3f0  lea     r8, [rsp+78h+var_48]
0x18002b3f5  sub     r9d, eax
0x18002b3f8  mov     ebx, eax
0x18002b3fa  mov     edx, 105h
0x18002b3ff  mov     rcx, r14
0x18002b402  call    cs:__imp__o_wcsncat_s
0x18002b408  mov     eax, [rsp+78h+var_58]
0x18002b40c  test    eax, eax
0x18002b40e  jz      loc_18002B68A
0x18002b414  lea     rcx, [rax+16h]
0x18002b418  mov     r9d, eax
0x18002b41b  shr     rcx, 1
0x18002b41e  add     rcx, rbx
0x18002b421  cmp     rcx, 104h
0x18002b428  ja      loc_18002B68A
0x18002b42e  mov     r8, [rsp+78h+hMem]
0x18002b433  mov     edx, 105h
0x18002b438  shr     r9, 1
0x18002b43b  mov     rcx, r14
0x18002b43e  call    cs:__imp__o_wcsncat_s
0x18002b444  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b44b  lea     rbx, WPP_GLOBAL_Control
0x18002b452  cmp     rcx, rbx
0x18002b455  jz      short loc_18002B46E
0x18002b457  test    byte ptr [rcx+1Ch], 4
0x18002b45b  jz      short loc_18002B46E
0x18002b45d  mov     rcx, [rcx+10h]
0x18002b461  mov     edx, 30h ; '0'
0x18002b466  mov     r9, r14
0x18002b469  call    WPP_SF_S
0x18002b46e  xor     r8d, r8d; dwFlags
0x18002b471  xor     edx, edx; hFile
0x18002b473  mov     rcx, r14; lpLibFileName
0x18002b476  call    cs:__imp_LoadLibraryExW
0x18002b47c  mov     rsi, rax
0x18002b47f  test    rax, rax
0x18002b482  jnz     short loc_18002B4C3
0x18002b484  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b48b  cmp     rcx, rbx
0x18002b48e  jz      short loc_18002B4B9
0x18002b490  test    byte ptr [rcx+1Ch], 1
0x18002b494  jz      short loc_18002B4B9
0x18002b496  call    cs:__imp_GetLastError
0x18002b49c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b4a3  lea     edx, [rsi+31h]
0x18002b4a6  mov     r9d, eax
0x18002b4a9  lea     r8, WPP_57c72a8c831a31d68b40d535909494f1_Traceguids
0x18002b4b0  mov     rcx, [rcx+10h]
0x18002b4b4  call    WPP_SF_d
0x18002b4b9  mov     ebx, 0C0000135h
0x18002b4be  jmp     loc_18002B6BD
0x18002b4c3  mov     ecx, 38h ; '8'; Size
0x18002b4c8  call    DigestAllocateMemory
0x18002b4cd  mov     rdi, rax
0x18002b4d0  test    rax, rax
0x18002b4d3  jnz     short loc_18002B504
0x18002b4d5  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b4dc  cmp     rcx, rbx
0x18002b4df  jz      short loc_18002B4FA
0x18002b4e1  test    byte ptr [rcx+1Ch], 1
0x18002b4e5  jz      short loc_18002B4FA
0x18002b4e7  mov     rcx, [rcx+10h]
0x18002b4eb  lea     edx, [rax+32h]
0x18002b4ee  lea     r8, WPP_57c72a8c831a31d68b40d535909494f1_Traceguids
0x18002b4f5  call    WPP_SF_
0x18002b4fa  mov     ebx, 80090300h
0x18002b4ff  jmp     loc_18002B6BD
0x18002b504  xorps   xmm0, xmm0
0x18002b507  lea     rcx, [rdi+18h]
0x18002b50b  movups  xmmword ptr [rdi], xmm0
0x18002b50e  xor     eax, eax
0x18002b510  mov     rdx, rbp
0x18002b513  movups  xmmword ptr [rdi+10h], xmm0
0x18002b517  movups  xmmword ptr [rdi+20h], xmm0
0x18002b51b  mov     [rdi+30h], rax
0x18002b51f  mov     dword ptr [rdi+14h], 1
0x18002b526  call    UnicodeStringDuplicate
0x18002b52b  mov     ebx, eax
0x18002b52d  test    eax, eax
0x18002b52f  jns     short loc_18002B56F
0x18002b531  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b538  lea     rbp, WPP_GLOBAL_Control
0x18002b53f  cmp     rcx, rbp
0x18002b542  jz      loc_18002B6BD
0x18002b548  test    byte ptr [rcx+1Ch], 1
0x18002b54c  jz      loc_18002B6BD
0x18002b552  mov     edx, 34h ; '4'
0x18002b557  mov     r9d, eax
0x18002b55a  mov     rcx, [rcx+10h]
0x18002b55e  lea     r8, WPP_57c72a8c831a31d68b40d535909494f1_Traceguids
0x18002b565  call    WPP_SF_d
0x18002b56a  jmp     loc_18002B6BD
0x18002b56f  lea     rdx, ProcName; "SsiInitialize"
0x18002b576  mov     rcx, rsi; hModule
0x18002b579  call    cs:__imp_GetProcAddress
0x18002b57f  mov     [rdi+30h], rax
0x18002b583  test    rax, rax
0x18002b586  jnz     short loc_18002B5B9
0x18002b588  mov     ebx, 0C0000135h
0x18002b58d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b594  lea     rbp, WPP_GLOBAL_Control
0x18002b59b  cmp     rcx, rbp
0x18002b59e  jz      loc_18002B6BD
0x18002b5a4  test    byte ptr [rcx+1Ch], 1
0x18002b5a8  jz      loc_18002B6BD
0x18002b5ae  lea     edx, [rax+35h]
0x18002b5b1  mov     r9d, 0C0000135h
0x18002b5b7  jmp     short loc_18002B55A
0x18002b5b9  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b5c0  lea     rbp, WPP_GLOBAL_Control
0x18002b5c7  cmp     rcx, rbp
0x18002b5ca  jz      short loc_18002B5E7
0x18002b5cc  test    byte ptr [rcx+1Ch], 4
0x18002b5d0  jz      short loc_18002B5E7
0x18002b5d2  mov     rcx, [rcx+10h]
0x18002b5d6  lea     r8, WPP_57c72a8c831a31d68b40d535909494f1_Traceguids
0x18002b5dd  mov     edx, 36h ; '6'
0x18002b5e2  call    WPP_SF_
0x18002b5e7  cmp     cs:?l_bSsiInitialized@@3HA, 0; int l_bSsiInitialized
0x18002b5ee  mov     [rdi+28h], rsi
0x18002b5f2  jz      short loc_18002B654
0x18002b5f4  lea     rcx, ?l_SsiCritSect@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18002b5fb  call    cs:__imp_RtlEnterCriticalSection
0x18002b601  mov     rax, cs:?l_SsiProviderList@@3U_LIST_ENTRY@@A; _LIST_ENTRY l_SsiProviderList
0x18002b608  lea     rcx, ?l_SsiProviderList@@3U_LIST_ENTRY@@A; _LIST_ENTRY l_SsiProviderList
0x18002b60f  cmp     [rax+8], rcx
0x18002b613  jz      short loc_18002B61C
0x18002b615  mov     ecx, 3
0x18002b61a  int     29h; Win8: RtlFailFast(ecx)
0x18002b61c  mov     [rdi+8], rcx
0x18002b620  lea     rcx, ?l_SsiCritSect@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18002b627  mov     [rdi], rax
0x18002b62a  mov     [rax+8], rdi
0x18002b62e  mov     cs:?l_SsiProviderList@@3U_LIST_ENTRY@@A, rdi; _LIST_ENTRY l_SsiProviderList
0x18002b635  mov     dword ptr [rdi+10h], 1
0x18002b63c  mov     dword ptr [rdi+14h], 0
0x18002b643  call    cs:__imp_RtlLeaveCriticalSection
0x18002b649  mov     [r15], rdi
0x18002b64c  xor     esi, esi
0x18002b64e  xor     edi, edi
0x18002b650  xor     ebx, ebx
0x18002b652  jmp     short loc_18002B6BD
0x18002b654  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b65b  cmp     rcx, rbp
0x18002b65e  jz      short loc_18002B681
0x18002b660  test    byte ptr [rcx+1Ch], 1
0x18002b664  jz      short loc_18002B681
0x18002b666  mov     rcx, [rcx+10h]
0x18002b66a  lea     r8, WPP_57c72a8c831a31d68b40d535909494f1_Traceguids
0x18002b671  mov     edx, 37h ; '7'
0x18002b676  mov     r9d, 0C00000E5h
0x18002b67c  call    WPP_SF_d
0x18002b681  xor     esi, esi
0x18002b683  mov     ebx, 0C00000E5h
0x18002b688  jmp     short loc_18002B6BD
0x18002b68a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b691  lea     rbp, WPP_GLOBAL_Control
0x18002b698  cmp     rcx, rbp
0x18002b69b  jz      short loc_18002B6B8
0x18002b69d  test    byte ptr [rcx+1Ch], 1
0x18002b6a1  jz      short loc_18002B6B8
0x18002b6a3  mov     rcx, [rcx+10h]
0x18002b6a7  lea     r8, WPP_57c72a8c831a31d68b40d535909494f1_Traceguids
0x18002b6ae  mov     edx, 2Fh ; '/'
0x18002b6b3  call    WPP_SF_
0x18002b6b8  mov     ebx, 0C00000BEh
0x18002b6bd  mov     rcx, r14; hMem
0x18002b6c0  call    DigestFreeMemory
0x18002b6c5  lea     r14, WPP_GLOBAL_Control
0x18002b6cc  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b6d3  cmp     [rsp+78h+hMem], 0
0x18002b6d9  jz      short loc_18002B6EC
0x18002b6db  mov     rcx, [rsp+78h+hMem]; hMem
0x18002b6e0  call    DigestFreeMemory
0x18002b6e5  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b6ec  test    rdi, rdi
0x18002b6ef  jz      short loc_18002B72E
0x18002b6f1  mov     rcx, rdi; hMem
0x18002b6f4  call    SsipProviderFree
0x18002b6f9  test    eax, eax
0x18002b6fb  jns     short loc_18002B727
0x18002b6fd  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b704  cmp     rcx, r14
0x18002b707  jz      short loc_18002B72E
0x18002b709  test    byte ptr [rcx+1Ch], 1
0x18002b70d  jz      short loc_18002B72E
0x18002b70f  mov     rcx, [rcx+10h]
0x18002b713  lea     r8, WPP_57c72a8c831a31d68b40d535909494f1_Traceguids
0x18002b71a  mov     edx, 38h ; '8'
0x18002b71f  mov     r9d, ebx
0x18002b722  call    WPP_SF_d
0x18002b727  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b72e  test    rsi, rsi
0x18002b731  jz      short loc_18002B78C
0x18002b733  mov     rcx, rsi; hLibModule
0x18002b736  call    cs:__imp_FreeLibrary
0x18002b73c  test    eax, eax
0x18002b73e  jnz     short loc_18002B785
0x18002b740  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b747  cmp     rcx, r14
0x18002b74a  jz      short loc_18002B77E
0x18002b74c  test    byte ptr [rcx+1Ch], 1
0x18002b750  jz      short loc_18002B77E
0x18002b752  call    cs:__imp_GetLastError
0x18002b758  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b75f  lea     r8, WPP_57c72a8c831a31d68b40d535909494f1_Traceguids
0x18002b766  mov     edx, 39h ; '9'
0x18002b76b  mov     r9d, eax
0x18002b76e  mov     rcx, [rcx+10h]
0x18002b772  call    WPP_SF_d
0x18002b777  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b77e  mov     ebx, 0C00000E5h
0x18002b783  jmp     short loc_18002B78C
0x18002b785  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b78c  cmp     rcx, r14
0x18002b78f  jz      short loc_18002B7AF
0x18002b791  test    byte ptr [rcx+1Ch], 80h
0x18002b795  jz      short loc_18002B7AF
0x18002b797  mov     rcx, [rcx+10h]
0x18002b79b  lea     r8, WPP_57c72a8c831a31d68b40d535909494f1_Traceguids
0x18002b7a2  mov     edx, 3Ah ; ':'
0x18002b7a7  mov     r9d, ebx
0x18002b7aa  call    WPP_SF_d
0x18002b7af  mov     eax, ebx
0x18002b7b1  mov     rcx, [rsp+78h+var_30]
0x18002b7b6  xor     rcx, rsp; StackCookie
0x18002b7b9  call    __security_check_cookie
  ... truncated ...
```
