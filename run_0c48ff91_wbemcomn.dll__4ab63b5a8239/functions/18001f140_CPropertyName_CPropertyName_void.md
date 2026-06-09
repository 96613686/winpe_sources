# CPropertyName::~CPropertyName(void)

- ea: `0x18001f140`
- end: `0x18001f1bd`
- name: `??1CPropertyName@@QEAA@XZ`
- size: `125`
- prototype: `void __fastcall(CPropertyName *__hidden this)`
- caller_count: `7`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180044d24`
- `0x180044d3a`
- `0x180044de2`
- `0x180044df8`
- `0x180044e59`
- `0x180044f14`
- `0x180044f2a`

## callees

- `0x18001f140`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001f1b1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001f1b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f18e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f18e`

## pseudocode

```c
void __fastcall CPropertyName::~CPropertyName(CPropertyName *this)
{
  int i; // edi
  __int64 v3; // rax
  void *v4; // r8

  if ( *((_QWORD *)this + 1) )
  {
    for ( i = 0; i < *(_DWORD *)this; ++i )
    {
      v3 = *((_QWORD *)this + 1);
      if ( !*(_WORD *)(v3 + 16LL * i) )
        CoTaskMemFree(*(LPVOID *)(v3 + 16LL * i + 8));
    }
    if ( hHeap )
    {
      v4 = (void *)*((_QWORD *)this + 1);
      if ( v4 )
        HeapFree(hHeap, 0, v4);
    }
    *((_QWORD *)this + 1) = 0;
  }
  *(_DWORD *)this = 0;
  *((_DWORD *)this + 4) = 0;
  *((_QWORD *)this + 3) = 0;
}

```

## disassembly

```asm
0x18001f140  mov     [rsp+arg_0], rbx
0x18001f145  mov     [rsp+arg_8], rsi
0x18001f14a  push    rdi
0x18001f14b  sub     rsp, 20h
0x18001f14f  mov     rbx, rcx
0x18001f152  xor     esi, esi
0x18001f154  cmp     [rcx+8], rsi
0x18001f158  jnz     short loc_18001F173
0x18001f15a  mov     [rbx], esi
0x18001f15c  mov     [rbx+10h], esi
0x18001f15f  mov     [rbx+18h], rsi
0x18001f163  mov     rbx, [rsp+28h+arg_0]
0x18001f168  mov     rsi, [rsp+28h+arg_8]
0x18001f16d  add     rsp, 20h
0x18001f171  pop     rdi
0x18001f172  retn
0x18001f173  mov     edi, esi
0x18001f175  cmp     [rcx], esi
0x18001f177  jle     short loc_18001F19A
0x18001f179  movsxd  rcx, edi
0x18001f17c  add     rcx, rcx
0x18001f17f  mov     rax, [rbx+8]
0x18001f183  cmp     [rax+rcx*8], si
0x18001f187  jnz     short loc_18001F194
0x18001f189  mov     rcx, [rax+rcx*8+8]; pv
0x18001f18e  call    cs:__imp_CoTaskMemFree
0x18001f194  inc     edi
0x18001f196  cmp     edi, [rbx]
0x18001f198  jl      short loc_18001F179
0x18001f19a  mov     rcx, cs:hHeap; hHeap
0x18001f1a1  test    rcx, rcx
0x18001f1a4  jz      short loc_18001F1B7
0x18001f1a6  mov     r8, [rbx+8]; lpMem
0x18001f1aa  test    r8, r8
0x18001f1ad  jz      short loc_18001F1B7
0x18001f1af  xor     edx, edx; dwFlags
0x18001f1b1  call    cs:__imp_HeapFree
0x18001f1b7  mov     [rbx+8], rsi
0x18001f1bb  jmp     short loc_18001F15A
```
