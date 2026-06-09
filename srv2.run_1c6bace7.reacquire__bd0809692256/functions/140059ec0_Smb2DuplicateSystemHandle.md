# Smb2DuplicateSystemHandle

- ea: `0x140059ec0`
- end: `0x140059f96`
- name: `Smb2DuplicateSystemHandle`
- size: `214`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140076e38`

## callees

- `0x140059ec0`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140059f77`
- `ntoskrnl!ZwClose` at `0x140059f77`
- `ntoskrnl!ObOpenObjectByPointer` at `0x140059f1e`
- `ntoskrnl!ObOpenObjectByPointer` at `0x140059f1e`
- `ntoskrnl!ZwDuplicateObject` at `0x140059f64`
- `ntoskrnl!ZwDuplicateObject` at `0x140059f64`

## pseudocode

```c
NTSTATUS __fastcall Smb2DuplicateSystemHandle(__int64 a1, void *a2, void **a3, char a4)
{
  NTSTATUS result; // eax
  NTSTATUS v8; // ebx
  HANDLE SourceProcessHandle; // [rsp+50h] [rbp+8h] BYREF

  SourceProcessHandle = 0;
  if ( !a3 )
    return -1073741811;
  result = ObOpenObjectByPointer(Srv2ServerProcess, 0x200u, 0, 0, 0, 0, &SourceProcessHandle);
  if ( result >= 0 )
  {
    v8 = ZwDuplicateObject(
           SourceProcessHandle,
           a2,
           (HANDLE)0xFFFFFFFFFFFFFFFFLL,
           a3,
           0,
           a4 != 0 ? 0x200 : 0,
           a4 != 0 ? 2 : 6);
    ZwClose(SourceProcessHandle);
    return v8;
  }
  return result;
}

```

## disassembly

```asm
0x140059ec0  mov     rax, rsp
0x140059ec3  mov     [rax+10h], rbx
0x140059ec7  mov     [rax+18h], rsi
0x140059ecb  mov     [rax+8], rcx
0x140059ecf  push    rdi
0x140059ed0  sub     rsp, 40h
0x140059ed4  mov     qword ptr [rax+8], 0
0x140059edc  mov     dil, r9b
0x140059edf  mov     rbx, r8
0x140059ee2  mov     rsi, rdx
0x140059ee5  test    r8, r8
0x140059ee8  jnz     short loc_140059EF4
0x140059eea  mov     eax, 0C000000Dh
0x140059eef  jmp     loc_140059F85
0x140059ef4  mov     rcx, cs:Srv2ServerProcess; Object
0x140059efb  lea     rax, [rsp+48h+SourceProcessHandle]
0x140059f00  mov     [rsp+48h+Handle], rax; Handle
0x140059f05  xor     r9d, r9d; DesiredAccess
0x140059f08  mov     [rsp+48h+AccessMode], 0; AccessMode
0x140059f0d  xor     r8d, r8d; PassedAccessState
0x140059f10  mov     edx, 200h; HandleAttributes
0x140059f15  mov     [rsp+48h+ObjectType], 0; ObjectType
0x140059f1e  call    cs:__imp_ObOpenObjectByPointer
0x140059f25  nop     dword ptr [rax+rax+00h]
0x140059f2a  test    eax, eax
0x140059f2c  js      short loc_140059F85
0x140059f2e  mov     al, dil
0x140059f31  mov     r9, rbx; TargetHandle
0x140059f34  neg     al
0x140059f36  mov     rdx, rsi; SourceHandle
0x140059f39  sbb     ecx, ecx
0x140059f3b  and     ecx, 0FFFFFFFCh
0x140059f3e  add     ecx, 6
0x140059f41  mov     dword ptr [rsp+48h+Handle], ecx; Options
0x140059f45  neg     dil
0x140059f48  mov     rcx, [rsp+48h+SourceProcessHandle]; SourceProcessHandle
0x140059f4d  sbb     eax, eax
0x140059f4f  or      r8, 0FFFFFFFFFFFFFFFFh; TargetProcessHandle
0x140059f53  and     eax, 200h
0x140059f58  mov     dword ptr [rsp+48h+AccessMode], eax; HandleAttributes
0x140059f5c  mov     dword ptr [rsp+48h+ObjectType], 0; DesiredAccess
0x140059f64  call    cs:__imp_ZwDuplicateObject
0x140059f6b  nop     dword ptr [rax+rax+00h]
0x140059f70  mov     rcx, [rsp+48h+SourceProcessHandle]; Handle
0x140059f75  mov     ebx, eax
0x140059f77  call    cs:__imp_ZwClose
0x140059f7e  nop     dword ptr [rax+rax+00h]
0x140059f83  mov     eax, ebx
0x140059f85  mov     rbx, [rsp+48h+arg_8]
0x140059f8a  mov     rsi, [rsp+48h+arg_10]
0x140059f8f  add     rsp, 40h
0x140059f93  pop     rdi
0x140059f94  retn
```
