# WcPreFsControl

- ea: `0x140023150`
- end: `0x14002363c`
- name: `WcPreFsControl`
- size: `1260`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData)`
- caller_count: `0`
- callee_count: `19`
- tags: `reparse_path, authz_impersonation`

## callees

- `0x140001500`
- `0x1400016b4`
- `0x140001b00`
- `0x140001bf8`
- `0x1400024fc`
- `0x140006340`
- `0x140019f1c`
- `0x14001a02c`
- `0x14001a148`
- `0x14001a20c`
- `0x14001a364`
- `0x140023150`
- `0x140023644`
- `0x1400237a8`
- `0x140023840`
- `0x140023a54`
- `0x140023c40`
- `0x140023e98`
- `0x14002f9f8`

## import_xrefs

- `ntoskrnl!PsIsCurrentThreadInServerSilo` at `0x1400232c9`
- `ntoskrnl!PsIsCurrentThreadInServerSilo` at `0x140023356`
- `ntoskrnl!PsIsCurrentThreadInServerSilo` at `0x1400232c9`
- `ntoskrnl!PsIsCurrentThreadInServerSilo` at `0x140023356`
- `FLTMGR!FltFsControlFile` at `0x1400235b3`
- `FLTMGR!FltFsControlFile` at `0x1400235b3`
- `FLTMGR!FltGetStreamContext` at `0x140023229`
- `FLTMGR!FltGetStreamContext` at `0x140023229`
- `FLTMGR!FltReleaseContext` at `0x14002325a`
- `FLTMGR!FltReleaseContext` at `0x140023345`
- `FLTMGR!FltReleaseContext` at `0x14002325a`
- `FLTMGR!FltReleaseContext` at `0x140023345`

## pseudocode

```c
__int64 __fastcall WcPreFsControl(PFLT_CALLBACK_DATA CallbackData, __int64 a2, _QWORD *a3)
{
  __int64 v3; // rsi
  PFLT_CALLBACK_DATA v4; // rdi
  unsigned int v5; // ebx
  DWORD LowPart; // eax
  DWORD v8; // eax
  struct _FILE_OBJECT *v10; // rdx
  struct _FLT_INSTANCE *v11; // rcx
  NTSTATUS StreamContext; // ebp
  __int64 v13; // rcx
  __int64 v14; // r9
  char ContextFileObject; // al
  PFLT_CONTEXT v16; // rsi
  bool v17; // zf
  DWORD v18; // eax
  DWORD v19; // eax
  __int64 Source; // rax
  PFLT_IO_PARAMETER_BLOCK Iopb; // rdx
  DWORD v22; // ecx
  NTSTATUS v23; // eax
  DWORD v24; // eax
  PFLT_CONTEXT LengthReturned; // [rsp+60h] [rbp+8h] BYREF
  PFLT_CONTEXT Context; // [rsp+70h] [rbp+18h] BYREF

  v3 = a2;
  *a3 = 0;
  v4 = CallbackData;
  v5 = 1;
  LowPart = CallbackData->Iopb->Parameters.Read.ByteOffset.LowPart;
  if ( LowPart > 0x9013C )
  {
    if ( LowPart > 0x90394 )
    {
      if ( LowPart <= 0x90C23 )
      {
        if ( LowPart != 592931 )
        {
          switch ( LowPart )
          {
            case 0x9039Bu:
            case 0x903A4u:
              return (unsigned int)WcFsctlRedirectDirectMappedRequest(CallbackData);
            case 0x903ABu:
              goto LABEL_23;
            case 0x9040Cu:
LABEL_49:
              v5 = WcPreFsctlSetReparsePoint(CallbackData);
              break;
            case 0x9042Bu:
              goto LABEL_73;
            case 0x90448u:
              return (unsigned int)WcFsctlManageBypassIo(CallbackData, a2);
            default:
              return v5;
          }
          return v5;
        }
        return (unsigned int)WcPreGetUnions();
      }
      else
      {
        if ( LowPart <= 0x98344 )
        {
          if ( LowPart != 623428 )
          {
            v18 = LowPart - 606415;
            if ( !v18 )
              return (unsigned int)WcPreFsctlQueryAllocatedRanges();
            v19 = v18 - 79;
            if ( v19 )
            {
              if ( v19 == 16298 )
                return (unsigned int)WcSynchronizeExpansionPreopWithReason(CallbackData, 11, (__int64)a3);
              return v5;
            }
            goto LABEL_77;
          }
        }
        else
        {
          v8 = LowPart - 639616;
          if ( v8 && v8 != 52 )
            return v5;
        }
LABEL_10:
        if ( !BYTE6(qword_14000E6A2) )
        {
          v5 = WcFsctlBlockOperation(CallbackData, a2);
          if ( v5 == 4 )
            return v5;
        }
        return (unsigned int)WcFailFsctlIfPlaceHolderStream(v4, v3);
      }
    }
    if ( LowPart == 590740 )
      return (unsigned int)WcFsctlSetLayerRoot(CallbackData);
    if ( LowPart > 0x901FC )
    {
      if ( LowPart == 590736 )
      {
        return (unsigned int)WcPreFsctlQueryContainerState();
      }
      else if ( LowPart <= 0x90390 )
      {
        switch ( LowPart )
        {
          case 0x90230u:
          case 0x9024Cu:
          case 0x902ECu:
            goto LABEL_77;
          case 0x90234u:
          case 0x90277u:
          case 0x902F0u:
            goto LABEL_73;
          case 0x9027Cu:
          case 0x902B0u:
            goto LABEL_10;
          case 0x902D0u:
          case 0x902F4u:
LABEL_23:
            if ( !BYTE5(qword_14000E6A2) && (unsigned __int8)PsIsCurrentThreadInServerSilo() )
              goto LABEL_35;
            break;
          default:
            return v5;
        }
      }
      return v5;
    }
    if ( LowPart == 590332 )
    {
LABEL_73:
      v17 = BYTE4(qword_14000E6A2) == 0;
LABEL_34:
      if ( !v17 )
        return v5;
LABEL_35:
      a2 = v3;
      CallbackData = v4;
      return (unsigned int)WcFsctlBlockOperation(CallbackData, a2);
    }
    v24 = LowPart - 590256;
    if ( v24 )
    {
      if ( v24 != 4 || BYTE3(qword_14000E6A2) )
        return v5;
      return (unsigned int)WcFsctlBlockOperation(CallbackData, a2);
    }
LABEL_77:
    v17 = BYTE2(qword_14000E6A2) == 0;
    goto LABEL_34;
  }
  if ( LowPart == 590140 )
    goto LABEL_77;
  switch ( LowPart )
  {
    case 0x90018u:
      if ( !BYTE2(qword_14000E6A2) )
      {
        v5 = WcFsctlBlockOperation(CallbackData, a2);
        if ( v5 == 4 )
          return v5;
      }
      return (unsigned int)WcPreDismountLockRemove(v4, v3);
    case 0x9001Cu:
    case 0x90030u:
    case 0x900F0u:
      goto LABEL_77;
    case 0x90020u:
      if ( BYTE2(qword_14000E6A2) || (v5 = WcFsctlBlockOperation(CallbackData, a2), v5 != 4) )
      {
        v5 = WcPreDismountLockRemove(v4, v3);
        if ( v5 != 4 )
          return 0;
      }
      return v5;
    case 0x9006Fu:
    case 0x90073u:
    case 0x90074u:
      goto LABEL_73;
    case 0x9008Fu:
      return (unsigned int)WcPreFsctlFindFilesBySid(CallbackData, a2);
    case 0x90098u:
    case 0x9009Cu:
    case 0x900A0u:
    case 0x900BCu:
    case 0x900C0u:
      v17 = (_BYTE)qword_14000E6A2 == 0;
      goto LABEL_34;
    case 0x900A4u:
      goto LABEL_49;
    case 0x900A8u:
    case 0x900ACu:
      v13 = *(_QWORD *)(a2 + 24);
      LengthReturned = 0;
      Context = 0;
      if ( !(unsigned __int8)WcIsSiloFileObject(v13)
        && !(unsigned __int8)WcUnionExistsForFileObject(v4, *(_QWORD *)(v3 + 24), *(_QWORD *)(v3 + 32), v14) )
      {
        return v5;
      }
      ContextFileObject = WcGetContextFileObject(*(PFLT_INSTANCE *)(v3 + 24), *(PFILE_OBJECT *)(v3 + 32));
      v16 = LengthReturned;
      if ( ContextFileObject && (unsigned __int8)WcIsPlaceHolder(LengthReturned) )
      {
        v4->IoStatus.Status = -1073741195;
        v5 = 4;
      }
      if ( v16 )
        FltReleaseContext(v16);
      goto LABEL_16;
    case 0x900B3u:
    case 0x900BBu:
    case 0x900E7u:
    case 0x900EFu:
    case 0x900F8u:
    case 0x900FCu:
      goto LABEL_23;
    case 0x900C4u:
      return (unsigned int)WcSynchronizeExpansionPreopWithReason(CallbackData, 12, (__int64)a3);
    case 0x900D7u:
    case 0x900DBu:
    case 0x900DFu:
    case 0x900E3u:
      v17 = BYTE1(qword_14000E6A2) == 0;
      goto LABEL_34;
    case 0x900EBu:
    case 0x900F4u:
      v10 = *(struct _FILE_OBJECT **)(a2 + 32);
      v11 = *(struct _FLT_INSTANCE **)(v3 + 24);
      LODWORD(LengthReturned) = 0;
      Context = 0;
      StreamContext = FltGetStreamContext(v11, v10, &Context);
      if ( StreamContext >= 0
        && (unsigned __int8)WcShouldRedirectEaAndUsn(
                              (unsigned __int8)v4->RequestorMode,
                              *(_QWORD *)(v3 + 32),
                              *((_QWORD *)Context + 4),
                              Context) )
      {
        Source = WcGetSource(Context);
        Iopb = v4->Iopb;
        v22 = Iopb->Parameters.Read.ByteOffset.LowPart;
        if ( v22 == 590068 )
        {
          v23 = FltFsControlFile(
                  *(PFLT_INSTANCE *)Source,
                  *(PFILE_OBJECT *)(Source + 16),
                  0x900F4u,
                  Iopb->Parameters.CreatePipe.Parameters,
                  Iopb->Parameters.Create.Options,
                  Iopb->Parameters.CreatePipe.Parameters,
                  Iopb->Parameters.Read.Length,
                  (PULONG)&LengthReturned);
        }
        else
        {
          if ( v22 != 590059 )
          {
LABEL_67:
            v5 = 4;
            v4->IoStatus.Information = (unsigned int)LengthReturned;
            v4->IoStatus.Status = StreamContext;
            goto LABEL_16;
          }
          v23 = FltFsControlFile(
                  *(PFLT_INSTANCE *)Source,
                  *(PFILE_OBJECT *)(Source + 16),
                  0x900EBu,
                  Iopb->Parameters.CreatePipe.Parameters,
                  Iopb->Parameters.Create.Options,
                  Iopb->Parameters.Create.EaBuffer,
                  Iopb->Parameters.Read.Length,
                  (PULONG)&LengthReturned);
        }
        StreamContext = v23;
        goto LABEL_67;
      }
      if ( !BYTE5(qword_14000E6A2) && (unsigned __int8)PsIsCurrentThreadInServerSilo() )
        v5 = WcFsctlBlockOperation(v4, v3);
LABEL_16:
      if ( Context )
        FltReleaseContext(Context);
      break;
    default:
      return v5;
  }
  return v5;
}

```

## disassembly

```asm
0x140023150  mov     [rsp+arg_8], rbx
0x140023155  push    rbp
0x140023156  push    rsi
0x140023157  push    rdi
0x140023158  sub     rsp, 40h
0x14002315c  xor     ebp, ebp
0x14002315e  mov     rsi, rdx
0x140023161  mov     [r8], rbp
0x140023164  mov     rdi, rcx
0x140023167  mov     rax, [rcx+10h]
0x14002316b  mov     ebx, 1
0x140023170  mov     eax, [rax+28h]
0x140023173  cmp     eax, 9013Ch
0x140023178  ja      short loc_14002319C
0x14002317a  jz      loc_140023630; jumptable 000000014002320D cases 589852,589872,590064
0x140023180  add     eax, 0FFF6FFE8h; switch 229 cases
0x140023185  cmp     eax, 0E4h
0x14002318a  jbe     short loc_1400231F4
0x14002318c  mov     eax, ebx; jumptable 000000014002320D default case, cases 589849-589851,589853-589855,589857-589871,589873-589934,589936-589938,589941-589966,589968-589975,589977-589979,589981-589983,589985-589987,589989-589991,589993-589995,589997-590002,590004-590010,590013-590015,590017-590019,590021-590038,590040-590042,590044-590046,590048-590050,590052-590054,590056-590058,590060-590062,590065-590067,590069-590071,590073-590075
0x14002318e  mov     rbx, [rsp+58h+arg_8]
0x140023193  add     rsp, 40h
0x140023197  pop     rdi
0x140023198  pop     rsi
0x140023199  pop     rbp
0x14002319a  retn
0x14002319c  cmp     eax, 90394h
0x1400231a1  jbe     loc_14002326B
0x1400231a7  cmp     eax, 90C23h
0x1400231ac  jbe     loc_140023427
0x1400231b2  cmp     eax, 98344h
0x1400231b7  jbe     loc_1400233A7
0x1400231bd  sub     eax, 9C280h
0x1400231c2  jz      short loc_1400231C9; jumptable 00000001400232B6 cases 590460,590512
0x1400231c4  cmp     eax, 34h ; '4'
0x1400231c7  jnz     short def_14002320D; jumptable 000000014002320D default case, cases 589849-589851,589853-589855,589857-589871,589873-589934,589936-589938,589941-589966,589968-589975,589977-589979,589981-589983,589985-589987,589989-589991,589993-589995,589997-590002,590004-590010,590013-590015,590017-590019,590021-590038,590040-590042,590044-590046,590048-590050,590052-590054,590056-590058,590060-590062,590065-590067,590069-590071,590073-590075
0x1400231c9  cmp     byte ptr cs:qword_14000E6A2+6, bpl; jumptable 00000001400232B6 cases 590460,590512
0x1400231d0  jnz     short loc_1400231E4
0x1400231d2  mov     rdx, rsi
0x1400231d5  mov     rcx, rdi
0x1400231d8  call    WcFsctlBlockOperation
0x1400231dd  mov     ebx, eax
0x1400231df  cmp     eax, 4
0x1400231e2  jz      short def_14002320D; jumptable 000000014002320D default case, cases 589849-589851,589853-589855,589857-589871,589873-589934,589936-589938,589941-589966,589968-589975,589977-589979,589981-589983,589985-589987,589989-589991,589993-589995,589997-590002,590004-590010,590013-590015,590017-590019,590021-590038,590040-590042,590044-590046,590048-590050,590052-590054,590056-590058,590060-590062,590065-590067,590069-590071,590073-590075
0x1400231e4  mov     rdx, rsi
0x1400231e7  mov     rcx, rdi
0x1400231ea  call    WcFailFsctlIfPlaceHolderStream
0x1400231ef  jmp     loc_140023394
0x1400231f4  lea     rdx, cs:140000000h
0x1400231fb  movzx   eax, ds:(byte_14000B156 - 140000000h)[rdx+rax]
0x140023203  mov     ecx, ds:(jpt_14002320D - 140000000h)[rdx+rax*4]
0x14002320a  add     rcx, rdx
0x14002320d  jmp     rcx; switch jump
0x140023213  mov     rdx, [rsi+20h]; jumptable 000000014002320D cases 590059,590068
0x140023217  lea     r8, [rsp+58h+Context]; Context
0x14002321c  mov     rcx, [rsi+18h]; Instance
0x140023220  mov     dword ptr [rsp+58h+arg_0], ebp
0x140023224  mov     [rsp+58h+Context], rbp
0x140023229  call    cs:__imp_FltGetStreamContext
0x140023230  nop     dword ptr [rax+rax+00h]
0x140023235  mov     ebp, eax
0x140023237  test    eax, eax
0x140023239  jns     loc_140023516
0x14002323f  cmp     byte ptr cs:qword_14000E6A2+5, 0
0x140023246  jz      loc_140023356
0x14002324c  mov     rcx, [rsp+58h+Context]; Context
0x140023251  test    rcx, rcx
0x140023254  jz      def_14002320D; jumptable 000000014002320D default case, cases 589849-589851,589853-589855,589857-589871,589873-589934,589936-589938,589941-589966,589968-589975,589977-589979,589981-589983,589985-589987,589989-589991,589993-589995,589997-590002,590004-590010,590013-590015,590017-590019,590021-590038,590040-590042,590044-590046,590048-590050,590052-590054,590056-590058,590060-590062,590065-590067,590069-590071,590073-590075
0x14002325a  call    cs:__imp_FltReleaseContext
0x140023261  nop     dword ptr [rax+rax+00h]
0x140023266  jmp     def_14002320D; jumptable 000000014002320D default case, cases 589849-589851,589853-589855,589857-589871,589873-589934,589936-589938,589941-589966,589968-589975,589977-589979,589981-589983,589985-589987,589989-589991,589993-589995,589997-590002,590004-590010,590013-590015,590017-590019,590021-590038,590040-590042,590044-590046,590048-590050,590052-590054,590056-590058,590060-590062,590065-590067,590069-590071,590073-590075
0x14002326b  jz      loc_14002346E
0x140023271  cmp     eax, 901FCh
0x140023276  jbe     loc_1400235D6
0x14002327c  cmp     eax, 90390h
0x140023281  jz      loc_14002339B
0x140023287  ja      def_14002320D; jumptable 000000014002320D default case, cases 589849-589851,589853-589855,589857-589871,589873-589934,589936-589938,589941-589966,589968-589975,589977-589979,589981-589983,589985-589987,589989-589991,589993-589995,589997-590002,590004-590010,590013-590015,590017-590019,590021-590038,590040-590042,590044-590046,590048-590050,590052-590054,590056-590058,590060-590062,590065-590067,590069-590071,590073-590075
0x14002328d  add     eax, 0FFF6FDD0h; switch 197 cases
0x140023292  cmp     eax, 0C4h
0x140023297  ja      def_14002320D; jumptable 000000014002320D default case, cases 589849-589851,589853-589855,589857-589871,589873-589934,589936-589938,589941-589966,589968-589975,589977-589979,589981-589983,589985-589987,589989-589991,589993-589995,589997-590002,590004-590010,590013-590015,590017-590019,590021-590038,590040-590042,590044-590046,590048-590050,590052-590054,590056-590058,590060-590062,590065-590067,590069-590071,590073-590075
0x14002329d  lea     rdx, cs:140000000h
0x1400232a4  movzx   eax, ds:(byte_14000B24F - 140000000h)[rdx+rax]
0x1400232ac  mov     ecx, ds:(jpt_1400232B6 - 140000000h)[rdx+rax*4]
0x1400232b3  add     rcx, rdx
0x1400232b6  jmp     rcx; switch jump
0x1400232bc  cmp     byte ptr cs:qword_14000E6A2+5, bpl; jumptable 000000014002320D cases 590003,590011,590055,590063,590072,590076
0x1400232c3  jnz     def_14002320D; jumptable 000000014002320D default case, cases 589849-589851,589853-589855,589857-589871,589873-589934,589936-589938,589941-589966,589968-589975,589977-589979,589981-589983,589985-589987,589989-589991,589993-589995,589997-590002,590004-590010,590013-590015,590017-590019,590021-590038,590040-590042,590044-590046,590048-590050,590052-590054,590056-590058,590060-590062,590065-590067,590069-590071,590073-590075
0x1400232c9  call    cs:__imp_PsIsCurrentThreadInServerSilo
0x1400232d0  nop     dword ptr [rax+rax+00h]
0x1400232d5  test    al, al
0x1400232d7  jz      def_14002320D; jumptable 000000014002320D default case, cases 589849-589851,589853-589855,589857-589871,589873-589934,589936-589938,589941-589966,589968-589975,589977-589979,589981-589983,589985-589987,589989-589991,589993-589995,589997-590002,590004-590010,590013-590015,590017-590019,590021-590038,590040-590042,590044-590046,590048-590050,590052-590054,590056-590058,590060-590062,590065-590067,590069-590071,590073-590075
0x1400232dd  jmp     loc_140023389
0x1400232e2  mov     rdx, [rsi+20h]; jumptable 000000014002320D cases 589992,589996
0x1400232e6  mov     rcx, [rsi+18h]
0x1400232ea  mov     [rsp+58h+arg_0], rbp
0x1400232ef  mov     [rsp+58h+Context], rbp
0x1400232f4  call    WcIsSiloFileObject
0x1400232f9  test    al, al
0x1400232fb  jnz     short loc_140023315
0x1400232fd  mov     r8, [rsi+20h]
0x140023301  mov     rcx, rdi
0x140023304  mov     rdx, [rsi+18h]
0x140023308  call    WcUnionExistsForFileObject
0x14002330d  test    al, al
0x14002330f  jz      def_14002320D; jumptable 000000014002320D default case, cases 589849-589851,589853-589855,589857-589871,589873-589934,589936-589938,589941-589966,589968-589975,589977-589979,589981-589983,589985-589987,589989-589991,589993-589995,589997-590002,590004-590010,590013-590015,590017-590019,590021-590038,590040-590042,590044-590046,590048-590050,590052-590054,590056-590058,590060-590062,590065-590067,590069-590071,590073-590075
0x140023315  mov     rdx, [rsi+20h]; FileObject
0x140023319  lea     r9, [rsp+58h+Context]
0x14002331e  mov     rcx, [rsi+18h]; Instance
0x140023322  lea     r8, [rsp+58h+arg_0]
0x140023327  call    WcGetContextFileObject
0x14002332c  mov     rsi, [rsp+58h+arg_0]
0x140023331  test    al, al
0x140023333  jnz     loc_1400234E5
0x140023339  test    rsi, rsi
0x14002333c  jz      loc_14002324C
0x140023342  mov     rcx, rsi; Context
0x140023345  call    cs:__imp_FltReleaseContext
0x14002334c  nop     dword ptr [rax+rax+00h]
0x140023351  jmp     loc_14002324C
0x140023356  call    cs:__imp_PsIsCurrentThreadInServerSilo
0x14002335d  nop     dword ptr [rax+rax+00h]
0x140023362  test    al, al
0x140023364  jz      loc_14002324C
0x14002336a  mov     rdx, rsi
0x14002336d  mov     rcx, rdi
0x140023370  call    WcFsctlBlockOperation
0x140023375  mov     ebx, eax
0x140023377  jmp     loc_14002324C
0x14002337c  cmp     byte ptr cs:qword_14000E6A2, bpl; jumptable 000000014002320D cases 589976,589980,589984,590012,590016
0x140023383  jnz     def_14002320D; jumptable 000000014002320D default case, cases 589849-589851,589853-589855,589857-589871,589873-589934,589936-589938,589941-589966,589968-589975,589977-589979,589981-589983,589985-589987,589989-589991,589993-589995,589997-590002,590004-590010,590013-590015,590017-590019,590021-590038,590040-590042,590044-590046,590048-590050,590052-590054,590056-590058,590060-590062,590065-590067,590069-590071,590073-590075
0x140023389  mov     rdx, rsi
0x14002338c  mov     rcx, rdi
0x14002338f  call    WcFsctlBlockOperation
0x140023394  mov     ebx, eax
0x140023396  jmp     def_14002320D; jumptable 000000014002320D default case, cases 589849-589851,589853-589855,589857-589871,589873-589934,589936-589938,589941-589966,589968-589975,589977-589979,589981-589983,589985-589987,589989-589991,589993-589995,589997-590002,590004-590010,590013-590015,590017-590019,590021-590038,590040-590042,590044-590046,590048-590050,590052-590054,590056-590058,590060-590062,590065-590067,590069-590071,590073-590075
0x14002339b  call    WcPreFsctlQueryContainerState
0x1400233a0  mov     ebx, eax
0x1400233a2  jmp     def_14002320D; jumptable 000000014002320D default case, cases 589849-589851,589853-589855,589857-589871,589873-589934,589936-589938,589941-589966,589968-589975,589977-589979,589981-589983,589985-589987,589989-589991,589993-589995,589997-590002,590004-590010,590013-590015,590017-590019,590021-590038,590040-590042,590044-590046,590048-590050,590052-590054,590056-590058,590060-590062,590065-590067,590069-590071,590073-590075
0x1400233a7  jz      loc_1400231C9; jumptable 00000001400232B6 cases 590460,590512
0x1400233ad  sub     eax, 940CFh
0x1400233b2  jnz     short loc_1400233F1
0x1400233b4  call    WcPreFsctlQueryAllocatedRanges
0x1400233b9  mov     ebx, eax
0x1400233bb  jmp     def_14002320D; jumptable 000000014002320D default case, cases 589849-589851,589853-589855,589857-589871,589873-589934,589936-589938,589941-589966,589968-589975,589977-589979,589981-589983,589985-589987,589989-589991,589993-589995,589997-590002,590004-590010,590013-590015,590017-590019,590021-590038,590040-590042,590044-590046,590048-590050,590052-590054,590056-590058,590060-590062,590065-590067,590069-590071,590073-590075
0x1400233c0  mov     [rsp+58h+OutputBuffer], r8; jumptable 000000014002320D case 590020
0x1400233c5  mov     r9d, 3
0x1400233cb  mov     r8d, ebx
0x1400233ce  mov     [rsp+58h+InputBufferLength], 0Ch; int
0x1400233d6  mov     rdx, rsi
0x1400233d9  mov     rcx, rdi; CallbackData
0x1400233dc  call    WcSynchronizeExpansionPreopWithReason
0x1400233e1  mov     ebx, eax
0x1400233e3  jmp     def_14002320D; jumptable 000000014002320D default case, cases 589849-589851,589853-589855,589857-589871,589873-589934,589936-589938,589941-589966,589968-589975,589977-589979,589981-589983,589985-589987,589989-589991,589993-589995,589997-590002,590004-590010,590013-590015,590017-590019,590021-590038,590040-590042,590044-590046,590048-590050,590052-590054,590056-590058,590060-590062,590065-590067,590069-590071,590073-590075
0x1400233e8  cmp     byte ptr cs:qword_14000E6A2+1, bpl; jumptable 000000014002320D cases 590039,590043,590047,590051
0x1400233ef  jmp     short loc_140023383
0x1400233f1  sub     eax, 4Fh ; 'O'
0x1400233f4  jz      loc_140023630; jumptable 000000014002320D cases 589852,589872,590064
0x1400233fa  cmp     eax, 3FAAh
0x1400233ff  jnz     def_14002320D; jumptable 000000014002320D default case, cases 589849-589851,589853-589855,589857-589871,589873-589934,589936-589938,589941-589966,589968-589975,589977-589979,589981-589983,589985-589987,589989-589991,589993-589995,589997-590002,590004-590010,590013-590015,590017-590019,590021-590038,590040-590042,590044-590046,590048-590050,590052-590054,590056-590058,590060-590062,590065-590067,590069-590071,590073-590075
0x140023405  mov     [rsp+58h+OutputBuffer], r8; __int64
0x14002340a  mov     r9d, 3
0x140023410  mov     r8d, ebx
0x140023413  mov     [rsp+58h+InputBufferLength], 0Bh; int
0x14002341b  call    WcSynchronizeExpansionPreopWithReason
0x140023420  mov     ebx, eax
0x140023422  jmp     def_14002320D; jumptable 000000014002320D default case, cases 589849-589851,589853-589855,589857-589871,589873-589934,589936-589938,589941-589966,589968-589975,589977-589979,589981-589983,589985-589987,589989-589991,589993-589995,589997-590002,590004-590010,590013-590015,590017-590019,590021-590038,590040-590042,590044-590046,590048-590050,590052-590054,590056-590058,590060-590062,590065-590067,590069-590071,590073-590075
0x140023427  jz      loc_140023626
0x14002342d  add     eax, 0FFF6FC65h; switch 174 cases
0x140023432  cmp     eax, 0ADh
0x140023437  ja      def_14002320D; jumptable 000000014002320D default case, cases 589849-589851,589853-589855,589857-589871,589873-589934,589936-589938,589941-589966,589968-589975,589977-589979,589981-589983,589985-589987,589989-589991,589993-589995,589997-590002,590004-590010,590013-590015,590017-590019,590021-590038,590040-590042,590044-590046,590048-590050,590052-590054,590056-590058,590060-590062,590065-590067,590069-590071,590073-590075
0x14002343d  lea     rdx, cs:140000000h
0x140023444  movzx   eax, ds:(byte_14000B32C - 140000000h)[rdx+rax]
0x14002344c  mov     ecx, ds:(jpt_140023456 - 140000000h)[rdx+rax*4]
0x140023453  add     rcx, rdx
0x140023456  jmp     rcx; switch jump
0x14002345c  mov     rdx, rsi; jumptable 000000014002320D case 589988
0x14002345f  mov     rcx, rdi; CallbackData
0x140023462  call    WcPreFsctlSetReparsePoint
0x140023467  mov     ebx, eax
0x140023469  jmp     def_14002320D; jumptable 000000014002320D default case, cases 589849-589851,589853-589855,589857-589871,589873-589934,589936-589938,589941-589966,589968-589975,589977-589979,589981-589983,589985-589987,589989-589991,589993-589995,589997-590002,590004-590010,590013-590015,590017-590019,590021-590038,590040-590042,590044-590046,590048-590050,590052-590054,590056-590058,590060-590062,590065-590067,590069-590071,590073-590075
0x14002346e  call    WcFsctlSetLayerRoot
0x140023473  mov     ebx, eax
0x140023475  jmp     def_14002320D; jumptable 000000014002320D default case, cases 589849-589851,589853-589855,589857-589871,589873-589934,589936-589938,589941-589966,589968-589975,589977-589979,589981-589983,589985-589987,589989-589991,589993-589995,589997-590002,590004-590010,590013-590015,590017-590019,590021-590038,590040-590042,590044-590046,590048-590050,590052-590054,590056-590058,590060-590062,590065-590067,590069-590071,590073-590075
0x14002347a  cmp     byte ptr cs:qword_14000E6A2+2, bpl; jumptable 000000014002320D case 589848
0x140023481  jnz     short loc_140023499
0x140023483  mov     rdx, rsi
0x140023486  mov     rcx, rdi
0x140023489  call    WcFsctlBlockOperation
0x14002348e  mov     ebx, eax
0x140023490  cmp     eax, 4
0x140023493  jz      def_14002320D; jumptable 000000014002320D default case, cases 589849-589851,589853-589855,589857-589871,589873-589934,589936-589938,589941-589966,589968-589975,589977-589979,589981-589983,589985-589987,589989-589991,589993-589995,589997-590002,590004-590010,590013-590015,590017-590019,590021-590038,590040-590042,590044-590046,590048-590050,590052-590054,590056-590058,590060-590062,590065-590067,590069-590071,590073-590075
0x140023499  mov     rdx, rsi
0x14002349c  mov     rcx, rdi
0x14002349f  call    WcPreDismountLockRemove
0x1400234a4  jmp     loc_140023394
0x1400234a9  cmp     byte ptr cs:qword_14000E6A2+2, bpl; jumptable 000000014002320D case 589856
0x1400234b0  jnz     short loc_1400234C8
0x1400234b2  mov     rdx, rsi
0x1400234b5  mov     rcx, rdi
0x1400234b8  call    WcFsctlBlockOperation
0x1400234bd  mov     ebx, eax
0x1400234bf  cmp     eax, 4
0x1400234c2  jz      def_14002320D; jumptable 000000014002320D default case, cases 589849-589851,589853-589855,589857-589871,589873-589934,589936-589938,589941-589966,589968-589975,589977-589979,589981-589983,589985-589987,589989-589991,589993-589995,589997-590002,590004-590010,590013-590015,590017-590019,590021-590038,590040-590042,590044-590046,590048-590050,590052-590054,590056-590058,590060-590062,590065-590067,590069-590071,590073-590075
0x1400234c8  mov     rdx, rsi
0x1400234cb  mov     rcx, rdi
0x1400234ce  call    WcPreDismountLockRemove
0x1400234d3  mov     ebx, eax
0x1400234d5  cmp     eax, 4
0x1400234d8  jz      def_14002320D; jumptable 000000014002320D default case, cases 589849-589851,589853-589855,589857-589871,589873-589934,589936-589938,589941-589966,589968-589975,589977-589979,589981-589983,589985-589987,589989-589991,589993-589995,589997-590002,590004-590010,590013-590015,590017-590019,590021-590038,590040-590042,590044-590046,590048-590050,590052-590054,590056-590058,590060-590062,590065-590067,590069-590071,590073-590075
0x1400234de  mov     ebx, ebp
0x1400234e0  jmp     def_14002320D; jumptable 000000014002320D default case, cases 589849-589851,589853-589855,589857-589871,589873-589934,589936-589938,589941-589966,589968-589975,589977-589979,589981-589983,589985-589987,589989-589991,589993-589995,589997-590002,590004-590010,590013-590015,590017-590019,590021-590038,590040-590042,590044-590046,590048-590050,590052-590054,590056-590058,590060-590062,590065-590067,590069-590071,590073-590075
0x1400234e5  mov     rcx, rsi
0x1400234e8  call    WcIsPlaceHolder
0x1400234ed  test    al, al
0x1400234ef  jz      loc_140023339
0x1400234f5  mov     dword ptr [rdi+18h], 0C0000275h
0x1400234fc  mov     ebx, 4
0x140023501  jmp     loc_140023339
0x140023506  mov     rdx, rsi; jumptable 000000014002320D case 589967
0x140023509  mov     rcx, rdi
0x14002350c  call    WcPreFsctlFindFilesBySid
0x140023511  jmp     loc_140023394
0x140023516  mov     r8, [rsp+58h+Context]
0x14002351b  mov     rdx, [rsi+20h]
0x14002351f  mov     r9, r8
0x140023522  movzx   ecx, byte ptr [rdi+50h]
0x140023526  mov     r8, [r8+20h]
0x14002352a  call    WcShouldRedirectEaAndUsn
0x14002352f  test    al, al
0x140023531  jz      loc_14002323F
0x140023537  mov     rcx, [rsp+58h+Context]
0x14002353c  call    WcGetSource
0x140023541  mov     rdx, [rdi+10h]
0x140023545  mov     r10, rax
0x140023548  mov     ecx, [rdx+28h]
0x14002354b  cmp     ecx, 900F4h
0x140023551  jnz     short loc_14002357C
0x140023553  mov     ecx, [rdx+18h]
0x140023556  lea     rax, [rsp+58h+arg_0]
0x14002355b  mov     r9, [rdx+30h]
0x14002355f  mov     r8d, 900F4h
0x140023565  mov     [rsp+58h+LengthReturned], rax
0x14002356a  mov     [rsp+58h+OutputBufferLength], ecx
0x14002356e  mov     ecx, [rdx+20h]
0x140023571  mov     [rsp+58h+OutputBuffer], r9
0x140023576  mov     [rsp+58h+InputBufferLength], ecx
0x14002357a  jmp     short loc_1400235AC
0x14002357c  cmp     ecx, 900EBh
0x140023582  jnz     short loc_1400235C1
0x140023584  mov     r9, [rdx+30h]; InputBuffer
0x140023588  lea     rax, [rsp+58h+arg_0]
0x14002358d  mov     [rsp+58h+LengthReturned], rax; LengthReturned
0x140023592  mov     r8d, ecx; FsControlCode
0x140023595  mov     eax, [rdx+18h]
0x140023598  mov     [rsp+58h+OutputBufferLength], eax; OutputBufferLength
0x14002359c  mov     rax, [rdx+38h]
0x1400235a0  mov     [rsp+58h+OutputBuffer], rax; OutputBuffer
0x1400235a5  mov     eax, [rdx+20h]
0x1400235a8  mov     [rsp+58h+InputBufferLength], eax; InputBufferLength
0x1400235ac  mov     rdx, [r10+10h]; FileObject
0x1400235b0  mov     rcx, [r10]; Instance
0x1400235b3  call    cs:__imp_FltFsControlFile
0x1400235ba  nop     dword ptr [rax+rax+00h]
0x1400235bf  mov     ebp, eax
0x1400235c1  mov     eax, dword ptr [rsp+58h+arg_0]
0x1400235c5  mov     ebx, 4
0x1400235ca  mov     [rdi+20h], rax
0x1400235ce  mov     [rdi+18h], ebp
0x1400235d1  jmp     loc_14002324C
0x1400235d6  jz      short loc_1400235FA; jumptable 000000014002320D cases 589935,589939,589940
0x1400235d8  sub     eax, 901B0h
0x1400235dd  jz      short loc_140023630; jumptable 000000014002320D cases 589852,589872,590064
0x1400235df  cmp     eax, 4
0x1400235e2  jnz     def_14002320D; jumptable 000000014002320D default case, cases 589849-589851,589853-589855,589857-589871,589873-589934,589936-589938,589941-589966,589968-589975,589977-589979,589981-589983,589985-589987,589989-589991,589993-589995,589997-590002,590004-590010,590013-590015,590017-590019,590021-590038,590040-590042,590044-590046,590048-590050,590052-590054,590056-590058,590060-590062,590065-590067,590069-590071,590073-590075
0x1400235e8  cmp     byte ptr cs:qword_14000E6A2+3, bpl
0x1400235ef  jnz     def_14002320D; jumptable 000000014002320D default case, cases 589849-589851,589853-589855,589857-589871,589873-589934,589936-589938,589941-589966,589968-589975,589977-589979,589981-589983,589985-589987,589989-589991,589993-589995,589997-590002,590004-590010,590013-590015,590017-590019,590021-590038,590040-590042,590044-590046,590048-590050,590052-590054,590056-590058,590060-590062,590065-590067,590069-590071,590073-590075
0x1400235f5  jmp     loc_14002338F
0x1400235fa  cmp     byte ptr cs:qword_14000E6A2+4, bpl; jumptable 000000014002320D cases 589935,589939,589940
0x140023601  jmp     loc_140023383
0x140023606  mov     rdx, rsi; jumptable 0000000140023456 cases 590747,590756
0x140023609  mov     rcx, rdi; Data
0x14002360c  call    WcFsctlRedirectDirectMappedRequest
0x140023611  jmp     loc_140023394
0x140023616  mov     rdx, rsi; jumptable 0000000140023456 case 590920
0x140023619  mov     rcx, rdi
0x14002361c  call    WcFsctlManageBypassIo
0x140023621  jmp     loc_140023394
0x140023626  call    WcPreGetUnions
0x14002362b  jmp     loc_140023394
0x140023630  cmp     byte ptr cs:qword_14000E6A2+2, bpl; jumptable 000000014002320D cases 589852,589872,590064
0x140023637  jmp     loc_140023383
```
