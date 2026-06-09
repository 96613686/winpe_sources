# StringCchCatW(ushort *,unsigned __int64,ushort const *)

- ea: `0x18000c8e8`
- end: `0x18000c992`
- name: `?StringCchCatW@@YAJPEAG_KPEBG@Z`
- size: `170`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a5c0`
- `0x18000cb58`
- `0x18000e7d0`

## callees

- `0x18000c8e8`

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
0x18000c8e8  mov     [rsp+arg_0], rbx
0x18000c8ed  mov     [rsp+arg_8], rdi
0x18000c8f2  mov     r9d, 104h
0x18000c8f8  mov     rbx, rcx
0x18000c8fb  mov     r10d, r9d
0x18000c8fe  mov     rax, rcx
0x18000c901  xor     edi, edi
0x18000c903  cmp     [rax], di
0x18000c906  jz      short loc_18000C912
0x18000c908  add     rax, 2
0x18000c90c  sub     r10, 1
0x18000c910  jnz     short loc_18000C903
0x18000c912  mov     rax, r10
0x18000c915  mov     rcx, r9
0x18000c918  neg     rax
0x18000c91b  mov     rax, r10
0x18000c91e  sbb     edx, edx
0x18000c920  sub     rcx, r10
0x18000c923  not     edx
0x18000c925  and     edx, 80070057h
0x18000c92b  neg     rax
0x18000c92e  sbb     r11, r11
0x18000c931  and     r11, rcx
0x18000c934  test    r10, r10
0x18000c937  jz      short loc_18000C984
0x18000c939  lea     rax, [rbx+r11*2]
0x18000c93d  mov     ecx, 7FFFFFFEh
0x18000c942  sub     r9, r11
0x18000c945  jz      short loc_18000C969
0x18000c947  test    rcx, rcx
0x18000c94a  jz      short loc_18000C969
0x18000c94c  movzx   edx, word ptr [r8]
0x18000c950  test    dx, dx
0x18000c953  jz      short loc_18000C969
0x18000c955  mov     [rax], dx
0x18000c958  add     r8, 2
0x18000c95c  add     rax, 2
0x18000c960  dec     rcx
0x18000c963  sub     r9, 1
0x18000c967  jnz     short loc_18000C947
0x18000c969  test    r9, r9
0x18000c96c  lea     rcx, [rax-2]
0x18000c970  cmovnz  rcx, rax
0x18000c974  neg     r9
0x18000c977  sbb     edx, edx
0x18000c979  not     edx
0x18000c97b  and     edx, 8007007Ah
0x18000c981  mov     [rcx], di
0x18000c984  mov     rbx, [rsp+arg_0]
0x18000c989  mov     eax, edx
0x18000c98b  mov     rdi, [rsp+arg_8]
0x18000c990  retn
```
