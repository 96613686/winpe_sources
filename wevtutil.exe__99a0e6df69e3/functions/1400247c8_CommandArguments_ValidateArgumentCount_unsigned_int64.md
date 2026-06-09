# CommandArguments::ValidateArgumentCount(unsigned __int64)

- ea: `0x1400247c8`
- end: `0x1400248d8`
- name: `?ValidateArgumentCount@CommandArguments@@QEBAX_K@Z`
- size: `272`
- prototype: `void __fastcall(CommandArguments *__hidden this, unsigned __int64)`
- caller_count: `10`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14001c6b0`
- `0x14001cfd0`
- `0x140024c90`
- `0x140024e00`
- `0x140025af0`
- `0x1400265e0`
- `0x140026a90`
- `0x1400271f0`
- `0x1400274f0`
- `0x140027e70`

## callees

- `0x140010450`
- `0x140022cec`
- `0x1400247c8`
- `0x140031810`

## pseudocode

```c
void __fastcall CommandArguments::ValidateArgumentCount(CommandArguments *this, unsigned __int64 a2)
{
  unsigned __int64 v2; // rax
  const char *v3; // [rsp+20h] [rbp-58h]
  _BYTE pExceptionObject[56]; // [rsp+40h] [rbp-38h] BYREF

  v2 = (__int64)(*((_QWORD *)this + 3) - *((_QWORD *)this + 2)) >> 5;
  if ( v2 < a2 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_1febe5f9a22d3f0baf040961cd9dcd00_Traceguids, 87);
    }
    EvtException::EvtException((EvtException *)pExceptionObject, 0x57u, 0, 0, v3, 208, 0x10u, 0);
    throw (EvtException *)pExceptionObject;
  }
  if ( v2 > a2 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_1febe5f9a22d3f0baf040961cd9dcd00_Traceguids, 87);
    }
    EvtException::EvtException((EvtException *)pExceptionObject, 0x57u, 0, 0, v3, 213, 0xFu, 0);
    throw (EvtException *)pExceptionObject;
  }
}

```

## disassembly

```asm
0x1400247c8  sub     rsp, 78h
0x1400247cc  mov     rax, [rcx+18h]
0x1400247d0  sub     rax, [rcx+10h]
0x1400247d4  sar     rax, 5
0x1400247d8  cmp     rax, rdx
0x1400247db  jnb     short loc_140024857
0x1400247dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400247e4  lea     rax, WPP_GLOBAL_Control
0x1400247eb  cmp     rcx, rax
0x1400247ee  jz      short loc_140024818
0x1400247f0  test    dword ptr [rcx+1Ch], 400000h
0x1400247f7  jz      short loc_140024818
0x1400247f9  cmp     byte ptr [rcx+19h], 2
0x1400247fd  jb      short loc_140024818
0x1400247ff  mov     rcx, [rcx+10h]
0x140024803  lea     r8, WPP_1febe5f9a22d3f0baf040961cd9dcd00_Traceguids
0x14002480a  mov     edx, 14h
0x14002480f  lea     r9d, [rdx+43h]
0x140024813  call    WPP_SF_d
0x140024818  xor     r9d, r9d; unsigned int
0x14002481b  mov     [rsp+78h+Src], 0; Src
0x140024824  mov     [rsp+78h+var_48], 10h; unsigned int
0x14002482c  lea     rcx, [rsp+78h+pExceptionObject]; this
0x140024831  xor     r8d, r8d; unsigned int
0x140024834  mov     [rsp+78h+var_50], 0D0h; int
0x14002483c  lea     edx, [r9+57h]; unsigned int
0x140024840  call    ??0EvtException@@QEAA@KKKPEBDHKPEB_W@Z; EvtException::EvtException(ulong,ulong,ulong,char const *,int,ulong,wchar_t const *)
0x140024845  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14002484c  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x140024851  call    _CxxThrowException_0
0x140024857  jbe     short loc_1400248D3
0x140024859  mov     rcx, cs:WPP_GLOBAL_Control
0x140024860  lea     rax, WPP_GLOBAL_Control
0x140024867  cmp     rcx, rax
0x14002486a  jz      short loc_140024894
0x14002486c  test    dword ptr [rcx+1Ch], 400000h
0x140024873  jz      short loc_140024894
0x140024875  cmp     byte ptr [rcx+19h], 2
0x140024879  jb      short loc_140024894
0x14002487b  mov     rcx, [rcx+10h]
0x14002487f  lea     r8, WPP_1febe5f9a22d3f0baf040961cd9dcd00_Traceguids
0x140024886  mov     edx, 15h
0x14002488b  lea     r9d, [rdx+42h]
0x14002488f  call    WPP_SF_d
0x140024894  xor     r9d, r9d; unsigned int
0x140024897  mov     [rsp+78h+Src], 0; Src
0x1400248a0  mov     [rsp+78h+var_48], 0Fh; unsigned int
0x1400248a8  lea     rcx, [rsp+78h+pExceptionObject]; this
0x1400248ad  xor     r8d, r8d; unsigned int
0x1400248b0  mov     [rsp+78h+var_50], 0D5h; int
0x1400248b8  lea     edx, [r9+57h]; unsigned int
0x1400248bc  call    ??0EvtException@@QEAA@KKKPEBDHKPEB_W@Z; EvtException::EvtException(ulong,ulong,ulong,char const *,int,ulong,wchar_t const *)
0x1400248c1  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1400248c8  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x1400248cd  call    _CxxThrowException_0
0x1400248d3  add     rsp, 78h
0x1400248d7  retn
```
