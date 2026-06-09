# VMX_LOG_BLOCK_HEADER::Unformat(uchar * *,ulong)

- ea: `0x14001a0a0`
- end: `0x14001a187`
- name: `?Unformat@VMX_LOG_BLOCK_HEADER@@QEAAJPEAPEAEK@Z`
- size: `231`
- prototype: `__int64 __fastcall(VMX_LOG_BLOCK_HEADER *this, unsigned __int8 **)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140019fec`
- `0x140049090`
- `0x14004931c`

## callees

- `0x1400099d8`
- `0x14001a0a0`
- `0x14001ae08`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x14001a0c8`
- `ntoskrnl!RtlCompareMemory` at `0x14001a0c8`

## pseudocode

```c
__int64 __fastcall VMX_LOG_BLOCK_HEADER::Unformat(VMX_LOG_BLOCK_HEADER *this, unsigned __int8 **a2)
{
  const void *v2; // rdi
  VMX_NOTIFICATION_QUEUE *v5; // rcx
  __int64 v6; // rdx
  unsigned __int8 *v7; // rax

  v2 = *a2;
  if ( RtlCompareMemory(*a2, "KLOG", 4u) != 4 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x800) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      return 3224895490LL;
    }
    v6 = 40;
LABEL_11:
    WPP_SF_d(*((_QWORD *)v5 + 3), v6, WPP_4b219bab5c283f1089a222952cd3541f_Traceguids, 3224895490LL);
    return 3224895490LL;
  }
  v7 = VmxpUnformatTable((const struct VMX_FIELD *)"\t", 4u, (char *)this, *a2 + 4, (int)v2 - (*(_DWORD *)a2 + 4) + 24);
  if ( !v7 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x800) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      return 3224895490LL;
    }
    v6 = 41;
    goto LABEL_11;
  }
  *a2 = v7;
  return 0;
}

```

## disassembly

```asm
0x14001a0a0  mov     [rsp+arg_0], rbx
0x14001a0a5  mov     [rsp+arg_8], rsi
0x14001a0aa  push    rdi
0x14001a0ab  sub     rsp, 30h
0x14001a0af  mov     rdi, [rdx]
0x14001a0b2  mov     rbx, rdx
0x14001a0b5  mov     rsi, rcx
0x14001a0b8  lea     rdx, aKlog; "KLOG"
0x14001a0bf  mov     rcx, rdi; Source1
0x14001a0c2  mov     r8d, 4; Length
0x14001a0c8  call    cs:__imp_RtlCompareMemory
0x14001a0cf  nop     dword ptr [rax+rax+00h]
0x14001a0d4  cmp     rax, 4
0x14001a0d8  jz      short loc_14001A103
0x14001a0da  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a0e1  lea     rax, WPP_GLOBAL_Control
0x14001a0e8  cmp     rcx, rax
0x14001a0eb  jz      short loc_14001A16A
0x14001a0ed  test    dword ptr [rcx+2Ch], 800h
0x14001a0f4  jz      short loc_14001A16A
0x14001a0f6  cmp     byte ptr [rcx+29h], 2
0x14001a0fa  jb      short loc_14001A16A
0x14001a0fc  mov     edx, 28h ; '('
0x14001a101  jmp     short loc_14001A154
0x14001a103  mov     r9, [rbx]
0x14001a106  lea     rcx, asc_14001FEC0; "\t"
0x14001a10d  add     r9, 4; unsigned __int8 *
0x14001a111  mov     r8, rsi; void *
0x14001a114  sub     edi, r9d
0x14001a117  mov     edx, 4; unsigned int
0x14001a11c  add     edi, 18h
0x14001a11f  mov     [rsp+38h+var_18], edi; unsigned int
0x14001a123  call    ?VmxpUnformatTable@@YAPEAEPEBVVMX_FIELD@@KPEAXPEAEK@Z; VmxpUnformatTable(VMX_FIELD const *,ulong,void *,uchar *,ulong)
0x14001a128  test    rax, rax
0x14001a12b  jnz     short loc_14001A171
0x14001a12d  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a134  lea     rax, WPP_GLOBAL_Control
0x14001a13b  cmp     rcx, rax
0x14001a13e  jz      short loc_14001A16A
0x14001a140  test    dword ptr [rcx+2Ch], 800h
0x14001a147  jz      short loc_14001A16A
0x14001a149  cmp     byte ptr [rcx+29h], 2
0x14001a14d  jb      short loc_14001A16A
0x14001a14f  mov     edx, 29h ; ')'
0x14001a154  mov     rcx, [rcx+18h]
0x14001a158  lea     r8, WPP_4b219bab5c283f1089a222952cd3541f_Traceguids
0x14001a15f  mov     r9d, 0C0380002h
0x14001a165  call    WPP_SF_d
0x14001a16a  mov     eax, 0C0380002h
0x14001a16f  jmp     short loc_14001A176
0x14001a171  mov     [rbx], rax
0x14001a174  xor     eax, eax
0x14001a176  mov     rbx, [rsp+38h+arg_0]
0x14001a17b  mov     rsi, [rsp+38h+arg_8]
0x14001a180  add     rsp, 30h
0x14001a184  pop     rdi
0x14001a185  retn
```
