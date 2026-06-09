# CPublicBinding::CPublicBinding(ushort const *,int,ulong *)

- ea: `0x180005db0`
- end: `0x180005fc4`
- name: `??0CPublicBinding@@QEAA@PEBGHPEAK@Z`
- size: `532`
- prototype: `CPublicBinding *__fastcall(CPublicBinding *this, unsigned __int16 *, int, unsigned int *)`
- caller_count: `18`
- callee_count: `9`
- tags: ``

## callers

- `0x180003034`
- `0x180003f10`
- `0x180004a30`
- `0x18000c420`
- `0x18000c570`
- `0x18000fca0`
- `0x1800101c0`
- `0x180010610`
- `0x180010aec`
- `0x180010d90`
- `0x180011170`
- `0x180011730`
- `0x180012b14`
- `0x180012f00`
- `0x180013088`
- `0x1800133e0`
- `0x180013910`
- `0x180013d80`

## callees

- `0x180005374`
- `0x180005db0`
- `0x180005fcc`
- `0x180007890`
- `0x180008340`
- `0x18000eadc`
- `0x18001f5f8`
- `0x18001f784`
- `0x1800230ec`

## import_xrefs

- `RPCRT4!RpcBindingFree` at `0x180005f74`
- `RPCRT4!RpcBindingFree` at `0x180005f74`

## string_xrefs

- `0x180005eff`: `StringCchCopy failed: %x`

## pseudocode

```c
CPublicBinding *__fastcall CPublicBinding::CPublicBinding(
        CPublicBinding *this,
        unsigned __int16 *a2,
        int a3,
        unsigned int *a4)
{
  int *v6; // rbx
  int v8; // eax
  __int64 v9; // rax
  unsigned __int64 v11; // rdi
  unsigned __int64 v12; // rax
  _WORD *v13; // rax
  _WORD *v14; // rdx
  __int64 v15; // rax
  _WORD *v16; // rcx
  int v17; // ebp
  unsigned int v18; // ebx
  void *v20; // rdx

  *((_QWORD *)this + 6) = 1;
  *(_QWORD *)this = 0;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  v6 = (int *)a2;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 7) = 0;
  if ( a2 && *a2 && !(unsigned int)CLocalHostAddress::operator==() )
  {
    v8 = 0;
  }
  else
  {
    v6 = &dword_18003D0CC;
    v8 = 1;
  }
  *((_DWORD *)this + 12) = v8;
  v9 = -1;
  while ( *((_WORD *)v6 + ++v9) != 0 )
    ;
  v11 = (unsigned int)(v9 + 1);
  v12 = 2 * v11;
  if ( !is_mul_ok(v11, 2u) )
    v12 = -1;
  v13 = operator new[](v12, (const struct std::nothrow_t *)&std::nothrow);
  *((_QWORD *)this + 5) = v13;
  v14 = v13;
  if ( !v13 )
  {
    v18 = 8;
    goto LABEL_20;
  }
  if ( !v11 )
  {
    v17 = -2147024809;
    goto LABEL_21;
  }
  if ( v11 > 0x7FFFFFFF )
  {
    v17 = -2147024809;
    *v13 = 0;
LABEL_21:
    v18 = ConvertHRESULT2WIN32(v17);
    _DbgPrintMessage(8, "StringCchCopy failed: %x", v17);
    goto LABEL_20;
  }
  v15 = 2147483646;
  do
  {
    if ( !v15 )
      break;
    if ( !*(_WORD *)v6 )
      break;
    *v14 = *(_WORD *)v6;
    v6 = (int *)((char *)v6 + 2);
    ++v14;
    --v15;
    --v11;
  }
  while ( v11 );
  v16 = v14 - 1;
  v17 = -2147024774;
  if ( v11 )
  {
    v16 = v14;
    v17 = 0;
  }
  *v16 = 0;
  if ( !v11 )
    goto LABEL_21;
  v18 = 0;
  if ( a3 )
  {
    CPublicBinding::GetUnifiedRpcBinding(this);
    v20 = (void *)*((_QWORD *)this + 3);
    if ( v20 )
    {
      if ( (unsigned int)CPublicBinding::OpenSessionContextHandle(this, v20) == -2147023174 )
      {
        RpcBindingFree((RPC_BINDING_HANDLE *)this + 3);
        *((_QWORD *)this + 3) = 0;
      }
      else
      {
        CPublicBinding::CloseSessionContextHandle(this);
      }
    }
  }
  if ( !*((_QWORD *)this + 3) && !*((_DWORD *)this + 12) )
  {
    if ( (unsigned int)CPublicBinding::OpenSessionContextHandle((RPC_BINDING_HANDLE *)this) == -2147023174 )
      *((_DWORD *)this + 13) = 1;
    CPublicBinding::CloseSessionContextHandle(this);
  }
LABEL_20:
  *a4 = v18;
  return this;
}

```

## disassembly

```asm
0x180005db0  mov     [rsp+arg_8], rbx
0x180005db5  mov     [rsp+arg_10], rsi
0x180005dba  push    rdi
0x180005dbb  push    r12
0x180005dbd  push    r13
0x180005dbf  push    r14
0x180005dc1  push    r15
0x180005dc3  sub     rsp, 20h
0x180005dc7  xor     r13d, r13d
0x180005dca  mov     qword ptr [rcx+30h], 1
0x180005dd2  mov     [rcx], r13
0x180005dd5  mov     r15, r9
0x180005dd8  mov     [rcx+8], r13
0x180005ddc  mov     r12d, r8d
0x180005ddf  mov     [rcx+10h], r13
0x180005de3  mov     rbx, rdx
0x180005de6  mov     [rcx+18h], r13
0x180005dea  mov     rsi, rcx
0x180005ded  mov     [rcx+20h], r13
0x180005df1  mov     [rcx+28h], r13
0x180005df5  mov     [rcx+38h], r13
0x180005df9  test    rdx, rdx
0x180005dfc  jnz     loc_180005F2D
0x180005e02  lea     rbx, dword_18003D0CC
0x180005e09  mov     eax, 1
0x180005e0e  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180005e15  mov     [rsi+30h], eax
0x180005e18  mov     rax, rcx
0x180005e1b  nop     dword ptr [rax+rax+00h]
0x180005e20  cmp     [rbx+rax*2+2], r13w
0x180005e26  lea     rax, [rax+1]
0x180005e2a  jnz     short loc_180005E20
0x180005e2c  lea     edi, [rax+1]
0x180005e2f  mov     eax, 2
0x180005e34  mul     rdi
0x180005e37  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180005e3e  cmovb   rax, rcx
0x180005e42  mov     rcx, rax; unsigned __int64
0x180005e45  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180005e4a  mov     [rsi+28h], rax
0x180005e4e  mov     rdx, rax
0x180005e51  test    rax, rax
0x180005e54  jz      loc_180005F90
0x180005e5a  mov     [rsp+48h+arg_0], rbp
0x180005e5f  test    rdi, rdi
0x180005e62  jz      loc_180005FAD
0x180005e68  cmp     rdi, 7FFFFFFFh
0x180005e6f  ja      loc_180005F9A
0x180005e75  mov     eax, 7FFFFFFEh
0x180005e7a  nop     word ptr [rax+rax+00h]
0x180005e80  test    rax, rax
0x180005e83  jz      short loc_180005EA1
0x180005e85  movzx   ecx, word ptr [rbx]
0x180005e88  test    cx, cx
0x180005e8b  jz      short loc_180005EA1
0x180005e8d  mov     [rdx], cx
0x180005e90  add     rbx, 2
0x180005e94  add     rdx, 2
0x180005e98  dec     rax
0x180005e9b  sub     rdi, 1
0x180005e9f  jnz     short loc_180005E80
0x180005ea1  test    rdi, rdi
0x180005ea4  lea     rcx, [rdx-2]
0x180005ea8  mov     ebp, 8007007Ah
0x180005ead  cmovnz  rcx, rdx
0x180005eb1  cmovnz  ebp, r13d
0x180005eb5  mov     [rcx], r13w
0x180005eb9  jz      short loc_180005EF5
0x180005ebb  mov     ebx, r13d
0x180005ebe  test    r12d, r12d
0x180005ec1  jnz     loc_180005F4C
0x180005ec7  cmp     [rsi+18h], rbx
0x180005ecb  jnz     short loc_180005ED2
0x180005ecd  cmp     [rsi+30h], ebx
0x180005ed0  jz      short loc_180005F14
0x180005ed2  mov     rbp, [rsp+48h+arg_0]
0x180005ed7  mov     [r15], ebx
0x180005eda  mov     rax, rsi
0x180005edd  mov     rbx, [rsp+48h+arg_8]
0x180005ee2  mov     rsi, [rsp+48h+arg_10]
0x180005ee7  add     rsp, 20h
0x180005eeb  pop     r15
0x180005eed  pop     r14
0x180005eef  pop     r13
0x180005ef1  pop     r12
0x180005ef3  pop     rdi
0x180005ef4  retn
0x180005ef5  mov     ecx, ebp; int
0x180005ef7  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x180005efc  mov     r8d, ebp
0x180005eff  lea     rdx, aStringcchcopyF; "StringCchCopy failed: %x"
0x180005f06  mov     ecx, 8; int
0x180005f0b  mov     ebx, eax
0x180005f0d  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180005f12  jmp     short loc_180005ED2
0x180005f14  mov     rcx, rsi; this
0x180005f17  call    ?OpenSessionContextHandle@CPublicBinding@@AEAAJXZ; CPublicBinding::OpenSessionContextHandle(void)
0x180005f1c  cmp     eax, 800706BAh
0x180005f21  jz      short loc_180005FA1
0x180005f23  mov     rcx, rsi; this
0x180005f26  call    ?CloseSessionContextHandle@CPublicBinding@@AEAAJXZ; CPublicBinding::CloseSessionContextHandle(void)
0x180005f2b  jmp     short loc_180005ED2
0x180005f2d  cmp     r13w, [rdx]
0x180005f31  jz      loc_180005E02
0x180005f37  call    ??8CLocalHostAddress@@QEAAHPEBG@Z; CLocalHostAddress::operator==(ushort const *)
0x180005f3c  test    eax, eax
0x180005f3e  jnz     loc_180005E02
0x180005f44  mov     eax, r13d
0x180005f47  jmp     loc_180005E0E
0x180005f4c  mov     rcx, rsi; this
0x180005f4f  call    ?GetUnifiedRpcBinding@CPublicBinding@@QEAAPEAXXZ; CPublicBinding::GetUnifiedRpcBinding(void)
0x180005f54  mov     rdx, [rsi+18h]; void *
0x180005f58  test    rdx, rdx
0x180005f5b  jz      loc_180005EC7
0x180005f61  mov     rcx, rsi; this
0x180005f64  call    ?OpenSessionContextHandle@CPublicBinding@@AEAAJPEAX@Z; CPublicBinding::OpenSessionContextHandle(void *)
0x180005f69  cmp     eax, 800706BAh
0x180005f6e  jnz     short loc_180005F83
0x180005f70  lea     rcx, [rsi+18h]; Binding
0x180005f74  call    cs:__imp_RpcBindingFree
0x180005f7a  mov     [rsi+18h], r13
0x180005f7e  jmp     loc_180005EC7
0x180005f83  mov     rcx, rsi; this
0x180005f86  call    ?CloseSessionContextHandle@CPublicBinding@@AEAAJXZ; CPublicBinding::CloseSessionContextHandle(void)
0x180005f8b  jmp     loc_180005EC7
0x180005f90  mov     ebx, 8
0x180005f95  jmp     loc_180005ED7
0x180005f9a  mov     ebp, 80070057h
0x180005f9f  jmp     short loc_180005FBB
0x180005fa1  mov     dword ptr [rsi+34h], 1
0x180005fa8  jmp     loc_180005F23
0x180005fad  mov     ebp, 80070057h
0x180005fb2  test    rdi, rdi
0x180005fb5  jz      loc_180005EF5
0x180005fbb  mov     [rax], r13w
0x180005fbf  jmp     loc_180005EF5
```
