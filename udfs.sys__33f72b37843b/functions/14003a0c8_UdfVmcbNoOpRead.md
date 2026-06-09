# UdfVmcbNoOpRead

- ea: `0x14003a0c8`
- end: `0x14003a180`
- name: `UdfVmcbNoOpRead`
- size: `184`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140030818`
- `0x1400473c0`

## callees

- `0x14000ca10`
- `0x14003a0c8`
- `0x14003d810`

## pseudocode

```c
char __fastcall UdfVmcbNoOpRead(__int64 a1, __int64 a2, int a3, unsigned int a4, signed __int32 a5)
{
  signed __int32 v7; // r9d
  __int64 i; // rdx
  char result; // al

  v7 = a5;
  if ( !a5 )
    v7 = ~*(_DWORD *)(a2 + 1276)
       & UdfLookupPsnOfExtent(
           a1,
           a2,
           *(_WORD *)((-(__int64)(a3 != 0) & 0xFFFFFFFFFFFFFFFCuLL) + *(_QWORD *)(a2 + 16) + 88),
           a4,
           *(_DWORD *)(a2 + 68));
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    if ( (unsigned int)i >= 4 )
      return 0;
    if ( v7 == _InterlockedCompareExchange((volatile signed __int32 *)(a2 + 4 * i + 1384), -1, v7) )
      break;
  }
  if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x400000) != 0 )
  {
    WPP_SF_d(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL), 35, WPP_c4c254f43dbb37edeabcdd77880d9f11_Traceguids);
  }
  result = 1;
  *(_DWORD *)(*(_QWORD *)(a1 + 48) + 28LL) &= ~0x80000u;
  return result;
}

```

## disassembly

```asm
0x14003a0c8  mov     [rsp+arg_0], rbx
0x14003a0cd  push    rdi
0x14003a0ce  sub     rsp, 30h
0x14003a0d2  mov     r11d, r9d
0x14003a0d5  mov     rbx, rdx
0x14003a0d8  mov     r9d, [rsp+38h+arg_20]
0x14003a0dd  mov     rdi, rcx
0x14003a0e0  test    r9d, r9d
0x14003a0e3  jnz     short loc_14003A116
0x14003a0e5  mov     eax, [rdx+44h]
0x14003a0e8  neg     r8d
0x14003a0eb  mov     r8, [rdx+10h]
0x14003a0ef  mov     r9d, r11d
0x14003a0f2  sbb     r10, r10
0x14003a0f5  mov     [rsp+38h+var_18], eax
0x14003a0f9  and     r10, 0FFFFFFFFFFFFFFFCh
0x14003a0fd  movzx   r8d, word ptr [r10+r8+58h]
0x14003a103  call    UdfLookupPsnOfExtent
0x14003a108  mov     ecx, [rbx+4FCh]
0x14003a10e  mov     r9d, eax
0x14003a111  not     ecx
0x14003a113  and     r9d, ecx
0x14003a116  xor     edx, edx
0x14003a118  cmp     edx, 4
0x14003a11b  jnb     short loc_14003A172
0x14003a11d  or      r8d, 0FFFFFFFFh
0x14003a121  mov     eax, r9d
0x14003a124  lock cmpxchg [rbx+rdx*4+568h], r8d
0x14003a12e  jz      short loc_14003A134
0x14003a130  inc     edx
0x14003a132  jmp     short loc_14003A118
0x14003a134  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a13b  lea     rax, WPP_GLOBAL_Control
0x14003a142  cmp     rcx, rax
0x14003a145  jz      short loc_14003A165
0x14003a147  test    dword ptr [rcx+2Ch], 400000h
0x14003a14e  jz      short loc_14003A165
0x14003a150  mov     rcx, [rcx+18h]
0x14003a154  lea     r8, WPP_c4c254f43dbb37edeabcdd77880d9f11_Traceguids
0x14003a15b  mov     edx, 23h ; '#'
0x14003a160  call    WPP_SF_d
0x14003a165  mov     rcx, [rdi+30h]
0x14003a169  mov     al, 1
0x14003a16b  btr     dword ptr [rcx+1Ch], 13h
0x14003a170  jmp     short loc_14003A174
0x14003a172  xor     al, al
0x14003a174  mov     rbx, [rsp+38h+arg_0]
0x14003a179  add     rsp, 30h
0x14003a17d  pop     rdi
0x14003a17e  retn
```
