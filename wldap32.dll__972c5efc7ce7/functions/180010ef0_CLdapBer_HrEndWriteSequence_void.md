# CLdapBer::HrEndWriteSequence(void)

- ea: `0x180010ef0`
- end: `0x180011015`
- name: `?HrEndWriteSequence@CLdapBer@@QEAAKXZ`
- size: `293`
- prototype: `unsigned int __fastcall(CLdapBer *__hidden this)`
- caller_count: `22`
- callee_count: `1`
- tags: ``

## callers

- `0x18000e0d0`
- `0x1800112b0`
- `0x180012400`
- `0x180012ab0`
- `0x180013610`
- `0x1800164a0`
- `0x18001f96c`
- `0x1800230a0`
- `0x18002bac0`
- `0x18002d1a8`
- `0x18002dbac`
- `0x180038678`
- `0x180039cd0`
- `0x18003a274`
- `0x18003c5bc`
- `0x18003e508`
- `0x18003f138`
- `0x1800400e4`
- `0x18004404c`
- `0x180047254`
- `0x1800491d4`
- `0x18004a984`

## callees

- `0x180010ef0`

## pseudocode

```c
__int64 __fastcall CLdapBer::HrEndWriteSequence(CLdapBer *this)
{
  int v2; // eax
  int v3; // r11d
  __int64 v4; // rax
  __int64 v5; // rcx
  __int64 v6; // r10
  int v7; // edx
  unsigned int v8; // r9d
  __int64 result; // rax

  if ( !*((_DWORD *)this + 216) )
  {
    v2 = *((_DWORD *)this + 8);
    if ( v2 )
    {
      v3 = *((_DWORD *)this + 1);
      v4 = (unsigned int)(v2 - 1);
      *((_DWORD *)this + 8) = v4;
      v5 = (unsigned int)v4;
      v4 *= 2;
      v6 = *((unsigned int *)this + 2 * v4 + 9);
      v7 = *((_DWORD *)this + 2 * v4 + 10);
      v8 = v3 - v7 - v6;
      *((_DWORD *)this + 210) = *((_DWORD *)this + 2 * v4 + 11);
      *((_DWORD *)this + 209) = *((_DWORD *)this + 4 * v5 + 12);
      *((_DWORD *)this + 1) = v6;
      if ( v8 <= 0x7F && v7 == -1 || v7 == 1 )
      {
        *(_BYTE *)(v6 + *((_QWORD *)this + 2)) = v8;
      }
      else
      {
        if ( v8 <= 0x7FFF && v7 == -1 || v7 == 3 )
        {
          *(_BYTE *)(v6 + *((_QWORD *)this + 2)) = -126;
        }
        else
        {
          if ( (v7 != -1 || v8 >= 0x7FFFFFFF) && v7 != 5 )
          {
            result = 2147942487LL;
            goto LABEL_7;
          }
          *(_BYTE *)(v6 + *((_QWORD *)this + 2)) = -124;
          *(_BYTE *)((unsigned int)++*((_DWORD *)this + 1) + *((_QWORD *)this + 2)) = HIBYTE(v8);
          *(_BYTE *)((unsigned int)++*((_DWORD *)this + 1) + *((_QWORD *)this + 2)) = BYTE2(v8);
        }
        *(_BYTE *)((unsigned int)++*((_DWORD *)this + 1) + *((_QWORD *)this + 2)) = BYTE1(v8);
        *(_BYTE *)((unsigned int)++*((_DWORD *)this + 1) + *((_QWORD *)this + 2)) = v8;
      }
      result = 0;
LABEL_7:
      *((_DWORD *)this + 1) = v3;
      return result;
    }
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x180010ef0  cmp     dword ptr [rcx+360h], 0
0x180010ef7  mov     r8, rcx
0x180010efa  jnz     loc_180010FF9
0x180010f00  mov     eax, [rcx+20h]
0x180010f03  test    eax, eax
0x180010f05  jz      loc_180010FF9
0x180010f0b  mov     r11d, [r8+4]
0x180010f0f  dec     eax
0x180010f11  mov     [rcx+20h], eax
0x180010f14  mov     r9d, r11d
0x180010f17  mov     ecx, eax
0x180010f19  add     rax, rax
0x180010f1c  mov     r10d, [r8+rax*8+24h]
0x180010f21  mov     edx, [r8+rax*8+28h]
0x180010f26  sub     r9d, edx
0x180010f29  mov     eax, [r8+rax*8+2Ch]
0x180010f2e  sub     r9d, r10d
0x180010f31  mov     [r8+348h], eax
0x180010f38  lea     rax, [rcx+3]
0x180010f3c  add     rax, rax
0x180010f3f  mov     eax, [r8+rax*8]
0x180010f43  mov     [r8+344h], eax
0x180010f4a  or      eax, 0FFFFFFFFh
0x180010f4d  mov     [r8+4], r10d
0x180010f51  cmp     r9d, 7Fh
0x180010f55  ja      short loc_180010F6B
0x180010f57  cmp     edx, eax
0x180010f59  jnz     short loc_180010F6B
0x180010f5b  mov     rax, [r8+10h]
0x180010f5f  mov     [r10+rax], r9b
0x180010f63  xor     eax, eax
0x180010f65  mov     [r8+4], r11d
0x180010f69  retn
0x180010f6b  cmp     edx, 1
0x180010f6e  jz      short loc_180010F5B
0x180010f70  cmp     r9d, 7FFFh
0x180010f77  ja      short loc_180010F81
0x180010f79  cmp     edx, eax
0x180010f7b  jz      loc_18001100A
0x180010f81  cmp     edx, 3
0x180010f84  jz      loc_18001100A
0x180010f8a  cmp     edx, eax
0x180010f8c  jnz     short loc_180010F97
0x180010f8e  cmp     r9d, 7FFFFFFFh
0x180010f95  jb      short loc_180010F9C
0x180010f97  cmp     edx, 5
0x180010f9a  jnz     short loc_180011000
0x180010f9c  mov     rax, [r8+10h]
0x180010fa0  mov     ecx, r9d
0x180010fa3  shr     ecx, 18h
0x180010fa6  mov     byte ptr [r10+rax], 84h
0x180010fab  inc     dword ptr [r8+4]
0x180010faf  mov     edx, [r8+4]
0x180010fb3  mov     rax, [r8+10h]
0x180010fb7  mov     [rdx+rax], cl
0x180010fba  mov     ecx, r9d
0x180010fbd  inc     dword ptr [r8+4]
0x180010fc1  mov     edx, [r8+4]
0x180010fc5  mov     rax, [r8+10h]
0x180010fc9  shr     ecx, 10h
0x180010fcc  mov     [rdx+rax], cl
0x180010fcf  inc     dword ptr [r8+4]
0x180010fd3  mov     ecx, r9d
0x180010fd6  mov     edx, [r8+4]
0x180010fda  mov     rax, [r8+10h]
0x180010fde  shr     ecx, 8
0x180010fe1  mov     [rdx+rax], cl
0x180010fe4  inc     dword ptr [r8+4]
0x180010fe8  mov     ecx, [r8+4]
0x180010fec  mov     rax, [r8+10h]
0x180010ff0  mov     [rcx+rax], r9b
0x180010ff4  jmp     loc_180010F63
0x180010ff9  mov     eax, 80070057h
0x180010ffe  retn
0x180011000  mov     eax, 80070057h
0x180011005  jmp     loc_180010F65
0x18001100a  mov     rax, [r8+10h]
0x18001100e  mov     byte ptr [r10+rax], 82h
0x180011013  jmp     short loc_180010FCF
```
