# WcPartiallyExpandDirectory

- ea: `0x14002ef90`
- end: `0x14002f1f2`
- name: `WcPartiallyExpandDirectory`
- size: `610`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData, struct _FLT_INSTANCE *FltObject, struct _FILE_OBJECT *Object, __int64, char, PUNICODE_STRING)`
- caller_count: `3`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x14001f08c`
- `0x140026260`
- `0x1400338b0`

## callees

- `0x140001500`
- `0x140001bc8`
- `0x140001ffc`
- `0x140004b0c`
- `0x140014008`
- `0x14002ef90`
- `0x140030da4`

## import_xrefs

- `ntoskrnl!ExReleaseRundownProtection` at `0x14002f0c5`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14002f0c5`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14002eff7`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14002eff7`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002f05e`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002f05e`
- `FLTMGR!FltParseFileName` at `0x14002f077`
- `FLTMGR!FltParseFileName` at `0x14002f077`
- `FLTMGR!FltReleaseContext` at `0x14002f1bb`
- `FLTMGR!FltReleaseContext` at `0x14002f1cf`
- `FLTMGR!FltReleaseContext` at `0x14002f1bb`
- `FLTMGR!FltReleaseContext` at `0x14002f1cf`

## pseudocode

```c
__int64 __fastcall WcPartiallyExpandDirectory(
        PFLT_CALLBACK_DATA CallbackData,
        struct _FLT_INSTANCE *FltObject,
        struct _FILE_OBJECT *Object,
        __int64 a4,
        char a5,
        PUNICODE_STRING a6)
{
  int v9; // ebx
  char ContextFileObject; // al
  PFLT_CONTEXT v11; // rsi
  struct _EX_RUNDOWN_REF *v12; // rdi
  int v13; // edx
  PFLT_CONTEXT v15; // [rsp+50h] [rbp-29h] BYREF
  PFLT_CONTEXT Context; // [rsp+58h] [rbp-21h] BYREF
  UNICODE_STRING FileName; // [rsp+60h] [rbp-19h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp-9h] BYREF

  Context = 0;
  v15 = 0;
  v9 = 0;
  FileName = 0;
  DestinationString = 0;
  ContextFileObject = WcGetContextFileObject(FltObject, Object, &Context, &v15);
  v11 = v15;
  v12 = (struct _EX_RUNDOWN_REF *)Context;
  if ( !ContextFileObject )
    goto LABEL_21;
  if ( ExAcquireRundownProtection((PEX_RUNDOWN_REF)Context + 9) )
  {
    if ( WcIsExpanded((__int64)v12) )
    {
      v9 = -1073741772;
    }
    else if ( WcIsPlaceHolderDirectory((__int64)v12, (__int64)v11) )
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
      v9 = WcPopulateFile(&FileName, a4, Object, 1, 0);
    }
    ExReleaseRundownProtection(v12 + 9);
    if ( a5 )
      goto LABEL_21;
    goto LABEL_19;
  }
  v9 = WcExpandAndWait(CallbackData, FltObject, Object, (__int64)v12, 2, 8);
  if ( v9 >= 0 )
  {
    if ( a5 )
      goto LABEL_21;
    if ( WcIsExpanded((__int64)v12) )
    {
LABEL_20:
      v9 = -1073741766;
      goto LABEL_21;
    }
    v9 = WcPopulateFile(a6, a4, Object, 1, 1);
LABEL_19:
    if ( v9 != -1073741772 )
      goto LABEL_21;
    goto LABEL_20;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v13) = 2;
    WPP_RECORDER_SF_sDdZ(
      wil_details_featureDescriptors_a->DeviceExtension,
      v13,
      10,
      37,
      (__int64)WPP_c8ed118f3d633d749a651abfa78156c7_Traceguids,
      (__int64)"onecore\\base\\fs\\wci\\wcifs\\expansion.c",
      172,
      v9,
      (__int64)&FileName);
  }
LABEL_21:
  if ( v12 )
    FltReleaseContext(v12);
  if ( v11 )
    FltReleaseContext(v11);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x14002ef90  mov     [rsp-8+arg_18], r9
0x14002ef95  push    rbp
0x14002ef96  push    rbx
0x14002ef97  push    rsi
0x14002ef98  push    rdi
0x14002ef99  push    r12
0x14002ef9b  push    r13
0x14002ef9d  push    r14
0x14002ef9f  push    r15
0x14002efa1  lea     rbp, [rsp-0Fh]
0x14002efa6  sub     rsp, 88h
0x14002efad  xor     eax, eax
0x14002efaf  lea     r9, [rbp+47h+var_70]
0x14002efb3  mov     r12, r8
0x14002efb6  mov     [rbp+47h+Context], rax
0x14002efba  mov     r13, rdx
0x14002efbd  mov     [rbp+47h+var_70], rax
0x14002efc1  mov     r14, rcx
0x14002efc4  lea     r8, [rbp+47h+Context]
0x14002efc8  xorps   xmm0, xmm0
0x14002efcb  xorps   xmm1, xmm1
0x14002efce  mov     rdx, r12; FileObject
0x14002efd1  mov     rcx, r13; Instance
0x14002efd4  mov     ebx, eax
0x14002efd6  movups  xmmword ptr [rbp+47h+FileName.Length], xmm0
0x14002efda  movups  xmmword ptr [rbp+47h+DestinationString.Length], xmm1
0x14002efde  call    WcGetContextFileObject
0x14002efe3  mov     rsi, [rbp+47h+var_70]
0x14002efe7  mov     rdi, [rbp+47h+Context]
0x14002efeb  test    al, al
0x14002efed  jz      loc_14002F1B3
0x14002eff3  lea     rcx, [rdi+48h]; RunRef
0x14002eff7  call    cs:__imp_ExAcquireRundownProtection
0x14002effe  nop     dword ptr [rax+rax+00h]
0x14002f003  test    al, al
0x14002f005  jz      loc_14002F0DF
0x14002f00b  mov     rcx, rdi
0x14002f00e  call    WcIsExpanded
0x14002f013  mov     r14b, [rbp+47h+arg_20]
0x14002f017  test    al, al
0x14002f019  jz      short loc_14002F025
0x14002f01b  mov     ebx, 0C0000034h
0x14002f020  jmp     loc_14002F0C1
0x14002f025  mov     rdx, rsi
0x14002f028  mov     rcx, rdi
0x14002f02b  call    WcIsPlaceHolderDirectory
0x14002f030  test    al, al
0x14002f032  jz      loc_14002F0C1
0x14002f038  mov     rcx, [rbp+47h+arg_28]
0x14002f03c  mov     rax, [rcx+8]
0x14002f040  mov     [rbp+47h+FileName.Buffer], rax
0x14002f044  movzx   eax, word ptr [rcx]
0x14002f047  mov     [rbp+47h+FileName.Length], ax
0x14002f04b  movzx   eax, word ptr [rcx+2]
0x14002f04f  mov     [rbp+47h+FileName.MaximumLength], ax
0x14002f053  test    r14b, r14b
0x14002f056  jz      short loc_14002F094
0x14002f058  xor     edx, edx; SourceString
0x14002f05a  lea     rcx, [rbp+47h+DestinationString]; DestinationString
0x14002f05e  call    cs:__imp_RtlInitUnicodeString
0x14002f065  nop     dword ptr [rax+rax+00h]
0x14002f06a  xor     r9d, r9d; FinalComponent
0x14002f06d  lea     r8, [rbp+47h+DestinationString]; Stream
0x14002f071  xor     edx, edx; Extension
0x14002f073  lea     rcx, [rbp+47h+FileName]; FileName
0x14002f077  call    cs:__imp_FltParseFileName
0x14002f07e  nop     dword ptr [rax+rax+00h]
0x14002f083  test    eax, eax
0x14002f085  js      short loc_14002F094
0x14002f087  movzx   eax, [rbp+47h+DestinationString.Length]
0x14002f08b  test    ax, ax
0x14002f08e  jz      short loc_14002F094
0x14002f090  sub     [rbp+47h+FileName.Length], ax
0x14002f094  mov     rax, [rbp+47h+arg_18]
0x14002f098  lea     rdx, [rsi+38h]
0x14002f09c  mov     r8, [rdi+40h]
0x14002f0a0  lea     rcx, [rbp+47h+FileName]; FileName
0x14002f0a4  mov     [rsp+0C0h+var_88], bl; char
0x14002f0a8  mov     r9, r13
0x14002f0ab  mov     [rsp+0C0h+var_90], 1; char
0x14002f0b0  mov     [rsp+0C0h+FileObject], r12; FileObject
0x14002f0b5  mov     [rsp+0C0h+var_A0], rax; __int64
0x14002f0ba  call    WcPopulateFile
0x14002f0bf  mov     ebx, eax
0x14002f0c1  lea     rcx, [rdi+48h]; RunRef
0x14002f0c5  call    cs:__imp_ExReleaseRundownProtection
0x14002f0cc  nop     dword ptr [rax+rax+00h]
0x14002f0d1  test    r14b, r14b
0x14002f0d4  jz      loc_14002F1A6
0x14002f0da  jmp     loc_14002F1B3
0x14002f0df  mov     dword ptr [rsp+0C0h+FileObject], 8; int
0x14002f0e7  mov     r9, rdi
0x14002f0ea  mov     r8, r12; Object
0x14002f0ed  mov     dword ptr [rsp+0C0h+var_A0], 2; int
0x14002f0f5  mov     rdx, r13; FltObject
0x14002f0f8  mov     rcx, r14; CallbackData
0x14002f0fb  call    WcExpandAndWait
0x14002f100  xor     r14d, r14d
0x14002f103  mov     ebx, eax
0x14002f105  test    eax, eax
0x14002f107  jns     short loc_14002F166
0x14002f109  lea     rax, WPP_RECORDER_INITIALIZED
0x14002f110  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002f117  jz      loc_14002F1B3
0x14002f11d  mov     rcx, cs:wil_details_featureDescriptors_a
0x14002f124  lea     rax, [rbp+47h+FileName]
0x14002f128  mov     [rsp+0C0h+var_80], rax
0x14002f12d  lea     r9d, [r14+25h]
0x14002f131  mov     dword ptr [rsp+0C0h+var_88], ebx
0x14002f135  lea     rax, aOnecoreBaseFsW_3; "onecore\\base\\fs\\wci\\wcifs\\expansio"...
0x14002f13c  mov     dword ptr [rsp+0C0h+var_90], 0BACh
0x14002f144  lea     r8d, [r14+0Ah]
0x14002f148  mov     rcx, [rcx+40h]
0x14002f14c  mov     dl, 2
0x14002f14e  mov     [rsp+0C0h+FileObject], rax
0x14002f153  lea     rax, WPP_c8ed118f3d633d749a651abfa78156c7_Traceguids
0x14002f15a  mov     [rsp+0C0h+var_A0], rax
0x14002f15f  call    WPP_RECORDER_SF_sDdZ
0x14002f164  jmp     short loc_14002F1B3
0x14002f166  cmp     [rbp+47h+arg_20], r14b
0x14002f16a  jnz     short loc_14002F1B3
0x14002f16c  mov     rcx, rdi
0x14002f16f  call    WcIsExpanded
0x14002f174  test    al, al
0x14002f176  jnz     short loc_14002F1AE
0x14002f178  mov     rax, [rbp+47h+arg_18]
0x14002f17c  lea     rdx, [rsi+38h]
0x14002f180  mov     r8, [rdi+40h]
0x14002f184  mov     r9, r13
0x14002f187  mov     rcx, [rbp+47h+arg_28]; FileName
0x14002f18b  mov     [rsp+0C0h+var_88], 1; char
0x14002f190  mov     [rsp+0C0h+var_90], 1; char
0x14002f195  mov     [rsp+0C0h+FileObject], r12; FileObject
0x14002f19a  mov     [rsp+0C0h+var_A0], rax; __int64
0x14002f19f  call    WcPopulateFile
0x14002f1a4  mov     ebx, eax
0x14002f1a6  cmp     ebx, 0C0000034h
0x14002f1ac  jnz     short loc_14002F1B3
0x14002f1ae  mov     ebx, 0C000003Ah
0x14002f1b3  test    rdi, rdi
0x14002f1b6  jz      short loc_14002F1C7
0x14002f1b8  mov     rcx, rdi; Context
0x14002f1bb  call    cs:__imp_FltReleaseContext
0x14002f1c2  nop     dword ptr [rax+rax+00h]
0x14002f1c7  test    rsi, rsi
0x14002f1ca  jz      short loc_14002F1DB
0x14002f1cc  mov     rcx, rsi; Context
0x14002f1cf  call    cs:__imp_FltReleaseContext
0x14002f1d6  nop     dword ptr [rax+rax+00h]
0x14002f1db  mov     eax, ebx
0x14002f1dd  add     rsp, 88h
0x14002f1e4  pop     r15
0x14002f1e6  pop     r14
0x14002f1e8  pop     r13
0x14002f1ea  pop     r12
0x14002f1ec  pop     rdi
0x14002f1ed  pop     rsi
0x14002f1ee  pop     rbx
0x14002f1ef  pop     rbp
0x14002f1f0  retn
```
