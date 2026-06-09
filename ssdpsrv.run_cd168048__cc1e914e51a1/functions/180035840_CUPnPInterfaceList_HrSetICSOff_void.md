# CUPnPInterfaceList::HrSetICSOff(void)

- ea: `0x180035840`
- end: `0x18003592a`
- name: `?HrSetICSOff@CUPnPInterfaceList@@QEAAJXZ`
- size: `234`
- prototype: `__int64 __fastcall(CUPnPInterfaceList *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18002ef60`

## callees

- `0x180029df0`
- `0x180035840`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800358d5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800358d5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180035859`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180035859`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180035874`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180035874`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800358be`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800358be`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180035887`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180035887`

## pseudocode

```c
__int64 __fastcall CUPnPInterfaceList::HrSetICSOff(CUPnPInterfaceList *this)
{
  void *v2; // rcx
  DWORD ThreadId; // [rsp+40h] [rbp+8h] BYREF

  ThreadId = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)this + 2);
  v2 = (void *)*((_QWORD *)this + 31);
  if ( v2 )
  {
    WaitForSingleObject(v2, 0xFFFFFFFF);
    CloseHandle(*((HANDLE *)this + 31));
    *((_QWORD *)this + 31) = 0;
  }
  *((_QWORD *)this + 31) = CreateThread(0, 0, ExecIcsChangeInterfaces, this, 0, &ThreadId);
  LeaveCriticalSection((LPCRITICAL_SECTION)this + 2);
  if ( !*((_QWORD *)this + 31)
    && WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_be91c1c7b6083381c2d2431ae6263e74_Traceguids);
  }
  return 0;
}

```

## disassembly

```asm
0x180035840  mov     [rsp+arg_8], rbx
0x180035845  push    rdi
0x180035846  sub     rsp, 30h
0x18003584a  mov     rbx, rcx
0x18003584d  mov     [rsp+38h+ThreadId], 0
0x180035855  add     rcx, 50h ; 'P'; lpCriticalSection
0x180035859  call    cs:__imp_EnterCriticalSection
0x180035860  nop     dword ptr [rax+rax+00h]
0x180035865  mov     rcx, [rbx+0F8h]; hHandle
0x18003586c  test    rcx, rcx
0x18003586f  jz      short loc_18003589E
0x180035871  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180035874  call    cs:__imp_WaitForSingleObject
0x18003587b  nop     dword ptr [rax+rax+00h]
0x180035880  mov     rcx, [rbx+0F8h]; hObject
0x180035887  call    cs:__imp_CloseHandle
0x18003588e  nop     dword ptr [rax+rax+00h]
0x180035893  mov     qword ptr [rbx+0F8h], 0
0x18003589e  lea     rax, [rsp+38h+ThreadId]
0x1800358a3  mov     r9, rbx; lpParameter
0x1800358a6  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x1800358ab  lea     r8, ?ExecIcsChangeInterfaces@@YAKPEAX@Z; lpStartAddress
0x1800358b2  xor     edx, edx; dwStackSize
0x1800358b4  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x1800358bc  xor     ecx, ecx; lpThreadAttributes
0x1800358be  call    cs:__imp_CreateThread
0x1800358c5  nop     dword ptr [rax+rax+00h]
0x1800358ca  lea     rcx, [rbx+50h]; lpCriticalSection
0x1800358ce  mov     [rbx+0F8h], rax
0x1800358d5  call    cs:__imp_LeaveCriticalSection
0x1800358dc  nop     dword ptr [rax+rax+00h]
0x1800358e1  cmp     qword ptr [rbx+0F8h], 0
0x1800358e9  jnz     short loc_18003591C
0x1800358eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800358f2  lea     rax, WPP_GLOBAL_Control
0x1800358f9  cmp     rcx, rax
0x1800358fc  jz      short loc_18003591C
0x1800358fe  test    dword ptr [rcx+1Ch], 200h
0x180035905  jz      short loc_18003591C
0x180035907  mov     rcx, [rcx+10h]
0x18003590b  lea     r8, WPP_be91c1c7b6083381c2d2431ae6263e74_Traceguids
0x180035912  mov     edx, 16h
0x180035917  call    WPP_SF_
0x18003591c  mov     rbx, [rsp+38h+arg_8]
0x180035921  xor     eax, eax
0x180035923  add     rsp, 30h
0x180035927  pop     rdi
0x180035928  retn
```
