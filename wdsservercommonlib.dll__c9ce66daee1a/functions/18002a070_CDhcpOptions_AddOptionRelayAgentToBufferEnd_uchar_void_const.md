# CDhcpOptions::AddOptionRelayAgentToBufferEnd(uchar,void const *)

- ea: `0x18002a070`
- end: `0x18002a103`
- name: `?AddOptionRelayAgentToBufferEnd@CDhcpOptions@@QEAAKEPEBX@Z`
- size: `147`
- prototype: `unsigned int(CDhcpOptions *__hidden this, unsigned __int8, const void *)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x18002d640`

## callees

- `0x18002a070`

## import_xrefs

- `msvcrt!memmove_s` at `0x18002a0d2`
- `msvcrt!memmove_s` at `0x18002a0d2`

## pseudocode

```c
__int64 __fastcall CDhcpOptions::AddOptionRelayAgentToBufferEnd(CDhcpOptions *this, unsigned __int8 a2, const void *a3)
{
  unsigned int v3; // ebx

  v3 = 0;
  if ( *((_DWORD *)this + 72) )
  {
    if ( (unsigned int)(*((_DWORD *)this + 70) - *((_DWORD *)this + 71)) >= (unsigned __int64)a2 + 1 )
    {
      memmove_s(
        (void *const)(*((unsigned int *)this + 70) - (unsigned __int64)a2 + *((_QWORD *)this + 34) - 1LL),
        a2,
        a3,
        a2);
      *(_BYTE *)(*((unsigned int *)this + 70) + *((_QWORD *)this + 34) - 1LL) = a2;
    }
    else
    {
      return 122;
    }
  }
  else
  {
    return 1;
  }
  return v3;
}

```

## disassembly

```asm
0x18002a070  mov     [rsp+arg_0], rbx
0x18002a075  mov     [rsp+arg_8], rsi
0x18002a07a  push    rdi
0x18002a07b  sub     rsp, 20h
0x18002a07f  xor     ebx, ebx
0x18002a081  movzx   esi, dl
0x18002a084  mov     r10, r8
0x18002a087  mov     rdi, rcx
0x18002a08a  cmp     [rcx+120h], ebx
0x18002a090  jnz     short loc_18002A099
0x18002a092  mov     ebx, 1
0x18002a097  jmp     short loc_18002A0F0
0x18002a099  mov     r8d, [rcx+118h]
0x18002a0a0  lea     rax, [rsi+1]
0x18002a0a4  mov     ecx, r8d
0x18002a0a7  mov     rdx, rsi; DestinationSize
0x18002a0aa  sub     ecx, [rdi+11Ch]
0x18002a0b0  cmp     rcx, rax
0x18002a0b3  jnb     short loc_18002A0BC
0x18002a0b5  mov     ebx, 7Ah ; 'z'
0x18002a0ba  jmp     short loc_18002A0F0
0x18002a0bc  mov     rcx, [rdi+110h]
0x18002a0c3  sub     r8, rdx
0x18002a0c6  dec     rcx
0x18002a0c9  mov     r9, rdx; SourceSize
0x18002a0cc  add     rcx, r8; Destination
0x18002a0cf  mov     r8, r10; Source
0x18002a0d2  call    cs:__imp_memmove_s
0x18002a0d9  nop     dword ptr [rax+rax+00h]
0x18002a0de  mov     edx, [rdi+118h]
0x18002a0e4  mov     rcx, [rdi+110h]
0x18002a0eb  mov     [rdx+rcx-1], sil
0x18002a0f0  mov     rsi, [rsp+28h+arg_8]
0x18002a0f5  mov     eax, ebx
0x18002a0f7  mov     rbx, [rsp+28h+arg_0]
0x18002a0fc  add     rsp, 20h
0x18002a100  pop     rdi
0x18002a101  retn
```
