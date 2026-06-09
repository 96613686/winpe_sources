# UTIL_ReadFile(void *,void *,ulong,ulong *,_OVERLAPPED *)

- ea: `0x18001a9cc`
- end: `0x18001aa7b`
- name: `?UTIL_ReadFile@@YAJPEAX0KPEAKPEAU_OVERLAPPED@@@Z`
- size: `175`
- prototype: `__int64 __fastcall(void *, void *, unsigned int, unsigned int *, PVOID ApcContext)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180011ec0`

## callees

- `0x18001a9cc`
- `0x18001e524`

## import_xrefs

- `ntdll!NtReadFile` at `0x18001aa27`
- `ntdll!NtReadFile` at `0x18001aa27`
- `ntdll!RtlNtStatusToDosError` at `0x18001aa4c`
- `ntdll!RtlNtStatusToDosError` at `0x18001aa4c`

## pseudocode

```c
__int64 __fastcall UTIL_ReadFile(void *a1, void *a2, ULONG a3, unsigned int *a4, struct _IO_STATUS_BLOCK *ApcContext)
{
  struct _IO_STATUS_BLOCK *v5; // rbx
  struct _IO_STATUS_BLOCK *v7; // r9
  void *Information; // rdx
  int File; // eax
  unsigned int v10; // edi
  ULONG v12; // ebx

  v5 = ApcContext;
  v7 = 0;
  Information = (void *)ApcContext[1].Information;
  if ( (ApcContext[1].Information & 1) == 0 )
    v7 = ApcContext;
  ApcContext->Pointer = (PVOID)259;
  ApcContext = 0;
  File = NtReadFile(a1, Information, 0, v7, v5, a2, a3, (PLARGE_INTEGER)&ApcContext, 0);
  v10 = File;
  if ( File == 259 )
    return 997;
  if ( File < 0 )
  {
    v12 = RtlNtStatusToDosError(File);
    CompRpcpErrorAddRecord(0x11u, v10, 0xBFEu, v12);
    return v12;
  }
  else
  {
    *a4 = v5->Information;
    return 0;
  }
}

```

## disassembly

```asm
0x18001a9cc  mov     r11, rsp
0x18001a9cf  mov     [r11+8], rbx
0x18001a9d3  mov     [r11+10h], rsi
0x18001a9d7  push    rdi
0x18001a9d8  sub     rsp, 50h
0x18001a9dc  mov     rbx, [rsp+58h+ApcContext]
0x18001a9e4  lea     rax, [r11+28h]
0x18001a9e8  mov     qword ptr [r11-18h], 0
0x18001a9f0  mov     rsi, r9
0x18001a9f3  mov     [r11-20h], rax
0x18001a9f7  mov     r9d, 0
0x18001a9fd  mov     [r11-28h], r8d
0x18001aa01  test    byte ptr [rbx+18h], 1
0x18001aa05  mov     [r11-30h], rdx
0x18001aa09  mov     rdx, [rbx+18h]; Event
0x18001aa0d  cmovz   r9, rbx; ApcContext
0x18001aa11  xor     r8d, r8d; ApcRoutine
0x18001aa14  mov     qword ptr [rbx], 103h
0x18001aa1b  mov     qword ptr [r11+28h], 0
0x18001aa23  mov     [r11-38h], rbx
0x18001aa27  call    cs:__imp_NtReadFile
0x18001aa2d  mov     edi, eax
0x18001aa2f  cmp     eax, 103h
0x18001aa34  jnz     short loc_18001AA3D
0x18001aa36  mov     eax, 3E5h
0x18001aa3b  jmp     short loc_18001AA6B
0x18001aa3d  test    edi, edi
0x18001aa3f  js      short loc_18001AA4A
0x18001aa41  mov     eax, [rbx+8]
0x18001aa44  mov     [rsi], eax
0x18001aa46  xor     eax, eax
0x18001aa48  jmp     short loc_18001AA6B
0x18001aa4a  mov     ecx, edi; Status
0x18001aa4c  call    cs:__imp_RtlNtStatusToDosError
0x18001aa52  mov     r8d, 0BFEh; unsigned __int16
0x18001aa58  mov     edx, edi; unsigned int
0x18001aa5a  mov     r9d, eax; unsigned int
0x18001aa5d  mov     ecx, 11h; unsigned int
0x18001aa62  mov     ebx, eax
0x18001aa64  call    ?CompRpcpErrorAddRecord@@YAXKKGK@Z; CompRpcpErrorAddRecord(ulong,ulong,ushort,ulong)
0x18001aa69  mov     eax, ebx
0x18001aa6b  mov     rbx, [rsp+58h+arg_0]
0x18001aa70  mov     rsi, [rsp+58h+arg_8]
0x18001aa75  add     rsp, 50h
0x18001aa79  pop     rdi
0x18001aa7a  retn
```
