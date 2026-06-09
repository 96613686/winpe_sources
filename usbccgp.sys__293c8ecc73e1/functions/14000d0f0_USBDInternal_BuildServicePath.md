# USBDInternal_BuildServicePath

- ea: `0x14000d0f0`
- end: `0x14000d23a`
- name: `USBDInternal_BuildServicePath`
- size: `330`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x14000cd78`

## callees

- `0x14000d0f0`
- `0x140014afc`
- `0x140014e00`
- `0x140015100`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000d215`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d215`
- `ntoskrnl!RtlCompareMemory` at `0x14000d14b`
- `ntoskrnl!RtlCompareMemory` at `0x14000d14b`
- `ntoskrnl!DbgPrintEx` at `0x14000d127`
- `ntoskrnl!DbgPrintEx` at `0x14000d1ae`
- `ntoskrnl!DbgPrintEx` at `0x14000d201`
- `ntoskrnl!DbgPrintEx` at `0x14000d127`
- `ntoskrnl!DbgPrintEx` at `0x14000d1ae`
- `ntoskrnl!DbgPrintEx` at `0x14000d201`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000d17a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000d17a`

## string_xrefs

- `0x14000d1a2`: `Couldnt allocate servicePath of size %d\n`

## pseudocode

```c
__int64 __fastcall USBDInternal_BuildServicePath(__int64 a1, _QWORD *a2)
{
  __int64 v2; // rbx
  void *v3; // rdi
  unsigned int v5; // ebx
  __int64 v6; // r15
  unsigned int v7; // ebp
  PVOID PoolWithTag; // rax
  NTSTRSAFE_PCWSTR v9; // r8
  NTSTATUS v10; // eax

  v2 = *(_QWORD *)(a1 + 8);
  v3 = 0;
  if ( *(_WORD *)(v2 + 56) > 0x10u && RtlCompareMemory(*(const void **)(v2 + 64), L"\\Driver\\", 0x10u) == 16 )
  {
    v6 = *(_QWORD *)(v2 + 64);
    v7 = *(unsigned __int16 *)(v2 + 56) - 16;
    PoolWithTag = ExAllocatePoolWithTag(PoolType, v7 + 24, 0x43627355u);
    v3 = PoolWithTag;
    if ( PoolWithTag )
    {
      memset(PoolWithTag, 0, v7 + 24);
      memmove(v3, (const void *)(v6 + 16), v7);
      v10 = RtlStringCbCatW((NTSTRSAFE_PWSTR)v3, v7 + 24, v9);
      v5 = v10;
      if ( v10 >= 0 )
      {
        v5 = 0;
      }
      else
      {
        if ( g_EnableDbgPrints )
          DbgPrintEx(0x4Du, 0, "RtlStringCchCatW failed with status 0x%x", v10);
        ExFreePoolWithTag(v3, 0x43627355u);
        v3 = 0;
      }
    }
    else
    {
      v5 = -1073741670;
      if ( g_EnableDbgPrints )
        DbgPrintEx(0x4Du, 0, "Couldnt allocate servicePath of size %d\n", v7 + 24);
    }
  }
  else
  {
    if ( g_EnableDbgPrints )
      DbgPrintEx(0x4Du, 0, "Unexpected Driver name, Drvobj 0x%p\n", (const void *)v2);
    v5 = -1073741595;
  }
  *a2 = v3;
  return v5;
}

```

## disassembly

```asm
0x14000d0f0  push    rbx
0x14000d0f2  push    rbp
0x14000d0f3  push    rsi
0x14000d0f4  push    rdi
0x14000d0f5  push    r14
0x14000d0f7  push    r15
0x14000d0f9  sub     rsp, 28h
0x14000d0fd  mov     rbx, [rcx+8]
0x14000d101  xor     edi, edi
0x14000d103  mov     r14, rdx
0x14000d106  lea     esi, [rdi+10h]
0x14000d109  cmp     [rbx+38h], si
0x14000d10d  ja      short loc_14000D13D
0x14000d10f  cmp     cs:g_EnableDbgPrints, dil
0x14000d116  jz      short loc_14000D133
0x14000d118  xor     edx, edx; Level
0x14000d11a  lea     r8, aUnexpectedDriv; "Unexpected Driver name, Drvobj 0x%p\n"
0x14000d121  mov     r9, rbx
0x14000d124  lea     ecx, [rdx+4Dh]; ComponentId
0x14000d127  call    cs:__imp_DbgPrintEx
0x14000d12e  nop     dword ptr [rax+rax+00h]
0x14000d133  mov     ebx, 0C00000E5h
0x14000d138  jmp     loc_14000D227
0x14000d13d  mov     rcx, [rbx+40h]; Source1
0x14000d141  lea     rdx, aDriver; "\\Driver\\"
0x14000d148  mov     r8, rsi; Length
0x14000d14b  call    cs:__imp_RtlCompareMemory
0x14000d152  nop     dword ptr [rax+rax+00h]
0x14000d157  cmp     rax, rsi
0x14000d15a  jnz     short loc_14000D10F
0x14000d15c  movzx   ebp, word ptr [rbx+38h]
0x14000d160  mov     r8d, 43627355h; Tag
0x14000d166  mov     r15, [rbx+40h]
0x14000d16a  add     ebp, 0FFFFFFF0h
0x14000d16d  mov     ecx, cs:PoolType; PoolType
0x14000d173  lea     esi, [rbp+18h]
0x14000d176  mov     edx, esi; NumberOfBytes
0x14000d178  mov     ebx, esi
0x14000d17a  call    cs:__imp_ExAllocatePoolWithTag
0x14000d181  nop     dword ptr [rax+rax+00h]
0x14000d186  mov     rdi, rax
0x14000d189  test    rax, rax
0x14000d18c  jnz     short loc_14000D1BC
0x14000d18e  cmp     cs:g_EnableDbgPrints, al
0x14000d194  mov     ebx, 0C000009Ah
0x14000d199  jz      loc_14000D227
0x14000d19f  mov     r9d, esi
0x14000d1a2  lea     r8, aCouldntAllocat; "Couldnt allocate servicePath of size %d"...
0x14000d1a9  xor     edx, edx; Level
0x14000d1ab  lea     ecx, [rax+4Dh]; ComponentId
0x14000d1ae  call    cs:__imp_DbgPrintEx
0x14000d1b5  nop     dword ptr [rax+rax+00h]
0x14000d1ba  jmp     short loc_14000D227
0x14000d1bc  mov     r8, rbx; Size
0x14000d1bf  xor     edx, edx; Val
0x14000d1c1  mov     rcx, rdi; void *
0x14000d1c4  call    memset
0x14000d1c9  mov     r8d, ebp; Size
0x14000d1cc  lea     rdx, [r15+10h]; Src
0x14000d1d0  mov     rcx, rdi; void *
0x14000d1d3  call    memmove
0x14000d1d8  mov     rdx, rbx; cbDest
0x14000d1db  mov     rcx, rdi; pszDest
0x14000d1de  call    RtlStringCbCatW
0x14000d1e3  mov     ebx, eax
0x14000d1e5  test    eax, eax
0x14000d1e7  jns     short loc_14000D225
0x14000d1e9  cmp     cs:g_EnableDbgPrints, 0
0x14000d1f0  jz      short loc_14000D20D
0x14000d1f2  xor     edx, edx; Level
0x14000d1f4  lea     r8, aRtlstringcchca; "RtlStringCchCatW failed with status 0x%"...
0x14000d1fb  mov     r9d, eax
0x14000d1fe  lea     ecx, [rdx+4Dh]; ComponentId
0x14000d201  call    cs:__imp_DbgPrintEx
0x14000d208  nop     dword ptr [rax+rax+00h]
0x14000d20d  mov     edx, 43627355h; Tag
0x14000d212  mov     rcx, rdi; P
0x14000d215  call    cs:__imp_ExFreePoolWithTag
0x14000d21c  nop     dword ptr [rax+rax+00h]
0x14000d221  xor     edi, edi
0x14000d223  jmp     short loc_14000D227
0x14000d225  xor     ebx, ebx
0x14000d227  mov     [r14], rdi
0x14000d22a  mov     eax, ebx
0x14000d22c  add     rsp, 28h
0x14000d230  pop     r15
0x14000d232  pop     r14
0x14000d234  pop     rdi
0x14000d235  pop     rsi
0x14000d236  pop     rbp
0x14000d237  pop     rbx
0x14000d238  retn
```
