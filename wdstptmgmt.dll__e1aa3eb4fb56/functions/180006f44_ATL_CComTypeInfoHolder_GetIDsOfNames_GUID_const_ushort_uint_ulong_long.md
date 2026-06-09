# ATL::CComTypeInfoHolder::GetIDsOfNames(_GUID const &,ushort * *,uint,ulong,long *)

- ea: `0x180006f44`
- end: `0x18000703c`
- name: `?GetIDsOfNames@CComTypeInfoHolder@ATL@@QEAAJAEBU_GUID@@PEAPEAGIKPEAJ@Z`
- size: `248`
- prototype: `__int64 __fastcall(ATL::CComTypeInfoHolder *__hidden this, const struct _GUID *, unsigned __int16 **, unsigned int, LCID lcid, int *)`
- caller_count: `20`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180006f30`
- `0x180008460`
- `0x180008eb0`
- `0x18000a610`
- `0x18000b970`
- `0x18000d160`
- `0x18000f5b0`
- `0x1800103f0`
- `0x180011bb0`
- `0x180011bd0`
- `0x180011bf0`
- `0x180011c10`
- `0x180011c30`
- `0x180014bf0`
- `0x180015820`
- `0x180016780`
- `0x1800178b0`
- `0x1800186d0`
- `0x180019060`
- `0x180019ae0`

## callees

- `0x180005c44`
- `0x180006f44`
- `0x180007044`
- `0x18001e9b6`
- `0x180020010`

## pseudocode

```c
__int64 __fastcall ATL::CComTypeInfoHolder::GetIDsOfNames(
        ATL::CComTypeInfoHolder *this,
        const struct _GUID *a2,
        const unsigned __int16 **a3,
        unsigned int a4,
        LCID lcid,
        int *a6)
{
  __int64 result; // rax
  __int64 v10; // rbp
  int v11; // r12d
  int v12; // esi
  __int64 v13; // r14
  __int64 v14; // rbx

  result = 0;
  if ( !*((_QWORD *)this + 3) || !*((_QWORD *)this + 5) )
    result = ATL::CComTypeInfoHolder::GetTI(this, lcid);
  if ( *((_QWORD *)this + 3) )
  {
    v10 = *((_QWORD *)this + 5);
    if ( v10 && a4 == 1 )
    {
      v11 = ocslen(*a3);
      v12 = *((_DWORD *)this + 12) - 1;
      v13 = v12;
      v14 = v10 + 16LL * v12;
      while ( v13 >= 0 )
      {
        if ( v11 == *(_DWORD *)(v14 + 8) && !memcmp_0(*(const void **)v14, *a3, 2LL * *(int *)(v14 + 8)) )
        {
          *a6 = *(_DWORD *)(v10 + 16LL * v12 + 12);
          return 0;
        }
        --v12;
        --v13;
        v14 -= 16;
      }
    }
    return (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 **, _QWORD, int *))(**((_QWORD **)this + 3) + 80LL))(
             *((_QWORD *)this + 3),
             a3,
             a4,
             a6);
  }
  return result;
}

```

## disassembly

```asm
0x180006f44  mov     [rsp+arg_0], rbx
0x180006f49  mov     [rsp+arg_8], rbp
0x180006f4e  mov     [rsp+arg_10], rsi
0x180006f53  push    rdi
0x180006f54  push    r12
0x180006f56  push    r13
0x180006f58  push    r14
0x180006f5a  push    r15
0x180006f5c  sub     rsp, 30h
0x180006f60  xor     eax, eax
0x180006f62  mov     r15d, r9d
0x180006f65  mov     r13, r8
0x180006f68  mov     rdi, rcx
0x180006f6b  cmp     [rcx+18h], rax
0x180006f6f  jz      short loc_180006F77
0x180006f71  cmp     [rcx+28h], rax
0x180006f75  jnz     short loc_180006F83
0x180006f77  mov     edx, [rsp+58h+lcid]; lcid
0x180006f7e  call    ?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z; ATL::CComTypeInfoHolder::GetTI(ulong)
0x180006f83  cmp     qword ptr [rdi+18h], 0
0x180006f88  jz      loc_18000701E
0x180006f8e  mov     rbp, [rdi+28h]
0x180006f92  test    rbp, rbp
0x180006f95  jz      short loc_180007000
0x180006f97  cmp     r15d, 1
0x180006f9b  jnz     short loc_180007000
0x180006f9d  mov     rcx, [r13+0]; unsigned __int16 *
0x180006fa1  call    ?ocslen@@YAHPEBG@Z; ocslen(ushort const *)
0x180006fa6  mov     esi, [rdi+30h]
0x180006fa9  mov     r12d, eax
0x180006fac  dec     esi
0x180006fae  movsxd  r14, esi
0x180006fb1  mov     rbx, r14
0x180006fb4  shl     rbx, 4
0x180006fb8  add     rbx, rbp
0x180006fbb  test    r14, r14
0x180006fbe  js      short loc_180007000
0x180006fc0  cmp     r12d, [rbx+8]
0x180006fc4  jnz     short loc_180006FDD
0x180006fc6  movsxd  r8, dword ptr [rbx+8]
0x180006fca  mov     rdx, [r13+0]; Buf2
0x180006fce  add     r8, r8; Size
0x180006fd1  mov     rcx, [rbx]; Buf1
0x180006fd4  call    memcmp_0
0x180006fd9  test    eax, eax
0x180006fdb  jz      short loc_180006FE8
0x180006fdd  dec     esi
0x180006fdf  dec     r14
0x180006fe2  sub     rbx, 10h
0x180006fe6  jmp     short loc_180006FBB
0x180006fe8  mov     rax, [rsp+58h+arg_28]
0x180006ff0  movsxd  rcx, esi
0x180006ff3  add     rcx, rcx
0x180006ff6  mov     ecx, [rbp+rcx*8+0Ch]
0x180006ffa  mov     [rax], ecx
0x180006ffc  xor     eax, eax
0x180006ffe  jmp     short loc_18000701E
0x180007000  mov     rcx, [rdi+18h]
0x180007004  mov     r8d, r15d
0x180007007  mov     r9, [rsp+58h+arg_28]
0x18000700f  mov     rdx, r13
0x180007012  mov     rax, [rcx]
0x180007015  mov     rax, [rax+50h]
0x180007019  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000701e  mov     rbx, [rsp+58h+arg_0]
0x180007023  mov     rbp, [rsp+58h+arg_8]
0x180007028  mov     rsi, [rsp+58h+arg_10]
0x18000702d  add     rsp, 30h
0x180007031  pop     r15
0x180007033  pop     r14
0x180007035  pop     r13
0x180007037  pop     r12
0x180007039  pop     rdi
0x18000703a  retn
```
