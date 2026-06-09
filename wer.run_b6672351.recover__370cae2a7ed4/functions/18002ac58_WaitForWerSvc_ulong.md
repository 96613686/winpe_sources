# WaitForWerSvc(ulong)

- ea: `0x18002ac58`
- end: `0x18002ad24`
- name: `?WaitForWerSvc@@YAJK@Z`
- size: `204`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, loader_planting`

## callers

- `0x18001e2c0`

## callees

- `0x18002ac58`

## import_xrefs

- `ntdll!NtWaitForSingleObject` at `0x18002acf8`
- `ntdll!NtWaitForSingleObject` at `0x18002acf8`
- `ntdll!NtOpenEvent` at `0x18002acc0`
- `ntdll!NtOpenEvent` at `0x18002acc0`
- `ntdll!NtClose` at `0x18002ad0a`
- `ntdll!NtClose` at `0x18002ad0a`

## string_xrefs

- `0x18002ac65`: `\KernelObjects\SystemErrorPortReady`

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
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-30h] BYREF
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
0x18002ac58  mov     [rsp-8+arg_0], rbx
0x18002ac5d  push    rbp
0x18002ac5e  mov     rbp, rsp
0x18002ac61  sub     rsp, 60h
0x18002ac65  lea     rax, aKernelobjectsS; "\\KernelObjects\\SystemErrorPortReady"
0x18002ac6c  movsxd  rbx, ecx
0x18002ac6f  mov     [rbp+var_38], rax
0x18002ac73  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18002ac77  lea     rax, [rbp+var_40]
0x18002ac7b  mov     [rbp+var_40], 480046h
0x18002ac83  xorps   xmm0, xmm0
0x18002ac86  mov     [rbp+ObjectAttributes.ObjectName], rax
0x18002ac8a  mov     edx, 100001h; DesiredAccess
0x18002ac8f  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x18002ac97  lea     rcx, [rbp+EventHandle]; EventHandle
0x18002ac9b  mov     qword ptr [rbp+ObjectAttributes.Attributes], 0
0x18002aca3  mov     [rbp+EventHandle], 0
0x18002acab  mov     [rbp+arg_10], 0
0x18002acb3  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x18002acbb  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18002acc0  call    cs:__imp_NtOpenEvent
0x18002acc7  nop     dword ptr [rax+rax+00h]
0x18002accc  test    eax, eax
0x18002acce  js      short loc_18002AD18
0x18002acd0  cmp     ebx, 0FFFFFFFFh
0x18002acd3  jnz     short loc_18002ACD9
0x18002acd5  mov     dl, 1
0x18002acd7  jmp     short loc_18002ACE6
0x18002acd9  xor     dl, dl
0x18002acdb  imul    rcx, rbx, 0FFFFFFFFFFFFD8F0h
0x18002ace2  mov     [rbp+arg_10], rcx
0x18002ace6  mov     rcx, [rbp+EventHandle]; Handle
0x18002acea  lea     r8, [rbp+arg_10]
0x18002acee  xor     eax, eax
0x18002acf0  test    dl, dl
0x18002acf2  cmovnz  r8, rax; Timeout
0x18002acf6  xor     edx, edx; Alertable
0x18002acf8  call    cs:__imp_NtWaitForSingleObject
0x18002acff  nop     dword ptr [rax+rax+00h]
0x18002ad04  mov     rcx, [rbp+EventHandle]; Handle
0x18002ad08  mov     ebx, eax
0x18002ad0a  call    cs:__imp_NtClose
0x18002ad11  nop     dword ptr [rax+rax+00h]
0x18002ad16  mov     eax, ebx
0x18002ad18  mov     rbx, [rsp+60h+arg_0]
0x18002ad1d  add     rsp, 60h
0x18002ad21  pop     rbp
0x18002ad22  retn
```
