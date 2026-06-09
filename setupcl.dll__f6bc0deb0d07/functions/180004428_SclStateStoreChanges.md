# SclStateStoreChanges

- ea: `0x180004428`
- end: `0x18000483d`
- name: `SclStateStoreChanges`
- size: `1045`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD **)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, reparse_path, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800061b0`

## callees

- `0x18000154c`
- `0x180001c74`
- `0x180004428`
- `0x1800051d8`
- `0x180007ac4`
- `0x180007b30`
- `0x180008e40`
- `0x18000a524`
- `0x18000de94`
- `0x180014c48`
- `0x1800151f0`
- `0x1800153c8`
- `0x1800179e0`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18000450e`
- `ntdll!RtlInitUnicodeString` at `0x18000450e`
- `ntdll!NtClose` at `0x1800047ae`
- `ntdll!NtClose` at `0x1800047be`
- `ntdll!NtClose` at `0x1800047ae`
- `ntdll!NtClose` at `0x1800047be`
- `ntdll!RtlFreeHeap` at `0x180004653`
- `ntdll!RtlFreeHeap` at `0x1800047f7`
- `ntdll!RtlFreeHeap` at `0x180004814`
- `ntdll!RtlFreeHeap` at `0x180004653`
- `ntdll!RtlFreeHeap` at `0x1800047f7`
- `ntdll!RtlFreeHeap` at `0x180004814`
- `ntdll!NtSaveKeyEx` at `0x18000474d`
- `ntdll!NtSaveKeyEx` at `0x18000474d`
- `ntdll!NtCreateFile` at `0x1800046e9`
- `ntdll!NtCreateFile` at `0x1800046e9`

## string_xrefs

- `0x1800044e8`: `\REGISTRY\MACHINE\SYSTEM\SETUP\SETUPCL`
- `0x180004593`: `SECURITY`
- `0x180004614`: `System32\config`
- `0x18000471b`: `(%lx): Error opening SetupCl hive file [%ws]`

## pseudocode

```c
__int64 __fastcall SclStateStoreChanges(__int64 a1, __int64 a2, _QWORD **a3)
{
  WCHAR *v3; // r15
  int v7; // ebx
  WCHAR *v8; // rdi
  const wchar_t *v9; // rsi
  int v10; // eax
  int v11; // ebx
  wchar_t *v12; // rax
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rcx
  wchar_t *v18; // rax
  wchar_t *v19; // rsi
  __int64 v20; // rcx
  __int64 v21; // rcx
  __int64 ShareAccess; // [rsp+30h] [rbp-D0h]
  HANDLE KeyHandle; // [rsp+60h] [rbp-A0h] BYREF
  void *FileHandle; // [rsp+68h] [rbp-98h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp-90h] BYREF
  struct _UNICODE_STRING v27; // [rsp+80h] [rbp-80h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+90h] [rbp-70h] BYREF
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v30[528]; // [rsp+E0h] [rbp-20h] BYREF

  v3 = 0;
  FileHandle = 0;
  KeyHandle = 0;
  DestinationString = 0;
  if ( !SclOSIsValid(a2) )
    return (unsigned int)-1073741811;
  v8 = 0;
  if ( a2 && *(_DWORD *)a2 != 1 )
  {
    if ( *(_DWORD *)a2 != 2 )
      return (unsigned int)-1073741811;
    v9 = *(const wchar_t **)(a2 + 8);
    goto LABEL_9;
  }
  v7 = SclExpandString(L"%SYSTEMROOT%", v30);
  if ( v7 >= 0 )
  {
    v9 = (const wchar_t *)v30;
LABEL_9:
    v10 = GenerateRandomChars(&IoStatusBlock);
    if ( v10 >= 0 )
    {
      v12 = BuildPath(L"\\REGISTRY\\MACHINE\\SYSTEM\\SETUP\\SETUPCL", (STRSAFE_PCNZWCH)&IoStatusBlock);
      v8 = v12;
      if ( v12 )
      {
        RtlInitUnicodeString(&DestinationString, v12);
        v7 = SclCreateKeyEx(0, &DestinationString, 0x30006u, 0, 0, &KeyHandle);
        if ( v7 >= 0 )
        {
          v7 = SclpStateStoreChangedKeys(v13, v9, KeyHandle, L"DEFAULT", *a3);
          if ( v7 >= 0 )
          {
            v7 = SclpStateStoreChangedKeys(v14, v9, KeyHandle, L"SAM", a3[1]);
            if ( v7 >= 0 )
            {
              v7 = SclpStateStoreChangedKeys(v15, v9, KeyHandle, L"SECURITY", a3[2]);
              if ( v7 >= 0 )
              {
                v7 = SclpStateStoreChangedKeys(v16, v9, KeyHandle, L"SOFTWARE", a3[3]);
                if ( v7 >= 0 )
                {
                  v7 = SclpStateStoreChangedKeys(v17, v9, KeyHandle, L"SYSTEM", a3[4]);
                  if ( v7 >= 0 )
                  {
                    v18 = BuildPathMulti(3u, v9, L"System32\\config", L"SETUPCL");
                    v19 = v18;
                    if ( v18 )
                    {
                      v7 = SclDosPathToNtPath((__int64)v18, &FileHandle);
                      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v19);
                      v3 = (WCHAR *)FileHandle;
                    }
                    else
                    {
                      v7 = -1073741801;
                    }
                    if ( v7 >= 0 )
                    {
                      FileHandle = 0;
                      v27 = 0;
                      memset(&ObjectAttributes, 0, 44);
                      IoStatusBlock = 0;
                      INIT_OBJA_EX((__int64)&ObjectAttributes, &v27, v3, 64, 0);
                      v7 = NtCreateFile(
                             &FileHandle,
                             0x120116u,
                             &ObjectAttributes,
                             &IoStatusBlock,
                             0,
                             0x80u,
                             0,
                             5u,
                             0x60u,
                             0,
                             0);
                      if ( v7 >= 0 )
                      {
                        v7 = NtSaveKeyEx(KeyHandle, FileHandle, 1u);
                        if ( v7 < 0 )
                        {
                          v21 = a1 + 1152;
                          LODWORD(ShareAccess) = v7;
                          if ( !a1 )
                            v21 = 0;
                          SclLogGenericMessage(
                            v21,
                            3,
                            (int)SclEvent_Generic_Error,
                            1862,
                            (__int64)"SclStateStoreChanges",
                            "(%lx): Error saving SetupCl key [%ws] to hive file [%ws]",
                            ShareAccess,
                            v8,
                            v3);
                        }
                      }
                      else
                      {
                        LODWORD(ShareAccess) = v7;
                        v20 = a1 + 1152;
                        if ( !a1 )
                          v20 = 0;
                        SclLogGenericMessage(
                          v20,
                          3,
                          (int)SclEvent_Generic_Error,
                          1853,
                          (__int64)"SclStateStoreChanges",
                          "(%lx): Error opening SetupCl hive file [%ws]",
                          ShareAccess,
                          v3);
                      }
                      if ( FileHandle )
                        NtClose(FileHandle);
                    }
                  }
                }
              }
            }
          }
        }
      }
      else
      {
        v7 = -1073741801;
      }
    }
    else
    {
      v11 = (unsigned __int16)v10;
      if ( !(_WORD)v10 )
        v11 = 31;
      v7 = v11 | 0xC0070000;
    }
  }
  if ( KeyHandle )
    NtClose(KeyHandle);
  if ( v8 )
  {
    if ( v7 < 0 )
      SclRegDeleteKeyRecursive(0, v8);
    else
      v7 = SclRegDeleteKeyRecursive(0, v8);
  }
  if ( v3 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v3);
  if ( v8 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v8);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180004428  push    rbp
0x18000442a  push    rbx
0x18000442b  push    rsi
0x18000442c  push    rdi
0x18000442d  push    r13
0x18000442f  push    r14
0x180004431  push    r15
0x180004433  lea     rbp, [rsp-200h]
0x18000443b  sub     rsp, 300h
0x180004442  mov     rax, cs:__security_cookie
0x180004449  xor     rax, rsp
0x18000444c  mov     [rbp+230h+var_40], rax
0x180004453  xor     r15d, r15d
0x180004456  mov     r13, rcx
0x180004459  xorps   xmm0, xmm0
0x18000445c  mov     [rsp+330h+FileHandle], r15
0x180004461  mov     rcx, rdx
0x180004464  mov     [rsp+330h+KeyHandle], r15
0x180004469  movups  xmmword ptr [rsp+330h+DestinationString.Length], xmm0
0x18000446e  mov     r14, r8
0x180004471  mov     rsi, rdx
0x180004474  call    SclOSIsValid
0x180004479  test    al, al
0x18000447b  jnz     short loc_180004487
0x18000447d  mov     ebx, 0C000000Dh
0x180004482  jmp     loc_18000481A
0x180004487  xor     edi, edi
0x180004489  test    rsi, rsi
0x18000448c  jz      short loc_1800044A0
0x18000448e  mov     ecx, [rsi]
0x180004490  sub     ecx, 1
0x180004493  jz      short loc_1800044A0
0x180004495  cmp     ecx, 1
0x180004498  jnz     short loc_18000447D
0x18000449a  mov     rsi, [rsi+8]
0x18000449e  jmp     short loc_1800044BE
0x1800044a0  lea     rdx, [rbp+230h+var_250]; void *
0x1800044a4  lea     rcx, aSystemroot_0; "%SYSTEMROOT%"
0x1800044ab  call    SclExpandString
0x1800044b0  mov     ebx, eax
0x1800044b2  test    eax, eax
0x1800044b4  js      loc_1800047B4
0x1800044ba  lea     rsi, [rbp+230h+var_250]
0x1800044be  lea     rcx, [rbp+230h+IoStatusBlock]
0x1800044c2  call    GenerateRandomChars
0x1800044c7  test    eax, eax
0x1800044c9  jns     short loc_1800044E4
0x1800044cb  movzx   ebx, ax
0x1800044ce  mov     eax, 1Fh
0x1800044d3  test    ebx, ebx
0x1800044d5  cmovz   ebx, eax
0x1800044d8  or      ebx, 0C0070000h
0x1800044de  jl      loc_1800047B4
0x1800044e4  lea     rdx, [rbp+230h+IoStatusBlock]; STRSAFE_PCNZWCH
0x1800044e8  lea     rcx, aRegistryMachin_2; "\\REGISTRY\\MACHINE\\SYSTEM\\SETUP\\SET"...
0x1800044ef  call    BuildPath
0x1800044f4  mov     rdi, rax
0x1800044f7  test    rax, rax
0x1800044fa  jnz     short loc_180004506
0x1800044fc  mov     ebx, 0C0000017h
0x180004501  jmp     loc_1800047B4
0x180004506  mov     rdx, rdi; SourceString
0x180004509  lea     rcx, [rsp+330h+DestinationString]; DestinationString
0x18000450e  call    cs:__imp_RtlInitUnicodeString
0x180004514  lea     rax, [rsp+330h+KeyHandle]
0x180004519  xor     r9d, r9d
0x18000451c  mov     qword ptr [rsp+330h+FileAttributes], rax
0x180004521  lea     rdx, [rsp+330h+DestinationString]
0x180004526  mov     r8d, 30006h
0x18000452c  mov     [rsp+330h+AllocationSize], r15
0x180004531  xor     ecx, ecx
0x180004533  call    SclCreateKeyEx
0x180004538  mov     ebx, eax
0x18000453a  test    eax, eax
0x18000453c  js      loc_1800047B4
0x180004542  mov     rax, [r14]
0x180004545  lea     r9, aDefault_0; "DEFAULT"
0x18000454c  mov     r8, [rsp+330h+KeyHandle]
0x180004551  mov     rdx, rsi
0x180004554  mov     [rsp+330h+AllocationSize], rax
0x180004559  call    SclpStateStoreChangedKeys
0x18000455e  mov     ebx, eax
0x180004560  test    eax, eax
0x180004562  js      loc_1800047B4
0x180004568  mov     rax, [r14+8]
0x18000456c  lea     r9, aSam; "SAM"
0x180004573  mov     r8, [rsp+330h+KeyHandle]
0x180004578  mov     rdx, rsi
0x18000457b  mov     [rsp+330h+AllocationSize], rax
0x180004580  call    SclpStateStoreChangedKeys
0x180004585  mov     ebx, eax
0x180004587  test    eax, eax
0x180004589  js      loc_1800047B4
0x18000458f  mov     rax, [r14+10h]
0x180004593  lea     r9, aSecurity; "SECURITY"
0x18000459a  mov     r8, [rsp+330h+KeyHandle]
0x18000459f  mov     rdx, rsi
0x1800045a2  mov     [rsp+330h+AllocationSize], rax
0x1800045a7  call    SclpStateStoreChangedKeys
0x1800045ac  mov     ebx, eax
0x1800045ae  test    eax, eax
0x1800045b0  js      loc_1800047B4
0x1800045b6  mov     rax, [r14+18h]
0x1800045ba  lea     r9, aSoftware; "SOFTWARE"
0x1800045c1  mov     r8, [rsp+330h+KeyHandle]
0x1800045c6  mov     rdx, rsi
0x1800045c9  mov     [rsp+330h+AllocationSize], rax
0x1800045ce  call    SclpStateStoreChangedKeys
0x1800045d3  mov     ebx, eax
0x1800045d5  test    eax, eax
0x1800045d7  js      loc_1800047B4
0x1800045dd  mov     rax, [r14+20h]
0x1800045e1  lea     r9, aSystem; "SYSTEM"
0x1800045e8  mov     r8, [rsp+330h+KeyHandle]
0x1800045ed  mov     rdx, rsi
0x1800045f0  mov     [rsp+330h+AllocationSize], rax
0x1800045f5  call    SclpStateStoreChangedKeys
0x1800045fa  mov     ebx, eax
0x1800045fc  test    eax, eax
0x1800045fe  js      loc_1800047B4
0x180004604  mov     r14d, 3
0x18000460a  lea     r9, aSetupcl; "SETUPCL"
0x180004611  mov     ecx, r14d
0x180004614  lea     r8, aSystem32Config; "System32\\config"
0x18000461b  mov     rdx, rsi
0x18000461e  call    BuildPathMulti
0x180004623  mov     rsi, rax
0x180004626  test    rax, rax
0x180004629  jnz     short loc_180004632
0x18000462b  mov     ebx, 0C0000017h
0x180004630  jmp     short loc_18000465E
0x180004632  lea     rdx, [rsp+330h+FileHandle]
0x180004637  mov     rcx, rsi
0x18000463a  call    SclDosPathToNtPath
0x18000463f  mov     rcx, gs:60h
0x180004648  mov     r8, rsi; P
0x18000464b  xor     edx, edx; Flags
0x18000464d  mov     ebx, eax
0x18000464f  mov     rcx, [rcx+30h]; HeapHandle
0x180004653  call    cs:__imp_RtlFreeHeap
0x180004659  mov     r15, [rsp+330h+FileHandle]
0x18000465e  test    ebx, ebx
0x180004660  js      loc_1800047B4
0x180004666  xorps   xmm0, xmm0
0x180004669  lea     rdx, [rbp+230h+var_2B0]
0x18000466d  xor     eax, eax
0x18000466f  lea     rcx, [rbp+230h+ObjectAttributes]
0x180004673  movups  xmmword ptr [rbp+230h+ObjectAttributes.ObjectName], xmm0
0x180004677  mov     r8, r15
0x18000467a  mov     [rsp+330h+FileHandle], rax
0x18000467f  movups  [rbp+230h+var_2B0], xmm0
0x180004683  lea     r9d, [rax+40h]
0x180004687  mov     [rsp+330h+AllocationSize], rax
0x18000468c  movups  xmmword ptr [rbp+230h+ObjectAttributes.Length], xmm0
0x180004690  movups  xmmword ptr [rbp+230h+ObjectAttributes+1Ch], xmm0
0x180004694  movups  xmmword ptr [rbp+230h+IoStatusBlock], xmm0
0x180004698  call    INIT_OBJA_EX
0x18000469d  mov     [rsp+330h+EaLength], 0; EaLength
0x1800046a5  lea     r9, [rbp+230h+IoStatusBlock]; IoStatusBlock
0x1800046a9  mov     [rsp+330h+EaBuffer], 0; EaBuffer
0x1800046b2  lea     r8, [rbp+230h+ObjectAttributes]; ObjectAttributes
0x1800046b6  mov     [rsp+330h+CreateOptions], 60h ; '`'; CreateOptions
0x1800046be  lea     rcx, [rsp+330h+FileHandle]; FileHandle
0x1800046c3  mov     [rsp+330h+CreateDisposition], 5; CreateDisposition
0x1800046cb  mov     edx, 120116h; DesiredAccess
0x1800046d0  mov     dword ptr [rsp+330h+ShareAccess], 0; ShareAccess
0x1800046d8  mov     [rsp+330h+FileAttributes], 80h; FileAttributes
0x1800046e0  mov     [rsp+330h+AllocationSize], 0; AllocationSize
0x1800046e9  call    cs:__imp_NtCreateFile
0x1800046ef  mov     ebx, eax
0x1800046f1  test    eax, eax
0x1800046f3  jns     short loc_18000473D
0x1800046f5  xor     eax, eax
0x1800046f7  mov     qword ptr [rsp+330h+CreateDisposition], r15
0x1800046fc  test    r13, r13
0x1800046ff  mov     dword ptr [rsp+330h+ShareAccess], ebx
0x180004703  lea     rcx, [r13+480h]
0x18000470a  mov     r9d, 73Dh
0x180004710  cmovz   rcx, rax
0x180004714  lea     r8, SclEvent_Generic_Error
0x18000471b  lea     rax, aLxErrorOpening; "(%lx): Error opening SetupCl hive file "...
0x180004722  mov     edx, r14d
0x180004725  mov     qword ptr [rsp+330h+FileAttributes], rax
0x18000472a  lea     rax, aSclstatestorec; "SclStateStoreChanges"
0x180004731  mov     [rsp+330h+AllocationSize], rax
0x180004736  call    SclLogGenericMessage
0x18000473b  jmp     short loc_1800047A4
0x18000473d  mov     rdx, [rsp+330h+FileHandle]; FileHandle
0x180004742  mov     r8d, 1; Flags
0x180004748  mov     rcx, [rsp+330h+KeyHandle]; KeyHandle
0x18000474d  call    cs:__imp_NtSaveKeyEx
0x180004753  mov     ebx, eax
0x180004755  test    eax, eax
0x180004757  jns     short loc_1800047A4
0x180004759  xor     eax, eax
0x18000475b  mov     qword ptr [rsp+330h+CreateOptions], r15
0x180004760  mov     qword ptr [rsp+330h+CreateDisposition], rdi
0x180004765  lea     rcx, [r13+480h]
0x18000476c  test    r13, r13
0x18000476f  mov     dword ptr [rsp+330h+ShareAccess], ebx
0x180004773  mov     r9d, 746h
0x180004779  lea     r8, SclEvent_Generic_Error
0x180004780  cmovz   rcx, rax
0x180004784  mov     edx, r14d
0x180004787  lea     rax, aLxErrorSavingS; "(%lx): Error saving SetupCl key [%ws] t"...
0x18000478e  mov     qword ptr [rsp+330h+FileAttributes], rax
0x180004793  lea     rax, aSclstatestorec; "SclStateStoreChanges"
0x18000479a  mov     [rsp+330h+AllocationSize], rax
0x18000479f  call    SclLogGenericMessage
0x1800047a4  mov     rcx, [rsp+330h+FileHandle]; Handle
0x1800047a9  test    rcx, rcx
0x1800047ac  jz      short loc_1800047B4
0x1800047ae  call    cs:__imp_NtClose
0x1800047b4  mov     rcx, [rsp+330h+KeyHandle]; Handle
0x1800047b9  test    rcx, rcx
0x1800047bc  jz      short loc_1800047C4
0x1800047be  call    cs:__imp_NtClose
0x1800047c4  test    rdi, rdi
0x1800047c7  jz      short loc_1800047E0
0x1800047c9  xor     ecx, ecx
0x1800047cb  mov     rdx, rdi
0x1800047ce  test    ebx, ebx
0x1800047d0  js      short loc_1800047DB
0x1800047d2  call    SclRegDeleteKeyRecursive
0x1800047d7  mov     ebx, eax
0x1800047d9  jmp     short loc_1800047E0
0x1800047db  call    SclRegDeleteKeyRecursive
0x1800047e0  test    r15, r15
0x1800047e3  jz      short loc_1800047FD
0x1800047e5  mov     rcx, gs:60h
0x1800047ee  mov     r8, r15; P
0x1800047f1  xor     edx, edx; Flags
0x1800047f3  mov     rcx, [rcx+30h]; HeapHandle
0x1800047f7  call    cs:__imp_RtlFreeHeap
0x1800047fd  test    rdi, rdi
0x180004800  jz      short loc_18000481A
0x180004802  mov     rcx, gs:60h
0x18000480b  mov     r8, rdi; P
0x18000480e  xor     edx, edx; Flags
0x180004810  mov     rcx, [rcx+30h]; HeapHandle
0x180004814  call    cs:__imp_RtlFreeHeap
0x18000481a  mov     eax, ebx
0x18000481c  mov     rcx, [rbp+230h+var_40]
0x180004823  xor     rcx, rsp; StackCookie
0x180004826  call    __security_check_cookie
0x18000482b  add     rsp, 300h
0x180004832  pop     r15
0x180004834  pop     r14
0x180004836  pop     r13
0x180004838  pop     rdi
0x180004839  pop     rsi
0x18000483a  pop     rbx
0x18000483b  pop     rbp
0x18000483c  retn
```
