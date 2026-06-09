# SclpGptInitZeroedPartitionGuids

- ea: `0x18000f22c`
- end: `0x18000f432`
- name: `SclpGptInitZeroedPartitionGuids`
- size: `518`
- prototype: `__int64 __fastcall(_BYTE *, unsigned int, char *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, installer_update`

## callers

- `0x18000f110`

## callees

- `0x18000a524`
- `0x18000e8d4`
- `0x18000ea28`
- `0x18000f22c`
- `0x18000f438`
- `0x180014da0`
- `0x1800179e0`

## import_xrefs

- `ntdll!NtClose` at `0x18000f403`
- `ntdll!NtClose` at `0x18000f403`
- `ntdll!RtlFreeHeap` at `0x18000f3f4`
- `ntdll!RtlFreeHeap` at `0x18000f3f4`

## string_xrefs

- `0x18000f374`: `Found and updated NULL GUID at partition %u`

## pseudocode

```c
__int64 __fastcall SclpGptInitZeroedPartitionGuids(_BYTE *a1, unsigned int a2, char *a3)
{
  unsigned int v4; // r13d
  __int64 v5; // rcx
  _DWORD *v6; // rdi
  char v8; // r12
  int DiskHandle; // ebx
  int DiskLayout; // eax
  __int64 v11; // r14
  unsigned __int64 v12; // rcx
  __int64 v13; // rcx
  unsigned int v15; // [rsp+40h] [rbp-40h] BYREF
  HANDLE Handle; // [rsp+48h] [rbp-38h] BYREF
  __int64 v17; // [rsp+50h] [rbp-30h]
  char *v18; // [rsp+58h] [rbp-28h]
  __int128 OutputBuffer; // [rsp+60h] [rbp-20h] BYREF

  v18 = a3;
  v4 = 0;
  v5 = (__int64)(a1 + 1152);
  v6 = 0;
  *a3 = 0;
  v15 = 0;
  v8 = 0;
  Handle = 0;
  *(_QWORD *)&OutputBuffer = 0;
  if ( !a1 )
    v5 = 0;
  v17 = v5;
  SclLogGenericMessage(
    v5,
    1,
    (int)SclEvent_Generic_Info,
    235,
    (__int64)"SclpGptInitZeroedPartitionGuids",
    "Inspecting disk %u",
    a2);
  DiskHandle = SclGetDiskHandle((__int64)a1, a2, &Handle);
  if ( DiskHandle >= 0 )
  {
    DiskLayout = SclGetDiskLayout(a1, Handle, &OutputBuffer, &v15);
    v6 = (_DWORD *)OutputBuffer;
    DiskHandle = DiskLayout;
    v4 = v15;
  }
  v11 = 0;
LABEL_14:
  if ( DiskHandle >= 0 )
  {
    while ( (unsigned int)v11 < v6[1] )
    {
      if ( v6[36 * v11 + 12] != 1 )
        goto LABEL_13;
      v12 = *(_QWORD *)&v6[36 * v11 + 24];
      if ( !v12 )
        v12 = *(_QWORD *)&v6[36 * v11 + 26] - _mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
      if ( v12 )
      {
LABEL_13:
        v11 = (unsigned int)(v11 + 1);
        goto LABEL_14;
      }
      OutputBuffer = 0;
      if ( !GenerateRandomData(&OutputBuffer, 0x10u) )
      {
        DiskHandle = -1073741823;
        goto LABEL_21;
      }
      v13 = v17;
      DiskHandle = 0;
      *(_OWORD *)&v6[36 * v11 + 24] = OutputBuffer;
      SclLogGenericMessage(
        v13,
        1,
        (int)SclEvent_Generic_Info,
        270,
        (__int64)"SclpGptInitZeroedPartitionGuids",
        "Found and updated NULL GUID at partition %u",
        v6[36 * v11 + 18]);
      v11 = (unsigned int)(v11 + 1);
      v8 = 1;
    }
    if ( !v8 || !*a1 || (DiskHandle = SclpSetDiskLayout(a1, Handle, v6, v4), DiskHandle >= 0) )
      *v18 = v8;
  }
LABEL_21:
  if ( v6 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v6);
  if ( Handle )
    NtClose(Handle);
  return (unsigned int)DiskHandle;
}

```

## disassembly

```asm
0x18000f22c  mov     [rsp-38h+arg_18], rbx
0x18000f231  push    rbp
0x18000f232  push    rsi
0x18000f233  push    rdi
0x18000f234  push    r12
0x18000f236  push    r13
0x18000f238  push    r14
0x18000f23a  push    r15
0x18000f23c  mov     rbp, rsp
0x18000f23f  sub     rsp, 80h
0x18000f246  mov     rax, cs:__security_cookie
0x18000f24d  xor     rax, rsp
0x18000f250  mov     [rbp+var_10], rax
0x18000f254  xor     eax, eax
0x18000f256  mov     [rsp+80h+var_50], edx
0x18000f25a  mov     r15, rcx
0x18000f25d  mov     [rbp+var_28], r8
0x18000f261  xor     r13d, r13d
0x18000f264  add     rcx, 480h
0x18000f26b  xor     edi, edi
0x18000f26d  mov     [r8], r13b
0x18000f270  mov     ebx, edx
0x18000f272  mov     [rbp+var_40], r13d
0x18000f276  xor     r12b, r12b
0x18000f279  mov     [rbp+Handle], r13
0x18000f27d  test    r15, r15
0x18000f280  mov     qword ptr [rbp+OutputBuffer], rdi
0x18000f284  mov     r9d, 0EBh
0x18000f28a  lea     r8, SclEvent_Generic_Info
0x18000f291  cmovz   rcx, rax
0x18000f295  lea     edx, [rdi+1]
0x18000f298  lea     rax, aInspectingDisk; "Inspecting disk %u"
0x18000f29f  mov     [rbp+var_30], rcx
0x18000f2a3  mov     [rsp+80h+var_58], rax
0x18000f2a8  lea     rax, aSclpgptinitzer; "SclpGptInitZeroedPartitionGuids"
0x18000f2af  mov     [rsp+80h+var_60], rax
0x18000f2b4  call    SclLogGenericMessage
0x18000f2b9  lea     r8, [rbp+Handle]
0x18000f2bd  mov     edx, ebx
0x18000f2bf  mov     rcx, r15
0x18000f2c2  call    SclGetDiskHandle
0x18000f2c7  mov     ebx, eax
0x18000f2c9  test    eax, eax
0x18000f2cb  js      short loc_18000F2EB
0x18000f2cd  mov     rdx, [rbp+Handle]
0x18000f2d1  lea     r9, [rbp+var_40]
0x18000f2d5  lea     r8, [rbp+OutputBuffer]
0x18000f2d9  mov     rcx, r15
0x18000f2dc  call    SclGetDiskLayout
0x18000f2e1  mov     rdi, qword ptr [rbp+OutputBuffer]
0x18000f2e5  mov     ebx, eax
0x18000f2e7  mov     r13d, [rbp+var_40]
0x18000f2eb  xor     r14d, r14d
0x18000f2ee  jmp     loc_18000F3A2
0x18000f2f3  cmp     r14d, [rdi+4]
0x18000f2f7  jnb     loc_18000F3B3
0x18000f2fd  lea     rsi, [r14+r14*8]
0x18000f301  xorps   xmm0, xmm0
0x18000f304  add     rsi, rsi
0x18000f307  cmp     dword ptr [rdi+rsi*8+30h], 1
0x18000f30c  jnz     loc_18000F39F
0x18000f312  mov     rcx, [rdi+rsi*8+60h]
0x18000f317  movq    rax, xmm0
0x18000f31c  sub     rcx, rax
0x18000f31f  jnz     short loc_18000F333
0x18000f321  mov     rcx, [rdi+rsi*8+68h]
0x18000f326  psrldq  xmm0, 8
0x18000f32b  movq    rax, xmm0
0x18000f330  sub     rcx, rax
0x18000f333  test    rcx, rcx
0x18000f336  jnz     short loc_18000F39F
0x18000f338  xorps   xmm0, xmm0
0x18000f33b  lea     edx, [rcx+10h]; OutputBufferLength
0x18000f33e  lea     rcx, [rbp+OutputBuffer]; OutputBuffer
0x18000f342  movups  [rbp+OutputBuffer], xmm0
0x18000f346  call    GenerateRandomData
0x18000f34b  test    eax, eax
0x18000f34d  jz      short loc_18000F3AC
0x18000f34f  movups  xmm0, [rbp+OutputBuffer]
0x18000f353  mov     rcx, [rbp+var_30]
0x18000f357  lea     r8, SclEvent_Generic_Info
0x18000f35e  xor     ebx, ebx
0x18000f360  mov     r9d, 10Eh
0x18000f366  movdqu  xmmword ptr [rdi+rsi*8+60h], xmm0
0x18000f36c  mov     eax, [rdi+rsi*8+48h]
0x18000f370  mov     [rsp+80h+var_50], eax
0x18000f374  lea     rax, aFoundAndUpdate; "Found and updated NULL GUID at partitio"...
0x18000f37b  mov     [rsp+80h+var_58], rax
0x18000f380  lea     edx, [rbx+1]
0x18000f383  lea     rax, aSclpgptinitzer; "SclpGptInitZeroedPartitionGuids"
0x18000f38a  mov     [rsp+80h+var_60], rax
0x18000f38f  call    SclLogGenericMessage
0x18000f394  inc     r14d
0x18000f397  mov     r12b, 1
0x18000f39a  jmp     loc_18000F2F3
0x18000f39f  inc     r14d
0x18000f3a2  test    ebx, ebx
0x18000f3a4  jns     loc_18000F2F3
0x18000f3aa  jmp     short loc_18000F3DD
0x18000f3ac  mov     ebx, 0C0000001h
0x18000f3b1  jmp     short loc_18000F3DD
0x18000f3b3  test    r12b, r12b
0x18000f3b6  jz      short loc_18000F3D6
0x18000f3b8  cmp     byte ptr [r15], 0
0x18000f3bc  jz      short loc_18000F3D6
0x18000f3be  mov     rdx, [rbp+Handle]
0x18000f3c2  mov     r9d, r13d
0x18000f3c5  mov     r8, rdi
0x18000f3c8  mov     rcx, r15
0x18000f3cb  call    SclpSetDiskLayout
0x18000f3d0  mov     ebx, eax
0x18000f3d2  test    eax, eax
0x18000f3d4  js      short loc_18000F3DD
0x18000f3d6  mov     rax, [rbp+var_28]
0x18000f3da  mov     [rax], r12b
0x18000f3dd  test    rdi, rdi
0x18000f3e0  jz      short loc_18000F3FA
0x18000f3e2  mov     rcx, gs:60h
0x18000f3eb  mov     r8, rdi; P
0x18000f3ee  xor     edx, edx; Flags
0x18000f3f0  mov     rcx, [rcx+30h]; HeapHandle
0x18000f3f4  call    cs:__imp_RtlFreeHeap
0x18000f3fa  mov     rcx, [rbp+Handle]; Handle
0x18000f3fe  test    rcx, rcx
0x18000f401  jz      short loc_18000F409
0x18000f403  call    cs:__imp_NtClose
0x18000f409  mov     eax, ebx
0x18000f40b  mov     rcx, [rbp+var_10]
0x18000f40f  xor     rcx, rsp; StackCookie
0x18000f412  call    __security_check_cookie
0x18000f417  mov     rbx, [rsp+80h+arg_18]
0x18000f41f  add     rsp, 80h
0x18000f426  pop     r15
0x18000f428  pop     r14
0x18000f42a  pop     r13
0x18000f42c  pop     r12
0x18000f42e  pop     rdi
0x18000f42f  pop     rsi
0x18000f430  pop     rbp
0x18000f431  retn
```
