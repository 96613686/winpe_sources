# RtlReadMemoryStream

- ea: `0x180005ad0`
- end: `0x180005b62`
- name: `RtlReadMemoryStream`
- size: `146`
- prototype: `HRESULT __stdcall(struct IStream *This, PVOID Buffer, ULONG Length, PULONG BytesRead)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180005ad0`

## import_xrefs

- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180005b3b`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180005b3b`
- `ntdll!RtlCopyMappedMemory` at `0x180005b09`
- `ntdll!RtlCopyMappedMemory` at `0x180005b09`

## pseudocode

```c
HRESULT __stdcall RtlReadMemoryStream(struct IStream *This, PVOID Buffer, ULONG Length, PULONG BytesRead)
{
  ULONG v5; // ebx
  const void *v8; // rdx
  unsigned __int64 v9; // rcx
  int v10; // eax
  HRESULT result; // eax

  v5 = Length;
  v8 = (const void *)*((_QWORD *)This + 2);
  v9 = *((_QWORD *)This + 4) - (_QWORD)v8;
  if ( v9 < Length )
    v5 = v9;
  v10 = RtlCopyMappedMemory(Buffer, v8, v5);
  if ( v10 < 0 )
  {
    result = RtlNtStatusToDosErrorNoTeb(v10);
    if ( result > 0 )
      result = (unsigned __int16)result | 0x80070000;
    *BytesRead = 0;
  }
  else
  {
    *((_QWORD *)This + 2) += v5;
    result = 0;
    *BytesRead = v5;
  }
  return result;
}

```

## disassembly

```asm
0x180005ad0  mov     [rsp+arg_0], rbx
0x180005ad5  mov     [rsp+arg_8], rsi
0x180005ada  mov     [rsp+arg_10], rdi
0x180005adf  push    r14
0x180005ae1  sub     rsp, 20h
0x180005ae5  mov     rsi, rcx
0x180005ae8  mov     ebx, r8d
0x180005aeb  mov     r10, rdx
0x180005aee  mov     r14, r9
0x180005af1  mov     rdx, [rcx+10h]; Source
0x180005af5  mov     rcx, [rcx+20h]
0x180005af9  sub     rcx, rdx
0x180005afc  cmp     rcx, rbx
0x180005aff  jb      short loc_180005B54
0x180005b01  mov     r8d, ebx; Size
0x180005b04  mov     rcx, r10; Destination
0x180005b07  mov     edi, ebx
0x180005b09  call    cs:__imp_RtlCopyMappedMemory
0x180005b10  nop     dword ptr [rax+rax+00h]
0x180005b15  test    eax, eax
0x180005b17  js      short loc_180005B39
0x180005b19  add     [rsi+10h], rdi
0x180005b1d  xor     eax, eax
0x180005b1f  mov     [r14], ebx
0x180005b22  mov     rbx, [rsp+28h+arg_0]
0x180005b27  mov     rsi, [rsp+28h+arg_8]
0x180005b2c  mov     rdi, [rsp+28h+arg_10]
0x180005b31  add     rsp, 20h
0x180005b35  pop     r14
0x180005b37  retn
0x180005b39  mov     ecx, eax; Status
0x180005b3b  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x180005b42  nop     dword ptr [rax+rax+00h]
0x180005b47  test    eax, eax
0x180005b49  jg      short loc_180005B58
0x180005b4b  mov     dword ptr [r14], 0
0x180005b52  jmp     short loc_180005B22
0x180005b54  mov     ebx, ecx
0x180005b56  jmp     short loc_180005B01
0x180005b58  movzx   eax, ax
0x180005b5b  or      eax, 80070000h
0x180005b60  jmp     short loc_180005B4B
```
