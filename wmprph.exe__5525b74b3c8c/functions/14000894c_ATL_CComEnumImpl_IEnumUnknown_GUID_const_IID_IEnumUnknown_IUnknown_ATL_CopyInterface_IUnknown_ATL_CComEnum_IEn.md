# ATL::CComEnumImpl<IEnumUnknown,&_GUID const IID_IEnumUnknown,IUnknown *,ATL::_CopyInterface<IUnknown>,ATL::CComEnum<IEnumUnknown,&_GUID const IID_IEnumUnknown,IUnknown *,ATL::_CopyInterface<IUnknown>,ATL::CComSingleThreadModel>>::Skip(ulong)

- ea: `0x14000894c`
- end: `0x140008977`
- name: `?Skip@?$CComEnumImpl@UIEnumUnknown@@$1?IID_IEnumUnknown@@3U_GUID@@BPEAUIUnknown@@V?$_CopyInterface@UIUnknown@@@ATL@@V?$CComEnum@UIEnumUnknown@@$1?IID_IEnumUnknown@@3U_GUID@@BPEAUIUnknown@@V?$_CopyInterface@UIUnknown@@@ATL@@VCComSingleThreadModel@6@@6@@ATL@@UEAAJK@Z`
- size: `43`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140008940`

## callees

- `0x14000894c`

## pseudocode

```c
__int64 __fastcall ATL::CComEnumImpl<IEnumUnknown,&_GUID const IID_IEnumUnknown,IUnknown *,ATL::_CopyInterface<IUnknown>,ATL::CComEnum<IEnumUnknown,&_GUID const IID_IEnumUnknown,IUnknown *,ATL::_CopyInterface<IUnknown>,ATL::CComSingleThreadModel>>::Skip(
        _QWORD *a1,
        unsigned int a2)
{
  unsigned __int64 v2; // rax

  a1[4] += 8LL * a2;
  v2 = a1[3];
  if ( a1[4] <= v2 )
  {
    v2 = a1[2];
    if ( a1[4] >= v2 )
      return 0;
  }
  a1[4] = v2;
  return 1;
}

```

## disassembly

```asm
0x14000894c  mov     eax, edx
0x14000894e  shl     rax, 3
0x140008952  add     [rcx+20h], rax
0x140008956  mov     rax, [rcx+18h]
0x14000895a  cmp     [rcx+20h], rax
0x14000895e  jbe     short loc_14000896A
0x140008960  mov     [rcx+20h], rax
0x140008964  mov     eax, 1
0x140008969  retn
0x14000896a  mov     rax, [rcx+10h]
0x14000896e  cmp     [rcx+20h], rax
0x140008972  jb      short loc_140008960
0x140008974  xor     eax, eax
0x140008976  retn
```
