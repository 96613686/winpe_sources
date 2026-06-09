# WcRevertDelete

- ea: `0x1400328d8`
- end: `0x140032d24`
- name: `WcRevertDelete`
- size: `1100`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400318f0`

## callees

- `0x140001008`
- `0x140001030`
- `0x140001500`
- `0x1400020c4`
- `0x140007c60`
- `0x14001bf24`
- `0x14002ee10`
- `0x1400328d8`

## import_xrefs

- `ntoskrnl!RtlInitEnumerationHashTable` at `0x140032ad0`
- `ntoskrnl!RtlInitEnumerationHashTable` at `0x140032ad0`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x140032c28`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x140032c28`
- `ntoskrnl!RtlEndEnumerationHashTable` at `0x140032c7f`
- `ntoskrnl!RtlEndEnumerationHashTable` at `0x140032c7f`
- `ntoskrnl!RtlEnumerateEntryHashTable` at `0x140032ae8`
- `ntoskrnl!RtlEnumerateEntryHashTable` at `0x140032c54`
- `ntoskrnl!RtlEnumerateEntryHashTable` at `0x140032ae8`
- `ntoskrnl!RtlEnumerateEntryHashTable` at `0x140032c54`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140032a78`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140032a78`
- `ntoskrnl!KeWaitForSingleObject` at `0x140032aa5`
- `ntoskrnl!KeWaitForSingleObject` at `0x140032aa5`
- `ntoskrnl!KeSetEvent` at `0x140032c93`
- `ntoskrnl!KeSetEvent` at `0x140032c93`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140032a60`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140032b28`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140032a60`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140032b28`
- `ntoskrnl!ExFreePoolWithTag` at `0x140032c3c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140032cae`
- `ntoskrnl!ExFreePoolWithTag` at `0x140032c3c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140032cae`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140032cc4`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140032cc4`
- `FLTMGR!FltGetFileNameInformation` at `0x140032a10`
- `FLTMGR!FltGetFileNameInformation` at `0x140032a10`
- `FLTMGR!FltQueryInformationFile` at `0x14003295a`
- `FLTMGR!FltQueryInformationFile` at `0x14003295a`
- `FLTMGR!FltReleaseContext` at `0x140032cda`
- `FLTMGR!FltReleaseContext` at `0x140032cee`
- `FLTMGR!FltReleaseContext` at `0x140032cda`
- `FLTMGR!FltReleaseContext` at `0x140032cee`

## pseudocode

```c
__int64 __fastcall WcRevertDelete(PFLT_CALLBACK_DATA CallbackData, __int64 a2)
{
  struct _FILE_OBJECT *v3; // rdx
  struct _FLT_INSTANCE *v4; // rcx
  NTSTATUS v5; // eax
  int v6; // edx
  unsigned int v7; // edi
  __int64 v9; // [rsp+48h] [rbp-B8h]
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+50h] [rbp-B0h]
  struct _UNICODE_STRING Destination; // [rsp+58h] [rbp-A8h]
  PFLT_CONTEXT Context; // [rsp+68h] [rbp-98h]
  struct _RTL_DYNAMIC_HASH_TABLE_ENUMERATOR Enumerator; // [rsp+70h] [rbp-90h] BYREF
  __int128 FileInformation; // [rsp+98h] [rbp-68h] BYREF
  __int64 v15; // [rsp+A8h] [rbp-58h]

  Context = 0;
  v3 = *(struct _FILE_OBJECT **)(a2 + 32);
  FileNameInformation = 0;
  v4 = *(struct _FLT_INSTANCE **)(a2 + 24);
  v9 = 0;
  memset(&Enumerator, 0, sizeof(Enumerator));
  v15 = 0;
  FileInformation = 0;
  Destination = 0;
  v5 = FltQueryInformationFile(v4, v3, &FileInformation, 0x18u, FileStandardInformation, 0);
  v7 = v5;
  if ( v5 >= 0 )
  {
    if ( !BYTE6(v15) )
      WcGetContextFileObject(*(PFLT_INSTANCE *)(a2 + 24), *(PFILE_OBJECT *)(a2 + 32));
  }
  else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v6) = 2;
    WPP_RECORDER_SF_sDd(
      WPP_GLOBAL_Control->DeviceExtension,
      v6,
      5,
      29,
      (__int64)WPP_6c993b8198b53d328fc429e03cc469de_Traceguids,
      (__int64)"onecore\\base\\fs\\wci\\wcifs\\tombstone.c",
      126,
      v5);
  }
  return v7;
}

```

## disassembly

```asm
0x1400328d8  mov     [rsp-8+arg_10], rbx
0x1400328dd  push    rbp
0x1400328de  push    rsi
0x1400328df  push    rdi
0x1400328e0  push    r12
0x1400328e2  push    r13
0x1400328e4  push    r14
0x1400328e6  push    r15
0x1400328e8  lea     rbp, [rsp-10h]
0x1400328ed  sub     rsp, 110h
0x1400328f4  mov     rax, cs:__security_cookie
0x1400328fb  xor     rax, rsp
0x1400328fe  mov     [rbp+40h+var_40], rax
0x140032902  xor     r15d, r15d
0x140032905  lea     r8, [rbp+40h+FileInformation]; FileInformation
0x140032909  xorps   xmm0, xmm0
0x14003290c  mov     [rsp+140h+LengthReturned], r15; LengthReturned
0x140032911  mov     r13, rdx
0x140032914  mov     [rsp+140h+Context], r15
0x140032919  mov     rdx, [rdx+20h]; FileObject
0x14003291d  xor     eax, eax
0x14003291f  mov     rsi, rcx
0x140032922  mov     qword ptr [rbp+40h+Enumerator.BucketIndex], rax
0x140032926  lea     r14d, [r15+5]
0x14003292a  mov     [rsp+140h+FileNameInformation], r15
0x14003292f  mov     rcx, [r13+18h]; Instance
0x140032933  lea     r9d, [r15+18h]; Length
0x140032937  mov     ebx, r15d
0x14003293a  mov     [rsp+140h+FileInformationClass], r14d; FileInformationClass
0x14003293f  mov     [rsp+140h+var_F8], rbx
0x140032944  movups  xmmword ptr [rsp+140h+Enumerator], xmm0
0x140032949  mov     [rbp+40h+var_98], rax
0x14003294d  movups  xmmword ptr [rbp+40h+Enumerator+10h], xmm0
0x140032951  movups  [rbp+40h+FileInformation], xmm0
0x140032955  movups  xmmword ptr [rsp+140h+Destination.Length], xmm0
0x14003295a  call    cs:__imp_FltQueryInformationFile
0x140032961  nop     dword ptr [rax+rax+00h]
0x140032966  mov     edi, eax
0x140032968  test    eax, eax
0x14003296a  jns     short loc_1400329C2
0x14003296c  lea     rsi, WPP_RECORDER_INITIALIZED
0x140032973  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14003297a  jz      loc_140032CBA
0x140032980  mov     rcx, cs:WPP_GLOBAL_Control
0x140032987  lea     r9d, [r15+1Dh]
0x14003298b  mov     [rsp+140h+var_108], eax
0x14003298f  lea     r15, aOnecoreBaseFsW_10; "onecore\\base\\fs\\wci\\wcifs\\tombston"...
0x140032996  mov     [rsp+140h+var_110], 57Eh
0x14003299e  lea     r12, WPP_6c993b8198b53d328fc429e03cc469de_Traceguids
0x1400329a5  mov     [rsp+140h+LengthReturned], r15
0x1400329aa  mov     r8d, r14d
0x1400329ad  mov     rcx, [rcx+40h]
0x1400329b1  mov     dl, 2
0x1400329b3  mov     qword ptr [rsp+140h+FileInformationClass], r12
0x1400329b8  call    WPP_RECORDER_SF_sDd
0x1400329bd  jmp     loc_140032CBA
0x1400329c2  cmp     byte ptr [rbp+40h+var_98+6], r15b
0x1400329c6  jnz     loc_140032CBA
0x1400329cc  mov     rdx, [r13+20h]; FileObject
0x1400329d0  lea     r9, [rsp+140h+var_F8]
0x1400329d5  mov     rcx, [r13+18h]; Instance
0x1400329d9  lea     r8, [rsp+140h+Context]
0x1400329de  call    WcGetContextFileObject
0x1400329e3  mov     rbx, [rsp+140h+var_F8]
0x1400329e8  test    al, al
0x1400329ea  jz      loc_140032CBA
0x1400329f0  test    rbx, rbx
0x1400329f3  jz      loc_140032CBA
0x1400329f9  cmp     [rbx+1Ch], r15b
0x1400329fd  jz      loc_140032CBA
0x140032a03  lea     r8, [rsp+140h+FileNameInformation]; FileNameInformation
0x140032a08  mov     edx, 301h; NameOptions
0x140032a0d  mov     rcx, rsi; CallbackData
0x140032a10  call    cs:__imp_FltGetFileNameInformation
0x140032a17  nop     dword ptr [rax+rax+00h]
0x140032a1c  mov     edi, eax
0x140032a1e  test    eax, eax
0x140032a20  js      loc_140032CBA
0x140032a26  mov     rax, [rsp+140h+FileNameInformation]
0x140032a2b  lea     rdx, [rsp+140h+Destination]
0x140032a30  mov     ecx, 20Ah
0x140032a35  add     cx, [rax+0Ah]
0x140032a39  mov     [rsp+140h+Destination.MaximumLength], cx
0x140032a3e  mov     ecx, 6E664357h
0x140032a43  call    WcAllocateUnicodeString
0x140032a48  mov     edi, eax
0x140032a4a  test    eax, eax
0x140032a4c  js      loc_140032CBA
0x140032a52  mov     rdx, [rsp+140h+FileNameInformation]
0x140032a57  lea     rcx, [rsp+140h+Destination]; Destination
0x140032a5c  add     rdx, 8; Source
0x140032a60  call    cs:__imp_RtlAppendUnicodeStringToString
0x140032a67  nop     dword ptr [rax+rax+00h]
0x140032a6c  lea     rdx, Source2; "\\"
0x140032a73  lea     rcx, [rsp+140h+Destination]; Destination
0x140032a78  call    cs:__imp_RtlAppendUnicodeToString
0x140032a7f  nop     dword ptr [rax+rax+00h]
0x140032a84  movzx   eax, [rsp+140h+Destination.Length]
0x140032a89  lea     rsi, [rbx+0E8h]
0x140032a90  mov     rcx, rsi; Object
0x140032a93  mov     [rsp+140h+var_FE], ax
0x140032a98  xor     r9d, r9d; Alertable
0x140032a9b  mov     qword ptr [rsp+140h+FileInformationClass], r15; Timeout
0x140032aa0  xor     r8d, r8d; WaitMode
0x140032aa3  xor     edx, edx; WaitReason
0x140032aa5  call    cs:__imp_KeWaitForSingleObject
0x140032aac  nop     dword ptr [rax+rax+00h]
0x140032ab1  mov     rcx, [rbx+100h]; HashTable
0x140032ab8  test    rcx, rcx
0x140032abb  jz      loc_140032C8B
0x140032ac1  cmp     [rcx+14h], r15d
0x140032ac5  jz      loc_140032C8B
0x140032acb  lea     rdx, [rsp+140h+Enumerator]; Enumerator
0x140032ad0  call    cs:__imp_RtlInitEnumerationHashTable
0x140032ad7  nop     dword ptr [rax+rax+00h]
0x140032adc  mov     rcx, [rbx+100h]; HashTable
0x140032ae3  lea     rdx, [rsp+140h+Enumerator]; Enumerator
0x140032ae8  call    cs:__imp_RtlEnumerateEntryHashTable
0x140032aef  nop     dword ptr [rax+rax+00h]
0x140032af4  mov     r14, rax
0x140032af7  test    rax, rax
0x140032afa  jz      loc_140032C73
0x140032b00  lea     rsi, WPP_RECORDER_INITIALIZED
0x140032b07  lea     r15, aOnecoreBaseFsW_10; "onecore\\base\\fs\\wci\\wcifs\\tombston"...
0x140032b0e  lea     r12, WPP_6c993b8198b53d328fc429e03cc469de_Traceguids
0x140032b15  movzx   eax, [rsp+140h+var_FE]
0x140032b1a  lea     rdx, [r14+20h]; Source
0x140032b1e  lea     rcx, [rsp+140h+Destination]; Destination
0x140032b23  mov     [rsp+140h+Destination.Length], ax
0x140032b28  call    cs:__imp_RtlAppendUnicodeStringToString
0x140032b2f  nop     dword ptr [rax+rax+00h]
0x140032b34  mov     r8b, [r14+18h]
0x140032b38  lea     rdx, [rsp+140h+Destination]
0x140032b3d  mov     rcx, [r13+18h]; Instance
0x140032b41  call    WcCreateTombstone
0x140032b46  mov     edi, eax
0x140032b48  test    eax, eax
0x140032b4a  jns     loc_140032C1B
0x140032b50  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140032b57  jz      short loc_140032B8B
0x140032b59  mov     rcx, cs:WPP_GLOBAL_Control
0x140032b60  mov     r9d, 1Eh
0x140032b66  mov     [rsp+140h+var_108], eax
0x140032b6a  mov     dl, 2
0x140032b6c  mov     [rsp+140h+var_110], 5C5h
0x140032b74  mov     [rsp+140h+LengthReturned], r15
0x140032b79  mov     rcx, [rcx+40h]
0x140032b7d  lea     r8d, [r9-19h]
0x140032b81  mov     qword ptr [rsp+140h+FileInformationClass], r12
0x140032b86  call    WPP_RECORDER_SF_sDd
0x140032b8b  mov     eax, cs:dword_14000E060
0x140032b91  cmp     eax, 5
0x140032b94  jbe     loc_140032C1B
0x140032b9a  mov     rdx, 400000000000h
0x140032ba4  lea     rcx, dword_14000E060
0x140032bab  call    _tlgKeywordOn
0x140032bb0  test    al, al
0x140032bb2  jz      short loc_140032C1B
0x140032bb4  mov     ecx, 1
0x140032bb9  mov     [rsp+140h+var_FF], 6
0x140032bbe  lea     rax, [rsp+140h+var_100]
0x140032bc3  mov     [rsp+140h+var_100], cl
0x140032bc7  mov     [rbp+40h+var_70], rax
0x140032bcb  lea     rdx, byte_14000BAEB
0x140032bd2  lea     rax, [rsp+140h+var_FF]
0x140032bd7  mov     [rbp+40h+var_68], rcx
0x140032bdb  mov     [rbp+40h+var_60], rax
0x140032bdf  xor     r9d, r9d
0x140032be2  lea     rax, [rsp+140h+var_F8]
0x140032be7  mov     [rbp+40h+var_58], rcx
0x140032beb  mov     [rbp+40h+var_50], rax
0x140032bef  lea     rcx, dword_14000E060
0x140032bf6  lea     rax, [rbp+40h+var_90]
0x140032bfa  mov     dword ptr [rsp+140h+var_F8], edi
0x140032bfe  mov     [rsp+140h+LengthReturned], rax
0x140032c03  xor     r8d, r8d
0x140032c06  mov     [rsp+140h+FileInformationClass], 5
0x140032c0e  mov     [rbp+40h+var_48], 4
0x140032c16  call    _tlgWriteTransfer_EtwWriteTransfer
0x140032c1b  mov     rcx, [rbx+100h]; HashTable
0x140032c22  xor     r8d, r8d; Context
0x140032c25  mov     rdx, r14; Entry
0x140032c28  call    cs:__imp_RtlRemoveEntryHashTable
0x140032c2f  nop     dword ptr [rax+rax+00h]
0x140032c34  mov     edx, 74684357h; Tag
0x140032c39  mov     rcx, r14; P
0x140032c3c  call    cs:__imp_ExFreePoolWithTag
0x140032c43  nop     dword ptr [rax+rax+00h]
0x140032c48  mov     rcx, [rbx+100h]; HashTable
0x140032c4f  lea     rdx, [rsp+140h+Enumerator]; Enumerator
0x140032c54  call    cs:__imp_RtlEnumerateEntryHashTable
0x140032c5b  nop     dword ptr [rax+rax+00h]
0x140032c60  mov     r14, rax
0x140032c63  test    rax, rax
0x140032c66  jnz     loc_140032B15
0x140032c6c  lea     rsi, [rbx+0E8h]
0x140032c73  mov     rcx, [rbx+100h]; HashTable
0x140032c7a  lea     rdx, [rsp+140h+Enumerator]; Enumerator
0x140032c7f  call    cs:__imp_RtlEndEnumerationHashTable
0x140032c86  nop     dword ptr [rax+rax+00h]
0x140032c8b  xor     r8d, r8d; Wait
0x140032c8e  xor     edx, edx; Increment
0x140032c90  mov     rcx, rsi; Event
0x140032c93  call    cs:__imp_KeSetEvent
0x140032c9a  nop     dword ptr [rax+rax+00h]
0x140032c9f  mov     rcx, [rsp+140h+Destination.Buffer]; P
0x140032ca4  test    rcx, rcx
0x140032ca7  jz      short loc_140032CBA
0x140032ca9  mov     edx, 6E664357h; Tag
0x140032cae  call    cs:__imp_ExFreePoolWithTag
0x140032cb5  nop     dword ptr [rax+rax+00h]
0x140032cba  mov     rcx, [rsp+140h+FileNameInformation]; FileNameInformation
0x140032cbf  test    rcx, rcx
0x140032cc2  jz      short loc_140032CD0
0x140032cc4  call    cs:__imp_FltReleaseFileNameInformation
0x140032ccb  nop     dword ptr [rax+rax+00h]
0x140032cd0  mov     rcx, [rsp+140h+Context]; Context
0x140032cd5  test    rcx, rcx
0x140032cd8  jz      short loc_140032CE6
0x140032cda  call    cs:__imp_FltReleaseContext
0x140032ce1  nop     dword ptr [rax+rax+00h]
0x140032ce6  test    rbx, rbx
0x140032ce9  jz      short loc_140032CFA
0x140032ceb  mov     rcx, rbx; Context
0x140032cee  call    cs:__imp_FltReleaseContext
0x140032cf5  nop     dword ptr [rax+rax+00h]
0x140032cfa  mov     eax, edi
0x140032cfc  mov     rcx, [rbp+40h+var_40]
0x140032d00  xor     rcx, rsp; StackCookie
0x140032d03  call    __security_check_cookie
0x140032d08  mov     rbx, [rsp+140h+arg_10]
0x140032d10  add     rsp, 110h
0x140032d17  pop     r15
0x140032d19  pop     r14
0x140032d1b  pop     r13
0x140032d1d  pop     r12
0x140032d1f  pop     rdi
0x140032d20  pop     rsi
0x140032d21  pop     rbp
0x140032d22  retn
```
