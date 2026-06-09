# SlbNatFindAndDeleteInstance

- ea: `0x140033518`
- end: `0x1400335df`
- name: `SlbNatFindAndDeleteInstance`
- size: `199`
- prototype: `__int64 __fastcall(wchar_t *Str2)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140030a50`

## callees

- `0x14000d7c8`
- `0x140031008`
- `0x140032430`
- `0x140033518`
- `0x140035808`

## import_xrefs

- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140033583`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140033583`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x140033528`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x140033528`

## string_xrefs

- `0x1400335a9`: `Delete instance`

## pseudocode

```c
__int64 __fastcall SlbNatFindAndDeleteInstance(wchar_t *Str2)
{
  char *Instance; // rax
  int v3; // ebx
  __int64 v4; // rdx
  char **v5; // r8
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // r8
  int v9; // edx
  int v10; // r8d

  ExEnterCriticalRegionAndAcquireResourceExclusive(&Resource);
  Instance = (char *)SlbNatFindInstance(Str2);
  if ( Instance )
  {
    v4 = *(_QWORD *)Instance;
    if ( *(char **)(*(_QWORD *)Instance + 8LL) != Instance || (v5 = (char **)*((_QWORD *)Instance + 1), *v5 != Instance) )
      __fastfail(3u);
    *v5 = (char *)v4;
    *(_QWORD *)(v4 + 8) = v5;
    --dword_140027348;
    SlbNatDeleteInstance(Instance, 0);
    SlbNatCheckLastInstance(v7, v6, v8);
    v3 = 0;
  }
  else
  {
    v3 = -1073741275;
  }
  ExReleaseResourceAndLeaveCriticalRegion(&Resource);
  if ( v3 < 0 && dword_140027104 == 1 && (byte_140027BED & 0x10) != 0 )
    McTemplateK0qzqq_EtwWriteTransfer(
      (unsigned int)&MICROSOFT_WINNAT_ETW_PROVIDER_Context,
      v9,
      v10,
      3003,
      (__int64)L"Delete instance",
      0,
      v3);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x140033518  push    rbx
0x14003351a  sub     rsp, 40h
0x14003351e  mov     rbx, rcx
0x140033521  lea     rcx, Resource; Resource
0x140033528  call    cs:__imp_ExEnterCriticalRegionAndAcquireResourceExclusive
0x14003352f  nop     dword ptr [rax+rax+00h]
0x140033534  mov     rcx, rbx; Str2
0x140033537  call    SlbNatFindInstance
0x14003353c  test    rax, rax
0x14003353f  jnz     short loc_140033548
0x140033541  mov     ebx, 0C0000225h
0x140033546  jmp     short loc_14003357C
0x140033548  mov     rdx, [rax]
0x14003354b  cmp     [rdx+8], rax
0x14003354f  jnz     loc_1400335D8
0x140033555  mov     r8, [rax+8]
0x140033559  cmp     [r8], rax
0x14003355c  jnz     short loc_1400335D8
0x14003355e  mov     [r8], rdx
0x140033561  mov     rcx, rax; P
0x140033564  mov     [rdx+8], r8
0x140033568  xor     edx, edx
0x14003356a  dec     cs:dword_140027348
0x140033570  call    SlbNatDeleteInstance
0x140033575  call    SlbNatCheckLastInstance
0x14003357a  xor     ebx, ebx
0x14003357c  lea     rcx, Resource; Resource
0x140033583  call    cs:__imp_ExReleaseResourceAndLeaveCriticalRegion
0x14003358a  nop     dword ptr [rax+rax+00h]
0x14003358f  test    ebx, ebx
0x140033591  jns     short loc_1400335CF
0x140033593  cmp     cs:dword_140027104, 1
0x14003359a  jnz     short loc_1400335CF
0x14003359c  test    cs:byte_140027BED, 10h
0x1400335a3  jz      short loc_1400335CF
0x1400335a5  mov     [rsp+48h+var_18], ebx
0x1400335a9  lea     rax, aDeleteInstance; "Delete instance"
0x1400335b0  mov     [rsp+48h+var_20], 0
0x1400335b8  lea     rcx, MICROSOFT_WINNAT_ETW_PROVIDER_Context
0x1400335bf  mov     r9d, 0BBBh
0x1400335c5  mov     [rsp+48h+var_28], rax
0x1400335ca  call    McTemplateK0qzqq_EtwWriteTransfer
0x1400335cf  mov     eax, ebx
0x1400335d1  add     rsp, 40h
0x1400335d5  pop     rbx
0x1400335d6  retn
0x1400335d8  mov     ecx, 3
0x1400335dd  int     29h; Win8: RtlFailFast(ecx)
```
