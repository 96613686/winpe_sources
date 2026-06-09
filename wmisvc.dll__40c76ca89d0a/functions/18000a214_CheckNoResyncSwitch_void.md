# CheckNoResyncSwitch(void)

- ea: `0x18000a214`
- end: `0x18000a333`
- name: `?CheckNoResyncSwitch@@YAHXZ`
- size: `287`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000b760`

## callees

- `0x18000a214`
- `0x18000b648`

## import_xrefs

- `wbemcomn!??0Registry@@QEAA@PEBGK@Z` at `0x18000a238`
- `wbemcomn!??0Registry@@QEAA@PEBGK@Z` at `0x18000a238`
- `wbemcomn!??1Registry@@QEAA@XZ` at `0x18000a314`
- `wbemcomn!??1Registry@@QEAA@XZ` at `0x18000a320`
- `wbemcomn!??1Registry@@QEAA@XZ` at `0x18000a314`
- `wbemcomn!??1Registry@@QEAA@XZ` at `0x18000a320`
- `wbemcomn!?GetDWORDStr@Registry@@QEAAHPEBGPEAK@Z` at `0x18000a250`
- `wbemcomn!?GetDWORDStr@Registry@@QEAAHPEBGPEAK@Z` at `0x18000a250`
- `wbemcomn!??0Registry@@QEAA@PEAUHKEY__@@KPEBG@Z` at `0x18000a2b4`
- `wbemcomn!??0Registry@@QEAA@PEAUHKEY__@@KPEBG@Z` at `0x18000a2b4`
- `wbemcomn!?GetDWORD@Registry@@QEAAHPEBGPEAK@Z` at `0x18000a2d1`
- `wbemcomn!?GetDWORD@Registry@@QEAAHPEBGPEAK@Z` at `0x18000a2d1`

## pseudocode

```c
__int64 CheckNoResyncSwitch(void)
{
  unsigned int v0; // ebx
  _BYTE v2[24]; // [rsp+20h] [rbp-38h] BYREF
  _BYTE v3[32]; // [rsp+38h] [rbp-20h] BYREF
  unsigned int v4; // [rsp+60h] [rbp+8h] BYREF

  v4 = 0;
  Registry::Registry((Registry *)v3, L"Software\\Microsoft\\WBEM\\CIMOM", 1u);
  if ( !Registry::GetDWORDStr((Registry *)v3, L"NoResyncPerf", &v4) )
  {
    if ( v4 )
    {
      v0 = 0;
      goto LABEL_16;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_1ead9032b647397af64ee4622953436c_Traceguids);
    }
  }
  Registry::Registry((Registry *)v2, HKEY_LOCAL_MACHINE, 0x20019u, L"Software\\Microsoft\\WBEM\\CIMOM\\ADAP");
  v0 = 1;
  if ( !Registry::GetDWORD((Registry *)v2, L"NoShell", &v4) )
  {
    if ( v4 )
    {
      v0 = 0;
    }
    else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_1ead9032b647397af64ee4622953436c_Traceguids);
    }
  }
  Registry::~Registry((Registry *)v2);
LABEL_16:
  Registry::~Registry((Registry *)v3);
  return v0;
}

```

## disassembly

```asm
0x18000a214  mov     [rsp+arg_8], rbx
0x18000a219  push    rbp
0x18000a21a  sub     rsp, 50h
0x18000a21e  mov     [rsp+58h+arg_0], 0
0x18000a226  mov     r8d, 1
0x18000a22c  lea     rdx, SubKey; "Software\\Microsoft\\WBEM\\CIMOM"
0x18000a233  lea     rcx, [rsp+58h+var_20]
0x18000a238  call    cs:__imp_??0Registry@@QEAA@PEBGK@Z; Registry::Registry(ushort const *,ulong)
0x18000a23e  nop
0x18000a23f  lea     r8, [rsp+58h+arg_0]
0x18000a244  lea     rdx, aNoresyncperf; "NoResyncPerf"
0x18000a24b  lea     rcx, [rsp+58h+var_20]
0x18000a250  call    cs:__imp_?GetDWORDStr@Registry@@QEAAHPEBGPEAK@Z; Registry::GetDWORDStr(ushort const *,ulong *)
0x18000a256  lea     rbp, WPP_GLOBAL_Control
0x18000a25d  test    eax, eax
0x18000a25f  jnz     short loc_18000A29B
0x18000a261  cmp     [rsp+58h+arg_0], eax
0x18000a265  jz      short loc_18000A26E
0x18000a267  xor     ebx, ebx
0x18000a269  jmp     loc_18000A31B
0x18000a26e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a275  cmp     rcx, rbp
0x18000a278  jz      short loc_18000A29B
0x18000a27a  test    byte ptr [rcx+1Ch], 1
0x18000a27e  jz      short loc_18000A29B
0x18000a280  cmp     byte ptr [rcx+19h], 5
0x18000a284  jb      short loc_18000A29B
0x18000a286  mov     edx, 0Ah
0x18000a28b  lea     r8, WPP_1ead9032b647397af64ee4622953436c_Traceguids
0x18000a292  mov     rcx, [rcx+10h]
0x18000a296  call    WPP_SF_
0x18000a29b  lea     r9, aSoftwareMicros_2; "Software\\Microsoft\\WBEM\\CIMOM\\ADAP"
0x18000a2a2  mov     rdx, 0FFFFFFFF80000002h
0x18000a2a9  mov     r8d, 20019h
0x18000a2af  lea     rcx, [rsp+58h+var_38]
0x18000a2b4  call    cs:__imp_??0Registry@@QEAA@PEAUHKEY__@@KPEBG@Z; Registry::Registry(HKEY__ *,ulong,ushort const *)
0x18000a2ba  nop
0x18000a2bb  mov     ebx, 1
0x18000a2c0  lea     r8, [rsp+58h+arg_0]
0x18000a2c5  lea     rdx, aNoshell; "NoShell"
0x18000a2cc  lea     rcx, [rsp+58h+var_38]
0x18000a2d1  call    cs:__imp_?GetDWORD@Registry@@QEAAHPEBGPEAK@Z; Registry::GetDWORD(ushort const *,ulong *)
0x18000a2d7  test    eax, eax
0x18000a2d9  jnz     short loc_18000A30F
0x18000a2db  cmp     [rsp+58h+arg_0], eax
0x18000a2df  jnz     short loc_18000A30D
0x18000a2e1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a2e8  cmp     rcx, rbp
0x18000a2eb  jz      short loc_18000A30F
0x18000a2ed  test    [rcx+1Ch], bl
0x18000a2f0  jz      short loc_18000A30F
0x18000a2f2  cmp     byte ptr [rcx+19h], 5
0x18000a2f6  jb      short loc_18000A30F
0x18000a2f8  lea     edx, [rbx+0Ah]
0x18000a2fb  lea     r8, WPP_1ead9032b647397af64ee4622953436c_Traceguids
0x18000a302  mov     rcx, [rcx+10h]
0x18000a306  call    WPP_SF_
0x18000a30b  jmp     short loc_18000A30F
0x18000a30d  xor     ebx, ebx
0x18000a30f  lea     rcx, [rsp+58h+var_38]
0x18000a314  call    cs:__imp_??1Registry@@QEAA@XZ; Registry::~Registry(void)
0x18000a31a  nop
0x18000a31b  lea     rcx, [rsp+58h+var_20]
0x18000a320  call    cs:__imp_??1Registry@@QEAA@XZ; Registry::~Registry(void)
0x18000a326  mov     eax, ebx
0x18000a328  mov     rbx, [rsp+58h+arg_8]
0x18000a32d  add     rsp, 50h
0x18000a331  pop     rbp
0x18000a332  retn
```
