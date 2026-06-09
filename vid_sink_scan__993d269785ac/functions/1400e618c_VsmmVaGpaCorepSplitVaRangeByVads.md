# VsmmVaGpaCorepSplitVaRangeByVads

- ea: `0x1400e618c`
- end: `0x1400e6305`
- name: `VsmmVaGpaCorepSplitVaRangeByVads`
- size: `377`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1400e593c`

## callees

- `0x140038630`
- `0x1400e618c`
- `0x1400eae60`

## import_xrefs

- `ntoskrnl!ObOpenObjectByPointer` at `0x1400e61e0`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400e61e0`
- `ntoskrnl!PsProcessType` at `0x1400e61b2`
- `ntoskrnl!ZwClose` at `0x1400e62e1`
- `ntoskrnl!ZwClose` at `0x1400e62e1`
- `ntoskrnl!ZwQueryVirtualMemory` at `0x1400e6257`
- `ntoskrnl!ZwQueryVirtualMemory` at `0x1400e6257`

## pseudocode

```c
__int64 __fastcall VsmmVaGpaCorepSplitVaRangeByVads(__int64 a1, __int64 a2, unsigned __int64 a3, unsigned __int64 a4)
{
  NTSTATUS v8; // ebx
  unsigned __int64 v9; // rdi
  __int128 MemoryInformation; // [rsp+40h] [rbp-48h] BYREF
  __int128 v12; // [rsp+50h] [rbp-38h]
  __int128 v13; // [rsp+60h] [rbp-28h]
  HANDLE ProcessHandle; // [rsp+98h] [rbp+10h] BYREF

  ProcessHandle = (HANDLE)-1LL;
  v8 = ObOpenObjectByPointer(*(PVOID *)(a2 + 56), 0x200u, 0, 0x1FFFFFu, (POBJECT_TYPE)PsProcessType, 0, &ProcessHandle);
  if ( v8 >= 0 )
  {
    while ( a3 < a4 )
    {
      MemoryInformation = 0;
      v12 = 0;
      v13 = 0;
      v8 = ZwQueryVirtualMemory(
             ProcessHandle,
             (PVOID)(a3 << 12),
             MemoryBasicVlmInformation,
             &MemoryInformation,
             0x30u,
             0);
      if ( v8 < 0 )
      {
        VidTraceErrorInternal0("VsmmVaGpaCorepSplitVaRangeByVads", "onecore\\vm\\vid\\sys\\vsmm\\vsmmvagpacore.c", 2557);
        goto LABEL_11;
      }
      v9 = (unsigned __int64)(v12 + MemoryInformation - 1) >> 12;
      if ( v9 >= a4 )
        break;
      v8 = VsmmVaGpaCorepSplitVaRange(a1, a2, (unsigned __int64)(v12 + MemoryInformation - 1) >> 12);
      if ( v8 < 0 )
      {
        VidTraceErrorInternal0("VsmmVaGpaCorepSplitVaRangeByVads", "onecore\\vm\\vid\\sys\\vsmm\\vsmmvagpacore.c", 2576);
        goto LABEL_11;
      }
      a3 = v9 + 1;
    }
    v8 = 0;
  }
  else
  {
    VidTraceErrorInternal0("VsmmVaGpaCorepSplitVaRangeByVads", "onecore\\vm\\vid\\sys\\vsmm\\vsmmvagpacore.c", 2541);
  }
LABEL_11:
  if ( ProcessHandle != (HANDLE)-1LL )
    ZwClose(ProcessHandle);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1400e618c  mov     r11, rsp
0x1400e618f  mov     [r11+8], rbx
0x1400e6193  mov     [r11+18h], rbp
0x1400e6197  push    rsi
0x1400e6198  push    rdi
0x1400e6199  push    r14
0x1400e619b  sub     rsp, 70h
0x1400e619f  lea     rax, [r11+10h]
0x1400e61a3  mov     qword ptr [r11+10h], 0FFFFFFFFFFFFFFFFh
0x1400e61ab  mov     [r11-58h], rax
0x1400e61af  mov     rbp, rdx
0x1400e61b2  mov     rax, cs:__imp_PsProcessType
0x1400e61b9  mov     rsi, r9
0x1400e61bc  mov     rdi, r8
0x1400e61bf  mov     [rsp+88h+AccessMode], 0; AccessMode
0x1400e61c4  mov     r14, rcx
0x1400e61c7  mov     r9d, 1FFFFFh; DesiredAccess
0x1400e61cd  mov     rcx, [rbp+38h]; Object
0x1400e61d1  xor     r8d, r8d; PassedAccessState
0x1400e61d4  mov     r10, [rax]
0x1400e61d7  mov     edx, 200h; HandleAttributes
0x1400e61dc  mov     [r11-68h], r10
0x1400e61e0  call    cs:__imp_ObOpenObjectByPointer
0x1400e61e7  nop     dword ptr [rax+rax+00h]
0x1400e61ec  mov     ebx, eax
0x1400e61ee  test    eax, eax
0x1400e61f0  jns     short loc_1400E6210
0x1400e61f2  mov     r8d, 9EDh
0x1400e61f8  lea     rdx, aOnecoreVmVidSy_60; "onecore\\vm\\vid\\sys\\vsmm\\vsmmvagpac"...
0x1400e61ff  lea     rcx, aVsmmvagpacorep_0; "VsmmVaGpaCorepSplitVaRangeByVads"
0x1400e6206  call    VidTraceErrorInternal0
0x1400e620b  jmp     loc_1400E62D3
0x1400e6210  cmp     rdi, rsi
0x1400e6213  jnb     loc_1400E62D1
0x1400e6219  mov     rcx, [rsp+88h+ProcessHandle]; ProcessHandle
0x1400e6221  lea     r9, [rsp+88h+MemoryInformation]; MemoryInformation
0x1400e6226  xorps   xmm0, xmm0
0x1400e6229  shl     rdi, 0Ch
0x1400e622d  mov     rdx, rdi; BaseAddress
0x1400e6230  mov     qword ptr [rsp+88h+AccessMode], 0; ReturnLength
0x1400e6239  mov     r8d, 3; MemoryInformationClass
0x1400e623f  mov     [rsp+88h+MemoryInformationLength], 30h ; '0'; MemoryInformationLength
0x1400e6248  movups  [rsp+88h+MemoryInformation], xmm0
0x1400e624d  movups  [rsp+88h+var_38], xmm0
0x1400e6252  movups  [rsp+88h+var_28], xmm0
0x1400e6257  call    cs:__imp_ZwQueryVirtualMemory
0x1400e625e  nop     dword ptr [rax+rax+00h]
0x1400e6263  mov     ebx, eax
0x1400e6265  test    eax, eax
0x1400e6267  js      short loc_1400E62B6
0x1400e6269  mov     rdi, qword ptr [rsp+88h+MemoryInformation]
0x1400e626e  dec     rdi
0x1400e6271  add     rdi, qword ptr [rsp+88h+var_38]
0x1400e6276  shr     rdi, 0Ch
0x1400e627a  cmp     rdi, rsi
0x1400e627d  jnb     short loc_1400E62D1
0x1400e627f  mov     r8, rdi
0x1400e6282  mov     rdx, rbp
0x1400e6285  mov     rcx, r14
0x1400e6288  call    VsmmVaGpaCorepSplitVaRange
0x1400e628d  mov     ebx, eax
0x1400e628f  test    eax, eax
0x1400e6291  js      short loc_1400E629B
0x1400e6293  inc     rdi
0x1400e6296  jmp     loc_1400E6210
0x1400e629b  mov     r8d, 0A10h
0x1400e62a1  lea     rdx, aOnecoreVmVidSy_60; "onecore\\vm\\vid\\sys\\vsmm\\vsmmvagpac"...
0x1400e62a8  lea     rcx, aVsmmvagpacorep_0; "VsmmVaGpaCorepSplitVaRangeByVads"
0x1400e62af  call    VidTraceErrorInternal0
0x1400e62b4  jmp     short loc_1400E62D3
0x1400e62b6  mov     r8d, 9FDh
0x1400e62bc  lea     rdx, aOnecoreVmVidSy_60; "onecore\\vm\\vid\\sys\\vsmm\\vsmmvagpac"...
0x1400e62c3  lea     rcx, aVsmmvagpacorep_0; "VsmmVaGpaCorepSplitVaRangeByVads"
0x1400e62ca  call    VidTraceErrorInternal0
0x1400e62cf  jmp     short loc_1400E62D3
0x1400e62d1  xor     ebx, ebx
0x1400e62d3  mov     rcx, [rsp+88h+ProcessHandle]; Handle
0x1400e62db  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1400e62df  jz      short loc_1400E62ED
0x1400e62e1  call    cs:__imp_ZwClose
0x1400e62e8  nop     dword ptr [rax+rax+00h]
0x1400e62ed  lea     r11, [rsp+88h+var_18]
0x1400e62f2  mov     eax, ebx
0x1400e62f4  mov     rbx, [r11+20h]
0x1400e62f8  mov     rbp, [r11+30h]
0x1400e62fc  mov     rsp, r11
0x1400e62ff  pop     r14
0x1400e6301  pop     rdi
0x1400e6302  pop     rsi
0x1400e6303  retn
```
