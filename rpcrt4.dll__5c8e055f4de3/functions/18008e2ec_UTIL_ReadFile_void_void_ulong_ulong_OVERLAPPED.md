# UTIL_ReadFile(void *,void *,ulong,ulong *,_OVERLAPPED *)

- ea: `0x18008e2ec`
- end: `0x18008e396`
- name: `?UTIL_ReadFile@@YAJPEAX0KPEAKPEAU_OVERLAPPED@@@Z`
- size: `170`
- prototype: `__int64 __fastcall(void *, void *, unsigned int, unsigned int *, PVOID ApcContext)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18008e2c0`

## callees

- `0x18008e2ec`
- `0x1800c9db8`

## import_xrefs

- `ntdll!NtReadFile` at `0x18008e347`
- `ntdll!NtReadFile` at `0x18008e347`
- `ntdll!RtlNtStatusToDosError` at `0x18008e37a`
- `ntdll!RtlNtStatusToDosError` at `0x18008e37a`

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
0x18008e2ec  mov     r11, rsp
0x18008e2ef  mov     [r11+8], rbx
0x18008e2f3  mov     [r11+10h], rsi
0x18008e2f7  push    rdi
0x18008e2f8  sub     rsp, 50h
0x18008e2fc  mov     rbx, [rsp+58h+ApcContext]
0x18008e304  lea     rax, [r11+28h]
0x18008e308  mov     qword ptr [r11-18h], 0
0x18008e310  mov     rsi, r9
0x18008e313  mov     [r11-20h], rax
0x18008e317  mov     r9d, 0
0x18008e31d  mov     [r11-28h], r8d
0x18008e321  test    byte ptr [rbx+18h], 1
0x18008e325  mov     [r11-30h], rdx
0x18008e329  mov     rdx, [rbx+18h]; Event
0x18008e32d  cmovz   r9, rbx; ApcContext
0x18008e331  xor     r8d, r8d; ApcRoutine
0x18008e334  mov     qword ptr [rbx], 103h
0x18008e33b  mov     qword ptr [r11+28h], 0
0x18008e343  mov     [r11-38h], rbx
0x18008e347  call    cs:__imp_NtReadFile
0x18008e34d  mov     edi, eax
0x18008e34f  cmp     eax, 103h
0x18008e354  jnz     short loc_18008E36B
0x18008e356  mov     eax, 3E5h
0x18008e35b  mov     rbx, [rsp+58h+arg_0]
0x18008e360  mov     rsi, [rsp+58h+arg_8]
0x18008e365  add     rsp, 50h
0x18008e369  pop     rdi
0x18008e36a  retn
0x18008e36b  test    edi, edi
0x18008e36d  js      short loc_18008E378
0x18008e36f  mov     eax, [rbx+8]
0x18008e372  mov     [rsi], eax
0x18008e374  xor     eax, eax
0x18008e376  jmp     short loc_18008E35B
0x18008e378  mov     ecx, edi; Status
0x18008e37a  call    cs:__imp_RtlNtStatusToDosError
0x18008e380  mov     r8d, 0BFEh; unsigned __int16
0x18008e386  mov     edx, edi; unsigned int
0x18008e388  mov     r9d, eax; unsigned int
0x18008e38b  mov     ebx, eax
0x18008e38d  call    ?CompRpcpErrorAddRecord@@YAXKKGK@Z; CompRpcpErrorAddRecord(ulong,ulong,ushort,ulong)
0x18008e392  mov     eax, ebx
0x18008e394  jmp     short loc_18008E35B
```
