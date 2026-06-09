# StringCchCatW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180005510`
- end: `0x1800055b9`
- name: `?StringCchCatW@@YAJPEAG_KPEBG@Z`
- size: `169`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800044e8`
- `0x1800055c0`

## callees

- `0x180005510`

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
0x180005510  mov     [rsp+arg_0], rbx
0x180005515  mov     [rsp+arg_8], rdi
0x18000551a  mov     r9d, 104h
0x180005520  mov     rbx, rcx
0x180005523  mov     r10d, r9d
0x180005526  mov     rax, rcx
0x180005529  xor     edi, edi
0x18000552b  cmp     [rax], di
0x18000552e  jz      short loc_18000553A
0x180005530  add     rax, 2
0x180005534  sub     r10, 1
0x180005538  jnz     short loc_18000552B
0x18000553a  mov     rax, r10
0x18000553d  mov     rcx, r9
0x180005540  neg     rax
0x180005543  mov     rax, r10
0x180005546  sbb     edx, edx
0x180005548  sub     rcx, r10
0x18000554b  not     edx
0x18000554d  and     edx, 80070057h
0x180005553  neg     rax
0x180005556  sbb     r11, r11
0x180005559  and     r11, rcx
0x18000555c  test    r10, r10
0x18000555f  jz      short loc_1800055AC
0x180005561  lea     rax, [rbx+r11*2]
0x180005565  mov     ecx, 7FFFFFFEh
0x18000556a  sub     r9, r11
0x18000556d  jz      short loc_180005591
0x18000556f  test    rcx, rcx
0x180005572  jz      short loc_180005591
0x180005574  movzx   edx, word ptr [r8]
0x180005578  test    dx, dx
0x18000557b  jz      short loc_180005591
0x18000557d  mov     [rax], dx
0x180005580  add     r8, 2
0x180005584  add     rax, 2
0x180005588  dec     rcx
0x18000558b  sub     r9, 1
0x18000558f  jnz     short loc_18000556F
0x180005591  test    r9, r9
0x180005594  lea     rcx, [rax-2]
0x180005598  cmovnz  rcx, rax
0x18000559c  neg     r9
0x18000559f  sbb     edx, edx
0x1800055a1  not     edx
0x1800055a3  and     edx, 8007007Ah
0x1800055a9  mov     [rcx], di
0x1800055ac  mov     rbx, [rsp+arg_0]
0x1800055b1  mov     eax, edx
0x1800055b3  mov     rdi, [rsp+arg_8]
0x1800055b8  retn
```
