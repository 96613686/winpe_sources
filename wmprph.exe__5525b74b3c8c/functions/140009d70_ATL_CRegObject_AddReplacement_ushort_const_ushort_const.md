# ATL::CRegObject::AddReplacement(ushort const *,ushort const *)

- ea: `0x140009d70`
- end: `0x140009ec2`
- name: `?AddReplacement@CRegObject@ATL@@QEAAJPEBG0@Z`
- size: `338`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, service_task`

## callers

- `0x14000c860`

## callees

- `0x140001008`
- `0x140001014`
- `0x140009d70`
- `0x14000e3e0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x140009e43`
- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x140009e43`
- `ole32!CoTaskMemAlloc` at `0x140009de3`
- `ole32!CoTaskMemAlloc` at `0x140009df7`
- `ole32!CoTaskMemAlloc` at `0x140009de3`
- `ole32!CoTaskMemAlloc` at `0x140009df7`
- `ole32!CoTaskMemFree` at `0x140009e51`
- `ole32!CoTaskMemFree` at `0x140009e5b`
- `ole32!CoTaskMemFree` at `0x140009e8f`
- `ole32!CoTaskMemFree` at `0x140009e99`
- `ole32!CoTaskMemFree` at `0x140009e51`
- `ole32!CoTaskMemFree` at `0x140009e5b`
- `ole32!CoTaskMemFree` at `0x140009e8f`
- `ole32!CoTaskMemFree` at `0x140009e99`

## pseudocode

```c
__int64 __fastcall ATL::CRegObject::AddReplacement(
        ATL::CRegObject *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  void **v6; // rdi
  __int64 v7; // rsi
  __int64 v8; // rax
  SIZE_T v9; // r15
  unsigned int v10; // esi
  LPVOID v11; // rax
  void *v12; // rcx
  int v13; // eax
  __int64 v14; // rcx
  int v15; // eax
  __int64 v16; // rax
  unsigned int v17; // edx

  v6 = (void **)operator new(0x10u);
  if ( !v6 )
    return (unsigned int)-2147024882;
  v7 = -1;
  if ( a2 )
  {
    v8 = -1;
    do
      ++v8;
    while ( a2[v8] );
  }
  else
  {
    LODWORD(v8) = 0;
  }
  if ( a3 )
  {
    do
      ++v7;
    while ( a3[v7] );
  }
  else
  {
    LODWORD(v7) = 0;
  }
  v9 = (unsigned int)(2 * v8 + 2);
  *v6 = CoTaskMemAlloc(v9);
  v10 = 2 * v7 + 2;
  v11 = CoTaskMemAlloc(v10);
  v12 = *v6;
  v6[1] = v11;
  if ( !v12 || !v11 )
  {
    CoTaskMemFree(v12);
    CoTaskMemFree(v6[1]);
    operator delete(v6, 0x10u);
    return (unsigned int)-2147024882;
  }
  memcpy_0(v12, a2, (unsigned int)v9);
  memcpy_0(v6[1], a3, v10);
  v13 = *((_DWORD *)this + 3);
  if ( *((_DWORD *)this + 2) == v13 )
  {
    v14 = *(_QWORD *)this;
    v15 = 2 * v13;
    *((_DWORD *)this + 3) = v15;
    v16 = _o_realloc(v14, 8LL * v15);
    if ( !v16 )
    {
      CoTaskMemFree(*v6);
      CoTaskMemFree(v6[1]);
      operator delete(v6, 0x10u);
      *((int *)this + 3) /= 2;
      return (unsigned int)-2147024882;
    }
    *(_QWORD *)this = v16;
  }
  v17 = 0;
  *(_QWORD *)(*(_QWORD *)this + 8LL * (int)(*((_DWORD *)this + 2))++) = v6;
  return v17;
}

```

## disassembly

```asm
0x140009d70  push    rbx
0x140009d72  push    rbp
0x140009d73  push    rsi
0x140009d74  push    rdi
0x140009d75  push    r12
0x140009d77  push    r13
0x140009d79  push    r14
0x140009d7b  push    r15
0x140009d7d  sub     rsp, 28h
0x140009d81  mov     rbx, rcx
0x140009d84  mov     r13d, 10h
0x140009d8a  mov     ecx, r13d; Size
0x140009d8d  mov     r14, r8
0x140009d90  mov     rbp, rdx
0x140009d93  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140009d98  xor     r12d, r12d
0x140009d9b  mov     rdi, rax
0x140009d9e  test    rax, rax
0x140009da1  jz      loc_140009EAA
0x140009da7  or      rsi, 0FFFFFFFFFFFFFFFFh
0x140009dab  test    rbp, rbp
0x140009dae  jnz     short loc_140009DB5
0x140009db0  mov     eax, r12d
0x140009db3  jmp     short loc_140009DC3
0x140009db5  mov     rax, rsi
0x140009db8  inc     rax
0x140009dbb  cmp     [rbp+rax*2+0], r12w
0x140009dc1  jnz     short loc_140009DB8
0x140009dc3  test    r14, r14
0x140009dc6  jnz     short loc_140009DCD
0x140009dc8  mov     esi, r12d
0x140009dcb  jmp     short loc_140009DD7
0x140009dcd  inc     rsi
0x140009dd0  cmp     [r14+rsi*2], r12w
0x140009dd5  jnz     short loc_140009DCD
0x140009dd7  lea     eax, ds:2[rax*2]
0x140009dde  mov     ecx, eax; cb
0x140009de0  mov     r15d, eax
0x140009de3  call    cs:__imp_CoTaskMemAlloc
0x140009de9  mov     [rdi], rax
0x140009dec  lea     eax, ds:2[rsi*2]
0x140009df3  mov     ecx, eax; cb
0x140009df5  mov     esi, eax
0x140009df7  call    cs:__imp_CoTaskMemAlloc
0x140009dfd  mov     rcx, [rdi]; void *
0x140009e00  mov     [rdi+8], rax
0x140009e04  test    rcx, rcx
0x140009e07  jz      loc_140009E8F
0x140009e0d  test    rax, rax
0x140009e10  jz      short loc_140009E8F
0x140009e12  mov     r8d, r15d; Size
0x140009e15  mov     rdx, rbp; Src
0x140009e18  call    memcpy_0
0x140009e1d  mov     rcx, [rdi+8]; void *
0x140009e21  mov     r8d, esi; Size
0x140009e24  mov     rdx, r14; Src
0x140009e27  call    memcpy_0
0x140009e2c  mov     eax, [rbx+0Ch]
0x140009e2f  cmp     [rbx+8], eax
0x140009e32  jnz     short loc_140009E7C
0x140009e34  mov     rcx, [rbx]
0x140009e37  add     eax, eax
0x140009e39  movsxd  rdx, eax
0x140009e3c  shl     rdx, 3
0x140009e40  mov     [rbx+0Ch], eax
0x140009e43  call    cs:__imp__o_realloc
0x140009e49  test    rax, rax
0x140009e4c  jnz     short loc_140009E79
0x140009e4e  mov     rcx, [rdi]; pv
0x140009e51  call    cs:__imp_CoTaskMemFree
0x140009e57  mov     rcx, [rdi+8]; pv
0x140009e5b  call    cs:__imp_CoTaskMemFree
0x140009e61  mov     rdx, r13; unsigned __int64
0x140009e64  mov     rcx, rdi; void *
0x140009e67  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140009e6c  mov     eax, [rbx+0Ch]
0x140009e6f  cdq
0x140009e70  sub     eax, edx
0x140009e72  sar     eax, 1
0x140009e74  mov     [rbx+0Ch], eax
0x140009e77  jmp     short loc_140009EAA
0x140009e79  mov     [rbx], rax
0x140009e7c  movsxd  rcx, dword ptr [rbx+8]
0x140009e80  mov     edx, r12d
0x140009e83  mov     rax, [rbx]
0x140009e86  mov     [rax+rcx*8], rdi
0x140009e8a  inc     dword ptr [rbx+8]
0x140009e8d  jmp     short loc_140009EAF
0x140009e8f  call    cs:__imp_CoTaskMemFree
0x140009e95  mov     rcx, [rdi+8]; pv
0x140009e99  call    cs:__imp_CoTaskMemFree
0x140009e9f  mov     rdx, r13; unsigned __int64
0x140009ea2  mov     rcx, rdi; void *
0x140009ea5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140009eaa  mov     edx, 8007000Eh
0x140009eaf  mov     eax, edx
0x140009eb1  add     rsp, 28h
0x140009eb5  pop     r15
0x140009eb7  pop     r14
0x140009eb9  pop     r13
0x140009ebb  pop     r12
0x140009ebd  pop     rdi
0x140009ebe  pop     rsi
0x140009ebf  pop     rbp
0x140009ec0  pop     rbx
0x140009ec1  retn
```
