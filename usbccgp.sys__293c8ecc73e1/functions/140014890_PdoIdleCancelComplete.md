# PdoIdleCancelComplete

- ea: `0x140014890`
- end: `0x140014998`
- name: `PdoIdleCancelComplete`
- size: `264`
- prototype: `IO_CSQ_COMPLETE_CANCELED_IRP`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1400054a0`
- `0x1400059e4`
- `0x140008eac`
- `0x140014890`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140014943`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014943`
- `ntoskrnl!IofCompleteRequest` at `0x14001495b`
- `ntoskrnl!IofCompleteRequest` at `0x14001495b`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140014982`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140014982`
- `ntoskrnl!ExAllocatePool2` at `0x140014903`
- `ntoskrnl!ExAllocatePool2` at `0x140014903`

## pseudocode

```c
void __fastcall PdoIdleCancelComplete(char *Csq, PIRP Irp)
{
  char *v2; // rbx
  PIRP v3; // rdi
  void (__fastcall *v4)(_IO_CSQ *, _IRP *); // rbp
  __int64 Pool2; // rax
  void *v6; // rsi
  char v7; // [rsp+30h] [rbp-38h]

  v2 = Csq - 120;
  v3 = Irp;
  v4 = (void (__fastcall *)(_IO_CSQ *, _IRP *))*((_QWORD *)Csq + 14);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v7 = (char)Irp;
    LOBYTE(Irp) = 4;
    WPP_RECORDER_SF_qq(
      *((_QWORD *)v2 + 49),
      (_DWORD)Irp,
      7,
      11,
      (__int64)WPP_c22e0bd291983066d7104eda50c0b1f9_Traceguids,
      *((_QWORD *)v2 + 28),
      v7);
  }
  if ( v2[301] )
  {
    Pool2 = ExAllocatePool2(64, 24, 1130525525);
    v6 = (void *)Pool2;
    if ( Pool2 )
    {
      *(_QWORD *)(Pool2 + 16) = v3;
      *(_QWORD *)Pool2 = v2;
      *(_DWORD *)(Pool2 + 8) = -1073741536;
      if ( (int)AllocateWorker(v4, &PdoIdleCancelCompleteWorker, Pool2) >= 0 )
        return;
      ExFreePoolWithTag(v6, 0x43627355u);
    }
  }
  v3->IoStatus.Status = -1073741536;
  IofCompleteRequest(v3, 0);
  UsbcReleaseRemoveLock(v4, v3);
  IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)((char *)v4 + 200), v3, 0x20u);
}

```

## disassembly

```asm
0x140014890  push    rbx
0x140014892  push    rbp
0x140014893  push    rsi
0x140014894  push    rdi
0x140014895  sub     rsp, 48h
0x140014899  lea     rbx, [rcx-78h]
0x14001489d  mov     rdi, rdx
0x1400148a0  mov     rbp, [rbx+0E8h]
0x1400148a7  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400148ae  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400148b5  jz      short loc_1400148EC
0x1400148b7  mov     rax, [rbx+0E0h]
0x1400148be  mov     r9d, 0Bh
0x1400148c4  mov     rcx, [rbx+188h]
0x1400148cb  mov     qword ptr [rsp+68h+var_38], rdx
0x1400148d0  mov     dl, 4
0x1400148d2  mov     [rsp+68h+var_40], rax
0x1400148d7  lea     rax, WPP_c22e0bd291983066d7104eda50c0b1f9_Traceguids
0x1400148de  lea     r8d, [r9-4]
0x1400148e2  mov     [rsp+68h+var_48], rax
0x1400148e7  call    WPP_RECORDER_SF_qq
0x1400148ec  cmp     byte ptr [rbx+12Dh], 0
0x1400148f3  jz      short loc_14001494F
0x1400148f5  mov     edx, 18h
0x1400148fa  mov     r8d, 43627355h
0x140014900  lea     ecx, [rdx+28h]
0x140014903  call    cs:__imp_ExAllocatePool2
0x14001490a  nop     dword ptr [rax+rax+00h]
0x14001490f  mov     rsi, rax
0x140014912  test    rax, rax
0x140014915  jz      short loc_14001494F
0x140014917  mov     r8, rax
0x14001491a  mov     [rax+10h], rdi
0x14001491e  lea     rdx, PdoIdleCancelCompleteWorker
0x140014925  mov     [rax], rbx
0x140014928  mov     rcx, rbp
0x14001492b  mov     dword ptr [rax+8], 0C0000120h
0x140014932  call    AllocateWorker
0x140014937  test    eax, eax
0x140014939  jns     short loc_14001498E
0x14001493b  mov     edx, 43627355h; Tag
0x140014940  mov     rcx, rsi; P
0x140014943  call    cs:__imp_ExFreePoolWithTag
0x14001494a  nop     dword ptr [rax+rax+00h]
0x14001494f  xor     edx, edx; PriorityBoost
0x140014951  mov     dword ptr [rdi+30h], 0C0000120h
0x140014958  mov     rcx, rdi; Irp
0x14001495b  call    cs:__imp_IofCompleteRequest
0x140014962  nop     dword ptr [rax+rax+00h]
0x140014967  mov     rdx, rdi
0x14001496a  mov     rcx, rbp
0x14001496d  call    UsbcReleaseRemoveLock
0x140014972  lea     rcx, [rbp+0C8h]; RemoveLock
0x140014979  mov     r8d, 20h ; ' '; RemlockSize
0x14001497f  mov     rdx, rdi; Tag
0x140014982  call    cs:__imp_IoReleaseRemoveLockEx
0x140014989  nop     dword ptr [rax+rax+00h]
0x14001498e  add     rsp, 48h
0x140014992  pop     rdi
0x140014993  pop     rsi
0x140014994  pop     rbp
0x140014995  pop     rbx
0x140014996  retn
```
