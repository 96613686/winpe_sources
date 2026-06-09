# SclRegProcessKeySubkeys

- ea: `0x18000b21c`
- end: `0x18000b527`
- name: `SclRegProcessKeySubkeys`
- size: `779`
- prototype: `__int64 __fastcall(_BYTE *, void *, __int64, __int64, __int64 *, __int64, char *)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000acec`

## callees

- `0x18000154c`
- `0x1800025ec`
- `0x180007ebc`
- `0x1800091c0`
- `0x18000a524`
- `0x18000ab90`
- `0x18000acec`
- `0x18000b21c`
- `0x18000c70c`
- `0x18000d124`
- `0x180012660`

## import_xrefs

- `ntdll!NtClose` at `0x18000b419`
- `ntdll!NtClose` at `0x18000b419`

## string_xrefs

- `0x18000b4b5`: `(%lx): Failure during enumeration of subkeys.`
- `0x18000b3a7`: `SclCreateKey failed to open child key [%.*ws], returning STATUS_ACCESS_DENIED; will try with lowered access rights`
- `0x18000b469`: `(%lx): Failed to open child key: [%.*ws]`

## pseudocode

```c
__int64 __fastcall SclRegProcessKeySubkeys(
        _BYTE *a1,
        void *a2,
        __int64 a3,
        __int64 a4,
        __int64 *a5,
        __int64 a6,
        char *a7)
{
  __int64 v7; // r14
  char v8; // r13
  int v9; // r12d
  int v12; // eax
  int v13; // ebx
  __int64 v14; // rsi
  int v15; // r9d
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  _QWORD *v19; // rsi
  int v20; // eax
  __int64 v22; // [rsp+30h] [rbp-50h]
  _BYTE v23[8]; // [rsp+50h] [rbp-30h] BYREF
  HANDLE Handle; // [rsp+58h] [rbp-28h] BYREF
  _QWORD *v25; // [rsp+60h] [rbp-20h] BYREF
  struct _UNICODE_STRING v26; // [rsp+68h] [rbp-18h] BYREF
  char v27; // [rsp+D0h] [rbp+50h]

  v27 = a3;
  v7 = a6;
  v8 = 0;
  v9 = 0;
  v25 = 0;
  while ( 1 )
  {
    LODWORD(Handle) = 0;
    v23[0] = 0;
    v26 = 0;
    v12 = SclRegEnumerateKey((__int64)a2, v9, a3, (int)a5, v7, 0, (__int64)&Handle);
    v13 = v12;
    if ( v12 == -2147483622 )
      break;
    if ( v12 < 0 )
    {
      v18 = (__int64)(a1 + 1152);
      if ( !a1 )
        v18 = 0;
      SclLogGenericMessage(
        v18,
        3,
        (int)SclEvent_Generic_Error,
        643,
        (__int64)"SclRegProcessKeySubkeys",
        "(%lx): Failure during enumeration of subkeys.",
        v12);
      goto LABEL_34;
    }
    v14 = *a5;
    v13 = RtlUIntToUShort(*(unsigned int *)(*a5 + 12), &v26);
    if ( v13 >= 0 )
    {
      if ( v26.Length > (unsigned int)(v15 - 16) )
      {
        v13 = -2147483643;
        goto LABEL_34;
      }
      v26.MaximumLength = v26.Length;
      v26.Buffer = (PWSTR)(v14 + 16);
      v13 = SclStringNeedsProcessing(a1, v14 + 16, (unsigned __int64)*(unsigned int *)(v14 + 12) >> 1, v23);
      if ( v13 < 0 )
        goto LABEL_19;
      if ( v23[0] )
      {
        v13 = SclpRegAddProcessItemToList((__int64)a1, &v25, (_WORD *)(v14 + 16), *(_DWORD *)(v14 + 12) >> 1, 2);
        v8 = 1;
        if ( v13 < 0 )
          goto LABEL_19;
      }
      if ( !v27 )
        goto LABEL_19;
      Handle = 0;
      v13 = SclCreateKeyEx(a2, &v26, 0x10F003Fu, 256, 0, &Handle);
      if ( v13 == -1073741790 )
      {
        v16 = (__int64)(a1 + 1152);
        if ( !a1 )
          v16 = 0;
        SclLogGenericMessage(
          v16,
          2,
          (int)SclEvent_Generic_Warning,
          718,
          (__int64)"SclRegProcessKeySubkeys",
          "SclCreateKey failed to open child key [%.*ws], returning STATUS_ACCESS_DENIED; will try with lowered access rights",
          (unsigned __int64)*(unsigned int *)(v14 + 12) >> 1,
          v14 + 16);
        v13 = SclOpenKey(a2, &v26, 0x1020019u, 256, &Handle);
        if ( v13 < 0 )
          goto LABEL_19;
      }
      else if ( v13 < 0 )
      {
        v17 = (__int64)(a1 + 1152);
        LODWORD(v22) = v13;
        if ( !a1 )
          v17 = 0;
        SclLogGenericMessage(
          v17,
          3,
          (int)SclEvent_Generic_Error,
          743,
          (__int64)"SclRegProcessKeySubkeys",
          "(%lx): Failed to open child key: [%.*ws]",
          v22,
          (unsigned __int64)*(unsigned int *)(v14 + 12) >> 1,
          v14 + 16);
        goto LABEL_34;
      }
      if ( Handle && ((unsigned __int64)Handle & 0xFFFFFFFF80000000uLL) == 0 )
      {
        v13 = SclRegProcessKeyByHandle((__int64)a1, Handle, v27, a4);
        NtClose(Handle);
      }
LABEL_19:
      v7 = a6;
    }
    ++v9;
    if ( v13 < 0 )
      goto LABEL_34;
  }
  v19 = v25;
  v13 = 0;
  do
  {
    if ( !v19 )
      break;
    v20 = SclRegApplyRename(a1, (__int64)a2, (__int64)v19);
    v19 = (_QWORD *)*v19;
    v13 = v20;
  }
  while ( v20 >= 0 );
  if ( v13 >= 0 )
    *a7 = v8;
LABEL_34:
  SclpFreeRenameList(&v25);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18000b21c  mov     [rsp-38h+arg_0], rbx
0x18000b221  mov     [rsp-38h+arg_18], r9
0x18000b226  mov     [rsp-38h+arg_10], r8b
0x18000b22b  push    rbp
0x18000b22c  push    rsi
0x18000b22d  push    rdi
0x18000b22e  push    r12
0x18000b230  push    r13
0x18000b232  push    r14
0x18000b234  push    r15
0x18000b236  mov     rbp, rsp
0x18000b239  sub     rsp, 80h
0x18000b240  mov     r14, [rbp+arg_28]
0x18000b244  xor     r13b, r13b
0x18000b247  xor     r12d, r12d
0x18000b24a  mov     [rbp+var_20], 0
0x18000b252  mov     r15, rdx
0x18000b255  mov     rdi, rcx
0x18000b258  mov     rsi, [rbp+arg_20]
0x18000b25c  lea     rax, [rbp+Handle]
0x18000b260  mov     [rsp+80h+var_50], rax
0x18000b265  xorps   xmm0, xmm0
0x18000b268  mov     dword ptr [rsp+80h+var_58], 0
0x18000b270  mov     r9, rsi
0x18000b273  mov     edx, r12d
0x18000b276  mov     [rsp+80h+var_60], r14
0x18000b27b  mov     rcx, r15
0x18000b27e  mov     dword ptr [rbp+Handle], 0
0x18000b285  mov     [rbp+var_30], 0
0x18000b289  movups  xmmword ptr [rbp+var_18.Length], xmm0
0x18000b28d  call    SclRegEnumerateKey
0x18000b292  mov     ebx, eax
0x18000b294  cmp     eax, 8000001Ah
0x18000b299  jz      loc_18000B4D4
0x18000b29f  test    eax, eax
0x18000b2a1  js      loc_18000B48F
0x18000b2a7  mov     rsi, [rsi]
0x18000b2aa  lea     rdx, [rbp+var_18]
0x18000b2ae  mov     r9d, [r14]
0x18000b2b1  mov     ecx, [rsi+0Ch]
0x18000b2b4  call    RtlUIntToUShort
0x18000b2b9  mov     ebx, eax
0x18000b2bb  test    eax, eax
0x18000b2bd  js      loc_18000B423
0x18000b2c3  movzx   edx, [rbp+var_18.Length]
0x18000b2c7  lea     ecx, [r9-10h]
0x18000b2cb  cmp     edx, ecx
0x18000b2cd  ja      loc_18000B488
0x18000b2d3  mov     [rbp+var_18.MaximumLength], dx
0x18000b2d7  lea     r14, [rsi+10h]
0x18000b2db  mov     [rbp+var_18.Buffer], r14
0x18000b2df  lea     r9, [rbp+var_30]
0x18000b2e3  mov     r8d, [rsi+0Ch]
0x18000b2e7  mov     rdx, r14
0x18000b2ea  shr     r8, 1
0x18000b2ed  mov     rcx, rdi
0x18000b2f0  call    SclStringNeedsProcessing
0x18000b2f5  mov     ebx, eax
0x18000b2f7  test    eax, eax
0x18000b2f9  js      loc_18000B41F
0x18000b2ff  cmp     [rbp+var_30], 0
0x18000b303  jz      short loc_18000B330
0x18000b305  mov     r9d, [rsi+0Ch]
0x18000b309  lea     rdx, [rbp+var_20]
0x18000b30d  shr     r9d, 1
0x18000b310  mov     r8, r14
0x18000b313  mov     rcx, rdi
0x18000b316  mov     dword ptr [rsp+80h+var_60], 2
0x18000b31e  call    SclpRegAddProcessItemToList
0x18000b323  mov     ebx, eax
0x18000b325  mov     r13b, 1
0x18000b328  test    eax, eax
0x18000b32a  js      loc_18000B41F
0x18000b330  cmp     [rbp+arg_10], 0
0x18000b334  jz      loc_18000B41F
0x18000b33a  lea     rax, [rbp+Handle]
0x18000b33e  mov     [rbp+Handle], 0
0x18000b346  mov     [rsp+80h+var_58], rax
0x18000b34b  lea     rdx, [rbp+var_18]
0x18000b34f  mov     r9d, 100h
0x18000b355  mov     [rsp+80h+var_60], 0
0x18000b35e  mov     r8d, 10F003Fh
0x18000b364  mov     rcx, r15
0x18000b367  call    SclCreateKeyEx
0x18000b36c  mov     ebx, eax
0x18000b36e  cmp     eax, 0C0000022h
0x18000b373  jnz     short loc_18000B3ED
0x18000b375  mov     edx, [rsi+0Ch]
0x18000b378  lea     rcx, [rdi+480h]
0x18000b37f  xor     eax, eax
0x18000b381  shr     rdx, 1
0x18000b384  mov     [rsp+80h+var_48], r14
0x18000b389  lea     r8, SclEvent_Generic_Warning
0x18000b390  mov     [rsp+80h+var_50], rdx
0x18000b395  test    rdi, rdi
0x18000b398  mov     r9d, 2CEh
0x18000b39e  mov     edx, 2
0x18000b3a3  cmovz   rcx, rax
0x18000b3a7  lea     rax, aSclcreatekeyFa; "SclCreateKey failed to open child key ["...
0x18000b3ae  mov     [rsp+80h+var_58], rax
0x18000b3b3  lea     rax, aSclregprocessk_1; "SclRegProcessKeySubkeys"
0x18000b3ba  mov     [rsp+80h+var_60], rax
0x18000b3bf  call    SclLogGenericMessage
0x18000b3c4  lea     rax, [rbp+Handle]
0x18000b3c8  mov     r9d, 100h
0x18000b3ce  mov     r8d, 1020019h
0x18000b3d4  mov     [rsp+80h+var_60], rax
0x18000b3d9  lea     rdx, [rbp+var_18]
0x18000b3dd  mov     rcx, r15
0x18000b3e0  call    SclOpenKey
0x18000b3e5  mov     ebx, eax
0x18000b3e7  test    eax, eax
0x18000b3e9  jns     short loc_18000B3F1
0x18000b3eb  jmp     short loc_18000B41F
0x18000b3ed  test    ebx, ebx
0x18000b3ef  js      short loc_18000B433
0x18000b3f1  mov     rdx, [rbp+Handle]
0x18000b3f5  test    rdx, rdx
0x18000b3f8  jz      short loc_18000B41F
0x18000b3fa  test    rdx, 0FFFFFFFF80000000h
0x18000b401  jnz     short loc_18000B41F
0x18000b403  mov     r9, [rbp+arg_18]
0x18000b407  mov     rcx, rdi
0x18000b40a  mov     r8b, [rbp+arg_10]
0x18000b40e  call    SclRegProcessKeyByHandle
0x18000b413  mov     rcx, [rbp+Handle]; Handle
0x18000b417  mov     ebx, eax
0x18000b419  call    cs:__imp_NtClose
0x18000b41f  mov     r14, [rbp+arg_28]
0x18000b423  inc     r12d
0x18000b426  test    ebx, ebx
0x18000b428  jns     loc_18000B258
0x18000b42e  jmp     loc_18000B501
0x18000b433  mov     edx, [rsi+0Ch]
0x18000b436  lea     rcx, [rdi+480h]
0x18000b43d  xor     eax, eax
0x18000b43f  shr     rdx, 1
0x18000b442  mov     [rsp+80h+var_40], r14
0x18000b447  lea     r8, SclEvent_Generic_Error
0x18000b44e  mov     [rsp+80h+var_48], rdx
0x18000b453  test    rdi, rdi
0x18000b456  mov     dword ptr [rsp+80h+var_50], ebx
0x18000b45a  mov     r9d, 2E7h
0x18000b460  cmovz   rcx, rax
0x18000b464  mov     edx, 3
0x18000b469  lea     rax, aLxFailedToOpen_5; "(%lx): Failed to open child key: [%.*ws"...
0x18000b470  mov     [rsp+80h+var_58], rax
0x18000b475  lea     rax, aSclregprocessk_1; "SclRegProcessKeySubkeys"
0x18000b47c  mov     [rsp+80h+var_60], rax
0x18000b481  call    SclLogGenericMessage
0x18000b486  jmp     short loc_18000B501
0x18000b488  mov     ebx, 80000005h
0x18000b48d  jmp     short loc_18000B501
0x18000b48f  xor     eax, eax
0x18000b491  mov     dword ptr [rsp+80h+var_50], ebx
0x18000b495  test    rdi, rdi
0x18000b498  lea     rcx, [rdi+480h]
0x18000b49f  mov     r9d, 283h
0x18000b4a5  lea     r8, SclEvent_Generic_Error
0x18000b4ac  cmovz   rcx, rax
0x18000b4b0  mov     edx, 3
0x18000b4b5  lea     rax, aLxFailureDurin; "(%lx): Failure during enumeration of su"...
0x18000b4bc  mov     [rsp+80h+var_58], rax
0x18000b4c1  lea     rax, aSclregprocessk_1; "SclRegProcessKeySubkeys"
0x18000b4c8  mov     [rsp+80h+var_60], rax
0x18000b4cd  call    SclLogGenericMessage
0x18000b4d2  jmp     short loc_18000B501
0x18000b4d4  mov     rsi, [rbp+var_20]
0x18000b4d8  xor     ebx, ebx
0x18000b4da  test    rsi, rsi
0x18000b4dd  jz      short loc_18000B4F6
0x18000b4df  mov     r8, rsi
0x18000b4e2  mov     rdx, r15
0x18000b4e5  mov     rcx, rdi
0x18000b4e8  call    SclRegApplyRename
0x18000b4ed  mov     rsi, [rsi]
0x18000b4f0  mov     ebx, eax
0x18000b4f2  test    eax, eax
0x18000b4f4  jns     short loc_18000B4DA
0x18000b4f6  test    ebx, ebx
0x18000b4f8  js      short loc_18000B501
0x18000b4fa  mov     rax, [rbp+arg_30]
0x18000b4fe  mov     [rax], r13b
0x18000b501  lea     rcx, [rbp+var_20]
0x18000b505  call    SclpFreeRenameList
0x18000b50a  mov     eax, ebx
0x18000b50c  mov     rbx, [rsp+80h+arg_0]
0x18000b514  add     rsp, 80h
0x18000b51b  pop     r15
0x18000b51d  pop     r14
0x18000b51f  pop     r13
0x18000b521  pop     r12
0x18000b523  pop     rdi
0x18000b524  pop     rsi
0x18000b525  pop     rbp
0x18000b526  retn
```
