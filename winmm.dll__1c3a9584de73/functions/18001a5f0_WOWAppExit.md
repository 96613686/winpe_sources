# WOWAppExit

- ea: `0x18001a5f0`
- end: `0x18001a756`
- name: `WOWAppExit`
- size: `358`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180009120`
- `0x180009a90`
- `0x180012cec`
- `0x180015eb4`
- `0x18001a5f0`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a644`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a6e3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a644`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a6e3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a6c4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a700`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a6c4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a700`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001a732`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001a732`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001a71d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001a71d`
- `WINMMBASE!winmmbaseFreeMMEHandles` at `0x18001a710`
- `WINMMBASE!winmmbaseFreeMMEHandles` at `0x18001a710`

## string_xrefs

- `0x18001a716`: `avicap32.dll`

## pseudocode

```c
HMODULE __fastcall WOWAppExit(__int64 a1)
{
  unsigned int v2; // edx
  MCIDEVICEID i; // ebx
  __int64 v4; // r9
  HMODULE result; // rax

  if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_b9c43a85d2863af168ea09e2fa4a4263_Traceguids, a1);
  }
  EnterCriticalSection(&mciCritSec);
  v2 = MCI_wNextDeviceID;
  for ( i = 1; i < v2; ++i )
  {
    if ( i )
    {
      if ( i < v2 )
      {
        v4 = *((_QWORD *)MCI_lpDeviceList + i);
        if ( v4 )
        {
          if ( *(_QWORD *)(v4 + 80) == a1 )
          {
            if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_Sd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                14,
                (unsigned int)WPP_b9c43a85d2863af168ea09e2fa4a4263_Traceguids,
                *(_QWORD *)(v4 + 8),
                i);
            }
            LeaveCriticalSection(&mciCritSec);
            mciSendCommandW(i, 0x804u, 0, 0);
            EnterCriticalSection(&mciCritSec);
            v2 = MCI_wNextDeviceID;
          }
        }
      }
    }
  }
  LeaveCriticalSection(&mciCritSec);
  TimeCleanup((unsigned int)a1);
  winmmbaseFreeMMEHandles(a1);
  result = GetModuleHandleW(L"avicap32.dll");
  if ( result )
  {
    result = (HMODULE)GetProcAddress(result, "AppCleanup");
    if ( result )
      return (HMODULE)((__int64 (__fastcall *)(__int64))result)(a1);
  }
  return result;
}

```

## disassembly

```asm
0x18001a5f0  mov     [rsp+arg_0], rbx
0x18001a5f5  mov     [rsp+arg_8], rdi
0x18001a5fa  push    r14
0x18001a5fc  sub     rsp, 30h
0x18001a600  mov     rdi, rcx
0x18001a603  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a60a  lea     r14, WPP_GLOBAL_Control
0x18001a611  cmp     rcx, r14
0x18001a614  jz      short loc_18001A63D
0x18001a616  test    dword ptr [rcx+1Ch], 400000h
0x18001a61d  jz      short loc_18001A63D
0x18001a61f  cmp     byte ptr [rcx+19h], 4
0x18001a623  jb      short loc_18001A63D
0x18001a625  mov     rcx, [rcx+10h]
0x18001a629  lea     r8, WPP_b9c43a85d2863af168ea09e2fa4a4263_Traceguids
0x18001a630  mov     edx, 0Dh
0x18001a635  mov     r9, rdi
0x18001a638  call    WPP_SF_q
0x18001a63d  lea     rcx, mciCritSec; lpCriticalSection
0x18001a644  call    cs:__imp_EnterCriticalSection
0x18001a64a  mov     edx, cs:MCI_wNextDeviceID
0x18001a650  mov     ebx, 1
0x18001a655  cmp     edx, ebx
0x18001a657  jbe     loc_18001A6F9
0x18001a65d  test    ebx, ebx
0x18001a65f  jz      loc_18001A6EF
0x18001a665  cmp     ebx, edx
0x18001a667  jnb     loc_18001A6EF
0x18001a66d  mov     rax, cs:MCI_lpDeviceList
0x18001a674  mov     ecx, ebx
0x18001a676  mov     r9, [rax+rcx*8]
0x18001a67a  test    r9, r9
0x18001a67d  jz      short loc_18001A6EF
0x18001a67f  cmp     [r9+50h], rdi
0x18001a683  jnz     short loc_18001A6EF
0x18001a685  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a68c  cmp     rcx, r14
0x18001a68f  jz      short loc_18001A6BD
0x18001a691  test    dword ptr [rcx+1Ch], 400000h
0x18001a698  jz      short loc_18001A6BD
0x18001a69a  cmp     byte ptr [rcx+19h], 2
0x18001a69e  jb      short loc_18001A6BD
0x18001a6a0  mov     r9, [r9+8]
0x18001a6a4  lea     r8, WPP_b9c43a85d2863af168ea09e2fa4a4263_Traceguids
0x18001a6ab  mov     rcx, [rcx+10h]
0x18001a6af  mov     edx, 0Eh
0x18001a6b4  mov     [rsp+38h+var_18], ebx
0x18001a6b8  call    WPP_SF_Sd
0x18001a6bd  lea     rcx, mciCritSec; lpCriticalSection
0x18001a6c4  call    cs:__imp_LeaveCriticalSection
0x18001a6ca  xor     r9d, r9d; dwParam2
0x18001a6cd  xor     r8d, r8d; dwParam1
0x18001a6d0  mov     edx, 804h; uMsg
0x18001a6d5  mov     ecx, ebx; mciId
0x18001a6d7  call    mciSendCommandW
0x18001a6dc  lea     rcx, mciCritSec; lpCriticalSection
0x18001a6e3  call    cs:__imp_EnterCriticalSection
0x18001a6e9  mov     edx, cs:MCI_wNextDeviceID
0x18001a6ef  inc     ebx
0x18001a6f1  cmp     ebx, edx
0x18001a6f3  jb      loc_18001A65D
0x18001a6f9  lea     rcx, mciCritSec; lpCriticalSection
0x18001a700  call    cs:__imp_LeaveCriticalSection
0x18001a706  mov     ecx, edi
0x18001a708  call    TimeCleanup
0x18001a70d  mov     rcx, rdi
0x18001a710  call    cs:__imp_winmmbaseFreeMMEHandles
0x18001a716  lea     rcx, aAvicap32Dll; "avicap32.dll"
0x18001a71d  call    cs:__imp_GetModuleHandleW
0x18001a723  test    rax, rax
0x18001a726  jz      short loc_18001A745
0x18001a728  lea     rdx, aAppcleanup; "AppCleanup"
0x18001a72f  mov     rcx, rax; hModule
0x18001a732  call    cs:__imp_GetProcAddress
0x18001a738  test    rax, rax
0x18001a73b  jz      short loc_18001A745
0x18001a73d  mov     rcx, rdi
0x18001a740  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a745  mov     rbx, [rsp+38h+arg_0]
0x18001a74a  mov     rdi, [rsp+38h+arg_8]
0x18001a74f  add     rsp, 30h
0x18001a753  pop     r14
0x18001a755  retn
```
