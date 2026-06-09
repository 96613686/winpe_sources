# GetMaxAgeFromCacheControl(char const *)

- ea: `0x180006fd0`
- end: `0x1800070c9`
- name: `?GetMaxAgeFromCacheControl@@YAHPEBD@Z`
- size: `249`
- prototype: `__int64 __fastcall(const char *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180006a60`
- `0x18000962c`

## callees

- `0x180006fd0`
- `0x180029df0`
- `0x18003623c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__atoi64` at `0x180007009`
- `api-ms-win-crt-private-l1-1-0!_o__atoi64` at `0x180007009`
- `api-ms-win-crt-private-l1-1-0!strchr` at `0x180006fe4`
- `api-ms-win-crt-private-l1-1-0!strchr` at `0x180006fe4`

## pseudocode

```c
__int64 __fastcall GetMaxAgeFromCacheControl(const char *a1)
{
  char *v1; // rbx
  __int64 v2; // rdx
  unsigned int v3; // eax
  LPCSTR v4; // r9
  unsigned int v5; // ecx

  if ( !a1 )
    return 0xFFFFFFFFLL;
  v1 = strchr(a1, 61);
  if ( !v1 )
    return 0xFFFFFFFFLL;
  if ( !g_fCheckedRegistry )
  {
    CheckRegistryForMinMaxLifetime();
    g_fCheckedRegistry = 1;
  }
  v2 = _atoi64(v1 + 1);
  v3 = g_nMaxLifetime;
  if ( v2 > g_nMaxLifetime )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 0x10) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, WPP_6f3552b14628310eb215fa0007e7d416_Traceguids);
      v3 = g_nMaxLifetime;
      v4 = WPP_GLOBAL_Control;
    }
    v2 = v3;
  }
  else
  {
    v4 = WPP_GLOBAL_Control;
  }
  v5 = g_nMinLifetime;
  if ( v2 < g_nMinLifetime )
  {
    if ( v4 != (LPCSTR)&WPP_GLOBAL_Control && (v4[28] & 0x10) != 0 )
    {
      WPP_SF_(*((_QWORD *)v4 + 2), 66, WPP_6f3552b14628310eb215fa0007e7d416_Traceguids);
      v5 = g_nMinLifetime;
    }
    LODWORD(v2) = v5;
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180006fd0  push    rbx
0x180006fd2  sub     rsp, 20h
0x180006fd6  test    rcx, rcx
0x180006fd9  jz      loc_1800070BF
0x180006fdf  mov     edx, 3Dh ; '='; Val
0x180006fe4  call    cs:__imp_strchr
0x180006feb  nop     dword ptr [rax+rax+00h]
0x180006ff0  mov     rbx, rax
0x180006ff3  test    rax, rax
0x180006ff6  jz      loc_1800070BF
0x180006ffc  cmp     cs:?g_fCheckedRegistry@@3HA, 0; int g_fCheckedRegistry
0x180007003  jz      short loc_180007072
0x180007005  lea     rcx, [rbx+1]; String
0x180007009  call    cs:__imp__atoi64
0x180007010  nop     dword ptr [rax+rax+00h]
0x180007015  mov     rdx, rax
0x180007018  lea     rbx, WPP_GLOBAL_Control
0x18000701f  mov     eax, cs:?g_nMaxLifetime@@3IA; uint g_nMaxLifetime
0x180007025  cmp     rdx, rax
0x180007028  jg      short loc_180007083
0x18000702a  mov     r9, cs:WPP_GLOBAL_Control
0x180007031  mov     ecx, cs:?g_nMinLifetime@@3IA; uint g_nMinLifetime
0x180007037  cmp     rdx, rcx
0x18000703a  jl      short loc_180007045
0x18000703c  mov     eax, edx
0x18000703e  add     rsp, 20h
0x180007042  pop     rbx
0x180007043  retn
0x180007045  cmp     r9, rbx
0x180007048  jnz     short loc_18000704E
0x18000704a  mov     edx, ecx
0x18000704c  jmp     short loc_18000703C
0x18000704e  test    byte ptr [r9+1Ch], 10h
0x180007053  jz      short loc_18000704A
0x180007055  mov     rcx, [r9+10h]
0x180007059  lea     r8, WPP_6f3552b14628310eb215fa0007e7d416_Traceguids
0x180007060  mov     edx, 42h ; 'B'
0x180007065  call    WPP_SF_
0x18000706a  mov     ecx, cs:?g_nMinLifetime@@3IA; uint g_nMinLifetime
0x180007070  jmp     short loc_18000704A
0x180007072  call    ?CheckRegistryForMinMaxLifetime@@YAXXZ; CheckRegistryForMinMaxLifetime(void)
0x180007077  mov     cs:?g_fCheckedRegistry@@3HA, 1; int g_fCheckedRegistry
0x180007081  jmp     short loc_180007005
0x180007083  mov     r9, cs:WPP_GLOBAL_Control
0x18000708a  cmp     r9, rbx
0x18000708d  jz      short loc_1800070B8
0x18000708f  test    byte ptr [r9+1Ch], 10h
0x180007094  jz      short loc_1800070B8
0x180007096  mov     rcx, [r9+10h]
0x18000709a  lea     r8, WPP_6f3552b14628310eb215fa0007e7d416_Traceguids
0x1800070a1  mov     edx, 41h ; 'A'
0x1800070a6  call    WPP_SF_
0x1800070ab  mov     eax, cs:?g_nMaxLifetime@@3IA; uint g_nMaxLifetime
0x1800070b1  mov     r9, cs:WPP_GLOBAL_Control
0x1800070b8  mov     edx, eax
0x1800070ba  jmp     loc_180007031
0x1800070bf  mov     eax, 0FFFFFFFFh
0x1800070c4  jmp     loc_18000703E
```
