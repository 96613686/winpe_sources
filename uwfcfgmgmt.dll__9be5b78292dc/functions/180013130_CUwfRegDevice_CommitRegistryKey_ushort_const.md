# CUwfRegDevice::CommitRegistryKey(ushort const *)

- ea: `0x180013130`
- end: `0x180013214`
- name: `?CommitRegistryKey@CUwfRegDevice@@QEAAJPEBG@Z`
- size: `228`
- prototype: `__int64 __fastcall(CUwfRegDevice *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800155f0`

## callees

- `0x180013130`
- `0x1800147d0`
- `0x18001afe2`
- `0x18001b020`

## pseudocode

```c
__int64 __fastcall CUwfRegDevice::CommitRegistryKey(CUwfRegDevice *this, const unsigned __int16 *a2)
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
    return (unsigned int)CDevice::SendIOCTL(this, 0x2289E8u, v10, 0x800u, 0, 0, 0);
  return v8;
}

```

## disassembly

```asm
0x180013130  mov     [rsp+arg_8], rbx
0x180013135  mov     [rsp+arg_10], rsi
0x18001313a  push    rdi
0x18001313b  sub     rsp, 850h
0x180013142  mov     rax, cs:__security_cookie
0x180013149  xor     rax, rsp
0x18001314c  mov     [rsp+858h+var_18], rax
0x180013154  mov     rbx, rdx
0x180013157  mov     rdi, rcx
0x18001315a  xor     edx, edx; Val
0x18001315c  lea     rcx, [rsp+858h+var_818]; void *
0x180013161  mov     r8d, 800h; Size
0x180013167  call    memset_0
0x18001316c  mov     eax, 7FFFFFFEh
0x180013171  lea     r11, [rsp+858h+var_818]
0x180013176  mov     r10d, 400h
0x18001317c  xor     esi, esi
0x18001317e  test    rax, rax
0x180013181  jz      short loc_1800131A0
0x180013183  movzx   ecx, word ptr [rbx]
0x180013186  test    cx, cx
0x180013189  jz      short loc_1800131A0
0x18001318b  mov     [r11], cx
0x18001318f  add     rbx, 2
0x180013193  add     r11, 2
0x180013197  dec     rax
0x18001319a  sub     r10, 1
0x18001319e  jnz     short loc_18001317E
0x1800131a0  mov     rax, r10
0x1800131a3  lea     rdx, [r11-2]
0x1800131a7  neg     rax
0x1800131aa  sbb     r8d, r8d
0x1800131ad  not     r8d
0x1800131b0  and     r8d, 8007007Ah
0x1800131b7  test    r10, r10
0x1800131ba  cmovnz  rdx, r11
0x1800131be  mov     [rdx], si
0x1800131c1  jz      short loc_1800131EC
0x1800131c3  mov     [rsp+858h+var_828], rsi; unsigned int *
0x1800131c8  lea     r8, [rsp+858h+var_818]; void *
0x1800131cd  mov     [rsp+858h+var_830], esi; DWORD
0x1800131d1  mov     r9d, 800h; unsigned int
0x1800131d7  mov     edx, 2289E8h; unsigned int
0x1800131dc  mov     [rsp+858h+var_838], rsi; void *
0x1800131e1  mov     rcx, rdi; this
0x1800131e4  call    ?SendIOCTL@CDevice@@QEAAJKPEAXK0KPEAK@Z; CDevice::SendIOCTL(ulong,void *,ulong,void *,ulong,ulong *)
0x1800131e9  mov     r8d, eax
0x1800131ec  mov     eax, r8d
0x1800131ef  mov     rcx, [rsp+858h+var_18]
0x1800131f7  xor     rcx, rsp; StackCookie
0x1800131fa  call    __security_check_cookie
0x1800131ff  lea     r11, [rsp+858h+var_8]
0x180013207  mov     rbx, [r11+18h]
0x18001320b  mov     rsi, [r11+20h]
0x18001320f  mov     rsp, r11
0x180013212  pop     rdi
0x180013213  retn
```
