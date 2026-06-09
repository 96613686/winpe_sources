# WsFindUse

- ea: `0x18000a3a0`
- end: `0x18000a721`
- name: `WsFindUse`
- size: `897`
- prototype: `__int64 __usercall@<rax>(PLUID SourceLuid@<rcx>, __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800012a0`

## callees

- `0x180002640`
- `0x180004d30`
- `0x180005504`
- `0x18000a3a0`
- `0x18000a730`
- `0x18001fbd0`
- `0x18003190c`

## import_xrefs

- `ntdll!RtlCopyLuid` at `0x18000a5a2`
- `ntdll!RtlCopyLuid` at `0x18000a5a2`
- `ntdll!RtlCompareUnicodeString` at `0x18000a479`
- `ntdll!RtlCompareUnicodeString` at `0x18000a479`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a65a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a70e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a65a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a70e`

## pseudocode

```c
__int64 __fastcall WsFindUse(PLUID SourceLuid, __int64 *a2, WCHAR *a3, void **a4, _QWORD *a5, _QWORD *a6)
{
  __int64 *v8; // rdi
  __int64 *v9; // rsi
  WCHAR *v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 *v13; // r14
  __int64 result; // rax
  unsigned __int8 v15; // r12
  PHANDLE v16; // rcx
  __int64 v17; // r13
  __int64 v18; // r14
  BOOL v19; // edi
  unsigned __int16 *v20; // rax
  void *v21; // rsi
  unsigned int v22; // r13d
  unsigned __int16 *v23; // rcx
  DWORD ConnectionSpecifyImpersonation; // ebx
  UNICODE_STRING String1; // [rsp+90h] [rbp-80h] BYREF
  PHANDLE FileHandle; // [rsp+A0h] [rbp-70h]
  UNICODE_STRING String2; // [rsp+A8h] [rbp-68h] BYREF
  HLOCAL hMem[2]; // [rsp+B8h] [rbp-58h] BYREF
  _DWORD v29[2]; // [rsp+C8h] [rbp-48h] BYREF
  struct _LUID DestinationLuid[2]; // [rsp+D0h] [rbp-40h] BYREF
  __int64 v31; // [rsp+E0h] [rbp-30h]
  int v32; // [rsp+E8h] [rbp-28h]

  FileHandle = a4;
  v8 = a2;
  *(_QWORD *)&String1.Length = a5;
  v15 = *SourceLuid == -1;
  if ( a3[1] != 92 )
  {
    v9 = a2;
    while ( 1 )
    {
      if ( !v8 )
      {
        *a5 = 0;
        return 2250;
      }
      v10 = (WCHAR *)v8[2];
      if ( v10 )
      {
        String1 = 0;
        v11 = -1;
        String2 = 0;
        do
          ++v11;
        while ( v10[v11] );
        String1.Buffer = v10;
        String1.MaximumLength = 2 * (v11 + 1);
        String1.Length = String1.MaximumLength;
        v12 = -1;
        do
          ++v12;
        while ( a3[v12] );
        String2.Buffer = a3;
        String2.MaximumLength = 2 * (v12 + 1);
        String2.Length = String2.MaximumLength;
        if ( !RtlCompareUnicodeString(&String1, &String2, 1u) )
          break;
      }
      v9 = v8;
      v8 = (__int64 *)*v8;
    }
    v16 = FileHandle;
    *a5 = v8;
    *v16 = (void *)v8[4];
    if ( a6 )
      *a6 = v9;
    return 0;
  }
  v13 = a2;
  while ( v8 )
  {
    if ( !v8[2] && !(unsigned int)FULLSTRICMP(v8[1] + 8, a3, a3) )
      goto LABEL_14;
    v13 = v8;
    v8 = (__int64 *)*v8;
  }
  v13 = 0;
  v8 = 0;
LABEL_14:
  **(_QWORD **)&String1.Length = v8;
  if ( v8 )
  {
    *FileHandle = (void *)v8[4];
    if ( a6 )
      *a6 = v13;
    return 0;
  }
  v31 = 0;
  v17 = -1;
  v32 = 0;
  *(_OWORD *)&DestinationLuid[0].LowPart = 0;
  v18 = -1;
  *(_QWORD *)&String1.Length = 0;
  do
    ++v18;
  while ( a3[v18] );
  v29[0] = 1;
  v29[1] = 6;
  *(_OWORD *)hMem = 0;
  RtlCopyLuid((PLUID)&DestinationLuid[0].HighPart, SourceLuid);
  DestinationLuid[0].LowPart = 0;
  v32 = 0;
  result = WsDeviceControlGetInfo(0, WsRedirDeviceHandle, 1311143, v29, 36, &String1, -1, 0);
  if ( !(_DWORD)result )
  {
    v19 = 0;
    v20 = *(unsigned __int16 **)&String1.Length;
    v21 = *(void **)&String1.Length;
    *(_QWORD *)&String2.Length = *(_QWORD *)&String1.Length;
    if ( DestinationLuid[1].HighPart )
    {
      v22 = 0;
      v23 = *(unsigned __int16 **)&String1.Length;
      do
      {
        if ( v19 )
          break;
        v19 = WsCompareStringU(*((_QWORD *)v23 + 1), *v20 >> 1, a3, (unsigned int)v18) == 0;
        v20 = (unsigned __int16 *)(*(_QWORD *)&String1.Length + 24LL);
        ++v22;
        *(_QWORD *)&String1.Length = v20;
        v23 = v20;
      }
      while ( v22 < DestinationLuid[1].HighPart );
      v21 = *(void **)&String2.Length;
      v17 = -1;
    }
    LocalFree(v21);
    if ( v19 )
    {
      do
        ++v17;
      while ( a3[v17] );
      result = WsCreateTreeConnectName((int)a3, v17, 0, v15, (PUNICODE_STRING)hMem);
      if ( !(_DWORD)result )
      {
        ConnectionSpecifyImpersonation = WsOpenCreateConnectionSpecifyImpersonation(
                                           (struct _UNICODE_STRING *)hMem,
                                           0,
                                           0,
                                           0,
                                           0,
                                           0,
                                           0,
                                           0,
                                           0,
                                           0,
                                           0,
                                           1u,
                                           -1,
                                           v15,
                                           1,
                                           0,
                                           FileHandle);
        LocalFree(hMem[1]);
        return ConnectionSpecifyImpersonation;
      }
    }
    else
    {
      return 2250;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000a3a0  push    rbp
0x18000a3a2  push    rbx
0x18000a3a3  push    rsi
0x18000a3a4  push    rdi
0x18000a3a5  push    r12
0x18000a3a7  push    r13
0x18000a3a9  push    r14
0x18000a3ab  mov     rbp, rsp
0x18000a3ae  sub     rsp, 110h
0x18000a3b5  mov     rax, cs:__security_cookie
0x18000a3bc  xor     rax, rsp
0x18000a3bf  mov     [rbp+var_20], rax
0x18000a3c3  mov     r14, [rbp+arg_20]
0x18000a3c7  mov     rsi, rcx
0x18000a3ca  mov     r13, [rbp+arg_28]
0x18000a3ce  xor     r12b, r12b
0x18000a3d1  mov     [rbp+var_70], r9
0x18000a3d5  mov     rbx, r8
0x18000a3d8  mov     rdi, rdx
0x18000a3db  mov     qword ptr [rbp+String1.Length], r14
0x18000a3df  cmp     dword ptr [rsi+4], 0FFFFFFFFh
0x18000a3e3  mov     ecx, 1
0x18000a3e8  jz      loc_18000A501
0x18000a3ee  cmp     word ptr [r8+2], 5Ch ; '\'
0x18000a3f4  mov     [rsp+110h+var_8], r15
0x18000a3fc  jz      loc_18000A49F
0x18000a402  mov     rsi, rdi
0x18000a405  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x18000a40c  nop     dword ptr [rax+00h]
0x18000a410  test    rdi, rdi
0x18000a413  jz      loc_18000A52A
0x18000a419  mov     rcx, [rdi+10h]
0x18000a41d  test    rcx, rcx
0x18000a420  jz      short loc_18000A494
0x18000a422  xorps   xmm0, xmm0
0x18000a425  xorps   xmm1, xmm1
0x18000a428  movups  xmmword ptr [rbp+String1.Length], xmm0
0x18000a42c  mov     rax, rdx
0x18000a42f  movups  xmmword ptr [rbp+String2.Length], xmm1
0x18000a433  inc     rax
0x18000a436  cmp     word ptr [rcx+rax*2], 0
0x18000a43b  jnz     short loc_18000A433
0x18000a43d  inc     ax
0x18000a440  mov     [rbp+String1.Buffer], rcx
0x18000a444  add     ax, ax
0x18000a447  mov     [rbp+String1.MaximumLength], ax
0x18000a44b  mov     [rbp+String1.Length], ax
0x18000a44f  mov     rax, rdx
0x18000a452  inc     rax
0x18000a455  cmp     word ptr [rbx+rax*2], 0
0x18000a45a  jnz     short loc_18000A452
0x18000a45c  inc     ax
0x18000a45f  mov     [rbp+String2.Buffer], rbx
0x18000a463  add     ax, ax
0x18000a466  lea     rdx, [rbp+String2]; String2
0x18000a46a  mov     r8b, 1; CaseInsensitive
0x18000a46d  mov     [rbp+String2.MaximumLength], ax
0x18000a471  lea     rcx, [rbp+String1]; String1
0x18000a475  mov     [rbp+String2.Length], ax
0x18000a479  call    cs:__imp_RtlCompareUnicodeString
0x18000a480  nop     dword ptr [rax+rax+00h]
0x18000a485  test    eax, eax
0x18000a487  jz      loc_18000A511
0x18000a48d  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x18000a494  mov     rsi, rdi
0x18000a497  mov     rdi, [rdi]
0x18000a49a  jmp     loc_18000A410
0x18000a49f  mov     r14, rdi
0x18000a4a2  xor     r15d, r15d
0x18000a4a5  test    rdi, rdi
0x18000a4a8  jnz     loc_18000A535
0x18000a4ae  mov     r14d, r15d
0x18000a4b1  mov     edi, r15d
0x18000a4b4  mov     rax, qword ptr [rbp+String1.Length]
0x18000a4b8  mov     [rax], rdi
0x18000a4bb  test    rdi, rdi
0x18000a4be  jz      loc_18000A55E
0x18000a4c4  mov     rcx, [rbp+var_70]
0x18000a4c8  mov     rax, [rdi+20h]
0x18000a4cc  mov     [rcx], rax
0x18000a4cf  test    r13, r13
0x18000a4d2  jz      short loc_18000A4D8
0x18000a4d4  mov     [r13+0], r14
0x18000a4d8  xor     eax, eax
0x18000a4da  mov     r15, [rsp+110h+var_8]
0x18000a4e2  mov     rcx, [rbp+var_20]
0x18000a4e6  xor     rcx, rsp; StackCookie
0x18000a4e9  call    __security_check_cookie
0x18000a4ee  add     rsp, 110h
0x18000a4f5  pop     r14
0x18000a4f7  pop     r13
0x18000a4f9  pop     r12
0x18000a4fb  pop     rdi
0x18000a4fc  pop     rsi
0x18000a4fd  pop     rbx
0x18000a4fe  pop     rbp
0x18000a4ff  retn
0x18000a501  cmp     dword ptr [rsi], 0FFFFFFFFh
0x18000a504  movzx   r12d, r12b
0x18000a508  cmovz   r12d, ecx
0x18000a50c  jmp     loc_18000A3EE
0x18000a511  mov     rcx, [rbp+var_70]
0x18000a515  mov     [r14], rdi
0x18000a518  mov     rax, [rdi+20h]
0x18000a51c  mov     [rcx], rax
0x18000a51f  test    r13, r13
0x18000a522  jz      short loc_18000A4D8
0x18000a524  mov     [r13+0], rsi
0x18000a528  jmp     short loc_18000A4D8
0x18000a52a  xor     r15d, r15d
0x18000a52d  mov     [r14], r15
0x18000a530  jmp     loc_18000A66A
0x18000a535  cmp     [rdi+10h], r15
0x18000a539  jnz     short loc_18000A553
0x18000a53b  mov     rcx, [rdi+8]
0x18000a53f  mov     rdx, rbx
0x18000a542  add     rcx, 8
0x18000a546  call    FULLSTRICMP
0x18000a54b  test    eax, eax
0x18000a54d  jz      loc_18000A4B4
0x18000a553  mov     r14, rdi
0x18000a556  mov     rdi, [rdi]
0x18000a559  jmp     loc_18000A4A2
0x18000a55e  xorps   xmm0, xmm0
0x18000a561  mov     [rbp+var_30], r15
0x18000a565  mov     r13, 0FFFFFFFFFFFFFFFFh
0x18000a56c  mov     [rbp+var_28], r15d
0x18000a570  movdqu  xmmword ptr [rbp+DestinationLuid.LowPart], xmm0
0x18000a575  mov     r14, r13
0x18000a578  mov     qword ptr [rbp+String1.Length], r15
0x18000a57c  inc     r14
0x18000a57f  cmp     [rbx+r14*2], r15w
0x18000a584  jnz     short loc_18000A57C
0x18000a586  xorps   xmm0, xmm0
0x18000a589  mov     [rbp+var_48], 1
0x18000a590  mov     rdx, rsi; SourceLuid
0x18000a593  mov     [rbp+var_44], 6
0x18000a59a  lea     rcx, [rbp+DestinationLuid.HighPart]; DestinationLuid
0x18000a59e  movups  xmmword ptr [rbp+hMem], xmm0
0x18000a5a2  call    cs:__imp_RtlCopyLuid
0x18000a5a9  nop     dword ptr [rax+rax+00h]
0x18000a5ae  mov     rdx, cs:WsRedirDeviceHandle
0x18000a5b5  lea     rax, [rbp+String1]
0x18000a5b9  mov     dword ptr [rsp+110h+var_D8], r15d
0x18000a5be  lea     r9, [rbp+var_48]
0x18000a5c2  mov     dword ptr [rsp+110h+var_E0], 0FFFFFFFFh
0x18000a5ca  mov     r8d, 1401A7h
0x18000a5d0  mov     [rsp+110h+var_E8], rax
0x18000a5d5  xor     ecx, ecx
0x18000a5d7  mov     dword ptr [rsp+110h+Destination], 24h ; '$'
0x18000a5df  mov     [rbp+DestinationLuid.LowPart], r15d
0x18000a5e3  mov     [rbp+var_28], r15d
0x18000a5e7  call    WsDeviceControlGetInfo
0x18000a5ec  test    eax, eax
0x18000a5ee  jnz     loc_18000A4DA
0x18000a5f4  mov     edi, r15d
0x18000a5f7  mov     rax, qword ptr [rbp+String1.Length]
0x18000a5fb  mov     rsi, rax
0x18000a5fe  mov     qword ptr [rbp+String2.Length], rax
0x18000a602  cmp     [rbp+DestinationLuid.HighPart+8], r15d
0x18000a606  jbe     short loc_18000A657
0x18000a608  mov     r13d, r15d
0x18000a60b  mov     qword ptr [rbp+String1.Length], rax
0x18000a60f  mov     rcx, rax
0x18000a612  mov     esi, 1
0x18000a617  test    edi, edi
0x18000a619  jnz     short loc_18000A64C
0x18000a61b  movzx   edx, word ptr [rax]
0x18000a61e  mov     r9d, r14d
0x18000a621  mov     rcx, [rcx+8]
0x18000a625  mov     r8, rbx
0x18000a628  shr     edx, 1
0x18000a62a  call    WsCompareStringU
0x18000a62f  test    eax, eax
0x18000a631  mov     rax, qword ptr [rbp+String1.Length]
0x18000a635  cmovz   edi, esi
0x18000a638  add     rax, 18h
0x18000a63c  inc     r13d
0x18000a63f  mov     qword ptr [rbp+String1.Length], rax
0x18000a643  mov     rcx, rax
0x18000a646  cmp     r13d, [rbp+DestinationLuid.HighPart+8]
0x18000a64a  jb      short loc_18000A617
0x18000a64c  mov     rsi, qword ptr [rbp+String2.Length]
0x18000a650  mov     r13, 0FFFFFFFFFFFFFFFFh
0x18000a657  mov     rcx, rsi; hMem
0x18000a65a  call    cs:__imp_LocalFree
0x18000a661  nop     dword ptr [rax+rax+00h]
0x18000a666  test    edi, edi
0x18000a668  jnz     short loc_18000A674
0x18000a66a  mov     eax, 8CAh
0x18000a66f  jmp     loc_18000A4DA
0x18000a674  inc     r13
0x18000a677  cmp     [rbx+r13*2], r15w
0x18000a67c  jnz     short loc_18000A674
0x18000a67e  lea     rax, [rbp+hMem]
0x18000a682  movzx   r9d, r12b; int
0x18000a686  xor     r8d, r8d; int
0x18000a689  mov     [rsp+110h+Destination], rax; Destination
0x18000a68e  mov     edx, r13d; int
0x18000a691  mov     rcx, rbx; int
0x18000a694  call    WsCreateTreeConnectName
0x18000a699  test    eax, eax
0x18000a69b  jnz     loc_18000A4DA
0x18000a6a1  mov     rcx, [rbp+var_70]
0x18000a6a5  xor     r9d, r9d; int
0x18000a6a8  mov     [rsp+110h+var_88], r15
0x18000a6b0  xor     r8d, r8d; int
0x18000a6b3  mov     [rsp+110h+FileHandle], rcx; FileHandle
0x18000a6bb  xor     edx, edx; int
0x18000a6bd  mov     [rsp+110h+var_98], r15b; char
0x18000a6c2  lea     rcx, [rbp+hMem]; int
0x18000a6c6  mov     [rsp+110h+var_A0], 1; char
0x18000a6cb  mov     [rsp+110h+var_A8], r12b; char
0x18000a6d0  mov     [rsp+110h+var_B0], 0FFFFFFFFh; int
0x18000a6d8  mov     [rsp+110h+var_B8], 1; ULONG
0x18000a6e0  mov     [rsp+110h+var_C0], r15d; ULONG
0x18000a6e5  mov     [rsp+110h+var_C8], r15; __int64
0x18000a6ea  mov     [rsp+110h+var_D0], r15; __int64
0x18000a6ef  mov     [rsp+110h+var_D8], r15; __int64
0x18000a6f4  mov     [rsp+110h+var_E0], r15; __int64
0x18000a6f9  mov     [rsp+110h+var_E8], r15; hMem
0x18000a6fe  mov     [rsp+110h+Destination], r15; __int64
0x18000a703  call    WsOpenCreateConnectionSpecifyImpersonation
0x18000a708  mov     rcx, [rbp+hMem+8]; hMem
0x18000a70c  mov     ebx, eax
0x18000a70e  call    cs:__imp_LocalFree
0x18000a715  nop     dword ptr [rax+rax+00h]
0x18000a71a  mov     eax, ebx
0x18000a71c  jmp     loc_18000A4DA
```
