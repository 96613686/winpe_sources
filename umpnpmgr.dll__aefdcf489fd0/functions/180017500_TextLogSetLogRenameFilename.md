# TextLogSetLogRenameFilename

- ea: `0x180017500`
- end: `0x1800175c6`
- name: `TextLogSetLogRenameFilename`
- size: `198`
- prototype: `_BOOL8 __fastcall(__int64, void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callers

- `0x18001725c`

## callees

- `0x18000c650`
- `0x1800101d8`
- `0x180017500`
- `0x18001812c`

## import_xrefs

- `ntdll!NtDeleteValueKey` at `0x18001757e`
- `ntdll!NtDeleteValueKey` at `0x18001757e`
- `ntdll!RtlInitUnicodeString` at `0x18001756f`
- `ntdll!RtlInitUnicodeString` at `0x18001756f`
- `ntdll!RtlNtStatusToDosError` at `0x18001758a`
- `ntdll!RtlNtStatusToDosError` at `0x18001758a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800175ae`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800175ae`

## string_xrefs

- `0x18001753b`: `SYSTEM\Setup\SetupapiLogRename`

## pseudocode

```c
_BOOL8 __fastcall TextLogSetLogRenameFilename(__int64 a1, void *a2)
{
  unsigned __int16 *FileTitle; // rdi
  DWORD v3; // eax
  DWORD v4; // ebx
  int v5; // eax
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-18h] BYREF
  HANDLE KeyHandle; // [rsp+48h] [rbp+10h] BYREF

  KeyHandle = a2;
  FileTitle = *(unsigned __int16 **)(a1 + 16);
  KeyHandle = 0;
  if ( !TextLogOffline )
    FileTitle = pSetupGetFileTitle(FileTitle);
  v3 = pSetupOpenKeyEx((void *)0xFFFFFFFF80000002LL, L"SYSTEM\\Setup\\SetupapiLogRename", 2u, &KeyHandle);
  v4 = v3;
  if ( v3 )
  {
    if ( v3 == 2 )
      v4 = 0;
  }
  else
  {
    v4 = 0;
    DestinationString = 0;
    RtlInitUnicodeString(&DestinationString, FileTitle);
    v5 = NtDeleteValueKey((HANDLE)(unsigned int)KeyHandle, &DestinationString);
    if ( v5 < 0 )
      v4 = RtlNtStatusToDosError(v5);
    if ( v4 == 2 )
      v4 = 0;
  }
  if ( KeyHandle )
    pSetupCloseKey((unsigned int)KeyHandle);
  SetLastError(v4);
  return v4 == 0;
}

```

## disassembly

```asm
0x180017500  mov     [rsp+arg_0], rbx
0x180017505  mov     [rsp+KeyHandle], rdx
0x18001750a  push    rdi
0x18001750b  sub     rsp, 30h
0x18001750f  cmp     cs:TextLogOffline, 0
0x180017516  mov     rdi, [rcx+10h]
0x18001751a  mov     [rsp+38h+KeyHandle], 0
0x180017523  jnz     short loc_180017530
0x180017525  mov     rcx, rdi
0x180017528  call    pSetupGetFileTitle
0x18001752d  mov     rdi, rax
0x180017530  lea     r9, [rsp+38h+KeyHandle]
0x180017535  mov     r8d, 2
0x18001753b  lea     rdx, aSystemSetupSet; "SYSTEM\\Setup\\SetupapiLogRename"
0x180017542  mov     rcx, 0FFFFFFFF80000002h
0x180017549  call    pSetupOpenKeyEx
0x18001754e  mov     ebx, eax
0x180017550  test    eax, eax
0x180017552  jz      short loc_18001755D
0x180017554  cmp     eax, 2
0x180017557  jnz     short loc_18001759A
0x180017559  xor     ebx, ebx
0x18001755b  jmp     short loc_18001759A
0x18001755d  xorps   xmm0, xmm0
0x180017560  lea     rcx, [rsp+38h+DestinationString]; DestinationString
0x180017565  mov     rdx, rdi; SourceString
0x180017568  xor     ebx, ebx
0x18001756a  movups  xmmword ptr [rsp+38h+DestinationString.Length], xmm0
0x18001756f  call    cs:__imp_RtlInitUnicodeString
0x180017575  mov     ecx, dword ptr [rsp+38h+KeyHandle]; KeyHandle
0x180017579  lea     rdx, [rsp+38h+DestinationString]; ValueName
0x18001757e  call    cs:__imp_NtDeleteValueKey
0x180017584  test    eax, eax
0x180017586  jns     short loc_180017592
0x180017588  mov     ecx, eax; Status
0x18001758a  call    cs:__imp_RtlNtStatusToDosError
0x180017590  mov     ebx, eax
0x180017592  xor     eax, eax
0x180017594  cmp     ebx, 2
0x180017597  cmovz   ebx, eax
0x18001759a  cmp     [rsp+38h+KeyHandle], 0
0x1800175a0  jz      short loc_1800175AC
0x1800175a2  mov     rcx, [rsp+38h+KeyHandle]
0x1800175a7  call    pSetupCloseKey
0x1800175ac  mov     ecx, ebx; dwErrCode
0x1800175ae  call    cs:__imp_SetLastError
0x1800175b4  xor     eax, eax
0x1800175b6  test    ebx, ebx
0x1800175b8  mov     rbx, [rsp+38h+arg_0]
0x1800175bd  setz    al
0x1800175c0  add     rsp, 30h
0x1800175c4  pop     rdi
0x1800175c5  retn
```
