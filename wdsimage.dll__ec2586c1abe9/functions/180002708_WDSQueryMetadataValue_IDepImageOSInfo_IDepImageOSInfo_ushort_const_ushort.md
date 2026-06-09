# WDSQueryMetadataValue<IDepImageOSInfo>(IDepImageOSInfo *,ushort const *,ushort * *)

- ea: `0x180002708`
- end: `0x1800027c8`
- name: `??$WDSQueryMetadataValue@VIDepImageOSInfo@@@@YAJPEAVIDepImageOSInfo@@PEBGPEAPEAG@Z`
- size: `192`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180002664`
- `0x18000284c`
- `0x180003010`

## callees

- `0x180002708`
- `0x18000e970`
- `0x180011010`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180002788`
- `ntdll!RtlFreeHeap` at `0x180002788`
- `ntdll!RtlAllocateHeap` at `0x180002748`
- `ntdll!RtlAllocateHeap` at `0x180002748`

## pseudocode

```c
__int64 __fastcall WDSQueryMetadataValue<IDepImageOSInfo>(__int64 (__fastcall ***a1)(_QWORD), __int64 a2, wchar_t **a3)
{
  unsigned int v4; // ebx
  wchar_t *Heap; // rax
  wchar_t *v6; // r11
  HRESULT v7; // eax
  unsigned __int16 v8; // di

  v4 = (**a1)(a1);
  if ( v4 == -2147023728 )
  {
    Heap = (wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2u);
    v4 = 0;
    v6 = Heap;
    if ( Heap )
    {
      v7 = StringCchCopyW(Heap, 1u, &pszSrc);
      v8 = v7;
      if ( v7 < 0 )
      {
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v6);
        NtCurrentTeb()->LastErrorValue = v8;
        *a3 = 0;
        return (unsigned int)-2147024882;
      }
    }
    *a3 = v6;
    if ( !v6 )
      return (unsigned int)-2147024882;
  }
  return v4;
}

```

## disassembly

```asm
0x180002708  mov     [rsp+arg_0], rbx
0x18000270d  mov     [rsp+arg_8], rsi
0x180002712  push    rdi
0x180002713  sub     rsp, 20h
0x180002717  mov     rax, [rcx]
0x18000271a  mov     rsi, r8
0x18000271d  mov     rax, [rax]
0x180002720  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002725  mov     ebx, eax
0x180002727  cmp     eax, 80070490h
0x18000272c  jnz     loc_1800027B5
0x180002732  mov     rcx, gs:60h
0x18000273b  mov     edx, 8; Flags
0x180002740  mov     rcx, [rcx+30h]; HeapHandle
0x180002744  lea     r8d, [rdx-6]; Size
0x180002748  call    cs:__imp_RtlAllocateHeap
0x18000274f  nop     dword ptr [rax+rax+00h]
0x180002754  xor     ebx, ebx
0x180002756  mov     r11, rax
0x180002759  test    rax, rax
0x18000275c  jz      short loc_1800027A8
0x18000275e  lea     r8, pszSrc; pszSrc
0x180002765  mov     rcx, rax; pszDest
0x180002768  lea     edx, [rbx+1]; cchDest
0x18000276b  call    StringCchCopyW
0x180002770  mov     edi, eax
0x180002772  test    eax, eax
0x180002774  jns     short loc_1800027A8
0x180002776  mov     rcx, gs:60h
0x18000277f  mov     r8, r11; P
0x180002782  xor     edx, edx; Flags
0x180002784  mov     rcx, [rcx+30h]; HeapHandle
0x180002788  call    cs:__imp_RtlFreeHeap
0x18000278f  nop     dword ptr [rax+rax+00h]
0x180002794  mov     rax, gs:30h
0x18000279d  movzx   ecx, di
0x1800027a0  mov     [rax+68h], ecx
0x1800027a3  mov     [rsi], rbx
0x1800027a6  jmp     short loc_1800027B0
0x1800027a8  mov     [rsi], r11
0x1800027ab  test    r11, r11
0x1800027ae  jnz     short loc_1800027B5
0x1800027b0  mov     ebx, 8007000Eh
0x1800027b5  mov     rsi, [rsp+28h+arg_8]
0x1800027ba  mov     eax, ebx
0x1800027bc  mov     rbx, [rsp+28h+arg_0]
0x1800027c1  add     rsp, 20h
0x1800027c5  pop     rdi
0x1800027c6  retn
```
