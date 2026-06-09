# QueueIntfWorkerThread(MSMSEC_INTF_CONTEXT *,void *)

- ea: `0x180025e20`
- end: `0x180025fbe`
- name: `?QueueIntfWorkerThread@@YAKPEAUMSMSEC_INTF_CONTEXT@@PEAX@Z`
- size: `414`
- prototype: `unsigned int __fastcall(struct MSMSEC_INTF_CONTEXT *, void *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180039810`

## callees

- `0x18000892c`
- `0x180008998`
- `0x18000a4e0`
- `0x180013bc0`
- `0x1800169c0`
- `0x180025e20`
- `0x180025fd0`
- `0x180056268`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025eef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025eef`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x180025e95`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x180025e95`

## string_xrefs

- `0x180025e6e`: `QueueIntfWorkerThread`
- `0x180025f50`: `QueueIntfWorkerThread`

## pseudocode

```c
__int64 __fastcall QueueIntfWorkerThread(struct MSMSEC_INTF_CONTEXT *a1, void *a2)
{
  PVOID *v4; // rcx
  unsigned int v5; // ebx
  DWORD LastError; // eax

  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 76, &WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a1 && a2 )
  {
    v5 = 0;
    TraceAdapterId(*((_DWORD *)a1 + 624), ">>> Refing >>>");
    SecMgrRefAdapterEx(a1, "QueueIntfWorkerThread", 1135);
    NetTraceMarkContextActivityStart(a2, 0xEu);
    if ( !QueueUserWorkItem(SecMgrIntfWorker, a2, 0) )
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 78, &WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids, LastError);
        NetTraceMarkContextActivityStop(a2, 0xEu);
        TraceAdapterId(*((_DWORD *)a1 + 624), "<<< Derefing <<<");
        SecMgrDerefAdapterEx(a1, "QueueIntfWorkerThread", 1151);
      }
    }
    goto LABEL_5;
  }
  v5 = 87;
  if ( v4 == &WPP_GLOBAL_Control )
    return v5;
  if ( (*((_BYTE *)v4 + 68) & 1) != 0 )
  {
    WPP_SF_(v4[7], 77, &WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids);
LABEL_5:
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_DWORD *)v4 + 17) & 0x100) != 0 )
    WPP_SF_d(v4[7], 79, &WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids, v5);
  return v5;
}

```

## disassembly

```asm
0x180025e20  push    rbx
0x180025e22  push    rbp
0x180025e23  push    rsi
0x180025e24  push    rdi
0x180025e25  sub     rsp, 28h
0x180025e29  mov     rsi, rdx
0x180025e2c  mov     rdi, rcx
0x180025e2f  mov     rcx, cs:WPP_GLOBAL_Control
0x180025e36  lea     rbp, WPP_GLOBAL_Control
0x180025e3d  cmp     rcx, rbp
0x180025e40  jnz     short loc_180025EC1
0x180025e42  test    rdi, rdi
0x180025e45  jz      loc_180025F64
0x180025e4b  test    rsi, rsi
0x180025e4e  jz      loc_180025F64
0x180025e54  mov     ecx, [rdi+9C0h]; unsigned int
0x180025e5a  lea     rdx, aRefing; ">>> Refing >>>"
0x180025e61  xor     ebx, ebx
0x180025e63  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x180025e68  mov     r8d, 46Fh; int
0x180025e6e  lea     rdx, aQueueintfworke; "QueueIntfWorkerThread"
0x180025e75  mov     rcx, rdi; struct MSMSEC_INTF_CONTEXT *
0x180025e78  call    ?SecMgrRefAdapterEx@@YAXPEAUMSMSEC_INTF_CONTEXT@@PEBDH@Z; SecMgrRefAdapterEx(MSMSEC_INTF_CONTEXT *,char const *,int)
0x180025e7d  lea     edx, [rbx+0Eh]; unsigned int
0x180025e80  mov     rcx, rsi; void *
0x180025e83  call    ?NetTraceMarkContextActivityStart@@YAXPEAXI@Z; NetTraceMarkContextActivityStart(void *,uint)
0x180025e88  xor     r8d, r8d; Flags
0x180025e8b  lea     rcx, ?SecMgrIntfWorker@@YAKPEAX@Z; Function
0x180025e92  mov     rdx, rsi; Context
0x180025e95  call    cs:__imp_QueueUserWorkItem
0x180025e9c  nop     dword ptr [rax+rax+00h]
0x180025ea1  test    eax, eax
0x180025ea3  jz      short loc_180025EEF
0x180025ea5  mov     rcx, cs:WPP_GLOBAL_Control
0x180025eac  cmp     rcx, rbp
0x180025eaf  jnz     loc_180025F94
0x180025eb5  mov     eax, ebx
0x180025eb7  add     rsp, 28h
0x180025ebb  pop     rdi
0x180025ebc  pop     rsi
0x180025ebd  pop     rbp
0x180025ebe  pop     rbx
0x180025ebf  retn
0x180025ec1  test    dword ptr [rcx+44h], 100h
0x180025ec8  jz      loc_180025E42
0x180025ece  mov     rcx, [rcx+38h]
0x180025ed2  lea     r8, WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids
0x180025ed9  mov     edx, 4Ch ; 'L'
0x180025ede  call    WPP_SF_
0x180025ee3  mov     rcx, cs:WPP_GLOBAL_Control
0x180025eea  jmp     loc_180025E42
0x180025eef  call    cs:__imp_GetLastError
0x180025ef6  nop     dword ptr [rax+rax+00h]
0x180025efb  mov     ebx, eax
0x180025efd  test    eax, eax
0x180025eff  jz      short loc_180025EA5
0x180025f01  mov     rcx, cs:WPP_GLOBAL_Control
0x180025f08  cmp     rcx, rbp
0x180025f0b  jz      short loc_180025F2B
0x180025f0d  test    byte ptr [rcx+44h], 1
0x180025f11  jz      short loc_180025F2B
0x180025f13  mov     rcx, [rcx+38h]
0x180025f17  lea     r8, WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids
0x180025f1e  mov     edx, 4Eh ; 'N'
0x180025f23  mov     r9d, eax
0x180025f26  call    WPP_SF_d
0x180025f2b  mov     edx, 0Eh; unsigned int
0x180025f30  mov     rcx, rsi; void *
0x180025f33  call    ?NetTraceMarkContextActivityStop@@YAXPEAXI@Z; NetTraceMarkContextActivityStop(void *,uint)
0x180025f38  mov     ecx, [rdi+9C0h]; unsigned int
0x180025f3e  lea     rdx, aDerefing; "<<< Derefing <<<"
0x180025f45  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x180025f4a  mov     r8d, 47Fh; int
0x180025f50  lea     rdx, aQueueintfworke; "QueueIntfWorkerThread"
0x180025f57  mov     rcx, rdi; struct MSMSEC_INTF_CONTEXT *
0x180025f5a  call    ?SecMgrDerefAdapterEx@@YAXPEAUMSMSEC_INTF_CONTEXT@@PEBDH@Z; SecMgrDerefAdapterEx(MSMSEC_INTF_CONTEXT *,char const *,int)
0x180025f5f  jmp     loc_180025EA5
0x180025f64  mov     ebx, 57h ; 'W'
0x180025f69  cmp     rcx, rbp
0x180025f6c  jz      loc_180025EB5
0x180025f72  test    byte ptr [rcx+44h], 1
0x180025f76  jz      loc_180025EAC
0x180025f7c  mov     rcx, [rcx+38h]
0x180025f80  lea     edx, [rbx-0Ah]
0x180025f83  lea     r8, WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids
0x180025f8a  call    WPP_SF_
0x180025f8f  jmp     loc_180025EA5
0x180025f94  test    dword ptr [rcx+44h], 100h
0x180025f9b  jz      loc_180025EB5
0x180025fa1  mov     rcx, [rcx+38h]
0x180025fa5  lea     r8, WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids
0x180025fac  mov     edx, 4Fh ; 'O'
0x180025fb1  mov     r9d, ebx
0x180025fb4  call    WPP_SF_d
0x180025fb9  jmp     loc_180025EB5
```
