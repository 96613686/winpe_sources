# COMXProc::_AdviseMountPointHelper(ushort const *,ushort const *,int)

- ea: `0x180029cdc`
- end: `0x180029de5`
- name: `?_AdviseMountPointHelper@COMXProc@@YAJPEBG0H@Z`
- size: `265`
- prototype: `__int64 __fastcall(COMXProc *this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path, service_task, broker_com_uri`

## callers

- `0x180014fd0`

## callees

- `0x180003570`
- `0x1800137e0`
- `0x1800140f0`
- `0x1800169e0`
- `0x18001b404`
- `0x1800297a0`
- `0x180029cdc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180029d60`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180029d60`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180029d76`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180029d76`

## pseudocode

```c
__int64 __fastcall COMXProc::_AdviseMountPointHelper(
        COMXProc *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  int v4; // esi
  COMXProc::CThreadTaskMountPointEvent *v6; // rax
  COMXProc::CThreadTaskMountPointEvent *v7; // rbx
  int v8; // edi
  int inited; // eax
  HANDLE ProcessHeap; // rax
  _DWORD *v11; // rax

  v4 = (int)a3;
  v6 = (COMXProc::CThreadTaskMountPointEvent *)operator new(0x30u);
  v7 = v6;
  if ( !v6 )
    return (unsigned int)-2147024882;
  *((_QWORD *)v6 + 1) = 1;
  *((_DWORD *)v6 + 5) = 0;
  *((_QWORD *)v6 + 4) = 0;
  *((_DWORD *)v6 + 4) = -2147418113;
  *((_QWORD *)v6 + 3) = 0;
  *((_QWORD *)v6 + 5) = 0;
  *(_QWORD *)v6 = &COMXProc::CThreadTaskDeviceEvent::`vftable';
  v8 = CThreadTaskRegister::RegisterWithService(v6);
  if ( v8 >= 0 )
  {
    if ( v4 )
    {
      inited = COMXProc::CThreadTaskMountPointEvent::InitAdded(v7, (const unsigned __int16 *)this, a2);
    }
    else
    {
      ProcessHeap = GetProcessHeap();
      v11 = HeapAlloc(ProcessHeap, 8u, 0x218u);
      *((_QWORD *)v7 + 5) = v11;
      if ( !v11 )
      {
        v8 = -2147024882;
        goto LABEL_9;
      }
      *v11 = 536;
      *(_DWORD *)(*((_QWORD *)v7 + 5) + 4LL) = 16;
      *(_DWORD *)(*((_QWORD *)v7 + 5) + 8LL) = 0;
      inited = StringCchCopyW((unsigned __int16 *)(*((_QWORD *)v7 + 5) + 12LL), 0x104u, (const unsigned __int16 *)this);
    }
    v8 = inited;
LABEL_9:
    if ( v8 >= 0 )
      v8 = CThreadTask::Run(v7);
  }
  CRefCounted::Release(v7);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180029cdc  push    rbx
0x180029cde  push    rbp
0x180029cdf  push    rsi
0x180029ce0  push    rdi
0x180029ce1  push    r14
0x180029ce3  sub     rsp, 20h
0x180029ce7  mov     rbp, rcx
0x180029cea  mov     esi, r8d
0x180029ced  mov     ecx, 30h ; '0'; Size
0x180029cf2  mov     r14, rdx
0x180029cf5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180029cfa  mov     rbx, rax
0x180029cfd  test    rax, rax
0x180029d00  jz      loc_180029DD3
0x180029d06  mov     qword ptr [rax+8], 1
0x180029d0e  mov     rcx, rbx; this
0x180029d11  mov     dword ptr [rax+14h], 0
0x180029d18  mov     qword ptr [rax+20h], 0
0x180029d20  mov     dword ptr [rax+10h], 8000FFFFh
0x180029d27  mov     qword ptr [rax+18h], 0
0x180029d2f  mov     qword ptr [rax+28h], 0
0x180029d37  lea     rax, ??_7CThreadTaskDeviceEvent@COMXProc@@6B@; const COMXProc::CThreadTaskDeviceEvent::`vftable'
0x180029d3e  mov     [rbx], rax
0x180029d41  call    ?RegisterWithService@CThreadTaskRegister@@QEAAJXZ; CThreadTaskRegister::RegisterWithService(void)
0x180029d46  mov     edi, eax
0x180029d48  test    eax, eax
0x180029d4a  js      short loc_180029DC9
0x180029d4c  test    esi, esi
0x180029d4e  jz      short loc_180029D60
0x180029d50  mov     r8, r14; unsigned __int16 *
0x180029d53  mov     rdx, rbp; unsigned __int16 *
0x180029d56  mov     rcx, rbx; this
0x180029d59  call    ?InitAdded@CThreadTaskMountPointEvent@COMXProc@@QEAAJPEBG0@Z; COMXProc::CThreadTaskMountPointEvent::InitAdded(ushort const *,ushort const *)
0x180029d5e  jmp     short loc_180029DB9
0x180029d60  call    cs:__imp_GetProcessHeap
0x180029d66  mov     edi, 218h
0x180029d6b  mov     edx, 8; dwFlags
0x180029d70  mov     rcx, rax; hHeap
0x180029d73  mov     r8d, edi; dwBytes
0x180029d76  call    cs:__imp_HeapAlloc
0x180029d7c  mov     [rbx+28h], rax
0x180029d80  test    rax, rax
0x180029d83  jnz     short loc_180029D8C
0x180029d85  mov     edi, 8007000Eh
0x180029d8a  jmp     short loc_180029DBB
0x180029d8c  mov     [rax], edi
0x180029d8e  mov     r8, rbp; unsigned __int16 *
0x180029d91  mov     rax, [rbx+28h]
0x180029d95  mov     edx, 104h; unsigned __int64
0x180029d9a  mov     dword ptr [rax+4], 10h
0x180029da1  mov     rax, [rbx+28h]
0x180029da5  mov     dword ptr [rax+8], 0
0x180029dac  mov     rcx, [rbx+28h]
0x180029db0  add     rcx, 0Ch; unsigned __int16 *
0x180029db4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180029db9  mov     edi, eax
0x180029dbb  test    edi, edi
0x180029dbd  js      short loc_180029DC9
0x180029dbf  mov     rcx, rbx; Context
0x180029dc2  call    ?Run@CThreadTask@@QEAAJXZ; CThreadTask::Run(void)
0x180029dc7  mov     edi, eax
0x180029dc9  mov     rcx, rbx; this
0x180029dcc  call    ?Release@CRefCounted@@QEBAKXZ; CRefCounted::Release(void)
0x180029dd1  jmp     short loc_180029DD8
0x180029dd3  mov     edi, 8007000Eh
0x180029dd8  mov     eax, edi
0x180029dda  add     rsp, 20h
0x180029dde  pop     r14
0x180029de0  pop     rdi
0x180029de1  pop     rsi
0x180029de2  pop     rbp
0x180029de3  pop     rbx
0x180029de4  retn
```
