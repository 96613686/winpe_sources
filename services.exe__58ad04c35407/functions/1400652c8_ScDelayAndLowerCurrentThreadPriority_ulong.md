# ScDelayAndLowerCurrentThreadPriority(ulong)

- ea: `0x1400652c8`
- end: `0x140065394`
- name: `?ScDelayAndLowerCurrentThreadPriority@@YAXK@Z`
- size: `204`
- prototype: `void __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140065d60`

## callees

- `0x140004c58`
- `0x1400652c8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140065315`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140065315`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1400652f2`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1400652f2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1400652e4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140065342`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1400652e4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140065342`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1400652de`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1400652de`
- `ntdll!NtSetInformationThread` at `0x14006535a`
- `ntdll!NtSetInformationThread` at `0x14006535a`

## pseudocode

```c
void __fastcall ScDelayAndLowerCurrentThreadPriority()
{
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  HANDLE v2; // rax
  NTSTATUS v3; // eax
  int ThreadInformation; // [rsp+30h] [rbp+8h] BYREF

  ThreadInformation = 0;
  Sleep(0x7530u);
  CurrentThread = GetCurrentThread();
  if ( !SetThreadPriority(CurrentThread, -2)
    && WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
    && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
  {
    LastError = GetLastError();
    WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 77, WPP_1af9861440053f7472b6b75dd72fc49f_Traceguids, LastError);
  }
  ThreadInformation = 3;
  v2 = GetCurrentThread();
  v3 = NtSetInformationThread(v2, ThreadPagePriority, &ThreadInformation, 4u);
  if ( v3 < 0
    && WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
    && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 78, WPP_1af9861440053f7472b6b75dd72fc49f_Traceguids, (unsigned int)v3);
  }
}

```

## disassembly

```asm
0x1400652c8  mov     [rsp+ThreadInformation], ecx
0x1400652cc  push    rbx
0x1400652cd  sub     rsp, 20h
0x1400652d1  mov     ecx, 7530h; dwMilliseconds
0x1400652d6  mov     [rsp+28h+ThreadInformation], 0
0x1400652de  call    cs:__imp_Sleep
0x1400652e4  call    cs:__imp_GetCurrentThread
0x1400652ea  mov     rcx, rax; hThread
0x1400652ed  mov     edx, 0FFFFFFFEh; nPriority
0x1400652f2  call    cs:__imp_SetThreadPriority
0x1400652f8  lea     rbx, WPP_GLOBAL_Control
0x1400652ff  test    eax, eax
0x140065301  jnz     short loc_14006533A
0x140065303  mov     rax, cs:WPP_GLOBAL_Control
0x14006530a  cmp     rax, rbx
0x14006530d  jz      short loc_14006533A
0x14006530f  test    byte ptr [rax+1Ch], 1
0x140065313  jz      short loc_14006533A
0x140065315  call    cs:__imp_GetLastError
0x14006531b  mov     rcx, cs:WPP_GLOBAL_Control
0x140065322  lea     r8, WPP_1af9861440053f7472b6b75dd72fc49f_Traceguids
0x140065329  mov     edx, 4Dh ; 'M'
0x14006532e  mov     r9d, eax
0x140065331  mov     rcx, [rcx+10h]
0x140065335  call    WPP_SF_d
0x14006533a  mov     [rsp+28h+ThreadInformation], 3
0x140065342  call    cs:__imp_GetCurrentThread
0x140065348  mov     r9d, 4; ThreadInformationLength
0x14006534e  lea     r8, [rsp+28h+ThreadInformation]; ThreadInformation
0x140065353  mov     rcx, rax; ThreadHandle
0x140065356  lea     edx, [r9+14h]; ThreadInformationClass
0x14006535a  call    cs:__imp_NtSetInformationThread
0x140065360  test    eax, eax
0x140065362  jns     short loc_14006538E
0x140065364  mov     rcx, cs:WPP_GLOBAL_Control
0x14006536b  cmp     rcx, rbx
0x14006536e  jz      short loc_14006538E
0x140065370  test    byte ptr [rcx+1Ch], 1
0x140065374  jz      short loc_14006538E
0x140065376  mov     rcx, [rcx+10h]
0x14006537a  lea     r8, WPP_1af9861440053f7472b6b75dd72fc49f_Traceguids
0x140065381  mov     edx, 4Eh ; 'N'
0x140065386  mov     r9d, eax
0x140065389  call    WPP_SF_d
0x14006538e  add     rsp, 20h
0x140065392  pop     rbx
0x140065393  retn
```
