# USBDInternal_BuildServicePath

- ea: `0x140042a0c`
- end: `0x140042bf6`
- name: `USBDInternal_BuildServicePath`
- size: `490`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x140042d48`

## callees

- `0x140042a0c`
- `0x140045640`
- `0x140045940`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140042bd2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140042bd2`
- `ntoskrnl!RtlCompareMemory` at `0x140042a6f`
- `ntoskrnl!RtlCompareMemory` at `0x140042a6f`
- `ntoskrnl!DbgPrintEx` at `0x140042a4b`
- `ntoskrnl!DbgPrintEx` at `0x140042ad3`
- `ntoskrnl!DbgPrintEx` at `0x140042bbe`
- `ntoskrnl!DbgPrintEx` at `0x140042a4b`
- `ntoskrnl!DbgPrintEx` at `0x140042ad3`
- `ntoskrnl!DbgPrintEx` at `0x140042bbe`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140042a9e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140042a9e`

## string_xrefs

- `0x140042ac7`: `Couldnt allocate servicePath of size %d\n`

## pseudocode

```c
__int64 __fastcall USBDInternal_BuildServicePath(__int64 a1, _QWORD *a2)
{
  __int64 v2; // rbx
  char *v4; // rsi
  unsigned int v5; // ebx
  __int64 v6; // r14
  unsigned int v7; // ebx
  unsigned int v8; // ebp
  char *PoolWithTag; // rax
  unsigned __int64 v10; // rdi
  unsigned __int64 v11; // rcx
  _WORD *v12; // rax
  unsigned __int64 v13; // rax
  const wchar_t *v14; // r8
  __int64 v15; // rcx
  char *v16; // rdx
  unsigned __int64 i; // rdi
  char *v18; // rcx

  v2 = *(_QWORD *)(a1 + 8);
  v4 = 0;
  if ( *(_WORD *)(v2 + 56) > 0x10u && RtlCompareMemory(*(const void **)(v2 + 64), L"\\Driver\\", 0x10u) == 16 )
  {
    v6 = *(_QWORD *)(v2 + 64);
    v7 = *(unsigned __int16 *)(v2 + 56) - 16;
    v8 = v7 + 24;
    PoolWithTag = (char *)ExAllocatePoolWithTag(PoolType, v7 + 24, 0x68334855u);
    v4 = PoolWithTag;
    if ( PoolWithTag )
    {
      memset(PoolWithTag, 0, v7 + 24);
      memmove(v4, (const void *)(v6 + 16), v7);
      v10 = (unsigned __int64)(v7 + 24) >> 1;
      if ( v10 )
      {
        v11 = (unsigned __int64)(v7 + 24) >> 1;
        v12 = v4;
        do
        {
          if ( !*v12 )
            break;
          ++v12;
          --v11;
        }
        while ( v11 );
        v5 = v11 == 0 ? 0xC000000D : 0;
        if ( v11 )
          v13 = v10 - v11;
        else
          v13 = 0;
        if ( v11 )
        {
          v14 = L"\\Parameters";
          v15 = 2147483646;
          v16 = &v4[2 * v13];
          for ( i = v10 - v13; i; --i )
          {
            if ( !v15 )
              break;
            if ( !*v14 )
              break;
            *(_WORD *)v16 = *v14++;
            v16 += 2;
            --v15;
          }
          v18 = v16 - 2;
          v5 = i == 0 ? 0x80000005 : 0;
          if ( i )
            v18 = v16;
          *(_WORD *)v18 = 0;
          if ( i )
          {
            v5 = 0;
            goto LABEL_29;
          }
        }
      }
      else
      {
        v5 = -1073741811;
      }
      if ( g_EnableDbgPrints )
        DbgPrintEx(0x4Du, 0, "RtlStringCchCatW failed with status 0x%x", v5);
      ExFreePoolWithTag(v4, 0x68334855u);
      v4 = 0;
    }
    else
    {
      v5 = -1073741670;
      if ( g_EnableDbgPrints )
        DbgPrintEx(0x4Du, 0, "Couldnt allocate servicePath of size %d\n", v8);
    }
  }
  else
  {
    if ( g_EnableDbgPrints )
      DbgPrintEx(0x4Du, 0, "Unexpected Driver name, Drvobj 0x%p\n", (const void *)v2);
    v5 = -1073741595;
  }
LABEL_29:
  *a2 = v4;
  return v5;
}

```

## disassembly

```asm
0x140042a0c  push    rbx
0x140042a0e  push    rbp
0x140042a0f  push    rsi
0x140042a10  push    rdi
0x140042a11  push    r12
0x140042a13  push    r14
0x140042a15  push    r15
0x140042a17  sub     rsp, 20h
0x140042a1b  mov     rbx, [rcx+8]
0x140042a1f  xor     r12d, r12d
0x140042a22  mov     r15, rdx
0x140042a25  mov     esi, r12d
0x140042a28  lea     edi, [r12+10h]
0x140042a2d  cmp     [rbx+38h], di
0x140042a31  ja      short loc_140042A61
0x140042a33  cmp     cs:g_EnableDbgPrints, r12b
0x140042a3a  jz      short loc_140042A57
0x140042a3c  xor     edx, edx; Level
0x140042a3e  lea     r8, aUnexpectedDriv; "Unexpected Driver name, Drvobj 0x%p\n"
0x140042a45  mov     r9, rbx
0x140042a48  lea     ecx, [rdx+4Dh]; ComponentId
0x140042a4b  call    cs:__imp_DbgPrintEx
0x140042a52  nop     dword ptr [rax+rax+00h]
0x140042a57  mov     ebx, 0C00000E5h
0x140042a5c  jmp     loc_140042BE1
0x140042a61  mov     rcx, [rbx+40h]; Source1
0x140042a65  lea     rdx, aDriver; "\\Driver\\"
0x140042a6c  mov     r8, rdi; Length
0x140042a6f  call    cs:__imp_RtlCompareMemory
0x140042a76  nop     dword ptr [rax+rax+00h]
0x140042a7b  cmp     rax, rdi
0x140042a7e  jnz     short loc_140042A33
0x140042a80  mov     r14, [rbx+40h]
0x140042a84  mov     r8d, 68334855h; Tag
0x140042a8a  movzx   ebx, word ptr [rbx+38h]
0x140042a8e  mov     ecx, cs:PoolType; PoolType
0x140042a94  add     ebx, 0FFFFFFF0h
0x140042a97  lea     ebp, [rbx+18h]
0x140042a9a  mov     edx, ebp; NumberOfBytes
0x140042a9c  mov     edi, ebp
0x140042a9e  call    cs:__imp_ExAllocatePoolWithTag
0x140042aa5  nop     dword ptr [rax+rax+00h]
0x140042aaa  mov     rsi, rax
0x140042aad  test    rax, rax
0x140042ab0  jnz     short loc_140042AE4
0x140042ab2  cmp     cs:g_EnableDbgPrints, r12b
0x140042ab9  mov     ebx, 0C000009Ah
0x140042abe  jz      loc_140042BE1
0x140042ac4  mov     r9d, ebp
0x140042ac7  lea     r8, aCouldntAllocat; "Couldnt allocate servicePath of size %d"...
0x140042ace  xor     edx, edx; Level
0x140042ad0  lea     ecx, [rax+4Dh]; ComponentId
0x140042ad3  call    cs:__imp_DbgPrintEx
0x140042ada  nop     dword ptr [rax+rax+00h]
0x140042adf  jmp     loc_140042BE1
0x140042ae4  mov     r8, rdi; Size
0x140042ae7  xor     edx, edx; Val
0x140042ae9  mov     rcx, rsi; void *
0x140042aec  call    memset
0x140042af1  mov     r8d, ebx; Size
0x140042af4  lea     rdx, [r14+10h]; Src
0x140042af8  mov     rcx, rsi; void *
0x140042afb  call    memmove
0x140042b00  shr     rdi, 1
0x140042b03  jz      loc_140042BA1
0x140042b09  mov     rcx, rdi
0x140042b0c  mov     rax, rsi
0x140042b0f  cmp     [rax], r12w
0x140042b13  jz      short loc_140042B1F
0x140042b15  add     rax, 2
0x140042b19  sub     rcx, 1
0x140042b1d  jnz     short loc_140042B0F
0x140042b1f  mov     rax, rcx
0x140042b22  neg     rax
0x140042b25  sbb     ebx, ebx
0x140042b27  not     ebx
0x140042b29  and     ebx, 0C000000Dh
0x140042b2f  test    rcx, rcx
0x140042b32  jz      short loc_140042B3C
0x140042b34  mov     rax, rdi
0x140042b37  sub     rax, rcx
0x140042b3a  jmp     short loc_140042B3F
0x140042b3c  mov     rax, r12
0x140042b3f  test    rcx, rcx
0x140042b42  jz      short loc_140042BA6
0x140042b44  lea     r8, aParameters; "\\Parameters"
0x140042b4b  mov     ecx, 7FFFFFFEh
0x140042b50  lea     rdx, [rsi+rax*2]
0x140042b54  sub     rdi, rax
0x140042b57  jz      short loc_140042B7B
0x140042b59  test    rcx, rcx
0x140042b5c  jz      short loc_140042B7B
0x140042b5e  movzx   eax, word ptr [r8]
0x140042b62  test    ax, ax
0x140042b65  jz      short loc_140042B7B
0x140042b67  mov     [rdx], ax
0x140042b6a  add     r8, 2
0x140042b6e  add     rdx, 2
0x140042b72  dec     rcx
0x140042b75  sub     rdi, 1
0x140042b79  jnz     short loc_140042B59
0x140042b7b  mov     rax, rdi
0x140042b7e  lea     rcx, [rdx-2]
0x140042b82  neg     rax
0x140042b85  sbb     ebx, ebx
0x140042b87  not     ebx
0x140042b89  and     ebx, 80000005h
0x140042b8f  test    rdi, rdi
0x140042b92  cmovnz  rcx, rdx
0x140042b96  mov     [rcx], r12w
0x140042b9a  jz      short loc_140042BA6
0x140042b9c  mov     ebx, r12d
0x140042b9f  jmp     short loc_140042BE1
0x140042ba1  mov     ebx, 0C000000Dh
0x140042ba6  cmp     cs:g_EnableDbgPrints, r12b
0x140042bad  jz      short loc_140042BCA
0x140042baf  xor     edx, edx; Level
0x140042bb1  lea     r8, aRtlstringcchca; "RtlStringCchCatW failed with status 0x%"...
0x140042bb8  mov     r9d, ebx
0x140042bbb  lea     ecx, [rdx+4Dh]; ComponentId
0x140042bbe  call    cs:__imp_DbgPrintEx
0x140042bc5  nop     dword ptr [rax+rax+00h]
0x140042bca  mov     edx, 68334855h; Tag
0x140042bcf  mov     rcx, rsi; P
0x140042bd2  call    cs:__imp_ExFreePoolWithTag
0x140042bd9  nop     dword ptr [rax+rax+00h]
0x140042bde  mov     rsi, r12
0x140042be1  mov     [r15], rsi
0x140042be4  mov     eax, ebx
0x140042be6  add     rsp, 20h
0x140042bea  pop     r15
0x140042bec  pop     r14
0x140042bee  pop     r12
0x140042bf0  pop     rdi
0x140042bf1  pop     rsi
0x140042bf2  pop     rbp
0x140042bf3  pop     rbx
0x140042bf4  retn
```
