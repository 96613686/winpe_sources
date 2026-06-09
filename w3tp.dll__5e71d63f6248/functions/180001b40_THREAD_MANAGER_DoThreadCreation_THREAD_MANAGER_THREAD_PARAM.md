# THREAD_MANAGER::DoThreadCreation(THREAD_MANAGER::THREAD_PARAM *)

- ea: `0x180001b40`
- end: `0x180001d71`
- name: `?DoThreadCreation@THREAD_MANAGER@@AEAAHPEAUTHREAD_PARAM@1@@Z`
- size: `561`
- prototype: `__int64 __fastcall(THREAD_MANAGER *__hidden this, struct THREAD_MANAGER::THREAD_PARAM *lpParameter)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180001450`
- `0x180002ab8`

## callees

- `0x180001690`
- `0x180001b40`
- `0x180001d80`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180001c75`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180001c75`
- `api-ms-win-core-processthreads-l1-1-0!CreateRemoteThreadEx` at `0x180001cad`
- `api-ms-win-core-processthreads-l1-1-0!CreateRemoteThreadEx` at `0x180001cad`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180001c66`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180001c66`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180001b5e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180001b5e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001cbf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001cbf`
- `iisutil!PuDbgPrint` at `0x180001b94`
- `iisutil!PuDbgPrint` at `0x180001cf5`
- `iisutil!PuDbgPrint` at `0x180001d4e`
- `iisutil!PuDbgPrint` at `0x180001b94`
- `iisutil!PuDbgPrint` at `0x180001cf5`
- `iisutil!PuDbgPrint` at `0x180001d4e`

## string_xrefs

- `0x180001b8d`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3tp\thread_manager.cxx`
- `0x180001cee`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3tp\thread_manager.cxx`
- `0x180001d47`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3tp\thread_manager.cxx`
- `0x180001b74`: `W3TP: Signaled a thread to be unparked\n`
- `0x180001b7b`: `THREAD_MANAGER::DoThreadCreation`
- `0x180001cdc`: `THREAD_MANAGER::DoThreadCreation`
- `0x180001d35`: `THREAD_MANAGER::DoThreadCreation`
- `0x180001cd5`: `W3TP: Created a new thread\n`
- `0x180001d2a`: `W3TP: CreateThread, increment count on node %d\n`

## pseudocode

```c
__int64 __fastcall THREAD_MANAGER::DoThreadCreation(
        THREAD_MANAGER *this,
        struct THREAD_MANAGER::THREAD_PARAM *lpParameter)
{
  __int64 result; // rax
  __int64 v5; // r9
  struct _PROC_THREAD_ATTRIBUTE_LIST *lpAttributeList; // r14
  __int64 v7; // r8
  __int64 v8; // rax
  unsigned int v9; // edi
  HANDLE CurrentProcess; // rax
  _PROCESSOR_NUMBER v11; // [rsp+80h] [rbp+18h] BYREF

  if ( *((_DWORD *)this + 20) )
  {
    SetEvent(*((HANDLE *)this + 11));
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3tp\\thread_manager.cxx",
        1311,
        "THREAD_MANAGER::DoThreadCreation",
        "W3TP: Signaled a thread to be unparked\n");
    return 0;
  }
  else
  {
    v5 = *((_QWORD *)this + 17);
    if ( v5 )
    {
      v7 = *(unsigned int *)(v5 + 12);
      v8 = *(_QWORD *)(v5 + 16);
      *(_DWORD *)(v5 + 12) = ((int)v7 + 1) % (unsigned int)*(unsigned __int16 *)(v5 + 8);
      lpAttributeList = **(struct _PROC_THREAD_ATTRIBUTE_LIST ***)(v8 + 8 * v7);
    }
    else
    {
      lpAttributeList = 0;
      if ( *((_DWORD *)this + 36) )
      {
        THREAD_MANAGER::GetNextIdealNodeAndCpu(this, (unsigned int *)&v11.Group);
        if ( !THREAD_MANAGER::SetReusableThreadAttributeListWithIdealCpu(this, &v11) )
          return 0;
        lpAttributeList = (struct _PROC_THREAD_ATTRIBUTE_LIST *)*((_QWORD *)this + 21);
        *((_DWORD *)lpParameter + 10) = 0;
      }
    }
    if ( *((_QWORD *)this + 17) || *((_DWORD *)this + 36) )
    {
      v9 = *(_DWORD *)(*((_QWORD *)this + 14) + 64LL);
      CurrentProcess = GetCurrentProcess();
      result = (__int64)CreateRemoteThreadEx(
                          CurrentProcess,
                          0,
                          v9,
                          THREAD_MANAGER::ThreadManagerThread,
                          lpParameter,
                          v9 != 0 ? 0x10000 : 0,
                          lpAttributeList,
                          0);
    }
    else
    {
      result = (__int64)CreateThread(
                          0,
                          *(unsigned int *)(*((_QWORD *)this + 14) + 64LL),
                          THREAD_MANAGER::ThreadManagerThread,
                          lpParameter,
                          *(_DWORD *)(*((_QWORD *)this + 14) + 64LL) != 0 ? 0x10000 : 0,
                          0);
    }
    if ( result )
    {
      CloseHandle((HANDLE)result);
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3tp\\thread_manager.cxx",
          1376,
          "THREAD_MANAGER::DoThreadCreation",
          "W3TP: Created a new thread\n");
      _InterlockedIncrement((volatile signed __int32 *)this + 19);
      if ( *((_DWORD *)this + 36) )
      {
        _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)this + 19) + 20LL));
        if ( (g_dwDebugFlags & 3) != 0 )
          PuDbgPrint(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3tp\\thread_manager.cxx",
            1384,
            "THREAD_MANAGER::DoThreadCreation",
            "W3TP: CreateThread, increment count on node %d\n",
            0);
      }
      return 1;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180001b40  push    rbx
0x180001b42  push    rsi
0x180001b43  push    r15
0x180001b45  sub     rsp, 50h
0x180001b49  xor     esi, esi
0x180001b4b  mov     r15, rdx
0x180001b4e  mov     rbx, rcx
0x180001b51  mov     [rsp+68h+arg_0], esi
0x180001b55  cmp     [rcx+50h], esi
0x180001b58  jz      short loc_180001BA1
0x180001b5a  mov     rcx, [rcx+58h]; hEvent
0x180001b5e  call    cs:__imp_SetEvent
0x180001b64  test    cs:g_dwDebugFlags, 3
0x180001b6b  jz      short loc_180001B9A
0x180001b6d  mov     rcx, cs:g_pDebug
0x180001b74  lea     rax, aW3tpSignaledAT; "W3TP: Signaled a thread to be unparked"...
0x180001b7b  lea     r9, aThreadManagerD_0; "THREAD_MANAGER::DoThreadCreation"
0x180001b82  mov     qword ptr [rsp+68h+dwCreationFlags], rax
0x180001b87  mov     r8d, 51Fh
0x180001b8d  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180001b94  call    cs:__imp_PuDbgPrint
0x180001b9a  xor     eax, eax
0x180001b9c  jmp     loc_180001D68
0x180001ba1  mov     r9, [rcx+88h]
0x180001ba8  mov     [rsp+68h+arg_8], rbp
0x180001bad  mov     [rsp+68h+var_20], rdi
0x180001bb2  mov     [rsp+68h+var_28], r14
0x180001bb7  test    r9, r9
0x180001bba  jnz     short loc_180001C07
0x180001bbc  xor     r14d, r14d
0x180001bbf  cmp     [rcx+90h], esi
0x180001bc5  jz      short loc_180001C27
0x180001bc7  lea     r8, [rsp+68h+arg_0]
0x180001bcc  xor     edi, edi
0x180001bce  lea     rdx, [rsp+68h+arg_10]; unsigned int *
0x180001bd6  call    ?GetNextIdealNodeAndCpu@THREAD_MANAGER@@AEAA?AU_PROCESSOR_NUMBER@@AEAK@Z; THREAD_MANAGER::GetNextIdealNodeAndCpu(ulong &)
0x180001bdb  lea     rdx, [rsp+68h+arg_10]; struct _PROCESSOR_NUMBER *
0x180001be3  mov     rcx, rbx; this
0x180001be6  call    ?SetReusableThreadAttributeListWithIdealCpu@THREAD_MANAGER@@AEAAHPEAU_PROCESSOR_NUMBER@@@Z; THREAD_MANAGER::SetReusableThreadAttributeListWithIdealCpu(_PROCESSOR_NUMBER *)
0x180001beb  test    eax, eax
0x180001bed  jz      short loc_180001C00
0x180001bef  mov     r14, [rbx+0A8h]
0x180001bf6  mov     esi, [rsp+68h+arg_0]
0x180001bfa  mov     [r15+28h], esi
0x180001bfe  jmp     short loc_180001C27
0x180001c00  mov     eax, edi
0x180001c02  jmp     loc_180001D59
0x180001c07  mov     r8d, [r9+0Ch]
0x180001c0b  xor     edx, edx
0x180001c0d  movzx   ecx, word ptr [r9+8]
0x180001c12  lea     eax, [r8+1]
0x180001c16  div     ecx
0x180001c18  mov     rax, [r9+10h]
0x180001c1c  mov     [r9+0Ch], edx
0x180001c20  mov     rcx, [rax+r8*8]
0x180001c24  mov     r14, [rcx]
0x180001c27  cmp     qword ptr [rbx+88h], 0
0x180001c2f  jnz     short loc_180001C6E
0x180001c31  cmp     dword ptr [rbx+90h], 0
0x180001c38  jnz     short loc_180001C6E
0x180001c3a  mov     rax, [rbx+70h]
0x180001c3e  lea     r8, ?ThreadManagerThread@THREAD_MANAGER@@CAKPEAX@Z; lpStartAddress
0x180001c45  mov     [rsp+68h+lpThreadId], 0; lpThreadId
0x180001c4e  mov     r9, r15; lpParameter
0x180001c51  mov     edx, [rax+40h]; dwStackSize
0x180001c54  mov     eax, edx
0x180001c56  neg     eax
0x180001c58  sbb     ecx, ecx
0x180001c5a  and     ecx, 10000h
0x180001c60  mov     [rsp+68h+dwCreationFlags], ecx; dwCreationFlags
0x180001c64  xor     ecx, ecx; lpThreadAttributes
0x180001c66  call    cs:__imp_CreateThread
0x180001c6c  jmp     short loc_180001CB3
0x180001c6e  mov     rax, [rbx+70h]
0x180001c72  mov     edi, [rax+40h]
0x180001c75  call    cs:__imp_GetCurrentProcess
0x180001c7b  mov     [rsp+68h+var_30], 0; lpThreadId
0x180001c84  lea     r9, ?ThreadManagerThread@THREAD_MANAGER@@CAKPEAX@Z; lpStartAddress
0x180001c8b  mov     ecx, edi
0x180001c8d  mov     [rsp+68h+lpAttributeList], r14; lpAttributeList
0x180001c92  neg     ecx
0x180001c94  mov     r8d, edi; dwStackSize
0x180001c97  mov     rcx, rax; hProcess
0x180001c9a  sbb     edx, edx
0x180001c9c  and     edx, 10000h
0x180001ca2  mov     dword ptr [rsp+68h+lpThreadId], edx; dwCreationFlags
0x180001ca6  xor     edx, edx; lpThreadAttributes
0x180001ca8  mov     qword ptr [rsp+68h+dwCreationFlags], r15; lpParameter
0x180001cad  call    cs:__imp_CreateRemoteThreadEx
0x180001cb3  test    rax, rax
0x180001cb6  jz      loc_180001D59
0x180001cbc  mov     rcx, rax; hObject
0x180001cbf  call    cs:__imp_CloseHandle
0x180001cc5  test    cs:g_dwDebugFlags, 3
0x180001ccc  jz      short loc_180001CFB
0x180001cce  mov     rcx, cs:g_pDebug
0x180001cd5  lea     rax, aW3tpCreatedANe; "W3TP: Created a new thread\n"
0x180001cdc  lea     r9, aThreadManagerD_0; "THREAD_MANAGER::DoThreadCreation"
0x180001ce3  mov     qword ptr [rsp+68h+dwCreationFlags], rax
0x180001ce8  mov     r8d, 560h
0x180001cee  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180001cf5  call    cs:__imp_PuDbgPrint
0x180001cfb  lock inc dword ptr [rbx+4Ch]
0x180001cff  cmp     dword ptr [rbx+90h], 0
0x180001d06  jz      short loc_180001D54
0x180001d08  mov     eax, esi
0x180001d0a  lea     rcx, [rax+rax*2]
0x180001d0e  mov     rax, [rbx+98h]
0x180001d15  lock inc dword ptr [rax+rcx*8+14h]
0x180001d1a  test    cs:g_dwDebugFlags, 3
0x180001d21  jz      short loc_180001D54
0x180001d23  mov     rcx, cs:g_pDebug
0x180001d2a  lea     rax, aW3tpCreatethre; "W3TP: CreateThread, increment count on "...
0x180001d31  mov     dword ptr [rsp+68h+lpThreadId], esi
0x180001d35  lea     r9, aThreadManagerD_0; "THREAD_MANAGER::DoThreadCreation"
0x180001d3c  mov     r8d, 568h
0x180001d42  mov     qword ptr [rsp+68h+dwCreationFlags], rax
0x180001d47  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180001d4e  call    cs:__imp_PuDbgPrint
0x180001d54  mov     eax, 1
0x180001d59  mov     rdi, [rsp+68h+var_20]
0x180001d5e  mov     rbp, [rsp+68h+arg_8]
0x180001d63  mov     r14, [rsp+68h+var_28]
0x180001d68  add     rsp, 50h
0x180001d6c  pop     r15
0x180001d6e  pop     rsi
0x180001d6f  pop     rbx
0x180001d70  retn
```
