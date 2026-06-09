# VhdmpiOpenRctFiles(VHD_SECURITY_CONTEXT *,_VHD_BACKING_STORE_HEADER *)

- ea: `0x14004c81c`
- end: `0x14004cbed`
- name: `?VhdmpiOpenRctFiles@@YAJPEAUVHD_SECURITY_CONTEXT@@PEAU_VHD_BACKING_STORE_HEADER@@@Z`
- size: `977`
- prototype: `__int64 __fastcall(struct VHD_SECURITY_CONTEXT *, struct _VHD_BACKING_STORE_HEADER *)`
- caller_count: `1`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x14004d6f8`

## callees

- `0x14001f14c`
- `0x140023980`
- `0x140025d10`
- `0x1400265b4`
- `0x140036284`
- `0x140040e20`
- `0x14004bd20`
- `0x14004c1f4`
- `0x14004c4ec`
- `0x14004c81c`
- `0x14004def0`
- `0x1400564e4`
- `0x140058ed8`
- `0x14005a6e4`
- `0x1400e6dfc`
- `0x1400e8f68`
- `0x1400ea6e4`
- `0x1400ebb10`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x14004cb3c`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14004cb4d`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14004cb3c`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14004cb4d`
- `ntoskrnl!ExAllocatePool2` at `0x14004c89b`
- `ntoskrnl!ExAllocatePool2` at `0x14004c89b`

## string_xrefs

- `0x14004c981`: `VhdmpiOpenRctFiles: Unable to open RTC file, status = 0x%08x`
- `0x14004ca47`: `VhdmpiOpenRctFiles: Unable to open MRT file, status = 0x%08x`
- `0x14004c98f`: `VhdmpiOpenRctFiles`
- `0x14004ca55`: `VhdmpiOpenRctFiles`

## pseudocode

```c
__int64 __fastcall VhdmpiOpenRctFiles(struct VHD_SECURITY_CONTEXT *a1, struct _VHD_BACKING_STORE_HEADER *a2)
{
  char v4; // r15
  char v5; // r14
  char v6; // r13
  char v7; // r12
  int RctFileNames; // edi
  __int64 Pool2; // rax
  __int64 v10; // rbx
  __int64 v11; // rdx
  void *v12; // rcx
  int v13; // eax
  unsigned int v14; // edx
  char v15; // si
  __int64 v16; // rdx
  int v17; // eax
  unsigned int v18; // edx
  unsigned int *v19; // r8
  unsigned int *v20; // r9
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // r9
  unsigned int v24; // edx
  unsigned int *v26; // [rsp+20h] [rbp-98h]
  char *v27; // [rsp+48h] [rbp-70h]
  struct _UNICODE_STRING UnicodeString; // [rsp+50h] [rbp-68h] BYREF
  struct _UNICODE_STRING v29; // [rsp+60h] [rbp-58h] BYREF
  _OWORD v30[4]; // [rsp+70h] [rbp-48h] BYREF

  UnicodeString = 0;
  v4 = 0;
  v29 = 0;
  v5 = 0;
  v6 = 0;
  v30[0] = 0;
  v27 = (char *)a2 + 72;
  v7 = 0;
  RctFileNames = VhdmpiGetRctFileNames((PCUNICODE_STRING)((char *)a2 + 72), &UnicodeString, &v29);
  if ( RctFileNames >= 0 && (Pool2 = ExAllocatePool2(64, 5376, 1816414294), (v10 = Pool2) != 0) )
  {
    *(_QWORD *)(Pool2 + 1568) = 0;
    *(_QWORD *)(Pool2 + 1576) = 0;
    *(_QWORD *)(Pool2 + 2552) = 0;
    *(_QWORD *)(Pool2 + 2560) = 0;
    *(_WORD *)(Pool2 + 2568) = 0;
    *(_QWORD *)(Pool2 + 2576) = 0;
    *(_DWORD *)(Pool2 + 2584) = 0;
    Rct::SequenceTable::SequenceTable((Rct::SequenceTable *)(Pool2 + 2696));
    *(_WORD *)(v10 + 5296) = 0;
    *(_BYTE *)(v10 + 5298) = 0;
    AeInitializeAsyncLock(v10 + 5304);
    if ( a1 )
    {
      v12 = *(void **)a1;
      if ( !*(_QWORD *)a1 )
        v12 = (void *)*((_QWORD *)a1 + 2);
      RctFileNames = VhdmpiBeginImpersonation(v12, (__int64)v30);
      if ( RctFileNames < 0 )
        goto LABEL_13;
    }
    v13 = VhdmpiInitializeRctFileWrapper(&UnicodeString, v11, a1, a2, v10);
    RctFileNames = v13;
    if ( v13 < 0 )
    {
      if ( v13 != -1073741772 && v13 != -1073741766 )
      {
        if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 0x20000) )
          TraceEvents(
            "VhdmpiOpenRctFiles",
            0x17Cu,
            2u,
            v14,
            "VhdmpiOpenRctFiles: Unable to open RTC file, status = 0x%08x",
            RctFileNames);
        goto LABEL_13;
      }
      RctFileNames = 0;
      goto LABEL_15;
    }
    v7 = 1;
    if ( *((_BYTE *)a2 + 1112) )
      *(_BYTE *)(v10 + 5297) = 1;
    RctFileNames = VhdmpiInitializeAeFile(v10 + 1600, v10, 0, 0);
    if ( RctFileNames < 0 )
    {
      v5 = 0;
      v15 = 0;
    }
    else
    {
      v6 = 1;
      v17 = VhdmpiInitializeRctFileWrapper(&v29, v16, a1, a2, v10 + 784);
      RctFileNames = v17;
      if ( v17 >= 0 )
      {
        v15 = 1;
        RctFileNames = VhdmpiInitializeAeFile(v10 + 1920, v10 + 784, 0, 0);
        if ( RctFileNames < 0 )
        {
          v4 = 0;
          v6 = 1;
          v5 = 0;
        }
        else
        {
          v4 = 1;
          RctFileNames = AeInitializeEnvironment((PKSPIN_LOCK)(v10 + 2240));
          if ( RctFileNames < 0 )
          {
            v5 = 0;
            v6 = 1;
LABEL_13:
            v15 = v7;
            goto LABEL_35;
          }
          AeInitializeFlushSequencer(v10 + 2376, v10 + 2240, v10 + 1600);
          RctFileNames = Rct::SequenceTable::Initialize(
                           (Rct::SequenceTable *)(v10 + 2696),
                           (struct AE_ENVIRON *)(v10 + 2240),
                           v19,
                           v20,
                           v26,
                           (struct AE_FILE *)(v10 + 1600),
                           (struct AE_FILE *)(v10 + 1920));
          v5 = 1;
          v6 = 1;
          v15 = 1;
          if ( RctFileNames >= 0 )
          {
            *((_QWORD *)a2 + 227) = v10;
            v10 = 0;
            RctFileNames = 0;
          }
        }
      }
      else
      {
        if ( v17 == -1073741772 || v17 == -1073741766 )
        {
          RctFileNames = 0;
          v4 = 0;
          v5 = 0;
LABEL_15:
          v15 = 0;
          goto LABEL_35;
        }
        if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 0x20000) )
          TraceEvents(
            "VhdmpiOpenRctFiles",
            0x1A5u,
            2u,
            v18,
            "VhdmpiOpenRctFiles: Unable to open MRT file, status = 0x%08x",
            RctFileNames);
        v4 = 0;
        v5 = 0;
        v15 = 0;
      }
    }
  }
  else
  {
    v10 = 0;
    v15 = 0;
  }
LABEL_35:
  RtlFreeUnicodeString(&UnicodeString);
  RtlFreeUnicodeString(&v29);
  if ( v10 )
  {
    if ( v5 )
      AeCleanupEnvironment(v10 + 2240);
    if ( v4 )
      VhdmpiUninitializeAeFile(v10 + 1920);
    if ( v15 )
      VhdmpiCleanupFileWrapper((struct _VHD_FILE_WRAPPER *)(v10 + 784));
    if ( v6 )
      VhdmpiUninitializeAeFile(v10 + 1600);
    if ( v7 )
      VhdmpiCleanupFileWrapper((struct _VHD_FILE_WRAPPER *)v10);
    VhdmpiDeleteRctFiles(v27, v21, v22, v23);
    VHD_RCT_STATE::`scalar deleting destructor'((VHD_RCT_STATE *)v10, v24);
  }
  VhdmpiEndImpersonation((__int64)v30);
  return (unsigned int)RctFileNames;
}

```

## disassembly

```asm
0x14004c81c  mov     rax, rsp
0x14004c81f  mov     [rax+8], rbx
0x14004c823  push    rbp
0x14004c824  push    rsi
0x14004c825  push    rdi
0x14004c826  push    r12
0x14004c828  push    r13
0x14004c82a  push    r14
0x14004c82c  push    r15
0x14004c82e  sub     rsp, 80h
0x14004c835  xorps   xmm0, xmm0
0x14004c838  lea     r8, [rsp+0B8h+var_58]; struct _UNICODE_STRING *
0x14004c83d  xorps   xmm1, xmm1
0x14004c840  mov     rbp, rdx
0x14004c843  movups  xmmword ptr [rax-68h], xmm0
0x14004c847  mov     rsi, rcx
0x14004c84a  xor     r15b, r15b
0x14004c84d  movups  xmmword ptr [rax-58h], xmm1
0x14004c851  xor     r14b, r14b
0x14004c854  xor     r13b, r13b
0x14004c857  movups  xmmword ptr [rax-48h], xmm0
0x14004c85b  lea     rax, [rdx+48h]
0x14004c85f  mov     [rsp+0B8h+var_78], r15b
0x14004c864  mov     rcx, rax; SourceString
0x14004c867  mov     [rsp+0B8h+arg_10], r14b
0x14004c86f  lea     rdx, [rsp+0B8h+UnicodeString]; struct _UNICODE_STRING *
0x14004c874  mov     [rsp+0B8h+var_70], rax
0x14004c879  xor     r12b, r12b
0x14004c87c  call    ?VhdmpiGetRctFileNames@@YAJPEBU_UNICODE_STRING@@PEAU1@1@Z; VhdmpiGetRctFileNames(_UNICODE_STRING const *,_UNICODE_STRING *,_UNICODE_STRING *)
0x14004c881  mov     edi, eax
0x14004c883  test    eax, eax
0x14004c885  js      loc_14004CB32
0x14004c88b  mov     edx, 1500h
0x14004c890  mov     ecx, 40h ; '@'
0x14004c895  mov     r8d, 6C444856h
0x14004c89b  call    cs:__imp_ExAllocatePool2
0x14004c8a2  nop     dword ptr [rax+rax+00h]
0x14004c8a7  mov     rbx, rax
0x14004c8aa  test    rax, rax
0x14004c8ad  jz      loc_14004CB32
0x14004c8b3  xor     edi, edi
0x14004c8b5  lea     rcx, [rax+0A88h]; this
0x14004c8bc  mov     [rax+620h], rdi
0x14004c8c3  mov     [rax+628h], rdi
0x14004c8ca  mov     [rax+9F8h], rdi
0x14004c8d1  mov     [rax+0A00h], rdi
0x14004c8d8  mov     [rax+0A08h], di
0x14004c8df  mov     [rax+0A10h], rdi
0x14004c8e6  mov     [rax+0A18h], edi
0x14004c8ec  call    ??0SequenceTable@Rct@@QEAA@XZ; Rct::SequenceTable::SequenceTable(void)
0x14004c8f1  lea     rcx, [rbx+14B8h]
0x14004c8f8  mov     [rbx+14B0h], di
0x14004c8ff  mov     [rbx+14B2h], dil
0x14004c906  call    AeInitializeAsyncLock
0x14004c90b  test    rsi, rsi
0x14004c90e  jz      short loc_14004C92C
0x14004c910  mov     rcx, [rsi]
0x14004c913  test    rcx, rcx
0x14004c916  jnz     short loc_14004C91C
0x14004c918  mov     rcx, [rsi+10h]; Token
0x14004c91c  lea     rdx, [rsp+0B8h+var_48]
0x14004c921  call    VhdmpiBeginImpersonation
0x14004c926  mov     edi, eax
0x14004c928  test    eax, eax
0x14004c92a  js      short loc_14004C9A1
0x14004c92c  mov     r9, rbp
0x14004c92f  mov     [rsp+0B8h+var_98], rbx
0x14004c934  mov     r8, rsi
0x14004c937  lea     rcx, [rsp+0B8h+UnicodeString]
0x14004c93c  call    ?VhdmpiInitializeRctFileWrapper@@YAJPEBU_UNICODE_STRING@@W4_VHD_FILE_WRAPPER_CACHE_MODE@@PEAUVHD_SECURITY_CONTEXT@@PEAU_VHD_BACKING_STORE_HEADER@@PEAU_VHD_FILE_WRAPPER@@@Z; VhdmpiInitializeRctFileWrapper(_UNICODE_STRING const *,_VHD_FILE_WRAPPER_CACHE_MODE,VHD_SECURITY_CONTEXT *,_VHD_BACKING_STORE_HEADER *,_VHD_FILE_WRAPPER *)
0x14004c941  mov     edi, eax
0x14004c943  test    eax, eax
0x14004c945  jns     short loc_14004C9B3
0x14004c947  cmp     eax, 0C0000034h
0x14004c94c  jz      short loc_14004C9A9
0x14004c94e  cmp     eax, 0C000003Ah
0x14004c953  jz      short loc_14004C9A9
0x14004c955  mov     eax, cs:dword_1400876D0
0x14004c95b  cmp     eax, 2
0x14004c95e  jbe     short loc_14004C9A1
0x14004c960  mov     edx, 20000h
0x14004c965  lea     rcx, dword_1400876D0
0x14004c96c  call    _tlgKeywordOn
0x14004c971  test    al, al
0x14004c973  jz      short loc_14004C9A1
0x14004c975  mov     ecx, 17Ch
0x14004c97a  mov     dword ptr [rsp+0B8h+var_90], edi; char
0x14004c97e  mov     r9d, edx; int
0x14004c981  lea     rax, aVhdmpiopenrctf_0; "VhdmpiOpenRctFiles: Unable to open RTC "...
0x14004c988  mov     edx, ecx; int
0x14004c98a  mov     [rsp+0B8h+var_98], rax; char *
0x14004c98f  lea     rcx, aVhdmpiopenrctf_1; "VhdmpiOpenRctFiles"
0x14004c996  mov     r8d, 2; int
0x14004c99c  call    TraceEvents
0x14004c9a1  mov     sil, r12b
0x14004c9a4  jmp     loc_14004CB37
0x14004c9a9  xor     edi, edi
0x14004c9ab  mov     sil, dil
0x14004c9ae  jmp     loc_14004CB37
0x14004c9b3  mov     r12b, 1
0x14004c9b6  cmp     [rbp+458h], r13b
0x14004c9bd  jz      short loc_14004C9C6
0x14004c9bf  mov     [rbx+14B1h], r12b
0x14004c9c6  lea     r14, [rbx+640h]
0x14004c9cd  xor     r9d, r9d
0x14004c9d0  mov     rcx, r14
0x14004c9d3  xor     r8d, r8d
0x14004c9d6  mov     rdx, rbx
0x14004c9d9  call    VhdmpiInitializeAeFile
0x14004c9de  mov     edi, eax
0x14004c9e0  test    eax, eax
0x14004c9e2  js      loc_14004CB2A
0x14004c9e8  lea     r15, [rbx+310h]
0x14004c9ef  mov     r9, rbp
0x14004c9f2  mov     r8, rsi
0x14004c9f5  mov     [rsp+0B8h+var_98], r15; unsigned int *
0x14004c9fa  lea     rcx, [rsp+0B8h+var_58]
0x14004c9ff  mov     r13b, r12b
0x14004ca02  call    ?VhdmpiInitializeRctFileWrapper@@YAJPEBU_UNICODE_STRING@@W4_VHD_FILE_WRAPPER_CACHE_MODE@@PEAUVHD_SECURITY_CONTEXT@@PEAU_VHD_BACKING_STORE_HEADER@@PEAU_VHD_FILE_WRAPPER@@@Z; VhdmpiInitializeRctFileWrapper(_UNICODE_STRING const *,_VHD_FILE_WRAPPER_CACHE_MODE,VHD_SECURITY_CONTEXT *,_VHD_BACKING_STORE_HEADER *,_VHD_FILE_WRAPPER *)
0x14004ca07  mov     edi, eax
0x14004ca09  test    eax, eax
0x14004ca0b  jns     short loc_14004CA84
0x14004ca0d  cmp     eax, 0C0000034h
0x14004ca12  jz      short loc_14004CA77
0x14004ca14  cmp     eax, 0C000003Ah
0x14004ca19  jz      short loc_14004CA77
0x14004ca1b  mov     eax, cs:dword_1400876D0
0x14004ca21  cmp     eax, 2
0x14004ca24  jbe     short loc_14004CA67
0x14004ca26  mov     edx, 20000h
0x14004ca2b  lea     rcx, dword_1400876D0
0x14004ca32  call    _tlgKeywordOn
0x14004ca37  test    al, al
0x14004ca39  jz      short loc_14004CA67
0x14004ca3b  mov     ecx, 1A5h
0x14004ca40  mov     dword ptr [rsp+0B8h+var_90], edi; char
0x14004ca44  mov     r9d, edx; int
0x14004ca47  lea     rax, aVhdmpiopenrctf; "VhdmpiOpenRctFiles: Unable to open MRT "...
0x14004ca4e  mov     edx, ecx; int
0x14004ca50  mov     [rsp+0B8h+var_98], rax; char *
0x14004ca55  lea     rcx, aVhdmpiopenrctf_1; "VhdmpiOpenRctFiles"
0x14004ca5c  mov     r8d, 2; int
0x14004ca62  call    TraceEvents
0x14004ca67  mov     r15b, [rsp+0B8h+var_78]
0x14004ca6c  mov     r14b, r15b
0x14004ca6f  mov     sil, r15b
0x14004ca72  jmp     loc_14004CB37
0x14004ca77  xor     edi, edi
0x14004ca79  mov     r15b, dil
0x14004ca7c  mov     r14b, dil
0x14004ca7f  jmp     loc_14004C9AB
0x14004ca84  lea     r13, [rbx+780h]
0x14004ca8b  xor     r9d, r9d
0x14004ca8e  mov     rcx, r13
0x14004ca91  xor     r8d, r8d
0x14004ca94  mov     rdx, r15
0x14004ca97  mov     sil, r12b
0x14004ca9a  call    VhdmpiInitializeAeFile
0x14004ca9f  mov     edi, eax
0x14004caa1  test    eax, eax
0x14004caa3  js      short loc_14004CB1D
0x14004caa5  lea     rsi, [rbx+8C0h]
0x14004caac  mov     r8d, 10h
0x14004cab2  mov     rcx, rsi; SpinLock
0x14004cab5  mov     rdx, r14
0x14004cab8  mov     r15b, r12b
0x14004cabb  call    AeInitializeEnvironment
0x14004cac0  mov     edi, eax
0x14004cac2  test    eax, eax
0x14004cac4  js      short loc_14004CB0D
0x14004cac6  lea     rcx, [rbx+948h]
0x14004cacd  mov     r8, r14
0x14004cad0  mov     rdx, rsi
0x14004cad3  call    AeInitializeFlushSequencer
0x14004cad8  lea     rcx, [rbx+0A88h]; this
0x14004cadf  mov     [rsp+0B8h+var_88], r13; struct AE_FILE *
0x14004cae4  mov     rdx, rsi; struct AE_ENVIRON *
0x14004cae7  mov     [rsp+0B8h+var_90], r14; struct AE_FILE *
0x14004caec  call    ?Initialize@SequenceTable@Rct@@QEAAJPEAUAE_ENVIRON@@PEAK11PEAUAE_FILE@@2@Z; Rct::SequenceTable::Initialize(AE_ENVIRON *,ulong *,ulong *,ulong *,AE_FILE *,AE_FILE *)
0x14004caf1  mov     edi, eax
0x14004caf3  mov     r14b, r12b
0x14004caf6  mov     r13b, r12b
0x14004caf9  mov     sil, r12b
0x14004cafc  test    eax, eax
0x14004cafe  js      short loc_14004CB37
0x14004cb00  mov     [rbp+718h], rbx
0x14004cb07  xor     ebx, ebx
0x14004cb09  xor     edi, edi
0x14004cb0b  jmp     short loc_14004CB37
0x14004cb0d  mov     r14b, [rsp+0B8h+arg_10]
0x14004cb15  mov     r13b, r12b
0x14004cb18  jmp     loc_14004C9A1
0x14004cb1d  mov     r15b, [rsp+0B8h+var_78]
0x14004cb22  mov     r13b, r12b
0x14004cb25  mov     r14b, r15b
0x14004cb28  jmp     short loc_14004CB37
0x14004cb2a  mov     r14b, r13b
0x14004cb2d  mov     sil, r13b
0x14004cb30  jmp     short loc_14004CB37
0x14004cb32  xor     ebx, ebx
0x14004cb34  mov     sil, bl
0x14004cb37  lea     rcx, [rsp+0B8h+UnicodeString]; UnicodeString
0x14004cb3c  call    cs:__imp_RtlFreeUnicodeString
0x14004cb43  nop     dword ptr [rax+rax+00h]
0x14004cb48  lea     rcx, [rsp+0B8h+var_58]; UnicodeString
0x14004cb4d  call    cs:__imp_RtlFreeUnicodeString
0x14004cb54  nop     dword ptr [rax+rax+00h]
0x14004cb59  test    rbx, rbx
0x14004cb5c  jz      short loc_14004CBC5
0x14004cb5e  test    r14b, r14b
0x14004cb61  jz      short loc_14004CB6F
0x14004cb63  lea     rcx, [rbx+8C0h]
0x14004cb6a  call    AeCleanupEnvironment
0x14004cb6f  test    r15b, r15b
0x14004cb72  jz      short loc_14004CB80
0x14004cb74  lea     rcx, [rbx+780h]
0x14004cb7b  call    VhdmpiUninitializeAeFile
0x14004cb80  test    sil, sil
0x14004cb83  jz      short loc_14004CB93
0x14004cb85  lea     rcx, [rbx+310h]; struct _VHD_FILE_WRAPPER *
0x14004cb8c  xor     edx, edx
0x14004cb8e  call    VhdmpiCleanupFileWrapper
0x14004cb93  test    r13b, r13b
0x14004cb96  jz      short loc_14004CBA4
0x14004cb98  lea     rcx, [rbx+640h]
0x14004cb9f  call    VhdmpiUninitializeAeFile
0x14004cba4  test    r12b, r12b
0x14004cba7  jz      short loc_14004CBB3
0x14004cba9  xor     edx, edx
0x14004cbab  mov     rcx, rbx; struct _VHD_FILE_WRAPPER *
0x14004cbae  call    VhdmpiCleanupFileWrapper
0x14004cbb3  mov     rcx, [rsp+0B8h+var_70]
0x14004cbb8  call    VhdmpiDeleteRctFiles
0x14004cbbd  mov     rcx, rbx; this
0x14004cbc0  call    ??_GVHD_RCT_STATE@@QEAAPEAXI@Z; VHD_RCT_STATE::`scalar deleting destructor'(uint)
0x14004cbc5  lea     rcx, [rsp+0B8h+var_48]
0x14004cbca  call    VhdmpiEndImpersonation
0x14004cbcf  mov     rbx, [rsp+0B8h+arg_0]
0x14004cbd7  mov     eax, edi
0x14004cbd9  add     rsp, 80h
0x14004cbe0  pop     r15
0x14004cbe2  pop     r14
0x14004cbe4  pop     r13
0x14004cbe6  pop     r12
0x14004cbe8  pop     rdi
0x14004cbe9  pop     rsi
0x14004cbea  pop     rbp
0x14004cbeb  retn
```
