# InitializeSam(void)

- ea: `0x18003f850`
- end: `0x18003facd`
- name: `?InitializeSam@@YAJXZ`
- size: `637`
- prototype: `NTSTATUS(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180041430`

## callees

- `0x18003f850`
- `0x180040e6c`
- `0x1800bb788`

## import_xrefs

- `ntdll!RtlApplyRXactNoFlush` at `0x18003fab6`
- `ntdll!RtlApplyRXactNoFlush` at `0x18003fab6`
- `ntdll!RtlStartRXact` at `0x18003f9b0`
- `ntdll!RtlStartRXact` at `0x18003f9b0`
- `ntdll!RtlInitializeRXact` at `0x18003f984`
- `ntdll!RtlInitializeRXact` at `0x18003f984`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x18003f929`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x18003f929`
- `ntdll!RtlpNtCreateKey` at `0x18003f90d`
- `ntdll!RtlpNtCreateKey` at `0x18003f90d`
- `ntdll!RtlFreeHeap` at `0x18003f94f`
- `ntdll!RtlFreeHeap` at `0x18003fa79`
- `ntdll!RtlFreeHeap` at `0x18003f94f`
- `ntdll!RtlFreeHeap` at `0x18003fa79`
- `ntdll!RtlAllocateHeap` at `0x18003f9d7`
- `ntdll!RtlAllocateHeap` at `0x18003f9d7`
- `ntdll!RtlAddAttributeActionToRXact` at `0x18003fa5b`
- `ntdll!RtlAddAttributeActionToRXact` at `0x18003fa5b`
- `ntdll!RtlAddActionToRXact` at `0x18003faa3`
- `ntdll!RtlAddActionToRXact` at `0x18003faa3`
- `ntdll!NtClose` at `0x18003f970`
- `ntdll!NtClose` at `0x18003f970`
- `ntdll!RtlInitUnicodeString` at `0x18003f8b1`
- `ntdll!RtlInitUnicodeString` at `0x18003fa23`
- `ntdll!RtlInitUnicodeString` at `0x18003f8b1`
- `ntdll!RtlInitUnicodeString` at `0x18003fa23`

## pseudocode

```c
NTSTATUS InitializeSam(void)
{
  NTSTATUS result; // eax
  NTSTATUS started; // eax
  struct _PEB *v2; // rcx
  ULONG ValueDataSize; // edi
  char *Heap; // rax
  void *ValueData; // rbx
  NTSTATUS v6; // eax
  struct _PEB *v7; // rcx
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-29h] BYREF
  _OWORD SecurityDescriptor[2]; // [rsp+50h] [rbp-19h] BYREF
  __int64 v10; // [rsp+70h] [rbp+7h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp+Fh] BYREF
  unsigned __int8 DaclPresent; // [rsp+D0h] [rbp+67h] BYREF
  ULONG Disposition; // [rsp+D8h] [rbp+6Fh] BYREF
  PACL Dacl; // [rsp+E0h] [rbp+77h] BYREF

  Disposition = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v10 = 0;
  DaclPresent = 0;
  Dacl = 0;
  DestinationString = 0;
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  result = SampCreateDatabaseProtection(SecurityDescriptor);
  dword_1800EF708 = result;
  if ( result >= 0 )
  {
    RtlInitUnicodeString(&DestinationString, L"SAM");
    ObjectAttributes.RootDirectory = qword_1800F0958;
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.Attributes = 64;
    ObjectAttributes.SecurityDescriptor = SecurityDescriptor;
    ObjectAttributes.SecurityQualityOfService = 0;
    dword_1800EF708 = RtlpNtCreateKey(&Handle, 0x2001Fu, &ObjectAttributes, 0, 0, &Disposition);
    result = RtlGetDaclSecurityDescriptor(SecurityDescriptor, &DaclPresent, &Dacl, &DaclPresent);
    dword_1800EF708 = result;
    if ( Dacl )
    {
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Dacl);
      result = dword_1800EF708;
    }
    if ( result >= 0 )
    {
      if ( Disposition == 1 )
      {
        result = RtlInitializeRXact(Handle, 0, &P);
        dword_1800EF708 = result;
        if ( result == 1073741828 )
        {
          started = RtlStartRXact(P);
          v2 = NtCurrentPeb();
          ValueDataSize = Size + 16;
          dword_1800EF708 = started;
          Heap = (char *)RtlAllocateHeap(v2->ProcessHeap, 0, (unsigned int)(Size + 16));
          ValueData = Heap;
          if ( !Heap )
            dword_1800EF708 = -1073741670;
          *(_QWORD *)Heap = 65540;
          *((_DWORD *)Heap + 2) = Size;
          *((_DWORD *)Heap + 3) = 65539;
          memcpy_0(Heap + 16, qword_1800F07D8, (unsigned int)Size);
          RtlInitUnicodeString(&DestinationString, 0);
          v6 = RtlAddAttributeActionToRXact(
                 P,
                 2u,
                 &DestinationString,
                 (HANDLE)0xFFFFFFFFFFFFFFFFLL,
                 &SampCombinedAttributeName,
                 3u,
                 ValueData,
                 ValueDataSize);
          v7 = NtCurrentPeb();
          dword_1800EF708 = v6;
          RtlFreeHeap(v7->ProcessHeap, 0, ValueData);
          dword_1800EF708 = RtlAddActionToRXact(P, 2u, &stru_1800EF810, 0, 0, 0);
          result = RtlApplyRXactNoFlush(P);
        }
        else
        {
          if ( result )
            return result;
          result = -1073741540;
        }
      }
      else
      {
        result = NtClose(Handle);
      }
      dword_1800EF708 = result;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18003f850  push    rbp
0x18003f852  push    rbx
0x18003f853  push    rdi
0x18003f854  lea     rbp, [rsp-47h]
0x18003f859  sub     rsp, 0B0h
0x18003f860  xorps   xmm0, xmm0
0x18003f863  mov     [rbp+57h+arg_8], 0
0x18003f86a  xor     eax, eax
0x18003f86c  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x18003f870  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18003f874  mov     [rbp+57h+var_50], rax
0x18003f878  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18003f87c  mov     [rbp+57h+DaclPresent], al
0x18003f87f  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18003f883  mov     [rbp+57h+Dacl], rax
0x18003f887  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18003f88b  movups  [rbp+57h+SecurityDescriptor], xmm0
0x18003f88f  movups  [rbp+57h+var_60], xmm0
0x18003f893  call    ?SampCreateDatabaseProtection@@YAJPEAU_SECURITY_DESCRIPTOR@@@Z; SampCreateDatabaseProtection(_SECURITY_DESCRIPTOR *)
0x18003f898  mov     cs:dword_1800EF708, eax
0x18003f89e  test    eax, eax
0x18003f8a0  js      loc_18003FAC2
0x18003f8a6  lea     rdx, aSam; "SAM"
0x18003f8ad  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18003f8b1  call    cs:__imp_RtlInitUnicodeString
0x18003f8b7  mov     rax, cs:qword_1800F0958
0x18003f8be  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18003f8c2  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x18003f8c6  lea     rcx, Handle; KeyHandle
0x18003f8cd  lea     rax, [rbp+57h+DestinationString]
0x18003f8d1  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18003f8d8  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18003f8dc  xor     r9d, r9d; TitleIndex
0x18003f8df  lea     rax, [rbp+57h+SecurityDescriptor]
0x18003f8e3  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x18003f8ea  mov     [rbp+57h+ObjectAttributes.SecurityDescriptor], rax
0x18003f8ee  mov     edx, 2001Fh; DesiredAccess
0x18003f8f3  lea     rax, [rbp+57h+arg_8]
0x18003f8f7  mov     [rbp+57h+ObjectAttributes.SecurityQualityOfService], 0
0x18003f8ff  mov     [rsp+0C0h+Disposition], rax; Disposition
0x18003f904  mov     [rsp+0C0h+Class], 0; Class
0x18003f90d  call    cs:__imp_RtlpNtCreateKey
0x18003f913  lea     r9, [rbp+57h+DaclPresent]; DaclDefaulted
0x18003f917  mov     cs:dword_1800EF708, eax
0x18003f91d  lea     r8, [rbp+57h+Dacl]; Dacl
0x18003f921  lea     rdx, [rbp+57h+DaclPresent]; DaclPresent
0x18003f925  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x18003f929  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x18003f92f  cmp     [rbp+57h+Dacl], 0
0x18003f934  mov     cs:dword_1800EF708, eax
0x18003f93a  jz      short loc_18003F95B
0x18003f93c  mov     rcx, gs:60h
0x18003f945  xor     edx, edx; Flags
0x18003f947  mov     r8, [rbp+57h+Dacl]; P
0x18003f94b  mov     rcx, [rcx+30h]; HeapHandle
0x18003f94f  call    cs:__imp_RtlFreeHeap
0x18003f955  mov     eax, cs:dword_1800EF708
0x18003f95b  test    eax, eax
0x18003f95d  js      loc_18003FAC2
0x18003f963  cmp     [rbp+57h+arg_8], 1
0x18003f967  mov     rcx, cs:Handle; RootDirectory
0x18003f96e  jz      short loc_18003F97B
0x18003f970  call    cs:__imp_NtClose
0x18003f976  jmp     loc_18003FABC
0x18003f97b  lea     r8, P; OutContext
0x18003f982  xor     edx, edx; Commit
0x18003f984  call    cs:__imp_RtlInitializeRXact
0x18003f98a  mov     cs:dword_1800EF708, eax
0x18003f990  cmp     eax, 40000004h
0x18003f995  jz      short loc_18003F9A9
0x18003f997  test    eax, eax
0x18003f999  jnz     loc_18003FAC2
0x18003f99f  mov     eax, 0C000011Ch
0x18003f9a4  jmp     loc_18003FABC
0x18003f9a9  mov     rcx, cs:P; Context
0x18003f9b0  call    cs:__imp_RtlStartRXact
0x18003f9b6  mov     rcx, gs:60h
0x18003f9bf  xor     edx, edx; Flags
0x18003f9c1  mov     edi, cs:Size
0x18003f9c7  add     edi, 10h
0x18003f9ca  mov     cs:dword_1800EF708, eax
0x18003f9d0  mov     r8d, edi; Size
0x18003f9d3  mov     rcx, [rcx+30h]; HeapHandle
0x18003f9d7  call    cs:__imp_RtlAllocateHeap
0x18003f9dd  mov     rbx, rax
0x18003f9e0  test    rax, rax
0x18003f9e3  jnz     short loc_18003F9EF
0x18003f9e5  mov     cs:dword_1800EF708, 0C000009Ah
0x18003f9ef  mov     qword ptr [rax], 10004h
0x18003f9f6  mov     ecx, cs:Size
0x18003f9fc  mov     [rax+8], ecx
0x18003f9ff  lea     rcx, [rax+10h]; void *
0x18003fa03  mov     dword ptr [rax+0Ch], 10003h
0x18003fa0a  mov     r8d, cs:Size; Size
0x18003fa11  mov     rdx, cs:qword_1800F07D8; Src
0x18003fa18  call    memcpy_0
0x18003fa1d  xor     edx, edx; SourceString
0x18003fa1f  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18003fa23  call    cs:__imp_RtlInitUnicodeString
0x18003fa29  mov     rcx, cs:P; Context
0x18003fa30  lea     rax, ?SampCombinedAttributeName@@3U_UNICODE_STRING@@A; _UNICODE_STRING SampCombinedAttributeName
0x18003fa37  mov     [rsp+0C0h+ValueDataSize], edi; ValueDataSize
0x18003fa3b  lea     r8, [rbp+57h+DestinationString]; KeyName
0x18003fa3f  or      r9, 0FFFFFFFFFFFFFFFFh; KeyHandle
0x18003fa43  mov     [rsp+0C0h+ValueData], rbx; ValueData
0x18003fa48  mov     dword ptr [rsp+0C0h+Disposition], 3; ValueType
0x18003fa50  mov     [rsp+0C0h+Class], rax; ValueName
0x18003fa55  lea     edi, [r9+3]
0x18003fa59  mov     edx, edi; ActionType
0x18003fa5b  call    cs:__imp_RtlAddAttributeActionToRXact
0x18003fa61  mov     rcx, gs:60h
0x18003fa6a  mov     r8, rbx; P
0x18003fa6d  xor     edx, edx; Flags
0x18003fa6f  mov     cs:dword_1800EF708, eax
0x18003fa75  mov     rcx, [rcx+30h]; HeapHandle
0x18003fa79  call    cs:__imp_RtlFreeHeap
0x18003fa7f  mov     rcx, cs:P; Context
0x18003fa86  lea     r8, stru_1800EF810; KeyName
0x18003fa8d  xor     r9d, r9d; ValueType
0x18003fa90  mov     dword ptr [rsp+0C0h+Disposition], 0; ValueDataSize
0x18003fa98  mov     edx, edi; ActionType
0x18003fa9a  mov     [rsp+0C0h+Class], 0; ValueData
0x18003faa3  call    cs:__imp_RtlAddActionToRXact
0x18003faa9  mov     rcx, cs:P; Context
0x18003fab0  mov     cs:dword_1800EF708, eax
0x18003fab6  call    cs:__imp_RtlApplyRXactNoFlush
0x18003fabc  mov     cs:dword_1800EF708, eax
0x18003fac2  add     rsp, 0B0h
0x18003fac9  pop     rdi
0x18003faca  pop     rbx
0x18003facb  pop     rbp
0x18003facc  retn
```
