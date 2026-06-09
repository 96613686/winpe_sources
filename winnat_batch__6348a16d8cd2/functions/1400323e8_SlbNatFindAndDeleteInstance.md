# SlbNatFindAndDeleteInstance

- ea: `0x1400323e8`
- end: `0x1400324af`
- name: `SlbNatFindAndDeleteInstance`
- size: `199`
- prototype: `__int64 __fastcall(wchar_t *Str2)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14002f920`

## callees

- `0x14000d7f8`
- `0x14002fed8`
- `0x140031300`
- `0x1400323e8`
- `0x1400344f8`

## import_xrefs

- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140032453`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140032453`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x1400323f8`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x1400323f8`

## string_xrefs

- `0x140032479`: `Delete instance`

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
  __int64 v9; // r9
  int v10; // edx
  int v11; // r8d

  ExEnterCriticalRegionAndAcquireResourceExclusive(&Resource);
  Instance = (char *)SlbNatFindInstance(Str2);
  if ( Instance )
  {
    v4 = *(_QWORD *)Instance;
    if ( *(char **)(*(_QWORD *)Instance + 8LL) != Instance || (v5 = (char **)*((_QWORD *)Instance + 1), *v5 != Instance) )
      __fastfail(3u);
    *v5 = (char *)v4;
    *(_QWORD *)(v4 + 8) = v5;
    --dword_140026348;
    SlbNatDeleteInstance(Instance, 0);
    SlbNatCheckLastInstance(v7, v6, v8, v9);
    v3 = 0;
  }
  else
  {
    v3 = -1073741275;
  }
  ExReleaseResourceAndLeaveCriticalRegion(&Resource);
  if ( v3 < 0 && dword_140026104 == 1 && (byte_140026BED & 0x10) != 0 )
    McTemplateK0qzqq_EtwWriteTransfer(
      (unsigned int)&MICROSOFT_WINNAT_ETW_PROVIDER_Context,
      v10,
      v11,
      3003,
      (__int64)L"Delete instance",
      0,
      v3);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1400323e8  push    rbx
0x1400323ea  sub     rsp, 40h
0x1400323ee  mov     rbx, rcx
0x1400323f1  lea     rcx, Resource; Resource
0x1400323f8  call    cs:__imp_ExEnterCriticalRegionAndAcquireResourceExclusive
0x1400323ff  nop     dword ptr [rax+rax+00h]
0x140032404  mov     rcx, rbx; Str2
0x140032407  call    SlbNatFindInstance
0x14003240c  test    rax, rax
0x14003240f  jnz     short loc_140032418
0x140032411  mov     ebx, 0C0000225h
0x140032416  jmp     short loc_14003244C
0x140032418  mov     rdx, [rax]
0x14003241b  cmp     [rdx+8], rax
0x14003241f  jnz     loc_1400324A8
0x140032425  mov     r8, [rax+8]
0x140032429  cmp     [r8], rax
0x14003242c  jnz     short loc_1400324A8
0x14003242e  mov     [r8], rdx
0x140032431  mov     rcx, rax; P
0x140032434  mov     [rdx+8], r8
0x140032438  xor     edx, edx
0x14003243a  dec     cs:dword_140026348
0x140032440  call    SlbNatDeleteInstance
0x140032445  call    SlbNatCheckLastInstance
0x14003244a  xor     ebx, ebx
0x14003244c  lea     rcx, Resource; Resource
0x140032453  call    cs:__imp_ExReleaseResourceAndLeaveCriticalRegion
0x14003245a  nop     dword ptr [rax+rax+00h]
0x14003245f  test    ebx, ebx
0x140032461  jns     short loc_14003249F
0x140032463  cmp     cs:dword_140026104, 1
0x14003246a  jnz     short loc_14003249F
0x14003246c  test    cs:byte_140026BED, 10h
0x140032473  jz      short loc_14003249F
0x140032475  mov     [rsp+48h+var_18], ebx
0x140032479  lea     rax, aDeleteInstance; "Delete instance"
0x140032480  mov     [rsp+48h+var_20], 0
0x140032488  lea     rcx, MICROSOFT_WINNAT_ETW_PROVIDER_Context
0x14003248f  mov     r9d, 0BBBh
0x140032495  mov     [rsp+48h+var_28], rax
0x14003249a  call    McTemplateK0qzqq_EtwWriteTransfer
0x14003249f  mov     eax, ebx
0x1400324a1  add     rsp, 40h
0x1400324a5  pop     rbx
0x1400324a6  retn
0x1400324a8  mov     ecx, 3
0x1400324ad  int     29h; Win8: RtlFailFast(ecx)
```
