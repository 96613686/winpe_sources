# SIPolicyCanLoadResources

- ea: `0x180020460`
- end: `0x180020570`
- name: `SIPolicyCanLoadResources`
- size: `272`
- prototype: `__int64 __fastcall(PVOID BaseAddress, ULONGLONG Size)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180013a24`

## callees

- `0x180017558`
- `0x180020460`
- `0x180039594`

## import_xrefs

- `ntdll!RtlImageNtHeaderEx` at `0x180020486`
- `ntdll!RtlImageNtHeaderEx` at `0x180020486`

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
0x180020460  mov     [rsp+arg_0], rbx
0x180020465  push    rdi
0x180020466  sub     rsp, 40h
0x18002046a  mov     rbx, rdx
0x18002046d  mov     rdi, rcx
0x180020470  mov     [rsp+48h+NtHeader], 0
0x180020479  lea     r9, [rsp+48h+NtHeader]; NtHeader
0x18002047e  mov     r8, rdx; Size
0x180020481  mov     rdx, rcx; BaseAddress
0x180020484  xor     ecx, ecx; Flags
0x180020486  call    cs:__imp_RtlImageNtHeaderEx
0x18002048c  mov     [rsp+48h+var_18], eax
0x180020490  test    eax, eax
0x180020492  js      loc_18002055F
0x180020498  mov     r9d, 1Ah
0x18002049e  mov     r8, [rsp+48h+NtHeader]
0x1800204a3  mov     rdx, rbx
0x1800204a6  mov     rcx, rdi
0x1800204a9  call    SIPolicyIsBlockWithinImage
0x1800204ae  mov     [rsp+48h+var_18], eax
0x1800204b2  test    eax, eax
0x1800204b4  js      loc_18002055F
0x1800204ba  mov     eax, 10Bh
0x1800204bf  cmp     [r8+18h], ax
0x1800204c4  jnz     short loc_1800204E8
0x1800204c6  lea     r9d, [rax-13h]
0x1800204ca  call    SIPolicyIsBlockWithinImage
0x1800204cf  mov     [rsp+48h+var_18], eax
0x1800204d3  test    eax, eax
0x1800204d5  js      loc_18002055F
0x1800204db  mov     edx, [r8+74h]
0x1800204df  mov     rax, [r8+88h]
0x1800204e6  jmp     short loc_18002051B
0x1800204e8  mov     eax, 20Bh
0x1800204ed  cmp     [r8+18h], ax
0x1800204f2  jnz     short loc_180020556
0x1800204f4  mov     r9d, 108h
0x1800204fa  mov     rdx, rbx
0x1800204fd  mov     rcx, rdi
0x180020500  call    SIPolicyIsBlockWithinImage
0x180020505  mov     [rsp+48h+var_18], eax
0x180020509  test    eax, eax
0x18002050b  js      short loc_18002055F
0x18002050d  mov     edx, [r8+84h]
0x180020514  mov     rax, [r8+98h]
0x18002051b  mov     rcx, rax
0x18002051e  mov     [rsp+48h+var_10], rax
0x180020523  cmp     edx, 2
0x180020526  jbe     short loc_18002054F
0x180020528  test    eax, eax
0x18002052a  jz      short loc_18002054F
0x18002052c  shr     rcx, 20h
0x180020530  test    ecx, ecx
0x180020532  jz      short loc_18002054F
0x180020534  lea     rcx, [rsp+48h+var_10]
0x180020539  mov     [rsp+48h+var_20], rcx
0x18002053e  mov     [rsp+48h+var_28], eax
0x180020542  mov     rdx, rbx
0x180020545  mov     rcx, rdi
0x180020548  call    SIPolicyFindNtSection
0x18002054d  jmp     short loc_18002055B
0x18002054f  mov     eax, 0C0000225h
0x180020554  jmp     short loc_18002055B
0x180020556  mov     eax, 0C000007Bh
0x18002055b  mov     [rsp+48h+var_18], eax
0x18002055f  jmp     short loc_180020565
0x180020561  mov     [rsp+48h+var_18], eax
0x180020565  mov     rbx, [rsp+48h+arg_0]
0x18002056a  add     rsp, 40h
0x18002056e  pop     rdi
0x18002056f  retn
```
