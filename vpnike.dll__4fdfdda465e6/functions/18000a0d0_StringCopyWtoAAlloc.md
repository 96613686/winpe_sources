# StringCopyWtoAAlloc

- ea: `0x18000a0d0`
- end: `0x18000a338`
- name: `StringCopyWtoAAlloc`
- size: `616`
- prototype: `__int64 __fastcall(LPCWCH lpWideCharStr)`
- caller_count: `3`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180042ad8`
- `0x1800435d0`
- `0x18005fa48`

## callees

- `0x180007590`
- `0x180007794`
- `0x1800077bc`
- `0x18000a0d0`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a2ba`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a2ba`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a1ec`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a1ec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a1d9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a2ac`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a1d9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a2ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a185`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a256`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a185`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a256`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000a178`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000a24c`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000a178`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000a24c`

## string_xrefs

- `0x18000a207`: `StringCopyWtoAAlloc: Failed to allocate memory.`

## pseudocode

```c
__int64 __fastcall StringCopyWtoAAlloc(LPCWCH lpWideCharStr, __int64 a2, CHAR **a3, int *a4)
{
  int v7; // eax
  SIZE_T cbMultiByte; // rsi
  DWORD v9; // eax
  DWORD LastError; // ebx
  CHAR *v11; // rdi
  HANDLE ProcessHeap; // rax
  CHAR *lpMultiByteStr; // rax
  int v14; // eax
  HANDLE v15; // rax
  int v17; // [rsp+50h] [rbp-838h] BYREF
  char v18[2044]; // [rsp+54h] [rbp-834h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, &WPP_91d98fef5f143f5b96f1a3fcbe8f5039_Traceguids);
  }
  v17 = 0;
  memset_0(v18, 0, sizeof(v18));
  v7 = WideCharToMultiByte(0, 0, lpWideCharStr, -1, 0, 0, 0, 0);
  cbMultiByte = v7;
  if ( v7 > 0 )
  {
    ProcessHeap = GetProcessHeap();
    LastError = 8;
    lpMultiByteStr = (CHAR *)HeapAlloc(ProcessHeap, 8u, cbMultiByte);
    v11 = lpMultiByteStr;
    if ( !lpMultiByteStr )
    {
      if ( (byte_1800AA941 & 4) != 0 )
        McTemplateU0z_EventWriteTransfer(
          &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          RasVpnIkeTraceError,
          L"StringCopyWtoAAlloc: Failed to allocate memory.");
      goto LABEL_20;
    }
    v14 = WideCharToMultiByte(0, 0, lpWideCharStr, -1, lpMultiByteStr, cbMultiByte, 0, 0);
    if ( v14 > 0 )
    {
      *a3 = v11;
      LastError = 0;
      *a4 = v14;
      goto LABEL_22;
    }
    LastError = GetLastError();
    if ( (byte_1800AA941 & 4) != 0 )
    {
      LOWORD(v17) = 0;
      FormatRRASErrorString(&v17, L"WideCharToMultiByte failed: %d", LastError);
      if ( (byte_1800AA941 & 4) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceError, &v17);
    }
  }
  else
  {
    v9 = GetLastError();
    LastError = v9;
    if ( (byte_1800AA941 & 4) != 0 )
    {
      LOWORD(v17) = 0;
      FormatRRASErrorString(&v17, L"WideCharToMultiByte failed: %d", v9);
      if ( (byte_1800AA941 & 4) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceError, &v17);
    }
    v11 = 0;
  }
  if ( LastError )
  {
    if ( v11 )
    {
      v15 = GetProcessHeap();
      HeapFree(v15, 0, v11);
    }
LABEL_20:
    *a3 = 0;
    *a4 = 0;
  }
LABEL_22:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_91d98fef5f143f5b96f1a3fcbe8f5039_Traceguids, LastError);
  }
  return LastError;
}

```

## disassembly

```asm
0x18000a0d0  mov     [rsp+arg_8], rbx
0x18000a0d5  push    rbp
0x18000a0d6  push    rsi
0x18000a0d7  push    rdi
0x18000a0d8  push    r14
0x18000a0da  push    r15
0x18000a0dc  sub     rsp, 860h
0x18000a0e3  mov     rax, cs:__security_cookie
0x18000a0ea  xor     rax, rsp
0x18000a0ed  mov     [rsp+888h+var_38], rax
0x18000a0f5  mov     r15, r9
0x18000a0f8  mov     r14, r8
0x18000a0fb  mov     rbp, rcx
0x18000a0fe  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a105  lea     rax, WPP_GLOBAL_Control
0x18000a10c  cmp     rcx, rax
0x18000a10f  jz      short loc_18000A132
0x18000a111  test    byte ptr [rcx+1Ch], 1
0x18000a115  jz      short loc_18000A132
0x18000a117  cmp     byte ptr [rcx+19h], 6
0x18000a11b  jb      short loc_18000A132
0x18000a11d  mov     rcx, [rcx+10h]
0x18000a121  lea     r8, WPP_91d98fef5f143f5b96f1a3fcbe8f5039_Traceguids
0x18000a128  mov     edx, 1Bh
0x18000a12d  call    WPP_SF_
0x18000a132  xor     eax, eax
0x18000a134  lea     rcx, [rsp+888h+var_834]; void *
0x18000a139  xor     edx, edx; Val
0x18000a13b  mov     [rsp+888h+var_838], eax
0x18000a13f  mov     r8d, 7FCh; Size
0x18000a145  call    memset_0
0x18000a14a  mov     [rsp+888h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x18000a153  or      r9d, 0FFFFFFFFh; cchWideChar
0x18000a157  mov     [rsp+888h+lpDefaultChar], 0; lpDefaultChar
0x18000a160  mov     r8, rbp; lpWideCharStr
0x18000a163  mov     [rsp+888h+cbMultiByte], 0; cbMultiByte
0x18000a16b  xor     edx, edx; dwFlags
0x18000a16d  xor     ecx, ecx; CodePage
0x18000a16f  mov     [rsp+888h+lpMultiByteStr], 0; lpMultiByteStr
0x18000a178  call    cs:__imp_WideCharToMultiByte
0x18000a17e  movsxd  rsi, eax
0x18000a181  test    eax, eax
0x18000a183  jg      short loc_18000A1D9
0x18000a185  call    cs:__imp_GetLastError
0x18000a18b  test    cs:byte_1800AA941, 4
0x18000a192  mov     ebx, eax
0x18000a194  jz      short loc_18000A1D2
0x18000a196  xor     ecx, ecx
0x18000a198  lea     rdx, aWidechartomult; "WideCharToMultiByte failed: %d"
0x18000a19f  mov     word ptr [rsp+888h+var_838], cx
0x18000a1a4  mov     r8d, eax
0x18000a1a7  lea     rcx, [rsp+888h+var_838]
0x18000a1ac  call    FormatRRASErrorString
0x18000a1b1  test    cs:byte_1800AA941, 4
0x18000a1b8  jz      short loc_18000A1D2
0x18000a1ba  lea     r8, [rsp+888h+var_838]
0x18000a1bf  lea     rdx, RasVpnIkeTraceError
0x18000a1c6  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000a1cd  call    McTemplateU0z_EventWriteTransfer
0x18000a1d2  xor     edi, edi
0x18000a1d4  jmp     loc_18000A2A3
0x18000a1d9  call    cs:__imp_GetProcessHeap
0x18000a1df  mov     ebx, 8
0x18000a1e4  mov     r8, rsi; dwBytes
0x18000a1e7  mov     rcx, rax; hHeap
0x18000a1ea  mov     edx, ebx; dwFlags
0x18000a1ec  call    cs:__imp_HeapAlloc
0x18000a1f2  mov     rdi, rax
0x18000a1f5  test    rax, rax
0x18000a1f8  jnz     short loc_18000A226
0x18000a1fa  test    cs:byte_1800AA941, 4
0x18000a201  jz      loc_18000A2C0
0x18000a207  lea     r8, aStringcopywtoa_0; "StringCopyWtoAAlloc: Failed to allocate"...
0x18000a20e  lea     rdx, RasVpnIkeTraceError
0x18000a215  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000a21c  call    McTemplateU0z_EventWriteTransfer
0x18000a221  jmp     loc_18000A2C0
0x18000a226  mov     [rsp+888h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x18000a22f  or      r9d, 0FFFFFFFFh; cchWideChar
0x18000a233  mov     [rsp+888h+lpDefaultChar], 0; lpDefaultChar
0x18000a23c  mov     r8, rbp; lpWideCharStr
0x18000a23f  mov     [rsp+888h+cbMultiByte], esi; cbMultiByte
0x18000a243  xor     edx, edx; dwFlags
0x18000a245  xor     ecx, ecx; CodePage
0x18000a247  mov     [rsp+888h+lpMultiByteStr], rdi; lpMultiByteStr
0x18000a24c  call    cs:__imp_WideCharToMultiByte
0x18000a252  test    eax, eax
0x18000a254  jg      short loc_18000A2D0
0x18000a256  call    cs:__imp_GetLastError
0x18000a25c  test    cs:byte_1800AA941, 4
0x18000a263  mov     ebx, eax
0x18000a265  jz      short loc_18000A2A3
0x18000a267  xor     eax, eax
0x18000a269  lea     rdx, aWidechartomult; "WideCharToMultiByte failed: %d"
0x18000a270  mov     r8d, ebx
0x18000a273  mov     word ptr [rsp+888h+var_838], ax
0x18000a278  lea     rcx, [rsp+888h+var_838]
0x18000a27d  call    FormatRRASErrorString
0x18000a282  test    cs:byte_1800AA941, 4
0x18000a289  jz      short loc_18000A2A3
0x18000a28b  lea     r8, [rsp+888h+var_838]
0x18000a290  lea     rdx, RasVpnIkeTraceError
0x18000a297  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000a29e  call    McTemplateU0z_EventWriteTransfer
0x18000a2a3  test    ebx, ebx
0x18000a2a5  jz      short loc_18000A2D8
0x18000a2a7  test    rdi, rdi
0x18000a2aa  jz      short loc_18000A2C0
0x18000a2ac  call    cs:__imp_GetProcessHeap
0x18000a2b2  mov     r8, rdi; lpMem
0x18000a2b5  xor     edx, edx; dwFlags
0x18000a2b7  mov     rcx, rax; hHeap
0x18000a2ba  call    cs:__imp_HeapFree
0x18000a2c0  mov     qword ptr [r14], 0
0x18000a2c7  mov     dword ptr [r15], 0
0x18000a2ce  jmp     short loc_18000A2D8
0x18000a2d0  mov     [r14], rdi
0x18000a2d3  xor     ebx, ebx
0x18000a2d5  mov     [r15], eax
0x18000a2d8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a2df  lea     rax, WPP_GLOBAL_Control
0x18000a2e6  cmp     rcx, rax
0x18000a2e9  jz      short loc_18000A30F
0x18000a2eb  test    byte ptr [rcx+1Ch], 1
0x18000a2ef  jz      short loc_18000A30F
0x18000a2f1  cmp     byte ptr [rcx+19h], 6
0x18000a2f5  jb      short loc_18000A30F
0x18000a2f7  mov     rcx, [rcx+10h]
0x18000a2fb  lea     r8, WPP_91d98fef5f143f5b96f1a3fcbe8f5039_Traceguids
0x18000a302  mov     edx, 1Ch
0x18000a307  mov     r9d, ebx
0x18000a30a  call    WPP_SF_d
0x18000a30f  mov     eax, ebx
0x18000a311  mov     rcx, [rsp+888h+var_38]
0x18000a319  xor     rcx, rsp; StackCookie
0x18000a31c  call    __security_check_cookie
0x18000a321  mov     rbx, [rsp+888h+arg_8]
0x18000a329  add     rsp, 860h
0x18000a330  pop     r15
0x18000a332  pop     r14
0x18000a334  pop     rdi
0x18000a335  pop     rsi
0x18000a336  pop     rbp
0x18000a337  retn
```
