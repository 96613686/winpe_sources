# WanNmrAttachClient

- ea: `0x1400042f0`
- end: `0x14000445c`
- name: `WanNmrAttachClient`
- size: `364`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1400024d0`
- `0x140002b6c`
- `0x1400042f0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000443e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000443e`
- `ntoskrnl!ExAllocatePool2` at `0x140004366`
- `ntoskrnl!ExAllocatePool2` at `0x140004366`
- `NDIS!NdisRegisterProtocolDriver` at `0x140004402`
- `NDIS!NdisRegisterProtocolDriver` at `0x140004402`

## pseudocode

```c
__int64 __fastcall WanNmrAttachClient(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        _QWORD *a6,
        _QWORD *a7)
{
  __int64 v7; // rsi
  char v8; // dl
  char v9; // bp
  void *v12; // rdi
  unsigned int v13; // ebx
  _QWORD *Pool2; // rax
  __int64 *v15; // rax

  v7 = a2 - 8;
  v8 = byte_140009AEC;
  v9 = 0;
  if ( (__int64 *)v7 != &WanNmrV4ProviderState )
    v8 = byte_140009C0C;
  if ( !v8 )
  {
    WanpAcquireResource(&g_wrBindMutex);
    v9 = 1;
  }
  if ( *(_WORD *)(a5 + 4) == *(_WORD *)(v7 + 92) )
  {
    Pool2 = (_QWORD *)ExAllocatePool2(64, 48, 1131441222);
    v12 = Pool2;
    if ( Pool2 )
    {
      if ( _InterlockedCompareExchange64((volatile signed __int64 *)(v7 + 216), (signed __int64)Pool2, 0) )
      {
        v13 = -1073741823;
      }
      else
      {
        Pool2[1] = a5;
        *Pool2 = a4;
        Pool2[3] = a1;
        Pool2[5] = v7;
        *a6 = *(_QWORD *)(v7 + 216);
        *a7 = v7 + 104;
        v15 = &qword_140009A70;
        if ( (__int64 *)v7 != &WanNmrV4ProviderState )
          v15 = &qword_140009B90;
        *(_BYTE *)v15 = 1;
        *(_DWORD *)(*(_QWORD *)(v7 + 216) + 32LL) = 2;
        v13 = NdisRegisterProtocolDriver(
                (NDIS_HANDLE)v7,
                (PNDIS_PROTOCOL_DRIVER_CHARACTERISTICS)(v7 + 224),
                (PNDIS_HANDLE)(v7 + 352));
        if ( v13 )
          *(_QWORD *)(v7 + 216) = 0;
      }
    }
    else
    {
      v13 = -1073741670;
    }
  }
  else
  {
    v12 = 0;
    v13 = -1073741127;
  }
  if ( v9 )
    WanpReleaseResource(&g_wrBindMutex);
  if ( v13 && v12 )
    ExFreePoolWithTag(v12, 0);
  return v13;
}

```

## disassembly

```asm
0x1400042f0  push    rbx
0x1400042f2  push    rbp
0x1400042f3  push    rsi
0x1400042f4  push    rdi
0x1400042f5  push    r12
0x1400042f7  push    r14
0x1400042f9  push    r15
0x1400042fb  sub     rsp, 20h
0x1400042ff  movzx   eax, cs:byte_140009C0C
0x140004306  lea     rsi, [rdx-8]
0x14000430a  movzx   edx, cs:byte_140009AEC
0x140004311  lea     r12, WanNmrV4ProviderState
0x140004318  xor     bpl, bpl
0x14000431b  mov     r14, r9
0x14000431e  cmp     rsi, r12
0x140004321  mov     r15, rcx
0x140004324  cmovnz  edx, eax
0x140004327  test    dl, dl
0x140004329  jnz     short loc_14000433A
0x14000432b  lea     rcx, g_wrBindMutex
0x140004332  call    WanpAcquireResource
0x140004337  mov     bpl, 1
0x14000433a  mov     rbx, [rsp+58h+arg_20]
0x140004342  movzx   eax, word ptr [rsi+5Ch]
0x140004346  cmp     [rbx+4], ax
0x14000434a  jz      short loc_140004358
0x14000434c  xor     edi, edi
0x14000434e  mov     ebx, 0C00002B9h
0x140004353  jmp     loc_14000441F
0x140004358  mov     edx, 30h ; '0'
0x14000435d  mov     r8d, 43706C46h
0x140004363  lea     ecx, [rdx+10h]
0x140004366  call    cs:__imp_ExAllocatePool2
0x14000436d  nop     dword ptr [rax+rax+00h]
0x140004372  mov     rdi, rax
0x140004375  test    rax, rax
0x140004378  jnz     short loc_140004384
0x14000437a  mov     ebx, 0C000009Ah
0x14000437f  jmp     loc_14000441F
0x140004384  xor     eax, eax
0x140004386  lock cmpxchg [rsi+0D8h], rdi
0x14000438f  jz      short loc_14000439B
0x140004391  mov     ebx, 0C0000001h
0x140004396  jmp     loc_14000441F
0x14000439b  mov     rax, [rsp+58h+arg_28]
0x1400043a3  cmp     rsi, r12
0x1400043a6  mov     [rdi+8], rbx
0x1400043aa  mov     [rdi], r14
0x1400043ad  mov     [rdi+18h], r15
0x1400043b1  mov     [rdi+28h], rsi
0x1400043b5  mov     rcx, [rsi+0D8h]
0x1400043bc  mov     [rax], rcx
0x1400043bf  lea     rcx, [rsi+68h]
0x1400043c3  mov     rax, [rsp+58h+arg_30]
0x1400043cb  mov     [rax], rcx
0x1400043ce  lea     rcx, qword_140009B90
0x1400043d5  lea     rax, qword_140009A70
0x1400043dc  cmovnz  rax, rcx
0x1400043e0  mov     byte ptr [rax], 1
0x1400043e3  mov     rax, [rsi+0D8h]
0x1400043ea  mov     dword ptr [rax+20h], 2
0x1400043f1  lea     r8, [rsi+160h]; NdisProtocolHandle
0x1400043f8  mov     rcx, rsi; ProtocolDriverContext
0x1400043fb  lea     rdx, [rsi+0E0h]; ProtocolCharacteristics
0x140004402  call    cs:__imp_NdisRegisterProtocolDriver
0x140004409  nop     dword ptr [rax+rax+00h]
0x14000440e  mov     ebx, eax
0x140004410  test    eax, eax
0x140004412  jz      short loc_14000441F
0x140004414  mov     qword ptr [rsi+0D8h], 0
0x14000441f  test    bpl, bpl
0x140004422  jz      short loc_140004430
0x140004424  lea     rcx, g_wrBindMutex
0x14000442b  call    WanpReleaseResource
0x140004430  test    ebx, ebx
0x140004432  jz      short loc_14000444A
0x140004434  test    rdi, rdi
0x140004437  jz      short loc_14000444A
0x140004439  xor     edx, edx; Tag
0x14000443b  mov     rcx, rdi; P
0x14000443e  call    cs:__imp_ExFreePoolWithTag
0x140004445  nop     dword ptr [rax+rax+00h]
0x14000444a  mov     eax, ebx
0x14000444c  add     rsp, 20h
0x140004450  pop     r15
0x140004452  pop     r14
0x140004454  pop     r12
0x140004456  pop     rdi
0x140004457  pop     rsi
0x140004458  pop     rbp
0x140004459  pop     rbx
0x14000445a  retn
```
