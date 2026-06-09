# Smb2CreateContinueOnOplockAck

- ea: `0x14006ade0`
- end: `0x14006af22`
- name: `Smb2CreateContinueOnOplockAck`
- size: `322`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x140007400`
- `0x140007900`
- `0x140008190`
- `0x14000f4d0`
- `0x14001ed38`
- `0x14001ffc4`
- `0x14006ade0`
- `0x14006ead0`

## import_xrefs

- `ntoskrnl!IoFreeMdl` at `0x14006ae52`
- `ntoskrnl!IoFreeMdl` at `0x14006ae52`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006ae07`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006ae07`
- `ntoskrnl!MmUnlockPages` at `0x14006ae43`
- `ntoskrnl!MmUnlockPages` at `0x14006ae43`

## string_xrefs

- `0x14006aefd`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\create.c`

## pseudocode

```c
__int64 __fastcall Smb2CreateContinueOnOplockAck(_QWORD *a1)
{
  __int64 v1; // rbp
  __int64 v3; // rdi
  void *v4; // rcx
  struct _MDL *v5; // rsi
  struct _MDL *v6; // r14
  CSHORT MdlFlags; // ax
  int BuildResponse; // esi
  __int64 v9; // r9
  __int64 v10; // rdx

  v1 = a1[15];
  v3 = a1[70];
  v4 = *(void **)(v1 + 160);
  if ( v4 )
  {
    ExFreePoolWithTag(v4, 0);
    *(_QWORD *)(v1 + 160) = 0;
  }
  v5 = *(struct _MDL **)(v1 + 8);
  if ( v5 && (v5->MdlFlags & 4) == 0 )
  {
    do
    {
      v6 = v5;
      v5 = v5->Next;
      MdlFlags = v6->MdlFlags;
      if ( (MdlFlags & 2) != 0 || (MdlFlags & 0x20) != 0 )
        MmUnlockPages(v6);
      IoFreeMdl(v6);
    }
    while ( v5 );
    *(_QWORD *)(v1 + 8) = 0;
  }
  if ( *(int *)(a1[15] + 48LL) < 0 )
  {
    Smb2CloseFile(*(_QWORD *)(v3 + 72));
    v9 = 3217;
    v10 = *(unsigned int *)(a1[15] + 48LL);
    goto LABEL_21;
  }
  if ( *(_BYTE *)(v3 + 378) )
  {
    BuildResponse = Smb2RequestOplockForResumedCreate(a1);
    if ( BuildResponse < 0 )
    {
      Smb2CloseFile(*(_QWORD *)(v3 + 72));
      v9 = 3187;
LABEL_14:
      v10 = (unsigned int)BuildResponse;
LABEL_21:
      Smb2SetError(a1, v10, "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\create.c", v9);
      return Srv2CompleteWorkItem(a1, 0);
    }
    if ( *(_BYTE *)(v3 + 381) )
    {
      Smb2RkfNotifyComplete(a1[8], *(_QWORD *)(*(_QWORD *)(v3 + 80) + 96LL));
      *(_BYTE *)(v3 + 381) = 0;
    }
  }
  BuildResponse = Smb2CreateBuildResponse(a1);
  if ( BuildResponse < 0 )
  {
    Smb2CloseFile(*(_QWORD *)(v3 + 72));
    v9 = 3207;
    goto LABEL_14;
  }
  Smb2SetSuccess(a1, 0);
  return Srv2CompleteWorkItem(a1, 0);
}

```

## disassembly

```asm
0x14006ade0  push    rbx
0x14006ade2  push    rbp
0x14006ade3  push    rsi
0x14006ade4  push    rdi
0x14006ade5  push    r14
0x14006ade7  sub     rsp, 20h
0x14006adeb  mov     rbp, [rcx+78h]
0x14006adef  mov     rbx, rcx
0x14006adf2  mov     rdi, [rcx+230h]
0x14006adf9  mov     rcx, [rbp+0A0h]; P
0x14006ae00  test    rcx, rcx
0x14006ae03  jz      short loc_14006AE1E
0x14006ae05  xor     edx, edx; Tag
0x14006ae07  call    cs:__imp_ExFreePoolWithTag
0x14006ae0e  nop     dword ptr [rax+rax+00h]
0x14006ae13  mov     qword ptr [rbp+0A0h], 0
0x14006ae1e  mov     rsi, [rbp+8]
0x14006ae22  test    rsi, rsi
0x14006ae25  jz      short loc_14006AE67
0x14006ae27  test    byte ptr [rsi+0Ah], 4
0x14006ae2b  jnz     short loc_14006AE67
0x14006ae2d  mov     r14, rsi
0x14006ae30  mov     rsi, [rsi]
0x14006ae33  movzx   eax, word ptr [r14+0Ah]
0x14006ae38  test    al, 2
0x14006ae3a  jnz     short loc_14006AE40
0x14006ae3c  test    al, 20h
0x14006ae3e  jz      short loc_14006AE4F
0x14006ae40  mov     rcx, r14; MemoryDescriptorList
0x14006ae43  call    cs:__imp_MmUnlockPages
0x14006ae4a  nop     dword ptr [rax+rax+00h]
0x14006ae4f  mov     rcx, r14; Mdl
0x14006ae52  call    cs:__imp_IoFreeMdl
0x14006ae59  nop     dword ptr [rax+rax+00h]
0x14006ae5e  test    rsi, rsi
0x14006ae61  jnz     short loc_14006AE2D
0x14006ae63  mov     [rbp+8], rsi
0x14006ae67  mov     rax, [rbx+78h]
0x14006ae6b  cmp     dword ptr [rax+30h], 0
0x14006ae6f  jl      short loc_14006AEE7
0x14006ae71  cmp     byte ptr [rdi+17Ah], 0
0x14006ae78  jz      short loc_14006AEBC
0x14006ae7a  mov     rcx, rbx
0x14006ae7d  call    Smb2RequestOplockForResumedCreate
0x14006ae82  mov     esi, eax
0x14006ae84  test    eax, eax
0x14006ae86  jns     short loc_14006AE9B
0x14006ae88  mov     rcx, [rdi+48h]
0x14006ae8c  call    Smb2CloseFile
0x14006ae91  mov     r9d, 0C73h
0x14006ae97  mov     edx, esi
0x14006ae99  jmp     short loc_14006AEFD
0x14006ae9b  cmp     byte ptr [rdi+17Dh], 0
0x14006aea2  jz      short loc_14006AEBC
0x14006aea4  mov     rdx, [rdi+50h]
0x14006aea8  mov     rcx, [rbx+40h]
0x14006aeac  mov     rdx, [rdx+60h]
0x14006aeb0  call    Smb2RkfNotifyComplete
0x14006aeb5  mov     byte ptr [rdi+17Dh], 0
0x14006aebc  mov     rcx, rbx
0x14006aebf  call    Smb2CreateBuildResponse
0x14006aec4  mov     esi, eax
0x14006aec6  test    eax, eax
0x14006aec8  jns     short loc_14006AEDB
0x14006aeca  mov     rcx, [rdi+48h]
0x14006aece  call    Smb2CloseFile
0x14006aed3  mov     r9d, 0C87h
0x14006aed9  jmp     short loc_14006AE97
0x14006aedb  xor     edx, edx
0x14006aedd  mov     rcx, rbx
0x14006aee0  call    Smb2SetSuccess
0x14006aee5  jmp     short loc_14006AF0C
0x14006aee7  mov     rcx, [rdi+48h]
0x14006aeeb  call    Smb2CloseFile
0x14006aef0  mov     rdx, [rbx+78h]
0x14006aef4  mov     r9d, 0C91h
0x14006aefa  mov     edx, [rdx+30h]
0x14006aefd  lea     r8, aOnecoreBaseFsR_19; "onecore\\base\\fs\\remotefs\\smb\\srv\\"...
0x14006af04  mov     rcx, rbx
0x14006af07  call    _Smb2SetError
0x14006af0c  xor     edx, edx
0x14006af0e  mov     rcx, rbx
0x14006af11  call    Srv2CompleteWorkItem
0x14006af16  add     rsp, 20h
0x14006af1a  pop     r14
0x14006af1c  pop     rdi
0x14006af1d  pop     rsi
0x14006af1e  pop     rbp
0x14006af1f  pop     rbx
0x14006af20  retn
```
