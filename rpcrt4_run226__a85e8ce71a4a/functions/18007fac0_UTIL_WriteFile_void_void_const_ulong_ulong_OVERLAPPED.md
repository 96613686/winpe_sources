# UTIL_WriteFile(void *,void const *,ulong,ulong *,_OVERLAPPED *)

- ea: `0x18007fac0`
- end: `0x18007fb6a`
- name: `?UTIL_WriteFile@@YAJPEAXPEBXKPEAKPEAU_OVERLAPPED@@@Z`
- size: `170`
- prototype: `__int64 __fastcall(void *, const void *, unsigned int, unsigned int *, PVOID ApcContext)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18007f1c0`
- `0x18007f950`

## callees

- `0x18007fac0`
- `0x1800c9db8`

## import_xrefs

- `ntdll!NtWriteFile` at `0x18007fb1b`
- `ntdll!NtWriteFile` at `0x18007fb1b`
- `ntdll!RtlNtStatusToDosError` at `0x18007fb4e`
- `ntdll!RtlNtStatusToDosError` at `0x18007fb4e`

## pseudocode

```c
__int64 __fastcall UTIL_WriteFile(void *a1, void *a2, ULONG a3, unsigned int *a4, struct _IO_STATUS_BLOCK *ApcContext)
{
  struct _IO_STATUS_BLOCK *v5; // rbx
  struct _IO_STATUS_BLOCK *v7; // r9
  void *Information; // rdx
  int v9; // eax
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
  v9 = NtWriteFile(a1, Information, 0, v7, v5, a2, a3, (PLARGE_INTEGER)&ApcContext, 0);
  v10 = v9;
  if ( v9 == 259 )
    return 997;
  if ( v9 < 0 )
  {
    v12 = RtlNtStatusToDosError(v9);
    CompRpcpErrorAddRecord(v13, v10, 0xBF4u, v12);
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
0x18007fac0  mov     r11, rsp
0x18007fac3  mov     [r11+8], rbx
0x18007fac7  mov     [r11+10h], rsi
0x18007facb  push    rdi
0x18007facc  sub     rsp, 50h
0x18007fad0  mov     rbx, [rsp+58h+ApcContext]
0x18007fad8  lea     rax, [r11+28h]
0x18007fadc  mov     qword ptr [r11-18h], 0
0x18007fae4  mov     rsi, r9
0x18007fae7  mov     [r11-20h], rax
0x18007faeb  mov     r9d, 0
0x18007faf1  mov     [r11-28h], r8d
0x18007faf5  test    byte ptr [rbx+18h], 1
0x18007faf9  mov     [r11-30h], rdx
0x18007fafd  mov     rdx, [rbx+18h]; Event
0x18007fb01  cmovz   r9, rbx; ApcContext
0x18007fb05  xor     r8d, r8d; ApcRoutine
0x18007fb08  mov     qword ptr [rbx], 103h
0x18007fb0f  mov     qword ptr [r11+28h], 0
0x18007fb17  mov     [r11-38h], rbx
0x18007fb1b  call    cs:__imp_NtWriteFile
0x18007fb21  mov     edi, eax
0x18007fb23  cmp     eax, 103h
0x18007fb28  jz      short loc_18007FB45
0x18007fb2a  test    eax, eax
0x18007fb2c  js      short loc_18007FB4C
0x18007fb2e  mov     eax, [rbx+8]
0x18007fb31  mov     [rsi], eax
0x18007fb33  xor     eax, eax
0x18007fb35  mov     rbx, [rsp+58h+arg_0]
0x18007fb3a  mov     rsi, [rsp+58h+arg_8]
0x18007fb3f  add     rsp, 50h
0x18007fb43  pop     rdi
0x18007fb44  retn
0x18007fb45  mov     eax, 3E5h
0x18007fb4a  jmp     short loc_18007FB35
0x18007fb4c  mov     ecx, edi; Status
0x18007fb4e  call    cs:__imp_RtlNtStatusToDosError
0x18007fb54  mov     r8d, 0BF4h; unsigned __int16
0x18007fb5a  mov     edx, edi; unsigned int
0x18007fb5c  mov     r9d, eax; unsigned int
0x18007fb5f  mov     ebx, eax
0x18007fb61  call    ?CompRpcpErrorAddRecord@@YAXKKGK@Z; CompRpcpErrorAddRecord(ulong,ulong,ushort,ulong)
0x18007fb66  mov     eax, ebx
0x18007fb68  jmp     short loc_18007FB35
```
