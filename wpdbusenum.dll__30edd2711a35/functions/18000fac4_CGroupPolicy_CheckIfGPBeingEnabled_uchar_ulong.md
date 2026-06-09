# CGroupPolicy::CheckIfGPBeingEnabled(uchar *,ulong)

- ea: `0x18000fac4`
- end: `0x18000fb74`
- name: `?CheckIfGPBeingEnabled@CGroupPolicy@@IEAAHPEAEK@Z`
- size: `176`
- prototype: `__int64 __fastcall(CGroupPolicy *this, unsigned __int8 *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000f390`

## callees

- `0x180002fa0`
- `0x180005bb0`
- `0x18000fac4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000fb5a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000fb5a`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x18000fb30`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x18000fb30`

## string_xrefs

- `0x18000fae4`: `HotplugSecurityDescriptor`
- `0x18000fb3b`: `No change in security descriptor\n`

## pseudocode

```c
__int64 __fastcall CGroupPolicy::CheckIfGPBeingEnabled(CGroupPolicy *this, unsigned __int8 *a2, int a3)
{
  __int64 v5; // rbx
  unsigned int v6; // ebx
  DWORD Length; // [rsp+50h] [rbp+8h] BYREF
  int Length_4; // [rsp+54h] [rbp+Ch]
  void *Source2; // [rsp+68h] [rbp+20h] BYREF

  Length_4 = HIDWORD(this);
  Source2 = 0;
  Length = 0;
  if ( WPDLibGetRegistryValue(
         0,
         (__int64)a2,
         L"SYSTEM\\CurrentControlSet\\Control\\Storage",
         L"HotplugSecurityDescriptor",
         3,
         (BYTE **)&Source2,
         &Length) )
  {
    return 1;
  }
  else
  {
    if ( Length == a3 && (v5 = Length, RtlCompareMemory(a2, Source2, Length) == v5) )
    {
      GPDebugPrintX(8u, "No change in security descriptor\n");
      v6 = 0;
    }
    else
    {
      v6 = 1;
    }
    LocalFree(Source2);
  }
  return v6;
}

```

## disassembly

```asm
0x18000fac4  mov     r11, rsp
0x18000fac7  mov     [r11+10h], rbx
0x18000facb  mov     [r11+8], rcx
0x18000facf  push    rdi
0x18000fad0  sub     rsp, 40h
0x18000fad4  lea     rax, [r11+8]
0x18000fad8  mov     qword ptr [r11+20h], 0
0x18000fae0  mov     [r11-18h], rax
0x18000fae4  lea     r9, aHotplugsecurit; "HotplugSecurityDescriptor"
0x18000faeb  lea     rax, [r11+20h]
0x18000faef  mov     dword ptr [rsp+48h+Length], 0
0x18000faf7  mov     ebx, r8d
0x18000fafa  mov     [r11-20h], rax
0x18000fafe  lea     r8, aSystemCurrentc_1; "SYSTEM\\CurrentControlSet\\Control\\Sto"...
0x18000fb05  mov     [rsp+48h+var_28], 3
0x18000fb0d  xor     ecx, ecx
0x18000fb0f  mov     rdi, rdx
0x18000fb12  call    WPDLibGetRegistryValue
0x18000fb17  test    eax, eax
0x18000fb19  jnz     short loc_18000FB62
0x18000fb1b  cmp     dword ptr [rsp+48h+Length], ebx
0x18000fb1f  jnz     short loc_18000FB50
0x18000fb21  mov     ebx, dword ptr [rsp+48h+Length]
0x18000fb25  mov     rcx, rdi; Source1
0x18000fb28  mov     rdx, [rsp+48h+Source2]; Source2
0x18000fb2d  mov     r8d, ebx; Length
0x18000fb30  call    cs:__imp_RtlCompareMemory
0x18000fb36  cmp     rax, rbx
0x18000fb39  jnz     short loc_18000FB50
0x18000fb3b  lea     rdx, aNoChangeInSecu; "No change in security descriptor\n"
0x18000fb42  mov     ecx, 8; unsigned int
0x18000fb47  call    ?GPDebugPrintX@@YAXKPEADZZ; GPDebugPrintX(ulong,char *,...)
0x18000fb4c  xor     ebx, ebx
0x18000fb4e  jmp     short loc_18000FB55
0x18000fb50  mov     ebx, 1
0x18000fb55  mov     rcx, [rsp+48h+Source2]; hMem
0x18000fb5a  call    cs:__imp_LocalFree
0x18000fb60  jmp     short loc_18000FB67
0x18000fb62  mov     ebx, 1
0x18000fb67  mov     eax, ebx
0x18000fb69  mov     rbx, [rsp+48h+arg_8]
0x18000fb6e  add     rsp, 40h
0x18000fb72  pop     rdi
0x18000fb73  retn
```
