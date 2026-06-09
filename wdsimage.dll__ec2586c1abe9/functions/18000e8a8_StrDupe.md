# StrDupe

- ea: `0x18000e8a8`
- end: `0x18000e96a`
- name: `StrDupe`
- size: `194`
- prototype: `__int64 __fastcall(STRSAFE_LPCWSTR pszSrc)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000bd94`
- `0x18000bef8`
- `0x18000dc28`
- `0x18000efbc`

## callees

- `0x18000e8a8`
- `0x18000e970`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18000e938`
- `ntdll!RtlFreeHeap` at `0x18000e938`
- `ntdll!RtlAllocateHeap` at `0x18000e8fe`
- `ntdll!RtlAllocateHeap` at `0x18000e8fe`

## pseudocode

```c
wchar_t *__fastcall StrDupe(STRSAFE_LPCWSTR pszSrc)
{
  __int64 v3; // rbx
  size_t v4; // rbx
  wchar_t *Heap; // rax
  wchar_t *v6; // r11
  HRESULT v7; // eax
  unsigned __int16 v8; // bx

  if ( pszSrc )
  {
    v3 = -1;
    do
      ++v3;
    while ( pszSrc[v3] );
    v4 = v3 + 1;
    Heap = (wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2 * v4);
    v6 = Heap;
    if ( Heap )
    {
      v7 = StringCchCopyW(Heap, v4, pszSrc);
      v8 = v7;
      if ( v7 < 0 )
      {
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v6);
        v6 = 0;
        NtCurrentTeb()->LastErrorValue = v8;
      }
    }
    return v6;
  }
  else
  {
    NtCurrentTeb()->LastErrorValue = 87;
    return 0;
  }
}

```

## disassembly

```asm
0x18000e8a8  mov     [rsp+arg_0], rbx
0x18000e8ad  mov     [rsp+arg_8], rsi
0x18000e8b2  push    rdi
0x18000e8b3  sub     rsp, 20h
0x18000e8b7  xor     esi, esi
0x18000e8b9  mov     rdi, rcx
0x18000e8bc  test    rcx, rcx
0x18000e8bf  jnz     short loc_18000E8D8
0x18000e8c1  mov     rax, gs:30h
0x18000e8ca  mov     dword ptr [rax+68h], 57h ; 'W'
0x18000e8d1  xor     eax, eax
0x18000e8d3  jmp     loc_18000E959
0x18000e8d8  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000e8dc  inc     rbx
0x18000e8df  cmp     [rcx+rbx*2], si
0x18000e8e3  jnz     short loc_18000E8DC
0x18000e8e5  mov     rcx, gs:60h
0x18000e8ee  inc     rbx
0x18000e8f1  mov     edx, 8; Flags
0x18000e8f6  mov     rcx, [rcx+30h]; HeapHandle
0x18000e8fa  lea     r8, [rbx+rbx]; Size
0x18000e8fe  call    cs:__imp_RtlAllocateHeap
0x18000e905  nop     dword ptr [rax+rax+00h]
0x18000e90a  mov     r11, rax
0x18000e90d  test    rax, rax
0x18000e910  jz      short loc_18000E956
0x18000e912  mov     r8, rdi; pszSrc
0x18000e915  mov     rdx, rbx; cchDest
0x18000e918  mov     rcx, rax; pszDest
0x18000e91b  call    StringCchCopyW
0x18000e920  mov     ebx, eax
0x18000e922  test    eax, eax
0x18000e924  jns     short loc_18000E956
0x18000e926  mov     rcx, gs:60h
0x18000e92f  mov     r8, r11; P
0x18000e932  xor     edx, edx; Flags
0x18000e934  mov     rcx, [rcx+30h]; HeapHandle
0x18000e938  call    cs:__imp_RtlFreeHeap
0x18000e93f  nop     dword ptr [rax+rax+00h]
0x18000e944  mov     rax, gs:30h
0x18000e94d  mov     r11, rsi
0x18000e950  movzx   ecx, bx
0x18000e953  mov     [rax+68h], ecx
0x18000e956  mov     rax, r11
0x18000e959  mov     rbx, [rsp+28h+arg_0]
0x18000e95e  mov     rsi, [rsp+28h+arg_8]
0x18000e963  add     rsp, 20h
0x18000e967  pop     rdi
0x18000e968  retn
```
