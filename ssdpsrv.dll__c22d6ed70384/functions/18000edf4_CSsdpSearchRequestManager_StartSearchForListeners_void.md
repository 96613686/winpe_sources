# CSsdpSearchRequestManager::StartSearchForListeners(void)

- ea: `0x18000edf4`
- end: `0x18000eead`
- name: `?StartSearchForListeners@CSsdpSearchRequestManager@@QEAAKXZ`
- size: `185`
- prototype: `__int64 __fastcall(CSsdpSearchRequestManager *this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000ea40`
- `0x180010890`
- `0x18001b720`

## callees

- `0x18000edf4`
- `0x180028000`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ee9a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ee9a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ee47`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ee47`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000ee8a`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000ee8a`

## pseudocode

```c
__int64 __fastcall CSsdpSearchRequestManager::StartSearchForListeners(CSsdpSearchRequestManager *this)
{
  bool v2; // zf

  if ( !*((_DWORD *)this + 168) )
  {
    if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, WPP_a39c2586c9f736b52f5e075cbea19de6_Traceguids);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 688));
    v2 = *((_QWORD *)this + 92) == 0;
    *((_DWORD *)this + 182) = 1;
    if ( v2 && *((_QWORD *)this + 93) )
      *((_QWORD *)this + 92) = CreateThread(
                                 0,
                                 0,
                                 (LPTHREAD_START_ROUTINE)CSsdpSearchRequestManager::SendSearchForListenersThread,
                                 this,
                                 0,
                                 (LPDWORD)this + 14);
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 688));
  }
  return 0;
}

```

## disassembly

```asm
0x18000edf4  mov     [rsp+arg_0], rbx
0x18000edf9  push    rdi
0x18000edfa  sub     rsp, 30h
0x18000edfe  mov     eax, [rcx+2A0h]
0x18000ee04  mov     rbx, rcx
0x18000ee07  test    eax, eax
0x18000ee09  jnz     loc_18000EEA0
0x18000ee0f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ee16  lea     rax, WPP_GLOBAL_Control
0x18000ee1d  cmp     rcx, rax
0x18000ee20  jz      short loc_18000EE3D
0x18000ee22  test    byte ptr [rcx+1Ch], 8
0x18000ee26  jz      short loc_18000EE3D
0x18000ee28  mov     rcx, [rcx+10h]
0x18000ee2c  lea     r8, WPP_a39c2586c9f736b52f5e075cbea19de6_Traceguids
0x18000ee33  mov     edx, 3Ah ; ':'
0x18000ee38  call    WPP_SF_
0x18000ee3d  lea     rdi, [rbx+2B0h]
0x18000ee44  mov     rcx, rdi; lpCriticalSection
0x18000ee47  call    cs:__imp_EnterCriticalSection
0x18000ee4d  cmp     qword ptr [rbx+2E0h], 0
0x18000ee55  mov     dword ptr [rbx+2D8h], 1
0x18000ee5f  jnz     short loc_18000EE97
0x18000ee61  cmp     qword ptr [rbx+2E8h], 0
0x18000ee69  jz      short loc_18000EE97
0x18000ee6b  lea     rax, [rbx+38h]
0x18000ee6f  mov     r9, rbx; lpParameter
0x18000ee72  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x18000ee77  lea     r8, ?SendSearchForListenersThread@CSsdpSearchRequestManager@@CAKPEAX@Z; lpStartAddress
0x18000ee7e  xor     edx, edx; dwStackSize
0x18000ee80  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x18000ee88  xor     ecx, ecx; lpThreadAttributes
0x18000ee8a  call    cs:__imp_CreateThread
0x18000ee90  mov     [rbx+2E0h], rax
0x18000ee97  mov     rcx, rdi; lpCriticalSection
0x18000ee9a  call    cs:__imp_LeaveCriticalSection
0x18000eea0  mov     rbx, [rsp+38h+arg_0]
0x18000eea5  xor     eax, eax
0x18000eea7  add     rsp, 30h
0x18000eeab  pop     rdi
0x18000eeac  retn
```
