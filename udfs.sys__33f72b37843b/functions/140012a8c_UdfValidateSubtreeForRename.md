# UdfValidateSubtreeForRename

- ea: `0x140012a8c`
- end: `0x140012c2a`
- name: `UdfValidateSubtreeForRename`
- size: `414`
- prototype: `__int64 __fastcall(PVOID Context)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140033548`
- `0x140034450`

## callees

- `0x1400091b8`
- `0x14000cad4`
- `0x140010b14`
- `0x140012a8c`
- `0x140038724`

## import_xrefs

- `ntoskrnl!FsRtlCheckOplock` at `0x140012b81`
- `ntoskrnl!FsRtlCheckOplock` at `0x140012b81`
- `ntoskrnl!MmFlushImageSection` at `0x140012af1`
- `ntoskrnl!MmFlushImageSection` at `0x140012af1`
- `ntoskrnl!FsRtlCurrentBatchOplock` at `0x140012b13`
- `ntoskrnl!FsRtlCurrentBatchOplock` at `0x140012b13`

## pseudocode

```c
__int64 __fastcall UdfValidateSubtreeForRename(PIRP *Context, __int64 a2)
{
  __int64 v4; // rdi
  unsigned int v5; // r14d
  __int64 i; // rdx
  __int64 NextScbBottomUp; // rax
  __int64 v8; // rsi
  __int64 v9; // rbx
  __int64 NextStreamScb; // r12
  PIRP v11; // rcx
  unsigned __int64 Information; // rdx
  __int64 v13; // r9
  __int64 v15; // [rsp+68h] [rbp+10h] BYREF

  v15 = 0;
  while ( 1 )
  {
    v4 = 0;
    v5 = 0;
    for ( i = 0; ; i = v8 )
    {
      NextScbBottomUp = UdfGetNextScbBottomUp(Context, i, a2, &v15);
      v8 = NextScbBottomUp;
      if ( NextScbBottomUp == a2 )
        break;
      v9 = NextScbBottomUp;
      do
      {
        NextStreamScb = UdfGetNextStreamScb(v9);
        if ( *(_DWORD *)(v9 + 200)
          || !MmFlushImageSection((PSECTION_OBJECT_POINTERS)(*(_QWORD *)(v9 + 424) + 8LL), MmFlushForDelete) )
        {
          if ( *(_WORD *)v9 != 2356 || !FsRtlCurrentBatchOplock((POPLOCK)(v9 + 88)) )
            return 3221225506LL;
          ++v5;
          if ( !v4 )
            v4 = v9;
        }
        v9 = NextStreamScb;
      }
      while ( NextStreamScb );
    }
    v11 = Context[1];
    if ( !v4 )
    {
      v11->IoStatus.Information = 0;
      return 0;
    }
    Information = v11->IoStatus.Information;
    if ( Information )
    {
      if ( v5 >= Information )
        break;
    }
    v11->IoStatus.Information = v5;
    if ( FsRtlCheckOplock((POPLOCK)(v4 + 88), Context[1], Context, UdfOplockComplete, 0) )
    {
      if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x200) != 0 )
      {
        LOBYTE(v13) = 89;
        WPP_SF_c(
          *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
          20,
          WPP_0dbe93714b6730a9f09221a306b03890_Traceguids,
          v13);
      }
      return 259;
    }
  }
  if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x200) != 0 )
  {
    WPP_SF_(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL), 19, WPP_0dbe93714b6730a9f09221a306b03890_Traceguids);
  }
  return 3221225506LL;
}

```

## disassembly

```asm
0x140012a8c  mov     [rsp+arg_0], rbx
0x140012a91  mov     [rsp+arg_10], rbp
0x140012a96  push    rsi
0x140012a97  push    rdi
0x140012a98  push    r12
0x140012a9a  push    r14
0x140012a9c  push    r15
0x140012a9e  sub     rsp, 30h
0x140012aa2  mov     rbp, rdx
0x140012aa5  mov     [rsp+58h+arg_8], 0
0x140012aae  mov     r15, rcx
0x140012ab1  xor     edi, edi
0x140012ab3  xor     r14d, r14d
0x140012ab6  xor     edx, edx
0x140012ab8  lea     r9, [rsp+58h+arg_8]
0x140012abd  mov     r8, rbp
0x140012ac0  call    UdfGetNextScbBottomUp
0x140012ac5  mov     rsi, rax
0x140012ac8  cmp     rax, rbp
0x140012acb  jz      short loc_140012B41
0x140012acd  mov     rbx, rax
0x140012ad0  mov     rcx, rbx
0x140012ad3  call    UdfGetNextStreamScb
0x140012ad8  cmp     dword ptr [rbx+0C8h], 0
0x140012adf  mov     r12, rax
0x140012ae2  jnz     short loc_140012B01
0x140012ae4  mov     rcx, [rbx+1A8h]
0x140012aeb  xor     edx, edx; FlushType
0x140012aed  add     rcx, 8; SectionObjectPointer
0x140012af1  call    cs:__imp_MmFlushImageSection
0x140012af8  nop     dword ptr [rax+rax+00h]
0x140012afd  test    al, al
0x140012aff  jnz     short loc_140012B31
0x140012b01  mov     eax, 934h
0x140012b06  cmp     [rbx], ax
0x140012b09  jnz     loc_140012C01
0x140012b0f  lea     rcx, [rbx+58h]; Oplock
0x140012b13  call    cs:__imp_FsRtlCurrentBatchOplock
0x140012b1a  nop     dword ptr [rax+rax+00h]
0x140012b1f  test    al, al
0x140012b21  jz      loc_140012C01
0x140012b27  inc     r14d
0x140012b2a  test    rdi, rdi
0x140012b2d  cmovz   rdi, rbx
0x140012b31  mov     rbx, r12
0x140012b34  test    r12, r12
0x140012b37  jnz     short loc_140012AD0
0x140012b39  mov     rdx, rsi
0x140012b3c  jmp     loc_140012AB8
0x140012b41  mov     rcx, [r15+8]
0x140012b45  test    rdi, rdi
0x140012b48  jz      loc_140012C08
0x140012b4e  mov     rdx, [rcx+38h]
0x140012b52  test    rdx, rdx
0x140012b55  jz      short loc_140012B5F
0x140012b57  mov     eax, r14d
0x140012b5a  cmp     rax, rdx
0x140012b5d  jnb     short loc_140012BD0
0x140012b5f  mov     eax, r14d
0x140012b62  lea     r9, UdfOplockComplete; CompletionRoutine
0x140012b69  mov     [rcx+38h], rax
0x140012b6d  mov     r8, r15; Context
0x140012b70  mov     rdx, [r15+8]; Irp
0x140012b74  lea     rcx, [rdi+58h]; Oplock
0x140012b78  mov     [rsp+58h+PostIrpRoutine], 0; PostIrpRoutine
0x140012b81  call    cs:__imp_FsRtlCheckOplock
0x140012b88  nop     dword ptr [rax+rax+00h]
0x140012b8d  test    eax, eax
0x140012b8f  jz      loc_140012AB1
0x140012b95  mov     rcx, cs:WPP_GLOBAL_Control
0x140012b9c  lea     rax, WPP_GLOBAL_Control
0x140012ba3  cmp     rcx, rax
0x140012ba6  jz      short loc_140012BC9
0x140012ba8  test    dword ptr [rcx+2Ch], 200h
0x140012baf  jz      short loc_140012BC9
0x140012bb1  mov     rcx, [rcx+18h]
0x140012bb5  lea     r8, WPP_0dbe93714b6730a9f09221a306b03890_Traceguids
0x140012bbc  mov     edx, 14h
0x140012bc1  mov     r9b, 59h ; 'Y'
0x140012bc4  call    WPP_SF_c
0x140012bc9  mov     eax, 103h
0x140012bce  jmp     short loc_140012C12
0x140012bd0  mov     rcx, cs:WPP_GLOBAL_Control
0x140012bd7  lea     rax, WPP_GLOBAL_Control
0x140012bde  cmp     rcx, rax
0x140012be1  jz      short loc_140012C01
0x140012be3  test    dword ptr [rcx+2Ch], 200h
0x140012bea  jz      short loc_140012C01
0x140012bec  mov     rcx, [rcx+18h]
0x140012bf0  lea     r8, WPP_0dbe93714b6730a9f09221a306b03890_Traceguids
0x140012bf7  mov     edx, 13h
0x140012bfc  call    WPP_SF_
0x140012c01  mov     eax, 0C0000022h
0x140012c06  jmp     short loc_140012C12
0x140012c08  mov     qword ptr [rcx+38h], 0
0x140012c10  xor     eax, eax
0x140012c12  mov     rbx, [rsp+58h+arg_0]
0x140012c17  mov     rbp, [rsp+58h+arg_10]
0x140012c1c  add     rsp, 30h
0x140012c20  pop     r15
0x140012c22  pop     r14
0x140012c24  pop     r12
0x140012c26  pop     rdi
0x140012c27  pop     rsi
0x140012c28  retn
```
