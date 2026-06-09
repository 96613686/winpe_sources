# CUPnPInterfaceList::HrSetICSInterfaces(long,_GUID *)

- ea: `0x18005262c`
- end: `0x1800526fb`
- name: `?HrSetICSInterfaces@CUPnPInterfaceList@@QEAAJJPEAU_GUID@@@Z`
- size: `207`
- prototype: `__int64 __fastcall(CUPnPInterfaceList *__hidden this, int, struct _GUID *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18004d030`

## callees

- `0x180039a84`
- `0x18005262c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180052649`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180052649`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18005265e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18005265e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800526ad`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800526ad`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18005269c`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18005269c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005266b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005266b`

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
0x18005262c  mov     [rsp+arg_0], rbx
0x180052631  mov     [rsp+ThreadId], edx
0x180052635  push    rdi
0x180052636  sub     rsp, 30h
0x18005263a  mov     rbx, rcx
0x18005263d  mov     [rsp+38h+ThreadId], 0
0x180052645  add     rcx, 50h ; 'P'; lpCriticalSection
0x180052649  call    cs:__imp_EnterCriticalSection
0x18005264f  mov     rcx, [rbx+0F8h]; hHandle
0x180052656  test    rcx, rcx
0x180052659  jz      short loc_18005267C
0x18005265b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18005265e  call    cs:__imp_WaitForSingleObject
0x180052664  mov     rcx, [rbx+0F8h]; hObject
0x18005266b  call    cs:__imp_CloseHandle
0x180052671  mov     qword ptr [rbx+0F8h], 0
0x18005267c  lea     rax, [rsp+38h+ThreadId]
0x180052681  mov     r9, rbx; lpParameter
0x180052684  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x180052689  lea     r8, ?ExecIcsChangeInterfaces@@YAKPEAX@Z; lpStartAddress
0x180052690  xor     edx, edx; dwStackSize
0x180052692  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x18005269a  xor     ecx, ecx; lpThreadAttributes
0x18005269c  call    cs:__imp_CreateThread
0x1800526a2  lea     rcx, [rbx+50h]; lpCriticalSection
0x1800526a6  mov     [rbx+0F8h], rax
0x1800526ad  call    cs:__imp_LeaveCriticalSection
0x1800526b3  cmp     qword ptr [rbx+0F8h], 0
0x1800526bb  jnz     short loc_1800526EE
0x1800526bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800526c4  lea     rax, WPP_GLOBAL_Control
0x1800526cb  cmp     rcx, rax
0x1800526ce  jz      short loc_1800526EE
0x1800526d0  test    dword ptr [rcx+1Ch], 200h
0x1800526d7  jz      short loc_1800526EE
0x1800526d9  mov     rcx, [rcx+10h]
0x1800526dd  lea     r8, WPP_be91c1c7b6083381c2d2431ae6263e74_Traceguids
0x1800526e4  mov     edx, 15h
0x1800526e9  call    WPP_SF_
0x1800526ee  mov     rbx, [rsp+38h+arg_0]
0x1800526f3  xor     eax, eax
0x1800526f5  add     rsp, 30h
0x1800526f9  pop     rdi
0x1800526fa  retn
```
