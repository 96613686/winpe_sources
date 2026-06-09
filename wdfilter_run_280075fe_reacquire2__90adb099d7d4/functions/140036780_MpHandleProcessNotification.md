# MpHandleProcessNotification

- ea: `0x140036780`
- end: `0x140036d7f`
- name: `MpHandleProcessNotification`
- size: `1535`
- prototype: ``
- caller_count: `2`
- callee_count: `19`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1400363d0`
- `0x140082150`

## callees

- `0x1400018a4`
- `0x1400051bc`
- `0x14000ed8c`
- `0x1400118d0`
- `0x14002c980`
- `0x14002cee0`
- `0x140030060`
- `0x140035130`
- `0x140036780`
- `0x140036f10`
- `0x140036f50`
- `0x140037820`
- `0x140037928`
- `0x1400387f0`
- `0x14005e9c4`
- `0x140064160`
- `0x1400735a8`
- `0x1400791e8`
- `0x1400861e0`

## import_xrefs

- `ntoskrnl!ExNotifyCallback` at `0x140036a0f`
- `ntoskrnl!ExNotifyCallback` at `0x140036b9f`
- `ntoskrnl!ExNotifyCallback` at `0x140036a0f`
- `ntoskrnl!ExNotifyCallback` at `0x140036b9f`
- `ntoskrnl!PsGetProcessCreateTimeQuadPart` at `0x14003684c`
- `ntoskrnl!PsGetProcessCreateTimeQuadPart` at `0x14003684c`
- `ntoskrnl!IoThreadToProcess` at `0x14003692e`
- `ntoskrnl!IoThreadToProcess` at `0x140036a89`
- `ntoskrnl!IoThreadToProcess` at `0x14003692e`
- `ntoskrnl!IoThreadToProcess` at `0x140036a89`
- `ntoskrnl!KeWaitForSingleObject` at `0x140036b03`
- `ntoskrnl!KeWaitForSingleObject` at `0x140036b03`
- `ntoskrnl!PsGetCurrentProcessId` at `0x1400368fc`
- `ntoskrnl!PsGetCurrentProcessId` at `0x1400368fc`

## pseudocode

```c
void __fastcall MpHandleProcessNotification(
        struct _KPROCESS *a1,
        void *a2,
        void *a3,
        char a4,
        int a5,
        struct _FILE_OBJECT *a6,
        const UNICODE_STRING *a7,
        const UNICODE_STRING *a8,
        _BYTE *a9)
{
  int v10; // r14d
  struct _KPROCESS *v14; // rbx
  int ProcessContext; // eax
  int v16; // eax
  int v17; // edx
  int v18; // r8d
  __int64 v19; // r8
  HANDLE CurrentProcessId; // rax
  struct _KPROCESS *v21; // rbx
  __int64 v22; // rcx
  unsigned __int8 v23; // dl
  int v24; // eax
  __int64 *v25; // rax
  int v26; // eax
  bool v27; // al
  struct _KPROCESS *v28; // rbx
  __int64 v29; // rdx
  __int64 v30; // rcx
  __int64 v31; // [rsp+60h] [rbp-79h] BYREF
  _BYTE *v32; // [rsp+68h] [rbp-71h]
  const UNICODE_STRING *v33; // [rsp+70h] [rbp-69h]
  PEPROCESS Process; // [rsp+78h] [rbp-61h]
  __int64 v35; // [rsp+80h] [rbp-59h] BYREF
  __int128 Argument1; // [rsp+88h] [rbp-51h] BYREF
  __int128 v37; // [rsp+98h] [rbp-41h]
  __int128 v38; // [rsp+A8h] [rbp-31h]
  void *v39; // [rsp+B8h] [rbp-21h]
  __int64 v40; // [rsp+C0h] [rbp-19h] BYREF
  int v41; // [rsp+C8h] [rbp-11h]

  v10 = a5 | 2;
  v33 = a8;
  Process = a1;
  v40 = 0;
  v41 = 0;
  v39 = 0;
  v32 = a9;
  v35 = 0;
  Argument1 = 0;
  v37 = 0;
  v38 = 0;
  if ( !g_bSystemProcessContextCreateTimeFixed )
    MpFixSystemProcessContextCreateTime();
  if ( a4 )
  {
    if ( MpDlpData && !*((_BYTE *)MpDlpData + 44) )
      MpDlpInitializeEnlightenment();
    if ( v32 )
      *v32 = 0;
    v14 = Process;
    *(_QWORD *)&v38 = a7;
    *((_QWORD *)&v38 + 1) = v33;
    v39 = a2;
    PsGetProcessCreateTimeQuadPart(Process);
    ProcessContext = MpCreateProcessContext(a3);
    if ( ProcessContext >= 0 )
    {
      _mm_lfence();
      *(_DWORD *)(v35 + 52) |= 4u;
      if ( *(_QWORD *)(MpData + 40) )
        *(_DWORD *)(v35 + 52) |= 0x400u;
      if ( *(_DWORD *)(MpData + 4084) )
      {
        v31 = 0;
        if ( (int)MpGetProcessContextById(a2, &v31) >= 0 )
        {
          v30 = v31;
          if ( v31 )
          {
            *(_DWORD *)(v31 + 52) |= 0x8000u;
            MpReleaseProcessContext(v30);
          }
        }
      }
      v16 = MpSetProcessDocOpenRule(v35, a7);
      if ( v16 < 0
        && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      {
        _mm_lfence();
        WPP_SF_qqZL(
          WPP_GLOBAL_Control->AttachedDevice,
          v17,
          v18,
          (unsigned int)KeGetCurrentThread(),
          (__int64)a3,
          (__int64)a7,
          v16);
      }
      MpSetProcessPreScanFilterRoutine(v14, v35, a7);
      LOBYTE(v19) = 1;
      MpSetProcessExempt(v35, a7, v19, 0);
      MpSetProcessHardening(v14);
      MpSetProcessHardeningExclusion(v35, v14, a7);
      CurrentProcessId = PsGetCurrentProcessId();
      LODWORD(v31) = GetMpUniquePidFromProcessId(CurrentProcessId, &v40);
      v21 = *(struct _KPROCESS **)(MpData + 232);
      if ( IoThreadToProcess(KeGetCurrentThread()) != v21 )
      {
        v28 = *(struct _KPROCESS **)(MpData + 256);
        if ( IoThreadToProcess(KeGetCurrentThread()) != v28 && a6 && (*(_DWORD *)(MpData + 864) & 0x10) != 0 )
        {
          v22 = v35;
          if ( *(_DWORD *)(v35 + 120) )
            goto LABEL_14;
          if ( !(unsigned __int8)MpIsNtCreateUserProcessFileObject(a6) )
            v10 = a5 & 0xFFFFFFFD;
        }
      }
      v22 = v35;
LABEL_14:
      v23 = *(_BYTE *)(v22 + 184) >> 4;
      if ( !v23 || v23 >= 9u || (unsigned __int8)((*(_BYTE *)(v22 + 184) & 7) - 1) > 1u )
      {
        v24 = *(_DWORD *)(v22 + 240);
        if ( v24 == 17 || v24 == 18 )
          v10 |= 0xCu;
      }
      v25 = &v40;
      if ( (int)v31 < 0 )
        v25 = 0;
      v26 = MpSendProcessMessage(1, Process, a6, a3, v10, a2, (__int64)v25, a7, v22, v33, v32);
      if ( v26 < 0
        && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      {
        _mm_lfence();
        WPP_SF_qD(
          WPP_GLOBAL_Control->AttachedDevice,
          26,
          WPP_8ebd71c5d5f53801838f519f7d1f4ffb_Traceguids,
          KeGetCurrentThread(),
          v26);
      }
      *((_QWORD *)&Argument1 + 1) = a2;
      *(_QWORD *)&Argument1 = a3;
      *(_QWORD *)&v37 = a7;
      v27 = (*(_BYTE *)(v35 + 52) & 0x40) != 0;
      DWORD2(v37) = 1;
      BYTE12(v37) = v27;
      BYTE13(v37) = (*(_BYTE *)(v35 + 60) & 2) != 0;
      BYTE14(v37) = (*(_DWORD *)(v35 + 60) & 0x400) != 0;
      ExNotifyCallback(*(PVOID *)(MpData + 2488), &Argument1, 0);
      goto LABEL_21;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      v29 = 24;
      goto LABEL_41;
    }
  }
  else
  {
    KeWaitForSingleObject((char *)MpProcessTable + 392, Executive, 0, 0, 0);
    if ( (int)MpGetProcessContextById(a3, &v35) < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          27,
          WPP_8ebd71c5d5f53801838f519f7d1f4ffb_Traceguids,
          (unsigned int)a3);
      goto LABEL_21;
    }
    _InterlockedOr((volatile signed __int32 *)(v35 + 52), 0x2000u);
    MpDeleteProcessContext(v35);
    *(_QWORD *)&Argument1 = a3;
    *(_QWORD *)&v37 = 0;
    DWORD2(v37) = 2;
    WORD6(v37) = 0;
    BYTE14(v37) = 0;
    ExNotifyCallback(*(PVOID *)(MpData + 2488), &Argument1, 0);
    if ( !v35 )
      return;
    if ( (*(_DWORD *)(v35 + 52) & 8) == 0 )
    {
      ProcessContext = MpSendProcessMessage(0, a1, a6, a3, v10, 0, 0, 0, v35, 0, 0);
      if ( ProcessContext < 0
        && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      {
        v29 = 28;
LABEL_41:
        _mm_lfence();
        WPP_SF_qD(
          WPP_GLOBAL_Control->AttachedDevice,
          v29,
          WPP_8ebd71c5d5f53801838f519f7d1f4ffb_Traceguids,
          KeGetCurrentThread(),
          ProcessContext);
      }
    }
  }
LABEL_21:
  if ( v35 )
    MpReleaseProcessContext(v35);
}

```

## disassembly

```asm
0x140036780  mov     [rsp-8+arg_18], rbx
0x140036785  push    rbp
0x140036786  push    rsi
0x140036787  push    rdi
0x140036788  push    r12
0x14003678a  push    r13
0x14003678c  push    r14
0x14003678e  push    r15
0x140036790  lea     rbp, [rsp-7]
0x140036795  sub     rsp, 0E0h
0x14003679c  mov     rax, cs:__security_cookie
0x1400367a3  xor     rax, rsp
0x1400367a6  mov     [rbp+37h+var_40], rax
0x1400367aa  mov     rax, [rbp+37h+arg_38]
0x1400367ae  xorps   xmm0, xmm0
0x1400367b1  mov     r14d, [rbp+37h+arg_20]
0x1400367b5  mov     r13, rdx
0x1400367b8  mov     rdx, [rbp+37h+arg_40]
0x1400367bf  or      r14d, 2
0x1400367c3  mov     r12, [rbp+37h+arg_28]
0x1400367c7  mov     bl, r9b
0x1400367ca  mov     r15, [rbp+37h+arg_30]
0x1400367ce  mov     rsi, r8
0x1400367d1  mov     [rbp+37h+var_A0], rax
0x1400367d5  mov     rdi, rcx
0x1400367d8  xor     eax, eax
0x1400367da  mov     [rbp+37h+Process], rcx
0x1400367de  mov     [rbp+37h+var_50], rax
0x1400367e2  mov     [rbp+37h+var_48], eax
0x1400367e5  mov     [rbp+37h+var_58], rax
0x1400367e9  mov     al, cs:g_bSystemProcessContextCreateTimeFixed
0x1400367ef  mov     [rbp+37h+var_A8], rdx
0x1400367f3  mov     [rbp+37h+var_90], 0
0x1400367fb  movups  [rbp+37h+Argument1], xmm0
0x1400367ff  movups  [rbp+37h+var_78], xmm0
0x140036803  movups  [rbp+37h+var_68], xmm0
0x140036807  test    al, al
0x140036809  jz      loc_140036C52
0x14003680f  test    bl, bl
0x140036811  jz      loc_140036AE5
0x140036817  mov     rax, cs:MpDlpData
0x14003681e  xor     edi, edi
0x140036820  test    rax, rax
0x140036823  jnz     loc_140036A50
0x140036829  mov     rax, [rbp+37h+var_A8]
0x14003682d  test    rax, rax
0x140036830  jz      short loc_140036835
0x140036832  mov     [rax], dil
0x140036835  mov     rax, [rbp+37h+var_A0]
0x140036839  mov     rbx, [rbp+37h+Process]
0x14003683d  mov     rcx, rbx; Process
0x140036840  mov     qword ptr [rbp+37h+var_68], r15
0x140036844  mov     qword ptr [rbp+37h+var_68+8], rax
0x140036848  mov     [rbp+37h+var_58], r13
0x14003684c  call    cs:__imp_PsGetProcessCreateTimeQuadPart
0x140036853  nop     dword ptr [rax+rax+00h]
0x140036858  lea     r9, [rbp+37h+var_90]
0x14003685c  mov     rcx, rsi; ProcessId
0x14003685f  mov     rdx, rax
0x140036862  lea     r8, [rbp+37h+var_68]
0x140036866  call    MpCreateProcessContext
0x14003686b  test    eax, eax
0x14003686d  js      loc_140036C5C
0x140036873  lfence
0x140036876  mov     rax, [rbp+37h+var_90]
0x14003687a  or      dword ptr [rax+34h], 4
0x14003687e  mov     rax, cs:MpData
0x140036885  cmp     [rax+28h], rdi
0x140036889  jnz     loc_140036A64
0x14003688f  mov     rax, cs:MpData
0x140036896  cmp     [rax+0FF4h], edi
0x14003689c  jnz     loc_140036C86
0x1400368a2  mov     rcx, [rbp+37h+var_90]
0x1400368a6  mov     rdx, r15
0x1400368a9  call    MpSetProcessDocOpenRule
0x1400368ae  lea     rdi, WPP_GLOBAL_Control
0x1400368b5  test    eax, eax
0x1400368b7  js      loc_140036CBA
0x1400368bd  mov     rdx, [rbp+37h+var_90]
0x1400368c1  mov     r8, r15
0x1400368c4  mov     rcx, rbx
0x1400368c7  call    MpSetProcessPreScanFilterRoutine
0x1400368cc  mov     rcx, [rbp+37h+var_90]
0x1400368d0  xor     r9d, r9d
0x1400368d3  mov     r8b, 1
0x1400368d6  mov     rdx, r15
0x1400368d9  call    MpSetProcessExempt
0x1400368de  mov     rdx, [rbp+37h+var_90]
0x1400368e2  mov     r8, r15
0x1400368e5  mov     rcx, rbx; Process
0x1400368e8  call    MpSetProcessHardening
0x1400368ed  mov     rcx, [rbp+37h+var_90]
0x1400368f1  mov     r8, r15
0x1400368f4  mov     rdx, rbx
0x1400368f7  call    MpSetProcessHardeningExclusion
0x1400368fc  call    cs:__imp_PsGetCurrentProcessId
0x140036903  nop     dword ptr [rax+rax+00h]
0x140036908  mov     rcx, rax
0x14003690b  lea     rdx, [rbp+37h+var_50]
0x14003690f  call    GetMpUniquePidFromProcessId
0x140036914  mov     rcx, gs:188h; Thread
0x14003691d  mov     rdx, cs:MpData
0x140036924  mov     dword ptr [rbp+37h+var_B0], eax
0x140036927  mov     rbx, [rdx+0E8h]
0x14003692e  call    cs:__imp_IoThreadToProcess
0x140036935  nop     dword ptr [rax+rax+00h]
0x14003693a  cmp     rax, rbx
0x14003693d  jnz     loc_140036A72
0x140036943  xor     ebx, ebx
0x140036945  mov     rcx, [rbp+37h+var_90]
0x140036949  mov     al, [rcx+0B8h]
0x14003694f  mov     dl, al
0x140036951  shr     dl, 4
0x140036954  test    dl, dl
0x140036956  jnz     loc_140036D05
0x14003695c  mov     eax, [rcx+0F0h]
0x140036962  cmp     eax, 11h
0x140036965  jz      loc_140036D1F
0x14003696b  cmp     eax, 12h
0x14003696e  jz      loc_140036D1F
0x140036974  mov     rdx, [rbp+37h+var_A8]
0x140036978  lea     rax, [rbp+37h+var_50]
0x14003697c  cmp     dword ptr [rbp+37h+var_B0], ebx
0x14003697f  mov     r9, rsi
0x140036982  mov     [rsp+110h+var_C0], rdx
0x140036987  mov     r8, r12
0x14003698a  mov     rdx, [rbp+37h+var_A0]
0x14003698e  cmovl   rax, rbx
0x140036992  mov     [rsp+110h+var_C8], rdx
0x140036997  mov     rdx, [rbp+37h+Process]
0x14003699b  mov     [rsp+110h+var_D0], rcx
0x1400369a0  mov     cl, 1
0x1400369a2  mov     [rsp+110h+var_D8], r15
0x1400369a7  mov     [rsp+110h+var_E0], rax
0x1400369ac  mov     [rsp+110h+var_E8], r13
0x1400369b1  mov     dword ptr [rsp+110h+Timeout], r14d
0x1400369b6  call    MpSendProcessMessage
0x1400369bb  test    eax, eax
0x1400369bd  js      loc_140036D28
0x1400369c3  mov     rcx, [rbp+37h+var_90]
0x1400369c7  lea     rdx, [rbp+37h+Argument1]; Argument1
0x1400369cb  mov     qword ptr [rbp+37h+Argument1+8], r13
0x1400369cf  xor     r8d, r8d; Argument2
0x1400369d2  mov     qword ptr [rbp+37h+Argument1], rsi
0x1400369d6  mov     qword ptr [rbp+37h+var_78], r15
0x1400369da  mov     al, [rcx+34h]
0x1400369dd  shr     al, 6
0x1400369e0  and     al, 1
0x1400369e2  mov     dword ptr [rbp+37h+var_78+8], 1
0x1400369e9  mov     byte ptr [rbp+37h+var_78+0Ch], al
0x1400369ec  mov     al, [rcx+3Ch]
0x1400369ef  shr     al, 1
0x1400369f1  and     al, 1
0x1400369f3  mov     byte ptr [rbp+37h+var_78+0Dh], al
0x1400369f6  mov     eax, [rcx+3Ch]
0x1400369f9  mov     rcx, cs:MpData
0x140036a00  shr     eax, 0Ah
0x140036a03  and     al, 1
0x140036a05  mov     byte ptr [rbp+37h+var_78+0Eh], al
0x140036a08  mov     rcx, [rcx+9B8h]; CallbackObject
0x140036a0f  call    cs:__imp_ExNotifyCallback
0x140036a16  nop     dword ptr [rax+rax+00h]
0x140036a1b  mov     rcx, [rbp+37h+var_90]
0x140036a1f  test    rcx, rcx
0x140036a22  jnz     loc_140036D75
0x140036a28  mov     rcx, [rbp+37h+var_40]
0x140036a2c  xor     rcx, rsp; StackCookie
0x140036a2f  call    __security_check_cookie
0x140036a34  mov     rbx, [rsp+110h+arg_18]
0x140036a3c  add     rsp, 0E0h
0x140036a43  pop     r15
0x140036a45  pop     r14
0x140036a47  pop     r13
0x140036a49  pop     r12
0x140036a4b  pop     rdi
0x140036a4c  pop     rsi
0x140036a4d  pop     rbp
0x140036a4e  retn
0x140036a50  cmp     [rax+2Ch], dil
0x140036a54  jnz     loc_140036829
0x140036a5a  call    MpDlpInitializeEnlightenment
0x140036a5f  jmp     loc_140036829
0x140036a64  mov     rax, [rbp+37h+var_90]
0x140036a68  bts     dword ptr [rax+34h], 0Ah
0x140036a6d  jmp     loc_14003688F
0x140036a72  mov     rcx, gs:188h; Thread
0x140036a7b  mov     rdx, cs:MpData
0x140036a82  mov     rbx, [rdx+100h]
0x140036a89  call    cs:__imp_IoThreadToProcess
0x140036a90  nop     dword ptr [rax+rax+00h]
0x140036a95  cmp     rax, rbx
0x140036a98  jz      loc_140036943
0x140036a9e  xor     ebx, ebx
0x140036aa0  test    r12, r12
0x140036aa3  jz      loc_140036945
0x140036aa9  mov     rax, cs:MpData
0x140036ab0  mov     ecx, [rax+360h]
0x140036ab6  test    cl, 10h
0x140036ab9  jz      loc_140036945
0x140036abf  mov     rcx, [rbp+37h+var_90]
0x140036ac3  cmp     [rcx+78h], ebx
0x140036ac6  jnz     loc_140036949
0x140036acc  mov     rcx, r12
0x140036acf  call    MpIsNtCreateUserProcessFileObject
0x140036ad4  test    al, al
0x140036ad6  jnz     loc_140036945
0x140036adc  and     r14d, 0FFFFFFFDh
0x140036ae0  jmp     loc_140036945
0x140036ae5  mov     rcx, cs:MpProcessTable
0x140036aec  xor     r15d, r15d
0x140036aef  add     rcx, 188h; Object
0x140036af6  mov     [rsp+110h+Timeout], r15; Timeout
0x140036afb  xor     r9d, r9d; Alertable
0x140036afe  xor     r8d, r8d; WaitMode
0x140036b01  xor     edx, edx; WaitReason
0x140036b03  call    cs:__imp_KeWaitForSingleObject
0x140036b0a  nop     dword ptr [rax+rax+00h]
0x140036b0f  lea     rdx, [rbp+37h+var_90]
0x140036b13  mov     rcx, rsi
0x140036b16  call    MpGetProcessContextById
0x140036b1b  test    eax, eax
0x140036b1d  jns     short loc_140036B5D
0x140036b1f  mov     rcx, cs:WPP_GLOBAL_Control
0x140036b26  lea     rdi, WPP_GLOBAL_Control
0x140036b2d  cmp     rcx, rdi
0x140036b30  jz      loc_140036A1B
0x140036b36  mov     eax, [rcx+2Ch]
0x140036b39  test    al, 4
0x140036b3b  jz      loc_140036A1B
0x140036b41  mov     rcx, [rcx+18h]
0x140036b45  lea     edx, [r15+1Bh]
0x140036b49  mov     r9d, esi
0x140036b4c  lea     r8, WPP_8ebd71c5d5f53801838f519f7d1f4ffb_Traceguids
0x140036b53  call    WPP_SF_d
0x140036b58  jmp     loc_140036A1B
0x140036b5d  mov     rax, [rbp+37h+var_90]
0x140036b61  lock or dword ptr [rax+34h], 2000h
0x140036b69  mov     rcx, [rbp+37h+var_90]
0x140036b6d  call    MpDeleteProcessContext
0x140036b72  mov     rcx, cs:MpData
0x140036b79  lea     rdx, [rbp+37h+Argument1]; Argument1
0x140036b7d  mov     qword ptr [rbp+37h+Argument1], rsi
0x140036b81  xor     r8d, r8d; Argument2
0x140036b84  mov     qword ptr [rbp+37h+var_78], r15
0x140036b88  mov     dword ptr [rbp+37h+var_78+8], 2
0x140036b8f  mov     word ptr [rbp+37h+var_78+0Ch], r15w
0x140036b94  mov     byte ptr [rbp+37h+var_78+0Eh], r15b
0x140036b98  mov     rcx, [rcx+9B8h]; CallbackObject
0x140036b9f  call    cs:__imp_ExNotifyCallback
0x140036ba6  nop     dword ptr [rax+rax+00h]
0x140036bab  mov     rcx, [rbp+37h+var_90]
0x140036baf  test    rcx, rcx
0x140036bb2  jz      loc_140036A28
0x140036bb8  mov     eax, [rcx+34h]
0x140036bbb  test    al, 8
0x140036bbd  jnz     loc_140036A1B
0x140036bc3  mov     [rsp+110h+var_C0], r15
0x140036bc8  mov     r9, rsi
0x140036bcb  mov     [rsp+110h+var_C8], r15
0x140036bd0  mov     r8, r12
0x140036bd3  mov     [rsp+110h+var_D0], rcx
0x140036bd8  mov     rdx, rdi
0x140036bdb  mov     [rsp+110h+var_D8], r15
0x140036be0  xor     ecx, ecx
0x140036be2  mov     [rsp+110h+var_E0], r15
0x140036be7  mov     [rsp+110h+var_E8], r15
0x140036bec  mov     dword ptr [rsp+110h+Timeout], r14d
0x140036bf1  call    MpSendProcessMessage
0x140036bf6  test    eax, eax
0x140036bf8  jns     loc_140036A1B
0x140036bfe  mov     rcx, cs:WPP_GLOBAL_Control
0x140036c05  lea     rdi, WPP_GLOBAL_Control
0x140036c0c  cmp     rcx, rdi
0x140036c0f  jz      loc_140036A1B
0x140036c15  mov     ecx, [rcx+2Ch]
0x140036c18  test    cl, 1
0x140036c1b  jz      loc_140036A1B
0x140036c21  mov     edx, 1Ch
0x140036c26  lfence
0x140036c29  mov     r9, gs:188h
0x140036c32  lea     r8, WPP_8ebd71c5d5f53801838f519f7d1f4ffb_Traceguids
0x140036c39  mov     rcx, cs:WPP_GLOBAL_Control
0x140036c40  mov     dword ptr [rsp+110h+Timeout], eax
0x140036c44  mov     rcx, [rcx+18h]
0x140036c48  call    WPP_SF_qD
0x140036c4d  jmp     loc_140036A1B
0x140036c52  call    MpFixSystemProcessContextCreateTime
0x140036c57  jmp     loc_14003680F
0x140036c5c  mov     rcx, cs:WPP_GLOBAL_Control
0x140036c63  lea     rdi, WPP_GLOBAL_Control
0x140036c6a  cmp     rcx, rdi
0x140036c6d  jz      loc_140036A1B
0x140036c73  mov     ecx, [rcx+2Ch]
0x140036c76  test    cl, 1
0x140036c79  jz      loc_140036A1B
0x140036c7f  mov     edx, 18h
0x140036c84  jmp     short loc_140036C26
0x140036c86  lea     rdx, [rbp+37h+var_B0]
0x140036c8a  mov     [rbp+37h+var_B0], rdi
0x140036c8e  mov     rcx, r13
  ... truncated ...
```
