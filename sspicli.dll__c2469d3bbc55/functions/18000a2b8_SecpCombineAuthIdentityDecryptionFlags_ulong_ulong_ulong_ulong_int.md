# SecpCombineAuthIdentityDecryptionFlags(ulong,ulong,ulong *,ulong *,int *)

- ea: `0x18000a2b8`
- end: `0x18000a3a3`
- name: `?SecpCombineAuthIdentityDecryptionFlags@@YAJKKPEAK0PEAH@Z`
- size: `235`
- prototype: `__int64 __fastcall(unsigned int, unsigned int, unsigned int *, unsigned int *, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800090e0`

## callees

- `0x18000a170`
- `0x18000a2b8`

## pseudocode

```c
__int64 __fastcall SecpCombineAuthIdentityDecryptionFlags(
        int a1,
        unsigned int a2,
        unsigned int *a3,
        unsigned int *a4,
        int *a5)
{
  int v8; // edi
  int ThreadLogonContext; // ecx
  int *v10; // rax
  unsigned int v11; // ebx
  int *v12; // rax
  int v14; // [rsp+58h] [rbp+10h] BYREF

  v14 = 0;
  if ( (a2 & 0x10000) == 0 )
    return (unsigned int)-1073741811;
  v8 = 128;
  *a3 = a2;
  if ( (a2 & 0x80u) == 0 )
  {
    if ( a1 == 1 )
    {
      if ( (a2 & 0x10) != 0 )
        return (unsigned int)-1073741637;
      ThreadLogonContext = SecpGetThreadLogonContext(&v14);
      if ( ThreadLogonContext < 0 )
        return (unsigned int)ThreadLogonContext;
      if ( v14 )
      {
        v8 = 32;
        v11 = a2 >> 5;
      }
      else
      {
        v8 = 64;
        v11 = a2 >> 6;
      }
      *a5 = v11 & 1;
      *a4 = 2;
      goto LABEL_17;
    }
    if ( a1 == 2 )
    {
      v12 = a5;
      ThreadLogonContext = 0;
      *a4 = 0;
      *v12 = (a2 >> 4) & 1;
      v8 = 16;
      goto LABEL_17;
    }
    return (unsigned int)-1073741811;
  }
  ThreadLogonContext = SecpGetThreadLogonContext(&v14);
  if ( ThreadLogonContext >= 0 )
  {
    if ( !v14 )
      return (unsigned int)-1073741790;
    v10 = a5;
    *a4 = 4;
    *v10 = 1;
LABEL_17:
    *a3 &= ~v8;
  }
  return (unsigned int)ThreadLogonContext;
}

```

## disassembly

```asm
0x18000a2b8  push    rbx
0x18000a2ba  push    rsi
0x18000a2bb  push    rdi
0x18000a2bc  push    r14
0x18000a2be  sub     rsp, 28h
0x18000a2c2  mov     [rsp+48h+arg_8], 0
0x18000a2ca  mov     r14, r9
0x18000a2cd  mov     rsi, r8
0x18000a2d0  mov     ebx, edx
0x18000a2d2  bt      edx, 10h
0x18000a2d6  jnb     loc_18000A392
0x18000a2dc  mov     edi, 80h
0x18000a2e1  mov     [r8], edx
0x18000a2e4  test    dil, bl
0x18000a2e7  jz      short loc_18000A322
0x18000a2e9  lea     rcx, [rsp+48h+arg_8]; int *
0x18000a2ee  call    ?SecpGetThreadLogonContext@@YAJPEAH@Z; SecpGetThreadLogonContext(int *)
0x18000a2f3  mov     ecx, eax
0x18000a2f5  test    eax, eax
0x18000a2f7  js      loc_18000A397
0x18000a2fd  cmp     [rsp+48h+arg_8], 0
0x18000a302  jnz     short loc_18000A30E
0x18000a304  mov     ecx, 0C0000022h
0x18000a309  jmp     loc_18000A397
0x18000a30e  mov     rax, [rsp+48h+arg_20]
0x18000a313  mov     dword ptr [r14], 4
0x18000a31a  mov     dword ptr [rax], 1
0x18000a320  jmp     short loc_18000A38C
0x18000a322  cmp     ecx, 1
0x18000a325  jnz     short loc_18000A372
0x18000a327  lea     edi, [rcx+0Fh]
0x18000a32a  test    dil, bl
0x18000a32d  jz      short loc_18000A336
0x18000a32f  mov     ecx, 0C00000BBh
0x18000a334  jmp     short loc_18000A397
0x18000a336  lea     rcx, [rsp+48h+arg_8]; int *
0x18000a33b  call    ?SecpGetThreadLogonContext@@YAJPEAH@Z; SecpGetThreadLogonContext(int *)
0x18000a340  mov     ecx, eax
0x18000a342  test    eax, eax
0x18000a344  js      short loc_18000A397
0x18000a346  cmp     [rsp+48h+arg_8], 0
0x18000a34b  jz      short loc_18000A357
0x18000a34d  mov     edi, 20h ; ' '
0x18000a352  shr     ebx, 5
0x18000a355  jmp     short loc_18000A35F
0x18000a357  mov     edi, 40h ; '@'
0x18000a35c  shr     ebx, 6
0x18000a35f  mov     rax, [rsp+48h+arg_20]
0x18000a364  and     ebx, 1
0x18000a367  mov     [rax], ebx
0x18000a369  mov     dword ptr [r14], 2
0x18000a370  jmp     short loc_18000A38C
0x18000a372  cmp     ecx, 2
0x18000a375  jnz     short loc_18000A392
0x18000a377  mov     rax, [rsp+48h+arg_20]
0x18000a37c  xor     ecx, ecx
0x18000a37e  shr     ebx, 4
0x18000a381  and     ebx, 1
0x18000a384  mov     [r9], ecx
0x18000a387  mov     [rax], ebx
0x18000a389  lea     edi, [rcx+10h]
0x18000a38c  not     edi
0x18000a38e  and     [rsi], edi
0x18000a390  jmp     short loc_18000A397
0x18000a392  mov     ecx, 0C000000Dh
0x18000a397  mov     eax, ecx
0x18000a399  add     rsp, 28h
0x18000a39d  pop     r14
0x18000a39f  pop     rdi
0x18000a3a0  pop     rsi
0x18000a3a1  pop     rbx
0x18000a3a2  retn
```
