# GenerateThreadProcAttributeList(_ISOLATION_CONTAINER *,_ISO_ISOLATION_OPTIONS *,_ISOLATION_MANIFSET_PROPERTIES *,_STARTUPINFOEXW *)

- ea: `0x180019fb0`
- end: `0x18001a20a`
- name: `?GenerateThreadProcAttributeList@@YAJPEAU_ISOLATION_CONTAINER@@PEAU_ISO_ISOLATION_OPTIONS@@PEAU_ISOLATION_MANIFSET_PROPERTIES@@PEAU_STARTUPINFOEXW@@@Z`
- size: `602`
- prototype: `int(struct _ISOLATION_CONTAINER *, struct _ISO_ISOLATION_OPTIONS *, struct _ISOLATION_MANIFSET_PROPERTIES *, struct _STARTUPINFOEXW *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callers

- `0x18001ba10`

## callees

- `0x180019fb0`
- `0x18001a210`
- `0x18001a288`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a000`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a00b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a068`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a0c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a11a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a183`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a1bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a000`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a00b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a068`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a0c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a11a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a183`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a1bd`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x18001a0bb`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x18001a110`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x18001a175`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x18001a0bb`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x18001a110`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x18001a175`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x180019ffa`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x18001a05e`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x180019ffa`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x18001a05e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001a03a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001a03a`

## string_xrefs

- `0x18001a020`: `Call: InitializeProcThreadAttributeList failed with unexpected error (expected ERROR_INSUFFICIENT_BUFFER)`
- `0x18001a199`: `Call: UpdateProcThreadAttribute (Setting allocated attributeList)`
- `0x18001a0db`: `Call: UpdateProcThreadAttribute (Adding LPAC to attribute list)`
- `0x18001a07e`: `Call: InitializeProcThreadAttributeList second call failure, expected success`
- `0x18001a130`: `Call: UpdateProcThreadAttribute (Adding manifest info to attribute list)`

## pseudocode

```c
__int64 __fastcall GenerateThreadProcAttributeList(
        struct _ISOLATION_CONTAINER *a1,
        struct _ISO_ISOLATION_OPTIONS *a2,
        struct _ISOLATION_MANIFSET_PROPERTIES *a3,
        struct _STARTUPINFOEXW *a4)
{
  int v4; // ebp
  LPPROC_THREAD_ATTRIBUTE_LIST lpAttributeList; // rsi
  DWORD v8; // edi
  signed int v9; // eax
  signed int v10; // edi
  struct _PROC_THREAD_ATTRIBUTE_LIST *v11; // rax
  struct _PROC_THREAD_ATTRIBUTE_LIST *v12; // rbx
  signed int v13; // eax
  const unsigned __int16 *v14; // rdx
  signed int v15; // eax
  signed int v16; // eax
  __int64 i; // rdi
  signed int LastError; // eax
  signed int v20; // eax
  ULONG_PTR Size; // [rsp+70h] [rbp+8h] BYREF
  struct _ISO_ISOLATION_OPTIONS *v22; // [rsp+78h] [rbp+10h] BYREF

  v22 = a2;
  v4 = *((_DWORD *)a1 + 9);
  lpAttributeList = a4->lpAttributeList;
  v8 = 2 - (v4 != 0);
  if ( lpAttributeList )
  {
    LODWORD(lpAttributeList) = *((_DWORD *)lpAttributeList + 1);
    v8 += (unsigned int)lpAttributeList;
  }
  Size = 0;
  InitializeProcThreadAttributeList(0, v8, 0, &Size);
  if ( GetLastError() == 122 )
  {
    v11 = (struct _PROC_THREAD_ATTRIBUTE_LIST *)LocalAlloc(0, Size);
    v22 = v11;
    v12 = v11;
    if ( v11 )
    {
      if ( InitializeProcThreadAttributeList(v11, v8, 0, &Size) )
      {
        if ( v4 || UpdateProcThreadAttribute(v12, 0, 0x2000Fu, &g_allApplicationPackagesPolicy, 4u, 0, 0) )
        {
          if ( UpdateProcThreadAttribute(v12, 0, 0x20017u, a3, 0x38u, 0, 0) )
          {
            for ( i = 0; ; i = (unsigned int)(i + 1) )
            {
              if ( (unsigned int)i >= (unsigned int)lpAttributeList )
              {
                v22 = 0;
                a4->lpAttributeList = v12;
                wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(&v22);
                return 0;
              }
              if ( !UpdateProcThreadAttribute(
                      v12,
                      0,
                      *((_QWORD *)a4->lpAttributeList + 3 * i + 3),
                      *((PVOID *)a4->lpAttributeList + 3 * i + 5),
                      *((_QWORD *)a4->lpAttributeList + 3 * i + 4),
                      0,
                      0) )
                break;
            }
            LastError = GetLastError();
            v10 = LastError;
            if ( LastError > 0 )
              v10 = (unsigned __int16)LastError | 0x80070000;
            v14 = L"Call: UpdateProcThreadAttribute (Setting allocated attributeList)";
          }
          else
          {
            v16 = GetLastError();
            v10 = v16;
            if ( v16 > 0 )
              v10 = (unsigned __int16)v16 | 0x80070000;
            v14 = L"Call: UpdateProcThreadAttribute (Adding manifest info to attribute list)";
          }
        }
        else
        {
          v15 = GetLastError();
          v10 = v15;
          if ( v15 > 0 )
            v10 = (unsigned __int16)v15 | 0x80070000;
          v14 = L"Call: UpdateProcThreadAttribute (Adding LPAC to attribute list)";
        }
      }
      else
      {
        v13 = GetLastError();
        v10 = v13;
        if ( v13 > 0 )
          v10 = (unsigned __int16)v13 | 0x80070000;
        v14 = L"Call: InitializeProcThreadAttributeList second call failure, expected success";
      }
    }
    else
    {
      v20 = GetLastError();
      v10 = v20;
      if ( v20 > 0 )
        v10 = (unsigned __int16)v20 | 0x80070000;
      v14 = L"attributeList buffer allocation failure";
    }
    IsolationApi::TelemetryHelper::LogAttributeListGenerationError(v10, v14);
    if ( v10 > 0 )
      v10 = (unsigned __int16)v10 | 0x80070000;
    wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(&v22);
  }
  else
  {
    v9 = GetLastError();
    v10 = v9;
    if ( v9 > 0 )
      v10 = (unsigned __int16)v9 | 0x80070000;
    IsolationApi::TelemetryHelper::LogAttributeListGenerationError(
      v10,
      L"Call: InitializeProcThreadAttributeList failed with unexpected error (expected ERROR_INSUFFICIENT_BUFFER)");
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180019fb0  mov     [rsp+arg_10], rbx
0x180019fb5  mov     [rsp+arg_8], rdx
0x180019fba  push    rbp
0x180019fbb  push    rsi
0x180019fbc  push    rdi
0x180019fbd  push    r14
0x180019fbf  push    r15
0x180019fc1  sub     rsp, 40h
0x180019fc5  mov     ebp, [rcx+24h]
0x180019fc8  mov     r14, r9
0x180019fcb  mov     rsi, [r9+68h]
0x180019fcf  mov     eax, ebp
0x180019fd1  neg     eax
0x180019fd3  mov     r15, r8
0x180019fd6  sbb     edi, edi
0x180019fd8  add     edi, 2
0x180019fdb  test    rsi, rsi
0x180019fde  jz      short loc_180019FE5
0x180019fe0  mov     esi, [rsi+4]
0x180019fe3  add     edi, esi
0x180019fe5  lea     r9, [rsp+68h+Size]; lpSize
0x180019fea  mov     [rsp+68h+Size], 0
0x180019ff3  xor     r8d, r8d; dwFlags
0x180019ff6  mov     edx, edi; dwAttributeCount
0x180019ff8  xor     ecx, ecx; lpAttributeList
0x180019ffa  call    cs:__imp_InitializeProcThreadAttributeList
0x18001a000  call    cs:__imp_GetLastError
0x18001a006  cmp     eax, 7Ah ; 'z'
0x18001a009  jz      short loc_18001A033
0x18001a00b  call    cs:__imp_GetLastError
0x18001a011  mov     edi, eax
0x18001a013  test    eax, eax
0x18001a015  jle     short loc_18001A020
0x18001a017  movzx   edi, ax
0x18001a01a  or      edi, 80070000h
0x18001a020  lea     rdx, aCallInitialize_0; "Call: InitializeProcThreadAttributeList"...
0x18001a027  mov     ecx, edi; int
0x18001a029  call    ?LogAttributeListGenerationError@TelemetryHelper@IsolationApi@@SAXJPEBG@Z; IsolationApi::TelemetryHelper::LogAttributeListGenerationError(long,ushort const *)
0x18001a02e  jmp     loc_18001A1F4
0x18001a033  mov     rdx, [rsp+68h+Size]; uBytes
0x18001a038  xor     ecx, ecx; uFlags
0x18001a03a  call    cs:__imp_LocalAlloc
0x18001a040  mov     [rsp+68h+arg_8], rax
0x18001a045  mov     rbx, rax
0x18001a048  test    rax, rax
0x18001a04b  jz      loc_18001A1BD
0x18001a051  lea     r9, [rsp+68h+Size]; lpSize
0x18001a056  xor     r8d, r8d; dwFlags
0x18001a059  mov     edx, edi; dwAttributeCount
0x18001a05b  mov     rcx, rax; lpAttributeList
0x18001a05e  call    cs:__imp_InitializeProcThreadAttributeList
0x18001a064  test    eax, eax
0x18001a066  jnz     short loc_18001A08A
0x18001a068  call    cs:__imp_GetLastError
0x18001a06e  mov     edi, eax
0x18001a070  mov     ebx, 80070000h
0x18001a075  test    eax, eax
0x18001a077  jle     short loc_18001A07E
0x18001a079  movzx   edi, ax
0x18001a07c  or      edi, ebx
0x18001a07e  lea     rdx, aCallInitialize; "Call: InitializeProcThreadAttributeList"...
0x18001a085  jmp     loc_18001A1DA
0x18001a08a  test    ebp, ebp
0x18001a08c  jnz     short loc_18001A0E7
0x18001a08e  mov     [rsp+68h+lpReturnSize], 0; lpReturnSize
0x18001a097  lea     r9, ?g_allApplicationPackagesPolicy@@3KA; lpValue
0x18001a09e  mov     [rsp+68h+lpPreviousValue], 0; lpPreviousValue
0x18001a0a7  xor     edx, edx; dwFlags
0x18001a0a9  mov     r8d, 2000Fh; Attribute
0x18001a0af  mov     [rsp+68h+cbSize], 4; cbSize
0x18001a0b8  mov     rcx, rbx; lpAttributeList
0x18001a0bb  call    cs:__imp_UpdateProcThreadAttribute
0x18001a0c1  test    eax, eax
0x18001a0c3  jnz     short loc_18001A0E7
0x18001a0c5  call    cs:__imp_GetLastError
0x18001a0cb  mov     edi, eax
0x18001a0cd  mov     ebx, 80070000h
0x18001a0d2  test    eax, eax
0x18001a0d4  jle     short loc_18001A0DB
0x18001a0d6  movzx   edi, ax
0x18001a0d9  or      edi, ebx
0x18001a0db  lea     rdx, aCallUpdateproc_1; "Call: UpdateProcThreadAttribute (Adding"...
0x18001a0e2  jmp     loc_18001A1DA
0x18001a0e7  mov     [rsp+68h+lpReturnSize], 0; lpReturnSize
0x18001a0f0  mov     r9, r15; lpValue
0x18001a0f3  mov     [rsp+68h+lpPreviousValue], 0; lpPreviousValue
0x18001a0fc  xor     edx, edx; dwFlags
0x18001a0fe  mov     r8d, 20017h; Attribute
0x18001a104  mov     [rsp+68h+cbSize], 38h ; '8'; cbSize
0x18001a10d  mov     rcx, rbx; lpAttributeList
0x18001a110  call    cs:__imp_UpdateProcThreadAttribute
0x18001a116  test    eax, eax
0x18001a118  jnz     short loc_18001A13C
0x18001a11a  call    cs:__imp_GetLastError
0x18001a120  mov     edi, eax
0x18001a122  mov     ebx, 80070000h
0x18001a127  test    eax, eax
0x18001a129  jle     short loc_18001A130
0x18001a12b  movzx   edi, ax
0x18001a12e  or      edi, ebx
0x18001a130  lea     rdx, aCallUpdateproc; "Call: UpdateProcThreadAttribute (Adding"...
0x18001a137  jmp     loc_18001A1DA
0x18001a13c  xor     edi, edi
0x18001a13e  cmp     edi, esi
0x18001a140  jnb     short loc_18001A1A2
0x18001a142  mov     r8, [r14+68h]
0x18001a146  lea     rcx, [rdi+rdi*2]
0x18001a14a  mov     [rsp+68h+lpReturnSize], 0; lpReturnSize
0x18001a153  xor     edx, edx; dwFlags
0x18001a155  mov     [rsp+68h+lpPreviousValue], 0; lpPreviousValue
0x18001a15e  mov     rax, [r8+rcx*8+20h]
0x18001a163  mov     r9, [r8+rcx*8+28h]; lpValue
0x18001a168  mov     r8, [r8+rcx*8+18h]; Attribute
0x18001a16d  mov     rcx, rbx; lpAttributeList
0x18001a170  mov     [rsp+68h+cbSize], rax; cbSize
0x18001a175  call    cs:__imp_UpdateProcThreadAttribute
0x18001a17b  test    eax, eax
0x18001a17d  jz      short loc_18001A183
0x18001a17f  inc     edi
0x18001a181  jmp     short loc_18001A13E
0x18001a183  call    cs:__imp_GetLastError
0x18001a189  mov     edi, eax
0x18001a18b  mov     ebx, 80070000h
0x18001a190  test    eax, eax
0x18001a192  jle     short loc_18001A199
0x18001a194  movzx   edi, ax
0x18001a197  or      edi, ebx
0x18001a199  lea     rdx, aCallUpdateproc_0; "Call: UpdateProcThreadAttribute (Settin"...
0x18001a1a0  jmp     short loc_18001A1DA
0x18001a1a2  lea     rcx, [rsp+68h+arg_8]
0x18001a1a7  mov     [rsp+68h+arg_8], 0
0x18001a1b0  mov     [r14+68h], rbx
0x18001a1b4  call    ??1?$unique_storage@U?$resource_policy@PEAU_PROC_THREAD_ATTRIBUTE_LIST@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(void)
0x18001a1b9  xor     eax, eax
0x18001a1bb  jmp     short loc_18001A1F6
0x18001a1bd  call    cs:__imp_GetLastError
0x18001a1c3  mov     edi, eax
0x18001a1c5  mov     ebx, 80070000h
0x18001a1ca  test    eax, eax
0x18001a1cc  jle     short loc_18001A1D3
0x18001a1ce  movzx   edi, ax
0x18001a1d1  or      edi, ebx
0x18001a1d3  lea     rdx, aAttributelistB; "attributeList buffer allocation failure"
0x18001a1da  mov     ecx, edi; int
0x18001a1dc  call    ?LogAttributeListGenerationError@TelemetryHelper@IsolationApi@@SAXJPEBG@Z; IsolationApi::TelemetryHelper::LogAttributeListGenerationError(long,ushort const *)
0x18001a1e1  test    edi, edi
0x18001a1e3  jle     short loc_18001A1EA
0x18001a1e5  movzx   edi, di
0x18001a1e8  or      edi, ebx
0x18001a1ea  lea     rcx, [rsp+68h+arg_8]
0x18001a1ef  call    ??1?$unique_storage@U?$resource_policy@PEAU_PROC_THREAD_ATTRIBUTE_LIST@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(void)
0x18001a1f4  mov     eax, edi
0x18001a1f6  mov     rbx, [rsp+68h+arg_10]
0x18001a1fe  add     rsp, 40h
0x18001a202  pop     r15
0x18001a204  pop     r14
0x18001a206  pop     rdi
0x18001a207  pop     rsi
0x18001a208  pop     rbp
0x18001a209  retn
```
