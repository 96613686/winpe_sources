# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)

- ea: `0x18006125c`
- end: `0x18006133a`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z`
- size: `222`
- prototype: ``
- caller_count: `14`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180024edc`
- `0x180025b70`
- `0x180079510`
- `0x180079750`
- `0x180079990`
- `0x180079bd0`
- `0x180079e10`
- `0x18007bc80`
- `0x1800855a4`
- `0x18009d8d0`
- `0x1800a78d0`
- `0x1800a7b00`
- `0x1800a7d30`
- `0x1800a7f60`

## callees

- `0x180095130`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x18006131f`
- `ntdll!EtwEventWriteTransfer` at `0x18006131f`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7)
{
  _DWORD v8[2]; // [rsp+38h] [rbp-39h] BYREF
  __int64 v9; // [rsp+40h] [rbp-31h]
  unsigned __int16 *v10; // [rsp+50h] [rbp-21h] BYREF
  int v11; // [rsp+58h] [rbp-19h]
  int v12; // [rsp+5Ch] [rbp-15h]
  unsigned __int8 *v13; // [rsp+60h] [rbp-11h]
  int v14; // [rsp+68h] [rbp-9h]
  int v15; // [rsp+6Ch] [rbp-5h]
  __int64 v16; // [rsp+70h] [rbp-1h]
  __int64 v17; // [rsp+78h] [rbp+7h]
  __int64 v18; // [rsp+80h] [rbp+Fh]
  __int64 v19; // [rsp+88h] [rbp+17h]
  __int64 v20; // [rsp+90h] [rbp+1Fh]
  __int64 v21; // [rsp+98h] [rbp+27h]

  v20 = a7;
  v18 = a6;
  v16 = a5;
  v8[0] = *a2 << 24;
  v8[1] = *(unsigned __int16 *)(a2 + 1);
  v9 = *(_QWORD *)(a2 + 3);
  v10 = *(unsigned __int16 **)(a1 + 8);
  v21 = 4;
  v19 = 4;
  v17 = 8;
  v11 = *v10;
  v14 = *(unsigned __int16 *)(a2 + 11);
  v13 = a2 + 11;
  v12 = 2;
  v15 = 1;
  return EtwEventWriteTransfer(*(_QWORD *)(a1 + 32), v8, a3, 0, 5, &v10);
}

```

## disassembly

```asm
0x18006125c  push    rbp
0x18006125e  lea     rbp, [rsp-3Fh]
0x180061263  sub     rsp, 0B0h
0x18006126a  mov     rax, cs:__security_cookie
0x180061271  xor     rax, rsp
0x180061274  mov     [rbp+3Fh+var_10], rax
0x180061278  mov     rax, [rbp+3Fh+arg_30]
0x18006127c  mov     r10, rcx
0x18006127f  mov     [rbp+3Fh+var_20], rax
0x180061283  lea     rcx, [rdx+0Bh]
0x180061287  mov     rax, [rbp+3Fh+arg_28]
0x18006128b  xor     r9d, r9d
0x18006128e  mov     [rbp+3Fh+var_30], rax
0x180061292  mov     rax, [rbp+3Fh+arg_20]
0x180061296  mov     [rbp+3Fh+var_40], rax
0x18006129a  movzx   eax, byte ptr [rdx]
0x18006129d  shl     eax, 18h
0x1800612a0  mov     [rbp+3Fh+var_78], eax
0x1800612a3  movzx   eax, word ptr [rdx+1]
0x1800612a7  mov     [rbp+3Fh+var_74], eax
0x1800612aa  mov     rax, [rdx+3]
0x1800612ae  lea     rdx, [rbp+3Fh+var_78]
0x1800612b2  mov     [rbp+3Fh+var_70], rax
0x1800612b6  mov     rax, [r10+8]
0x1800612ba  mov     [rbp+3Fh+var_60], rax
0x1800612be  mov     [rbp+3Fh+var_18], 4
0x1800612c6  mov     [rbp+3Fh+var_28], 4
0x1800612ce  mov     [rbp+3Fh+var_38], 8
0x1800612d6  movzx   eax, word ptr [rax]
0x1800612d9  mov     [rbp+3Fh+var_58], eax
0x1800612dc  movzx   eax, word ptr [rcx]
0x1800612df  mov     [rbp+3Fh+var_48], eax
0x1800612e2  lea     rax, _TraceLoggingMetadataEnd
0x1800612e9  mov     [rbp+3Fh+var_50], rcx
0x1800612ed  lea     rcx, _TraceLoggingMetadata
0x1800612f4  sub     eax, ecx
0x1800612f6  mov     [rbp+3Fh+var_54], 2
0x1800612fd  mov     [rbp+3Fh+var_44], 1
0x180061304  mov     [rbp+3Fh+var_80], eax
0x180061307  mov     eax, [rbp+3Fh+var_80]
0x18006130a  mov     rcx, [r10+20h]
0x18006130e  lea     rax, [rbp+3Fh+var_60]
0x180061312  mov     [rsp+0B0h+var_88], rax
0x180061317  mov     [rsp+0B0h+var_90], 5
0x18006131f  call    cs:__imp_EtwEventWriteTransfer
0x180061325  mov     rcx, [rbp+3Fh+var_10]
0x180061329  xor     rcx, rsp; StackCookie
0x18006132c  call    __security_check_cookie
0x180061331  add     rsp, 0B0h
0x180061338  pop     rbp
0x180061339  retn
```
