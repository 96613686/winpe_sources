# CSWbemNamedValueSet::Remove(ushort *,long)

- ea: `0x180023cc0`
- end: `0x180023dc1`
- name: `?Remove@CSWbemNamedValueSet@@UEAAJPEAGJ@Z`
- size: `257`
- prototype: `int(CSWbemNamedValueSet *__hidden this, unsigned __int16 *, int)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x1800050dc`
- `0x180006300`
- `0x18000c0b0`
- `0x180023cc0`
- `0x180036010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180023d37`
- `OLEAUT32!__imp_SysAllocString` at `0x180023d37`
- `OLEAUT32!__imp_SysFreeString` at `0x180023da8`
- `OLEAUT32!__imp_SysFreeString` at `0x180023da8`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CSWbemNamedValueSet::Remove(CSWbemNamedValueSet *this, unsigned __int16 *a2, unsigned int a3)
{
  int v6; // ebx
  __int64 v8; // rcx
  __int64 v9; // rsi
  OLECHAR *v10; // rbx
  char v11; // bp
  __int64 v12; // rcx
  __int64 v13; // [rsp+40h] [rbp+8h] BYREF
  OLECHAR *v14; // [rsp+58h] [rbp+20h]

  ResetLastErrors();
  if ( !*((_BYTE *)this + 144) )
  {
    v6 = -2147217373;
LABEL_3:
    CDispatchHelp::RaiseException((CSWbemNamedValueSet *)((char *)this + 56), v6);
    return (unsigned int)v6;
  }
  v6 = -2147217407;
  v8 = *((_QWORD *)this + 6);
  if ( !v8 )
    goto LABEL_3;
  v6 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *, _QWORD))(*(_QWORD *)v8 + 80LL))(v8, a2, a3);
  if ( v6 < 0 )
    goto LABEL_3;
  v9 = *((_QWORD *)this + 17);
  if ( v9 )
  {
    v10 = SysAllocString(a2);
    v14 = v10;
    v11 = 0;
    if ( *(_DWORD *)(v9 + 28) == 1 )
    {
      v12 = *(_QWORD *)(v9 + 8);
      if ( v12 )
      {
        v13 = 0;
        if ( (*(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v12 + 176LL))(v12, &v13) < 0
          || (*(int (__fastcall **)(__int64, OLECHAR *, _QWORD))(*(_QWORD *)v13 + 64LL))(v13, v10, 0) >= 0 )
        {
          v11 = 1;
        }
        ATL::CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>::~CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>(&v13);
      }
    }
    SysFreeString(v10);
    return v11 != 1 ? 0x80041001 : 0;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180023cc0  mov     [rsp+arg_8], rbx
0x180023cc5  push    rbp
0x180023cc6  push    rsi
0x180023cc7  push    rdi
0x180023cc8  sub     rsp, 20h
0x180023ccc  mov     esi, r8d
0x180023ccf  mov     rbp, rdx
0x180023cd2  mov     rdi, rcx
0x180023cd5  call    ?ResetLastErrors@@YAXXZ; ResetLastErrors(void)
0x180023cda  cmp     byte ptr [rdi+90h], 0
0x180023ce1  jnz     short loc_180023D02
0x180023ce3  mov     ebx, 80041023h
0x180023ce8  lea     rcx, [rdi+38h]; this
0x180023cec  mov     edx, ebx; int
0x180023cee  call    ?RaiseException@CDispatchHelp@@QEAAXJ@Z; CDispatchHelp::RaiseException(long)
0x180023cf3  mov     eax, ebx
0x180023cf5  mov     rbx, [rsp+38h+arg_8]
0x180023cfa  add     rsp, 20h
0x180023cfe  pop     rdi
0x180023cff  pop     rsi
0x180023d00  pop     rbp
0x180023d01  retn
0x180023d02  mov     ebx, 80041001h
0x180023d07  mov     rcx, [rdi+30h]
0x180023d0b  test    rcx, rcx
0x180023d0e  jz      short loc_180023CE8
0x180023d10  mov     rax, [rcx]
0x180023d13  mov     r8d, esi
0x180023d16  mov     rdx, rbp
0x180023d19  mov     rax, [rax+50h]
0x180023d1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023d22  mov     ebx, eax
0x180023d24  test    eax, eax
0x180023d26  js      short loc_180023CE8
0x180023d28  mov     rsi, [rdi+88h]
0x180023d2f  test    rsi, rsi
0x180023d32  jz      short loc_180023CF3
0x180023d34  mov     rcx, rbp; psz
0x180023d37  call    cs:__imp_SysAllocString
0x180023d3d  mov     rbx, rax
0x180023d40  mov     [rsp+38h+arg_18], rax
0x180023d45  xor     bpl, bpl
0x180023d48  mov     edi, 1
0x180023d4d  cmp     [rsi+1Ch], edi
0x180023d50  jnz     short loc_180023DA5
0x180023d52  mov     rcx, [rsi+8]
0x180023d56  test    rcx, rcx
0x180023d59  jz      short loc_180023DA5
0x180023d5b  mov     [rsp+38h+arg_0], 0
0x180023d64  mov     rax, [rcx]
0x180023d67  lea     rdx, [rsp+38h+arg_0]
0x180023d6c  mov     rax, [rax+0B0h]
0x180023d73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023d78  test    eax, eax
0x180023d7a  js      short loc_180023D97
0x180023d7c  mov     rcx, [rsp+38h+arg_0]
0x180023d81  mov     rax, [rcx]
0x180023d84  xor     r8d, r8d
0x180023d87  mov     rdx, rbx
0x180023d8a  mov     rax, [rax+40h]
0x180023d8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023d93  test    eax, eax
0x180023d95  js      short loc_180023D9A
0x180023d97  mov     bpl, dil
0x180023d9a  lea     rcx, [rsp+38h+arg_0]
0x180023d9f  call    ??1?$CComQIPtr@UISWbemObject@@$1?_GUID_76a6415a_cb41_11d1_8b02_00600806d9b6@@3U__s_GUID@@B@ATL@@QEAA@XZ; ATL::CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>::~CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>(void)
0x180023da4  nop
0x180023da5  mov     rcx, rbx; bstrString
0x180023da8  call    cs:__imp_SysFreeString
0x180023dae  sub     dil, bpl
0x180023db1  neg     dil
0x180023db4  sbb     ebx, ebx
0x180023db6  and     ebx, 80041001h
0x180023dbc  jmp     loc_180023CF3
```
