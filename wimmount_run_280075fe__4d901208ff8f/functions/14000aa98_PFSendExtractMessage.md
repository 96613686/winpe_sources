# PFSendExtractMessage

- ea: `0x14000aa98`
- end: `0x14000adae`
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
- `0x14000aa98`

## import_xrefs

- `ntoskrnl!PsProcessType` at `0x14000aca1`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x14000ad18`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x14000ad18`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ad4e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ad4e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000ab05`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000ab05`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14000acc9`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14000acc9`
- `ntoskrnl!ObfDereferenceObject` at `0x14000ad3a`
- `ntoskrnl!ObfDereferenceObject` at `0x14000ad63`
- `ntoskrnl!ObfDereferenceObject` at `0x14000ad78`
- `ntoskrnl!ObfDereferenceObject` at `0x14000ad3a`
- `ntoskrnl!ObfDereferenceObject` at `0x14000ad63`
- `ntoskrnl!ObfDereferenceObject` at `0x14000ad78`
- `ntoskrnl!ZwDuplicateObject` at `0x14000ab42`
- `ntoskrnl!ZwDuplicateObject` at `0x14000ab42`
- `FLTMGR!FltSendMessage` at `0x14000ac77`
- `FLTMGR!FltSendMessage` at `0x14000ac77`
- `FLTMGR!FltClose` at `0x14000ab5b`
- `FLTMGR!FltClose` at `0x14000ab5b`

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
0x14000aa98  mov     [rsp-8+arg_8], rbx
0x14000aa9d  push    rbp
0x14000aa9e  push    rsi
0x14000aa9f  push    rdi
0x14000aaa0  push    r12
0x14000aaa2  push    r13
0x14000aaa4  push    r14
0x14000aaa6  push    r15
0x14000aaa8  lea     rbp, [rsp-1Fh]
0x14000aaad  sub     rsp, 0B0h
0x14000aab4  mov     rax, cs:__security_cookie
0x14000aabb  xor     rax, rsp
0x14000aabe  mov     [rbp+4Fh+var_38], rax
0x14000aac2  mov     r15d, dword ptr [rbp+4Fh+Size]
0x14000aac6  xor     ebx, ebx
0x14000aac8  xor     eax, eax
0x14000aaca  mov     [rbp+4Fh+ReplyLength], 14h
0x14000aad1  mov     rsi, r8
0x14000aad4  mov     [rbp+4Fh+var_58], eax
0x14000aad7  mov     r14, rcx
0x14000aada  mov     [rbp+4Fh+TargetHandle], rbx
0x14000aade  xorps   xmm0, xmm0
0x14000aae1  mov     [rbp+4Fh+var_78], rbx
0x14000aae5  lea     rdx, [r15+38h]; NumberOfBytes
0x14000aae9  mov     [rbp+4Fh+var_70], rbx
0x14000aaed  lea     ecx, [rax+1]; PoolType
0x14000aaf0  mov     [rbp+4Fh+var_88], rbx
0x14000aaf4  mov     r8d, 574D6D67h; Tag
0x14000aafa  mov     [rbp+4Fh+var_80], rbx
0x14000aafe  mov     r12, r9
0x14000ab01  movups  [rbp+4Fh+ReplyBuffer], xmm0
0x14000ab05  call    cs:__imp_ExAllocatePoolWithTag
0x14000ab0c  nop     dword ptr [rax+rax+00h]
0x14000ab11  mov     rdi, rax
0x14000ab14  test    rax, rax
0x14000ab17  jnz     short loc_14000AB23
0x14000ab19  mov     ebx, 0C000009Ah
0x14000ab1e  jmp     loc_14000AD5A
0x14000ab23  mov     r8, [rsi+30h]; TargetProcessHandle
0x14000ab27  lea     r9, [rbp+4Fh+TargetHandle]; TargetHandle
0x14000ab2b  mov     rdx, [r14]; SourceHandle
0x14000ab2e  or      rcx, 0FFFFFFFFFFFFFFFFh; SourceProcessHandle
0x14000ab32  mov     [rsp+0E0h+Options], 6; Options
0x14000ab3a  mov     [rsp+0E0h+HandleAttributes], ebx; HandleAttributes
0x14000ab3e  mov     [rsp+0E0h+DesiredAccess], ebx; DesiredAccess
0x14000ab42  call    cs:__imp_ZwDuplicateObject
0x14000ab49  nop     dword ptr [rax+rax+00h]
0x14000ab4e  mov     ebx, eax
0x14000ab50  test    eax, eax
0x14000ab52  js      loc_14000AD46
0x14000ab58  mov     rcx, [r14]; FileHandle
0x14000ab5b  call    cs:__imp_FltClose
0x14000ab62  nop     dword ptr [rax+rax+00h]
0x14000ab67  mov     qword ptr [r14], 0
0x14000ab6e  mov     ecx, 3
0x14000ab73  mov     dword ptr [rdi], 42424242h
0x14000ab79  cmp     [rsi+3Ch], cx
0x14000ab7d  ja      short loc_14000ABC8
0x14000ab7f  jnz     short loc_14000AB8A
0x14000ab81  lea     eax, [rcx-2]
0x14000ab84  cmp     [rsi+3Eh], ax
0x14000ab88  jnb     short loc_14000ABCD
0x14000ab8a  mov     [rdi+4], cx
0x14000ab8e  xor     eax, eax
0x14000ab90  mov     [rdi+6], ax
0x14000ab94  lea     rcx, [rdi+1Ch]; void *
0x14000ab98  mov     [rdi+0Ch], eax
0x14000ab9b  mov     r8, r15; Size
0x14000ab9e  lea     eax, [r15+20h]
0x14000aba2  mov     [rdi+18h], r15d
0x14000aba6  mov     rdx, r12; Src
0x14000aba9  mov     [rdi+8], eax
0x14000abac  xor     r14b, r14b
0x14000abaf  call    memmove
0x14000abb4  mov     rax, [rbp+4Fh+TargetHandle]
0x14000abb8  xor     r15d, r15d
0x14000abbb  mov     [rdi+10h], rax
0x14000abbf  lea     r12d, [r15+1]
0x14000abc3  jmp     loc_14000AC4E
0x14000abc8  mov     eax, 1
0x14000abcd  mov     [rdi+4], cx
0x14000abd1  mov     r8, r15; Size
0x14000abd4  mov     [rdi+6], ax
0x14000abd8  lea     rcx, [rdi+2Ch]; void *
0x14000abdc  lea     eax, [r15+30h]
0x14000abe0  mov     dword ptr [rdi+0Ch], 4
0x14000abe7  mov     rdx, r12; Src
0x14000abea  mov     [rdi+8], eax
0x14000abed  mov     [rdi+28h], r15d
0x14000abf1  call    memmove
0x14000abf6  mov     rax, [rbp+4Fh+TargetHandle]
0x14000abfa  lea     r8, [rbp+4Fh+var_88]; Object
0x14000abfe  mov     [rdi+10h], rax
0x14000ac02  lea     rdx, [rbp+4Fh+var_78]; TargetHandle
0x14000ac06  mov     rcx, [rsi+30h]; TargetProcessHandle
0x14000ac0a  call    DuplicateEventIntoProcess
0x14000ac0f  xor     r15d, r15d
0x14000ac12  mov     ebx, eax
0x14000ac14  test    eax, eax
0x14000ac16  js      loc_14000AD46
0x14000ac1c  mov     rcx, [rsi+30h]; TargetProcessHandle
0x14000ac20  lea     r8, [rbp+4Fh+var_80]; Object
0x14000ac24  lea     rdx, [rbp+4Fh+var_70]; TargetHandle
0x14000ac28  call    DuplicateEventIntoProcess
0x14000ac2d  mov     ebx, eax
0x14000ac2f  test    eax, eax
0x14000ac31  js      loc_14000AD46
0x14000ac37  mov     rax, [rbp+4Fh+var_78]
0x14000ac3b  lea     r12d, [r15+1]
0x14000ac3f  mov     [rdi+18h], rax
0x14000ac43  mov     r14b, r12b
0x14000ac46  mov     rax, [rbp+4Fh+var_70]
0x14000ac4a  mov     [rdi+20h], rax
0x14000ac4e  mov     r9d, [rdi+8]; SenderBufferLength
0x14000ac52  lea     rax, [rbp+4Fh+ReplyLength]
0x14000ac56  mov     rcx, cs:gFilterHandle; Filter
0x14000ac5d  lea     rdx, [rsi+28h]; ClientPort
0x14000ac61  mov     qword ptr [rsp+0E0h+Options], r15; Timeout
0x14000ac66  mov     r8, rdi; SenderBuffer
0x14000ac69  mov     qword ptr [rsp+0E0h+HandleAttributes], rax; ReplyLength
0x14000ac6e  lea     rax, [rbp+4Fh+ReplyBuffer]
0x14000ac72  mov     qword ptr [rsp+0E0h+DesiredAccess], rax; ReplyBuffer
0x14000ac77  call    cs:__imp_FltSendMessage
0x14000ac7e  nop     dword ptr [rax+rax+00h]
0x14000ac83  mov     ebx, eax
0x14000ac85  test    eax, eax
0x14000ac87  js      loc_14000AD46
0x14000ac8d  mov     ebx, dword ptr [rbp+4Fh+ReplyBuffer+0Ch]
0x14000ac90  test    ebx, ebx
0x14000ac92  js      loc_14000AD46
0x14000ac98  test    r14b, r14b
0x14000ac9b  jz      loc_14000AD46
0x14000aca1  mov     r8, cs:__imp_PsProcessType
0x14000aca8  lea     rax, [rbp+4Fh+Object]
0x14000acac  mov     rcx, [rsi+30h]; Handle
0x14000acb0  xor     r9d, r9d; AccessMode
0x14000acb3  mov     qword ptr [rsp+0E0h+HandleAttributes], r15; HandleInformation
0x14000acb8  mov     edx, 0F0000h; DesiredAccess
0x14000acbd  mov     [rbp+4Fh+Object], r15
0x14000acc1  mov     r8, [r8]; ObjectType
0x14000acc4  mov     qword ptr [rsp+0E0h+DesiredAccess], rax; Object
0x14000acc9  call    cs:__imp_ObReferenceObjectByHandle
0x14000acd0  nop     dword ptr [rax+rax+00h]
0x14000acd5  mov     ebx, eax
0x14000acd7  test    eax, eax
0x14000acd9  js      short loc_14000AD31
0x14000acdb  mov     rax, [rbp+4Fh+var_80]
0x14000acdf  lea     rdx, [rbp+4Fh+var_50]; Object
0x14000ace3  mov     [rbp+4Fh+var_50], rax
0x14000ace7  mov     r9d, 6; WaitReason
0x14000aced  mov     rax, [rbp+4Fh+var_88]
0x14000acf1  mov     r8d, r12d; WaitType
0x14000acf4  mov     [rsp+0E0h+WaitBlockArray], r15; WaitBlockArray
0x14000acf9  mov     [rbp+4Fh+var_48], rax
0x14000acfd  mov     rax, [rbp+4Fh+Object]
0x14000ad01  lea     ecx, [r9-3]; Count
0x14000ad05  mov     qword ptr [rsp+0E0h+Options], r15; Timeout
0x14000ad0a  mov     byte ptr [rsp+0E0h+HandleAttributes], r12b; Alertable
0x14000ad0f  mov     [rbp+4Fh+var_40], rax
0x14000ad13  mov     byte ptr [rsp+0E0h+DesiredAccess], r15b; WaitMode
0x14000ad18  call    cs:__imp_KeWaitForMultipleObjects
0x14000ad1f  nop     dword ptr [rax+rax+00h]
0x14000ad24  sub     eax, r12d
0x14000ad27  neg     eax
0x14000ad29  sbb     ebx, ebx
0x14000ad2b  and     ebx, 0C0000267h
0x14000ad31  mov     rcx, [rbp+4Fh+Object]; Object
0x14000ad35  test    rcx, rcx
0x14000ad38  jz      short loc_14000AD46
0x14000ad3a  call    cs:__imp_ObfDereferenceObject
0x14000ad41  nop     dword ptr [rax+rax+00h]
0x14000ad46  mov     edx, 574D6D67h; Tag
0x14000ad4b  mov     rcx, rdi; P
0x14000ad4e  call    cs:__imp_ExFreePoolWithTag
0x14000ad55  nop     dword ptr [rax+rax+00h]
0x14000ad5a  mov     rcx, [rbp+4Fh+var_88]; Object
0x14000ad5e  test    rcx, rcx
0x14000ad61  jz      short loc_14000AD6F
0x14000ad63  call    cs:__imp_ObfDereferenceObject
0x14000ad6a  nop     dword ptr [rax+rax+00h]
0x14000ad6f  mov     rcx, [rbp+4Fh+var_80]; Object
0x14000ad73  test    rcx, rcx
0x14000ad76  jz      short loc_14000AD84
0x14000ad78  call    cs:__imp_ObfDereferenceObject
0x14000ad7f  nop     dword ptr [rax+rax+00h]
0x14000ad84  mov     eax, ebx
0x14000ad86  mov     rcx, [rbp+4Fh+var_38]
0x14000ad8a  xor     rcx, rsp; StackCookie
0x14000ad8d  call    __security_check_cookie
0x14000ad92  mov     rbx, [rsp+0E0h+arg_8]
0x14000ad9a  add     rsp, 0B0h
0x14000ada1  pop     r15
0x14000ada3  pop     r14
0x14000ada5  pop     r13
0x14000ada7  pop     r12
0x14000ada9  pop     rdi
0x14000adaa  pop     rsi
0x14000adab  pop     rbp
0x14000adac  retn
```
