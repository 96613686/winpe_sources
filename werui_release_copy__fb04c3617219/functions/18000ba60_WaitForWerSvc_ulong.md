# WaitForWerSvc(ulong)

- ea: `0x18000ba60`
- end: `0x18000bb19`
- name: `?WaitForWerSvc@@YAJK@Z`
- size: `185`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, loader_planting`

## callers

- `0x18000bb20`

## callees

- `0x18000ba60`

## import_xrefs

- `ntdll!NtOpenEvent` at `0x18000bac8`
- `ntdll!NtOpenEvent` at `0x18000bac8`
- `ntdll!NtWaitForSingleObject` at `0x18000bafa`
- `ntdll!NtWaitForSingleObject` at `0x18000bafa`
- `ntdll!NtClose` at `0x18000bb06`
- `ntdll!NtClose` at `0x18000bb06`

## string_xrefs

- `0x18000ba6d`: `\KernelObjects\SystemErrorPortReady`

## pseudocode

```c
NTSTATUS __fastcall WaitForWerSvc(int a1)
{
  __int64 v1; // rbx
  NTSTATUS result; // eax
  char v3; // dl
  union _LARGE_INTEGER *v4; // r8
  NTSTATUS v5; // ebx
  _QWORD v6[2]; // [rsp+20h] [rbp-40h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-30h] BYREF
  void *EventHandle; // [rsp+78h] [rbp+18h] BYREF
  __int64 v9; // [rsp+80h] [rbp+20h] BYREF

  v1 = a1;
  v6[1] = L"\\KernelObjects\\SystemErrorPortReady";
  v6[0] = 4718662;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)v6;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  memset(&ObjectAttributes.Attributes, 0, 24);
  EventHandle = 0;
  v9 = 0;
  ObjectAttributes.RootDirectory = 0;
  result = NtOpenEvent(&EventHandle, 0x100001u, &ObjectAttributes);
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
    v5 = NtWaitForSingleObject(EventHandle, 0, v4);
    NtClose(EventHandle);
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x18000ba60  mov     [rsp-8+arg_0], rbx
0x18000ba65  push    rbp
0x18000ba66  mov     rbp, rsp
0x18000ba69  sub     rsp, 60h
0x18000ba6d  lea     rax, aKernelobjectsS; "\\KernelObjects\\SystemErrorPortReady"
0x18000ba74  movsxd  rbx, ecx
0x18000ba77  mov     [rbp+var_38], rax
0x18000ba7b  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18000ba7f  lea     rax, [rbp+var_40]
0x18000ba83  mov     [rbp+var_40], 480046h
0x18000ba8b  xorps   xmm0, xmm0
0x18000ba8e  mov     [rbp+ObjectAttributes.ObjectName], rax
0x18000ba92  mov     edx, 100001h; DesiredAccess
0x18000ba97  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x18000ba9f  lea     rcx, [rbp+EventHandle]; EventHandle
0x18000baa3  mov     qword ptr [rbp+ObjectAttributes.Attributes], 0
0x18000baab  mov     [rbp+EventHandle], 0
0x18000bab3  mov     [rbp+arg_10], 0
0x18000babb  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x18000bac3  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18000bac8  call    cs:__imp_NtOpenEvent
0x18000bace  test    eax, eax
0x18000bad0  js      short loc_18000BB0E
0x18000bad2  cmp     ebx, 0FFFFFFFFh
0x18000bad5  jnz     short loc_18000BADB
0x18000bad7  mov     dl, 1
0x18000bad9  jmp     short loc_18000BAE8
0x18000badb  xor     dl, dl
0x18000badd  imul    rcx, rbx, 0FFFFFFFFFFFFD8F0h
0x18000bae4  mov     [rbp+arg_10], rcx
0x18000bae8  mov     rcx, [rbp+EventHandle]; Handle
0x18000baec  lea     r8, [rbp+arg_10]
0x18000baf0  xor     eax, eax
0x18000baf2  test    dl, dl
0x18000baf4  cmovnz  r8, rax; Timeout
0x18000baf8  xor     edx, edx; Alertable
0x18000bafa  call    cs:__imp_NtWaitForSingleObject
0x18000bb00  mov     rcx, [rbp+EventHandle]; Handle
0x18000bb04  mov     ebx, eax
0x18000bb06  call    cs:__imp_NtClose
0x18000bb0c  mov     eax, ebx
0x18000bb0e  mov     rbx, [rsp+60h+arg_0]
0x18000bb13  add     rsp, 60h
0x18000bb17  pop     rbp
0x18000bb18  retn
```
