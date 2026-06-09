# ATL::IConnectionPointImpl<CTDCCtl,&_GUID const IID_IPropertyNotifySink,ATL::CComDynamicUnkArray>::_LocCPQueryInterface(_GUID const &,void * *)

- ea: `0x180009a40`
- end: `0x180009ab6`
- name: `?_LocCPQueryInterface@?$IConnectionPointImpl@VCTDCCtl@@$1?IID_IPropertyNotifySink@@3U_GUID@@BVCComDynamicUnkArray@ATL@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `118`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180009a40`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall ATL::IConnectionPointImpl<CTDCCtl,&_GUID const IID_IPropertyNotifySink,ATL::CComDynamicUnkArray>::_LocCPQueryInterface(
        __int64 a1,
        _DWORD *a2,
        _QWORD *a3)
{
  bool v4; // zf

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  if ( *a2 == -1315523962 )
  {
    if ( a2[1] != *(_DWORD *)&GUID_b196b286_bab4_101a_b69c_00aa00341d07.Data2
      || a2[2] != *(_DWORD *)GUID_b196b286_bab4_101a_b69c_00aa00341d07.Data4 )
    {
      return 2147500034LL;
    }
    v4 = a2[3] == *(_DWORD *)&GUID_b196b286_bab4_101a_b69c_00aa00341d07.Data4[4];
  }
  else
  {
    if ( *a2 || a2[1] || a2[2] != 192 )
      return 2147500034LL;
    v4 = a2[3] == 1174405120;
  }
  if ( v4 )
  {
    *a3 = a1;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
    return 0;
  }
  return 2147500034LL;
}

```

## disassembly

```asm
0x180009a40  sub     rsp, 28h
0x180009a44  xor     eax, eax
0x180009a46  test    r8, r8
0x180009a49  jnz     short loc_180009A52
0x180009a4b  mov     eax, 80004003h
0x180009a50  jmp     short loc_180009AB1
0x180009a52  mov     [r8], rax
0x180009a55  cmp     dword ptr [rdx], 0B196B286h
0x180009a5b  jnz     short loc_180009A7E
0x180009a5d  mov     eax, dword ptr cs:_GUID_b196b286_bab4_101a_b69c_00aa00341d07.Data2
0x180009a63  cmp     [rdx+4], eax
0x180009a66  jnz     short loc_180009AAC
0x180009a68  mov     eax, dword ptr cs:_GUID_b196b286_bab4_101a_b69c_00aa00341d07.Data4
0x180009a6e  cmp     [rdx+8], eax
0x180009a71  jnz     short loc_180009AAC
0x180009a73  mov     eax, dword ptr cs:_GUID_b196b286_bab4_101a_b69c_00aa00341d07.Data4+4
0x180009a79  cmp     [rdx+0Ch], eax
0x180009a7c  jmp     short loc_180009A97
0x180009a7e  cmp     [rdx], eax
0x180009a80  jnz     short loc_180009AAC
0x180009a82  cmp     [rdx+4], eax
0x180009a85  jnz     short loc_180009AAC
0x180009a87  cmp     dword ptr [rdx+8], 0C0h
0x180009a8e  jnz     short loc_180009AAC
0x180009a90  cmp     dword ptr [rdx+0Ch], 46000000h
0x180009a97  jnz     short loc_180009AAC
0x180009a99  mov     [r8], rcx
0x180009a9c  mov     rax, [rcx]
0x180009a9f  mov     rax, [rax+8]
0x180009aa3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009aa8  xor     eax, eax
0x180009aaa  jmp     short loc_180009AB1
0x180009aac  mov     eax, 80004002h
0x180009ab1  add     rsp, 28h
0x180009ab5  retn
```
