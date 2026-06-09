# WinHvCreateCpuGroup

- ea: `0x140020e60`
- end: `0x140021029`
- name: `WinHvCreateCpuGroup`
- size: `457`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callees

- `0x140002240`
- `0x140002358`
- `0x140004460`
- `0x140009c90`
- `0x14000a040`
- `0x140020e60`

## pseudocode

```c
__int64 __fastcall WinHvCreateCpuGroup(__int64 a1, unsigned int a2, _QWORD *a3)
{
  __int64 v4; // rbx
  int v5; // r15d
  __int64 *v6; // rsi
  __int64 v7; // rdx
  __int64 v8; // r14
  unsigned int v9; // edi
  __int64 v10; // rbx
  __int64 v11; // r12
  __int64 v12; // rax
  int v13; // ebx
  _QWORD *v15; // [rsp+30h] [rbp-50h] BYREF
  _QWORD v16[8]; // [rsp+40h] [rbp-40h] BYREF
  __int64 *v19; // [rsp+D8h] [rbp+58h] BYREF

  v19 = 0;
  v4 = a1;
  memset(v16, 0, sizeof(v16));
  v15 = 0;
  if ( a2 > 0x800 )
  {
    return (unsigned int)-1073741811;
  }
  else
  {
    v5 = 0;
    while ( 2 )
    {
      WinHvpSetupHypercall(&v19, (__int64 *)&v15, (__int64)v16);
      v6 = v19;
      v7 = 0;
      v8 = 0;
      *(_OWORD *)v19 = 0;
      while ( (unsigned int)v8 < a2 )
      {
        v9 = *(_DWORD *)(v4 + 4 * v8);
        if ( v9 >= 0x800 )
          goto LABEL_20;
        v10 = v9 >> 6;
        if ( (unsigned int)v10 >= (unsigned int)v7 )
        {
          v11 = (unsigned int)(v10 + 1);
          if ( (unsigned __int64)(8 * v11 + 16) > 0x1000 )
          {
LABEL_20:
            ((void (__fastcall *)(_QWORD, __int64))v16[7])(v16[0], v7);
            return (unsigned int)-1073741811;
          }
          memset(&v6[(unsigned int)v7 + 2], 0, 8LL * (unsigned int)(v10 - v7 + 1));
          v7 = (unsigned int)v11;
        }
        v6[v10 + 2] |= 1LL << (v9 & 0x3F);
        v8 = (unsigned int)(v8 + 1);
        v4 = a1;
      }
      *v6 = 0;
      if ( (_DWORD)v7 == 64 )
        v12 = -1;
      else
        v12 = (1LL << v7) - 1;
      v6[1] = v12;
      v13 = WinHvpVariableHeaderHypercall(
              181,
              (unsigned int)(8 * v7 + 16),
              *(_QWORD *)(v16[5] + 24LL),
              *(_QWORD *)(v16[5] + 40LL));
      if ( v13 >= 0 )
        *a3 = *v15;
      ((void (__fastcall *)(_QWORD))v16[7])(v16[0]);
      if ( v13 == -1070268299 || v13 == -1070268405 || (unsigned int)(v13 + 1070268287) <= 1 )
      {
        v13 = WinHvpLowMemoryHandler(-1, -2147418113, v13, 181, v5, 0);
        if ( v13 >= 0 )
        {
          v4 = a1;
          ++v5;
          continue;
        }
      }
      break;
    }
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x140020e60  mov     [rsp-38h+arg_8], rbx
0x140020e65  mov     [rsp-38h+arg_10], r8
0x140020e6a  mov     [rsp-38h+arg_0], rcx
0x140020e6f  push    rbp
0x140020e70  push    rsi
0x140020e71  push    rdi
0x140020e72  push    r12
0x140020e74  push    r13
0x140020e76  push    r14
0x140020e78  push    r15
0x140020e7a  mov     rbp, rsp
0x140020e7d  sub     rsp, 80h
0x140020e84  mov     r13d, edx
0x140020e87  mov     [rbp+arg_18], 0
0x140020e8f  xor     edx, edx; Val
0x140020e91  mov     rbx, rcx
0x140020e94  lea     rcx, [rbp+var_40]; void *
0x140020e98  lea     r8d, [rdx+40h]; Size
0x140020e9c  call    memset
0x140020ea1  mov     [rbp+var_50], 0
0x140020ea9  cmp     r13d, 800h
0x140020eb0  ja      loc_140021006
0x140020eb6  xor     r15d, r15d
0x140020eb9  lea     r8, [rbp+var_40]
0x140020ebd  lea     rdx, [rbp+var_50]
0x140020ec1  lea     rcx, [rbp+arg_18]
0x140020ec5  call    WinHvpSetupHypercall
0x140020eca  mov     rsi, [rbp+arg_18]
0x140020ece  xorps   xmm0, xmm0
0x140020ed1  xor     edx, edx
0x140020ed3  xor     r14d, r14d
0x140020ed6  movups  xmmword ptr [rsi], xmm0
0x140020ed9  cmp     r14d, r13d
0x140020edc  jnb     short loc_140020F4A
0x140020ede  mov     edi, [rbx+r14*4]
0x140020ee2  cmp     edi, 800h
0x140020ee8  jnb     loc_140020FF9
0x140020eee  mov     ebx, edi
0x140020ef0  shr     ebx, 6
0x140020ef3  cmp     ebx, edx
0x140020ef5  jb      short loc_140020F30
0x140020ef7  lea     r12d, [rbx+1]
0x140020efb  lea     rax, ds:10h[r12*8]
0x140020f03  cmp     rax, 1000h
0x140020f09  ja      loc_140020FF9
0x140020f0f  mov     eax, edx
0x140020f11  mov     r8d, ebx
0x140020f14  sub     r8d, edx
0x140020f17  add     rax, 2
0x140020f1b  inc     r8d
0x140020f1e  xor     edx, edx; Val
0x140020f20  shl     r8, 3; Size
0x140020f24  lea     rcx, [rsi+rax*8]; void *
0x140020f28  call    memset
0x140020f2d  mov     edx, r12d
0x140020f30  mov     rax, [rsi+rbx*8+10h]
0x140020f35  and     edi, 3Fh
0x140020f38  bts     rax, rdi
0x140020f3c  mov     [rsi+rbx*8+10h], rax
0x140020f41  inc     r14d
0x140020f44  mov     rbx, [rbp+arg_0]
0x140020f48  jmp     short loc_140020ED9
0x140020f4a  mov     qword ptr [rsi], 0
0x140020f51  cmp     edx, 40h ; '@'
0x140020f54  jz      short loc_140020F65
0x140020f56  mov     ecx, edx
0x140020f58  mov     eax, 1
0x140020f5d  shl     rax, cl
0x140020f60  dec     rax
0x140020f63  jmp     short loc_140020F69
0x140020f65  or      rax, 0FFFFFFFFFFFFFFFFh
0x140020f69  mov     [rsi+8], rax
0x140020f6d  lea     edx, ds:10h[rdx*8]
0x140020f74  mov     r8, [rbp+var_18]
0x140020f78  mov     ecx, 0B5h
0x140020f7d  mov     r9, [r8+28h]
0x140020f81  mov     r8, [r8+18h]
0x140020f85  call    WinHvpVariableHeaderHypercall
0x140020f8a  mov     ebx, eax
0x140020f8c  test    eax, eax
0x140020f8e  js      short loc_140020F9E
0x140020f90  mov     rcx, [rbp+var_50]
0x140020f94  mov     rax, [rbp+arg_10]
0x140020f98  mov     rdx, [rcx]
0x140020f9b  mov     [rax], rdx
0x140020f9e  mov     rcx, [rbp+var_40]
0x140020fa2  mov     rax, [rbp+var_8]
0x140020fa6  call    _guard_dispatch_icall
0x140020fab  cmp     ebx, 0C0350075h
0x140020fb1  jz      short loc_140020FC6
0x140020fb3  cmp     ebx, 0C035000Bh
0x140020fb9  jz      short loc_140020FC6
0x140020fbb  lea     eax, [rbx+3FCAFF7Fh]
0x140020fc1  cmp     eax, 1
0x140020fc4  ja      short loc_14002100B
0x140020fc6  mov     [rsp+80h+var_58], 0
0x140020fcb  mov     r9d, 0B5h
0x140020fd1  mov     r8d, ebx
0x140020fd4  mov     [rsp+80h+var_60], r15d
0x140020fd9  mov     edx, 8000FFFFh
0x140020fde  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140020fe2  call    WinHvpLowMemoryHandler
0x140020fe7  mov     ebx, eax
0x140020fe9  test    eax, eax
0x140020feb  js      short loc_14002100B
0x140020fed  mov     rbx, [rbp+arg_0]
0x140020ff1  inc     r15d
0x140020ff4  jmp     loc_140020EB9
0x140020ff9  mov     rcx, [rbp+var_40]
0x140020ffd  mov     rax, [rbp+var_8]
0x140021001  call    _guard_dispatch_icall
0x140021006  mov     ebx, 0C000000Dh
0x14002100b  mov     eax, ebx
0x14002100d  mov     rbx, [rsp+80h+arg_8]
0x140021015  add     rsp, 80h
0x14002101c  pop     r15
0x14002101e  pop     r14
0x140021020  pop     r13
0x140021022  pop     r12
0x140021024  pop     rdi
0x140021025  pop     rsi
0x140021026  pop     rbp
0x140021027  retn
```
