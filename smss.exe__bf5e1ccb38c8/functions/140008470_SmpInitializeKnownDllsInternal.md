# SmpInitializeKnownDllsInternal

- ea: `0x140008470`
- end: `0x140008aac`
- name: `SmpInitializeKnownDllsInternal`
- size: `1596`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14000eb40`

## callees

- `0x1400010ec`
- `0x140008470`
- `0x140008ab4`
- `0x140008b10`
- `0x140008ba8`
- `0x14000d494`
- `0x14000d4c0`
- `0x140017d5c`
- `0x14001cc29`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x1400088bb`
- `ntdll!RtlInitUnicodeString` at `0x140008a3a`
- `ntdll!RtlInitUnicodeString` at `0x1400088bb`
- `ntdll!RtlInitUnicodeString` at `0x140008a3a`
- `ntdll!NtOpenFile` at `0x140008822`
- `ntdll!NtOpenFile` at `0x140008822`
- `ntdll!NtClose` at `0x1400088e3`
- `ntdll!NtClose` at `0x1400088ee`
- `ntdll!NtClose` at `0x1400088e3`
- `ntdll!NtClose` at `0x1400088ee`
- `ntdll!RtlAllocateHeap` at `0x140008740`
- `ntdll!RtlAllocateHeap` at `0x140008740`
- `ntdll!RtlFreeHeap` at `0x1400087f9`
- `ntdll!RtlFreeHeap` at `0x14000890d`
- `ntdll!RtlFreeHeap` at `0x1400087f9`
- `ntdll!RtlFreeHeap` at `0x14000890d`
- `ntdll!RtlAppendUnicodeToString` at `0x1400087a0`
- `ntdll!RtlAppendUnicodeToString` at `0x1400087a0`
- `ntdll!RtlCompareUnicodeString` at `0x140008619`
- `ntdll!RtlCompareUnicodeString` at `0x140008619`
- `ntdll!RtlAppendUnicodeStringToString` at `0x1400087b3`
- `ntdll!RtlAppendUnicodeStringToString` at `0x1400087b3`
- `ntdll!NtQueryObject` at `0x140008705`
- `ntdll!NtQueryObject` at `0x14000876e`
- `ntdll!NtQueryObject` at `0x140008705`
- `ntdll!NtQueryObject` at `0x14000876e`
- `ntdll!NtSystemDebugControl` at `0x1400087e1`
- `ntdll!NtSystemDebugControl` at `0x1400087e1`
- `ntdll!LdrVerifyImageMatchesChecksumEx` at `0x140008863`
- `ntdll!LdrVerifyImageMatchesChecksumEx` at `0x140008863`
- `ntdll!RtlAppxIsFileOwnedByTrustedInstaller` at `0x14000889f`
- `ntdll!RtlAppxIsFileOwnedByTrustedInstaller` at `0x14000889f`

## string_xrefs

- `0x140008522`: `SmpInitializeKnownDllsInternal`
- `0x140008a1c`: `SmpInitializeKnownDllsInternal`
- `0x140008a51`: `SmpInitializeKnownDllsInternal`
- `0x1400088b0`: `Verification of a KnownDLL failed.`
- `0x140008a2f`: `Non-DLL file included in KnownDLL list.`

## pseudocode

```c
__int64 __fastcall SmpInitializeKnownDllsInternal(__int64 a1, void *a2, int a3, int a4, char a5)
{
  int v7; // eax
  unsigned int v8; // ebx
  unsigned __int8 v9; // r13
  unsigned int v10; // r15d
  _QWORD *v11; // r12
  unsigned int v12; // edi
  __int64 v13; // rbx
  const UNICODE_STRING *v14; // r14
  const UNICODE_STRING *v15; // rsi
  PWSTR Buffer; // rax
  BOOL v17; // edx
  __m128i *Heap; // rsi
  __int16 v19; // cx
  __int16 v20; // cx
  int v21; // esi
  __int64 v22; // rcx
  __int128 *v23; // rbx
  unsigned int v24; // esi
  __int128 *v25; // rdi
  int v26; // eax
  _QWORD *v27; // rcx
  _QWORD *v28; // rdx
  __int64 v29; // r8
  char v31[4]; // [rsp+30h] [rbp-D0h] BYREF
  ULONG ObjectInformationLength; // [rsp+34h] [rbp-CCh] BYREF
  unsigned int v33; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v34; // [rsp+40h] [rbp-C0h] BYREF
  void *FileHandle; // [rsp+50h] [rbp-B0h] BYREF
  PVOID BaseAddress; // [rsp+58h] [rbp-A8h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+60h] [rbp-A0h] BYREF
  struct _OBJECT_ATTRIBUTES Handle; // [rsp+70h] [rbp-90h] BYREF
  __int128 ObjectInformation; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v40[48]; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v41; // [rsp+E0h] [rbp-20h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+F0h] [rbp-10h] BYREF
  _DWORD v43[2]; // [rsp+100h] [rbp+0h] BYREF
  void *v44; // [rsp+108h] [rbp+8h]
  __int128 *v45; // [rsp+110h] [rbp+10h]
  HANDLE v46; // [rsp+118h] [rbp+18h]
  int v47; // [rsp+120h] [rbp+20h]
  _BYTE *v48; // [rsp+128h] [rbp+28h]
  int v49; // [rsp+130h] [rbp+30h]
  int v50; // [rsp+134h] [rbp+34h]
  __int16 v51; // [rsp+138h] [rbp+38h]
  unsigned __int64 Parameters[3]; // [rsp+140h] [rbp+40h] BYREF
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+158h] [rbp+58h] BYREF

  FileHandle = 0;
  ObjectInformationLength = 0;
  v31[0] = 0;
  DestinationString = 0;
  v41 = 0;
  v34 = 0;
  IoStatusBlock = 0;
  memset(&Handle, 0, 44);
  ObjectInformation = 0;
  Destination = 0;
  memset(v40, 0, 44);
  memset_0(v43, 0, 0x40u);
  BaseAddress = 0;
  v33 = 0;
  v7 = SmpRandomizeDllList(&SmpKnownDllsList, &BaseAddress, &v33);
  v8 = v7;
  if ( v7 >= 0 )
  {
    Handle.Length = 48;
    *((_QWORD *)&v41 + 1) = &v34;
    Handle.RootDirectory = a2;
    v45 = &v41;
    v9 = 0;
    Handle.Attributes = 64;
    v44 = &SmpProcessModuleImports;
    *(_OWORD *)&v40[32] = (unsigned __int64)SmpKnownDllSecurityDescriptor;
    v48 = v40;
    Handle.ObjectName = 0;
    *(_OWORD *)&Handle.SecurityDescriptor = 0;
    v43[0] = 64;
    v43[1] = 7;
    *(_DWORD *)v40 = 48;
    *(_QWORD *)&v40[8] = a1;
    *(_DWORD *)&v40[24] = 80;
    *(_QWORD *)&v40[16] = 0;
    v47 = 983071;
    v49 = 16;
    while ( 1 )
    {
      v10 = v33;
      v11 = BaseAddress;
      v12 = 0;
      *((_QWORD *)&v34 + 1) = &v34;
      *(_QWORD *)&v34 = &v34;
      while ( v12 < v10 )
      {
        v13 = SmpExcludeKnownDllsList;
        v14 = (const UNICODE_STRING *)v11[2 * v12 + 1];
        v15 = v14 + 1;
        while ( 1 )
        {
          if ( (__int64 *)v13 == &SmpExcludeKnownDllsList )
            goto LABEL_11;
          v15 = v14 + 1;
          if ( !RtlCompareUnicodeString((PCUNICODE_STRING)(v13 + 16), v14 + 1, 1u) )
            break;
          v13 = *(_QWORD *)v13;
        }
        if ( !v13 )
        {
LABEL_11:
          if ( SmpFindRegistryValueEx(&SmpExcludeKnownDllsList, &v14[2]) )
            goto LABEL_45;
          if ( v15->Length < 2u )
          {
            v50 = 0x1000000;
          }
          else
          {
            Buffer = v14[1].Buffer;
            v17 = *Buffer == 95;
            if ( *Buffer == 42 )
            {
              if ( (a5 & 2) != 0 )
                goto LABEL_45;
            }
            else if ( (a5 & 3) == 1 )
            {
              goto LABEL_45;
            }
            v50 = 0x1000000;
            if ( v17 )
            {
              if ( a3 || !a4 )
                goto LABEL_45;
              v50 = 17825792;
            }
          }
          Handle.ObjectName = (PUNICODE_STRING)&v14[2];
          if ( (*(_DWORD *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 188LL) & 0x40000) != 0 )
          {
            LODWORD(ObjectInformation) = 0;
            *((_QWORD *)&ObjectInformation + 1) = 0;
            ObjectInformationLength = 0;
            if ( NtQueryObject(
                   Handle.RootDirectory,
                   ObjectNameInformation,
                   &ObjectInformation,
                   0,
                   &ObjectInformationLength) == -1073741820 )
            {
              ObjectInformationLength += 2;
              ObjectInformationLength += Handle.ObjectName->Length;
              Heap = (__m128i *)RtlAllocateHeap(
                                  *(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL),
                                  0,
                                  ObjectInformationLength);
              if ( Heap )
              {
                if ( NtQueryObject(
                       Handle.RootDirectory,
                       ObjectNameInformation,
                       Heap,
                       ObjectInformationLength,
                       &ObjectInformationLength) >= 0 )
                {
                  v19 = _mm_cvtsi128_si32(*Heap);
                  Destination = (struct _UNICODE_STRING)*Heap;
                  Destination.MaximumLength = Handle.ObjectName->Length + v19 + 2;
                  if ( RtlAppendUnicodeToString(&Destination, L"\\") >= 0
                    && RtlAppendUnicodeStringToString(&Destination, Handle.ObjectName) >= 0 )
                  {
                    NtSystemDebugControl(SysDbgClearUmAttachPid|SysDbgSetTracepoint, &Destination, 0x10u, 0, 0, 0);
                  }
                }
                RtlFreeHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, Heap);
              }
            }
          }
          if ( NtOpenFile(&FileHandle, 0x120020u, &Handle, &IoStatusBlock, 5u, 0x60u) >= 0 )
          {
            *(_QWORD *)&v40[16] = v14 + 2;
            *(_QWORD *)&v41 = v14 + 2;
            if ( *(_QWORD *)&v40[32] )
            {
              v20 = *(_WORD *)(*(_QWORD *)&v40[32] + 2LL);
              v9 = v20 & 8;
              *(_WORD *)(*(_QWORD *)&v40[32] + 2LL) = v20 | 8;
            }
            v21 = LdrVerifyImageMatchesChecksumEx((unsigned __int64)FileHandle | 1, v43);
            if ( *(_QWORD *)&v40[32] )
              *(_WORD *)(*(_QWORD *)&v40[32] + 2LL) ^= (v9 ^ (unsigned __int8)*(_WORD *)(*(_QWORD *)&v40[32] + 2LL)) & 8;
            if ( v21 >= 0 )
            {
              if ( (v51 & 0x2000) == 0 )
              {
                RtlInitUnicodeString(&DestinationString, L"Non-DLL file included in KnownDLL list.");
                v21 = -1073740945;
LABEL_61:
                Parameters[2] = (unsigned __int64)&v14[2];
                Parameters[0] = (unsigned __int64)&DestinationString;
                Parameters[1] = v21;
                SmpLogFailureString("SmpInitializeKnownDllsInternal", 5192, v14[1].Buffer, (unsigned int)v21);
                SmpTerminate(Parameters, 5u, 3u);
              }
              NtClose(v46);
            }
            else
            {
              v31[0] = 1;
              if ( v21 == -1073740760 )
              {
                if ( (int)RtlAppxIsFileOwnedByTrustedInstaller(FileHandle, v31) < 0 || v31[0] )
                {
LABEL_39:
                  RtlInitUnicodeString(&DestinationString, L"Verification of a KnownDLL failed.");
                  goto LABEL_61;
                }
              }
              else if ( v21 != -1073741771 )
              {
                goto LABEL_39;
              }
            }
            NtClose(FileHandle);
          }
        }
LABEL_45:
        ++v12;
      }
      RtlFreeHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, v11);
      v23 = (__int128 *)v34;
      BaseAddress = 0;
      v24 = 0;
      v33 = 0;
      if ( (__int128 *)v34 == &v34 )
        return 0;
      do
      {
        v25 = v23;
        v23 = *(__int128 **)v23;
        if ( SmpFindModuleInModuleList(v22, v25 + 1) )
          SmpFreeSavedRegistryEntry(v25);
        else
          ++v24;
      }
      while ( v23 != &v34 );
      v33 = v24;
      if ( !v24 )
        return 0;
      v26 = SmpRandomizeDllList(&v34, &BaseAddress, &v33);
      v27 = (_QWORD *)v34;
      v8 = v26;
      if ( *(__int128 **)(v34 + 8) != &v34
        || (v28 = (_QWORD *)*((_QWORD *)&v34 + 1), **((__int128 ***)&v34 + 1) != &v34)
        || (**((_QWORD **)&v34 + 1) = v34, v27[1] = v28, *(__int64 **)(SmpKnownDllsList + 8) != &SmpKnownDllsList)
        || (v29 = qword_140030AE8, *(__int64 **)qword_140030AE8 != &SmpKnownDllsList)
        || *(_QWORD **)(*v27 + 8LL) != v27
        || (_QWORD *)*v28 != v27 )
      {
        __fastfail(3u);
      }
      *(_QWORD *)qword_140030AE8 = v27;
      qword_140030AE8 = v27[1];
      *(_QWORD *)v27[1] = &SmpKnownDllsList;
      v27[1] = v29;
      if ( v26 < 0 )
      {
        SmpLogFailure("SmpInitializeKnownDllsInternal", 5244, (unsigned int)v26);
        return v8;
      }
    }
  }
  SmpLogFailure("SmpInitializeKnownDllsInternal", 4917, (unsigned int)v7);
  return v8;
}

```

## disassembly

```asm
0x140008470  mov     [rsp-8+arg_0], rbx
0x140008475  mov     [rsp-8+arg_18], r9d
0x14000847a  mov     [rsp-8+arg_10], r8d
0x14000847f  push    rbp
0x140008480  push    rsi
0x140008481  push    rdi
0x140008482  push    r12
0x140008484  push    r13
0x140008486  push    r14
0x140008488  push    r15
0x14000848a  lea     rbp, [rsp-70h]
0x14000848f  sub     rsp, 170h
0x140008496  xorps   xmm0, xmm0
0x140008499  xorps   xmm1, xmm1
0x14000849c  mov     rdi, rdx
0x14000849f  mov     rsi, rcx
0x1400084a2  xor     r14d, r14d
0x1400084a5  lea     rcx, [rbp+0A0h+var_A0]; void *
0x1400084a9  xor     eax, eax
0x1400084ab  mov     [rsp+1A0h+FileHandle], r14
0x1400084b0  movups  xmmword ptr [rbp+0A0h+Source], xmm0
0x1400084b4  xor     edx, edx; Val
0x1400084b6  mov     r8d, 40h ; '@'; Size
0x1400084bc  movups  [rbp+0A0h+var_E0], xmm0
0x1400084c0  mov     [rsp+1A0h+ObjectInformationLength], r14d
0x1400084c5  movups  xmmword ptr [rbp+0A0h+Source+0Ch], xmm0
0x1400084c9  mov     [rsp+1A0h+var_170], al
0x1400084cd  movups  [rbp+0A0h+var_E0+0Ch], xmm0
0x1400084d1  movups  xmmword ptr [rbp+0A0h+DestinationString.Length], xmm0
0x1400084d5  movups  [rbp+0A0h+var_C0], xmm0
0x1400084d9  movups  [rsp+1A0h+var_160], xmm1
0x1400084de  movups  xmmword ptr [rbp+0A0h+IoStatusBlock], xmm0
0x1400084e2  movups  xmmword ptr [rsp+1A0h+Handle], xmm0
0x1400084e7  movups  [rbp+0A0h+ObjectInformation], xmm0
0x1400084eb  movups  xmmword ptr [rsp+1A0h+Destination.Length], xmm1
0x1400084f0  movups  [rbp+0A0h+var_F0], xmm0
0x1400084f4  call    memset_0
0x1400084f9  lea     r8, [rsp+1A0h+var_168]
0x1400084fe  mov     [rsp+1A0h+BaseAddress], r14
0x140008503  lea     rdx, [rsp+1A0h+BaseAddress]
0x140008508  mov     [rsp+1A0h+var_168], r14d
0x14000850d  lea     rcx, SmpKnownDllsList
0x140008514  call    SmpRandomizeDllList
0x140008519  mov     ebx, eax
0x14000851b  test    eax, eax
0x14000851d  jns     short loc_140008538
0x14000851f  mov     r8d, eax
0x140008522  lea     rcx, aSmpinitializek; "SmpInitializeKnownDllsInternal"
0x140008529  mov     edx, 1335h
0x14000852e  call    SmpLogFailure
0x140008533  jmp     loc_140008A8F
0x140008538  lea     rax, [rsp+1A0h+var_160]
0x14000853d  mov     dword ptr [rsp+1A0h+Handle], 30h ; '0'
0x140008545  mov     qword ptr [rbp+0A0h+var_C0+8], rax
0x140008549  xorps   xmm0, xmm0
0x14000854c  lea     rax, [rbp+0A0h+var_C0]
0x140008550  mov     [rsp+1A0h+Handle+8], rdi
0x140008555  mov     [rbp+0A0h+var_90], rax
0x140008559  mov     r13d, r14d
0x14000855c  lea     rax, SmpProcessModuleImports
0x140008563  mov     dword ptr [rbp+0A0h+Source+8], 40h ; '@'
0x14000856a  mov     [rbp+0A0h+var_98], rax
0x14000856e  mov     rax, cs:SmpKnownDllSecurityDescriptor
0x140008575  mov     [rbp+0A0h+var_D0], rax
0x140008579  lea     rax, [rbp+0A0h+var_F0]
0x14000857d  mov     [rbp+0A0h+var_78], rax
0x140008581  mov     [rbp+0A0h+Source], r14
0x140008585  movdqu  [rbp+0A0h+var_110], xmm0
0x14000858a  mov     [rbp+0A0h+var_A0], 40h ; '@'
0x140008591  mov     [rbp+0A0h+var_9C], 7
0x140008598  mov     dword ptr [rbp+0A0h+var_F0], 30h ; '0'
0x14000859f  mov     qword ptr [rbp+0A0h+var_F0+8], rsi
0x1400085a3  mov     dword ptr [rbp+0A0h+var_E0+8], 50h ; 'P'
0x1400085aa  mov     qword ptr [rbp+0A0h+var_E0], r14
0x1400085ae  mov     [rbp+0A0h+var_C8], r14
0x1400085b2  mov     [rbp+0A0h+var_80], 0F001Fh
0x1400085b9  mov     [rbp+0A0h+var_70], 10h
0x1400085c0  mov     r15d, [rsp+1A0h+var_168]
0x1400085c5  lea     rax, [rsp+1A0h+var_160]
0x1400085ca  mov     r12, [rsp+1A0h+BaseAddress]
0x1400085cf  mov     edi, r14d
0x1400085d2  mov     qword ptr [rsp+1A0h+var_160+8], rax
0x1400085d7  lea     rax, [rsp+1A0h+var_160]
0x1400085dc  mov     qword ptr [rsp+1A0h+var_160], rax
0x1400085e1  lea     rcx, SmpExcludeKnownDllsList
0x1400085e8  cmp     edi, r15d
0x1400085eb  jnb     loc_1400088FB
0x1400085f1  mov     rbx, cs:SmpExcludeKnownDllsList
0x1400085f8  mov     eax, edi
0x1400085fa  add     rax, rax
0x1400085fd  mov     r14, [r12+rax*8+8]
0x140008602  lea     rsi, [r14+10h]
0x140008606  cmp     rbx, rcx
0x140008609  jz      short loc_14000863F
0x14000860b  lea     rsi, [r14+10h]
0x14000860f  mov     r8b, 1; CaseInSensitive
0x140008612  mov     rdx, rsi; String2
0x140008615  lea     rcx, [rbx+10h]; String1
0x140008619  call    cs:__imp_RtlCompareUnicodeString
0x14000861f  test    eax, eax
0x140008621  jz      short loc_14000862F
0x140008623  mov     rbx, [rbx]
0x140008626  lea     rcx, SmpExcludeKnownDllsList
0x14000862d  jmp     short loc_140008606
0x14000862f  test    rbx, rbx
0x140008632  jnz     loc_1400088F4
0x140008638  lea     rcx, SmpExcludeKnownDllsList
0x14000863f  lea     rbx, [r14+20h]
0x140008643  mov     rdx, rbx
0x140008646  call    SmpFindRegistryValueEx
0x14000864b  test    rax, rax
0x14000864e  jnz     loc_1400088F4
0x140008654  cmp     word ptr [rsi], 2
0x140008658  jb      short loc_1400086B9
0x14000865a  mov     rax, [r14+18h]
0x14000865e  xor     edx, edx
0x140008660  cmp     word ptr [rax], 5Fh ; '_'
0x140008664  setz    dl
0x140008667  cmp     word ptr [rax], 2Ah ; '*'
0x14000866b  jnz     short loc_14000867B
0x14000866d  test    byte ptr [rbp+0A0h+arg_20], 2
0x140008674  jz      short loc_14000868B
0x140008676  jmp     loc_1400088F4
0x14000867b  mov     eax, [rbp+0A0h+arg_20]
0x140008681  and     al, 3
0x140008683  cmp     al, 1
0x140008685  jz      loc_1400088F4
0x14000868b  mov     [rbp+0A0h+var_6C], 1000000h
0x140008692  test    edx, edx
0x140008694  jz      short loc_1400086C0
0x140008696  cmp     [rbp+0A0h+arg_10], 0
0x14000869d  jnz     loc_1400088F4
0x1400086a3  cmp     [rbp+0A0h+arg_18], 0
0x1400086aa  jz      loc_1400088F4
0x1400086b0  mov     [rbp+0A0h+var_6C], 1100000h
0x1400086b7  jmp     short loc_1400086C0
0x1400086b9  mov     [rbp+0A0h+var_6C], 1000000h
0x1400086c0  mov     [rbp+0A0h+Source], rbx
0x1400086c4  mov     rax, gs:60h
0x1400086cd  test    dword ptr [rax+0BCh], 40000h
0x1400086d7  jz      loc_1400087FF
0x1400086dd  mov     rcx, [rsp+1A0h+Handle+8]; Handle
0x1400086e2  lea     r8, [rbp+0A0h+ObjectInformation]; ObjectInformation
0x1400086e6  xor     eax, eax
0x1400086e8  xor     r9d, r9d; ObjectInformationLength
0x1400086eb  mov     dword ptr [rbp+0A0h+ObjectInformation], eax
0x1400086ee  mov     edx, 1; ObjectInformationClass
0x1400086f3  mov     qword ptr [rbp+0A0h+ObjectInformation+8], rax
0x1400086f7  mov     [rsp+1A0h+ObjectInformationLength], eax
0x1400086fb  lea     rax, [rsp+1A0h+ObjectInformationLength]
0x140008700  mov     [rsp+1A0h+ReturnLength], rax; ReturnLength
0x140008705  call    cs:__imp_NtQueryObject
0x14000870b  cmp     eax, 0C0000004h
0x140008710  jnz     loc_1400087FF
0x140008716  mov     edx, [rsp+1A0h+ObjectInformationLength]
0x14000871a  mov     rax, [rbp+0A0h+Source]
0x14000871e  add     edx, 2
0x140008721  mov     [rsp+1A0h+ObjectInformationLength], edx
0x140008725  movzx   eax, word ptr [rax]
0x140008728  add     eax, edx
0x14000872a  xor     edx, edx; Flags
0x14000872c  mov     [rsp+1A0h+ObjectInformationLength], eax
0x140008730  mov     rcx, gs:60h
0x140008739  mov     r8d, eax; Size
0x14000873c  mov     rcx, [rcx+30h]; HeapHandle
0x140008740  call    cs:__imp_RtlAllocateHeap
0x140008746  mov     rsi, rax
0x140008749  test    rax, rax
0x14000874c  jz      loc_1400087FF
0x140008752  mov     r9d, [rsp+1A0h+ObjectInformationLength]; ObjectInformationLength
0x140008757  lea     rax, [rsp+1A0h+ObjectInformationLength]
0x14000875c  mov     rcx, [rsp+1A0h+Handle+8]; Handle
0x140008761  mov     r8, rsi; ObjectInformation
0x140008764  mov     edx, 1; ObjectInformationClass
0x140008769  mov     [rsp+1A0h+ReturnLength], rax; ReturnLength
0x14000876e  call    cs:__imp_NtQueryObject
0x140008774  test    eax, eax
0x140008776  js      short loc_1400087E7
0x140008778  movups  xmm0, xmmword ptr [rsi]
0x14000877b  mov     rax, [rbp+0A0h+Source]
0x14000877f  lea     rdx, asc_140026670; "\\"
0x140008786  movd    ecx, xmm0
0x14000878a  movups  xmmword ptr [rsp+1A0h+Destination.Length], xmm0
0x14000878f  add     cx, 2
0x140008793  add     cx, [rax]
0x140008796  mov     [rsp+1A0h+Destination.MaximumLength], cx
0x14000879b  lea     rcx, [rsp+1A0h+Destination]; Destination
0x1400087a0  call    cs:__imp_RtlAppendUnicodeToString
0x1400087a6  test    eax, eax
0x1400087a8  js      short loc_1400087E7
0x1400087aa  mov     rdx, [rbp+0A0h+Source]; Source
0x1400087ae  lea     rcx, [rsp+1A0h+Destination]; Destination
0x1400087b3  call    cs:__imp_RtlAppendUnicodeStringToString
0x1400087b9  test    eax, eax
0x1400087bb  js      short loc_1400087E7
0x1400087bd  mov     [rsp+1A0h+var_178], 0; ReturnLength
0x1400087c6  lea     rdx, [rsp+1A0h+Destination]; InputBuffer
0x1400087cb  xor     r9d, r9d; OutputBuffer
0x1400087ce  mov     dword ptr [rsp+1A0h+ReturnLength], 0; OutputBufferLength
0x1400087d6  mov     r8d, 10h; InputBufferLength
0x1400087dc  mov     ecx, 26h ; '&'; ControlCode
0x1400087e1  call    cs:__imp_NtSystemDebugControl
0x1400087e7  mov     rcx, gs:60h
0x1400087f0  mov     r8, rsi; BaseAddress
0x1400087f3  xor     edx, edx; Flags
0x1400087f5  mov     rcx, [rcx+30h]; HeapHandle
0x1400087f9  call    cs:__imp_RtlFreeHeap
0x1400087ff  mov     dword ptr [rsp+1A0h+var_178], 60h ; '`'; OpenOptions
0x140008807  lea     r9, [rbp+0A0h+IoStatusBlock]; IoStatusBlock
0x14000880b  lea     r8, [rsp+1A0h+Handle]; ObjectAttributes
0x140008810  mov     dword ptr [rsp+1A0h+ReturnLength], 5; ShareAccess
0x140008818  mov     edx, 120020h; DesiredAccess
0x14000881d  lea     rcx, [rsp+1A0h+FileHandle]; FileHandle
0x140008822  call    cs:__imp_NtOpenFile
0x140008828  test    eax, eax
0x14000882a  js      loc_1400088F4
0x140008830  mov     rdx, [rbp+0A0h+var_D0]
0x140008834  mov     qword ptr [rbp+0A0h+var_E0], rbx
0x140008838  mov     qword ptr [rbp+0A0h+var_C0], rbx
0x14000883c  test    rdx, rdx
0x14000883f  jz      short loc_140008856
0x140008841  movzx   ecx, word ptr [rdx+2]
0x140008845  movzx   r13d, cx
0x140008849  and     r13w, 8
0x14000884e  or      cx, 8
0x140008852  mov     [rdx+2], cx
0x140008856  mov     rcx, [rsp+1A0h+FileHandle]
0x14000885b  lea     rdx, [rbp+0A0h+var_A0]
0x14000885f  or      rcx, 1
0x140008863  call    cs:__imp_LdrVerifyImageMatchesChecksumEx
0x140008869  mov     esi, eax
0x14000886b  mov     rax, [rbp+0A0h+var_D0]
0x14000886f  test    rax, rax
0x140008872  jz      short loc_140008884
0x140008874  movzx   edx, word ptr [rax+2]
0x140008878  xor     dx, r13w
0x14000887c  and     dx, 8
0x140008880  xor     [rax+2], dx
0x140008884  test    esi, esi
0x140008886  jns     short loc_1400088D0
0x140008888  mov     [rsp+1A0h+var_170], 1
0x14000888d  cmp     esi, 0C0000428h
0x140008893  jnz     short loc_1400088C6
0x140008895  mov     rcx, [rsp+1A0h+FileHandle]
0x14000889a  lea     rdx, [rsp+1A0h+var_170]
0x14000889f  call    cs:__imp_RtlAppxIsFileOwnedByTrustedInstaller
0x1400088a5  test    eax, eax
0x1400088a7  js      short loc_1400088B0
0x1400088a9  cmp     [rsp+1A0h+var_170], 0
0x1400088ae  jz      short loc_1400088E9
0x1400088b0  lea     rdx, aVerificationOf; "Verification of a KnownDLL failed."
0x1400088b7  lea     rcx, [rbp+0A0h+DestinationString]; DestinationString
0x1400088bb  call    cs:__imp_RtlInitUnicodeString
0x1400088c1  jmp     loc_140008A45
0x1400088c6  cmp     esi, 0C0000035h
0x1400088cc  jz      short loc_1400088E9
0x1400088ce  jmp     short loc_1400088B0
0x1400088d0  mov     eax, 2000h
0x1400088d5  test    [rbp+0A0h+var_68], ax
0x1400088d9  jz      loc_140008A2F
0x1400088df  mov     rcx, [rbp+0A0h+var_88]; Handle
0x1400088e3  call    cs:__imp_NtClose
0x1400088e9  mov     rcx, [rsp+1A0h+FileHandle]; Handle
0x1400088ee  call    cs:__imp_NtClose
0x1400088f4  inc     edi
0x1400088f6  jmp     loc_1400085E1
0x1400088fb  mov     rcx, gs:60h
0x140008904  mov     r8, r12; BaseAddress
0x140008907  xor     edx, edx; Flags
0x140008909  mov     rcx, [rcx+30h]; HeapHandle
0x14000890d  call    cs:__imp_RtlFreeHeap
0x140008913  mov     rbx, qword ptr [rsp+1A0h+var_160]
0x140008918  lea     rax, [rsp+1A0h+var_160]
0x14000891d  xor     r14d, r14d
0x140008920  mov     [rsp+1A0h+BaseAddress], r14
0x140008925  mov     esi, r14d
0x140008928  mov     [rsp+1A0h+var_168], r14d
0x14000892d  cmp     rbx, rax
0x140008930  jz      loc_140008A8C
0x140008936  nop     word ptr [rax+rax+00000000h]
0x140008940  mov     rdi, rbx
0x140008943  mov     rbx, [rbx]
0x140008946  lea     rdx, [rdi+10h]
0x14000894a  call    SmpFindModuleInModuleList
0x14000894f  test    rax, rax
0x140008952  jz      short loc_14000895E
0x140008954  mov     rcx, rdi
0x140008957  call    SmpFreeSavedRegistryEntry
0x14000895c  jmp     short loc_140008960
0x14000895e  inc     esi
0x140008960  lea     rax, [rsp+1A0h+var_160]
0x140008965  cmp     rbx, rax
0x140008968  jnz     short loc_140008940
0x14000896a  mov     [rsp+1A0h+var_168], esi
0x14000896e  test    esi, esi
0x140008970  jz      loc_140008A8C
0x140008976  lea     r8, [rsp+1A0h+var_168]
0x14000897b  lea     rdx, [rsp+1A0h+BaseAddress]
0x140008980  lea     rcx, [rsp+1A0h+var_160]
0x140008985  call    SmpRandomizeDllList
  ... truncated ...
```
