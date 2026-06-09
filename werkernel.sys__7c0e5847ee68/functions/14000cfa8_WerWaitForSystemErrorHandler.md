# WerWaitForSystemErrorHandler

- ea: `0x14000cfa8`
- end: `0x14000d06a`
- name: `WerWaitForSystemErrorHandler`
- size: `194`
- prototype: `NTSTATUS __fastcall(int)`
- caller_count: `2`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1400011a0`
- `0x1400100f4`

## callees

- `0x14000cfa8`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x14000d050`
- `ntoskrnl!ZwClose` at `0x14000d050`
- `ntoskrnl!ZwOpenEvent` at `0x14000d006`
- `ntoskrnl!ZwOpenEvent` at `0x14000d006`
- `ntoskrnl!ZwWaitForSingleObject` at `0x14000d03e`
- `ntoskrnl!ZwWaitForSingleObject` at `0x14000d03e`

## string_xrefs

- `0x14000cfb5`: `\KernelObjects\SystemErrorPortReady`

## pseudocode

```c
NTSTATUS __fastcall WerWaitForSystemErrorHandler(int a1)
{
  __int64 v1; // rbx
  NTSTATUS result; // eax
  char v3; // dl
  union _LARGE_INTEGER *v4; // r8
  NTSTATUS v5; // ebx
  _QWORD v6[2]; // [rsp+20h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-30h] BYREF
  void *EventHandle; // [rsp+78h] [rbp+18h] BYREF
  __int64 v9; // [rsp+80h] [rbp+20h] BYREF

  v1 = a1;
  v6[1] = L"\\KernelObjects\\SystemErrorPortReady";
  v6[0] = 4718662;
  EventHandle = 0;
  v9 = 0;
  ObjectAttributes.RootDirectory = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)v6;
  *(_QWORD *)&ObjectAttributes.Attributes = 512;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  result = ZwOpenEvent(&EventHandle, 0x100001u, &ObjectAttributes);
  if ( result >= 0 )
  {
    if ( (_DWORD)v1 == -1 )
    {
      v3 = 1;
    }
    else
    {
      v3 = 0;
      v9 = -10000 * v1;
    }
    v4 = (union _LARGE_INTEGER *)&v9;
    if ( v3 )
      v4 = 0;
    v5 = ZwWaitForSingleObject(EventHandle, 0, v4);
    ZwClose(EventHandle);
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x14000cfa8  mov     [rsp-8+arg_0], rbx
0x14000cfad  push    rbp
0x14000cfae  mov     rbp, rsp
0x14000cfb1  sub     rsp, 60h
0x14000cfb5  lea     rax, aKernelobjectsS; "\\KernelObjects\\SystemErrorPortReady"
0x14000cfbc  movsxd  rbx, ecx
0x14000cfbf  mov     [rbp+var_38], rax
0x14000cfc3  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14000cfc7  xor     eax, eax
0x14000cfc9  mov     [rbp+var_40], 480046h
0x14000cfd1  mov     [rbp+EventHandle], rax
0x14000cfd5  lea     rcx, [rbp+EventHandle]; EventHandle
0x14000cfd9  mov     [rbp+arg_10], rax
0x14000cfdd  xorps   xmm0, xmm0
0x14000cfe0  mov     [rbp+ObjectAttributes.RootDirectory], rax
0x14000cfe4  mov     edx, 100001h; DesiredAccess
0x14000cfe9  lea     rax, [rbp+var_40]
0x14000cfed  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x14000cff5  mov     [rbp+ObjectAttributes.ObjectName], rax
0x14000cff9  mov     qword ptr [rbp+ObjectAttributes.Attributes], 200h
0x14000d001  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14000d006  call    cs:__imp_ZwOpenEvent
0x14000d00d  nop     dword ptr [rax+rax+00h]
0x14000d012  test    eax, eax
0x14000d014  js      short loc_14000D05E
0x14000d016  cmp     ebx, 0FFFFFFFFh
0x14000d019  jnz     short loc_14000D01F
0x14000d01b  mov     dl, 1
0x14000d01d  jmp     short loc_14000D02C
0x14000d01f  xor     dl, dl
0x14000d021  imul    rcx, rbx, 0FFFFFFFFFFFFD8F0h
0x14000d028  mov     [rbp+arg_10], rcx
0x14000d02c  mov     rcx, [rbp+EventHandle]; Handle
0x14000d030  lea     r8, [rbp+arg_10]
0x14000d034  xor     eax, eax
0x14000d036  test    dl, dl
0x14000d038  cmovnz  r8, rax; Timeout
0x14000d03c  xor     edx, edx; Alertable
0x14000d03e  call    cs:__imp_ZwWaitForSingleObject
0x14000d045  nop     dword ptr [rax+rax+00h]
0x14000d04a  mov     rcx, [rbp+EventHandle]; Handle
0x14000d04e  mov     ebx, eax
0x14000d050  call    cs:__imp_ZwClose
0x14000d057  nop     dword ptr [rax+rax+00h]
0x14000d05c  mov     eax, ebx
0x14000d05e  mov     rbx, [rsp+60h+arg_0]
0x14000d063  add     rsp, 60h
0x14000d067  pop     rbp
0x14000d068  retn
```
