# CUwfRegDevice::CommitRegistryValue(ushort const *,ushort const *)

- ea: `0x180013310`
- end: `0x180013452`
- name: `?CommitRegistryValue@CUwfRegDevice@@QEAAJPEBG0@Z`
- size: `322`
- prototype: `__int64 __fastcall(CUwfRegDevice *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800092a8`
- `0x180009a50`
- `0x18000ea14`
- `0x1800155f0`

## callees

- `0x180013310`
- `0x1800147d0`
- `0x18001afe2`
- `0x18001b020`

## pseudocode

```c
__int64 __fastcall CUwfRegDevice::CommitRegistryValue(
        CUwfRegDevice *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  __int64 v6; // rdi
  _WORD *v7; // rdx
  __int64 v8; // rax
  __int64 v9; // r9
  _WORD *v10; // rcx
  unsigned int v11; // r8d
  __int64 v12; // r10
  char *v13; // r11
  char *v14; // rdx
  _BYTE v16[2048]; // [rsp+40h] [rbp-A28h] BYREF
  char v17; // [rsp+840h] [rbp-228h] BYREF

  memset_0(v16, 0, 0xA00u);
  v6 = 2147483646;
  v7 = v16;
  v8 = 2147483646;
  v9 = 1024;
  do
  {
    if ( !v8 )
      break;
    if ( !*a2 )
      break;
    *v7++ = *a2++;
    --v8;
    --v9;
  }
  while ( v9 );
  v10 = v7 - 1;
  v11 = v9 == 0 ? 0x8007007A : 0;
  if ( v9 )
    v10 = v7;
  *v10 = 0;
  if ( v9 )
  {
    v12 = 256;
    v13 = &v17;
    do
    {
      if ( !v6 )
        break;
      if ( !*a3 )
        break;
      *(_WORD *)v13 = *a3++;
      v13 += 2;
      --v6;
      --v12;
    }
    while ( v12 );
    v14 = v13 - 2;
    v11 = v12 == 0 ? 0x8007007A : 0;
    if ( v12 )
      v14 = v13;
    *(_WORD *)v14 = 0;
    if ( v12 )
      return (unsigned int)CDevice::SendIOCTL(this, 0x2289E4u, v16, 0xA00u, 0, 0, 0);
  }
  return v11;
}

```

## disassembly

```asm
0x180013310  mov     [rsp+arg_8], rbx
0x180013315  mov     [rsp+arg_10], rbp
0x18001331a  push    rsi
0x18001331b  push    rdi
0x18001331c  push    r14
0x18001331e  sub     rsp, 0A50h
0x180013325  mov     rax, cs:__security_cookie
0x18001332c  xor     rax, rsp
0x18001332f  mov     [rsp+0A68h+var_28], rax
0x180013337  mov     rsi, r8
0x18001333a  mov     rbx, rdx
0x18001333d  mov     rbp, rcx
0x180013340  xor     edx, edx; Val
0x180013342  mov     r8d, 0A00h; Size
0x180013348  lea     rcx, [rsp+0A68h+var_A28]; void *
0x18001334d  call    memset_0
0x180013352  mov     edi, 7FFFFFFEh
0x180013357  lea     rdx, [rsp+0A68h+var_A28]
0x18001335c  mov     eax, edi
0x18001335e  mov     r9d, 400h
0x180013364  xor     r14d, r14d
0x180013367  test    rax, rax
0x18001336a  jz      short loc_180013388
0x18001336c  movzx   ecx, word ptr [rbx]
0x18001336f  test    cx, cx
0x180013372  jz      short loc_180013388
0x180013374  mov     [rdx], cx
0x180013377  add     rbx, 2
0x18001337b  add     rdx, 2
0x18001337f  dec     rax
0x180013382  sub     r9, 1
0x180013386  jnz     short loc_180013367
0x180013388  mov     rax, r9
0x18001338b  lea     rcx, [rdx-2]
0x18001338f  neg     rax
0x180013392  mov     ebx, 8007007Ah
0x180013397  sbb     r8d, r8d
0x18001339a  not     r8d
0x18001339d  and     r8d, ebx
0x1800133a0  test    r9, r9
0x1800133a3  cmovnz  rcx, rdx
0x1800133a7  mov     [rcx], r14w
0x1800133ab  jz      short loc_180013427
0x1800133ad  mov     r10d, 100h
0x1800133b3  lea     r11, [rsp+0A68h+var_228]
0x1800133bb  test    rdi, rdi
0x1800133be  jz      short loc_1800133DD
0x1800133c0  movzx   eax, word ptr [rsi]
0x1800133c3  test    ax, ax
0x1800133c6  jz      short loc_1800133DD
0x1800133c8  mov     [r11], ax
0x1800133cc  add     rsi, 2
0x1800133d0  add     r11, 2
0x1800133d4  dec     rdi
0x1800133d7  sub     r10, 1
0x1800133db  jnz     short loc_1800133BB
0x1800133dd  mov     rax, r10
0x1800133e0  lea     rdx, [r11-2]
0x1800133e4  neg     rax
0x1800133e7  sbb     r8d, r8d
0x1800133ea  not     r8d
0x1800133ed  and     r8d, ebx
0x1800133f0  test    r10, r10
0x1800133f3  cmovnz  rdx, r11
0x1800133f7  mov     [rdx], r14w
0x1800133fb  jz      short loc_180013427
0x1800133fd  mov     [rsp+0A68h+var_A38], r14; unsigned int *
0x180013402  lea     r8, [rsp+0A68h+var_A28]; void *
0x180013407  mov     [rsp+0A68h+var_A40], r14d; DWORD
0x18001340c  mov     r9d, 0A00h; unsigned int
0x180013412  mov     edx, 2289E4h; unsigned int
0x180013417  mov     [rsp+0A68h+var_A48], r14; void *
0x18001341c  mov     rcx, rbp; this
0x18001341f  call    ?SendIOCTL@CDevice@@QEAAJKPEAXK0KPEAK@Z; CDevice::SendIOCTL(ulong,void *,ulong,void *,ulong,ulong *)
0x180013424  mov     r8d, eax
0x180013427  mov     eax, r8d
0x18001342a  mov     rcx, [rsp+0A68h+var_28]
0x180013432  xor     rcx, rsp; StackCookie
0x180013435  call    __security_check_cookie
0x18001343a  lea     r11, [rsp+0A68h+var_18]
0x180013442  mov     rbx, [r11+28h]
0x180013446  mov     rbp, [r11+30h]
0x18001344a  mov     rsp, r11
0x18001344d  pop     r14
0x18001344f  pop     rdi
0x180013450  pop     rsi
0x180013451  retn
```
