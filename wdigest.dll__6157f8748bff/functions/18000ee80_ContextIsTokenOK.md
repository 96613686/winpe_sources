# ContextIsTokenOK

- ea: `0x18000ee80`
- end: `0x18000ef39`
- name: `ContextIsTokenOK`
- size: `185`
- prototype: ``
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x18001e4b0`
- `0x1800206d0`
- `0x18002e180`
- `0x18002eb94`
- `0x18002f1ac`
- `0x18002f43c`
- `0x18002fe90`

## callees

- `0x18000ee80`
- `0x180011fec`
- `0x180018b18`

## pseudocode

```c
__int64 __fastcall ContextIsTokenOK(__int64 a1, unsigned int a2)
{
  _QWORD *v3; // rcx
  __int64 v4; // rdx

  if ( !a1 )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return 0;
    v4 = 44;
LABEL_14:
    WPP_SF_(v3[2], v4, WPP_5a1eec0057703498b5d13460810c8614_Traceguids);
    return 0;
  }
  if ( !*(_QWORD *)(a1 + 8) && *(_DWORD *)a1 )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return 0;
    v4 = 45;
    goto LABEL_14;
  }
  if ( !a2 || *(_DWORD *)a1 <= a2 )
    return 1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      46,
      WPP_5a1eec0057703498b5d13460810c8614_Traceguids,
      a2,
      *(_DWORD *)a1);
  return 0;
}

```

## disassembly

```asm
0x18000ee80  sub     rsp, 38h
0x18000ee84  mov     r9d, edx
0x18000ee87  test    rcx, rcx
0x18000ee8a  jz      short loc_18000EEA9
0x18000ee8c  cmp     qword ptr [rcx+8], 0
0x18000ee91  jz      short loc_18000EED0
0x18000ee93  test    r9d, r9d
0x18000ee96  jz      short loc_18000EE9F
0x18000ee98  mov     eax, [rcx]
0x18000ee9a  cmp     eax, r9d
0x18000ee9d  ja      short loc_18000EF05
0x18000ee9f  mov     eax, 1
0x18000eea4  add     rsp, 38h
0x18000eea8  retn
0x18000eea9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eeb0  lea     rdx, WPP_GLOBAL_Control
0x18000eeb7  cmp     rcx, rdx
0x18000eeba  jnz     short loc_18000EEC3
0x18000eebc  xor     eax, eax
0x18000eebe  add     rsp, 38h
0x18000eec2  retn
0x18000eec3  test    byte ptr [rcx+1Ch], 1
0x18000eec7  jz      short loc_18000EEBC
0x18000eec9  mov     edx, 2Ch ; ','
0x18000eece  jmp     short loc_18000EEF3
0x18000eed0  cmp     dword ptr [rcx], 0
0x18000eed3  jz      short loc_18000EE93
0x18000eed5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eedc  lea     rdx, WPP_GLOBAL_Control
0x18000eee3  cmp     rcx, rdx
0x18000eee6  jz      short loc_18000EEBC
0x18000eee8  test    byte ptr [rcx+1Ch], 1
0x18000eeec  jz      short loc_18000EEBC
0x18000eeee  mov     edx, 2Dh ; '-'
0x18000eef3  mov     rcx, [rcx+10h]
0x18000eef7  lea     r8, WPP_5a1eec0057703498b5d13460810c8614_Traceguids
0x18000eefe  call    WPP_SF_
0x18000ef03  jmp     short loc_18000EEBC
0x18000ef05  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ef0c  lea     rdx, WPP_GLOBAL_Control
0x18000ef13  cmp     rcx, rdx
0x18000ef16  jz      short loc_18000EEBC
0x18000ef18  test    byte ptr [rcx+1Ch], 1
0x18000ef1c  jz      short loc_18000EEBC
0x18000ef1e  mov     rcx, [rcx+10h]
0x18000ef22  lea     r8, WPP_5a1eec0057703498b5d13460810c8614_Traceguids
0x18000ef29  mov     edx, 2Eh ; '.'
0x18000ef2e  mov     [rsp+38h+var_18], eax
0x18000ef32  call    WPP_SF_dd
0x18000ef37  jmp     short loc_18000EEBC
```
