# CWMFileSinkV1::CommandShouldExecuteNow(unsigned __int64,PACKET_PARSE_INFO_EX *,CPayloadMapEntryEx *)

- ea: `0x180008a20`
- end: `0x180008a97`
- name: `?CommandShouldExecuteNow@CWMFileSinkV1@@MEAAH_KPEAUPACKET_PARSE_INFO_EX@@PEAVCPayloadMapEntryEx@@@Z`
- size: `119`
- prototype: `__int64 __fastcall(CWMFileSinkV1 *__hidden this, unsigned __int64, struct PACKET_PARSE_INFO_EX *, struct CPayloadMapEntryEx *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180008a20`

## pseudocode

```c
_BOOL8 __fastcall CWMFileSinkV1::CommandShouldExecuteNow(
        CWMFileSinkV1 *this,
        unsigned __int64 a2,
        struct PACKET_PARSE_INFO_EX *a3,
        struct CPayloadMapEntryEx *a4)
{
  unsigned int i; // r10d
  unsigned __int8 v5; // al

  if ( *((_WORD *)this + 4500) )
  {
    for ( i = 0; i < *((_DWORD *)a3 + 22); ++i )
    {
      v5 = *((_BYTE *)a4 + 48 * i + 8) & 0x7F;
      if ( v5 < 0x40u
        && *((_DWORD *)this + 12 * v5 + 97)
        && a2 + *((_QWORD *)this + 31) <= *((unsigned int *)a4 + 12 * i + 5) )
      {
        return 1;
      }
    }
  }
  return a2 <= *((unsigned int *)a3 + 15);
}

```

## disassembly

```asm
0x180008a20  push    rbx
0x180008a22  push    rsi
0x180008a23  push    rdi
0x180008a24  xor     esi, esi
0x180008a26  mov     rbx, rdx
0x180008a29  mov     r11, rcx
0x180008a2c  cmp     [rcx+2328h], si
0x180008a33  jbe     short loc_180008A87
0x180008a35  mov     rdi, [rcx+0F8h]
0x180008a3c  mov     r10d, esi
0x180008a3f  add     rdi, rdx
0x180008a42  cmp     r10d, [r8+58h]
0x180008a46  jnb     short loc_180008A87
0x180008a48  mov     eax, r10d
0x180008a4b  lea     rdx, [rax+rax*2]
0x180008a4f  add     rdx, rdx
0x180008a52  mov     al, [r9+rdx*8+8]
0x180008a57  and     al, 7Fh
0x180008a59  cmp     al, 40h ; '@'
0x180008a5b  jnb     short loc_180008A7B
0x180008a5d  movzx   eax, al
0x180008a60  lea     rcx, [rax+rax*2]
0x180008a64  add     rcx, rcx
0x180008a67  cmp     [r11+rcx*8+184h], esi
0x180008a6f  jz      short loc_180008A7B
0x180008a71  mov     eax, [r9+rdx*8+14h]
0x180008a76  cmp     rdi, rax
0x180008a79  jbe     short loc_180008A80
0x180008a7b  inc     r10d
0x180008a7e  jmp     short loc_180008A42
0x180008a80  mov     eax, 1
0x180008a85  jmp     short loc_180008A93
0x180008a87  mov     ecx, [r8+3Ch]
0x180008a8b  mov     eax, esi
0x180008a8d  cmp     rbx, rcx
0x180008a90  setbe   al
0x180008a93  pop     rdi
0x180008a94  pop     rsi
0x180008a95  pop     rbx
0x180008a96  retn
```
