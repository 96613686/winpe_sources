# Smb2CreateEcps

- ea: `0x14007a290`
- end: `0x14007a680`
- name: `Smb2CreateEcps`
- size: `1008`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `reparse_path`

## callers

- `0x14006fc74`
- `0x140079c80`

## callees

- `0x1400149e0`
- `0x140022958`
- `0x140033b84`
- `0x14007a290`
- `0x14007a690`

## import_xrefs

- `ntoskrnl!FsRtlFreeExtraCreateParameterList` at `0x14007a47e`
- `ntoskrnl!FsRtlFreeExtraCreateParameterList` at `0x14007a47e`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x14007a5b9`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x14007a652`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x14007a5b9`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x14007a652`
- `ntoskrnl!FsRtlFreeExtraCreateParameter` at `0x14007a400`
- `ntoskrnl!FsRtlFreeExtraCreateParameter` at `0x14007a43d`
- `ntoskrnl!FsRtlFreeExtraCreateParameter` at `0x14007a400`
- `ntoskrnl!FsRtlFreeExtraCreateParameter` at `0x14007a43d`
- `ntoskrnl!FsRtlInsertExtraCreateParameter` at `0x14007a390`
- `ntoskrnl!FsRtlInsertExtraCreateParameter` at `0x14007a492`
- `ntoskrnl!FsRtlInsertExtraCreateParameter` at `0x14007a390`
- `ntoskrnl!FsRtlInsertExtraCreateParameter` at `0x14007a492`
- `ntoskrnl!FsRtlAllocateExtraCreateParameterList` at `0x14007a2ca`
- `ntoskrnl!FsRtlAllocateExtraCreateParameterList` at `0x14007a2ca`
- `ntoskrnl!FsRtlAllocateExtraCreateParameter` at `0x14007a32d`
- `ntoskrnl!FsRtlAllocateExtraCreateParameter` at `0x14007a3d4`
- `ntoskrnl!FsRtlAllocateExtraCreateParameter` at `0x14007a32d`
- `ntoskrnl!FsRtlAllocateExtraCreateParameter` at `0x14007a3d4`

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
0x14007a290  mov     [rsp+arg_10], rbx
0x14007a295  push    rbp
0x14007a296  push    rsi
0x14007a297  push    rdi
0x14007a298  push    r12
0x14007a29a  push    r13
0x14007a29c  push    r14
0x14007a29e  push    r15
0x14007a2a0  sub     rsp, 30h
0x14007a2a4  mov     rsi, [rcx+230h]
0x14007a2ab  xor     r13d, r13d
0x14007a2ae  xor     bpl, bpl
0x14007a2b1  mov     [rsp+68h+arg_8], r13
0x14007a2b6  mov     r14, rcx
0x14007a2b9  lea     rdi, [rsi+140h]
0x14007a2c0  cmp     [rdi], r13
0x14007a2c3  jnz     short loc_14007A2E3
0x14007a2c5  mov     rdx, rdi; EcpList
0x14007a2c8  xor     ecx, ecx; Flags
0x14007a2ca  call    cs:__imp_FsRtlAllocateExtraCreateParameterList
0x14007a2d1  nop     dword ptr [rax+rax+00h]
0x14007a2d6  mov     ebx, eax
0x14007a2d8  test    eax, eax
0x14007a2da  js      loc_14007A539
0x14007a2e0  mov     bpl, 1
0x14007a2e3  cmp     [rsi+132h], r13b
0x14007a2ea  jz      loc_14007A3A7
0x14007a2f0  cmp     [rsi+68h], r13
0x14007a2f4  jz      loc_14007A59D
0x14007a2fa  mov     r12, [rdi]
0x14007a2fd  lea     rax, [rsp+68h+arg_0]
0x14007a302  mov     r15, [r14+230h]
0x14007a309  lea     rcx, GUID_ECP_DUAL_OPLOCK_KEY; EcpType
0x14007a310  mov     [rsp+68h+EcpContext], rax; EcpContext
0x14007a315  xor     r9d, r9d; CleanupCallback
0x14007a318  xor     r8d, r8d; Flags
0x14007a31b  mov     [rsp+68h+PoolTag], 5324534Ch; PoolTag
0x14007a323  mov     edx, 24h ; '$'; SizeOfContext
0x14007a328  mov     [rsp+68h+arg_0], r13
0x14007a32d  call    cs:__imp_FsRtlAllocateExtraCreateParameter
0x14007a334  nop     dword ptr [rax+rax+00h]
0x14007a339  mov     ebx, eax
0x14007a33b  test    eax, eax
0x14007a33d  js      loc_14007A45F
0x14007a343  mov     rax, [r15+68h]
0x14007a347  mov     rcx, [rsp+68h+arg_0]
0x14007a34c  movups  xmm0, xmmword ptr [rax+50h]
0x14007a350  movups  xmmword ptr [rcx+10h], xmm0
0x14007a354  mov     rax, [rsp+68h+arg_0]
0x14007a359  mov     byte ptr [rax+21h], 1
0x14007a35d  mov     rax, [rsp+68h+arg_0]
0x14007a362  mov     [rax+20h], r13b
0x14007a366  cmp     [r15+12Dh], r13b
0x14007a36d  jz      short loc_14007A388
0x14007a36f  mov     rax, [rsp+68h+arg_0]
0x14007a374  movups  xmm0, xmmword ptr [r15+118h]
0x14007a37c  movups  xmmword ptr [rax], xmm0
0x14007a37f  mov     rax, [rsp+68h+arg_0]
0x14007a384  mov     byte ptr [rax+20h], 1
0x14007a388  mov     rdx, [rsp+68h+arg_0]; EcpContext
0x14007a38d  mov     rcx, r12; EcpList
0x14007a390  call    cs:__imp_FsRtlInsertExtraCreateParameter
0x14007a397  nop     dword ptr [rax+rax+00h]
0x14007a39c  mov     r15d, eax
0x14007a39f  test    eax, eax
0x14007a3a1  js      loc_14007A438
0x14007a3a7  test    bpl, bpl
0x14007a3aa  jz      loc_14007A5A9
0x14007a3b0  lea     rax, [rsp+68h+arg_8]
0x14007a3b5  xor     r9d, r9d; CleanupCallback
0x14007a3b8  mov     [rsp+68h+EcpContext], rax; EcpContext
0x14007a3bd  lea     rcx, GUID_ECP_SRV_OPEN; EcpType
0x14007a3c4  xor     r8d, r8d; Flags
0x14007a3c7  mov     [rsp+68h+PoolTag], 5324534Ch; PoolTag
0x14007a3cf  mov     edx, 20h ; ' '; SizeOfContext
0x14007a3d4  call    cs:__imp_FsRtlAllocateExtraCreateParameter
0x14007a3db  nop     dword ptr [rax+rax+00h]
0x14007a3e0  mov     ebx, eax
0x14007a3e2  test    eax, eax
0x14007a3e4  js      loc_14007A501
0x14007a3ea  mov     r8, [rdi]
0x14007a3ed  test    r8, r8
0x14007a3f0  jnz     loc_14009807A
0x14007a3f6  mov     ebx, 0C000000Dh
0x14007a3fb  mov     rcx, [rsp+68h+arg_8]; EcpContext
0x14007a400  call    cs:__imp_FsRtlFreeExtraCreateParameter
0x14007a407  nop     dword ptr [rax+rax+00h]
0x14007a40c  mov     rcx, cs:WPP_GLOBAL_Control
0x14007a413  lea     rax, WPP_GLOBAL_Control
0x14007a41a  cmp     rcx, rax
0x14007a41d  jz      short loc_14007A476
0x14007a41f  test    dword ptr [rcx+2Ch], 100000h
0x14007a426  jz      short loc_14007A476
0x14007a428  cmp     byte ptr [rcx+29h], 1
0x14007a42c  jb      short loc_14007A476
0x14007a42e  mov     edx, 3Eh ; '>'
0x14007a433  jmp     loc_14009816D
0x14007a438  mov     rcx, [rsp+68h+arg_0]; EcpContext
0x14007a43d  call    cs:__imp_FsRtlFreeExtraCreateParameter
0x14007a444  nop     dword ptr [rax+rax+00h]
0x14007a449  cmp     r15d, 0C000000Dh
0x14007a450  mov     ebx, r13d
0x14007a453  cmovnz  ebx, r15d
0x14007a457  test    ebx, ebx
0x14007a459  jns     loc_14007A3A7
0x14007a45f  mov     rcx, cs:WPP_GLOBAL_Control
0x14007a466  lea     rax, WPP_GLOBAL_Control
0x14007a46d  cmp     rcx, rax
0x14007a470  jnz     loc_14007A57C
0x14007a476  test    bpl, bpl
0x14007a479  jz      short loc_14007A4E6
0x14007a47b  mov     rcx, [rdi]; EcpList
0x14007a47e  call    cs:__imp_FsRtlFreeExtraCreateParameterList
0x14007a485  nop     dword ptr [rax+rax+00h]
0x14007a48a  mov     [rdi], r13
0x14007a48d  jmp     short loc_14007A4E6
0x14007a48f  mov     rcx, r8; EcpList
0x14007a492  call    cs:__imp_FsRtlInsertExtraCreateParameter
0x14007a499  nop     dword ptr [rax+rax+00h]
0x14007a49e  mov     ebx, eax
0x14007a4a0  test    eax, eax
0x14007a4a2  js      loc_14007A3FB
0x14007a4a8  mov     rcx, rdi
0x14007a4ab  call    Smb2CreateStopOnSymlinkEcp
0x14007a4b0  mov     ebx, eax
0x14007a4b2  test    eax, eax
0x14007a4b4  js      loc_14007A5D2
0x14007a4ba  mov     rcx, [rdi]; EcpList
0x14007a4bd  call    Smb2CreateOpenParametersEcp
0x14007a4c2  mov     ebx, eax
0x14007a4c4  test    eax, eax
0x14007a4c6  js      loc_14007A60A
0x14007a4cc  cmp     [rsi+17Bh], r13b
0x14007a4d3  jnz     loc_14007A642
0x14007a4d9  cmp     [rsi+17Eh], r13b
0x14007a4e0  jnz     loc_14007A642
0x14007a4e6  mov     eax, ebx
0x14007a4e8  mov     rbx, [rsp+68h+arg_10]
0x14007a4f0  add     rsp, 30h
0x14007a4f4  pop     r15
0x14007a4f6  pop     r14
0x14007a4f8  pop     r13
0x14007a4fa  pop     r12
0x14007a4fc  pop     rdi
0x14007a4fd  pop     rsi
0x14007a4fe  pop     rbp
0x14007a4ff  retn
0x14007a501  mov     rcx, cs:WPP_GLOBAL_Control
0x14007a508  lea     rax, WPP_GLOBAL_Control
0x14007a50f  cmp     rcx, rax
0x14007a512  jz      loc_14007A476
0x14007a518  test    dword ptr [rcx+2Ch], 100000h
0x14007a51f  jz      loc_14007A476
0x14007a525  cmp     byte ptr [rcx+29h], 1
0x14007a529  jb      loc_14007A476
0x14007a52f  mov     edx, 3Dh ; '='
0x14007a534  jmp     loc_14009816D
0x14007a539  mov     rcx, cs:WPP_GLOBAL_Control
0x14007a540  lea     rax, WPP_GLOBAL_Control
0x14007a547  cmp     rcx, rax
0x14007a54a  jz      short loc_14007A4E6
0x14007a54c  test    dword ptr [rcx+2Ch], 100000h
0x14007a553  jz      short loc_14007A4E6
0x14007a555  cmp     byte ptr [rcx+29h], 1
0x14007a559  jb      short loc_14007A4E6
0x14007a55b  mov     rcx, [rcx+18h]
0x14007a55f  lea     r8, WPP_1eeac08a4da9393ddade0ba3ac297e5e_Traceguids
0x14007a566  mov     edx, 3Bh ; ';'
0x14007a56b  mov     [rsp+68h+PoolTag], ebx
0x14007a56f  mov     r9, r14
0x14007a572  call    WPP_SF_qD
0x14007a577  jmp     loc_14007A4E6
0x14007a57c  test    dword ptr [rcx+2Ch], 100000h
0x14007a583  jz      loc_14007A476
0x14007a589  cmp     byte ptr [rcx+29h], 1
0x14007a58d  jb      loc_14007A476
0x14007a593  mov     edx, 3Ch ; '<'
0x14007a598  jmp     loc_14009816D
0x14007a59d  mov     [rsi+132h], r13b
0x14007a5a4  jmp     loc_14007A3A7
0x14007a5a9  mov     rcx, [rdi]; EcpList
0x14007a5ac  lea     rdx, GUID_ECP_SRV_OPEN; EcpType
0x14007a5b3  xor     r9d, r9d; EcpContextSize
0x14007a5b6  xor     r8d, r8d; EcpContext
0x14007a5b9  call    cs:__imp_FsRtlFindExtraCreateParameter
0x14007a5c0  nop     dword ptr [rax+rax+00h]
0x14007a5c5  test    eax, eax
0x14007a5c7  jns     loc_14007A4A8
0x14007a5cd  jmp     loc_14007A3B0
0x14007a5d2  mov     rcx, cs:WPP_GLOBAL_Control
0x14007a5d9  lea     rax, WPP_GLOBAL_Control
0x14007a5e0  cmp     rcx, rax
0x14007a5e3  jz      loc_14007A476
0x14007a5e9  test    dword ptr [rcx+2Ch], 100000h
0x14007a5f0  jz      loc_14007A476
0x14007a5f6  cmp     byte ptr [rcx+29h], 1
0x14007a5fa  jb      loc_14007A476
0x14007a600  mov     edx, 3Fh ; '?'
0x14007a605  jmp     loc_14009816D
0x14007a60a  mov     rcx, cs:WPP_GLOBAL_Control
0x14007a611  lea     rax, WPP_GLOBAL_Control
0x14007a618  cmp     rcx, rax
0x14007a61b  jz      loc_14007A476
0x14007a621  test    dword ptr [rcx+2Ch], 100000h
0x14007a628  jz      loc_14007A476
0x14007a62e  cmp     byte ptr [rcx+29h], 1
0x14007a632  jb      loc_14007A476
0x14007a638  mov     edx, 40h ; '@'
0x14007a63d  jmp     loc_14009816D
0x14007a642  mov     rcx, [rdi]; EcpList
0x14007a645  lea     rdx, Smb2RkfGuidEcpIn; EcpType
0x14007a64c  xor     r9d, r9d; EcpContextSize
0x14007a64f  xor     r8d, r8d; EcpContext
0x14007a652  call    cs:__imp_FsRtlFindExtraCreateParameter
0x14007a659  nop     dword ptr [rax+rax+00h]
0x14007a65e  test    eax, eax
0x14007a660  jns     loc_14007A4E6
0x14007a666  mov     rdx, [rdi]
0x14007a669  mov     rcx, r14
0x14007a66c  call    SrvAllocateRkfEcp
0x14007a671  mov     ebx, eax
0x14007a673  test    eax, eax
0x14007a675  js      loc_14007A476
0x14007a67b  jmp     loc_14007A4E6
0x14009807a  mov     rdx, [rsp+68h+arg_8]; EcpContext
0x14009807f  test    rdx, rdx
0x140098082  jz      loc_14007A3F6
0x140098088  mov     rax, [r14+60h]
0x14009808c  test    rax, rax
0x14009808f  jz      loc_140098163
0x140098095  mov     rcx, [r14+230h]
0x14009809c  add     rax, 0D8h
0x1400980a2  mov     [rdx+8], rax
0x1400980a6  mov     rax, [rcx+38h]
0x1400980aa  test    rax, rax
0x1400980ad  jz      loc_140098163
0x1400980b3  mov     rax, [rax+60h]
0x1400980b7  test    rax, rax
0x1400980ba  jz      loc_140098163
0x1400980c0  add     rax, 48h ; 'H'
0x1400980c4  mov     r10d, 2
0x1400980ca  mov     [rdx], rax
0x1400980cd  cmp     dword ptr [r14+48h], 1
0x1400980d2  setz    al
0x1400980d5  mov     [rdx+10h], al
0x1400980d8  cmp     dword ptr [r14+48h], 1
0x1400980dd  mov     byte ptr [rdx+11h], 1
0x1400980e1  setz    al
0x1400980e4  mov     [rdx+14h], r10w
0x1400980e9  mov     [rdx+12h], al
0x1400980ec  mov     rax, [r14+40h]
0x1400980f0  test    rax, rax
0x1400980f3  jz      short loc_140098163
0x1400980f5  movzx   eax, byte ptr [rax]
0x1400980f8  cmp     eax, 5; switch 6 cases
0x1400980fb  ja      short def_14009810F; jumptable 000000014009810F default case
0x1400980fd  lea     r9, cs:140000000h
0x140098104  mov     ecx, ds:(jpt_14009810F - 140000000h)[r9+rax*4]
0x14009810c  add     rcx, r9
0x14009810f  jmp     rcx; switch jump
0x140098115  mov     dword ptr [rdx+18h], 1; jumptable 000000014009810F case 0
0x14009811c  jmp     loc_14007A48F
0x140098121  mov     [rdx+18h], r10d; jumptable 000000014009810F case 1
0x140098125  jmp     loc_14007A48F
0x14009812a  mov     dword ptr [rdx+18h], 3; jumptable 000000014009810F case 2
0x140098131  jmp     loc_14007A48F
0x140098136  mov     dword ptr [rdx+18h], 4; jumptable 000000014009810F case 3
0x14009813d  jmp     loc_14007A48F
0x140098142  mov     dword ptr [rdx+18h], 6; jumptable 000000014009810F case 4
0x140098149  jmp     loc_14007A48F
0x14009814e  mov     dword ptr [rdx+18h], 7; jumptable 000000014009810F case 5
0x140098155  jmp     loc_14007A48F
0x14009815a  mov     [rdx+18h], r13d; jumptable 000000014009810F default case
0x14009815e  jmp     loc_14007A48F
0x140098163  mov     ebx, 0C00000E5h
0x140098168  jmp     loc_14007A3FB
0x14009816d  mov     rcx, [rcx+18h]
0x140098171  lea     r8, WPP_1eeac08a4da9393ddade0ba3ac297e5e_Traceguids
0x140098178  mov     r9, r14
0x14009817b  mov     [rsp+68h+PoolTag], ebx
0x14009817f  call    WPP_SF_qD
0x140098184  nop
0x140098185  jmp     loc_14007A476
```
