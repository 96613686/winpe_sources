# THREAD_MANAGER::CreateThread(ulong (*)(void *),void *)

- ea: `0x180002ab8`
- end: `0x180002bb7`
- name: `?CreateThread@THREAD_MANAGER@@QEAAHP6AKPEAX@Z0@Z`
- size: `255`
- prototype: `__int64 __fastcall(THREAD_MANAGER *__hidden this, unsigned int (*)(void *), void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800017a0`

## callees

- `0x180001770`
- `0x180001b40`
- `0x180001f4c`
- `0x180002ab8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002ba6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002ba6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002acb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002acb`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002b67`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002b67`
- `iisutil!PuDbgPrint` at `0x180002b4e`
- `iisutil!PuDbgPrint` at `0x180002b4e`

## string_xrefs

- `0x180002b47`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3tp\thread_manager.cxx`
- `0x180002b2e`: `W3TP: CreateThread thread creation\n`
- `0x180002b35`: `THREAD_MANAGER::CreateThread`

## pseudocode

```c
__int64 __fastcall THREAD_MANAGER::CreateThread(THREAD_MANAGER *this, unsigned int (*a2)(void *), void *a3)
{
  _QWORD *v5; // rax
  _QWORD *v6; // rbx
  bool v7; // zf
  DWORD TickCount; // eax
  unsigned int v9; // edx
  unsigned int v10; // edi

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  if ( *((_DWORD *)this + 12) || (v5 = operator new(0x30u), (v6 = v5) == 0) )
  {
    v10 = 0;
    goto LABEL_9;
  }
  v7 = (g_dwDebugFlags & 3) == 0;
  *(_DWORD *)v5 = 1380012116;
  v5[1] = 0;
  v5[2] = 0;
  v5[3] = 0;
  v5[4] = 0;
  *((_DWORD *)v5 + 10) = 0;
  if ( !v7 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3tp\\thread_manager.cxx",
      1577,
      "THREAD_MANAGER::CreateThread",
      "W3TP: CreateThread thread creation\n");
  v6[2] = a3;
  v6[1] = THREAD_POOL_DATA::ThreadPoolThread;
  v6[3] = this;
  TickCount = GetTickCount();
  *((_DWORD *)v6 + 9) = 0;
  *((_DWORD *)v6 + 8) = TickCount;
  v10 = THREAD_MANAGER::DoThreadCreation(this, (struct THREAD_MANAGER::THREAD_PARAM *)v6);
  if ( !v10 )
  {
    THREAD_MANAGER::THREAD_PARAM::`scalar deleting destructor'((THREAD_MANAGER::THREAD_PARAM *)v6, v9);
LABEL_9:
    *((_DWORD *)this + 13) = 0;
    goto LABEL_10;
  }
  v10 = 1;
LABEL_10:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  return v10;
}

```

## disassembly

```asm
0x180002ab8  push    rbx
0x180002aba  push    rbp
0x180002abb  push    rsi
0x180002abc  push    rdi
0x180002abd  sub     rsp, 38h
0x180002ac1  mov     rsi, rcx
0x180002ac4  mov     rdi, r8
0x180002ac7  add     rcx, 8; lpCriticalSection
0x180002acb  call    cs:__imp_EnterCriticalSection
0x180002ad1  cmp     dword ptr [rsi+30h], 0
0x180002ad5  jnz     loc_180002B99
0x180002adb  mov     ecx, 30h ; '0'; Size
0x180002ae0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002ae5  mov     rbx, rax
0x180002ae8  test    rax, rax
0x180002aeb  jz      loc_180002B99
0x180002af1  test    cs:g_dwDebugFlags, 3
0x180002af8  mov     dword ptr [rax], 52415054h
0x180002afe  mov     qword ptr [rax+8], 0
0x180002b06  mov     qword ptr [rax+10h], 0
0x180002b0e  mov     qword ptr [rax+18h], 0
0x180002b16  mov     qword ptr [rax+20h], 0
0x180002b1e  mov     dword ptr [rax+28h], 0
0x180002b25  jz      short loc_180002B54
0x180002b27  mov     rcx, cs:g_pDebug
0x180002b2e  lea     rax, aW3tpCreatethre_0; "W3TP: CreateThread thread creation\n"
0x180002b35  lea     r9, aThreadManagerC; "THREAD_MANAGER::CreateThread"
0x180002b3c  mov     [rsp+58h+var_38], rax
0x180002b41  mov     r8d, 629h
0x180002b47  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180002b4e  call    cs:__imp_PuDbgPrint
0x180002b54  lea     rax, ?ThreadPoolThread@THREAD_POOL_DATA@@SAKPEAX@Z; THREAD_POOL_DATA::ThreadPoolThread(void *)
0x180002b5b  mov     [rbx+10h], rdi
0x180002b5f  mov     [rbx+8], rax
0x180002b63  mov     [rbx+18h], rsi
0x180002b67  call    cs:__imp_GetTickCount
0x180002b6d  mov     rdx, rbx; lpParameter
0x180002b70  mov     dword ptr [rbx+24h], 0
0x180002b77  mov     rcx, rsi; this
0x180002b7a  mov     [rbx+20h], eax
0x180002b7d  call    ?DoThreadCreation@THREAD_MANAGER@@AEAAHPEAUTHREAD_PARAM@1@@Z; THREAD_MANAGER::DoThreadCreation(THREAD_MANAGER::THREAD_PARAM *)
0x180002b82  mov     edi, eax
0x180002b84  test    eax, eax
0x180002b86  jz      short loc_180002B8F
0x180002b88  mov     edi, 1
0x180002b8d  jmp     short loc_180002BA2
0x180002b8f  mov     rcx, rbx; this
0x180002b92  call    ??_GTHREAD_PARAM@THREAD_MANAGER@@QEAAPEAXI@Z; THREAD_MANAGER::THREAD_PARAM::`scalar deleting destructor'(uint)
0x180002b97  jmp     short loc_180002B9B
0x180002b99  xor     edi, edi
0x180002b9b  mov     dword ptr [rsi+34h], 0
0x180002ba2  lea     rcx, [rsi+8]; lpCriticalSection
0x180002ba6  call    cs:__imp_LeaveCriticalSection
0x180002bac  mov     eax, edi
0x180002bae  add     rsp, 38h
0x180002bb2  pop     rdi
0x180002bb3  pop     rsi
0x180002bb4  pop     rbp
0x180002bb5  pop     rbx
0x180002bb6  retn
```
