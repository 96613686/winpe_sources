# CUwfConfiguration::set_UwfBootPersistenceEnabled(bool)

- ea: `0x18000cf40`
- end: `0x18000d039`
- name: `?set_UwfBootPersistenceEnabled@CUwfConfiguration@@QEAAJ_N@Z`
- size: `249`
- prototype: `__int64 __fastcall(CUwfConfiguration *this, char)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000c190`
- `0x180019a30`

## callees

- `0x18000a824`
- `0x18000cf40`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18000cf76`
- `ntdll!RtlNtStatusToDosError` at `0x18000cfa8`
- `ntdll!RtlNtStatusToDosError` at `0x18000cfde`
- `ntdll!RtlNtStatusToDosError` at `0x18000cf76`
- `ntdll!RtlNtStatusToDosError` at `0x18000cfa8`
- `ntdll!RtlNtStatusToDosError` at `0x18000cfde`
- `bcd!BcdOpenObject` at `0x18000cfa0`
- `bcd!BcdOpenObject` at `0x18000cfa0`
- `bcd!BcdCloseStore` at `0x18000d023`
- `bcd!BcdCloseStore` at `0x18000d023`
- `bcd!BcdSetElementData` at `0x18000cfd6`
- `bcd!BcdSetElementData` at `0x18000cfd6`
- `bcd!BcdOpenStore` at `0x18000cf6e`
- `bcd!BcdOpenStore` at `0x18000cf6e`
- `bcd!BcdCloseObject` at `0x18000d013`
- `bcd!BcdCloseObject` at `0x18000d013`

## pseudocode

```c
__int64 __fastcall CUwfConfiguration::set_UwfBootPersistenceEnabled(CUwfConfiguration *this, char a2)
{
  NTSTATUS v3; // eax
  signed int v4; // eax
  signed int v5; // ebx
  NTSTATUS v6; // eax
  signed int v7; // eax
  NTSTATUS v8; // eax
  signed int v9; // eax
  CUwfConfiguration *v10; // rcx
  __int64 v12; // [rsp+30h] [rbp+8h] BYREF
  char v13; // [rsp+38h] [rbp+10h] BYREF
  char v14; // [rsp+39h] [rbp+11h]
  __int64 v15; // [rsp+40h] [rbp+18h] BYREF

  v13 = a2;
  v15 = 0;
  v12 = 0;
  v14 = 0;
  v3 = BcdOpenStore(0, 0, &v15);
  v4 = RtlNtStatusToDosError(v3);
  v5 = v4;
  if ( v4 > 0 )
    v5 = (unsigned __int16)v4 | 0x80070000;
  if ( v5 >= 0 )
  {
    v6 = BcdOpenObject(v15, &GUID_GLOBAL_SETTINGS_GROUP, &v12);
    v7 = RtlNtStatusToDosError(v6);
    v5 = v7;
    if ( v7 > 0 )
      v5 = (unsigned __int16)v7 | 0x80070000;
    if ( v5 >= 0 )
    {
      v8 = BcdSetElementData(v12, 369098885, &v13, 2);
      v9 = RtlNtStatusToDosError(v8);
      v5 = v9;
      if ( v9 > 0 )
        v5 = (unsigned __int16)v9 | 0x80070000;
      if ( v5 >= 0 )
        CUwfConfiguration::commitBcdValue(v10, &GUID_GLOBAL_SETTINGS_GROUP, 369098885);
    }
  }
  if ( v12 )
    BcdCloseObject();
  if ( v15 )
    BcdCloseStore();
  *((_DWORD *)this + 4) = v5;
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000cf40  mov     rax, rsp
0x18000cf43  mov     [rax+20h], rbx
0x18000cf47  push    rdi
0x18000cf48  sub     rsp, 20h
0x18000cf4c  mov     rdi, rcx
0x18000cf4f  mov     [rax+10h], dl
0x18000cf52  xor     edx, edx
0x18000cf54  mov     qword ptr [rax+18h], 0
0x18000cf5c  xor     ecx, ecx
0x18000cf5e  mov     qword ptr [rax+8], 0
0x18000cf66  lea     r8, [rax+18h]
0x18000cf6a  mov     byte ptr [rax+11h], 0
0x18000cf6e  call    cs:__imp_BcdOpenStore
0x18000cf74  mov     ecx, eax; Status
0x18000cf76  call    cs:__imp_RtlNtStatusToDosError
0x18000cf7c  mov     ebx, eax
0x18000cf7e  test    eax, eax
0x18000cf80  jle     short loc_18000CF8B
0x18000cf82  movzx   ebx, ax
0x18000cf85  or      ebx, 80070000h
0x18000cf8b  test    ebx, ebx
0x18000cf8d  js      short loc_18000D009
0x18000cf8f  mov     rcx, [rsp+28h+arg_10]
0x18000cf94  lea     r8, [rsp+28h+arg_0]
0x18000cf99  lea     rdx, GUID_GLOBAL_SETTINGS_GROUP
0x18000cfa0  call    cs:__imp_BcdOpenObject
0x18000cfa6  mov     ecx, eax; Status
0x18000cfa8  call    cs:__imp_RtlNtStatusToDosError
0x18000cfae  mov     ebx, eax
0x18000cfb0  test    eax, eax
0x18000cfb2  jle     short loc_18000CFBD
0x18000cfb4  movzx   ebx, ax
0x18000cfb7  or      ebx, 80070000h
0x18000cfbd  test    ebx, ebx
0x18000cfbf  js      short loc_18000D009
0x18000cfc1  mov     rcx, [rsp+28h+arg_0]
0x18000cfc6  lea     r8, [rsp+28h+arg_8]
0x18000cfcb  mov     r9d, 2
0x18000cfd1  mov     edx, 16000085h
0x18000cfd6  call    cs:__imp_BcdSetElementData
0x18000cfdc  mov     ecx, eax; Status
0x18000cfde  call    cs:__imp_RtlNtStatusToDosError
0x18000cfe4  mov     ebx, eax
0x18000cfe6  test    eax, eax
0x18000cfe8  jle     short loc_18000CFF3
0x18000cfea  movzx   ebx, ax
0x18000cfed  or      ebx, 80070000h
0x18000cff3  test    ebx, ebx
0x18000cff5  js      short loc_18000D009
0x18000cff7  mov     r8d, 16000085h; unsigned int
0x18000cffd  lea     rdx, GUID_GLOBAL_SETTINGS_GROUP; struct _GUID *
0x18000d004  call    ?commitBcdValue@CUwfConfiguration@@AEAAJAEBU_GUID@@K@Z; CUwfConfiguration::commitBcdValue(_GUID const &,ulong)
0x18000d009  mov     rcx, [rsp+28h+arg_0]
0x18000d00e  test    rcx, rcx
0x18000d011  jz      short loc_18000D019
0x18000d013  call    cs:__imp_BcdCloseObject
0x18000d019  mov     rcx, [rsp+28h+arg_10]
0x18000d01e  test    rcx, rcx
0x18000d021  jz      short loc_18000D029
0x18000d023  call    cs:__imp_BcdCloseStore
0x18000d029  mov     [rdi+10h], ebx
0x18000d02c  mov     eax, ebx
0x18000d02e  mov     rbx, [rsp+28h+arg_18]
0x18000d033  add     rsp, 20h
0x18000d037  pop     rdi
0x18000d038  retn
```
