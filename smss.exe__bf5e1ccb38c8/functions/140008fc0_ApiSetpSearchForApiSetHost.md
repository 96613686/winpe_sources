# ApiSetpSearchForApiSetHost

- ea: `0x140008fc0`
- end: `0x140009071`
- name: `ApiSetpSearchForApiSetHost`
- size: `177`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400080c0`

## callees

- `0x140008fc0`

## import_xrefs

- `ntdll!RtlCompareUnicodeStrings` at `0x140009033`
- `ntdll!RtlCompareUnicodeStrings` at `0x140009033`

## pseudocode

```c
__int64 __fastcall ApiSetpSearchForApiSetHost(__int64 a1, const WCHAR *a2, unsigned __int16 a3, __int64 a4)
{
  __int64 v5; // rsi
  int v6; // ebx
  SIZE_T v7; // r12
  int v10; // edi
  int v11; // r15d
  __int64 v12; // rax
  LONG v13; // eax
  __int64 v15; // [rsp+60h] [rbp+8h]

  v5 = a4 + *(unsigned int *)(a1 + 16);
  v6 = *(_DWORD *)(a1 + 20) - 1;
  v7 = a3;
  v10 = 1;
  while ( v10 <= v6 )
  {
    v11 = (v10 + v6) >> 1;
    v12 = a4 + *(unsigned int *)(a1 + 16) + 20LL * v11;
    v15 = v12;
    v13 = RtlCompareUnicodeStrings(
            a2,
            v7,
            (PCWCH)(a4 + *(unsigned int *)(v12 + 4)),
            (unsigned __int64)*(unsigned int *)(v12 + 8) >> 1,
            1u);
    if ( v13 >= 0 )
    {
      if ( v13 <= 0 )
        return v15;
      v10 = v11 + 1;
    }
    else
    {
      v6 = v11 - 1;
    }
  }
  return v5;
}

```

## disassembly

```asm
0x140008fc0  mov     [rsp+arg_10], rbx
0x140008fc5  mov     [rsp+arg_18], rbp
0x140008fca  push    rsi
0x140008fcb  push    rdi
0x140008fcc  push    r12
0x140008fce  push    r13
0x140008fd0  push    r14
0x140008fd2  sub     rsp, 30h
0x140008fd6  mov     esi, [rcx+10h]
0x140008fd9  mov     r14, r9
0x140008fdc  mov     ebx, [rcx+14h]
0x140008fdf  add     rsi, r9
0x140008fe2  dec     ebx
0x140008fe4  movzx   r12d, r8w
0x140008fe8  mov     r13, rdx
0x140008feb  mov     [rsp+58h+arg_8], r15
0x140008ff0  mov     rbp, rcx
0x140008ff3  mov     edi, 1
0x140008ff8  cmp     edi, ebx
0x140008ffa  jg      short loc_140009052
0x140008ffc  mov     ecx, [rbp+10h]
0x140008fff  lea     r15d, [rdi+rbx]
0x140009003  add     rcx, r14
0x140009006  sar     r15d, 1
0x140009009  movsxd  rax, r15d
0x14000900c  mov     [rsp+58h+CaseInSensitive], 1; CaseInSensitive
0x140009011  lea     rdx, [rax+rax*4]
0x140009015  mov     r9d, [rcx+rdx*4+8]
0x14000901a  lea     rax, [rcx+rdx*4]
0x14000901e  mov     r8d, [rax+4]
0x140009022  mov     rdx, r12; String1Length
0x140009025  shr     r9, 1; String2Length
0x140009028  add     r8, r14; String2
0x14000902b  mov     rcx, r13; String1
0x14000902e  mov     [rsp+58h+arg_0], rax
0x140009033  call    cs:__imp_RtlCompareUnicodeStrings
0x140009039  test    eax, eax
0x14000903b  jns     short loc_140009043
0x14000903d  lea     ebx, [r15-1]
0x140009041  jmp     short loc_140008FF8
0x140009043  jle     short loc_14000904B
0x140009045  lea     edi, [r15+1]
0x140009049  jmp     short loc_140008FF8
0x14000904b  mov     rax, [rsp+58h+arg_0]
0x140009050  jmp     short loc_140009055
0x140009052  mov     rax, rsi
0x140009055  mov     r15, [rsp+58h+arg_8]
0x14000905a  mov     rbx, [rsp+58h+arg_10]
0x14000905f  mov     rbp, [rsp+58h+arg_18]
0x140009064  add     rsp, 30h
0x140009068  pop     r14
0x14000906a  pop     r13
0x14000906c  pop     r12
0x14000906e  pop     rdi
0x14000906f  pop     rsi
0x140009070  retn
```
