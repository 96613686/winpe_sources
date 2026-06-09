# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapBuffer<_UNICODE_STRING> const &,_tlgWrapBuffer<_UNICODE_STRING> const &,_tlgWrapBuffer<_UNICODE_STRING> const &,_tlgWrapBuffer<_UNICODE_STRING> const &,_tlgWrapSz<ushort> const &)

- ea: `0x140001008`
- end: `0x140001142`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapBuffer@U_UNICODE_STRING@@@@U2@U2@U2@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapBuffer@U_UNICODE_STRING@@@@444AEBU?$_tlgWrapSz@G@@@Z`
- size: `314`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14001e808`

## callees

- `0x140001008`
- `0x140001148`
- `0x14000f900`

## pseudocode

```c
NTSTATUS __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapSz<unsigned short>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        unsigned __int16 **a6,
        unsigned __int16 **a7,
        unsigned __int16 **a8,
        unsigned __int16 **a9,
        __int64 **a10)
{
  __int64 *v10; // rcx
  __int64 v11; // rax
  int v12; // eax
  int v13; // ecx
  int v14; // ecx
  int v15; // ecx
  int v16; // ecx
  struct _EVENT_DATA_DESCRIPTOR v18; // [rsp+30h] [rbp-A9h] BYREF
  __int64 v19; // [rsp+50h] [rbp-89h]
  __int64 v20; // [rsp+58h] [rbp-81h]
  _DWORD *v21; // [rsp+60h] [rbp-79h]
  __int64 v22; // [rsp+68h] [rbp-71h]
  __int64 v23; // [rsp+70h] [rbp-69h]
  _DWORD v24[2]; // [rsp+78h] [rbp-61h] BYREF
  _DWORD *v25; // [rsp+80h] [rbp-59h]
  __int64 v26; // [rsp+88h] [rbp-51h]
  __int64 v27; // [rsp+90h] [rbp-49h]
  _DWORD v28[2]; // [rsp+98h] [rbp-41h] BYREF
  _DWORD *v29; // [rsp+A0h] [rbp-39h]
  __int64 v30; // [rsp+A8h] [rbp-31h]
  __int64 v31; // [rsp+B0h] [rbp-29h]
  _DWORD v32[2]; // [rsp+B8h] [rbp-21h] BYREF
  _DWORD *v33; // [rsp+C0h] [rbp-19h]
  __int64 v34; // [rsp+C8h] [rbp-11h]
  __int64 v35; // [rsp+D0h] [rbp-9h]
  _DWORD v36[2]; // [rsp+D8h] [rbp-1h] BYREF
  __int64 *v37; // [rsp+E0h] [rbp+7h]
  int v38; // [rsp+E8h] [rbp+Fh]
  int v39; // [rsp+ECh] [rbp+13h]

  v10 = *a10;
  if ( *a10 )
  {
    v11 = -1;
    do
      ++v11;
    while ( *((_WORD *)v10 + v11) );
    v12 = 2 * v11 + 2;
  }
  else
  {
    v10 = &qword_140012AB8;
    v12 = 2;
  }
  v38 = v12;
  v33 = v36;
  v37 = v10;
  v34 = 2;
  v39 = 0;
  v13 = **a9;
  v35 = *((_QWORD *)*a9 + 1);
  v29 = v32;
  v36[0] = v13;
  v30 = 2;
  v36[1] = 0;
  v14 = **a8;
  v31 = *((_QWORD *)*a8 + 1);
  v25 = v28;
  v32[0] = v14;
  v26 = 2;
  v32[1] = 0;
  v15 = **a7;
  v27 = *((_QWORD *)*a7 + 1);
  v21 = v24;
  v28[0] = v15;
  v22 = 2;
  v28[1] = 0;
  v16 = **a6;
  v23 = *((_QWORD *)*a6 + 1);
  v19 = a5;
  v24[0] = v16;
  v24[1] = 0;
  v20 = 8;
  return tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_140019000, a2, 0, 0, 0xCu, &v18);
}

```

## disassembly

```asm
0x140001008  push    rbp
0x14000100a  lea     rbp, [rsp-27h]
0x14000100f  sub     rsp, 100h
0x140001016  mov     rax, cs:__security_cookie
0x14000101d  xor     rax, rsp
0x140001020  mov     [rbp+27h+var_10], rax
0x140001024  mov     rax, [rbp+27h+arg_48]
0x140001028  xor     r8d, r8d
0x14000102b  mov     r9d, 2
0x140001031  mov     rcx, [rax]
0x140001034  test    rcx, rcx
0x140001037  jz      short loc_140001050
0x140001039  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000103d  inc     rax
0x140001040  cmp     [rcx+rax*2], r8w
0x140001045  jnz     short loc_14000103D
0x140001047  lea     eax, ds:2[rax*2]
0x14000104e  jmp     short loc_14000105A
0x140001050  lea     rcx, qword_140012AB8
0x140001057  mov     eax, r9d
0x14000105a  mov     [rbp+27h+var_18], eax
0x14000105d  lea     rax, [rbp+27h+var_28]
0x140001061  mov     [rbp+27h+var_40], rax
0x140001065  mov     rax, [rbp+27h+arg_40]
0x140001069  mov     [rbp+27h+var_20], rcx
0x14000106d  mov     [rbp+27h+var_38], r9
0x140001071  mov     [rbp+27h+var_14], r8d
0x140001075  mov     rax, [rax]
0x140001078  movzx   ecx, word ptr [rax]
0x14000107b  mov     rax, [rax+8]
0x14000107f  mov     [rbp+27h+var_30], rax
0x140001083  lea     rax, [rbp+27h+var_48]
0x140001087  mov     [rbp+27h+var_60], rax
0x14000108b  mov     rax, [rbp+27h+arg_38]
0x14000108f  mov     [rbp+27h+var_28], ecx
0x140001092  mov     [rbp+27h+var_58], r9
0x140001096  mov     [rbp+27h+var_24], r8d
0x14000109a  mov     rax, [rax]
0x14000109d  movzx   ecx, word ptr [rax]
0x1400010a0  mov     rax, [rax+8]
0x1400010a4  mov     [rbp+27h+var_50], rax
0x1400010a8  lea     rax, [rbp+27h+var_68]
0x1400010ac  mov     [rbp+27h+var_80], rax
0x1400010b0  mov     rax, [rbp+27h+arg_30]
0x1400010b4  mov     [rbp+27h+var_48], ecx
0x1400010b7  mov     [rbp+27h+var_78], r9
0x1400010bb  mov     [rbp+27h+var_44], r8d
0x1400010bf  mov     rax, [rax]
0x1400010c2  movzx   ecx, word ptr [rax]
0x1400010c5  mov     rax, [rax+8]
0x1400010c9  mov     [rbp+27h+var_70], rax
0x1400010cd  lea     rax, [rbp+27h+var_88]
0x1400010d1  mov     [rbp+27h+var_A0], rax
0x1400010d5  mov     rax, [rbp+27h+arg_28]
0x1400010d9  mov     [rbp+27h+var_68], ecx
0x1400010dc  mov     [rbp+27h+var_98], r9
0x1400010e0  xor     r9d, r9d
0x1400010e3  mov     [rbp+27h+var_64], r8d
0x1400010e7  mov     rax, [rax]
0x1400010ea  movzx   ecx, word ptr [rax]
0x1400010ed  mov     rax, [rax+8]
0x1400010f1  mov     [rbp+27h+var_90], rax
0x1400010f5  mov     rax, [rbp+27h+arg_20]
0x1400010f9  mov     [rsp+100h+var_B0], rax
0x1400010fe  lea     rax, [rsp+100h+var_D0]
0x140001103  mov     [rbp+27h+var_88], ecx
0x140001106  lea     rcx, dword_140019000
0x14000110d  mov     [rsp+100h+var_D8], rax
0x140001112  mov     [rsp+100h+var_E0], 0Ch
0x14000111a  mov     [rbp+27h+var_84], r8d
0x14000111e  mov     [rsp+100h+var_A8], 8
0x140001127  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000112c  mov     rcx, [rbp+27h+var_10]
0x140001130  xor     rcx, rsp; StackCookie
0x140001133  call    __security_check_cookie
0x140001138  add     rsp, 100h
0x14000113f  pop     rbp
0x140001140  retn
```
