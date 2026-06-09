# ComTaskMgrWnd::ShutdownTasksWorker(void)

- ea: `0x140003b10`
- end: `0x140003c28`
- name: `?ShutdownTasksWorker@ComTaskMgrWnd@@AEAAJXZ`
- size: `280`
- prototype: `HRESULT __fastcall(RTL_SRWLOCK *this)`
- caller_count: `3`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x140003180`
- `0x140003270`
- `0x140003880`

## callees

- `0x1400036b0`
- `0x140003b10`
- `0x140003c30`
- `0x140003e20`
- `0x140007360`
- `0x140009370`
- `0x14000c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140003ba4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140003bfd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140003ba4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140003bfd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140003b88`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140003b88`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140003c03`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140003c03`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140003b6a`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140003b6a`

## pseudocode

```c
HRESULT __fastcall ComTaskMgrWnd::ShutdownTasksWorker(RTL_SRWLOCK *this)
{
  HRESULT result; // eax
  HRESULT v3; // esi
  ComTaskHost *v4; // r14
  const unsigned __int16 *v5; // rax
  int v6; // eax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_70d3f6ab2bd730cad06006a8dcaaa1a7_Traceguids, this);
  ComTaskMgrWnd::CreateShutdownBlockMessage((HWND *)this, 0);
  result = ComTaskMgrBase::WaitForShutdownGuards();
  if ( result >= 0 )
  {
    result = CoInitializeEx(0, 0);
    v3 = result;
    if ( result >= 0 )
    {
      while ( 1 )
      {
        AcquireSRWLockExclusive(this + 9);
        if ( !this[11].Ptr )
          break;
        v4 = *(ComTaskHost **)(*(_QWORD *)this[10].Ptr + 32LL);
        ReleaseSRWLockExclusive(this + 9);
        if ( !v4 )
          goto LABEL_14;
        if ( (*(__int64 (__fastcall **)(ComTaskHost *))(*(_QWORD *)v4 + 48LL))(v4) )
        {
          ComTaskMgrWnd::DestroyShutdownBlockMessage((HWND *)this);
          v5 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(ComTaskHost *))(*(_QWORD *)v4 + 48LL))(v4);
          ComTaskMgrWnd::CreateShutdownBlockMessage((HWND *)this, v5);
        }
        v6 = ComTaskHost::Shutdown(v4);
        if ( !v3 && v6 < 0 )
          v3 = v6;
      }
      ReleaseSRWLockExclusive(this + 9);
LABEL_14:
      CoUninitialize();
      ComTaskMgrWnd::DestroyShutdownBlockMessage((HWND *)this);
      return v3;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140003b10  push    rbx
0x140003b12  sub     rsp, 20h
0x140003b16  mov     rbx, rcx
0x140003b19  mov     rcx, cs:WPP_GLOBAL_Control
0x140003b20  lea     rax, WPP_GLOBAL_Control
0x140003b27  cmp     rcx, rax
0x140003b2a  jz      short loc_140003B4A
0x140003b2c  test    byte ptr [rcx+1Ch], 4
0x140003b30  jz      short loc_140003B4A
0x140003b32  mov     rcx, [rcx+10h]
0x140003b36  lea     r8, WPP_70d3f6ab2bd730cad06006a8dcaaa1a7_Traceguids
0x140003b3d  mov     edx, 0Ch
0x140003b42  mov     r9, rbx
0x140003b45  call    WPP_SF_q
0x140003b4a  xor     edx, edx; unsigned __int16 *
0x140003b4c  mov     rcx, rbx; this
0x140003b4f  call    ?CreateShutdownBlockMessage@ComTaskMgrWnd@@AEBAJPEBG@Z; ComTaskMgrWnd::CreateShutdownBlockMessage(ushort const *)
0x140003b54  call    ?WaitForShutdownGuards@ComTaskMgrBase@@KAJXZ; ComTaskMgrBase::WaitForShutdownGuards(void)
0x140003b59  test    eax, eax
0x140003b5b  js      loc_140003C22
0x140003b61  xor     edx, edx; dwCoInit
0x140003b63  mov     [rsp+28h+arg_0], rsi
0x140003b68  xor     ecx, ecx; pvReserved
0x140003b6a  call    cs:__imp_CoInitializeEx
0x140003b70  mov     esi, eax
0x140003b72  test    eax, eax
0x140003b74  js      loc_140003C1D
0x140003b7a  mov     [rsp+28h+arg_8], rdi
0x140003b7f  mov     [rsp+28h+arg_10], r14
0x140003b84  lea     rcx, [rbx+48h]; SRWLock
0x140003b88  call    cs:__imp_AcquireSRWLockExclusive
0x140003b8e  cmp     qword ptr [rbx+58h], 0
0x140003b93  jz      short loc_140003BF9
0x140003b95  mov     rax, [rbx+50h]
0x140003b99  mov     rcx, [rax]
0x140003b9c  mov     r14, [rcx+20h]
0x140003ba0  lea     rcx, [rbx+48h]; SRWLock
0x140003ba4  call    cs:__imp_ReleaseSRWLockExclusive
0x140003baa  test    r14, r14
0x140003bad  jz      short loc_140003C03
0x140003baf  mov     rax, [r14]
0x140003bb2  mov     rcx, r14
0x140003bb5  mov     rax, [rax+30h]
0x140003bb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003bbe  test    rax, rax
0x140003bc1  jz      short loc_140003BE5
0x140003bc3  mov     rcx, rbx; this
0x140003bc6  call    ?DestroyShutdownBlockMessage@ComTaskMgrWnd@@AEBAJXZ; ComTaskMgrWnd::DestroyShutdownBlockMessage(void)
0x140003bcb  mov     rax, [r14]
0x140003bce  mov     rcx, r14
0x140003bd1  mov     rax, [rax+30h]
0x140003bd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003bda  mov     rdx, rax; unsigned __int16 *
0x140003bdd  mov     rcx, rbx; this
0x140003be0  call    ?CreateShutdownBlockMessage@ComTaskMgrWnd@@AEBAJPEBG@Z; ComTaskMgrWnd::CreateShutdownBlockMessage(ushort const *)
0x140003be5  mov     rcx, r14; this
0x140003be8  call    ?Shutdown@ComTaskHost@@QEAAJXZ; ComTaskHost::Shutdown(void)
0x140003bed  test    esi, esi
0x140003bef  jnz     short loc_140003B84
0x140003bf1  test    eax, eax
0x140003bf3  jns     short loc_140003B84
0x140003bf5  mov     esi, eax
0x140003bf7  jmp     short loc_140003B84
0x140003bf9  lea     rcx, [rbx+48h]; SRWLock
0x140003bfd  call    cs:__imp_ReleaseSRWLockExclusive
0x140003c03  call    cs:__imp_CoUninitialize
0x140003c09  mov     rcx, rbx; this
0x140003c0c  call    ?DestroyShutdownBlockMessage@ComTaskMgrWnd@@AEBAJXZ; ComTaskMgrWnd::DestroyShutdownBlockMessage(void)
0x140003c11  mov     r14, [rsp+28h+arg_10]
0x140003c16  mov     eax, esi
0x140003c18  mov     rdi, [rsp+28h+arg_8]
0x140003c1d  mov     rsi, [rsp+28h+arg_0]
0x140003c22  add     rsp, 20h
0x140003c26  pop     rbx
0x140003c27  retn
```
