# SmpUnhandledExceptionFilter

- ea: `0x140017e28`
- end: `0x140017ebd`
- name: `SmpUnhandledExceptionFilter`
- size: `149`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140001880`
- `0x140005f64`
- `0x140017c70`

## callees

- `0x140003114`
- `0x140017d5c`
- `0x140017e28`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x140017e5c`
- `ntdll!RtlInitUnicodeString` at `0x140017e5c`

## pseudocode

```c
__int64 __fastcall SmpUnhandledExceptionFilter(int **a1)
{
  int *v3; // r8
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-38h] BYREF
  unsigned __int64 Parameters[5]; // [rsp+40h] [rbp-28h] BYREF

  DestinationString = 0;
  if ( *(_BYTE *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 2LL) != 1 )
  {
    RtlInitUnicodeString(&DestinationString, L"Unhandled Exception in Session Manager");
    v3 = *a1;
    Parameters[0] = (unsigned __int64)&DestinationString;
    Parameters[1] = *v3;
    Parameters[2] = *((_QWORD *)v3 + 2);
    Parameters[3] = (unsigned __int64)a1[1];
    SmLogFailureInt((__int64)"SmpUnhandledExceptionFilter", 0x2EAu, *((_QWORD *)v3 + 4), *((_QWORD *)v3 + 2), *v3);
    SmpTerminate(Parameters, 1u, 4u);
  }
  return 0;
}

```

## disassembly

```asm
0x140017e28  push    rbx
0x140017e2a  sub     rsp, 60h
0x140017e2e  xorps   xmm0, xmm0
0x140017e31  mov     rbx, rcx
0x140017e34  movups  xmmword ptr [rsp+68h+DestinationString.Length], xmm0
0x140017e39  mov     rax, gs:60h
0x140017e42  cmp     byte ptr [rax+2], 1
0x140017e46  jnz     short loc_140017E50
0x140017e48  xor     eax, eax
0x140017e4a  add     rsp, 60h
0x140017e4e  pop     rbx
0x140017e4f  retn
0x140017e50  lea     rdx, aUnhandledExcep; "Unhandled Exception in Session Manager"
0x140017e57  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x140017e5c  call    cs:__imp_RtlInitUnicodeString
0x140017e62  mov     r8, [rbx]
0x140017e65  lea     rax, [rsp+68h+DestinationString]
0x140017e6a  mov     [rsp+68h+Parameters], rax
0x140017e6f  lea     rcx, aSmpunhandledex; "SmpUnhandledExceptionFilter"
0x140017e76  mov     edx, 2EAh
0x140017e7b  movsxd  rax, dword ptr [r8]
0x140017e7e  mov     [rsp+68h+var_20], rax
0x140017e83  mov     rax, [r8+10h]
0x140017e87  mov     [rsp+68h+var_18], rax
0x140017e8c  mov     rax, [rbx+8]
0x140017e90  mov     [rsp+68h+var_10], rax
0x140017e95  mov     eax, [r8]
0x140017e98  mov     r9, [r8+10h]
0x140017e9c  mov     r8, [r8+20h]
0x140017ea0  mov     [rsp+68h+var_48], eax
0x140017ea4  call    SmLogFailureInt
0x140017ea9  mov     edx, 1; UnicodeStringParameterMask
0x140017eae  lea     rcx, [rsp+68h+Parameters]; Parameters
0x140017eb3  lea     r8d, [rdx+3]; NumberOfParameters
0x140017eb7  call    SmpTerminate
```
