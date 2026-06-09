# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &)

- ea: `0x180001010`
- end: `0x1800010b4`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@D@@@Z`
- size: `164`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, const unsigned __int16 **)`
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x1800094c0`
- `0x180009df0`
- `0x180009e90`
- `0x180009f30`
- `0x180009fd0`
- `0x18000a070`
- `0x180012590`

## callees

- `0x180001010`
- `0x18000169c`
- `0x18001b150`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        const unsigned __int16 **a6)
{
  const unsigned __int16 *v6; // rax
  __int64 v7; // rcx
  int v8; // ecx
  _BYTE v10[32]; // [rsp+30h] [rbp-58h] BYREF
  __int64 v11; // [rsp+50h] [rbp-38h]
  __int64 v12; // [rsp+58h] [rbp-30h]
  const unsigned __int16 *v13; // [rsp+60h] [rbp-28h]
  int v14; // [rsp+68h] [rbp-20h]
  int v15; // [rsp+6Ch] [rbp-1Ch]

  v6 = *a6;
  if ( *a6 )
  {
    v7 = -1;
    do
      ++v7;
    while ( *((_BYTE *)v6 + v7) );
    v8 = v7 + 1;
  }
  else
  {
    v6 = &word_180021DC6;
    v8 = 1;
  }
  v13 = v6;
  v14 = v8;
  v11 = a5;
  v15 = 0;
  v12 = 8;
  return tlgWriteTransfer_EventWriteTransfer(&dword_180030000, a2, 0, 0, 4, v10);
}

```

## disassembly

```asm
0x180001010  sub     rsp, 88h
0x180001017  mov     rax, cs:__security_cookie
0x18000101e  xor     rax, rsp
0x180001021  mov     [rsp+88h+var_18], rax
0x180001026  mov     rax, [rsp+88h+arg_28]
0x18000102e  mov     rax, [rax]
0x180001031  test    rax, rax
0x180001034  jz      short loc_18000104A
0x180001036  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000103d  inc     rcx
0x180001040  cmp     byte ptr [rax+rcx], 0
0x180001044  jnz     short loc_18000103D
0x180001046  inc     ecx
0x180001048  jmp     short loc_180001056
0x18000104a  lea     rax, word_180021DC6
0x180001051  mov     ecx, 1
0x180001056  mov     [rsp+88h+var_28], rax
0x18000105b  xor     r9d, r9d
0x18000105e  mov     rax, [rsp+88h+arg_20]
0x180001066  xor     r8d, r8d
0x180001069  mov     [rsp+88h+var_20], ecx
0x18000106d  xor     ecx, ecx
0x18000106f  mov     [rsp+88h+var_38], rax
0x180001074  lea     rax, [rsp+88h+var_58]
0x180001079  mov     [rsp+88h+var_1C], ecx
0x18000107d  lea     rcx, dword_180030000
0x180001084  mov     [rsp+88h+var_60], rax
0x180001089  mov     [rsp+88h+var_68], 4
0x180001091  mov     [rsp+88h+var_30], 8
0x18000109a  call    _tlgWriteTransfer_EventWriteTransfer
0x18000109f  mov     rcx, [rsp+88h+var_18]
0x1800010a4  xor     rcx, rsp; StackCookie
0x1800010a7  call    __security_check_cookie
0x1800010ac  add     rsp, 88h
0x1800010b3  retn
```
