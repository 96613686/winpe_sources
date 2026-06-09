# DispatchFdoWaitWake

- ea: `0x14000a1b4`
- end: `0x14000a2f8`
- name: `DispatchFdoWaitWake`
- size: `324`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140003e88`

## callees

- `0x140005940`
- `0x1400083c8`
- `0x140008eac`
- `0x14000a1b4`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14000a2e7`
- `ntoskrnl!IofCompleteRequest` at `0x14000a2e7`
- `ntoskrnl!PoCallDriver` at `0x14000a257`
- `ntoskrnl!PoCallDriver` at `0x14000a257`

## pseudocode

```c
__int64 __fastcall DispatchFdoWaitWake(__int64 a1, IRP *a2)
{
  IRP *v2; // rdi
  struct _DEVICE_OBJECT **v4; // rsi
  _QWORD *v5; // r14
  _IO_STACK_LOCATION *CurrentStackLocation; // rax
  unsigned int v7; // esi

  v2 = a2;
  v4 = (struct _DEVICE_OBJECT **)(a1 + 32);
  v5 = (_QWORD *)(a1 + 1368);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(a2) = 4;
    WPP_RECORDER_SF_qq(
      *v5,
      (_DWORD)a2,
      3,
      29,
      (__int64)WPP_6d8a51a08a9b3edb1d37cbc5358a5e6d_Traceguids,
      (char)*v4,
      (char)v2);
  }
  _InterlockedExchange64((volatile __int64 *)(a1 + 376), (__int64)v2);
  if ( _InterlockedExchange((volatile __int32 *)(a1 + 392), 1) )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = 4;
      WPP_RECORDER_SF_q(*v5, (_DWORD)a2, 3, 30, (__int64)WPP_6d8a51a08a9b3edb1d37cbc5358a5e6d_Traceguids, (char)*v4);
    }
    v7 = -1073741536;
    _InterlockedExchange64((volatile __int64 *)(a1 + 376), 0);
    v2->IoStatus.Status = -1073741536;
    *(_QWORD *)(a1 + 384) = v2;
    IofCompleteRequest(v2, 0);
  }
  else
  {
    CurrentStackLocation = v2->Tail.Overlay.CurrentStackLocation;
    *(_OWORD *)&CurrentStackLocation[-1].MajorFunction = *(_OWORD *)&CurrentStackLocation->MajorFunction;
    *(_OWORD *)&CurrentStackLocation[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&CurrentStackLocation->Parameters.NotifyDirectoryEx.CompletionFilter;
    *(_OWORD *)(&CurrentStackLocation[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&CurrentStackLocation->Parameters.SetQuota
                                                                               + 6);
    CurrentStackLocation[-1].FileObject = CurrentStackLocation->FileObject;
    CurrentStackLocation[-1].Control = 0;
    SetCompletionRoutine(*v5, *v4, v2, (IO_COMPLETION_ROUTINE *)CompletionFdoWaitWake, (PVOID)a1);
    return (unsigned int)PoCallDriver(*(PDEVICE_OBJECT *)(a1 + 40), v2);
  }
  return v7;
}

```

## disassembly

```asm
0x14000a1b4  push    rbx
0x14000a1b6  push    rbp
0x14000a1b7  push    rsi
0x14000a1b8  push    rdi
0x14000a1b9  push    r12
0x14000a1bb  push    r14
0x14000a1bd  sub     rsp, 48h
0x14000a1c1  mov     rdi, rdx
0x14000a1c4  mov     rbx, rcx
0x14000a1c7  lea     rbp, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000a1ce  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14000a1d5  lea     rsi, [rcx+20h]
0x14000a1d9  lea     r14, [rcx+558h]
0x14000a1e0  lea     r12, WPP_6d8a51a08a9b3edb1d37cbc5358a5e6d_Traceguids
0x14000a1e7  jnz     loc_14000A275
0x14000a1ed  mov     rax, rdi
0x14000a1f0  xchg    rax, [rbx+178h]
0x14000a1f7  mov     eax, 1
0x14000a1fc  xchg    eax, [rbx+188h]
0x14000a202  test    eax, eax
0x14000a204  jnz     loc_14000A2A0
0x14000a20a  mov     rax, [rdi+0B8h]
0x14000a211  lea     r9, CompletionFdoWaitWake
0x14000a218  mov     r8, rdi
0x14000a21b  mov     [rsp+78h+var_58], rbx
0x14000a220  movups  xmm0, xmmword ptr [rax]
0x14000a223  movups  xmmword ptr [rax-48h], xmm0
0x14000a227  movups  xmm1, xmmword ptr [rax+10h]
0x14000a22b  movups  xmmword ptr [rax-38h], xmm1
0x14000a22f  movups  xmm0, xmmword ptr [rax+20h]
0x14000a233  movups  xmmword ptr [rax-28h], xmm0
0x14000a237  movsd   xmm1, qword ptr [rax+30h]
0x14000a23c  movsd   qword ptr [rax-18h], xmm1
0x14000a241  mov     byte ptr [rax-45h], 0
0x14000a245  mov     rdx, [rsi]
0x14000a248  mov     rcx, [r14]
0x14000a24b  call    SetCompletionRoutine
0x14000a250  mov     rcx, [rbx+28h]; DeviceObject
0x14000a254  mov     rdx, rdi; Irp
0x14000a257  call    cs:__imp_PoCallDriver
0x14000a25e  nop     dword ptr [rax+rax+00h]
0x14000a263  mov     esi, eax
0x14000a265  mov     eax, esi
0x14000a267  add     rsp, 48h
0x14000a26b  pop     r14
0x14000a26d  pop     r12
0x14000a26f  pop     rdi
0x14000a270  pop     rsi
0x14000a271  pop     rbp
0x14000a272  pop     rbx
0x14000a273  retn
0x14000a275  mov     rax, [rsi]
0x14000a278  mov     r9d, 1Dh
0x14000a27e  mov     rcx, [r14]
0x14000a281  mov     dl, 4
0x14000a283  mov     [rsp+78h+var_48], rdi
0x14000a288  mov     [rsp+78h+var_50], rax
0x14000a28d  lea     r8d, [r9-1Ah]
0x14000a291  mov     [rsp+78h+var_58], r12
0x14000a296  call    WPP_RECORDER_SF_qq
0x14000a29b  jmp     loc_14000A1ED
0x14000a2a0  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x14000a2a7  jz      short loc_14000A2CA
0x14000a2a9  mov     rax, [rsi]
0x14000a2ac  mov     r9d, 1Eh
0x14000a2b2  mov     rcx, [r14]
0x14000a2b5  mov     dl, 4
0x14000a2b7  mov     [rsp+78h+var_50], rax
0x14000a2bc  mov     [rsp+78h+var_58], r12
0x14000a2c1  lea     r8d, [r9-1Bh]
0x14000a2c5  call    WPP_RECORDER_SF_q
0x14000a2ca  xor     eax, eax
0x14000a2cc  mov     esi, 0C0000120h
0x14000a2d1  xchg    rax, [rbx+178h]
0x14000a2d8  mov     [rdi+30h], esi
0x14000a2db  xor     edx, edx; PriorityBoost
0x14000a2dd  mov     rcx, rdi; Irp
0x14000a2e0  mov     [rbx+180h], rdi
0x14000a2e7  call    cs:__imp_IofCompleteRequest
0x14000a2ee  nop     dword ptr [rax+rax+00h]
0x14000a2f3  jmp     loc_14000A265
```
