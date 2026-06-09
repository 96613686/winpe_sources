# COMXProc::_AdviseVolumeRemoved(ushort const *)

- ea: `0x180029eec`
- end: `0x180029fe3`
- name: `?_AdviseVolumeRemoved@COMXProc@@YAJPEBG@Z`
- size: `247`
- prototype: `__int64 __fastcall(COMXProc *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180014fd0`

## callees

- `0x180003570`
- `0x1800137e0`
- `0x1800140f0`
- `0x1800169e0`
- `0x18001b404`
- `0x180029eec`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180029f51`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180029f51`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180029f67`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180029f67`

## pseudocode

```c
__int64 __fastcall COMXProc::_AdviseVolumeRemoved(COMXProc *this, const unsigned __int16 *a2)
{
  _QWORD *v3; // rax
  _QWORD *v4; // rbx
  int v5; // edi
  HANDLE ProcessHeap; // rax
  _DWORD *v7; // rax
  __int64 v8; // rcx

  v3 = operator new(0x38u);
  v4 = v3;
  if ( v3 )
  {
    *((_DWORD *)v3 + 2) = 1;
    *((_DWORD *)v3 + 4) = -2147418113;
    v3[3] = 0;
    *((_DWORD *)v3 + 8) = 0;
    v3[5] = 0;
    *v3 = &COMXProc::CThreadTaskVolumeEvent::`vftable';
    v5 = CThreadTaskRegister::RegisterWithService((CThreadTaskRegister *)v3);
    if ( v5 >= 0 )
    {
      ProcessHeap = GetProcessHeap();
      v7 = HeapAlloc(ProcessHeap, 8u, 0x218u);
      v4[5] = v7;
      if ( v7 )
      {
        *v7 = 536;
        *(_DWORD *)(v4[5] + 4LL) = 4;
        *(_DWORD *)(v4[5] + 8LL) = 0;
        v8 = v4[5];
        v4[6] = v8 + 94;
        v5 = StringCchCopyW((unsigned __int16 *)(v8 + 12), 0x104u, (const unsigned __int16 *)this);
        if ( v5 >= 0 )
          v5 = CThreadTask::Run(v4);
      }
      else
      {
        v5 = -2147024882;
      }
    }
    CRefCounted::Release((CRefCounted *)v4);
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180029eec  mov     [rsp+arg_0], rbx
0x180029ef1  mov     [rsp+arg_8], rsi
0x180029ef6  push    rdi
0x180029ef7  sub     rsp, 20h
0x180029efb  mov     rsi, rcx
0x180029efe  mov     ecx, 38h ; '8'; Size
0x180029f03  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180029f08  mov     rbx, rax
0x180029f0b  test    rax, rax
0x180029f0e  jz      loc_180029FCC
0x180029f14  mov     dword ptr [rax+8], 1
0x180029f1b  mov     rcx, rbx; this
0x180029f1e  mov     dword ptr [rax+10h], 8000FFFFh
0x180029f25  mov     qword ptr [rax+18h], 0
0x180029f2d  mov     dword ptr [rax+20h], 0
0x180029f34  mov     qword ptr [rax+28h], 0
0x180029f3c  lea     rax, ??_7CThreadTaskVolumeEvent@COMXProc@@6B@; const COMXProc::CThreadTaskVolumeEvent::`vftable'
0x180029f43  mov     [rbx], rax
0x180029f46  call    ?RegisterWithService@CThreadTaskRegister@@QEAAJXZ; CThreadTaskRegister::RegisterWithService(void)
0x180029f4b  mov     edi, eax
0x180029f4d  test    eax, eax
0x180029f4f  js      short loc_180029FC2
0x180029f51  call    cs:__imp_GetProcessHeap
0x180029f57  mov     edi, 218h
0x180029f5c  mov     edx, 8; dwFlags
0x180029f61  mov     rcx, rax; hHeap
0x180029f64  mov     r8d, edi; dwBytes
0x180029f67  call    cs:__imp_HeapAlloc
0x180029f6d  mov     [rbx+28h], rax
0x180029f71  test    rax, rax
0x180029f74  jnz     short loc_180029F7D
0x180029f76  mov     edi, 8007000Eh
0x180029f7b  jmp     short loc_180029FC2
0x180029f7d  mov     [rax], edi
0x180029f7f  mov     r8, rsi; unsigned __int16 *
0x180029f82  mov     rax, [rbx+28h]
0x180029f86  mov     edx, 104h; unsigned __int64
0x180029f8b  mov     dword ptr [rax+4], 4
0x180029f92  mov     rax, [rbx+28h]
0x180029f96  mov     dword ptr [rax+8], 0
0x180029f9d  mov     rcx, [rbx+28h]
0x180029fa1  lea     rax, [rcx+5Eh]
0x180029fa5  add     rcx, 0Ch; unsigned __int16 *
0x180029fa9  mov     [rbx+30h], rax
0x180029fad  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180029fb2  mov     edi, eax
0x180029fb4  test    eax, eax
0x180029fb6  js      short loc_180029FC2
0x180029fb8  mov     rcx, rbx; Context
0x180029fbb  call    ?Run@CThreadTask@@QEAAJXZ; CThreadTask::Run(void)
0x180029fc0  mov     edi, eax
0x180029fc2  mov     rcx, rbx; this
0x180029fc5  call    ?Release@CRefCounted@@QEBAKXZ; CRefCounted::Release(void)
0x180029fca  jmp     short loc_180029FD1
0x180029fcc  mov     edi, 8007000Eh
0x180029fd1  mov     rbx, [rsp+28h+arg_0]
0x180029fd6  mov     eax, edi
0x180029fd8  mov     rsi, [rsp+28h+arg_8]
0x180029fdd  add     rsp, 20h
0x180029fe1  pop     rdi
0x180029fe2  retn
```
