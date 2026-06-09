# FindIfEntry

- ea: `0x18001bc4c`
- end: `0x18001bcd8`
- name: `FindIfEntry`
- size: `140`
- prototype: ``
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x180011850`
- `0x180012800`
- `0x1800134c0`
- `0x180014580`
- `0x180014970`
- `0x1800155fc`
- `0x180016d00`
- `0x180017a44`
- `0x18001958c`
- `0x180019de0`
- `0x18001a360`
- `0x18001af20`

## callees

- `0x18001bc4c`

## pseudocode

```c
__int64 __fastcall FindIfEntry(__int64 **a1, unsigned int a2, unsigned int a3, _QWORD *a4)
{
  __int64 *v4; // r10
  unsigned int v5; // r11d
  unsigned int v8; // edx
  int v9; // ecx

  v4 = *a1;
  v5 = 0;
  *a4 = 0;
  if ( v4 != (__int64 *)a1 )
  {
    while ( 1 )
    {
      if ( *((_DWORD *)v4 + 4) >= a2 )
      {
        if ( *((_DWORD *)v4 + 4) > a2 )
        {
          *a4 = v4;
          return v5;
        }
        v8 = *((_DWORD *)v4 + 5);
        v9 = (unsigned __int8)v8 - (unsigned __int8)a3;
        if ( (unsigned __int8)v8 == (unsigned __int8)a3 )
        {
          v9 = (*((_DWORD *)v4 + 5) & 0xFF00) - (a3 & 0xFF00);
          if ( !v9 )
          {
            v9 = (v8 & 0xFF0000) - (a3 & 0xFF0000);
            if ( (v8 & 0xFF0000) == (a3 & 0xFF0000) )
              v9 = ((v8 >> 8) & 0xFF0000) - ((a3 >> 8) & 0xFF0000);
          }
        }
        if ( v9 >= 0 )
          break;
      }
      v4 = (__int64 *)*v4;
      if ( v4 == (__int64 *)a1 )
        return v5;
    }
    *a4 = v4;
    if ( v9 <= 0 )
      return 1;
  }
  return v5;
}

```

## disassembly

```asm
0x18001bc4c  push    rbx
0x18001bc4e  push    rsi
0x18001bc4f  push    rdi
0x18001bc50  mov     r10, [rcx]
0x18001bc53  xor     r11d, r11d
0x18001bc56  mov     [r9], r11
0x18001bc59  mov     edi, edx
0x18001bc5b  mov     rbx, rcx
0x18001bc5e  cmp     r10, rcx
0x18001bc61  jz      short loc_18001BCD1
0x18001bc63  mov     esi, 0FF0000h
0x18001bc68  cmp     [r10+10h], edi
0x18001bc6c  jb      short loc_18001BCB5
0x18001bc6e  ja      short loc_18001BCCE
0x18001bc70  mov     edx, [r10+14h]
0x18001bc74  movzx   ecx, dl
0x18001bc77  movzx   eax, r8b
0x18001bc7b  sub     ecx, eax
0x18001bc7d  jnz     short loc_18001BCB1
0x18001bc7f  mov     eax, r8d
0x18001bc82  mov     ecx, edx
0x18001bc84  and     eax, 0FF00h
0x18001bc89  and     ecx, 0FF00h
0x18001bc8f  sub     ecx, eax
0x18001bc91  jnz     short loc_18001BCB1
0x18001bc93  mov     ecx, edx
0x18001bc95  mov     eax, r8d
0x18001bc98  and     ecx, esi
0x18001bc9a  and     eax, esi
0x18001bc9c  sub     ecx, eax
0x18001bc9e  jnz     short loc_18001BCB1
0x18001bca0  mov     ecx, edx
0x18001bca2  mov     eax, r8d
0x18001bca5  shr     ecx, 8
0x18001bca8  shr     eax, 8
0x18001bcab  and     ecx, esi
0x18001bcad  and     eax, esi
0x18001bcaf  sub     ecx, eax
0x18001bcb1  test    ecx, ecx
0x18001bcb3  jns     short loc_18001BCBF
0x18001bcb5  mov     r10, [r10]
0x18001bcb8  cmp     r10, rbx
0x18001bcbb  jnz     short loc_18001BC68
0x18001bcbd  jmp     short loc_18001BCD1
0x18001bcbf  mov     [r9], r10
0x18001bcc2  test    ecx, ecx
0x18001bcc4  jg      short loc_18001BCD1
0x18001bcc6  mov     r11d, 1
0x18001bccc  jmp     short loc_18001BCD1
0x18001bcce  mov     [r9], r10
0x18001bcd1  mov     eax, r11d
0x18001bcd4  pop     rdi
0x18001bcd5  pop     rsi
0x18001bcd6  pop     rbx
0x18001bcd7  retn
```
