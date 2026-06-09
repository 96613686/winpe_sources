# WsOpenCreateConnectionSpecifyImpersonation

- ea: `0x180004a40`
- end: `0x1800051ba`
- name: `WsOpenCreateConnectionSpecifyImpersonation`
- size: `1914`
- prototype: `DWORD __fastcall(struct _UNICODE_STRING *, const void **, __int64, int, const void **, char *hMem, __int64, __int64, __int64, __int64, int EaLength, ULONG CreateDisposition, int, char, char, char, PHANDLE FileHandle)`
- caller_count: `4`
- callee_count: `8`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180001710`
- `0x180003b70`
- `0x180009b80`
- `0x1800299a4`

## callees

- `0x180004a40`
- `0x180005a60`
- `0x180008950`
- `0x18000abb0`
- `0x18000b4e8`
- `0x18001ed46`
- `0x18002ecc0`
- `0x180033159`

## import_xrefs

- `ntdll!DbgPrint` at `0x180004d09`
- `ntdll!DbgPrint` at `0x180004dca`
- `ntdll!DbgPrint` at `0x180004df4`
- `ntdll!DbgPrint` at `0x180004e1e`
- `ntdll!DbgPrint` at `0x180004f5e`
- `ntdll!DbgPrint` at `0x180004fb5`
- `ntdll!DbgPrint` at `0x180005008`
- `ntdll!DbgPrint` at `0x18000510d`
- `ntdll!DbgPrint` at `0x180004d09`
- `ntdll!DbgPrint` at `0x180004dca`
- `ntdll!DbgPrint` at `0x180004df4`
- `ntdll!DbgPrint` at `0x180004e1e`
- `ntdll!DbgPrint` at `0x180004f5e`
- `ntdll!DbgPrint` at `0x180004fb5`
- `ntdll!DbgPrint` at `0x180005008`
- `ntdll!DbgPrint` at `0x18000510d`
- `ntdll!NtCreateFile` at `0x180004cf8`
- `ntdll!NtCreateFile` at `0x180004cf8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004b57`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004b57`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180004b45`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180004b45`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004d35`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004d35`
- `RPCRT4!RpcImpersonateClient` at `0x180004d45`
- `RPCRT4!RpcImpersonateClient` at `0x180004d45`

## string_xrefs

- `0x180004d00`: `NtCreateFile Status : %lx\n`
- `0x180004f74`: `CompressionInfo`
- `0x180004ded`: `Compression params specified by user.\n`
- `0x180004f4d`: `EA created for specified TransportParams. %u \n`
- `0x180004fa7`: `EA created for specified CompressionParams.`
- `0x180004ffa`: `EA created for specified BlockNTLMParams.`
- `0x18000507a`: `CscAgent`

## pseudocode

```c
DWORD __fastcall WsOpenCreateConnectionSpecifyImpersonation(
        struct _UNICODE_STRING *a1,
        const void **a2,
        __int64 a3,
        int a4,
        const void **a5,
        char *hMem,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        int EaLength,
        ULONG CreateDisposition,
        int a13,
        char a14,
        char a15,
        char a16,
        PHANDLE FileHandle)
{
  const void **v17; // r14
  int v18; // ebx
  char v19; // di
  ULONG v20; // esi
  const void **v21; // r12
  __int64 v22; // r13
  char *v23; // rax
  char *EaBuffer; // r11
  char *v26; // rsi
  ULONG CreateOptions; // r15d
  int v28; // ebx
  ULONG FileAttributes; // edi
  int v30; // r14d
  const char *v31; // r8
  __int64 v32; // r9
  _BYTE *v33; // rax
  __int64 v34; // rcx
  char v35; // bl
  _BYTE *v36; // rcx
  int v37; // eax
  ULONG v38; // esi
  NTSTATUS Status; // edi
  RPC_STATUS v40; // eax
  __int64 v41; // r11
  __int64 v42; // rax
  _OWORD *v43; // r10
  __int64 v44; // rax
  _DWORD *v45; // r10
  _QWORD *v46; // r10
  __int64 v47; // rax
  _QWORD *v48; // r10
  __int64 v49; // rax
  __int64 v50; // rax
  __int64 v51; // rax
  __int64 v52; // rax
  const void *v53; // r10
  unsigned int v54; // ebx
  __int64 v55; // rax
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+60h] [rbp-39h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp-29h] BYREF
  int v58; // [rsp+E0h] [rbp+47h] BYREF
  __int64 v59; // [rsp+F0h] [rbp+57h]
  size_t Size; // [rsp+F8h] [rbp+5Fh]

  LODWORD(Size) = a4;
  v59 = a3;
  v17 = a2;
  *(&ObjectAttributes.Length + 1) = 0;
  v18 = 0;
  *(&ObjectAttributes.Attributes + 1) = 0;
  v58 = 0;
  IoStatusBlock = 0;
  if ( a2 && !*(_WORD *)a2 )
    v17 = 0;
  ObjectAttributes.SecurityDescriptor = hMem;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = a1;
  ObjectAttributes.SecurityQualityOfService = 0;
  if ( a3 )
  {
    NetpULongRoundUp((unsigned int)(a4 + 21), 4, &v58);
    v18 = v58;
  }
  v19 = EaLength;
  v20 = EaLength & 1;
  if ( (EaLength & 1) != 0 )
  {
    v58 = 20;
    v18 += 20;
  }
  v21 = a5;
  if ( a5 )
  {
    NetpULongRoundUp((unsigned int)*(unsigned __int16 *)a5 + 18, 4, &v58);
    v18 += v58;
  }
  v22 = a7;
  if ( a7 )
  {
    v58 = 148;
    v18 += 148;
  }
  if ( a8 )
  {
    NetpULongRoundUp(38, 4, &v58);
    v18 += v58;
    DbgPrint("Transport Params specified by user.\n");
  }
  if ( a9 )
  {
    NetpULongRoundUp(32, 4, &v58);
    v18 += v58;
    DbgPrint("Compression params specified by user.\n");
  }
  if ( a10 )
  {
    NetpULongRoundUp(30, 4, &v58);
    v18 += v58;
    DbgPrint("BlockNTLM params specified by user.\n");
  }
  if ( (v19 & 2) != 0 )
  {
    v58 = 20;
    v18 += 20;
  }
  if ( v17 )
  {
    NetpULongRoundUp((unsigned int)*(unsigned __int16 *)v17 + 20, 4, &v58);
    v18 += v58;
  }
  EaLength = v18 + 17;
  v23 = (char *)LocalAlloc(0x40u, (unsigned int)(v18 + 17));
  hMem = v23;
  EaBuffer = v23;
  if ( !v23 )
    return GetLastError();
  if ( v20 )
  {
    StringCbCopyA(v23 + 8, 0xAu, "NoConnect");
    *(_BYTE *)(v41 + 5) = 9;
    *(_WORD *)(v41 + 6) = 0;
    NetpULongRoundUp(18, 4, v41);
    v26 = &EaBuffer[*(unsigned int *)EaBuffer];
    EaBuffer[4] = 0;
  }
  else
  {
    v26 = v23;
  }
  if ( v22 )
  {
    StringCbCopyA(v26 + 8, 0x17u, "DeferredConnectionInfo");
    v26[5] = 22;
    *((_WORD *)v26 + 3) = 116;
    *(_OWORD *)(v26 + 31) = *(_OWORD *)v22;
    *(_OWORD *)(v26 + 47) = *(_OWORD *)(v22 + 16);
    *(_OWORD *)(v26 + 63) = *(_OWORD *)(v22 + 32);
    *(_OWORD *)(v26 + 79) = *(_OWORD *)(v22 + 48);
    *(_OWORD *)(v26 + 95) = *(_OWORD *)(v22 + 64);
    *(_OWORD *)(v26 + 111) = *(_OWORD *)(v22 + 80);
    *(_OWORD *)(v26 + 127) = *(_OWORD *)(v22 + 96);
    *(_DWORD *)(v26 + 143) = *(_DWORD *)(v22 + 112);
    NetpULongRoundUp(147, 4, v26);
    v42 = *(unsigned int *)v26;
    v26[4] = 0;
    v26 += v42;
  }
  if ( a8 )
  {
    StringCbCopyA(v26 + 8, 0xEu, "TransportInfo");
    v26[5] = 13;
    *((_WORD *)v26 + 3) = 16;
    *(_OWORD *)(v26 + 22) = *v43;
    NetpULongRoundUp(38, 4, v26);
    v44 = *(unsigned int *)v26;
    v26[4] = 0;
    v26 += v44;
    DbgPrint("EA created for specified TransportParams. %u \n", *v45);
    EaBuffer = hMem;
  }
  if ( a9 )
  {
    StringCbCopyA(v26 + 8, 0x10u, "CompressionInfo");
    v26[5] = 15;
    *((_WORD *)v26 + 3) = 8;
    *((_QWORD *)v26 + 3) = *v46;
    NetpULongRoundUp(32, 4, v26);
    v47 = *(unsigned int *)v26;
    v26[4] = 0;
    v26 += v47;
    DbgPrint("EA created for specified CompressionParams.");
    EaBuffer = hMem;
  }
  if ( a10 )
  {
    StringCbCopyA(v26 + 8, 0xEu, "BlockNTLMInfo");
    v26[5] = 13;
    *((_WORD *)v26 + 3) = 8;
    *(_QWORD *)(v26 + 22) = *v48;
    NetpULongRoundUp(30, 4, v26);
    v49 = *(unsigned int *)v26;
    v26[4] = 0;
    v26 += v49;
    DbgPrint("EA created for specified BlockNTLMParams.");
    EaBuffer = hMem;
  }
  if ( v21 )
  {
    StringCbCopyA(v26 + 8, 0xAu, "Principal");
    v26[5] = 9;
    *((_WORD *)v26 + 3) = *(_WORD *)v21;
    memcpy_0(v26 + 18, v21[1], *(unsigned __int16 *)v21);
    NetpULongRoundUp((unsigned int)*(unsigned __int16 *)v21 + 18, 4, v26);
    v50 = *(unsigned int *)v26;
    EaBuffer = hMem;
    v26[4] = 0;
    v26 += v50;
  }
  if ( (v19 & 2) != 0 )
  {
    StringCbCopyA(v26 + 8, 9u, "CscAgent");
    v26[5] = 8;
    *((_WORD *)v26 + 3) = 0;
    NetpULongRoundUp(17, 4, v26);
    v51 = *(unsigned int *)v26;
    v26[4] = 0;
    v26 += v51;
  }
  if ( v17 )
  {
    StringCbCopyA(v26 + 8, 0xCu, "LocalDevice");
    v26[5] = 11;
    *((_WORD *)v26 + 3) = *(_WORD *)v17;
    memcpy_0(v26 + 20, v17[1], *(unsigned __int16 *)v17);
    NetpULongRoundUp((unsigned int)*(unsigned __int16 *)v17 + 20, 4, v26);
    v52 = *(unsigned int *)v26;
    EaBuffer = hMem;
    v26[4] = 0;
    v26 += v52;
  }
  CreateOptions = ((v19 & 4) << 8) | 0xA2;
  if ( (v19 & 0x40) == 0 )
    CreateOptions = ((v19 & 4) << 8) | 0xA0;
  v28 = ((v19 & 8) << 12) | 0x4080;
  if ( (v19 & 0x10) == 0 )
    v28 = ((v19 & 8) << 12) | 0x80;
  if ( a14 )
  {
    v28 |= 4u;
    DbgPrint("Setting attribute TREE_CONNECT_ATTRIBUTE_GLOBAL\n");
    EaBuffer = hMem;
  }
  FileAttributes = v28 | 2;
  if ( !a16 )
    FileAttributes = v28;
  if ( v59 )
  {
    StringCbCopyA(v26 + 8, 0xDu, "AuthIdentity");
    v54 = Size;
    v26[5] = 12;
    if ( v54 )
      memcpy_0(v26 + 21, v53, v54);
    *((_WORD *)v26 + 3) = v54;
    NetpULongRoundUp(v54 + 21, 4, v26);
    v55 = *(unsigned int *)v26;
    v26[4] = 0;
    v26 += v55;
  }
  v30 = 5;
  v31 = "Type";
  v32 = 5;
  v33 = v26 + 8;
  v34 = 2147483646;
  do
  {
    if ( !v34 )
      break;
    if ( !*v31 )
      break;
    *v33++ = *v31++;
    --v34;
    --v32;
  }
  while ( v32 );
  v35 = a15;
  v36 = v33 - 1;
  if ( v32 )
    v36 = v33;
  v37 = a13;
  *v36 = 0;
  *((_DWORD *)v26 + 1) = 263168;
  *(_DWORD *)(v26 + 13) = v37;
  *(_DWORD *)v26 = 0;
  if ( v35 )
  {
    v40 = RpcImpersonateClient(0);
    if ( v40 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        WPP_SF_sdL(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          10,
          (unsigned int)&WPP_GLOBAL_Control,
          (unsigned int)"unknown",
          0,
          v40);
      }
      v38 = EaLength;
      goto LABEL_59;
    }
    EaBuffer = hMem;
  }
  v38 = EaLength;
  Status = NtCreateFile(
             FileHandle,
             0x100000u,
             &ObjectAttributes,
             &IoStatusBlock,
             0,
             FileAttributes,
             7u,
             CreateDisposition,
             CreateOptions,
             EaBuffer,
             EaLength);
  DbgPrint("NtCreateFile Status : %lx\n", Status);
  if ( v35 )
    WsRevertToSelf2(0, 0);
  if ( Status >= 0 )
    Status = IoStatusBlock.Status;
  v30 = WsMapStatus((unsigned int)Status);
LABEL_59:
  memset_0(hMem, 0, v38);
  LocalFree(hMem);
  return v30;
}

```

## disassembly

```asm
0x180004a40  mov     [rsp-8+arg_8], rbx
0x180004a45  mov     dword ptr [rsp-8+Size], r9d
0x180004a4a  mov     [rsp-8+arg_10], r8
0x180004a4f  push    rbp
0x180004a50  push    rsi
0x180004a51  push    rdi
0x180004a52  push    r12
0x180004a54  push    r13
0x180004a56  push    r14
0x180004a58  push    r15
0x180004a5a  lea     rbp, [rsp-7]
0x180004a5f  sub     rsp, 0A0h
0x180004a66  mov     r14, rdx
0x180004a69  xor     eax, eax
0x180004a6b  xor     edx, edx
0x180004a6d  xorps   xmm0, xmm0
0x180004a70  mov     dword ptr [rbp+37h+ObjectAttributes+4], edx
0x180004a73  mov     ebx, edx
0x180004a75  mov     dword ptr [rbp+37h+ObjectAttributes+1Ch], edx
0x180004a78  mov     [rbp+37h+arg_0], edx
0x180004a7b  movups  xmmword ptr [rbp+37h+IoStatusBlock], xmm0
0x180004a7f  test    r14, r14
0x180004a82  jnz     loc_180004D67
0x180004a88  mov     rax, [rbp+37h+hMem]
0x180004a8c  mov     [rbp+37h+ObjectAttributes.SecurityDescriptor], rax
0x180004a90  mov     eax, 4
0x180004a95  mov     [rbp+37h+ObjectAttributes.Length], 30h ; '0'
0x180004a9c  mov     [rbp+37h+ObjectAttributes.RootDirectory], rdx
0x180004aa0  mov     [rbp+37h+ObjectAttributes.Attributes], 40h ; '@'
0x180004aa7  mov     [rbp+37h+ObjectAttributes.ObjectName], rcx
0x180004aab  mov     [rbp+37h+ObjectAttributes.SecurityQualityOfService], rdx
0x180004aaf  test    r8, r8
0x180004ab2  jnz     loc_180004D74
0x180004ab8  mov     edi, [rbp+37h+arg_50]
0x180004abe  mov     esi, edi
0x180004ac0  and     esi, 1
0x180004ac3  jz      short loc_180004ACF
0x180004ac5  mov     [rbp+37h+arg_0], 14h
0x180004acc  add     ebx, 14h
0x180004acf  mov     r12, [rbp+37h+arg_20]
0x180004ad3  test    r12, r12
0x180004ad6  jnz     loc_180004D90
0x180004adc  mov     r13, [rbp+37h+arg_30]
0x180004ae0  test    r13, r13
0x180004ae3  jz      short loc_180004AF2
0x180004ae5  mov     [rbp+37h+arg_0], 94h
0x180004aec  add     ebx, 94h
0x180004af2  cmp     [rbp+37h+arg_38], 0
0x180004af7  jnz     loc_180004DB0
0x180004afd  cmp     [rbp+37h+arg_40], 0
0x180004b05  jnz     loc_180004DDA
0x180004b0b  cmp     [rbp+37h+arg_48], 0
0x180004b13  jnz     loc_180004E04
0x180004b19  mov     r15d, edi
0x180004b1c  and     r15d, 2
0x180004b20  jz      short loc_180004B2C
0x180004b22  mov     [rbp+37h+arg_0], 14h
0x180004b29  add     ebx, 14h
0x180004b2c  test    r14, r14
0x180004b2f  jnz     loc_180004E2E
0x180004b35  lea     eax, [rbx+11h]
0x180004b38  mov     ecx, 40h ; '@'; uFlags
0x180004b3d  mov     edx, eax; uBytes
0x180004b3f  mov     [rbp+37h+arg_50], eax
0x180004b45  call    cs:__imp_LocalAlloc
0x180004b4b  mov     [rbp+37h+hMem], rax
0x180004b4f  mov     r11, rax
0x180004b52  test    rax, rax
0x180004b55  jnz     short loc_180004B78
0x180004b57  call    cs:__imp_GetLastError
0x180004b5d  mov     rbx, [rsp+0D0h+arg_8]
0x180004b65  add     rsp, 0A0h
0x180004b6c  pop     r15
0x180004b6e  pop     r14
0x180004b70  pop     r13
0x180004b72  pop     r12
0x180004b74  pop     rdi
0x180004b75  pop     rsi
0x180004b76  pop     rbp
0x180004b77  retn
0x180004b78  test    esi, esi
0x180004b7a  jnz     loc_180004E48
0x180004b80  mov     rsi, r11
0x180004b83  test    r13, r13
0x180004b86  jnz     loc_180004E8B
0x180004b8c  mov     r10, [rbp+37h+arg_38]
0x180004b90  mov     r13d, 10h
0x180004b96  test    r10, r10
0x180004b99  jnz     loc_180004F13
0x180004b9f  mov     r10, [rbp+37h+arg_40]
0x180004ba6  mov     ebx, 8
0x180004bab  test    r10, r10
0x180004bae  jnz     loc_180004F6D
0x180004bb4  mov     r13d, 4
0x180004bba  mov     r10, [rbp+37h+arg_48]
0x180004bc1  test    r10, r10
0x180004bc4  jnz     loc_180004FC4
0x180004bca  test    r12, r12
0x180004bcd  jnz     loc_180005017
0x180004bd3  test    r15d, r15d
0x180004bd6  jnz     loc_180005071
0x180004bdc  test    r14, r14
0x180004bdf  jnz     loc_1800050AD
0x180004be5  mov     ecx, edi
0x180004be7  mov     eax, edi
0x180004be9  and     ecx, 4
0x180004bec  shl     ecx, 8
0x180004bef  or      ecx, 0A0h
0x180004bf5  mov     r15d, ecx
0x180004bf8  or      r15d, 2
0x180004bfc  test    dil, 40h
0x180004c00  cmovz   r15d, ecx
0x180004c04  and     eax, ebx
0x180004c06  shl     eax, 0Ch
0x180004c09  bts     eax, 7
0x180004c0d  mov     ebx, eax
0x180004c0f  bts     ebx, 0Eh
0x180004c13  test    dil, 10h
0x180004c17  cmovz   ebx, eax
0x180004c1a  cmp     [rbp+37h+arg_68], 0
0x180004c21  jnz     loc_180005103
0x180004c27  mov     r10, [rbp+37h+arg_10]
0x180004c2b  mov     edi, ebx
0x180004c2d  or      edi, 2
0x180004c30  cmp     [rbp+37h+arg_78], 0
0x180004c37  cmovz   edi, ebx
0x180004c3a  test    r10, r10
0x180004c3d  jnz     loc_18000511C
0x180004c43  mov     r14d, 5
0x180004c49  lea     r8, aType_0; "Type"
0x180004c50  mov     r9d, r14d
0x180004c53  lea     rax, [rsi+8]
0x180004c57  mov     ecx, 7FFFFFFEh
0x180004c5c  nop     dword ptr [rax+00h]
0x180004c60  test    rcx, rcx
0x180004c63  jz      short loc_180004C7E
0x180004c65  movzx   edx, byte ptr [r8]
0x180004c69  test    dl, dl
0x180004c6b  jz      short loc_180004C7E
0x180004c6d  mov     [rax], dl
0x180004c6f  inc     r8
0x180004c72  inc     rax
0x180004c75  dec     rcx
0x180004c78  sub     r9, 1
0x180004c7c  jnz     short loc_180004C60
0x180004c7e  movzx   ebx, [rbp+37h+arg_70]
0x180004c85  lea     rcx, [rax-1]
0x180004c89  test    r9, r9
0x180004c8c  cmovnz  rcx, rax
0x180004c90  mov     eax, [rbp+37h+arg_60]
0x180004c96  mov     byte ptr [rcx], 0
0x180004c99  mov     dword ptr [rsi+4], 40400h
0x180004ca0  mov     [rsi+0Dh], eax
0x180004ca3  mov     dword ptr [rsi], 0
0x180004ca9  test    bl, bl
0x180004cab  jnz     loc_180004D43
0x180004cb1  mov     eax, [rbp+37h+arg_58]
0x180004cb7  lea     r9, [rbp+37h+IoStatusBlock]; IoStatusBlock
0x180004cbb  mov     esi, [rbp+37h+arg_50]
0x180004cc1  lea     r8, [rbp+37h+ObjectAttributes]; ObjectAttributes
0x180004cc5  mov     rcx, [rbp+37h+FileHandle]; FileHandle
0x180004ccc  mov     edx, 100000h; DesiredAccess
0x180004cd1  mov     [rsp+0D0h+EaLength], esi; EaLength
0x180004cd5  mov     [rsp+0D0h+EaBuffer], r11; EaBuffer
0x180004cda  mov     [rsp+0D0h+CreateOptions], r15d; CreateOptions
0x180004cdf  mov     [rsp+0D0h+CreateDisposition], eax; CreateDisposition
0x180004ce3  mov     [rsp+0D0h+ShareAccess], 7; ShareAccess
0x180004ceb  mov     [rsp+0D0h+FileAttributes], edi; FileAttributes
0x180004cef  mov     [rsp+0D0h+AllocationSize], 0; AllocationSize
0x180004cf8  call    cs:__imp_NtCreateFile
0x180004cfe  mov     edx, eax
0x180004d00  lea     rcx, aNtcreatefileSt; "NtCreateFile Status : %lx\n"
0x180004d07  mov     edi, eax
0x180004d09  call    cs:__imp_DbgPrint
0x180004d0f  test    bl, bl
0x180004d11  jnz     short loc_180004D5C
0x180004d13  test    edi, edi
0x180004d15  cmovns  edi, dword ptr [rbp+37h+IoStatusBlock]
0x180004d19  mov     ecx, edi
0x180004d1b  call    WsMapStatus
0x180004d20  mov     r14d, eax
0x180004d23  mov     rcx, [rbp+37h+hMem]; void *
0x180004d27  xor     edx, edx; Val
0x180004d29  mov     r8d, esi; Size
0x180004d2c  call    memset_0
0x180004d31  mov     rcx, [rbp+37h+hMem]; hMem
0x180004d35  call    cs:__imp_LocalFree
0x180004d3b  mov     eax, r14d
0x180004d3e  jmp     loc_180004B5D
0x180004d43  xor     ecx, ecx; BindingHandle
0x180004d45  call    cs:__imp_RpcImpersonateClient
0x180004d4b  test    eax, eax
0x180004d4d  jnz     loc_18000516F
0x180004d53  mov     r11, [rbp+37h+hMem]
0x180004d57  jmp     loc_180004CB1
0x180004d5c  xor     edx, edx
0x180004d5e  xor     ecx, ecx
0x180004d60  call    WsRevertToSelf2
0x180004d65  jmp     short loc_180004D13
0x180004d67  cmp     [r14], ax
0x180004d6b  cmovz   r14, rdx
0x180004d6f  jmp     loc_180004A88
0x180004d74  lea     ecx, [r9+15h]
0x180004d78  mov     edx, eax
0x180004d7a  lea     r8, [rbp+37h+arg_0]
0x180004d7e  call    NetpULongRoundUp
0x180004d83  mov     ebx, [rbp+37h+arg_0]
0x180004d86  mov     eax, 4
0x180004d8b  jmp     loc_180004AB8
0x180004d90  movzx   ecx, word ptr [r12]
0x180004d95  lea     r8, [rbp+37h+arg_0]
0x180004d99  add     ecx, 12h
0x180004d9c  mov     edx, eax
0x180004d9e  call    NetpULongRoundUp
0x180004da3  add     ebx, [rbp+37h+arg_0]
0x180004da6  mov     eax, 4
0x180004dab  jmp     loc_180004ADC
0x180004db0  lea     r8, [rbp+37h+arg_0]
0x180004db4  mov     edx, eax
0x180004db6  mov     ecx, 26h ; '&'
0x180004dbb  call    NetpULongRoundUp
0x180004dc0  add     ebx, [rbp+37h+arg_0]
0x180004dc3  lea     rcx, aTransportParam; "Transport Params specified by user.\n"
0x180004dca  call    cs:__imp_DbgPrint
0x180004dd0  mov     eax, 4
0x180004dd5  jmp     loc_180004AFD
0x180004dda  lea     r8, [rbp+37h+arg_0]
0x180004dde  mov     edx, eax
0x180004de0  mov     ecx, 20h ; ' '
0x180004de5  call    NetpULongRoundUp
0x180004dea  add     ebx, [rbp+37h+arg_0]
0x180004ded  lea     rcx, aCompressionPar; "Compression params specified by user.\n"
0x180004df4  call    cs:__imp_DbgPrint
0x180004dfa  mov     eax, 4
0x180004dff  jmp     loc_180004B0B
0x180004e04  lea     r8, [rbp+37h+arg_0]
0x180004e08  mov     edx, eax
0x180004e0a  mov     ecx, 1Eh
0x180004e0f  call    NetpULongRoundUp
0x180004e14  add     ebx, [rbp+37h+arg_0]
0x180004e17  lea     rcx, aBlockntlmParam; "BlockNTLM params specified by user.\n"
0x180004e1e  call    cs:__imp_DbgPrint
0x180004e24  mov     eax, 4
0x180004e29  jmp     loc_180004B19
0x180004e2e  movzx   ecx, word ptr [r14]
0x180004e32  lea     r8, [rbp+37h+arg_0]
0x180004e36  add     ecx, 14h
0x180004e39  mov     edx, eax
0x180004e3b  call    NetpULongRoundUp
0x180004e40  add     ebx, [rbp+37h+arg_0]
0x180004e43  jmp     loc_180004B35
0x180004e48  lea     rcx, [rax+8]; pszDest
0x180004e4c  mov     edx, 0Ah; cbDest
0x180004e51  lea     r8, pszSrc; "NoConnect"
0x180004e58  call    StringCbCopyA
0x180004e5d  xor     eax, eax
0x180004e5f  mov     byte ptr [r11+5], 9
0x180004e64  mov     r8, r11
0x180004e67  mov     [r11+6], ax
0x180004e6c  mov     edx, 4
0x180004e71  mov     ecx, 12h
0x180004e76  call    NetpULongRoundUp
0x180004e7b  mov     esi, [r11]
0x180004e7e  add     rsi, r11
0x180004e81  mov     byte ptr [r11+4], 0
0x180004e86  jmp     loc_180004B83
0x180004e8b  lea     rcx, [rsi+8]; pszDest
0x180004e8f  mov     edx, 17h; cbDest
0x180004e94  lea     r8, aDeferredconnec; "DeferredConnectionInfo"
0x180004e9b  call    StringCbCopyA
0x180004ea0  mov     byte ptr [rsi+5], 16h
0x180004ea4  mov     r8, rsi
0x180004ea7  mov     word ptr [rsi+6], 74h ; 't'
0x180004ead  mov     edx, 4
0x180004eb2  movups  xmm0, xmmword ptr [r13+0]
0x180004eb7  mov     ecx, 93h
0x180004ebc  movups  xmmword ptr [rsi+1Fh], xmm0
0x180004ec0  movups  xmm1, xmmword ptr [r13+10h]
0x180004ec5  movups  xmmword ptr [rsi+2Fh], xmm1
0x180004ec9  movups  xmm0, xmmword ptr [r13+20h]
0x180004ece  movups  xmmword ptr [rsi+3Fh], xmm0
0x180004ed2  movups  xmm1, xmmword ptr [r13+30h]
0x180004ed7  movups  xmmword ptr [rsi+4Fh], xmm1
0x180004edb  movups  xmm0, xmmword ptr [r13+40h]
0x180004ee0  movups  xmmword ptr [rsi+5Fh], xmm0
0x180004ee4  movups  xmm1, xmmword ptr [r13+50h]
0x180004ee9  movups  xmmword ptr [rsi+6Fh], xmm1
0x180004eed  movups  xmm0, xmmword ptr [r13+60h]
0x180004ef2  movups  xmmword ptr [rsi+7Fh], xmm0
0x180004ef6  mov     eax, [r13+70h]
0x180004efa  mov     [rsi+8Fh], eax
0x180004f00  call    NetpULongRoundUp
0x180004f05  mov     eax, [rsi]
0x180004f07  mov     byte ptr [rsi+4], 0
0x180004f0b  add     rsi, rax
0x180004f0e  jmp     loc_180004B8C
0x180004f13  lea     rcx, [rsi+8]; pszDest
0x180004f17  mov     edx, 0Eh; cbDest
0x180004f1c  lea     r8, aTransportinfo; "TransportInfo"
0x180004f23  call    StringCbCopyA
  ... truncated ...
```
