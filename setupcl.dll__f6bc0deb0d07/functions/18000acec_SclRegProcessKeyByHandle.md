# SclRegProcessKeyByHandle

- ea: `0x18000acec`
- end: `0x18000b213`
- name: `SclRegProcessKeyByHandle`
- size: `1319`
- prototype: `__int64 __fastcall(__int64, void *, char, __int64)`
- caller_count: `4`
- callee_count: `14`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000ac28`
- `0x18000acec`
- `0x18000b21c`
- `0x1800111bc`

## callees

- `0x18000154c`
- `0x18000a524`
- `0x18000a75c`
- `0x18000aaac`
- `0x18000ab90`
- `0x18000acec`
- `0x18000b21c`
- `0x18000b530`
- `0x18000c70c`
- `0x18000d124`
- `0x1800121d4`
- `0x180012660`
- `0x180014fa0`
- `0x180018010`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18000af9f`
- `ntdll!RtlAllocateHeap` at `0x18000b102`
- `ntdll!RtlAllocateHeap` at `0x18000af9f`
- `ntdll!RtlAllocateHeap` at `0x18000b102`
- `ntdll!RtlInitUnicodeString` at `0x18000ae94`
- `ntdll!RtlInitUnicodeString` at `0x18000ae94`
- `ntdll!NtClose` at `0x18000aee7`
- `ntdll!NtClose` at `0x18000aee7`
- `ntdll!RtlFreeHeap` at `0x18000b17b`
- `ntdll!RtlFreeHeap` at `0x18000b1d1`
- `ntdll!RtlFreeHeap` at `0x18000b1f3`
- `ntdll!RtlFreeHeap` at `0x18000b17b`
- `ntdll!RtlFreeHeap` at `0x18000b1d1`
- `ntdll!RtlFreeHeap` at `0x18000b1f3`

## string_xrefs

- `0x18000adab`: `(%lx): Failed call to SclProcessObjectSecurity().`
- `0x18000afd2`: `(%lx): Failed to open child key: [%ws]`
- `0x18000b0ba`: `(%lx): Failed to get canonical path for a changed reg key`
- `0x18000b194`: `(%lx): Failed to process registry key!`

## pseudocode

```c
__int64 __fastcall SclRegProcessKeyByHandle(__int64 a1, void *a2, char a3, __int64 a4)
{
  __int64 v4; // r12
  void (__fastcall *v5)(__int64, _QWORD); // rax
  __int64 v6; // rsi
  char v10; // r15
  int v11; // ebx
  int v12; // eax
  __int64 v13; // rcx
  int v14; // eax
  PVOID v15; // rsi
  _QWORD *v16; // rsi
  const WCHAR *v17; // rdx
  _QWORD *v18; // rsi
  int v19; // eax
  PVOID Heap; // rax
  int v21; // r8d
  __int64 v22; // rcx
  int v23; // eax
  char *v24; // r15
  _QWORD *v25; // rsi
  __int64 v26; // rcx
  _QWORD *v27; // rax
  __int64 v28; // rdx
  char *v29; // rcx
  __int64 v31; // [rsp+30h] [rbp-40h]
  __int64 v32; // [rsp+40h] [rbp-30h] BYREF
  PVOID v33; // [rsp+48h] [rbp-28h] BYREF
  HANDLE Handle; // [rsp+50h] [rbp-20h] BYREF
  _QWORD *v35; // [rsp+58h] [rbp-18h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-10h] BYREF
  PVOID P; // [rsp+B0h] [rbp+40h] BYREF
  char v38; // [rsp+C0h] [rbp+50h]
  char v39; // [rsp+C8h] [rbp+58h] BYREF

  v38 = a3;
  LODWORD(v32) = 2064;
  v4 = a1 + 1152;
  v33 = 0;
  v5 = *(void (__fastcall **)(__int64, _QWORD))(a1 + 1152);
  v6 = a1 + 1192;
  LOBYTE(P) = 0;
  v10 = 0;
  if ( v5 )
    v5(a1 + 1192, *(_QWORD *)(a1 + 1160));
  if ( a4 )
  {
    if ( *(_BYTE *)a1 )
    {
      v10 = 0;
    }
    else
    {
      v10 = 1;
      if ( !*(_QWORD *)(a4 + 8) )
      {
        v11 = -1073741811;
LABEL_15:
        P = 0;
        v14 = CanonicalizeObjectPathByHandle(a2, &P);
        v15 = P;
        if ( v14 < 0 )
        {
          if ( !a1 )
            v4 = 0;
          SclLogGenericMessage(
            v4,
            3,
            (int)SclEvent_Generic_Error,
            560,
            (__int64)"SclRegProcessKeyByHandle",
            "(%lx): Failed to process registry key!",
            v11);
        }
        else
        {
          LODWORD(v31) = v11;
          if ( !a1 )
            v4 = 0;
          SclLogGenericMessage(
            v4,
            3,
            (int)SclEvent_Generic_Error,
            554,
            (__int64)"SclRegProcessKeyByHandle",
            "(%lx): Failed to process reg key or one of its descendants: [%ws]",
            v31,
            P);
        }
        if ( v15 )
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v15);
        goto LABEL_64;
      }
    }
  }
  v11 = 0;
  if ( v6 )
    ++*(_QWORD *)(a1 + 1192);
  if ( (*(_DWORD *)(a1 + 8) & 4) != 0 )
  {
    v12 = SclProcessObjectSecurity(a1, a2, &P);
    v11 = v12;
    if ( v12 < 0 )
    {
      v13 = a1 + 1152;
      if ( !a1 )
        v13 = 0;
      SclLogGenericMessage(
        v13,
        3,
        (int)SclEvent_Generic_Error,
        350,
        (__int64)"SclRegProcessKeyByHandle",
        "(%lx): Failed call to SclProcessObjectSecurity().",
        v12);
      goto LABEL_15;
    }
  }
  if ( !v10 )
  {
    if ( a4 )
    {
      v16 = *(_QWORD **)a4;
      v35 = 0;
      while ( 1 )
      {
        if ( !v16 )
        {
LABEL_29:
          if ( v11 >= 0 )
          {
            v18 = v35;
            v11 = 0;
            do
            {
              if ( !v18 )
                break;
              v19 = SclRegApplyRename((_BYTE *)a1, (__int64)a2, (__int64)v18);
              v18 = (_QWORD *)*v18;
              v11 = v19;
            }
            while ( v19 >= 0 );
          }
          goto LABEL_33;
        }
        v17 = (const WCHAR *)v16[1];
        Handle = 0;
        DestinationString = 0;
        v39 = 0;
        RtlInitUnicodeString(&DestinationString, v17);
        v11 = SclCreateKeyEx(a2, &DestinationString, 0x10F003Fu, 256, 0, &Handle);
        if ( v11 < 0 )
          break;
        v11 = SclRegProcessKeyByHandle(a1, Handle, 0, 0);
        NtClose(Handle);
        Handle = 0;
        if ( v11 >= 0 )
        {
          v11 = SclStringNeedsProcessing(
                  a1,
                  DestinationString.Buffer,
                  (unsigned __int64)DestinationString.Length >> 1,
                  &v39);
          if ( v11 >= 0 )
          {
            if ( v39 )
              v11 = SclpRegAddProcessItemToList(a1, &v35, DestinationString.Buffer, DestinationString.Length >> 1, 2);
          }
        }
        v16 = (_QWORD *)*v16;
        if ( v11 < 0 )
          goto LABEL_29;
      }
      v22 = a1 + 1152;
      if ( !a1 )
        v22 = 0;
      SclLogGenericMessage(
        v22,
        3,
        (int)SclEvent_Generic_Error,
        412,
        (__int64)"SclRegProcessKeyByHandle",
        "(%lx): Failed to open child key: [%ws]",
        v11,
        v16[1],
        v32);
LABEL_33:
      SclpFreeRenameList(&v35);
    }
    if ( v11 < 0 )
      goto LABEL_15;
  }
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x810u);
  v21 = 0;
  v33 = Heap;
  if ( !Heap )
  {
    v11 = -1073741801;
    goto LABEL_15;
  }
  LOBYTE(v21) = v38;
  v11 = SclRegProcessKeySubkeys(a1, (_DWORD)a2, v21, v38 != 0 ? a4 : 0, (__int64)&v33, (__int64)&v32, (__int64)&P);
  if ( v11 < 0 )
    goto LABEL_15;
  v11 = SclRegProcessKeyValues(a1, (_DWORD)a2, (unsigned int)&v33, (unsigned int)&v32, (__int64)&P);
  if ( v11 < 0 )
    goto LABEL_15;
  if ( v10 && (_BYTE)P && a4 )
  {
    P = 0;
    v23 = CanonicalizeObjectPathByHandle(a2, &P);
    v24 = (char *)P;
    v11 = v23;
    if ( v23 >= 0 )
    {
      v27 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x10u);
      v25 = v27;
      if ( v27 )
      {
        v28 = -1;
        v29 = &v24[2 * *(_QWORD *)(a4 + 8) + 2];
        do
          ++v28;
        while ( *(_WORD *)&v29[2 * v28] );
        v11 = SclCloneString(v29, v28, v27 + 1, 0);
        if ( v11 >= 0 )
        {
          *v25 = *(_QWORD *)a4;
          *(_QWORD *)a4 = v25;
          v25 = 0;
        }
      }
      else
      {
        v11 = -1073741801;
      }
    }
    else
    {
      LODWORD(v31) = v23;
      v25 = 0;
      v26 = v4;
      if ( !a1 )
        v26 = 0;
      SclLogGenericMessage(
        v26,
        3,
        (int)SclEvent_Generic_Error,
        488,
        (__int64)"SclRegProcessKeyByHandle",
        "(%lx): Failed to get canonical path for a changed reg key",
        v31);
    }
    SclFreeChangedKeyItem(v25);
    if ( v24 )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v24);
    if ( v11 < 0 )
      goto LABEL_15;
  }
LABEL_64:
  if ( v33 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v33);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18000acec  mov     [rsp-38h+arg_8], rbx
0x18000acf1  mov     [rsp-38h+arg_10], r8b
0x18000acf6  push    rbp
0x18000acf7  push    rsi
0x18000acf8  push    rdi
0x18000acf9  push    r12
0x18000acfb  push    r13
0x18000acfd  push    r14
0x18000acff  push    r15
0x18000ad01  mov     rbp, rsp
0x18000ad04  sub     rsp, 70h
0x18000ad08  xor     r8d, r8d
0x18000ad0b  mov     dword ptr [rbp+var_30], 810h
0x18000ad12  lea     r12, [rcx+480h]
0x18000ad19  mov     [rbp+var_28], r8
0x18000ad1d  mov     rax, [r12]
0x18000ad21  lea     rsi, [rcx+4A8h]
0x18000ad28  mov     byte ptr [rbp+P], r8b
0x18000ad2c  mov     r14, r9
0x18000ad2f  mov     r13, rdx
0x18000ad32  mov     rdi, rcx
0x18000ad35  mov     r15b, r8b
0x18000ad38  test    rax, rax
0x18000ad3b  jz      short loc_18000AD4F
0x18000ad3d  mov     rdx, [rcx+488h]
0x18000ad44  mov     rcx, rsi
0x18000ad47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad4c  xor     r8d, r8d
0x18000ad4f  test    r14, r14
0x18000ad52  jz      short loc_18000AD60
0x18000ad54  cmp     [rdi], r8b
0x18000ad57  jz      loc_18000ADE6
0x18000ad5d  mov     r15b, r8b
0x18000ad60  mov     ebx, r8d
0x18000ad63  test    rsi, rsi
0x18000ad66  jz      short loc_18000AD79
0x18000ad68  mov     rax, [rdi+4A8h]
0x18000ad6f  inc     rax
0x18000ad72  mov     [rdi+4A8h], rax
0x18000ad79  mov     eax, [rdi+8]
0x18000ad7c  test    al, 4
0x18000ad7e  jz      loc_18000AE5B
0x18000ad84  lea     r8, [rbp+P]
0x18000ad88  mov     rdx, r13
0x18000ad8b  mov     rcx, rdi
0x18000ad8e  call    SclProcessObjectSecurity
0x18000ad93  xor     r8d, r8d
0x18000ad96  mov     ebx, eax
0x18000ad98  test    eax, eax
0x18000ad9a  jns     loc_18000AE5B
0x18000ada0  mov     dword ptr [rsp+70h+var_40], eax
0x18000ada4  lea     rcx, [rdi+480h]
0x18000adab  lea     rax, aLxFailedCallTo; "(%lx): Failed call to SclProcessObjectS"...
0x18000adb2  test    rdi, rdi
0x18000adb5  mov     [rsp+70h+var_48], rax
0x18000adba  lea     r14, aSclregprocessk_2; "SclRegProcessKeyByHandle"
0x18000adc1  cmovz   rcx, r8
0x18000adc5  mov     [rsp+70h+var_50], r14
0x18000adca  lea     r8, SclEvent_Generic_Error
0x18000add1  mov     r9d, 15Eh
0x18000add7  mov     edx, 3
0x18000addc  call    SclLogGenericMessage
0x18000ade1  xor     r8d, r8d
0x18000ade4  jmp     short loc_18000ADFF
0x18000ade6  mov     r15b, 1
0x18000ade9  cmp     [r14+8], r8
0x18000aded  jnz     loc_18000AD60
0x18000adf3  mov     ebx, 0C000000Dh
0x18000adf8  lea     r14, aSclregprocessk_2; "SclRegProcessKeyByHandle"
0x18000adff  lea     rdx, [rbp+P]
0x18000ae03  mov     [rbp+P], r8
0x18000ae07  mov     rcx, r13; Handle
0x18000ae0a  call    CanonicalizeObjectPathByHandle
0x18000ae0f  mov     rsi, [rbp+P]
0x18000ae13  lea     r8, SclEvent_Generic_Error
0x18000ae1a  xor     ecx, ecx
0x18000ae1c  lea     edx, [rcx+3]
0x18000ae1f  test    eax, eax
0x18000ae21  js      loc_18000B18D
0x18000ae27  mov     [rsp+70h+var_38], rsi
0x18000ae2c  lea     rax, aLxFailedToProc_2; "(%lx): Failed to process reg key or one"...
0x18000ae33  test    rdi, rdi
0x18000ae36  mov     dword ptr [rsp+70h+var_40], ebx
0x18000ae3a  mov     [rsp+70h+var_48], rax
0x18000ae3f  mov     r9d, 22Ah
0x18000ae45  cmovz   r12, rcx
0x18000ae49  mov     [rsp+70h+var_50], r14
0x18000ae4e  mov     rcx, r12
0x18000ae51  call    SclLogGenericMessage
0x18000ae56  jmp     loc_18000B1B7
0x18000ae5b  test    r15b, r15b
0x18000ae5e  jnz     loc_18000AF8A
0x18000ae64  test    r14, r14
0x18000ae67  jz      loc_18000AF82
0x18000ae6d  mov     rsi, [r14]
0x18000ae70  mov     [rbp+var_18], r8
0x18000ae74  test    rsi, rsi
0x18000ae77  jz      loc_18000AF4F
0x18000ae7d  mov     rdx, [rsi+8]; SourceString
0x18000ae81  lea     rcx, [rbp+DestinationString]; DestinationString
0x18000ae85  xorps   xmm0, xmm0
0x18000ae88  mov     [rbp+Handle], r8
0x18000ae8c  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18000ae90  mov     [rbp+arg_18], r8b
0x18000ae94  call    cs:__imp_RtlInitUnicodeString
0x18000ae9a  xor     r8d, r8d
0x18000ae9d  lea     rax, [rbp+Handle]
0x18000aea1  mov     [rsp+70h+var_48], rax
0x18000aea6  lea     rdx, [rbp+DestinationString]
0x18000aeaa  mov     [rsp+70h+var_50], r8
0x18000aeaf  mov     r9d, 100h
0x18000aeb5  mov     r8d, 10F003Fh
0x18000aebb  mov     rcx, r13
0x18000aebe  call    SclCreateKeyEx
0x18000aec3  xor     edx, edx
0x18000aec5  mov     ebx, eax
0x18000aec7  test    eax, eax
0x18000aec9  js      loc_18000AFBB
0x18000aecf  mov     rdx, [rbp+Handle]
0x18000aed3  xor     r9d, r9d
0x18000aed6  xor     r8d, r8d
0x18000aed9  mov     rcx, rdi
0x18000aedc  call    SclRegProcessKeyByHandle
0x18000aee1  mov     rcx, [rbp+Handle]; Handle
0x18000aee5  mov     ebx, eax
0x18000aee7  call    cs:__imp_NtClose
0x18000aeed  xor     r8d, r8d
0x18000aef0  mov     [rbp+Handle], r8
0x18000aef4  test    ebx, ebx
0x18000aef6  js      short loc_18000AF44
0x18000aef8  movzx   r8d, [rbp+DestinationString.Length]
0x18000aefd  lea     r9, [rbp+arg_18]
0x18000af01  mov     rdx, [rbp+DestinationString.Buffer]
0x18000af05  mov     rcx, rdi
0x18000af08  shr     r8, 1
0x18000af0b  call    SclStringNeedsProcessing
0x18000af10  xor     r8d, r8d
0x18000af13  mov     ebx, eax
0x18000af15  test    eax, eax
0x18000af17  js      short loc_18000AF44
0x18000af19  cmp     [rbp+arg_18], r8b
0x18000af1d  jz      short loc_18000AF44
0x18000af1f  movzx   r9d, [rbp+DestinationString.Length]
0x18000af24  lea     rdx, [rbp+var_18]
0x18000af28  mov     r8, [rbp+DestinationString.Buffer]
0x18000af2c  mov     rcx, rdi
0x18000af2f  shr     r9d, 1
0x18000af32  mov     dword ptr [rsp+70h+var_50], 2
0x18000af3a  call    SclpRegAddProcessItemToList
0x18000af3f  mov     ebx, eax
0x18000af41  xor     r8d, r8d
0x18000af44  mov     rsi, [rsi]
0x18000af47  test    ebx, ebx
0x18000af49  jns     loc_18000AE74
0x18000af4f  test    ebx, ebx
0x18000af51  js      short loc_18000AF76
0x18000af53  mov     rsi, [rbp+var_18]
0x18000af57  mov     ebx, r8d
0x18000af5a  test    rsi, rsi
0x18000af5d  jz      short loc_18000AF76
0x18000af5f  mov     r8, rsi
0x18000af62  mov     rdx, r13
0x18000af65  mov     rcx, rdi
0x18000af68  call    SclRegApplyRename
0x18000af6d  mov     rsi, [rsi]
0x18000af70  mov     ebx, eax
0x18000af72  test    eax, eax
0x18000af74  jns     short loc_18000AF5A
0x18000af76  lea     rcx, [rbp+var_18]
0x18000af7a  call    SclpFreeRenameList
0x18000af7f  xor     r8d, r8d
0x18000af82  test    ebx, ebx
0x18000af84  js      loc_18000ADF8
0x18000af8a  mov     rcx, gs:60h
0x18000af93  xor     edx, edx; Flags
0x18000af95  mov     r8d, 810h; Size
0x18000af9b  mov     rcx, [rcx+30h]; HeapHandle
0x18000af9f  call    cs:__imp_RtlAllocateHeap
0x18000afa5  xor     r8d, r8d
0x18000afa8  mov     [rbp+var_28], rax
0x18000afac  test    rax, rax
0x18000afaf  jnz     short loc_18000B00A
0x18000afb1  mov     ebx, 0C0000017h
0x18000afb6  jmp     loc_18000ADF8
0x18000afbb  mov     rax, [rsi+8]
0x18000afbf  lea     rcx, [rdi+480h]
0x18000afc6  mov     [rsp+70h+var_38], rax
0x18000afcb  lea     r8, SclEvent_Generic_Error
0x18000afd2  lea     rax, aLxFailedToOpen_3; "(%lx): Failed to open child key: [%ws]"
0x18000afd9  mov     dword ptr [rsp+70h+var_40], ebx
0x18000afdd  mov     [rsp+70h+var_48], rax
0x18000afe2  test    rdi, rdi
0x18000afe5  lea     rax, aSclregprocessk_2; "SclRegProcessKeyByHandle"
0x18000afec  mov     r9d, 19Ch
0x18000aff2  cmovz   rcx, rdx
0x18000aff6  mov     [rsp+70h+var_50], rax
0x18000affb  mov     edx, 3
0x18000b000  call    SclLogGenericMessage
0x18000b005  jmp     loc_18000AF76
0x18000b00a  mov     r8b, [rbp+arg_10]
0x18000b00e  mov     rdx, r13
0x18000b011  mov     al, r8b
0x18000b014  mov     rcx, rdi
0x18000b017  neg     al
0x18000b019  lea     rax, [rbp+P]
0x18000b01d  mov     [rsp+70h+var_40], rax
0x18000b022  sbb     r9, r9
0x18000b025  lea     rax, [rbp+var_30]
0x18000b029  and     r9, r14
0x18000b02c  mov     [rsp+70h+var_48], rax
0x18000b031  lea     rax, [rbp+var_28]
0x18000b035  mov     [rsp+70h+var_50], rax
0x18000b03a  call    SclRegProcessKeySubkeys
0x18000b03f  xor     r8d, r8d
0x18000b042  mov     ebx, eax
0x18000b044  test    eax, eax
0x18000b046  js      loc_18000ADF8
0x18000b04c  lea     rax, [rbp+P]
0x18000b050  mov     rdx, r13
0x18000b053  lea     r9, [rbp+var_30]
0x18000b057  mov     [rsp+70h+var_50], rax
0x18000b05c  lea     r8, [rbp+var_28]
0x18000b060  mov     rcx, rdi
0x18000b063  call    SclRegProcessKeyValues
0x18000b068  xor     r8d, r8d
0x18000b06b  mov     ebx, eax
0x18000b06d  test    eax, eax
0x18000b06f  js      loc_18000ADF8
0x18000b075  test    r15b, r15b
0x18000b078  jz      loc_18000B1DA
0x18000b07e  cmp     byte ptr [rbp+P], r8b
0x18000b082  jz      loc_18000B1DA
0x18000b088  test    r14, r14
0x18000b08b  jz      loc_18000B1DA
0x18000b091  lea     rdx, [rbp+P]
0x18000b095  mov     [rbp+P], r8
0x18000b099  mov     rcx, r13; Handle
0x18000b09c  call    CanonicalizeObjectPathByHandle
0x18000b0a1  mov     r15, [rbp+P]
0x18000b0a5  xor     edx, edx
0x18000b0a7  mov     ebx, eax
0x18000b0a9  test    eax, eax
0x18000b0ab  jns     short loc_18000B0EC
0x18000b0ad  mov     dword ptr [rsp+70h+var_40], eax
0x18000b0b1  lea     r14, aSclregprocessk_2; "SclRegProcessKeyByHandle"
0x18000b0b8  mov     esi, edx
0x18000b0ba  lea     rax, aLxFailedToGetC; "(%lx): Failed to get canonical path for"...
0x18000b0c1  test    rdi, rdi
0x18000b0c4  mov     [rsp+70h+var_48], rax
0x18000b0c9  mov     rcx, r12
0x18000b0cc  mov     [rsp+70h+var_50], r14
0x18000b0d1  cmovz   rcx, rdx
0x18000b0d5  lea     r8, SclEvent_Generic_Error
0x18000b0dc  lea     edx, [rsi+3]
0x18000b0df  mov     r9d, 1E8h
0x18000b0e5  call    SclLogGenericMessage
0x18000b0ea  jmp     short loc_18000B159
0x18000b0ec  mov     rcx, gs:60h
0x18000b0f5  mov     edx, 8; Flags
0x18000b0fa  mov     rcx, [rcx+30h]; HeapHandle
0x18000b0fe  lea     r8d, [rdx+8]; Size
0x18000b102  call    cs:__imp_RtlAllocateHeap
0x18000b108  xor     r8d, r8d
0x18000b10b  mov     rsi, rax
0x18000b10e  test    rax, rax
0x18000b111  jnz     short loc_18000B11A
0x18000b113  mov     ebx, 0C0000017h
0x18000b118  jmp     short loc_18000B152
0x18000b11a  mov     rcx, [r14+8]
0x18000b11e  inc     rcx
0x18000b121  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000b125  lea     rcx, [r15+rcx*2]
0x18000b129  inc     rdx
0x18000b12c  cmp     [rcx+rdx*2], r8w
0x18000b131  jnz     short loc_18000B129
0x18000b133  lea     r8, [rax+8]
0x18000b137  xor     r9d, r9d
0x18000b13a  call    SclCloneString
0x18000b13f  xor     ecx, ecx
0x18000b141  mov     ebx, eax
0x18000b143  test    eax, eax
0x18000b145  js      short loc_18000B152
0x18000b147  mov     rax, [r14]
0x18000b14a  mov     [rsi], rax
0x18000b14d  mov     [r14], rsi
0x18000b150  mov     esi, ecx
0x18000b152  lea     r14, aSclregprocessk_2; "SclRegProcessKeyByHandle"
0x18000b159  mov     rcx, rsi; P
0x18000b15c  call    SclFreeChangedKeyItem
0x18000b161  xor     r8d, r8d
0x18000b164  test    r15, r15
0x18000b167  jz      short loc_18000B184
0x18000b169  mov     rcx, gs:60h
0x18000b172  mov     r8, r15; P
0x18000b175  xor     edx, edx; Flags
0x18000b177  mov     rcx, [rcx+30h]; HeapHandle
0x18000b17b  call    cs:__imp_RtlFreeHeap
0x18000b181  xor     r8d, r8d
0x18000b184  test    ebx, ebx
0x18000b186  jns     short loc_18000B1DA
  ... truncated ...
```
