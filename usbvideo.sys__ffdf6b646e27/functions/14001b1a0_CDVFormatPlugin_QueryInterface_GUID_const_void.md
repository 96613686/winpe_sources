# CDVFormatPlugin::QueryInterface(_GUID const &,void * *)

- ea: `0x14001b1a0`
- end: `0x14001b212`
- name: `?QueryInterface@CDVFormatPlugin@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `114`
- prototype: `__int64 __fastcall(CDVFormatPlugin *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x140014050`
- `0x14001b1a0`
- `0x140040a70`

## pseudocode

```c
__int64 __fastcall CDVFormatPlugin::QueryInterface(CDVFormatPlugin *this, const struct _GUID *a2, CDVFormatPlugin **a3)
{
  CDVFormatPlugin *v3; // r9
  __int64 v5; // rax

  v3 = this;
  if ( !a3 )
    return 3221225485LL;
  *a3 = 0;
  if ( *(_OWORD *)a2 == *(_OWORD *)&GUID_63f2a8c7_4a21_4812_9ea0_420f970f1eb7 )
  {
    *a3 = this;
    v5 = *(_QWORD *)this;
LABEL_7:
    (*(void (__fastcall **)(CDVFormatPlugin *, const struct _GUID *, CDVFormatPlugin **, CDVFormatPlugin *))(v5 + 8))(
      this,
      a2,
      a3,
      v3);
    return 0;
  }
  if ( (unsigned int)IsEqualGUIDAligned(a2, &GUID_00000000_0000_0000_c000_000000000046) )
  {
    *a3 = v3;
    this = v3;
    v5 = *(_QWORD *)v3;
    goto LABEL_7;
  }
  return 3221225473LL;
}

```

## disassembly

```asm
0x14001b1a0  sub     rsp, 28h
0x14001b1a4  mov     r10, rdx
0x14001b1a7  mov     r9, rcx
0x14001b1aa  test    r8, r8
0x14001b1ad  jnz     short loc_14001B1B6
0x14001b1af  mov     eax, 0C000000Dh
0x14001b1b4  jmp     short loc_14001B20C
0x14001b1b6  mov     qword ptr [r8], 0
0x14001b1bd  mov     rax, qword ptr cs:_GUID_63f2a8c7_4a21_4812_9ea0_420f970f1eb7.Data1
0x14001b1c4  cmp     [rdx], rax
0x14001b1c7  jnz     short loc_14001B1DE
0x14001b1c9  mov     rax, qword ptr cs:_GUID_63f2a8c7_4a21_4812_9ea0_420f970f1eb7.Data4
0x14001b1d0  cmp     [rdx+8], rax
0x14001b1d4  jnz     short loc_14001B1DE
0x14001b1d6  mov     [r8], r9
0x14001b1d9  mov     rax, [rcx]
0x14001b1dc  jmp     short loc_14001B1FA
0x14001b1de  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x14001b1e5  mov     rcx, r10
0x14001b1e8  call    IsEqualGUIDAligned
0x14001b1ed  test    eax, eax
0x14001b1ef  jz      short loc_14001B207
0x14001b1f1  mov     [r8], r9
0x14001b1f4  mov     rcx, r9
0x14001b1f7  mov     rax, [r9]
0x14001b1fa  mov     rax, [rax+8]
0x14001b1fe  call    _guard_dispatch_icall
0x14001b203  xor     eax, eax
0x14001b205  jmp     short loc_14001B20C
0x14001b207  mov     eax, 0C0000001h
0x14001b20c  add     rsp, 28h
0x14001b210  retn
```
