# TpmTransportTis::CancelCurrentCommand(void)

- ea: `0x140024f40`
- end: `0x140024fce`
- name: `?CancelCurrentCommand@TpmTransportTis@@UEAAXXZ`
- size: `142`
- prototype: `void __fastcall(TpmTransportTis *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1400078b8`
- `0x14000ff70`
- `0x1400103f8`
- `0x140024f40`

## pseudocode

```c
void __fastcall TpmTransportTis::CancelCurrentCommand(TpmTransportTis *this)
{
  __int64 v2; // rdx
  __int64 v3; // rcx

  if ( *((_DWORD *)this + 78) && TpmTransport::ShouldCancelCommand(this, *((_DWORD *)this + 79) != 0) )
  {
    if ( LODWORD(WPP_MAIN_CB.DeviceExtension) == 6 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_180f891eace83e5bd5ec0d2a96c28cc7_Traceguids);
      TpmRegister<unsigned char>::Write((unsigned int *)this + 84, v2, 1);
    }
    else
    {
      TpmRegister<unsigned char>::Write((unsigned int *)(v3 + 324), v2, 64);
      *((_DWORD *)this + 78) = 0;
    }
  }
}

```

## disassembly

```asm
0x140024f40  push    rbx
0x140024f42  sub     rsp, 20h
0x140024f46  cmp     dword ptr [rcx+138h], 0
0x140024f4d  mov     rbx, rcx
0x140024f50  jz      short loc_140024FC7
0x140024f52  cmp     dword ptr [rcx+13Ch], 0
0x140024f59  setnz   dl; bool
0x140024f5c  call    ?ShouldCancelCommand@TpmTransport@@IEBA_N_N@Z; TpmTransport::ShouldCancelCommand(bool)
0x140024f61  test    al, al
0x140024f63  jz      short loc_140024FC7
0x140024f65  cmp     dword ptr cs:WPP_MAIN_CB.DeviceExtension, 6
0x140024f6c  jnz     short loc_140024FAE
0x140024f6e  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140024f75  lea     rax, WPP_GLOBAL_Control
0x140024f7c  cmp     rcx, rax
0x140024f7f  jz      short loc_140024F9D
0x140024f81  mov     eax, [rcx+2Ch]
0x140024f84  test    al, 2
0x140024f86  jz      short loc_140024F9D
0x140024f88  mov     rcx, [rcx+18h]
0x140024f8c  lea     r8, WPP_180f891eace83e5bd5ec0d2a96c28cc7_Traceguids
0x140024f93  mov     edx, 17h
0x140024f98  call    WPP_SF_
0x140024f9d  lea     rcx, [rbx+150h]
0x140024fa4  mov     r8b, 1
0x140024fa7  call    ?Write@?$TpmRegister@E@@QEAAXIE@Z; TpmRegister<uchar>::Write(uint,uchar)
0x140024fac  jmp     short loc_140024FC7
0x140024fae  add     rcx, 144h
0x140024fb5  mov     r8b, 40h ; '@'
0x140024fb8  call    ?Write@?$TpmRegister@E@@QEAAXIE@Z; TpmRegister<uchar>::Write(uint,uchar)
0x140024fbd  mov     dword ptr [rbx+138h], 0
0x140024fc7  add     rsp, 20h
0x140024fcb  pop     rbx
0x140024fcc  retn
```
