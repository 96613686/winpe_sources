# MpPreFsControl

- ea: `0x140044520`
- end: `0x1400448ee`
- name: `MpPreFsControl`
- size: `974`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `authz_impersonation, installer_update`

## callees

- `0x1400049dc`
- `0x1400051bc`
- `0x1400118d0`
- `0x140044520`
- `0x1400448f0`
- `0x140044e6c`
- `0x140045670`
- `0x140078280`
- `0x14007888c`
- `0x140078f04`
- `0x14007d45c`
- `0x140081fe0`
- `0x140082084`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessId` at `0x1400445ad`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14004486c`
- `ntoskrnl!PsGetCurrentProcessId` at `0x1400445ad`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14004486c`
- `FLTMGR!FltReleaseContext` at `0x140044622`
- `FLTMGR!FltReleaseContext` at `0x140044622`
- `FLTMGR!FltGetStreamContext` at `0x1400445f6`
- `FLTMGR!FltGetStreamContext` at `0x1400445f6`

## pseudocode

```c
__int64 __fastcall MpPreFsControl(PFLT_CALLBACK_DATA CallbackData, __int64 a2, PFLT_CONTEXT *a3)
{
  PFLT_IO_PARAMETER_BLOCK Iopb; // rdx
  UCHAR MinorFunction; // al
  __int64 result; // rax
  unsigned int LowPart; // eax
  HANDLE v10; // rbx
  unsigned int v11; // eax
  NTSTATUS StreamContext; // eax
  PFLT_CONTEXT v13; // rcx
  unsigned int v14; // eax
  unsigned int v15; // eax
  _DWORD *Parameters; // rax
  unsigned int v17; // eax
  NTSTATUS v18; // eax
  int MappedPurgeExclusionLock; // eax
  __int64 v20; // rdx
  HANDLE v21; // rbx
  __int64 v22; // [rsp+30h] [rbp-38h] BYREF
  PFLT_CONTEXT Context; // [rsp+38h] [rbp-30h] BYREF
  void *v24; // [rsp+40h] [rbp-28h] BYREF

  Context = 0;
  v22 = 0;
  v24 = 0;
  if ( !*(_QWORD *)(a2 + 32) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_1bce4dab9b883aab79efa6fb296bde6e_Traceguids);
    return 1;
  }
  *a3 = 0;
  Iopb = CallbackData->Iopb;
  MinorFunction = Iopb->MinorFunction;
  if ( MinorFunction && MinorFunction != 4 )
    return 1;
  LowPart = Iopb->Parameters.Read.ByteOffset.LowPart;
  if ( LowPart == 590571 )
  {
    v10 = *(HANDLE *)(MpData + 240);
    if ( PsGetCurrentProcessId() != v10 )
    {
      v21 = *(HANDLE *)(MpData + 264);
      if ( PsGetCurrentProcessId() != v21 && *(int *)(MpData + 868) >= 0 && !*(_BYTE *)(MpData + 208) )
        return 1;
    }
    CallbackData->IoStatus.Status = MpFsCtlDispatcher(CallbackData);
    return 4;
  }
  if ( LowPart <= 0x903FC )
  {
    if ( LowPart == 590844 )
    {
      return MpMarkStreamDataChanged(CallbackData, a2, 1);
    }
    else
    {
      switch ( LowPart )
      {
        case 0x900D7u:
        case 0x900DBu:
          return MpPreSetEncryption(CallbackData, a2);
        case 0x900DFu:
          return MpMarkStreamDataChanged(CallbackData, a2, 3);
        case 0x900E3u:
          return MpPreReadRawEncrypted(CallbackData, a2);
        case 0x900E7u:
          goto LABEL_27;
        case 0x900F8u:
          Parameters = Iopb->Parameters.CreatePipe.Parameters;
          if ( !Parameters || (Parameters[2] & 1) == 0 )
            return 1;
LABEL_27:
          result = 5;
          break;
        default:
          return 1;
      }
    }
  }
  else
  {
    v11 = LowPart - 622792;
    if ( v11 )
    {
      v14 = v11 - 176;
      if ( v14 )
      {
        v15 = v14 - 144;
        if ( v15 )
        {
          v17 = v15 - 96;
          if ( v17 )
          {
            if ( v17 != 220 )
              return 1;
            return MpPreDuplicateExtentsToFile(CallbackData, a2);
          }
          else
          {
            return MpMarkStreamDataChanged(CallbackData, a2, 7);
          }
        }
        else
        {
          return MpPreFileLevelTrim(CallbackData, a2);
        }
      }
      else
      {
        v18 = MpTxfPreSavepointNotification(CallbackData, &v24);
        if ( v18 < 0 )
        {
          CallbackData->IoStatus.Status = v18;
          CallbackData->IoStatus.Information = 0;
          *a3 = 0;
          return 4;
        }
        if ( !v24 )
          return 1;
        *a3 = v24;
        return 0;
      }
    }
    else
    {
      StreamContext = FltGetStreamContext(*(PFLT_INSTANCE *)(a2 + 24), *(PFILE_OBJECT *)(a2 + 32), &Context);
      if ( StreamContext < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        {
          _mm_lfence();
          WPP_SF_qD(
            WPP_GLOBAL_Control->AttachedDevice,
            11,
            WPP_1bce4dab9b883aab79efa6fb296bde6e_Traceguids,
            CallbackData->Thread,
            StreamContext);
        }
        return 1;
      }
      v13 = Context;
      if ( (*(_DWORD *)(*((_QWORD *)Context + 1) + 80LL) & 4) != 0 )
        goto LABEL_13;
      MappedPurgeExclusionLock = MpGetMappedPurgeExclusionLock(Context, &v22, (unsigned int)StreamContext);
      if ( MappedPurgeExclusionLock < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        {
          _mm_lfence();
          WPP_SF_qD(
            WPP_GLOBAL_Control->AttachedDevice,
            12,
            WPP_1bce4dab9b883aab79efa6fb296bde6e_Traceguids,
            CallbackData->Thread,
            MappedPurgeExclusionLock);
        }
        v13 = Context;
LABEL_13:
        FltReleaseContext(v13);
        return 1;
      }
      MpRWLAcquireShared(v22, v20, (unsigned int)MappedPurgeExclusionLock);
      *a3 = Context;
      return 5;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140044520  mov     [rsp+arg_18], rbx
0x140044525  push    rbp
0x140044526  push    rsi
0x140044527  push    rdi
0x140044528  sub     rsp, 50h
0x14004452c  mov     rax, cs:__security_cookie
0x140044533  xor     rax, rsp
0x140044536  mov     [rsp+68h+var_20], rax
0x14004453b  xor     ebp, ebp
0x14004453d  mov     rbx, r8
0x140044540  mov     rsi, rdx
0x140044543  mov     rdi, rcx
0x140044546  mov     [rsp+68h+Context], rbp
0x14004454b  mov     [rsp+68h+var_38], rbp
0x140044550  mov     [rsp+68h+var_28], rbp
0x140044555  cmp     [rdx+20h], rbp
0x140044559  jz      loc_140044656
0x14004455f  mov     [r8], rbp
0x140044562  mov     rdx, [rcx+10h]
0x140044566  movzx   eax, byte ptr [rdx+5]
0x14004456a  test    al, al
0x14004456c  jz      short loc_140044595
0x14004456e  cmp     al, 4
0x140044570  jz      short loc_140044595
0x140044572  mov     eax, 1; jumptable 0000000140044711 default case, cases 590040-590042,590044-590046,590048-590050,590052-590054,590056-590071
0x140044577  mov     rcx, [rsp+68h+var_20]
0x14004457c  xor     rcx, rsp; StackCookie
0x14004457f  call    __security_check_cookie
0x140044584  mov     rbx, [rsp+68h+arg_18]
0x14004458c  add     rsp, 50h
0x140044590  pop     rdi
0x140044591  pop     rsi
0x140044592  pop     rbp
0x140044593  retn
0x140044595  mov     eax, [rdx+28h]
0x140044598  cmp     eax, 902EBh
0x14004459d  jnz     short loc_1400445D7
0x14004459f  mov     rax, cs:MpData
0x1400445a6  mov     rbx, [rax+0F0h]
0x1400445ad  call    cs:__imp_PsGetCurrentProcessId
0x1400445b4  nop     dword ptr [rax+rax+00h]
0x1400445b9  cmp     rax, rbx
0x1400445bc  jnz     loc_14004485E
0x1400445c2  mov     rdx, rsi
0x1400445c5  mov     rcx, rdi; CallbackData
0x1400445c8  call    MpFsCtlDispatcher
0x1400445cd  mov     [rdi+18h], eax
0x1400445d0  mov     eax, 4
0x1400445d5  jmp     short loc_140044577
0x1400445d7  cmp     eax, 903FCh
0x1400445dc  jbe     loc_1400446E2
0x1400445e2  sub     eax, 980C8h
0x1400445e7  jnz     short loc_140044633
0x1400445e9  mov     rdx, [rsi+20h]; FileObject
0x1400445ed  lea     r8, [rsp+68h+Context]; Context
0x1400445f2  mov     rcx, [rsi+18h]; Instance
0x1400445f6  call    cs:__imp_FltGetStreamContext
0x1400445fd  nop     dword ptr [rax+rax+00h]
0x140044602  mov     r8d, eax
0x140044605  test    eax, eax
0x140044607  js      loc_140044692
0x14004460d  mov     rcx, [rsp+68h+Context]; Context
0x140044612  mov     rax, [rcx+8]
0x140044616  mov     edx, [rax+50h]
0x140044619  test    dl, 4
0x14004461c  jz      loc_1400447E4
0x140044622  call    cs:__imp_FltReleaseContext
0x140044629  nop     dword ptr [rax+rax+00h]
0x14004462e  jmp     def_140044711; jumptable 0000000140044711 default case, cases 590040-590042,590044-590046,590048-590050,590052-590054,590056-590071
0x140044633  sub     eax, 0B0h
0x140044638  jz      loc_1400447AF
0x14004463e  sub     eax, 90h
0x140044643  jnz     loc_14004477F
0x140044649  mov     rdx, rsi
0x14004464c  call    MpPreFileLevelTrim
0x140044651  jmp     loc_140044577
0x140044656  mov     rcx, cs:WPP_GLOBAL_Control
0x14004465d  lea     rax, WPP_GLOBAL_Control
0x140044664  cmp     rcx, rax
0x140044667  jz      def_140044711; jumptable 0000000140044711 default case, cases 590040-590042,590044-590046,590048-590050,590052-590054,590056-590071
0x14004466d  mov     eax, [rcx+2Ch]
0x140044670  test    al, 1
0x140044672  jz      def_140044711; jumptable 0000000140044711 default case, cases 590040-590042,590044-590046,590048-590050,590052-590054,590056-590071
0x140044678  mov     rcx, [rcx+18h]
0x14004467c  lea     r8, WPP_1bce4dab9b883aab79efa6fb296bde6e_Traceguids
0x140044683  mov     edx, 0Ah
0x140044688  call    WPP_SF_
0x14004468d  jmp     def_140044711; jumptable 0000000140044711 default case, cases 590040-590042,590044-590046,590048-590050,590052-590054,590056-590071
0x140044692  mov     rcx, cs:WPP_GLOBAL_Control
0x140044699  lea     rax, WPP_GLOBAL_Control
0x1400446a0  cmp     rcx, rax
0x1400446a3  jz      def_140044711; jumptable 0000000140044711 default case, cases 590040-590042,590044-590046,590048-590050,590052-590054,590056-590071
0x1400446a9  mov     ecx, [rcx+2Ch]
0x1400446ac  test    cl, 1
0x1400446af  jz      def_140044711; jumptable 0000000140044711 default case, cases 590040-590042,590044-590046,590048-590050,590052-590054,590056-590071
0x1400446b5  lfence
0x1400446b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400446bf  mov     edx, 0Bh
0x1400446c4  mov     r9, [rdi+8]
0x1400446c8  mov     [rsp+68h+var_48], r8d
0x1400446cd  lea     r8, WPP_1bce4dab9b883aab79efa6fb296bde6e_Traceguids
0x1400446d4  mov     rcx, [rcx+18h]
0x1400446d8  call    WPP_SF_qD
0x1400446dd  jmp     def_140044711; jumptable 0000000140044711 default case, cases 590040-590042,590044-590046,590048-590050,590052-590054,590056-590071
0x1400446e2  jz      loc_14004476C
0x1400446e8  add     eax, 0FFF6FF29h; switch 34 cases
0x1400446ed  cmp     eax, 21h
0x1400446f0  ja      def_140044711; jumptable 0000000140044711 default case, cases 590040-590042,590044-590046,590048-590050,590052-590054,590056-590071
0x1400446f6  lea     r8, cs:140000000h
0x1400446fd  movzx   eax, ds:(byte_1400448CC - 140000000h)[r8+rax]
0x140044706  mov     ecx, ds:(jpt_140044711 - 140000000h)[r8+rax*4]
0x14004470e  add     rcx, r8
0x140044711  jmp     rcx; switch jump
0x140044717  mov     rax, [rdx+30h]; jumptable 0000000140044711 case 590072
0x14004471b  test    rax, rax
0x14004471e  jz      def_140044711; jumptable 0000000140044711 default case, cases 590040-590042,590044-590046,590048-590050,590052-590054,590056-590071
0x140044724  mov     eax, [rax+8]
0x140044727  test    al, 1
0x140044729  jz      def_140044711; jumptable 0000000140044711 default case, cases 590040-590042,590044-590046,590048-590050,590052-590054,590056-590071
0x14004472f  mov     eax, 5; jumptable 0000000140044711 case 590055
0x140044734  jmp     loc_140044577
0x140044739  mov     r8d, 3; jumptable 0000000140044711 case 590047
0x14004473f  mov     rdx, rsi
0x140044742  call    MpMarkStreamDataChanged
0x140044747  jmp     loc_140044577
0x14004474c  mov     rdx, rsi; jumptable 0000000140044711 case 590051
0x14004474f  mov     rcx, rdi
0x140044752  call    MpPreReadRawEncrypted
0x140044757  jmp     loc_140044577
0x14004475c  mov     rdx, rsi; jumptable 0000000140044711 cases 590039,590043
0x14004475f  mov     rcx, rdi; CallbackData
0x140044762  call    MpPreSetEncryption
0x140044767  jmp     loc_140044577
0x14004476c  mov     r8d, 1
0x140044772  mov     rdx, rsi
0x140044775  call    MpMarkStreamDataChanged
0x14004477a  jmp     loc_140044577
0x14004477f  sub     eax, 60h ; '`'
0x140044782  jz      short loc_14004479C
0x140044784  cmp     eax, 0DCh
0x140044789  jnz     def_140044711; jumptable 0000000140044711 default case, cases 590040-590042,590044-590046,590048-590050,590052-590054,590056-590071
0x14004478f  mov     rdx, rsi
0x140044792  call    MpPreDuplicateExtentsToFile
0x140044797  jmp     loc_140044577
0x14004479c  mov     r8d, 7
0x1400447a2  mov     rdx, rsi
0x1400447a5  call    MpMarkStreamDataChanged
0x1400447aa  jmp     loc_140044577
0x1400447af  lea     rdx, [rsp+68h+var_28]
0x1400447b4  call    MpTxfPreSavepointNotification
0x1400447b9  test    eax, eax
0x1400447bb  js      short loc_1400447D5
0x1400447bd  mov     rax, [rsp+68h+var_28]
0x1400447c2  test    rax, rax
0x1400447c5  jz      def_140044711; jumptable 0000000140044711 default case, cases 590040-590042,590044-590046,590048-590050,590052-590054,590056-590071
0x1400447cb  mov     [rbx], rax
0x1400447ce  xor     eax, eax
0x1400447d0  jmp     loc_140044577
0x1400447d5  mov     [rdi+18h], eax
0x1400447d8  mov     [rdi+20h], rbp
0x1400447dc  mov     [rbx], rbp
0x1400447df  jmp     loc_1400445D0
0x1400447e4  lea     rdx, [rsp+68h+var_38]
0x1400447e9  call    MpGetMappedPurgeExclusionLock
0x1400447ee  mov     r8d, eax
0x1400447f1  test    eax, eax
0x1400447f3  jns     short loc_140044842
0x1400447f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400447fc  lea     rax, WPP_GLOBAL_Control
0x140044803  cmp     rcx, rax
0x140044806  jz      short loc_140044838
0x140044808  mov     ecx, [rcx+2Ch]
0x14004480b  test    cl, 1
0x14004480e  jz      short loc_140044838
0x140044810  lfence
0x140044813  mov     rcx, cs:WPP_GLOBAL_Control
0x14004481a  mov     edx, 0Ch
0x14004481f  mov     r9, [rdi+8]
0x140044823  mov     [rsp+68h+var_48], r8d
0x140044828  lea     r8, WPP_1bce4dab9b883aab79efa6fb296bde6e_Traceguids
0x14004482f  mov     rcx, [rcx+18h]
0x140044833  call    WPP_SF_qD
0x140044838  mov     rcx, [rsp+68h+Context]
0x14004483d  jmp     loc_140044622
0x140044842  mov     rcx, [rsp+68h+var_38]
0x140044847  call    MpRWLAcquireShared
0x14004484c  mov     rax, [rsp+68h+Context]
0x140044851  mov     [rbx], rax
0x140044854  mov     eax, 5
0x140044859  jmp     loc_140044577
0x14004485e  mov     rax, cs:MpData
0x140044865  mov     rbx, [rax+108h]
0x14004486c  call    cs:__imp_PsGetCurrentProcessId
0x140044873  nop     dword ptr [rax+rax+00h]
0x140044878  cmp     rax, rbx
0x14004487b  jz      loc_1400445C2
0x140044881  mov     rax, cs:MpData
0x140044888  mov     ecx, [rax+364h]
0x14004488e  test    ecx, ecx
0x140044890  js      loc_1400445C2
0x140044896  mov     rax, cs:MpData
0x14004489d  movzx   ecx, byte ptr [rax+0D0h]
0x1400448a4  test    cl, cl
0x1400448a6  jz      def_140044711; jumptable 0000000140044711 default case, cases 590040-590042,590044-590046,590048-590050,590052-590054,590056-590071
0x1400448ac  jmp     loc_1400445C2
```
