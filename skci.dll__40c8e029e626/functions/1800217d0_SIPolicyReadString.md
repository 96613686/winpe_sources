# SIPolicyReadString

- ea: `0x1800217d0`
- end: `0x180021893`
- name: `SIPolicyReadString`
- size: `195`
- prototype: `__int64 __fastcall(__int64 *, __int64)`
- caller_count: `8`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18001e674`
- `0x18001ef1c`
- `0x18001f33c`
- `0x18001f624`
- `0x18001fb08`
- `0x18001fc94`
- `0x18001fd18`
- `0x18001feec`

## callees

- `0x180021710`
- `0x180021748`
- `0x1800217d0`

## pseudocode

```c
__int64 __fastcall SIPolicyReadString(__int64 *a1, __int64 a2)
{
  __int64 result; // rax
  _QWORD *v5; // rcx
  int v6; // r11d
  unsigned __int64 v7; // rsi
  __int16 v8; // r11
  __int64 v9; // rcx
  _QWORD v10[3]; // [rsp+20h] [rbp-18h] BYREF
  unsigned int v11; // [rsp+50h] [rbp+18h] BYREF
  __int64 v12; // [rsp+58h] [rbp+20h] BYREF

  v12 = 0;
  v10[0] = 0;
  v11 = 0;
  result = SIPolicyReadPrimitive(a1, 4u, &v11);
  if ( (int)result >= 0 )
  {
    if ( v11 > 0xFFFE )
      return 3236495363LL;
    result = SIPolicyReadBytes(a1, v11, v10);
    if ( (int)result >= 0 )
    {
      v7 = (-v6 & 3) + 4LL;
      result = SIPolicyReadBytes(v5, v7, &v12);
      if ( (int)result >= 0 )
      {
        v9 = 0;
        while ( !*(_BYTE *)(v9 + v12) )
        {
          v9 = (unsigned int)(v9 + 1);
          if ( (unsigned int)v9 >= v7 )
          {
            *(_QWORD *)(a2 + 8) = v10[0];
            result = (unsigned int)result;
            *(_WORD *)a2 = v8;
            *(_WORD *)(a2 + 2) = v8;
            return result;
          }
        }
        return 3236495363LL;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800217d0  mov     rax, rsp
0x1800217d3  mov     [rax+8], rbx
0x1800217d7  mov     [rax+10h], rsi
0x1800217db  push    rdi
0x1800217dc  sub     rsp, 30h
0x1800217e0  mov     rbx, rdx
0x1800217e3  mov     qword ptr [rax+20h], 0
0x1800217eb  mov     edx, 4
0x1800217f0  mov     qword ptr [rax-18h], 0
0x1800217f8  lea     r8, [rax+18h]
0x1800217fc  mov     dword ptr [rax+18h], 0
0x180021803  mov     rdi, rcx
0x180021806  call    SIPolicyReadPrimitive
0x18002180b  test    eax, eax
0x18002180d  js      short loc_180021882
0x18002180f  mov     r11d, [rsp+38h+arg_10]
0x180021814  cmp     r11d, 0FFFEh
0x18002181b  ja      short loc_18002187D
0x18002181d  mov     edx, r11d
0x180021820  lea     r8, [rsp+38h+var_18]
0x180021825  mov     rcx, rdi
0x180021828  call    SIPolicyReadBytes
0x18002182d  test    eax, eax
0x18002182f  js      short loc_180021882
0x180021831  mov     esi, r11d
0x180021834  lea     r8, [rsp+38h+arg_18]
0x180021839  neg     esi
0x18002183b  and     esi, 3
0x18002183e  add     rsi, 4
0x180021842  mov     rdx, rsi
0x180021845  call    SIPolicyReadBytes
0x18002184a  mov     edx, eax
0x18002184c  test    eax, eax
0x18002184e  js      short loc_180021882
0x180021850  mov     r8, [rsp+38h+arg_18]
0x180021855  xor     ecx, ecx
0x180021857  cmp     byte ptr [rcx+r8], 0
0x18002185c  jnz     short loc_18002187D
0x18002185e  inc     ecx
0x180021860  mov     eax, ecx
0x180021862  cmp     rax, rsi
0x180021865  jb      short loc_180021857
0x180021867  mov     rax, [rsp+38h+var_18]
0x18002186c  mov     [rbx+8], rax
0x180021870  mov     eax, edx
0x180021872  mov     [rbx], r11w
0x180021876  mov     [rbx+2], r11w
0x18002187b  jmp     short loc_180021882
0x18002187d  mov     eax, 0C0E90003h
0x180021882  mov     rbx, [rsp+38h+arg_0]
0x180021887  mov     rsi, [rsp+38h+arg_8]
0x18002188c  add     rsp, 30h
0x180021890  pop     rdi
0x180021891  retn
```
