# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x140007024`
- end: `0x14000708f`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `107`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, unsigned __int16 *)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x140003c88`
- `0x140003ff4`
- `0x1400046f4`
- `0x140004c74`
- `0x140004df8`
- `0x140005b88`
- `0x140008500`
- `0x140024958`

## callees

- `0x140007024`

## pseudocode

```c
__int64 __fastcall StringCchCopyW(unsigned __int16 *a1, unsigned __int64 a2, unsigned __int16 *a3)
{
  unsigned __int16 *v3; // r9
  __int64 result; // rax
  __int64 v5; // rax

  v3 = a1;
  if ( !a2 )
    return 2147942487LL;
  if ( a2 <= 0x7FFFFFFF )
  {
    v5 = 2147483646;
    do
    {
      if ( !v5 )
        break;
      if ( !*a3 )
        break;
      *v3++ = *a3++;
      --v5;
      --a2;
    }
    while ( a2 );
    a1 = v3 - 1;
    if ( a2 )
      a1 = v3;
    result = a2 == 0 ? 0x8007007A : 0;
  }
  else
  {
    result = 2147942487LL;
  }
  *a1 = 0;
  return result;
}

```

## disassembly

```asm
0x140007024  xor     r10d, r10d
0x140007027  mov     r9, rcx
0x14000702a  test    rdx, rdx
0x14000702d  jz      short loc_140007080
0x14000702f  cmp     rdx, 7FFFFFFFh
0x140007036  jbe     short loc_14000703F
0x140007038  mov     eax, 80070057h
0x14000703d  jmp     short loc_14000708A
0x14000703f  mov     eax, 7FFFFFFEh
0x140007044  test    rax, rax
0x140007047  jz      short loc_140007067
0x140007049  movzx   ecx, word ptr [r8]
0x14000704d  test    cx, cx
0x140007050  jz      short loc_140007067
0x140007052  mov     [r9], cx
0x140007056  add     r8, 2
0x14000705a  add     r9, 2
0x14000705e  dec     rax
0x140007061  sub     rdx, 1
0x140007065  jnz     short loc_140007044
0x140007067  test    rdx, rdx
0x14000706a  lea     rcx, [r9-2]
0x14000706e  cmovnz  rcx, r9
0x140007072  neg     rdx
0x140007075  sbb     eax, eax
0x140007077  not     eax
0x140007079  and     eax, 8007007Ah
0x14000707e  jmp     short loc_14000708A
0x140007080  mov     eax, 80070057h
0x140007085  test    rdx, rdx
0x140007088  jz      short locret_14000708E
0x14000708a  mov     [rcx], r10w
0x14000708e  retn
```
