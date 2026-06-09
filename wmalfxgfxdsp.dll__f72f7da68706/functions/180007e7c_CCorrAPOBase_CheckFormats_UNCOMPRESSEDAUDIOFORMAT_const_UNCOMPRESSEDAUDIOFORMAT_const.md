# CCorrAPOBase::CheckFormats(_UNCOMPRESSEDAUDIOFORMAT const *,_UNCOMPRESSEDAUDIOFORMAT const *)

- ea: `0x180007e7c`
- end: `0x180007f22`
- name: `?CheckFormats@CCorrAPOBase@@IEAAJPEBU_UNCOMPRESSEDAUDIOFORMAT@@0@Z`
- size: `166`
- prototype: `int(CCorrAPOBase *__hidden this, const struct _UNCOMPRESSEDAUDIOFORMAT *, const struct _UNCOMPRESSEDAUDIOFORMAT *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180006ca0`

## callees

- `0x180007cf8`
- `0x180007e7c`
- `0x180007f28`

## pseudocode

```c
__int64 __fastcall CCorrAPOBase::CheckFormats(
        CCorrAPOBase *this,
        const struct _UNCOMPRESSEDAUDIOFORMAT *a2,
        const struct _UNCOMPRESSEDAUDIOFORMAT *a3)
{
  const struct _UNCOMPRESSEDAUDIOFORMAT *v3; // r10
  const struct _UNCOMPRESSEDAUDIOFORMAT *v4; // r11
  __int64 result; // rax
  DWORD dwSamplesPerFrame; // esi
  DWORD dwChannelMask; // edi
  DWORD v9; // ebp
  DWORD v10; // ebx

  v3 = a3;
  v4 = a2;
  if ( !a2 || (result = CCorrAPOBase::CheckFormat(this, a2), (int)result >= 0) )
  {
    if ( !v3 || (result = CCorrAPOBase::CheckFormat(this, v3), (int)result >= 0) )
    {
      if ( !v4 || !v3 )
        return 0;
      if ( v4->fFramesPerSecond == v3->fFramesPerSecond )
      {
        dwSamplesPerFrame = v3->dwSamplesPerFrame;
        dwChannelMask = v4->dwChannelMask;
        v9 = v4->dwSamplesPerFrame;
        v10 = v3->dwChannelMask;
        if ( (unsigned int)CCorrAPOBase::ChannelMaskQuality(this, v9, dwChannelMask, dwSamplesPerFrame, v10) )
        {
          if ( !*((_DWORD *)this + 36) )
            return 0;
          if ( v9 == dwSamplesPerFrame )
          {
            if ( dwChannelMask != v10 && dwChannelMask )
              return v10 != 0 ? 0x887D0009 : 0;
            return 0;
          }
        }
      }
      return 2289893385LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180007e7c  push    rbx
0x180007e7e  push    rbp
0x180007e7f  push    rsi
0x180007e80  push    rdi
0x180007e81  push    r14
0x180007e83  sub     rsp, 30h
0x180007e87  mov     r10, r8
0x180007e8a  mov     r11, rdx
0x180007e8d  mov     r14, rcx
0x180007e90  test    rdx, rdx
0x180007e93  jz      short loc_180007E9E
0x180007e95  call    ?CheckFormat@CCorrAPOBase@@IEAAJPEBU_UNCOMPRESSEDAUDIOFORMAT@@@Z; CCorrAPOBase::CheckFormat(_UNCOMPRESSEDAUDIOFORMAT const *)
0x180007e9a  test    eax, eax
0x180007e9c  js      short loc_180007EF9
0x180007e9e  test    r10, r10
0x180007ea1  jz      short loc_180007EAF
0x180007ea3  mov     rdx, r10; struct _UNCOMPRESSEDAUDIOFORMAT *
0x180007ea6  call    ?CheckFormat@CCorrAPOBase@@IEAAJPEBU_UNCOMPRESSEDAUDIOFORMAT@@@Z; CCorrAPOBase::CheckFormat(_UNCOMPRESSEDAUDIOFORMAT const *)
0x180007eab  test    eax, eax
0x180007ead  js      short loc_180007EF9
0x180007eaf  test    r11, r11
0x180007eb2  jz      short loc_180007EF7
0x180007eb4  test    r10, r10
0x180007eb7  jz      short loc_180007EF7
0x180007eb9  movss   xmm0, dword ptr [r11+1Ch]
0x180007ebf  ucomiss xmm0, dword ptr [r10+1Ch]
0x180007ec4  jp      short loc_180007F04
0x180007ec6  jnz     short loc_180007F04
0x180007ec8  mov     esi, [r10+10h]
0x180007ecc  mov     r9d, esi
0x180007ecf  mov     edi, [r11+20h]
0x180007ed3  mov     r8d, edi
0x180007ed6  mov     ebp, [r11+10h]
0x180007eda  mov     edx, ebp
0x180007edc  mov     ebx, [r10+20h]
0x180007ee0  mov     [rsp+58h+var_38], ebx
0x180007ee4  call    ?ChannelMaskQuality@CCorrAPOBase@@IEAA?AW4CHANNELMASKQUALITY@@KKKK@Z; CCorrAPOBase::ChannelMaskQuality(ulong,ulong,ulong,ulong)
0x180007ee9  test    eax, eax
0x180007eeb  jz      short loc_180007F04
0x180007eed  cmp     dword ptr [r14+90h], 0
0x180007ef5  jnz     short loc_180007F0B
0x180007ef7  xor     eax, eax
0x180007ef9  add     rsp, 30h
0x180007efd  pop     r14
0x180007eff  pop     rdi
0x180007f00  pop     rsi
0x180007f01  pop     rbp
0x180007f02  pop     rbx
0x180007f03  retn
0x180007f04  mov     eax, 887D0009h
0x180007f09  jmp     short loc_180007EF9
0x180007f0b  cmp     ebp, esi
0x180007f0d  jnz     short loc_180007F04
0x180007f0f  cmp     edi, ebx
0x180007f11  jz      short loc_180007EF7
0x180007f13  test    edi, edi
0x180007f15  jz      short loc_180007EF7
0x180007f17  neg     ebx
0x180007f19  sbb     eax, eax
0x180007f1b  and     eax, 887D0009h
0x180007f20  jmp     short loc_180007EF9
```
