# UTIL_ReadFile(void *,void *,ulong,ulong *,_OVERLAPPED *)

- ea: `0x180091e6c`
- end: `0x180091f23`
- name: `?UTIL_ReadFile@@YAJPEAX0KPEAKPEAU_OVERLAPPED@@@Z`
- size: `183`
- prototype: `__int64 __fastcall(void *, void *, unsigned int, unsigned int *, PVOID ApcContext)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180091e40`

## callees

- `0x180091e6c`
- `0x1800ce9fc`

## import_xrefs

- `ntdll!NtReadFile` at `0x180091ec7`
- `ntdll!NtReadFile` at `0x180091ec7`
- `ntdll!RtlNtStatusToDosError` at `0x180091f01`
- `ntdll!RtlNtStatusToDosError` at `0x180091f01`

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
  unsigned int v13; // ecx

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
    CompRpcpErrorAddRecord(v13, v10, 0xBFEu, v12);
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
0x180091e6c  mov     r11, rsp
0x180091e6f  mov     [r11+8], rbx
0x180091e73  mov     [r11+10h], rsi
0x180091e77  push    rdi
0x180091e78  sub     rsp, 50h
0x180091e7c  mov     rbx, [rsp+58h+ApcContext]
0x180091e84  lea     rax, [r11+28h]
0x180091e88  mov     qword ptr [r11-18h], 0
0x180091e90  mov     rsi, r9
0x180091e93  mov     [r11-20h], rax
0x180091e97  mov     r9d, 0
0x180091e9d  mov     [r11-28h], r8d
0x180091ea1  test    byte ptr [rbx+18h], 1
0x180091ea5  mov     [r11-30h], rdx
0x180091ea9  mov     rdx, [rbx+18h]; Event
0x180091ead  cmovz   r9, rbx; ApcContext
0x180091eb1  xor     r8d, r8d; ApcRoutine
0x180091eb4  mov     qword ptr [rbx], 103h
0x180091ebb  mov     qword ptr [r11+28h], 0
0x180091ec3  mov     [r11-38h], rbx
0x180091ec7  call    cs:__imp_NtReadFile
0x180091ece  nop     dword ptr [rax+rax+00h]
0x180091ed3  mov     edi, eax
0x180091ed5  cmp     eax, 103h
0x180091eda  jnz     short loc_180091EF2
0x180091edc  mov     eax, 3E5h
0x180091ee1  mov     rbx, [rsp+58h+arg_0]
0x180091ee6  mov     rsi, [rsp+58h+arg_8]
0x180091eeb  add     rsp, 50h
0x180091eef  pop     rdi
0x180091ef0  retn
0x180091ef2  test    edi, edi
0x180091ef4  js      short loc_180091EFF
0x180091ef6  mov     eax, [rbx+8]
0x180091ef9  mov     [rsi], eax
0x180091efb  xor     eax, eax
0x180091efd  jmp     short loc_180091EE1
0x180091eff  mov     ecx, edi; Status
0x180091f01  call    cs:__imp_RtlNtStatusToDosError
0x180091f08  nop     dword ptr [rax+rax+00h]
0x180091f0d  mov     r8d, 0BFEh; unsigned __int16
0x180091f13  mov     edx, edi; unsigned int
0x180091f15  mov     r9d, eax; unsigned int
0x180091f18  mov     ebx, eax
0x180091f1a  call    ?CompRpcpErrorAddRecord@@YAXKKGK@Z; CompRpcpErrorAddRecord(ulong,ulong,ushort,ulong)
0x180091f1f  mov     eax, ebx
0x180091f21  jmp     short loc_180091EE1
```
