# ScCacheDeleteCache

- ea: `0x180037070`
- end: `0x18003711a`
- name: `ScCacheDeleteCache`
- size: `170`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180012d08`
- `0x180015728`
- `0x18002cb34`
- `0x18002e52c`

## callees

- `0x18000a408`
- `0x18000a590`
- `0x180013734`
- `0x180036e68`
- `0x180037070`

## pseudocode

```c
__int64 __fastcall ScCacheDeleteCache(struct _RTL_CRITICAL_SECTION *a1)
{
  __int64 v2; // rcx

  WppTraceIndent((__int64)a1, 0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids, WPP_pszIndent);
  }
  I_ServerCacheCleanup(a1);
  WppTraceIndent(v2, 1u);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      19,
      (unsigned int)WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids,
      WPP_pszIndent,
      0);
  }
  return 0;
}

```

## disassembly

```asm
0x180037070  mov     [rsp+arg_0], rbx
0x180037075  push    rdi
0x180037076  sub     rsp, 30h
0x18003707a  xor     edx, edx
0x18003707c  mov     rbx, rcx
0x18003707f  call    WppTraceIndent
0x180037084  mov     rcx, cs:WPP_GLOBAL_Control
0x18003708b  lea     rdi, WPP_GLOBAL_Control
0x180037092  cmp     rcx, rdi
0x180037095  jz      short loc_1800370BF
0x180037097  test    byte ptr [rcx+1Ch], 2
0x18003709b  jz      short loc_1800370BF
0x18003709d  cmp     byte ptr [rcx+19h], 5
0x1800370a1  jb      short loc_1800370BF
0x1800370a3  mov     r9, cs:WPP_pszIndent
0x1800370aa  lea     r8, WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids
0x1800370b1  mov     rcx, [rcx+10h]
0x1800370b5  mov     edx, 12h
0x1800370ba  call    WPP_SF_s
0x1800370bf  mov     rcx, rbx
0x1800370c2  call    I_ServerCacheCleanup
0x1800370c7  mov     edx, 1
0x1800370cc  call    WppTraceIndent
0x1800370d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800370d8  cmp     rcx, rdi
0x1800370db  jz      short loc_18003710D
0x1800370dd  test    byte ptr [rcx+1Ch], 2
0x1800370e1  jz      short loc_18003710D
0x1800370e3  cmp     byte ptr [rcx+19h], 5
0x1800370e7  jb      short loc_18003710D
0x1800370e9  mov     r9, cs:WPP_pszIndent
0x1800370f0  lea     r8, WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids
0x1800370f7  mov     rcx, [rcx+10h]
0x1800370fb  mov     edx, 13h
0x180037100  mov     [rsp+38h+var_18], 0
0x180037108  call    WPP_SF_sd
0x18003710d  mov     rbx, [rsp+38h+arg_0]
0x180037112  xor     eax, eax
0x180037114  add     rsp, 30h
0x180037118  pop     rdi
0x180037119  retn
```
