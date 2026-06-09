# CDhcpOptions::AddOptionRelayAgentToBufferEnd(uchar,void const *)

- ea: `0x18002b260`
- end: `0x18002b2f3`
- name: `?AddOptionRelayAgentToBufferEnd@CDhcpOptions@@QEAAKEPEBX@Z`
- size: `147`
- prototype: `__int64 __fastcall(CDhcpOptions *this, unsigned __int8, const void *)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x18002e860`

## callees

- `0x18002b260`

## import_xrefs

- `msvcrt!memmove_s` at `0x18002b2c2`
- `msvcrt!memmove_s` at `0x18002b2c2`

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
0x18002b260  mov     [rsp+arg_0], rbx
0x18002b265  mov     [rsp+arg_8], rsi
0x18002b26a  push    rdi
0x18002b26b  sub     rsp, 20h
0x18002b26f  xor     ebx, ebx
0x18002b271  movzx   esi, dl
0x18002b274  mov     r10, r8
0x18002b277  mov     rdi, rcx
0x18002b27a  cmp     [rcx+120h], ebx
0x18002b280  jnz     short loc_18002B289
0x18002b282  mov     ebx, 1
0x18002b287  jmp     short loc_18002B2E0
0x18002b289  mov     r8d, [rcx+118h]
0x18002b290  lea     rax, [rsi+1]
0x18002b294  mov     ecx, r8d
0x18002b297  mov     rdx, rsi; DestinationSize
0x18002b29a  sub     ecx, [rdi+11Ch]
0x18002b2a0  cmp     rcx, rax
0x18002b2a3  jnb     short loc_18002B2AC
0x18002b2a5  mov     ebx, 7Ah ; 'z'
0x18002b2aa  jmp     short loc_18002B2E0
0x18002b2ac  mov     rcx, [rdi+110h]
0x18002b2b3  sub     r8, rdx
0x18002b2b6  dec     rcx
0x18002b2b9  mov     r9, rdx; SourceSize
0x18002b2bc  add     rcx, r8; Destination
0x18002b2bf  mov     r8, r10; Source
0x18002b2c2  call    cs:__imp_memmove_s
0x18002b2c9  nop     dword ptr [rax+rax+00h]
0x18002b2ce  mov     edx, [rdi+118h]
0x18002b2d4  mov     rcx, [rdi+110h]
0x18002b2db  mov     [rdx+rcx-1], sil
0x18002b2e0  mov     rsi, [rsp+28h+arg_8]
0x18002b2e5  mov     eax, ebx
0x18002b2e7  mov     rbx, [rsp+28h+arg_0]
0x18002b2ec  add     rsp, 20h
0x18002b2f0  pop     rdi
0x18002b2f1  retn
```
