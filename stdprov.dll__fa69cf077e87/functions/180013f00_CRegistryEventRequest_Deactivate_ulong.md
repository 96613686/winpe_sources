# CRegistryEventRequest::Deactivate(ulong)

- ea: `0x180013f00`
- end: `0x180013fdf`
- name: `?Deactivate@CRegistryEventRequest@@QEAAJK@Z`
- size: `223`
- prototype: `__int64 __fastcall(CRegistryEventRequest *this, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180008030`
- `0x180008570`

## callees

- `0x1800082d0`
- `0x18000a2e0`
- `0x180013f00`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013f83`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013f83`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013fba`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013fc9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013fba`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013fc9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013f9b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013f9b`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180013f6b`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180013f6b`
- `wbemcomn!??ACFlexArray@@QEAAAEAPEAXH@Z` at `0x180013f38`
- `wbemcomn!??ACFlexArray@@QEAAAEAPEAXH@Z` at `0x180013f38`
- `wbemcomn!?RemoveAt@CFlexArray@@QEAAHH@Z` at `0x180013f4c`
- `wbemcomn!?RemoveAt@CFlexArray@@QEAAHH@Z` at `0x180013f4c`

## pseudocode

```c
__int64 __fastcall CRegistryEventRequest::Deactivate(CRegistryEventRequest *this, int a2)
{
  int v4; // ebp
  unsigned int i; // edi
  LPCRITICAL_SECTION lpCriticalSection[7]; // [rsp+20h] [rbp-38h] BYREF

  CInCritSec::CInCritSec((CInCritSec *)lpCriticalSection, (struct _RTL_CRITICAL_SECTION *)((char *)this + 184));
  v4 = *((_DWORD *)this + 8);
  for ( i = 0; (int)i < v4; ++i )
  {
    if ( *(_DWORD *)CFlexArray::operator[]((char *)this + 32, i) == a2 )
    {
      CFlexArray::RemoveAt((CRegistryEventRequest *)((char *)this + 32), i);
      if ( _InterlockedDecrement((volatile signed __int32 *)this + 41) < 0 )
      {
        UnregisterWaitEx(*((HANDLE *)this + 22), (HANDLE)0xFFFFFFFFFFFFFFFFLL);
        *((_QWORD *)this + 22) = 0;
        RegCloseKey(*((HKEY *)this + 18));
        *((_QWORD *)this + 18) = 0;
        CloseHandle(*((HANDLE *)this + 19));
        *((_QWORD *)this + 19) = 0;
        CRegistryEventRequest::Release(this);
        LeaveCriticalSection(lpCriticalSection[0]);
        return 0;
      }
      break;
    }
  }
  LeaveCriticalSection(lpCriticalSection[0]);
  return 1;
}

```

## disassembly

```asm
0x180013f00  push    rbx
0x180013f02  push    rbp
0x180013f03  push    rsi
0x180013f04  push    rdi
0x180013f05  push    r14
0x180013f07  sub     rsp, 30h
0x180013f0b  mov     r14d, edx
0x180013f0e  mov     rbx, rcx
0x180013f11  lea     rdx, [rcx+0B8h]; struct _RTL_CRITICAL_SECTION *
0x180013f18  lea     rcx, [rsp+58h+lpCriticalSection]; this
0x180013f1d  call    ??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInCritSec::CInCritSec(_RTL_CRITICAL_SECTION *)
0x180013f22  nop
0x180013f23  lea     rsi, [rbx+20h]
0x180013f27  mov     ebp, [rsi]
0x180013f29  xor     edi, edi
0x180013f2b  cmp     edi, ebp
0x180013f2d  jge     loc_180013FC4
0x180013f33  mov     edx, edi
0x180013f35  mov     rcx, rsi
0x180013f38  call    cs:__imp_??ACFlexArray@@QEAAAEAPEAXH@Z; CFlexArray::operator[](int)
0x180013f3e  cmp     [rax], r14d
0x180013f41  jz      short loc_180013F47
0x180013f43  inc     edi
0x180013f45  jmp     short loc_180013F2B
0x180013f47  mov     edx, edi
0x180013f49  mov     rcx, rsi
0x180013f4c  call    cs:__imp_?RemoveAt@CFlexArray@@QEAAHH@Z; CFlexArray::RemoveAt(int)
0x180013f52  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x180013f56  mov     eax, edx
0x180013f58  lock xadd [rbx+0A4h], eax
0x180013f60  add     eax, edx
0x180013f62  jns     short loc_180013FC4
0x180013f64  mov     rcx, [rbx+0B0h]; WaitHandle
0x180013f6b  call    cs:__imp_UnregisterWaitEx
0x180013f71  mov     qword ptr [rbx+0B0h], 0
0x180013f7c  mov     rcx, [rbx+90h]; hKey
0x180013f83  call    cs:__imp_RegCloseKey
0x180013f89  mov     qword ptr [rbx+90h], 0
0x180013f94  mov     rcx, [rbx+98h]; hObject
0x180013f9b  call    cs:__imp_CloseHandle
0x180013fa1  mov     qword ptr [rbx+98h], 0
0x180013fac  mov     rcx, rbx; this
0x180013faf  call    ?Release@CRegistryEventRequest@@QEAAJXZ; CRegistryEventRequest::Release(void)
0x180013fb4  nop
0x180013fb5  mov     rcx, [rsp+58h+lpCriticalSection]; lpCriticalSection
0x180013fba  call    cs:__imp_LeaveCriticalSection
0x180013fc0  xor     eax, eax
0x180013fc2  jmp     short loc_180013FD4
0x180013fc4  mov     rcx, [rsp+58h+lpCriticalSection]; lpCriticalSection
0x180013fc9  call    cs:__imp_LeaveCriticalSection
0x180013fcf  mov     eax, 1
0x180013fd4  add     rsp, 30h
0x180013fd8  pop     r14
0x180013fda  pop     rdi
0x180013fdb  pop     rsi
0x180013fdc  pop     rbp
0x180013fdd  pop     rbx
0x180013fde  retn
```
