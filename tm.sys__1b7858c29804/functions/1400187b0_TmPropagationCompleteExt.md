# TmPropagationCompleteExt

- ea: `0x1400187b0`
- end: `0x140018806`
- name: `TmPropagationCompleteExt`
- size: `86`
- prototype: `NTSTATUS __stdcall(PKRESOURCEMANAGER ResourceManager, ULONG RequestCookie, ULONG BufferLength, PVOID Buffer)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1400181c0`

## callees

- `0x14000cfa8`
- `0x1400187b0`
- `0x140019334`
- `0x14001953c`

## pseudocode

```c
NTSTATUS __stdcall TmPropagationCompleteExt(
        PKRESOURCEMANAGER ResourceManager,
        ULONG RequestCookie,
        ULONG BufferLength,
        PVOID Buffer)
{
  __int64 PropagationRequest; // rax
  void *v7; // rdi
  NTSTATUS v9; // ebx

  PropagationRequest = TmpFindPropagationRequest(ResourceManager, RequestCookie);
  v7 = (void *)PropagationRequest;
  if ( !PropagationRequest )
    return -1073741772;
  v9 = TmpPropagationComplete(PropagationRequest, BufferLength, Buffer, 0);
  TmpDereferencePropagateRequest(v7);
  return v9;
}

```

## disassembly

```asm
0x1400187b0  mov     [rsp+arg_0], rbx
0x1400187b5  mov     [rsp+arg_8], rsi
0x1400187ba  push    rdi
0x1400187bb  sub     rsp, 20h
0x1400187bf  mov     rbx, r9
0x1400187c2  mov     esi, r8d
0x1400187c5  call    TmpFindPropagationRequest
0x1400187ca  mov     rdi, rax
0x1400187cd  test    rax, rax
0x1400187d0  jnz     short loc_1400187D9
0x1400187d2  mov     eax, 0C0000034h
0x1400187d7  jmp     short loc_1400187F5
0x1400187d9  xor     r9d, r9d
0x1400187dc  mov     r8, rbx
0x1400187df  mov     edx, esi
0x1400187e1  mov     rcx, rdi
0x1400187e4  call    TmpPropagationComplete
0x1400187e9  mov     rcx, rdi; P
0x1400187ec  mov     ebx, eax
0x1400187ee  call    TmpDereferencePropagateRequest
0x1400187f3  mov     eax, ebx
0x1400187f5  mov     rbx, [rsp+28h+arg_0]
0x1400187fa  mov     rsi, [rsp+28h+arg_8]
0x1400187ff  add     rsp, 20h
0x140018803  pop     rdi
0x140018804  retn
```
