# WapTcpCloseSocket

- ea: `0x180046840`
- end: `0x180046978`
- name: `WapTcpCloseSocket`
- size: `312`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180046370`

## callees

- `0x1800452d4`
- `0x180046840`
- `0x180046980`
- `0x180092500`
- `0x180092564`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180046868`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180046868`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800468a3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800468a3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x1800468ee`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x1800468ee`
- `WS2_32!__imp_closesocket` at `0x1800468da`
- `WS2_32!__imp_closesocket` at `0x1800468da`
- `WS2_32!__imp_shutdown` at `0x1800468cb`
- `WS2_32!__imp_shutdown` at `0x1800468cb`

## pseudocode

```c
void __fastcall WapTcpCloseSocket(RTL_SRWLOCK *a1, unsigned __int8 a2)
{
  SOCKET Ptr; // rsi
  struct _TP_IO *v5; // r14
  int v6; // edx
  int v7; // ecx

  if ( (xmmword_1800AD720 & 8) != 0 )
    WPP_SF_qD(1027, 46, WPP_14086b36644f38024399eb8d606249d9_Traceguids, a1, a2);
  AcquireSRWLockExclusive(a1 + 87);
  WapTcpUnmarkForPushLocked(a1);
  Ptr = (SOCKET)a1[88].Ptr;
  v5 = (struct _TP_IO *)a1[89].Ptr;
  a1[88].Ptr = (PVOID)-1LL;
  a1[89].Ptr = 0;
  ReleaseSRWLockExclusive(a1 + 87);
  if ( Ptr != -1 )
  {
    if ( (Microsoft_Windows_WebIOEnableBits & 0x40) != 0 )
      McTemplateU0pxqqxt_EventWriteTransfer(v7, v6, a1[1].Ptr, Ptr, 8, 0, 0, 0);
    if ( a2 )
      shutdown(Ptr, 1);
    closesocket(Ptr);
  }
  if ( v5 )
    CloseThreadpoolIo(v5);
  if ( (xmmword_1800AD720 & 8) != 0 )
    WPP_SF_(1027, 47, WPP_14086b36644f38024399eb8d606249d9_Traceguids);
}

```

## disassembly

```asm
0x180046840  push    rbx
0x180046842  push    rbp
0x180046843  push    rsi
0x180046844  push    rdi
0x180046845  push    r14
0x180046847  sub     rsp, 40h
0x18004684b  movzx   ebp, dl
0x18004684e  mov     rdi, rcx
0x180046851  test    byte ptr cs:xmmword_1800AD720, 8
0x180046858  jnz     loc_18004693E
0x18004685e  lea     rbx, [rdi+2B8h]
0x180046865  mov     rcx, rbx; SRWLock
0x180046868  call    cs:__imp_AcquireSRWLockExclusive
0x18004686f  nop     dword ptr [rax+rax+00h]
0x180046874  mov     rcx, rdi
0x180046877  call    WapTcpUnmarkForPushLocked
0x18004687c  mov     rsi, [rdi+2C0h]
0x180046883  mov     rcx, rbx; SRWLock
0x180046886  mov     r14, [rdi+2C8h]
0x18004688d  mov     qword ptr [rdi+2C0h], 0FFFFFFFFFFFFFFFFh
0x180046898  mov     qword ptr [rdi+2C8h], 0
0x1800468a3  call    cs:__imp_ReleaseSRWLockExclusive
0x1800468aa  nop     dword ptr [rax+rax+00h]
0x1800468af  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x1800468b3  jz      short loc_1800468E6
0x1800468b5  test    byte ptr cs:Microsoft_Windows_WebIOEnableBits, 40h
0x1800468bc  jnz     short loc_18004690F
0x1800468be  test    bpl, bpl
0x1800468c1  jz      short loc_1800468D7
0x1800468c3  mov     edx, 1; how
0x1800468c8  mov     rcx, rsi; s
0x1800468cb  call    cs:__imp_shutdown
0x1800468d2  nop     dword ptr [rax+rax+00h]
0x1800468d7  mov     rcx, rsi; s
0x1800468da  call    cs:__imp_closesocket
0x1800468e1  nop     dword ptr [rax+rax+00h]
0x1800468e6  test    r14, r14
0x1800468e9  jz      short loc_1800468FA
0x1800468eb  mov     rcx, r14; pio
0x1800468ee  call    cs:__imp_CloseThreadpoolIo
0x1800468f5  nop     dword ptr [rax+rax+00h]
0x1800468fa  test    byte ptr cs:xmmword_1800AD720, 8
0x180046901  jnz     short loc_180046960
0x180046903  add     rsp, 40h
0x180046907  pop     r14
0x180046909  pop     rdi
0x18004690a  pop     rsi
0x18004690b  pop     rbp
0x18004690c  pop     rbx
0x18004690d  retn
0x18004690f  mov     r8, [rdi+8]
0x180046913  mov     r9, rsi
0x180046916  mov     [rsp+68h+var_30], 0
0x18004691e  mov     [rsp+68h+var_38], 0
0x180046927  mov     [rsp+68h+var_40], 0
0x18004692f  mov     [rsp+68h+var_48], 8
0x180046937  call    McTemplateU0pxqqxt_EventWriteTransfer
0x18004693c  jmp     short loc_1800468BE
0x18004693e  mov     edx, 2Eh ; '.'
0x180046943  mov     [rsp+68h+var_48], ebp
0x180046947  mov     ecx, 403h
0x18004694c  lea     r8, WPP_14086b36644f38024399eb8d606249d9_Traceguids
0x180046953  mov     r9, rdi
0x180046956  call    WPP_SF_qD
0x18004695b  jmp     loc_18004685E
0x180046960  mov     edx, 2Fh ; '/'
0x180046965  lea     r8, WPP_14086b36644f38024399eb8d606249d9_Traceguids
0x18004696c  mov     ecx, 403h
0x180046971  call    WPP_SF_
0x180046976  jmp     short loc_180046903
```
