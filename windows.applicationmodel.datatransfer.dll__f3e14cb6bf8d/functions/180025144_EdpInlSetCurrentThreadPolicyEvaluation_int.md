# EdpInlSetCurrentThreadPolicyEvaluation(int)

- ea: `0x180025144`
- end: `0x18002526d`
- name: `?EdpInlSetCurrentThreadPolicyEvaluation@@YAJH@Z`
- size: `297`
- prototype: `__int64 __fastcall(int)`
- caller_count: `15`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, service_task`

## callers

- `0x18000e5a0`
- `0x18000e874`
- `0x18000eb1c`
- `0x18000edc0`
- `0x18000f09c`
- `0x18000f340`
- `0x18000f5e8`
- `0x180016aa8`
- `0x180016ad0`
- `0x18002d080`
- `0x18002dba0`
- `0x18002df60`
- `0x18003ea60`
- `0x18004f4e0`
- `0x18006b730`

## callees

- `0x18000346c`
- `0x18002508c`
- `0x180025144`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800251cc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800251cc`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x18002521c`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x18002521c`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x18002519e`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x18002519e`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180025230`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180025230`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800251ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002523a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800251ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002523a`
- `FeClient!EdpSetCredServiceInfo` at `0x1800251ec`
- `FeClient!EdpSetCredServiceInfo` at `0x1800251ec`

## pseudocode

```c
__int64 __fastcall EdpInlSetCurrentThreadPolicyEvaluation(void *a1)
{
  int v1; // esi
  signed int ProcessTlsIndex; // ebx
  DWORD v3; // ecx
  DWORD v4; // edi
  signed int LastError; // eax
  void *v6; // rcx
  signed int v7; // eax
  int v9; // [rsp+30h] [rbp-49h] BYREF
  unsigned int v10; // [rsp+34h] [rbp-45h]
  DWORD CurrentProcessId; // [rsp+38h] [rbp-41h]
  DWORD v12; // [rsp+3Ch] [rbp-3Dh]
  DWORD dwTlsIndex; // [rsp+E8h] [rbp+6Fh] BYREF

  dwTlsIndex = -1;
  v1 = (int)a1;
  ProcessTlsIndex = EdpInlGetProcessTlsIndex(a1, &dwTlsIndex);
  if ( ProcessTlsIndex < 0 )
    return (unsigned int)ProcessTlsIndex;
  v3 = dwTlsIndex;
  if ( dwTlsIndex == -1 )
  {
    memset_0(&v9, 0, 0x88u);
    dwTlsIndex = -1;
    v4 = TlsAlloc();
    if ( v4 == -1 )
    {
      LastError = GetLastError();
      ProcessTlsIndex = LastError;
      if ( LastError > 0 )
        ProcessTlsIndex = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_12;
    }
    v9 = 136;
    v10 = 7;
    CurrentProcessId = GetCurrentProcessId();
    v12 = v4;
    ProcessTlsIndex = EdpSetCredServiceInfo(v10, 0, 0, 0, &v9);
    if ( ProcessTlsIndex < 0 || (ProcessTlsIndex = EdpInlGetProcessTlsIndex(v6, &dwTlsIndex), ProcessTlsIndex < 0) )
    {
LABEL_11:
      TlsFree(v4);
LABEL_12:
      if ( ProcessTlsIndex < 0 )
        return (unsigned int)ProcessTlsIndex;
      v3 = dwTlsIndex;
      goto LABEL_14;
    }
    v3 = dwTlsIndex;
    if ( dwTlsIndex == -1 )
    {
      ProcessTlsIndex = -2147418113;
      goto LABEL_11;
    }
    if ( v4 != dwTlsIndex )
      goto LABEL_11;
  }
LABEL_14:
  if ( TlsSetValue(v3, (LPVOID)(v1 != 0)) )
  {
    return 0;
  }
  else
  {
    v7 = GetLastError();
    ProcessTlsIndex = v7;
    if ( v7 > 0 )
      return (unsigned __int16)v7 | 0x80070000;
  }
  return (unsigned int)ProcessTlsIndex;
}

```

## disassembly

```asm
0x180025144  mov     [rsp-8+arg_0], rbx
0x180025149  mov     [rsp-8+arg_10], rsi
0x18002514e  push    rbp
0x18002514f  push    rdi
0x180025150  push    r14
0x180025152  lea     rbp, [rsp-47h]
0x180025157  sub     rsp, 0C0h
0x18002515e  or      r14d, 0FFFFFFFFh
0x180025162  lea     rdx, [rbp+57h+dwTlsIndex]; unsigned int *
0x180025166  mov     [rbp+57h+dwTlsIndex], r14d
0x18002516a  mov     esi, ecx
0x18002516c  call    ?EdpInlGetProcessTlsIndex@@YAJPEAXPEAK@Z; EdpInlGetProcessTlsIndex(void *,ulong *)
0x180025171  mov     ebx, eax
0x180025173  test    eax, eax
0x180025175  js      loc_180025253
0x18002517b  mov     ecx, [rbp+57h+dwTlsIndex]
0x18002517e  cmp     ecx, r14d
0x180025181  jnz     loc_180025229
0x180025187  mov     ebx, 88h
0x18002518c  lea     rcx, [rbp+57h+var_A0]; void *
0x180025190  mov     r8d, ebx; Size
0x180025193  xor     edx, edx; Val
0x180025195  call    memset_0
0x18002519a  mov     [rbp+57h+dwTlsIndex], r14d
0x18002519e  call    cs:__imp_TlsAlloc
0x1800251a4  mov     edi, eax
0x1800251a6  cmp     eax, r14d
0x1800251a9  jnz     short loc_1800251C2
0x1800251ab  call    cs:__imp_GetLastError
0x1800251b1  mov     ebx, eax
0x1800251b3  test    eax, eax
0x1800251b5  jle     short loc_180025222
0x1800251b7  movzx   ebx, ax
0x1800251ba  or      ebx, 80070000h
0x1800251c0  jmp     short loc_180025222
0x1800251c2  mov     [rbp+57h+var_A0], ebx
0x1800251c5  mov     [rbp+57h+var_9C], 7
0x1800251cc  call    cs:__imp_GetCurrentProcessId
0x1800251d2  mov     ecx, [rbp+57h+var_9C]
0x1800251d5  xor     r9d, r9d
0x1800251d8  mov     [rbp+57h+var_98], eax
0x1800251db  xor     r8d, r8d
0x1800251de  lea     rax, [rbp+57h+var_A0]
0x1800251e2  mov     [rbp+57h+var_94], edi
0x1800251e5  xor     edx, edx
0x1800251e7  mov     [rsp+0D0h+var_B0], rax
0x1800251ec  call    cs:__imp_EdpSetCredServiceInfo
0x1800251f2  mov     ebx, eax
0x1800251f4  test    eax, eax
0x1800251f6  js      short loc_18002521A
0x1800251f8  lea     rdx, [rbp+57h+dwTlsIndex]; unsigned int *
0x1800251fc  call    ?EdpInlGetProcessTlsIndex@@YAJPEAXPEAK@Z; EdpInlGetProcessTlsIndex(void *,ulong *)
0x180025201  mov     ebx, eax
0x180025203  test    eax, eax
0x180025205  js      short loc_18002521A
0x180025207  mov     ecx, [rbp+57h+dwTlsIndex]
0x18002520a  cmp     ecx, r14d
0x18002520d  jnz     short loc_180025216
0x18002520f  mov     ebx, 8000FFFFh
0x180025214  jmp     short loc_18002521A
0x180025216  cmp     edi, ecx
0x180025218  jz      short loc_180025229
0x18002521a  mov     ecx, edi; dwTlsIndex
0x18002521c  call    cs:__imp_TlsFree
0x180025222  test    ebx, ebx
0x180025224  js      short loc_180025253
0x180025226  mov     ecx, [rbp+57h+dwTlsIndex]; dwTlsIndex
0x180025229  xor     edx, edx
0x18002522b  test    esi, esi
0x18002522d  setnz   dl; lpTlsValue
0x180025230  call    cs:__imp_TlsSetValue
0x180025236  test    eax, eax
0x180025238  jnz     short loc_180025251
0x18002523a  call    cs:__imp_GetLastError
0x180025240  mov     ebx, eax
0x180025242  test    eax, eax
0x180025244  jle     short loc_180025253
0x180025246  movzx   ebx, ax
0x180025249  or      ebx, 80070000h
0x18002524f  jmp     short loc_180025253
0x180025251  xor     ebx, ebx
0x180025253  lea     r11, [rsp+0D0h+var_10]
0x18002525b  mov     eax, ebx
0x18002525d  mov     rbx, [r11+20h]
0x180025261  mov     rsi, [r11+30h]
0x180025265  mov     rsp, r11
0x180025268  pop     r14
0x18002526a  pop     rdi
0x18002526b  pop     rbp
0x18002526c  retn
```
