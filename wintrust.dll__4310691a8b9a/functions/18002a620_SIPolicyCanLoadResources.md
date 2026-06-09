# SIPolicyCanLoadResources

- ea: `0x18002a620`
- end: `0x18002a730`
- name: `SIPolicyCanLoadResources`
- size: `272`
- prototype: `__int64 __fastcall(PVOID BaseAddress, ULONGLONG Size)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x18002737c`

## callees

- `0x18002a620`
- `0x18004bf28`
- `0x18004c048`

## import_xrefs

- `ntdll!RtlImageNtHeaderEx` at `0x18002a646`
- `ntdll!RtlImageNtHeaderEx` at `0x18002a646`

## pseudocode

```c
NTSTATUS __fastcall SIPolicyCanLoadResources(PVOID BaseAddress, ULONGLONG Size)
{
  NTSTATUS result; // eax
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // r8
  __int64 v8; // r8
  int v9; // r9d
  unsigned int v10; // edx
  __int64 v11; // rax
  __int64 v12; // [rsp+38h] [rbp-10h] BYREF
  PIMAGE_NT_HEADERS NtHeader; // [rsp+68h] [rbp+20h] BYREF

  NtHeader = 0;
  result = RtlImageNtHeaderEx(0, BaseAddress, Size, &NtHeader);
  if ( result >= 0 )
  {
    result = SIPolicyIsBlockWithinImage(BaseAddress, Size, NtHeader, 26);
    if ( result >= 0 )
    {
      if ( *(_WORD *)(v7 + 24) == 267 )
      {
        result = SIPolicyIsBlockWithinImage(v6, v5, v7, 248);
        if ( result < 0 )
          return result;
        v10 = *(_DWORD *)(v8 + 116);
        v11 = *(_QWORD *)(v8 + 136);
      }
      else
      {
        if ( *(_WORD *)(v7 + 24) != 523 )
          return -1073741701;
        result = SIPolicyIsBlockWithinImage(BaseAddress, Size, v7, 264);
        if ( result < 0 )
          return result;
        v10 = *(_DWORD *)(v8 + 132);
        v11 = *(_QWORD *)(v8 + 152);
      }
      v12 = v11;
      if ( v10 > 2 && (_DWORD)v11 && HIDWORD(v11) )
        return SIPolicyFindNtSection((_DWORD)BaseAddress, Size, v8, v9, v11, (__int64)&v12);
      else
        return -1073741275;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18002a620  mov     [rsp+arg_0], rbx
0x18002a625  push    rdi
0x18002a626  sub     rsp, 40h
0x18002a62a  mov     rbx, rdx
0x18002a62d  mov     rdi, rcx
0x18002a630  mov     [rsp+48h+NtHeader], 0
0x18002a639  lea     r9, [rsp+48h+NtHeader]; NtHeader
0x18002a63e  mov     r8, rdx; Size
0x18002a641  mov     rdx, rcx; BaseAddress
0x18002a644  xor     ecx, ecx; Flags
0x18002a646  call    cs:__imp_RtlImageNtHeaderEx
0x18002a64c  mov     [rsp+48h+var_18], eax
0x18002a650  test    eax, eax
0x18002a652  js      loc_18002A71F
0x18002a658  mov     r9d, 1Ah
0x18002a65e  mov     r8, [rsp+48h+NtHeader]
0x18002a663  mov     rdx, rbx
0x18002a666  mov     rcx, rdi
0x18002a669  call    SIPolicyIsBlockWithinImage
0x18002a66e  mov     [rsp+48h+var_18], eax
0x18002a672  test    eax, eax
0x18002a674  js      loc_18002A71F
0x18002a67a  mov     eax, 10Bh
0x18002a67f  cmp     [r8+18h], ax
0x18002a684  jnz     short loc_18002A6A8
0x18002a686  lea     r9d, [rax-13h]
0x18002a68a  call    SIPolicyIsBlockWithinImage
0x18002a68f  mov     [rsp+48h+var_18], eax
0x18002a693  test    eax, eax
0x18002a695  js      loc_18002A71F
0x18002a69b  mov     edx, [r8+74h]
0x18002a69f  mov     rax, [r8+88h]
0x18002a6a6  jmp     short loc_18002A6DB
0x18002a6a8  mov     eax, 20Bh
0x18002a6ad  cmp     [r8+18h], ax
0x18002a6b2  jnz     short loc_18002A716
0x18002a6b4  mov     r9d, 108h
0x18002a6ba  mov     rdx, rbx
0x18002a6bd  mov     rcx, rdi
0x18002a6c0  call    SIPolicyIsBlockWithinImage
0x18002a6c5  mov     [rsp+48h+var_18], eax
0x18002a6c9  test    eax, eax
0x18002a6cb  js      short loc_18002A71F
0x18002a6cd  mov     edx, [r8+84h]
0x18002a6d4  mov     rax, [r8+98h]
0x18002a6db  mov     rcx, rax
0x18002a6de  mov     [rsp+48h+var_10], rax
0x18002a6e3  cmp     edx, 2
0x18002a6e6  jbe     short loc_18002A70F
0x18002a6e8  test    eax, eax
0x18002a6ea  jz      short loc_18002A70F
0x18002a6ec  shr     rcx, 20h
0x18002a6f0  test    ecx, ecx
0x18002a6f2  jz      short loc_18002A70F
0x18002a6f4  lea     rcx, [rsp+48h+var_10]
0x18002a6f9  mov     [rsp+48h+var_20], rcx
0x18002a6fe  mov     [rsp+48h+var_28], eax
0x18002a702  mov     rdx, rbx
0x18002a705  mov     rcx, rdi
0x18002a708  call    SIPolicyFindNtSection
0x18002a70d  jmp     short loc_18002A71B
0x18002a70f  mov     eax, 0C0000225h
0x18002a714  jmp     short loc_18002A71B
0x18002a716  mov     eax, 0C000007Bh
0x18002a71b  mov     [rsp+48h+var_18], eax
0x18002a71f  jmp     short loc_18002A725
0x18002a721  mov     [rsp+48h+var_18], eax
0x18002a725  mov     rbx, [rsp+48h+arg_0]
0x18002a72a  add     rsp, 40h
0x18002a72e  pop     rdi
0x18002a72f  retn
```
