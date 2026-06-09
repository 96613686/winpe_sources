# StringCchCatW(ushort *,unsigned __int64,ushort const *)

- ea: `0x140006204`
- end: `0x1400062ad`
- name: `?StringCchCatW@@YAJPEAG_KPEBG@Z`
- size: `169`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, unsigned __int16 *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140003ffc`
- `0x1400064cc`
- `0x140007b40`

## callees

- `0x140006204`

## pseudocode

```c
__int64 __fastcall StringCchCatW(unsigned __int16 *a1, __int64 a2, unsigned __int16 *a3)
{
  __int64 v3; // r10
  unsigned __int16 *v4; // rax
  unsigned int v5; // edx
  __int64 v6; // r11
  unsigned __int16 *v7; // rax
  __int64 v8; // rcx
  __int64 v9; // r9
  unsigned __int16 *v10; // rcx

  v3 = 260;
  v4 = a1;
  do
  {
    if ( !*v4 )
      break;
    ++v4;
    --v3;
  }
  while ( v3 );
  v5 = v3 == 0 ? 0x80070057 : 0;
  v6 = (260 - v3) & -(__int64)(v3 != 0);
  if ( v3 )
  {
    v7 = &a1[v6];
    v8 = 2147483646;
    v9 = 260 - v6;
    if ( 260 != v6 )
    {
      do
      {
        if ( !v8 )
          break;
        if ( !*a3 )
          break;
        *v7++ = *a3++;
        --v8;
        --v9;
      }
      while ( v9 );
    }
    v10 = v7 - 1;
    if ( v9 )
      v10 = v7;
    v5 = v9 == 0 ? 0x8007007A : 0;
    *v10 = 0;
  }
  return v5;
}

```

## disassembly

```asm
0x140006204  mov     [rsp+arg_0], rbx
0x140006209  mov     [rsp+arg_8], rdi
0x14000620e  mov     r9d, 104h
0x140006214  mov     rbx, rcx
0x140006217  mov     r10d, r9d
0x14000621a  mov     rax, rcx
0x14000621d  xor     edi, edi
0x14000621f  cmp     [rax], di
0x140006222  jz      short loc_14000622E
0x140006224  add     rax, 2
0x140006228  sub     r10, 1
0x14000622c  jnz     short loc_14000621F
0x14000622e  mov     rax, r10
0x140006231  mov     rcx, r9
0x140006234  neg     rax
0x140006237  mov     rax, r10
0x14000623a  sbb     edx, edx
0x14000623c  sub     rcx, r10
0x14000623f  not     edx
0x140006241  and     edx, 80070057h
0x140006247  neg     rax
0x14000624a  sbb     r11, r11
0x14000624d  and     r11, rcx
0x140006250  test    r10, r10
0x140006253  jz      short loc_1400062A0
0x140006255  lea     rax, [rbx+r11*2]
0x140006259  mov     ecx, 7FFFFFFEh
0x14000625e  sub     r9, r11
0x140006261  jz      short loc_140006285
0x140006263  test    rcx, rcx
0x140006266  jz      short loc_140006285
0x140006268  movzx   edx, word ptr [r8]
0x14000626c  test    dx, dx
0x14000626f  jz      short loc_140006285
0x140006271  mov     [rax], dx
0x140006274  add     r8, 2
0x140006278  add     rax, 2
0x14000627c  dec     rcx
0x14000627f  sub     r9, 1
0x140006283  jnz     short loc_140006263
0x140006285  test    r9, r9
0x140006288  lea     rcx, [rax-2]
0x14000628c  cmovnz  rcx, rax
0x140006290  neg     r9
0x140006293  sbb     edx, edx
0x140006295  not     edx
0x140006297  and     edx, 8007007Ah
0x14000629d  mov     [rcx], di
0x1400062a0  mov     rbx, [rsp+arg_0]
0x1400062a5  mov     eax, edx
0x1400062a7  mov     rdi, [rsp+arg_8]
0x1400062ac  retn
```
