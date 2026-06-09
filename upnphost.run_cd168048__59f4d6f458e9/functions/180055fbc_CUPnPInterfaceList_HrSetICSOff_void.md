# CUPnPInterfaceList::HrSetICSOff(void)

- ea: `0x180055fbc`
- end: `0x1800560a6`
- name: `?HrSetICSOff@CUPnPInterfaceList@@QEAAJXZ`
- size: `234`
- prototype: `__int64 __fastcall(CUPnPInterfaceList *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800504e0`

## callees

- `0x18003c018`
- `0x180055fbc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180055fd5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180055fd5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180055ff0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180055ff0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180056051`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180056051`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18005603a`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18005603a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180056003`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180056003`

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
0x180055fbc  mov     [rsp+arg_8], rbx
0x180055fc1  push    rdi
0x180055fc2  sub     rsp, 30h
0x180055fc6  mov     rbx, rcx
0x180055fc9  mov     [rsp+38h+ThreadId], 0
0x180055fd1  add     rcx, 50h ; 'P'; lpCriticalSection
0x180055fd5  call    cs:__imp_EnterCriticalSection
0x180055fdc  nop     dword ptr [rax+rax+00h]
0x180055fe1  mov     rcx, [rbx+0F8h]; hHandle
0x180055fe8  test    rcx, rcx
0x180055feb  jz      short loc_18005601A
0x180055fed  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180055ff0  call    cs:__imp_WaitForSingleObject
0x180055ff7  nop     dword ptr [rax+rax+00h]
0x180055ffc  mov     rcx, [rbx+0F8h]; hObject
0x180056003  call    cs:__imp_CloseHandle
0x18005600a  nop     dword ptr [rax+rax+00h]
0x18005600f  mov     qword ptr [rbx+0F8h], 0
0x18005601a  lea     rax, [rsp+38h+ThreadId]
0x18005601f  mov     r9, rbx; lpParameter
0x180056022  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x180056027  lea     r8, ?ExecIcsChangeInterfaces@@YAKPEAX@Z; lpStartAddress
0x18005602e  xor     edx, edx; dwStackSize
0x180056030  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x180056038  xor     ecx, ecx; lpThreadAttributes
0x18005603a  call    cs:__imp_CreateThread
0x180056041  nop     dword ptr [rax+rax+00h]
0x180056046  lea     rcx, [rbx+50h]; lpCriticalSection
0x18005604a  mov     [rbx+0F8h], rax
0x180056051  call    cs:__imp_LeaveCriticalSection
0x180056058  nop     dword ptr [rax+rax+00h]
0x18005605d  cmp     qword ptr [rbx+0F8h], 0
0x180056065  jnz     short loc_180056098
0x180056067  mov     rcx, cs:WPP_GLOBAL_Control
0x18005606e  lea     rax, WPP_GLOBAL_Control
0x180056075  cmp     rcx, rax
0x180056078  jz      short loc_180056098
0x18005607a  test    dword ptr [rcx+1Ch], 200h
0x180056081  jz      short loc_180056098
0x180056083  mov     rcx, [rcx+10h]
0x180056087  lea     r8, WPP_be91c1c7b6083381c2d2431ae6263e74_Traceguids
0x18005608e  mov     edx, 16h
0x180056093  call    WPP_SF_
0x180056098  mov     rbx, [rsp+38h+arg_8]
0x18005609d  xor     eax, eax
0x18005609f  add     rsp, 30h
0x1800560a3  pop     rdi
0x1800560a4  retn
```
