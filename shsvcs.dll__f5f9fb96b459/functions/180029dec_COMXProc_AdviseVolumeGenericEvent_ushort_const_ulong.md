# COMXProc::_AdviseVolumeGenericEvent(ushort const *,ulong)

- ea: `0x180029dec`
- end: `0x180029ee5`
- name: `?_AdviseVolumeGenericEvent@COMXProc@@YAJPEBGK@Z`
- size: `249`
- prototype: `__int64 __fastcall(COMXProc *this, const unsigned __int16 *)`
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
- `0x180029dec`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180029e67`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180029e67`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180029e78`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180029e78`

## pseudocode

```c
__int64 __fastcall COMXProc::_AdviseVolumeGenericEvent(COMXProc *this, const unsigned __int16 *a2)
{
  int v3; // ebp
  _QWORD *v4; // rax
  _QWORD *v5; // rbx
  int v6; // edi
  unsigned int v7; // edi
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v9; // rax

  v3 = (int)a2;
  v4 = operator new(0x30u);
  v5 = v4;
  if ( v4 )
  {
    v4[1] = 1;
    *((_DWORD *)v4 + 5) = 0;
    v4[4] = 0;
    *((_DWORD *)v4 + 4) = -2147418113;
    v4[3] = 0;
    v4[5] = 0;
    *v4 = &COMXProc::CThreadTaskDeviceEvent::`vftable';
    v6 = CThreadTaskRegister::RegisterWithService((CThreadTaskRegister *)v4);
    if ( v6 >= 0 )
    {
      v7 = this != 0 ? 536 : 16;
      ProcessHeap = GetProcessHeap();
      v9 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 8u, v7);
      v5[5] = v9;
      if ( v9 )
      {
        *(_DWORD *)v9 = v7;
        *(_DWORD *)(v5[5] + 4LL) = v3;
        *(_DWORD *)(v5[5] + 8LL) = 0;
        if ( !this || (v6 = StringCchCopyW(v9 + 6, 0x104u, (const unsigned __int16 *)this), v6 >= 0) )
          v6 = CThreadTask::Run(v5);
      }
      else
      {
        v6 = -2147024882;
      }
    }
    CRefCounted::Release((CRefCounted *)v5);
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180029dec  push    rbx
0x180029dee  push    rbp
0x180029def  push    rsi
0x180029df0  push    rdi
0x180029df1  sub     rsp, 28h
0x180029df5  mov     rsi, rcx
0x180029df8  mov     ebp, edx
0x180029dfa  mov     ecx, 30h ; '0'; Size
0x180029dff  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180029e04  mov     rbx, rax
0x180029e07  test    rax, rax
0x180029e0a  jz      loc_180029ED5
0x180029e10  mov     qword ptr [rax+8], 1
0x180029e18  mov     rcx, rbx; this
0x180029e1b  mov     dword ptr [rax+14h], 0
0x180029e22  mov     qword ptr [rax+20h], 0
0x180029e2a  mov     dword ptr [rax+10h], 8000FFFFh
0x180029e31  mov     qword ptr [rax+18h], 0
0x180029e39  mov     qword ptr [rax+28h], 0
0x180029e41  lea     rax, ??_7CThreadTaskDeviceEvent@COMXProc@@6B@; const COMXProc::CThreadTaskDeviceEvent::`vftable'
0x180029e48  mov     [rbx], rax
0x180029e4b  call    ?RegisterWithService@CThreadTaskRegister@@QEAAJXZ; CThreadTaskRegister::RegisterWithService(void)
0x180029e50  mov     edi, eax
0x180029e52  test    eax, eax
0x180029e54  js      short loc_180029ECB
0x180029e56  mov     rax, rsi
0x180029e59  neg     rax
0x180029e5c  sbb     ecx, ecx
0x180029e5e  and     ecx, 208h
0x180029e64  lea     edi, [rcx+10h]
0x180029e67  call    cs:__imp_GetProcessHeap
0x180029e6d  mov     r8d, edi; dwBytes
0x180029e70  mov     edx, 8; dwFlags
0x180029e75  mov     rcx, rax; hHeap
0x180029e78  call    cs:__imp_HeapAlloc
0x180029e7e  mov     [rbx+28h], rax
0x180029e82  mov     rcx, rax
0x180029e85  test    rax, rax
0x180029e88  jnz     short loc_180029E91
0x180029e8a  mov     edi, 8007000Eh
0x180029e8f  jmp     short loc_180029ECB
0x180029e91  mov     [rax], edi
0x180029e93  mov     rax, [rbx+28h]
0x180029e97  mov     [rax+4], ebp
0x180029e9a  mov     rax, [rbx+28h]
0x180029e9e  mov     dword ptr [rax+8], 0
0x180029ea5  test    rsi, rsi
0x180029ea8  jz      short loc_180029EC1
0x180029eaa  add     rcx, 0Ch; unsigned __int16 *
0x180029eae  mov     r8, rsi; unsigned __int16 *
0x180029eb1  mov     edx, 104h; unsigned __int64
0x180029eb6  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180029ebb  mov     edi, eax
0x180029ebd  test    eax, eax
0x180029ebf  js      short loc_180029ECB
0x180029ec1  mov     rcx, rbx; Context
0x180029ec4  call    ?Run@CThreadTask@@QEAAJXZ; CThreadTask::Run(void)
0x180029ec9  mov     edi, eax
0x180029ecb  mov     rcx, rbx; this
0x180029ece  call    ?Release@CRefCounted@@QEBAKXZ; CRefCounted::Release(void)
0x180029ed3  jmp     short loc_180029EDA
0x180029ed5  mov     edi, 8007000Eh
0x180029eda  mov     eax, edi
0x180029edc  add     rsp, 28h
0x180029ee0  pop     rdi
0x180029ee1  pop     rsi
0x180029ee2  pop     rbp
0x180029ee3  pop     rbx
0x180029ee4  retn
```
