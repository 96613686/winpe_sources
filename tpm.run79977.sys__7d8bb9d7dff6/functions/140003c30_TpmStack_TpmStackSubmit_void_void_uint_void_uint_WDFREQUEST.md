# TpmStack::TpmStackSubmit(void *,void *,uint,void *,uint,WDFREQUEST__ *)

- ea: `0x140003c30`
- end: `0x14000451a`
- name: `?TpmStackSubmit@TpmStack@@QEAAJPEAX0I0IPEAUWDFREQUEST__@@@Z`
- size: `2282`
- prototype: `__int64 __fastcall(TpmStack *__hidden this, void *, void *, unsigned int, void *, unsigned int, struct WDFREQUEST__ *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140017ea0`

## callees

- `0x140003c30`
- `0x140004520`
- `0x14000463c`
- `0x1400049b4`
- `0x140009278`
- `0x14000e98c`
- `0x1400454a0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140003d3f`
- `ntoskrnl!ExAllocatePool2` at `0x140003e1b`
- `ntoskrnl!ExAllocatePool2` at `0x140003fd8`
- `ntoskrnl!ExAllocatePool2` at `0x1400040c8`
- `ntoskrnl!ExAllocatePool2` at `0x1400041b3`
- `ntoskrnl!ExAllocatePool2` at `0x140003d3f`
- `ntoskrnl!ExAllocatePool2` at `0x140003e1b`
- `ntoskrnl!ExAllocatePool2` at `0x140003fd8`
- `ntoskrnl!ExAllocatePool2` at `0x1400040c8`
- `ntoskrnl!ExAllocatePool2` at `0x1400041b3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003ea1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000405d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003ea1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000405d`
- `ntoskrnl!SeCaptureSubjectContext` at `0x140003cca`
- `ntoskrnl!SeCaptureSubjectContext` at `0x140003ee4`
- `ntoskrnl!SeCaptureSubjectContext` at `0x140003cca`
- `ntoskrnl!SeCaptureSubjectContext` at `0x140003ee4`
- `ntoskrnl!ExGetPreviousMode` at `0x140003ef0`
- `ntoskrnl!ExGetPreviousMode` at `0x140003ef0`
- `ntoskrnl!SeAccessCheck` at `0x140003f39`
- `ntoskrnl!SeAccessCheck` at `0x140003f39`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140003da0`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140003f4c`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140003da0`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140003f4c`
- `ntoskrnl!ObOpenObjectByPointer` at `0x140003d19`
- `ntoskrnl!ObOpenObjectByPointer` at `0x140003d19`
- `ntoskrnl!ZwQueryInformationToken` at `0x140003d85`
- `ntoskrnl!ZwQueryInformationToken` at `0x140003d85`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x140003dda`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x140003dda`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140003eb1`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140003eb1`
- `ntoskrnl!SeLocateProcessImageName` at `0x140003f98`
- `ntoskrnl!SeLocateProcessImageName` at `0x140003f98`
- `ntoskrnl!ZwClose` at `0x140003db6`
- `ntoskrnl!ZwClose` at `0x140003db6`
- `ntoskrnl!RtlInitUnicodeString` at `0x140003ca2`
- `ntoskrnl!RtlInitUnicodeString` at `0x140003ca2`
- `ntoskrnl!PsGetCurrentProcess` at `0x140003f7f`
- `ntoskrnl!PsGetCurrentProcess` at `0x140003f7f`

## pseudocode

```c
int __fastcall TpmStack::TpmStackSubmit(
        TpmDevice **this,
        void *a2,
        unsigned __int8 *a3,
        unsigned int a4,
        unsigned __int8 *a5,
        unsigned int a6,
        struct WDFREQUEST__ *a7)
{
  _WORD *v9; // rsi
  void *v10; // rdi
  PSID *v11; // r14
  PACCESS_TOKEN PrimaryToken; // rcx
  int v13; // ebx
  _QWORD *Pool2; // rax
  unsigned __int64 v15; // rax
  _QWORD *v16; // rax
  _WORD *v17; // r9
  PWSTR Buffer; // rdx
  __int64 Length; // rcx
  __int64 v20; // r8
  _WORD *v21; // rcx
  KPROCESSOR_MODE PreviousMode; // al
  BOOLEAN v23; // bl
  signed int v24; // ecx
  struct _KPROCESS *CurrentProcess; // rax
  unsigned __int64 v26; // rdx
  _QWORD *v27; // rax
  _WORD *v28; // r10
  unsigned __int16 *v29; // r11
  _WORD *v30; // r9
  __int64 v31; // rcx
  _WORD *v32; // rdx
  __int64 v33; // r8
  _WORD *v34; // rcx
  int v35; // r12d
  unsigned __int8 *v36; // rbx
  unsigned __int8 *v37; // rax
  __int16 v38; // si
  _QWORD *v39; // rax
  _QWORD *v40; // rdi
  void *v41; // rcx
  HANDLE v42; // xmm0_8
  unsigned __int8 *v43; // rcx
  unsigned __int8 *v44; // rax
  int result; // eax
  unsigned int v46; // ebx
  ULONG v47; // esi
  int v48; // eax
  int v49; // eax
  __int64 v50; // rcx
  HANDLE TokenHandle; // [rsp+58h] [rbp-81h] BYREF
  __int16 v52; // [rsp+60h] [rbp-79h]
  ULONG ReturnLength; // [rsp+68h] [rbp-71h] BYREF
  int v54; // [rsp+6Ch] [rbp-6Dh]
  unsigned int v55; // [rsp+70h] [rbp-69h]
  void *v56; // [rsp+78h] [rbp-61h]
  void *v57; // [rsp+80h] [rbp-59h]
  _UNICODE_STRING DestinationString; // [rsp+88h] [rbp-51h] BYREF
  unsigned __int8 *v59; // [rsp+98h] [rbp-41h]
  struct _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+A0h] [rbp-39h] BYREF
  void *v61; // [rsp+C0h] [rbp-19h]
  struct WDFREQUEST__ *v62; // [rsp+C8h] [rbp-11h]
  TpmDevice **v63; // [rsp+D0h] [rbp-9h]
  _UNKNOWN *retaddr; // [rsp+120h] [rbp+47h]

  v63 = this;
  v59 = a5;
  v55 = a4;
  v61 = a2;
  v62 = a7;
  if ( TpmTransportType::m_Version == 1 )
    return TpmDevice::Submit(*this, a2, a3, a4, a5, a6, a7);
  v9 = 0;
  v56 = 0;
  v57 = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, 0);
  ReturnLength = 0;
  TokenHandle = 0;
  memset(&SubjectContext, 0, sizeof(SubjectContext));
  v10 = 0;
  v11 = 0;
  SeCaptureSubjectContext(&SubjectContext);
  PrimaryToken = SubjectContext.PrimaryToken;
  v54 = 1;
  if ( SubjectContext.ClientToken )
    PrimaryToken = SubjectContext.ClientToken;
  if ( PrimaryToken )
  {
    v13 = ObOpenObjectByPointer(PrimaryToken, 0x200u, 0, 8u, 0, 0, &TokenHandle);
    if ( v13 >= 0 )
    {
      Pool2 = (_QWORD *)ExAllocatePool2(257, 100, 1349349460);
      v10 = Pool2;
      if ( Pool2 )
      {
        *Pool2 = retaddr;
        Pool2[1] = retaddr;
        v10 = Pool2 + 2;
      }
      if ( v10 )
      {
        v13 = ZwQueryInformationToken(TokenHandle, TokenUser, v10, 0x54u, &ReturnLength);
        if ( v13 >= 0 )
        {
          v11 = (PSID *)v10;
          v10 = 0;
        }
      }
      else
      {
        v13 = -1073741670;
      }
    }
  }
  else
  {
    v13 = -1073741790;
  }
  SeReleaseSubjectContext(&SubjectContext);
  if ( TokenHandle )
    ZwClose(TokenHandle);
  if ( v10 )
    TpmFree(v10);
  if ( v13 >= 0 )
  {
    v13 = RtlConvertSidToUnicodeString(&DestinationString, *v11, 1u);
    if ( v13 >= 0 )
    {
      v15 = 2LL * ((unsigned int)DestinationString.Length + 1);
      if ( !v15 || v15 + 16 < v15 )
        goto LABEL_19;
      v16 = (_QWORD *)ExAllocatePool2(257, v15 + 16, 1349349460);
      v9 = v16;
      if ( v16 )
      {
        *v16 = retaddr;
        v16[1] = retaddr;
        v9 = v16 + 2;
      }
      if ( v9 )
      {
        v17 = v9;
        Buffer = DestinationString.Buffer;
        Length = DestinationString.Length;
        v20 = (unsigned int)DestinationString.Length + 1;
        do
        {
          if ( !Length )
            break;
          if ( !*Buffer )
            break;
          *v17++ = *Buffer++;
          --Length;
          --v20;
        }
        while ( v20 );
        v21 = v17 - 1;
        v13 = -2147483643;
        if ( v20 )
        {
          v21 = v17;
          v13 = 0;
        }
        *v21 = 0;
        if ( v20 )
        {
          v56 = v9;
          v13 = 0;
          v9 = 0;
        }
      }
      else
      {
LABEL_19:
        v13 = -1073741670;
      }
    }
  }
  if ( v11 )
    ExFreePoolWithTag(v11 - 2, 0x506D7054u);
  RtlFreeUnicodeString(&DestinationString);
  if ( v9 )
    TpmFree(v9);
  if ( v13 < 0 )
    goto LABEL_85;
  ReturnLength = 0;
  LODWORD(TokenHandle) = 0;
  memset(&SubjectContext, 0, sizeof(SubjectContext));
  SeCaptureSubjectContext(&SubjectContext);
  PreviousMode = ExGetPreviousMode();
  v23 = SeAccessCheck(
          qword_14003B9F0,
          &SubjectContext,
          0,
          1u,
          0,
          0,
          &GenericMapping,
          PreviousMode,
          (PACCESS_MASK)&TokenHandle,
          (PNTSTATUS)&ReturnLength);
  SeReleaseSubjectContext(&SubjectContext);
  v24 = ReturnLength;
  if ( !v23 && (ReturnLength == -1073741790 || (ReturnLength & 0xC0000000) != 0xC0000000) )
    v24 = -1071050748;
  if ( v24 )
  {
    if ( v24 == -1071050748 )
    {
      v48 = TpmAccessCheck(1);
      v24 = v48;
      if ( !v48 )
        goto LABEL_41;
      if ( v48 == -1071050748 )
      {
        v54 = 3;
        v49 = TpmAccessCheck(3);
        v24 = v49;
        if ( !v49 )
          goto LABEL_41;
        if ( v49 >= 0 )
LABEL_96:
          v24 = -1073741823;
      }
      else
      {
        v54 = 0;
        if ( v48 >= 0 )
          goto LABEL_41;
      }
LABEL_101:
      v13 = v24;
      goto LABEL_85;
    }
    if ( v24 < 0 )
      goto LABEL_101;
    goto LABEL_96;
  }
  v54 = 2;
LABEL_41:
  CurrentProcess = (struct _KPROCESS *)PsGetCurrentProcess();
  TokenHandle = 0;
  if ( SeLocateProcessImageName(CurrentProcess, (PUNICODE_STRING *)&TokenHandle) >= 0 )
  {
    v26 = 2LL * *(unsigned __int16 *)TokenHandle + 18;
    if ( v26 >= 2 * (unsigned __int64)*(unsigned __int16 *)TokenHandle + 2 )
    {
      v27 = (_QWORD *)ExAllocatePool2(257, v26, 1349349460);
      v28 = v27;
      if ( v27 )
      {
        v28 = v27 + 2;
        *v27 = retaddr;
        v27[1] = retaddr;
      }
      if ( v28 )
      {
        v29 = (unsigned __int16 *)TokenHandle;
        v30 = v28;
        v31 = *(unsigned __int16 *)TokenHandle;
        v32 = (_WORD *)*((_QWORD *)TokenHandle + 1);
        v33 = v31 + 1;
        do
        {
          if ( !v31 )
            break;
          if ( !*v32 )
            break;
          *v30++ = *v32++;
          --v31;
          --v33;
        }
        while ( v33 );
        v34 = v30 - 1;
        if ( v33 )
          v34 = v30;
        *v34 = 0;
        if ( v33 )
        {
          v50 = *v29;
          v57 = v28;
          v28[v50] = 0;
        }
        else
        {
          TpmFree(v28);
        }
      }
    }
  }
  if ( TokenHandle )
    ExFreePoolWithTag(TokenHandle, 0);
  if ( a4 )
  {
    v35 = 100 * *a3;
    *a3 = 0x80;
  }
  else
  {
    v35 = 0;
  }
  TokenHandle = 0;
  v52 = 0;
  if ( a4 < 0xA || a6 < 0xA )
  {
    v13 = -1073741811;
  }
  else
  {
    v36 = 0;
    if ( a3 != v59 )
      goto LABEL_65;
    if ( (unsigned __int64)a6 + 16 < a6 )
      goto LABEL_80;
    v37 = (unsigned __int8 *)ExAllocatePool2(257, a6 + 16LL, 1349349460);
    v36 = v37;
    if ( v37 )
    {
      *(_QWORD *)v37 = retaddr;
      *((_QWORD *)v37 + 1) = retaddr;
      v36 = v37 + 16;
    }
    if ( !v36 )
    {
LABEL_80:
      v13 = -1073741670;
    }
    else
    {
LABEL_65:
      LOBYTE(TokenHandle) = a3[1];
      BYTE1(TokenHandle) = *a3;
      BYTE2(TokenHandle) = a3[5];
      BYTE3(TokenHandle) = a3[4];
      BYTE4(TokenHandle) = a3[3];
      BYTE5(TokenHandle) = a3[2];
      BYTE6(TokenHandle) = a3[9];
      HIBYTE(TokenHandle) = a3[8];
      LOBYTE(v52) = a3[7];
      HIBYTE(v52) = a3[6];
      v38 = v52;
      if ( *(_DWORD *)((char *)&TokenHandle + 2) == a4 )
      {
        v39 = (_QWORD *)ExAllocatePool2(257, 304, 1349349460);
        v40 = v39;
        if ( v39 )
        {
          *v39 = retaddr;
          v39[1] = retaddr;
          v40 = v39 + 2;
        }
        if ( v40 )
        {
          v41 = v56;
          *(_DWORD *)((char *)v40 + 10) = 0;
          *((_WORD *)v40 + 7) = 0;
          v40[26] = 16;
          *((_OWORD *)v40 + 16) = 0;
          *((_DWORD *)v40 + 71) = 0;
          v42 = TokenHandle;
          v40[2] = v61;
          *((_DWORD *)v40 + 45) = v55;
          v40[27] = v62;
          *((_DWORD *)v40 + 70) = v54;
          v40[29] = v41;
          v40[30] = v57;
          v43 = v59;
          *v40 = v42;
          v44 = v43;
          v40[34] = 0;
          v40[3] = a3;
          if ( v36 )
            v44 = v36;
          v40[4] = v44;
          if ( !v36 )
            v43 = 0;
          v40[5] = 0;
          v40[21] = 0;
          *((_DWORD *)v40 + 44) = v35;
          *((_DWORD *)v40 + 46) = a6;
          *((_DWORD *)v40 + 47) = 0;
          v40[24] = 2431;
          v40[25] = 0;
          *((_WORD *)v40 + 4) = v38;
          v40[28] = 0;
          v40[31] = v43;
          *((_OWORD *)v40 + 3) = 0;
          *((_OWORD *)v40 + 4) = 0;
          *((_OWORD *)v40 + 5) = 0;
          *((_OWORD *)v40 + 6) = 0;
          *((_OWORD *)v40 + 7) = 0;
          *((_OWORD *)v40 + 8) = 0;
          *((_OWORD *)v40 + 9) = 0;
          v40[20] = 0;
          v40[34] = MEMORY[0xFFFFF78000000014];
          result = Tpm20Scheduler::SubmitRequest(v63[2], (struct Tpm20Request *)v40);
          v46 = result;
          if ( result )
          {
            Tpm20Context::CompleteTpm20Request((struct Tpm20Request *)v40, result);
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
            {
              WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_b13eeff4b5e83ce555d199d430c2416d_Traceguids, v46);
            }
            return 0;
          }
          return result;
        }
        v47 = -1073741670;
      }
      else
      {
        v47 = -1073741811;
      }
      ReturnLength = v47;
      if ( v36 )
        TpmFree(v36);
      v13 = ReturnLength;
    }
  }
LABEL_85:
  if ( v56 )
    TpmFree(v56);
  if ( v57 )
    TpmFree(v57);
  return v13;
}

```

## disassembly

```asm
0x140003c30  mov     r11, rsp
0x140003c33  push    rbp
0x140003c34  push    r13
0x140003c36  push    r15
0x140003c38  lea     rbp, [r11-47h]
0x140003c3c  sub     rsp, 100h
0x140003c43  cmp     cs:?m_Version@TpmTransportType@@0W4VERSION@1@A, 1; TpmTransportType::VERSION TpmTransportType::m_Version
0x140003c4a  mov     r10, rcx
0x140003c4d  mov     rax, [rbp+3Fh+arg_30]
0x140003c51  mov     r13, r8
0x140003c54  mov     [rbp+3Fh+var_48], rcx
0x140003c58  mov     rcx, [rbp+3Fh+arg_20]
0x140003c5c  mov     r15d, r9d
0x140003c5f  mov     [rbp+3Fh+var_80], rcx
0x140003c63  mov     [rbp+3Fh+var_A8], r15d
0x140003c67  mov     [rbp+3Fh+var_58], rdx
0x140003c6b  mov     [rbp+3Fh+var_50], rax
0x140003c6f  jz      loc_140004453
0x140003c75  mov     [r11-20h], rbx
0x140003c79  lea     rcx, [rbp+3Fh+DestinationString]; DestinationString
0x140003c7d  mov     [r11-28h], rsi
0x140003c81  xor     ebx, ebx
0x140003c83  mov     [r11-30h], rdi
0x140003c87  xorps   xmm0, xmm0
0x140003c8a  mov     [r11-38h], r12
0x140003c8e  xor     edx, edx; SourceString
0x140003c90  mov     [r11-40h], r14
0x140003c94  mov     esi, ebx
0x140003c96  mov     [rbp+3Fh+var_A0], rbx
0x140003c9a  mov     [rbp+3Fh+var_98], rbx
0x140003c9e  movups  xmmword ptr [rbp+3Fh+DestinationString.Length], xmm0
0x140003ca2  call    cs:__imp_RtlInitUnicodeString
0x140003ca9  nop     dword ptr [rax+rax+00h]
0x140003cae  xorps   xmm0, xmm0
0x140003cb1  mov     [rbp+3Fh+ReturnLength], ebx
0x140003cb4  lea     rcx, [rbp+3Fh+SubjectContext]; SubjectContext
0x140003cb8  mov     [rsp+110h+TokenHandle], rbx
0x140003cbd  movups  xmmword ptr [rbp+3Fh+SubjectContext.ClientToken], xmm0
0x140003cc1  mov     edi, ebx
0x140003cc3  mov     r14d, ebx
0x140003cc6  movups  xmmword ptr [rbp+3Fh+SubjectContext.PrimaryToken], xmm0
0x140003cca  call    cs:__imp_SeCaptureSubjectContext
0x140003cd1  nop     dword ptr [rax+rax+00h]
0x140003cd6  mov     rax, [rbp+3Fh+SubjectContext.ClientToken]
0x140003cda  mov     r12d, 1
0x140003ce0  mov     rcx, [rbp+3Fh+SubjectContext.PrimaryToken]
0x140003ce4  test    rax, rax
0x140003ce7  mov     [rbp+3Fh+var_AC], r12d
0x140003ceb  cmovnz  rcx, rax; Object
0x140003cef  test    rcx, rcx
0x140003cf2  jz      loc_140004489
0x140003cf8  lea     rax, [rsp+110h+TokenHandle]
0x140003cfd  mov     r9d, 8; DesiredAccess
0x140003d03  mov     [rsp+110h+Handle], rax; Handle
0x140003d08  xor     r8d, r8d; PassedAccessState
0x140003d0b  mov     [rsp+110h+AccessMode], bl; AccessMode
0x140003d0f  mov     edx, 200h; HandleAttributes
0x140003d14  mov     [rsp+110h+ObjectType], rbx; ObjectType
0x140003d19  call    cs:__imp_ObOpenObjectByPointer
0x140003d20  nop     dword ptr [rax+rax+00h]
0x140003d25  mov     ebx, eax
0x140003d27  test    eax, eax
0x140003d29  js      short loc_140003D9C
0x140003d2b  mov     rbx, [rbp+47h]
0x140003d2f  mov     edx, 64h ; 'd'
0x140003d34  mov     ecx, 101h
0x140003d39  mov     r8d, 506D7054h
0x140003d3f  call    cs:__imp_ExAllocatePool2
0x140003d46  nop     dword ptr [rax+rax+00h]
0x140003d4b  mov     rdi, rax
0x140003d4e  test    rax, rax
0x140003d51  jz      short loc_140003D62
0x140003d53  mov     [rax], rbx
0x140003d56  mov     rax, [rbp+47h]
0x140003d5a  mov     [rdi+8], rax
0x140003d5e  add     rdi, 10h
0x140003d62  test    rdi, rdi
0x140003d65  jz      loc_140004493
0x140003d6b  mov     rcx, [rsp+110h+TokenHandle]; TokenHandle
0x140003d70  lea     rax, [rbp+3Fh+ReturnLength]
0x140003d74  mov     r9d, 54h ; 'T'; TokenInformationLength
0x140003d7a  mov     [rsp+110h+ObjectType], rax; ReturnLength
0x140003d7f  mov     r8, rdi; TokenInformation
0x140003d82  mov     edx, r12d; TokenInformationClass
0x140003d85  call    cs:__imp_ZwQueryInformationToken
0x140003d8c  nop     dword ptr [rax+rax+00h]
0x140003d91  mov     ebx, eax
0x140003d93  test    eax, eax
0x140003d95  js      short loc_140003D9C
0x140003d97  mov     r14, rdi
0x140003d9a  xor     edi, edi
0x140003d9c  lea     rcx, [rbp+3Fh+SubjectContext]; SubjectContext
0x140003da0  call    cs:__imp_SeReleaseSubjectContext
0x140003da7  nop     dword ptr [rax+rax+00h]
0x140003dac  mov     rcx, [rsp+110h+TokenHandle]; Handle
0x140003db1  test    rcx, rcx
0x140003db4  jz      short loc_140003DC2
0x140003db6  call    cs:__imp_ZwClose
0x140003dbd  nop     dword ptr [rax+rax+00h]
0x140003dc2  test    rdi, rdi
0x140003dc5  jnz     loc_14000449D
0x140003dcb  test    ebx, ebx
0x140003dcd  js      short loc_140003E09
0x140003dcf  mov     rdx, [r14]; Sid
0x140003dd2  lea     rcx, [rbp+3Fh+DestinationString]; UnicodeString
0x140003dd6  movzx   r8d, r12b; AllocateDestinationString
0x140003dda  call    cs:__imp_RtlConvertSidToUnicodeString
0x140003de1  nop     dword ptr [rax+rax+00h]
0x140003de6  mov     ebx, eax
0x140003de8  test    eax, eax
0x140003dea  js      short loc_140003E09
0x140003dec  movzx   eax, [rbp+3Fh+DestinationString.Length]
0x140003df0  mov     rbx, [rbp+47h]
0x140003df4  inc     eax
0x140003df6  add     rax, rax
0x140003df9  jz      short loc_140003E04
0x140003dfb  lea     rdx, [rax+10h]
0x140003dff  cmp     rdx, rax
0x140003e02  jnb     short loc_140003E10
0x140003e04  mov     ebx, 0C000009Ah
0x140003e09  xor     edi, edi
0x140003e0b  jmp     loc_140003E93
0x140003e10  mov     ecx, 101h
0x140003e15  mov     r8d, 506D7054h
0x140003e1b  call    cs:__imp_ExAllocatePool2
0x140003e22  nop     dword ptr [rax+rax+00h]
0x140003e27  mov     rsi, rax
0x140003e2a  test    rax, rax
0x140003e2d  jz      short loc_140003E3E
0x140003e2f  mov     [rax], rbx
0x140003e32  mov     rax, [rbp+47h]
0x140003e36  mov     [rsi+8], rax
0x140003e3a  add     rsi, 10h
0x140003e3e  test    rsi, rsi
0x140003e41  jz      short loc_140003E04
0x140003e43  movzx   eax, [rbp+3Fh+DestinationString.Length]
0x140003e47  mov     r9, rsi
0x140003e4a  mov     rdx, [rbp+3Fh+DestinationString.Buffer]
0x140003e4e  mov     ecx, eax
0x140003e50  lea     r8d, [rax+1]
0x140003e54  test    rcx, rcx
0x140003e57  jz      short loc_140003E75
0x140003e59  movzx   eax, word ptr [rdx]
0x140003e5c  test    ax, ax
0x140003e5f  jz      short loc_140003E75
0x140003e61  mov     [r9], ax
0x140003e65  add     rdx, 2
0x140003e69  add     r9, 2
0x140003e6d  dec     rcx
0x140003e70  sub     r8, r12
0x140003e73  jnz     short loc_140003E54
0x140003e75  xor     edi, edi
0x140003e77  lea     rcx, [r9-2]
0x140003e7b  test    r8, r8
0x140003e7e  mov     ebx, 80000005h
0x140003e83  cmovnz  rcx, r9
0x140003e87  cmovnz  ebx, edi
0x140003e8a  mov     [rcx], di
0x140003e8d  jnz     loc_140004420
0x140003e93  test    r14, r14
0x140003e96  jz      short loc_140003EAD
0x140003e98  lea     rcx, [r14-10h]; P
0x140003e9c  mov     edx, 506D7054h; Tag
0x140003ea1  call    cs:__imp_ExFreePoolWithTag
0x140003ea8  nop     dword ptr [rax+rax+00h]
0x140003ead  lea     rcx, [rbp+3Fh+DestinationString]; UnicodeString
0x140003eb1  call    cs:__imp_RtlFreeUnicodeString
0x140003eb8  nop     dword ptr [rax+rax+00h]
0x140003ebd  test    rsi, rsi
0x140003ec0  jnz     loc_1400044AA
0x140003ec6  test    ebx, ebx
0x140003ec8  js      loc_140004371
0x140003ece  xorps   xmm0, xmm0
0x140003ed1  mov     [rbp+3Fh+ReturnLength], edi
0x140003ed4  lea     rcx, [rbp+3Fh+SubjectContext]; SubjectContext
0x140003ed8  mov     dword ptr [rsp+110h+TokenHandle], edi
0x140003edc  movups  xmmword ptr [rbp+3Fh+SubjectContext.ClientToken], xmm0
0x140003ee0  movups  xmmword ptr [rbp+3Fh+SubjectContext.PrimaryToken], xmm0
0x140003ee4  call    cs:__imp_SeCaptureSubjectContext
0x140003eeb  nop     dword ptr [rax+rax+00h]
0x140003ef0  call    cs:__imp_ExGetPreviousMode
0x140003ef7  nop     dword ptr [rax+rax+00h]
0x140003efc  lea     rcx, [rbp+3Fh+ReturnLength]
0x140003f00  mov     r9d, r12d; DesiredAccess
0x140003f03  mov     [rsp+110h+AccessStatus], rcx; AccessStatus
0x140003f08  lea     rdx, [rbp+3Fh+SubjectContext]; SubjectSecurityContext
0x140003f0c  lea     rcx, [rsp+110h+TokenHandle]
0x140003f11  xor     r8d, r8d; SubjectContextLocked
0x140003f14  mov     [rsp+110h+GrantedAccess], rcx; GrantedAccess
0x140003f19  lea     rcx, qword_14003B9F0; SecurityDescriptor
0x140003f20  mov     [rsp+110h+var_D8], al; AccessMode
0x140003f24  lea     rax, GenericMapping
0x140003f2b  mov     [rsp+110h+Handle], rax; GenericMapping
0x140003f30  mov     qword ptr [rsp+110h+AccessMode], rdi; Privileges
0x140003f35  mov     dword ptr [rsp+110h+ObjectType], edi; PreviouslyGrantedAccess
0x140003f39  call    cs:__imp_SeAccessCheck
0x140003f40  nop     dword ptr [rax+rax+00h]
0x140003f45  lea     rcx, [rbp+3Fh+SubjectContext]; SubjectContext
0x140003f49  movzx   ebx, al
0x140003f4c  call    cs:__imp_SeReleaseSubjectContext
0x140003f53  nop     dword ptr [rax+rax+00h]
0x140003f58  mov     ecx, [rbp+3Fh+ReturnLength]
0x140003f5b  test    bl, bl
0x140003f5d  jz      loc_14000440A
0x140003f63  test    ecx, ecx
0x140003f65  jnz     loc_1400043C3
0x140003f6b  mov     [rbp+3Fh+var_AC], 2
0x140003f72  jmp     short loc_140003F7F
0x140003f74  mov     [rbp+3Fh+var_AC], edi
0x140003f77  test    eax, eax
0x140003f79  js      loc_140004444
0x140003f7f  call    cs:__imp_PsGetCurrentProcess
0x140003f86  nop     dword ptr [rax+rax+00h]
0x140003f8b  lea     rdx, [rsp+110h+TokenHandle]; pImageFileName
0x140003f90  mov     [rsp+110h+TokenHandle], rdi
0x140003f95  mov     rcx, rax; Process
0x140003f98  call    cs:__imp_SeLocateProcessImageName
0x140003f9f  nop     dword ptr [rax+rax+00h]
0x140003fa4  test    eax, eax
0x140003fa6  js      loc_140004051
0x140003fac  mov     rax, [rsp+110h+TokenHandle]
0x140003fb1  mov     rbx, [rbp+47h]
0x140003fb5  movzx   ecx, word ptr [rax]
0x140003fb8  lea     rcx, ds:2[rcx*2]
0x140003fc0  lea     rdx, [rcx+10h]
0x140003fc4  cmp     rdx, rcx
0x140003fc7  jb      loc_140004051
0x140003fcd  mov     ecx, 101h
0x140003fd2  mov     r8d, 506D7054h
0x140003fd8  call    cs:__imp_ExAllocatePool2
0x140003fdf  nop     dword ptr [rax+rax+00h]
0x140003fe4  mov     r10, rax
0x140003fe7  test    rax, rax
0x140003fea  jz      short loc_140003FFB
0x140003fec  mov     rcx, [rbp+47h]
0x140003ff0  add     r10, 10h
0x140003ff4  mov     [rax], rbx
0x140003ff7  mov     [rax+8], rcx
0x140003ffb  test    r10, r10
0x140003ffe  jz      short loc_140004051
0x140004000  mov     r11, [rsp+110h+TokenHandle]
0x140004005  mov     r9, r10
0x140004008  movzx   ecx, word ptr [r11]
0x14000400c  mov     rdx, [r11+8]
0x140004010  lea     r8, [rcx+1]
0x140004014  test    rcx, rcx
0x140004017  jz      short loc_140004035
0x140004019  movzx   eax, word ptr [rdx]
0x14000401c  test    ax, ax
0x14000401f  jz      short loc_140004035
0x140004021  mov     [r9], ax
0x140004025  add     rdx, 2
0x140004029  add     r9, 2
0x14000402d  dec     rcx
0x140004030  sub     r8, r12
0x140004033  jnz     short loc_140004014
0x140004035  test    r8, r8
0x140004038  lea     rcx, [r9-2]
0x14000403c  cmovnz  rcx, r9
0x140004040  mov     [rcx], di
0x140004043  jnz     loc_14000442E
0x140004049  mov     rcx, r10; void *
0x14000404c  call    ?TpmFree@@YAXPEAX@Z; TpmFree(void *)
0x140004051  mov     rcx, [rsp+110h+TokenHandle]; P
0x140004056  test    rcx, rcx
0x140004059  jz      short loc_140004069
0x14000405b  xor     edx, edx; Tag
0x14000405d  call    cs:__imp_ExFreePoolWithTag
0x140004064  nop     dword ptr [rax+rax+00h]
0x140004069  test    r15d, r15d
0x14000406c  jz      loc_1400044CE
0x140004072  movzx   eax, byte ptr [r13+0]
0x140004077  imul    r12d, eax, 64h ; 'd'
0x14000407b  mov     byte ptr [r13+0], 80h
0x140004080  xor     esi, esi
0x140004082  mov     [rsp+110h+TokenHandle], rsi
0x140004087  mov     [rbp+3Fh+var_B8], si
0x14000408b  cmp     r15d, 0Ah
0x14000408f  jb      loc_1400044FC
0x140004095  mov     r14d, [rbp+3Fh+arg_28]
0x140004099  cmp     r14d, 0Ah
0x14000409d  jb      loc_1400044FC
0x1400040a3  mov     rbx, rdi
0x1400040a6  cmp     r13, [rbp+3Fh+var_80]
0x1400040aa  jnz     short loc_1400040F6
0x1400040ac  mov     rdi, [rbp+47h]
0x1400040b0  lea     rdx, [r14+10h]
0x1400040b4  cmp     rdx, r14
0x1400040b7  jb      loc_14000434E
0x1400040bd  mov     ecx, 101h
0x1400040c2  mov     r8d, 506D7054h
0x1400040c8  call    cs:__imp_ExAllocatePool2
0x1400040cf  nop     dword ptr [rax+rax+00h]
0x1400040d4  mov     rbx, rax
0x1400040d7  test    rax, rax
0x1400040da  jz      short loc_1400040EB
0x1400040dc  mov     [rax], rdi
0x1400040df  mov     rax, [rbp+47h]
0x1400040e3  mov     [rbx+8], rax
0x1400040e7  add     rbx, 10h
  ... truncated ...
```
