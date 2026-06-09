# CUwfConfiguration::set_WinResumeHORMEnabled(bool)

- ea: `0x18000d18c`
- end: `0x18000d330`
- name: `?set_WinResumeHORMEnabled@CUwfConfiguration@@AEAAJ_N@Z`
- size: `420`
- prototype: `__int64 __fastcall(CUwfConfiguration *this, unsigned __int8)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000c030`

## callees

- `0x18000a824`
- `0x18000d18c`
- `0x18001b020`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18000d1ea`
- `ntdll!RtlNtStatusToDosError` at `0x18000d221`
- `ntdll!RtlNtStatusToDosError` at `0x18000d25b`
- `ntdll!RtlNtStatusToDosError` at `0x18000d285`
- `ntdll!RtlNtStatusToDosError` at `0x18000d2ba`
- `ntdll!RtlNtStatusToDosError` at `0x18000d1ea`
- `ntdll!RtlNtStatusToDosError` at `0x18000d221`
- `ntdll!RtlNtStatusToDosError` at `0x18000d25b`
- `ntdll!RtlNtStatusToDosError` at `0x18000d285`
- `ntdll!RtlNtStatusToDosError` at `0x18000d2ba`
- `bcd!BcdOpenObject` at `0x18000d219`
- `bcd!BcdOpenObject` at `0x18000d27d`
- `bcd!BcdOpenObject` at `0x18000d219`
- `bcd!BcdOpenObject` at `0x18000d27d`
- `bcd!BcdCloseStore` at `0x18000d308`
- `bcd!BcdCloseStore` at `0x18000d308`
- `bcd!BcdSetElementData` at `0x18000d2b2`
- `bcd!BcdSetElementData` at `0x18000d2b2`
- `bcd!BcdOpenStore` at `0x18000d1e2`
- `bcd!BcdOpenStore` at `0x18000d1e2`
- `bcd!BcdCloseObject` at `0x18000d2ea`
- `bcd!BcdCloseObject` at `0x18000d2f9`
- `bcd!BcdCloseObject` at `0x18000d2ea`
- `bcd!BcdCloseObject` at `0x18000d2f9`
- `bcd!BcdGetElementData` at `0x18000d253`
- `bcd!BcdGetElementData` at `0x18000d253`

## pseudocode

```c
__int64 __fastcall CUwfConfiguration::set_WinResumeHORMEnabled(CUwfConfiguration *this, unsigned __int8 a2)
{
  NTSTATUS v3; // eax
  signed int v4; // eax
  int v5; // ebx
  NTSTATUS v6; // eax
  signed int v7; // eax
  NTSTATUS ElementData; // eax
  signed int v9; // eax
  NTSTATUS v10; // eax
  signed int v11; // eax
  NTSTATUS v12; // eax
  signed int v13; // eax
  CUwfConfiguration *v14; // rcx
  __int64 v16; // [rsp+20h] [rbp-40h] BYREF
  __int64 v17; // [rsp+28h] [rbp-38h] BYREF
  __int64 v18; // [rsp+30h] [rbp-30h] BYREF
  __int64 v19; // [rsp+38h] [rbp-28h] BYREF
  struct _GUID v20; // [rsp+40h] [rbp-20h] BYREF

  LOWORD(v16) = a2;
  v17 = 0;
  v19 = 0;
  v18 = 0;
  v20 = 0;
  HIDWORD(v16) = 0;
  v3 = BcdOpenStore(0, 0, &v17);
  v4 = RtlNtStatusToDosError(v3);
  v5 = v4;
  if ( v4 > 0 )
    v5 = (unsigned __int16)v4 | 0x80070000;
  if ( v5 >= 0 )
  {
    v6 = BcdOpenObject(v17, &GUID_CURRENT_BOOT_ENTRY, &v19);
    v7 = RtlNtStatusToDosError(v6);
    v5 = v7;
    if ( v7 > 0 )
      v5 = (unsigned __int16)v7 | 0x80070000;
    if ( v5 >= 0 )
    {
      HIDWORD(v16) = 16;
      ElementData = BcdGetElementData(v19, 587202563, &v20, (char *)&v16 + 4, v16);
      v9 = RtlNtStatusToDosError(ElementData);
      v5 = v9;
      if ( v9 > 0 )
        v5 = (unsigned __int16)v9 | 0x80070000;
      if ( v5 >= 0 )
      {
        v10 = BcdOpenObject(v17, &v20, &v18);
        v11 = RtlNtStatusToDosError(v10);
        v5 = v11;
        if ( v11 > 0 )
          v5 = (unsigned __int16)v11 | 0x80070000;
        if ( v5 >= 0 )
        {
          HIDWORD(v16) = 2;
          v12 = BcdSetElementData(v18, 637534244, &v16, 2);
          v13 = RtlNtStatusToDosError(v12);
          v5 = v13;
          if ( v13 > 0 )
            v5 = (unsigned __int16)v13 | 0x80070000;
          if ( v5 >= 0 )
            v5 = CUwfConfiguration::commitBcdValue(v14, &v20, 637534244);
        }
      }
    }
  }
  if ( v18 )
    BcdCloseObject();
  if ( v19 )
    BcdCloseObject();
  if ( v17 )
    BcdCloseStore();
  *((_DWORD *)this + 4) = v5;
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000d18c  mov     [rsp-18h+arg_10], rbx
0x18000d191  push    rbp
0x18000d192  push    rdi
0x18000d193  push    r14
0x18000d195  mov     rbp, rsp
0x18000d198  sub     rsp, 60h
0x18000d19c  mov     rax, cs:__security_cookie
0x18000d1a3  xor     rax, rsp
0x18000d1a6  mov     [rbp+var_10], rax
0x18000d1aa  mov     rdi, rcx
0x18000d1ad  mov     [rbp+var_40], dl
0x18000d1b0  xorps   xmm0, xmm0
0x18000d1b3  mov     [rbp+var_38], 0
0x18000d1bb  xor     edx, edx
0x18000d1bd  mov     [rbp+var_28], 0
0x18000d1c5  xor     ecx, ecx
0x18000d1c7  mov     [rbp+var_30], 0
0x18000d1cf  lea     r8, [rbp+var_38]
0x18000d1d3  mov     [rbp+var_3F], 0
0x18000d1d7  movups  xmmword ptr [rbp+var_20.Data1], xmm0
0x18000d1db  mov     [rbp+var_3C], 0
0x18000d1e2  call    cs:__imp_BcdOpenStore
0x18000d1e8  mov     ecx, eax; Status
0x18000d1ea  call    cs:__imp_RtlNtStatusToDosError
0x18000d1f0  mov     ebx, eax
0x18000d1f2  mov     r14d, 80070000h
0x18000d1f8  test    eax, eax
0x18000d1fa  jle     short loc_18000D202
0x18000d1fc  movzx   ebx, ax
0x18000d1ff  or      ebx, r14d
0x18000d202  test    ebx, ebx
0x18000d204  js      loc_18000D2E1
0x18000d20a  mov     rcx, [rbp+var_38]
0x18000d20e  lea     r8, [rbp+var_28]
0x18000d212  lea     rdx, GUID_CURRENT_BOOT_ENTRY
0x18000d219  call    cs:__imp_BcdOpenObject
0x18000d21f  mov     ecx, eax; Status
0x18000d221  call    cs:__imp_RtlNtStatusToDosError
0x18000d227  mov     ebx, eax
0x18000d229  test    eax, eax
0x18000d22b  jle     short loc_18000D233
0x18000d22d  movzx   ebx, ax
0x18000d230  or      ebx, r14d
0x18000d233  test    ebx, ebx
0x18000d235  js      loc_18000D2E1
0x18000d23b  mov     rcx, [rbp+var_28]
0x18000d23f  lea     r9, [rbp+var_3C]
0x18000d243  lea     r8, [rbp+var_20]
0x18000d247  mov     [rbp+var_3C], 10h
0x18000d24e  mov     edx, 23000003h
0x18000d253  call    cs:__imp_BcdGetElementData
0x18000d259  mov     ecx, eax; Status
0x18000d25b  call    cs:__imp_RtlNtStatusToDosError
0x18000d261  mov     ebx, eax
0x18000d263  test    eax, eax
0x18000d265  jle     short loc_18000D26D
0x18000d267  movzx   ebx, ax
0x18000d26a  or      ebx, r14d
0x18000d26d  test    ebx, ebx
0x18000d26f  js      short loc_18000D2E1
0x18000d271  mov     rcx, [rbp+var_38]
0x18000d275  lea     r8, [rbp+var_30]
0x18000d279  lea     rdx, [rbp+var_20]
0x18000d27d  call    cs:__imp_BcdOpenObject
0x18000d283  mov     ecx, eax; Status
0x18000d285  call    cs:__imp_RtlNtStatusToDosError
0x18000d28b  mov     ebx, eax
0x18000d28d  test    eax, eax
0x18000d28f  jle     short loc_18000D297
0x18000d291  movzx   ebx, ax
0x18000d294  or      ebx, r14d
0x18000d297  test    ebx, ebx
0x18000d299  js      short loc_18000D2E1
0x18000d29b  mov     rcx, [rbp+var_30]
0x18000d29f  lea     r8, [rbp+var_40]
0x18000d2a3  mov     r9d, 2
0x18000d2a9  mov     edx, 26000024h
0x18000d2ae  mov     [rbp+var_3C], r9d
0x18000d2b2  call    cs:__imp_BcdSetElementData
0x18000d2b8  mov     ecx, eax; Status
0x18000d2ba  call    cs:__imp_RtlNtStatusToDosError
0x18000d2c0  mov     ebx, eax
0x18000d2c2  test    eax, eax
0x18000d2c4  jle     short loc_18000D2CC
0x18000d2c6  movzx   ebx, ax
0x18000d2c9  or      ebx, r14d
0x18000d2cc  test    ebx, ebx
0x18000d2ce  js      short loc_18000D2E1
0x18000d2d0  mov     r8d, 26000024h; unsigned int
0x18000d2d6  lea     rdx, [rbp+var_20]; struct _GUID *
0x18000d2da  call    ?commitBcdValue@CUwfConfiguration@@AEAAJAEBU_GUID@@K@Z; CUwfConfiguration::commitBcdValue(_GUID const &,ulong)
0x18000d2df  mov     ebx, eax
0x18000d2e1  mov     rcx, [rbp+var_30]
0x18000d2e5  test    rcx, rcx
0x18000d2e8  jz      short loc_18000D2F0
0x18000d2ea  call    cs:__imp_BcdCloseObject
0x18000d2f0  mov     rcx, [rbp+var_28]
0x18000d2f4  test    rcx, rcx
0x18000d2f7  jz      short loc_18000D2FF
0x18000d2f9  call    cs:__imp_BcdCloseObject
0x18000d2ff  mov     rcx, [rbp+var_38]
0x18000d303  test    rcx, rcx
0x18000d306  jz      short loc_18000D30E
0x18000d308  call    cs:__imp_BcdCloseStore
0x18000d30e  mov     [rdi+10h], ebx
0x18000d311  mov     eax, ebx
0x18000d313  mov     rcx, [rbp+var_10]
0x18000d317  xor     rcx, rsp; StackCookie
0x18000d31a  call    __security_check_cookie
0x18000d31f  mov     rbx, [rsp+60h+arg_10]
0x18000d327  add     rsp, 60h
0x18000d32b  pop     r14
0x18000d32d  pop     rdi
0x18000d32e  pop     rbp
0x18000d32f  retn
```
