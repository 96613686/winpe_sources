# CacheExposureControlValues

- ea: `0x140028f64`
- end: `0x14002910d`
- name: `CacheExposureControlValues`
- size: `425`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140027ef0`

## callees

- `0x140004bac`
- `0x140008640`
- `0x140028f64`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14002900b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002900b`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140028f92`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140028f92`
- `ks!KsAddItemToObjectBag` at `0x140028fc5`
- `ks!KsAddItemToObjectBag` at `0x140028fc5`
- `ks!KsRemoveItemFromObjectBag` at `0x1400290ef`
- `ks!KsRemoveItemFromObjectBag` at `0x1400290ef`

## pseudocode

```c
__int64 __fastcall CacheExposureControlValues(__int64 a1, char a2, char a3, __int64 a4)
{
  char *PoolWithTag; // rax
  char *v9; // rbx
  int v10; // edx
  int v11; // ecx
  NTSTATUS v12; // edi
  int v13; // r9d
  __int64 v15; // r14
  int v16; // edx
  int v17; // ecx
  int v18; // r9d
  int v19; // edx
  int v20; // ecx
  int v21; // r9d
  int v22; // [rsp+20h] [rbp-68h]
  int v23; // [rsp+20h] [rbp-68h]
  int v24; // [rsp+20h] [rbp-68h]
  size_t Size; // [rsp+30h] [rbp-58h]
  size_t Sizea; // [rsp+30h] [rbp-58h]
  size_t Sizeb; // [rsp+30h] [rbp-58h]

  PoolWithTag = (char *)ExAllocatePoolWithTag((POOL_TYPE)1536, 0xCu, 0x56425355u);
  v9 = PoolWithTag;
  if ( ExPoolZeroingNativelySupported )
  {
    if ( PoolWithTag )
      goto LABEL_4;
    return 3221225626LL;
  }
  if ( !PoolWithTag )
    return 3221225626LL;
  *(_QWORD *)PoolWithTag = 0;
  *((_DWORD *)PoolWithTag + 2) = 0;
LABEL_4:
  v12 = KsAddItemToObjectBag(*(KSOBJECT_BAG *)(a1 + 8), PoolWithTag, FreeMem);
  if ( v12 >= 0 )
  {
    *(_QWORD *)(a4 + 472) = v9;
    v15 = *(_QWORD *)(a1 + 16);
    LOBYTE(v13) = a2;
    LOBYTE(v10) = -126;
    LOBYTE(v11) = -95;
    LODWORD(Size) = 4;
    LOBYTE(v22) = a3;
    v12 = SubmitControlRequest(v11, v10, 1024, v13, v22, v9, Size, a4, v15);
    if ( v12 < 0 )
      goto LABEL_14;
    LODWORD(Sizea) = 4;
    LOBYTE(v18) = a2;
    LOBYTE(v16) = -125;
    LOBYTE(v17) = -95;
    LOBYTE(v23) = a3;
    v12 = SubmitControlRequest(v17, v16, 1024, v18, v23, v9 + 4, Sizea, a4, v15);
    if ( v12 < 0
      || (LODWORD(Sizeb) = 4,
          LOBYTE(v21) = a2,
          LOBYTE(v19) = -124,
          LOBYTE(v20) = -95,
          LOBYTE(v24) = a3,
          v12 = SubmitControlRequest(v20, v19, 1024, v21, v24, v9 + 8, Sizeb, a4, v15),
          v12 < 0) )
    {
LABEL_14:
      *(_QWORD *)(a4 + 472) = 0;
      KsRemoveItemFromObjectBag(*(KSOBJECT_BAG *)(a1 + 8), v9, 1u);
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 26, WPP_ebeb762af7253cd886177c9038d34848_Traceguids);
    ExFreePoolWithTag(v9, 0x56425355u);
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x140028f64  push    rbx
0x140028f66  push    rbp
0x140028f67  push    rsi
0x140028f68  push    rdi
0x140028f69  push    r12
0x140028f6b  push    r14
0x140028f6d  push    r15
0x140028f6f  sub     rsp, 50h
0x140028f73  mov     r15b, r8b
0x140028f76  mov     r12b, dl
0x140028f79  mov     rbp, rcx
0x140028f7c  mov     r14d, 56425355h
0x140028f82  mov     r8d, r14d; Tag
0x140028f85  mov     edx, 0Ch; NumberOfBytes
0x140028f8a  mov     ecx, 600h; PoolType
0x140028f8f  mov     rsi, r9
0x140028f92  call    cs:__imp_ExAllocatePoolWithTag
0x140028f99  nop     dword ptr [rax+rax+00h]
0x140028f9e  cmp     cs:ExPoolZeroingNativelySupported, 0
0x140028fa5  mov     rbx, rax
0x140028fa8  jnz     short loc_14002901C
0x140028faa  test    rax, rax
0x140028fad  jz      short loc_140029021
0x140028faf  xor     eax, eax
0x140028fb1  mov     [rbx], rax
0x140028fb4  mov     [rbx+8], eax
0x140028fb7  mov     rcx, [rbp+8]; ObjectBag
0x140028fbb  lea     r8, FreeMem; Free
0x140028fc2  mov     rdx, rbx; Item
0x140028fc5  call    cs:__imp_KsAddItemToObjectBag
0x140028fcc  nop     dword ptr [rax+rax+00h]
0x140028fd1  mov     edi, eax
0x140028fd3  test    eax, eax
0x140028fd5  jns     short loc_14002902B
0x140028fd7  mov     rcx, cs:WPP_GLOBAL_Control
0x140028fde  lea     rax, WPP_GLOBAL_Control
0x140028fe5  cmp     rcx, rax
0x140028fe8  jz      short loc_140029005
0x140028fea  cmp     byte ptr [rcx+29h], 2
0x140028fee  jb      short loc_140029005
0x140028ff0  mov     rcx, [rcx+18h]
0x140028ff4  lea     r8, WPP_ebeb762af7253cd886177c9038d34848_Traceguids
0x140028ffb  mov     edx, 1Ah
0x140029000  call    WPP_SF_
0x140029005  mov     edx, r14d; Tag
0x140029008  mov     rcx, rbx; P
0x14002900b  call    cs:__imp_ExFreePoolWithTag
0x140029012  nop     dword ptr [rax+rax+00h]
0x140029017  jmp     loc_1400290FB
0x14002901c  test    rbx, rbx
0x14002901f  jnz     short loc_140028FB7
0x140029021  mov     eax, 0C000009Ah
0x140029026  jmp     loc_1400290FD
0x14002902b  mov     [rsi+1D8h], rbx
0x140029032  mov     r8d, 400h; int
0x140029038  mov     r14, [rbp+10h]
0x14002903c  mov     r9b, r12b; int
0x14002903f  mov     [rsp+88h+var_48], r14; __int64
0x140029044  mov     dl, 82h; int
0x140029046  mov     [rsp+88h+var_50], rsi; __int64
0x14002904b  mov     cl, 0A1h; int
0x14002904d  mov     dword ptr [rsp+88h+Size], 4; Size
0x140029055  mov     [rsp+88h+var_60], rbx; void *
0x14002905a  mov     byte ptr [rsp+88h+var_68], r15b; int
0x14002905f  call    SubmitControlRequest
0x140029064  mov     edi, eax
0x140029066  test    eax, eax
0x140029068  js      short loc_1400290DA
0x14002906a  mov     [rsp+88h+var_48], r14; __int64
0x14002906f  lea     rax, [rbx+4]
0x140029073  mov     [rsp+88h+var_50], rsi; __int64
0x140029078  mov     r8d, 400h; int
0x14002907e  mov     dword ptr [rsp+88h+Size], 4; Size
0x140029086  mov     r9b, r12b; int
0x140029089  mov     [rsp+88h+var_60], rax; void *
0x14002908e  mov     dl, 83h; int
0x140029090  mov     cl, 0A1h; int
0x140029092  mov     byte ptr [rsp+88h+var_68], r15b; int
0x140029097  call    SubmitControlRequest
0x14002909c  mov     edi, eax
0x14002909e  test    eax, eax
0x1400290a0  js      short loc_1400290DA
0x1400290a2  mov     [rsp+88h+var_48], r14; __int64
0x1400290a7  lea     rax, [rbx+8]
0x1400290ab  mov     [rsp+88h+var_50], rsi; __int64
0x1400290b0  mov     r8d, 400h; int
0x1400290b6  mov     dword ptr [rsp+88h+Size], 4; Size
0x1400290be  mov     r9b, r12b; int
0x1400290c1  mov     [rsp+88h+var_60], rax; void *
0x1400290c6  mov     dl, 84h; int
0x1400290c8  mov     cl, 0A1h; int
0x1400290ca  mov     byte ptr [rsp+88h+var_68], r15b; int
0x1400290cf  call    SubmitControlRequest
0x1400290d4  mov     edi, eax
0x1400290d6  test    eax, eax
0x1400290d8  jns     short loc_1400290FB
0x1400290da  mov     qword ptr [rsi+1D8h], 0
0x1400290e5  mov     r8b, 1; Free
0x1400290e8  mov     rcx, [rbp+8]; ObjectBag
0x1400290ec  mov     rdx, rbx; Item
0x1400290ef  call    cs:__imp_KsRemoveItemFromObjectBag
0x1400290f6  nop     dword ptr [rax+rax+00h]
0x1400290fb  mov     eax, edi
0x1400290fd  add     rsp, 50h
0x140029101  pop     r15
0x140029103  pop     r14
0x140029105  pop     r12
0x140029107  pop     rdi
0x140029108  pop     rsi
0x140029109  pop     rbp
0x14002910a  pop     rbx
0x14002910b  retn
```
