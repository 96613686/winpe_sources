# SlbNatFindAndDeleteExternalAddress

- ea: `0x140033444`
- end: `0x140033510`
- name: `SlbNatFindAndDeleteExternalAddress`
- size: `204`
- prototype: `__int64 __fastcall(wchar_t *Str2)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1400309b0`

## callees

- `0x14000d7c8`
- `0x140032228`
- `0x140033444`
- `0x140035808`
- `0x140035948`

## import_xrefs

- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x1400334b4`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x1400334b4`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x140033454`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x140033454`

## string_xrefs

- `0x1400334da`: `Delete external address`

## pseudocode

```c
__int64 __fastcall SlbNatFindAndDeleteExternalAddress(wchar_t *Str2)
{
  __int64 Instance; // rax
  int v3; // ebx
  char *ExternalAddress; // rax
  __int64 v5; // r9
  __int64 v6; // rdx
  char **v7; // r8
  int v8; // edx
  int v9; // r8d

  ExEnterCriticalRegionAndAcquireResourceExclusive(&Resource);
  Instance = SlbNatFindInstance(Str2);
  if ( Instance && (ExternalAddress = (char *)SlbNatFindExternalAddress(Instance, *((unsigned int *)Str2 + 20))) != 0 )
  {
    v6 = *(_QWORD *)ExternalAddress;
    if ( *(char **)(*(_QWORD *)ExternalAddress + 8LL) != ExternalAddress
      || (v7 = (char **)*((_QWORD *)ExternalAddress + 1), *v7 != ExternalAddress) )
    {
      __fastfail(3u);
    }
    *v7 = (char *)v6;
    v3 = 0;
    *(_QWORD *)(v6 + 8) = v7;
    SlbNatDeleteExternalAddress(ExternalAddress, v5);
  }
  else
  {
    v3 = -1073741275;
  }
  ExReleaseResourceAndLeaveCriticalRegion(&Resource);
  if ( v3 < 0 && dword_140027104 == 1 && (byte_140027BED & 0x10) != 0 )
    McTemplateK0qzqq_EtwWriteTransfer(
      (unsigned int)&MICROSOFT_WINNAT_ETW_PROVIDER_Context,
      v8,
      v9,
      3006,
      (__int64)L"Delete external address",
      0,
      v3);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x140033444  push    rbx
0x140033446  sub     rsp, 40h
0x14003344a  mov     rbx, rcx
0x14003344d  lea     rcx, Resource; Resource
0x140033454  call    cs:__imp_ExEnterCriticalRegionAndAcquireResourceExclusive
0x14003345b  nop     dword ptr [rax+rax+00h]
0x140033460  mov     rcx, rbx; Str2
0x140033463  call    SlbNatFindInstance
0x140033468  mov     r9, rax
0x14003346b  test    rax, rax
0x14003346e  jnz     short loc_140033477
0x140033470  mov     ebx, 0C0000225h
0x140033475  jmp     short loc_1400334AD
0x140033477  mov     edx, [rbx+50h]
0x14003347a  mov     rcx, r9
0x14003347d  call    SlbNatFindExternalAddress
0x140033482  test    rax, rax
0x140033485  jz      short loc_140033470
0x140033487  mov     rdx, [rax]
0x14003348a  cmp     [rdx+8], rax
0x14003348e  jnz     short loc_140033509
0x140033490  mov     r8, [rax+8]
0x140033494  cmp     [r8], rax
0x140033497  jnz     short loc_140033509
0x140033499  mov     [r8], rdx
0x14003349c  xor     ebx, ebx
0x14003349e  mov     [rdx+8], r8
0x1400334a2  mov     rcx, rax; P
0x1400334a5  mov     rdx, r9
0x1400334a8  call    SlbNatDeleteExternalAddress
0x1400334ad  lea     rcx, Resource; Resource
0x1400334b4  call    cs:__imp_ExReleaseResourceAndLeaveCriticalRegion
0x1400334bb  nop     dword ptr [rax+rax+00h]
0x1400334c0  test    ebx, ebx
0x1400334c2  jns     short loc_140033500
0x1400334c4  cmp     cs:dword_140027104, 1
0x1400334cb  jnz     short loc_140033500
0x1400334cd  test    cs:byte_140027BED, 10h
0x1400334d4  jz      short loc_140033500
0x1400334d6  mov     [rsp+48h+var_18], ebx
0x1400334da  lea     rax, aDeleteExternal; "Delete external address"
0x1400334e1  mov     [rsp+48h+var_20], 0
0x1400334e9  lea     rcx, MICROSOFT_WINNAT_ETW_PROVIDER_Context
0x1400334f0  mov     r9d, 0BBEh
0x1400334f6  mov     [rsp+48h+var_28], rax
0x1400334fb  call    McTemplateK0qzqq_EtwWriteTransfer
0x140033500  mov     eax, ebx
0x140033502  add     rsp, 40h
0x140033506  pop     rbx
0x140033507  retn
0x140033509  mov     ecx, 3
0x14003350e  int     29h; Win8: RtlFailFast(ecx)
```
