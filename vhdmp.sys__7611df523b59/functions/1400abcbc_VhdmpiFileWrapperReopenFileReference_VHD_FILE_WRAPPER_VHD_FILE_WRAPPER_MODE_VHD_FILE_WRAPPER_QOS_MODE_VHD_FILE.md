# VhdmpiFileWrapperReopenFileReference(_VHD_FILE_WRAPPER *,_VHD_FILE_WRAPPER_MODE,_VHD_FILE_WRAPPER_QOS_MODE,_VHD_FILE_WRAPPER_FILE_REF_TYPE)

- ea: `0x1400abcbc`
- end: `0x1400ac2a4`
- name: `?VhdmpiFileWrapperReopenFileReference@@YAJPEAU_VHD_FILE_WRAPPER@@W4_VHD_FILE_WRAPPER_MODE@@W4_VHD_FILE_WRAPPER_QOS_MODE@@W4_VHD_FILE_WRAPPER_FILE_REF_TYPE@@@Z`
- size: `1512`
- prototype: `__int64 __fastcall(__int64, int, __int64, __int64)`
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x1400ae104`

## callees

- `0x140015a98`
- `0x14002118c`
- `0x140023560`
- `0x140023a1c`
- `0x14002debc`
- `0x14002e0cc`
- `0x14002e210`
- `0x140035e94`
- `0x1400abcbc`
- `0x1400ac4f8`
- `0x1400d0ff4`
- `0x1400e6e6c`
- `0x1400e8fd8`

## import_xrefs

- `ntoskrnl!IoGetRelatedDeviceObject` at `0x1400abe93`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x1400abe93`
- `ntoskrnl!ObfReferenceObject` at `0x1400ac09a`
- `ntoskrnl!ObfReferenceObject` at `0x1400ac09a`
- `ntoskrnl!ObfDereferenceObject` at `0x1400ac084`
- `ntoskrnl!ObfDereferenceObject` at `0x1400ac0e1`
- `ntoskrnl!ObfDereferenceObject` at `0x1400ac084`
- `ntoskrnl!ObfDereferenceObject` at `0x1400ac0e1`
- `ntoskrnl!ZwClose` at `0x1400ac0cd`
- `ntoskrnl!ZwClose` at `0x1400ac0cd`

## string_xrefs

- `0x1400abd9a`: `VhdmpiFileWrapperReopenFileReference`
- `0x1400abe55`: `VhdmpiFileWrapperReopenFileReference`
- `0x1400abf05`: `VhdmpiFileWrapperReopenFileReference`
- `0x1400abfee`: `VhdmpiFileWrapperReopenFileReference`
- `0x1400ac1cc`: `VhdmpiFileWrapperReopenFileReference`

## pseudocode

```c
__int64 __fastcall VhdmpiFileWrapperReopenFileReference(__int64 a1, int a2, __int64 a3, __int64 a4)
{
  int v5; // r14d
  __int64 v7; // rax
  int v8; // r8d
  int v9; // r9d
  struct _VHD_SAFE_FILE_REFERENCE *v10; // rsi
  int VolumeStableGuid; // ebx
  void *v12; // rcx
  char v13; // r15
  __int64 v14; // r9
  int v15; // edx
  __int64 v16; // r8
  ACCESS_MASK v17; // edx
  __int64 v18; // r8
  __int64 v19; // r9
  int v20; // edx
  char IsRecoverable; // al
  struct _FILE_OBJECT *v22; // rdi
  PDEVICE_OBJECT RelatedDeviceObject; // r15
  int v24; // edx
  int v25; // ecx
  int v26; // edx
  int v27; // edx
  int v28; // edx
  __int128 v30; // [rsp+E0h] [rbp-80h] BYREF
  PFILE_OBJECT FileObject; // [rsp+F0h] [rbp-70h] BYREF
  HANDLE Handle; // [rsp+F8h] [rbp-68h] BYREF
  __int64 v33; // [rsp+100h] [rbp-60h] BYREF
  int v34; // [rsp+108h] [rbp-58h]
  int v35; // [rsp+10Ch] [rbp-54h]
  int v36; // [rsp+110h] [rbp-50h]
  int v37; // [rsp+114h] [rbp-4Ch]
  int v38; // [rsp+118h] [rbp-48h]
  _OWORD v39[4]; // [rsp+120h] [rbp-40h] BYREF
  int v41; // [rsp+188h] [rbp+28h] BYREF

  v5 = a4;
  v7 = VhdmpiSafeFileReferenceFromType(a1, (unsigned int)a4, a3, a4);
  FileObject = 0;
  v10 = (struct _VHD_SAFE_FILE_REFERENCE *)v7;
  Handle = 0;
  v33 = 0;
  LOBYTE(v41) = 0;
  v39[0] = 0;
  v30 = 0;
  if ( v9 )
  {
    if ( *(_QWORD *)(v7 + 8) || *(_QWORD *)v7 )
      __fastfail(5u);
    if ( v9 == 2 && !v8 )
      return 0;
  }
  v12 = *(void **)(v7 + 56);
  v13 = *(_BYTE *)(v7 + 88);
  if ( !v12 )
    v12 = *(void **)(v7 + 72);
  VolumeStableGuid = VhdmpiBeginImpersonation(v12);
  if ( VolumeStableGuid < 0 )
  {
    if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 0x80000) )
      TraceEvents(
        (int)"VhdmpiFileWrapperReopenFileReference",
        9541,
        2,
        v15,
        "Cleanup with status 0x%08X",
        VolumeStableGuid);
    return (unsigned int)VolumeStableGuid;
  }
  v16 = 1;
  if ( v5 == 1 )
  {
    v17 = -1073741824;
    if ( a2 != 3 )
      v17 = 0x80000000;
  }
  else
  {
    v17 = 0x80000000;
  }
  LOBYTE(v14) = v13;
  if ( v5 != 1 )
    v16 = 3;
  VolumeStableGuid = VhdmpiOpenBackingFile(
                       (struct _VHD_FILE_WRAPPER *)a1,
                       v17,
                       v16,
                       v14,
                       v5 != 0,
                       &Handle,
                       &FileObject,
                       (unsigned __int8 *)&v41);
  VhdmpiEndImpersonation(v39);
  if ( VolumeStableGuid < 0 )
  {
    if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 0x80000) )
      TraceEvents(
        (int)"VhdmpiFileWrapperReopenFileReference",
        9568,
        2,
        v20,
        "Log status 0x%08X: File = %wZ",
        VolumeStableGuid);
    IsRecoverable = VhdmpiFileWrapperIoErrorIsRecoverable(a1, (unsigned int)VolumeStableGuid, v18, v19);
    v22 = FileObject;
    if ( !IsRecoverable )
      VolumeStableGuid = -1073741202;
    goto LABEL_49;
  }
  v22 = FileObject;
  RelatedDeviceObject = IoGetRelatedDeviceObject(FileObject);
  if ( v5 )
    goto LABEL_48;
  VolumeStableGuid = VhdmpiGetVolumeStableGuid(v22, &v30);
  if ( VolumeStableGuid < 0 )
  {
    if ( (unsigned int)dword_140087708 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140087708, 0x80000) )
      goto LABEL_49;
    v25 = 9587;
    goto LABEL_32;
  }
  if ( v30 != *(_OWORD *)(a1 + 504) )
  {
    VolumeStableGuid = -1073741823;
    LODWORD(v33) = -1073741823;
    if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 0x80000) )
    {
      v41 = *(unsigned __int8 *)(a1 + 515);
      v34 = *(unsigned __int8 *)(a1 + 514);
      v35 = *(unsigned __int8 *)(a1 + 513);
      v36 = *(unsigned __int8 *)(a1 + 512);
      v37 = *(unsigned __int16 *)(a1 + 510);
      v38 = *(unsigned __int16 *)(a1 + 508);
      TraceEvents(
        (int)"VhdmpiFileWrapperReopenFileReference",
        9594,
        2,
        0x80000,
        "Cleanup [status = ((NTSTATUS)0xC0000001L)]: Volume ID mismatch: expected = {%08X-%04x-%04x-%02x%02x-%02x%02x%02x"
        "%02x%02x%02x}, actual = {%08X-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x} (File = %wZ)",
        *(_DWORD *)(a1 + 504));
      VolumeStableGuid = v33;
      v22 = FileObject;
    }
    goto LABEL_49;
  }
  VolumeStableGuid = VhdmpiGetFileId(Handle, &v33);
  if ( VolumeStableGuid >= 0 )
  {
    if ( v33 != *(_QWORD *)(a1 + 496) )
    {
      VolumeStableGuid = -1073741823;
      if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 0x80000) )
        TraceEvents(
          (int)"VhdmpiFileWrapperReopenFileReference",
          9605,
          2,
          v27,
          "Cleanup [status = ((NTSTATUS)0xC0000001L)]: File ID mismatch: expected = %I64u, actual = %I64u (File = %wZ)",
          *(_QWORD *)(a1 + 496));
      goto LABEL_49;
    }
    if ( *(char *)(a1 + 544) < RelatedDeviceObject->StackSize + 3 )
    {
      VolumeStableGuid = -1073741823;
      if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 0x80000) )
        TraceEvents(
          (int)"VhdmpiFileWrapperReopenFileReference",
          9614,
          2,
          v28,
          "Cleanup [status = ((NTSTATUS)0xC0000001L)]: Stack size mismatch: expected = %u, actual = %u (File = %wZ)",
          *(_BYTE *)(a1 + 544) - 3);
      goto LABEL_49;
    }
    VhdmpiCleanupSafeFileReference(v10, v26);
    ObfDereferenceObject(*(PVOID *)(a1 + 536));
    *(_QWORD *)(a1 + 536) = RelatedDeviceObject;
    ObfReferenceObject(RelatedDeviceObject);
LABEL_48:
    VhdmpiSetSafeFileReference(v10, Handle, v22);
    VhdmpiResumeSafeFileReference(v10);
    Handle = 0;
    v22 = 0;
    goto LABEL_49;
  }
  if ( (unsigned int)dword_140087708 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140087708, 0x80000) )
    goto LABEL_49;
  v25 = 9598;
LABEL_32:
  TraceEvents(
    (int)"VhdmpiFileWrapperReopenFileReference",
    v25,
    2,
    v24,
    "Cleanup with status 0x%08X: File = %wZ",
    VolumeStableGuid);
LABEL_49:
  if ( Handle )
    ZwClose(Handle);
  if ( v22 )
    ObfDereferenceObject(v22);
  return (unsigned int)VolumeStableGuid;
}

```

## disassembly

```asm
0x1400abcbc  mov     [rsp-8+arg_8], rbx
0x1400abcc1  mov     [rsp-8+arg_0], rcx
0x1400abcc6  push    rbp
0x1400abcc7  push    rsi
0x1400abcc8  push    rdi
0x1400abcc9  push    r12
0x1400abccb  push    r13
0x1400abccd  push    r14
0x1400abccf  push    r15
0x1400abcd1  lea     rbp, [rsp+30h]
0x1400abcd6  sub     rsp, 130h
0x1400abcdd  mov     edi, edx
0x1400abcdf  mov     r14d, r9d
0x1400abce2  mov     edx, r9d
0x1400abce5  mov     r13, rcx
0x1400abce8  call    ?VhdmpiSafeFileReferenceFromType@@YAPEAU_VHD_SAFE_FILE_REFERENCE@@PEAU_VHD_FILE_WRAPPER@@W4_VHD_FILE_WRAPPER_FILE_REF_TYPE@@@Z; VhdmpiSafeFileReferenceFromType(_VHD_FILE_WRAPPER *,_VHD_FILE_WRAPPER_FILE_REF_TYPE)
0x1400abced  xor     r12d, r12d
0x1400abcf0  xorps   xmm0, xmm0
0x1400abcf3  mov     [rbp+FileObject], r12
0x1400abcf7  mov     rsi, rax
0x1400abcfa  mov     [rbp+Handle], r12
0x1400abcfe  mov     [rbp+var_60], r12
0x1400abd02  mov     byte ptr [rbp+arg_18], r12b
0x1400abd06  movups  [rbp+var_40], xmm0
0x1400abd0a  movups  [rbp+var_80], xmm0
0x1400abd0e  test    r9d, r9d
0x1400abd11  jz      short loc_1400ABD38
0x1400abd13  cmp     [rax+8], r12
0x1400abd17  jnz     short loc_1400ABD31
0x1400abd19  cmp     [rax], r12
0x1400abd1c  jnz     short loc_1400ABD31
0x1400abd1e  cmp     r9d, 2
0x1400abd22  jnz     short loc_1400ABD38
0x1400abd24  test    r8d, r8d
0x1400abd27  jnz     short loc_1400ABD38
0x1400abd29  mov     ebx, r12d
0x1400abd2c  jmp     loc_1400AC0ED
0x1400abd31  mov     ecx, 5
0x1400abd36  int     29h; Win8: RtlFailFast(ecx)
0x1400abd38  mov     rcx, [rax+38h]
0x1400abd3c  mov     r15b, [rax+58h]
0x1400abd40  test    rcx, rcx
0x1400abd43  jnz     short loc_1400ABD49
0x1400abd45  mov     rcx, [rax+48h]; Token
0x1400abd49  lea     rdx, [rbp+var_40]
0x1400abd4d  call    VhdmpiBeginImpersonation
0x1400abd52  mov     ebx, eax
0x1400abd54  test    eax, eax
0x1400abd56  jns     short loc_1400ABDB1
0x1400abd58  mov     ecx, cs:dword_140087708
0x1400abd5e  cmp     ecx, 2
0x1400abd61  jbe     loc_1400AC0ED
0x1400abd67  mov     edx, 80000h
0x1400abd6c  lea     rcx, dword_140087708
0x1400abd73  call    _tlgKeywordOn
0x1400abd78  test    al, al
0x1400abd7a  jz      loc_1400AC0ED
0x1400abd80  mov     ecx, 2545h
0x1400abd85  mov     dword ptr [rsp+160h+var_138], ebx; char
0x1400abd89  mov     r9d, edx; int
0x1400abd8c  lea     rax, aCleanupWithSta_1; "Cleanup with status 0x%08X"
0x1400abd93  mov     edx, ecx; int
0x1400abd95  mov     [rsp+160h+var_140], rax; char *
0x1400abd9a  lea     rcx, aVhdmpifilewrap_5; "VhdmpiFileWrapperReopenFileReference"
0x1400abda1  mov     r8d, 2; int
0x1400abda7  call    TraceEvents
0x1400abdac  jmp     loc_1400AC0ED
0x1400abdb1  mov     ecx, 3
0x1400abdb6  lea     r8d, [rcx-2]
0x1400abdba  cmp     r14d, r8d
0x1400abdbd  jnz     short loc_1400ABDD0
0x1400abdbf  cmp     edi, ecx
0x1400abdc1  mov     edx, 0C0000000h
0x1400abdc6  mov     eax, 80000000h
0x1400abdcb  cmovnz  edx, eax
0x1400abdce  jmp     short loc_1400ABDD5
0x1400abdd0  mov     edx, 80000000h; unsigned int
0x1400abdd5  test    r14d, r14d
0x1400abdd8  mov     r9b, r15b; unsigned __int8
0x1400abddb  setnz   al
0x1400abdde  cmp     r14d, r8d
0x1400abde1  cmovnz  r8d, ecx; unsigned int
0x1400abde5  lea     rcx, [rbp+arg_18]
0x1400abde9  mov     [rsp+160h+var_128], rcx; unsigned __int8 *
0x1400abdee  lea     rcx, [rbp+FileObject]
0x1400abdf2  mov     [rsp+160h+var_130], rcx; struct _FILE_OBJECT **
0x1400abdf7  lea     rcx, [rbp+Handle]
0x1400abdfb  mov     [rsp+160h+var_138], rcx; void **
0x1400abe00  mov     rcx, r13; struct _VHD_FILE_WRAPPER *
0x1400abe03  mov     byte ptr [rsp+160h+var_140], al; char
0x1400abe07  call    ?VhdmpiOpenBackingFile@@YAJPEAU_VHD_FILE_WRAPPER@@KKEEPEAPEAXPEAPEAU_FILE_OBJECT@@PEAE@Z; VhdmpiOpenBackingFile(_VHD_FILE_WRAPPER *,ulong,ulong,uchar,uchar,void * *,_FILE_OBJECT * *,uchar *)
0x1400abe0c  lea     rcx, [rbp+var_40]
0x1400abe10  mov     ebx, eax
0x1400abe12  call    VhdmpiEndImpersonation
0x1400abe17  test    ebx, ebx
0x1400abe19  jns     short loc_1400ABE8C
0x1400abe1b  mov     eax, cs:dword_140087708
0x1400abe21  cmp     eax, 2
0x1400abe24  jbe     short loc_1400ABE6C
0x1400abe26  mov     edx, 80000h
0x1400abe2b  lea     rcx, dword_140087708
0x1400abe32  call    _tlgKeywordOn
0x1400abe37  test    al, al
0x1400abe39  jz      short loc_1400ABE6C
0x1400abe3b  mov     ecx, 2560h
0x1400abe40  mov     [rsp+160h+var_130], r13
0x1400abe45  mov     r9d, edx; int
0x1400abe48  mov     dword ptr [rsp+160h+var_138], ebx; char
0x1400abe4c  mov     edx, ecx; int
0x1400abe4e  lea     rax, aLogStatus0x08x_5; "Log status 0x%08X: File = %wZ"
0x1400abe55  lea     rcx, aVhdmpifilewrap_5; "VhdmpiFileWrapperReopenFileReference"
0x1400abe5c  mov     [rsp+160h+var_140], rax; char *
0x1400abe61  mov     r8d, 2; int
0x1400abe67  call    TraceEvents
0x1400abe6c  mov     edx, ebx
0x1400abe6e  mov     rcx, r13
0x1400abe71  call    VhdmpiFileWrapperIoErrorIsRecoverable
0x1400abe76  mov     rdi, [rbp+FileObject]
0x1400abe7a  test    al, al
0x1400abe7c  jnz     loc_1400AC0C4
0x1400abe82  mov     ebx, 0C000026Eh
0x1400abe87  jmp     loc_1400AC0C4
0x1400abe8c  mov     rdi, [rbp+FileObject]
0x1400abe90  mov     rcx, rdi; FileObject
0x1400abe93  call    cs:__imp_IoGetRelatedDeviceObject
0x1400abe9a  nop     dword ptr [rax+rax+00h]
0x1400abe9f  mov     r15, rax
0x1400abea2  test    r14d, r14d
0x1400abea5  jnz     loc_1400AC0A6
0x1400abeab  lea     rdx, [rbp+var_80]
0x1400abeaf  mov     rcx, rdi
0x1400abeb2  call    VhdmpiGetVolumeStableGuid
0x1400abeb7  mov     ebx, eax
0x1400abeb9  test    eax, eax
0x1400abebb  jns     short loc_1400ABF1B
0x1400abebd  mov     eax, cs:dword_140087708
0x1400abec3  cmp     eax, 2
0x1400abec6  jbe     loc_1400AC0C4
0x1400abecc  mov     edx, 80000h
0x1400abed1  lea     rcx, dword_140087708
0x1400abed8  call    _tlgKeywordOn
0x1400abedd  test    al, al
0x1400abedf  jz      loc_1400AC0C4
0x1400abee5  mov     ecx, 2573h
0x1400abeea  mov     r9d, edx; int
0x1400abeed  mov     [rsp+160h+var_130], r13
0x1400abef2  mov     edx, ecx; int
0x1400abef4  mov     dword ptr [rsp+160h+var_138], ebx; char
0x1400abef8  lea     rax, aCleanupWithSta_0; "Cleanup with status 0x%08X: File = %wZ"
0x1400abeff  mov     r8d, 2; int
0x1400abf05  lea     rcx, aVhdmpifilewrap_5; "VhdmpiFileWrapperReopenFileReference"
0x1400abf0c  mov     [rsp+160h+var_140], rax; char *
0x1400abf11  call    TraceEvents
0x1400abf16  jmp     loc_1400AC0C4
0x1400abf1b  mov     rax, qword ptr [rbp+var_80]
0x1400abf1f  mov     r14, qword ptr [rbp+var_80+8]
0x1400abf23  cmp     rax, [r13+1F8h]
0x1400abf2a  jnz     loc_1400AC10B
0x1400abf30  cmp     r14, [r13+200h]
0x1400abf37  jnz     loc_1400AC10B
0x1400abf3d  mov     rcx, [rbp+Handle]; void *
0x1400abf41  lea     rdx, [rbp+var_60]; __int64 *
0x1400abf45  call    ?VhdmpiGetFileId@@YAJPEAXPEA_J@Z; VhdmpiGetFileId(void *,__int64 *)
0x1400abf4a  mov     ebx, eax
0x1400abf4c  test    eax, eax
0x1400abf4e  jns     short loc_1400ABF82
0x1400abf50  mov     eax, cs:dword_140087708
0x1400abf56  cmp     eax, 2
0x1400abf59  jbe     loc_1400AC0C4
0x1400abf5f  mov     edx, 80000h
0x1400abf64  lea     rcx, dword_140087708
0x1400abf6b  call    _tlgKeywordOn
0x1400abf70  test    al, al
0x1400abf72  jz      loc_1400AC0C4
0x1400abf78  mov     ecx, 257Eh
0x1400abf7d  jmp     loc_1400ABEEA
0x1400abf82  mov     r8, [rbp+var_60]
0x1400abf86  cmp     r8, [r13+1F0h]
0x1400abf8d  jz      short loc_1400ABFFF
0x1400abf8f  mov     eax, cs:dword_140087708
0x1400abf95  mov     ebx, 0C0000001h
0x1400abf9a  cmp     eax, 2
0x1400abf9d  jbe     loc_1400AC0C4
0x1400abfa3  mov     edx, 80000h
0x1400abfa8  lea     rcx, dword_140087708
0x1400abfaf  call    _tlgKeywordOn
0x1400abfb4  test    al, al
0x1400abfb6  jz      loc_1400AC0C4
0x1400abfbc  mov     rax, [r13+1F0h]
0x1400abfc3  mov     ecx, 2585h
0x1400abfc8  mov     [rsp+160h+var_128], r13
0x1400abfcd  mov     r9d, edx; int
0x1400abfd0  mov     [rsp+160h+var_130], r8
0x1400abfd5  mov     edx, ecx; int
0x1400abfd7  mov     [rsp+160h+var_138], rax; char
0x1400abfdc  lea     rax, aCleanupStatusN_11; "Cleanup [status = ((NTSTATUS)0xC0000001"...
0x1400abfe3  mov     r8d, 2; int
0x1400abfe9  mov     [rsp+160h+var_140], rax; char *
0x1400abfee  lea     rcx, aVhdmpifilewrap_5; "VhdmpiFileWrapperReopenFileReference"
0x1400abff5  call    TraceEvents
0x1400abffa  jmp     loc_1400AC0C4
0x1400abfff  movsx   ecx, byte ptr [r15+4Ch]
0x1400ac004  movsx   eax, byte ptr [r13+220h]
0x1400ac00c  add     ecx, 3
0x1400ac00f  cmp     eax, ecx
0x1400ac011  jge     short loc_1400AC075
0x1400ac013  mov     eax, cs:dword_140087708
0x1400ac019  mov     ebx, 0C0000001h
0x1400ac01e  cmp     eax, 2
0x1400ac021  jbe     loc_1400AC0C4
0x1400ac027  mov     edx, 80000h
0x1400ac02c  lea     rcx, dword_140087708
0x1400ac033  call    _tlgKeywordOn
0x1400ac038  test    al, al
0x1400ac03a  jz      loc_1400AC0C4
0x1400ac040  movsx   eax, byte ptr [r15+4Ch]
0x1400ac045  mov     r10d, 258Eh
0x1400ac04b  movsx   ecx, byte ptr [r13+220h]
0x1400ac053  mov     r9d, edx
0x1400ac056  mov     [rsp+160h+var_128], r13
0x1400ac05b  sub     ecx, 3
0x1400ac05e  mov     dword ptr [rsp+160h+var_130], eax
0x1400ac062  mov     edx, r10d
0x1400ac065  mov     dword ptr [rsp+160h+var_138], ecx
0x1400ac069  lea     rax, aCleanupStatusN; "Cleanup [status = ((NTSTATUS)0xC0000001"...
0x1400ac070  jmp     loc_1400ABFE3
0x1400ac075  mov     rcx, rsi; struct _VHD_SAFE_FILE_REFERENCE *
0x1400ac078  call    ?VhdmpiCleanupSafeFileReference@@YAXPEAU_VHD_SAFE_FILE_REFERENCE@@J@Z; VhdmpiCleanupSafeFileReference(_VHD_SAFE_FILE_REFERENCE *,long)
0x1400ac07d  mov     rcx, [r13+218h]; Object
0x1400ac084  call    cs:__imp_ObfDereferenceObject
0x1400ac08b  nop     dword ptr [rax+rax+00h]
0x1400ac090  mov     rcx, r15; Object
0x1400ac093  mov     [r13+218h], r15
0x1400ac09a  call    cs:__imp_ObfReferenceObject
0x1400ac0a1  nop     dword ptr [rax+rax+00h]
0x1400ac0a6  mov     rdx, [rbp+Handle]; void *
0x1400ac0aa  mov     r8, rdi; struct _FILE_OBJECT *
0x1400ac0ad  mov     rcx, rsi; struct _VHD_SAFE_FILE_REFERENCE *
0x1400ac0b0  call    ?VhdmpiSetSafeFileReference@@YAXPEAU_VHD_SAFE_FILE_REFERENCE@@PEAXPEAU_FILE_OBJECT@@@Z; VhdmpiSetSafeFileReference(_VHD_SAFE_FILE_REFERENCE *,void *,_FILE_OBJECT *)
0x1400ac0b5  mov     rcx, rsi; struct _VHD_SAFE_FILE_REFERENCE *
0x1400ac0b8  call    ?VhdmpiResumeSafeFileReference@@YAXPEAU_VHD_SAFE_FILE_REFERENCE@@@Z; VhdmpiResumeSafeFileReference(_VHD_SAFE_FILE_REFERENCE *)
0x1400ac0bd  mov     [rbp+Handle], r12
0x1400ac0c1  mov     rdi, r12
0x1400ac0c4  mov     rcx, [rbp+Handle]; Handle
0x1400ac0c8  test    rcx, rcx
0x1400ac0cb  jz      short loc_1400AC0D9
0x1400ac0cd  call    cs:__imp_ZwClose
0x1400ac0d4  nop     dword ptr [rax+rax+00h]
0x1400ac0d9  test    rdi, rdi
0x1400ac0dc  jz      short loc_1400AC0ED
0x1400ac0de  mov     rcx, rdi; Object
0x1400ac0e1  call    cs:__imp_ObfDereferenceObject
0x1400ac0e8  nop     dword ptr [rax+rax+00h]
0x1400ac0ed  mov     eax, ebx
0x1400ac0ef  mov     rbx, [rsp+160h+arg_8]
0x1400ac0f7  add     rsp, 130h
0x1400ac0fe  pop     r15
0x1400ac100  pop     r14
0x1400ac102  pop     r13
0x1400ac104  pop     r12
0x1400ac106  pop     rdi
0x1400ac107  pop     rsi
0x1400ac108  pop     rbp
0x1400ac109  retn
0x1400ac10b  mov     eax, cs:dword_140087708
0x1400ac111  mov     ebx, 0C0000001h
0x1400ac116  mov     dword ptr [rbp+var_60], ebx
0x1400ac119  cmp     eax, 2
0x1400ac11c  jbe     short loc_1400AC0C4
0x1400ac11e  mov     edx, 80000h
0x1400ac123  lea     rcx, dword_140087708
0x1400ac12a  call    _tlgKeywordOn
0x1400ac12f  test    al, al
0x1400ac131  jz      short loc_1400AC0C4
0x1400ac133  mov     rcx, [rbp+arg_0]
0x1400ac137  movzx   edx, byte ptr [rbp+var_80+0Dh]
0x1400ac13b  movzx   r8d, byte ptr [rbp+var_80+0Ch]
0x1400ac140  movzx   r9d, byte ptr [rbp+var_80+0Bh]
0x1400ac145  mov     rax, [rbp+arg_0]
0x1400ac149  movzx   r15d, byte ptr [r13+206h]
0x1400ac151  movzx   r12d, byte ptr [r13+205h]
0x1400ac159  movzx   r10d, byte ptr [rbp+var_80+0Ah]
0x1400ac15e  movzx   eax, byte ptr [rax+203h]
0x1400ac165  movzx   r11d, byte ptr [rbp+var_80+9]
0x1400ac16a  movzx   edi, word ptr [rbp+var_80+6]
0x1400ac16e  movzx   esi, word ptr [rbp+var_80+4]
0x1400ac172  mov     [rsp+160h+var_88], rcx
0x1400ac17a  mov     [rbp+arg_18], eax
0x1400ac17d  movzx   eax, byte ptr [rcx+202h]
0x1400ac184  mov     [rbp+var_58], eax
0x1400ac187  movzx   eax, byte ptr [rcx+201h]
0x1400ac18e  mov     [rbp+var_54], eax
0x1400ac191  movzx   eax, byte ptr [rcx+200h]
0x1400ac198  mov     [rbp+var_50], eax
0x1400ac19b  movzx   eax, word ptr [rcx+1FEh]
0x1400ac1a2  mov     [rbp+var_4C], eax
0x1400ac1a5  movzx   eax, word ptr [rcx+1FCh]
0x1400ac1ac  mov     [rbp+var_48], eax
0x1400ac1af  mov     rax, rcx
0x1400ac1b2  movzx   eax, byte ptr [rbp+var_80+0Fh]
  ... truncated ...
```
