# WcPreFsctlSetReparsePoint

- ea: `0x140023c40`
- end: `0x140023e8f`
- name: `WcPreFsctlSetReparsePoint`
- size: `591`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData)`
- caller_count: `1`
- callee_count: `10`
- tags: `reparse_path, loader_planting`

## callers

- `0x140023150`

## callees

- `0x140001500`
- `0x1400016f0`
- `0x140001b94`
- `0x140001bc8`
- `0x140001fd0`
- `0x1400057a0`
- `0x14001eadc`
- `0x140023840`
- `0x140023c40`
- `0x14002ee54`

## import_xrefs

- `ntoskrnl!FsRtlValidateReparsePointBuffer` at `0x140023d01`
- `ntoskrnl!FsRtlValidateReparsePointBuffer` at `0x140023d01`
- `FLTMGR!FltReleaseContext` at `0x140023e6a`
- `FLTMGR!FltReleaseContext` at `0x140023e7e`
- `FLTMGR!FltReleaseContext` at `0x140023e6a`
- `FLTMGR!FltReleaseContext` at `0x140023e7e`

## pseudocode

```c
__int64 __fastcall WcPreFsctlSetReparsePoint(PFLT_CALLBACK_DATA CallbackData, __int64 a2, __int64 a3)
{
  unsigned int v6; // ebx
  __int64 UnionContext; // r15
  int IsDirectoryEmpty; // edi
  __int64 result; // rax
  PFLT_IO_PARAMETER_BLOCK Iopb; // rax
  struct _REPARSE_DATA_BUFFER *Parameters; // rsi
  ULONG Options; // ecx
  int v13; // edx
  ULONG ReparseTag; // eax

  v6 = 1;
  UnionContext = WcGetUnionContext(CallbackData, *(_QWORD *)(a2 + 24), *(_QWORD *)(a2 + 32));
  if ( !UnionContext )
  {
    IsDirectoryEmpty = 0;
    goto LABEL_3;
  }
  Iopb = CallbackData->Iopb;
  Parameters = (struct _REPARSE_DATA_BUFFER *)Iopb->Parameters.CreatePipe.Parameters;
  if ( !Parameters )
  {
    IsDirectoryEmpty = -1073741306;
LABEL_20:
    v6 = 4;
    goto LABEL_21;
  }
  Options = Iopb->Parameters.Create.Options;
  if ( Iopb->Parameters.Read.ByteOffset.LowPart == 590860 )
  {
    if ( Options < 0x20 )
    {
      IsDirectoryEmpty = -1073741789;
      goto LABEL_20;
    }
    Parameters = (struct _REPARSE_DATA_BUFFER *)((char *)Parameters + 32);
    Options -= 32;
  }
  IsDirectoryEmpty = FsRtlValidateReparsePointBuffer(Options, Parameters);
  if ( IsDirectoryEmpty < 0 )
    goto LABEL_20;
  ReparseTag = Parameters->ReparseTag;
  if ( Parameters->ReparseTag == *(_DWORD *)(UnionContext + 36) || ReparseTag == -1610612705 )
  {
    IsDirectoryEmpty = -1073741637;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_sDDd(
        WPP_GLOBAL_Control->DeviceExtension,
        v13,
        7,
        15,
        (__int64)WPP_c070de6cd2643f4183d5a0f659a39519_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\wcifs\\fsctrl.c",
        165,
        ReparseTag,
        187);
    goto LABEL_20;
  }
  if ( (unsigned __int8)WcGetContextFileObject(*(PFLT_INSTANCE *)(a2 + 24), *(PFILE_OBJECT *)(a2 + 32)) )
  {
    if ( (unsigned __int8)WcIsPlaceHolderDirectory(0, 0) && (unsigned __int8)WcIsSourcedStream(0) )
    {
      IsDirectoryEmpty = WcIsDirectoryEmpty(*(PFLT_INSTANCE *)(a2 + 24), *(PFILE_OBJECT *)(a2 + 32));
      if ( IsDirectoryEmpty >= 0 )
        IsDirectoryEmpty = -1073741567;
      v6 = 4;
    }
    else if ( (unsigned __int8)WcIsPlaceHolderStream(0, 0) )
    {
      v6 = WcSynchronizeExpansionPreopWithReason(CallbackData, 15, a3);
    }
  }
LABEL_3:
  if ( UnionContext )
LABEL_21:
    WcReleaseUnionContext(UnionContext);
  result = v6;
  CallbackData->IoStatus.Status = IsDirectoryEmpty;
  return result;
}

```

## disassembly

```asm
0x140023c40  mov     rax, rsp
0x140023c43  mov     [rax+18h], rbx
0x140023c47  push    rbp
0x140023c48  push    rsi
0x140023c49  push    rdi
0x140023c4a  push    r12
0x140023c4c  push    r13
0x140023c4e  push    r14
0x140023c50  push    r15
0x140023c52  sub     rsp, 50h
0x140023c56  mov     r12, r8
0x140023c59  mov     byte ptr [rax+8], 0
0x140023c5d  mov     r8, [rdx+20h]
0x140023c61  mov     r14, rdx
0x140023c64  mov     rdx, [rdx+18h]
0x140023c68  xor     ebp, ebp
0x140023c6a  xor     esi, esi
0x140023c6c  mov     [rax+10h], rbp
0x140023c70  mov     r13, rcx
0x140023c73  mov     [rax+20h], rsi
0x140023c77  mov     ebx, 1
0x140023c7c  call    WcGetUnionContext
0x140023c81  mov     r15, rax
0x140023c84  test    rax, rax
0x140023c87  jnz     short loc_140023CC5
0x140023c89  xor     edi, edi
0x140023c8b  test    rbp, rbp
0x140023c8e  jnz     loc_140023E67
0x140023c94  test    rsi, rsi
0x140023c97  jnz     loc_140023E7B
0x140023c9d  test    r15, r15
0x140023ca0  jnz     loc_140023E05
0x140023ca6  mov     eax, ebx
0x140023ca8  mov     [r13+18h], edi
0x140023cac  mov     rbx, [rsp+88h+arg_10]
0x140023cb4  add     rsp, 50h
0x140023cb8  pop     r15
0x140023cba  pop     r14
0x140023cbc  pop     r13
0x140023cbe  pop     r12
0x140023cc0  pop     rdi
0x140023cc1  pop     rsi
0x140023cc2  pop     rbp
0x140023cc3  retn
0x140023cc5  mov     rax, [r13+10h]
0x140023cc9  mov     rsi, [rax+30h]
0x140023ccd  test    rsi, rsi
0x140023cd0  jnz     short loc_140023CDC
0x140023cd2  mov     edi, 0C0000206h
0x140023cd7  jmp     loc_140023E00
0x140023cdc  cmp     dword ptr [rax+28h], 9040Ch
0x140023ce3  mov     ecx, [rax+20h]
0x140023ce6  jnz     short loc_140023CFE
0x140023ce8  cmp     ecx, 20h ; ' '
0x140023ceb  jnb     short loc_140023CF7
0x140023ced  mov     edi, 0C0000023h
0x140023cf2  jmp     loc_140023E00
0x140023cf7  add     rsi, 20h ; ' '
0x140023cfb  add     ecx, 0FFFFFFE0h; BufferLength
0x140023cfe  mov     rdx, rsi; ReparseBuffer
0x140023d01  call    cs:__imp_FsRtlValidateReparsePointBuffer
0x140023d08  nop     dword ptr [rax+rax+00h]
0x140023d0d  mov     edi, eax
0x140023d0f  test    eax, eax
0x140023d11  js      loc_140023E00
0x140023d17  mov     eax, [rsi]
0x140023d19  cmp     eax, [r15+24h]
0x140023d1d  jz      loc_140023E4D
0x140023d23  cmp     eax, 0A000001Fh
0x140023d28  jz      loc_140023E4D
0x140023d2e  mov     rdx, [r14+20h]; FileObject
0x140023d32  lea     r9, [rsp+88h+arg_18]
0x140023d3a  mov     rcx, [r14+18h]; Instance
0x140023d3e  lea     r8, [rsp+88h+arg_8]
0x140023d46  call    WcGetContextFileObject
0x140023d4b  mov     rsi, [rsp+88h+arg_18]
0x140023d53  mov     rbp, [rsp+88h+arg_8]
0x140023d5b  test    al, al
0x140023d5d  jz      loc_140023C8B
0x140023d63  mov     rdx, rsi
0x140023d66  mov     rcx, rbp
0x140023d69  call    WcIsPlaceHolderDirectory
0x140023d6e  test    al, al
0x140023d70  jz      loc_140023E12
0x140023d76  mov     rcx, rsi
0x140023d79  call    WcIsSourcedStream
0x140023d7e  test    al, al
0x140023d80  jz      loc_140023E12
0x140023d86  mov     rdx, [r14+20h]; FileObject
0x140023d8a  lea     r8, [rsp+88h+arg_0]
0x140023d92  mov     rcx, [r14+18h]; Instance
0x140023d96  call    WcIsDirectoryEmpty
0x140023d9b  mov     edi, eax
0x140023d9d  test    eax, eax
0x140023d9f  js      short loc_140023DB4
0x140023da1  cmp     [rsp+88h+arg_0], 0
0x140023da9  jnz     loc_140023C8B
0x140023daf  mov     edi, 0C0000101h
0x140023db4  mov     ebx, 4
0x140023db9  jmp     loc_140023C8B
0x140023dbe  mov     rcx, cs:WPP_GLOBAL_Control
0x140023dc5  mov     r9d, 0Fh
0x140023dcb  mov     [rsp+88h+var_48], edi
0x140023dcf  mov     [rsp+88h+var_50], eax
0x140023dd3  lea     rax, aOnecoreBaseFsW_2; "onecore\\base\\fs\\wci\\wcifs\\fsctrl.c"
0x140023dda  mov     [rsp+88h+var_58], 1A5h
0x140023de2  mov     rcx, [rcx+40h]
0x140023de6  lea     r8d, [r9-8]
0x140023dea  mov     [rsp+88h+var_60], rax
0x140023def  lea     rax, WPP_c070de6cd2643f4183d5a0f659a39519_Traceguids
0x140023df6  mov     qword ptr [rsp+88h+var_68], rax
0x140023dfb  call    WPP_RECORDER_SF_sDDd
0x140023e00  mov     ebx, 4
0x140023e05  mov     rcx, r15
0x140023e08  call    WcReleaseUnionContext
0x140023e0d  jmp     loc_140023CA6
0x140023e12  mov     rdx, rsi
0x140023e15  mov     rcx, rbp
0x140023e18  call    WcIsPlaceHolderStream
0x140023e1d  test    al, al
0x140023e1f  jz      loc_140023C8B
0x140023e25  mov     [rsp+88h+var_60], r12; __int64
0x140023e2a  mov     r9d, 3
0x140023e30  mov     r8d, ebx
0x140023e33  mov     [rsp+88h+var_68], 0Fh; int
0x140023e3b  mov     rdx, r14
0x140023e3e  mov     rcx, r13; CallbackData
0x140023e41  call    WcSynchronizeExpansionPreopWithReason
0x140023e46  mov     ebx, eax
0x140023e48  jmp     loc_140023C8B
0x140023e4d  mov     edi, 0C00000BBh
0x140023e52  lea     rcx, WPP_RECORDER_INITIALIZED
0x140023e59  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140023e60  jz      short loc_140023E00
0x140023e62  jmp     loc_140023DBE
0x140023e67  mov     rcx, rbp; Context
0x140023e6a  call    cs:__imp_FltReleaseContext
0x140023e71  nop     dword ptr [rax+rax+00h]
0x140023e76  jmp     loc_140023C94
0x140023e7b  mov     rcx, rsi; Context
0x140023e7e  call    cs:__imp_FltReleaseContext
0x140023e85  nop     dword ptr [rax+rax+00h]
0x140023e8a  jmp     loc_140023C9D
```
