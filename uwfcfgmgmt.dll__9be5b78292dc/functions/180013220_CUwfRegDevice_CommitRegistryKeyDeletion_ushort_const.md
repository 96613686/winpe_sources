# CUwfRegDevice::CommitRegistryKeyDeletion(ushort const *)

- ea: `0x180013220`
- end: `0x180013304`
- name: `?CommitRegistryKeyDeletion@CUwfRegDevice@@QEAAJPEBG@Z`
- size: `228`
- prototype: `__int64 __fastcall(CUwfRegDevice *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180015870`

## callees

- `0x180013220`
- `0x1800147d0`
- `0x18001afe2`
- `0x18001b020`

## pseudocode

```c
__int64 __fastcall CUwfRegDevice::CommitRegistryKeyDeletion(CUwfRegDevice *this, const unsigned __int16 *a2)
{
  __int64 v4; // rax
  _WORD *v5; // r11
  __int64 v6; // r10
  _WORD *v7; // rdx
  unsigned int v8; // r8d
  _BYTE v10[2048]; // [rsp+40h] [rbp-818h] BYREF

  memset_0(v10, 0, sizeof(v10));
  v4 = 2147483646;
  v5 = v10;
  v6 = 1024;
  do
  {
    if ( !v4 )
      break;
    if ( !*a2 )
      break;
    *v5++ = *a2++;
    --v4;
    --v6;
  }
  while ( v6 );
  v7 = v5 - 1;
  v8 = v6 == 0 ? 0x8007007A : 0;
  if ( v6 )
    v7 = v5;
  *v7 = 0;
  if ( v6 )
    return (unsigned int)CDevice::SendIOCTL(this, 0x2289F0u, v10, 0x800u, 0, 0, 0);
  return v8;
}

```

## disassembly

```asm
0x180013220  mov     [rsp+arg_8], rbx
0x180013225  mov     [rsp+arg_10], rsi
0x18001322a  push    rdi
0x18001322b  sub     rsp, 850h
0x180013232  mov     rax, cs:__security_cookie
0x180013239  xor     rax, rsp
0x18001323c  mov     [rsp+858h+var_18], rax
0x180013244  mov     rbx, rdx
0x180013247  mov     rdi, rcx
0x18001324a  xor     edx, edx; Val
0x18001324c  lea     rcx, [rsp+858h+var_818]; void *
0x180013251  mov     r8d, 800h; Size
0x180013257  call    memset_0
0x18001325c  mov     eax, 7FFFFFFEh
0x180013261  lea     r11, [rsp+858h+var_818]
0x180013266  mov     r10d, 400h
0x18001326c  xor     esi, esi
0x18001326e  test    rax, rax
0x180013271  jz      short loc_180013290
0x180013273  movzx   ecx, word ptr [rbx]
0x180013276  test    cx, cx
0x180013279  jz      short loc_180013290
0x18001327b  mov     [r11], cx
0x18001327f  add     rbx, 2
0x180013283  add     r11, 2
0x180013287  dec     rax
0x18001328a  sub     r10, 1
0x18001328e  jnz     short loc_18001326E
0x180013290  mov     rax, r10
0x180013293  lea     rdx, [r11-2]
0x180013297  neg     rax
0x18001329a  sbb     r8d, r8d
0x18001329d  not     r8d
0x1800132a0  and     r8d, 8007007Ah
0x1800132a7  test    r10, r10
0x1800132aa  cmovnz  rdx, r11
0x1800132ae  mov     [rdx], si
0x1800132b1  jz      short loc_1800132DC
0x1800132b3  mov     [rsp+858h+var_828], rsi; unsigned int *
0x1800132b8  lea     r8, [rsp+858h+var_818]; void *
0x1800132bd  mov     [rsp+858h+var_830], esi; DWORD
0x1800132c1  mov     r9d, 800h; unsigned int
0x1800132c7  mov     edx, 2289F0h; unsigned int
0x1800132cc  mov     [rsp+858h+var_838], rsi; void *
0x1800132d1  mov     rcx, rdi; this
0x1800132d4  call    ?SendIOCTL@CDevice@@QEAAJKPEAXK0KPEAK@Z; CDevice::SendIOCTL(ulong,void *,ulong,void *,ulong,ulong *)
0x1800132d9  mov     r8d, eax
0x1800132dc  mov     eax, r8d
0x1800132df  mov     rcx, [rsp+858h+var_18]
0x1800132e7  xor     rcx, rsp; StackCookie
0x1800132ea  call    __security_check_cookie
0x1800132ef  lea     r11, [rsp+858h+var_8]
0x1800132f7  mov     rbx, [r11+18h]
0x1800132fb  mov     rsi, [r11+20h]
0x1800132ff  mov     rsp, r11
0x180013302  pop     rdi
0x180013303  retn
```
