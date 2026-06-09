# OncRpcSepProcessIncomingCallGssData

- ea: `0x14000b624`
- end: `0x14000bb5e`
- name: `OncRpcSepProcessIncomingCallGssData`
- size: `1338`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140009c14`

## callees

- `0x140001de4`
- `0x1400020c0`
- `0x140002170`
- `0x140005830`
- `0x1400059f8`
- `0x140007098`
- `0x140009540`
- `0x14000a6e8`
- `0x14000a814`
- `0x14000b340`
- `0x14000b624`
- `0x14000cb78`
- `0x14000d04c`
- `0x14000d104`
- `0x140012838`

## pseudocode

```c
__int64 __fastcall OncRpcSepProcessIncomingCallGssData(__int64 a1, _DWORD *a2)
{
  int v4; // eax
  int Signature; // ebx
  __int64 v7; // rsi
  struct _SecHandle *v8; // r13
  void *BufferStart; // rax
  unsigned int *v10; // r15
  __int64 v11; // r8
  void **v12; // r12
  bool v13; // zf
  int v14; // ecx
  unsigned int v15; // eax
  __int64 v16; // rcx
  unsigned int v17; // ebx
  void *v18; // r12
  PDEVICE_OBJECT v19; // rcx
  __int64 v20; // rdx
  unsigned int v21; // ebx
  __int64 v22; // r9
  unsigned int v23; // r13d
  unsigned int *PtrFromPtrAndOffset; // rax
  __int64 v25; // r9
  unsigned int v26; // r15d
  unsigned int v27; // ecx
  __int64 v28; // rax
  unsigned int v29; // r15d
  __int64 v30; // rax
  void *v31; // r9
  void *v32; // [rsp+28h] [rbp-50h]
  unsigned int v33; // [rsp+30h] [rbp-48h]
  unsigned int v34; // [rsp+80h] [rbp+8h] BYREF
  __int64 v35; // [rsp+90h] [rbp+18h] BYREF
  struct _SecHandle *v36; // [rsp+98h] [rbp+20h]

  v35 = 0;
  v4 = OncRpcSepInboundQueryAndRefGssCtx(&v35, *(unsigned int *)(a1 + 328));
  Signature = v4;
  if ( v4 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
      WPP_SF_Dd(
        WPP_GLOBAL_Control->AttachedDevice,
        41,
        WPP_e26fb84b27c236afaa3664beb63ddb12_Traceguids,
        *(unsigned int *)(a1 + 328),
        v4);
    *a2 = 0x80000;
    goto LABEL_6;
  }
  v7 = v35;
  Signature = OncRpcSepCheckAndUpdateSeqWindow(v35, *(unsigned int *)(a1 + 316), a2);
  if ( Signature < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
      WPP_SF_dddd(
        WPP_GLOBAL_Control->AttachedDevice,
        42,
        WPP_e26fb84b27c236afaa3664beb63ddb12_Traceguids,
        *(unsigned int *)(a1 + 328),
        *(_DWORD *)(a1 + 316),
        *a2,
        Signature);
    goto LABEL_6;
  }
  v8 = (struct _SecHandle *)(v7 + 88);
  v36 = (struct _SecHandle *)(v7 + 88);
  BufferStart = (void *)OncRpcBufMgrGetBufferStart(a1 + 32);
  Signature = OncRpcSepVerifyMessage(
                (struct _SecHandle *)(v7 + 88),
                a2,
                a1 + 32,
                BufferStart,
                *(_DWORD *)(a1 + 1028),
                a1 + 32,
                *(_QWORD *)(a1 + 720),
                *(_DWORD *)(a1 + 712));
  if ( Signature < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
      WPP_SF_Dd(
        WPP_GLOBAL_Control->AttachedDevice,
        43,
        WPP_e26fb84b27c236afaa3664beb63ddb12_Traceguids,
        *(unsigned int *)(a1 + 328),
        Signature);
    goto LABEL_6;
  }
  v10 = (unsigned int *)(a1 + 1080);
  v34 = _byteswap_ulong(*(_DWORD *)(a1 + 316));
  *(_QWORD *)(a1 + 1072) = a1 + 376;
  *(_DWORD *)(a1 + 1080) = 0;
  Signature = OncRpcSeMakeSignature(
                (struct _SecHandle *)(v7 + 88),
                a2,
                0,
                &v34,
                4u,
                (void *)(a1 + 376),
                0x40u,
                (unsigned int *)(a1 + 1080));
  if ( Signature < 0 )
  {
    v11 = *v10;
    if ( !(_DWORD)v11
      || (v12 = (void **)(a1 + 1064), Signature = NfsMemMgrBufferAllocate(1, 1987004242, v11, a1 + 1064), Signature < 0)
      || (v33 = *v10,
          v32 = *v12,
          *(_QWORD *)(a1 + 1072) = *v12,
          Signature = OncRpcSeMakeSignature(v8, a2, 0, &v34, 4u, v32, v33, (unsigned int *)(a1 + 1080)),
          Signature < 0) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          44,
          WPP_e26fb84b27c236afaa3664beb63ddb12_Traceguids,
          (unsigned int)Signature);
      goto LABEL_6;
    }
  }
  v13 = *(_DWORD *)(a1 + 1024) == 0;
  v14 = *(_DWORD *)(a1 + 320);
  *(_DWORD *)(a1 + 1048) = v14;
  *(_DWORD *)(a1 + 1052) = *(_DWORD *)(a1 + 316);
  if ( !v13 )
    *(_BYTE *)(a1 + 1056) = 1;
  if ( v14 == 1 )
    goto LABEL_51;
  if ( v14 != 2 )
  {
    if ( v14 != 3 )
    {
      Signature = -1073741811;
      goto LABEL_6;
    }
    v29 = XdrDecodeInt_0(a1);
    if ( (unsigned int)XdrBytesLeft(a1) < v29 )
    {
LABEL_42:
      Signature = -2147483643;
      goto LABEL_6;
    }
    if ( *(int *)(a1 + 264) >= 0 )
    {
      v30 = *(_QWORD *)(a1 + 72);
      if ( v30 )
        v31 = *(void **)(v30 + 64);
      else
        v31 = 0;
      Signature = OncRpcSepDecryptMessage((__int64)v8, a2, a1 + 32, v31, v29);
      if ( Signature < 0 )
      {
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
        {
          v20 = 47;
          goto LABEL_63;
        }
        goto LABEL_6;
      }
      if ( (unsigned int)XdrDecodeInt_0(a1) == *(_DWORD *)(a1 + 316) )
      {
LABEL_52:
        *(_QWORD *)(a1 + 1000) = v35;
        goto LABEL_8;
      }
      Signature = -1073741790;
    }
LABEL_51:
    if ( Signature < 0 )
      goto LABEL_6;
    goto LABEL_52;
  }
  v15 = XdrDecodeInt_0(a1);
  v16 = *(_QWORD *)(a1 + 72);
  v17 = v15;
  v34 = v15;
  if ( v16 )
    v18 = *(void **)(v16 + 64);
  else
    v18 = 0;
  if ( (unsigned int)XdrDecodeInt_0(a1) != *(_DWORD *)(a1 + 316) )
  {
    Signature = -1073741811;
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    {
      v20 = 45;
LABEL_63:
      WPP_SF_d(v19->AttachedDevice, v20, WPP_e26fb84b27c236afaa3664beb63ddb12_Traceguids, (unsigned int)Signature);
      goto LABEL_6;
    }
    goto LABEL_6;
  }
  v21 = (v17 + 3) & 0xFFFFFFFC;
  if ( v21 + 4 < v21 || (v23 = XdrBytesLeft(a1), v23 < v21 + 4) )
  {
    Signature = -2147483643;
    goto LABEL_51;
  }
  LOBYTE(v22) = 1;
  PtrFromPtrAndOffset = (unsigned int *)OncRpcBufMgrpContextGetPtrFromPtrAndOffset(a1 + 32, v18, v21, v22);
  if ( !PtrFromPtrAndOffset )
    goto LABEL_42;
  v26 = _byteswap_ulong(*PtrFromPtrAndOffset);
  v27 = v21 + ((v26 + 3) & 0xFFFFFFFC);
  if ( v27 < v21 )
    goto LABEL_42;
  if ( v23 < v27 )
    goto LABEL_42;
  LOBYTE(v25) = 1;
  v28 = OncRpcBufMgrpContextGetPtrFromPtrAndOffset(a1 + 32, PtrFromPtrAndOffset, 4, v25);
  if ( !v28 )
    goto LABEL_42;
  Signature = OncRpcSepVerifyMessage(v36, a2, a1 + 32, v18, v34, a1 + 32, v28, v26);
  if ( Signature >= 0 )
    goto LABEL_52;
  v19 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
  {
    v20 = 46;
    goto LABEL_63;
  }
LABEL_6:
  if ( v35 )
    NfsStandardHeaderDereferenceNoType(v35);
LABEL_8:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      48,
      WPP_e26fb84b27c236afaa3664beb63ddb12_Traceguids,
      (unsigned int)Signature);
  return (unsigned int)Signature;
}

```

## disassembly

```asm
0x14000b624  mov     rax, rsp
0x14000b627  mov     [rax+10h], rbx
0x14000b62b  push    rbp
0x14000b62c  push    rsi
0x14000b62d  push    rdi
0x14000b62e  push    r12
0x14000b630  push    r13
0x14000b632  push    r14
0x14000b634  push    r15
0x14000b636  sub     rsp, 40h
0x14000b63a  mov     r14, rdx
0x14000b63d  mov     qword ptr [rax+18h], 0
0x14000b645  mov     edx, [rcx+148h]
0x14000b64b  mov     rdi, rcx
0x14000b64e  lea     rcx, [rax+18h]
0x14000b652  call    OncRpcSepInboundQueryAndRefGssCtx
0x14000b657  mov     ebx, eax
0x14000b659  test    eax, eax
0x14000b65b  jns     loc_14000B6FE
0x14000b661  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b668  lea     rsi, WPP_GLOBAL_Control
0x14000b66f  cmp     rcx, rsi
0x14000b672  jz      short loc_14000B69C
0x14000b674  mov     edx, [rcx+2Ch]
0x14000b677  test    dl, 40h
0x14000b67a  jz      short loc_14000B69C
0x14000b67c  mov     r9d, [rdi+148h]
0x14000b683  lea     r8, WPP_e26fb84b27c236afaa3664beb63ddb12_Traceguids
0x14000b68a  mov     rcx, [rcx+18h]
0x14000b68e  mov     edx, 29h ; ')'
0x14000b693  mov     [rsp+78h+var_58], eax
0x14000b697  call    WPP_SF_Dd
0x14000b69c  mov     dword ptr [r14], 80000h
0x14000b6a3  mov     rax, [rsp+78h+arg_10]
0x14000b6ab  test    rax, rax
0x14000b6ae  jz      short loc_14000B6B8
0x14000b6b0  mov     rcx, rax
0x14000b6b3  call    NfsStandardHeaderDereferenceNoType
0x14000b6b8  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b6bf  cmp     rcx, rsi
0x14000b6c2  jz      short loc_14000B6E3
0x14000b6c4  mov     eax, [rcx+2Ch]
0x14000b6c7  test    al, 1
0x14000b6c9  jz      short loc_14000B6E3
0x14000b6cb  mov     rcx, [rcx+18h]
0x14000b6cf  lea     r8, WPP_e26fb84b27c236afaa3664beb63ddb12_Traceguids
0x14000b6d6  mov     edx, 30h ; '0'
0x14000b6db  mov     r9d, ebx
0x14000b6de  call    WPP_SF_d
0x14000b6e3  mov     eax, ebx
0x14000b6e5  mov     rbx, [rsp+78h+arg_8]
0x14000b6ed  add     rsp, 40h
0x14000b6f1  pop     r15
0x14000b6f3  pop     r14
0x14000b6f5  pop     r13
0x14000b6f7  pop     r12
0x14000b6f9  pop     rdi
0x14000b6fa  pop     rsi
0x14000b6fb  pop     rbp
0x14000b6fc  retn
0x14000b6fe  mov     rsi, [rsp+78h+arg_10]
0x14000b706  mov     r8, r14
0x14000b709  mov     edx, [rdi+13Ch]
0x14000b70f  mov     rcx, rsi
0x14000b712  call    OncRpcSepCheckAndUpdateSeqWindow
0x14000b717  mov     ebx, eax
0x14000b719  test    eax, eax
0x14000b71b  jns     short loc_14000B775
0x14000b71d  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b724  lea     rsi, WPP_GLOBAL_Control
0x14000b72b  cmp     rcx, rsi
0x14000b72e  jz      loc_14000B6A3
0x14000b734  mov     eax, [rcx+2Ch]
0x14000b737  test    al, 40h
0x14000b739  jz      loc_14000B6A3
0x14000b73f  mov     eax, [r14]
0x14000b742  lea     r8, WPP_e26fb84b27c236afaa3664beb63ddb12_Traceguids
0x14000b749  mov     r9d, [rdi+148h]
0x14000b750  mov     edx, 2Ah ; '*'
0x14000b755  mov     rcx, [rcx+18h]
0x14000b759  mov     dword ptr [rsp+78h+var_48], ebx
0x14000b75d  mov     dword ptr [rsp+78h+var_50], eax
0x14000b761  mov     eax, [rdi+13Ch]
0x14000b767  mov     [rsp+78h+var_58], eax
0x14000b76b  call    WPP_SF_dddd
0x14000b770  jmp     loc_14000B6A3
0x14000b775  lea     rbp, [rdi+20h]
0x14000b779  lea     r13, [rsi+58h]
0x14000b77d  mov     rcx, rbp
0x14000b780  mov     [rsp+78h+arg_18], r13
0x14000b788  call    OncRpcBufMgrGetBufferStart
0x14000b78d  mov     r9, rax
0x14000b790  mov     r8, rbp
0x14000b793  mov     eax, [rdi+2C8h]
0x14000b799  mov     rdx, r14
0x14000b79c  mov     dword ptr [rsp+78h+var_40], eax
0x14000b7a0  mov     rcx, r13
0x14000b7a3  mov     rax, [rdi+2D0h]
0x14000b7aa  mov     [rsp+78h+var_48], rax
0x14000b7af  mov     eax, [rdi+404h]
0x14000b7b5  mov     [rsp+78h+var_50], rbp
0x14000b7ba  mov     [rsp+78h+var_58], eax
0x14000b7be  call    OncRpcSepVerifyMessage
0x14000b7c3  mov     ebx, eax
0x14000b7c5  test    eax, eax
0x14000b7c7  jns     short loc_14000B810
0x14000b7c9  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b7d0  lea     rsi, WPP_GLOBAL_Control
0x14000b7d7  cmp     rcx, rsi
0x14000b7da  jz      loc_14000B6A3
0x14000b7e0  mov     eax, [rcx+2Ch]
0x14000b7e3  test    al, 40h
0x14000b7e5  jz      loc_14000B6A3
0x14000b7eb  mov     r9d, [rdi+148h]
0x14000b7f2  lea     r8, WPP_e26fb84b27c236afaa3664beb63ddb12_Traceguids
0x14000b7f9  mov     rcx, [rcx+18h]
0x14000b7fd  mov     edx, 2Bh ; '+'
0x14000b802  mov     [rsp+78h+var_58], ebx
0x14000b806  call    WPP_SF_Dd
0x14000b80b  jmp     loc_14000B6A3
0x14000b810  mov     eax, [rdi+13Ch]
0x14000b816  lea     r15, [rdi+438h]
0x14000b81d  bswap   eax
0x14000b81f  mov     [rsp+78h+var_40], r15
0x14000b824  lea     r9, [rsp+78h+arg_0]
0x14000b82c  mov     [rsp+78h+arg_0], eax
0x14000b833  xor     r8d, r8d
0x14000b836  lea     rax, [rdi+178h]
0x14000b83d  mov     dword ptr [rsp+78h+var_48], 40h ; '@'
0x14000b845  mov     [rsp+78h+var_50], rax
0x14000b84a  mov     rdx, r14
0x14000b84d  mov     rcx, r13
0x14000b850  mov     [rsp+78h+var_58], 4
0x14000b858  mov     [rdi+430h], rax
0x14000b85f  mov     dword ptr [r15], 0
0x14000b866  call    OncRpcSeMakeSignature
0x14000b86b  lea     rsi, WPP_GLOBAL_Control
0x14000b872  mov     ebx, eax
0x14000b874  test    eax, eax
0x14000b876  jns     loc_14000B91A
0x14000b87c  mov     r8d, [r15]
0x14000b87f  test    r8d, r8d
0x14000b882  jz      short loc_14000B8E3
0x14000b884  lea     r12, [rdi+428h]
0x14000b88b  mov     edx, 766F4752h
0x14000b890  mov     r9, r12
0x14000b893  mov     ecx, 1
0x14000b898  call    NfsMemMgrBufferAllocate
0x14000b89d  mov     ebx, eax
0x14000b89f  test    eax, eax
0x14000b8a1  js      short loc_14000B8E3
0x14000b8a3  mov     rcx, [r12]
0x14000b8a7  lea     r9, [rsp+78h+arg_0]
0x14000b8af  mov     eax, [r15]
0x14000b8b2  xor     r8d, r8d
0x14000b8b5  mov     [rsp+78h+var_40], r15
0x14000b8ba  mov     rdx, r14
0x14000b8bd  mov     dword ptr [rsp+78h+var_48], eax
0x14000b8c1  mov     [rsp+78h+var_50], rcx
0x14000b8c6  mov     [rdi+430h], rcx
0x14000b8cd  mov     rcx, r13
0x14000b8d0  mov     [rsp+78h+var_58], 4
0x14000b8d8  call    OncRpcSeMakeSignature
0x14000b8dd  mov     ebx, eax
0x14000b8df  test    eax, eax
0x14000b8e1  jns     short loc_14000B91A
0x14000b8e3  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b8ea  cmp     rcx, rsi
0x14000b8ed  jz      loc_14000B6A3
0x14000b8f3  mov     eax, [rcx+2Ch]
0x14000b8f6  test    al, 40h
0x14000b8f8  jz      short loc_14000B912
0x14000b8fa  mov     rcx, [rcx+18h]
0x14000b8fe  lea     r8, WPP_e26fb84b27c236afaa3664beb63ddb12_Traceguids
0x14000b905  mov     edx, 2Ch ; ','
0x14000b90a  mov     r9d, ebx
0x14000b90d  call    WPP_SF_d
0x14000b912  test    ebx, ebx
0x14000b914  js      loc_14000B6A3
0x14000b91a  cmp     dword ptr [rdi+400h], 0
0x14000b921  mov     ecx, [rdi+140h]
0x14000b927  mov     [rdi+418h], ecx
0x14000b92d  mov     eax, [rdi+13Ch]
0x14000b933  mov     [rdi+41Ch], eax
0x14000b939  jz      short loc_14000B942
0x14000b93b  mov     byte ptr [rdi+420h], 1
0x14000b942  cmp     ecx, 1
0x14000b945  jz      loc_14000BA89
0x14000b94b  cmp     ecx, 2
0x14000b94e  jnz     loc_14000BAA5
0x14000b954  mov     rcx, rdi
0x14000b957  call    XdrDecodeInt_0
0x14000b95c  mov     rcx, [rbp+28h]
0x14000b960  mov     ebx, eax
0x14000b962  mov     [rsp+78h+arg_0], eax
0x14000b969  test    rcx, rcx
0x14000b96c  jnz     short loc_14000B973
0x14000b96e  xor     r12d, r12d
0x14000b971  jmp     short loc_14000B977
0x14000b973  mov     r12, [rcx+40h]
0x14000b977  mov     rcx, rdi
0x14000b97a  call    XdrDecodeInt_0
0x14000b97f  cmp     eax, [rdi+13Ch]
0x14000b985  jz      short loc_14000B9B1
0x14000b987  mov     ebx, 0C000000Dh
0x14000b98c  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b993  cmp     rcx, rsi
0x14000b996  jz      loc_14000B6A3
0x14000b99c  mov     eax, [rcx+2Ch]
0x14000b99f  test    al, 40h
0x14000b9a1  jz      loc_14000B6A3
0x14000b9a7  mov     edx, 2Dh ; '-'
0x14000b9ac  jmp     loc_14000BB1E
0x14000b9b1  add     ebx, 3
0x14000b9b4  and     ebx, 0FFFFFFFCh
0x14000b9b7  lea     r15d, [rbx+4]
0x14000b9bb  cmp     r15d, ebx
0x14000b9be  jb      loc_14000BA84
0x14000b9c4  mov     rcx, rdi
0x14000b9c7  call    XdrBytesLeft
0x14000b9cc  mov     r13d, eax
0x14000b9cf  cmp     eax, r15d
0x14000b9d2  jb      loc_14000BA84
0x14000b9d8  mov     r9b, 1
0x14000b9db  mov     r8d, ebx
0x14000b9de  mov     rdx, r12
0x14000b9e1  mov     rcx, rbp
0x14000b9e4  call    OncRpcBufMgrpContextGetPtrFromPtrAndOffset
0x14000b9e9  mov     rdx, rax
0x14000b9ec  test    rax, rax
0x14000b9ef  jnz     short loc_14000B9FB
0x14000b9f1  mov     ebx, 80000005h
0x14000b9f6  jmp     loc_14000B6A3
0x14000b9fb  mov     r15d, [rax]
0x14000b9fe  bswap   r15d
0x14000ba01  lea     ecx, [r15+3]
0x14000ba05  and     ecx, 0FFFFFFFCh
0x14000ba08  add     ecx, ebx
0x14000ba0a  cmp     ecx, ebx
0x14000ba0c  jb      short loc_14000B9F1
0x14000ba0e  cmp     r13d, ecx
0x14000ba11  jb      short loc_14000B9F1
0x14000ba13  mov     r9b, 1
0x14000ba16  mov     r8d, 4
0x14000ba1c  mov     rcx, rbp
0x14000ba1f  call    OncRpcBufMgrpContextGetPtrFromPtrAndOffset
0x14000ba24  test    rax, rax
0x14000ba27  jz      short loc_14000B9F1
0x14000ba29  mov     rcx, [rsp+78h+arg_18]
0x14000ba31  mov     r9, r12
0x14000ba34  mov     dword ptr [rsp+78h+var_40], r15d
0x14000ba39  mov     r8, rbp
0x14000ba3c  mov     [rsp+78h+var_48], rax
0x14000ba41  mov     rdx, r14
0x14000ba44  mov     eax, [rsp+78h+arg_0]
0x14000ba4b  mov     [rsp+78h+var_50], rbp
0x14000ba50  mov     [rsp+78h+var_58], eax
0x14000ba54  call    OncRpcSepVerifyMessage
0x14000ba59  mov     ebx, eax
0x14000ba5b  test    eax, eax
0x14000ba5d  jns     short loc_14000BA91
0x14000ba5f  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ba66  cmp     rcx, rsi
0x14000ba69  jz      loc_14000B6A3
0x14000ba6f  mov     eax, [rcx+2Ch]
0x14000ba72  test    al, 40h
0x14000ba74  jz      loc_14000B6A3
0x14000ba7a  mov     edx, 2Eh ; '.'
0x14000ba7f  jmp     loc_14000BB1E
0x14000ba84  mov     ebx, 80000005h
0x14000ba89  test    ebx, ebx
0x14000ba8b  js      loc_14000B6A3
0x14000ba91  mov     rax, [rsp+78h+arg_10]
0x14000ba99  mov     [rdi+3E8h], rax
0x14000baa0  jmp     loc_14000B6B8
0x14000baa5  cmp     ecx, 3
0x14000baa8  jnz     loc_14000BB54
0x14000baae  mov     rcx, rdi
0x14000bab1  call    XdrDecodeInt_0
0x14000bab6  mov     rcx, rdi
0x14000bab9  mov     r15d, eax
0x14000babc  call    XdrBytesLeft
0x14000bac1  cmp     eax, r15d
0x14000bac4  jb      loc_14000B9F1
0x14000baca  cmp     dword ptr [rdi+108h], 0
0x14000bad1  jl      short loc_14000BA89
0x14000bad3  mov     rax, [rbp+28h]
0x14000bad7  test    rax, rax
0x14000bada  jnz     short loc_14000BAE1
0x14000badc  xor     r9d, r9d
0x14000badf  jmp     short loc_14000BAE5
0x14000bae1  mov     r9, [rax+40h]
0x14000bae5  mov     r8, rbp
0x14000bae8  mov     [rsp+78h+var_58], r15d
0x14000baed  mov     rdx, r14
0x14000baf0  mov     rcx, r13
0x14000baf3  call    OncRpcSepDecryptMessage
0x14000baf8  mov     ebx, eax
0x14000bafa  test    eax, eax
0x14000bafc  jns     short loc_14000BB36
  ... truncated ...
```
