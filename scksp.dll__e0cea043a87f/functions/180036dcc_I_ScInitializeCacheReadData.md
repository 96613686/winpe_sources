# I_ScInitializeCacheReadData

- ea: `0x180036dcc`
- end: `0x180036e62`
- name: `I_ScInitializeCacheReadData`
- size: `150`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800375d4`

## callees

- `0x18000a408`
- `0x18000a590`
- `0x180013734`
- `0x180036dcc`

## pseudocode

```c
__int64 __fastcall I_ScInitializeCacheReadData(__int64 a1)
{
  PVOID v1; // rcx

  WppTraceIndent(a1, 0);
  v1 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids, WPP_pszIndent);
  }
  WppTraceIndent((__int64)v1, 1u);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      17,
      (unsigned int)WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids,
      WPP_pszIndent,
      0);
  }
  return 0;
}

```

## disassembly

```asm
0x180036dcc  push    rbx
0x180036dce  sub     rsp, 30h
0x180036dd2  xor     edx, edx
0x180036dd4  call    WppTraceIndent
0x180036dd9  mov     rcx, cs:WPP_GLOBAL_Control
0x180036de0  lea     rbx, WPP_GLOBAL_Control
0x180036de7  cmp     rcx, rbx
0x180036dea  jz      short loc_180036E14
0x180036dec  test    byte ptr [rcx+1Ch], 2
0x180036df0  jz      short loc_180036E14
0x180036df2  cmp     byte ptr [rcx+19h], 5
0x180036df6  jb      short loc_180036E14
0x180036df8  mov     r9, cs:WPP_pszIndent
0x180036dff  lea     r8, WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids
0x180036e06  mov     rcx, [rcx+10h]
0x180036e0a  mov     edx, 0Ah
0x180036e0f  call    WPP_SF_s
0x180036e14  mov     edx, 1
0x180036e19  call    WppTraceIndent
0x180036e1e  mov     rcx, cs:WPP_GLOBAL_Control
0x180036e25  cmp     rcx, rbx
0x180036e28  jz      short loc_180036E5A
0x180036e2a  test    byte ptr [rcx+1Ch], 2
0x180036e2e  jz      short loc_180036E5A
0x180036e30  cmp     byte ptr [rcx+19h], 5
0x180036e34  jb      short loc_180036E5A
0x180036e36  mov     r9, cs:WPP_pszIndent
0x180036e3d  lea     r8, WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids
0x180036e44  mov     rcx, [rcx+10h]
0x180036e48  mov     edx, 11h
0x180036e4d  mov     [rsp+38h+var_18], 0
0x180036e55  call    WPP_SF_sd
0x180036e5a  xor     eax, eax
0x180036e5c  add     rsp, 30h
0x180036e60  pop     rbx
0x180036e61  retn
```
