# CommandArguments::GetArgument(unsigned __int64)

- ea: `0x14002445c`
- end: `0x1400244fb`
- name: `?GetArgument@CommandArguments@@QEBAAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_K@Z`
- size: `159`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `10`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14000f09c`
- `0x14001c6b0`
- `0x14001cfd0`
- `0x140024c90`
- `0x140024e00`
- `0x1400265e0`
- `0x140026a90`
- `0x1400271f0`
- `0x1400274f0`
- `0x140027e70`

## callees

- `0x140010450`
- `0x140022cec`
- `0x14002445c`
- `0x140031810`

## pseudocode

```c
__int64 __fastcall CommandArguments::GetArgument(__int64 a1, unsigned __int64 a2)
{
  __int64 v2; // r8
  const char *v4; // [rsp+20h] [rbp-58h]
  _BYTE pExceptionObject[56]; // [rsp+40h] [rbp-38h] BYREF

  v2 = *(_QWORD *)(a1 + 16);
  if ( a2 >= (*(_QWORD *)(a1 + 24) - v2) >> 5 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_1febe5f9a22d3f0baf040961cd9dcd00_Traceguids, 87);
    }
    EvtException::EvtException((EvtException *)pExceptionObject, 0x57u, 0, 0, v4, 164, 0x11u, 0);
    throw (EvtException *)pExceptionObject;
  }
  return v2 + 32 * a2;
}

```

## disassembly

```asm
0x14002445c  sub     rsp, 78h
0x140024460  mov     r8, [rcx+10h]
0x140024464  mov     rax, [rcx+18h]
0x140024468  sub     rax, r8
0x14002446b  sar     rax, 5
0x14002446f  cmp     rdx, rax
0x140024472  jb      short loc_1400244EE
0x140024474  mov     rcx, cs:WPP_GLOBAL_Control
0x14002447b  lea     rax, WPP_GLOBAL_Control
0x140024482  cmp     rcx, rax
0x140024485  jz      short loc_1400244AF
0x140024487  test    dword ptr [rcx+1Ch], 400000h
0x14002448e  jz      short loc_1400244AF
0x140024490  cmp     byte ptr [rcx+19h], 2
0x140024494  jb      short loc_1400244AF
0x140024496  mov     rcx, [rcx+10h]
0x14002449a  lea     r8, WPP_1febe5f9a22d3f0baf040961cd9dcd00_Traceguids
0x1400244a1  mov     edx, 12h
0x1400244a6  lea     r9d, [rdx+45h]
0x1400244aa  call    WPP_SF_d
0x1400244af  xor     r9d, r9d; unsigned int
0x1400244b2  mov     [rsp+78h+Src], 0; Src
0x1400244bb  mov     [rsp+78h+var_48], 11h; unsigned int
0x1400244c3  lea     rcx, [rsp+78h+pExceptionObject]; this
0x1400244c8  xor     r8d, r8d; unsigned int
0x1400244cb  mov     [rsp+78h+var_50], 0A4h; int
0x1400244d3  lea     edx, [r9+57h]; unsigned int
0x1400244d7  call    ??0EvtException@@QEAA@KKKPEBDHKPEB_W@Z; EvtException::EvtException(ulong,ulong,ulong,char const *,int,ulong,wchar_t const *)
0x1400244dc  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1400244e3  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x1400244e8  call    _CxxThrowException_0
0x1400244ee  shl     rdx, 5
0x1400244f2  lea     rax, [r8+rdx]
0x1400244f6  add     rsp, 78h
0x1400244fa  retn
```
