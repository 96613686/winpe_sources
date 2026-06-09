# USBDInternal_BuildServicePath

- ea: `0x14001aba0`
- end: `0x14001acea`
- name: `USBDInternal_BuildServicePath`
- size: `330`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x14000f528`

## callees

- `0x14001aba0`
- `0x14003bd80`
- `0x140040b40`
- `0x140040e40`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x14001abfb`
- `ntoskrnl!RtlCompareMemory` at `0x14001abfb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001acc5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001acc5`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14001ac2a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14001ac2a`
- `ntoskrnl!DbgPrintEx` at `0x14001abd7`
- `ntoskrnl!DbgPrintEx` at `0x14001ac5e`
- `ntoskrnl!DbgPrintEx` at `0x14001acb1`
- `ntoskrnl!DbgPrintEx` at `0x14001abd7`
- `ntoskrnl!DbgPrintEx` at `0x14001ac5e`
- `ntoskrnl!DbgPrintEx` at `0x14001acb1`

## string_xrefs

- `0x14001ac52`: `Couldnt allocate servicePath of size %d\n`

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
    PoolWithTag = ExAllocatePoolWithTag(PoolType, v7 + 24, 0x56425355u);
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
        ExFreePoolWithTag(v3, 0x56425355u);
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
0x14001aba0  push    rbx
0x14001aba2  push    rbp
0x14001aba3  push    rsi
0x14001aba4  push    rdi
0x14001aba5  push    r14
0x14001aba7  push    r15
0x14001aba9  sub     rsp, 28h
0x14001abad  mov     rbx, [rcx+8]
0x14001abb1  xor     edi, edi
0x14001abb3  mov     r14, rdx
0x14001abb6  lea     esi, [rdi+10h]
0x14001abb9  cmp     [rbx+38h], si
0x14001abbd  ja      short loc_14001ABED
0x14001abbf  cmp     cs:g_EnableDbgPrints, dil
0x14001abc6  jz      short loc_14001ABE3
0x14001abc8  xor     edx, edx; Level
0x14001abca  lea     r8, aUnexpectedDriv; "Unexpected Driver name, Drvobj 0x%p\n"
0x14001abd1  mov     r9, rbx
0x14001abd4  lea     ecx, [rdx+4Dh]; ComponentId
0x14001abd7  call    cs:__imp_DbgPrintEx
0x14001abde  nop     dword ptr [rax+rax+00h]
0x14001abe3  mov     ebx, 0C00000E5h
0x14001abe8  jmp     loc_14001ACD7
0x14001abed  mov     rcx, [rbx+40h]; Source1
0x14001abf1  lea     rdx, aDriver; "\\Driver\\"
0x14001abf8  mov     r8, rsi; Length
0x14001abfb  call    cs:__imp_RtlCompareMemory
0x14001ac02  nop     dword ptr [rax+rax+00h]
0x14001ac07  cmp     rax, rsi
0x14001ac0a  jnz     short loc_14001ABBF
0x14001ac0c  movzx   ebp, word ptr [rbx+38h]
0x14001ac10  mov     r8d, 56425355h; Tag
0x14001ac16  mov     r15, [rbx+40h]
0x14001ac1a  add     ebp, 0FFFFFFF0h
0x14001ac1d  mov     ecx, cs:PoolType; PoolType
0x14001ac23  lea     esi, [rbp+18h]
0x14001ac26  mov     edx, esi; NumberOfBytes
0x14001ac28  mov     ebx, esi
0x14001ac2a  call    cs:__imp_ExAllocatePoolWithTag
0x14001ac31  nop     dword ptr [rax+rax+00h]
0x14001ac36  mov     rdi, rax
0x14001ac39  test    rax, rax
0x14001ac3c  jnz     short loc_14001AC6C
0x14001ac3e  cmp     cs:g_EnableDbgPrints, al
0x14001ac44  mov     ebx, 0C000009Ah
0x14001ac49  jz      loc_14001ACD7
0x14001ac4f  mov     r9d, esi
0x14001ac52  lea     r8, aCouldntAllocat; "Couldnt allocate servicePath of size %d"...
0x14001ac59  xor     edx, edx; Level
0x14001ac5b  lea     ecx, [rax+4Dh]; ComponentId
0x14001ac5e  call    cs:__imp_DbgPrintEx
0x14001ac65  nop     dword ptr [rax+rax+00h]
0x14001ac6a  jmp     short loc_14001ACD7
0x14001ac6c  mov     r8, rbx; Size
0x14001ac6f  xor     edx, edx; Val
0x14001ac71  mov     rcx, rdi; void *
0x14001ac74  call    memset
0x14001ac79  mov     r8d, ebp; Size
0x14001ac7c  lea     rdx, [r15+10h]; Src
0x14001ac80  mov     rcx, rdi; void *
0x14001ac83  call    memmove
0x14001ac88  mov     rdx, rbx; cbDest
0x14001ac8b  mov     rcx, rdi; pszDest
0x14001ac8e  call    RtlStringCbCatW
0x14001ac93  mov     ebx, eax
0x14001ac95  test    eax, eax
0x14001ac97  jns     short loc_14001ACD5
0x14001ac99  cmp     cs:g_EnableDbgPrints, 0
0x14001aca0  jz      short loc_14001ACBD
0x14001aca2  xor     edx, edx; Level
0x14001aca4  lea     r8, aRtlstringcchca; "RtlStringCchCatW failed with status 0x%"...
0x14001acab  mov     r9d, eax
0x14001acae  lea     ecx, [rdx+4Dh]; ComponentId
0x14001acb1  call    cs:__imp_DbgPrintEx
0x14001acb8  nop     dword ptr [rax+rax+00h]
0x14001acbd  mov     edx, 56425355h; Tag
0x14001acc2  mov     rcx, rdi; P
0x14001acc5  call    cs:__imp_ExFreePoolWithTag
0x14001accc  nop     dword ptr [rax+rax+00h]
0x14001acd1  xor     edi, edi
0x14001acd3  jmp     short loc_14001ACD7
0x14001acd5  xor     ebx, ebx
0x14001acd7  mov     [r14], rdi
0x14001acda  mov     eax, ebx
0x14001acdc  add     rsp, 28h
0x14001ace0  pop     r15
0x14001ace2  pop     r14
0x14001ace4  pop     rdi
0x14001ace5  pop     rsi
0x14001ace6  pop     rbp
0x14001ace7  pop     rbx
0x14001ace8  retn
```
