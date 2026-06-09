# SmpOpenTargetFile

- ea: `0x1400158e4`
- end: `0x140015983`
- name: `SmpOpenTargetFile`
- size: `159`
- prototype: `__int64 __fastcall(int, int, int, int, ULONG)`
- caller_count: `6`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1400130f4`
- `0x14001426c`
- `0x140015ae8`
- `0x140016018`
- `0x140016958`
- `0x140016b94`

## callees

- `0x1400158e4`

## import_xrefs

- `ntdll!NtOpenFile` at `0x140015921`
- `ntdll!NtOpenFile` at `0x140015921`
- `ntdll!NtClose` at `0x140015967`
- `ntdll!NtClose` at `0x140015967`
- `ntdll!NtQueryInformationFile` at `0x140015946`
- `ntdll!NtQueryInformationFile` at `0x140015946`

## pseudocode

```c
NTSTATUS __fastcall SmpOpenTargetFile(
        void **a1,
        ACCESS_MASK a2,
        struct _OBJECT_ATTRIBUTES *a3,
        char a4,
        ULONG ShareAccess)
{
  NTSTATUS result; // eax
  __int64 FileInformation; // [rsp+30h] [rbp-28h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+38h] [rbp-20h] BYREF

  FileInformation = 0;
  IoStatusBlock = 0;
  result = NtOpenFile(a1, a2, a3, &IoStatusBlock, ShareAccess, a4 != 0 ? 2113568 : 16416);
  if ( result >= 0 )
  {
    if ( NtQueryInformationFile(*a1, &IoStatusBlock, &FileInformation, 8u, FileAttributeTagInformation) < 0
      || (FileInformation & 0x400) == 0
      || (FileInformation & 0x2000000000000000LL) != 0 )
    {
      return 0;
    }
    else
    {
      NtClose(*a1);
      result = -1073741608;
      *a1 = 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1400158e4  push    rbx
0x1400158e6  sub     rsp, 50h
0x1400158ea  neg     r9b
0x1400158ed  mov     [rsp+58h+FileInformation], 0
0x1400158f6  xorps   xmm0, xmm0
0x1400158f9  lea     r9, [rsp+58h+IoStatusBlock]; IoStatusBlock
0x1400158fe  sbb     eax, eax
0x140015900  mov     rbx, rcx
0x140015903  and     eax, 200000h
0x140015908  add     eax, 4020h
0x14001590d  mov     [rsp+58h+OpenOptions], eax; OpenOptions
0x140015911  mov     eax, [rsp+58h+arg_20]
0x140015918  mov     [rsp+58h+ShareAccess], eax; ShareAccess
0x14001591c  movups  xmmword ptr [rsp+58h+IoStatusBlock], xmm0
0x140015921  call    cs:__imp_NtOpenFile
0x140015927  test    eax, eax
0x140015929  js      short loc_14001597D
0x14001592b  mov     rcx, [rbx]; FileHandle
0x14001592e  lea     r8, [rsp+58h+FileInformation]; FileInformation
0x140015933  mov     r9d, 8; Length
0x140015939  mov     [rsp+58h+ShareAccess], 23h ; '#'; FileInformationClass
0x140015941  lea     rdx, [rsp+58h+IoStatusBlock]; IoStatusBlock
0x140015946  call    cs:__imp_NtQueryInformationFile
0x14001594c  test    eax, eax
0x14001594e  js      short loc_14001597B
0x140015950  test    dword ptr [rsp+58h+FileInformation], 400h
0x140015958  jz      short loc_14001597B
0x14001595a  test    dword ptr [rsp+58h+FileInformation+4], 20000000h
0x140015962  jnz     short loc_14001597B
0x140015964  mov     rcx, [rbx]; Handle
0x140015967  call    cs:__imp_NtClose
0x14001596d  mov     eax, 0C00000D8h
0x140015972  mov     qword ptr [rbx], 0
0x140015979  jmp     short loc_14001597D
0x14001597b  xor     eax, eax
0x14001597d  add     rsp, 50h
0x140015981  pop     rbx
0x140015982  retn
```
