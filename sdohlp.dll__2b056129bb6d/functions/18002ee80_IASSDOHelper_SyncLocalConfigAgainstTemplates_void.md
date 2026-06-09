# IASSDOHelper::SyncLocalConfigAgainstTemplates(void)

- ea: `0x18002ee80`
- end: `0x18002ef99`
- name: `?SyncLocalConfigAgainstTemplates@IASSDOHelper@@UEAAJXZ`
- size: `281`
- prototype: `__int64 __fastcall(IASSDOHelper *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180024cac`
- `0x18002cd00`
- `0x18002d08c`
- `0x18002ee80`
- `0x18002efa0`
- `0x180042a80`
- `0x180058010`

## string_xrefs

- `0x18002ef4a`: `Sync local config against templates failed. hr = %!hresult!`

## pseudocode

```c
__int64 __fastcall IASSDOHelper::SyncLocalConfigAgainstTemplates(IASSDOHelper *this)
{
  __int64 (__fastcall ***v2)(_QWORD, GUID *, __int64 *); // rcx
  int v4; // ebx
  __int64 v5; // rbx
  __int64 (__fastcall *v6)(__int64, __int64, __int64 *, char *, _WORD); // rsi
  _bstr_t *v7; // rax
  __int64 v8; // rdx
  __int64 v9; // [rsp+40h] [rbp+8h] BYREF
  char v10; // [rsp+48h] [rbp+10h] BYREF

  v2 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 11);
  if ( !v2 )
    return 2147500035LL;
  v9 = 0;
  v4 = (**v2)(v2, &IID_IUnknown, &v9);
  if ( v4 < 0
    || ((v5 = *((_QWORD *)this + 10),
         v6 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *, char *, _WORD))(*(_QWORD *)v5 + 144LL),
         v7 = _bstr_t::_bstr_t((_bstr_t *)&v10, L"IAS"),
         !*(_QWORD *)v7)
      ? (v8 = 0)
      : (v8 = **(_QWORD **)v7),
        v4 = v6(v5, v8, &v9, (char *)this + 96, 0),
        _bstr_t::_Free((_bstr_t *)&v10),
        v4 < 0) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    {
      WppDbgPrint("Sync local config against templates failed. hr = %!hresult!");
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        38,
        (unsigned int)WPP_b2e5ba8d027733d341583b07c20330d3_Traceguids,
        (unsigned int)"NPSSDO",
        v4);
    }
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v9);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18002ee80  mov     [rsp+arg_10], rbx
0x18002ee85  mov     [rsp+arg_18], rsi
0x18002ee8a  push    rdi
0x18002ee8b  sub     rsp, 30h
0x18002ee8f  mov     rdi, rcx
0x18002ee92  mov     rcx, [rcx+58h]
0x18002ee96  test    rcx, rcx
0x18002ee99  jnz     short loc_18002EEA5
0x18002ee9b  mov     eax, 80004003h
0x18002eea0  jmp     loc_18002EF89
0x18002eea5  mov     [rsp+38h+arg_0], 0
0x18002eeae  lea     r8, [rsp+38h+arg_0]
0x18002eeb3  mov     rax, [rcx]
0x18002eeb6  lea     rdx, IID_IUnknown
0x18002eebd  mov     rax, [rax]
0x18002eec0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eec5  mov     ebx, eax
0x18002eec7  test    eax, eax
0x18002eec9  js      short loc_18002EF26
0x18002eecb  mov     rbx, [rdi+50h]
0x18002eecf  lea     rdx, aIas; "IAS"
0x18002eed6  lea     rcx, [rsp+38h+arg_8]; this
0x18002eedb  mov     rax, [rbx]
0x18002eede  mov     rsi, [rax+90h]
0x18002eee5  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18002eeea  mov     rcx, [rax]
0x18002eeed  test    rcx, rcx
0x18002eef0  jz      short loc_18002EEF7
0x18002eef2  mov     rdx, [rcx]
0x18002eef5  jmp     short loc_18002EEF9
0x18002eef7  xor     edx, edx
0x18002eef9  xor     r8d, r8d
0x18002eefc  lea     r9, [rdi+60h]
0x18002ef00  mov     word ptr [rsp+38h+var_18], r8w
0x18002ef06  mov     rcx, rbx
0x18002ef09  lea     r8, [rsp+38h+arg_0]
0x18002ef0e  mov     rax, rsi
0x18002ef11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ef16  lea     rcx, [rsp+38h+arg_8]; this
0x18002ef1b  mov     ebx, eax
0x18002ef1d  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18002ef22  test    ebx, ebx
0x18002ef24  jns     short loc_18002EF7D
0x18002ef26  mov     rax, cs:WPP_GLOBAL_Control
0x18002ef2d  lea     rcx, WPP_GLOBAL_Control
0x18002ef34  cmp     rax, rcx
0x18002ef37  jz      short loc_18002EF7D
0x18002ef39  cmp     byte ptr [rax+19h], 2
0x18002ef3d  jb      short loc_18002EF7D
0x18002ef3f  test    dword ptr [rax+1Ch], 400h
0x18002ef46  jz      short loc_18002EF7D
0x18002ef48  mov     edx, ebx
0x18002ef4a  lea     rcx, aSyncLocalConfi; "Sync local config against templates fai"...
0x18002ef51  call    WppDbgPrint
0x18002ef56  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ef5d  lea     r9, aNpssdo; "NPSSDO"
0x18002ef64  mov     edx, 26h ; '&'
0x18002ef69  mov     [rsp+38h+var_18], ebx
0x18002ef6d  lea     r8, WPP_b2e5ba8d027733d341583b07c20330d3_Traceguids
0x18002ef74  mov     rcx, [rcx+10h]
0x18002ef78  call    WPP_SF_sd
0x18002ef7d  lea     rcx, [rsp+38h+arg_0]
0x18002ef82  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002ef87  mov     eax, ebx
0x18002ef89  mov     rbx, [rsp+38h+arg_10]
0x18002ef8e  mov     rsi, [rsp+38h+arg_18]
0x18002ef93  add     rsp, 30h
0x18002ef97  pop     rdi
0x18002ef98  retn
```
