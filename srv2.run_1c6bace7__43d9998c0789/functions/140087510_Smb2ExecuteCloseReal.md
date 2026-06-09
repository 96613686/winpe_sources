# Smb2ExecuteCloseReal

- ea: `0x140087510`
- end: `0x1400876d4`
- name: `Smb2ExecuteCloseReal`
- size: `452`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400874f0`

## callees

- `0x140005070`
- `0x140007900`
- `0x140008190`
- `0x14000c8e0`
- `0x140012c30`
- `0x1400154b0`
- `0x14001b3fc`
- `0x1400329f0`
- `0x140085de0`
- `0x140087510`

## import_xrefs

- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140087590`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140087590`
- `srvnet!SrvXsSchedulePrintJob` at `0x140087639`
- `srvnet!SrvXsSchedulePrintJob` at `0x140087639`

## string_xrefs

- `0x140087571`: `Srv2PostToThreadPool`

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
0x140087510  mov     rax, rsp
0x140087513  mov     [rax+18h], rbx
0x140087517  mov     [rax+20h], rbp
0x14008751b  push    rsi
0x14008751c  push    rdi
0x14008751d  push    r14
0x14008751f  sub     rsp, 30h
0x140087523  mov     rdi, [rcx+230h]
0x14008752a  xor     esi, esi
0x14008752c  xor     bpl, bpl
0x14008752f  mov     [rax+10h], esi
0x140087532  mov     [rax+8], bpl
0x140087536  mov     rbx, rcx
0x140087539  mov     rax, [rdi+38h]
0x14008753d  cmp     dword ptr [rax+4Ch], 7Fh
0x140087541  jnz     loc_1400875D1
0x140087547  cmp     dword ptr [rcx+48h], 2
0x14008754b  jz      short loc_1400875B5
0x14008754d  cmp     dword ptr [rcx+8], 5
0x140087551  lea     rax, Smb2ExecuteCloseReal
0x140087558  mov     [rcx+30h], rax
0x14008755c  mov     dword ptr [rcx+48h], 2
0x140087563  jnz     short loc_140087585
0x140087565  add     rcx, 248h
0x14008756c  mov     [rsp+48h+var_28], 1
0x140087571  lea     r9, SourceString; "Srv2PostToThreadPool"
0x140087578  mov     r8d, 187h
0x14008757e  mov     dl, 1
0x140087580  call    SRV2_PERF_ENTER_EX
0x140087585  mov     rax, [rbx+40h]
0x140087589  mov     rdi, [rax+98h]
0x140087590  call    cs:__imp_KeGetCurrentNodeNumber
0x140087597  nop     dword ptr [rax+rax+00h]
0x14008759c  movzx   ecx, ax
0x14008759f  xor     r8d, r8d
0x1400875a2  lea     rdx, [rbx+20h]
0x1400875a6  mov     rcx, [rdi+rcx*8+8]
0x1400875ab  call    RfspThreadPoolNodeQueueWorkItem
0x1400875b0  jmp     loc_1400876C0
0x1400875b5  mov     rcx, [rdi+48h]
0x1400875b9  lea     r8, [rsp+48h+arg_8]
0x1400875be  lea     rdx, [rsp+48h+arg_0]
0x1400875c3  call    Smb2GetSpoolJobID
0x1400875c8  mov     esi, [rsp+48h+arg_8]
0x1400875cc  mov     bpl, [rsp+48h+arg_0]
0x1400875d1  cmp     byte ptr [rdi+0C0h], 0
0x1400875d8  jz      short loc_1400875ED
0x1400875da  mov     rcx, rbx
0x1400875dd  call    Smb2ForceUpdateAndQueryAttributesOnClose
0x1400875e2  test    eax, eax
0x1400875e4  jns     short loc_1400875ED
0x1400875e6  mov     byte ptr [rdi+0C0h], 0
0x1400875ed  mov     rcx, [rdi+50h]; P
0x1400875f1  lea     r14, [rbx+248h]
0x1400875f8  test    rcx, rcx
0x1400875fb  jz      short loc_14008760D
0x1400875fd  mov     rdx, r14
0x140087600  call    Smb2DereferenceHandleEx
0x140087605  mov     qword ptr [rdi+50h], 0
0x14008760d  mov     rcx, [rdi+48h]
0x140087611  xor     r9d, r9d
0x140087614  xor     r8d, r8d
0x140087617  mov     qword ptr [rsp+48h+var_28], r14
0x14008761c  mov     dl, 1
0x14008761e  call    Smb2CloseFileEx
0x140087623  test    bpl, bpl
0x140087626  jz      short loc_140087645
0x140087628  mov     rax, [rdi+38h]
0x14008762c  mov     edx, esi
0x14008762e  mov     rcx, [rax+60h]
0x140087632  mov     rcx, [rcx+168h]
0x140087639  call    cs:__imp_SrvXsSchedulePrintJob
0x140087640  nop     dword ptr [rax+rax+00h]
0x140087645  mov     rcx, rbx
0x140087648  call    Srv2SetResponseBufferToReceiveBuffer
0x14008764d  mov     rax, [rbx+138h]
0x140087654  mov     rcx, [rax+18h]
0x140087658  xor     eax, eax
0x14008765a  mov     dword ptr [rcx+44h], 0
0x140087661  mov     word ptr [rcx+40h], 3Ch ; '<'
0x140087667  cmp     [rdi+0C0h], al
0x14008766d  setnz   al
0x140087670  xor     edx, edx
0x140087672  mov     [rcx+42h], ax
0x140087676  movups  xmm0, xmmword ptr [rdi+0C8h]
0x14008767d  movups  xmmword ptr [rcx+48h], xmm0
0x140087681  movups  xmm1, xmmword ptr [rdi+0D8h]
0x140087688  movups  xmmword ptr [rcx+58h], xmm1
0x14008768c  movups  xmm0, xmmword ptr [rdi+0E8h]
0x140087693  movups  xmmword ptr [rcx+68h], xmm0
0x140087697  mov     eax, [rdi+0F8h]
0x14008769d  mov     [rcx+78h], eax
0x1400876a0  mov     rcx, rbx
0x1400876a3  mov     rax, [rbx+138h]
0x1400876aa  mov     dword ptr [rax+24h], 7Ch ; '|'
0x1400876b1  call    Smb2SetSuccess
0x1400876b6  xor     edx, edx
0x1400876b8  mov     rcx, rbx
0x1400876bb  call    Srv2CompleteWorkItem
0x1400876c0  mov     rbx, [rsp+48h+arg_10]
0x1400876c5  mov     rbp, [rsp+48h+arg_18]
0x1400876ca  add     rsp, 30h
0x1400876ce  pop     r14
0x1400876d0  pop     rdi
0x1400876d1  pop     rsi
0x1400876d2  retn
```
