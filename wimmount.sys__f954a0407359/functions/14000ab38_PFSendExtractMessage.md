# PFSendExtractMessage

- ea: `0x14000ab38`
- end: `0x14000ae4e`
- name: `PFSendExtractMessage`
- size: `790`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140009aa0`

## callees

- `0x140002050`
- `0x140002bb0`
- `0x140002d00`
- `0x14000ab38`

## import_xrefs

- `ntoskrnl!PsProcessType` at `0x14000ad41`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x14000adb8`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x14000adb8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000adee`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000adee`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000aba5`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000aba5`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14000ad69`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14000ad69`
- `ntoskrnl!ObfDereferenceObject` at `0x14000adda`
- `ntoskrnl!ObfDereferenceObject` at `0x14000ae03`
- `ntoskrnl!ObfDereferenceObject` at `0x14000ae18`
- `ntoskrnl!ObfDereferenceObject` at `0x14000adda`
- `ntoskrnl!ObfDereferenceObject` at `0x14000ae03`
- `ntoskrnl!ObfDereferenceObject` at `0x14000ae18`
- `ntoskrnl!ZwDuplicateObject` at `0x14000abe2`
- `ntoskrnl!ZwDuplicateObject` at `0x14000abe2`
- `FLTMGR!FltSendMessage` at `0x14000ad17`
- `FLTMGR!FltSendMessage` at `0x14000ad17`
- `FLTMGR!FltClose` at `0x14000abfb`
- `FLTMGR!FltClose` at `0x14000abfb`

## pseudocode

```c
__int64 __fastcall PFSendExtractMessage(HANDLE *a1, __int64 a2, __int64 a3, const void *a4, unsigned int Size)
{
  _DWORD *PoolWithTag; // rdi
  NTSTATUS v9; // ebx
  char v10; // r14
  void *v11; // rcx
  ULONG ReplyLength; // [rsp+40h] [rbp-51h] BYREF
  void *TargetHandle; // [rsp+48h] [rbp-49h] BYREF
  PVOID Object; // [rsp+50h] [rbp-41h] BYREF
  PVOID v16; // [rsp+58h] [rbp-39h] BYREF
  PVOID v17; // [rsp+60h] [rbp-31h] BYREF
  void *v18; // [rsp+68h] [rbp-29h] BYREF
  void *v19; // [rsp+70h] [rbp-21h] BYREF
  __int128 ReplyBuffer; // [rsp+78h] [rbp-19h] BYREF
  int v21; // [rsp+88h] [rbp-9h]
  PVOID v22[3]; // [rsp+90h] [rbp-1h] BYREF

  ReplyLength = 20;
  v21 = 0;
  TargetHandle = 0;
  v18 = 0;
  v19 = 0;
  v16 = 0;
  v17 = 0;
  ReplyBuffer = 0;
  PoolWithTag = ExAllocatePoolWithTag(PagedPool, Size + 56LL, 0x574D6D67u);
  if ( !PoolWithTag )
  {
    v9 = -1073741670;
    goto LABEL_19;
  }
  v9 = ZwDuplicateObject((HANDLE)0xFFFFFFFFFFFFFFFFLL, *a1, *(HANDLE *)(a3 + 48), &TargetHandle, 0, 0, 6u);
  if ( v9 >= 0 )
  {
    FltClose(*a1);
    *a1 = 0;
    *PoolWithTag = 1111638594;
    if ( *(_WORD *)(a3 + 60) <= 3u && (*(_WORD *)(a3 + 60) != 3 || !*(_WORD *)(a3 + 62)) )
    {
      PoolWithTag[1] = 3;
      PoolWithTag[3] = 0;
      PoolWithTag[6] = Size;
      PoolWithTag[2] = Size + 32;
      v10 = 0;
      memmove(PoolWithTag + 7, a4, Size);
      *((_QWORD *)PoolWithTag + 2) = TargetHandle;
LABEL_11:
      v9 = FltSendMessage(
             gFilterHandle,
             (PFLT_PORT *)(a3 + 40),
             PoolWithTag,
             PoolWithTag[2],
             &ReplyBuffer,
             &ReplyLength,
             0);
      if ( v9 >= 0 )
      {
        v9 = HIDWORD(ReplyBuffer);
        if ( ReplyBuffer >= 0 )
        {
          if ( v10 )
          {
            v11 = *(void **)(a3 + 48);
            Object = 0;
            v9 = ObReferenceObjectByHandle(v11, 0xF0000u, (POBJECT_TYPE)PsProcessType, 0, &Object, 0);
            if ( v9 >= 0 )
            {
              v22[0] = v17;
              v22[1] = v16;
              v22[2] = Object;
              v9 = KeWaitForMultipleObjects(3u, v22, WaitAny, UserRequest, 0, 1u, 0, 0) != 1 ? 0xC0000267 : 0;
            }
            if ( Object )
              ObfDereferenceObject(Object);
          }
        }
      }
      goto LABEL_18;
    }
    *((_WORD *)PoolWithTag + 2) = 3;
    *((_WORD *)PoolWithTag + 3) = 1;
    PoolWithTag[3] = 4;
    PoolWithTag[2] = Size + 48;
    PoolWithTag[10] = Size;
    memmove(PoolWithTag + 11, a4, Size);
    *((_QWORD *)PoolWithTag + 2) = TargetHandle;
    v9 = DuplicateEventIntoProcess(*(HANDLE *)(a3 + 48), &v18, &v16);
    if ( v9 >= 0 )
    {
      v9 = DuplicateEventIntoProcess(*(HANDLE *)(a3 + 48), &v19, &v17);
      if ( v9 >= 0 )
      {
        *((_QWORD *)PoolWithTag + 3) = v18;
        v10 = 1;
        *((_QWORD *)PoolWithTag + 4) = v19;
        goto LABEL_11;
      }
    }
  }
LABEL_18:
  ExFreePoolWithTag(PoolWithTag, 0x574D6D67u);
LABEL_19:
  if ( v16 )
    ObfDereferenceObject(v16);
  if ( v17 )
    ObfDereferenceObject(v17);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x14000ab38  mov     [rsp-8+arg_8], rbx
0x14000ab3d  push    rbp
0x14000ab3e  push    rsi
0x14000ab3f  push    rdi
0x14000ab40  push    r12
0x14000ab42  push    r13
0x14000ab44  push    r14
0x14000ab46  push    r15
0x14000ab48  lea     rbp, [rsp-1Fh]
0x14000ab4d  sub     rsp, 0B0h
0x14000ab54  mov     rax, cs:__security_cookie
0x14000ab5b  xor     rax, rsp
0x14000ab5e  mov     [rbp+4Fh+var_38], rax
0x14000ab62  mov     r15d, dword ptr [rbp+4Fh+Size]
0x14000ab66  xor     ebx, ebx
0x14000ab68  xor     eax, eax
0x14000ab6a  mov     [rbp+4Fh+ReplyLength], 14h
0x14000ab71  mov     rsi, r8
0x14000ab74  mov     [rbp+4Fh+var_58], eax
0x14000ab77  mov     r14, rcx
0x14000ab7a  mov     [rbp+4Fh+TargetHandle], rbx
0x14000ab7e  xorps   xmm0, xmm0
0x14000ab81  mov     [rbp+4Fh+var_78], rbx
0x14000ab85  lea     rdx, [r15+38h]; NumberOfBytes
0x14000ab89  mov     [rbp+4Fh+var_70], rbx
0x14000ab8d  lea     ecx, [rax+1]; PoolType
0x14000ab90  mov     [rbp+4Fh+var_88], rbx
0x14000ab94  mov     r8d, 574D6D67h; Tag
0x14000ab9a  mov     [rbp+4Fh+var_80], rbx
0x14000ab9e  mov     r12, r9
0x14000aba1  movups  [rbp+4Fh+ReplyBuffer], xmm0
0x14000aba5  call    cs:__imp_ExAllocatePoolWithTag
0x14000abac  nop     dword ptr [rax+rax+00h]
0x14000abb1  mov     rdi, rax
0x14000abb4  test    rax, rax
0x14000abb7  jnz     short loc_14000ABC3
0x14000abb9  mov     ebx, 0C000009Ah
0x14000abbe  jmp     loc_14000ADFA
0x14000abc3  mov     r8, [rsi+30h]; TargetProcessHandle
0x14000abc7  lea     r9, [rbp+4Fh+TargetHandle]; TargetHandle
0x14000abcb  mov     rdx, [r14]; SourceHandle
0x14000abce  or      rcx, 0FFFFFFFFFFFFFFFFh; SourceProcessHandle
0x14000abd2  mov     [rsp+0E0h+Options], 6; Options
0x14000abda  mov     [rsp+0E0h+HandleAttributes], ebx; HandleAttributes
0x14000abde  mov     [rsp+0E0h+DesiredAccess], ebx; DesiredAccess
0x14000abe2  call    cs:__imp_ZwDuplicateObject
0x14000abe9  nop     dword ptr [rax+rax+00h]
0x14000abee  mov     ebx, eax
0x14000abf0  test    eax, eax
0x14000abf2  js      loc_14000ADE6
0x14000abf8  mov     rcx, [r14]; FileHandle
0x14000abfb  call    cs:__imp_FltClose
0x14000ac02  nop     dword ptr [rax+rax+00h]
0x14000ac07  mov     qword ptr [r14], 0
0x14000ac0e  mov     ecx, 3
0x14000ac13  mov     dword ptr [rdi], 42424242h
0x14000ac19  cmp     [rsi+3Ch], cx
0x14000ac1d  ja      short loc_14000AC68
0x14000ac1f  jnz     short loc_14000AC2A
0x14000ac21  lea     eax, [rcx-2]
0x14000ac24  cmp     [rsi+3Eh], ax
0x14000ac28  jnb     short loc_14000AC6D
0x14000ac2a  mov     [rdi+4], cx
0x14000ac2e  xor     eax, eax
0x14000ac30  mov     [rdi+6], ax
0x14000ac34  lea     rcx, [rdi+1Ch]; void *
0x14000ac38  mov     [rdi+0Ch], eax
0x14000ac3b  mov     r8, r15; Size
0x14000ac3e  lea     eax, [r15+20h]
0x14000ac42  mov     [rdi+18h], r15d
0x14000ac46  mov     rdx, r12; Src
0x14000ac49  mov     [rdi+8], eax
0x14000ac4c  xor     r14b, r14b
0x14000ac4f  call    memmove
0x14000ac54  mov     rax, [rbp+4Fh+TargetHandle]
0x14000ac58  xor     r15d, r15d
0x14000ac5b  mov     [rdi+10h], rax
0x14000ac5f  lea     r12d, [r15+1]
0x14000ac63  jmp     loc_14000ACEE
0x14000ac68  mov     eax, 1
0x14000ac6d  mov     [rdi+4], cx
0x14000ac71  mov     r8, r15; Size
0x14000ac74  mov     [rdi+6], ax
0x14000ac78  lea     rcx, [rdi+2Ch]; void *
0x14000ac7c  lea     eax, [r15+30h]
0x14000ac80  mov     dword ptr [rdi+0Ch], 4
0x14000ac87  mov     rdx, r12; Src
0x14000ac8a  mov     [rdi+8], eax
0x14000ac8d  mov     [rdi+28h], r15d
0x14000ac91  call    memmove
0x14000ac96  mov     rax, [rbp+4Fh+TargetHandle]
0x14000ac9a  lea     r8, [rbp+4Fh+var_88]; Object
0x14000ac9e  mov     [rdi+10h], rax
0x14000aca2  lea     rdx, [rbp+4Fh+var_78]; TargetHandle
0x14000aca6  mov     rcx, [rsi+30h]; TargetProcessHandle
0x14000acaa  call    DuplicateEventIntoProcess
0x14000acaf  xor     r15d, r15d
0x14000acb2  mov     ebx, eax
0x14000acb4  test    eax, eax
0x14000acb6  js      loc_14000ADE6
0x14000acbc  mov     rcx, [rsi+30h]; TargetProcessHandle
0x14000acc0  lea     r8, [rbp+4Fh+var_80]; Object
0x14000acc4  lea     rdx, [rbp+4Fh+var_70]; TargetHandle
0x14000acc8  call    DuplicateEventIntoProcess
0x14000accd  mov     ebx, eax
0x14000accf  test    eax, eax
0x14000acd1  js      loc_14000ADE6
0x14000acd7  mov     rax, [rbp+4Fh+var_78]
0x14000acdb  lea     r12d, [r15+1]
0x14000acdf  mov     [rdi+18h], rax
0x14000ace3  mov     r14b, r12b
0x14000ace6  mov     rax, [rbp+4Fh+var_70]
0x14000acea  mov     [rdi+20h], rax
0x14000acee  mov     r9d, [rdi+8]; SenderBufferLength
0x14000acf2  lea     rax, [rbp+4Fh+ReplyLength]
0x14000acf6  mov     rcx, cs:gFilterHandle; Filter
0x14000acfd  lea     rdx, [rsi+28h]; ClientPort
0x14000ad01  mov     qword ptr [rsp+0E0h+Options], r15; Timeout
0x14000ad06  mov     r8, rdi; SenderBuffer
0x14000ad09  mov     qword ptr [rsp+0E0h+HandleAttributes], rax; ReplyLength
0x14000ad0e  lea     rax, [rbp+4Fh+ReplyBuffer]
0x14000ad12  mov     qword ptr [rsp+0E0h+DesiredAccess], rax; ReplyBuffer
0x14000ad17  call    cs:__imp_FltSendMessage
0x14000ad1e  nop     dword ptr [rax+rax+00h]
0x14000ad23  mov     ebx, eax
0x14000ad25  test    eax, eax
0x14000ad27  js      loc_14000ADE6
0x14000ad2d  mov     ebx, dword ptr [rbp+4Fh+ReplyBuffer+0Ch]
0x14000ad30  test    ebx, ebx
0x14000ad32  js      loc_14000ADE6
0x14000ad38  test    r14b, r14b
0x14000ad3b  jz      loc_14000ADE6
0x14000ad41  mov     r8, cs:__imp_PsProcessType
0x14000ad48  lea     rax, [rbp+4Fh+Object]
0x14000ad4c  mov     rcx, [rsi+30h]; Handle
0x14000ad50  xor     r9d, r9d; AccessMode
0x14000ad53  mov     qword ptr [rsp+0E0h+HandleAttributes], r15; HandleInformation
0x14000ad58  mov     edx, 0F0000h; DesiredAccess
0x14000ad5d  mov     [rbp+4Fh+Object], r15
0x14000ad61  mov     r8, [r8]; ObjectType
0x14000ad64  mov     qword ptr [rsp+0E0h+DesiredAccess], rax; Object
0x14000ad69  call    cs:__imp_ObReferenceObjectByHandle
0x14000ad70  nop     dword ptr [rax+rax+00h]
0x14000ad75  mov     ebx, eax
0x14000ad77  test    eax, eax
0x14000ad79  js      short loc_14000ADD1
0x14000ad7b  mov     rax, [rbp+4Fh+var_80]
0x14000ad7f  lea     rdx, [rbp+4Fh+var_50]; Object
0x14000ad83  mov     [rbp+4Fh+var_50], rax
0x14000ad87  mov     r9d, 6; WaitReason
0x14000ad8d  mov     rax, [rbp+4Fh+var_88]
0x14000ad91  mov     r8d, r12d; WaitType
0x14000ad94  mov     [rsp+0E0h+WaitBlockArray], r15; WaitBlockArray
0x14000ad99  mov     [rbp+4Fh+var_48], rax
0x14000ad9d  mov     rax, [rbp+4Fh+Object]
0x14000ada1  lea     ecx, [r9-3]; Count
0x14000ada5  mov     qword ptr [rsp+0E0h+Options], r15; Timeout
0x14000adaa  mov     byte ptr [rsp+0E0h+HandleAttributes], r12b; Alertable
0x14000adaf  mov     [rbp+4Fh+var_40], rax
0x14000adb3  mov     byte ptr [rsp+0E0h+DesiredAccess], r15b; WaitMode
0x14000adb8  call    cs:__imp_KeWaitForMultipleObjects
0x14000adbf  nop     dword ptr [rax+rax+00h]
0x14000adc4  sub     eax, r12d
0x14000adc7  neg     eax
0x14000adc9  sbb     ebx, ebx
0x14000adcb  and     ebx, 0C0000267h
0x14000add1  mov     rcx, [rbp+4Fh+Object]; Object
0x14000add5  test    rcx, rcx
0x14000add8  jz      short loc_14000ADE6
0x14000adda  call    cs:__imp_ObfDereferenceObject
0x14000ade1  nop     dword ptr [rax+rax+00h]
0x14000ade6  mov     edx, 574D6D67h; Tag
0x14000adeb  mov     rcx, rdi; P
0x14000adee  call    cs:__imp_ExFreePoolWithTag
0x14000adf5  nop     dword ptr [rax+rax+00h]
0x14000adfa  mov     rcx, [rbp+4Fh+var_88]; Object
0x14000adfe  test    rcx, rcx
0x14000ae01  jz      short loc_14000AE0F
0x14000ae03  call    cs:__imp_ObfDereferenceObject
0x14000ae0a  nop     dword ptr [rax+rax+00h]
0x14000ae0f  mov     rcx, [rbp+4Fh+var_80]; Object
0x14000ae13  test    rcx, rcx
0x14000ae16  jz      short loc_14000AE24
0x14000ae18  call    cs:__imp_ObfDereferenceObject
0x14000ae1f  nop     dword ptr [rax+rax+00h]
0x14000ae24  mov     eax, ebx
0x14000ae26  mov     rcx, [rbp+4Fh+var_38]
0x14000ae2a  xor     rcx, rsp; StackCookie
0x14000ae2d  call    __security_check_cookie
0x14000ae32  mov     rbx, [rsp+0E0h+arg_8]
0x14000ae3a  add     rsp, 0B0h
0x14000ae41  pop     r15
0x14000ae43  pop     r14
0x14000ae45  pop     r13
0x14000ae47  pop     r12
0x14000ae49  pop     rdi
0x14000ae4a  pop     rsi
0x14000ae4b  pop     rbp
0x14000ae4c  retn
```
