# Worker::CopyContext(_CONTEXT *)

- ea: `0x100490e60`
- end: `0x10049116c`
- name: `?CopyContext@Worker@@QEAA?AW4SOS_RESULT@@PEAU_CONTEXT@@@Z`
- size: `780`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x100403070`
- `0x100404bf2`
- `0x100411fb0`
- `0x100435af0`
- `0x100490e60`

## import_xrefs

- `KERNEL32!GetThreadContext` at `0x10049106b`
- `KERNEL32!GetThreadContext` at `0x10049106b`
- `api-ms-win-crt-runtime-l1-1-0!_resetstkoflw` at `0x100491132`
- `api-ms-win-crt-runtime-l1-1-0!_resetstkoflw` at `0x100491132`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x100490f5d`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x10049104c`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x10049107d`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x100490f5d`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x10049104c`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x10049107d`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x100490f69`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x100491058`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x100491089`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x100490f69`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x100491058`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x100491089`

## pseudocode

```c
__int64 __fastcall Worker::CopyContext(__int64 a1, _OWORD *a2)
{
  _OWORD *v2; // rbx
  unsigned int v3; // esi
  BOOL ThreadContext; // r15d
  __int64 v5; // rax
  _OWORD *v6; // rax
  __int64 v7; // rdi
  __int64 v8; // rdi
  void *v9; // r14
  _OWORD *v10; // rax
  CONTEXT *p_Context; // rcx
  __int64 v12; // rdi
  __int64 v13; // rdx
  CONTEXT *v14; // rax
  unsigned int v15; // eax
  CONTEXT Context; // [rsp+30h] [rbp-1368h] BYREF

  v2 = a2;
  v3 = 0;
  ThreadContext = 0;
  if ( (*(_BYTE *)(a1 + 800) & 8) != 0 )
  {
    v5 = *(_QWORD *)(a1 + 640);
    if ( v5 )
    {
      v6 = (_OWORD *)(v5 + 48);
      if ( a2 )
      {
        if ( v6 )
        {
          v7 = 9;
          do
          {
            *v2 = *v6;
            v2[1] = v6[1];
            v2[2] = v6[2];
            v2[3] = v6[3];
            v2[4] = v6[4];
            v2[5] = v6[5];
            v2[6] = v6[6];
            v2 += 8;
            *(v2 - 1) = v6[7];
            v6 += 8;
            --v7;
          }
          while ( v7 );
          *v2 = *v6;
          v2[1] = v6[1];
          v2[2] = v6[2];
          v2[3] = v6[3];
          v2[4] = v6[4];
          return v3;
        }
        memset_0(a2, 0, 0x4D0u);
      }
      *_errno() = 22;
      _invalid_parameter_noinfo();
      return v3;
    }
  }
  v8 = *(_QWORD *)(a1 + 624);
  v9 = *(void **)(v8 + 296);
  if ( v9 || (SystemThread::CreateThreadHandle(*(SystemThread **)(a1 + 624)), (v9 = *(void **)(v8 + 296)) != 0) )
  {
    if ( v2 )
    {
      v10 = v2;
      p_Context = &Context;
      v12 = 9;
      v13 = 9;
      do
      {
        *(_OWORD *)&p_Context->P1Home = *v10;
        *(_OWORD *)&p_Context->P3Home = v10[1];
        *(_OWORD *)&p_Context->P5Home = v10[2];
        *(_OWORD *)&p_Context->ContextFlags = v10[3];
        *(_OWORD *)&p_Context->SegGs = v10[4];
        *(_OWORD *)&p_Context->Dr1 = v10[5];
        *(_OWORD *)&p_Context->Dr3 = v10[6];
        p_Context = (CONTEXT *)((char *)p_Context + 128);
        *(_OWORD *)&p_Context[-1].LastExceptionToRip = v10[7];
        v10 += 8;
        --v13;
      }
      while ( v13 );
      *(_OWORD *)&p_Context->P1Home = *v10;
      *(_OWORD *)&p_Context->P3Home = v10[1];
      *(_OWORD *)&p_Context->P5Home = v10[2];
      *(_OWORD *)&p_Context->ContextFlags = v10[3];
      *(_OWORD *)&p_Context->SegGs = v10[4];
    }
    else
    {
      memset_0(&Context, 0, 0x1340u);
      *_errno() = 22;
      _invalid_parameter_noinfo();
      v12 = 9;
    }
    ThreadContext = GetThreadContext(v9, &Context);
    if ( v2 )
    {
      v14 = &Context;
      do
      {
        *v2 = *(_OWORD *)&v14->P1Home;
        v2[1] = *(_OWORD *)&v14->P3Home;
        v2[2] = *(_OWORD *)&v14->P5Home;
        v2[3] = *(_OWORD *)&v14->ContextFlags;
        v2[4] = *(_OWORD *)&v14->SegGs;
        v2[5] = *(_OWORD *)&v14->Dr1;
        v2[6] = *(_OWORD *)&v14->Dr3;
        v2 += 8;
        *(v2 - 1) = *(_OWORD *)&v14->Dr7;
        v14 = (CONTEXT *)((char *)v14 + 128);
        --v12;
      }
      while ( v12 );
      *v2 = *(_OWORD *)&v14->P1Home;
      v2[1] = *(_OWORD *)&v14->P3Home;
      v2[2] = *(_OWORD *)&v14->P5Home;
      v2[3] = *(_OWORD *)&v14->ContextFlags;
      v2[4] = *(_OWORD *)&v14->SegGs;
    }
    else
    {
      *_errno() = 22;
      _invalid_parameter_noinfo();
    }
  }
  v15 = 0x80000000;
  if ( ThreadContext )
    return 0;
  return v15;
}

```

## disassembly

```asm
0x100490e60  mov     [rsp+arg_10], rbx
0x100490e65  mov     [rsp+arg_18], rsi
0x100490e6a  push    rdi
0x100490e6b  push    r14
0x100490e6d  push    r15
0x100490e6f  mov     eax, 1380h
0x100490e74  call    _alloca_probe
0x100490e79  sub     rsp, rax
0x100490e7c  mov     rax, cs:__security_cookie
0x100490e83  xor     rax, rsp
0x100490e86  mov     [rsp+1398h+var_28], rax
0x100490e8e  mov     rbx, rdx
0x100490e91  xor     esi, esi
0x100490e93  mov     r15d, esi
0x100490e96  test    byte ptr [rcx+320h], 8
0x100490e9d  jz      loc_100490F74
0x100490ea3  mov     rax, [rcx+280h]
0x100490eaa  test    rax, rax
0x100490ead  jz      loc_100490F74
0x100490eb3  add     rax, 30h ; '0'
0x100490eb7  test    rdx, rdx
0x100490eba  jz      loc_100490F5D
0x100490ec0  test    rax, rax
0x100490ec3  jz      loc_100490F4D
0x100490ec9  lea     edi, [rsi+9]
0x100490ecc  nop     dword ptr [rax+00h]
0x100490ed0  movups  xmm0, xmmword ptr [rax]
0x100490ed3  movups  xmmword ptr [rbx], xmm0
0x100490ed6  movups  xmm1, xmmword ptr [rax+10h]
0x100490eda  movups  xmmword ptr [rbx+10h], xmm1
0x100490ede  movups  xmm0, xmmword ptr [rax+20h]
0x100490ee2  movups  xmmword ptr [rbx+20h], xmm0
0x100490ee6  movups  xmm1, xmmword ptr [rax+30h]
0x100490eea  movups  xmmword ptr [rbx+30h], xmm1
0x100490eee  movups  xmm0, xmmword ptr [rax+40h]
0x100490ef2  movups  xmmword ptr [rbx+40h], xmm0
0x100490ef6  movups  xmm1, xmmword ptr [rax+50h]
0x100490efa  movups  xmmword ptr [rbx+50h], xmm1
0x100490efe  movups  xmm0, xmmword ptr [rax+60h]
0x100490f02  movups  xmmword ptr [rbx+60h], xmm0
0x100490f06  lea     rbx, [rbx+80h]
0x100490f0d  movups  xmm1, xmmword ptr [rax+70h]
0x100490f11  movups  xmmword ptr [rbx-10h], xmm1
0x100490f15  lea     rax, [rax+80h]
0x100490f1c  sub     rdi, 1
0x100490f20  jnz     short loc_100490ED0
0x100490f22  movups  xmm0, xmmword ptr [rax]
0x100490f25  movups  xmmword ptr [rbx], xmm0
0x100490f28  movups  xmm1, xmmword ptr [rax+10h]
0x100490f2c  movups  xmmword ptr [rbx+10h], xmm1
0x100490f30  movups  xmm0, xmmword ptr [rax+20h]
0x100490f34  movups  xmmword ptr [rbx+20h], xmm0
0x100490f38  movups  xmm1, xmmword ptr [rax+30h]
0x100490f3c  movups  xmmword ptr [rbx+30h], xmm1
0x100490f40  movups  xmm0, xmmword ptr [rax+40h]
0x100490f44  movups  xmmword ptr [rbx+40h], xmm0
0x100490f48  jmp     loc_100491141
0x100490f4d  xor     edx, edx; Val
0x100490f4f  mov     r8d, 4D0h; Size
0x100490f55  mov     rcx, rbx; void *
0x100490f58  call    memset_0
0x100490f5d  call    cs:__imp__errno
0x100490f63  mov     dword ptr [rax], 16h
0x100490f69  call    cs:__imp__invalid_parameter_noinfo
0x100490f6f  jmp     loc_100491141
0x100490f74  mov     rdi, [rcx+270h]
0x100490f7b  mov     r14, [rdi+128h]
0x100490f82  test    r14, r14
0x100490f85  jnz     short loc_100490F9F
0x100490f87  mov     rcx, rdi; this
0x100490f8a  call    ?CreateThreadHandle@SystemThread@@AEAAXXZ; SystemThread::CreateThreadHandle(void)
0x100490f8f  mov     r14, [rdi+128h]
0x100490f96  test    r14, r14
0x100490f99  jz      loc_100491118
0x100490f9f  test    rbx, rbx
0x100490fa2  jz      loc_10049103A
0x100490fa8  mov     rax, rbx
0x100490fab  lea     rcx, [rsp+1398h+Context]
0x100490fb0  mov     edi, 9
0x100490fb5  mov     edx, edi
0x100490fb7  nop     word ptr [rax+rax+00000000h]
0x100490fc0  movups  xmm0, xmmword ptr [rax]
0x100490fc3  movups  xmmword ptr [rcx], xmm0
0x100490fc6  movups  xmm1, xmmword ptr [rax+10h]
0x100490fca  movups  xmmword ptr [rcx+10h], xmm1
0x100490fce  movups  xmm0, xmmword ptr [rax+20h]
0x100490fd2  movups  xmmword ptr [rcx+20h], xmm0
0x100490fd6  movups  xmm1, xmmword ptr [rax+30h]
0x100490fda  movups  xmmword ptr [rcx+30h], xmm1
0x100490fde  movups  xmm0, xmmword ptr [rax+40h]
0x100490fe2  movups  xmmword ptr [rcx+40h], xmm0
0x100490fe6  movups  xmm1, xmmword ptr [rax+50h]
0x100490fea  movups  xmmword ptr [rcx+50h], xmm1
0x100490fee  movups  xmm0, xmmword ptr [rax+60h]
0x100490ff2  movups  xmmword ptr [rcx+60h], xmm0
0x100490ff6  lea     rcx, [rcx+80h]
0x100490ffd  movups  xmm1, xmmword ptr [rax+70h]
0x100491001  movups  xmmword ptr [rcx-10h], xmm1
0x100491005  lea     rax, [rax+80h]
0x10049100c  sub     rdx, 1
0x100491010  jnz     short loc_100490FC0
0x100491012  movups  xmm0, xmmword ptr [rax]
0x100491015  movups  xmmword ptr [rcx], xmm0
0x100491018  movups  xmm1, xmmword ptr [rax+10h]
0x10049101c  movups  xmmword ptr [rcx+10h], xmm1
0x100491020  movups  xmm0, xmmword ptr [rax+20h]
0x100491024  movups  xmmword ptr [rcx+20h], xmm0
0x100491028  movups  xmm1, xmmword ptr [rax+30h]
0x10049102c  movups  xmmword ptr [rcx+30h], xmm1
0x100491030  movups  xmm0, xmmword ptr [rax+40h]
0x100491034  movups  xmmword ptr [rcx+40h], xmm0
0x100491038  jmp     short loc_100491063
0x10049103a  xor     edx, edx; Val
0x10049103c  mov     r8d, 1340h; Size
0x100491042  lea     rcx, [rsp+1398h+Context]; void *
0x100491047  call    memset_0
0x10049104c  call    cs:__imp__errno
0x100491052  mov     dword ptr [rax], 16h
0x100491058  call    cs:__imp__invalid_parameter_noinfo
0x10049105e  mov     edi, 9
0x100491063  lea     rdx, [rsp+1398h+Context]; lpContext
0x100491068  mov     rcx, r14; hThread
0x10049106b  call    cs:__imp_GetThreadContext
0x100491071  mov     r15d, eax
0x100491074  mov     [rsp+1398h+var_1374], eax
0x100491078  test    rbx, rbx
0x10049107b  jnz     short loc_100491094
0x10049107d  call    cs:__imp__errno
0x100491083  mov     dword ptr [rax], 16h
0x100491089  call    cs:__imp__invalid_parameter_noinfo
0x10049108f  jmp     loc_100491118
0x100491094  lea     rax, [rsp+1398h+Context]
0x100491099  nop     dword ptr [rax+00000000h]
0x1004910a0  movups  xmm0, xmmword ptr [rax]
0x1004910a3  movups  xmmword ptr [rbx], xmm0
0x1004910a6  movups  xmm1, xmmword ptr [rax+10h]
0x1004910aa  movups  xmmword ptr [rbx+10h], xmm1
0x1004910ae  movups  xmm0, xmmword ptr [rax+20h]
0x1004910b2  movups  xmmword ptr [rbx+20h], xmm0
0x1004910b6  movups  xmm1, xmmword ptr [rax+30h]
0x1004910ba  movups  xmmword ptr [rbx+30h], xmm1
0x1004910be  movups  xmm0, xmmword ptr [rax+40h]
0x1004910c2  movups  xmmword ptr [rbx+40h], xmm0
0x1004910c6  movups  xmm1, xmmword ptr [rax+50h]
0x1004910ca  movups  xmmword ptr [rbx+50h], xmm1
0x1004910ce  movups  xmm0, xmmword ptr [rax+60h]
0x1004910d2  movups  xmmword ptr [rbx+60h], xmm0
0x1004910d6  lea     rbx, [rbx+80h]
0x1004910dd  movups  xmm1, xmmword ptr [rax+70h]
0x1004910e1  movups  xmmword ptr [rbx-10h], xmm1
0x1004910e5  lea     rax, [rax+80h]
0x1004910ec  sub     rdi, 1
0x1004910f0  jnz     short loc_1004910A0
0x1004910f2  movups  xmm0, xmmword ptr [rax]
0x1004910f5  movups  xmmword ptr [rbx], xmm0
0x1004910f8  movups  xmm1, xmmword ptr [rax+10h]
0x1004910fc  movups  xmmword ptr [rbx+10h], xmm1
0x100491100  movups  xmm0, xmmword ptr [rax+20h]
0x100491104  movups  xmmword ptr [rbx+20h], xmm0
0x100491108  movups  xmm1, xmmword ptr [rax+30h]
0x10049110c  movups  xmmword ptr [rbx+30h], xmm1
0x100491110  movups  xmm0, xmmword ptr [rax+40h]
0x100491114  movups  xmmword ptr [rbx+40h], xmm0
0x100491118  mov     eax, 80000000h
0x10049111d  test    r15d, r15d
0x100491120  cmovnz  eax, esi
0x100491123  mov     esi, eax
0x100491125  mov     [rsp+1398h+var_1378], eax
0x100491129  jmp     short loc_100491141
0x10049112b  cmp     eax, 0C00000FDh
0x100491130  jnz     short loc_100491138
0x100491132  call    cs:__imp__resetstkoflw
0x100491138  mov     esi, 80000000h
0x10049113d  mov     [rsp+1398h+var_1378], esi
0x100491141  mov     eax, esi
0x100491143  mov     rcx, [rsp+1398h+var_28]
0x10049114b  xor     rcx, rsp; StackCookie
0x10049114e  call    __security_check_cookie
0x100491153  lea     r11, [rsp+1398h+var_18]
0x10049115b  mov     rbx, [r11+30h]
0x10049115f  mov     rsi, [r11+38h]
0x100491163  mov     rsp, r11
0x100491166  pop     r15
0x100491168  pop     r14
0x10049116a  pop     rdi
0x10049116b  retn
```
