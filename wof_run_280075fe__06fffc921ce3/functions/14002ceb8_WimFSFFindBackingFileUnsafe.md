# WimFSFFindBackingFileUnsafe

- ea: `0x14002ceb8`
- end: `0x14002cf25`
- name: `WimFSFFindBackingFileUnsafe`
- size: `109`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14002c53c`

## callees

- `0x14002ceb8`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x14002cee3`
- `ntoskrnl!RtlCompareMemory` at `0x14002cee3`

## pseudocode

```c
__int64 __fastcall WimFSFFindBackingFileUnsafe(__int64 a1, const void *a2, __int64 a3, volatile signed __int32 **a4)
{
  __int64 *v4; // rsi
  volatile signed __int32 *i; // rbx
  __int64 result; // rax

  v4 = (__int64 *)(a1 + 24);
  for ( i = *(volatile signed __int32 **)(a1 + 24); i != (volatile signed __int32 *)v4; i = *(volatile signed __int32 **)i )
  {
    if ( RtlCompareMemory((const void *)(i + 246), a2, 0x14u) == 20 )
    {
      result = 0;
      if ( a4 )
      {
        *a4 = i;
        _InterlockedIncrement(i + 14);
      }
      return result;
    }
  }
  result = 3221226021LL;
  if ( a4 )
    *a4 = 0;
  return result;
}

```

## disassembly

```asm
0x14002ceb8  push    rbx
0x14002ceba  push    rbp
0x14002cebb  push    rsi
0x14002cebc  push    rdi
0x14002cebd  sub     rsp, 28h
0x14002cec1  lea     rsi, [rcx+18h]
0x14002cec5  mov     rdi, r9
0x14002cec8  mov     rbx, [rsi]
0x14002cecb  mov     rbp, rdx
0x14002cece  cmp     rbx, rsi
0x14002ced1  jz      short loc_14002CF0A
0x14002ced3  lea     rcx, [rbx+3D8h]; Source1
0x14002ceda  mov     r8d, 14h; Length
0x14002cee0  mov     rdx, rbp; Source2
0x14002cee3  call    cs:__imp_RtlCompareMemory
0x14002ceea  nop     dword ptr [rax+rax+00h]
0x14002ceef  cmp     rax, 14h
0x14002cef3  jz      short loc_14002CEFA
0x14002cef5  mov     rbx, [rbx]
0x14002cef8  jmp     short loc_14002CECE
0x14002cefa  xor     eax, eax
0x14002cefc  test    rdi, rdi
0x14002ceff  jz      short loc_14002CF1B
0x14002cf01  mov     [rdi], rbx
0x14002cf04  lock inc dword ptr [rbx+38h]
0x14002cf08  jmp     short loc_14002CF1B
0x14002cf0a  mov     eax, 0C0000225h
0x14002cf0f  test    rdi, rdi
0x14002cf12  jz      short loc_14002CF1B
0x14002cf14  mov     qword ptr [rdi], 0
0x14002cf1b  add     rsp, 28h
0x14002cf1f  pop     rdi
0x14002cf20  pop     rsi
0x14002cf21  pop     rbp
0x14002cf22  pop     rbx
0x14002cf23  retn
```
