# MvmDeleteGpadl

- ea: `0x14000d620`
- end: `0x14000d6fc`
- name: `MvmDeleteGpadl`
- size: `220`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x14000a9e0`

## callees

- `0x14000d620`
- `0x14000dd98`
- `0x14000e0a0`
- `0x14000e0f0`
- `0x14000e8ec`
- `0x14000e910`
- `0x14000e9f4`
- `0x140017540`

## pseudocode

```c
__int64 __fastcall MvmDeleteGpadl(__int64 a1, unsigned int a2)
{
  __int64 v4; // rbx
  __int64 v5; // rcx
  __int64 result; // rax
  unsigned int v7[64]; // [rsp+20h] [rbp-108h] BYREF

  memset(v7, 0, 0xF4u);
  v4 = MvmpEstablishGhcbPage(*(_QWORD *)(a1 + 40));
  MvmpEstablishMessagePage(*(_QWORD *)(a1 + 40), v4, 0);
  memset(v7, 0, 0xF4u);
  v7[3] = *(_DWORD *)(a1 + 48);
  v5 = *(_QWORD *)(a1 + 40);
  v7[1] = 11;
  v7[0] = 16;
  v7[4] = a2;
  MvmpSendMessageSynchronous(v5, v4, v7);
  MvmpReceiveMessageIgnoreUnsupported(*(_QWORD *)(a1 + 40), v4, v7);
  MvmpReleaseMessagePage(*(_QWORD *)(a1 + 40), v4);
  result = MvmpReleaseGhcbPage(*(_QWORD *)(a1 + 40), v4);
  if ( v7[1] != 12 || v7[0] != 12 || v7[3] != a2 )
    __fastfail(0x3Au);
  return result;
}

```

## disassembly

```asm
0x14000d620  mov     [rsp+arg_0], rbx
0x14000d625  mov     [rsp+arg_8], rsi
0x14000d62a  push    rdi
0x14000d62b  sub     rsp, 120h
0x14000d632  mov     esi, edx
0x14000d634  mov     rdi, rcx
0x14000d637  xor     edx, edx; Val
0x14000d639  lea     rcx, [rsp+128h+var_108]; void *
0x14000d63e  mov     r8d, 0F4h; Size
0x14000d644  call    memset
0x14000d649  mov     rcx, [rdi+28h]
0x14000d64d  call    MvmpEstablishGhcbPage
0x14000d652  mov     rcx, [rdi+28h]
0x14000d656  xor     r8d, r8d
0x14000d659  mov     rdx, rax
0x14000d65c  mov     rbx, rax
0x14000d65f  call    MvmpEstablishMessagePage
0x14000d664  xor     edx, edx; Val
0x14000d666  lea     rcx, [rsp+128h+var_108]; void *
0x14000d66b  mov     r8d, 0F4h; Size
0x14000d671  call    memset
0x14000d676  mov     ecx, [rdi+30h]
0x14000d679  lea     r8, [rsp+128h+var_108]
0x14000d67e  mov     [rsp+128h+var_FC], ecx
0x14000d682  mov     rdx, rbx
0x14000d685  mov     rcx, [rdi+28h]
0x14000d689  mov     [rsp+128h+var_104], 0Bh
0x14000d691  mov     [rsp+128h+var_108], 10h
0x14000d699  mov     [rsp+128h+var_F8], esi
0x14000d69d  call    MvmpSendMessageSynchronous
0x14000d6a2  mov     rcx, [rdi+28h]
0x14000d6a6  lea     r8, [rsp+128h+var_108]
0x14000d6ab  mov     rdx, rbx
0x14000d6ae  call    MvmpReceiveMessageIgnoreUnsupported
0x14000d6b3  mov     rcx, [rdi+28h]
0x14000d6b7  mov     rdx, rbx
0x14000d6ba  call    MvmpReleaseMessagePage
0x14000d6bf  mov     rcx, [rdi+28h]
0x14000d6c3  mov     rdx, rbx
0x14000d6c6  call    MvmpReleaseGhcbPage
0x14000d6cb  cmp     [rsp+128h+var_104], 0Ch
0x14000d6d0  jnz     short loc_14000D6DF
0x14000d6d2  cmp     [rsp+128h+var_108], 0Ch
0x14000d6d7  jnz     short loc_14000D6DF
0x14000d6d9  cmp     [rsp+128h+var_FC], esi
0x14000d6dd  jz      short loc_14000D6E6
0x14000d6df  mov     ecx, 3Ah ; ':'
0x14000d6e4  int     29h; Win8: RtlFailFast(ecx)
0x14000d6e6  lea     r11, [rsp+128h+var_8]
0x14000d6ee  mov     rbx, [r11+10h]
0x14000d6f2  mov     rsi, [r11+18h]
0x14000d6f6  mov     rsp, r11
0x14000d6f9  pop     rdi
0x14000d6fa  retn
```
