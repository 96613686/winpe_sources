# UpdateTraceFLagsOnManagedInstance(void)

- ea: `0x100424980`
- end: `0x100424c47`
- name: `?UpdateTraceFLagsOnManagedInstance@@YAXXZ`
- size: `711`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x100416770`

## callees

- `0x100424980`
- `0x100436610`

## import_xrefs

- `KERNEL32!HeapFree` at `0x100424aba`
- `KERNEL32!HeapFree` at `0x100424b34`
- `KERNEL32!HeapFree` at `0x100424c2f`
- `KERNEL32!HeapFree` at `0x100424aba`
- `KERNEL32!HeapFree` at `0x100424b34`
- `KERNEL32!HeapFree` at `0x100424c2f`
- `KERNEL32!GetProcessHeap` at `0x100424a1a`
- `KERNEL32!GetProcessHeap` at `0x100424aac`
- `KERNEL32!GetProcessHeap` at `0x100424ad0`
- `KERNEL32!GetProcessHeap` at `0x100424b26`
- `KERNEL32!GetProcessHeap` at `0x100424c21`
- `KERNEL32!GetProcessHeap` at `0x100424a1a`
- `KERNEL32!GetProcessHeap` at `0x100424aac`
- `KERNEL32!GetProcessHeap` at `0x100424ad0`
- `KERNEL32!GetProcessHeap` at `0x100424b26`
- `KERNEL32!GetProcessHeap` at `0x100424c21`
- `KERNEL32!HeapAlloc` at `0x100424a2b`
- `KERNEL32!HeapAlloc` at `0x100424ae2`
- `KERNEL32!HeapAlloc` at `0x100424a2b`
- `KERNEL32!HeapAlloc` at `0x100424ae2`
- `sqlmin!?FireXEventForTraceFlags@@YAXPEB_WHW4FlagScope@CGlobalTraceFlags@@00@Z` at `0x100424bf9`
- `sqlmin!?FireXEventForTraceFlags@@YAXPEB_WHW4FlagScope@CGlobalTraceFlags@@00@Z` at `0x100424bf9`
- `sqlmin!GetXdbServerGlobals` at `0x100424996`
- `sqlmin!GetXdbServerGlobals` at `0x100424996`
- `sqldk!?UtilDbccTraceOn@@YA_NKFW4FlagScope@CGlobalTraceFlags@@W4FlagUsage@2@@Z` at `0x100424bb9`
- `sqldk!?UtilDbccTraceOn@@YA_NKFW4FlagScope@CGlobalTraceFlags@@W4FlagUsage@2@@Z` at `0x100424bb9`
- `api-ms-win-crt-string-l1-1-0!wcstok_s` at `0x100424b67`
- `api-ms-win-crt-string-l1-1-0!wcstok_s` at `0x100424c0d`
- `api-ms-win-crt-string-l1-1-0!wcstok_s` at `0x100424b67`
- `api-ms-win-crt-string-l1-1-0!wcstok_s` at `0x100424c0d`
- `api-ms-win-crt-convert-l1-1-0!wcstol` at `0x100424b99`
- `api-ms-win-crt-convert-l1-1-0!wcstol` at `0x100424b99`
- `hostregdll!HostReg_GetPropertyValueAsBinary` at `0x1004249ff`
- `hostregdll!HostReg_GetPropertyValueAsBinary` at `0x100424a86`
- `hostregdll!HostReg_GetPropertyValueAsBinary` at `0x1004249ff`
- `hostregdll!HostReg_GetPropertyValueAsBinary` at `0x100424a86`
- `hostregdll!HostReg_GetApplicationName` at `0x1004249c4`
- `hostregdll!HostReg_GetApplicationName` at `0x100424a4c`
- `hostregdll!HostReg_GetApplicationName` at `0x1004249c4`
- `hostregdll!HostReg_GetApplicationName` at `0x100424a4c`

## string_xrefs

- `0x100424b84`: `Wrong trace flag number read from winfab property during startup.`
- `0x100424bbf`: `Unable to set trace flag during startup. Check trace flag number and usage.`
- `0x100424b76`: `Trace flags is set during startup`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall UpdateTraceFLagsOnManagedInstance(__int64 a1, __int64 a2)
{
  int ApplicationName; // edi
  SIZE_T v3; // rbp
  wchar_t *v4; // rbx
  HANDLE ProcessHeap; // rax
  void *v6; // rsi
  HANDLE v7; // rax
  __int64 v8; // rbx
  HANDLE v9; // rax
  wchar_t *v10; // rax
  HANDLE v11; // rax
  wchar_t *i; // rax
  unsigned int v13; // eax
  unsigned int v14; // edi
  char v15; // al
  const wchar_t *v16; // rcx
  const wchar_t *v17; // r9
  HANDLE v18; // rax
  wchar_t *Context[11]; // [rsp+40h] [rbp-58h] BYREF
  SIZE_T dwBytes; // [rsp+A0h] [rbp+8h] BYREF
  void *v21; // [rsp+A8h] [rbp+10h]
  __int64 v22; // [rsp+B0h] [rbp+18h] BYREF
  __int64 v23; // [rsp+B8h] [rbp+20h] BYREF

  Context[2] = (wchar_t *)-2LL;
  if ( !*(_DWORD *)(GetXdbServerGlobals(a1, a2) + 11996) )
    return;
  LODWORD(dwBytes) = 0;
  v22 = 0;
  ApplicationName = HostReg_GetApplicationName(&v22);
  if ( ApplicationName >= 0 )
    ApplicationName = HostReg_GetPropertyValueAsBinary(v22, L"TraceFlags", 20000, 0, 0, &dwBytes, 0);
  v3 = (unsigned int)dwBytes;
  if ( (_DWORD)dwBytes )
  {
    ProcessHeap = GetProcessHeap();
    v6 = HeapAlloc(ProcessHeap, 8u, v3);
    v21 = v6;
    v23 = 0;
    ApplicationName = HostReg_GetApplicationName(&v23);
    if ( ApplicationName >= 0 )
      ApplicationName = HostReg_GetPropertyValueAsBinary(v23, L"TraceFlags", 20000, 0, v3, &dwBytes, v6);
    if ( (_DWORD)dwBytes )
    {
      if ( ApplicationName >= 0 )
      {
        v8 = (unsigned int)dwBytes;
        v9 = GetProcessHeap();
        v10 = (wchar_t *)HeapAlloc(v9, 8u, v8 + 2);
        v4 = v10;
        if ( v10 )
        {
          _mm_lfence();
          memcpy_s(v10, (unsigned int)dwBytes, v6, (unsigned int)dwBytes);
          v4[(unsigned __int64)(unsigned int)dwBytes >> 1] = 0;
          if ( v6 )
          {
            _mm_lfence();
            v11 = GetProcessHeap();
            HeapFree(v11, 0, v6);
            v21 = 0;
          }
          goto LABEL_18;
        }
        ApplicationName = -2147024882;
      }
    }
    else
    {
      ApplicationName = -2147467259;
    }
    if ( v6 )
    {
      _mm_lfence();
      v7 = GetProcessHeap();
      HeapFree(v7, 0, v6);
      v21 = 0;
    }
    v4 = 0;
  }
  else
  {
    v4 = 0;
  }
LABEL_18:
  Context[1] = v4;
  if ( !ApplicationName )
  {
    if ( v4 )
    {
      for ( i = wcstok_s(v4, L",", Context); i; i = wcstok_s(0, L",", Context) )
      {
        v13 = wcstol(i, 0, 10);
        v14 = v13;
        if ( v13 > 0x3BC3 )
        {
          FireXEventForTraceFlags(
            L"TRACEON",
            v13,
            0xFFFFFFFFLL,
            L"ERROR",
            L"Wrong trace flag number read from winfab property during startup.");
        }
        else
        {
          _mm_lfence();
          v15 = UtilDbccTraceOn(v13, 0, 0xFFFFFFFFLL, 2);
          v16 = L"Unable to set trace flag during startup. Check trace flag number and usage.";
          if ( v15 )
            v16 = L"Trace flags is set during startup";
          v17 = L"ERROR";
          if ( v15 )
            v17 = L"SUCCESS";
          FireXEventForTraceFlags(L"TRACEON", v14, 0xFFFFFFFFLL, v17, v16);
        }
      }
    }
  }
  if ( v4 )
  {
    v18 = GetProcessHeap();
    HeapFree(v18, 0, v4);
  }
}

```

## disassembly

```asm
0x100424980  push    rbx
0x100424982  push    rbp
0x100424983  push    rsi
0x100424984  push    rdi
0x100424985  push    r14
0x100424987  push    r15
0x100424989  sub     rsp, 68h
0x10042498d  mov     [rsp+98h+var_48], 0FFFFFFFFFFFFFFFEh
0x100424996  call    cs:__imp_GetXdbServerGlobals
0x10042499c  cmp     dword ptr [rax+2EDCh], 0
0x1004249a3  jz      loc_100424C3A
0x1004249a9  xor     r14d, r14d
0x1004249ac  mov     dword ptr [rsp+98h+dwBytes], r14d
0x1004249b4  mov     [rsp+98h+arg_10], r14
0x1004249bc  lea     rcx, [rsp+98h+arg_10]
0x1004249c4  call    cs:__imp_HostReg_GetApplicationName
0x1004249ca  mov     edi, eax
0x1004249cc  test    eax, eax
0x1004249ce  js      short loc_100424A07
0x1004249d0  mov     [rsp+98h+var_68], r14
0x1004249d5  lea     rax, [rsp+98h+dwBytes]
0x1004249dd  mov     [rsp+98h+var_70], rax
0x1004249e2  mov     dword ptr [rsp+98h+var_78], r14d
0x1004249e7  xor     r9d, r9d
0x1004249ea  mov     r8d, 4E20h
0x1004249f0  lea     rdx, aTraceflags; "TraceFlags"
0x1004249f7  mov     rcx, [rsp+98h+arg_10]
0x1004249ff  call    cs:__imp_HostReg_GetPropertyValueAsBinary
0x100424a05  mov     edi, eax
0x100424a07  mov     ebp, dword ptr [rsp+98h+dwBytes]
0x100424a0e  test    ebp, ebp
0x100424a10  jnz     short loc_100424A1A
0x100424a12  mov     rbx, r14
0x100424a15  jmp     loc_100424B42
0x100424a1a  call    cs:__imp_GetProcessHeap
0x100424a20  mov     rcx, rax; hHeap
0x100424a23  mov     r8, rbp; dwBytes
0x100424a26  mov     edx, 8; dwFlags
0x100424a2b  call    cs:__imp_HeapAlloc
0x100424a31  mov     rsi, rax
0x100424a34  mov     [rsp+98h+arg_8], rax
0x100424a3c  mov     [rsp+98h+arg_18], r14
0x100424a44  lea     rcx, [rsp+98h+arg_18]
0x100424a4c  call    cs:__imp_HostReg_GetApplicationName
0x100424a52  mov     edi, eax
0x100424a54  test    eax, eax
0x100424a56  js      short loc_100424A8E
0x100424a58  mov     [rsp+98h+var_68], rsi
0x100424a5d  lea     rax, [rsp+98h+dwBytes]
0x100424a65  mov     [rsp+98h+var_70], rax
0x100424a6a  mov     dword ptr [rsp+98h+var_78], ebp
0x100424a6e  xor     r9d, r9d
0x100424a71  mov     r8d, 4E20h
0x100424a77  lea     rdx, aTraceflags; "TraceFlags"
0x100424a7e  mov     rcx, [rsp+98h+arg_18]
0x100424a86  call    cs:__imp_HostReg_GetPropertyValueAsBinary
0x100424a8c  mov     edi, eax
0x100424a8e  mov     eax, dword ptr [rsp+98h+dwBytes]
0x100424a95  test    eax, eax
0x100424a97  jnz     short loc_100424AA0
0x100424a99  mov     edi, 80004005h
0x100424a9e  jmp     short loc_100424AA4
0x100424aa0  test    edi, edi
0x100424aa2  jns     short loc_100424ACD
0x100424aa4  test    rsi, rsi
0x100424aa7  jz      short loc_100424AC8
0x100424aa9  lfence
0x100424aac  call    cs:__imp_GetProcessHeap
0x100424ab2  mov     rcx, rax; hHeap
0x100424ab5  mov     r8, rsi; lpMem
0x100424ab8  xor     edx, edx; dwFlags
0x100424aba  call    cs:__imp_HeapFree
0x100424ac0  mov     [rsp+98h+arg_8], r14
0x100424ac8  mov     rbx, r14
0x100424acb  jmp     short loc_100424B42
0x100424acd  mov     rbx, rax
0x100424ad0  call    cs:__imp_GetProcessHeap
0x100424ad6  mov     rcx, rax; hHeap
0x100424ad9  lea     r8, [rbx+2]; dwBytes
0x100424add  mov     edx, 8; dwFlags
0x100424ae2  call    cs:__imp_HeapAlloc
0x100424ae8  mov     rbx, rax
0x100424aeb  test    rax, rax
0x100424aee  jnz     short loc_100424AF7
0x100424af0  mov     edi, 8007000Eh
0x100424af5  jmp     short loc_100424AA4
0x100424af7  lfence
0x100424afa  mov     edx, dword ptr [rsp+98h+dwBytes]; DestinationSize
0x100424b01  mov     r9d, edx; SourceSize
0x100424b04  mov     r8, rsi; Source
0x100424b07  mov     rcx, rbx; Destination
0x100424b0a  call    memcpy_s
0x100424b0f  mov     eax, dword ptr [rsp+98h+dwBytes]
0x100424b16  shr     rax, 1
0x100424b19  mov     [rbx+rax*2], r14w
0x100424b1e  test    rsi, rsi
0x100424b21  jz      short loc_100424B42
0x100424b23  lfence
0x100424b26  call    cs:__imp_GetProcessHeap
0x100424b2c  mov     rcx, rax; hHeap
0x100424b2f  mov     r8, rsi; lpMem
0x100424b32  xor     edx, edx; dwFlags
0x100424b34  call    cs:__imp_HeapFree
0x100424b3a  mov     [rsp+98h+arg_8], r14
0x100424b42  mov     [rsp+98h+var_50], rbx
0x100424b47  test    edi, edi
0x100424b49  jnz     loc_100424C1C
0x100424b4f  test    rbx, rbx
0x100424b52  jz      loc_100424C1C
0x100424b58  lea     r8, [rsp+98h+Context]; Context
0x100424b5d  lea     rdx, Delimiter; ","
0x100424b64  mov     rcx, rbx; String
0x100424b67  call    cs:__imp_wcstok_s
0x100424b6d  test    rax, rax
0x100424b70  jz      loc_100424C1C
0x100424b76  lea     rbp, aTraceFlagsIsSe; "Trace flags is set during startup"
0x100424b7d  lea     r15, aSuccess; "SUCCESS"
0x100424b84  lea     rsi, aWrongTraceFlag; "Wrong trace flag number read from winfa"...
0x100424b8b  nop     dword ptr [rax+rax+00h]
0x100424b90  xor     edx, edx; EndPtr
0x100424b92  lea     r8d, [rdx+0Ah]; Radix
0x100424b96  mov     rcx, rax; String
0x100424b99  call    cs:__imp_wcstol
0x100424b9f  mov     edi, eax
0x100424ba1  mov     r8d, 0FFFFFFFFh
0x100424ba7  cmp     eax, 3BC3h
0x100424bac  ja      short loc_100424BE4
0x100424bae  lfence
0x100424bb1  xor     edx, edx
0x100424bb3  lea     r9d, [r8+3]
0x100424bb7  mov     ecx, eax
0x100424bb9  call    cs:__imp_?UtilDbccTraceOn@@YA_NKFW4FlagScope@CGlobalTraceFlags@@W4FlagUsage@2@@Z; UtilDbccTraceOn(ulong,short,CGlobalTraceFlags::FlagScope,CGlobalTraceFlags::FlagUsage)
0x100424bbf  lea     rcx, aUnableToSetTra; "Unable to set trace flag during startup"...
0x100424bc6  test    al, al
0x100424bc8  cmovnz  rcx, rbp
0x100424bcc  lea     r9, aError; "ERROR"
0x100424bd3  cmovnz  r9, r15
0x100424bd7  mov     [rsp+98h+var_78], rcx
0x100424bdc  mov     r8d, 0FFFFFFFFh
0x100424be2  jmp     short loc_100424BF0
0x100424be4  mov     [rsp+98h+var_78], rsi
0x100424be9  lea     r9, aError; "ERROR"
0x100424bf0  mov     edx, edi
0x100424bf2  lea     rcx, aTraceon; "TRACEON"
0x100424bf9  call    cs:__imp_?FireXEventForTraceFlags@@YAXPEB_WHW4FlagScope@CGlobalTraceFlags@@00@Z; FireXEventForTraceFlags(wchar_t const *,int,CGlobalTraceFlags::FlagScope,wchar_t const *,wchar_t const *)
0x100424bff  lea     r8, [rsp+98h+Context]; Context
0x100424c04  lea     rdx, Delimiter; ","
0x100424c0b  xor     ecx, ecx; String
0x100424c0d  call    cs:__imp_wcstok_s
0x100424c13  test    rax, rax
0x100424c16  jnz     loc_100424B90
0x100424c1c  test    rbx, rbx
0x100424c1f  jz      short loc_100424C3A
0x100424c21  call    cs:__imp_GetProcessHeap
0x100424c27  mov     rcx, rax; hHeap
0x100424c2a  mov     r8, rbx; lpMem
0x100424c2d  xor     edx, edx; dwFlags
0x100424c2f  call    cs:__imp_HeapFree
0x100424c35  mov     [rsp+98h+var_50], r14
0x100424c3a  add     rsp, 68h
0x100424c3e  pop     r15
0x100424c40  pop     r14
0x100424c42  pop     rdi
0x100424c43  pop     rsi
0x100424c44  pop     rbp
0x100424c45  pop     rbx
0x100424c46  retn
```
