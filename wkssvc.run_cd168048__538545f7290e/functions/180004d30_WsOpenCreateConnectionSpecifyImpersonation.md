# WsOpenCreateConnectionSpecifyImpersonation

- ea: `0x180004d30`
- end: `0x1800054fc`
- name: `WsOpenCreateConnectionSpecifyImpersonation`
- size: `1996`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, HLOCAL hMem, __int64, __int64, __int64, __int64, ULONG, ULONG, int, char, char, char, PHANDLE FileHandle)`
- caller_count: `4`
- callee_count: `8`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180001750`
- `0x180003db0`
- `0x18000a3a0`
- `0x18002be90`

## callees

- `0x180004d30`
- `0x180005df0`
- `0x180009010`
- `0x18000b4f0`
- `0x18000bf08`
- `0x1800204f6`
- `0x180031878`
- `0x180036191`

## import_xrefs

- `ntdll!DbgPrint` at `0x18000500f`
- `ntdll!DbgPrint` at `0x1800050e2`
- `ntdll!DbgPrint` at `0x180005112`
- `ntdll!DbgPrint` at `0x180005142`
- `ntdll!DbgPrint` at `0x180005288`
- `ntdll!DbgPrint` at `0x1800052e5`
- `ntdll!DbgPrint` at `0x18000533e`
- `ntdll!DbgPrint` at `0x180005449`
- `ntdll!DbgPrint` at `0x18000500f`
- `ntdll!DbgPrint` at `0x1800050e2`
- `ntdll!DbgPrint` at `0x180005112`
- `ntdll!DbgPrint` at `0x180005142`
- `ntdll!DbgPrint` at `0x180005288`
- `ntdll!DbgPrint` at `0x1800052e5`
- `ntdll!DbgPrint` at `0x18000533e`
- `ntdll!DbgPrint` at `0x180005449`
- `ntdll!NtCreateFile` at `0x180004ff8`
- `ntdll!NtCreateFile` at `0x180004ff8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004e4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004e4d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180004e35`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180004e35`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005041`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005041`
- `RPCRT4!RpcImpersonateClient` at `0x180005057`
- `RPCRT4!RpcImpersonateClient` at `0x180005057`

## string_xrefs

- `0x180005006`: `NtCreateFile Status : %lx\n`
- `0x1800052a4`: `CompressionInfo`
- `0x18000510b`: `Compression params specified by user.\n`
- `0x180005277`: `EA created for specified TransportParams. %u \n`
- `0x1800052d7`: `EA created for specified CompressionParams.`
- `0x180005330`: `EA created for specified BlockNTLMParams.`
- `0x1800053b6`: `CscAgent`

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
0x180004d30  mov     [rsp-8+arg_8], rbx
0x180004d35  mov     dword ptr [rsp-8+Size], r9d
0x180004d3a  mov     [rsp-8+arg_10], r8
0x180004d3f  push    rbp
0x180004d40  push    rsi
0x180004d41  push    rdi
0x180004d42  push    r12
0x180004d44  push    r13
0x180004d46  push    r14
0x180004d48  push    r15
0x180004d4a  lea     rbp, [rsp-7]
0x180004d4f  sub     rsp, 0A0h
0x180004d56  mov     r14, rdx
0x180004d59  xor     eax, eax
0x180004d5b  xor     edx, edx
0x180004d5d  xorps   xmm0, xmm0
0x180004d60  mov     dword ptr [rbp+37h+ObjectAttributes+4], edx
0x180004d63  mov     ebx, edx
0x180004d65  mov     dword ptr [rbp+37h+ObjectAttributes+1Ch], edx
0x180004d68  mov     [rbp+37h+arg_0], edx
0x180004d6b  movups  xmmword ptr [rbp+37h+IoStatusBlock], xmm0
0x180004d6f  test    r14, r14
0x180004d72  jnz     loc_18000507F
0x180004d78  mov     rax, [rbp+37h+hMem]
0x180004d7c  mov     [rbp+37h+ObjectAttributes.SecurityDescriptor], rax
0x180004d80  mov     eax, 4
0x180004d85  mov     [rbp+37h+ObjectAttributes.Length], 30h ; '0'
0x180004d8c  mov     [rbp+37h+ObjectAttributes.RootDirectory], rdx
0x180004d90  mov     [rbp+37h+ObjectAttributes.Attributes], 40h ; '@'
0x180004d97  mov     [rbp+37h+ObjectAttributes.ObjectName], rcx
0x180004d9b  mov     [rbp+37h+ObjectAttributes.SecurityQualityOfService], rdx
0x180004d9f  test    r8, r8
0x180004da2  jnz     loc_18000508C
0x180004da8  mov     edi, [rbp+37h+arg_50]
0x180004dae  mov     esi, edi
0x180004db0  and     esi, 1
0x180004db3  jz      short loc_180004DBF
0x180004db5  mov     [rbp+37h+arg_0], 14h
0x180004dbc  add     ebx, 14h
0x180004dbf  mov     r12, [rbp+37h+arg_20]
0x180004dc3  test    r12, r12
0x180004dc6  jnz     loc_1800050A8
0x180004dcc  mov     r13, [rbp+37h+arg_30]
0x180004dd0  test    r13, r13
0x180004dd3  jz      short loc_180004DE2
0x180004dd5  mov     [rbp+37h+arg_0], 94h
0x180004ddc  add     ebx, 94h
0x180004de2  cmp     [rbp+37h+arg_38], 0
0x180004de7  jnz     loc_1800050C8
0x180004ded  cmp     [rbp+37h+arg_40], 0
0x180004df5  jnz     loc_1800050F8
0x180004dfb  cmp     [rbp+37h+arg_48], 0
0x180004e03  jnz     loc_180005128
0x180004e09  mov     r15d, edi
0x180004e0c  and     r15d, 2
0x180004e10  jz      short loc_180004E1C
0x180004e12  mov     [rbp+37h+arg_0], 14h
0x180004e19  add     ebx, 14h
0x180004e1c  test    r14, r14
0x180004e1f  jnz     loc_180005158
0x180004e25  lea     eax, [rbx+11h]
0x180004e28  mov     ecx, 40h ; '@'; uFlags
0x180004e2d  mov     edx, eax; uBytes
0x180004e2f  mov     [rbp+37h+arg_50], eax
0x180004e35  call    cs:__imp_LocalAlloc
0x180004e3c  nop     dword ptr [rax+rax+00h]
0x180004e41  mov     [rbp+37h+hMem], rax
0x180004e45  mov     r11, rax
0x180004e48  test    rax, rax
0x180004e4b  jnz     short loc_180004E75
0x180004e4d  call    cs:__imp_GetLastError
0x180004e54  nop     dword ptr [rax+rax+00h]
0x180004e59  mov     rbx, [rsp+0D0h+arg_8]
0x180004e61  add     rsp, 0A0h
0x180004e68  pop     r15
0x180004e6a  pop     r14
0x180004e6c  pop     r13
0x180004e6e  pop     r12
0x180004e70  pop     rdi
0x180004e71  pop     rsi
0x180004e72  pop     rbp
0x180004e73  retn
0x180004e75  test    esi, esi
0x180004e77  jnz     loc_180005172
0x180004e7d  mov     rsi, r11
0x180004e80  test    r13, r13
0x180004e83  jnz     loc_1800051B5
0x180004e89  mov     r10, [rbp+37h+arg_38]
0x180004e8d  mov     r13d, 10h
0x180004e93  test    r10, r10
0x180004e96  jnz     loc_18000523D
0x180004e9c  mov     r10, [rbp+37h+arg_40]
0x180004ea3  mov     ebx, 8
0x180004ea8  test    r10, r10
0x180004eab  jnz     loc_18000529D
0x180004eb1  mov     r13d, 4
0x180004eb7  mov     r10, [rbp+37h+arg_48]
0x180004ebe  test    r10, r10
0x180004ec1  jnz     loc_1800052FA
0x180004ec7  test    r12, r12
0x180004eca  jnz     loc_180005353
0x180004ed0  test    r15d, r15d
0x180004ed3  jnz     loc_1800053AD
0x180004ed9  test    r14, r14
0x180004edc  jnz     loc_1800053E9
0x180004ee2  mov     ecx, edi
0x180004ee4  mov     eax, edi
0x180004ee6  and     ecx, 4
0x180004ee9  shl     ecx, 8
0x180004eec  or      ecx, 0A0h
0x180004ef2  mov     r15d, ecx
0x180004ef5  or      r15d, 2
0x180004ef9  test    dil, 40h
0x180004efd  cmovz   r15d, ecx
0x180004f01  and     eax, ebx
0x180004f03  shl     eax, 0Ch
0x180004f06  bts     eax, 7
0x180004f0a  mov     ebx, eax
0x180004f0c  bts     ebx, 0Eh
0x180004f10  test    dil, 10h
0x180004f14  cmovz   ebx, eax
0x180004f17  cmp     [rbp+37h+arg_68], 0
0x180004f1e  jnz     loc_18000543F
0x180004f24  mov     r10, [rbp+37h+arg_10]
0x180004f28  mov     edi, ebx
0x180004f2a  or      edi, 2
0x180004f2d  cmp     [rbp+37h+arg_78], 0
0x180004f34  cmovz   edi, ebx
0x180004f37  test    r10, r10
0x180004f3a  jnz     loc_18000545E
0x180004f40  mov     r14d, 5
0x180004f46  lea     r8, aType_0; "Type"
0x180004f4d  mov     r9d, r14d
0x180004f50  lea     rax, [rsi+8]
0x180004f54  mov     ecx, 7FFFFFFEh
0x180004f59  nop     dword ptr [rax+00000000h]
0x180004f60  test    rcx, rcx
0x180004f63  jz      short loc_180004F7E
0x180004f65  movzx   edx, byte ptr [r8]
0x180004f69  test    dl, dl
0x180004f6b  jz      short loc_180004F7E
0x180004f6d  mov     [rax], dl
0x180004f6f  inc     r8
0x180004f72  inc     rax
0x180004f75  dec     rcx
0x180004f78  sub     r9, 1
0x180004f7c  jnz     short loc_180004F60
0x180004f7e  movzx   ebx, [rbp+37h+arg_70]
0x180004f85  lea     rcx, [rax-1]
0x180004f89  test    r9, r9
0x180004f8c  cmovnz  rcx, rax
0x180004f90  mov     eax, [rbp+37h+arg_60]
0x180004f96  mov     byte ptr [rcx], 0
0x180004f99  mov     dword ptr [rsi+4], 40400h
0x180004fa0  mov     [rsi+0Dh], eax
0x180004fa3  mov     dword ptr [rsi], 0
0x180004fa9  test    bl, bl
0x180004fab  jnz     loc_180005055
0x180004fb1  mov     eax, [rbp+37h+arg_58]
0x180004fb7  lea     r9, [rbp+37h+IoStatusBlock]; IoStatusBlock
0x180004fbb  mov     esi, [rbp+37h+arg_50]
0x180004fc1  lea     r8, [rbp+37h+ObjectAttributes]; ObjectAttributes
0x180004fc5  mov     rcx, [rbp+37h+FileHandle]; FileHandle
0x180004fcc  mov     edx, 100000h; DesiredAccess
0x180004fd1  mov     [rsp+0D0h+EaLength], esi; EaLength
0x180004fd5  mov     [rsp+0D0h+EaBuffer], r11; EaBuffer
0x180004fda  mov     [rsp+0D0h+CreateOptions], r15d; CreateOptions
0x180004fdf  mov     [rsp+0D0h+CreateDisposition], eax; CreateDisposition
0x180004fe3  mov     [rsp+0D0h+ShareAccess], 7; ShareAccess
0x180004feb  mov     [rsp+0D0h+FileAttributes], edi; FileAttributes
0x180004fef  mov     [rsp+0D0h+AllocationSize], 0; AllocationSize
0x180004ff8  call    cs:__imp_NtCreateFile
0x180004fff  nop     dword ptr [rax+rax+00h]
0x180005004  mov     edx, eax
0x180005006  lea     rcx, aNtcreatefileSt; "NtCreateFile Status : %lx\n"
0x18000500d  mov     edi, eax
0x18000500f  call    cs:__imp_DbgPrint
0x180005016  nop     dword ptr [rax+rax+00h]
0x18000501b  test    bl, bl
0x18000501d  jnz     short loc_180005074
0x18000501f  test    edi, edi
0x180005021  cmovns  edi, dword ptr [rbp+37h+IoStatusBlock]
0x180005025  mov     ecx, edi
0x180005027  call    WsMapStatus
0x18000502c  mov     r14d, eax
0x18000502f  mov     rcx, [rbp+37h+hMem]; void *
0x180005033  xor     edx, edx; Val
0x180005035  mov     r8d, esi; Size
0x180005038  call    memset_0
0x18000503d  mov     rcx, [rbp+37h+hMem]; hMem
0x180005041  call    cs:__imp_LocalFree
0x180005048  nop     dword ptr [rax+rax+00h]
0x18000504d  mov     eax, r14d
0x180005050  jmp     loc_180004E59
0x180005055  xor     ecx, ecx; BindingHandle
0x180005057  call    cs:__imp_RpcImpersonateClient
0x18000505e  nop     dword ptr [rax+rax+00h]
0x180005063  test    eax, eax
0x180005065  jnz     loc_1800054B1
0x18000506b  mov     r11, [rbp+37h+hMem]
0x18000506f  jmp     loc_180004FB1
0x180005074  xor     edx, edx
0x180005076  xor     ecx, ecx
0x180005078  call    WsRevertToSelf2
0x18000507d  jmp     short loc_18000501F
0x18000507f  cmp     [r14], ax
0x180005083  cmovz   r14, rdx
0x180005087  jmp     loc_180004D78
0x18000508c  lea     ecx, [r9+15h]
0x180005090  mov     edx, eax
0x180005092  lea     r8, [rbp+37h+arg_0]
0x180005096  call    NetpULongRoundUp
0x18000509b  mov     ebx, [rbp+37h+arg_0]
0x18000509e  mov     eax, 4
0x1800050a3  jmp     loc_180004DA8
0x1800050a8  movzx   ecx, word ptr [r12]
0x1800050ad  lea     r8, [rbp+37h+arg_0]
0x1800050b1  add     ecx, 12h
0x1800050b4  mov     edx, eax
0x1800050b6  call    NetpULongRoundUp
0x1800050bb  add     ebx, [rbp+37h+arg_0]
0x1800050be  mov     eax, 4
0x1800050c3  jmp     loc_180004DCC
0x1800050c8  lea     r8, [rbp+37h+arg_0]
0x1800050cc  mov     edx, eax
0x1800050ce  mov     ecx, 26h ; '&'
0x1800050d3  call    NetpULongRoundUp
0x1800050d8  add     ebx, [rbp+37h+arg_0]
0x1800050db  lea     rcx, aTransportParam; "Transport Params specified by user.\n"
0x1800050e2  call    cs:__imp_DbgPrint
0x1800050e9  nop     dword ptr [rax+rax+00h]
0x1800050ee  mov     eax, 4
0x1800050f3  jmp     loc_180004DED
0x1800050f8  lea     r8, [rbp+37h+arg_0]
0x1800050fc  mov     edx, eax
0x1800050fe  mov     ecx, 20h ; ' '
0x180005103  call    NetpULongRoundUp
0x180005108  add     ebx, [rbp+37h+arg_0]
0x18000510b  lea     rcx, aCompressionPar; "Compression params specified by user.\n"
0x180005112  call    cs:__imp_DbgPrint
0x180005119  nop     dword ptr [rax+rax+00h]
0x18000511e  mov     eax, 4
0x180005123  jmp     loc_180004DFB
0x180005128  lea     r8, [rbp+37h+arg_0]
0x18000512c  mov     edx, eax
0x18000512e  mov     ecx, 1Eh
0x180005133  call    NetpULongRoundUp
0x180005138  add     ebx, [rbp+37h+arg_0]
0x18000513b  lea     rcx, aBlockntlmParam; "BlockNTLM params specified by user.\n"
0x180005142  call    cs:__imp_DbgPrint
0x180005149  nop     dword ptr [rax+rax+00h]
0x18000514e  mov     eax, 4
0x180005153  jmp     loc_180004E09
0x180005158  movzx   ecx, word ptr [r14]
0x18000515c  lea     r8, [rbp+37h+arg_0]
0x180005160  add     ecx, 14h
0x180005163  mov     edx, eax
0x180005165  call    NetpULongRoundUp
0x18000516a  add     ebx, [rbp+37h+arg_0]
0x18000516d  jmp     loc_180004E25
0x180005172  lea     rcx, [rax+8]; pszDest
0x180005176  mov     edx, 0Ah; cbDest
0x18000517b  lea     r8, pszSrc; "NoConnect"
0x180005182  call    StringCbCopyA
0x180005187  xor     eax, eax
0x180005189  mov     byte ptr [r11+5], 9
0x18000518e  mov     r8, r11
0x180005191  mov     [r11+6], ax
0x180005196  mov     edx, 4
0x18000519b  mov     ecx, 12h
0x1800051a0  call    NetpULongRoundUp
0x1800051a5  mov     esi, [r11]
0x1800051a8  add     rsi, r11
0x1800051ab  mov     byte ptr [r11+4], 0
0x1800051b0  jmp     loc_180004E80
0x1800051b5  lea     rcx, [rsi+8]; pszDest
0x1800051b9  mov     edx, 17h; cbDest
0x1800051be  lea     r8, aDeferredconnec; "DeferredConnectionInfo"
0x1800051c5  call    StringCbCopyA
0x1800051ca  mov     byte ptr [rsi+5], 16h
0x1800051ce  mov     r8, rsi
0x1800051d1  mov     word ptr [rsi+6], 74h ; 't'
0x1800051d7  mov     edx, 4
0x1800051dc  movups  xmm0, xmmword ptr [r13+0]
0x1800051e1  mov     ecx, 93h
0x1800051e6  movups  xmmword ptr [rsi+1Fh], xmm0
0x1800051ea  movups  xmm1, xmmword ptr [r13+10h]
0x1800051ef  movups  xmmword ptr [rsi+2Fh], xmm1
0x1800051f3  movups  xmm0, xmmword ptr [r13+20h]
0x1800051f8  movups  xmmword ptr [rsi+3Fh], xmm0
0x1800051fc  movups  xmm1, xmmword ptr [r13+30h]
0x180005201  movups  xmmword ptr [rsi+4Fh], xmm1
0x180005205  movups  xmm0, xmmword ptr [r13+40h]
0x18000520a  movups  xmmword ptr [rsi+5Fh], xmm0
0x18000520e  movups  xmm1, xmmword ptr [r13+50h]
0x180005213  movups  xmmword ptr [rsi+6Fh], xmm1
0x180005217  movups  xmm0, xmmword ptr [r13+60h]
0x18000521c  movups  xmmword ptr [rsi+7Fh], xmm0
0x180005220  mov     eax, [r13+70h]
0x180005224  mov     [rsi+8Fh], eax
  ... truncated ...
```
