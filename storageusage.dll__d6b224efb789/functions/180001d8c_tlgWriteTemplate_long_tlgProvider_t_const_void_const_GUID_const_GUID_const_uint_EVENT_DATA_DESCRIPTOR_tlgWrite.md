# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)

- ea: `0x180001d8c`
- end: `0x180001eeb`
- name: `??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$00@@U3@U3@U3@U3@U3@U3@U3@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$00@@55555553AEBU?$_tlgWrapperByVal@$07@@@Z`
- size: `351`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001b870`

## callees

- `0x180001010`
- `0x1800050f0`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 *a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        __int64 a11,
        __int64 a12,
        __int64 a13,
        __int64 a14,
        __int64 a15,
        __int64 a16,
        __int64 a17,
        __int64 a18)
{
  __int64 v18; // rcx
  struct _EVENT_DATA_DESCRIPTOR v20; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v21; // [rsp+50h] [rbp-B0h]
  __int64 v22; // [rsp+58h] [rbp-A8h]
  __int64 v23; // [rsp+60h] [rbp-A0h]
  __int64 v24; // [rsp+68h] [rbp-98h]
  __int64 v25; // [rsp+70h] [rbp-90h]
  __int64 v26; // [rsp+78h] [rbp-88h]
  __int64 v27; // [rsp+80h] [rbp-80h]
  __int64 v28; // [rsp+88h] [rbp-78h]
  __int64 v29; // [rsp+90h] [rbp-70h]
  __int64 v30; // [rsp+98h] [rbp-68h]
  __int64 v31; // [rsp+A0h] [rbp-60h]
  __int64 v32; // [rsp+A8h] [rbp-58h]
  __int64 v33; // [rsp+B0h] [rbp-50h]
  __int64 v34; // [rsp+B8h] [rbp-48h]
  __int64 v35; // [rsp+C0h] [rbp-40h]
  __int64 v36; // [rsp+C8h] [rbp-38h]
  __int64 v37; // [rsp+D0h] [rbp-30h]
  __int64 v38; // [rsp+D8h] [rbp-28h]
  __int64 v39; // [rsp+E0h] [rbp-20h]
  __int64 v40; // [rsp+E8h] [rbp-18h]
  __int64 v41; // [rsp+F0h] [rbp-10h]
  __int64 v42; // [rsp+F8h] [rbp-8h]
  __int64 v43; // [rsp+100h] [rbp+0h]
  __int64 v44; // [rsp+108h] [rbp+8h]
  __int64 v45; // [rsp+110h] [rbp+10h]
  __int64 v46; // [rsp+118h] [rbp+18h]
  __int64 v47; // [rsp+120h] [rbp+20h]
  __int64 v48; // [rsp+128h] [rbp+28h]

  v47 = a18;
  v45 = a17;
  v43 = a16;
  v41 = a15;
  v39 = a14;
  v37 = a13;
  v35 = a12;
  v33 = a11;
  v31 = a10;
  v29 = a9;
  v27 = a8;
  v48 = 8;
  v46 = 4;
  v44 = 1;
  v18 = *a7;
  v23 = a6;
  v25 = v18;
  v21 = a5;
  v26 = 16;
  v42 = 1;
  v40 = 1;
  v38 = 1;
  v36 = 1;
  v34 = 1;
  v32 = 1;
  v30 = 1;
  v28 = 4;
  v24 = 4;
  v22 = 4;
  return tlgWriteTransfer_EventWriteTransfer((__int64)&dword_180040010, a2, 0, 0, 0x10u, &v20);
}

```

## disassembly

```asm
0x180001d8c  push    rbp
0x180001d8e  lea     rbp, [rsp-40h]
0x180001d93  sub     rsp, 140h
0x180001d9a  mov     rax, cs:__security_cookie
0x180001da1  xor     rax, rsp
0x180001da4  mov     [rbp+40h+var_10], rax
0x180001da8  mov     rax, [rbp+40h+arg_88]
0x180001daf  xor     r9d, r9d
0x180001db2  mov     [rbp+40h+var_20], rax
0x180001db6  xor     r8d, r8d
0x180001db9  mov     rax, [rbp+40h+arg_80]
0x180001dc0  mov     [rbp+40h+var_30], rax
0x180001dc4  mov     rax, [rbp+40h+arg_78]
0x180001dcb  mov     [rbp+40h+var_40], rax
0x180001dcf  mov     rax, [rbp+40h+arg_70]
0x180001dd6  mov     [rbp+40h+var_50], rax
0x180001dda  mov     rax, [rbp+40h+arg_68]
0x180001de1  mov     [rbp+40h+var_60], rax
0x180001de5  mov     rax, [rbp+40h+arg_60]
0x180001dec  mov     [rbp+40h+var_70], rax
0x180001df0  mov     rax, [rbp+40h+arg_58]
0x180001df7  mov     [rbp+40h+var_80], rax
0x180001dfb  mov     rax, [rbp+40h+arg_50]
0x180001e02  mov     [rbp+40h+var_90], rax
0x180001e06  mov     rax, [rbp+40h+arg_48]
0x180001e0d  mov     [rbp+40h+var_A0], rax
0x180001e11  mov     rax, [rbp+40h+arg_40]
0x180001e18  mov     [rbp+40h+var_B0], rax
0x180001e1c  mov     rax, [rbp+40h+arg_38]
0x180001e23  mov     [rbp+40h+var_C0], rax
0x180001e27  mov     rax, [rbp+40h+arg_30]
0x180001e2e  mov     [rbp+40h+var_18], 8
0x180001e36  mov     [rbp+40h+var_28], 4
0x180001e3e  mov     [rbp+40h+var_38], 1
0x180001e46  mov     rcx, [rax]
0x180001e49  mov     rax, [rbp+40h+arg_28]
0x180001e4d  mov     [rsp+140h+var_E0], rax
0x180001e52  mov     rax, [rbp+40h+arg_20]
0x180001e56  mov     [rsp+140h+var_D0], rcx
0x180001e5b  mov     ecx, 10h
0x180001e60  mov     [rsp+140h+var_F0], rax
0x180001e65  lea     rax, [rsp+140h+var_110]
0x180001e6a  mov     [rsp+140h+var_118], rax
0x180001e6f  mov     [rsp+140h+var_120], ecx
0x180001e73  mov     [rsp+140h+var_C8], rcx
0x180001e78  lea     rcx, dword_180040010
0x180001e7f  mov     [rbp+40h+var_48], 1
0x180001e87  mov     [rbp+40h+var_58], 1
0x180001e8f  mov     [rbp+40h+var_68], 1
0x180001e97  mov     [rbp+40h+var_78], 1
0x180001e9f  mov     [rbp+40h+var_88], 1
0x180001ea7  mov     [rbp+40h+var_98], 1
0x180001eaf  mov     [rbp+40h+var_A8], 1
0x180001eb7  mov     [rbp+40h+var_B8], 4
0x180001ebf  mov     [rsp+140h+var_D8], 4
0x180001ec8  mov     [rsp+140h+var_E8], 4
0x180001ed1  call    _tlgWriteTransfer_EventWriteTransfer
0x180001ed6  mov     rcx, [rbp+40h+var_10]
0x180001eda  xor     rcx, rsp; StackCookie
0x180001edd  call    __security_check_cookie
0x180001ee2  add     rsp, 140h
0x180001ee9  pop     rbp
0x180001eea  retn
```
