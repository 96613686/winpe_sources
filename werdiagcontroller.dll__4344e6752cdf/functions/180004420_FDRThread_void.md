# FDRThread(void)

- ea: `0x180004420`
- end: `0x180004623`
- name: `?FDRThread@@YAJXZ`
- size: `515`
- prototype: `__int64(void)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, loader_planting`

## callees

- `0x180001400`
- `0x180001cd4`
- `0x1800039e0`
- `0x180003b58`
- `0x180004384`
- `0x180004420`
- `0x180005488`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004501`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800045b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004501`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800045b5`
- `ntdll!DbgPrintEx` at `0x180004460`
- `ntdll!DbgPrintEx` at `0x1800044de`
- `ntdll!DbgPrintEx` at `0x180004518`
- `ntdll!DbgPrintEx` at `0x18000459d`
- `ntdll!DbgPrintEx` at `0x1800045d5`
- `ntdll!DbgPrintEx` at `0x1800045f5`
- `ntdll!DbgPrintEx` at `0x180004460`
- `ntdll!DbgPrintEx` at `0x1800044de`
- `ntdll!DbgPrintEx` at `0x180004518`
- `ntdll!DbgPrintEx` at `0x18000459d`
- `ntdll!DbgPrintEx` at `0x1800045d5`
- `ntdll!DbgPrintEx` at `0x1800045f5`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800045ab`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800045ab`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800044f3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800044f3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000456d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000456d`

## pseudocode

```c
__int64 FDRThread(void)
{
  int started; // eax
  unsigned int v1; // ebx
  int UniqueProcess; // ebx
  wchar_t **unique_for; // rax
  wchar_t *v4; // rdi
  int v5; // eax
  HANDLE EventW; // rbx
  DWORD v7; // eax
  int v8; // edx
  unsigned int i; // r8d
  int v10; // eax
  BOOL j; // eax
  DWORD v12; // eax
  DWORD LastError; // eax
  void *v15; // [rsp+30h] [rbp-158h] BYREF
  _QWORD v16[38]; // [rsp+40h] [rbp-148h] BYREF

  started = CFDRShim::StartFDR((CFDRShim *)v16);
  v1 = started;
  if ( started >= 0 )
  {
    UniqueProcess = (int)NtCurrentTeb()->ClientId.UniqueProcess;
    unique_for = (wchar_t **)utl::make_unique_for_overwrite<wchar_t [0],0>(&v15, 260);
    v4 = *unique_for;
    *unique_for = 0;
    if ( v15 )
      operator delete[](v15);
    if ( !v4 )
    {
      DbgPrintEx(0x96u, 0, "WERDIAG: Out of resources allocating memory for string buffer\n");
      return (unsigned int)-2147024882;
    }
    v5 = StringCchPrintfW(v4, 0x104u, L"%s-%d", L"FDR_FLUSH_MESSAGE", UniqueProcess);
    v1 = v5;
    if ( v5 >= 0 )
    {
      EventW = CreateEventW(0, 0, 0, v4);
      if ( EventW )
      {
        v8 = 0;
        for ( i = 0; i < LODWORD(v16[0]); v8 = v10 )
        {
          v10 = v8 + 1;
          if ( *((_DWORD *)&v16[4] + 7 * i) )
            v10 = v8;
          ++i;
        }
        for ( j = v8 == 0; ; j = (int)CFDRShim::EnableLogProviders((CFDRShim *)v16) >= 0 )
        {
          v12 = WaitForSingleObject(EventW, j ? -1 : 5000);
          if ( !v12 )
            break;
          if ( v12 != 258 )
          {
            DbgPrintEx(0x96u, 0, "WERDIAG: Unexpected event response or failed waiting for event\n");
            goto LABEL_10;
          }
        }
        if ( SetEvent(EventW) )
        {
          DbgPrintEx(0x96u, 0, "WERDIAG: Flushing done, done signal sent\n");
          v1 = 0;
          goto LABEL_23;
        }
        LastError = GetLastError();
        DbgPrintEx(0x96u, 0, "WERDIAG: Failed setting event. Win32 error: %08X\n", LastError);
      }
      else
      {
        v7 = GetLastError();
        DbgPrintEx(0x96u, 0, "WERDIAG: Failed creating event. Win32 error: %08X\n", v7);
      }
LABEL_10:
      v1 = -2147467259;
    }
    else
    {
      DbgPrintEx(0x96u, 0, "WERDIAG: Failed concatenating strings. HRESULT: %08X\n", v5);
    }
LABEL_23:
    operator delete[](v4);
    return v1;
  }
  DbgPrintEx(0x96u, 0, "WERDIAG: StartFDR failed 0x%x\n", started);
  return v1;
}

```

## disassembly

```asm
0x180004420  mov     [rsp+arg_0], rbx
0x180004425  push    rdi
0x180004426  sub     rsp, 180h
0x18000442d  mov     rax, cs:__security_cookie
0x180004434  xor     rax, rsp
0x180004437  mov     [rsp+188h+var_18], rax
0x18000443f  lea     rcx, [rsp+188h+var_148]; this
0x180004444  call    ?StartFDR@CFDRShim@@QEAAJXZ; CFDRShim::StartFDR(void)
0x180004449  mov     ebx, eax
0x18000444b  test    eax, eax
0x18000444d  jns     short loc_18000446B
0x18000444f  mov     r9d, eax
0x180004452  lea     r8, aWerdiagStartfd; "WERDIAG: StartFDR failed 0x%x\n"
0x180004459  xor     edx, edx; Level
0x18000445b  mov     ecx, 96h; ComponentId
0x180004460  call    cs:__imp_DbgPrintEx
0x180004466  jmp     loc_180004600
0x18000446b  mov     rax, gs:30h
0x180004474  lea     rcx, [rsp+188h+var_158]
0x180004479  mov     edx, 104h
0x18000447e  mov     ebx, [rax+40h]
0x180004481  call    ??$make_unique_for_overwrite@$$BY0A@_W$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@0@_K@Z; utl::make_unique_for_overwrite<wchar_t [0],0>(unsigned __int64)
0x180004486  mov     rdi, [rax]
0x180004489  mov     qword ptr [rax], 0
0x180004490  mov     rcx, [rsp+188h+var_158]; void *
0x180004495  test    rcx, rcx
0x180004498  jz      short loc_18000449F
0x18000449a  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x18000449f  test    rdi, rdi
0x1800044a2  jz      loc_1800045E7
0x1800044a8  lea     r9, aFdrFlushMessag; "FDR_FLUSH_MESSAGE"
0x1800044af  mov     [rsp+188h+var_168], ebx
0x1800044b3  lea     r8, aSD; "%s-%d"
0x1800044ba  mov     edx, 104h; unsigned __int64
0x1800044bf  mov     rcx, rdi; wchar_t *
0x1800044c2  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800044c7  mov     ebx, eax
0x1800044c9  test    eax, eax
0x1800044cb  jns     short loc_1800044E9
0x1800044cd  mov     r9d, eax
0x1800044d0  lea     r8, aWerdiagFailedC_1; "WERDIAG: Failed concatenating strings. "...
0x1800044d7  xor     edx, edx; Level
0x1800044d9  mov     ecx, 96h; ComponentId
0x1800044de  call    cs:__imp_DbgPrintEx
0x1800044e4  jmp     loc_1800045DD
0x1800044e9  mov     r9, rdi; lpName
0x1800044ec  xor     r8d, r8d; bInitialState
0x1800044ef  xor     edx, edx; bManualReset
0x1800044f1  xor     ecx, ecx; lpEventAttributes
0x1800044f3  call    cs:__imp_CreateEventW
0x1800044f9  mov     rbx, rax
0x1800044fc  test    rax, rax
0x1800044ff  jnz     short loc_180004528
0x180004501  call    cs:__imp_GetLastError
0x180004507  lea     r8, aWerdiagFailedC_7; "WERDIAG: Failed creating event. Win32 e"...
0x18000450e  mov     r9d, eax
0x180004511  xor     edx, edx; Level
0x180004513  mov     ecx, 96h; ComponentId
0x180004518  call    cs:__imp_DbgPrintEx
0x18000451e  mov     ebx, 80004005h
0x180004523  jmp     loc_1800045DD
0x180004528  mov     r9, [rsp+188h+var_148]
0x18000452d  xor     edx, edx
0x18000452f  xor     r8d, r8d
0x180004532  test    r9d, r9d
0x180004535  jz      short loc_180004553
0x180004537  mov     eax, r8d
0x18000453a  imul    rcx, rax, 1Ch
0x18000453e  lea     eax, [rdx+1]
0x180004541  cmp     [rsp+rcx+188h+var_128], 0
0x180004546  cmovnz  eax, edx
0x180004549  inc     r8d
0x18000454c  mov     edx, eax
0x18000454e  cmp     r8d, r9d
0x180004551  jb      short loc_180004537
0x180004553  xor     eax, eax
0x180004555  test    edx, edx
0x180004557  setz    al
0x18000455a  neg     eax
0x18000455c  mov     rcx, rbx; hHandle
0x18000455f  sbb     edx, edx
0x180004561  and     edx, 0FFFFEC77h
0x180004567  add     edx, 1388h; dwMilliseconds
0x18000456d  call    cs:__imp_WaitForSingleObject
0x180004573  test    eax, eax
0x180004575  jz      short loc_1800045A8
0x180004577  cmp     eax, 102h
0x18000457c  jnz     short loc_18000458F
0x18000457e  lea     rcx, [rsp+188h+var_148]; this
0x180004583  call    ?EnableLogProviders@CFDRShim@@QEAAJXZ; CFDRShim::EnableLogProviders(void)
0x180004588  not     eax
0x18000458a  shr     eax, 1Fh
0x18000458d  jmp     short loc_18000455A
0x18000458f  lea     r8, aWerdiagUnexpec; "WERDIAG: Unexpected event response or f"...
0x180004596  xor     edx, edx; Level
0x180004598  mov     ecx, 96h; ComponentId
0x18000459d  call    cs:__imp_DbgPrintEx
0x1800045a3  jmp     loc_18000451E
0x1800045a8  mov     rcx, rbx; hEvent
0x1800045ab  call    cs:__imp_SetEvent
0x1800045b1  test    eax, eax
0x1800045b3  jnz     short loc_1800045C7
0x1800045b5  call    cs:__imp_GetLastError
0x1800045bb  lea     r8, aWerdiagFailedS_0; "WERDIAG: Failed setting event. Win32 er"...
0x1800045c2  jmp     loc_18000450E
0x1800045c7  lea     r8, aWerdiagFlushin; "WERDIAG: Flushing done, done signal sen"...
0x1800045ce  xor     edx, edx; Level
0x1800045d0  mov     ecx, 96h; ComponentId
0x1800045d5  call    cs:__imp_DbgPrintEx
0x1800045db  xor     ebx, ebx
0x1800045dd  mov     rcx, rdi; void *
0x1800045e0  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x1800045e5  jmp     short loc_180004600
0x1800045e7  lea     r8, aWerdiagOutOfRe; "WERDIAG: Out of resources allocating me"...
0x1800045ee  xor     edx, edx; Level
0x1800045f0  mov     ecx, 96h; ComponentId
0x1800045f5  call    cs:__imp_DbgPrintEx
0x1800045fb  mov     ebx, 8007000Eh
0x180004600  mov     eax, ebx
0x180004602  mov     rcx, [rsp+188h+var_18]
0x18000460a  xor     rcx, rsp; StackCookie
0x18000460d  call    __security_check_cookie
0x180004612  mov     rbx, [rsp+188h+arg_0]
0x18000461a  add     rsp, 180h
0x180004621  pop     rdi
0x180004622  retn
```
