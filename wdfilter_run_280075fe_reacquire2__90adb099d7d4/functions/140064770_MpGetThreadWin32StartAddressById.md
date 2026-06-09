# MpGetThreadWin32StartAddressById

- ea: `0x140064770`
- end: `0x14006488a`
- name: `MpGetThreadWin32StartAddressById`
- size: `282`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140063a70`

## callees

- `0x1400118d0`
- `0x140064770`

## import_xrefs

- `ntoskrnl!ObOpenObjectByPointer` at `0x1400647f7`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400647f7`
- `ntoskrnl!ZwQueryInformationThread` at `0x140064841`
- `ntoskrnl!ZwQueryInformationThread` at `0x140064841`
- `ntoskrnl!PsLookupThreadByThreadId` at `0x1400647b4`
- `ntoskrnl!PsLookupThreadByThreadId` at `0x1400647b4`
- `ntoskrnl!ZwClose` at `0x14006485b`
- `ntoskrnl!ZwClose` at `0x14006485b`
- `ntoskrnl!PsThreadType` at `0x1400647d9`
- `ntoskrnl!ObfDereferenceObject` at `0x14006480a`
- `ntoskrnl!ObfDereferenceObject` at `0x14006480a`

## pseudocode

```c
__int64 __fastcall MpGetThreadWin32StartAddressById(void *a1, void *a2)
{
  NTSTATUS v3; // ebx
  HANDLE v5; // rcx
  NTSTATUS InformationThread; // eax
  PVOID Object; // [rsp+40h] [rbp-28h] BYREF
  HANDLE ThreadHandle; // [rsp+48h] [rbp-20h] BYREF

  ThreadHandle = 0;
  if ( !a1 || !a2 )
    return 3221225485LL;
  Object = 0;
  v3 = PsLookupThreadByThreadId(a1, (PETHREAD *)&Object);
  if ( v3 >= 0
    && (v3 = ObOpenObjectByPointer(Object, 0x200u, 0, 0x40u, (POBJECT_TYPE)PsThreadType, 0, &ThreadHandle),
        ObfDereferenceObject(Object),
        v3 >= 0) )
  {
    v5 = ThreadHandle;
    if ( ThreadHandle )
    {
      InformationThread = ZwQueryInformationThread(ThreadHandle, ThreadQuerySetWin32StartAddress, a2, 8u, 0);
      v5 = ThreadHandle;
      v3 = InformationThread;
    }
    else
    {
      v3 = -1073741811;
    }
    ZwClose(v5);
  }
  else
  {
    _mm_lfence();
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x140064770  mov     r11, rsp
0x140064773  mov     [r11+18h], rbx
0x140064777  push    rdi
0x140064778  sub     rsp, 60h
0x14006477c  mov     rax, cs:__security_cookie
0x140064783  xor     rax, rsp
0x140064786  mov     [rsp+68h+var_18], rax
0x14006478b  mov     qword ptr [r11-20h], 0
0x140064793  mov     rdi, rdx
0x140064796  test    rcx, rcx
0x140064799  jz      loc_140064869
0x14006479f  test    rdx, rdx
0x1400647a2  jz      loc_140064869
0x1400647a8  lea     rdx, [r11-28h]; Thread
0x1400647ac  mov     qword ptr [r11-28h], 0
0x1400647b4  call    cs:__imp_PsLookupThreadByThreadId
0x1400647bb  nop     dword ptr [rax+rax+00h]
0x1400647c0  mov     ebx, eax
0x1400647c2  test    eax, eax
0x1400647c4  js      short loc_14006481A
0x1400647c6  lea     rax, [rsp+68h+ThreadHandle]
0x1400647cb  mov     r9d, 40h ; '@'; DesiredAccess
0x1400647d1  mov     [rsp+68h+Handle], rax; Handle
0x1400647d6  xor     r8d, r8d; PassedAccessState
0x1400647d9  mov     rax, cs:__imp_PsThreadType
0x1400647e0  mov     edx, 200h; HandleAttributes
0x1400647e5  mov     [rsp+68h+AccessMode], 0; AccessMode
0x1400647ea  mov     rcx, [rax]
0x1400647ed  mov     [rsp+68h+ObjectType], rcx; ObjectType
0x1400647f2  mov     rcx, [rsp+68h+Object]; Object
0x1400647f7  call    cs:__imp_ObOpenObjectByPointer
0x1400647fe  nop     dword ptr [rax+rax+00h]
0x140064803  mov     rcx, [rsp+68h+Object]; Object
0x140064808  mov     ebx, eax
0x14006480a  call    cs:__imp_ObfDereferenceObject
0x140064811  nop     dword ptr [rax+rax+00h]
0x140064816  test    ebx, ebx
0x140064818  jns     short loc_140064821
0x14006481a  lfence
0x14006481d  mov     eax, ebx
0x14006481f  jmp     short loc_14006486E
0x140064821  mov     rcx, [rsp+68h+ThreadHandle]; Handle
0x140064826  test    rcx, rcx
0x140064829  jz      short loc_140064856
0x14006482b  mov     r9d, 8; ThreadInformationLength
0x140064831  mov     [rsp+68h+ObjectType], 0; ReturnLength
0x14006483a  mov     r8, rdi; ThreadInformation
0x14006483d  lea     edx, [r9+1]; ThreadInformationClass
0x140064841  call    cs:__imp_ZwQueryInformationThread
0x140064848  nop     dword ptr [rax+rax+00h]
0x14006484d  mov     rcx, [rsp+68h+ThreadHandle]
0x140064852  mov     ebx, eax
0x140064854  jmp     short loc_14006485B
0x140064856  mov     ebx, 0C000000Dh
0x14006485b  call    cs:__imp_ZwClose
0x140064862  nop     dword ptr [rax+rax+00h]
0x140064867  jmp     short loc_14006481D
0x140064869  mov     eax, 0C000000Dh
0x14006486e  mov     rcx, [rsp+68h+var_18]
0x140064873  xor     rcx, rsp; StackCookie
0x140064876  call    __security_check_cookie
0x14006487b  mov     rbx, [rsp+68h+arg_10]
0x140064883  add     rsp, 60h
0x140064887  pop     rdi
0x140064888  retn
```
