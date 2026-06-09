# UMReflectorStart

- ea: `0x180029310`
- end: `0x1800295f4`
- name: `UMReflectorStart`
- size: `740`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180025f10`

## callees

- `0x18000b7dc`
- `0x18000b89c`
- `0x180029310`
- `0x18002e010`

## import_xrefs

- `ntdll!NtFsControlFile` at `0x18002953c`
- `ntdll!NtFsControlFile` at `0x18002953c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029394`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029402`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002946d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029394`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029402`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002946d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800293e8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800293e8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180029353`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800293c4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180029432`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002949d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800294ec`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002956c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800295be`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180029353`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800293c4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180029432`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002949d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800294ec`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002956c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800295be`
- `KERNEL32!LocalFree` at `0x1800295dc`
- `KERNEL32!LocalFree` at `0x1800295dc`
- `KERNEL32!LocalAlloc` at `0x180029386`
- `KERNEL32!LocalAlloc` at `0x180029386`
- `KERNEL32!LoadLibraryW` at `0x1800293f7`
- `KERNEL32!LoadLibraryW` at `0x1800293f7`
- `KERNEL32!GetProcAddress` at `0x180029462`
- `KERNEL32!GetProcAddress` at `0x180029462`

## string_xrefs

- `0x1800293ee`: `shell32.dll`
- `0x180029458`: `SHGetSpecialFolderPathW`

## pseudocode

```c
__int64 UMReflectorStart()
{
  _QWORD *v0; // rbx
  __int64 v1; // rbx
  DWORD CurrentThreadId; // eax
  DWORD LastError; // edi
  _DWORD *InputBuffer; // rsi
  __int64 v5; // rbx
  DWORD v6; // eax
  HMODULE LibraryW; // rax
  __int64 v8; // rbx
  DWORD v9; // eax
  __int64 v10; // rdx
  FARPROC ProcAddress; // rax
  void *v12; // rcx
  __int64 v13; // rbx
  DWORD v14; // eax
  __int64 v15; // rbx
  DWORD v16; // eax
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-18h] BYREF

  v0 = DavReflectorHandle;
  IoStatusBlock = 0;
  if ( !DavReflectorHandle )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
    {
      v1 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      CurrentThreadId = GetCurrentThreadId();
      WPP_SF_d(v1, 12, WPP_788794445e0d336c1137d10bf28c55d3_Traceguids, CurrentThreadId);
    }
    return 87;
  }
  InputBuffer = LocalAlloc(0x40u, 0x20Cu);
  if ( InputBuffer )
  {
    *InputBuffer = GetCurrentProcessId();
    LibraryW = LoadLibraryW(L"shell32.dll");
    if ( LibraryW )
    {
      ProcAddress = GetProcAddress(LibraryW, "SHGetSpecialFolderPathW");
      if ( ProcAddress )
      {
        if ( ((unsigned int (__fastcall *)(_QWORD, _DWORD *, __int64, __int64))ProcAddress)(0, InputBuffer + 1, 32, 1) )
        {
          v12 = (void *)v0[1];
          if ( v12 == (void *)-1LL )
          {
            LastError = 110;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
            {
              v15 = *((_QWORD *)WPP_GLOBAL_Control + 2);
              v16 = GetCurrentThreadId();
              WPP_SF_d(v15, 18, WPP_788794445e0d336c1137d10bf28c55d3_Traceguids, v16);
            }
          }
          else
          {
            LastError = NtFsControlFile(v12, 0, 0, 0, &IoStatusBlock, 0x14038Cu, InputBuffer, 0x20Cu, 0, 0);
            if ( LastError )
            {
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
              {
                v13 = *((_QWORD *)WPP_GLOBAL_Control + 2);
                v14 = GetCurrentThreadId();
                WPP_SF_Dd(v13, 17, WPP_788794445e0d336c1137d10bf28c55d3_Traceguids, v14, LastError);
              }
              if ( LastError == -1073741572 )
                LastError = 0;
            }
          }
          goto LABEL_33;
        }
        LastError = 87;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0 )
        {
LABEL_33:
          LocalFree(InputBuffer);
          return LastError;
        }
        v8 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        v9 = GetCurrentThreadId();
        v10 = 16;
      }
      else
      {
        LastError = GetLastError();
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0 )
        {
          goto LABEL_33;
        }
        v8 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        v9 = GetCurrentThreadId();
        v10 = 15;
      }
    }
    else
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0 )
        goto LABEL_33;
      v8 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v9 = GetCurrentThreadId();
      v10 = 14;
    }
    WPP_SF_Dd(v8, v10, WPP_788794445e0d336c1137d10bf28c55d3_Traceguids, v9, LastError);
    goto LABEL_33;
  }
  LastError = GetLastError();
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
  {
    v5 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    v6 = GetCurrentThreadId();
    WPP_SF_Dd(v5, 13, WPP_788794445e0d336c1137d10bf28c55d3_Traceguids, v6, LastError);
  }
  return LastError;
}

```

## disassembly

```asm
0x180029310  mov     [rsp+arg_0], rbx
0x180029315  mov     [rsp+arg_8], rsi
0x18002931a  push    rdi
0x18002931b  sub     rsp, 60h
0x18002931f  mov     rbx, cs:DavReflectorHandle
0x180029326  xorps   xmm0, xmm0
0x180029329  movups  xmmword ptr [rsp+68h+var_18], xmm0
0x18002932e  test    rbx, rbx
0x180029331  jnz     short loc_18002937A
0x180029333  mov     rbx, cs:WPP_GLOBAL_Control
0x18002933a  lea     rax, WPP_GLOBAL_Control
0x180029341  cmp     rbx, rax
0x180029344  jz      short loc_180029370
0x180029346  test    dword ptr [rbx+1Ch], 1000h
0x18002934d  jz      short loc_180029370
0x18002934f  mov     rbx, [rbx+10h]
0x180029353  call    cs:__imp_GetCurrentThreadId
0x180029359  mov     edx, 0Ch
0x18002935e  lea     r8, WPP_788794445e0d336c1137d10bf28c55d3_Traceguids
0x180029365  mov     r9d, eax
0x180029368  mov     rcx, rbx
0x18002936b  call    WPP_SF_d
0x180029370  mov     edi, 57h ; 'W'
0x180029375  jmp     loc_1800295E2
0x18002937a  mov     edi, 20Ch
0x18002937f  mov     ecx, 40h ; '@'; uFlags
0x180029384  mov     edx, edi; uBytes
0x180029386  call    cs:__imp_LocalAlloc
0x18002938c  mov     rsi, rax
0x18002938f  test    rax, rax
0x180029392  jnz     short loc_1800293E8
0x180029394  call    cs:__imp_GetLastError
0x18002939a  mov     edi, eax
0x18002939c  mov     rbx, cs:WPP_GLOBAL_Control
0x1800293a3  lea     rax, WPP_GLOBAL_Control
0x1800293aa  cmp     rbx, rax
0x1800293ad  jz      loc_1800295E2
0x1800293b3  test    dword ptr [rbx+1Ch], 1000h
0x1800293ba  jz      loc_1800295E2
0x1800293c0  mov     rbx, [rbx+10h]
0x1800293c4  call    cs:__imp_GetCurrentThreadId
0x1800293ca  lea     edx, [rsi+0Dh]
0x1800293cd  mov     dword ptr [rsp+68h+IoStatusBlock], edi
0x1800293d1  mov     r9d, eax
0x1800293d4  lea     r8, WPP_788794445e0d336c1137d10bf28c55d3_Traceguids
0x1800293db  mov     rcx, rbx
0x1800293de  call    WPP_SF_Dd
0x1800293e3  jmp     loc_1800295E2
0x1800293e8  call    cs:__imp_GetCurrentProcessId
0x1800293ee  lea     rcx, LibFileName; "shell32.dll"
0x1800293f5  mov     [rsi], eax
0x1800293f7  call    cs:__imp_LoadLibraryW
0x1800293fd  test    rax, rax
0x180029400  jnz     short loc_180029458
0x180029402  call    cs:__imp_GetLastError
0x180029408  mov     edi, eax
0x18002940a  mov     rbx, cs:WPP_GLOBAL_Control
0x180029411  lea     rax, WPP_GLOBAL_Control
0x180029418  cmp     rbx, rax
0x18002941b  jz      loc_1800295D9
0x180029421  test    dword ptr [rbx+1Ch], 1000h
0x180029428  jz      loc_1800295D9
0x18002942e  mov     rbx, [rbx+10h]
0x180029432  call    cs:__imp_GetCurrentThreadId
0x180029438  mov     edx, 0Eh
0x18002943d  mov     r9d, eax
0x180029440  mov     dword ptr [rsp+68h+IoStatusBlock], edi
0x180029444  lea     r8, WPP_788794445e0d336c1137d10bf28c55d3_Traceguids
0x18002944b  mov     rcx, rbx
0x18002944e  call    WPP_SF_Dd
0x180029453  jmp     loc_1800295D9
0x180029458  lea     rdx, ProcName; "SHGetSpecialFolderPathW"
0x18002945f  mov     rcx, rax; hModule
0x180029462  call    cs:__imp_GetProcAddress
0x180029468  test    rax, rax
0x18002946b  jnz     short loc_1800294AA
0x18002946d  call    cs:__imp_GetLastError
0x180029473  mov     edi, eax
0x180029475  mov     rbx, cs:WPP_GLOBAL_Control
0x18002947c  lea     rax, WPP_GLOBAL_Control
0x180029483  cmp     rbx, rax
0x180029486  jz      loc_1800295D9
0x18002948c  test    dword ptr [rbx+1Ch], 1000h
0x180029493  jz      loc_1800295D9
0x180029499  mov     rbx, [rbx+10h]
0x18002949d  call    cs:__imp_GetCurrentThreadId
0x1800294a3  mov     edx, 0Fh
0x1800294a8  jmp     short loc_18002943D
0x1800294aa  xor     ecx, ecx
0x1800294ac  lea     rdx, [rsi+4]
0x1800294b0  lea     r9d, [rcx+1]
0x1800294b4  lea     r8d, [rcx+20h]
0x1800294b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800294bd  test    eax, eax
0x1800294bf  jnz     short loc_1800294FA
0x1800294c1  lea     edi, [rax+57h]
0x1800294c4  mov     rbx, cs:WPP_GLOBAL_Control
0x1800294cb  lea     rax, WPP_GLOBAL_Control
0x1800294d2  cmp     rbx, rax
0x1800294d5  jz      loc_1800295D9
0x1800294db  test    dword ptr [rbx+1Ch], 1000h
0x1800294e2  jz      loc_1800295D9
0x1800294e8  mov     rbx, [rbx+10h]
0x1800294ec  call    cs:__imp_GetCurrentThreadId
0x1800294f2  lea     edx, [rdi-47h]
0x1800294f5  jmp     loc_18002943D
0x1800294fa  mov     rcx, [rbx+8]; FileHandle
0x1800294fe  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180029502  jz      loc_180029599
0x180029508  mov     [rsp+68h+OutputBufferLength], 0; OutputBufferLength
0x180029510  lea     rax, [rsp+68h+var_18]
0x180029515  mov     [rsp+68h+OutputBuffer], 0; OutputBuffer
0x18002951e  xor     r9d, r9d; ApcContext
0x180029521  mov     [rsp+68h+InputBufferLength], edi; InputBufferLength
0x180029525  xor     r8d, r8d; ApcRoutine
0x180029528  mov     [rsp+68h+InputBuffer], rsi; InputBuffer
0x18002952d  xor     edx, edx; Event
0x18002952f  mov     [rsp+68h+FsControlCode], 14038Ch; FsControlCode
0x180029537  mov     [rsp+68h+IoStatusBlock], rax; IoStatusBlock
0x18002953c  call    cs:__imp_NtFsControlFile
0x180029542  mov     edi, eax
0x180029544  test    eax, eax
0x180029546  jz      loc_1800295D9
0x18002954c  mov     rbx, cs:WPP_GLOBAL_Control
0x180029553  lea     rax, WPP_GLOBAL_Control
0x18002955a  cmp     rbx, rax
0x18002955d  jz      short loc_18002958D
0x18002955f  test    dword ptr [rbx+1Ch], 1000h
0x180029566  jz      short loc_18002958D
0x180029568  mov     rbx, [rbx+10h]
0x18002956c  call    cs:__imp_GetCurrentThreadId
0x180029572  mov     edx, 11h
0x180029577  mov     dword ptr [rsp+68h+IoStatusBlock], edi
0x18002957b  mov     r9d, eax
0x18002957e  lea     r8, WPP_788794445e0d336c1137d10bf28c55d3_Traceguids
0x180029585  mov     rcx, rbx
0x180029588  call    WPP_SF_Dd
0x18002958d  cmp     edi, 0C00000FCh
0x180029593  jnz     short loc_1800295D9
0x180029595  xor     edi, edi
0x180029597  jmp     short loc_1800295D9
0x180029599  mov     edi, 6Eh ; 'n'
0x18002959e  mov     rbx, cs:WPP_GLOBAL_Control
0x1800295a5  lea     rax, WPP_GLOBAL_Control
0x1800295ac  cmp     rbx, rax
0x1800295af  jz      short loc_1800295D9
0x1800295b1  test    dword ptr [rbx+1Ch], 1000h
0x1800295b8  jz      short loc_1800295D9
0x1800295ba  mov     rbx, [rbx+10h]
0x1800295be  call    cs:__imp_GetCurrentThreadId
0x1800295c4  lea     edx, [rdi-5Ch]
0x1800295c7  mov     rcx, rbx
0x1800295ca  mov     r9d, eax
0x1800295cd  lea     r8, WPP_788794445e0d336c1137d10bf28c55d3_Traceguids
0x1800295d4  call    WPP_SF_d
0x1800295d9  mov     rcx, rsi; hMem
0x1800295dc  call    cs:__imp_LocalFree
0x1800295e2  mov     rbx, [rsp+68h+arg_0]
0x1800295e7  mov     eax, edi
0x1800295e9  mov     rsi, [rsp+68h+arg_8]
0x1800295ee  add     rsp, 60h
0x1800295f2  pop     rdi
0x1800295f3  retn
```
