# MpDlpSetProcessEntryFlags

- ea: `0x140042be0`
- end: `0x140043187`
- name: `MpDlpSetProcessEntryFlags`
- size: `1447`
- prototype: `__int64 __usercall@<rax>(PFLT_CALLBACK_DATA CallbackData@<rcx>, PFLT_FILE_NAME_INFORMATION FileNameInformation, int, int)`
- caller_count: `4`
- callee_count: `12`
- tags: ``

## callers

- `0x140002080`
- `0x14003fe70`
- `0x1400408b0`
- `0x14006f0d8`

## callees

- `0x140002450`
- `0x1400051bc`
- `0x1400118d0`
- `0x140011bc0`
- `0x14002fe00`
- `0x140030060`
- `0x140042be0`
- `0x140043ed0`
- `0x1400444b0`
- `0x140047950`
- `0x140048908`
- `0x140054230`

## import_xrefs

- `ntoskrnl!PsInitialSystemProcess` at `0x140042d91`
- `ntoskrnl!IoGetCurrentProcess` at `0x140042c7b`
- `ntoskrnl!IoGetCurrentProcess` at `0x140042c7b`
- `ntoskrnl!IoThreadToProcess` at `0x140042d3d`
- `ntoskrnl!IoThreadToProcess` at `0x140042d69`
- `ntoskrnl!IoThreadToProcess` at `0x140042d3d`
- `ntoskrnl!IoThreadToProcess` at `0x140042d69`
- `ntoskrnl!ExFreePoolWithTag` at `0x140043150`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004316c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140043150`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004316c`
- `FLTMGR!FltReleaseContext` at `0x140042e9c`
- `FLTMGR!FltReleaseContext` at `0x140042e9c`
- `FLTMGR!FltReleasePushLock` at `0x140042cf7`
- `FLTMGR!FltReleasePushLock` at `0x140042cf7`
- `FLTMGR!FltGetStreamHandleContext` at `0x140042efa`
- `FLTMGR!FltGetStreamHandleContext` at `0x140042efa`
- `FLTMGR!FltAcquirePushLockExclusive` at `0x140042ecd`
- `FLTMGR!FltAcquirePushLockExclusive` at `0x140042ecd`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140042e6d`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140042e6d`

## pseudocode

```c
__int64 __fastcall MpDlpSetProcessEntryFlags(
        PFLT_CALLBACK_DATA CallbackData,
        __int64 a2,
        _QWORD *a3,
        void *a4,
        PFLT_FILE_NAME_INFORMATION FileNameInformation,
        int a6,
        int a7)
{
  PFLT_FILE_NAME_INFORMATION v7; // rbx
  struct _FLT_FILE_NAME_INFORMATION *v11; // rsi
  int FileName; // r14d
  char v13; // r15
  struct _KPROCESS *v15; // rbx
  struct _KPROCESS *v16; // rbx
  struct _KPROCESS *RequestorProcess; // rcx
  unsigned __int64 *v18; // rcx
  unsigned __int64 *i; // rdx
  _QWORD *v20; // rcx
  char *v21; // rax
  PFLT_CONTEXT *v22; // rdx
  _QWORD *v23; // rbx
  PFLT_IO_PARAMETER_BLOCK Iopb; // rax
  _OWORD *v25; // rax
  __int64 v26; // rcx
  void *v27; // rcx
  __int64 v28; // [rsp+40h] [rbp-C0h] BYREF
  PFLT_FILE_NAME_INFORMATION v29; // [rsp+48h] [rbp-B8h]
  PFLT_CALLBACK_DATA v30; // [rsp+50h] [rbp-B0h]
  PEPROCESS CurrentProcess; // [rsp+58h] [rbp-A8h]
  PFLT_CONTEXT v32; // [rsp+60h] [rbp-A0h]
  PFLT_CONTEXT Context; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v34[16]; // [rsp+70h] [rbp-90h] BYREF

  v7 = FileNameInformation;
  v32 = a4;
  Context = a4;
  v29 = FileNameInformation;
  v28 = 0;
  v11 = FileNameInformation;
  FileName = -1073741823;
  v13 = 0;
  memset(v34, 0, 0x78u);
  if ( !a7 || !a2 || !a3 )
    return 3221225485LL;
  v30 = CallbackData;
  CurrentProcess = IoGetCurrentProcess();
  if ( MpDlpData )
  {
    if ( (unsigned __int64)(&CallbackData[-1].RequestorMode + 7) <= 1 )
      v30 = 0;
    if ( *((_BYTE *)MpDlpData + 32)
      && (*(_DWORD *)(MpData + 864) & 0x400) != 0
      && (*(_QWORD *)(MpData + 320) || *(_QWORD *)(MpData + 336)) )
    {
      v15 = *(struct _KPROCESS **)(MpData + 232);
      if ( IoThreadToProcess(KeGetCurrentThread()) == v15
        || (v16 = *(struct _KPROCESS **)(MpData + 256), IoThreadToProcess(KeGetCurrentThread()) == v16) )
      {
        if ( (unsigned __int64)(&CallbackData[-1].RequestorMode + 7) > 1 )
        {
LABEL_45:
          v7 = FileNameInformation;
          goto LABEL_8;
        }
      }
      else
      {
        if ( v30 )
        {
          RequestorProcess = (struct _KPROCESS *)MpGetRequestorProcess(v30);
          if ( !RequestorProcess )
          {
            v7 = FileNameInformation;
            goto LABEL_8;
          }
        }
        else
        {
          RequestorProcess = CurrentProcess;
        }
        if ( PsInitialSystemProcess == RequestorProcess
          && !(unsigned __int8)MpIsPotentialRemoteOpen(v30)
          && CallbackData != (PFLT_CALLBACK_DATA)2
          || MpDlpIsProcessExcluded((__int64)v30, a3) )
        {
          goto LABEL_45;
        }
      }
      v18 = (unsigned __int64 *)Context;
      if ( Context )
      {
LABEL_22:
        if ( CallbackData->Iopb->MajorFunction )
        {
          FltAcquirePushLockExclusive(v18 + 8);
          v18 = (unsigned __int64 *)Context;
          v13 = 1;
        }
        for ( i = (unsigned __int64 *)v18[6]; i != v18 + 6; i = (unsigned __int64 *)*i )
        {
          if ( (_QWORD *)i[2] == a3 )
          {
            v7 = FileNameInformation;
            *((_DWORD *)i + 10) |= a7;
            FileName = 0;
            goto LABEL_8;
          }
        }
        v7 = FileNameInformation;
        if ( FileNameInformation )
          goto LABEL_27;
        if ( (*((_DWORD *)v18 + 10) & 0x80u) != 0 && (v25 = (_OWORD *)v18[10]) != 0 )
        {
          *(_OWORD *)&v34[1] = *v25;
          FileName = MpParseFileName(v18[10], 0, &v34[7], &v34[9], &v34[11]);
          if ( FileName >= 0 )
          {
            v11 = (struct _FLT_FILE_NAME_INFORMATION *)v34;
            goto LABEL_27;
          }
        }
        else
        {
          v11 = v29;
          FileName = MpQueryFileName(CallbackData);
          if ( FileName >= 0 )
          {
LABEL_27:
            FileName = MpCreateDlpProcessEntry(a3, &v11->Name, &v28);
            if ( FileName < 0 )
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
              {
                _mm_lfence();
                WPP_SF_qD(
                  WPP_GLOBAL_Control->AttachedDevice,
                  92,
                  WPP_4c1363a434f0368aee73563b7bc19017_Traceguids,
                  KeGetCurrentThread(),
                  FileName);
              }
              v23 = (_QWORD *)v28;
            }
            else
            {
              v20 = (_QWORD *)v28;
              *(_DWORD *)(v28 + 40) |= a7;
              v21 = (char *)Context + 48;
              v22 = (PFLT_CONTEXT *)*((_QWORD *)Context + 7);
              if ( *v22 != (char *)Context + 48 )
                __fastfail(3u);
              *v20 = v21;
              v23 = 0;
              v20[1] = v22;
              FileName = 0;
              *v22 = v20;
              *((_QWORD *)v21 + 1) = v20;
            }
            if ( v23 )
            {
              v26 = v23[2];
              if ( v26 )
              {
                MpReleaseProcessContext(v26);
                v23[2] = 0;
              }
              v27 = (void *)v23[4];
              if ( v27 )
              {
                ExFreePoolWithTag(v27, 0x6E66504Du);
                v23[4] = 0;
              }
              ExFreePoolWithTag(v23, 0x6670504Du);
            }
            v7 = FileNameInformation;
            goto LABEL_8;
          }
        }
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        {
          _mm_lfence();
          WPP_SF_qD(
            WPP_GLOBAL_Control->AttachedDevice,
            91,
            WPP_4c1363a434f0368aee73563b7bc19017_Traceguids,
            KeGetCurrentThread(),
            FileName);
        }
        goto LABEL_8;
      }
      if ( FltGetStreamHandleContext(*(PFLT_INSTANCE *)(a2 + 24), *(PFILE_OBJECT *)(a2 + 32), &Context) < 0 )
      {
        FileName = MpCreateHandleContext(a2, &Context, 0);
        if ( FileName < 0 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          {
            _mm_lfence();
            WPP_SF_qD(
              WPP_GLOBAL_Control->AttachedDevice,
              90,
              WPP_4c1363a434f0368aee73563b7bc19017_Traceguids,
              KeGetCurrentThread(),
              FileName);
          }
          goto LABEL_45;
        }
        Iopb = CallbackData->Iopb;
        if ( !Iopb->MajorFunction )
          *((_DWORD *)Context + 22) = *(_DWORD *)(Iopb->Parameters.WMI.ProviderId + 16);
      }
      v18 = (unsigned __int64 *)Context;
      goto LABEL_22;
    }
  }
LABEL_8:
  if ( v11 && v11 != (struct _FLT_FILE_NAME_INFORMATION *)v34 && v11 != v7 )
    FltReleaseFileNameInformation(v11);
  if ( v13 )
    FltReleasePushLock((PULONG_PTR)Context + 8);
  if ( Context )
  {
    if ( Context != v32 )
      FltReleaseContext(Context);
  }
  return (unsigned int)FileName;
}

```

## disassembly

```asm
0x140042be0  push    rbp
0x140042be2  push    rbx
0x140042be3  push    rsi
0x140042be4  push    rdi
0x140042be5  push    r12
0x140042be7  push    r13
0x140042be9  push    r14
0x140042beb  push    r15
0x140042bed  lea     rbp, [rsp-8]
0x140042bf2  sub     rsp, 108h
0x140042bf9  mov     rax, cs:__security_cookie
0x140042c00  xor     rax, rsp
0x140042c03  mov     [rbp+40h+var_50], rax
0x140042c07  mov     rbx, [rbp+40h+FileNameInformation]
0x140042c0b  mov     rax, r9
0x140042c0e  mov     r12, r8
0x140042c11  mov     [rsp+140h+var_E0], rax
0x140042c16  mov     r13, rdx
0x140042c19  mov     [rsp+140h+var_108], rbx
0x140042c1e  mov     rdi, rcx
0x140042c21  mov     [rsp+140h+Context], rax
0x140042c26  xor     edx, edx; Val
0x140042c28  mov     [rsp+140h+var_F8], rbx
0x140042c2d  mov     r8d, 78h ; 'x'; Size
0x140042c33  mov     [rsp+140h+var_100], 0
0x140042c3c  lea     rcx, [rsp+140h+var_D0]; void *
0x140042c41  mov     rsi, rbx
0x140042c44  mov     r14d, 0C0000001h
0x140042c4a  xor     r15b, r15b
0x140042c4d  call    memset
0x140042c52  cmp     [rbp+40h+arg_30], 0
0x140042c59  mov     [rsp+140h+var_110], r15b
0x140042c5e  jz      loc_14004317D
0x140042c64  test    r13, r13
0x140042c67  jz      loc_14004317D
0x140042c6d  test    r12, r12
0x140042c70  jz      loc_14004317D
0x140042c76  mov     [rsp+140h+var_F0], rdi
0x140042c7b  call    cs:__imp_IoGetCurrentProcess
0x140042c82  nop     dword ptr [rax+rax+00h]
0x140042c87  mov     [rsp+140h+var_E8], rax
0x140042c8c  mov     rax, cs:MpDlpData
0x140042c93  test    rax, rax
0x140042c96  jz      short loc_140042CAE
0x140042c98  lea     rcx, [rdi-1]
0x140042c9c  cmp     rcx, 1
0x140042ca0  jbe     loc_140042F77
0x140042ca6  movzx   ecx, byte ptr [rax+20h]
0x140042caa  test    cl, cl
0x140042cac  jnz     short loc_140042D05
0x140042cae  test    rsi, rsi
0x140042cb1  jnz     loc_140042E53
0x140042cb7  test    r15b, r15b
0x140042cba  jnz     short loc_140042CEE
0x140042cbc  mov     rcx, [rsp+140h+Context]; Context
0x140042cc1  test    rcx, rcx
0x140042cc4  jnz     loc_140042E91
0x140042cca  mov     eax, r14d
0x140042ccd  mov     rcx, [rbp+40h+var_50]
0x140042cd1  xor     rcx, rsp; StackCookie
0x140042cd4  call    __security_check_cookie
0x140042cd9  add     rsp, 108h
0x140042ce0  pop     r15
0x140042ce2  pop     r14
0x140042ce4  pop     r13
0x140042ce6  pop     r12
0x140042ce8  pop     rdi
0x140042ce9  pop     rsi
0x140042cea  pop     rbx
0x140042ceb  pop     rbp
0x140042cec  retn
0x140042cee  mov     rcx, [rsp+140h+Context]
0x140042cf3  add     rcx, 40h ; '@'; PushLock
0x140042cf7  call    cs:__imp_FltReleasePushLock
0x140042cfe  nop     dword ptr [rax+rax+00h]
0x140042d03  jmp     short loc_140042CBC
0x140042d05  mov     rcx, cs:MpData
0x140042d0c  test    dword ptr [rcx+360h], 400h
0x140042d16  jz      short loc_140042CAE
0x140042d18  cmp     qword ptr [rcx+140h], 0
0x140042d20  jz      loc_140042F64
0x140042d26  mov     rcx, gs:188h; Thread
0x140042d2f  mov     rax, cs:MpData
0x140042d36  mov     rbx, [rax+0E8h]
0x140042d3d  call    cs:__imp_IoThreadToProcess
0x140042d44  nop     dword ptr [rax+rax+00h]
0x140042d49  cmp     rax, rbx
0x140042d4c  jz      loc_140042E7E
0x140042d52  mov     rcx, gs:188h; Thread
0x140042d5b  mov     rax, cs:MpData
0x140042d62  mov     rbx, [rax+100h]
0x140042d69  call    cs:__imp_IoThreadToProcess
0x140042d70  nop     dword ptr [rax+rax+00h]
0x140042d75  cmp     rax, rbx
0x140042d78  jz      loc_140042E7E
0x140042d7e  mov     rbx, [rsp+140h+var_F0]
0x140042d83  test    rbx, rbx
0x140042d86  jnz     loc_140042EAD
0x140042d8c  mov     rcx, [rsp+140h+var_E8]
0x140042d91  mov     rax, cs:__imp_PsInitialSystemProcess
0x140042d98  cmp     [rax], rcx
0x140042d9b  jz      loc_140042F48
0x140042da1  mov     rdx, r12
0x140042da4  mov     rcx, rbx
0x140042da7  call    MpDlpIsProcessExcluded
0x140042dac  test    al, al
0x140042dae  jnz     loc_140042F40
0x140042db4  mov     rcx, [rsp+140h+Context]
0x140042db9  test    rcx, rcx
0x140042dbc  jz      loc_140042EED
0x140042dc2  mov     rax, [rdi+10h]
0x140042dc6  cmp     [rax+4], r15b
0x140042dca  jnz     loc_140042EC9
0x140042dd0  mov     rdx, [rcx+30h]
0x140042dd4  lea     rax, [rcx+30h]
0x140042dd8  cmp     rdx, rax
0x140042ddb  jnz     loc_140043009
0x140042de1  mov     rbx, rsi
0x140042de4  test    rbx, rbx
0x140042de7  jz      loc_140042F85
0x140042ded  lea     rdx, [rsi+8]
0x140042df1  mov     rcx, r12
0x140042df4  lea     r8, [rsp+140h+var_100]
0x140042df9  call    MpCreateDlpProcessEntry
0x140042dfe  mov     r14d, eax
0x140042e01  test    eax, eax
0x140042e03  js      loc_1400430DB
0x140042e09  mov     eax, [rbp+40h+arg_30]
0x140042e0f  mov     rcx, [rsp+140h+var_100]
0x140042e14  or      [rcx+28h], eax
0x140042e17  mov     rax, [rsp+140h+Context]
0x140042e1c  add     rax, 30h ; '0'
0x140042e20  mov     rdx, [rax+8]
0x140042e24  cmp     [rdx], rax
0x140042e27  jnz     loc_140042EE6
0x140042e2d  mov     [rcx], rax
0x140042e30  xor     ebx, ebx
0x140042e32  mov     [rcx+8], rdx
0x140042e36  xor     r14d, r14d
0x140042e39  mov     [rdx], rcx
0x140042e3c  mov     [rax+8], rcx
0x140042e40  test    rbx, rbx
0x140042e43  jnz     loc_14004312C
0x140042e49  mov     rbx, [rsp+140h+var_108]
0x140042e4e  jmp     loc_140042CAE
0x140042e53  lea     rax, [rsp+140h+var_D0]
0x140042e58  cmp     rsi, rax
0x140042e5b  jz      loc_140042CB7
0x140042e61  cmp     rsi, rbx
0x140042e64  jz      loc_140042CB7
0x140042e6a  mov     rcx, rsi; FileNameInformation
0x140042e6d  call    cs:__imp_FltReleaseFileNameInformation
0x140042e74  nop     dword ptr [rax+rax+00h]
0x140042e79  jmp     loc_140042CB7
0x140042e7e  lea     rax, [rdi-1]
0x140042e82  cmp     rax, 1
0x140042e86  jbe     loc_140042DB4
0x140042e8c  jmp     loc_140042F40
0x140042e91  cmp     rcx, [rsp+140h+var_E0]
0x140042e96  jz      loc_140042CCA
0x140042e9c  call    cs:__imp_FltReleaseContext
0x140042ea3  nop     dword ptr [rax+rax+00h]
0x140042ea8  jmp     loc_140042CCA
0x140042ead  mov     rcx, rbx
0x140042eb0  call    MpGetRequestorProcess
0x140042eb5  mov     rcx, rax
0x140042eb8  test    rax, rax
0x140042ebb  jnz     loc_140042D91
0x140042ec1  mov     rbx, rsi
0x140042ec4  jmp     loc_140042CAE
0x140042ec9  add     rcx, 40h ; '@'; PushLock
0x140042ecd  call    cs:__imp_FltAcquirePushLockExclusive
0x140042ed4  nop     dword ptr [rax+rax+00h]
0x140042ed9  mov     rcx, [rsp+140h+Context]
0x140042ede  mov     r15b, 1
0x140042ee1  jmp     loc_140042DD0
0x140042ee6  mov     ecx, 3
0x140042eeb  int     29h; Win8: RtlFailFast(ecx)
0x140042eed  mov     rdx, [r13+20h]; FileObject
0x140042ef1  lea     r8, [rsp+140h+Context]; Context
0x140042ef6  mov     rcx, [r13+18h]; Instance
0x140042efa  call    cs:__imp_FltGetStreamHandleContext
0x140042f01  nop     dword ptr [rax+rax+00h]
0x140042f06  test    eax, eax
0x140042f08  jns     loc_140043082
0x140042f0e  xor     r8d, r8d
0x140042f11  lea     rdx, [rsp+140h+Context]
0x140042f16  mov     rcx, r13
0x140042f19  call    MpCreateHandleContext
0x140042f1e  mov     r14d, eax
0x140042f21  test    eax, eax
0x140042f23  jns     loc_140043069
0x140042f29  mov     rcx, cs:WPP_GLOBAL_Control
0x140042f30  lea     rax, WPP_GLOBAL_Control
0x140042f37  cmp     rcx, rax
0x140042f3a  jnz     loc_14004302B
0x140042f40  mov     rbx, rsi
0x140042f43  jmp     loc_140042CAE
0x140042f48  mov     rcx, rbx
0x140042f4b  call    MpIsPotentialRemoteOpen
0x140042f50  test    al, al
0x140042f52  jnz     loc_140042DA1
0x140042f58  cmp     rdi, 2
0x140042f5c  jz      loc_140042DA1
0x140042f62  jmp     short loc_140042F40
0x140042f64  cmp     qword ptr [rcx+150h], 0
0x140042f6c  jnz     loc_140042D26
0x140042f72  jmp     loc_140042CAE
0x140042f77  mov     [rsp+140h+var_F0], 0
0x140042f80  jmp     loc_140042CA6
0x140042f85  mov     eax, [rcx+28h]
0x140042f88  test    al, al
0x140042f8a  js      loc_14004308C
0x140042f90  mov     edx, [rbp+40h+arg_28]
0x140042f93  lea     r9, [rsp+140h+var_110]
0x140042f98  lea     r8, [rsp+140h+var_F8]
0x140042f9d  mov     rcx, rdi; CallbackData
0x140042fa0  call    MpQueryFileName
0x140042fa5  mov     rsi, [rsp+140h+var_F8]
0x140042faa  mov     r14d, eax
0x140042fad  test    eax, eax
0x140042faf  jns     loc_140042DED
0x140042fb5  mov     rcx, cs:WPP_GLOBAL_Control
0x140042fbc  lea     rax, WPP_GLOBAL_Control
0x140042fc3  cmp     rcx, rax
0x140042fc6  jz      loc_140042CAE
0x140042fcc  mov     eax, [rcx+2Ch]
0x140042fcf  test    al, 1
0x140042fd1  jz      loc_140042CAE
0x140042fd7  lfence
0x140042fda  mov     r9, gs:188h
0x140042fe3  lea     r8, WPP_4c1363a434f0368aee73563b7bc19017_Traceguids
0x140042fea  mov     rcx, cs:WPP_GLOBAL_Control
0x140042ff1  mov     edx, 5Bh ; '['
0x140042ff6  mov     dword ptr [rsp+140h+var_120], r14d
0x140042ffb  mov     rcx, [rcx+18h]
0x140042fff  call    WPP_SF_qD
0x140043004  jmp     loc_140042CAE
0x140043009  cmp     [rdx+10h], r12
0x14004300d  jz      short loc_140043017
0x14004300f  mov     rdx, [rdx]
0x140043012  jmp     loc_140042DD8
0x140043017  mov     eax, [rbp+40h+arg_30]
0x14004301d  mov     rbx, rsi
0x140043020  or      [rdx+28h], eax
0x140043023  xor     r14d, r14d
0x140043026  jmp     loc_140042CAE
0x14004302b  mov     ecx, [rcx+2Ch]
0x14004302e  test    cl, 1
0x140043031  jz      loc_140042F40
0x140043037  lfence
0x14004303a  mov     r9, gs:188h
0x140043043  lea     r8, WPP_4c1363a434f0368aee73563b7bc19017_Traceguids
0x14004304a  mov     rcx, cs:WPP_GLOBAL_Control
0x140043051  mov     edx, 5Ah ; 'Z'
0x140043056  mov     dword ptr [rsp+140h+var_120], r14d
0x14004305b  mov     rcx, [rcx+18h]
0x14004305f  call    WPP_SF_qD
0x140043064  jmp     loc_140042F40
0x140043069  mov     rax, [rdi+10h]
0x14004306d  cmp     [rax+4], r15b
0x140043071  jnz     short loc_140043082
0x140043073  mov     rax, [rax+18h]
0x140043077  mov     ecx, [rax+10h]
0x14004307a  mov     rax, [rsp+140h+Context]
0x14004307f  mov     [rax+58h], ecx
0x140043082  mov     rcx, [rsp+140h+Context]
0x140043087  jmp     loc_140042DC2
0x14004308c  mov     rax, [rcx+50h]
0x140043090  test    rax, rax
0x140043093  jz      loc_140042F90
0x140043099  movups  xmm0, xmmword ptr [rax]
0x14004309c  lea     rax, [rbp+40h+var_68]
0x1400430a0  xor     edx, edx
0x1400430a2  mov     [rsp+140h+var_118], rax
0x1400430a7  lea     r9, [rbp+40h+var_88]
0x1400430ab  movups  [rsp+140h+var_C8], xmm0
0x1400430b0  mov     rcx, [rcx+50h]
0x1400430b4  lea     rax, [rbp+40h+var_78]
0x1400430b8  lea     r8, [rbp+40h+var_98]
0x1400430bc  mov     [rsp+140h+var_120], rax
0x1400430c1  call    MpParseFileName
0x1400430c6  mov     r14d, eax
0x1400430c9  test    eax, eax
0x1400430cb  js      loc_140042FB5
0x1400430d1  lea     rsi, [rsp+140h+var_D0]
0x1400430d6  jmp     loc_140042DED
0x1400430db  mov     rcx, cs:WPP_GLOBAL_Control
0x1400430e2  lea     rax, WPP_GLOBAL_Control
0x1400430e9  cmp     rcx, rax
0x1400430ec  jz      short loc_140043122
0x1400430ee  mov     eax, [rcx+2Ch]
0x1400430f1  test    al, 1
0x1400430f3  jz      short loc_140043122
0x1400430f5  lfence
0x1400430f8  mov     r9, gs:188h
0x140043101  lea     r8, WPP_4c1363a434f0368aee73563b7bc19017_Traceguids
0x140043108  mov     rcx, cs:WPP_GLOBAL_Control
0x14004310f  mov     edx, 5Ch ; '\'
0x140043114  mov     dword ptr [rsp+140h+var_120], r14d
  ... truncated ...
```
