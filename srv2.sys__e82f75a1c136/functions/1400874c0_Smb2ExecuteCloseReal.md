# Smb2ExecuteCloseReal

- ea: `0x1400874c0`
- end: `0x140087684`
- name: `Smb2ExecuteCloseReal`
- size: `452`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400874a0`

## callees

- `0x140005070`
- `0x140007900`
- `0x140008190`
- `0x14000c8e0`
- `0x140012c30`
- `0x1400154b0`
- `0x14001b3fc`
- `0x1400329f0`
- `0x140085d90`
- `0x1400874c0`

## import_xrefs

- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140087540`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140087540`
- `srvnet!SrvXsSchedulePrintJob` at `0x1400875e9`
- `srvnet!SrvXsSchedulePrintJob` at `0x1400875e9`

## string_xrefs

- `0x140087521`: `Srv2PostToThreadPool`

## pseudocode

```c
char __fastcall Smb2ExecuteCloseReal(__int64 a1, __int64 a2)
{
  __int64 v2; // rdi
  unsigned int v3; // esi
  char v4; // bp
  bool v6; // zf
  __int64 v7; // rdi
  USHORT CurrentNodeNumber; // ax
  char *v10; // rcx
  __int64 v11; // rcx
  char v12; // [rsp+20h] [rbp-28h]
  char v13; // [rsp+50h] [rbp+8h] BYREF
  unsigned int v14; // [rsp+58h] [rbp+10h] BYREF

  v2 = *(_QWORD *)(a1 + 560);
  v3 = 0;
  v4 = 0;
  v14 = 0;
  v13 = 0;
  if ( *(_DWORD *)(*(_QWORD *)(v2 + 56) + 76LL) == 127 )
  {
    if ( *(_DWORD *)(a1 + 72) != 2 )
    {
      v6 = *(_DWORD *)(a1 + 8) == 5;
      *(_QWORD *)(a1 + 48) = Smb2ExecuteCloseReal;
      *(_DWORD *)(a1 + 72) = 2;
      if ( v6 )
      {
        v12 = 1;
        LOBYTE(a2) = 1;
        SRV2_PERF_ENTER_EX(a1 + 584, a2, 391, "Srv2PostToThreadPool", v12);
      }
      v7 = *(_QWORD *)(*(_QWORD *)(a1 + 64) + 152LL);
      CurrentNodeNumber = KeGetCurrentNodeNumber();
      return RfspThreadPoolNodeQueueWorkItem(
               *(union _SLIST_HEADER **)(v7 + 8LL * CurrentNodeNumber + 8),
               (struct _SLIST_ENTRY *)(a1 + 32),
               0);
    }
    Smb2GetSpoolJobID(*(_QWORD *)(v2 + 72), &v13, &v14);
    v3 = v14;
    v4 = v13;
  }
  if ( *(_BYTE *)(v2 + 192) && (int)Smb2ForceUpdateAndQueryAttributesOnClose(a1) < 0 )
    *(_BYTE *)(v2 + 192) = 0;
  v10 = *(char **)(v2 + 80);
  if ( v10 )
  {
    Smb2DereferenceHandleEx(v10, a1 + 584);
    *(_QWORD *)(v2 + 80) = 0;
  }
  Smb2CloseFileEx(*(PVOID *)(v2 + 72), a1 + 584);
  if ( v4 )
    SrvXsSchedulePrintJob(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v2 + 56) + 96LL) + 360LL), v3);
  Srv2SetResponseBufferToReceiveBuffer(a1);
  v11 = *(_QWORD *)(*(_QWORD *)(a1 + 312) + 24LL);
  *(_DWORD *)(v11 + 68) = 0;
  *(_WORD *)(v11 + 64) = 60;
  *(_WORD *)(v11 + 66) = *(_BYTE *)(v2 + 192) != 0;
  *(_OWORD *)(v11 + 72) = *(_OWORD *)(v2 + 200);
  *(_OWORD *)(v11 + 88) = *(_OWORD *)(v2 + 216);
  *(_OWORD *)(v11 + 104) = *(_OWORD *)(v2 + 232);
  *(_DWORD *)(v11 + 120) = *(_DWORD *)(v2 + 248);
  *(_DWORD *)(*(_QWORD *)(a1 + 312) + 36LL) = 124;
  Smb2SetSuccess(a1, 0);
  return Srv2CompleteWorkItem(a1, 0);
}

```

## disassembly

```asm
0x1400874c0  mov     rax, rsp
0x1400874c3  mov     [rax+18h], rbx
0x1400874c7  mov     [rax+20h], rbp
0x1400874cb  push    rsi
0x1400874cc  push    rdi
0x1400874cd  push    r14
0x1400874cf  sub     rsp, 30h
0x1400874d3  mov     rdi, [rcx+230h]
0x1400874da  xor     esi, esi
0x1400874dc  xor     bpl, bpl
0x1400874df  mov     [rax+10h], esi
0x1400874e2  mov     [rax+8], bpl
0x1400874e6  mov     rbx, rcx
0x1400874e9  mov     rax, [rdi+38h]
0x1400874ed  cmp     dword ptr [rax+4Ch], 7Fh
0x1400874f1  jnz     loc_140087581
0x1400874f7  cmp     dword ptr [rcx+48h], 2
0x1400874fb  jz      short loc_140087565
0x1400874fd  cmp     dword ptr [rcx+8], 5
0x140087501  lea     rax, Smb2ExecuteCloseReal
0x140087508  mov     [rcx+30h], rax
0x14008750c  mov     dword ptr [rcx+48h], 2
0x140087513  jnz     short loc_140087535
0x140087515  add     rcx, 248h
0x14008751c  mov     [rsp+48h+var_28], 1
0x140087521  lea     r9, SourceString; "Srv2PostToThreadPool"
0x140087528  mov     r8d, 187h
0x14008752e  mov     dl, 1
0x140087530  call    SRV2_PERF_ENTER_EX
0x140087535  mov     rax, [rbx+40h]
0x140087539  mov     rdi, [rax+98h]
0x140087540  call    cs:__imp_KeGetCurrentNodeNumber
0x140087547  nop     dword ptr [rax+rax+00h]
0x14008754c  movzx   ecx, ax
0x14008754f  xor     r8d, r8d
0x140087552  lea     rdx, [rbx+20h]
0x140087556  mov     rcx, [rdi+rcx*8+8]
0x14008755b  call    RfspThreadPoolNodeQueueWorkItem
0x140087560  jmp     loc_140087670
0x140087565  mov     rcx, [rdi+48h]
0x140087569  lea     r8, [rsp+48h+arg_8]
0x14008756e  lea     rdx, [rsp+48h+arg_0]
0x140087573  call    Smb2GetSpoolJobID
0x140087578  mov     esi, [rsp+48h+arg_8]
0x14008757c  mov     bpl, [rsp+48h+arg_0]
0x140087581  cmp     byte ptr [rdi+0C0h], 0
0x140087588  jz      short loc_14008759D
0x14008758a  mov     rcx, rbx
0x14008758d  call    Smb2ForceUpdateAndQueryAttributesOnClose
0x140087592  test    eax, eax
0x140087594  jns     short loc_14008759D
0x140087596  mov     byte ptr [rdi+0C0h], 0
0x14008759d  mov     rcx, [rdi+50h]; P
0x1400875a1  lea     r14, [rbx+248h]
0x1400875a8  test    rcx, rcx
0x1400875ab  jz      short loc_1400875BD
0x1400875ad  mov     rdx, r14
0x1400875b0  call    Smb2DereferenceHandleEx
0x1400875b5  mov     qword ptr [rdi+50h], 0
0x1400875bd  mov     rcx, [rdi+48h]
0x1400875c1  xor     r9d, r9d
0x1400875c4  xor     r8d, r8d
0x1400875c7  mov     qword ptr [rsp+48h+var_28], r14
0x1400875cc  mov     dl, 1
0x1400875ce  call    Smb2CloseFileEx
0x1400875d3  test    bpl, bpl
0x1400875d6  jz      short loc_1400875F5
0x1400875d8  mov     rax, [rdi+38h]
0x1400875dc  mov     edx, esi
0x1400875de  mov     rcx, [rax+60h]
0x1400875e2  mov     rcx, [rcx+168h]
0x1400875e9  call    cs:__imp_SrvXsSchedulePrintJob
0x1400875f0  nop     dword ptr [rax+rax+00h]
0x1400875f5  mov     rcx, rbx
0x1400875f8  call    Srv2SetResponseBufferToReceiveBuffer
0x1400875fd  mov     rax, [rbx+138h]
0x140087604  mov     rcx, [rax+18h]
0x140087608  xor     eax, eax
0x14008760a  mov     dword ptr [rcx+44h], 0
0x140087611  mov     word ptr [rcx+40h], 3Ch ; '<'
0x140087617  cmp     [rdi+0C0h], al
0x14008761d  setnz   al
0x140087620  xor     edx, edx
0x140087622  mov     [rcx+42h], ax
0x140087626  movups  xmm0, xmmword ptr [rdi+0C8h]
0x14008762d  movups  xmmword ptr [rcx+48h], xmm0
0x140087631  movups  xmm1, xmmword ptr [rdi+0D8h]
0x140087638  movups  xmmword ptr [rcx+58h], xmm1
0x14008763c  movups  xmm0, xmmword ptr [rdi+0E8h]
0x140087643  movups  xmmword ptr [rcx+68h], xmm0
0x140087647  mov     eax, [rdi+0F8h]
0x14008764d  mov     [rcx+78h], eax
0x140087650  mov     rcx, rbx
0x140087653  mov     rax, [rbx+138h]
0x14008765a  mov     dword ptr [rax+24h], 7Ch ; '|'
0x140087661  call    Smb2SetSuccess
0x140087666  xor     edx, edx
0x140087668  mov     rcx, rbx
0x14008766b  call    Srv2CompleteWorkItem
0x140087670  mov     rbx, [rsp+48h+arg_10]
0x140087675  mov     rbp, [rsp+48h+arg_18]
0x14008767a  add     rsp, 30h
0x14008767e  pop     r14
0x140087680  pop     rdi
0x140087681  pop     rsi
0x140087682  retn
```
