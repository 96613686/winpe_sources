# DVRSourceSink::ReaderEventExists(_GUID *,int *)

- ea: `0x180006f20`
- end: `0x180006fb4`
- name: `?ReaderEventExists@DVRSourceSink@@YAJPEAU_GUID@@PEAH@Z`
- size: `148`
- prototype: `__int64 __fastcall(DVRSourceSink *__hidden this, struct _GUID *, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180005df0`

## callees

- `0x1800015f0`
- `0x1800057f4`
- `0x180006f20`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180006f78`
- `KERNEL32!CloseHandle` at `0x180006f78`
- `KERNEL32!GetLastError` at `0x180006f80`
- `KERNEL32!GetLastError` at `0x180006f80`
- `KERNEL32!OpenEventW` at `0x180006f64`
- `KERNEL32!OpenEventW` at `0x180006f64`

## pseudocode

```c
__int64 __fastcall DVRSourceSink::ReaderEventExists(GUID *this, struct _GUID *a2, int *a3, unsigned __int16 *a4)
{
  int ReaderIdEventName; // edi
  HANDLE v6; // rax
  WCHAR Name[264]; // [rsp+20h] [rbp-228h] BYREF

  a2->Data1 = 1;
  ReaderIdEventName = DVRSourceSink::CreateReaderIdEventName(this, a2, (unsigned __int64)Name, a4);
  if ( ReaderIdEventName >= 0 )
  {
    v6 = OpenEventW(0x100000u, 0, Name);
    if ( v6 )
    {
      a2->Data1 = 1;
      CloseHandle(v6);
    }
    else if ( GetLastError() == 2 )
    {
      a2->Data1 = 0;
    }
  }
  return (unsigned int)ReaderIdEventName;
}

```

## disassembly

```asm
0x180006f20  mov     [rsp+arg_10], rbx
0x180006f25  push    rdi
0x180006f26  sub     rsp, 240h
0x180006f2d  mov     rax, cs:__security_cookie
0x180006f34  xor     rax, rsp
0x180006f37  mov     [rsp+248h+var_18], rax
0x180006f3f  lea     r8, [rsp+248h+Name]; unsigned __int64
0x180006f44  mov     dword ptr [rdx], 1
0x180006f4a  mov     rbx, rdx
0x180006f4d  call    ?CreateReaderIdEventName@DVRSourceSink@@YAJPEAU_GUID@@_KPEAG@Z; DVRSourceSink::CreateReaderIdEventName(_GUID *,unsigned __int64,ushort *)
0x180006f52  mov     edi, eax
0x180006f54  test    eax, eax
0x180006f56  js      short loc_180006F91
0x180006f58  lea     r8, [rsp+248h+Name]; lpName
0x180006f5d  xor     edx, edx; bInheritHandle
0x180006f5f  mov     ecx, 100000h; dwDesiredAccess
0x180006f64  call    cs:__imp_OpenEventW
0x180006f6a  test    rax, rax
0x180006f6d  jz      short loc_180006F80
0x180006f6f  mov     rcx, rax; hObject
0x180006f72  mov     dword ptr [rbx], 1
0x180006f78  call    cs:__imp_CloseHandle
0x180006f7e  jmp     short loc_180006F91
0x180006f80  call    cs:__imp_GetLastError
0x180006f86  cmp     eax, 2
0x180006f89  jnz     short loc_180006F91
0x180006f8b  mov     dword ptr [rbx], 0
0x180006f91  mov     eax, edi
0x180006f93  mov     rcx, [rsp+248h+var_18]
0x180006f9b  xor     rcx, rsp; StackCookie
0x180006f9e  call    __security_check_cookie
0x180006fa3  mov     rbx, [rsp+248h+arg_10]
0x180006fab  add     rsp, 240h
0x180006fb2  pop     rdi
0x180006fb3  retn
```
