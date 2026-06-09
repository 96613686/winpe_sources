# SOS_DispatcherPool<XE_Buffer,XE_BufferMgr,XE_DispatcherQueue,XE_DispatcherPoolConfig,void *>::Start(void)

- ea: `0x1005db050`
- end: `0x1005db13c`
- name: `?Start@?$SOS_DispatcherPool@VXE_Buffer@@VXE_BufferMgr@@VXE_DispatcherQueue@@VXE_DispatcherPoolConfig@@PEAX@@QEAA?AW4SOS_RESULT@@XZ`
- size: `236`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callers

- `0x1005da330`
- `0x1005da9b0`

## callees

- `0x1005db050`
- `0x1005db150`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x1005db0a0`
- `KERNEL32!CreateEventW` at `0x1005db0d2`
- `KERNEL32!CreateEventW` at `0x1005db0a0`
- `KERNEL32!CreateEventW` at `0x1005db0d2`
- `KERNEL32!CreateSemaphoreW` at `0x1005db06a`
- `KERNEL32!CreateSemaphoreW` at `0x1005db06a`
- `KERNEL32!CloseHandle` at `0x1005db081`
- `KERNEL32!CloseHandle` at `0x1005db0b7`
- `KERNEL32!CloseHandle` at `0x1005db0ec`
- `KERNEL32!CloseHandle` at `0x1005db081`
- `KERNEL32!CloseHandle` at `0x1005db0b7`
- `KERNEL32!CloseHandle` at `0x1005db0ec`

## pseudocode

```c
__int64 __fastcall SOS_DispatcherPool<XE_Buffer,XE_BufferMgr,XE_DispatcherQueue,XE_DispatcherPoolConfig,void *>::Start(
        __int64 *a1)
{
  HANDLE SemaphoreW; // rax
  HANDLE v3; // rcx
  __int64 v4; // rdi
  HANDLE EventW; // rax
  HANDLE v6; // rcx
  __int64 v7; // rdi
  HANDLE v8; // rax
  HANDLE v9; // rcx
  __int64 v10; // rdi
  __int64 v11; // rax
  __int64 result; // rax
  unsigned int v13; // edi

  SemaphoreW = CreateSemaphoreW(0, 0, 0x7FFFFFFF, 0);
  v3 = (HANDLE)a1[15];
  v4 = (__int64)SemaphoreW;
  if ( v3 && v3 != SemaphoreW )
    CloseHandle(v3);
  a1[15] = v4;
  if ( !v4 )
    return 0x80000000LL;
  EventW = CreateEventW(0, 1, 0, 0);
  v6 = (HANDLE)a1[14];
  v7 = (__int64)EventW;
  if ( v6 && v6 != EventW )
    CloseHandle(v6);
  a1[14] = v7;
  if ( !v7 )
    return 0x80000000LL;
  v8 = CreateEventW(0, 1, 0, 0);
  v9 = (HANDLE)a1[16];
  v10 = (__int64)v8;
  if ( v9 && v9 != v8 )
    CloseHandle(v9);
  a1[16] = v10;
  if ( !v10 )
    return 0x80000000LL;
  v11 = *a1;
  *((_DWORD *)a1 + 141) = 0;
  result = (*(__int64 (__fastcall **)(__int64 *))(v11 + 24))(a1);
  v13 = result;
  if ( (_DWORD)result )
  {
    SOS_DispatcherPool<XE_Buffer,XE_BufferMgr,XE_DispatcherQueue,XE_DispatcherPoolConfig,void *>::Stop(a1);
    return v13;
  }
  return result;
}

```

## disassembly

```asm
0x1005db050  mov     [rsp+arg_0], rbx
0x1005db055  push    rdi
0x1005db056  sub     rsp, 20h
0x1005db05a  mov     rbx, rcx
0x1005db05d  xor     r9d, r9d; lpName
0x1005db060  xor     ecx, ecx; lpSemaphoreAttributes
0x1005db062  xor     edx, edx; lInitialCount
0x1005db064  mov     r8d, 7FFFFFFFh; lMaximumCount
0x1005db06a  call    cs:__imp_CreateSemaphoreW
0x1005db070  mov     rcx, [rbx+78h]; hObject
0x1005db074  mov     rdi, rax
0x1005db077  test    rcx, rcx
0x1005db07a  jz      short loc_1005DB087
0x1005db07c  cmp     rcx, rax
0x1005db07f  jz      short loc_1005DB087
0x1005db081  call    cs:__imp_CloseHandle
0x1005db087  mov     [rbx+78h], rdi
0x1005db08b  test    rdi, rdi
0x1005db08e  jz      loc_1005DB12C
0x1005db094  xor     r9d, r9d; lpName
0x1005db097  xor     r8d, r8d; bInitialState
0x1005db09a  xor     ecx, ecx; lpEventAttributes
0x1005db09c  lea     edx, [r9+1]; bManualReset
0x1005db0a0  call    cs:__imp_CreateEventW
0x1005db0a6  mov     rcx, [rbx+70h]; hObject
0x1005db0aa  mov     rdi, rax
0x1005db0ad  test    rcx, rcx
0x1005db0b0  jz      short loc_1005DB0BD
0x1005db0b2  cmp     rcx, rax
0x1005db0b5  jz      short loc_1005DB0BD
0x1005db0b7  call    cs:__imp_CloseHandle
0x1005db0bd  mov     [rbx+70h], rdi
0x1005db0c1  test    rdi, rdi
0x1005db0c4  jz      short loc_1005DB12C
0x1005db0c6  xor     r9d, r9d; lpName
0x1005db0c9  xor     r8d, r8d; bInitialState
0x1005db0cc  xor     ecx, ecx; lpEventAttributes
0x1005db0ce  lea     edx, [r9+1]; bManualReset
0x1005db0d2  call    cs:__imp_CreateEventW
0x1005db0d8  mov     rcx, [rbx+80h]; hObject
0x1005db0df  mov     rdi, rax
0x1005db0e2  test    rcx, rcx
0x1005db0e5  jz      short loc_1005DB0F2
0x1005db0e7  cmp     rcx, rax
0x1005db0ea  jz      short loc_1005DB0F2
0x1005db0ec  call    cs:__imp_CloseHandle
0x1005db0f2  mov     [rbx+80h], rdi
0x1005db0f9  test    rdi, rdi
0x1005db0fc  jz      short loc_1005DB12C
0x1005db0fe  mov     rax, [rbx]
0x1005db101  mov     rcx, rbx
0x1005db104  mov     dword ptr [rbx+234h], 0
0x1005db10e  call    qword ptr [rax+18h]
0x1005db111  mov     edi, eax
0x1005db113  test    eax, eax
0x1005db115  jz      short loc_1005DB131
0x1005db117  mov     rcx, rbx
0x1005db11a  call    ?Stop@?$SOS_DispatcherPool@VXE_Buffer@@VXE_BufferMgr@@VXE_DispatcherQueue@@VXE_DispatcherPoolConfig@@PEAX@@QEAAXXZ; SOS_DispatcherPool<XE_Buffer,XE_BufferMgr,XE_DispatcherQueue,XE_DispatcherPoolConfig,void *>::Stop(void)
0x1005db11f  mov     eax, edi
0x1005db121  mov     rbx, [rsp+28h+arg_0]
0x1005db126  add     rsp, 20h
0x1005db12a  pop     rdi
0x1005db12b  retn
0x1005db12c  mov     eax, 80000000h
0x1005db131  mov     rbx, [rsp+28h+arg_0]
0x1005db136  add     rsp, 20h
0x1005db13a  pop     rdi
0x1005db13b  retn
```
