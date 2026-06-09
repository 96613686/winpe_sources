# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &)

- ea: `0x1800010bc`
- end: `0x18000111a`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@@Z`
- size: `94`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64)`
- caller_count: `30`
- callee_count: `2`
- tags: ``

## callers

- `0x180010b54`
- `0x180010cac`
- `0x180012628`
- `0x1800143a0`
- `0x1800145cc`
- `0x180014704`
- `0x18001b673`
- `0x18001b6d3`
- `0x18001b733`
- `0x18001b793`
- `0x18001b7f3`
- `0x18001b853`
- `0x18001b8b3`
- `0x18001b913`
- `0x18001b973`
- `0x18001b9d3`
- `0x18001be48`
- `0x18001bea8`
- `0x18001bf08`
- `0x18001bf68`
- `0x18001c0c4`
- `0x18001c124`
- `0x18001c184`
- `0x18001c1e4`
- `0x18001c244`
- `0x18001c2a4`
- `0x18001c304`
- `0x18001c364`
- `0x18001c444`
- `0x18001c4a4`

## callees

- `0x18000169c`
- `0x18001b150`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5)
{
  _QWORD v6[6]; // [rsp+30h] [rbp-48h] BYREF

  v6[4] = a5;
  v6[5] = 8;
  return tlgWriteTransfer_EventWriteTransfer(&dword_180030000, a2, 0, 0, 3, v6);
}

```

## disassembly

```asm
0x1800010bc  mov     r11, rsp
0x1800010bf  sub     rsp, 78h
0x1800010c3  mov     rax, cs:__security_cookie
0x1800010ca  xor     rax, rsp
0x1800010cd  mov     [rsp+78h+var_18], rax
0x1800010d2  mov     rax, [rsp+78h+arg_20]
0x1800010da  lea     rcx, dword_180030000
0x1800010e1  mov     [r11-28h], rax
0x1800010e5  xor     r9d, r9d
0x1800010e8  lea     rax, [r11-48h]
0x1800010ec  mov     qword ptr [r11-20h], 8
0x1800010f4  mov     [r11-50h], rax
0x1800010f8  xor     r8d, r8d
0x1800010fb  mov     [rsp+78h+var_58], 3
0x180001103  call    _tlgWriteTransfer_EventWriteTransfer
0x180001108  mov     rcx, [rsp+78h+var_18]
0x18000110d  xor     rcx, rsp; StackCookie
0x180001110  call    __security_check_cookie
0x180001115  add     rsp, 78h
0x180001119  retn
```
