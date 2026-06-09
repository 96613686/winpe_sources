# MpScanOnPreUserModeReadCopySourceFile

- ea: `0x14002d520`
- end: `0x14002da8e`
- name: `MpScanOnPreUserModeReadCopySourceFile`
- size: `1390`
- prototype: ``
- caller_count: `3`
- callee_count: `15`
- tags: `authz_impersonation`

## callers

- `0x140002080`
- `0x14002da90`
- `0x140082084`

## callees

- `0x140002450`
- `0x140003af0`
- `0x140003d20`
- `0x14000a760`
- `0x14000ae58`
- `0x14000b7dc`
- `0x140011890`
- `0x1400118d0`
- `0x14002d520`
- `0x140030060`
- `0x14003a1b0`
- `0x1400510e4`
- `0x140055eb0`
- `0x140068f54`
- `0x14007b128`

## import_xrefs

- `ntoskrnl!IoThreadToProcess` at `0x14002d665`
- `ntoskrnl!IoThreadToProcess` at `0x14002d691`
- `ntoskrnl!IoThreadToProcess` at `0x14002d665`
- `ntoskrnl!IoThreadToProcess` at `0x14002d691`
- `FLTMGR!FltReleaseContext` at `0x14002da6c`
- `FLTMGR!FltReleaseContext` at `0x14002da7d`
- `FLTMGR!FltReleaseContext` at `0x14002da6c`
- `FLTMGR!FltReleaseContext` at `0x14002da7d`
- `FLTMGR!FltGetStreamHandleContext` at `0x14002d6de`
- `FLTMGR!FltGetStreamHandleContext` at `0x14002d6de`
- `FLTMGR!FltGetStreamContext` at `0x14002d7e4`
- `FLTMGR!FltGetStreamContext` at `0x14002d7e4`
- `FLTMGR!FltSupportsStreamContexts` at `0x14002d6a6`
- `FLTMGR!FltSupportsStreamContexts` at `0x14002d6a6`
- `FLTMGR!FltSupportsStreamHandleContexts` at `0x14002d6be`
- `FLTMGR!FltSupportsStreamHandleContexts` at `0x14002d6be`

## string_xrefs

- `0x14002d9b1`: `blocked access`

## pseudocode

```c
__int64 __fastcall MpScanOnPreUserModeReadCopySourceFile(
        struct _FLT_CALLBACK_DATA *a1,
        __int64 a2,
        PFLT_CONTEXT *a3,
        PFLT_CONTEXT *a4,
        char a5)
{
  unsigned int v5; // edi
  __int64 v7; // r12
  unsigned __int8 (__fastcall *v11)(_QWORD); // rax
  struct _KPROCESS *v13; // rbx
  struct _KPROCESS *v14; // rbx
  PDEVICE_OBJECT v15; // rcx
  __int64 v16; // rdx
  volatile signed __int32 *v17; // rcx
  volatile signed __int32 v18; // eax
  bool v19; // zf
  int v20; // eax
  struct _KPROCESS *RequestorProcess; // rax
  int ProcessContextByObject; // r12d
  PETHREAD Thread; // rbx
  struct _DEVICE_OBJECT *AttachedDevice; // rdi
  int RequestorProcessId; // eax
  __int64 v26; // r9
  int v27; // eax
  int v28; // eax
  const char *v29; // rcx
  __int64 v30; // [rsp+68h] [rbp-11h] BYREF
  PFLT_CONTEXT Context; // [rsp+70h] [rbp-9h] BYREF
  PFLT_CONTEXT v32; // [rsp+78h] [rbp-1h] BYREF

  v5 = 2;
  v7 = 0;
  v32 = 0;
  Context = 0;
  v30 = 0;
  if ( a1 && *(_BYTE *)(MpData + 4040) && ((a1->Flags & 2) != 0 || a1->RequestorMode || (a5 & 1) != 0) )
  {
    v11 = *(unsigned __int8 (__fastcall **)(_QWORD))(MpData + 176);
    if ( v11 )
    {
      if ( v11(*(_QWORD *)(a2 + 32)) )
      {
        v13 = *(struct _KPROCESS **)(MpData + 232);
        if ( IoThreadToProcess(KeGetCurrentThread()) != v13 )
        {
          v14 = *(struct _KPROCESS **)(MpData + 256);
          if ( IoThreadToProcess(KeGetCurrentThread()) != v14 )
          {
            if ( FltSupportsStreamContexts(*(PFILE_OBJECT *)(a2 + 32))
              && FltSupportsStreamHandleContexts(*(PFILE_OBJECT *)(a2 + 32)) )
            {
              if ( FltGetStreamHandleContext(*(PFLT_INSTANCE *)(a2 + 24), *(PFILE_OBJECT *)(a2 + 32), &Context) >= 0 )
              {
                v17 = (volatile signed __int32 *)*((_QWORD *)Context + 12);
                if ( v17 )
                {
                  v18 = *v17;
                  if ( (*v17 & 1) != 0 )
                  {
                    if ( (v18 & 2) != 0 )
                    {
                      if ( (v18 & 8) != 0 )
                      {
                        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
                        {
                          WPP_SF_qZ(
                            WPP_GLOBAL_Control->AttachedDevice,
                            98,
                            (unsigned int)WPP_ddfeb2d17970385cb7e6e54739bfb2ed_Traceguids,
                            a1->Thread,
                            *(_QWORD *)(a2 + 32) + 88LL);
                        }
                        v5 = 1;
                        v19 = (*(_DWORD *)(MpData + 864) & 4) == 0;
                        a1->IoStatus.Information = 0;
                        v20 = -1073739514;
                        if ( v19 )
                          v20 = -1073741790;
                        a1->IoStatus.Status = v20;
                      }
                    }
                    else
                    {
                      _InterlockedOr(v17, 4u);
                      if ( !(unsigned __int8)IsThisCallBeingThrottled() )
                        MpSendOSCopyHintTelemetry(1);
                      if ( FltGetStreamContext(*(PFLT_INSTANCE *)(a2 + 24), *(PFILE_OBJECT *)(a2 + 32), &v32) >= 0 )
                      {
                        RequestorProcess = (struct _KPROCESS *)MpGetRequestorProcess(a1);
                        if ( RequestorProcess )
                        {
                          ProcessContextByObject = MpGetProcessContextByObject(RequestorProcess);
                          if ( ProcessContextByObject < 0
                            && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
                          {
                            _mm_lfence();
                            Thread = a1->Thread;
                            AttachedDevice = WPP_GLOBAL_Control->AttachedDevice;
                            RequestorProcessId = MpGetRequestorProcessId(a1);
                            WPP_SF_qDD(
                              AttachedDevice,
                              100,
                              WPP_ddfeb2d17970385cb7e6e54739bfb2ed_Traceguids,
                              Thread,
                              RequestorProcessId,
                              ProcessContextByObject);
                          }
                          v7 = v30;
                        }
                        _InterlockedOr(*((volatile signed __int32 **)Context + 12), 2u);
                        v26 = *((_QWORD *)Context + 12);
                        v27 = *((_DWORD *)Context + 11);
                        LODWORD(v30) = 0;
                        v28 = MpScanFile(
                                0,
                                a1,
                                a2,
                                5,
                                *(_DWORD *)(v26 + 4),
                                0,
                                v26 + 16,
                                v27,
                                v26 + 56,
                                v32,
                                v7,
                                Context);
                        v5 = HandleMpScanFileResult(
                               (unsigned int)&v30,
                               v28,
                               (_DWORD)a1,
                               *(_DWORD *)(*((_QWORD *)Context + 12) + 4LL),
                               v7,
                               0);
                        if ( v5 == 1 )
                        {
                          _InterlockedOr(*((volatile signed __int32 **)Context + 12), 8u);
                          MpSendOSCopyHintTelemetry(4);
                          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
                          {
                            switch ( (_DWORD)v30 )
                            {
                              case 1:
                                v29 = "bad";
                                break;
                              case 2:
                                v29 = "HIPS blocked for execution";
                                break;
                              case 3:
                                v29 = "blocked access";
                                break;
                              default:
                                v29 = "blocked for execution";
                                if ( (_DWORD)v30 != 4 )
                                  v29 = "unknown";
                                break;
                            }
                            WPP_SF_qsDZ(
                              WPP_GLOBAL_Control->AttachedDevice,
                              101,
                              (unsigned int)WPP_ddfeb2d17970385cb7e6e54739bfb2ed_Traceguids,
                              a1->Thread,
                              (__int64)v29,
                              *((_DWORD *)v32 + 42),
                              *(_QWORD *)(a2 + 32) + 88LL);
                          }
                        }
                      }
                      else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                             && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
                      {
                        WPP_SF_qZ(
                          WPP_GLOBAL_Control->AttachedDevice,
                          99,
                          (unsigned int)WPP_ddfeb2d17970385cb7e6e54739bfb2ed_Traceguids,
                          a1->Thread,
                          *(_QWORD *)(a2 + 32) + 88LL);
                      }
                    }
                  }
                }
              }
              else
              {
                v15 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
                {
                  v16 = 97;
LABEL_66:
                  WPP_SF_q(v15->AttachedDevice, v16, WPP_ddfeb2d17970385cb7e6e54739bfb2ed_Traceguids, a1->Thread);
                }
              }
            }
            else
            {
              v15 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
              {
                v16 = 96;
                goto LABEL_66;
              }
            }
          }
        }
      }
    }
  }
  if ( a3 && v32 )
  {
    *a3 = v32;
    v32 = 0;
  }
  if ( a4 && Context )
  {
    *a4 = Context;
    Context = 0;
  }
  if ( v32 )
    FltReleaseContext(v32);
  if ( Context )
    FltReleaseContext(Context);
  return v5;
}

```

## disassembly

```asm
0x14002d520  mov     r11, rsp
0x14002d523  push    rbp
0x14002d524  push    rdi
0x14002d525  lea     rbp, [r11-57h]
0x14002d529  sub     rsp, 0B8h
0x14002d530  mov     rax, cs:__security_cookie
0x14002d537  xor     rax, rsp
0x14002d53a  mov     [rbp+4Fh+var_48], rax
0x14002d53e  mov     [r11-20h], rsi
0x14002d542  mov     edi, 2
0x14002d547  mov     [r11-28h], r12
0x14002d54b  mov     rsi, rcx
0x14002d54e  mov     [r11-30h], r13
0x14002d552  xor     r12d, r12d
0x14002d555  mov     [r11-38h], r14
0x14002d559  mov     r14, r9
0x14002d55c  mov     [r11-40h], r15
0x14002d560  mov     r15, r8
0x14002d563  mov     [rbp+4Fh+var_50], 0
0x14002d56b  mov     r13, rdx
0x14002d56e  mov     [rbp+4Fh+Context], 0
0x14002d576  mov     [rbp+4Fh+var_60], r12
0x14002d57a  test    rcx, rcx
0x14002d57d  jz      short loc_14002D5BE
0x14002d57f  mov     rax, cs:MpData
0x14002d586  cmp     [rax+0FC8h], r12b
0x14002d58d  jz      short loc_14002D5BE
0x14002d58f  mov     ecx, [rcx]
0x14002d591  test    dil, cl
0x14002d594  jnz     short loc_14002D5A0
0x14002d596  cmp     [rsi+50h], r12b
0x14002d59a  jz      loc_14002D728
0x14002d5a0  mov     rax, [rax+0B0h]
0x14002d5a7  test    rax, rax
0x14002d5aa  jz      short loc_14002D5BE
0x14002d5ac  mov     rcx, [rdx+20h]
0x14002d5b0  call    cs:__guard_dispatch_icall_fptr
0x14002d5b6  test    al, al
0x14002d5b8  jnz     loc_14002D646
0x14002d5be  mov     r13, [rsp+0C0h+var_28]
0x14002d5c6  mov     r12, [rsp+0C0h+var_20]
0x14002d5ce  mov     rsi, [rsp+0C0h+var_18]
0x14002d5d6  test    r15, r15
0x14002d5d9  jz      short loc_14002D5E8
0x14002d5db  mov     rcx, [rbp+4Fh+var_50]
0x14002d5df  test    rcx, rcx
0x14002d5e2  jnz     loc_14002DA5C
0x14002d5e8  mov     r15, [rsp+0C0h+var_38]
0x14002d5f0  test    r14, r14
0x14002d5f3  jnz     short loc_14002D630
0x14002d5f5  mov     rcx, [rbp+4Fh+var_50]; Context
0x14002d5f9  mov     r14, [rsp+0C0h+var_30]
0x14002d601  test    rcx, rcx
0x14002d604  jnz     loc_14002DA6C
0x14002d60a  mov     rcx, [rbp+4Fh+Context]; Context
0x14002d60e  test    rcx, rcx
0x14002d611  jnz     loc_14002DA7D
0x14002d617  mov     eax, edi
0x14002d619  mov     rcx, [rbp+4Fh+var_48]
0x14002d61d  xor     rcx, rsp; StackCookie
0x14002d620  call    __security_check_cookie
0x14002d625  add     rsp, 0B8h
0x14002d62c  pop     rdi
0x14002d62d  pop     rbp
0x14002d62e  retn
0x14002d630  mov     rcx, [rbp+4Fh+Context]
0x14002d634  test    rcx, rcx
0x14002d637  jz      short loc_14002D5F5
0x14002d639  mov     [r14], rcx
0x14002d63c  mov     [rbp+4Fh+Context], 0
0x14002d644  jmp     short loc_14002D5F5
0x14002d646  mov     rcx, gs:188h; Thread
0x14002d64f  mov     rax, cs:MpData
0x14002d656  mov     [rsp+0B0h], rbx
0x14002d65e  mov     rbx, [rax+0E8h]
0x14002d665  call    cs:__imp_IoThreadToProcess
0x14002d66c  nop     dword ptr [rax+rax+00h]
0x14002d671  cmp     rax, rbx
0x14002d674  jz      loc_14002D71B
0x14002d67a  mov     rcx, gs:188h; Thread
0x14002d683  mov     rax, cs:MpData
0x14002d68a  mov     rbx, [rax+100h]
0x14002d691  call    cs:__imp_IoThreadToProcess
0x14002d698  nop     dword ptr [rax+rax+00h]
0x14002d69d  cmp     rax, rbx
0x14002d6a0  jz      short loc_14002D71B
0x14002d6a2  mov     rcx, [r13+20h]; FileObject
0x14002d6a6  call    cs:__imp_FltSupportsStreamContexts
0x14002d6ad  nop     dword ptr [rax+rax+00h]
0x14002d6b2  test    al, al
0x14002d6b4  jz      loc_14002DA1C
0x14002d6ba  mov     rcx, [r13+20h]; FileObject
0x14002d6be  call    cs:__imp_FltSupportsStreamHandleContexts
0x14002d6c5  nop     dword ptr [rax+rax+00h]
0x14002d6ca  test    al, al
0x14002d6cc  jz      loc_14002DA1C
0x14002d6d2  mov     rdx, [r13+20h]; FileObject
0x14002d6d6  lea     r8, [rbp+4Fh+Context]; Context
0x14002d6da  mov     rcx, [r13+18h]; Instance
0x14002d6de  call    cs:__imp_FltGetStreamHandleContext
0x14002d6e5  nop     dword ptr [rax+rax+00h]
0x14002d6ea  test    eax, eax
0x14002d6ec  jns     short loc_14002D737
0x14002d6ee  mov     rcx, cs:WPP_GLOBAL_Control
0x14002d6f5  lea     rax, WPP_GLOBAL_Control
0x14002d6fc  cmp     rcx, rax
0x14002d6ff  jz      short loc_14002D71B
0x14002d701  mov     eax, [rcx+2Ch]
0x14002d704  test    al, 4
0x14002d706  jz      short loc_14002D71B
0x14002d708  mov     edx, 61h ; 'a'
0x14002d70d  jmp     loc_14002DA43
0x14002d712  test    r12, r12
0x14002d715  jnz     loc_14002DA0F
0x14002d71b  mov     rbx, [rsp+0B0h]
0x14002d723  jmp     loc_14002D5BE
0x14002d728  test    [rbp+4Fh+arg_20], 1
0x14002d72c  jz      loc_14002D5BE
0x14002d732  jmp     loc_14002D5A0
0x14002d737  mov     rax, [rbp+4Fh+Context]
0x14002d73b  mov     rcx, [rax+60h]
0x14002d73f  test    rcx, rcx
0x14002d742  jz      short loc_14002D71B
0x14002d744  mov     eax, [rcx]
0x14002d746  test    al, 1
0x14002d748  jz      short loc_14002D71B
0x14002d74a  test    dil, al
0x14002d74d  jz      short loc_14002D7C1
0x14002d74f  test    al, 8
0x14002d751  jz      short loc_14002D71B
0x14002d753  mov     rcx, cs:WPP_GLOBAL_Control
0x14002d75a  lea     rax, WPP_GLOBAL_Control
0x14002d761  cmp     rcx, rax
0x14002d764  jz      short loc_14002D793
0x14002d766  mov     eax, [rcx+2Ch]
0x14002d769  test    al, 4
0x14002d76b  jz      short loc_14002D793
0x14002d76d  mov     rax, [r13+20h]
0x14002d771  lea     r8, WPP_ddfeb2d17970385cb7e6e54739bfb2ed_Traceguids
0x14002d778  mov     r9, [rsi+8]
0x14002d77c  add     rax, 58h ; 'X'
0x14002d780  mov     rcx, [rcx+18h]
0x14002d784  mov     edx, 62h ; 'b'
0x14002d789  mov     [rsp+0C0h+var_A0], rax
0x14002d78e  call    WPP_SF_qZ
0x14002d793  mov     rax, cs:MpData
0x14002d79a  mov     edi, 1
0x14002d79f  mov     ecx, [rax+360h]
0x14002d7a5  test    cl, 4
0x14002d7a8  mov     ecx, 0C0000022h
0x14002d7ad  mov     [rsi+20h], r12
0x14002d7b1  mov     eax, 0C0000906h
0x14002d7b6  cmovz   eax, ecx
0x14002d7b9  mov     [rsi+18h], eax
0x14002d7bc  jmp     loc_14002D71B
0x14002d7c1  lock or dword ptr [rcx], 4
0x14002d7c5  call    IsThisCallBeingThrottled
0x14002d7ca  test    al, al
0x14002d7cc  jnz     short loc_14002D7D8
0x14002d7ce  mov     ecx, 1
0x14002d7d3  call    MpSendOSCopyHintTelemetry
0x14002d7d8  mov     rdx, [r13+20h]; FileObject
0x14002d7dc  lea     r8, [rbp+4Fh+var_50]; Context
0x14002d7e0  mov     rcx, [r13+18h]; Instance
0x14002d7e4  call    cs:__imp_FltGetStreamContext
0x14002d7eb  nop     dword ptr [rax+rax+00h]
0x14002d7f0  test    eax, eax
0x14002d7f2  jns     short loc_14002D841
0x14002d7f4  mov     rcx, cs:WPP_GLOBAL_Control
0x14002d7fb  lea     rax, WPP_GLOBAL_Control
0x14002d802  cmp     rcx, rax
0x14002d805  jz      loc_14002D71B
0x14002d80b  mov     eax, [rcx+2Ch]
0x14002d80e  test    al, 1
0x14002d810  jz      loc_14002D71B
0x14002d816  mov     rax, [r13+20h]
0x14002d81a  lea     r8, WPP_ddfeb2d17970385cb7e6e54739bfb2ed_Traceguids
0x14002d821  mov     r9, [rsi+8]
0x14002d825  add     rax, 58h ; 'X'
0x14002d829  mov     rcx, [rcx+18h]
0x14002d82d  mov     edx, 63h ; 'c'
0x14002d832  mov     [rsp+0C0h+var_A0], rax
0x14002d837  call    WPP_SF_qZ
0x14002d83c  jmp     loc_14002D71B
0x14002d841  mov     rcx, rsi
0x14002d844  call    MpGetRequestorProcess
0x14002d849  lea     rbx, WPP_GLOBAL_Control
0x14002d850  test    rax, rax
0x14002d853  jz      short loc_14002D8C1
0x14002d855  lea     rdx, [rbp+4Fh+var_60]
0x14002d859  mov     rcx, rax; Process
0x14002d85c  call    MpGetProcessContextByObject
0x14002d861  mov     r12d, eax
0x14002d864  test    eax, eax
0x14002d866  jns     short loc_14002D8BD
0x14002d868  mov     rax, cs:WPP_GLOBAL_Control
0x14002d86f  cmp     rax, rbx
0x14002d872  jz      short loc_14002D8BD
0x14002d874  mov     eax, [rax+2Ch]
0x14002d877  test    dil, al
0x14002d87a  jz      short loc_14002D8BD
0x14002d87c  lfence
0x14002d87f  mov     rax, cs:WPP_GLOBAL_Control
0x14002d886  mov     rcx, rsi
0x14002d889  mov     rbx, [rsi+8]
0x14002d88d  mov     rdi, [rax+18h]
0x14002d891  call    MpGetRequestorProcessId
0x14002d896  mov     edx, 64h ; 'd'
0x14002d89b  mov     dword ptr [rsp+0C0h+var_98], r12d
0x14002d8a0  mov     r9, rbx
0x14002d8a3  mov     dword ptr [rsp+0C0h+var_A0], eax
0x14002d8a7  lea     r8, WPP_ddfeb2d17970385cb7e6e54739bfb2ed_Traceguids
0x14002d8ae  mov     rcx, rdi
0x14002d8b1  call    WPP_SF_qDD
0x14002d8b6  lea     rbx, WPP_GLOBAL_Control
0x14002d8bd  mov     r12, [rbp+4Fh+var_60]
0x14002d8c1  mov     rax, [rbp+4Fh+Context]
0x14002d8c5  mov     rcx, [rax+60h]
0x14002d8c9  lock or dword ptr [rcx], 2
0x14002d8cd  mov     r8, [rbp+4Fh+Context]
0x14002d8d1  mov     rax, [rbp+4Fh+var_50]
0x14002d8d5  mov     [rsp+58h], r8
0x14002d8da  mov     [rsp+0C0h+var_70], r12
0x14002d8df  mov     r9, [r8+60h]
0x14002d8e3  mov     [rsp+0C0h+var_78], rax
0x14002d8e8  mov     eax, [r8+2Ch]
0x14002d8ec  mov     r8, r13
0x14002d8ef  mov     dword ptr [rbp+4Fh+var_60], 0
0x14002d8f6  lea     rcx, [r9+38h]
0x14002d8fa  mov     [rsp+0C0h+var_80], rcx
0x14002d8ff  lea     rdx, [r9+10h]
0x14002d903  mov     dword ptr [rsp+0C0h+var_88], eax
0x14002d907  xor     ecx, ecx
0x14002d909  mov     eax, [r9+4]
0x14002d90d  mov     r9d, 5
0x14002d913  mov     qword ptr [rsp+0C0h+var_90], rdx
0x14002d918  mov     rdx, rsi
0x14002d91b  mov     [rsp+0C0h+var_98], 0
0x14002d924  mov     dword ptr [rsp+0C0h+var_A0], eax
0x14002d928  call    MpScanFile
0x14002d92d  mov     edx, eax
0x14002d92f  mov     byte ptr [rsp+0C0h+var_98], 0
0x14002d934  mov     rax, [rbp+4Fh+Context]
0x14002d938  lea     rcx, [rbp+4Fh+var_60]
0x14002d93c  mov     r8, rsi
0x14002d93f  mov     [rsp+0C0h+var_A0], r12
0x14002d944  mov     r9, [rax+60h]
0x14002d948  mov     r9d, [r9+4]
0x14002d94c  call    HandleMpScanFileResult
0x14002d951  mov     edi, eax
0x14002d953  cmp     eax, 1
0x14002d956  jnz     loc_14002D712
0x14002d95c  mov     rcx, [rbp+4Fh+Context]
0x14002d960  mov     rdx, [rcx+60h]
0x14002d964  lock or dword ptr [rdx], 8
0x14002d968  mov     ecx, 4
0x14002d96d  call    MpSendOSCopyHintTelemetry
0x14002d972  mov     r10, cs:WPP_GLOBAL_Control
0x14002d979  cmp     r10, rbx
0x14002d97c  jz      loc_14002D712
0x14002d982  mov     eax, [r10+2Ch]
0x14002d986  test    al, 4
0x14002d988  jz      loc_14002D712
0x14002d98e  mov     eax, dword ptr [rbp+4Fh+var_60]
0x14002d991  cmp     eax, edi
0x14002d993  jnz     short loc_14002D99E
0x14002d995  lea     rcx, aBad; "bad"
0x14002d99c  jmp     short loc_14002D9CF
0x14002d99e  cmp     eax, 2
0x14002d9a1  jnz     short loc_14002D9AC
0x14002d9a3  lea     rcx, aHipsBlockedFor; "HIPS blocked for execution"
0x14002d9aa  jmp     short loc_14002D9CF
0x14002d9ac  cmp     eax, 3
0x14002d9af  jnz     short loc_14002D9BA
0x14002d9b1  lea     rcx, aBlockedAccess; "blocked access"
0x14002d9b8  jmp     short loc_14002D9CF
0x14002d9ba  cmp     eax, 4
0x14002d9bd  lea     rcx, aBlockedForExec; "blocked for execution"
0x14002d9c4  lea     rdx, aUnknown_0; "unknown"
0x14002d9cb  cmovnz  rcx, rdx
0x14002d9cf  mov     rax, [r13+20h]
0x14002d9d3  mov     edx, 65h ; 'e'
0x14002d9d8  mov     r9, [rsi+8]
0x14002d9dc  add     rax, 58h ; 'X'
0x14002d9e0  mov     qword ptr [rsp+0C0h+var_90], rax
0x14002d9e5  mov     rax, [rbp+4Fh+var_50]
0x14002d9e9  mov     r8d, [rax+0A8h]
0x14002d9f0  mov     dword ptr [rsp+0C0h+var_98], r8d
0x14002d9f5  lea     r8, WPP_ddfeb2d17970385cb7e6e54739bfb2ed_Traceguids
0x14002d9fc  mov     [rsp+0C0h+var_A0], rcx
0x14002da01  mov     rcx, [r10+18h]
0x14002da05  call    WPP_SF_qsDZ
0x14002da0a  jmp     loc_14002D712
0x14002da0f  mov     rcx, r12
0x14002da12  call    MpReleaseProcessContext
0x14002da17  jmp     loc_14002D71B
0x14002da1c  mov     rcx, cs:WPP_GLOBAL_Control
0x14002da23  lea     rax, WPP_GLOBAL_Control
0x14002da2a  cmp     rcx, rax
0x14002da2d  jz      loc_14002D71B
  ... truncated ...
```
