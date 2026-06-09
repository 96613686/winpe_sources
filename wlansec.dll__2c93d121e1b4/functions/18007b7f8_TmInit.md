# TmInit

- ea: `0x18007b7f8`
- end: `0x18007b8c8`
- name: `TmInit`
- size: `208`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18007a2e4`

## callees

- `0x18000892c`
- `0x180008998`
- `0x18007b7f8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007b858`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007b858`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueue` at `0x18007b840`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueue` at `0x18007b840`

## pseudocode

```c
__int64 TmInit()
{
  DWORD v0; // ebx
  PVOID *v1; // rcx
  DWORD LastError; // eax

  v0 = 0;
  v1 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_ae96259228ce3526774098cd20cb7e4b_Traceguids);
    v1 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( g_hTimerQueue )
    goto LABEL_10;
  g_hTimerQueue = CreateTimerQueue();
  if ( g_hTimerQueue )
    goto LABEL_9;
  LastError = GetLastError();
  v0 = LastError;
  v1 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v0;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_ae96259228ce3526774098cd20cb7e4b_Traceguids, LastError);
LABEL_9:
    v1 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_10:
  if ( v1 != &WPP_GLOBAL_Control && (*((_BYTE *)v1 + 28) & 1) != 0 )
    WPP_SF_d(v1[2], 12, WPP_ae96259228ce3526774098cd20cb7e4b_Traceguids, v0);
  return v0;
}

```

## disassembly

```asm
0x18007b7f8  mov     [rsp+arg_0], rbx
0x18007b7fd  push    rdi
0x18007b7fe  sub     rsp, 20h
0x18007b802  xor     ebx, ebx
0x18007b804  mov     rcx, cs:WPP_GLOBAL_Control
0x18007b80b  lea     rdi, WPP_GLOBAL_Control
0x18007b812  cmp     rcx, rdi
0x18007b815  jz      short loc_18007B837
0x18007b817  test    byte ptr [rcx+1Ch], 1
0x18007b81b  jz      short loc_18007B837
0x18007b81d  mov     rcx, [rcx+10h]
0x18007b821  lea     edx, [rbx+0Ah]
0x18007b824  lea     r8, WPP_ae96259228ce3526774098cd20cb7e4b_Traceguids
0x18007b82b  call    WPP_SF_
0x18007b830  mov     rcx, cs:WPP_GLOBAL_Control
0x18007b837  cmp     cs:g_hTimerQueue, rbx
0x18007b83e  jnz     short loc_18007B897
0x18007b840  call    cs:__imp_CreateTimerQueue
0x18007b847  nop     dword ptr [rax+rax+00h]
0x18007b84c  mov     cs:g_hTimerQueue, rax
0x18007b853  test    rax, rax
0x18007b856  jnz     short loc_18007B890
0x18007b858  call    cs:__imp_GetLastError
0x18007b85f  nop     dword ptr [rax+rax+00h]
0x18007b864  mov     ebx, eax
0x18007b866  mov     rcx, cs:WPP_GLOBAL_Control
0x18007b86d  cmp     rcx, rdi
0x18007b870  jz      short loc_18007B8BA
0x18007b872  test    byte ptr [rcx+1Ch], 2
0x18007b876  jz      short loc_18007B897
0x18007b878  mov     rcx, [rcx+10h]
0x18007b87c  lea     r8, WPP_ae96259228ce3526774098cd20cb7e4b_Traceguids
0x18007b883  mov     edx, 0Bh
0x18007b888  mov     r9d, eax
0x18007b88b  call    WPP_SF_d
0x18007b890  mov     rcx, cs:WPP_GLOBAL_Control
0x18007b897  cmp     rcx, rdi
0x18007b89a  jz      short loc_18007B8BA
0x18007b89c  test    byte ptr [rcx+1Ch], 1
0x18007b8a0  jz      short loc_18007B8BA
0x18007b8a2  mov     rcx, [rcx+10h]
0x18007b8a6  lea     r8, WPP_ae96259228ce3526774098cd20cb7e4b_Traceguids
0x18007b8ad  mov     edx, 0Ch
0x18007b8b2  mov     r9d, ebx
0x18007b8b5  call    WPP_SF_d
0x18007b8ba  mov     eax, ebx
0x18007b8bc  mov     rbx, [rsp+28h+arg_0]
0x18007b8c1  add     rsp, 20h
0x18007b8c5  pop     rdi
0x18007b8c6  retn
```
