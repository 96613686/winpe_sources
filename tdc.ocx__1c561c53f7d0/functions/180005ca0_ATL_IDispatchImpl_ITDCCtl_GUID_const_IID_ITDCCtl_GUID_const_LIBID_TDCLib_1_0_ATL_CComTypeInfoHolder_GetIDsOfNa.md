# ATL::IDispatchImpl<ITDCCtl,&_GUID const IID_ITDCCtl,&_GUID const LIBID_TDCLib,1,0,ATL::CComTypeInfoHolder>::GetIDsOfNames(_GUID const &,ushort * *,uint,ulong,long *)

- ea: `0x180005ca0`
- end: `0x180005d93`
- name: `?GetIDsOfNames@?$IDispatchImpl@UITDCCtl@@$1?IID_ITDCCtl@@3U_GUID@@B$1?LIBID_TDCLib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@UEAAJAEBU_GUID@@PEAPEAGIKPEAJ@Z`
- size: `243`
- prototype: `__int64 __fastcall(int, int, int, int, LCID lcid, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180005ca0`
- `0x180005e28`
- `0x180014226`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall ATL::IDispatchImpl<ITDCCtl,&_GUID const IID_ITDCCtl,&_GUID const LIBID_TDCLib,1,0,ATL::CComTypeInfoHolder>::GetIDsOfNames(
        __int64 a1,
        __int64 a2,
        const void **a3,
        unsigned int a4,
        LCID lcid,
        _DWORD *a6)
{
  __int64 v6; // r14
  __int64 v9; // rbx
  __int64 result; // rax
  _WORD *v11; // r15
  __int64 v12; // rsi
  unsigned int v13; // ebp

  v6 = qword_18001B168;
  if ( !qword_18001B168 || (v9 = qword_18001B178, result = 0, !qword_18001B178) )
  {
    result = ATL::CComTypeInfoHolder::GetTI(
               (ATL::CComTypeInfoHolder *)ATL::IDispatchImpl<ITDCCtl,&_GUID const IID_ITDCCtl,&_GUID const LIBID_TDCLib,1,0,ATL::CComTypeInfoHolder>::_tih,
               lcid);
    v9 = qword_18001B178;
    v6 = qword_18001B168;
  }
  if ( v6 )
  {
    if ( v9 && a4 == 1 )
    {
      v11 = *a3;
      if ( *a3 )
      {
        v12 = -1;
        do
          ++v12;
        while ( v11[v12] );
      }
      else
      {
        LODWORD(v12) = 0;
      }
      v13 = dword_18001B180;
      while ( (--v13 & 0x80000000) == 0 )
      {
        if ( (_DWORD)v12 == *(_DWORD *)(v9 + 16LL * v13 + 8)
          && !memcmp_0(*(const void **)(v9 + 16LL * v13), v11, 2LL * *(int *)(v9 + 16LL * v13 + 8)) )
        {
          *a6 = *(_DWORD *)(v9 + 16LL * v13 + 12);
          return 0;
        }
      }
    }
    return (*(__int64 (__fastcall **)(__int64, const void **, _QWORD, _DWORD *))(*(_QWORD *)v6 + 80LL))(v6, a3, a4, a6);
  }
  return result;
}

```

## disassembly

```asm
0x180005ca0  push    rbx
0x180005ca2  push    rbp
0x180005ca3  push    rsi
0x180005ca4  push    rdi
0x180005ca5  push    r12
0x180005ca7  push    r13
0x180005ca9  push    r14
0x180005cab  push    r15
0x180005cad  sub     rsp, 38h
0x180005cb1  mov     r14, cs:qword_18001B168
0x180005cb8  xor     edx, edx
0x180005cba  mov     r12d, r9d
0x180005cbd  mov     r13, r8
0x180005cc0  test    r14, r14
0x180005cc3  jz      short loc_180005CD3
0x180005cc5  mov     rbx, cs:qword_18001B178
0x180005ccc  mov     eax, edx
0x180005cce  test    rbx, rbx
0x180005cd1  jnz     short loc_180005CF6
0x180005cd3  mov     edx, [rsp+78h+lcid]; lcid
0x180005cda  lea     rcx, ?_tih@?$IDispatchImpl@UITDCCtl@@$1?IID_ITDCCtl@@3U_GUID@@B$1?LIBID_TDCLib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@1VCComTypeInfoHolder@2@A; this
0x180005ce1  call    ?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z; ATL::CComTypeInfoHolder::GetTI(ulong)
0x180005ce6  mov     rbx, cs:qword_18001B178
0x180005ced  xor     edx, edx
0x180005cef  mov     r14, cs:qword_18001B168
0x180005cf6  test    r14, r14
0x180005cf9  jz      short loc_180005D70
0x180005cfb  test    rbx, rbx
0x180005cfe  jz      short loc_180005D53
0x180005d00  cmp     r12d, 1
0x180005d04  jnz     short loc_180005D53
0x180005d06  mov     r15, [r13+0]
0x180005d0a  test    r15, r15
0x180005d0d  jnz     short loc_180005D13
0x180005d0f  mov     esi, edx
0x180005d11  jmp     short loc_180005D21
0x180005d13  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180005d17  inc     rsi
0x180005d1a  cmp     [r15+rsi*2], dx
0x180005d1f  jnz     short loc_180005D17
0x180005d21  mov     ebp, cs:dword_18001B180
0x180005d27  jmp     short loc_180005D4E
0x180005d29  mov     edi, ebp
0x180005d2b  add     rdi, rdi
0x180005d2e  cmp     esi, [rbx+rdi*8+8]
0x180005d32  jnz     short loc_180005D4E
0x180005d34  movsxd  r8, dword ptr [rbx+rdi*8+8]
0x180005d39  mov     rdx, r15; Buf2
0x180005d3c  mov     rcx, [rbx+rdi*8]; Buf1
0x180005d40  add     r8, r8; Size
0x180005d43  call    memcmp_0
0x180005d48  xor     edx, edx
0x180005d4a  test    eax, eax
0x180005d4c  jz      short loc_180005D81
0x180005d4e  sub     ebp, 1
0x180005d51  jns     short loc_180005D29
0x180005d53  mov     rax, [r14]
0x180005d56  mov     r8d, r12d
0x180005d59  mov     r9, [rsp+78h+arg_28]
0x180005d61  mov     rdx, r13
0x180005d64  mov     rcx, r14
0x180005d67  mov     rax, [rax+50h]
0x180005d6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d70  add     rsp, 38h
0x180005d74  pop     r15
0x180005d76  pop     r14
0x180005d78  pop     r13
0x180005d7a  pop     r12
0x180005d7c  pop     rdi
0x180005d7d  pop     rsi
0x180005d7e  pop     rbp
0x180005d7f  pop     rbx
0x180005d80  retn
0x180005d81  mov     rax, [rsp+78h+arg_28]
0x180005d89  mov     ecx, [rbx+rdi*8+0Ch]
0x180005d8d  mov     [rax], ecx
0x180005d8f  mov     eax, edx
0x180005d91  jmp     short loc_180005D70
```
