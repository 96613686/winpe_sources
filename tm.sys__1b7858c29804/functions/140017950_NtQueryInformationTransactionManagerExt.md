# NtQueryInformationTransactionManagerExt

- ea: `0x140017950`
- end: `0x140017e14`
- name: `NtQueryInformationTransactionManagerExt`
- size: `1220`
- prototype: `NTSTATUS __stdcall(HANDLE TransactionManagerHandle, TRANSACTIONMANAGER_INFORMATION_CLASS TransactionManagerInformationClass, PVOID TransactionManagerInformation, ULONG TransactionManagerInformationLength, PULONG ReturnLength)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x1400024e0`
- `0x140002510`
- `0x140002940`
- `0x14000d198`
- `0x14000d238`
- `0x14000d274`
- `0x14000d2bc`
- `0x140017950`

## import_xrefs

- `CLFS!ClfsGetLogFileInformation` at `0x140017ce8`
- `CLFS!ClfsGetLogFileInformation` at `0x140017ce8`
- `ntoskrnl!KeWaitForSingleObject` at `0x140017afa`
- `ntoskrnl!KeWaitForSingleObject` at `0x140017b6a`
- `ntoskrnl!KeWaitForSingleObject` at `0x140017afa`
- `ntoskrnl!KeWaitForSingleObject` at `0x140017b6a`
- `ntoskrnl!KeReleaseMutex` at `0x140017b3d`
- `ntoskrnl!KeReleaseMutex` at `0x140017bc4`
- `ntoskrnl!KeReleaseMutex` at `0x140017db0`
- `ntoskrnl!KeReleaseMutex` at `0x14002295d`
- `ntoskrnl!KeReleaseMutex` at `0x140017b3d`
- `ntoskrnl!KeReleaseMutex` at `0x140017bc4`
- `ntoskrnl!KeReleaseMutex` at `0x140017db0`
- `ntoskrnl!KeReleaseMutex` at `0x14002295d`
- `ntoskrnl!ObfDereferenceObject` at `0x140017dc4`
- `ntoskrnl!ObfDereferenceObject` at `0x140022976`
- `ntoskrnl!ObfDereferenceObject` at `0x140017dc4`
- `ntoskrnl!ObfDereferenceObject` at `0x140022976`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140017ac2`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140017ac2`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140017c82`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140017c82`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x140017c0e`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x140017c0e`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140017c46`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140017cbb`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140017c46`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140017cbb`
- `ntoskrnl!ExSystemExceptionFilter` at `0x14002289e`
- `ntoskrnl!ExSystemExceptionFilter` at `0x1400228d9`
- `ntoskrnl!ExSystemExceptionFilter` at `0x1400228f6`
- `ntoskrnl!ExSystemExceptionFilter` at `0x140022913`
- `ntoskrnl!ExSystemExceptionFilter` at `0x140022930`
- `ntoskrnl!ExSystemExceptionFilter` at `0x14002299a`
- `ntoskrnl!ExSystemExceptionFilter` at `0x14002289e`
- `ntoskrnl!ExSystemExceptionFilter` at `0x1400228d9`
- `ntoskrnl!ExSystemExceptionFilter` at `0x1400228f6`
- `ntoskrnl!ExSystemExceptionFilter` at `0x140022913`
- `ntoskrnl!ExSystemExceptionFilter` at `0x140022930`
- `ntoskrnl!ExSystemExceptionFilter` at `0x14002299a`
- `ntoskrnl!ProbeForWrite` at `0x140017a6e`
- `ntoskrnl!ProbeForWrite` at `0x140017a6e`
- `ntoskrnl!PsIsComponentEnabled` at `0x1400179d7`
- `ntoskrnl!PsIsComponentEnabled` at `0x1400179d7`

## pseudocode

```c
NTSTATUS __stdcall NtQueryInformationTransactionManagerExt(
        HANDLE TransactionManagerHandle,
        TRANSACTIONMANAGER_INFORMATION_CLASS TransactionManagerInformationClass,
        PVOID TransactionManagerInformation,
        ULONG TransactionManagerInformationLength,
        PULONG ReturnLength)
{
  SIZE_T v5; // rdi
  KPROCESSOR_MODE v10; // al
  unsigned int ULongFromUser; // eax
  int LogFileInformation; // edi
  char *v13; // r14
  __int32 v14; // ebx
  __int32 v15; // ebx
  __int32 v16; // ebx
  char *v17; // rcx
  __int128 v18; // xmm0
  int MaximumLength; // eax
  __int64 v20; // rbx
  char v21; // [rsp+30h] [rbp-138h]
  KPROCESSOR_MODE v22; // [rsp+31h] [rbp-137h]
  ULONG v23; // [rsp+3Ch] [rbp-12Ch]
  ULONG pcbInfoBuffer; // [rsp+48h] [rbp-120h] BYREF
  PULONG v25; // [rsp+50h] [rbp-118h]
  UNICODE_STRING StringOut; // [rsp+58h] [rbp-110h] BYREF
  PVOID Object; // [rsp+68h] [rbp-100h] BYREF
  UNICODE_STRING DestinationString; // [rsp+78h] [rbp-F0h] BYREF
  __int64 v29; // [rsp+88h] [rbp-E0h]
  __int128 v30; // [rsp+90h] [rbp-D8h]
  __int128 Src; // [rsp+A0h] [rbp-C8h] BYREF
  CLFS_INFORMATION pinfoBuffer; // [rsp+B0h] [rbp-B8h] BYREF

  v5 = TransactionManagerInformationLength;
  LODWORD(v29) = TransactionManagerInformationLength;
  v25 = ReturnLength;
  Src = 0;
  memset(&pinfoBuffer, 0, sizeof(pinfoBuffer));
  pcbInfoBuffer = 0;
  *(_QWORD *)&StringOut.Length = 0;
  StringOut.Buffer = 0;
  *(_QWORD *)&DestinationString.Length = 0;
  DestinationString.Buffer = 0;
  v23 = 0;
  if ( !(unsigned __int8)PsIsComponentEnabled(1) )
    return -1073741790;
  if ( TransactionManagerInformationClass == (TransactionManagerLogPathInformation|TransactionManagerLogInformation)
    || (unsigned int)TransactionManagerInformationClass > (TransactionManagerRecoveryInformation|TransactionManagerLogInformation) )
  {
    return -1073741821;
  }
  if ( TransactionManagerInformationClass == TransactionManagerBasicInformation && (_DWORD)v5 != 24
    || TransactionManagerInformationClass == TransactionManagerLogInformation && (_DWORD)v5 != 16
    || TransactionManagerInformationClass == TransactionManagerRecoveryInformation && (_DWORD)v5 != 8
    || TransactionManagerInformationClass == (TransactionManagerRecoveryInformation|TransactionManagerLogInformation)
    && (_DWORD)v5 != 16 )
  {
    return -1073741820;
  }
  v21 = 0;
  v10 = *((_BYTE *)KeGetCurrentThread() + 562);
  v22 = v10;
  if ( v10 )
  {
    ProbeForWrite(TransactionManagerInformation, v5, 4u);
    if ( ReturnLength )
    {
      ULongFromUser = RtlReadULongFromUser(ReturnLength);
      RtlWriteULongToUser(ReturnLength, ULongFromUser);
    }
    v10 = v22;
  }
  Object = 0;
  LogFileInformation = ObReferenceObjectByHandle(
                         TransactionManagerHandle,
                         1u,
                         (POBJECT_TYPE)TmTransactionManagerObjectType,
                         v10,
                         &Object,
                         0);
  v13 = (char *)Object;
  if ( LogFileInformation >= 0 )
  {
    KeWaitForSingleObject((char *)Object + 8, Executive, 0, 0, 0);
    v21 = 1;
    if ( TransactionManagerInformationClass )
    {
      v14 = TransactionManagerInformationClass - 1;
      if ( v14 )
      {
        v15 = v14 - 1;
        if ( v15 )
        {
          v16 = v15 - 2;
          if ( v16 )
          {
            if ( v16 == 1 )
            {
              KeReleaseMutex((PRKMUTEX)(v13 + 8), 0);
              v21 = 0;
              Object = v13 + 512;
              KeWaitForSingleObject(v13 + 512, Executive, 0, 0, 0);
              v17 = (char *)*((_QWORD *)v13 + 71);
              if ( v17 == v13 + 568 )
              {
                v18 = 0;
              }
              else
              {
                v18 = *(_OWORD *)(v17 - 312);
                v30 = v18;
              }
              *(_OWORD *)TransactionManagerInformation = v18;
              v23 = 16;
              KeReleaseMutex((PRKMUTEX)(v13 + 512), 0);
            }
          }
          else
          {
            *(_QWORD *)TransactionManagerInformation = *((_QWORD *)v13 + 83);
            v23 = 8;
          }
        }
        else
        {
          LogFileInformation = RtlDuplicateUnicodeString(0, (PCUNICODE_STRING)(v13 + 136), &StringOut);
          if ( LogFileInformation >= 0 )
          {
            v23 = StringOut.Length + 8;
            if ( (unsigned int)v29 >= (unsigned __int64)StringOut.Length + 8 )
            {
              DestinationString.Buffer = (wchar_t *)((char *)TransactionManagerInformation + 4);
              DestinationString.MaximumLength = v29 - 6;
              *(_DWORD *)TransactionManagerInformation = 0;
              RtlCopyUnicodeString(&DestinationString, &StringOut);
              MaximumLength = DestinationString.MaximumLength;
              if ( StringOut.Length < DestinationString.MaximumLength )
                MaximumLength = StringOut.Length;
              *(_DWORD *)TransactionManagerInformation = MaximumLength;
              RtlFreeUnicodeString(&StringOut);
            }
            else
            {
              RtlFreeUnicodeString(&StringOut);
              LogFileInformation = -1073741789;
            }
          }
        }
      }
      else
      {
        pcbInfoBuffer = 120;
        LogFileInformation = ClfsGetLogFileInformation(*((PLOG_FILE_OBJECT *)v13 + 19), &pinfoBuffer, &pcbInfoBuffer);
        if ( LogFileInformation >= 0 )
        {
          *(GUID *)TransactionManagerInformation = pinfoBuffer.Identity;
          v23 = 16;
        }
      }
    }
    else
    {
      Src = *((_OWORD *)v13 + 7);
      v20 = *((_QWORD *)v13 + 73);
      v29 = v20;
      if ( v22 )
        RtlCopyToUser(TransactionManagerInformation, &Src, 0x10u);
      else
        RtlCopyVolatileMemory(TransactionManagerInformation, &Src, 0x10u);
      if ( v22 )
        RtlWriteULong64ToUser((char *)TransactionManagerInformation + 16, v20);
      else
        *((_QWORD *)TransactionManagerInformation + 2) = v20;
      v23 = 24;
    }
  }
  if ( v21 )
    KeReleaseMutex((PRKMUTEX)(v13 + 8), 0);
  if ( v13 )
    ObfDereferenceObject(v13);
  if ( ReturnLength )
    *ReturnLength = v23;
  return LogFileInformation;
}

```

## disassembly

```asm
0x140017950  mov     [rsp+arg_8], rbx
0x140017955  push    rsi
0x140017956  push    rdi
0x140017957  push    r12
0x140017959  push    r14
0x14001795b  push    r15
0x14001795d  sub     rsp, 140h
0x140017964  mov     rax, cs:__security_cookie
0x14001796b  xor     rax, rsp
0x14001796e  mov     [rsp+168h+var_38], rax
0x140017976  mov     edi, r9d
0x140017979  mov     dword ptr [rsp+168h+var_E0], edi
0x140017980  mov     r15, r8
0x140017983  mov     ebx, edx
0x140017985  mov     r14, rcx
0x140017988  mov     r12, [rsp+168h+ReturnLength]
0x140017990  mov     [rsp+168h+var_118], r12
0x140017995  xorps   xmm0, xmm0
0x140017998  movups  [rsp+168h+Src], xmm0
0x1400179a0  xor     edx, edx; Val
0x1400179a2  lea     r8d, [rdx+78h]; Size
0x1400179a6  lea     rcx, [rsp+168h+pinfoBuffer]; void *
0x1400179ae  call    memset
0x1400179b3  xor     esi, esi
0x1400179b5  mov     [rsp+168h+pcbInfoBuffer], esi
0x1400179b9  mov     qword ptr [rsp+168h+StringOut.Length], rsi
0x1400179be  mov     [rsp+168h+StringOut.Buffer], rsi
0x1400179c3  mov     qword ptr [rsp+168h+DestinationString.Length], rsi
0x1400179c8  mov     [rsp+168h+DestinationString.Buffer], rsi
0x1400179d0  mov     [rsp+168h+var_12C], esi
0x1400179d4  lea     ecx, [rsi+1]
0x1400179d7  call    cs:__imp_PsIsComponentEnabled
0x1400179de  nop     dword ptr [rax+rax+00h]
0x1400179e3  test    al, al
0x1400179e5  jnz     short loc_1400179F1
0x1400179e7  mov     eax, 0C0000022h
0x1400179ec  jmp     loc_140017DEB
0x1400179f1  cmp     ebx, 3
0x1400179f4  jz      loc_140017DE6
0x1400179fa  cmp     ebx, 0FFFFFFFFh
0x1400179fd  jle     loc_140017DE6
0x140017a03  cmp     ebx, 6
0x140017a06  jge     loc_140017DE6
0x140017a0c  test    ebx, ebx
0x140017a0e  jnz     short loc_140017A15
0x140017a10  cmp     edi, 18h
0x140017a13  jnz     short loc_140017A39
0x140017a15  cmp     ebx, 1
0x140017a18  jnz     short loc_140017A1F
0x140017a1a  cmp     edi, 10h
0x140017a1d  jnz     short loc_140017A39
0x140017a1f  mov     r8d, 4; Alignment
0x140017a25  cmp     ebx, r8d
0x140017a28  jnz     short loc_140017A2F
0x140017a2a  cmp     edi, 8
0x140017a2d  jnz     short loc_140017A39
0x140017a2f  cmp     ebx, 5
0x140017a32  jnz     short loc_140017A43
0x140017a34  cmp     edi, 10h
0x140017a37  jz      short loc_140017A43
0x140017a39  mov     eax, 0C0000004h
0x140017a3e  jmp     loc_140017DEB
0x140017a43  mov     [rsp+168h+var_128], rsi
0x140017a48  mov     [rsp+168h+var_138], sil
0x140017a4d  mov     rax, gs:188h
0x140017a56  mov     al, [rax+232h]
0x140017a5c  mov     [rsp+168h+var_137], al
0x140017a60  mov     [rsp+168h+var_130], al
0x140017a64  test    al, al
0x140017a66  jz      short loc_140017A9C
0x140017a68  mov     rdx, rdi; Length
0x140017a6b  mov     rcx, r15; Address
0x140017a6e  call    cs:__imp_ProbeForWrite
0x140017a75  nop     dword ptr [rax+rax+00h]
0x140017a7a  test    r12, r12
0x140017a7d  jz      short loc_140017A91
0x140017a7f  mov     rcx, r12
0x140017a82  call    RtlReadULongFromUser
0x140017a87  mov     edx, eax
0x140017a89  mov     rcx, r12
0x140017a8c  call    RtlWriteULongToUser
0x140017a91  mov     al, [rsp+168h+var_137]
0x140017a95  jmp     short loc_140017A9C
0x140017a97  jmp     loc_140017DEB
0x140017a9c  mov     r8, cs:TmTransactionManagerObjectType; ObjectType
0x140017aa3  mov     [rsp+168h+var_100], rsi
0x140017aa8  mov     [rsp+168h+HandleInformation], rsi; HandleInformation
0x140017aad  lea     rcx, [rsp+168h+var_100]
0x140017ab2  mov     [rsp+168h+Object], rcx; Object
0x140017ab7  mov     r9b, al; AccessMode
0x140017aba  mov     edx, 1; DesiredAccess
0x140017abf  mov     rcx, r14; Handle
0x140017ac2  call    cs:__imp_ObReferenceObjectByHandle
0x140017ac9  nop     dword ptr [rax+rax+00h]
0x140017ace  mov     edi, eax
0x140017ad0  mov     r14, [rsp+168h+var_100]
0x140017ad5  mov     [rsp+168h+var_128], r14
0x140017ada  mov     [rsp+168h+var_134], eax
0x140017ade  test    eax, eax
0x140017ae0  js      loc_140017DA3
0x140017ae6  lea     rax, [r14+8]
0x140017aea  mov     [rsp+168h+Object], rsi; Timeout
0x140017aef  xor     r9d, r9d; Alertable
0x140017af2  xor     r8d, r8d; WaitMode
0x140017af5  xor     edx, edx; WaitReason
0x140017af7  mov     rcx, rax; Object
0x140017afa  call    cs:__imp_KeWaitForSingleObject
0x140017b01  nop     dword ptr [rax+rax+00h]
0x140017b06  mov     [rsp+168h+var_138], 1
0x140017b0b  test    ebx, ebx
0x140017b0d  jz      loc_140017D2D
0x140017b13  sub     ebx, 1
0x140017b16  jz      loc_140017CCC
0x140017b1c  sub     ebx, 1
0x140017b1f  jz      loc_140017C00
0x140017b25  sub     ebx, 2
0x140017b28  jz      loc_140017BD5
0x140017b2e  cmp     ebx, 1
0x140017b31  jnz     loc_140017DA3
0x140017b37  xor     edx, edx; Wait
0x140017b39  lea     rcx, [r14+8]; Mutex
0x140017b3d  call    cs:__imp_KeReleaseMutex
0x140017b44  nop     dword ptr [rax+rax+00h]
0x140017b49  mov     [rsp+168h+var_138], sil
0x140017b4e  lea     rbx, [r14+200h]
0x140017b55  mov     [rsp+168h+var_100], rbx
0x140017b5a  mov     [rsp+168h+Object], rsi; Timeout
0x140017b5f  xor     r9d, r9d; Alertable
0x140017b62  xor     r8d, r8d; WaitMode
0x140017b65  xor     edx, edx; WaitReason
0x140017b67  mov     rcx, rbx; Object
0x140017b6a  call    cs:__imp_KeWaitForSingleObject
0x140017b71  nop     dword ptr [rax+rax+00h]
0x140017b76  lea     rax, [r14+238h]
0x140017b7d  mov     rcx, [rax]
0x140017b80  cmp     rcx, rax
0x140017b83  jz      short loc_140017B96
0x140017b85  movups  xmm0, xmmword ptr [rcx-138h]
0x140017b8c  movups  [rsp+168h+var_D8], xmm0
0x140017b94  jmp     short loc_140017B99
0x140017b96  xorps   xmm0, xmm0
0x140017b99  movdqu  xmmword ptr [r15], xmm0
0x140017b9e  mov     [rsp+168h+var_12C], 10h
0x140017ba6  jmp     short loc_140017BBF
0x140017ba8  mov     edi, eax
0x140017baa  mov     [rsp+168h+var_134], eax
0x140017bae  xor     esi, esi
0x140017bb0  mov     r14, [rsp+168h+var_128]
0x140017bb5  mov     r12, [rsp+168h+var_118]
0x140017bba  mov     rbx, [rsp+168h+var_100]
0x140017bbf  xor     edx, edx; Wait
0x140017bc1  mov     rcx, rbx; Mutex
0x140017bc4  call    cs:__imp_KeReleaseMutex
0x140017bcb  nop     dword ptr [rax+rax+00h]
0x140017bd0  jmp     loc_140017DA3
0x140017bd5  mov     rax, [r14+298h]
0x140017bdc  mov     [r15], rax
0x140017bdf  mov     [rsp+168h+var_12C], 8
0x140017be7  jmp     short loc_140017BFB
0x140017be9  mov     edi, eax
0x140017beb  mov     [rsp+168h+var_134], eax
0x140017bef  xor     esi, esi
0x140017bf1  mov     r14, [rsp+168h+var_128]
0x140017bf6  mov     r12, [rsp+168h+var_118]
0x140017bfb  jmp     loc_140017DA3
0x140017c00  lea     rdx, [r14+88h]; StringIn
0x140017c07  lea     r8, [rsp+168h+StringOut]; StringOut
0x140017c0c  xor     ecx, ecx; Flags
0x140017c0e  call    cs:__imp_RtlDuplicateUnicodeString
0x140017c15  nop     dword ptr [rax+rax+00h]
0x140017c1a  mov     edi, eax
0x140017c1c  mov     [rsp+168h+var_134], eax
0x140017c20  test    eax, eax
0x140017c22  js      loc_140017DA3
0x140017c28  movzx   ecx, [rsp+168h+StringOut.Length]
0x140017c2d  add     rcx, 8
0x140017c31  mov     [rsp+168h+var_12C], ecx
0x140017c35  mov     edx, dword ptr [rsp+168h+var_E0]
0x140017c3c  cmp     rdx, rcx
0x140017c3f  jnb     short loc_140017C60
0x140017c41  lea     rcx, [rsp+168h+StringOut]; UnicodeString
0x140017c46  call    cs:__imp_RtlFreeUnicodeString
0x140017c4d  nop     dword ptr [rax+rax+00h]
0x140017c52  mov     edi, 0C0000023h
0x140017c57  mov     [rsp+168h+var_134], edi
0x140017c5b  jmp     loc_140017DA3
0x140017c60  lea     rax, [r15+4]
0x140017c64  mov     [rsp+168h+DestinationString.Buffer], rax
0x140017c6c  sub     dx, 6
0x140017c70  mov     [rsp+168h+DestinationString.MaximumLength], dx
0x140017c75  mov     [r15], esi
0x140017c78  lea     rdx, [rsp+168h+StringOut]; SourceString
0x140017c7d  lea     rcx, [rsp+168h+DestinationString]; DestinationString
0x140017c82  call    cs:__imp_RtlCopyUnicodeString
0x140017c89  nop     dword ptr [rax+rax+00h]
0x140017c8e  movzx   eax, [rsp+168h+DestinationString.MaximumLength]
0x140017c93  cmp     [rsp+168h+StringOut.Length], ax
0x140017c98  jnb     short loc_140017C9F
0x140017c9a  movzx   eax, [rsp+168h+StringOut.Length]
0x140017c9f  mov     [r15], eax
0x140017ca2  jmp     short loc_140017CB6
0x140017ca4  mov     edi, eax
0x140017ca6  mov     [rsp+168h+var_134], eax
0x140017caa  xor     esi, esi
0x140017cac  mov     r14, [rsp+168h+var_128]
0x140017cb1  mov     r12, [rsp+168h+var_118]
0x140017cb6  lea     rcx, [rsp+168h+StringOut]; UnicodeString
0x140017cbb  call    cs:__imp_RtlFreeUnicodeString
0x140017cc2  nop     dword ptr [rax+rax+00h]
0x140017cc7  jmp     loc_140017DA3
0x140017ccc  mov     [rsp+168h+pcbInfoBuffer], 78h ; 'x'
0x140017cd4  lea     r8, [rsp+168h+pcbInfoBuffer]; pcbInfoBuffer
0x140017cd9  lea     rdx, [rsp+168h+pinfoBuffer]; pinfoBuffer
0x140017ce1  mov     rcx, [r14+98h]; plfoLog
0x140017ce8  call    cs:__imp_ClfsGetLogFileInformation
0x140017cef  nop     dword ptr [rax+rax+00h]
0x140017cf4  mov     edi, eax
0x140017cf6  mov     [rsp+168h+var_134], eax
0x140017cfa  test    eax, eax
0x140017cfc  js      loc_140017DA3
0x140017d02  movups  xmm0, xmmword ptr [rsp+168h+pinfoBuffer.Identity.Data1]
0x140017d0a  movdqu  xmmword ptr [r15], xmm0
0x140017d0f  mov     [rsp+168h+var_12C], 10h
0x140017d17  jmp     short loc_140017D2B
0x140017d19  mov     edi, eax
0x140017d1b  mov     [rsp+168h+var_134], eax
0x140017d1f  xor     esi, esi
0x140017d21  mov     r14, [rsp+168h+var_128]
0x140017d26  mov     r12, [rsp+168h+var_118]
0x140017d2b  jmp     short loc_140017DA3
0x140017d2d  movups  xmm0, xmmword ptr [r14+70h]
0x140017d32  movdqu  [rsp+168h+Src], xmm0
0x140017d3b  mov     rbx, [r14+248h]
0x140017d42  mov     [rsp+168h+var_E0], rbx
0x140017d4a  mov     r8d, 10h; Size
0x140017d50  lea     rdx, [rsp+168h+Src]; Src
0x140017d58  mov     rcx, r15; void *
0x140017d5b  cmp     [rsp+168h+var_137], sil
0x140017d60  jz      short loc_140017D69
0x140017d62  call    RtlCopyToUser
0x140017d67  jmp     short loc_140017D6E
0x140017d69  call    RtlCopyVolatileMemory
0x140017d6e  cmp     [rsp+168h+var_137], sil
0x140017d73  jz      short loc_140017D83
0x140017d75  mov     rdx, rbx
0x140017d78  lea     rcx, [r15+10h]
0x140017d7c  call    RtlWriteULong64ToUser
0x140017d81  jmp     short loc_140017D87
0x140017d83  mov     [r15+10h], rbx
0x140017d87  mov     [rsp+168h+var_12C], 18h
0x140017d8f  jmp     short loc_140017DA3
0x140017d91  mov     edi, eax
0x140017d93  mov     [rsp+168h+var_134], eax
0x140017d97  xor     esi, esi
0x140017d99  mov     r14, [rsp+168h+var_128]
0x140017d9e  mov     r12, [rsp+168h+var_118]
0x140017da3  cmp     [rsp+168h+var_138], sil
0x140017da8  jz      short loc_140017DBC
0x140017daa  lea     rcx, [r14+8]; Mutex
0x140017dae  xor     edx, edx; Wait
0x140017db0  call    cs:__imp_KeReleaseMutex
0x140017db7  nop     dword ptr [rax+rax+00h]
0x140017dbc  test    r14, r14
0x140017dbf  jz      short loc_140017DD1
0x140017dc1  mov     rcx, r14; Object
0x140017dc4  call    cs:__imp_ObfDereferenceObject
0x140017dcb  nop     dword ptr [rax+rax+00h]
0x140017dd0  nop
0x140017dd1  test    r12, r12
0x140017dd4  jz      short loc_140017DDE
0x140017dd6  mov     eax, [rsp+168h+var_12C]
0x140017dda  mov     [r12], eax
0x140017dde  jmp     short loc_140017DE2
0x140017de0  mov     edi, eax
0x140017de2  mov     eax, edi
0x140017de4  jmp     short loc_140017DEB
0x140017de6  mov     eax, 0C0000003h
0x140017deb  mov     rcx, [rsp+168h+var_38]
0x140017df3  xor     rcx, rsp; StackCookie
0x140017df6  call    __security_check_cookie
0x140017dfb  mov     rbx, [rsp+168h+arg_8]
0x140017e03  add     rsp, 140h
0x140017e0a  pop     r15
0x140017e0c  pop     r14
0x140017e0e  pop     r12
0x140017e10  pop     rdi
0x140017e11  pop     rsi
0x140017e12  retn
0x140022895  push    rbp
0x140022897  sub     rsp, 30h
0x14002289b  mov     rbp, rdx
0x14002289e  call    cs:__imp_ExSystemExceptionFilter
0x1400228a5  nop     dword ptr [rax+rax+00h]
0x1400228aa  nop
0x1400228ab  add     rsp, 30h
0x1400228af  pop     rbp
0x1400228b0  retn
0x1400228b2  push    rbp
0x1400228b4  sub     rsp, 30h
0x1400228b8  mov     rbp, rdx
  ... truncated ...
```
