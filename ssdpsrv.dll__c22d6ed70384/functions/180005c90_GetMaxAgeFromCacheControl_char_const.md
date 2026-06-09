# GetMaxAgeFromCacheControl(char const *)

- ea: `0x180005c90`
- end: `0x180005d7c`
- name: `?GetMaxAgeFromCacheControl@@YAHPEBD@Z`
- size: `236`
- prototype: `__int64 __fastcall(const char *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180005740`
- `0x180007bec`

## callees

- `0x180005c90`
- `0x180028000`
- `0x1800337b8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__atoi64` at `0x180005cc3`
- `api-ms-win-crt-private-l1-1-0!_o__atoi64` at `0x180005cc3`
- `api-ms-win-crt-private-l1-1-0!strchr` at `0x180005ca4`
- `api-ms-win-crt-private-l1-1-0!strchr` at `0x180005ca4`

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
0x180005c90  push    rbx
0x180005c92  sub     rsp, 20h
0x180005c96  test    rcx, rcx
0x180005c99  jz      loc_180005D72
0x180005c9f  mov     edx, 3Dh ; '='; Val
0x180005ca4  call    cs:__imp_strchr
0x180005caa  mov     rbx, rax
0x180005cad  test    rax, rax
0x180005cb0  jz      loc_180005D72
0x180005cb6  cmp     cs:?g_fCheckedRegistry@@3HA, 0; int g_fCheckedRegistry
0x180005cbd  jz      short loc_180005D25
0x180005cbf  lea     rcx, [rbx+1]; String
0x180005cc3  call    cs:__imp__atoi64
0x180005cc9  mov     rdx, rax
0x180005ccc  lea     rbx, WPP_GLOBAL_Control
0x180005cd3  mov     eax, cs:?g_nMaxLifetime@@3IA; uint g_nMaxLifetime
0x180005cd9  cmp     rdx, rax
0x180005cdc  jg      short loc_180005D36
0x180005cde  mov     r9, cs:WPP_GLOBAL_Control
0x180005ce5  mov     ecx, cs:?g_nMinLifetime@@3IA; uint g_nMinLifetime
0x180005ceb  cmp     rdx, rcx
0x180005cee  jl      short loc_180005CF8
0x180005cf0  mov     eax, edx
0x180005cf2  add     rsp, 20h
0x180005cf6  pop     rbx
0x180005cf7  retn
0x180005cf8  cmp     r9, rbx
0x180005cfb  jnz     short loc_180005D01
0x180005cfd  mov     edx, ecx
0x180005cff  jmp     short loc_180005CF0
0x180005d01  test    byte ptr [r9+1Ch], 10h
0x180005d06  jz      short loc_180005CFD
0x180005d08  mov     rcx, [r9+10h]
0x180005d0c  lea     r8, WPP_6f3552b14628310eb215fa0007e7d416_Traceguids
0x180005d13  mov     edx, 42h ; 'B'
0x180005d18  call    WPP_SF_
0x180005d1d  mov     ecx, cs:?g_nMinLifetime@@3IA; uint g_nMinLifetime
0x180005d23  jmp     short loc_180005CFD
0x180005d25  call    ?CheckRegistryForMinMaxLifetime@@YAXXZ; CheckRegistryForMinMaxLifetime(void)
0x180005d2a  mov     cs:?g_fCheckedRegistry@@3HA, 1; int g_fCheckedRegistry
0x180005d34  jmp     short loc_180005CBF
0x180005d36  mov     r9, cs:WPP_GLOBAL_Control
0x180005d3d  cmp     r9, rbx
0x180005d40  jz      short loc_180005D6B
0x180005d42  test    byte ptr [r9+1Ch], 10h
0x180005d47  jz      short loc_180005D6B
0x180005d49  mov     rcx, [r9+10h]
0x180005d4d  lea     r8, WPP_6f3552b14628310eb215fa0007e7d416_Traceguids
0x180005d54  mov     edx, 41h ; 'A'
0x180005d59  call    WPP_SF_
0x180005d5e  mov     eax, cs:?g_nMaxLifetime@@3IA; uint g_nMaxLifetime
0x180005d64  mov     r9, cs:WPP_GLOBAL_Control
0x180005d6b  mov     edx, eax
0x180005d6d  jmp     loc_180005CE5
0x180005d72  mov     eax, 0FFFFFFFFh
0x180005d77  jmp     loc_180005CF2
```
