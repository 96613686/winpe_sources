# CUwfConfiguration::set_BootMgrHORMEnabled(bool)

- ea: `0x18000bdf4`
- end: `0x18000beef`
- name: `?set_BootMgrHORMEnabled@CUwfConfiguration@@AEAAJ_N@Z`
- size: `251`
- prototype: `__int64 __fastcall(CUwfConfiguration *this, char)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000c030`

## callees

- `0x18000a824`
- `0x18000bdf4`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18000be2a`
- `ntdll!RtlNtStatusToDosError` at `0x18000be5c`
- `ntdll!RtlNtStatusToDosError` at `0x18000be92`
- `ntdll!RtlNtStatusToDosError` at `0x18000be2a`
- `ntdll!RtlNtStatusToDosError` at `0x18000be5c`
- `ntdll!RtlNtStatusToDosError` at `0x18000be92`
- `bcd!BcdOpenObject` at `0x18000be54`
- `bcd!BcdOpenObject` at `0x18000be54`
- `bcd!BcdCloseStore` at `0x18000bed9`
- `bcd!BcdCloseStore` at `0x18000bed9`
- `bcd!BcdSetElementData` at `0x18000be8a`
- `bcd!BcdSetElementData` at `0x18000be8a`
- `bcd!BcdOpenStore` at `0x18000be22`
- `bcd!BcdOpenStore` at `0x18000be22`
- `bcd!BcdCloseObject` at `0x18000bec9`
- `bcd!BcdCloseObject` at `0x18000bec9`

## pseudocode

```c
__int64 __fastcall CUwfConfiguration::set_BootMgrHORMEnabled(CUwfConfiguration *this, char a2)
{
  NTSTATUS v3; // eax
  signed int v4; // eax
  int v5; // ebx
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
    v6 = BcdOpenObject(v15, &GUID_WINDOWS_BOOTMGR, &v12);
    v7 = RtlNtStatusToDosError(v6);
    v5 = v7;
    if ( v7 > 0 )
      v5 = (unsigned __int16)v7 | 0x80070000;
    if ( v5 >= 0 )
    {
      v8 = BcdSetElementData(v12, 637534244, &v13, 2);
      v9 = RtlNtStatusToDosError(v8);
      v5 = v9;
      if ( v9 > 0 )
        v5 = (unsigned __int16)v9 | 0x80070000;
      if ( v5 >= 0 )
        v5 = CUwfConfiguration::commitBcdValue(v10, &GUID_WINDOWS_BOOTMGR, 637534244);
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
0x18000bdf4  mov     rax, rsp
0x18000bdf7  mov     [rax+20h], rbx
0x18000bdfb  push    rdi
0x18000bdfc  sub     rsp, 20h
0x18000be00  mov     rdi, rcx
0x18000be03  mov     [rax+10h], dl
0x18000be06  xor     edx, edx
0x18000be08  mov     qword ptr [rax+18h], 0
0x18000be10  xor     ecx, ecx
0x18000be12  mov     qword ptr [rax+8], 0
0x18000be1a  lea     r8, [rax+18h]
0x18000be1e  mov     byte ptr [rax+11h], 0
0x18000be22  call    cs:__imp_BcdOpenStore
0x18000be28  mov     ecx, eax; Status
0x18000be2a  call    cs:__imp_RtlNtStatusToDosError
0x18000be30  mov     ebx, eax
0x18000be32  test    eax, eax
0x18000be34  jle     short loc_18000BE3F
0x18000be36  movzx   ebx, ax
0x18000be39  or      ebx, 80070000h
0x18000be3f  test    ebx, ebx
0x18000be41  js      short loc_18000BEBF
0x18000be43  mov     rcx, [rsp+28h+arg_10]
0x18000be48  lea     r8, [rsp+28h+arg_0]
0x18000be4d  lea     rdx, GUID_WINDOWS_BOOTMGR
0x18000be54  call    cs:__imp_BcdOpenObject
0x18000be5a  mov     ecx, eax; Status
0x18000be5c  call    cs:__imp_RtlNtStatusToDosError
0x18000be62  mov     ebx, eax
0x18000be64  test    eax, eax
0x18000be66  jle     short loc_18000BE71
0x18000be68  movzx   ebx, ax
0x18000be6b  or      ebx, 80070000h
0x18000be71  test    ebx, ebx
0x18000be73  js      short loc_18000BEBF
0x18000be75  mov     rcx, [rsp+28h+arg_0]
0x18000be7a  lea     r8, [rsp+28h+arg_8]
0x18000be7f  mov     r9d, 2
0x18000be85  mov     edx, 26000024h
0x18000be8a  call    cs:__imp_BcdSetElementData
0x18000be90  mov     ecx, eax; Status
0x18000be92  call    cs:__imp_RtlNtStatusToDosError
0x18000be98  mov     ebx, eax
0x18000be9a  test    eax, eax
0x18000be9c  jle     short loc_18000BEA7
0x18000be9e  movzx   ebx, ax
0x18000bea1  or      ebx, 80070000h
0x18000bea7  test    ebx, ebx
0x18000bea9  js      short loc_18000BEBF
0x18000beab  mov     r8d, 26000024h; unsigned int
0x18000beb1  lea     rdx, GUID_WINDOWS_BOOTMGR; struct _GUID *
0x18000beb8  call    ?commitBcdValue@CUwfConfiguration@@AEAAJAEBU_GUID@@K@Z; CUwfConfiguration::commitBcdValue(_GUID const &,ulong)
0x18000bebd  mov     ebx, eax
0x18000bebf  mov     rcx, [rsp+28h+arg_0]
0x18000bec4  test    rcx, rcx
0x18000bec7  jz      short loc_18000BECF
0x18000bec9  call    cs:__imp_BcdCloseObject
0x18000becf  mov     rcx, [rsp+28h+arg_10]
0x18000bed4  test    rcx, rcx
0x18000bed7  jz      short loc_18000BEDF
0x18000bed9  call    cs:__imp_BcdCloseStore
0x18000bedf  mov     [rdi+10h], ebx
0x18000bee2  mov     eax, ebx
0x18000bee4  mov     rbx, [rsp+28h+arg_18]
0x18000bee9  add     rsp, 20h
0x18000beed  pop     rdi
0x18000beee  retn
```
