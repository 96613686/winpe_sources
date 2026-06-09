# SclRegProcessUpgradeRegistryOnline

- ea: `0x18000b90c`
- end: `0x18000bc61`
- name: `SclRegProcessUpgradeRegistryOnline`
- size: `853`
- prototype: `__int64 __fastcall(__int64, char)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800065f8`

## callees

- `0x180007cac`
- `0x18000a524`
- `0x18000b90c`
- `0x18000c4b4`
- `0x18000c73c`
- `0x18000d620`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18000bc44`
- `ntdll!RtlFreeHeap` at `0x18000bc44`

## string_xrefs

- `0x18000b959`: `SECURITY`
- `0x18000bb7f`: `SECURITY`
- `0x18000b994`: `Deleted SECURITY hive contents in target image Status:0x%x`
- `0x18000b977`: `SclRegProcessUpgradeRegistryOnline`
- `0x18000b9da`: `Deleted SAM hive contents in target image Status:0x%x`
- `0x18000ba00`: `Migrating SAM registry content`
- `0x18000baf7`: `Migrating SECURITY registry content`
- `0x18000bb5f`: `(%lx): Failed to create the SECURITY root descriptor.`

## pseudocode

```c
__int64 __fastcall SclRegProcessUpgradeRegistryOnline(__int64 a1, char a2)
{
  int OnlineOSVolumeNtPath; // ebx
  int v5; // eax
  __int64 v6; // rdi
  int DatabaseProtection; // eax
  _OWORD *v8; // rcx
  __int64 v10; // [rsp+30h] [rbp-40h]
  __int64 v11; // [rsp+30h] [rbp-40h]
  PVOID P; // [rsp+40h] [rbp-30h] BYREF
  _OWORD SecurityDescriptor[2]; // [rsp+48h] [rbp-28h] BYREF
  __int64 v14; // [rsp+68h] [rbp-8h]
  unsigned int v15; // [rsp+B0h] [rbp+40h] BYREF
  unsigned int v16; // [rsp+B8h] [rbp+48h] BYREF

  P = 0;
  v15 = 0;
  v16 = 0;
  OnlineOSVolumeNtPath = SclGetOnlineOSVolumeNtPath(&P);
  if ( OnlineOSVolumeNtPath >= 0 )
  {
    v5 = SclpWipeHive(a1, (__int64)L"SECURITY", (wchar_t *)L"SAM");
    OnlineOSVolumeNtPath = v5;
    v6 = a1 + 1152;
    if ( !a1 )
      v6 = 0;
    SclLogGenericMessage(
      v6,
      1,
      (int)SclEvent_Generic_Info,
      2933,
      (__int64)"SclRegProcessUpgradeRegistryOnline",
      "Deleted SECURITY hive contents in target image Status:0x%x",
      v5);
    if ( OnlineOSVolumeNtPath >= 0 )
    {
      OnlineOSVolumeNtPath = SclpWipeHive(a1, (__int64)L"SAM", 0);
      SclLogGenericMessage(
        v6,
        1,
        (int)SclEvent_Generic_Info,
        2941,
        (__int64)"SclRegProcessUpgradeRegistryOnline",
        "Deleted SAM hive contents in target image Status:0x%x",
        OnlineOSVolumeNtPath);
      if ( OnlineOSVolumeNtPath >= 0 )
      {
        v15 = 0;
        v16 = 0;
        SclLogGenericMessage(
          v6,
          1,
          (int)SclEvent_Generic_Info,
          2948,
          (__int64)"SclRegProcessUpgradeRegistryOnline",
          "Migrating SAM registry content");
        OnlineOSVolumeNtPath = SclpMigrateHive(a1, (__int64)P, (__int64)L"SAM", 0, 0, (__int64)&v15, (__int64)&v16);
        if ( OnlineOSVolumeNtPath >= 0 )
        {
          SclLogGenericMessage(
            v6,
            1,
            (int)SclEvent_Generic_Info,
            2963,
            (__int64)"SclRegProcessUpgradeRegistryOnline",
            "Migrated keys: %d, values: %d",
            v15,
            v16);
          if ( v15 < 0x14 || v16 < 0x14 )
          {
            OnlineOSVolumeNtPath = -1073741436;
            SclLogGenericMessage(
              v6,
              3,
              (int)SclEvent_Generic_Error,
              2972,
              (__int64)"SclRegProcessUpgradeRegistryOnline",
              "Migrated keys/values below the threshold limit, will return [0x%08X]",
              -1073741436);
          }
          if ( OnlineOSVolumeNtPath >= 0 )
          {
            v15 = 0;
            v16 = 0;
            SclLogGenericMessage(
              v6,
              1,
              (int)SclEvent_Generic_Info,
              2981,
              (__int64)"SclRegProcessUpgradeRegistryOnline",
              "Migrating SECURITY registry content");
            v14 = 0;
            memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
            if ( a2
              || (DatabaseProtection = SclpCreateDatabaseProtection(SecurityDescriptor),
                  OnlineOSVolumeNtPath = DatabaseProtection,
                  DatabaseProtection >= 0) )
            {
              v8 = SecurityDescriptor;
              if ( a2 )
                v8 = 0;
              OnlineOSVolumeNtPath = SclpMigrateHive(
                                       a1,
                                       (__int64)P,
                                       (__int64)L"SECURITY",
                                       L"POLICY\\POLACDMS",
                                       v8,
                                       (__int64)&v15,
                                       (__int64)&v16);
              if ( OnlineOSVolumeNtPath >= 0 )
              {
                SclLogGenericMessage(
                  v6,
                  1,
                  (int)SclEvent_Generic_Info,
                  3007,
                  (__int64)"SclRegProcessUpgradeRegistryOnline",
                  "Migrated keys: %d, values: %d",
                  v15,
                  v16);
                if ( v15 < 0x14 || v16 < 0x14 )
                {
                  OnlineOSVolumeNtPath = -1073741436;
                  LODWORD(v11) = -1073741436;
                  SclLogGenericMessage(
                    v6,
                    3,
                    (int)SclEvent_Generic_Error,
                    3016,
                    (__int64)"SclRegProcessUpgradeRegistryOnline",
                    "Migrated keys/values below the threshold limit, will return [0x%08X]",
                    v11);
                }
              }
            }
            else
            {
              LODWORD(v10) = DatabaseProtection;
              SclLogGenericMessage(
                v6,
                3,
                (int)SclEvent_Generic_Error,
                2989,
                (__int64)"SclRegProcessUpgradeRegistryOnline",
                "(%lx): Failed to create the SECURITY root descriptor.",
                v10);
            }
          }
        }
      }
    }
  }
  if ( P )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
  return (unsigned int)OnlineOSVolumeNtPath;
}

```

## disassembly

```asm
0x18000b90c  mov     [rsp-28h+arg_0], rbx
0x18000b911  push    rbp
0x18000b912  push    rdi
0x18000b913  push    r13
0x18000b915  push    r14
0x18000b917  push    r15
0x18000b919  mov     rbp, rsp
0x18000b91c  sub     rsp, 70h
0x18000b920  mov     r14, rcx
0x18000b923  mov     [rbp+P], 0
0x18000b92b  lea     rcx, [rbp+P]
0x18000b92f  mov     [rbp+arg_10], 0
0x18000b936  mov     r15b, dl
0x18000b939  mov     [rbp+arg_18], 0
0x18000b940  call    SclGetOnlineOSVolumeNtPath
0x18000b945  mov     ebx, eax
0x18000b947  test    eax, eax
0x18000b949  js      loc_18000BC2A
0x18000b94f  lea     r8, aSam; "SAM"
0x18000b956  mov     rcx, r14
0x18000b959  lea     rdx, aSecurity; "SECURITY"
0x18000b960  call    SclpWipeHive
0x18000b965  mov     ebx, eax
0x18000b967  lea     rdi, [r14+480h]
0x18000b96e  xor     eax, eax
0x18000b970  mov     dword ptr [rsp+70h+var_40], ebx
0x18000b974  test    r14, r14
0x18000b977  lea     r13, aSclregprocessu; "SclRegProcessUpgradeRegistryOnline"
0x18000b97e  mov     r9d, 0B75h
0x18000b984  lea     r8, SclEvent_Generic_Info
0x18000b98b  cmovz   rdi, rax
0x18000b98f  mov     edx, 1
0x18000b994  lea     rax, aDeletedSecurit; "Deleted SECURITY hive contents in targe"...
0x18000b99b  mov     rcx, rdi
0x18000b99e  mov     [rsp+70h+var_48], rax
0x18000b9a3  mov     [rsp+70h+var_50], r13
0x18000b9a8  call    SclLogGenericMessage
0x18000b9ad  test    ebx, ebx
0x18000b9af  js      loc_18000BC2A
0x18000b9b5  xor     r8d, r8d
0x18000b9b8  lea     rdx, aSam; "SAM"
0x18000b9bf  mov     rcx, r14
0x18000b9c2  call    SclpWipeHive
0x18000b9c7  mov     dword ptr [rsp+70h+var_40], eax
0x18000b9cb  lea     r8, SclEvent_Generic_Info
0x18000b9d2  mov     ebx, eax
0x18000b9d4  mov     r9d, 0B7Dh
0x18000b9da  lea     rax, aDeletedSamHive; "Deleted SAM hive contents in target ima"...
0x18000b9e1  mov     edx, 1
0x18000b9e6  mov     [rsp+70h+var_48], rax
0x18000b9eb  mov     rcx, rdi
0x18000b9ee  mov     [rsp+70h+var_50], r13
0x18000b9f3  call    SclLogGenericMessage
0x18000b9f8  test    ebx, ebx
0x18000b9fa  js      loc_18000BC2A
0x18000ba00  lea     rax, aMigratingSamRe; "Migrating SAM registry content"
0x18000ba07  mov     [rbp+arg_10], 0
0x18000ba0e  mov     [rsp+70h+var_48], rax
0x18000ba13  lea     r8, SclEvent_Generic_Info
0x18000ba1a  mov     r9d, 0B84h
0x18000ba20  mov     [rsp+70h+var_50], r13
0x18000ba25  mov     edx, 1
0x18000ba2a  mov     [rbp+arg_18], 0
0x18000ba31  mov     rcx, rdi
0x18000ba34  call    SclLogGenericMessage
0x18000ba39  mov     rdx, [rbp+P]
0x18000ba3d  lea     rax, [rbp+arg_18]
0x18000ba41  mov     [rsp+70h+var_40], rax
0x18000ba46  lea     r8, aSam; "SAM"
0x18000ba4d  lea     rax, [rbp+arg_10]
0x18000ba51  xor     r9d, r9d
0x18000ba54  mov     [rsp+70h+var_48], rax
0x18000ba59  mov     rcx, r14
0x18000ba5c  mov     [rsp+70h+var_50], 0
0x18000ba65  call    SclpMigrateHive
0x18000ba6a  mov     ebx, eax
0x18000ba6c  test    eax, eax
0x18000ba6e  js      loc_18000BC2A
0x18000ba74  mov     eax, [rbp+arg_18]
0x18000ba77  lea     r8, SclEvent_Generic_Info
0x18000ba7e  mov     [rsp+70h+var_38], eax
0x18000ba82  mov     r9d, 0B93h
0x18000ba88  mov     eax, [rbp+arg_10]
0x18000ba8b  mov     edx, 1
0x18000ba90  mov     dword ptr [rsp+70h+var_40], eax
0x18000ba94  mov     rcx, rdi
0x18000ba97  lea     rax, aMigratedKeysDV; "Migrated keys: %d, values: %d"
0x18000ba9e  mov     [rsp+70h+var_48], rax
0x18000baa3  mov     [rsp+70h+var_50], r13
0x18000baa8  call    SclLogGenericMessage
0x18000baad  cmp     [rbp+arg_10], 14h
0x18000bab1  lea     rcx, aMigratedKeysVa; "Migrated keys/values below the threshol"...
0x18000bab8  mov     eax, 0C0000184h
0x18000babd  jb      short loc_18000BAC5
0x18000babf  cmp     [rbp+arg_18], 14h
0x18000bac3  jnb     short loc_18000BAEF
0x18000bac5  mov     dword ptr [rsp+70h+var_40], eax
0x18000bac9  lea     r8, SclEvent_Generic_Error
0x18000bad0  mov     [rsp+70h+var_48], rcx
0x18000bad5  mov     r9d, 0B9Ch
0x18000badb  mov     rcx, rdi
0x18000bade  mov     [rsp+70h+var_50], r13
0x18000bae3  mov     edx, 3
0x18000bae8  mov     ebx, eax
0x18000baea  call    SclLogGenericMessage
0x18000baef  test    ebx, ebx
0x18000baf1  js      loc_18000BC2A
0x18000baf7  lea     rax, aMigratingSecur; "Migrating SECURITY registry content"
0x18000bafe  mov     [rbp+arg_10], 0
0x18000bb05  mov     [rsp+70h+var_48], rax
0x18000bb0a  lea     r8, SclEvent_Generic_Info
0x18000bb11  mov     r9d, 0BA5h
0x18000bb17  mov     [rsp+70h+var_50], r13
0x18000bb1c  mov     edx, 1
0x18000bb21  mov     [rbp+arg_18], 0
0x18000bb28  mov     rcx, rdi
0x18000bb2b  call    SclLogGenericMessage
0x18000bb30  xor     eax, eax
0x18000bb32  xorps   xmm0, xmm0
0x18000bb35  mov     [rbp+var_8], rax
0x18000bb39  movups  [rbp+SecurityDescriptor], xmm0
0x18000bb3d  movups  [rbp+var_18], xmm0
0x18000bb41  test    r15b, r15b
0x18000bb44  jnz     short loc_18000BB6B
0x18000bb46  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x18000bb4a  call    SclpCreateDatabaseProtection
0x18000bb4f  mov     ebx, eax
0x18000bb51  test    eax, eax
0x18000bb53  jns     short loc_18000BB6B
0x18000bb55  mov     dword ptr [rsp+70h+var_40], eax
0x18000bb59  mov     r9d, 0BADh
0x18000bb5f  lea     rax, aLxFailedToCrea_1; "(%lx): Failed to create the SECURITY ro"...
0x18000bb66  jmp     loc_18000BC0C
0x18000bb6b  mov     rdx, [rbp+P]
0x18000bb6f  lea     rcx, [rbp+SecurityDescriptor]
0x18000bb73  xor     eax, eax
0x18000bb75  lea     r9, aPolicyPolacdms; "POLICY\\POLACDMS"
0x18000bb7c  test    r15b, r15b
0x18000bb7f  lea     r8, aSecurity; "SECURITY"
0x18000bb86  cmovnz  rcx, rax
0x18000bb8a  lea     rax, [rbp+arg_18]
0x18000bb8e  mov     [rsp+70h+var_40], rax
0x18000bb93  lea     rax, [rbp+arg_10]
0x18000bb97  mov     [rsp+70h+var_48], rax
0x18000bb9c  mov     [rsp+70h+var_50], rcx
0x18000bba1  mov     rcx, r14
0x18000bba4  call    SclpMigrateHive
0x18000bba9  mov     ebx, eax
0x18000bbab  test    eax, eax
0x18000bbad  js      short loc_18000BC2A
0x18000bbaf  mov     eax, [rbp+arg_18]
0x18000bbb2  lea     r8, SclEvent_Generic_Info
0x18000bbb9  mov     [rsp+70h+var_38], eax
0x18000bbbd  mov     r9d, 0BBFh
0x18000bbc3  mov     eax, [rbp+arg_10]
0x18000bbc6  mov     edx, 1
0x18000bbcb  mov     dword ptr [rsp+70h+var_40], eax
0x18000bbcf  mov     rcx, rdi
0x18000bbd2  lea     rax, aMigratedKeysDV; "Migrated keys: %d, values: %d"
0x18000bbd9  mov     [rsp+70h+var_48], rax
0x18000bbde  mov     [rsp+70h+var_50], r13
0x18000bbe3  call    SclLogGenericMessage
0x18000bbe8  cmp     [rbp+arg_10], 14h
0x18000bbec  jb      short loc_18000BBF4
0x18000bbee  cmp     [rbp+arg_18], 14h
0x18000bbf2  jnb     short loc_18000BC2A
0x18000bbf4  mov     eax, 0C0000184h
0x18000bbf9  mov     r9d, 0BC8h
0x18000bbff  mov     ebx, eax
0x18000bc01  mov     dword ptr [rsp+70h+var_40], eax
0x18000bc05  lea     rax, aMigratedKeysVa; "Migrated keys/values below the threshol"...
0x18000bc0c  mov     [rsp+70h+var_48], rax
0x18000bc11  lea     r8, SclEvent_Generic_Error
0x18000bc18  mov     edx, 3
0x18000bc1d  mov     [rsp+70h+var_50], r13
0x18000bc22  mov     rcx, rdi
0x18000bc25  call    SclLogGenericMessage
0x18000bc2a  cmp     [rbp+P], 0
0x18000bc2f  jz      short loc_18000BC4A
0x18000bc31  mov     rcx, gs:60h
0x18000bc3a  xor     edx, edx; Flags
0x18000bc3c  mov     r8, [rbp+P]; P
0x18000bc40  mov     rcx, [rcx+30h]; HeapHandle
0x18000bc44  call    cs:__imp_RtlFreeHeap
0x18000bc4a  mov     eax, ebx
0x18000bc4c  mov     rbx, [rsp+70h+arg_0]
0x18000bc54  add     rsp, 70h
0x18000bc58  pop     r15
0x18000bc5a  pop     r14
0x18000bc5c  pop     r13
0x18000bc5e  pop     rdi
0x18000bc5f  pop     rbp
0x18000bc60  retn
```
