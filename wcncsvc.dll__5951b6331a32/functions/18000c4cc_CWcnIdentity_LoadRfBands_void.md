# CWcnIdentity::LoadRfBands(void)

- ea: `0x18000c4cc`
- end: `0x18000c583`
- name: `?LoadRfBands@CWcnIdentity@@AEAA?AW4tagWCN_VALUE_TYPE_RF_BANDS@@XZ`
- size: `183`
- prototype: `__int64 __fastcall(CWcnIdentity *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x18000b850`

## callees

- `0x180005014`
- `0x18000c4cc`
- `0x180053004`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000c51b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000c51b`

## string_xrefs

- `0x18000c4ff`: `SYSTEM\CurrentControlSet\Services\wcncsvc\Parameters`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CWcnIdentity::LoadRfBands(CWcnIdentity *this)
{
  int v1; // eax
  unsigned int v2; // ebx
  unsigned int Indent; // eax
  __int64 v4; // r10
  int v6; // [rsp+50h] [rbp+8h] BYREF
  int v7; // [rsp+54h] [rbp+Ch]
  DWORD v8; // [rsp+58h] [rbp+10h] BYREF

  v7 = HIDWORD(this);
  v6 = 0;
  v8 = 4;
  if ( RegGetValueW(
         HKEY_LOCAL_MACHINE,
         L"SYSTEM\\CurrentControlSet\\Services\\wcncsvc\\Parameters",
         L"5GhzBandEnabled",
         0x10u,
         0,
         &v6,
         &v8) )
  {
    v1 = 0;
    v6 = 0;
  }
  else
  {
    v1 = v6;
  }
  v2 = 1;
  if ( v1 )
    v2 = 3;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    Indent = (unsigned int)GetIndent(0);
    WPP_SF_sd(*(_QWORD *)(v4 + 16), 19, (unsigned int)WPP_e632221d673033b22bf624a0da3869d5_Traceguids, Indent, v2);
  }
  return v2;
}

```

## disassembly

```asm
0x18000c4cc  mov     r11, rsp
0x18000c4cf  mov     [r11+8], rcx
0x18000c4d3  push    rbx
0x18000c4d4  sub     rsp, 40h
0x18000c4d8  lea     rax, [r11+10h]
0x18000c4dc  mov     [rsp+48h+arg_0], 0
0x18000c4e4  mov     [r11-18h], rax
0x18000c4e8  lea     r8, a5ghzbandenable; "5GhzBandEnabled"
0x18000c4ef  lea     rax, [r11+8]
0x18000c4f3  mov     [rsp+48h+arg_8], 4
0x18000c4fb  mov     [r11-20h], rax
0x18000c4ff  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\wc"...
0x18000c506  mov     r9d, 10h; dwFlags
0x18000c50c  mov     qword ptr [r11-28h], 0
0x18000c514  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18000c51b  call    cs:__imp_RegGetValueW
0x18000c521  test    eax, eax
0x18000c523  jz      short loc_18000C52D
0x18000c525  xor     eax, eax
0x18000c527  mov     [rsp+48h+arg_0], eax
0x18000c52b  jmp     short loc_18000C531
0x18000c52d  mov     eax, [rsp+48h+arg_0]
0x18000c531  mov     ebx, 1
0x18000c536  test    eax, eax
0x18000c538  lea     ecx, [rbx+2]
0x18000c53b  cmovnz  ebx, ecx
0x18000c53e  mov     r10, cs:WPP_GLOBAL_Control
0x18000c545  lea     rax, WPP_GLOBAL_Control
0x18000c54c  cmp     r10, rax
0x18000c54f  jz      short loc_18000C57B
0x18000c551  cmp     byte ptr [r10+19h], 4
0x18000c556  jb      short loc_18000C57B
0x18000c558  xor     ecx, ecx; int
0x18000c55a  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18000c55f  mov     rcx, [r10+10h]
0x18000c563  lea     r8, WPP_e632221d673033b22bf624a0da3869d5_Traceguids
0x18000c56a  mov     edx, 13h
0x18000c56f  mov     [rsp+48h+var_28], ebx
0x18000c573  mov     r9, rax
0x18000c576  call    WPP_SF_sd
0x18000c57b  mov     eax, ebx
0x18000c57d  add     rsp, 40h
0x18000c581  pop     rbx
0x18000c582  retn
```
