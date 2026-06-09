# FrameObfuscator::ProcessMask(uchar *,ulong)

- ea: `0x18000d890`
- end: `0x18000d94e`
- name: `?ProcessMask@FrameObfuscator@@AEAAXPEAEK@Z`
- size: `190`
- prototype: `void __fastcall(FrameObfuscator *__hidden this, unsigned __int8 *, unsigned int)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000bb2c`
- `0x18000c6a8`
- `0x18000d648`
- `0x18000d6f8`

## callees

- `0x18000d890`

## pseudocode

```c
void __fastcall FrameObfuscator::ProcessMask(FrameObfuscator *this, unsigned __int8 *a2, unsigned int a3)
{
  __int64 v3; // r11
  unsigned __int8 *v4; // r10
  __int64 v5; // rax
  unsigned __int8 *v6; // r11

  if ( *(_DWORD *)this && a3 )
  {
    v3 = a3;
    v4 = &a2[a3];
    if ( a3 <= 8 )
    {
      while ( a2 < v4 )
        *a2++ ^= *((_BYTE *)this + ((*((_DWORD *)this + 1))++ & 3));
    }
    else
    {
      v5 = (unsigned __int8)a2 & 3;
      if ( a3 >= (unsigned __int64)(4 - v5) )
        v3 = 4 - v5;
      v6 = &a2[v3];
      while ( a2 < v6 )
        *a2++ ^= *((_BYTE *)this + ((*((_DWORD *)this + 1))++ & 3));
      *(_DWORD *)this = __ROR4__(*(_DWORD *)this, 8 * *((_DWORD *)this + 1));
      *((_DWORD *)this + 1) = 0;
      while ( (unsigned __int64)a2 < ((unsigned int)v4 & 0xFFFFFFFC) )
      {
        *(_DWORD *)a2 ^= *(_DWORD *)this;
        a2 += 4;
      }
      while ( a2 < v4 )
        *a2++ ^= *((_BYTE *)this + ((*((_DWORD *)this + 1))++ & 3));
    }
  }
}

```

## disassembly

```asm
0x18000d890  cmp     dword ptr [rcx], 0
0x18000d893  mov     r9, rcx
0x18000d896  jz      locret_18000D94D
0x18000d89c  test    r8d, r8d
0x18000d89f  jz      locret_18000D94D
0x18000d8a5  mov     r11d, r8d
0x18000d8a8  lea     r10, [r11+rdx]
0x18000d8ac  cmp     r8d, 8
0x18000d8b0  jbe     loc_18000D948
0x18000d8b6  mov     rax, rdx
0x18000d8b9  mov     ecx, 4
0x18000d8be  and     eax, 3
0x18000d8c1  sub     rcx, rax
0x18000d8c4  cmp     r11, rcx
0x18000d8c7  cmovnb  r11, rcx
0x18000d8cb  add     r11, rdx
0x18000d8ce  jmp     short loc_18000D8E4
0x18000d8d0  mov     eax, [r9+4]
0x18000d8d4  and     eax, 3
0x18000d8d7  mov     al, [rax+r9]
0x18000d8db  xor     [rdx], al
0x18000d8dd  inc     dword ptr [r9+4]
0x18000d8e1  inc     rdx
0x18000d8e4  cmp     rdx, r11
0x18000d8e7  jb      short loc_18000D8D0
0x18000d8e9  mov     ecx, [r9+4]
0x18000d8ed  mov     eax, [r9]
0x18000d8f0  shl     ecx, 3
0x18000d8f3  ror     eax, cl
0x18000d8f5  mov     rcx, r10
0x18000d8f8  mov     [r9], eax
0x18000d8fb  mov     eax, 0FFFFFFFCh
0x18000d900  and     rcx, rax
0x18000d903  mov     dword ptr [r9+4], 0
0x18000d90b  jmp     short loc_18000D916
0x18000d90d  mov     eax, [r9]
0x18000d910  xor     [rdx], eax
0x18000d912  add     rdx, 4
0x18000d916  cmp     rdx, rcx
0x18000d919  jb      short loc_18000D90D
0x18000d91b  jmp     short loc_18000D931
0x18000d91d  mov     eax, [r9+4]
0x18000d921  and     eax, 3
0x18000d924  mov     al, [rax+r9]
0x18000d928  xor     [rdx], al
0x18000d92a  inc     dword ptr [r9+4]
0x18000d92e  inc     rdx
0x18000d931  cmp     rdx, r10
0x18000d934  jb      short loc_18000D91D
0x18000d936  retn
0x18000d937  mov     eax, [rcx+4]
0x18000d93a  and     eax, 3
0x18000d93d  mov     al, [rax+rcx]
0x18000d940  xor     [rdx], al
0x18000d942  inc     dword ptr [rcx+4]
0x18000d945  inc     rdx
0x18000d948  cmp     rdx, r10
0x18000d94b  jb      short loc_18000D937
0x18000d94d  retn
```
