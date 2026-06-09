# WcPartiallyExpandDirectory

- ea: `0x14002ef40`
- end: `0x14002f1a2`
- name: `WcPartiallyExpandDirectory`
- size: `610`
- prototype: `__int64 __usercall@<rax>(PFLT_CALLBACK_DATA CallbackData@<rcx>, PVOID FltObject@<rdx>, PVOID Object@<r8>, char, PUNICODE_STRING)`
- caller_count: `3`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x14001f08c`
- `0x140026210`
- `0x140033860`

## callees

- `0x140001500`
- `0x140001bc8`
- `0x140001ffc`
- `0x140004b0c`
- `0x140014008`
- `0x14002ef40`
- `0x140030d54`

## import_xrefs

- `ntoskrnl!ExReleaseRundownProtection` at `0x14002f075`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14002f075`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14002efa7`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14002efa7`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002f00e`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002f00e`
- `FLTMGR!FltParseFileName` at `0x14002f027`
- `FLTMGR!FltParseFileName` at `0x14002f027`
- `FLTMGR!FltReleaseContext` at `0x14002f16b`
- `FLTMGR!FltReleaseContext` at `0x14002f17f`
- `FLTMGR!FltReleaseContext` at `0x14002f16b`
- `FLTMGR!FltReleaseContext` at `0x14002f17f`

## pseudocode

```c
__int64 __fastcall WcPartiallyExpandDirectory(
        PFLT_CALLBACK_DATA CallbackData,
        struct _FLT_INSTANCE *FltObject,
        struct _FILE_OBJECT *Object,
        struct _LIST_ENTRY *a4,
        char a5,
        PUNICODE_STRING a6)
{
  unsigned int v9; // ebx
  int v10; // edx
  UNICODE_STRING FileName; // [rsp+60h] [rbp-19h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp-9h] BYREF

  v9 = 0;
  FileName = 0;
  DestinationString = 0;
  if ( !(unsigned __int8)WcGetContextFileObject(FltObject, Object) )
    return v9;
  if ( ExAcquireRundownProtection((PEX_RUNDOWN_REF)0x48) )
  {
    if ( (unsigned __int8)WcIsExpanded(0) )
    {
      v9 = -1073741772;
    }
    else if ( WcIsPlaceHolderDirectory(0, 0) )
    {
      FileName.Buffer = a6->Buffer;
      FileName.Length = a6->Length;
      FileName.MaximumLength = a6->MaximumLength;
      if ( a5 )
      {
        RtlInitUnicodeString(&DestinationString, 0);
        if ( FltParseFileName(&FileName, 0, &DestinationString, 0) >= 0 )
        {
          if ( DestinationString.Length )
            FileName.Length -= DestinationString.Length;
        }
      }
      v9 = WcPopulateFile(&FileName, (_QWORD *)0x38, MEMORY[0x40], FltObject, a4, Object, 1, 0);
    }
    ExReleaseRundownProtection((PEX_RUNDOWN_REF)0x48);
    if ( a5 )
      return v9;
    goto LABEL_19;
  }
  v9 = WcExpandAndWait(CallbackData, FltObject, Object, 2, 8);
  if ( (v9 & 0x80000000) == 0 )
  {
    if ( a5 )
      return v9;
    if ( (unsigned __int8)WcIsExpanded(0) )
      return (unsigned int)-1073741766;
    v9 = WcPopulateFile(a6, (_QWORD *)0x38, MEMORY[0x40], FltObject, a4, Object, 1, 1);
LABEL_19:
    if ( v9 != -1073741772 )
      return v9;
    return (unsigned int)-1073741766;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v10) = 2;
    WPP_RECORDER_SF_sDdZ(
      WPP_GLOBAL_Control->DeviceExtension,
      v10,
      10,
      37,
      (__int64)WPP_c8ed118f3d633d749a651abfa78156c7_Traceguids,
      (__int64)"onecore\\base\\fs\\wci\\wcifs\\expansion.c",
      172,
      v9,
      (__int64)&FileName);
  }
  return v9;
}

```

## disassembly

```asm
0x14002ef40  mov     [rsp-8+arg_18], r9
0x14002ef45  push    rbp
0x14002ef46  push    rbx
0x14002ef47  push    rsi
0x14002ef48  push    rdi
0x14002ef49  push    r12
0x14002ef4b  push    r13
0x14002ef4d  push    r14
0x14002ef4f  push    r15
0x14002ef51  lea     rbp, [rsp-0Fh]
0x14002ef56  sub     rsp, 88h
0x14002ef5d  xor     eax, eax
0x14002ef5f  lea     r9, [rbp+47h+var_70]
0x14002ef63  mov     r12, r8
0x14002ef66  mov     [rbp+47h+Context], rax
0x14002ef6a  mov     r13, rdx
0x14002ef6d  mov     [rbp+47h+var_70], rax
0x14002ef71  mov     r14, rcx
0x14002ef74  lea     r8, [rbp+47h+Context]
0x14002ef78  xorps   xmm0, xmm0
0x14002ef7b  xorps   xmm1, xmm1
0x14002ef7e  mov     rdx, r12; FileObject
0x14002ef81  mov     rcx, r13; Instance
0x14002ef84  mov     ebx, eax
0x14002ef86  movups  xmmword ptr [rbp+47h+FileName.Length], xmm0
0x14002ef8a  movups  xmmword ptr [rbp+47h+DestinationString.Length], xmm1
0x14002ef8e  call    WcGetContextFileObject
0x14002ef93  mov     rsi, [rbp+47h+var_70]
0x14002ef97  mov     rdi, [rbp+47h+Context]
0x14002ef9b  test    al, al
0x14002ef9d  jz      loc_14002F163
0x14002efa3  lea     rcx, [rdi+48h]; RunRef
0x14002efa7  call    cs:__imp_ExAcquireRundownProtection
0x14002efae  nop     dword ptr [rax+rax+00h]
0x14002efb3  test    al, al
0x14002efb5  jz      loc_14002F08F
0x14002efbb  mov     rcx, rdi
0x14002efbe  call    WcIsExpanded
0x14002efc3  mov     r14b, [rbp+47h+arg_20]
0x14002efc7  test    al, al
0x14002efc9  jz      short loc_14002EFD5
0x14002efcb  mov     ebx, 0C0000034h
0x14002efd0  jmp     loc_14002F071
0x14002efd5  mov     rdx, rsi
0x14002efd8  mov     rcx, rdi
0x14002efdb  call    WcIsPlaceHolderDirectory
0x14002efe0  test    al, al
0x14002efe2  jz      loc_14002F071
0x14002efe8  mov     rcx, [rbp+47h+arg_28]
0x14002efec  mov     rax, [rcx+8]
0x14002eff0  mov     [rbp+47h+FileName.Buffer], rax
0x14002eff4  movzx   eax, word ptr [rcx]
0x14002eff7  mov     [rbp+47h+FileName.Length], ax
0x14002effb  movzx   eax, word ptr [rcx+2]
0x14002efff  mov     [rbp+47h+FileName.MaximumLength], ax
0x14002f003  test    r14b, r14b
0x14002f006  jz      short loc_14002F044
0x14002f008  xor     edx, edx; SourceString
0x14002f00a  lea     rcx, [rbp+47h+DestinationString]; DestinationString
0x14002f00e  call    cs:__imp_RtlInitUnicodeString
0x14002f015  nop     dword ptr [rax+rax+00h]
0x14002f01a  xor     r9d, r9d; FinalComponent
0x14002f01d  lea     r8, [rbp+47h+DestinationString]; Stream
0x14002f021  xor     edx, edx; Extension
0x14002f023  lea     rcx, [rbp+47h+FileName]; FileName
0x14002f027  call    cs:__imp_FltParseFileName
0x14002f02e  nop     dword ptr [rax+rax+00h]
0x14002f033  test    eax, eax
0x14002f035  js      short loc_14002F044
0x14002f037  movzx   eax, [rbp+47h+DestinationString.Length]
0x14002f03b  test    ax, ax
0x14002f03e  jz      short loc_14002F044
0x14002f040  sub     [rbp+47h+FileName.Length], ax
0x14002f044  mov     rax, [rbp+47h+arg_18]
0x14002f048  lea     rdx, [rsi+38h]
0x14002f04c  mov     r8, [rdi+40h]
0x14002f050  lea     rcx, [rbp+47h+FileName]; FileName
0x14002f054  mov     [rsp+0C0h+var_88], bl; char
0x14002f058  mov     r9, r13
0x14002f05b  mov     [rsp+0C0h+var_90], 1; char
0x14002f060  mov     [rsp+0C0h+FileObject], r12; FileObject
0x14002f065  mov     [rsp+0C0h+var_A0], rax; __int64
0x14002f06a  call    WcPopulateFile
0x14002f06f  mov     ebx, eax
0x14002f071  lea     rcx, [rdi+48h]; RunRef
0x14002f075  call    cs:__imp_ExReleaseRundownProtection
0x14002f07c  nop     dword ptr [rax+rax+00h]
0x14002f081  test    r14b, r14b
0x14002f084  jz      loc_14002F156
0x14002f08a  jmp     loc_14002F163
0x14002f08f  mov     dword ptr [rsp+0C0h+FileObject], 8; int
0x14002f097  mov     r9, rdi
0x14002f09a  mov     r8, r12; Object
0x14002f09d  mov     dword ptr [rsp+0C0h+var_A0], 2; int
0x14002f0a5  mov     rdx, r13; FltObject
0x14002f0a8  mov     rcx, r14; CallbackData
0x14002f0ab  call    WcExpandAndWait
0x14002f0b0  xor     r14d, r14d
0x14002f0b3  mov     ebx, eax
0x14002f0b5  test    eax, eax
0x14002f0b7  jns     short loc_14002F116
0x14002f0b9  lea     rax, WPP_RECORDER_INITIALIZED
0x14002f0c0  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002f0c7  jz      loc_14002F163
0x14002f0cd  mov     rcx, cs:WPP_GLOBAL_Control
0x14002f0d4  lea     rax, [rbp+47h+FileName]
0x14002f0d8  mov     [rsp+0C0h+var_80], rax
0x14002f0dd  lea     r9d, [r14+25h]
0x14002f0e1  mov     dword ptr [rsp+0C0h+var_88], ebx
0x14002f0e5  lea     rax, aOnecoreBaseFsW_3; "onecore\\base\\fs\\wci\\wcifs\\expansio"...
0x14002f0ec  mov     dword ptr [rsp+0C0h+var_90], 0BACh
0x14002f0f4  lea     r8d, [r14+0Ah]
0x14002f0f8  mov     rcx, [rcx+40h]
0x14002f0fc  mov     dl, 2
0x14002f0fe  mov     [rsp+0C0h+FileObject], rax
0x14002f103  lea     rax, WPP_c8ed118f3d633d749a651abfa78156c7_Traceguids
0x14002f10a  mov     [rsp+0C0h+var_A0], rax
0x14002f10f  call    WPP_RECORDER_SF_sDdZ
0x14002f114  jmp     short loc_14002F163
0x14002f116  cmp     [rbp+47h+arg_20], r14b
0x14002f11a  jnz     short loc_14002F163
0x14002f11c  mov     rcx, rdi
0x14002f11f  call    WcIsExpanded
0x14002f124  test    al, al
0x14002f126  jnz     short loc_14002F15E
0x14002f128  mov     rax, [rbp+47h+arg_18]
0x14002f12c  lea     rdx, [rsi+38h]
0x14002f130  mov     r8, [rdi+40h]
0x14002f134  mov     r9, r13
0x14002f137  mov     rcx, [rbp+47h+arg_28]; FileName
0x14002f13b  mov     [rsp+0C0h+var_88], 1; char
0x14002f140  mov     [rsp+0C0h+var_90], 1; char
0x14002f145  mov     [rsp+0C0h+FileObject], r12; FileObject
0x14002f14a  mov     [rsp+0C0h+var_A0], rax; __int64
0x14002f14f  call    WcPopulateFile
0x14002f154  mov     ebx, eax
0x14002f156  cmp     ebx, 0C0000034h
0x14002f15c  jnz     short loc_14002F163
0x14002f15e  mov     ebx, 0C000003Ah
0x14002f163  test    rdi, rdi
0x14002f166  jz      short loc_14002F177
0x14002f168  mov     rcx, rdi; Context
0x14002f16b  call    cs:__imp_FltReleaseContext
0x14002f172  nop     dword ptr [rax+rax+00h]
0x14002f177  test    rsi, rsi
0x14002f17a  jz      short loc_14002F18B
0x14002f17c  mov     rcx, rsi; Context
0x14002f17f  call    cs:__imp_FltReleaseContext
0x14002f186  nop     dword ptr [rax+rax+00h]
0x14002f18b  mov     eax, ebx
0x14002f18d  add     rsp, 88h
0x14002f194  pop     r15
0x14002f196  pop     r14
0x14002f198  pop     r13
0x14002f19a  pop     r12
0x14002f19c  pop     rdi
0x14002f19d  pop     rsi
0x14002f19e  pop     rbx
0x14002f19f  pop     rbp
0x14002f1a0  retn
```
