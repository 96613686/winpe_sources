# TpmUserAuthFailureData::AgeAuthFailureList(unsigned __int64,ulong)

- ea: `0x140028dec`
- end: `0x140028eb0`
- name: `?AgeAuthFailureList@TpmUserAuthFailureData@@QEAAK_KK@Z`
- size: `196`
- prototype: `unsigned int __fastcall(TpmUserAuthFailureData *__hidden this, unsigned __int64, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140022270`
- `0x140022440`

## callees

- `0x140028dec`
- `0x140028eb8`
- `0x140039b40`

## import_xrefs

- `ntoskrnl!memmove_s` at `0x140028e75`
- `ntoskrnl!memmove_s` at `0x140028e75`

## pseudocode

```c
__int64 __fastcall TpmUserAuthFailureData::AgeAuthFailureList(TpmUserAuthFailureData *this, __int64 a2, int a3)
{
  int v3; // r9d
  unsigned int v6; // ebp
  int i; // edi
  __int64 v8; // r10

  v3 = *((_DWORD *)this + 5);
  if ( !v3 )
    return 0;
  v6 = 0;
  for ( i = v3 - 1; i >= 0; --i )
  {
    v8 = *((_QWORD *)this + 1);
    if ( a2 - *(_QWORD *)(v8 + 8LL * i) > 10000 * (unsigned __int64)(unsigned int)(1000 * a3) )
    {
      if ( i == v3 - 1 )
      {
        v6 = *((_DWORD *)this + 5);
        TpmUserAuthFailureData::ClearHistory(this);
      }
      else
      {
        memmove_s(
          *((void **)this + 1),
          8LL * *((unsigned int *)this + 4),
          (const void *)(v8 + 8 + 8LL * i),
          8LL * (unsigned int)(~i + v3));
        v6 = i + 1;
        memset((void *)(*((_QWORD *)this + 1) + 8LL * (unsigned int)(~i + *((_DWORD *)this + 5))), 0, 8LL * (i + 1));
        *((_DWORD *)this + 5) -= i + 1;
      }
      return v6;
    }
  }
  return v6;
}

```

## disassembly

```asm
0x140028dec  push    rbx
0x140028dee  push    rbp
0x140028def  push    rsi
0x140028df0  push    rdi
0x140028df1  push    r14
0x140028df3  sub     rsp, 20h
0x140028df7  mov     r9d, [rcx+14h]
0x140028dfb  mov     r11d, r8d
0x140028dfe  mov     rbx, rdx
0x140028e01  mov     rsi, rcx
0x140028e04  test    r9d, r9d
0x140028e07  jnz     short loc_140028E10
0x140028e09  xor     eax, eax
0x140028e0b  jmp     loc_140028EA4
0x140028e10  lea     r8d, [r9-1]
0x140028e14  xor     ebp, ebp
0x140028e16  mov     edi, r8d
0x140028e19  test    edi, edi
0x140028e1b  js      loc_140028EA2
0x140028e21  mov     r10, [rsi+8]
0x140028e25  mov     rax, rbx
0x140028e28  imul    ecx, r11d, 3E8h
0x140028e2f  movsxd  r14, edi
0x140028e32  sub     rax, [r10+r14*8]
0x140028e36  imul    rdx, rcx, 2710h
0x140028e3d  cmp     rax, rdx
0x140028e40  ja      short loc_140028E46
0x140028e42  dec     edi
0x140028e44  jmp     short loc_140028E19
0x140028e46  cmp     edi, r8d
0x140028e49  jnz     short loc_140028E58
0x140028e4b  mov     rcx, rsi; this
0x140028e4e  mov     ebp, r9d
0x140028e51  call    ?ClearHistory@TpmUserAuthFailureData@@QEAAXXZ; TpmUserAuthFailureData::ClearHistory(void)
0x140028e56  jmp     short loc_140028EA2
0x140028e58  mov     edx, [rsi+10h]
0x140028e5b  lea     r8, [r10+8]
0x140028e5f  mov     ebx, edi
0x140028e61  shl     rdx, 3; DstSize
0x140028e65  not     ebx
0x140028e67  lea     r8, [r8+r14*8]; Src
0x140028e6b  add     r9d, ebx
0x140028e6e  mov     rcx, r10; void *
0x140028e71  shl     r9, 3; MaxCount
0x140028e75  call    cs:__imp_memmove_s
0x140028e7c  nop     dword ptr [rax+rax+00h]
0x140028e81  mov     edx, [rsi+14h]
0x140028e84  lea     ebp, [rdi+1]
0x140028e87  mov     rcx, [rsi+8]
0x140028e8b  add     edx, ebx
0x140028e8d  movsxd  r8, ebp
0x140028e90  shl     r8, 3; Size
0x140028e94  lea     rcx, [rcx+rdx*8]; void *
0x140028e98  xor     edx, edx; Val
0x140028e9a  call    memset
0x140028e9f  sub     [rsi+14h], ebp
0x140028ea2  mov     eax, ebp
0x140028ea4  add     rsp, 20h
0x140028ea8  pop     r14
0x140028eaa  pop     rdi
0x140028eab  pop     rsi
0x140028eac  pop     rbp
0x140028ead  pop     rbx
0x140028eae  retn
```
