# CUPnPInterfaceList::HrSetICSInterfaces(long,_GUID *)

- ea: `0x180055ec8`
- end: `0x180055fb6`
- name: `?HrSetICSInterfaces@CUPnPInterfaceList@@QEAAJJPEAU_GUID@@@Z`
- size: `238`
- prototype: `__int64 __fastcall(CUPnPInterfaceList *__hidden this, int, struct _GUID *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180050430`

## callees

- `0x18003c018`
- `0x180055ec8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180055ee5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180055ee5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180055f00`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180055f00`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180055f61`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180055f61`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180055f4a`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180055f4a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180055f13`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180055f13`

## pseudocode

```c
__int64 __fastcall CUPnPInterfaceList::HrSetICSInterfaces(CUPnPInterfaceList *this, __int64 a2, struct _GUID *a3)
{
  void *v4; // rcx
  DWORD ThreadId; // [rsp+48h] [rbp+10h] BYREF

  ThreadId = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)this + 2);
  v4 = (void *)*((_QWORD *)this + 31);
  if ( v4 )
  {
    WaitForSingleObject(v4, 0xFFFFFFFF);
    CloseHandle(*((HANDLE *)this + 31));
    *((_QWORD *)this + 31) = 0;
  }
  *((_QWORD *)this + 31) = CreateThread(0, 0, ExecIcsChangeInterfaces, this, 0, &ThreadId);
  LeaveCriticalSection((LPCRITICAL_SECTION)this + 2);
  if ( !*((_QWORD *)this + 31)
    && WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_be91c1c7b6083381c2d2431ae6263e74_Traceguids);
  }
  return 0;
}

```

## disassembly

```asm
0x180055ec8  mov     [rsp+arg_0], rbx
0x180055ecd  mov     [rsp+ThreadId], edx
0x180055ed1  push    rdi
0x180055ed2  sub     rsp, 30h
0x180055ed6  mov     rbx, rcx
0x180055ed9  mov     [rsp+38h+ThreadId], 0
0x180055ee1  add     rcx, 50h ; 'P'; lpCriticalSection
0x180055ee5  call    cs:__imp_EnterCriticalSection
0x180055eec  nop     dword ptr [rax+rax+00h]
0x180055ef1  mov     rcx, [rbx+0F8h]; hHandle
0x180055ef8  test    rcx, rcx
0x180055efb  jz      short loc_180055F2A
0x180055efd  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180055f00  call    cs:__imp_WaitForSingleObject
0x180055f07  nop     dword ptr [rax+rax+00h]
0x180055f0c  mov     rcx, [rbx+0F8h]; hObject
0x180055f13  call    cs:__imp_CloseHandle
0x180055f1a  nop     dword ptr [rax+rax+00h]
0x180055f1f  mov     qword ptr [rbx+0F8h], 0
0x180055f2a  lea     rax, [rsp+38h+ThreadId]
0x180055f2f  mov     r9, rbx; lpParameter
0x180055f32  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x180055f37  lea     r8, ?ExecIcsChangeInterfaces@@YAKPEAX@Z; lpStartAddress
0x180055f3e  xor     edx, edx; dwStackSize
0x180055f40  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x180055f48  xor     ecx, ecx; lpThreadAttributes
0x180055f4a  call    cs:__imp_CreateThread
0x180055f51  nop     dword ptr [rax+rax+00h]
0x180055f56  lea     rcx, [rbx+50h]; lpCriticalSection
0x180055f5a  mov     [rbx+0F8h], rax
0x180055f61  call    cs:__imp_LeaveCriticalSection
0x180055f68  nop     dword ptr [rax+rax+00h]
0x180055f6d  cmp     qword ptr [rbx+0F8h], 0
0x180055f75  jnz     short loc_180055FA8
0x180055f77  mov     rcx, cs:WPP_GLOBAL_Control
0x180055f7e  lea     rax, WPP_GLOBAL_Control
0x180055f85  cmp     rcx, rax
0x180055f88  jz      short loc_180055FA8
0x180055f8a  test    dword ptr [rcx+1Ch], 200h
0x180055f91  jz      short loc_180055FA8
0x180055f93  mov     rcx, [rcx+10h]
0x180055f97  lea     r8, WPP_be91c1c7b6083381c2d2431ae6263e74_Traceguids
0x180055f9e  mov     edx, 15h
0x180055fa3  call    WPP_SF_
0x180055fa8  mov     rbx, [rsp+38h+arg_0]
0x180055fad  xor     eax, eax
0x180055faf  add     rsp, 30h
0x180055fb3  pop     rdi
0x180055fb4  retn
```
