# CUPnPInterfaceList::HrSetICSOff(void)

- ea: `0x180052704`
- end: `0x1800527cf`
- name: `?HrSetICSOff@CUPnPInterfaceList@@QEAAJXZ`
- size: `203`
- prototype: `__int64 __fastcall(CUPnPInterfaceList *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18004d0e0`

## callees

- `0x180039a84`
- `0x180052704`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005271d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005271d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180052732`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180052732`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180052781`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180052781`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180052770`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180052770`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005273f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005273f`

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
    && WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_be91c1c7b6083381c2d2431ae6263e74_Traceguids);
  }
  return 0;
}

```

## disassembly

```asm
0x180052704  mov     [rsp+arg_8], rbx
0x180052709  push    rdi
0x18005270a  sub     rsp, 30h
0x18005270e  mov     rbx, rcx
0x180052711  mov     [rsp+38h+ThreadId], 0
0x180052719  add     rcx, 50h ; 'P'; lpCriticalSection
0x18005271d  call    cs:__imp_EnterCriticalSection
0x180052723  mov     rcx, [rbx+0F8h]; hHandle
0x18005272a  test    rcx, rcx
0x18005272d  jz      short loc_180052750
0x18005272f  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180052732  call    cs:__imp_WaitForSingleObject
0x180052738  mov     rcx, [rbx+0F8h]; hObject
0x18005273f  call    cs:__imp_CloseHandle
0x180052745  mov     qword ptr [rbx+0F8h], 0
0x180052750  lea     rax, [rsp+38h+ThreadId]
0x180052755  mov     r9, rbx; lpParameter
0x180052758  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x18005275d  lea     r8, ?ExecIcsChangeInterfaces@@YAKPEAX@Z; lpStartAddress
0x180052764  xor     edx, edx; dwStackSize
0x180052766  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x18005276e  xor     ecx, ecx; lpThreadAttributes
0x180052770  call    cs:__imp_CreateThread
0x180052776  lea     rcx, [rbx+50h]; lpCriticalSection
0x18005277a  mov     [rbx+0F8h], rax
0x180052781  call    cs:__imp_LeaveCriticalSection
0x180052787  cmp     qword ptr [rbx+0F8h], 0
0x18005278f  jnz     short loc_1800527C2
0x180052791  mov     rcx, cs:WPP_GLOBAL_Control
0x180052798  lea     rax, WPP_GLOBAL_Control
0x18005279f  cmp     rcx, rax
0x1800527a2  jz      short loc_1800527C2
0x1800527a4  test    dword ptr [rcx+1Ch], 200h
0x1800527ab  jz      short loc_1800527C2
0x1800527ad  mov     rcx, [rcx+10h]
0x1800527b1  lea     r8, WPP_be91c1c7b6083381c2d2431ae6263e74_Traceguids
0x1800527b8  mov     edx, 16h
0x1800527bd  call    WPP_SF_
0x1800527c2  mov     rbx, [rsp+38h+arg_8]
0x1800527c7  xor     eax, eax
0x1800527c9  add     rsp, 30h
0x1800527cd  pop     rdi
0x1800527ce  retn
```
