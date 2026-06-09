# HTTP2VirtualConnection::GetChannelPointerFromId(int)

- ea: `0x18000ac90`
- end: `0x18000acd5`
- name: `?GetChannelPointerFromId@HTTP2VirtualConnection@@IEAAPEAVHTTP2ChannelPointer@@H@Z`
- size: `69`
- prototype: `struct HTTP2ChannelPointer *__fastcall(HTTP2VirtualConnection *__hidden this, int)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x18000f1b0`
- `0x180012110`
- `0x180013920`
- `0x180014850`
- `0x1800158e0`

## callees

- `0x18000ac90`

## pseudocode

```c
struct HTTP2ChannelPointer *__fastcall HTTP2VirtualConnection::GetChannelPointerFromId(
        HTTP2VirtualConnection *this,
        int a2)
{
  struct HTTP2ChannelPointer *result; // rax
  char *v4; // rcx

  if ( a2 == *((_DWORD *)this + 38) )
    return (HTTP2VirtualConnection *)((char *)this + 120);
  if ( a2 == *((_DWORD *)this + 39) )
    return (HTTP2VirtualConnection *)((char *)this + 136);
  if ( a2 == *((_DWORD *)this + 58) )
    return (HTTP2VirtualConnection *)((char *)this + 200);
  v4 = (char *)this + 216;
  result = 0;
  if ( a2 == *((_DWORD *)this + 59) )
    return (struct HTTP2ChannelPointer *)v4;
  return result;
}

```

## disassembly

```asm
0x18000ac90  mov     r8, rcx
0x18000ac93  cmp     edx, [rcx+98h]
0x18000ac99  jnz     short loc_18000ACA0
0x18000ac9b  lea     rax, [rcx+78h]
0x18000ac9f  retn
0x18000aca0  cmp     edx, [rcx+9Ch]
0x18000aca6  jnz     short loc_18000ACB0
0x18000aca8  lea     rax, [rcx+88h]
0x18000acaf  retn
0x18000acb0  cmp     edx, [rcx+0E8h]
0x18000acb6  jnz     short loc_18000ACC0
0x18000acb8  lea     rax, [rcx+0C8h]
0x18000acbf  retn
0x18000acc0  add     rcx, 0D8h
0x18000acc7  xor     eax, eax
0x18000acc9  cmp     edx, [r8+0ECh]
0x18000acd0  cmovz   rax, rcx
0x18000acd4  retn
```
