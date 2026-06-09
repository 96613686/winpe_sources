# CUPnPInterfaceList::HrSetICSInterfaces(long,_GUID *)

- ea: `0x18003574c`
- end: `0x18003583a`
- name: `?HrSetICSInterfaces@CUPnPInterfaceList@@QEAAJJPEAU_GUID@@@Z`
- size: `238`
- prototype: `__int64 __fastcall(CUPnPInterfaceList *__hidden this, int, struct _GUID *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18002ef30`

## callees

- `0x180029df0`
- `0x18003574c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800357e5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800357e5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180035769`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180035769`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180035784`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180035784`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800357ce`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800357ce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180035797`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180035797`

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
    && WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_be91c1c7b6083381c2d2431ae6263e74_Traceguids);
  }
  return 0;
}

```

## disassembly

```asm
0x18003574c  mov     [rsp+arg_0], rbx
0x180035751  mov     [rsp+ThreadId], edx
0x180035755  push    rdi
0x180035756  sub     rsp, 30h
0x18003575a  mov     rbx, rcx
0x18003575d  mov     [rsp+38h+ThreadId], 0
0x180035765  add     rcx, 50h ; 'P'; lpCriticalSection
0x180035769  call    cs:__imp_EnterCriticalSection
0x180035770  nop     dword ptr [rax+rax+00h]
0x180035775  mov     rcx, [rbx+0F8h]; hHandle
0x18003577c  test    rcx, rcx
0x18003577f  jz      short loc_1800357AE
0x180035781  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180035784  call    cs:__imp_WaitForSingleObject
0x18003578b  nop     dword ptr [rax+rax+00h]
0x180035790  mov     rcx, [rbx+0F8h]; hObject
0x180035797  call    cs:__imp_CloseHandle
0x18003579e  nop     dword ptr [rax+rax+00h]
0x1800357a3  mov     qword ptr [rbx+0F8h], 0
0x1800357ae  lea     rax, [rsp+38h+ThreadId]
0x1800357b3  mov     r9, rbx; lpParameter
0x1800357b6  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x1800357bb  lea     r8, ?ExecIcsChangeInterfaces@@YAKPEAX@Z; lpStartAddress
0x1800357c2  xor     edx, edx; dwStackSize
0x1800357c4  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x1800357cc  xor     ecx, ecx; lpThreadAttributes
0x1800357ce  call    cs:__imp_CreateThread
0x1800357d5  nop     dword ptr [rax+rax+00h]
0x1800357da  lea     rcx, [rbx+50h]; lpCriticalSection
0x1800357de  mov     [rbx+0F8h], rax
0x1800357e5  call    cs:__imp_LeaveCriticalSection
0x1800357ec  nop     dword ptr [rax+rax+00h]
0x1800357f1  cmp     qword ptr [rbx+0F8h], 0
0x1800357f9  jnz     short loc_18003582C
0x1800357fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180035802  lea     rax, WPP_GLOBAL_Control
0x180035809  cmp     rcx, rax
0x18003580c  jz      short loc_18003582C
0x18003580e  test    dword ptr [rcx+1Ch], 200h
0x180035815  jz      short loc_18003582C
0x180035817  mov     rcx, [rcx+10h]
0x18003581b  lea     r8, WPP_be91c1c7b6083381c2d2431ae6263e74_Traceguids
0x180035822  mov     edx, 15h
0x180035827  call    WPP_SF_
0x18003582c  mov     rbx, [rsp+38h+arg_0]
0x180035831  xor     eax, eax
0x180035833  add     rsp, 30h
0x180035837  pop     rdi
0x180035838  retn
```
