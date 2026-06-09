# DigestUserCompareDirectives

- ea: `0x18002dfc8`
- end: `0x18002e0b0`
- name: `DigestUserCompareDirectives`
- size: `232`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002e180`

## callees

- `0x180011fec`
- `0x1800185b8`
- `0x18002dfc8`
- `0x180032f18`

## import_xrefs

- `ntdll!RtlEqualString` at `0x18002e03b`
- `ntdll!RtlEqualString` at `0x18002e03b`

## pseudocode

```c
__int64 __fastcall DigestUserCompareDirectives(__int64 a1, __int64 a2)
{
  unsigned int v4; // edi
  int i; // ebx
  __int64 v6; // r8
  PVOID *v7; // rcx

  v4 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 336, &WPP_3a9703e229fb3d42fb846768cfaf323c_Traceguids);
  for ( i = 0; ; ++i )
  {
    if ( i >= 24 )
      goto LABEL_13;
    if ( (!i || (unsigned int)(i - 1) <= 1)
      && !RtlEqualString((const STRING *)(16LL * i + a1 + 280), (const STRING *)(16LL * i + a2 + 24), 0) )
    {
      break;
    }
  }
  v4 = -2146893018;
  v7 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v4;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_dD(*((_QWORD *)WPP_GLOBAL_Control + 2), 337, v6, (unsigned int)i, -2146893018);
LABEL_13:
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v7 != &WPP_GLOBAL_Control && *((char *)v7 + 28) < 0 )
    WPP_SF_d(v7[2], 338, &WPP_3a9703e229fb3d42fb846768cfaf323c_Traceguids, v4);
  return v4;
}

```

## disassembly

```asm
0x18002dfc8  push    rbx
0x18002dfca  push    rbp
0x18002dfcb  push    rsi
0x18002dfcc  push    rdi
0x18002dfcd  push    r14
0x18002dfcf  sub     rsp, 30h
0x18002dfd3  mov     rsi, rdx
0x18002dfd6  mov     rbp, rcx
0x18002dfd9  xor     edi, edi
0x18002dfdb  mov     rcx, cs:WPP_GLOBAL_Control
0x18002dfe2  lea     r14, WPP_GLOBAL_Control
0x18002dfe9  cmp     rcx, r14
0x18002dfec  jz      short loc_18002E009
0x18002dfee  test    byte ptr [rcx+1Ch], 80h
0x18002dff2  jz      short loc_18002E009
0x18002dff4  mov     rcx, [rcx+10h]
0x18002dff8  lea     r8, WPP_3a9703e229fb3d42fb846768cfaf323c_Traceguids
0x18002dfff  mov     edx, 150h
0x18002e004  call    WPP_SF_
0x18002e009  xor     ebx, ebx
0x18002e00b  cmp     ebx, 18h
0x18002e00e  jge     short loc_18002E079
0x18002e010  mov     ecx, ebx
0x18002e012  test    ebx, ebx
0x18002e014  jz      short loc_18002E020
0x18002e016  sub     ecx, 1
0x18002e019  jz      short loc_18002E020
0x18002e01b  cmp     ecx, 1
0x18002e01e  jnz     short loc_18002E045
0x18002e020  movsxd  rax, ebx
0x18002e023  lea     rdx, [rsi+18h]
0x18002e027  shl     rax, 4
0x18002e02b  lea     rcx, [rbp+118h]
0x18002e032  add     rdx, rax; String2
0x18002e035  add     rcx, rax; String1
0x18002e038  xor     r8d, r8d; CaseInSensitive
0x18002e03b  call    cs:__imp_RtlEqualString
0x18002e041  test    al, al
0x18002e043  jz      short loc_18002E049
0x18002e045  inc     ebx
0x18002e047  jmp     short loc_18002E00B
0x18002e049  mov     edi, 80090326h
0x18002e04e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e055  cmp     rcx, r14
0x18002e058  jz      short loc_18002E0A3
0x18002e05a  test    byte ptr [rcx+1Ch], 1
0x18002e05e  jz      short loc_18002E080
0x18002e060  mov     rcx, [rcx+10h]
0x18002e064  mov     edx, 151h
0x18002e069  mov     r9d, ebx
0x18002e06c  mov     [rsp+58h+var_38], 80090326h
0x18002e074  call    WPP_SF_dD
0x18002e079  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e080  cmp     rcx, r14
0x18002e083  jz      short loc_18002E0A3
0x18002e085  test    byte ptr [rcx+1Ch], 80h
0x18002e089  jz      short loc_18002E0A3
0x18002e08b  mov     rcx, [rcx+10h]
0x18002e08f  lea     r8, WPP_3a9703e229fb3d42fb846768cfaf323c_Traceguids
0x18002e096  mov     edx, 152h
0x18002e09b  mov     r9d, edi
0x18002e09e  call    WPP_SF_d
0x18002e0a3  mov     eax, edi
0x18002e0a5  add     rsp, 30h
0x18002e0a9  pop     r14
0x18002e0ab  pop     rdi
0x18002e0ac  pop     rsi
0x18002e0ad  pop     rbp
0x18002e0ae  pop     rbx
0x18002e0af  retn
```
