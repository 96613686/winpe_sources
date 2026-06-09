# RtlReadOutOfProcessMemoryStream

- ea: `0x1800049b0`
- end: `0x180004a4a`
- name: `RtlReadOutOfProcessMemoryStream`
- size: `154`
- prototype: `HRESULT __stdcall(struct IStream *This, PVOID Buffer, ULONG Length, PULONG BytesRead)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800049b0`

## import_xrefs

- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180004a30`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180004a30`
- `ntdll!NtReadVirtualMemory` at `0x1800049f6`
- `ntdll!NtReadVirtualMemory` at `0x1800049f6`

## pseudocode

```c
HRESULT __stdcall RtlReadOutOfProcessMemoryStream(struct IStream *This, PVOID Buffer, ULONG Length, PULONG BytesRead)
{
  void *v6; // rdx
  unsigned __int64 v8; // rcx
  NTSTATUS v9; // eax
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
    result = 0;
    *((_QWORD *)This + 2) += NumberOfBytesRead;
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
0x1800049b0  mov     [rsp+arg_8], rbx
0x1800049b5  push    rdi
0x1800049b6  sub     rsp, 30h
0x1800049ba  mov     rbx, rcx
0x1800049bd  mov     eax, r8d
0x1800049c0  mov     r10, rdx
0x1800049c3  mov     [rsp+38h+arg_0], 0
0x1800049cc  mov     rdx, [rcx+10h]; BaseAddress
0x1800049d0  mov     rdi, r9
0x1800049d3  mov     rcx, [rcx+20h]
0x1800049d7  sub     rcx, rdx
0x1800049da  cmp     rcx, rax
0x1800049dd  jnb     short loc_1800049E2
0x1800049df  mov     r8d, ecx
0x1800049e2  mov     rcx, [rbx+30h]; ProcessHandle
0x1800049e6  lea     rax, [rsp+38h+arg_0]
0x1800049eb  mov     r9d, r8d; NumberOfBytesToRead
0x1800049ee  mov     r8, r10; Buffer
0x1800049f1  mov     [rsp+38h+NumberOfBytesRead], rax; NumberOfBytesRead
0x1800049f6  call    cs:__imp_NtReadVirtualMemory
0x1800049fd  nop     dword ptr [rax+rax+00h]
0x180004a02  mov     edx, 80000000h
0x180004a07  lea     ecx, [rax+rdx]
0x180004a0a  test    edx, ecx
0x180004a0c  jz      short loc_180004A27
0x180004a0e  mov     rcx, [rsp+38h+arg_0]
0x180004a13  xor     eax, eax
0x180004a15  add     [rbx+10h], rcx
0x180004a19  mov     [rdi], ecx
0x180004a1b  mov     rbx, [rsp+38h+arg_8]
0x180004a20  add     rsp, 30h
0x180004a24  pop     rdi
0x180004a25  retn
0x180004a27  cmp     eax, 8000000Dh
0x180004a2c  jz      short loc_180004A0E
0x180004a2e  mov     ecx, eax; Status
0x180004a30  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x180004a37  nop     dword ptr [rax+rax+00h]
0x180004a3c  test    eax, eax
0x180004a3e  jle     short loc_180004A1B
0x180004a40  movzx   eax, ax
0x180004a43  or      eax, 80070000h
0x180004a48  jmp     short loc_180004A1B
```
