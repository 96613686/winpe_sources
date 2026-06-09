# CCorrAPOBase::CheckFormat(_UNCOMPRESSEDAUDIOFORMAT const *)

- ea: `0x180007f28`
- end: `0x180007fb8`
- name: `?CheckFormat@CCorrAPOBase@@IEAAJPEBU_UNCOMPRESSEDAUDIOFORMAT@@@Z`
- size: `144`
- prototype: `__int64 __fastcall(CCorrAPOBase *__hidden this, const struct _UNCOMPRESSEDAUDIOFORMAT *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180007e7c`

## callees

- `0x180007f28`
- `0x180007fc0`

## pseudocode

```c
__int64 __fastcall CCorrAPOBase::CheckFormat(CCorrAPOBase *this, const struct _UNCOMPRESSEDAUDIOFORMAT *a2)
{
  __int64 v2; // rax
  float fFramesPerSecond; // xmm0_4
  unsigned int v4; // r8d
  int v5; // r9d

  v2 = *(_QWORD *)&MEDIASUBTYPE_IEEE_FLOAT.Data1 - *(_QWORD *)&a2->guidFormatType.Data1;
  if ( *(_QWORD *)&MEDIASUBTYPE_IEEE_FLOAT.Data1 == *(_QWORD *)&a2->guidFormatType.Data1 )
    v2 = *(_QWORD *)MEDIASUBTYPE_IEEE_FLOAT.Data4 - *(_QWORD *)a2->guidFormatType.Data4;
  if ( !v2
    && a2->dwSamplesPerFrame - 1 <= 0xFFF
    && a2->dwBytesPerSampleContainer == 4
    && a2->dwValidBitsPerSample == 32
    && (fFramesPerSecond = a2->fFramesPerSecond, fFramesPerSecond <= 384000.0)
    && fFramesPerSecond >= 10.0
    && (unsigned int)RateSupported(this)
    && (v4 & 0x1F) == 0
    && v4 <= 8 * v5 )
  {
    return 8 * v5 != v4 ? 0x887D0009 : 0;
  }
  else
  {
    return 2289893385LL;
  }
}

```

## disassembly

```asm
0x180007f28  sub     rsp, 28h
0x180007f2c  mov     rax, qword ptr cs:MEDIASUBTYPE_IEEE_FLOAT.Data1
0x180007f33  sub     rax, [rdx]
0x180007f36  jnz     short loc_180007F43
0x180007f38  mov     rax, qword ptr cs:MEDIASUBTYPE_IEEE_FLOAT.Data4
0x180007f3f  sub     rax, [rdx+8]
0x180007f43  test    rax, rax
0x180007f46  jnz     short loc_180007F8C
0x180007f48  mov     eax, [rdx+10h]
0x180007f4b  dec     eax
0x180007f4d  cmp     eax, 0FFFh
0x180007f52  ja      short loc_180007F8C
0x180007f54  mov     r9d, [rdx+14h]
0x180007f58  cmp     r9d, 4
0x180007f5c  jnz     short loc_180007F8C
0x180007f5e  mov     r8d, [rdx+18h]
0x180007f62  cmp     r8d, 20h ; ' '
0x180007f66  jnz     short loc_180007F8C
0x180007f68  movss   xmm0, dword ptr [rdx+1Ch]
0x180007f6d  comiss  xmm0, cs:__real@48bb8000
0x180007f74  ja      short loc_180007F8C
0x180007f76  movss   xmm1, cs:__real@41200000
0x180007f7e  comiss  xmm1, xmm0
0x180007f81  ja      short loc_180007F8C
0x180007f83  call    RateSupported
0x180007f88  test    eax, eax
0x180007f8a  jnz     short loc_180007F96
0x180007f8c  mov     eax, 887D0009h
0x180007f91  add     rsp, 28h
0x180007f95  retn
0x180007f96  test    r8b, 1Fh
0x180007f9a  jnz     short loc_180007F8C
0x180007f9c  lea     eax, ds:0[r9*8]
0x180007fa4  cmp     r8d, eax
0x180007fa7  ja      short loc_180007F8C
0x180007fa9  sub     r8d, eax
0x180007fac  neg     r8d
0x180007faf  sbb     eax, eax
0x180007fb1  and     eax, 887D0009h
0x180007fb6  jmp     short loc_180007F91
```
