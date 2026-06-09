# SP_DRIVE::BuildChildPacketsIo(SC_PACKET *,SC_SEQUENTIAL *)

- ea: `0x140009380`
- end: `0x14000975f`
- name: `?BuildChildPacketsIo@SP_DRIVE@@QEAAJPEAVSC_PACKET@@PEAVSC_SEQUENTIAL@@@Z`
- size: `991`
- prototype: `__int64 __fastcall(SP_DRIVE *__hidden this, struct SC_PACKET *, struct SC_SEQUENTIAL *)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140008d50`
- `0x140009160`

## callees

- `0x140009380`
- `0x140068000`

## import_xrefs

- `ntoskrnl!IoAllocateIrp` at `0x140009436`
- `ntoskrnl!IoAllocateIrp` at `0x140009436`
- `ntoskrnl!IoReuseIrp` at `0x14000965d`
- `ntoskrnl!IoReuseIrp` at `0x14000965d`
- `ntoskrnl!IoPropagateIrpExtensionEx` at `0x1400094e1`
- `ntoskrnl!IoPropagateIrpExtensionEx` at `0x1400094e1`
- `ntoskrnl!IoSetIoPriorityHint` at `0x140009495`
- `ntoskrnl!IoSetIoPriorityHint` at `0x14000970d`
- `ntoskrnl!IoSetIoPriorityHint` at `0x140009495`
- `ntoskrnl!IoSetIoPriorityHint` at `0x14000970d`
- `ntoskrnl!IoGetIoPriorityHint` at `0x140009484`
- `ntoskrnl!IoGetIoPriorityHint` at `0x140009526`
- `ntoskrnl!IoGetIoPriorityHint` at `0x140009484`
- `ntoskrnl!IoGetIoPriorityHint` at `0x140009526`

## pseudocode

```c
__int64 __fastcall SP_DRIVE::BuildChildPacketsIo(SP_DRIVE *this, struct SC_PACKET *a2, struct SC_SEQUENTIAL *a3)
{
  int v4; // ecx
  LARGE_INTEGER v6; // r12
  IRP *v7; // r14
  int v8; // ebp
  PIRP Irp; // rax
  IRP *v10; // rsi
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rdi
  IO_PRIORITY_HINT v12; // eax
  __int64 v13; // r9
  __int64 v14; // r8
  __int64 result; // rax
  struct _IO_STACK_LOCATION *v16; // rcx
  IO_PRIORITY_HINT IoPriorityHint; // eax
  __int64 v18; // rcx
  unsigned __int8 v19; // al
  struct _IO_STACK_LOCATION *v20; // rdi
  int v21; // ecx
  int v22; // ecx
  __int64 v23; // rax
  IO_PRIORITY_HINT v24; // eax

  v4 = *((unsigned __int8 *)a2 + 168);
  v6 = *(LARGE_INTEGER *)((char *)a2 + 192);
  v7 = *(IRP **)(*((_QWORD *)a2 + 1) + 80LL);
  if ( v4 != 14 )
  {
    v21 = v4 - 3;
    if ( !v21 )
    {
      if ( !*((_QWORD *)this + 58) )
      {
        v8 = -1058602979;
        goto LABEL_9;
      }
      if ( !*((_BYTE *)this + 568) )
        goto LABEL_7;
LABEL_34:
      v8 = -1058602980;
      goto LABEL_9;
    }
    v22 = v21 - 1;
    if ( v22 )
    {
      if ( v22 != 5 )
        return 3221225485LL;
      v23 = *((_QWORD *)this + 76);
      if ( v23 && *(_BYTE *)(v23 + 66)
        || *((_DWORD *)this + 186) != 1 && *((_DWORD *)this + 186) != 2 && *((_DWORD *)this + 186) != 4 )
      {
        return 15138818;
      }
    }
  }
  if ( *((_DWORD *)this + 140) == 1 )
    return 3236364315LL;
  if ( *((_DWORD *)this + 140) == 2 )
  {
    v8 = -2147483631;
    goto LABEL_9;
  }
  v8 = -1073740669;
  if ( *((_DWORD *)this + 144) == -1073740669 )
    goto LABEL_9;
  if ( !*((_QWORD *)this + 58) )
  {
    v8 = -1058602979;
    goto LABEL_9;
  }
  if ( *((_BYTE *)this + 568) )
    goto LABEL_34;
LABEL_7:
  v8 = 0;
  if ( *((_BYTE *)this + 566) )
    v8 = -1073740647;
LABEL_9:
  if ( v8 < 0 )
    return (unsigned int)v8;
  if ( a3 )
  {
    v10 = (IRP *)*((_QWORD *)this + 150);
    IoReuseIrp(v10, 0);
    --v10->CurrentLocation;
    --v10->Tail.Overlay.CurrentStackLocation;
  }
  else if ( (*((_DWORD *)a2 + 19) & 4) != 0 && v7 && v7->CurrentLocation > *(_BYTE *)(*((_QWORD *)this + 82) + 76LL) )
  {
    v10 = *(IRP **)(*((_QWORD *)a2 + 1) + 80LL);
  }
  else
  {
    Irp = IoAllocateIrp(*(_BYTE *)(*((_QWORD *)this + 82) + 76LL) + 1, 0);
    v10 = Irp;
    if ( !Irp )
      return 3221225626LL;
    --Irp->CurrentLocation;
    --Irp->Tail.Overlay.CurrentStackLocation;
  }
  CurrentStackLocation = v10->Tail.Overlay.CurrentStackLocation;
  if ( !v7 || v10 == v7 )
  {
LABEL_20:
    IoPriorityHint = IoGetIoPriorityHint(v10);
    v18 = *((_QWORD *)a2 + 29);
    *((_DWORD *)a2 + 46) = IoPriorityHint;
    if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v18 + 24LL))(v18) != 5 )
    {
      v24 = (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)a2 + 29) + 24LL))(*((_QWORD *)a2 + 29));
      IoSetIoPriorityHint(v10, v24);
    }
    v19 = *((_BYTE *)a2 + 168);
    *(_WORD *)&CurrentStackLocation[-1].MajorFunction = v19;
    if ( v19 != 4 )
    {
      if ( v19 == 9 )
      {
        CurrentStackLocation[-1].Flags |= 1u;
        goto LABEL_24;
      }
      if ( v19 != 3 )
      {
        if ( v19 == 14 )
        {
          v10->AssociatedIrp.MasterIrp = (struct _IRP *)(*(_QWORD *)(*((_QWORD *)a2 + 15) + 32LL)
                                                       + *(unsigned int *)(*((_QWORD *)a2 + 15) + 44LL));
          CurrentStackLocation[-1].Parameters.Read.Length = *(_DWORD *)(*((_QWORD *)a2 + 15) + 40LL);
          CurrentStackLocation[-1].Parameters.Create.Options = *(_DWORD *)(*((_QWORD *)a2 + 15) + 40LL);
          CurrentStackLocation[-1].Parameters.Read.ByteOffset.LowPart = 2987012;
        }
        goto LABEL_24;
      }
    }
    v10->MdlAddress = (PMDL)*((_QWORD *)a2 + 15);
    CurrentStackLocation[-1].Parameters.Read.ByteOffset = v6;
    CurrentStackLocation[-1].Parameters.Read.Length = *((_DWORD *)a2 + 36);
LABEL_24:
    CurrentStackLocation[-1].Flags |= 0x10u;
    v20 = v10->Tail.Overlay.CurrentStackLocation;
    v20->MinorFunction = 84;
    v20->Parameters.WMI.ProviderId = 1833528662;
    v20->Parameters.QueryDirectory.FileName = (PUNICODE_STRING)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)a2 + 29)
                                                                                                 + 16LL))(*((_QWORD *)a2 + 29));
    result = (unsigned int)v8;
    v20->Parameters.Read.ByteOffset.QuadPart = (LONGLONG)a2;
    v20->Parameters.CreatePipe.Parameters = 0;
    *((_DWORD *)a2 + 18) = 1;
    *((_QWORD *)a2 + 10) = v10;
    return result;
  }
  v10->Flags |= v7->Flags & 2;
  v12 = IoGetIoPriorityHint(v7);
  IoSetIoPriorityHint(v10, v12);
  v13 = 19;
  v10->Tail.Overlay.Thread = v7->Tail.Overlay.Thread;
  v10->Tail.Overlay.OriginalFileObject = v7->Tail.Overlay.OriginalFileObject;
  v14 = *((unsigned int *)a2 + 41);
  if ( (_DWORD)v14 == -1 )
  {
    v13 = 3;
    v14 = 0;
  }
  result = IoPropagateIrpExtensionEx(v7, v10, v14, v13);
  v8 = result;
  if ( (int)result >= 0 )
  {
    v16 = v7->Tail.Overlay.CurrentStackLocation;
    *(_OWORD *)&CurrentStackLocation[-1].MajorFunction = *(_OWORD *)&v16->MajorFunction;
    *(_OWORD *)&CurrentStackLocation[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&v16->Parameters.NotifyDirectoryEx.CompletionFilter;
    *(_OWORD *)(&CurrentStackLocation[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&v16->Parameters.SetQuota + 6);
    CurrentStackLocation[-1].FileObject = v16->FileObject;
    CurrentStackLocation[-1].Control = 0;
    goto LABEL_20;
  }
  return result;
}

```

## disassembly

```asm
0x140009380  push    rbx
0x140009382  push    rbp
0x140009383  push    rsi
0x140009384  push    r12
0x140009386  push    r14
0x140009388  push    r15
0x14000938a  sub     rsp, 28h
0x14000938e  mov     rax, [rdx+8]
0x140009392  mov     rsi, rcx
0x140009395  movzx   ecx, byte ptr [rdx+0A8h]
0x14000939c  mov     rbx, rdx
0x14000939f  mov     r12, [rdx+0C0h]
0x1400093a6  mov     r14, [rax+50h]
0x1400093aa  cmp     ecx, 0Eh
0x1400093ad  jnz     loc_14000961F
0x1400093b3  cmp     dword ptr [rsi+230h], 1
0x1400093ba  jz      loc_140009728
0x1400093c0  mov     eax, [rsi+240h]
0x1400093c6  xor     r15d, r15d
0x1400093c9  cmp     dword ptr [rsi+230h], 2
0x1400093d0  jz      loc_140009679
0x1400093d6  mov     ebp, 0C0000483h
0x1400093db  cmp     eax, ebp
0x1400093dd  jz      short loc_14000940B
0x1400093df  cmp     [rsi+1D0h], r15
0x1400093e6  jbe     loc_1400095D2
0x1400093ec  cmp     [rsi+238h], r15b
0x1400093f3  jnz     loc_14000963D
0x1400093f9  mov     ebp, r15d
0x1400093fc  mov     eax, 0C0000499h
0x140009401  cmp     [rsi+236h], bpl
0x140009408  cmovnz  ebp, eax
0x14000940b  test    ebp, ebp
0x14000940d  js      loc_140009758
0x140009413  test    r8, r8
0x140009416  jnz     loc_140009651
0x14000941c  mov     eax, [rdx+4Ch]
0x14000941f  test    al, 4
0x140009421  jnz     loc_140009732
0x140009427  mov     rax, [rsi+290h]
0x14000942e  xor     edx, edx; ChargeQuota
0x140009430  movzx   ecx, byte ptr [rax+4Ch]
0x140009434  inc     cl; StackSize
0x140009436  call    cs:__imp_IoAllocateIrp
0x14000943d  nop     dword ptr [rax+rax+00h]
0x140009442  mov     rsi, rax
0x140009445  test    rax, rax
0x140009448  jz      loc_140009683
0x14000944e  dec     byte ptr [rax+43h]
0x140009451  add     qword ptr [rax+0B8h], 0FFFFFFFFFFFFFFB8h
0x140009459  mov     [rsp+58h+arg_0], rdi
0x14000945e  mov     rdi, [rsi+0B8h]
0x140009465  test    r14, r14
0x140009468  jz      loc_140009523
0x14000946e  cmp     rsi, r14
0x140009471  jz      loc_140009523
0x140009477  mov     eax, [r14+10h]
0x14000947b  mov     rcx, r14; Irp
0x14000947e  and     eax, 2
0x140009481  or      [rsi+10h], eax
0x140009484  call    cs:__imp_IoGetIoPriorityHint
0x14000948b  nop     dword ptr [rax+rax+00h]
0x140009490  mov     edx, eax; PriorityHint
0x140009492  mov     rcx, rsi; Irp
0x140009495  call    cs:__imp_IoSetIoPriorityHint
0x14000949c  nop     dword ptr [rax+rax+00h]
0x1400094a1  mov     rax, [r14+98h]
0x1400094a8  mov     r9d, 13h
0x1400094ae  mov     [rsi+98h], rax
0x1400094b5  mov     rdx, rsi
0x1400094b8  mov     rax, [r14+0C0h]
0x1400094bf  mov     rcx, r14
0x1400094c2  mov     [rsi+0C0h], rax
0x1400094c9  mov     eax, 3
0x1400094ce  mov     r8d, [rbx+0A4h]
0x1400094d5  cmp     r8d, 0FFFFFFFFh
0x1400094d9  cmovz   r9d, eax
0x1400094dd  cmovz   r8, r15
0x1400094e1  call    cs:__imp_IoPropagateIrpExtensionEx
0x1400094e8  nop     dword ptr [rax+rax+00h]
0x1400094ed  mov     ebp, eax
0x1400094ef  test    eax, eax
0x1400094f1  js      loc_1400095BE
0x1400094f7  mov     rcx, [r14+0B8h]
0x1400094fe  movups  xmm0, xmmword ptr [rcx]
0x140009501  movups  xmmword ptr [rdi-48h], xmm0
0x140009505  movups  xmm1, xmmword ptr [rcx+10h]
0x140009509  movups  xmmword ptr [rdi-38h], xmm1
0x14000950d  movups  xmm0, xmmword ptr [rcx+20h]
0x140009511  movups  xmmword ptr [rdi-28h], xmm0
0x140009515  movsd   xmm1, qword ptr [rcx+30h]
0x14000951a  movsd   qword ptr [rdi-18h], xmm1
0x14000951f  mov     byte ptr [rdi-45h], 0
0x140009523  mov     rcx, rsi; Irp
0x140009526  call    cs:__imp_IoGetIoPriorityHint
0x14000952d  nop     dword ptr [rax+rax+00h]
0x140009532  mov     rcx, [rbx+0E8h]
0x140009539  mov     [rbx+0B8h], eax
0x14000953f  mov     rax, [rcx]
0x140009542  mov     rax, [rax+18h]
0x140009546  call    _guard_dispatch_icall
0x14000954b  cmp     eax, 5
0x14000954e  jnz     loc_1400096F5
0x140009554  movzx   eax, byte ptr [rbx+0A8h]
0x14000955b  mov     [rdi-48h], al
0x14000955e  mov     byte ptr [rdi-47h], 0
0x140009562  cmp     al, 4
0x140009564  jnz     short loc_1400095DC
0x140009566  mov     rax, [rbx+78h]
0x14000956a  mov     [rsi+8], rax
0x14000956e  mov     [rdi-30h], r12
0x140009572  mov     eax, [rbx+90h]
0x140009578  mov     [rdi-40h], eax
0x14000957b  or      byte ptr [rdi-46h], 10h
0x14000957f  mov     rdi, [rsi+0B8h]
0x140009586  mov     byte ptr [rdi+1], 54h ; 'T'
0x14000958a  mov     qword ptr [rdi+8], 6D496D56h
0x140009592  mov     rcx, [rbx+0E8h]
0x140009599  mov     rax, [rcx]
0x14000959c  mov     rax, [rax+10h]
0x1400095a0  call    _guard_dispatch_icall
0x1400095a5  mov     [rdi+10h], rax
0x1400095a9  mov     eax, ebp
0x1400095ab  mov     [rdi+18h], rbx
0x1400095af  mov     [rdi+20h], r15
0x1400095b3  mov     dword ptr [rbx+48h], 1
0x1400095ba  mov     [rbx+50h], rsi
0x1400095be  mov     rdi, [rsp+58h+arg_0]
0x1400095c3  add     rsp, 28h
0x1400095c7  pop     r15
0x1400095c9  pop     r14
0x1400095cb  pop     r12
0x1400095cd  pop     rsi
0x1400095ce  pop     rbp
0x1400095cf  pop     rbx
0x1400095d0  retn
0x1400095d2  mov     ebp, 0C0E7001Dh
0x1400095d7  jmp     loc_14000940B
0x1400095dc  cmp     al, 9
0x1400095de  jz      loc_1400096EC
0x1400095e4  cmp     al, 3
0x1400095e6  jz      loc_140009566
0x1400095ec  cmp     al, 0Eh
0x1400095ee  jnz     short loc_14000957B
0x1400095f0  mov     rax, [rbx+78h]
0x1400095f4  mov     ecx, [rax+2Ch]
0x1400095f7  add     rcx, [rax+20h]
0x1400095fb  mov     [rsi+18h], rcx
0x1400095ff  mov     rax, [rbx+78h]
0x140009603  mov     ecx, [rax+28h]
0x140009606  mov     [rdi-40h], ecx
0x140009609  mov     rax, [rbx+78h]
0x14000960d  mov     ecx, [rax+28h]
0x140009610  mov     [rdi-38h], ecx
0x140009613  mov     dword ptr [rdi-30h], 2D9404h
0x14000961a  jmp     loc_14000957B
0x14000961f  sub     ecx, 3
0x140009622  jnz     short loc_140009697
0x140009624  xor     r15d, r15d
0x140009627  cmp     [rsi+1D0h], r15
0x14000962e  jbe     short loc_140009647
0x140009630  cmp     [rsi+238h], r15b
0x140009637  jz      loc_1400093F9
0x14000963d  mov     ebp, 0C0E7001Ch
0x140009642  jmp     loc_14000940B
0x140009647  mov     ebp, 0C0E7001Dh
0x14000964c  jmp     loc_14000940B
0x140009651  mov     rsi, [rsi+4B0h]
0x140009658  xor     edx, edx; Iostatus
0x14000965a  mov     rcx, rsi; Irp
0x14000965d  call    cs:__imp_IoReuseIrp
0x140009664  nop     dword ptr [rax+rax+00h]
0x140009669  dec     byte ptr [rsi+43h]
0x14000966c  add     qword ptr [rsi+0B8h], 0FFFFFFFFFFFFFFB8h
0x140009674  jmp     loc_140009459
0x140009679  mov     ebp, 80000011h
0x14000967e  jmp     loc_14000940B
0x140009683  mov     eax, 0C000009Ah
0x140009688  add     rsp, 28h
0x14000968c  pop     r15
0x14000968e  pop     r14
0x140009690  pop     r12
0x140009692  pop     rsi
0x140009693  pop     rbp
0x140009694  pop     rbx
0x140009695  retn
0x140009697  sub     ecx, 1
0x14000969a  jz      loc_1400093B3
0x1400096a0  cmp     ecx, 5
0x1400096a3  jnz     short loc_14000971E
0x1400096a5  mov     rax, [rsi+260h]
0x1400096ac  test    rax, rax
0x1400096af  jz      short loc_1400096B7
0x1400096b1  cmp     byte ptr [rax+42h], 0
0x1400096b5  jnz     short loc_1400096D8
0x1400096b7  mov     ecx, [rsi+2E8h]
0x1400096bd  sub     ecx, 1
0x1400096c0  jz      loc_1400093B3
0x1400096c6  sub     ecx, 1
0x1400096c9  jz      loc_1400093B3
0x1400096cf  cmp     ecx, 2
0x1400096d2  jz      loc_1400093B3
0x1400096d8  mov     eax, 0E70002h
0x1400096dd  add     rsp, 28h
0x1400096e1  pop     r15
0x1400096e3  pop     r14
0x1400096e5  pop     r12
0x1400096e7  pop     rsi
0x1400096e8  pop     rbp
0x1400096e9  pop     rbx
0x1400096ea  retn
0x1400096ec  or      byte ptr [rdi-46h], 1
0x1400096f0  jmp     loc_14000957B
0x1400096f5  mov     rcx, [rbx+0E8h]
0x1400096fc  mov     rax, [rcx]
0x1400096ff  mov     rax, [rax+18h]
0x140009703  call    _guard_dispatch_icall
0x140009708  mov     edx, eax; PriorityHint
0x14000970a  mov     rcx, rsi; Irp
0x14000970d  call    cs:__imp_IoSetIoPriorityHint
0x140009714  nop     dword ptr [rax+rax+00h]
0x140009719  jmp     loc_140009554
0x14000971e  mov     eax, 0C000000Dh
0x140009723  jmp     loc_1400095C3
0x140009728  mov     eax, 0C0E7001Bh
0x14000972d  jmp     loc_1400095C3
0x140009732  test    r14, r14
0x140009735  jz      loc_140009427
0x14000973b  mov     rax, [rsi+290h]
0x140009742  movzx   ecx, byte ptr [rax+4Ch]
0x140009746  cmp     [r14+43h], cl
0x14000974a  jle     loc_140009427
0x140009750  mov     rsi, r14
0x140009753  jmp     loc_140009459
0x140009758  mov     eax, ebp
0x14000975a  jmp     loc_1400095C3
```
