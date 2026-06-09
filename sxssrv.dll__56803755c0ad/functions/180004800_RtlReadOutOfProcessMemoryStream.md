# RtlReadOutOfProcessMemoryStream

- ea: `0x180004800`
- end: `0x180004899`
- name: `RtlReadOutOfProcessMemoryStream`
- size: `153`
- prototype: `HRESULT __stdcall(struct IStream *This, PVOID Buffer, ULONG Length, PULONG BytesRead)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180004800`

## import_xrefs

- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18000487f`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18000487f`
- `ntdll!NtReadVirtualMemory` at `0x180004845`
- `ntdll!NtReadVirtualMemory` at `0x180004845`

## pseudocode

```c
HRESULT __stdcall RtlReadOutOfProcessMemoryStream(struct IStream *This, PVOID Buffer, ULONG Length, PULONG BytesRead)
{
  void *v6; // rdx
  unsigned __int64 v8; // rcx
  NTSTATUS v9; // ecx
  ULONG v10; // ecx
  HRESULT result; // eax
  ULONG_PTR NumberOfBytesRead; // [rsp+40h] [rbp+8h] BYREF

  NumberOfBytesRead = 0;
  v6 = (void *)*((_QWORD *)This + 2);
  v8 = *((_QWORD *)This + 4) - (_QWORD)v6;
  if ( v8 < Length )
    Length = v8;
  v9 = NtReadVirtualMemory(*((HANDLE *)This + 6), v6, Buffer, Length, &NumberOfBytesRead);
  if ( (int)(v9 + 0x80000000) < 0 || v9 == -2147483635 )
  {
    v10 = NumberOfBytesRead;
    *((_QWORD *)This + 2) += NumberOfBytesRead;
    result = 0;
    *BytesRead = v10;
  }
  else
  {
    result = RtlNtStatusToDosErrorNoTeb(v9);
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x180004800  mov     [rsp+arg_8], rbx
0x180004805  push    rdi
0x180004806  sub     rsp, 30h
0x18000480a  mov     eax, r8d
0x18000480d  mov     rbx, rcx
0x180004810  mov     r10, rdx
0x180004813  mov     [rsp+38h+arg_0], 0
0x18000481c  mov     rdx, [rcx+10h]; BaseAddress
0x180004820  mov     rdi, r9
0x180004823  mov     rcx, [rcx+20h]
0x180004827  sub     rcx, rdx
0x18000482a  cmp     rcx, rax
0x18000482d  lea     rax, [rsp+38h+arg_0]
0x180004832  mov     [rsp+38h+NumberOfBytesRead], rax; NumberOfBytesRead
0x180004837  cmovb   r8d, ecx
0x18000483b  mov     rcx, [rbx+30h]; ProcessHandle
0x18000483f  mov     r9d, r8d; NumberOfBytesToRead
0x180004842  mov     r8, r10; Buffer
0x180004845  call    cs:__imp_NtReadVirtualMemory
0x18000484c  nop     dword ptr [rax+rax+00h]
0x180004851  mov     edx, 80000000h
0x180004856  mov     ecx, eax; Status
0x180004858  add     eax, edx
0x18000485a  test    edx, eax
0x18000485c  jz      short loc_180004877
0x18000485e  mov     rcx, [rsp+38h+arg_0]
0x180004863  add     [rbx+10h], rcx
0x180004867  xor     eax, eax
0x180004869  mov     [rdi], ecx
0x18000486b  mov     rbx, [rsp+38h+arg_8]
0x180004870  add     rsp, 30h
0x180004874  pop     rdi
0x180004875  retn
0x180004877  cmp     ecx, 8000000Dh
0x18000487d  jz      short loc_18000485E
0x18000487f  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x180004886  nop     dword ptr [rax+rax+00h]
0x18000488b  test    eax, eax
0x18000488d  jle     short loc_18000486B
0x18000488f  movzx   eax, ax
0x180004892  or      eax, 80070000h
0x180004897  jmp     short loc_18000486B
```
