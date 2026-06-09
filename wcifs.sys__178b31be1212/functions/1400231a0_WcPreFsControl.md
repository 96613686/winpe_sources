# WcPreFsControl

- ea: `0x1400231a0`
- end: `0x14002368c`
- name: `WcPreFsControl`
- size: `1260`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData, __int64, _QWORD *)`
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
- `0x1400231a0`
- `0x140023694`
- `0x1400237f8`
- `0x140023890`
- `0x140023aa4`
- `0x140023c90`
- `0x140023ee8`
- `0x14002fa48`

## import_xrefs

- `ntoskrnl!PsIsCurrentThreadInServerSilo` at `0x140023319`
- `ntoskrnl!PsIsCurrentThreadInServerSilo` at `0x1400233a6`
- `ntoskrnl!PsIsCurrentThreadInServerSilo` at `0x140023319`
- `ntoskrnl!PsIsCurrentThreadInServerSilo` at `0x1400233a6`
- `FLTMGR!FltFsControlFile` at `0x140023603`
- `FLTMGR!FltFsControlFile` at `0x140023603`
- `FLTMGR!FltGetStreamContext` at `0x140023279`
- `FLTMGR!FltGetStreamContext` at `0x140023279`
- `FLTMGR!FltReleaseContext` at `0x1400232aa`
- `FLTMGR!FltReleaseContext` at `0x140023395`
- `FLTMGR!FltReleaseContext` at `0x1400232aa`
- `FLTMGR!FltReleaseContext` at `0x140023395`

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
  __int64 v13; // rdx
  __int64 v14; // rcx
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
      v13 = *(_QWORD *)(a2 + 32);
      v14 = *(_QWORD *)(v3 + 24);
      LengthReturned = 0;
      Context = 0;
      if ( !(unsigned __int8)WcIsSiloFileObject(v14, v13)
        && !(unsigned __int8)WcUnionExistsForFileObject(v4, *(_QWORD *)(v3 + 24), *(_QWORD *)(v3 + 32)) )
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
0x1400231a0  mov     [rsp+arg_8], rbx
0x1400231a5  push    rbp
0x1400231a6  push    rsi
0x1400231a7  push    rdi
0x1400231a8  sub     rsp, 40h
0x1400231ac  xor     ebp, ebp
0x1400231ae  mov     rsi, rdx
0x1400231b1  mov     [r8], rbp
0x1400231b4  mov     rdi, rcx
0x1400231b7  mov     rax, [rcx+10h]
0x1400231bb  mov     ebx, 1
0x1400231c0  mov     eax, [rax+28h]
0x1400231c3  cmp     eax, 9013Ch
0x1400231c8  ja      short loc_1400231EC
0x1400231ca  jz      loc_140023680; jumptable 000000014002325D cases 589852,589872,590064
0x1400231d0  add     eax, 0FFF6FFE8h; switch 229 cases
0x1400231d5  cmp     eax, 0E4h
0x1400231da  jbe     short loc_140023244
0x1400231dc  mov     eax, ebx; jumptable 000000014002325D default case, cases 589849-589851,589853-589855,589857-589871,589873-589934,589936-589938,589941-589966,589968-589975,589977-589979,589981-589983,589985-589987,589989-589991,589993-589995,589997-590002,590004-590010,590013-590015,590017-590019,590021-590038,590040-590042,590044-590046,590048-590050,590052-590054,590056-590058,590060-590062,590065-590067,590069-590071,590073-590075
0x1400231de  mov     rbx, [rsp+58h+arg_8]
0x1400231e3  add     rsp, 40h
0x1400231e7  pop     rdi
0x1400231e8  pop     rsi
0x1400231e9  pop     rbp
0x1400231ea  retn
0x1400231ec  cmp     eax, 90394h
0x1400231f1  jbe     loc_1400232BB
0x1400231f7  cmp     eax, 90C23h
0x1400231fc  jbe     loc_140023477
0x140023202  cmp     eax, 98344h
0x140023207  jbe     loc_1400233F7
0x14002320d  sub     eax, 9C280h
0x140023212  jz      short loc_140023219; jumptable 0000000140023306 cases 590460,590512
0x140023214  cmp     eax, 34h ; '4'
0x140023217  jnz     short def_14002325D; jumptable 000000014002325D default case, cases 589849-589851,589853-589855,589857-589871,589873-589934,589936-589938,589941-589966,589968-589975,589977-589979,589981-589983,589985-589987,589989-589991,589993-589995,589997-590002,590004-590010,590013-590015,590017-590019,590021-590038,590040-590042,590044-590046,590048-590050,590052-590054,590056-590058,590060-590062,590065-590067,590069-590071,590073-590075
0x140023219  cmp     byte ptr cs:qword_14000E6A2+6, bpl; jumptable 0000000140023306 cases 590460,590512
0x140023220  jnz     short loc_140023234
0x140023222  mov     rdx, rsi
0x140023225  mov     rcx, rdi
0x140023228  call    WcFsctlBlockOperation
0x14002322d  mov     ebx, eax
0x14002322f  cmp     eax, 4
0x140023232  jz      short def_14002325D; jumptable 000000014002325D default case, cases 589849-589851,589853-589855,589857-589871,589873-589934,589936-589938,589941-589966,589968-589975,589977-589979,589981-589983,589985-589987,589989-589991,589993-589995,589997-590002,590004-590010,590013-590015,590017-590019,590021-590038,590040-590042,590044-590046,590048-590050,590052-590054,590056-590058,590060-590062,590065-590067,590069-590071,590073-590075
0x140023234  mov     rdx, rsi
0x140023237  mov     rcx, rdi
0x14002323a  call    WcFailFsctlIfPlaceHolderStream
0x14002323f  jmp     loc_1400233E4
0x140023244  lea     rdx, cs:140000000h
0x14002324b  movzx   eax, ds:(byte_14000B156 - 140000000h)[rdx+rax]
0x140023253  mov     ecx, ds:(jpt_14002325D - 140000000h)[rdx+rax*4]
0x14002325a  add     rcx, rdx
0x14002325d  jmp     rcx; switch jump
0x140023263  mov     rdx, [rsi+20h]; jumptable 000000014002325D cases 590059,590068
0x140023267  lea     r8, [rsp+58h+Context]; Context
0x14002326c  mov     rcx, [rsi+18h]; Instance
0x140023270  mov     dword ptr [rsp+58h+arg_0], ebp
0x140023274  mov     [rsp+58h+Context], rbp
0x140023279  call    cs:__imp_FltGetStreamContext
0x140023280  nop     dword ptr [rax+rax+00h]
0x140023285  mov     ebp, eax
0x140023287  test    eax, eax
0x140023289  jns     loc_140023566
0x14002328f  cmp     byte ptr cs:qword_14000E6A2+5, 0
0x140023296  jz      loc_1400233A6
0x14002329c  mov     rcx, [rsp+58h+Context]; Context
0x1400232a1  test    rcx, rcx
0x1400232a4  jz      def_14002325D; jumptable 000000014002325D default case, cases 589849-589851,589853-589855,589857-589871,589873-589934,589936-589938,589941-589966,589968-589975,589977-589979,589981-589983,589985-589987,589989-589991,589993-589995,589997-590002,590004-590010,590013-590015,590017-590019,590021-590038,590040-590042,590044-590046,590048-590050,590052-590054,590056-590058,590060-590062,590065-590067,590069-590071,590073-590075
0x1400232aa  call    cs:__imp_FltReleaseContext
0x1400232b1  nop     dword ptr [rax+rax+00h]
0x1400232b6  jmp     def_14002325D; jumptable 000000014002325D default case, cases 589849-589851,589853-589855,589857-589871,589873-589934,589936-589938,589941-589966,589968-589975,589977-589979,589981-589983,589985-589987,589989-589991,589993-589995,589997-590002,590004-590010,590013-590015,590017-590019,590021-590038,590040-590042,590044-590046,590048-590050,590052-590054,590056-590058,590060-590062,590065-590067,590069-590071,590073-590075
0x1400232bb  jz      loc_1400234BE
0x1400232c1  cmp     eax, 901FCh
0x1400232c6  jbe     loc_140023626
0x1400232cc  cmp     eax, 90390h
0x1400232d1  jz      loc_1400233EB
0x1400232d7  ja      def_14002325D; jumptable 000000014002325D default case, cases 589849-589851,589853-589855,589857-589871,589873-589934,589936-589938,589941-589966,589968-589975,589977-589979,589981-589983,589985-589987,589989-589991,589993-589995,589997-590002,590004-590010,590013-590015,590017-590019,590021-590038,590040-590042,590044-590046,590048-590050,590052-590054,590056-590058,590060-590062,590065-590067,590069-590071,590073-590075
0x1400232dd  add     eax, 0FFF6FDD0h; switch 197 cases
0x1400232e2  cmp     eax, 0C4h
0x1400232e7  ja      def_14002325D; jumptable 000000014002325D default case, cases 589849-589851,589853-589855,589857-589871,589873-589934,589936-589938,589941-589966,589968-589975,589977-589979,589981-589983,589985-589987,589989-589991,589993-589995,589997-590002,590004-590010,590013-590015,590017-590019,590021-590038,590040-590042,590044-590046,590048-590050,590052-590054,590056-590058,590060-590062,590065-590067,590069-590071,590073-590075
0x1400232ed  lea     rdx, cs:140000000h
0x1400232f4  movzx   eax, ds:(byte_14000B24F - 140000000h)[rdx+rax]
0x1400232fc  mov     ecx, ds:(jpt_140023306 - 140000000h)[rdx+rax*4]
0x140023303  add     rcx, rdx
0x140023306  jmp     rcx; switch jump
0x14002330c  cmp     byte ptr cs:qword_14000E6A2+5, bpl; jumptable 000000014002325D cases 590003,590011,590055,590063,590072,590076
0x140023313  jnz     def_14002325D; jumptable 000000014002325D default case, cases 589849-589851,589853-589855,589857-589871,589873-589934,589936-589938,589941-589966,589968-589975,589977-589979,589981-589983,589985-589987,589989-589991,589993-589995,589997-590002,590004-590010,590013-590015,590017-590019,590021-590038,590040-590042,590044-590046,590048-590050,590052-590054,590056-590058,590060-590062,590065-590067,590069-590071,590073-590075
0x140023319  call    cs:__imp_PsIsCurrentThreadInServerSilo
0x140023320  nop     dword ptr [rax+rax+00h]
0x140023325  test    al, al
0x140023327  jz      def_14002325D; jumptable 000000014002325D default case, cases 589849-589851,589853-589855,589857-589871,589873-589934,589936-589938,589941-589966,589968-589975,589977-589979,589981-589983,589985-589987,589989-589991,589993-589995,589997-590002,590004-590010,590013-590015,590017-590019,590021-590038,590040-590042,590044-590046,590048-590050,590052-590054,590056-590058,590060-590062,590065-590067,590069-590071,590073-590075
0x14002332d  jmp     loc_1400233D9
0x140023332  mov     rdx, [rsi+20h]; jumptable 000000014002325D cases 589992,589996
0x140023336  mov     rcx, [rsi+18h]
0x14002333a  mov     [rsp+58h+arg_0], rbp
0x14002333f  mov     [rsp+58h+Context], rbp
0x140023344  call    WcIsSiloFileObject
0x140023349  test    al, al
0x14002334b  jnz     short loc_140023365
0x14002334d  mov     r8, [rsi+20h]
0x140023351  mov     rcx, rdi
0x140023354  mov     rdx, [rsi+18h]
0x140023358  call    WcUnionExistsForFileObject
0x14002335d  test    al, al
0x14002335f  jz      def_14002325D; jumptable 000000014002325D default case, cases 589849-589851,589853-589855,589857-589871,589873-589934,589936-589938,589941-589966,589968-589975,589977-589979,589981-589983,589985-589987,589989-589991,589993-589995,589997-590002,590004-590010,590013-590015,590017-590019,590021-590038,590040-590042,590044-590046,590048-590050,590052-590054,590056-590058,590060-590062,590065-590067,590069-590071,590073-590075
0x140023365  mov     rdx, [rsi+20h]; FileObject
0x140023369  lea     r9, [rsp+58h+Context]
0x14002336e  mov     rcx, [rsi+18h]; Instance
0x140023372  lea     r8, [rsp+58h+arg_0]
0x140023377  call    WcGetContextFileObject
0x14002337c  mov     rsi, [rsp+58h+arg_0]
0x140023381  test    al, al
0x140023383  jnz     loc_140023535
0x140023389  test    rsi, rsi
0x14002338c  jz      loc_14002329C
0x140023392  mov     rcx, rsi; Context
0x140023395  call    cs:__imp_FltReleaseContext
0x14002339c  nop     dword ptr [rax+rax+00h]
0x1400233a1  jmp     loc_14002329C
0x1400233a6  call    cs:__imp_PsIsCurrentThreadInServerSilo
0x1400233ad  nop     dword ptr [rax+rax+00h]
0x1400233b2  test    al, al
0x1400233b4  jz      loc_14002329C
0x1400233ba  mov     rdx, rsi
0x1400233bd  mov     rcx, rdi
0x1400233c0  call    WcFsctlBlockOperation
0x1400233c5  mov     ebx, eax
0x1400233c7  jmp     loc_14002329C
0x1400233cc  cmp     byte ptr cs:qword_14000E6A2, bpl; jumptable 000000014002325D cases 589976,589980,589984,590012,590016
0x1400233d3  jnz     def_14002325D; jumptable 000000014002325D default case, cases 589849-589851,589853-589855,589857-589871,589873-589934,589936-589938,589941-589966,589968-589975,589977-589979,589981-589983,589985-589987,589989-589991,589993-589995,589997-590002,590004-590010,590013-590015,590017-590019,590021-590038,590040-590042,590044-590046,590048-590050,590052-590054,590056-590058,590060-590062,590065-590067,590069-590071,590073-590075
0x1400233d9  mov     rdx, rsi
0x1400233dc  mov     rcx, rdi
0x1400233df  call    WcFsctlBlockOperation
0x1400233e4  mov     ebx, eax
0x1400233e6  jmp     def_14002325D; jumptable 000000014002325D default case, cases 589849-589851,589853-589855,589857-589871,589873-589934,589936-589938,589941-589966,589968-589975,589977-589979,589981-589983,589985-589987,589989-589991,589993-589995,589997-590002,590004-590010,590013-590015,590017-590019,590021-590038,590040-590042,590044-590046,590048-590050,590052-590054,590056-590058,590060-590062,590065-590067,590069-590071,590073-590075
0x1400233eb  call    WcPreFsctlQueryContainerState
0x1400233f0  mov     ebx, eax
0x1400233f2  jmp     def_14002325D; jumptable 000000014002325D default case, cases 589849-589851,589853-589855,589857-589871,589873-589934,589936-589938,589941-589966,589968-589975,589977-589979,589981-589983,589985-589987,589989-589991,589993-589995,589997-590002,590004-590010,590013-590015,590017-590019,590021-590038,590040-590042,590044-590046,590048-590050,590052-590054,590056-590058,590060-590062,590065-590067,590069-590071,590073-590075
0x1400233f7  jz      loc_140023219; jumptable 0000000140023306 cases 590460,590512
0x1400233fd  sub     eax, 940CFh
0x140023402  jnz     short loc_140023441
0x140023404  call    WcPreFsctlQueryAllocatedRanges
0x140023409  mov     ebx, eax
0x14002340b  jmp     def_14002325D; jumptable 000000014002325D default case, cases 589849-589851,589853-589855,589857-589871,589873-589934,589936-589938,589941-589966,589968-589975,589977-589979,589981-589983,589985-589987,589989-589991,589993-589995,589997-590002,590004-590010,590013-590015,590017-590019,590021-590038,590040-590042,590044-590046,590048-590050,590052-590054,590056-590058,590060-590062,590065-590067,590069-590071,590073-590075
0x140023410  mov     [rsp+58h+OutputBuffer], r8; jumptable 000000014002325D case 590020
0x140023415  mov     r9d, 3
0x14002341b  mov     r8d, ebx
0x14002341e  mov     [rsp+58h+InputBufferLength], 0Ch; int
0x140023426  mov     rdx, rsi
0x140023429  mov     rcx, rdi; CallbackData
0x14002342c  call    WcSynchronizeExpansionPreopWithReason
0x140023431  mov     ebx, eax
0x140023433  jmp     def_14002325D; jumptable 000000014002325D default case, cases 589849-589851,589853-589855,589857-589871,589873-589934,589936-589938,589941-589966,589968-589975,589977-589979,589981-589983,589985-589987,589989-589991,589993-589995,589997-590002,590004-590010,590013-590015,590017-590019,590021-590038,590040-590042,590044-590046,590048-590050,590052-590054,590056-590058,590060-590062,590065-590067,590069-590071,590073-590075
0x140023438  cmp     byte ptr cs:qword_14000E6A2+1, bpl; jumptable 000000014002325D cases 590039,590043,590047,590051
0x14002343f  jmp     short loc_1400233D3
0x140023441  sub     eax, 4Fh ; 'O'
0x140023444  jz      loc_140023680; jumptable 000000014002325D cases 589852,589872,590064
0x14002344a  cmp     eax, 3FAAh
0x14002344f  jnz     def_14002325D; jumptable 000000014002325D default case, cases 589849-589851,589853-589855,589857-589871,589873-589934,589936-589938,589941-589966,589968-589975,589977-589979,589981-589983,589985-589987,589989-589991,589993-589995,589997-590002,590004-590010,590013-590015,590017-590019,590021-590038,590040-590042,590044-590046,590048-590050,590052-590054,590056-590058,590060-590062,590065-590067,590069-590071,590073-590075
0x140023455  mov     [rsp+58h+OutputBuffer], r8; __int64
0x14002345a  mov     r9d, 3
0x140023460  mov     r8d, ebx
0x140023463  mov     [rsp+58h+InputBufferLength], 0Bh; int
0x14002346b  call    WcSynchronizeExpansionPreopWithReason
0x140023470  mov     ebx, eax
0x140023472  jmp     def_14002325D; jumptable 000000014002325D default case, cases 589849-589851,589853-589855,589857-589871,589873-589934,589936-589938,589941-589966,589968-589975,589977-589979,589981-589983,589985-589987,589989-589991,589993-589995,589997-590002,590004-590010,590013-590015,590017-590019,590021-590038,590040-590042,590044-590046,590048-590050,590052-590054,590056-590058,590060-590062,590065-590067,590069-590071,590073-590075
0x140023477  jz      loc_140023676
0x14002347d  add     eax, 0FFF6FC65h; switch 174 cases
0x140023482  cmp     eax, 0ADh
0x140023487  ja      def_14002325D; jumptable 000000014002325D default case, cases 589849-589851,589853-589855,589857-589871,589873-589934,589936-589938,589941-589966,589968-589975,589977-589979,589981-589983,589985-589987,589989-589991,589993-589995,589997-590002,590004-590010,590013-590015,590017-590019,590021-590038,590040-590042,590044-590046,590048-590050,590052-590054,590056-590058,590060-590062,590065-590067,590069-590071,590073-590075
0x14002348d  lea     rdx, cs:140000000h
0x140023494  movzx   eax, ds:(byte_14000B32C - 140000000h)[rdx+rax]
0x14002349c  mov     ecx, ds:(jpt_1400234A6 - 140000000h)[rdx+rax*4]
0x1400234a3  add     rcx, rdx
0x1400234a6  jmp     rcx; switch jump
0x1400234ac  mov     rdx, rsi; jumptable 000000014002325D case 589988
0x1400234af  mov     rcx, rdi; CallbackData
0x1400234b2  call    WcPreFsctlSetReparsePoint
0x1400234b7  mov     ebx, eax
0x1400234b9  jmp     def_14002325D; jumptable 000000014002325D default case, cases 589849-589851,589853-589855,589857-589871,589873-589934,589936-589938,589941-589966,589968-589975,589977-589979,589981-589983,589985-589987,589989-589991,589993-589995,589997-590002,590004-590010,590013-590015,590017-590019,590021-590038,590040-590042,590044-590046,590048-590050,590052-590054,590056-590058,590060-590062,590065-590067,590069-590071,590073-590075
0x1400234be  call    WcFsctlSetLayerRoot
0x1400234c3  mov     ebx, eax
0x1400234c5  jmp     def_14002325D; jumptable 000000014002325D default case, cases 589849-589851,589853-589855,589857-589871,589873-589934,589936-589938,589941-589966,589968-589975,589977-589979,589981-589983,589985-589987,589989-589991,589993-589995,589997-590002,590004-590010,590013-590015,590017-590019,590021-590038,590040-590042,590044-590046,590048-590050,590052-590054,590056-590058,590060-590062,590065-590067,590069-590071,590073-590075
0x1400234ca  cmp     byte ptr cs:qword_14000E6A2+2, bpl; jumptable 000000014002325D case 589848
0x1400234d1  jnz     short loc_1400234E9
0x1400234d3  mov     rdx, rsi
0x1400234d6  mov     rcx, rdi
0x1400234d9  call    WcFsctlBlockOperation
0x1400234de  mov     ebx, eax
0x1400234e0  cmp     eax, 4
0x1400234e3  jz      def_14002325D; jumptable 000000014002325D default case, cases 589849-589851,589853-589855,589857-589871,589873-589934,589936-589938,589941-589966,589968-589975,589977-589979,589981-589983,589985-589987,589989-589991,589993-589995,589997-590002,590004-590010,590013-590015,590017-590019,590021-590038,590040-590042,590044-590046,590048-590050,590052-590054,590056-590058,590060-590062,590065-590067,590069-590071,590073-590075
0x1400234e9  mov     rdx, rsi
0x1400234ec  mov     rcx, rdi
0x1400234ef  call    WcPreDismountLockRemove
0x1400234f4  jmp     loc_1400233E4
0x1400234f9  cmp     byte ptr cs:qword_14000E6A2+2, bpl; jumptable 000000014002325D case 589856
0x140023500  jnz     short loc_140023518
0x140023502  mov     rdx, rsi
0x140023505  mov     rcx, rdi
0x140023508  call    WcFsctlBlockOperation
0x14002350d  mov     ebx, eax
0x14002350f  cmp     eax, 4
0x140023512  jz      def_14002325D; jumptable 000000014002325D default case, cases 589849-589851,589853-589855,589857-589871,589873-589934,589936-589938,589941-589966,589968-589975,589977-589979,589981-589983,589985-589987,589989-589991,589993-589995,589997-590002,590004-590010,590013-590015,590017-590019,590021-590038,590040-590042,590044-590046,590048-590050,590052-590054,590056-590058,590060-590062,590065-590067,590069-590071,590073-590075
0x140023518  mov     rdx, rsi
0x14002351b  mov     rcx, rdi
0x14002351e  call    WcPreDismountLockRemove
0x140023523  mov     ebx, eax
0x140023525  cmp     eax, 4
0x140023528  jz      def_14002325D; jumptable 000000014002325D default case, cases 589849-589851,589853-589855,589857-589871,589873-589934,589936-589938,589941-589966,589968-589975,589977-589979,589981-589983,589985-589987,589989-589991,589993-589995,589997-590002,590004-590010,590013-590015,590017-590019,590021-590038,590040-590042,590044-590046,590048-590050,590052-590054,590056-590058,590060-590062,590065-590067,590069-590071,590073-590075
0x14002352e  mov     ebx, ebp
0x140023530  jmp     def_14002325D; jumptable 000000014002325D default case, cases 589849-589851,589853-589855,589857-589871,589873-589934,589936-589938,589941-589966,589968-589975,589977-589979,589981-589983,589985-589987,589989-589991,589993-589995,589997-590002,590004-590010,590013-590015,590017-590019,590021-590038,590040-590042,590044-590046,590048-590050,590052-590054,590056-590058,590060-590062,590065-590067,590069-590071,590073-590075
0x140023535  mov     rcx, rsi
0x140023538  call    WcIsPlaceHolder
0x14002353d  test    al, al
0x14002353f  jz      loc_140023389
0x140023545  mov     dword ptr [rdi+18h], 0C0000275h
0x14002354c  mov     ebx, 4
0x140023551  jmp     loc_140023389
0x140023556  mov     rdx, rsi; jumptable 000000014002325D case 589967
0x140023559  mov     rcx, rdi
0x14002355c  call    WcPreFsctlFindFilesBySid
0x140023561  jmp     loc_1400233E4
0x140023566  mov     r8, [rsp+58h+Context]
0x14002356b  mov     rdx, [rsi+20h]
0x14002356f  mov     r9, r8
0x140023572  movzx   ecx, byte ptr [rdi+50h]
0x140023576  mov     r8, [r8+20h]
0x14002357a  call    WcShouldRedirectEaAndUsn
0x14002357f  test    al, al
0x140023581  jz      loc_14002328F
0x140023587  mov     rcx, [rsp+58h+Context]
0x14002358c  call    WcGetSource
0x140023591  mov     rdx, [rdi+10h]
0x140023595  mov     r10, rax
0x140023598  mov     ecx, [rdx+28h]
0x14002359b  cmp     ecx, 900F4h
0x1400235a1  jnz     short loc_1400235CC
0x1400235a3  mov     ecx, [rdx+18h]
0x1400235a6  lea     rax, [rsp+58h+arg_0]
0x1400235ab  mov     r9, [rdx+30h]
0x1400235af  mov     r8d, 900F4h
0x1400235b5  mov     [rsp+58h+LengthReturned], rax
0x1400235ba  mov     [rsp+58h+OutputBufferLength], ecx
0x1400235be  mov     ecx, [rdx+20h]
0x1400235c1  mov     [rsp+58h+OutputBuffer], r9
0x1400235c6  mov     [rsp+58h+InputBufferLength], ecx
0x1400235ca  jmp     short loc_1400235FC
0x1400235cc  cmp     ecx, 900EBh
0x1400235d2  jnz     short loc_140023611
0x1400235d4  mov     r9, [rdx+30h]; InputBuffer
0x1400235d8  lea     rax, [rsp+58h+arg_0]
0x1400235dd  mov     [rsp+58h+LengthReturned], rax; LengthReturned
0x1400235e2  mov     r8d, ecx; FsControlCode
0x1400235e5  mov     eax, [rdx+18h]
0x1400235e8  mov     [rsp+58h+OutputBufferLength], eax; OutputBufferLength
0x1400235ec  mov     rax, [rdx+38h]
0x1400235f0  mov     [rsp+58h+OutputBuffer], rax; OutputBuffer
0x1400235f5  mov     eax, [rdx+20h]
0x1400235f8  mov     [rsp+58h+InputBufferLength], eax; InputBufferLength
0x1400235fc  mov     rdx, [r10+10h]; FileObject
0x140023600  mov     rcx, [r10]; Instance
0x140023603  call    cs:__imp_FltFsControlFile
0x14002360a  nop     dword ptr [rax+rax+00h]
0x14002360f  mov     ebp, eax
0x140023611  mov     eax, dword ptr [rsp+58h+arg_0]
0x140023615  mov     ebx, 4
0x14002361a  mov     [rdi+20h], rax
0x14002361e  mov     [rdi+18h], ebp
0x140023621  jmp     loc_14002329C
0x140023626  jz      short loc_14002364A; jumptable 000000014002325D cases 589935,589939,589940
0x140023628  sub     eax, 901B0h
0x14002362d  jz      short loc_140023680; jumptable 000000014002325D cases 589852,589872,590064
0x14002362f  cmp     eax, 4
0x140023632  jnz     def_14002325D; jumptable 000000014002325D default case, cases 589849-589851,589853-589855,589857-589871,589873-589934,589936-589938,589941-589966,589968-589975,589977-589979,589981-589983,589985-589987,589989-589991,589993-589995,589997-590002,590004-590010,590013-590015,590017-590019,590021-590038,590040-590042,590044-590046,590048-590050,590052-590054,590056-590058,590060-590062,590065-590067,590069-590071,590073-590075
0x140023638  cmp     byte ptr cs:qword_14000E6A2+3, bpl
0x14002363f  jnz     def_14002325D; jumptable 000000014002325D default case, cases 589849-589851,589853-589855,589857-589871,589873-589934,589936-589938,589941-589966,589968-589975,589977-589979,589981-589983,589985-589987,589989-589991,589993-589995,589997-590002,590004-590010,590013-590015,590017-590019,590021-590038,590040-590042,590044-590046,590048-590050,590052-590054,590056-590058,590060-590062,590065-590067,590069-590071,590073-590075
0x140023645  jmp     loc_1400233DF
0x14002364a  cmp     byte ptr cs:qword_14000E6A2+4, bpl; jumptable 000000014002325D cases 589935,589939,589940
0x140023651  jmp     loc_1400233D3
0x140023656  mov     rdx, rsi; jumptable 00000001400234A6 cases 590747,590756
0x140023659  mov     rcx, rdi; Data
0x14002365c  call    WcFsctlRedirectDirectMappedRequest
0x140023661  jmp     loc_1400233E4
0x140023666  mov     rdx, rsi; jumptable 00000001400234A6 case 590920
0x140023669  mov     rcx, rdi
0x14002366c  call    WcFsctlManageBypassIo
0x140023671  jmp     loc_1400233E4
0x140023676  call    WcPreGetUnions
0x14002367b  jmp     loc_1400233E4
0x140023680  cmp     byte ptr cs:qword_14000E6A2+2, bpl; jumptable 000000014002325D cases 589852,589872,590064
0x140023687  jmp     loc_1400233D3
```
