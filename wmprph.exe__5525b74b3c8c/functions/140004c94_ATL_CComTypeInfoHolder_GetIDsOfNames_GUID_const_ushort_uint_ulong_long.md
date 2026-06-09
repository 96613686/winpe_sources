# ATL::CComTypeInfoHolder::GetIDsOfNames(_GUID const &,ushort * *,uint,ulong,long *)

- ea: `0x140004c94`
- end: `0x140004d71`
- name: `?GetIDsOfNames@CComTypeInfoHolder@ATL@@QEAAJAEBU_GUID@@PEAPEAGIKPEAJ@Z`
- size: `221`
- prototype: `__int64 __fastcall(ATL::CComTypeInfoHolder *__hidden this, const struct _GUID *, unsigned __int16 **, unsigned int, LCID lcid, int *)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140004c60`
- `0x140004c80`

## callees

- `0x140004c94`
- `0x1400050b8`
- `0x14000e3d4`
- `0x14000f010`

## pseudocode

```c
__int64 __fastcall ATL::CComTypeInfoHolder::GetIDsOfNames(
        ATL::CComTypeInfoHolder *this,
        const struct _GUID *a2,
        unsigned __int16 **a3,
        unsigned int a4,
        LCID lcid,
        int *a6)
{
  __int64 result; // rax
  __int64 v10; // r15
  __int64 v11; // rbp
  _WORD *v12; // r14
  __int64 v13; // rsi
  unsigned int v14; // ebx

  if ( *((_QWORD *)this + 3) && *((_QWORD *)this + 5) )
    result = 0;
  else
    result = ATL::CComTypeInfoHolder::GetTI(this, lcid);
  v10 = *((_QWORD *)this + 3);
  if ( v10 )
  {
    v11 = *((_QWORD *)this + 5);
    if ( v11 && a4 == 1 )
    {
      v12 = *a3;
      if ( *a3 )
      {
        v13 = -1;
        do
          ++v13;
        while ( v12[v13] );
      }
      else
      {
        LODWORD(v13) = 0;
      }
      v14 = *((_DWORD *)this + 12);
      while ( (--v14 & 0x80000000) == 0 )
      {
        if ( (_DWORD)v13 == *(_DWORD *)(v11 + 16LL * v14 + 8)
          && !memcmp_0(*(const void **)(v11 + 16LL * v14), v12, 2LL * *(int *)(v11 + 16LL * v14 + 8)) )
        {
          *a6 = *(_DWORD *)(v11 + 16LL * v14 + 12);
          return 0;
        }
      }
    }
    return (*(__int64 (__fastcall **)(__int64, unsigned __int16 **, _QWORD, int *))(*(_QWORD *)v10 + 80LL))(
             v10,
             a3,
             a4,
             a6);
  }
  return result;
}

```

## disassembly

```asm
0x140004c94  push    rbx
0x140004c96  push    rbp
0x140004c97  push    rsi
0x140004c98  push    rdi
0x140004c99  push    r12
0x140004c9b  push    r13
0x140004c9d  push    r14
0x140004c9f  push    r15
0x140004ca1  sub     rsp, 38h
0x140004ca5  xor     edx, edx
0x140004ca7  mov     r12d, r9d
0x140004caa  mov     r13, r8
0x140004cad  mov     rdi, rcx
0x140004cb0  cmp     [rcx+18h], rdx
0x140004cb4  jz      short loc_140004CC0
0x140004cb6  cmp     [rcx+28h], rdx
0x140004cba  jz      short loc_140004CC0
0x140004cbc  mov     eax, edx
0x140004cbe  jmp     short loc_140004CCE
0x140004cc0  mov     edx, [rsp+78h+lcid]; lcid
0x140004cc7  call    ?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z; ATL::CComTypeInfoHolder::GetTI(ulong)
0x140004ccc  xor     edx, edx
0x140004cce  mov     r15, [rdi+18h]
0x140004cd2  test    r15, r15
0x140004cd5  jz      short loc_140004D4E
0x140004cd7  mov     rbp, [rdi+28h]
0x140004cdb  test    rbp, rbp
0x140004cde  jz      short loc_140004D31
0x140004ce0  cmp     r12d, 1
0x140004ce4  jnz     short loc_140004D31
0x140004ce6  mov     r14, [r13+0]
0x140004cea  test    r14, r14
0x140004ced  jnz     short loc_140004CF3
0x140004cef  mov     esi, edx
0x140004cf1  jmp     short loc_140004D01
0x140004cf3  or      rsi, 0FFFFFFFFFFFFFFFFh
0x140004cf7  inc     rsi
0x140004cfa  cmp     [r14+rsi*2], dx
0x140004cff  jnz     short loc_140004CF7
0x140004d01  mov     ebx, [rdi+30h]
0x140004d04  jmp     short loc_140004D2C
0x140004d06  mov     edi, ebx
0x140004d08  add     rdi, rdi
0x140004d0b  cmp     esi, [rbp+rdi*8+8]
0x140004d0f  jnz     short loc_140004D2C
0x140004d11  movsxd  r8, dword ptr [rbp+rdi*8+8]
0x140004d16  mov     rdx, r14; Buf2
0x140004d19  mov     rcx, [rbp+rdi*8+0]; Buf1
0x140004d1e  add     r8, r8; Size
0x140004d21  call    memcmp_0
0x140004d26  xor     edx, edx
0x140004d28  test    eax, eax
0x140004d2a  jz      short loc_140004D5F
0x140004d2c  sub     ebx, 1
0x140004d2f  jns     short loc_140004D06
0x140004d31  mov     rax, [r15]
0x140004d34  mov     r8d, r12d
0x140004d37  mov     r9, [rsp+78h+arg_28]
0x140004d3f  mov     rdx, r13
0x140004d42  mov     rcx, r15
0x140004d45  mov     rax, [rax+50h]
0x140004d49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004d4e  add     rsp, 38h
0x140004d52  pop     r15
0x140004d54  pop     r14
0x140004d56  pop     r13
0x140004d58  pop     r12
0x140004d5a  pop     rdi
0x140004d5b  pop     rsi
0x140004d5c  pop     rbp
0x140004d5d  pop     rbx
0x140004d5e  retn
0x140004d5f  mov     rax, [rsp+78h+arg_28]
0x140004d67  mov     ecx, [rbp+rdi*8+0Ch]
0x140004d6b  mov     [rax], ecx
0x140004d6d  mov     eax, edx
0x140004d6f  jmp     short loc_140004D4E
```
