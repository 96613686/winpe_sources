# CUPnPInterfaceList::HrSetICSInterfaces(long,_GUID *)

- ea: `0x180032d80`
- end: `0x180032e4f`
- name: `?HrSetICSInterfaces@CUPnPInterfaceList@@QEAAJJPEAU_GUID@@@Z`
- size: `207`
- prototype: `__int64 __fastcall(CUPnPInterfaceList *this, __int64, struct _GUID *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18002cf10`

## callees

- `0x180028000`
- `0x180032d80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180032e01`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180032e01`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180032d9d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180032d9d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180032db2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180032db2`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180032df0`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180032df0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180032dbf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180032dbf`

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
0x180032d80  mov     [rsp+arg_0], rbx
0x180032d85  mov     [rsp+ThreadId], edx
0x180032d89  push    rdi
0x180032d8a  sub     rsp, 30h
0x180032d8e  mov     rbx, rcx
0x180032d91  mov     [rsp+38h+ThreadId], 0
0x180032d99  add     rcx, 50h ; 'P'; lpCriticalSection
0x180032d9d  call    cs:__imp_EnterCriticalSection
0x180032da3  mov     rcx, [rbx+0F8h]; hHandle
0x180032daa  test    rcx, rcx
0x180032dad  jz      short loc_180032DD0
0x180032daf  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180032db2  call    cs:__imp_WaitForSingleObject
0x180032db8  mov     rcx, [rbx+0F8h]; hObject
0x180032dbf  call    cs:__imp_CloseHandle
0x180032dc5  mov     qword ptr [rbx+0F8h], 0
0x180032dd0  lea     rax, [rsp+38h+ThreadId]
0x180032dd5  mov     r9, rbx; lpParameter
0x180032dd8  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x180032ddd  lea     r8, ?ExecIcsChangeInterfaces@@YAKPEAX@Z; lpStartAddress
0x180032de4  xor     edx, edx; dwStackSize
0x180032de6  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x180032dee  xor     ecx, ecx; lpThreadAttributes
0x180032df0  call    cs:__imp_CreateThread
0x180032df6  lea     rcx, [rbx+50h]; lpCriticalSection
0x180032dfa  mov     [rbx+0F8h], rax
0x180032e01  call    cs:__imp_LeaveCriticalSection
0x180032e07  cmp     qword ptr [rbx+0F8h], 0
0x180032e0f  jnz     short loc_180032E42
0x180032e11  mov     rcx, cs:WPP_GLOBAL_Control
0x180032e18  lea     rax, WPP_GLOBAL_Control
0x180032e1f  cmp     rcx, rax
0x180032e22  jz      short loc_180032E42
0x180032e24  test    dword ptr [rcx+1Ch], 200h
0x180032e2b  jz      short loc_180032E42
0x180032e2d  mov     rcx, [rcx+10h]
0x180032e31  lea     r8, WPP_be91c1c7b6083381c2d2431ae6263e74_Traceguids
0x180032e38  mov     edx, 15h
0x180032e3d  call    WPP_SF_
0x180032e42  mov     rbx, [rsp+38h+arg_0]
0x180032e47  xor     eax, eax
0x180032e49  add     rsp, 30h
0x180032e4d  pop     rdi
0x180032e4e  retn
```
