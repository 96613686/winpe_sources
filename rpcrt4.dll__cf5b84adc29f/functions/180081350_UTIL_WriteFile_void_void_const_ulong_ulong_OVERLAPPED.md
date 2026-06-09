# UTIL_WriteFile(void *,void const *,ulong,ulong *,_OVERLAPPED *)

- ea: `0x180081350`
- end: `0x180081407`
- name: `?UTIL_WriteFile@@YAJPEAXPEBXKPEAKPEAU_OVERLAPPED@@@Z`
- size: `183`
- prototype: `__int64 __fastcall(void *, const void *, unsigned int, unsigned int *, PVOID ApcContext)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180080a30`
- `0x1800811e0`

## callees

- `0x180081350`
- `0x1800ce9fc`

## import_xrefs

- `ntdll!NtWriteFile` at `0x1800813ab`
- `ntdll!NtWriteFile` at `0x1800813ab`
- `ntdll!RtlNtStatusToDosError` at `0x1800813e5`
- `ntdll!RtlNtStatusToDosError` at `0x1800813e5`

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
0x180081350  mov     r11, rsp
0x180081353  mov     [r11+8], rbx
0x180081357  mov     [r11+10h], rsi
0x18008135b  push    rdi
0x18008135c  sub     rsp, 50h
0x180081360  mov     rbx, [rsp+58h+ApcContext]
0x180081368  lea     rax, [r11+28h]
0x18008136c  mov     qword ptr [r11-18h], 0
0x180081374  mov     rsi, r9
0x180081377  mov     [r11-20h], rax
0x18008137b  mov     r9d, 0
0x180081381  mov     [r11-28h], r8d
0x180081385  test    byte ptr [rbx+18h], 1
0x180081389  mov     [r11-30h], rdx
0x18008138d  mov     rdx, [rbx+18h]; Event
0x180081391  cmovz   r9, rbx; ApcContext
0x180081395  xor     r8d, r8d; ApcRoutine
0x180081398  mov     qword ptr [rbx], 103h
0x18008139f  mov     qword ptr [r11+28h], 0
0x1800813a7  mov     [r11-38h], rbx
0x1800813ab  call    cs:__imp_NtWriteFile
0x1800813b2  nop     dword ptr [rax+rax+00h]
0x1800813b7  mov     edi, eax
0x1800813b9  cmp     eax, 103h
0x1800813be  jz      short loc_1800813DC
0x1800813c0  test    eax, eax
0x1800813c2  js      short loc_1800813E3
0x1800813c4  mov     eax, [rbx+8]
0x1800813c7  mov     [rsi], eax
0x1800813c9  xor     eax, eax
0x1800813cb  mov     rbx, [rsp+58h+arg_0]
0x1800813d0  mov     rsi, [rsp+58h+arg_8]
0x1800813d5  add     rsp, 50h
0x1800813d9  pop     rdi
0x1800813da  retn
0x1800813dc  mov     eax, 3E5h
0x1800813e1  jmp     short loc_1800813CB
0x1800813e3  mov     ecx, edi; Status
0x1800813e5  call    cs:__imp_RtlNtStatusToDosError
0x1800813ec  nop     dword ptr [rax+rax+00h]
0x1800813f1  mov     r8d, 0BF4h; unsigned __int16
0x1800813f7  mov     edx, edi; unsigned int
0x1800813f9  mov     r9d, eax; unsigned int
0x1800813fc  mov     ebx, eax
0x1800813fe  call    ?CompRpcpErrorAddRecord@@YAXKKGK@Z; CompRpcpErrorAddRecord(ulong,ulong,ushort,ulong)
0x180081403  mov     eax, ebx
0x180081405  jmp     short loc_1800813CB
```
