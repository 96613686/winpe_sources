# CUPnPInterfaceList::HrSetICSOff(void)

- ea: `0x180032e58`
- end: `0x180032f23`
- name: `?HrSetICSOff@CUPnPInterfaceList@@QEAAJXZ`
- size: `203`
- prototype: `__int64 __fastcall(CUPnPInterfaceList *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18002cf30`

## callees

- `0x180028000`
- `0x180032e58`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180032ed5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180032ed5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180032e71`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180032e71`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180032e86`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180032e86`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180032ec4`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180032ec4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180032e93`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180032e93`

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
0x180032e58  mov     [rsp+arg_8], rbx
0x180032e5d  push    rdi
0x180032e5e  sub     rsp, 30h
0x180032e62  mov     rbx, rcx
0x180032e65  mov     [rsp+38h+ThreadId], 0
0x180032e6d  add     rcx, 50h ; 'P'; lpCriticalSection
0x180032e71  call    cs:__imp_EnterCriticalSection
0x180032e77  mov     rcx, [rbx+0F8h]; hHandle
0x180032e7e  test    rcx, rcx
0x180032e81  jz      short loc_180032EA4
0x180032e83  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180032e86  call    cs:__imp_WaitForSingleObject
0x180032e8c  mov     rcx, [rbx+0F8h]; hObject
0x180032e93  call    cs:__imp_CloseHandle
0x180032e99  mov     qword ptr [rbx+0F8h], 0
0x180032ea4  lea     rax, [rsp+38h+ThreadId]
0x180032ea9  mov     r9, rbx; lpParameter
0x180032eac  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x180032eb1  lea     r8, ?ExecIcsChangeInterfaces@@YAKPEAX@Z; lpStartAddress
0x180032eb8  xor     edx, edx; dwStackSize
0x180032eba  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x180032ec2  xor     ecx, ecx; lpThreadAttributes
0x180032ec4  call    cs:__imp_CreateThread
0x180032eca  lea     rcx, [rbx+50h]; lpCriticalSection
0x180032ece  mov     [rbx+0F8h], rax
0x180032ed5  call    cs:__imp_LeaveCriticalSection
0x180032edb  cmp     qword ptr [rbx+0F8h], 0
0x180032ee3  jnz     short loc_180032F16
0x180032ee5  mov     rcx, cs:WPP_GLOBAL_Control
0x180032eec  lea     rax, WPP_GLOBAL_Control
0x180032ef3  cmp     rcx, rax
0x180032ef6  jz      short loc_180032F16
0x180032ef8  test    dword ptr [rcx+1Ch], 200h
0x180032eff  jz      short loc_180032F16
0x180032f01  mov     rcx, [rcx+10h]
0x180032f05  lea     r8, WPP_be91c1c7b6083381c2d2431ae6263e74_Traceguids
0x180032f0c  mov     edx, 16h
0x180032f11  call    WPP_SF_
0x180032f16  mov     rbx, [rsp+38h+arg_8]
0x180032f1b  xor     eax, eax
0x180032f1d  add     rsp, 30h
0x180032f21  pop     rdi
0x180032f22  retn
```
