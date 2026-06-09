# VhdmpiOpenRctFiles(VHD_SECURITY_CONTEXT *,_VHD_BACKING_STORE_HEADER *)

- ea: `0x14004c42c`
- end: `0x14004c7fd`
- name: `?VhdmpiOpenRctFiles@@YAJPEAUVHD_SECURITY_CONTEXT@@PEAU_VHD_BACKING_STORE_HEADER@@@Z`
- size: `977`
- prototype: `__int64 __fastcall(struct VHD_SECURITY_CONTEXT *, struct _VHD_BACKING_STORE_HEADER *)`
- caller_count: `1`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x14004d308`

## callees

- `0x14001ed2c`
- `0x140023560`
- `0x1400258f0`
- `0x140026194`
- `0x140035e94`
- `0x140040a30`
- `0x14004b930`
- `0x14004be04`
- `0x14004c0fc`
- `0x14004c42c`
- `0x14004db00`
- `0x1400560f4`
- `0x140058ae8`
- `0x14005a2f4`
- `0x1400e6e6c`
- `0x1400e8fd8`
- `0x1400ea754`
- `0x1400ebb80`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x14004c74c`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14004c75d`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14004c74c`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14004c75d`
- `ntoskrnl!ExAllocatePool2` at `0x14004c4ab`
- `ntoskrnl!ExAllocatePool2` at `0x14004c4ab`

## string_xrefs

- `0x14004c59f`: `VhdmpiOpenRctFiles`
- `0x14004c665`: `VhdmpiOpenRctFiles`
- `0x14004c591`: `VhdmpiOpenRctFiles: Unable to open RTC file, status = 0x%08x`
- `0x14004c657`: `VhdmpiOpenRctFiles: Unable to open MRT file, status = 0x%08x`

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
  unsigned int v21; // edx
  unsigned int *v23; // [rsp+20h] [rbp-98h]
  char *v24; // [rsp+48h] [rbp-70h]
  struct _UNICODE_STRING UnicodeString; // [rsp+50h] [rbp-68h] BYREF
  struct _UNICODE_STRING v26; // [rsp+60h] [rbp-58h] BYREF
  _OWORD v27[4]; // [rsp+70h] [rbp-48h] BYREF

  UnicodeString = 0;
  v4 = 0;
  v26 = 0;
  v5 = 0;
  v6 = 0;
  v27[0] = 0;
  v24 = (char *)a2 + 72;
  v7 = 0;
  RctFileNames = VhdmpiGetRctFileNames((PCUNICODE_STRING)((char *)a2 + 72), &UnicodeString, &v26);
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
      RctFileNames = VhdmpiBeginImpersonation(v12, (__int64)v27);
      if ( RctFileNames < 0 )
        goto LABEL_13;
    }
    v13 = VhdmpiInitializeRctFileWrapper(&UnicodeString, v11, a1, a2, v10);
    RctFileNames = v13;
    if ( v13 < 0 )
    {
      if ( v13 != -1073741772 && v13 != -1073741766 )
      {
        if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 0x20000) )
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
      v17 = VhdmpiInitializeRctFileWrapper(&v26, v16, a1, a2, v10 + 784);
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
                           v23,
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
        if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 0x20000) )
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
  RtlFreeUnicodeString(&v26);
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
    VhdmpiDeleteRctFiles(v24);
    VHD_RCT_STATE::`scalar deleting destructor'((VHD_RCT_STATE *)v10, v21);
  }
  VhdmpiEndImpersonation((__int64)v27);
  return (unsigned int)RctFileNames;
}

```

## disassembly

```asm
0x14004c42c  mov     rax, rsp
0x14004c42f  mov     [rax+8], rbx
0x14004c433  push    rbp
0x14004c434  push    rsi
0x14004c435  push    rdi
0x14004c436  push    r12
0x14004c438  push    r13
0x14004c43a  push    r14
0x14004c43c  push    r15
0x14004c43e  sub     rsp, 80h
0x14004c445  xorps   xmm0, xmm0
0x14004c448  lea     r8, [rsp+0B8h+var_58]; struct _UNICODE_STRING *
0x14004c44d  xorps   xmm1, xmm1
0x14004c450  mov     rbp, rdx
0x14004c453  movups  xmmword ptr [rax-68h], xmm0
0x14004c457  mov     rsi, rcx
0x14004c45a  xor     r15b, r15b
0x14004c45d  movups  xmmword ptr [rax-58h], xmm1
0x14004c461  xor     r14b, r14b
0x14004c464  xor     r13b, r13b
0x14004c467  movups  xmmword ptr [rax-48h], xmm0
0x14004c46b  lea     rax, [rdx+48h]
0x14004c46f  mov     [rsp+0B8h+var_78], r15b
0x14004c474  mov     rcx, rax; SourceString
0x14004c477  mov     [rsp+0B8h+arg_10], r14b
0x14004c47f  lea     rdx, [rsp+0B8h+UnicodeString]; struct _UNICODE_STRING *
0x14004c484  mov     [rsp+0B8h+var_70], rax
0x14004c489  xor     r12b, r12b
0x14004c48c  call    ?VhdmpiGetRctFileNames@@YAJPEBU_UNICODE_STRING@@PEAU1@1@Z; VhdmpiGetRctFileNames(_UNICODE_STRING const *,_UNICODE_STRING *,_UNICODE_STRING *)
0x14004c491  mov     edi, eax
0x14004c493  test    eax, eax
0x14004c495  js      loc_14004C742
0x14004c49b  mov     edx, 1500h
0x14004c4a0  mov     ecx, 40h ; '@'
0x14004c4a5  mov     r8d, 6C444856h
0x14004c4ab  call    cs:__imp_ExAllocatePool2
0x14004c4b2  nop     dword ptr [rax+rax+00h]
0x14004c4b7  mov     rbx, rax
0x14004c4ba  test    rax, rax
0x14004c4bd  jz      loc_14004C742
0x14004c4c3  xor     edi, edi
0x14004c4c5  lea     rcx, [rax+0A88h]; this
0x14004c4cc  mov     [rax+620h], rdi
0x14004c4d3  mov     [rax+628h], rdi
0x14004c4da  mov     [rax+9F8h], rdi
0x14004c4e1  mov     [rax+0A00h], rdi
0x14004c4e8  mov     [rax+0A08h], di
0x14004c4ef  mov     [rax+0A10h], rdi
0x14004c4f6  mov     [rax+0A18h], edi
0x14004c4fc  call    ??0SequenceTable@Rct@@QEAA@XZ; Rct::SequenceTable::SequenceTable(void)
0x14004c501  lea     rcx, [rbx+14B8h]
0x14004c508  mov     [rbx+14B0h], di
0x14004c50f  mov     [rbx+14B2h], dil
0x14004c516  call    AeInitializeAsyncLock
0x14004c51b  test    rsi, rsi
0x14004c51e  jz      short loc_14004C53C
0x14004c520  mov     rcx, [rsi]
0x14004c523  test    rcx, rcx
0x14004c526  jnz     short loc_14004C52C
0x14004c528  mov     rcx, [rsi+10h]; Token
0x14004c52c  lea     rdx, [rsp+0B8h+var_48]
0x14004c531  call    VhdmpiBeginImpersonation
0x14004c536  mov     edi, eax
0x14004c538  test    eax, eax
0x14004c53a  js      short loc_14004C5B1
0x14004c53c  mov     r9, rbp
0x14004c53f  mov     [rsp+0B8h+var_98], rbx
0x14004c544  mov     r8, rsi
0x14004c547  lea     rcx, [rsp+0B8h+UnicodeString]
0x14004c54c  call    ?VhdmpiInitializeRctFileWrapper@@YAJPEBU_UNICODE_STRING@@W4_VHD_FILE_WRAPPER_CACHE_MODE@@PEAUVHD_SECURITY_CONTEXT@@PEAU_VHD_BACKING_STORE_HEADER@@PEAU_VHD_FILE_WRAPPER@@@Z; VhdmpiInitializeRctFileWrapper(_UNICODE_STRING const *,_VHD_FILE_WRAPPER_CACHE_MODE,VHD_SECURITY_CONTEXT *,_VHD_BACKING_STORE_HEADER *,_VHD_FILE_WRAPPER *)
0x14004c551  mov     edi, eax
0x14004c553  test    eax, eax
0x14004c555  jns     short loc_14004C5C3
0x14004c557  cmp     eax, 0C0000034h
0x14004c55c  jz      short loc_14004C5B9
0x14004c55e  cmp     eax, 0C000003Ah
0x14004c563  jz      short loc_14004C5B9
0x14004c565  mov     eax, cs:dword_140087708
0x14004c56b  cmp     eax, 2
0x14004c56e  jbe     short loc_14004C5B1
0x14004c570  mov     edx, 20000h
0x14004c575  lea     rcx, dword_140087708
0x14004c57c  call    _tlgKeywordOn
0x14004c581  test    al, al
0x14004c583  jz      short loc_14004C5B1
0x14004c585  mov     ecx, 17Ch
0x14004c58a  mov     dword ptr [rsp+0B8h+var_90], edi; char
0x14004c58e  mov     r9d, edx; int
0x14004c591  lea     rax, aVhdmpiopenrctf_0; "VhdmpiOpenRctFiles: Unable to open RTC "...
0x14004c598  mov     edx, ecx; int
0x14004c59a  mov     [rsp+0B8h+var_98], rax; char *
0x14004c59f  lea     rcx, aVhdmpiopenrctf_1; "VhdmpiOpenRctFiles"
0x14004c5a6  mov     r8d, 2; int
0x14004c5ac  call    TraceEvents
0x14004c5b1  mov     sil, r12b
0x14004c5b4  jmp     loc_14004C747
0x14004c5b9  xor     edi, edi
0x14004c5bb  mov     sil, dil
0x14004c5be  jmp     loc_14004C747
0x14004c5c3  mov     r12b, 1
0x14004c5c6  cmp     [rbp+458h], r13b
0x14004c5cd  jz      short loc_14004C5D6
0x14004c5cf  mov     [rbx+14B1h], r12b
0x14004c5d6  lea     r14, [rbx+640h]
0x14004c5dd  xor     r9d, r9d
0x14004c5e0  mov     rcx, r14
0x14004c5e3  xor     r8d, r8d
0x14004c5e6  mov     rdx, rbx
0x14004c5e9  call    VhdmpiInitializeAeFile
0x14004c5ee  mov     edi, eax
0x14004c5f0  test    eax, eax
0x14004c5f2  js      loc_14004C73A
0x14004c5f8  lea     r15, [rbx+310h]
0x14004c5ff  mov     r9, rbp
0x14004c602  mov     r8, rsi
0x14004c605  mov     [rsp+0B8h+var_98], r15; unsigned int *
0x14004c60a  lea     rcx, [rsp+0B8h+var_58]
0x14004c60f  mov     r13b, r12b
0x14004c612  call    ?VhdmpiInitializeRctFileWrapper@@YAJPEBU_UNICODE_STRING@@W4_VHD_FILE_WRAPPER_CACHE_MODE@@PEAUVHD_SECURITY_CONTEXT@@PEAU_VHD_BACKING_STORE_HEADER@@PEAU_VHD_FILE_WRAPPER@@@Z; VhdmpiInitializeRctFileWrapper(_UNICODE_STRING const *,_VHD_FILE_WRAPPER_CACHE_MODE,VHD_SECURITY_CONTEXT *,_VHD_BACKING_STORE_HEADER *,_VHD_FILE_WRAPPER *)
0x14004c617  mov     edi, eax
0x14004c619  test    eax, eax
0x14004c61b  jns     short loc_14004C694
0x14004c61d  cmp     eax, 0C0000034h
0x14004c622  jz      short loc_14004C687
0x14004c624  cmp     eax, 0C000003Ah
0x14004c629  jz      short loc_14004C687
0x14004c62b  mov     eax, cs:dword_140087708
0x14004c631  cmp     eax, 2
0x14004c634  jbe     short loc_14004C677
0x14004c636  mov     edx, 20000h
0x14004c63b  lea     rcx, dword_140087708
0x14004c642  call    _tlgKeywordOn
0x14004c647  test    al, al
0x14004c649  jz      short loc_14004C677
0x14004c64b  mov     ecx, 1A5h
0x14004c650  mov     dword ptr [rsp+0B8h+var_90], edi; char
0x14004c654  mov     r9d, edx; int
0x14004c657  lea     rax, aVhdmpiopenrctf; "VhdmpiOpenRctFiles: Unable to open MRT "...
0x14004c65e  mov     edx, ecx; int
0x14004c660  mov     [rsp+0B8h+var_98], rax; char *
0x14004c665  lea     rcx, aVhdmpiopenrctf_1; "VhdmpiOpenRctFiles"
0x14004c66c  mov     r8d, 2; int
0x14004c672  call    TraceEvents
0x14004c677  mov     r15b, [rsp+0B8h+var_78]
0x14004c67c  mov     r14b, r15b
0x14004c67f  mov     sil, r15b
0x14004c682  jmp     loc_14004C747
0x14004c687  xor     edi, edi
0x14004c689  mov     r15b, dil
0x14004c68c  mov     r14b, dil
0x14004c68f  jmp     loc_14004C5BB
0x14004c694  lea     r13, [rbx+780h]
0x14004c69b  xor     r9d, r9d
0x14004c69e  mov     rcx, r13
0x14004c6a1  xor     r8d, r8d
0x14004c6a4  mov     rdx, r15
0x14004c6a7  mov     sil, r12b
0x14004c6aa  call    VhdmpiInitializeAeFile
0x14004c6af  mov     edi, eax
0x14004c6b1  test    eax, eax
0x14004c6b3  js      short loc_14004C72D
0x14004c6b5  lea     rsi, [rbx+8C0h]
0x14004c6bc  mov     r8d, 10h
0x14004c6c2  mov     rcx, rsi; SpinLock
0x14004c6c5  mov     rdx, r14
0x14004c6c8  mov     r15b, r12b
0x14004c6cb  call    AeInitializeEnvironment
0x14004c6d0  mov     edi, eax
0x14004c6d2  test    eax, eax
0x14004c6d4  js      short loc_14004C71D
0x14004c6d6  lea     rcx, [rbx+948h]
0x14004c6dd  mov     r8, r14
0x14004c6e0  mov     rdx, rsi
0x14004c6e3  call    AeInitializeFlushSequencer
0x14004c6e8  lea     rcx, [rbx+0A88h]; this
0x14004c6ef  mov     [rsp+0B8h+var_88], r13; struct AE_FILE *
0x14004c6f4  mov     rdx, rsi; struct AE_ENVIRON *
0x14004c6f7  mov     [rsp+0B8h+var_90], r14; struct AE_FILE *
0x14004c6fc  call    ?Initialize@SequenceTable@Rct@@QEAAJPEAUAE_ENVIRON@@PEAK11PEAUAE_FILE@@2@Z; Rct::SequenceTable::Initialize(AE_ENVIRON *,ulong *,ulong *,ulong *,AE_FILE *,AE_FILE *)
0x14004c701  mov     edi, eax
0x14004c703  mov     r14b, r12b
0x14004c706  mov     r13b, r12b
0x14004c709  mov     sil, r12b
0x14004c70c  test    eax, eax
0x14004c70e  js      short loc_14004C747
0x14004c710  mov     [rbp+718h], rbx
0x14004c717  xor     ebx, ebx
0x14004c719  xor     edi, edi
0x14004c71b  jmp     short loc_14004C747
0x14004c71d  mov     r14b, [rsp+0B8h+arg_10]
0x14004c725  mov     r13b, r12b
0x14004c728  jmp     loc_14004C5B1
0x14004c72d  mov     r15b, [rsp+0B8h+var_78]
0x14004c732  mov     r13b, r12b
0x14004c735  mov     r14b, r15b
0x14004c738  jmp     short loc_14004C747
0x14004c73a  mov     r14b, r13b
0x14004c73d  mov     sil, r13b
0x14004c740  jmp     short loc_14004C747
0x14004c742  xor     ebx, ebx
0x14004c744  mov     sil, bl
0x14004c747  lea     rcx, [rsp+0B8h+UnicodeString]; UnicodeString
0x14004c74c  call    cs:__imp_RtlFreeUnicodeString
0x14004c753  nop     dword ptr [rax+rax+00h]
0x14004c758  lea     rcx, [rsp+0B8h+var_58]; UnicodeString
0x14004c75d  call    cs:__imp_RtlFreeUnicodeString
0x14004c764  nop     dword ptr [rax+rax+00h]
0x14004c769  test    rbx, rbx
0x14004c76c  jz      short loc_14004C7D5
0x14004c76e  test    r14b, r14b
0x14004c771  jz      short loc_14004C77F
0x14004c773  lea     rcx, [rbx+8C0h]
0x14004c77a  call    AeCleanupEnvironment
0x14004c77f  test    r15b, r15b
0x14004c782  jz      short loc_14004C790
0x14004c784  lea     rcx, [rbx+780h]
0x14004c78b  call    VhdmpiUninitializeAeFile
0x14004c790  test    sil, sil
0x14004c793  jz      short loc_14004C7A3
0x14004c795  lea     rcx, [rbx+310h]; struct _VHD_FILE_WRAPPER *
0x14004c79c  xor     edx, edx
0x14004c79e  call    VhdmpiCleanupFileWrapper
0x14004c7a3  test    r13b, r13b
0x14004c7a6  jz      short loc_14004C7B4
0x14004c7a8  lea     rcx, [rbx+640h]
0x14004c7af  call    VhdmpiUninitializeAeFile
0x14004c7b4  test    r12b, r12b
0x14004c7b7  jz      short loc_14004C7C3
0x14004c7b9  xor     edx, edx
0x14004c7bb  mov     rcx, rbx; struct _VHD_FILE_WRAPPER *
0x14004c7be  call    VhdmpiCleanupFileWrapper
0x14004c7c3  mov     rcx, [rsp+0B8h+var_70]
0x14004c7c8  call    VhdmpiDeleteRctFiles
0x14004c7cd  mov     rcx, rbx; this
0x14004c7d0  call    ??_GVHD_RCT_STATE@@QEAAPEAXI@Z; VHD_RCT_STATE::`scalar deleting destructor'(uint)
0x14004c7d5  lea     rcx, [rsp+0B8h+var_48]
0x14004c7da  call    VhdmpiEndImpersonation
0x14004c7df  mov     rbx, [rsp+0B8h+arg_0]
0x14004c7e7  mov     eax, edi
0x14004c7e9  add     rsp, 80h
0x14004c7f0  pop     r15
0x14004c7f2  pop     r14
0x14004c7f4  pop     r13
0x14004c7f6  pop     r12
0x14004c7f8  pop     rdi
0x14004c7f9  pop     rsi
0x14004c7fa  pop     rbp
0x14004c7fb  retn
```
