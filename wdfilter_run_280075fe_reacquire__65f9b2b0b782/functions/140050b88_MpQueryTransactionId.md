# MpQueryTransactionId

- ea: `0x140050b88`
- end: `0x140050ced`
- name: `MpQueryTransactionId`
- size: `357`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x14003be04`
- `0x140051160`
- `0x140055520`
- `0x1400752b0`

## callees

- `0x1400051bc`
- `0x1400118d0`
- `0x140050b88`

## import_xrefs

- `ntoskrnl!ObOpenObjectByPointer` at `0x140050bf5`
- `ntoskrnl!ObOpenObjectByPointer` at `0x140050bf5`
- `ntoskrnl!ZwQueryInformationTransaction` at `0x140050c74`
- `ntoskrnl!ZwQueryInformationTransaction` at `0x140050c74`
- `ntoskrnl!ZwClose` at `0x140050cc3`
- `ntoskrnl!ZwClose` at `0x140050cc3`

## pseudocode

```c
__int64 __fastcall MpQueryTransactionId(void *a1, _OWORD *a2)
{
  NTSTATUS v3; // ebx
  __int64 v4; // rdx
  HANDLE TransactionHandle; // [rsp+40h] [rbp-38h] BYREF
  ULONG ReturnLength; // [rsp+48h] [rbp-30h] BYREF
  __int128 TransactionInformation; // [rsp+50h] [rbp-28h] BYREF
  __int64 v9; // [rsp+60h] [rbp-18h]

  TransactionHandle = 0;
  ReturnLength = 0;
  TransactionInformation = 0;
  v9 = 0;
  if ( a1 && a2 )
  {
    v3 = ObOpenObjectByPointer(a1, 0x200u, 0, 0x80000000, 0, 0, &TransactionHandle);
    if ( v3 >= 0 )
    {
      v3 = ZwQueryInformationTransaction(
             TransactionHandle,
             TransactionBasicInformation,
             &TransactionInformation,
             0x18u,
             &ReturnLength);
      if ( v3 >= 0 )
      {
        v3 = 0;
        *a2 = TransactionInformation;
      }
      else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
             && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      {
        v4 = 11;
        goto LABEL_7;
      }
    }
    else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      v4 = 10;
LABEL_7:
      _mm_lfence();
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        v4,
        WPP_81cd47ed6b7c3e33e522c0360ded0121_Traceguids,
        KeGetCurrentThread(),
        v3);
    }
  }
  else
  {
    v3 = -1073741811;
  }
  if ( TransactionHandle )
    ZwClose(TransactionHandle);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x140050b88  mov     r11, rsp
0x140050b8b  mov     [r11+18h], rbx
0x140050b8f  push    rdi
0x140050b90  sub     rsp, 70h
0x140050b94  mov     rax, cs:__security_cookie
0x140050b9b  xor     rax, rsp
0x140050b9e  mov     [rsp+78h+var_10], rax
0x140050ba3  xor     eax, eax
0x140050ba5  mov     qword ptr [r11-38h], 0
0x140050bad  mov     [rsp+78h+var_30], eax
0x140050bb1  xorps   xmm0, xmm0
0x140050bb4  mov     rdi, rdx
0x140050bb7  movups  [rsp+78h+TransactionInformation], xmm0
0x140050bbc  mov     [r11-18h], rax
0x140050bc0  test    rcx, rcx
0x140050bc3  jz      loc_140050CB4
0x140050bc9  test    rdx, rdx
0x140050bcc  jz      loc_140050CB4
0x140050bd2  lea     rax, [r11-38h]
0x140050bd6  mov     r9d, 80000000h; DesiredAccess
0x140050bdc  mov     [r11-48h], rax
0x140050be0  xor     r8d, r8d; PassedAccessState
0x140050be3  mov     [rsp+78h+AccessMode], 0; AccessMode
0x140050be8  mov     edx, 200h; HandleAttributes
0x140050bed  mov     qword ptr [r11-58h], 0
0x140050bf5  call    cs:__imp_ObOpenObjectByPointer
0x140050bfc  nop     dword ptr [rax+rax+00h]
0x140050c01  mov     ebx, eax
0x140050c03  test    eax, eax
0x140050c05  jns     short loc_140050C58
0x140050c07  mov     rcx, cs:WPP_GLOBAL_Control
0x140050c0e  lea     rax, WPP_GLOBAL_Control
0x140050c15  cmp     rcx, rax
0x140050c18  jz      loc_140050CB9
0x140050c1e  mov     ecx, [rcx+2Ch]
0x140050c21  test    cl, 1
0x140050c24  jz      loc_140050CB9
0x140050c2a  mov     edx, 0Ah
0x140050c2f  lfence
0x140050c32  mov     r9, gs:188h
0x140050c3b  lea     r8, WPP_81cd47ed6b7c3e33e522c0360ded0121_Traceguids
0x140050c42  mov     rcx, cs:WPP_GLOBAL_Control
0x140050c49  mov     dword ptr [rsp+78h+ReturnLength], ebx
0x140050c4d  mov     rcx, [rcx+18h]
0x140050c51  call    WPP_SF_qD
0x140050c56  jmp     short loc_140050CB9
0x140050c58  mov     rcx, [rsp+78h+TransactionHandle]; TransactionHandle
0x140050c5d  lea     rax, [rsp+78h+var_30]
0x140050c62  mov     r9d, 18h; TransactionInformationLength
0x140050c68  mov     [rsp+78h+ReturnLength], rax; ReturnLength
0x140050c6d  lea     r8, [rsp+78h+TransactionInformation]; TransactionInformation
0x140050c72  xor     edx, edx; TransactionInformationClass
0x140050c74  call    cs:__imp_ZwQueryInformationTransaction
0x140050c7b  nop     dword ptr [rax+rax+00h]
0x140050c80  mov     ebx, eax
0x140050c82  test    eax, eax
0x140050c84  jns     short loc_140050CA7
0x140050c86  mov     rcx, cs:WPP_GLOBAL_Control
0x140050c8d  lea     rax, WPP_GLOBAL_Control
0x140050c94  cmp     rcx, rax
0x140050c97  jz      short loc_140050CB9
0x140050c99  mov     eax, [rcx+2Ch]
0x140050c9c  test    al, 1
0x140050c9e  jz      short loc_140050CB9
0x140050ca0  mov     edx, 0Bh
0x140050ca5  jmp     short loc_140050C2F
0x140050ca7  movups  xmm0, [rsp+78h+TransactionInformation]
0x140050cac  xor     ebx, ebx
0x140050cae  movdqu  xmmword ptr [rdi], xmm0
0x140050cb2  jmp     short loc_140050CB9
0x140050cb4  mov     ebx, 0C000000Dh
0x140050cb9  mov     rcx, [rsp+78h+TransactionHandle]; Handle
0x140050cbe  test    rcx, rcx
0x140050cc1  jz      short loc_140050CCF
0x140050cc3  call    cs:__imp_ZwClose
0x140050cca  nop     dword ptr [rax+rax+00h]
0x140050ccf  mov     eax, ebx
0x140050cd1  mov     rcx, [rsp+78h+var_10]
0x140050cd6  xor     rcx, rsp; StackCookie
0x140050cd9  call    __security_check_cookie
0x140050cde  mov     rbx, [rsp+78h+arg_10]
0x140050ce6  add     rsp, 70h
0x140050cea  pop     rdi
0x140050ceb  retn
```
