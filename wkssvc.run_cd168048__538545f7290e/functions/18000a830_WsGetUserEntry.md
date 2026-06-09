# WsGetUserEntry

- ea: `0x18000a830`
- end: `0x18000a917`
- name: `WsGetUserEntry`
- size: `231`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800012a0`
- `0x180001750`
- `0x18002be90`

## callees

- `0x18000a830`
- `0x180031ae4`

## import_xrefs

- `ntdll!RtlCopyLuid` at `0x18000a8e8`
- `ntdll!RtlCopyLuid` at `0x18000a903`
- `ntdll!RtlCopyLuid` at `0x18000a8e8`
- `ntdll!RtlCopyLuid` at `0x18000a903`

## pseudocode

```c
__int64 __fastcall WsGetUserEntry(
        __int64 a1,
        struct _LUID *a2,
        unsigned int *LowPart,
        __int64 a4,
        struct _LUID *SourceLuid)
{
  unsigned int *v5; // r14
  struct _LUID *v6; // rdi
  unsigned int v8; // ebp
  __int64 i; // rbx
  __int64 result; // rax
  __int64 v11; // rbx

  v5 = LowPart;
  v6 = a2;
  v8 = -1;
  for ( i = 0; (unsigned int)i < *(_DWORD *)(a1 + 112); i = (unsigned int)(i + 1) )
  {
    LowPart = (unsigned int *)v6->LowPart;
    a2 = (struct _LUID *)(*(_QWORD *)a1 + 24 * i);
    if ( *v6 == *(_QWORD *)&a2[1] || *v6 == *(_QWORD *)&a2[2] )
    {
      *v5 = i;
      return 0;
    }
    if ( v8 == -1 && !*(_QWORD *)a2 )
      v8 = i;
  }
  if ( !(_DWORD)a4 )
    return 2221;
  if ( v8 != -1 )
  {
LABEL_19:
    v11 = 24LL * v8;
    RtlCopyLuid((PLUID)(v11 + *(_QWORD *)a1 + 8LL), v6);
    RtlCopyLuid((PLUID)(v11 + *(_QWORD *)a1 + 16LL), SourceLuid);
    *v5 = v8;
    return 0;
  }
  result = WsGrowTable(a1, a2, LowPart, a4);
  if ( !(_DWORD)result )
  {
    v8 = i;
    goto LABEL_19;
  }
  return result;
}

```

## disassembly

```asm
0x18000a830  push    rbx
0x18000a832  push    rbp
0x18000a833  push    rsi
0x18000a834  push    rdi
0x18000a835  push    r14
0x18000a837  sub     rsp, 20h
0x18000a83b  mov     r10d, [rcx+70h]
0x18000a83f  mov     r14, r8
0x18000a842  mov     rdi, rdx
0x18000a845  mov     rsi, rcx
0x18000a848  mov     ebp, 0FFFFFFFFh
0x18000a84d  xor     ebx, ebx
0x18000a84f  nop
0x18000a850  cmp     ebx, r10d
0x18000a853  jnb     short loc_18000A89A
0x18000a855  mov     rax, [rsi]
0x18000a858  lea     rcx, [rbx+rbx*2]
0x18000a85c  mov     r8d, [rdi]
0x18000a85f  lea     rdx, [rax+rcx*8]
0x18000a863  cmp     r8d, [rdx+8]
0x18000a867  jz      short loc_18000A878
0x18000a869  cmp     r8d, [rdx+10h]
0x18000a86d  jz      short loc_18000A8B0
0x18000a86f  cmp     ebp, 0FFFFFFFFh
0x18000a872  jz      short loc_18000A891
0x18000a874  inc     ebx
0x18000a876  jmp     short loc_18000A850
0x18000a878  mov     eax, [rdx+0Ch]
0x18000a87b  cmp     [rdi+4], eax
0x18000a87e  jnz     short loc_18000A869
0x18000a880  mov     [r14], ebx
0x18000a883  xor     eax, eax
0x18000a885  add     rsp, 20h
0x18000a889  pop     r14
0x18000a88b  pop     rdi
0x18000a88c  pop     rsi
0x18000a88d  pop     rbp
0x18000a88e  pop     rbx
0x18000a88f  retn
0x18000a891  cmp     qword ptr [rdx], 0
0x18000a895  cmovz   ebp, ebx
0x18000a898  jmp     short loc_18000A874
0x18000a89a  test    r9d, r9d
0x18000a89d  jnz     short loc_18000A8BA
0x18000a89f  mov     eax, 8ADh
0x18000a8a4  add     rsp, 20h
0x18000a8a8  pop     r14
0x18000a8aa  pop     rdi
0x18000a8ab  pop     rsi
0x18000a8ac  pop     rbp
0x18000a8ad  pop     rbx
0x18000a8ae  retn
0x18000a8b0  mov     eax, [rdx+14h]
0x18000a8b3  cmp     [rdi+4], eax
0x18000a8b6  jnz     short loc_18000A86F
0x18000a8b8  jmp     short loc_18000A880
0x18000a8ba  cmp     ebp, 0FFFFFFFFh
0x18000a8bd  jnz     short loc_18000A8CD
0x18000a8bf  mov     rcx, rsi
0x18000a8c2  call    WsGrowTable
0x18000a8c7  test    eax, eax
0x18000a8c9  jnz     short loc_18000A885
0x18000a8cb  mov     ebp, ebx
0x18000a8cd  mov     eax, ebp
0x18000a8cf  mov     rdx, rdi; SourceLuid
0x18000a8d2  lea     rcx, [rax+rax*2]
0x18000a8d6  lea     rbx, ds:0[rcx*8]
0x18000a8de  mov     rcx, [rsi]
0x18000a8e1  add     rcx, 8
0x18000a8e5  add     rcx, rbx; DestinationLuid
0x18000a8e8  call    cs:__imp_RtlCopyLuid
0x18000a8ef  nop     dword ptr [rax+rax+00h]
0x18000a8f4  mov     rcx, [rsi]
0x18000a8f7  mov     rdx, [rsp+48h+SourceLuid]; SourceLuid
0x18000a8fc  add     rcx, 10h
0x18000a900  add     rcx, rbx; DestinationLuid
0x18000a903  call    cs:__imp_RtlCopyLuid
0x18000a90a  nop     dword ptr [rax+rax+00h]
0x18000a90f  mov     [r14], ebp
0x18000a912  jmp     loc_18000A883
```
