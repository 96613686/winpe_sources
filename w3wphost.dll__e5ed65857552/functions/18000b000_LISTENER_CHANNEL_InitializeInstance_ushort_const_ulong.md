# LISTENER_CHANNEL::InitializeInstance(ushort const *,ulong)

- ea: `0x18000b000`
- end: `0x18000b085`
- name: `?InitializeInstance@LISTENER_CHANNEL@@QEAAJPEBGK@Z`
- size: `133`
- prototype: `__int64 __fastcall(LISTENER_CHANNEL *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000b708`

## callees

- `0x180002090`
- `0x18000aaf0`
- `0x18000b000`

## import_xrefs

- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000b013`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000b013`

## pseudocode

```c
__int64 __fastcall LISTENER_CHANNEL::InitializeInstance(LISTENER_CHANNEL *this, const unsigned __int16 *a2, int a3)
{
  int v5; // esi
  LISTENER_CHANNEL_WORKITEM *v6; // rax
  LISTENER_CHANNEL_WORKITEM *v7; // rbx

  v5 = STRU::Copy((LISTENER_CHANNEL *)((char *)this + 16), a2);
  if ( v5 >= 0 )
  {
    v6 = (LISTENER_CHANNEL_WORKITEM *)operator new(0x38u);
    v7 = v6;
    if ( v6 )
    {
      LISTENER_CHANNEL_WORKITEM::LISTENER_CHANNEL_WORKITEM(v6, 0, 0);
      *((_DWORD *)v7 + 12) = 0;
      *(_QWORD *)v7 = &LISTENER_CHANNEL_STOP_WORKITEM::`vftable';
    }
    else
    {
      v7 = 0;
    }
    *((_QWORD *)this + 39) = v7;
    if ( v7 )
    {
      *((_DWORD *)this + 18) = a3;
      *((_DWORD *)this + 66) = 1;
    }
    else
    {
      return (unsigned int)-2147024888;
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000b000  push    rbx
0x18000b002  push    rbp
0x18000b003  push    rsi
0x18000b004  push    rdi
0x18000b005  sub     rsp, 28h
0x18000b009  mov     rdi, rcx
0x18000b00c  mov     ebp, r8d
0x18000b00f  add     rcx, 10h
0x18000b013  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000b01a  nop     dword ptr [rax+rax+00h]
0x18000b01f  mov     esi, eax
0x18000b021  test    eax, eax
0x18000b023  js      short loc_18000B079
0x18000b025  mov     ecx, 38h ; '8'; Size
0x18000b02a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000b02f  mov     rbx, rax
0x18000b032  test    rax, rax
0x18000b035  jz      short loc_18000B057
0x18000b037  xor     r8d, r8d; int
0x18000b03a  xor     edx, edx; struct LISTENER_CHANNEL *
0x18000b03c  mov     rcx, rax; this
0x18000b03f  call    ??0LISTENER_CHANNEL_WORKITEM@@QEAA@PEAVLISTENER_CHANNEL@@H@Z; LISTENER_CHANNEL_WORKITEM::LISTENER_CHANNEL_WORKITEM(LISTENER_CHANNEL *,int)
0x18000b044  lea     rax, ??_7LISTENER_CHANNEL_STOP_WORKITEM@@6B@; const LISTENER_CHANNEL_STOP_WORKITEM::`vftable'
0x18000b04b  mov     dword ptr [rbx+30h], 0
0x18000b052  mov     [rbx], rax
0x18000b055  jmp     short loc_18000B059
0x18000b057  xor     ebx, ebx
0x18000b059  mov     [rdi+138h], rbx
0x18000b060  test    rbx, rbx
0x18000b063  jnz     short loc_18000B06C
0x18000b065  mov     esi, 80070008h
0x18000b06a  jmp     short loc_18000B079
0x18000b06c  mov     [rdi+48h], ebp
0x18000b06f  mov     dword ptr [rdi+108h], 1
0x18000b079  mov     eax, esi
0x18000b07b  add     rsp, 28h
0x18000b07f  pop     rdi
0x18000b080  pop     rsi
0x18000b081  pop     rbp
0x18000b082  pop     rbx
0x18000b083  retn
```
