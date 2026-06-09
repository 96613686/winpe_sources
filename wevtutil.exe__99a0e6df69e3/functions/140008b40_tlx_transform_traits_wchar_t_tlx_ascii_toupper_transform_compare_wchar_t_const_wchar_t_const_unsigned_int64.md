# tlx::transform_traits<wchar_t,tlx::ascii_toupper_transform>::compare(wchar_t const *,wchar_t const *,unsigned __int64)

- ea: `0x140008b40`
- end: `0x140008bb3`
- name: `?compare@?$transform_traits@_WUascii_toupper_transform@tlx@@@tlx@@SAHPEB_W0_K@Z`
- size: `115`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `17`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140006de0`
- `0x14000a670`
- `0x14000b6d0`
- `0x140017fbc`
- `0x140019348`
- `0x14001aec0`
- `0x14001b324`
- `0x14001b4e4`
- `0x14001b518`
- `0x14001b580`
- `0x14001b5b4`
- `0x14001b75c`
- `0x140024a90`
- `0x140026058`
- `0x1400286bc`
- `0x14002b108`
- `0x14002b2a8`

## callees

- `0x140008b40`

## pseudocode

```c
__int64 __fastcall tlx::transform_traits<wchar_t,tlx::ascii_toupper_transform>::compare(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 i; // rax
  int v5; // edx
  unsigned int v6; // r9d
  int v7; // edx
  unsigned int v8; // r10d
  __int64 result; // rax

  if ( a1 != a2 )
  {
    for ( i = 0; i != a3; ++i )
    {
      v5 = *(unsigned __int16 *)(a1 + 2 * i);
      v6 = v5 - 32;
      if ( (unsigned int)(v5 - 97) >= 0x1A )
        v6 = *(unsigned __int16 *)(a1 + 2 * i);
      v7 = *(unsigned __int16 *)(a2 + 2 * i);
      v8 = v7 - 32;
      if ( (unsigned int)(v7 - 97) >= 0x1A )
        v8 = *(unsigned __int16 *)(a2 + 2 * i);
      if ( v6 != v8 )
      {
        result = 1;
        if ( v6 < v8 )
          return 0xFFFFFFFFLL;
        return result;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140008b40  mov     [rsp+arg_0], rbx
0x140008b45  mov     [rsp+arg_8], rdi
0x140008b4a  xor     r11d, r11d
0x140008b4d  mov     rbx, rdx
0x140008b50  mov     rdi, rcx
0x140008b53  cmp     rcx, rdx
0x140008b56  jz      short loc_140008BA5
0x140008b58  xor     eax, eax
0x140008b5a  cmp     rax, r8
0x140008b5d  jz      short loc_140008BA5
0x140008b5f  movzx   edx, word ptr [rdi+rax*2]
0x140008b63  lea     ecx, [rdx-61h]
0x140008b66  cmp     ecx, 1Ah
0x140008b69  lea     r9d, [rdx-20h]
0x140008b6d  cmovnb  r9d, edx
0x140008b71  movzx   edx, word ptr [rbx+rax*2]
0x140008b75  lea     ecx, [rdx-61h]
0x140008b78  cmp     ecx, 1Ah
0x140008b7b  lea     r10d, [rdx-20h]
0x140008b7f  cmovnb  r10d, edx
0x140008b83  cmp     r9d, r10d
0x140008b86  jnz     short loc_140008B8D
0x140008b88  inc     rax
0x140008b8b  jmp     short loc_140008B5A
0x140008b8d  mov     eax, 1
0x140008b92  mov     ecx, 0FFFFFFFFh
0x140008b97  cmovb   eax, ecx
0x140008b9a  mov     rbx, [rsp+arg_0]
0x140008b9f  mov     rdi, [rsp+arg_8]
0x140008ba4  retn
0x140008ba5  mov     rbx, [rsp+arg_0]
0x140008baa  mov     eax, r11d
0x140008bad  mov     rdi, [rsp+arg_8]
0x140008bb2  retn
```
