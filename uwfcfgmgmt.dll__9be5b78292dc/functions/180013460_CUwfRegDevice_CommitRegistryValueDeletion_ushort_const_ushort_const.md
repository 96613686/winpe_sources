# CUwfRegDevice::CommitRegistryValueDeletion(ushort const *,ushort const *)

- ea: `0x180013460`
- end: `0x1800135a2`
- name: `?CommitRegistryValueDeletion@CUwfRegDevice@@QEAAJPEBG0@Z`
- size: `322`
- prototype: `__int64 __fastcall(CUwfRegDevice *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800092a8`
- `0x180009a50`
- `0x180015870`

## callees

- `0x180013460`
- `0x1800147d0`
- `0x18001afe2`
- `0x18001b020`

## pseudocode

```c
__int64 __fastcall CUwfRegDevice::CommitRegistryValueDeletion(
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
      return (unsigned int)CDevice::SendIOCTL(this, 0x2289ECu, v16, 0xA00u, 0, 0, 0);
  }
  return v11;
}

```

## disassembly

```asm
0x180013460  mov     [rsp+arg_8], rbx
0x180013465  mov     [rsp+arg_10], rbp
0x18001346a  push    rsi
0x18001346b  push    rdi
0x18001346c  push    r14
0x18001346e  sub     rsp, 0A50h
0x180013475  mov     rax, cs:__security_cookie
0x18001347c  xor     rax, rsp
0x18001347f  mov     [rsp+0A68h+var_28], rax
0x180013487  mov     rsi, r8
0x18001348a  mov     rbx, rdx
0x18001348d  mov     rbp, rcx
0x180013490  xor     edx, edx; Val
0x180013492  mov     r8d, 0A00h; Size
0x180013498  lea     rcx, [rsp+0A68h+var_A28]; void *
0x18001349d  call    memset_0
0x1800134a2  mov     edi, 7FFFFFFEh
0x1800134a7  lea     rdx, [rsp+0A68h+var_A28]
0x1800134ac  mov     eax, edi
0x1800134ae  mov     r9d, 400h
0x1800134b4  xor     r14d, r14d
0x1800134b7  test    rax, rax
0x1800134ba  jz      short loc_1800134D8
0x1800134bc  movzx   ecx, word ptr [rbx]
0x1800134bf  test    cx, cx
0x1800134c2  jz      short loc_1800134D8
0x1800134c4  mov     [rdx], cx
0x1800134c7  add     rbx, 2
0x1800134cb  add     rdx, 2
0x1800134cf  dec     rax
0x1800134d2  sub     r9, 1
0x1800134d6  jnz     short loc_1800134B7
0x1800134d8  mov     rax, r9
0x1800134db  lea     rcx, [rdx-2]
0x1800134df  neg     rax
0x1800134e2  mov     ebx, 8007007Ah
0x1800134e7  sbb     r8d, r8d
0x1800134ea  not     r8d
0x1800134ed  and     r8d, ebx
0x1800134f0  test    r9, r9
0x1800134f3  cmovnz  rcx, rdx
0x1800134f7  mov     [rcx], r14w
0x1800134fb  jz      short loc_180013577
0x1800134fd  mov     r10d, 100h
0x180013503  lea     r11, [rsp+0A68h+var_228]
0x18001350b  test    rdi, rdi
0x18001350e  jz      short loc_18001352D
0x180013510  movzx   eax, word ptr [rsi]
0x180013513  test    ax, ax
0x180013516  jz      short loc_18001352D
0x180013518  mov     [r11], ax
0x18001351c  add     rsi, 2
0x180013520  add     r11, 2
0x180013524  dec     rdi
0x180013527  sub     r10, 1
0x18001352b  jnz     short loc_18001350B
0x18001352d  mov     rax, r10
0x180013530  lea     rdx, [r11-2]
0x180013534  neg     rax
0x180013537  sbb     r8d, r8d
0x18001353a  not     r8d
0x18001353d  and     r8d, ebx
0x180013540  test    r10, r10
0x180013543  cmovnz  rdx, r11
0x180013547  mov     [rdx], r14w
0x18001354b  jz      short loc_180013577
0x18001354d  mov     [rsp+0A68h+var_A38], r14; unsigned int *
0x180013552  lea     r8, [rsp+0A68h+var_A28]; void *
0x180013557  mov     [rsp+0A68h+var_A40], r14d; DWORD
0x18001355c  mov     r9d, 0A00h; unsigned int
0x180013562  mov     edx, 2289ECh; unsigned int
0x180013567  mov     [rsp+0A68h+var_A48], r14; void *
0x18001356c  mov     rcx, rbp; this
0x18001356f  call    ?SendIOCTL@CDevice@@QEAAJKPEAXK0KPEAK@Z; CDevice::SendIOCTL(ulong,void *,ulong,void *,ulong,ulong *)
0x180013574  mov     r8d, eax
0x180013577  mov     eax, r8d
0x18001357a  mov     rcx, [rsp+0A68h+var_28]
0x180013582  xor     rcx, rsp; StackCookie
0x180013585  call    __security_check_cookie
0x18001358a  lea     r11, [rsp+0A68h+var_18]
0x180013592  mov     rbx, [r11+28h]
0x180013596  mov     rbp, [r11+30h]
0x18001359a  mov     rsp, r11
0x18001359d  pop     r14
0x18001359f  pop     rdi
0x1800135a0  pop     rsi
0x1800135a1  retn
```
