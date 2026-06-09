# RtlReadMemoryStream

- ea: `0x180005bb0`
- end: `0x180005c2c`
- name: `RtlReadMemoryStream`
- size: `124`
- prototype: `HRESULT __stdcall(struct IStream *This, PVOID Buffer, ULONG Length, PULONG BytesRead)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180005bb0`

## import_xrefs

- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180005c04`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180005c04`
- `ntdll!RtlCopyMappedMemory` at `0x180005bde`
- `ntdll!RtlCopyMappedMemory` at `0x180005bde`

## pseudocode

```c
HRESULT __stdcall RtlReadMemoryStream(struct IStream *This, PVOID Buffer, ULONG Length, PULONG BytesRead)
{
  ULONG v4; // ebx
  const void *v6; // rdx
  int v9; // eax
  HRESULT result; // eax

  v4 = Length;
  v6 = (const void *)*((_QWORD *)This + 2);
  if ( *((_QWORD *)This + 4) - (_QWORD)v6 < (unsigned __int64)Length )
    v4 = *((_DWORD *)This + 8) - (_DWORD)v6;
  v9 = RtlCopyMappedMemory(Buffer, v6, v4);
  if ( v9 < 0 )
  {
    result = RtlNtStatusToDosErrorNoTeb(v9);
    if ( result > 0 )
      result = (unsigned __int16)result | 0x80070000;
    *BytesRead = 0;
  }
  else
  {
    *((_QWORD *)This + 2) += v4;
    result = 0;
    *BytesRead = v4;
  }
  return result;
}

```

## disassembly

```asm
0x180005bb0  push    rbx
0x180005bb2  push    rsi
0x180005bb3  push    rdi
0x180005bb4  push    r14
0x180005bb6  sub     rsp, 28h
0x180005bba  mov     ebx, r8d
0x180005bbd  mov     r10, rdx
0x180005bc0  mov     rdx, [rcx+10h]; Source
0x180005bc4  mov     r14, r9
0x180005bc7  mov     r8, [rcx+20h]
0x180005bcb  mov     rdi, rcx
0x180005bce  sub     r8, rdx
0x180005bd1  cmp     r8, rbx
0x180005bd4  jb      short loc_180005C1D
0x180005bd6  mov     r8d, ebx; Size
0x180005bd9  mov     rcx, r10; Destination
0x180005bdc  mov     esi, ebx
0x180005bde  call    cs:__imp_RtlCopyMappedMemory
0x180005be5  nop     dword ptr [rax+rax+00h]
0x180005bea  test    eax, eax
0x180005bec  js      short loc_180005C02
0x180005bee  add     [rdi+10h], rsi
0x180005bf2  xor     eax, eax
0x180005bf4  mov     [r14], ebx
0x180005bf7  add     rsp, 28h
0x180005bfb  pop     r14
0x180005bfd  pop     rdi
0x180005bfe  pop     rsi
0x180005bff  pop     rbx
0x180005c00  retn
0x180005c02  mov     ecx, eax; Status
0x180005c04  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x180005c0b  nop     dword ptr [rax+rax+00h]
0x180005c10  test    eax, eax
0x180005c12  jg      short loc_180005C22
0x180005c14  mov     dword ptr [r14], 0
0x180005c1b  jmp     short loc_180005BF7
0x180005c1d  mov     ebx, r8d
0x180005c20  jmp     short loc_180005BD6
0x180005c22  movzx   eax, ax
0x180005c25  or      eax, 80070000h
0x180005c2a  jmp     short loc_180005C14
```
