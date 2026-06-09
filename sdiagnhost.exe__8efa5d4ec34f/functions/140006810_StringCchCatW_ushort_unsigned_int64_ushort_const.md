# StringCchCatW(ushort *,unsigned __int64,ushort const *)

- ea: `0x140006810`
- end: `0x1400068b9`
- name: `?StringCchCatW@@YAJPEAG_KPEBG@Z`
- size: `169`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140003f74`
- `0x14000697c`

## callees

- `0x140006810`

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
0x140006810  mov     [rsp+arg_0], rbx
0x140006815  mov     [rsp+arg_8], rdi
0x14000681a  mov     r9d, 104h
0x140006820  mov     rbx, rcx
0x140006823  mov     r10d, r9d
0x140006826  mov     rax, rcx
0x140006829  xor     edi, edi
0x14000682b  cmp     [rax], di
0x14000682e  jz      short loc_14000683A
0x140006830  add     rax, 2
0x140006834  sub     r10, 1
0x140006838  jnz     short loc_14000682B
0x14000683a  mov     rax, r10
0x14000683d  mov     rcx, r9
0x140006840  neg     rax
0x140006843  mov     rax, r10
0x140006846  sbb     edx, edx
0x140006848  sub     rcx, r10
0x14000684b  not     edx
0x14000684d  and     edx, 80070057h
0x140006853  neg     rax
0x140006856  sbb     r11, r11
0x140006859  and     r11, rcx
0x14000685c  test    r10, r10
0x14000685f  jz      short loc_1400068AC
0x140006861  lea     rax, [rbx+r11*2]
0x140006865  mov     ecx, 7FFFFFFEh
0x14000686a  sub     r9, r11
0x14000686d  jz      short loc_140006891
0x14000686f  test    rcx, rcx
0x140006872  jz      short loc_140006891
0x140006874  movzx   edx, word ptr [r8]
0x140006878  test    dx, dx
0x14000687b  jz      short loc_140006891
0x14000687d  mov     [rax], dx
0x140006880  add     r8, 2
0x140006884  add     rax, 2
0x140006888  dec     rcx
0x14000688b  sub     r9, 1
0x14000688f  jnz     short loc_14000686F
0x140006891  test    r9, r9
0x140006894  lea     rcx, [rax-2]
0x140006898  cmovnz  rcx, rax
0x14000689c  neg     r9
0x14000689f  sbb     edx, edx
0x1400068a1  not     edx
0x1400068a3  and     edx, 8007007Ah
0x1400068a9  mov     [rcx], di
0x1400068ac  mov     rbx, [rsp+arg_0]
0x1400068b1  mov     eax, edx
0x1400068b3  mov     rdi, [rsp+arg_8]
0x1400068b8  retn
```
