# BiLoadHive

- ea: `0x18006abe4`
- end: `0x18006b01e`
- name: `BiLoadHive`
- size: `1082`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800650c8`

## callees

- `0x180002f50`
- `0x18006abe4`
- `0x18006b250`
- `0x18006b964`
- `0x18006c4c0`
- `0x18006c7bc`
- `0x18006ca08`
- `0x180086010`

## import_xrefs

- `ntdll!ZwClose` at `0x18006af9c`
- `ntdll!ZwClose` at `0x18006af9c`
- `ntdll!ZwLoadKey` at `0x18006aecf`
- `ntdll!ZwLoadKey` at `0x18006aecf`
- `ntdll!ZwUnloadKey` at `0x18006af57`
- `ntdll!ZwUnloadKey` at `0x18006af57`
- `ntdll!ZwOpenKey` at `0x18006af2d`
- `ntdll!ZwOpenKey` at `0x18006af2d`
- `ntdll!ZwQueryAttributesFile` at `0x18006ad21`
- `ntdll!ZwQueryAttributesFile` at `0x18006ad21`
- `ntdll!RtlInitUnicodeString` at `0x18006accb`
- `ntdll!RtlInitUnicodeString` at `0x18006ad94`
- `ntdll!RtlInitUnicodeString` at `0x18006addb`
- `ntdll!RtlInitUnicodeString` at `0x18006accb`
- `ntdll!RtlInitUnicodeString` at `0x18006ad94`
- `ntdll!RtlInitUnicodeString` at `0x18006addb`

## string_xrefs

- `0x18006ad4e`: `\Registry\Machine`
- `0x18006ad69`: `\Registry\Machine`
- `0x18006ae41`: `\Registry\Machine`
- `0x18006ad70`: `Failed open key %ws. Status: %x`
- `0x18006af7a`: `Failed open newly loaded key %ws. Flags: 0x%x Status: %x`

## pseudocode

```c
__int64 __fastcall BiLoadHive(PCWSTR SourceString, __int64 a2, void **a3)
{
  unsigned int i; // esi
  HANDLE v5; // rdi
  const WCHAR *v6; // r13
  int v7; // eax
  int v8; // ebx
  NTSTATUS v9; // eax
  __int64 v10; // rcx
  __int64 v12; // [rsp+20h] [rbp-168h]
  __int64 v13; // [rsp+28h] [rbp-160h]
  __int64 v14; // [rsp+30h] [rbp-158h]
  HANDLE Handle; // [rsp+38h] [rbp-150h] BYREF
  __int64 v16; // [rsp+40h] [rbp-148h] BYREF
  __int64 v17; // [rsp+48h] [rbp-140h]
  PHANDLE KeyHandle; // [rsp+50h] [rbp-138h]
  struct _OBJECT_ATTRIBUTES KeyObjectAttributes; // [rsp+58h] [rbp-130h] BYREF
  PCWSTR v20; // [rsp+88h] [rbp-100h]
  __int64 v21; // [rsp+90h] [rbp-F8h]
  void **v22; // [rsp+98h] [rbp-F0h]
  struct _OBJECT_ATTRIBUTES FileObjectAttributes; // [rsp+A0h] [rbp-E8h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+D0h] [rbp-B8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+100h] [rbp-88h] BYREF
  struct _UNICODE_STRING v26; // [rsp+110h] [rbp-78h] BYREF
  struct _UNICODE_STRING v27; // [rsp+120h] [rbp-68h] BYREF
  struct _FILE_BASIC_INFORMATION FileInformation; // [rsp+130h] [rbp-58h] BYREF

  KeyHandle = a3;
  v17 = a2;
  v20 = SourceString;
  v21 = a2;
  v22 = a3;
  memset(&FileObjectAttributes, 0, 44);
  memset(&KeyObjectAttributes, 0, 44);
  v16 = 0;
  v27 = 0;
  v26 = 0;
  for ( i = 0; ; ++i )
  {
    v5 = 0;
    Handle = 0;
    memset(&ObjectAttributes, 0, 44);
    memset(&FileInformation, 0, sizeof(FileInformation));
    DestinationString = 0;
    v6 = (const WCHAR *)(a2 + 12);
    RtlInitUnicodeString(&DestinationString, (PCWSTR)(a2 + 12));
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 64;
    ObjectAttributes.ObjectName = &DestinationString;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    if ( ZwQueryAttributesFile(&ObjectAttributes, &FileInformation) < 0 || (FileInformation.FileAttributes & 0x10) != 0 )
    {
      v8 = -1073741809;
    }
    else
    {
      v7 = BiOpenKeyNonBcd(0, L"\\Registry\\Machine", 983103, &Handle);
      v8 = v7;
      if ( v7 >= 0 )
      {
        RtlInitUnicodeString(&v26, SourceString);
        KeyObjectAttributes.Length = 48;
        v5 = Handle;
        KeyObjectAttributes.RootDirectory = Handle;
        KeyObjectAttributes.Attributes = 64;
        KeyObjectAttributes.ObjectName = &v26;
        *(_OWORD *)&KeyObjectAttributes.SecurityDescriptor = 0;
        RtlInitUnicodeString(&v27, v6);
        FileObjectAttributes.Length = 48;
        FileObjectAttributes.RootDirectory = 0;
        FileObjectAttributes.Attributes = 64;
        FileObjectAttributes.ObjectName = &v27;
        *(_OWORD *)&FileObjectAttributes.SecurityDescriptor = 0;
        v9 = BiAcquirePrivilege(0x12u, (__int64)&v16);
        v8 = v9;
        if ( v9 >= 0 )
        {
          Handle = 0;
          v8 = BiLookupNtdllProcedureAddress("ZwLoadKey2", &Handle);
          if ( v8 >= 0 )
          {
            v8 = ((__int64 (__fastcall *)(struct _OBJECT_ATTRIBUTES *, struct _OBJECT_ATTRIBUTES *, __int64))Handle)(
                   &KeyObjectAttributes,
                   &FileObjectAttributes,
                   6016);
            if ( v8 < 0 )
              v8 = ((__int64 (__fastcall *)(struct _OBJECT_ATTRIBUTES *, struct _OBJECT_ATTRIBUTES *, __int64))Handle)(
                     &KeyObjectAttributes,
                     &FileObjectAttributes,
                     4992);
          }
          if ( v8 < 0 )
            v8 = ZwLoadKey(&KeyObjectAttributes, &FileObjectAttributes);
          BiReleasePrivilege(&v16);
          if ( v8 >= 0 )
          {
            v8 = ZwOpenKey(KeyHandle, 0x20019u, &KeyObjectAttributes);
            if ( v8 < 0 )
            {
              BiAcquirePrivilege(0x11u, (__int64)&v16);
              ZwUnloadKey(&KeyObjectAttributes);
              BiReleasePrivilege(&v16);
              LODWORD(v12) = v8;
              BiLogMessage(4, L"Failed open newly loaded key %ws. Flags: 0x%x Status: %x", SourceString, 64, v12);
            }
          }
          else
          {
            LODWORD(v14) = v8;
            v10 = 2;
            if ( v8 != -1073741790 )
              v10 = 4;
            LODWORD(v13) = v8;
            BiLogMessage(v10, L"Failed load key %ws. Flags: 0x%x File: %s Status: %x", SourceString, 64, v6, v13, v14);
          }
        }
        else
        {
          BiLogMessage(
            4,
            L"Failed to acquire permissions to load hive. Status: %x",
            L"\\Registry\\Machine",
            (unsigned int)v9);
        }
      }
      else
      {
        BiLogMessage(4, L"Failed open key %ws. Status: %x", L"\\Registry\\Machine", (unsigned int)v7);
        v5 = Handle;
      }
    }
    if ( v5 )
      ZwClose(v5);
    if ( v8 != -1073741443 )
      break;
    __debugbreak();
    a2 = v17;
    if ( i >= 5 )
      break;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18006abe4  mov     r11, rsp
0x18006abe7  mov     [r11+20h], rbx
0x18006abeb  push    rsi
0x18006abec  push    rdi
0x18006abed  push    r12
0x18006abef  push    r13
0x18006abf1  push    r14
0x18006abf3  sub     rsp, 160h
0x18006abfa  mov     rax, cs:__security_cookie
0x18006ac01  xor     rax, rsp
0x18006ac04  mov     [rsp+188h+var_30], rax
0x18006ac0c  mov     rax, r8
0x18006ac0f  mov     [rsp+188h+KeyHandle], rax
0x18006ac14  mov     [rsp+188h+var_140], rdx
0x18006ac19  mov     r12, rcx
0x18006ac1c  mov     [rsp+188h+var_100], rcx
0x18006ac24  mov     [rsp+188h+var_F8], rdx
0x18006ac2c  mov     [rsp+188h+var_F0], rax
0x18006ac34  xor     eax, eax
0x18006ac36  xorps   xmm0, xmm0
0x18006ac39  movups  xmmword ptr [rsp+188h+FileObjectAttributes.Length], xmm0
0x18006ac41  movups  xmmword ptr [rsp+188h+FileObjectAttributes.ObjectName], xmm0
0x18006ac49  movups  xmmword ptr [rsp+188h+FileObjectAttributes+1Ch], xmm0
0x18006ac51  movups  xmmword ptr [rsp+188h+KeyObjectAttributes.Length], xmm0
0x18006ac56  movups  xmmword ptr [rsp+188h+KeyObjectAttributes.ObjectName], xmm0
0x18006ac5b  movups  xmmword ptr [rsp+188h+KeyObjectAttributes+1Ch], xmm0
0x18006ac60  mov     [rsp+188h+var_148], rax
0x18006ac65  movups  xmmword ptr [r11-68h], xmm0
0x18006ac6a  xorps   xmm1, xmm1
0x18006ac6d  movups  xmmword ptr [r11-78h], xmm1
0x18006ac72  xor     esi, esi
0x18006ac74  lea     r14d, [rax+4]
0x18006ac78  xor     edi, edi
0x18006ac7a  mov     [rsp+188h+Handle], rdi
0x18006ac7f  xor     eax, eax
0x18006ac81  xorps   xmm0, xmm0
0x18006ac84  movups  xmmword ptr [rsp+188h+ObjectAttributes.Length], xmm0
0x18006ac8c  movups  xmmword ptr [rsp+188h+ObjectAttributes.ObjectName], xmm0
0x18006ac94  movups  xmmword ptr [rsp+188h+ObjectAttributes+1Ch], xmm0
0x18006ac9c  movups  xmmword ptr [rsp+188h+FileInformation.CreationTime], xmm0
0x18006aca4  movups  xmmword ptr [rsp+188h+FileInformation.LastWriteTime], xmm0
0x18006acac  mov     qword ptr [rsp+188h+FileInformation.FileAttributes], rax
0x18006acb4  movups  xmmword ptr [rsp+188h+DestinationString.Length], xmm0
0x18006acbc  lea     r13, [rdx+0Ch]
0x18006acc0  mov     rdx, r13; SourceString
0x18006acc3  lea     rcx, [rsp+188h+DestinationString]; DestinationString
0x18006accb  call    cs:__imp_RtlInitUnicodeString
0x18006acd2  nop     dword ptr [rax+rax+00h]
0x18006acd7  mov     [rsp+188h+ObjectAttributes.Length], 30h ; '0'
0x18006ace2  mov     [rsp+188h+ObjectAttributes.RootDirectory], rdi
0x18006acea  mov     [rsp+188h+ObjectAttributes.Attributes], 40h ; '@'
0x18006acf5  lea     rax, [rsp+188h+DestinationString]
0x18006acfd  mov     [rsp+188h+ObjectAttributes.ObjectName], rax
0x18006ad05  xorps   xmm0, xmm0
0x18006ad08  movdqu  xmmword ptr [rsp+188h+ObjectAttributes.SecurityDescriptor], xmm0
0x18006ad11  lea     rdx, [rsp+188h+FileInformation]; FileInformation
0x18006ad19  lea     rcx, [rsp+188h+ObjectAttributes]; ObjectAttributes
0x18006ad21  call    cs:__imp_ZwQueryAttributesFile
0x18006ad28  nop     dword ptr [rax+rax+00h]
0x18006ad2d  test    eax, eax
0x18006ad2f  js      loc_18006AF8B
0x18006ad35  test    byte ptr [rsp+188h+FileInformation.FileAttributes], 10h
0x18006ad3d  jnz     loc_18006AF8B
0x18006ad43  lea     r9, [rsp+188h+Handle]
0x18006ad48  mov     r8d, 0F003Fh
0x18006ad4e  lea     rdx, aRegistryMachin_1; "\\Registry\\Machine"
0x18006ad55  xor     ecx, ecx
0x18006ad57  call    BiOpenKeyNonBcd
0x18006ad5c  mov     ebx, eax
0x18006ad5e  mov     dword ptr [rsp+188h+var_158], eax
0x18006ad62  test    eax, eax
0x18006ad64  jns     short loc_18006AD89
0x18006ad66  mov     r9d, eax
0x18006ad69  lea     r8, aRegistryMachin_1; "\\Registry\\Machine"
0x18006ad70  lea     rdx, aFailedOpenKeyW; "Failed open key %ws. Status: %x"
0x18006ad77  mov     ecx, r14d
0x18006ad7a  call    BiLogMessage
0x18006ad7f  mov     rdi, [rsp+188h+Handle]
0x18006ad84  jmp     loc_18006AF94
0x18006ad89  mov     rdx, r12; SourceString
0x18006ad8c  lea     rcx, [rsp+188h+var_78]; DestinationString
0x18006ad94  call    cs:__imp_RtlInitUnicodeString
0x18006ad9b  nop     dword ptr [rax+rax+00h]
0x18006ada0  mov     [rsp+188h+KeyObjectAttributes.Length], 30h ; '0'
0x18006ada8  mov     rdi, [rsp+188h+Handle]
0x18006adad  mov     [rsp+188h+KeyObjectAttributes.RootDirectory], rdi
0x18006adb2  mov     [rsp+188h+KeyObjectAttributes.Attributes], 40h ; '@'
0x18006adba  lea     rax, [rsp+188h+var_78]
0x18006adc2  mov     [rsp+188h+KeyObjectAttributes.ObjectName], rax
0x18006adc7  xorps   xmm0, xmm0
0x18006adca  movdqu  xmmword ptr [rsp+188h+KeyObjectAttributes.SecurityDescriptor], xmm0
0x18006add0  mov     rdx, r13; SourceString
0x18006add3  lea     rcx, [rsp+188h+var_68]; DestinationString
0x18006addb  call    cs:__imp_RtlInitUnicodeString
0x18006ade2  nop     dword ptr [rax+rax+00h]
0x18006ade7  mov     [rsp+188h+FileObjectAttributes.Length], 30h ; '0'
0x18006adf2  mov     [rsp+188h+FileObjectAttributes.RootDirectory], 0
0x18006adfe  mov     [rsp+188h+FileObjectAttributes.Attributes], 40h ; '@'
0x18006ae09  lea     rax, [rsp+188h+var_68]
0x18006ae11  mov     [rsp+188h+FileObjectAttributes.ObjectName], rax
0x18006ae19  xorps   xmm0, xmm0
0x18006ae1c  movdqu  xmmword ptr [rsp+188h+FileObjectAttributes.SecurityDescriptor], xmm0
0x18006ae25  lea     rdx, [rsp+188h+var_148]
0x18006ae2a  mov     ecx, 12h
0x18006ae2f  call    BiAcquirePrivilege
0x18006ae34  mov     ebx, eax
0x18006ae36  mov     dword ptr [rsp+188h+var_158], eax
0x18006ae3a  test    eax, eax
0x18006ae3c  jns     short loc_18006AE5C
0x18006ae3e  mov     r9d, eax
0x18006ae41  lea     r8, aRegistryMachin_1; "\\Registry\\Machine"
0x18006ae48  lea     rdx, aFailedToAcquir; "Failed to acquire permissions to load h"...
0x18006ae4f  mov     ecx, r14d
0x18006ae52  call    BiLogMessage
0x18006ae57  jmp     loc_18006AF94
0x18006ae5c  mov     [rsp+188h+Handle], 0
0x18006ae65  lea     rdx, [rsp+188h+Handle]
0x18006ae6a  lea     rcx, aZwloadkey2; "ZwLoadKey2"
0x18006ae71  call    BiLookupNtdllProcedureAddress
0x18006ae76  mov     ebx, eax
0x18006ae78  test    eax, eax
0x18006ae7a  js      short loc_18006AEBE
0x18006ae7c  mov     r8d, 1780h
0x18006ae82  lea     rdx, [rsp+188h+FileObjectAttributes]
0x18006ae8a  lea     rcx, [rsp+188h+KeyObjectAttributes]
0x18006ae8f  mov     rax, [rsp+188h+Handle]
0x18006ae94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ae99  mov     ebx, eax
0x18006ae9b  test    eax, eax
0x18006ae9d  jns     short loc_18006AEBE
0x18006ae9f  mov     r8d, 1380h
0x18006aea5  lea     rdx, [rsp+188h+FileObjectAttributes]
0x18006aead  lea     rcx, [rsp+188h+KeyObjectAttributes]
0x18006aeb2  mov     rax, [rsp+188h+Handle]
0x18006aeb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006aebc  mov     ebx, eax
0x18006aebe  test    ebx, ebx
0x18006aec0  jns     short loc_18006AEDD
0x18006aec2  lea     rdx, [rsp+188h+FileObjectAttributes]; FileObjectAttributes
0x18006aeca  lea     rcx, [rsp+188h+KeyObjectAttributes]; KeyObjectAttributes
0x18006aecf  call    cs:__imp_ZwLoadKey
0x18006aed6  nop     dword ptr [rax+rax+00h]
0x18006aedb  mov     ebx, eax
0x18006aedd  lea     rcx, [rsp+188h+var_148]
0x18006aee2  call    BiReleasePrivilege
0x18006aee7  test    ebx, ebx
0x18006aee9  jns     short loc_18006AF1E
0x18006aeeb  mov     dword ptr [rsp+188h+var_158], ebx
0x18006aeef  mov     ecx, 2
0x18006aef4  cmp     ebx, 0C0000022h
0x18006aefa  cmovnz  ecx, r14d
0x18006aefe  mov     dword ptr [rsp+188h+var_160], ebx
0x18006af02  mov     [rsp+188h+var_168], r13
0x18006af07  mov     r9d, 40h ; '@'
0x18006af0d  mov     r8, r12
0x18006af10  lea     rdx, aFailedLoadKeyW; "Failed load key %ws. Flags: 0x%x File: "...
0x18006af17  call    BiLogMessage
0x18006af1c  jmp     short loc_18006AF94
0x18006af1e  lea     r8, [rsp+188h+KeyObjectAttributes]; ObjectAttributes
0x18006af23  mov     edx, 20019h; DesiredAccess
0x18006af28  mov     rcx, [rsp+188h+KeyHandle]; KeyHandle
0x18006af2d  call    cs:__imp_ZwOpenKey
0x18006af34  nop     dword ptr [rax+rax+00h]
0x18006af39  mov     ebx, eax
0x18006af3b  mov     dword ptr [rsp+188h+var_158], eax
0x18006af3f  test    eax, eax
0x18006af41  jns     short loc_18006AF94
0x18006af43  lea     rdx, [rsp+188h+var_148]
0x18006af48  mov     ecx, 11h
0x18006af4d  call    BiAcquirePrivilege
0x18006af52  lea     rcx, [rsp+188h+KeyObjectAttributes]; KeyObjectAttributes
0x18006af57  call    cs:__imp_ZwUnloadKey
0x18006af5e  nop     dword ptr [rax+rax+00h]
0x18006af63  lea     rcx, [rsp+188h+var_148]
0x18006af68  call    BiReleasePrivilege
0x18006af6d  mov     dword ptr [rsp+188h+var_168], ebx
0x18006af71  mov     r9d, 40h ; '@'
0x18006af77  mov     r8, r12
0x18006af7a  lea     rdx, aFailedOpenNewl; "Failed open newly loaded key %ws. Flags"...
0x18006af81  mov     ecx, r14d
0x18006af84  call    BiLogMessage
0x18006af89  jmp     short loc_18006AF94
0x18006af8b  mov     ebx, 0C000000Fh
0x18006af90  mov     dword ptr [rsp+188h+var_158], ebx
0x18006af94  test    rdi, rdi
0x18006af97  jz      short loc_18006AFA8
0x18006af99  mov     rcx, rdi; Handle
0x18006af9c  call    cs:__imp_ZwClose
0x18006afa3  nop     dword ptr [rax+rax+00h]
0x18006afa8  cmp     ebx, 0C000017Dh
0x18006afae  jnz     short loc_18006AFF3
0x18006afb0  int     3; Trap to Debugger
0x18006afb1  mov     rdx, [rsp+188h+var_140]
0x18006afb6  jmp     short loc_18006AFE7
0x18006afb8  mov     esi, 5
0x18006afbd  lea     r14d, [rsi-1]
0x18006afc1  mov     ebx, dword ptr [rsp+188h+var_158]
0x18006afc5  mov     r12, [rsp+188h+var_100]
0x18006afcd  mov     rdx, [rsp+188h+var_F8]
0x18006afd5  mov     [rsp+188h+var_140], rdx
0x18006afda  mov     rax, [rsp+188h+var_F0]
0x18006afe2  mov     [rsp+188h+KeyHandle], rax
0x18006afe7  cmp     esi, 5
0x18006afea  jnb     short loc_18006AFF3
0x18006afec  inc     esi
0x18006afee  jmp     loc_18006AC78
0x18006aff3  mov     eax, ebx
0x18006aff5  mov     rcx, [rsp+188h+var_30]
0x18006affd  xor     rcx, rsp; StackCookie
0x18006b000  call    __security_check_cookie
0x18006b005  mov     rbx, [rsp+188h+arg_18]
0x18006b00d  add     rsp, 160h
0x18006b014  pop     r14
0x18006b016  pop     r13
0x18006b018  pop     r12
0x18006b01a  pop     rdi
0x18006b01b  pop     rsi
0x18006b01c  retn
```
