# WcPreFsctlSetReparsePoint

- ea: `0x140023c90`
- end: `0x140023edf`
- name: `WcPreFsctlSetReparsePoint`
- size: `591`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData, __int64, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `reparse_path, loader_planting`

## callers

- `0x1400231a0`

## callees

- `0x140001500`
- `0x1400016f0`
- `0x140001b94`
- `0x140001bc8`
- `0x140001fd0`
- `0x1400057a0`
- `0x14001eadc`
- `0x140023890`
- `0x140023c90`
- `0x14002eea4`

## import_xrefs

- `ntoskrnl!FsRtlValidateReparsePointBuffer` at `0x140023d51`
- `ntoskrnl!FsRtlValidateReparsePointBuffer` at `0x140023d51`
- `FLTMGR!FltReleaseContext` at `0x140023eba`
- `FLTMGR!FltReleaseContext` at `0x140023ece`
- `FLTMGR!FltReleaseContext` at `0x140023eba`
- `FLTMGR!FltReleaseContext` at `0x140023ece`

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
        wil_details_featureDescriptors_a->DeviceExtension,
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
0x140023c90  mov     rax, rsp
0x140023c93  mov     [rax+18h], rbx
0x140023c97  push    rbp
0x140023c98  push    rsi
0x140023c99  push    rdi
0x140023c9a  push    r12
0x140023c9c  push    r13
0x140023c9e  push    r14
0x140023ca0  push    r15
0x140023ca2  sub     rsp, 50h
0x140023ca6  mov     r12, r8
0x140023ca9  mov     byte ptr [rax+8], 0
0x140023cad  mov     r8, [rdx+20h]
0x140023cb1  mov     r14, rdx
0x140023cb4  mov     rdx, [rdx+18h]
0x140023cb8  xor     ebp, ebp
0x140023cba  xor     esi, esi
0x140023cbc  mov     [rax+10h], rbp
0x140023cc0  mov     r13, rcx
0x140023cc3  mov     [rax+20h], rsi
0x140023cc7  mov     ebx, 1
0x140023ccc  call    WcGetUnionContext
0x140023cd1  mov     r15, rax
0x140023cd4  test    rax, rax
0x140023cd7  jnz     short loc_140023D15
0x140023cd9  xor     edi, edi
0x140023cdb  test    rbp, rbp
0x140023cde  jnz     loc_140023EB7
0x140023ce4  test    rsi, rsi
0x140023ce7  jnz     loc_140023ECB
0x140023ced  test    r15, r15
0x140023cf0  jnz     loc_140023E55
0x140023cf6  mov     eax, ebx
0x140023cf8  mov     [r13+18h], edi
0x140023cfc  mov     rbx, [rsp+88h+arg_10]
0x140023d04  add     rsp, 50h
0x140023d08  pop     r15
0x140023d0a  pop     r14
0x140023d0c  pop     r13
0x140023d0e  pop     r12
0x140023d10  pop     rdi
0x140023d11  pop     rsi
0x140023d12  pop     rbp
0x140023d13  retn
0x140023d15  mov     rax, [r13+10h]
0x140023d19  mov     rsi, [rax+30h]
0x140023d1d  test    rsi, rsi
0x140023d20  jnz     short loc_140023D2C
0x140023d22  mov     edi, 0C0000206h
0x140023d27  jmp     loc_140023E50
0x140023d2c  cmp     dword ptr [rax+28h], 9040Ch
0x140023d33  mov     ecx, [rax+20h]
0x140023d36  jnz     short loc_140023D4E
0x140023d38  cmp     ecx, 20h ; ' '
0x140023d3b  jnb     short loc_140023D47
0x140023d3d  mov     edi, 0C0000023h
0x140023d42  jmp     loc_140023E50
0x140023d47  add     rsi, 20h ; ' '
0x140023d4b  add     ecx, 0FFFFFFE0h; BufferLength
0x140023d4e  mov     rdx, rsi; ReparseBuffer
0x140023d51  call    cs:__imp_FsRtlValidateReparsePointBuffer
0x140023d58  nop     dword ptr [rax+rax+00h]
0x140023d5d  mov     edi, eax
0x140023d5f  test    eax, eax
0x140023d61  js      loc_140023E50
0x140023d67  mov     eax, [rsi]
0x140023d69  cmp     eax, [r15+24h]
0x140023d6d  jz      loc_140023E9D
0x140023d73  cmp     eax, 0A000001Fh
0x140023d78  jz      loc_140023E9D
0x140023d7e  mov     rdx, [r14+20h]; FileObject
0x140023d82  lea     r9, [rsp+88h+arg_18]
0x140023d8a  mov     rcx, [r14+18h]; Instance
0x140023d8e  lea     r8, [rsp+88h+arg_8]
0x140023d96  call    WcGetContextFileObject
0x140023d9b  mov     rsi, [rsp+88h+arg_18]
0x140023da3  mov     rbp, [rsp+88h+arg_8]
0x140023dab  test    al, al
0x140023dad  jz      loc_140023CDB
0x140023db3  mov     rdx, rsi
0x140023db6  mov     rcx, rbp
0x140023db9  call    WcIsPlaceHolderDirectory
0x140023dbe  test    al, al
0x140023dc0  jz      loc_140023E62
0x140023dc6  mov     rcx, rsi
0x140023dc9  call    WcIsSourcedStream
0x140023dce  test    al, al
0x140023dd0  jz      loc_140023E62
0x140023dd6  mov     rdx, [r14+20h]; FileObject
0x140023dda  lea     r8, [rsp+88h+arg_0]
0x140023de2  mov     rcx, [r14+18h]; Instance
0x140023de6  call    WcIsDirectoryEmpty
0x140023deb  mov     edi, eax
0x140023ded  test    eax, eax
0x140023def  js      short loc_140023E04
0x140023df1  cmp     [rsp+88h+arg_0], 0
0x140023df9  jnz     loc_140023CDB
0x140023dff  mov     edi, 0C0000101h
0x140023e04  mov     ebx, 4
0x140023e09  jmp     loc_140023CDB
0x140023e0e  mov     rcx, cs:wil_details_featureDescriptors_a
0x140023e15  mov     r9d, 0Fh
0x140023e1b  mov     [rsp+88h+var_48], edi
0x140023e1f  mov     [rsp+88h+var_50], eax
0x140023e23  lea     rax, aOnecoreBaseFsW_2; "onecore\\base\\fs\\wci\\wcifs\\fsctrl.c"
0x140023e2a  mov     [rsp+88h+var_58], 1A5h
0x140023e32  mov     rcx, [rcx+40h]
0x140023e36  lea     r8d, [r9-8]
0x140023e3a  mov     [rsp+88h+var_60], rax
0x140023e3f  lea     rax, WPP_c070de6cd2643f4183d5a0f659a39519_Traceguids
0x140023e46  mov     qword ptr [rsp+88h+var_68], rax
0x140023e4b  call    WPP_RECORDER_SF_sDDd
0x140023e50  mov     ebx, 4
0x140023e55  mov     rcx, r15
0x140023e58  call    WcReleaseUnionContext
0x140023e5d  jmp     loc_140023CF6
0x140023e62  mov     rdx, rsi
0x140023e65  mov     rcx, rbp
0x140023e68  call    WcIsPlaceHolderStream
0x140023e6d  test    al, al
0x140023e6f  jz      loc_140023CDB
0x140023e75  mov     [rsp+88h+var_60], r12; __int64
0x140023e7a  mov     r9d, 3
0x140023e80  mov     r8d, ebx
0x140023e83  mov     [rsp+88h+var_68], 0Fh; int
0x140023e8b  mov     rdx, r14
0x140023e8e  mov     rcx, r13; CallbackData
0x140023e91  call    WcSynchronizeExpansionPreopWithReason
0x140023e96  mov     ebx, eax
0x140023e98  jmp     loc_140023CDB
0x140023e9d  mov     edi, 0C00000BBh
0x140023ea2  lea     rcx, WPP_RECORDER_INITIALIZED
0x140023ea9  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140023eb0  jz      short loc_140023E50
0x140023eb2  jmp     loc_140023E0E
0x140023eb7  mov     rcx, rbp; Context
0x140023eba  call    cs:__imp_FltReleaseContext
0x140023ec1  nop     dword ptr [rax+rax+00h]
0x140023ec6  jmp     loc_140023CE4
0x140023ecb  mov     rcx, rsi; Context
0x140023ece  call    cs:__imp_FltReleaseContext
0x140023ed5  nop     dword ptr [rax+rax+00h]
0x140023eda  jmp     loc_140023CED
```
