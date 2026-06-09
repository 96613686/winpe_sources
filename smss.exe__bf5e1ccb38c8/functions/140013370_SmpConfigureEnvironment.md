# SmpConfigureEnvironment

- ea: `0x140013370`
- end: `0x140013465`
- name: `SmpConfigureEnvironment`
- size: `245`
- prototype: `__int64 __fastcall(wchar_t *Str1)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callees

- `0x1400010ec`
- `0x140013370`
- `0x14001cc11`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x14001339a`
- `ntdll!RtlInitUnicodeString` at `0x1400133a8`
- `ntdll!RtlInitUnicodeString` at `0x140013454`
- `ntdll!RtlInitUnicodeString` at `0x14001339a`
- `ntdll!RtlInitUnicodeString` at `0x1400133a8`
- `ntdll!RtlInitUnicodeString` at `0x140013454`
- `ntdll!RtlAllocateHeap` at `0x140013420`
- `ntdll!RtlAllocateHeap` at `0x140013420`
- `ntdll!_wcsicmp` at `0x1400133ed`
- `ntdll!_wcsicmp` at `0x1400133ed`
- `ntdll!RtlSetEnvironmentVariable` at `0x1400133ba`
- `ntdll!RtlSetEnvironmentVariable` at `0x1400133ba`

## string_xrefs

- `0x1400133cb`: `SmpConfigureEnvironment`

## pseudocode

```c
__int64 __fastcall SmpConfigureEnvironment(wchar_t *Str1, __int64 a2, const WCHAR *a3, unsigned int a4)
{
  SIZE_T v5; // rbp
  NTSTATUS v7; // eax
  unsigned int v8; // ebx
  WCHAR *Heap; // rax
  const WCHAR *v11; // rbx
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-48h] BYREF
  struct _UNICODE_STRING Value; // [rsp+30h] [rbp-38h] BYREF

  v5 = a4;
  DestinationString = 0;
  Value = 0;
  RtlInitUnicodeString(&DestinationString, Str1);
  RtlInitUnicodeString(&Value, a3);
  v7 = RtlSetEnvironmentVariable(0, &DestinationString, &Value);
  v8 = v7;
  if ( v7 < 0 )
  {
    SmpLogFailureString("SmpConfigureEnvironment", 8105, DestinationString.Buffer, (unsigned int)v7);
    return v8;
  }
  if ( !_wcsicmp(Str1, L"Path") && ++SmpCalledConfigEnv == 2 )
  {
    Heap = (WCHAR *)RtlAllocateHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), SmBaseTag, v5);
    SmpDefaultLibPathBuffer = (__int64)Heap;
    v11 = Heap;
    if ( !Heap )
      return 3221225495LL;
    memcpy_0(Heap, a3, v5);
    RtlInitUnicodeString(&SmpDefaultLibPath, v11);
  }
  return 0;
}

```

## disassembly

```asm
0x140013370  push    rbx
0x140013372  push    rbp
0x140013373  push    rsi
0x140013374  push    rdi
0x140013375  sub     rsp, 48h
0x140013379  mov     rdi, rcx
0x14001337c  mov     ebp, r9d
0x14001337f  xorps   xmm0, xmm0
0x140013382  xorps   xmm1, xmm1
0x140013385  mov     rdx, rcx; SourceString
0x140013388  mov     rsi, r8
0x14001338b  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x140013390  movups  xmmword ptr [rsp+68h+DestinationString.Length], xmm0
0x140013395  movups  xmmword ptr [rsp+68h+Value.Length], xmm1
0x14001339a  call    cs:__imp_RtlInitUnicodeString
0x1400133a0  mov     rdx, rsi; SourceString
0x1400133a3  lea     rcx, [rsp+68h+Value]; DestinationString
0x1400133a8  call    cs:__imp_RtlInitUnicodeString
0x1400133ae  lea     r8, [rsp+68h+Value]; Value
0x1400133b3  xor     ecx, ecx; Environment
0x1400133b5  lea     rdx, [rsp+68h+DestinationString]; Name
0x1400133ba  call    cs:__imp_RtlSetEnvironmentVariable
0x1400133c0  mov     ebx, eax
0x1400133c2  test    eax, eax
0x1400133c4  jns     short loc_1400133E3
0x1400133c6  mov     r8, [rsp+68h+DestinationString.Buffer]
0x1400133cb  lea     rcx, aSmpconfigureen; "SmpConfigureEnvironment"
0x1400133d2  mov     r9d, eax
0x1400133d5  mov     edx, 1FA9h
0x1400133da  call    SmpLogFailureString
0x1400133df  mov     eax, ebx
0x1400133e1  jmp     short loc_14001345C
0x1400133e3  lea     rdx, aPath; "Path"
0x1400133ea  mov     rcx, rdi; Str1
0x1400133ed  call    cs:__imp__wcsicmp
0x1400133f3  test    eax, eax
0x1400133f5  jnz     short loc_14001345A
0x1400133f7  mov     eax, cs:SmpCalledConfigEnv
0x1400133fd  inc     eax
0x1400133ff  mov     cs:SmpCalledConfigEnv, eax
0x140013405  cmp     eax, 2
0x140013408  jnz     short loc_14001345A
0x14001340a  mov     rcx, gs:60h
0x140013413  mov     r8, rbp; Size
0x140013416  mov     edx, cs:SmBaseTag; Flags
0x14001341c  mov     rcx, [rcx+30h]; HeapHandle
0x140013420  call    cs:__imp_RtlAllocateHeap
0x140013426  mov     cs:SmpDefaultLibPathBuffer, rax
0x14001342d  mov     rbx, rax
0x140013430  test    rax, rax
0x140013433  jnz     short loc_14001343C
0x140013435  mov     eax, 0C0000017h
0x14001343a  jmp     short loc_14001345C
0x14001343c  mov     r8, rbp; MaxCount
0x14001343f  mov     rdx, rsi; Src
0x140013442  mov     rcx, rbx; void *
0x140013445  call    memcpy_0
0x14001344a  mov     rdx, rbx; SourceString
0x14001344d  lea     rcx, SmpDefaultLibPath; DestinationString
0x140013454  call    cs:__imp_RtlInitUnicodeString
0x14001345a  xor     eax, eax
0x14001345c  add     rsp, 48h
0x140013460  pop     rdi
0x140013461  pop     rsi
0x140013462  pop     rbp
0x140013463  pop     rbx
0x140013464  retn
```
