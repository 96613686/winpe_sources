# CPublicBinding::CPublicBinding(ushort const *,int,ulong *)

- ea: `0x180004330`
- end: `0x18000454f`
- name: `??0CPublicBinding@@QEAA@PEBGHPEAK@Z`
- size: `543`
- prototype: `CPublicBinding *__fastcall(CPublicBinding *__hidden this, const unsigned __int16 *, int, unsigned int *)`
- caller_count: `18`
- callee_count: `9`
- tags: ``

## callers

- `0x180002464`
- `0x18000a7b0`
- `0x18000b448`
- `0x18000e000`
- `0x18000e160`
- `0x1800107c0`
- `0x180010ea0`
- `0x180011550`
- `0x180011a7c`
- `0x180011d30`
- `0x180011ef0`
- `0x180012820`
- `0x180013994`
- `0x180013dd0`
- `0x180013fcc`
- `0x1800142c0`
- `0x180014880`
- `0x180014d40`

## callees

- `0x1800032b4`
- `0x180004330`
- `0x180004558`
- `0x180005b40`
- `0x1800066d0`
- `0x18000f578`
- `0x180020c90`
- `0x180020e40`
- `0x180024a1c`

## import_xrefs

- `RPCRT4!RpcBindingFree` at `0x1800044f9`
- `RPCRT4!RpcBindingFree` at `0x1800044f9`

## string_xrefs

- `0x180004480`: `StringCchCopy failed: %x`

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
  if ( a2 && *a2 && !(unsigned int)CLocalHostAddress::operator==((__int64)this, a2) )
  {
    v8 = 0;
  }
  else
  {
    v6 = &dword_18003FF34;
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
0x180004330  mov     [rsp+arg_8], rbx
0x180004335  mov     [rsp+arg_10], rsi
0x18000433a  push    rdi
0x18000433b  push    r12
0x18000433d  push    r13
0x18000433f  push    r14
0x180004341  push    r15
0x180004343  sub     rsp, 20h
0x180004347  xor     r13d, r13d
0x18000434a  mov     qword ptr [rcx+30h], 1
0x180004352  mov     [rcx], r13
0x180004355  mov     r15, r9
0x180004358  mov     [rcx+8], r13
0x18000435c  mov     r12d, r8d
0x18000435f  mov     [rcx+10h], r13
0x180004363  mov     rbx, rdx
0x180004366  mov     [rcx+18h], r13
0x18000436a  mov     rsi, rcx
0x18000436d  mov     [rcx+20h], r13
0x180004371  mov     [rcx+28h], r13
0x180004375  mov     [rcx+38h], r13
0x180004379  test    rdx, rdx
0x18000437c  jnz     loc_1800044B2
0x180004382  lea     rbx, dword_18003FF34
0x180004389  mov     eax, 1
0x18000438e  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180004395  mov     [rsi+30h], eax
0x180004398  mov     rax, rcx
0x18000439b  nop     dword ptr [rax+rax+00h]
0x1800043a0  cmp     [rbx+rax*2+2], r13w
0x1800043a6  lea     rax, [rax+1]
0x1800043aa  jnz     short loc_1800043A0
0x1800043ac  lea     edi, [rax+1]
0x1800043af  mov     eax, 2
0x1800043b4  mul     rdi
0x1800043b7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800043be  cmovb   rax, rcx
0x1800043c2  mov     rcx, rax; unsigned __int64
0x1800043c5  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800043ca  mov     [rsi+28h], rax
0x1800043ce  mov     rdx, rax
0x1800043d1  test    rax, rax
0x1800043d4  jz      loc_18000451B
0x1800043da  mov     [rsp+48h+arg_0], rbp
0x1800043df  test    rdi, rdi
0x1800043e2  jz      loc_180004538
0x1800043e8  cmp     rdi, 7FFFFFFFh
0x1800043ef  ja      loc_180004525
0x1800043f5  mov     eax, 7FFFFFFEh
0x1800043fa  nop     word ptr [rax+rax+00h]
0x180004400  test    rax, rax
0x180004403  jz      short loc_180004421
0x180004405  movzx   ecx, word ptr [rbx]
0x180004408  test    cx, cx
0x18000440b  jz      short loc_180004421
0x18000440d  mov     [rdx], cx
0x180004410  add     rbx, 2
0x180004414  add     rdx, 2
0x180004418  dec     rax
0x18000441b  sub     rdi, 1
0x18000441f  jnz     short loc_180004400
0x180004421  test    rdi, rdi
0x180004424  lea     rcx, [rdx-2]
0x180004428  mov     ebp, 8007007Ah
0x18000442d  cmovnz  rcx, rdx
0x180004431  cmovnz  ebp, r13d
0x180004435  mov     [rcx], r13w
0x180004439  jz      short loc_180004476
0x18000443b  mov     ebx, r13d
0x18000443e  test    r12d, r12d
0x180004441  jnz     loc_1800044D1
0x180004447  cmp     [rsi+18h], rbx
0x18000444b  jnz     short loc_180004452
0x18000444d  cmp     [rsi+30h], ebx
0x180004450  jz      short loc_180004495
0x180004452  mov     rbp, [rsp+48h+arg_0]
0x180004457  mov     [r15], ebx
0x18000445a  mov     rax, rsi
0x18000445d  mov     rbx, [rsp+48h+arg_8]
0x180004462  mov     rsi, [rsp+48h+arg_10]
0x180004467  add     rsp, 20h
0x18000446b  pop     r15
0x18000446d  pop     r14
0x18000446f  pop     r13
0x180004471  pop     r12
0x180004473  pop     rdi
0x180004474  retn
0x180004476  mov     ecx, ebp; int
0x180004478  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x18000447d  mov     r8d, ebp
0x180004480  lea     rdx, aStringcchcopyF; "StringCchCopy failed: %x"
0x180004487  mov     ecx, 8; int
0x18000448c  mov     ebx, eax
0x18000448e  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180004493  jmp     short loc_180004452
0x180004495  mov     rcx, rsi; this
0x180004498  call    ?OpenSessionContextHandle@CPublicBinding@@AEAAJXZ; CPublicBinding::OpenSessionContextHandle(void)
0x18000449d  cmp     eax, 800706BAh
0x1800044a2  jz      loc_18000452C
0x1800044a8  mov     rcx, rsi; this
0x1800044ab  call    ?CloseSessionContextHandle@CPublicBinding@@AEAAJXZ; CPublicBinding::CloseSessionContextHandle(void)
0x1800044b0  jmp     short loc_180004452
0x1800044b2  cmp     r13w, [rdx]
0x1800044b6  jz      loc_180004382
0x1800044bc  call    ??8CLocalHostAddress@@QEAAHPEBG@Z; CLocalHostAddress::operator==(ushort const *)
0x1800044c1  test    eax, eax
0x1800044c3  jnz     loc_180004382
0x1800044c9  mov     eax, r13d
0x1800044cc  jmp     loc_18000438E
0x1800044d1  mov     rcx, rsi; this
0x1800044d4  call    ?GetUnifiedRpcBinding@CPublicBinding@@QEAAPEAXXZ; CPublicBinding::GetUnifiedRpcBinding(void)
0x1800044d9  mov     rdx, [rsi+18h]; void *
0x1800044dd  test    rdx, rdx
0x1800044e0  jz      loc_180004447
0x1800044e6  mov     rcx, rsi; this
0x1800044e9  call    ?OpenSessionContextHandle@CPublicBinding@@AEAAJPEAX@Z; CPublicBinding::OpenSessionContextHandle(void *)
0x1800044ee  cmp     eax, 800706BAh
0x1800044f3  jnz     short loc_18000450E
0x1800044f5  lea     rcx, [rsi+18h]; Binding
0x1800044f9  call    cs:__imp_RpcBindingFree
0x180004500  nop     dword ptr [rax+rax+00h]
0x180004505  mov     [rsi+18h], r13
0x180004509  jmp     loc_180004447
0x18000450e  mov     rcx, rsi; this
0x180004511  call    ?CloseSessionContextHandle@CPublicBinding@@AEAAJXZ; CPublicBinding::CloseSessionContextHandle(void)
0x180004516  jmp     loc_180004447
0x18000451b  mov     ebx, 8
0x180004520  jmp     loc_180004457
0x180004525  mov     ebp, 80070057h
0x18000452a  jmp     short loc_180004546
0x18000452c  mov     dword ptr [rsi+34h], 1
0x180004533  jmp     loc_1800044A8
0x180004538  mov     ebp, 80070057h
0x18000453d  test    rdi, rdi
0x180004540  jz      loc_180004476
0x180004546  mov     [rax], r13w
0x18000454a  jmp     loc_180004476
```
