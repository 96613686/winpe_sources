# Smb2CreateEcps

- ea: `0x14007a240`
- end: `0x14007a630`
- name: `Smb2CreateEcps`
- size: `1008`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `reparse_path`

## callers

- `0x14006fc24`
- `0x140079c30`

## callees

- `0x1400149e0`
- `0x140022958`
- `0x140033b84`
- `0x14007a240`
- `0x14007a640`

## import_xrefs

- `ntoskrnl!FsRtlFreeExtraCreateParameterList` at `0x14007a42e`
- `ntoskrnl!FsRtlFreeExtraCreateParameterList` at `0x14007a42e`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x14007a569`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x14007a602`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x14007a569`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x14007a602`
- `ntoskrnl!FsRtlFreeExtraCreateParameter` at `0x14007a3b0`
- `ntoskrnl!FsRtlFreeExtraCreateParameter` at `0x14007a3ed`
- `ntoskrnl!FsRtlFreeExtraCreateParameter` at `0x14007a3b0`
- `ntoskrnl!FsRtlFreeExtraCreateParameter` at `0x14007a3ed`
- `ntoskrnl!FsRtlInsertExtraCreateParameter` at `0x14007a340`
- `ntoskrnl!FsRtlInsertExtraCreateParameter` at `0x14007a442`
- `ntoskrnl!FsRtlInsertExtraCreateParameter` at `0x14007a340`
- `ntoskrnl!FsRtlInsertExtraCreateParameter` at `0x14007a442`
- `ntoskrnl!FsRtlAllocateExtraCreateParameterList` at `0x14007a27a`
- `ntoskrnl!FsRtlAllocateExtraCreateParameterList` at `0x14007a27a`
- `ntoskrnl!FsRtlAllocateExtraCreateParameter` at `0x14007a2dd`
- `ntoskrnl!FsRtlAllocateExtraCreateParameter` at `0x14007a384`
- `ntoskrnl!FsRtlAllocateExtraCreateParameter` at `0x14007a2dd`
- `ntoskrnl!FsRtlAllocateExtraCreateParameter` at `0x14007a384`

## pseudocode

```c
__int64 __fastcall Smb2CreateEcps(__int64 a1)
{
  __int64 v1; // rsi
  char v2; // bp
  PECP_LIST *v4; // rdi
  NTSTATUS ParameterList; // ebx
  struct _ECP_LIST *v6; // r12
  __int64 v7; // r15
  NTSTATUS Parameter; // r15d
  struct _ECP_LIST *v9; // r8
  PDEVICE_OBJECT v10; // rcx
  __int64 v11; // rdx
  _BYTE *v13; // rdx
  __int64 v14; // rax
  __int64 v15; // rcx
  __int64 v16; // rax
  __int64 v17; // rax
  bool v18; // zf
  _BYTE *v19; // rax
  PVOID EcpContext; // [rsp+70h] [rbp+8h] BYREF
  PVOID v21; // [rsp+78h] [rbp+10h] BYREF

  v1 = *(_QWORD *)(a1 + 560);
  v2 = 0;
  v21 = 0;
  v4 = (PECP_LIST *)(v1 + 320);
  if ( !*(_QWORD *)(v1 + 320) )
  {
    ParameterList = FsRtlAllocateExtraCreateParameterList(0, (PECP_LIST *)(v1 + 320));
    if ( ParameterList < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_qD(
          WPP_GLOBAL_Control->AttachedDevice,
          59,
          WPP_1eeac08a4da9393ddade0ba3ac297e5e_Traceguids,
          a1,
          ParameterList);
      }
      return (unsigned int)ParameterList;
    }
    v2 = 1;
  }
  if ( *(_BYTE *)(v1 + 306) )
  {
    if ( *(_QWORD *)(v1 + 104) )
    {
      v6 = *v4;
      v7 = *(_QWORD *)(a1 + 560);
      EcpContext = 0;
      ParameterList = FsRtlAllocateExtraCreateParameter(
                        &GUID_ECP_DUAL_OPLOCK_KEY,
                        0x24u,
                        0,
                        0,
                        0x5324534Cu,
                        &EcpContext);
      if ( ParameterList < 0 )
        goto LABEL_21;
      *((_OWORD *)EcpContext + 1) = *(_OWORD *)(*(_QWORD *)(v7 + 104) + 80LL);
      *((_BYTE *)EcpContext + 33) = 1;
      *((_BYTE *)EcpContext + 32) = 0;
      if ( *(_BYTE *)(v7 + 301) )
      {
        *(_OWORD *)EcpContext = *(_OWORD *)(v7 + 280);
        *((_BYTE *)EcpContext + 32) = 1;
      }
      Parameter = FsRtlInsertExtraCreateParameter(v6, EcpContext);
      if ( Parameter < 0 )
      {
        FsRtlFreeExtraCreateParameter(EcpContext);
        ParameterList = 0;
        if ( Parameter != -1073741811 )
          ParameterList = Parameter;
        if ( ParameterList < 0 )
        {
LABEL_21:
          v10 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) )
          {
            v11 = 60;
            goto LABEL_69;
          }
LABEL_22:
          if ( v2 )
          {
            FsRtlFreeExtraCreateParameterList(*v4);
            *v4 = 0;
          }
          return (unsigned int)ParameterList;
        }
      }
    }
    else
    {
      *(_BYTE *)(v1 + 306) = 0;
    }
  }
  if ( v2 || FsRtlFindExtraCreateParameter(*v4, &GUID_ECP_SRV_OPEN, 0, 0) < 0 )
  {
    ParameterList = FsRtlAllocateExtraCreateParameter(&GUID_ECP_SRV_OPEN, 0x20u, 0, 0, 0x5324534Cu, &v21);
    if ( ParameterList < 0 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) == 0
        || !BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        goto LABEL_22;
      }
      v11 = 61;
    }
    else
    {
      v9 = *v4;
      if ( *v4 && (v13 = v21) != 0 )
      {
        v14 = *(_QWORD *)(a1 + 96);
        if ( !v14 )
          goto LABEL_68;
        v15 = *(_QWORD *)(a1 + 560);
        *((_QWORD *)v21 + 1) = v14 + 216;
        v16 = *(_QWORD *)(v15 + 56);
        if ( !v16 )
          goto LABEL_68;
        v17 = *(_QWORD *)(v16 + 96);
        if ( !v17 )
          goto LABEL_68;
        *(_QWORD *)v13 = v17 + 72;
        v13[16] = *(_DWORD *)(a1 + 72) == 1;
        v18 = *(_DWORD *)(a1 + 72) == 1;
        v13[17] = 1;
        *((_WORD *)v13 + 10) = 2;
        v13[18] = v18;
        v19 = *(_BYTE **)(a1 + 64);
        if ( v19 )
        {
          switch ( *v19 )
          {
            case 0:
              *((_DWORD *)v13 + 6) = 1;
              break;
            case 1:
              *((_DWORD *)v13 + 6) = 2;
              break;
            case 2:
              *((_DWORD *)v13 + 6) = 3;
              break;
            case 3:
              *((_DWORD *)v13 + 6) = 4;
              break;
            case 4:
              *((_DWORD *)v13 + 6) = 6;
              break;
            case 5:
              *((_DWORD *)v13 + 6) = 7;
              break;
            default:
              *((_DWORD *)v13 + 6) = 0;
              break;
          }
          ParameterList = FsRtlInsertExtraCreateParameter(v9, v13);
          if ( ParameterList >= 0 )
            goto LABEL_25;
        }
        else
        {
LABEL_68:
          ParameterList = -1073741595;
        }
      }
      else
      {
        ParameterList = -1073741811;
      }
      FsRtlFreeExtraCreateParameter(v21);
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) == 0
        || !BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        goto LABEL_22;
      }
      v11 = 62;
    }
LABEL_69:
    WPP_SF_qD(v10->AttachedDevice, v11, WPP_1eeac08a4da9393ddade0ba3ac297e5e_Traceguids, a1, ParameterList);
    goto LABEL_22;
  }
LABEL_25:
  ParameterList = Smb2CreateStopOnSymlinkEcp(v1 + 320);
  if ( ParameterList < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      v11 = 63;
      goto LABEL_69;
    }
    goto LABEL_22;
  }
  ParameterList = Smb2CreateOpenParametersEcp(*v4);
  if ( ParameterList < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      v11 = 64;
      goto LABEL_69;
    }
    goto LABEL_22;
  }
  if ( (*(_BYTE *)(v1 + 379) || *(_BYTE *)(v1 + 382)) && FsRtlFindExtraCreateParameter(*v4, &Smb2RkfGuidEcpIn, 0, 0) < 0 )
  {
    ParameterList = SrvAllocateRkfEcp(a1, *v4);
    if ( ParameterList < 0 )
      goto LABEL_22;
  }
  return (unsigned int)ParameterList;
}

```

## disassembly

```asm
0x14007a240  mov     [rsp+arg_10], rbx
0x14007a245  push    rbp
0x14007a246  push    rsi
0x14007a247  push    rdi
0x14007a248  push    r12
0x14007a24a  push    r13
0x14007a24c  push    r14
0x14007a24e  push    r15
0x14007a250  sub     rsp, 30h
0x14007a254  mov     rsi, [rcx+230h]
0x14007a25b  xor     r13d, r13d
0x14007a25e  xor     bpl, bpl
0x14007a261  mov     [rsp+68h+arg_8], r13
0x14007a266  mov     r14, rcx
0x14007a269  lea     rdi, [rsi+140h]
0x14007a270  cmp     [rdi], r13
0x14007a273  jnz     short loc_14007A293
0x14007a275  mov     rdx, rdi; EcpList
0x14007a278  xor     ecx, ecx; Flags
0x14007a27a  call    cs:__imp_FsRtlAllocateExtraCreateParameterList
0x14007a281  nop     dword ptr [rax+rax+00h]
0x14007a286  mov     ebx, eax
0x14007a288  test    eax, eax
0x14007a28a  js      loc_14007A4E9
0x14007a290  mov     bpl, 1
0x14007a293  cmp     [rsi+132h], r13b
0x14007a29a  jz      loc_14007A357
0x14007a2a0  cmp     [rsi+68h], r13
0x14007a2a4  jz      loc_14007A54D
0x14007a2aa  mov     r12, [rdi]
0x14007a2ad  lea     rax, [rsp+68h+arg_0]
0x14007a2b2  mov     r15, [r14+230h]
0x14007a2b9  lea     rcx, GUID_ECP_DUAL_OPLOCK_KEY; EcpType
0x14007a2c0  mov     [rsp+68h+EcpContext], rax; EcpContext
0x14007a2c5  xor     r9d, r9d; CleanupCallback
0x14007a2c8  xor     r8d, r8d; Flags
0x14007a2cb  mov     [rsp+68h+PoolTag], 5324534Ch; PoolTag
0x14007a2d3  mov     edx, 24h ; '$'; SizeOfContext
0x14007a2d8  mov     [rsp+68h+arg_0], r13
0x14007a2dd  call    cs:__imp_FsRtlAllocateExtraCreateParameter
0x14007a2e4  nop     dword ptr [rax+rax+00h]
0x14007a2e9  mov     ebx, eax
0x14007a2eb  test    eax, eax
0x14007a2ed  js      loc_14007A40F
0x14007a2f3  mov     rax, [r15+68h]
0x14007a2f7  mov     rcx, [rsp+68h+arg_0]
0x14007a2fc  movups  xmm0, xmmword ptr [rax+50h]
0x14007a300  movups  xmmword ptr [rcx+10h], xmm0
0x14007a304  mov     rax, [rsp+68h+arg_0]
0x14007a309  mov     byte ptr [rax+21h], 1
0x14007a30d  mov     rax, [rsp+68h+arg_0]
0x14007a312  mov     [rax+20h], r13b
0x14007a316  cmp     [r15+12Dh], r13b
0x14007a31d  jz      short loc_14007A338
0x14007a31f  mov     rax, [rsp+68h+arg_0]
0x14007a324  movups  xmm0, xmmword ptr [r15+118h]
0x14007a32c  movups  xmmword ptr [rax], xmm0
0x14007a32f  mov     rax, [rsp+68h+arg_0]
0x14007a334  mov     byte ptr [rax+20h], 1
0x14007a338  mov     rdx, [rsp+68h+arg_0]; EcpContext
0x14007a33d  mov     rcx, r12; EcpList
0x14007a340  call    cs:__imp_FsRtlInsertExtraCreateParameter
0x14007a347  nop     dword ptr [rax+rax+00h]
0x14007a34c  mov     r15d, eax
0x14007a34f  test    eax, eax
0x14007a351  js      loc_14007A3E8
0x14007a357  test    bpl, bpl
0x14007a35a  jz      loc_14007A559
0x14007a360  lea     rax, [rsp+68h+arg_8]
0x14007a365  xor     r9d, r9d; CleanupCallback
0x14007a368  mov     [rsp+68h+EcpContext], rax; EcpContext
0x14007a36d  lea     rcx, GUID_ECP_SRV_OPEN; EcpType
0x14007a374  xor     r8d, r8d; Flags
0x14007a377  mov     [rsp+68h+PoolTag], 5324534Ch; PoolTag
0x14007a37f  mov     edx, 20h ; ' '; SizeOfContext
0x14007a384  call    cs:__imp_FsRtlAllocateExtraCreateParameter
0x14007a38b  nop     dword ptr [rax+rax+00h]
0x14007a390  mov     ebx, eax
0x14007a392  test    eax, eax
0x14007a394  js      loc_14007A4B1
0x14007a39a  mov     r8, [rdi]
0x14007a39d  test    r8, r8
0x14007a3a0  jnz     loc_14009802A
0x14007a3a6  mov     ebx, 0C000000Dh
0x14007a3ab  mov     rcx, [rsp+68h+arg_8]; EcpContext
0x14007a3b0  call    cs:__imp_FsRtlFreeExtraCreateParameter
0x14007a3b7  nop     dword ptr [rax+rax+00h]
0x14007a3bc  mov     rcx, cs:WPP_GLOBAL_Control
0x14007a3c3  lea     rax, WPP_GLOBAL_Control
0x14007a3ca  cmp     rcx, rax
0x14007a3cd  jz      short loc_14007A426
0x14007a3cf  test    dword ptr [rcx+2Ch], 100000h
0x14007a3d6  jz      short loc_14007A426
0x14007a3d8  cmp     byte ptr [rcx+29h], 1
0x14007a3dc  jb      short loc_14007A426
0x14007a3de  mov     edx, 3Eh ; '>'
0x14007a3e3  jmp     loc_14009811D
0x14007a3e8  mov     rcx, [rsp+68h+arg_0]; EcpContext
0x14007a3ed  call    cs:__imp_FsRtlFreeExtraCreateParameter
0x14007a3f4  nop     dword ptr [rax+rax+00h]
0x14007a3f9  cmp     r15d, 0C000000Dh
0x14007a400  mov     ebx, r13d
0x14007a403  cmovnz  ebx, r15d
0x14007a407  test    ebx, ebx
0x14007a409  jns     loc_14007A357
0x14007a40f  mov     rcx, cs:WPP_GLOBAL_Control
0x14007a416  lea     rax, WPP_GLOBAL_Control
0x14007a41d  cmp     rcx, rax
0x14007a420  jnz     loc_14007A52C
0x14007a426  test    bpl, bpl
0x14007a429  jz      short loc_14007A496
0x14007a42b  mov     rcx, [rdi]; EcpList
0x14007a42e  call    cs:__imp_FsRtlFreeExtraCreateParameterList
0x14007a435  nop     dword ptr [rax+rax+00h]
0x14007a43a  mov     [rdi], r13
0x14007a43d  jmp     short loc_14007A496
0x14007a43f  mov     rcx, r8; EcpList
0x14007a442  call    cs:__imp_FsRtlInsertExtraCreateParameter
0x14007a449  nop     dword ptr [rax+rax+00h]
0x14007a44e  mov     ebx, eax
0x14007a450  test    eax, eax
0x14007a452  js      loc_14007A3AB
0x14007a458  mov     rcx, rdi
0x14007a45b  call    Smb2CreateStopOnSymlinkEcp
0x14007a460  mov     ebx, eax
0x14007a462  test    eax, eax
0x14007a464  js      loc_14007A582
0x14007a46a  mov     rcx, [rdi]; EcpList
0x14007a46d  call    Smb2CreateOpenParametersEcp
0x14007a472  mov     ebx, eax
0x14007a474  test    eax, eax
0x14007a476  js      loc_14007A5BA
0x14007a47c  cmp     [rsi+17Bh], r13b
0x14007a483  jnz     loc_14007A5F2
0x14007a489  cmp     [rsi+17Eh], r13b
0x14007a490  jnz     loc_14007A5F2
0x14007a496  mov     eax, ebx
0x14007a498  mov     rbx, [rsp+68h+arg_10]
0x14007a4a0  add     rsp, 30h
0x14007a4a4  pop     r15
0x14007a4a6  pop     r14
0x14007a4a8  pop     r13
0x14007a4aa  pop     r12
0x14007a4ac  pop     rdi
0x14007a4ad  pop     rsi
0x14007a4ae  pop     rbp
0x14007a4af  retn
0x14007a4b1  mov     rcx, cs:WPP_GLOBAL_Control
0x14007a4b8  lea     rax, WPP_GLOBAL_Control
0x14007a4bf  cmp     rcx, rax
0x14007a4c2  jz      loc_14007A426
0x14007a4c8  test    dword ptr [rcx+2Ch], 100000h
0x14007a4cf  jz      loc_14007A426
0x14007a4d5  cmp     byte ptr [rcx+29h], 1
0x14007a4d9  jb      loc_14007A426
0x14007a4df  mov     edx, 3Dh ; '='
0x14007a4e4  jmp     loc_14009811D
0x14007a4e9  mov     rcx, cs:WPP_GLOBAL_Control
0x14007a4f0  lea     rax, WPP_GLOBAL_Control
0x14007a4f7  cmp     rcx, rax
0x14007a4fa  jz      short loc_14007A496
0x14007a4fc  test    dword ptr [rcx+2Ch], 100000h
0x14007a503  jz      short loc_14007A496
0x14007a505  cmp     byte ptr [rcx+29h], 1
0x14007a509  jb      short loc_14007A496
0x14007a50b  mov     rcx, [rcx+18h]
0x14007a50f  lea     r8, WPP_1eeac08a4da9393ddade0ba3ac297e5e_Traceguids
0x14007a516  mov     edx, 3Bh ; ';'
0x14007a51b  mov     [rsp+68h+PoolTag], ebx
0x14007a51f  mov     r9, r14
0x14007a522  call    WPP_SF_qD
0x14007a527  jmp     loc_14007A496
0x14007a52c  test    dword ptr [rcx+2Ch], 100000h
0x14007a533  jz      loc_14007A426
0x14007a539  cmp     byte ptr [rcx+29h], 1
0x14007a53d  jb      loc_14007A426
0x14007a543  mov     edx, 3Ch ; '<'
0x14007a548  jmp     loc_14009811D
0x14007a54d  mov     [rsi+132h], r13b
0x14007a554  jmp     loc_14007A357
0x14007a559  mov     rcx, [rdi]; EcpList
0x14007a55c  lea     rdx, GUID_ECP_SRV_OPEN; EcpType
0x14007a563  xor     r9d, r9d; EcpContextSize
0x14007a566  xor     r8d, r8d; EcpContext
0x14007a569  call    cs:__imp_FsRtlFindExtraCreateParameter
0x14007a570  nop     dword ptr [rax+rax+00h]
0x14007a575  test    eax, eax
0x14007a577  jns     loc_14007A458
0x14007a57d  jmp     loc_14007A360
0x14007a582  mov     rcx, cs:WPP_GLOBAL_Control
0x14007a589  lea     rax, WPP_GLOBAL_Control
0x14007a590  cmp     rcx, rax
0x14007a593  jz      loc_14007A426
0x14007a599  test    dword ptr [rcx+2Ch], 100000h
0x14007a5a0  jz      loc_14007A426
0x14007a5a6  cmp     byte ptr [rcx+29h], 1
0x14007a5aa  jb      loc_14007A426
0x14007a5b0  mov     edx, 3Fh ; '?'
0x14007a5b5  jmp     loc_14009811D
0x14007a5ba  mov     rcx, cs:WPP_GLOBAL_Control
0x14007a5c1  lea     rax, WPP_GLOBAL_Control
0x14007a5c8  cmp     rcx, rax
0x14007a5cb  jz      loc_14007A426
0x14007a5d1  test    dword ptr [rcx+2Ch], 100000h
0x14007a5d8  jz      loc_14007A426
0x14007a5de  cmp     byte ptr [rcx+29h], 1
0x14007a5e2  jb      loc_14007A426
0x14007a5e8  mov     edx, 40h ; '@'
0x14007a5ed  jmp     loc_14009811D
0x14007a5f2  mov     rcx, [rdi]; EcpList
0x14007a5f5  lea     rdx, Smb2RkfGuidEcpIn; EcpType
0x14007a5fc  xor     r9d, r9d; EcpContextSize
0x14007a5ff  xor     r8d, r8d; EcpContext
0x14007a602  call    cs:__imp_FsRtlFindExtraCreateParameter
0x14007a609  nop     dword ptr [rax+rax+00h]
0x14007a60e  test    eax, eax
0x14007a610  jns     loc_14007A496
0x14007a616  mov     rdx, [rdi]
0x14007a619  mov     rcx, r14
0x14007a61c  call    SrvAllocateRkfEcp
0x14007a621  mov     ebx, eax
0x14007a623  test    eax, eax
0x14007a625  js      loc_14007A426
0x14007a62b  jmp     loc_14007A496
0x14009802a  mov     rdx, [rsp+68h+arg_8]; EcpContext
0x14009802f  test    rdx, rdx
0x140098032  jz      loc_14007A3A6
0x140098038  mov     rax, [r14+60h]
0x14009803c  test    rax, rax
0x14009803f  jz      loc_140098113
0x140098045  mov     rcx, [r14+230h]
0x14009804c  add     rax, 0D8h
0x140098052  mov     [rdx+8], rax
0x140098056  mov     rax, [rcx+38h]
0x14009805a  test    rax, rax
0x14009805d  jz      loc_140098113
0x140098063  mov     rax, [rax+60h]
0x140098067  test    rax, rax
0x14009806a  jz      loc_140098113
0x140098070  add     rax, 48h ; 'H'
0x140098074  mov     r10d, 2
0x14009807a  mov     [rdx], rax
0x14009807d  cmp     dword ptr [r14+48h], 1
0x140098082  setz    al
0x140098085  mov     [rdx+10h], al
0x140098088  cmp     dword ptr [r14+48h], 1
0x14009808d  mov     byte ptr [rdx+11h], 1
0x140098091  setz    al
0x140098094  mov     [rdx+14h], r10w
0x140098099  mov     [rdx+12h], al
0x14009809c  mov     rax, [r14+40h]
0x1400980a0  test    rax, rax
0x1400980a3  jz      short loc_140098113
0x1400980a5  movzx   eax, byte ptr [rax]
0x1400980a8  cmp     eax, 5; switch 6 cases
0x1400980ab  ja      short def_1400980BF; jumptable 00000001400980BF default case
0x1400980ad  lea     r9, cs:140000000h
0x1400980b4  mov     ecx, ds:(jpt_1400980BF - 140000000h)[r9+rax*4]
0x1400980bc  add     rcx, r9
0x1400980bf  jmp     rcx; switch jump
0x1400980c5  mov     dword ptr [rdx+18h], 1; jumptable 00000001400980BF case 0
0x1400980cc  jmp     loc_14007A43F
0x1400980d1  mov     [rdx+18h], r10d; jumptable 00000001400980BF case 1
0x1400980d5  jmp     loc_14007A43F
0x1400980da  mov     dword ptr [rdx+18h], 3; jumptable 00000001400980BF case 2
0x1400980e1  jmp     loc_14007A43F
0x1400980e6  mov     dword ptr [rdx+18h], 4; jumptable 00000001400980BF case 3
0x1400980ed  jmp     loc_14007A43F
0x1400980f2  mov     dword ptr [rdx+18h], 6; jumptable 00000001400980BF case 4
0x1400980f9  jmp     loc_14007A43F
0x1400980fe  mov     dword ptr [rdx+18h], 7; jumptable 00000001400980BF case 5
0x140098105  jmp     loc_14007A43F
0x14009810a  mov     [rdx+18h], r13d; jumptable 00000001400980BF default case
0x14009810e  jmp     loc_14007A43F
0x140098113  mov     ebx, 0C00000E5h
0x140098118  jmp     loc_14007A3AB
0x14009811d  mov     rcx, [rcx+18h]
0x140098121  lea     r8, WPP_1eeac08a4da9393ddade0ba3ac297e5e_Traceguids
0x140098128  mov     r9, r14
0x14009812b  mov     [rsp+68h+PoolTag], ebx
0x14009812f  call    WPP_SF_qD
0x140098134  nop
0x140098135  jmp     loc_14007A426
```
