# TraceCreateServerThread

- ea: `0x180001c20`
- end: `0x180001f8e`
- name: `TraceCreateServerThread`
- size: `878`
- prototype: `__int64 __fastcall(char, int, int)`
- caller_count: `12`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180001100`
- `0x180001640`
- `0x1800016c0`
- `0x180001740`
- `0x1800030d0`
- `0x1800046c0`
- `0x180004cc0`
- `0x180005040`
- `0x1800050c0`
- `0x180005140`
- `0x180005450`
- `0x1800056a0`

## callees

- `0x180001010`
- `0x180001c20`
- `0x180002130`
- `0x180002d90`
- `0x180003450`
- `0x180005e98`
- `0x180005f3c`
- `0x180005f70`
- `0x180009714`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180001f54`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180001f54`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001cd8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001de0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001ea3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001cd8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001de0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001ea3`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180001e78`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180001e78`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001f83`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001f83`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180001c33`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180001c33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001f66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001f66`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180001f75`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180001f75`

## pseudocode

```c
__int64 __fastcall TraceCreateServerThread(char a1, int a2, int a3)
{
  DWORD TickCount; // eax
  LPCRITICAL_SECTION Server; // rbx
  unsigned int v8; // r14d
  int v9; // edi
  int v10; // ecx
  DWORD LastError; // esi
  unsigned int v13; // r8d
  unsigned __int64 i; // rsi
  _DWORD *v15; // r14
  int v16; // r15d
  int v17; // eax
  int v18; // r13d
  DWORD v19; // eax
  __int64 v20; // rax
  __int64 v21; // rcx
  HANDLE v22; // rax
  DWORD ThreadId; // [rsp+68h] [rbp+10h] BYREF

  TickCount = GetTickCount();
  Server = g_server;
  v8 = TickCount;
  ThreadId = 0;
  if ( !g_server )
  {
    Server = (LPCRITICAL_SECTION)TraceCreateServer();
    if ( !Server )
      return 0xFFFFFFFFLL;
  }
  v9 = a2;
  if ( (a1 & 3) != 0 )
  {
LABEL_9:
    LastError = 0;
    if ( !v9 )
      AcquireWriteLock(Server);
    if ( !g_serverThread )
    {
      g_moduleRef = (HMODULE)IncrementModuleReference();
      if ( g_moduleRef )
      {
        v22 = CreateThread(0, 0, TraceServerThread, Server, 0, &ThreadId);
        g_serverThread = (__int64)v22;
        if ( v22 )
        {
          CloseHandle(v22);
        }
        else
        {
          LastError = GetLastError();
          FreeLibrary(g_moduleRef);
        }
      }
      else
      {
        LastError = 1003;
      }
    }
    if ( !a2 )
    {
      LODWORD(Server[1].DebugInfo) = 0;
      LeaveCriticalSection(Server);
    }
    return LastError;
  }
  else
  {
    v10 = g_traceTime;
    if ( g_traceTime > v8 )
    {
      v10 = v8;
      g_traceTime = v8;
    }
    if ( !a3 && v8 - v10 < 0x7530 )
      goto LABEL_7;
    if ( !a2 )
    {
      AcquireWriteLock(Server);
      v9 = 1;
    }
    if ( g_serverThread )
    {
LABEL_7:
      if ( v9 )
      {
        if ( !a2 )
        {
          LODWORD(Server[1].DebugInfo) = 0;
          LeaveCriticalSection(Server);
        }
      }
      return 0;
    }
    if ( a3 )
    {
LABEL_18:
      v13 = 3;
      g_traceTime = v8;
      g_posLast = 3;
      for ( i = (unsigned __int64)&Server[8].SpinCount; ; i += 8LL )
      {
        if ( i >= (unsigned __int64)&Server[20].SpinCount )
          goto LABEL_7;
        v15 = *(_DWORD **)i;
        if ( *(_QWORD *)i )
          break;
LABEL_25:
        ;
      }
      v16 = v15[14];
      if ( (v16 & 1) != 0 )
      {
LABEL_22:
        v17 = *(_DWORD *)(*(_QWORD *)i + 56LL);
        if ( (v17 & 6) != 0 )
          goto LABEL_9;
        if ( (v17 & 8) != 0 )
        {
          v20 = *(_QWORD *)(*(_QWORD *)i + 1080LL);
          v21 = v13++;
          g_posLast = v13;
          g_hWaitHandles[v21] = v20;
        }
        goto LABEL_25;
      }
      v15[14] = v16 & 0xFFFFFFFE;
      if ( (v16 & 8) == 0 || !TraceRegConfigClientA((__int64)v15, 0) )
      {
        if ( (v15[14] & 4) != 0 )
        {
          if ( (v16 & 4) == 0 && (unsigned int)TraceOpenClientConsoleW(Server, v15) )
            goto LABEL_35;
          v18 = v15[69] | 4;
        }
        else
        {
          v18 = 0;
          if ( (v16 & 4) != 0 )
            TraceCloseClientConsoleW(Server, v15);
        }
        if ( (v16 & 2) != 0 )
          TraceCloseClientFileW(v15);
        if ( (v15[14] & 2) != 0 )
        {
          if ( TraceCreateClientFileA((__int64)v15) )
            goto LABEL_35;
          v18 |= v15[68] | 2;
        }
        _InterlockedExchange((volatile __int32 *)&Server[2].SpinCount + (unsigned int)v15[15], v18);
      }
LABEL_35:
      v13 = g_posLast;
      goto LABEL_22;
    }
    if ( g_posLast >= (unsigned int)g_posBase )
    {
      v19 = WaitForMultipleObjectsEx(g_posLast - g_posBase, (const HANDLE *)&g_hWaitHandles[g_posBase], 0, 0, 0);
      g_traceTime = v8;
      if ( v19 != 258 )
        goto LABEL_18;
      goto LABEL_7;
    }
    if ( v9 && !a2 )
    {
      LODWORD(Server[1].DebugInfo) = 0;
      LeaveCriticalSection(Server);
    }
    return 111;
  }
}

```

## disassembly

```asm
0x180001c20  push    rbx
0x180001c22  push    rbp
0x180001c23  push    rsi
0x180001c24  push    r14
0x180001c26  push    r15
0x180001c28  sub     rsp, 30h
0x180001c2c  mov     r15d, r8d
0x180001c2f  mov     ebp, edx
0x180001c31  mov     esi, ecx
0x180001c33  call    cs:__imp_GetTickCount
0x180001c39  mov     rbx, cs:g_server
0x180001c40  mov     r14d, eax
0x180001c43  mov     [rsp+58h+ThreadId], 0
0x180001c4b  test    rbx, rbx
0x180001c4e  jz      loc_180001E0F
0x180001c54  mov     [rsp+58h+arg_0], rdi
0x180001c59  mov     edi, ebp
0x180001c5b  mov     [rsp+58h+arg_10], r12
0x180001c60  mov     [rsp+58h+arg_18], r13
0x180001c65  test    sil, 3
0x180001c69  jnz     short loc_180001CB0
0x180001c6b  mov     ecx, cs:g_traceTime
0x180001c71  cmp     ecx, r14d
0x180001c74  ja      loc_180001E2A
0x180001c7a  test    r15d, r15d
0x180001c7d  jnz     short loc_180001CE3
0x180001c7f  mov     eax, r14d
0x180001c82  sub     eax, ecx
0x180001c84  cmp     eax, 7530h
0x180001c89  jnb     short loc_180001CE3
0x180001c8b  test    edi, edi
0x180001c8d  jnz     loc_180001DD2
0x180001c93  xor     eax, eax
0x180001c95  mov     r12, [rsp+58h+arg_10]
0x180001c9a  mov     rdi, [rsp+58h+arg_0]
0x180001c9f  mov     r13, [rsp+58h+arg_18]
0x180001ca4  add     rsp, 30h
0x180001ca8  pop     r15
0x180001caa  pop     r14
0x180001cac  pop     rsi
0x180001cad  pop     rbp
0x180001cae  pop     rbx
0x180001caf  retn
0x180001cb0  xor     esi, esi
0x180001cb2  test    edi, edi
0x180001cb4  jz      loc_180001F0B
0x180001cba  mov     rax, cs:g_serverThread
0x180001cc1  test    rax, rax
0x180001cc4  jz      loc_180001F1D
0x180001cca  test    ebp, ebp
0x180001ccc  jnz     loc_180001DF3
0x180001cd2  mov     rcx, rbx; lpCriticalSection
0x180001cd5  mov     [rbx+28h], ebp
0x180001cd8  call    cs:__imp_LeaveCriticalSection
0x180001cde  jmp     loc_180001DF3
0x180001ce3  test    ebp, ebp
0x180001ce5  jz      loc_180001E38
0x180001ceb  cmp     cs:g_serverThread, 0
0x180001cf3  jnz     short loc_180001C8B
0x180001cf5  lea     r13, g_hWaitHandles
0x180001cfc  test    r15d, r15d
0x180001cff  jz      loc_180001E4A
0x180001d05  mov     r8d, 3
0x180001d0b  mov     cs:g_traceTime, r14d
0x180001d12  mov     cs:g_posLast, r8d
0x180001d19  lea     r12, [rbx+340h]
0x180001d20  lea     rsi, [rbx+160h]
0x180001d27  cmp     rsi, r12
0x180001d2a  jnb     loc_180001C8B
0x180001d30  mov     r14, [rsi]
0x180001d33  test    r14, r14
0x180001d36  jz      short loc_180001D58
0x180001d38  mov     r15d, [r14+38h]
0x180001d3c  test    r15b, 1
0x180001d40  jz      short loc_180001D5E
0x180001d42  mov     rdx, [rsi]
0x180001d45  mov     eax, [rdx+38h]
0x180001d48  test    al, 6
0x180001d4a  jnz     loc_180001CB0
0x180001d50  test    al, 8
0x180001d52  jnz     loc_180001EED
0x180001d58  add     rsi, 8
0x180001d5c  jmp     short loc_180001D27
0x180001d5e  mov     eax, r15d
0x180001d61  and     eax, 0FFFFFFFEh
0x180001d64  mov     [r14+38h], eax
0x180001d68  test    al, 8
0x180001d6a  jz      short loc_180001D7A
0x180001d6c  xor     edx, edx
0x180001d6e  mov     rcx, r14
0x180001d71  call    TraceRegConfigClientA
0x180001d76  test    eax, eax
0x180001d78  jnz     short loc_180001DC6
0x180001d7a  mov     eax, r15d
0x180001d7d  and     eax, 4
0x180001d80  test    byte ptr [r14+38h], 4
0x180001d85  jnz     loc_180001EB3
0x180001d8b  xor     r13d, r13d
0x180001d8e  test    eax, eax
0x180001d90  jz      short loc_180001D9D
0x180001d92  mov     rdx, r14
0x180001d95  mov     rcx, rbx
0x180001d98  call    TraceCloseClientConsoleW
0x180001d9d  test    r15b, 2
0x180001da1  jz      short loc_180001DAB
0x180001da3  mov     rcx, r14
0x180001da6  call    TraceCloseClientFileW
0x180001dab  test    byte ptr [r14+38h], 2
0x180001db0  jnz     loc_180001ECB
0x180001db6  mov     eax, [r14+3Ch]
0x180001dba  xchg    r13d, [rbx+rax*4+70h]
0x180001dbf  lea     r13, g_hWaitHandles
0x180001dc6  mov     r8d, cs:g_posLast
0x180001dcd  jmp     loc_180001D42
0x180001dd2  test    ebp, ebp
0x180001dd4  jnz     loc_180001C93
0x180001dda  mov     rcx, rbx; lpCriticalSection
0x180001ddd  mov     [rbx+28h], ebp
0x180001de0  call    cs:__imp_LeaveCriticalSection
0x180001de6  jmp     loc_180001C93
0x180001deb  test    edi, edi
0x180001ded  jnz     loc_180001CCA
0x180001df3  mov     eax, esi
0x180001df5  jmp     loc_180001C95
0x180001dfa  mov     rdx, r14
0x180001dfd  mov     rcx, rbx
0x180001e00  call    TraceOpenClientConsoleW
0x180001e05  test    eax, eax
0x180001e07  jz      loc_180001EBB
0x180001e0d  jmp     short loc_180001DC6
0x180001e0f  call    TraceCreateServer
0x180001e14  mov     rbx, rax
0x180001e17  test    rax, rax
0x180001e1a  jnz     loc_180001C54
0x180001e20  mov     eax, 0FFFFFFFFh
0x180001e25  jmp     loc_180001CA4
0x180001e2a  mov     ecx, r14d
0x180001e2d  mov     cs:g_traceTime, ecx
0x180001e33  jmp     loc_180001C7A
0x180001e38  mov     rcx, rbx
0x180001e3b  call    AcquireWriteLock
0x180001e40  mov     edi, 1
0x180001e45  jmp     loc_180001CEB
0x180001e4a  mov     r8d, cs:g_posBase
0x180001e51  mov     ecx, cs:g_posLast
0x180001e57  cmp     ecx, r8d
0x180001e5a  jb      short loc_180001E95
0x180001e5c  lea     rdx, ds:0[r8*8]
0x180001e64  mov     [rsp+58h+bAlertable], 0; bAlertable
0x180001e6c  sub     ecx, r8d; nCount
0x180001e6f  add     rdx, r13; lpHandles
0x180001e72  xor     r9d, r9d; dwMilliseconds
0x180001e75  xor     r8d, r8d; bWaitAll
0x180001e78  call    cs:__imp_WaitForMultipleObjectsEx
0x180001e7e  mov     cs:g_traceTime, r14d
0x180001e85  cmp     eax, 102h
0x180001e8a  jz      loc_180001C8B
0x180001e90  jmp     loc_180001D05
0x180001e95  test    edi, edi
0x180001e97  jz      short loc_180001EA9
0x180001e99  test    ebp, ebp
0x180001e9b  jnz     short loc_180001EA9
0x180001e9d  mov     rcx, rbx; lpCriticalSection
0x180001ea0  mov     [rbx+28h], ebp
0x180001ea3  call    cs:__imp_LeaveCriticalSection
0x180001ea9  mov     eax, 6Fh ; 'o'
0x180001eae  jmp     loc_180001C95
0x180001eb3  test    eax, eax
0x180001eb5  jz      loc_180001DFA
0x180001ebb  mov     r13d, [r14+114h]
0x180001ec2  or      r13d, 4
0x180001ec6  jmp     loc_180001D9D
0x180001ecb  mov     rcx, r14
0x180001ece  call    TraceCreateClientFileA
0x180001ed3  test    eax, eax
0x180001ed5  jnz     loc_180001DBF
0x180001edb  mov     eax, [r14+110h]
0x180001ee2  or      eax, 2
0x180001ee5  or      r13d, eax
0x180001ee8  jmp     loc_180001DB6
0x180001eed  mov     rax, [rdx+438h]
0x180001ef4  mov     ecx, r8d
0x180001ef7  inc     r8d
0x180001efa  mov     cs:g_posLast, r8d
0x180001f01  mov     [r13+rcx*8+0], rax
0x180001f06  jmp     loc_180001D58
0x180001f0b  mov     rcx, rbx
0x180001f0e  call    AcquireWriteLock
0x180001f13  mov     edi, 1
0x180001f18  jmp     loc_180001CBA
0x180001f1d  call    IncrementModuleReference
0x180001f22  mov     cs:g_moduleRef, rax
0x180001f29  test    rax, rax
0x180001f2c  jnz     short loc_180001F38
0x180001f2e  mov     esi, 3EBh
0x180001f33  jmp     loc_180001DEB
0x180001f38  lea     rax, [rsp+58h+ThreadId]
0x180001f3d  mov     r9, rbx; lpParameter
0x180001f40  mov     [rsp+58h+lpThreadId], rax; lpThreadId
0x180001f45  lea     r8, TraceServerThread; lpStartAddress
0x180001f4c  xor     edx, edx; dwStackSize
0x180001f4e  mov     [rsp+58h+bAlertable], esi; dwCreationFlags
0x180001f52  xor     ecx, ecx; lpThreadAttributes
0x180001f54  call    cs:__imp_CreateThread
0x180001f5a  mov     cs:g_serverThread, rax
0x180001f61  test    rax, rax
0x180001f64  jnz     short loc_180001F80
0x180001f66  call    cs:__imp_GetLastError
0x180001f6c  mov     rcx, cs:g_moduleRef; hLibModule
0x180001f73  mov     esi, eax
0x180001f75  call    cs:__imp_FreeLibrary
0x180001f7b  jmp     loc_180001DEB
0x180001f80  mov     rcx, rax; hObject
0x180001f83  call    cs:__imp_CloseHandle
0x180001f89  jmp     loc_180001DEB
```
