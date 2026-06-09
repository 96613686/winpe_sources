# WPP_SF__sid_

- ea: `0x180078fb4`
- end: `0x18007903c`
- name: `WPP_SF__sid_`
- size: `136`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180011a00`
- `0x180014ea0`
- `0x1800261c0`
- `0x180078860`
- `0x180078d20`
- `0x1800902b4`
- `0x1800908f0`

## callees

- `0x180078fb4`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x18007902b`
- `ntdll!EtwTraceMessage` at `0x18007902b`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180078fe0`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180078fe0`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180078fd3`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180078ff7`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180078fd3`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180078ff7`

## pseudocode

```c
__int64 __fastcall WPP_SF__sid_(__int64 a1, unsigned __int16 a2, __int64 a3, char *a4)
{
  unsigned int v4; // ebp
  char *v5; // rbx
  DWORD LengthSid; // edi

  v4 = a2;
  v5 = a4;
  if ( a4 && IsValidSid(a4) )
  {
    LengthSid = GetLengthSid(v5);
  }
  else
  {
    LengthSid = 5;
    if ( !v5 )
    {
LABEL_6:
      v5 = "NULL";
      return EtwTraceMessage(a1, 43, a3, v4, v5, LengthSid, 0);
    }
  }
  if ( !IsValidSid(v5) )
    goto LABEL_6;
  return EtwTraceMessage(a1, 43, a3, v4, v5, LengthSid, 0);
}

```

## disassembly

```asm
0x180078fb4  push    rbx
0x180078fb6  push    rbp
0x180078fb7  push    rsi
0x180078fb8  push    rdi
0x180078fb9  push    r14
0x180078fbb  sub     rsp, 40h
0x180078fbf  movzx   ebp, dx
0x180078fc2  mov     rbx, r9
0x180078fc5  mov     rsi, r8
0x180078fc8  mov     r14, rcx
0x180078fcb  test    r9, r9
0x180078fce  jz      short loc_180078FEA
0x180078fd0  mov     rcx, rbx; pSid
0x180078fd3  call    cs:__imp_IsValidSid
0x180078fd9  test    eax, eax
0x180078fdb  jz      short loc_180078FEA
0x180078fdd  mov     rcx, rbx; pSid
0x180078fe0  call    cs:__imp_GetLengthSid
0x180078fe6  mov     edi, eax
0x180078fe8  jmp     short loc_180078FF4
0x180078fea  mov     edi, 5
0x180078fef  test    rbx, rbx
0x180078ff2  jz      short loc_180079001
0x180078ff4  mov     rcx, rbx; pSid
0x180078ff7  call    cs:__imp_IsValidSid
0x180078ffd  test    eax, eax
0x180078fff  jnz     short loc_180079008
0x180079001  lea     rbx, aNull; "NULL"
0x180079008  mov     eax, edi
0x18007900a  mov     r9d, ebp
0x18007900d  mov     [rsp+68h+var_38], 0
0x180079016  mov     r8, rsi
0x180079019  mov     [rsp+68h+var_40], rax
0x18007901e  mov     edx, 2Bh ; '+'
0x180079023  mov     rcx, r14
0x180079026  mov     [rsp+68h+var_48], rbx
0x18007902b  call    cs:__imp_EtwTraceMessage
0x180079031  add     rsp, 40h
0x180079035  pop     r14
0x180079037  pop     rdi
0x180079038  pop     rsi
0x180079039  pop     rbp
0x18007903a  pop     rbx
0x18007903b  retn
```
